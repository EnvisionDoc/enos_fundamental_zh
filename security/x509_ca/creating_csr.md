## Creating your Certificate Signing Request (CSR) file

To obtain an X.509 certificate from the EnOS CA, you need to create a CSR file in your device or application.

The following procedure uses  _OpenSSL_ as an example to create a CSR:

1. Generate a key pair.
    ```
    openssl genrsa -out <key_name>.key 2048
    ```
    **Note**: You **MUST** use RSA algorithm with 2048 bits to generate the key pair. `<key_name>` is the name of the key, for example, `deviceCert.key`.

2. Create a CSR for the your device or application.
    ```
    openssl req -new -key <key_name>.key -out <csr_name>.csr -sha256
    ```
    **Note**: The `<key_name>.key` file is the key that you generated in step 1 and `<csr_name>` is the csr file name, for example, `deviceCert.csr`.

    You will be prompted with information as follows:
    ```
    Country Name (2 letter code) [AU]:
    State or Province Name (full name) []:
    Locality Name (for example, city) []:
    Organization Name (for example, company) []:
    Organizational Unit Name (for example, section) []:
    Common Name (e.g. server FQDN or YOUR name) []:
    Email Address []:
    ```

**Note**: You MUST follow the rules defined by CA:

1. All the subject fields except `Email Address` are required.
2. Ensure that the subject fields `Country Name (C)`, `State or Province Name (ST)`, and `Organization Name (O)` are consistent with the CA root certificate.
