# HTTP
## HTTP Methods
You’ve probably heard about Hypertext Transfer Protocol, also known as HTTP. 
HTTP allows you to interact with Web pages, HTML documents, and APIs. 
It is the foundation of any data exchange on the Internet. 
A typical DevOps engineer works with HTTP every day and should have a solid knowledge of this protocol.

As a DevOps engineer, you should know what an HTTP request is, the various HTTP request methods that exist, and how they are different from each other.
An HTTP request is a request message from a client to a server asking for access to a resource.
There are 7 main HTTP request methods:

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/924f1860-c015-4628-ab73-905b692e14a9)

## HTTP Response Codes
Response codes indicate whether a request was completed successfully or failed. 
You’ve probably seen them floating around in pop culture references or been on the receiving end of a hyperlink that goes nowhere.

There are 4 categories of HTTP responses:

200s: Successful responses

300s: Redirects

400s: Client errors

500s: Server errors

Take a look at some of the most common response codes:

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/e5d6761c-bd92-4f88-afe1-b3c9337c328c)

## HTTP Headers
HTTP headers allow the client to add additional information to a request for purposes such as authentication, caching, and specifying the type of client device sending the request. 
Headers are widely used to control traffic and implement features such as canary releases, blue-green deployments, and a/b testing.

Headers fall into 4 general contexts:

1. General Header: A header that works for both response and requests messages.
2. Request Header: A header that only applies to request messages from a client.
3. Response Header: A header that only applies to responses from a server.
4. Entity Header: A header that gives information about the entity itself or the resource requested.
   Headers are case-insensitive in the structure Name: Value.


## What is HTTPS?
HTTPS stands for Hyper Text Transfer Protocol Secure. 
It is highly advanced and secure version of HTTP. 
It uses the port no. 443 for Data Communication. 
It allows the secure transactions by encrypting the entire communication with SSL. 
It is a combination of SSL/TLS protocol and HTTP. It provides encrypted and secure identification of a network server.

HTTP also allows you to create a secure encrypted connection between the server and the browser. 
It offers the bi-directional security of Data. This helps you to protect potentially sensitive information from being stolen.

In HTTPS protocol SSL transactions are negotiated with the help of key-based encryption algorithm. This key is generally either 40 or 128 bits in strength.

## Key Difference between HTTP and HTTPS
HTTP lacks a security mechanism to encrypt the data, whereas HTTPS provides SSL or TLS Digital Certificate to secure the communication between server and client.
HTTP operates at the Application Layer, whereas HTTPS operates at Transport Layer.
HTTP by default operates on port 80, whereas HTTPS by default operates on port 443.
HTTP transfers data in plain text, while HTTPS transfers data in cipher text (encrypt text).
HTTP is fast as compared to HTTPS because HTTPS consumes computation power to encrypt the communication channel.

## Types of SSL/TLS certificate used with HTTPS
Now in this, we will cover the types of SSL/TLS certificates used with HTTPS:

### Domain Validation
Domain validation validates that the person who applies for a certificate is an owner of the domain name. This type of validation generally takes a few minutes up to a few hours.

### Organization Validation
The Certification Authority not only validate the domain’s ownership but also owners identify. It means that an owner might be asked to provide the personal ID proof document to prove their identity.

### Extended Validation
Extended validation is a topmost level of validation. It includes validation of domain ownership, owner identity as well as registration proof of business.
