X.509 Certificate Service in EnOS
=================================

EnOS provides the X.509 Certificate Service to enforce X.509 certificate-based bi-directional authentication for all communication sessions between the EnOS Edge and IoT Hub.

In cryptography, X.509 is a standard that defines the format of the public key certificate, which is an electronic document used to prove the ownership of a public key. X.509 certificate is defined by the `RFC5280 <https://tools.ietf.org/html/rfc5280>`__ standard. X.509 certificates are issued by a trusted entity of Public-key Infrastructure (PKI) called Certification Authority (CA).

Certificate-based authentication has the following benefits over other identification and authentication mechanisms.

- Asymmetric keys, which ensure that sensitive cryptographic material never leaves the devices

- Stronger client authentication

There are several concepts you need to know before you start to use the X.509 Certificate Service:

- **Public-key Infrastructure (PKI)**, is a set of roles, policies, and procedures that are needed to create, manage, distribute, use, store, and revoke digital certificates and manage public-key encryption.
- **Certification Authority (CA)**, is an entity that issues digital certificates.
- **Certificate signing request (CSR)**, is a message sent from the certificate applicant to the certificate authority to apply for an X.509 certificate.
- **Certificate Revocation List (CRL)**, is a time-stamped list that maintains the revoked certificates of the CA.

EnOS X.509 Certificate Service provides the following functions:

- Retrieving root CA certificate
- Retrieving certification revocation list
- Getting X.509 certificate
- Revoking X.509 certificate


There functions are available through REST APIs.

.. toctree::
   :maxdepth: 1

   using_ca_service_api
   secure_communication_iothub
