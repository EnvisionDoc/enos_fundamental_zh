# How to get root CA certificate and CRL

The APIs to get root CA certificate and CRL are open to public.

The following two APIs are relative to `https://<enos_cluster_hostname>`, where `https://<enos_cluster_hostname>` refers to the hostname of the EnOS cloud cluster instance. EnOS cloud cluster has the following instances:

- AWS-CN: `https://developer.envisioncn.com`
- DECADA: `https://portal-decada1.envisioniot.com`

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
