# How to use the EnOS X.509 Certificate Service APIs

To use the X.509 Certificate Service, you must have a valid service account. For more information, see [Application management](https://docs.envisioniot.com/docs/app-development/en/latest/app_mgmt/app_mgmt_overview).

The rest of this article instructs how to manage X.509 certificates using REST API.

The following two APIs are relative to `https://<enos_cluster_hostname>`, where `https://<enos_cluster_hostname>` refers to the hostname of the EnOS cloud cluster instance. EnOS cloud cluster has the following instances:

- AWS-CN: `developer.envisioncn.com`
- Azure-CN: `dev.envisioncn.com`

## Retrieving root CA certificate

A root CA certificate is a certificate with the public key of the current CA. The root certificate is used to check the validity of an issued certificate.

To retrieve the root CA certificate, send the following API request:

```
GET /enos/CA/cacert
```

## Retrieving certificate revocation list

A revoked certificate is identified in the certificate revocation list (CRL) by its certificate serial number. To check whether a certificate is revoked, you'll need to retrieve the CRL and check whether the corresponding certificate serial number is on that CRL. To retrieve the CRL, call the following API periodically.

```
GET /enos/CA/crl
```

**Note**: The EnOS X.509 Certificate Service refreshes CRL at 00:00 am every day.

All URIs in the rest of the article are in relative to `https://<enos_api_hostname>` , where `<enos_api_hostname>` refers to the hostname of the **EnOS API Service** instance where your application or device connects. **EnOS API Service**  has the following instances:

- AWS-CN: `ag-cn2.envisioniot.com`
- Azure-CN: `ag-cn1.envisioniot.com`

## Getting X.509 certificate

Before getting an X.509 certificate, you need to
1. Create your key pair locally, we recommend you with the open source tool **OpenSSL**.
2. Create a CSR that is signed by your own private key.

Call the API with the following request:

  ```
  POST /enos/CA/reqCertificate
  ```

### URI parameters

   <table>
      <tr>
        <th>Name</th>
        <th>Required</th>
        <th>Type</th>
        <th>Description</th>
      </tr>
      <tr>
        <td>reqData</td>
        <td>true</td>
        <td>string</td>
        <td>Certificate signing request to get X.509 certificate, Base64 encoded, enclosed between <P>"-----BEGIN CERTIFICATE REQUEST-----"</p> and <p>"-----END CERTIFICATE REQUEST-----".<p> The request is expressed in ASN.1.</td>
      </tr>
    </table>

An example of `reqData` is shown as follows:

    -----BEGIN CERTIFICATE REQUEST-----
    MIIC3TCCAcUCAQAwgZcxCzAJBgNVBAYTAkNOMREwDwYDVQQIDAhTaGFuZ2hhaTEN
    MAsGA1UECgwERW5PUzESMBAGA1UECwwJRW5PUyBFZGdlMTEwLwYDVQQDDCgyZjQ5
    MTQ3Ny02OWM3LTQ4YWUtYmQ0Zi0zZTgwNGQ0amF1ZHVlb2FiMR8wHQYJKoZIhvcN
    AQkBFhBlZGdlLW9wQGVuaW90LmlvMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIB
    CgKCAQEAxb3fteSyiHUURhQw7NUVN4c2xeWpGKITLsTHQmwj1/l1uXamJW3UbQeE
    JcWSuCqQxUXOhsH95SLViEm04pSV/rmPTiuZnYSH9rL2wIt9cw2j0awXgVtXUY31
    1oXIVxWrOg2zoE66gGp8bsCYGM4fn+oSb1YHg52RE7qNJ7qx+QcKwAqfDNR/wGhG
    CYCygtpd2r/UrE2GRQMI+2kPgvCt/yyNpkQl+dr+ziGhDhQ+q3anheKCuGDSNz+M
    MxQC+dD3UHX9sD+e5p1OJhAdwbbCs2pc8FveoiIXc4gskXF86FKVrejyKCwyS0HW
    SrfFk3p05gWkUee2i3+K7hgzNYpFCQIDAQABoAAwDQYJKoZIhvcNAQELBQADggEB
    AEW1rFevaE4TjBh2M7Vuel4h54DapOdrhOoNsTDrGHR0ykN0tKYKcplO0l3i1RLO
    JqEm2o5iUZ4w992ESKCiC6tbm+n8NeQE/dKhJpAix30i4WdRkdSiW0cz12BkvXw3
    5a3tlEboefrjVwG4jxWY3zNV/h3uLUh+CMDLtU3A4nxJphFJVh8vu5/+jI0Fb87j
    DNHvWvefYSxFNHqDR1zBYZPkfPPL+ULxsZkXjMSo3DmbYiPl46F0j7ANucXinWPD
    NhXXvqx62VjYxpY4HHYZoARMeJojFOCMAAT2Ld+3ojRc9L542vhzIJib7pGwowYe
    kwm6LSi1HWA58ocRUbY4E1M=
    -----END CERTIFICATE REQUEST-----


For how to add common REST request parameters in the request body to verify the identity and integrity, refer to the tutorial [EnOS APIs](https://docs.envisioniot.com/docs/enos-tutorials/en/latest/application_development/try/module_4.html). For details about the API parameters, please refer to **EnOS Portal > API Service > Public API**.
<!--@huangzhi, are the APIs available as part of public API now? Are you sure the link is correct? This is a tutorial. -->

## Revoking X.509 certificate

An issued certificate is expected to be in use for its entire validity period. However, under some circumstances, including change of name, change of association between subject and CA (e.g., an employee terminates employment with an organization), and compromise or suspected compromise of the corresponding private key, you need to revoke the certificate.

Call the API with the following request:

  ```
  POST /enos/CA/revokeCertificate
  ```

### URI parameters

<table>
  <tr>
    <th>Name</th>
    <th>Required</th>
    <th>Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>issuedCertSN</td>
    <td>true</td>
    <td>int</td>
    <td>The serial number of the issued certificate.</td>
  </tr>
</table>

For how to add common REST request parameters in the request body to verify the identity and integrity, refer to the tutorial [EnOS APIs](https://docs.envisioniot.com/docs/enos-tutorials/en/latest/application_development/try/module_4.html). For details about the API parameters, please refer to **EnOS Portal > API Service > Public API**.
<!--@huangzhi, are the APIs available as part of public API now? Are you sure the link is correct? This is a tutorial. -->
