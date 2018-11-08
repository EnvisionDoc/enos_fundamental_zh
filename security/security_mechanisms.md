# Security schemes

## Authentication

Access to the EnOS service APIs and portal require authentication. EnOS provides
integration with customers’ user registries that supports LDAP, such as Windows
Directory Server. EnOS uses several types of credentials for authentication.
These include 1) passwords, 2) cryptographic keys, 3) digital signatures, and 4)
certificates. EnOS also provides the option of requiring 5) multi-factor
authentication (MFA) to log into the portal.

## Passwords

Passwords are required to access EnOS portal. If the customer’s organizational
user registry is not used for authentication, customers may specify the password
when they first create the account, and they can change it at any time. Password
complexity policy may be applied to force users to create strong passwords that
cannot be easily guessed.

## Multi-Factor Authentication (MFA)

Multi-Factor Authentication (MFcfdA) is an additional layer of security for
accessing EnOS portal. When this optional feature is enabled, users will be
prompted to provide a six-digit single-use code in addition to user name and
password credentials before access is granted. User gets this single-use code
via SMS or email.

## Access Keys

EnOS requires that all API requests be signed—that is, they must include a
digital signature that the platform can use to verify the identity of the
requestor. Application developers calculate the digital signature using a
cryptographic hash function. The input to the hash function in this case
includes the text of request and the secret access key.

Not only does the signing process help protect message integrity by preventing
tampering with the request while it is in transit, it also helps protect against
potential replay attacks. A request must reach the EnOS services within 15
minutes of the time stamp in the request. Otherwise, the platform denies the
request.

## Key Pairs

The virtual machine instances are created with a public/private key pair rather
than a password for signing in via Secure Shell (SSH). The public key is
embedded in the virtual machine instance, and users use the private key to sign
in securely without a password.

## X.509 Certificates

X.509 certificates are used to sign SOAP-based requests. X.509 certificates
contain a public key and additional metadata (like an expiration date that EnOS
verifies when applications upload the certificate), and is associated with a
private key. When an application creates a request, it creates a digital
signature with the private key and then include that signature in the request,
along with the certificate. The EnOS verifies the sender by decrypting the
signature with the public key that is in the certificate. The platform also
verifies that the certificate the application sent matches the certificate that
are uploaded.

## Certificate Authority (CA)

EnOS has built-in industry-standard Certificate Authority service for
certificate management purpose. It provides a series of fundamental CA service
APIs, including CA setup, certificate issue, certificate renew, certificate
revoke and certificate status query. Certificates for different purposes may be
requested and issued from EnOS CA service. Corresponding operation may be
completed through API invokes in seconds. Both CRL distribution and OSCP
stapling with high availability is supported.

### Role-based Access Control

EnOS adopts Role-Based-Access-Control (RBAC) that is a policy neutral access
control mechanism defined around roles and privileges. Access control rule is
defined as a 3-tuples in the form of role-permission-resource.

Within an
organization, [roles](https://en.wikipedia.org/wiki/Role_(computer_science)) are
created for various job functions. The permissions to perform certain operations
are assigned to specific roles. Members or staff (or other system users) are
assigned particular roles, and through those role assignments acquire the
computer permissions to perform particular computer-system functions. Since
users are not assigned permissions directly, but only acquire them through their
role (or roles), management of individual user rights becomes a matter of simply
assigning appropriate roles to the user's account; this simplifies common
operations, such as adding a user, or changing a user's department.

### Network Protection

For greater communication security when accessing EnOS portal, devices and end
users must use HTTPS for data transmissions. HTTPS uses the SSL/TLS protocol,
which uses public-key cryptography to prevent eavesdropping, tampering, and
forgery. Public trusted CA issued web server certificates should be deployed to
enable this feature.

All EnOS services provide API endpoints that allow devices and end users to
establish secured communication sessions. For RESTful APIs, HTTPS is used. For
SSL/TLS protected data channel between devices and EnOS cloud cluster, X.509
certification based bidirectional authentication is adopted, all data is
encrypted during transfer.

### Data Encryption

EnOS adopts a very strict way for protecting data at rest. Sensitive data is
encrypted before putting into files or databases. Data is encrypted with a key
generated by the platform or with a key customers supply. Decryption happens
automatically when data is retrieved through the platform API. Therefore, no
intruders or platform operators will have access to the data even when they have
access to the underlying file system or database systems, unless they have
obtained the decryption keys.

### Logging and Monitoring

EnOS logs all user activities to the portal and application invokes to the
service APIs. The access log contains details about each access request
including request type, the requested resource, the requestor’s IP, and the time
and date of the request.

EnOS operation team not only monitors for cloud application performance and
resiliency, but also platform security. Centralized logging service is
configured to aggregate access logs and display security related metrics at
real-time to the operation team. Alerts are also configured to rise when defined
thresholds are met. Based on real-time monitoring and alerts, the operation can
react to security attacks and leaks very quickly.

### Auditing

EnOS security team periodically audits internal activities from the software
development team and the service operation team to ensure the IT process meets
the standard. In addition, EnOS provides customers with user activity logs
associated with their applications and users. Customers can use these logs to
decide whether users are assigned properly to roles and what kind of activity a
particular user has performed.
