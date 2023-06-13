# How to make a Secure API

## Contents
  - [Authenticate and authorize](#authenticate-and-authorize)
  - [Implement access control](#implement-access-control)
  - [Encrypt requests and responses](#encrypt-requests-and-responses)
  - [Record APIs in an API registry](#record-apis-in-an-api-registry)

## Authenticate and authorize
Authentication and authorization are two important aspects of making an API safer. Authentication is the process of verifying the identity of a user or an app that wants to access the API, while authorization is the process of determining what level of access they have to the API resources¹.

Authentication helps prevent unauthorized or malicious access to sensitive data, such as personal information, financial transactions, or confidential documents. Authentication can be done using various methods, such as username and password, certificates, tokens, or single sign-on (SSO) protocols¹²⁴.

Authorization helps enforce the access policy of the API, which defines who can view or modify data on the server. Authorization can be done using a token-based protocol such as OAuth 2.0, which restricts the actions that a client app can perform on behalf of the user without sharing their credentials²³. OAuth 2.0 can also be combined with OpenID Connect (OIDC), which provides user authentication and SSO functionality³.

By using authentication and authorization, an API can ensure that only legitimate and authorized users or apps can access its data and functionality, thus reducing the risk of data breaches, identity theft, or abuse of the API⁴⁵⁶

Sources:
- (1) API Authentication: What Is It? | DreamFactory Software- Blog. https://blog.dreamfactory.com/api-authentication-what-is-it/.
- (2) Best practices for REST API security: Authentication and authorization .... https://stackoverflow.blog/2021/10/06/best-practices-for-authentication-and-authorization-for-rest-apis/.
- (3) API authentication and authorization best practices | Synopsys. https://www.synopsys.com/blogs/software-security/api-authentication-authorization-best-practices/.
- (4) API authentication and authorization - Overview - Azure API Management .... https://learn.microsoft.com/en-us/azure/api-management/authentication-authorization-overview.
- (5) Authentication and authorization in minimal APIs | Microsoft Learn. https://learn.microsoft.com/en-us/aspnet/core/fundamentals/minimal-apis/security?view=aspnetcore-7.0.
- (6) Authentication and Authorization to Secure API | Devoteam. https://nl.devoteam.com/expert-view/authentication-and-authorization-to-secure-apis/.

## Implement access control

Implementing access control is a key way to make an API safer. Access control is the process of verifying and enforcing the permissions of users or apps that want to access the API resources¹. Access control helps prevent unauthorized or malicious access to sensitive data or functionality, such as personal information, financial transactions, or confidential documents.

One of the common methods to implement access control is using role-based access control (RBAC), which allows users or groups to have specific permissions based on their roles¹². RBAC can be implemented using app roles, groups, or custom data stores². App roles are defined in the application registration and assigned to users or groups, and then accessed in the tokens coming into the application². Groups are used to assign users or groups to predefined roles, and then accessed in the tokens coming into the application². Custom data stores are used to retrieve and interpret role assignments using logic within the application².

Another common method to implement access control is using OAuth 2.0, which is a standard authorization framework that restricts the actions that a client app can perform on behalf of the user without sharing their credentials¹³. OAuth 2.0 can also be combined with OpenID Connect (OIDC), which provides user authentication and SSO functionality³.

By implementing access control, an API can ensure that only legitimate and authorized users or apps can access its data and functionality, thus reducing the risk of data breaches, identity theft, or abuse of the API³ .

Source: Conversation with Bing, 13/06/2023
- (1) Implement role-based access control in applications - Microsoft Entra. https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-implement-rbac-for-apps.
- (2) Overview of API Access Control and implementing API key access control .... https://community.f5.com/t5/technical-articles/overview-of-api-access-control-and-implementing-api-key-access/ta-p/295747.
- (3) 12 API security best practices to protect your business. https://www.techtarget.com/searchapparchitecture/tip/10-API-security-guidelines-and-best-practices.

## Encrypt requests and responses

Encrypting requests and responses is a vital way to make an API safer. Encryption is the process of transforming data into an unreadable form using a secret key, so that only authorized parties can access it. Encryption helps protect the information that the API sends and receives from eavesdropping, tampering, or modification by third parties.

One of the essential methods to encrypt requests and responses is using TLS (Transport Layer Security), which is a protocol that secures the communication between the client and the server. TLS encrypts the messages while they are in transit, so that no one can intercept and read sensitive information, such as API credentials and private data²³. TLS also verifies the identity of the server using certificates, which prevents impersonation or spoofing attacks².

Another method to encrypt requests and responses is using a symmetric encryption algorithm, such as AES (Advanced Encryption Standard), which uses the same key to encrypt and decrypt data. This method requires generating a random symmetric key and an initialization vector (IV), which are used to encrypt the request and response data¹. The encrypted data, along with the key and IV, are then sent in the header of the HTTP request or response¹. The receiver can use the same key and IV to decrypt the data and access the original information¹.

By encrypting requests and responses, an API can ensure that only legitimate and authorized parties can access its data and functionality, thus reducing the risk of data breaches, identity theft, or abuse of the API²³.

Source: Conversation with Bing, 13/06/2023
(1) Best practices for REST API security ... - Stack Overflow Blog. https://stackoverflow.blog/2021/10/06/best-practices-for-authentication-and-authorization-for-rest-apis/.
(2) 12 API security best practices to protect your business. https://www.techtarget.com/searchapparchitecture/tip/10-API-security-guidelines-and-best-practices.
(3) How to Encrypt WEB API request and response using PyCryptodome. https://learn.microsoft.com/en-us/answers/questions/1167267/how-to-encrypt-web-api-request-and-response-using.

## Record APIs in an API registry

Share only necessary information. 


