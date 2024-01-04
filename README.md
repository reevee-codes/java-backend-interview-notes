# Java Backend Interviews notes

- ---------------------------------
<h3>Core Java</h3>
- **Access modifiers**<br>
  public: visible in class, subclass, package, global <br>
  protected: visible in class, subclass, package (protected from global) <br>
  default: visible in class, package <br>
  private: visible in class <br>
- **Exceptions**
  A checked exception is caught at compile time whereas a runtime or unchecked exception is checked at runtime.<br>
  Checked: IOException, SQLException, FileNotFoundException, ClassNotFoundException <br>
  Unchecked: NPE, ArrayIndexOutOfBonds, ArithmeticException
- **OOP concepts**
- inheritance, encapsulation, polymorphism, and abstraction
- **interface vs abstract class**
  Abstract class is a class with partial implementation while interface is a contract with no implementation.
  Abstract class can have both abstract and non-abstract methods while interface can only have abstract methods.
  (java 9 - interfaces can have private methods, java 8 - static and default methods)
  A class can implement multiple interfaces but can only inherit from one abstract class.
  Abstract class can have constructors while interface cannot but Abstract class also cant be instantiated.
  Abstract class can have access modifiers while interface methods are public by default.
- **Array**<br>
- **Array**<br>
- Starts on 0, but length is normal, so for indexes 0, 1, 2 your length of array 3
- **Generics**<br>

- **Autoboxing Unboxing**<br>
- **Anonymous classes**<br>
- They enable you to declare and instantiate a class at the same time. They are like local classes except that they do not have a name. Use them if you need to use a local class only once.
- While local classes are class declarations, anonymous classes are expressions, which means that you define the class in another expression.
- **Functional programming**<br>
- avoiding changing-state and mutable data
- more concise code
- encourages immutability
- Parallel and Concurrent Programming and shared data is managed safely (
  `Parallel` - tasks literally run at the same time, e.g., on a multicore
  processor, `Concurrent` - when two or more tasks can start, run, and complete in
  overlapping time periods. It doesn't necessarily mean they'll ever both be running at
  the same instant. For example, multitasking on a single-core machine.)
- Higher-Order Functions: pass functions as arguments and return
  functions from other functions
- Declarative Approach: You describe what your code should achieve, rather
  than listing the steps to achieve it
- **Lambda expressions**<br>
- Lambda expressions let you express instances of single-method classes.
-  external variables used inside a lambda must be effectively final (Forcing the variable to be final avoids giving the impression that modifying the variable inside the lambda could actually modify the method parameter + concurrency issues)<br>
   `Supplier<Integer> incrementer(int start) {`\
   `return () -> start++;`\
   `}`\
   The lambda is capturing the value of start, meaning making a copy of it. Forcing the variable to be final avoids giving the impression that incrementing start inside the lambda could actually modify the start method parameter.
- **Streams**
- **Optional**<br>
  may or may not contain a non-null value. If a value is present,
  `isPresent()` will return true and get() will return the value<br>
  `orElse(T other)`
  Return the value if present, otherwise return other.
- use of identity-sensitive operations (including reference equality (==),
  identity hash code, or synchronization) on instances of Optional may have
  unpredictable results and should be avoided
- **How to make class immutable?**<br>
- The class must be declared as final so that child classes can’t be created.
- Data members in the class must be declared private so that direct access is not allowed.<br>
- Data members in the class must be declared as final<br>
- A parameterized constructor should initialize all the fields performing a deep copy so that data members can’t be modified with an object reference <br>
  Deep Copy of objects should be performed in the getter methods to return a copy<br>
- **Effectively final**<br>
In Java 8, all variables are final by default.<br>
`int variable = 123;`<br>
Any variable that is assigned once and only once, is "effectively final".
- --------------------------------------------------------
<h3>Spring</h3><br>
- **Bean scopes**<br>
- singleton - (Default) Scopes a single bean definition to a single object instance for each
  Spring IoC container<br>
- prototype - Scopes a single bean definition to any number of object instances.<br>
- request - Scopes a single bean definition to any number of object instances.<br>
- session - Scopes a single bean definition to the lifecycle of an HTTP Session. Only valid
  in the context of a web-aware Spring ApplicationContext.<br>
- application - Scopes a single bean definition to the lifecycle of a ServletContext.<br>
- websocket - Scopes a single bean definition to the lifecycle of a WebSocket.<br>
- **Filters**<br>
- filters intercept and process incoming HTTP requests and outgoing HTTP responses. They are executed in a specific order, allowing each filter to perform its designated task
- Some of the most used Spring filters are AbstractRequestLoggingFilter (to perform logging operations before and after a request is processed), CharacterEncodingFilter (to specify a character encoding for requests), and CorsFilter (to handle CORS pre-flight requests and to update the response) (CORS - http header that enables scripts running on a browser client to interact with resources from a different origin)
- --------------------------------------------------------
<h3>Internet</h3>
- **Cookies**<br>
-  quite limited compared to some modern alternatives to storing data in the browser like localStorage or sessionStorage (4KB)
- your ally.com cookie will work on ally.com, ally.com/about, and the subdomain ally.com, but not axos.com
- cookies are meant to be openly read and sent, so you should never store sensitive information like passwords in them
- your cookies are sent with every request you make in the browser. This is very convenient, but has some serious security implications
- **What are the things present in HTTP response?**<br>
-  HTTP response: contains a status line, a header ( a request message can use headers to indicate it's preferred media formats, while a response can use header to indicate the media format of the returned body), and a message body
- **How to get HTTPS certificate**<br>
1. Create a private and public key pair, and prepare a Certificate Signing Request (CSR), including information about the organization and the public key. <br>
2. Contact a certification authority and request an HTTPS certificate, based on the CSR.<br>
- **How does HTTPS work?**<br>
1. When you enter a URL, the server of that website sends its public key and a certificate to your browser.
2. communication over secure SSL/TLS connection
3. Even if the packets are intercepted, they will come across as nonsensical characters
4. Decryption: The private key on the server-side is used for the decryption of the data that has been encrypted by the public key
- ---------------------------------
<h3>HTTP Methods (http verbs)</h3>
GET - retrieves data <br>
HEAD - response like get but without response body<br>
POST -  submits an entity to the specified resource<br>
PUT -  replaces all current representations<br>
DELETE -  deletes the specified resource<br>
CONNECT -  establishes a tunnel to the server identified by the target resource<br>
OPTIONS - describes the communication options for the target resource<br>
TRACE - performs a message loop-back test along the path to the target resource<br>
PATCH - applies partial modifications to a resource<br>
POST vs PUT vs PATCH -  PUT is used for creating or replacing resources, POST is used for creating or appending data to resources, and PATCH is used for partially updating existing resources
- ---------------------------------
<h3>HTTP 1 vs HTTP 2 vs HTTP 3</h3>
HTTP1 - web browser makes several parallel requests for page contents: HTML, images, style, JS<br>
HTTP2 - web browser makes one TCP connection with requests for all page contents in streams (binary)<br>
HTTP3 - web browser makes one QUIC connection with requests for all page contents in QUIC streams (binary)<br>
- ---------------------------------
<h3>HTTP 2.0</h3>
HTTP/2 is binary instead of textual.
HTTP/2 is fully multiplexed.<br>
This means that HTTP/2 can send multiple requests for data in parallel over a single TCP connection. This is the most advanced feature of the HTTP/2 protocol
because it allows you to download web files via ASync mode from one server.
Most modern browsers limit TCP connections to one server.
- ---------------------------------
<h3>HTTP 3.0</h3>
Unlike previous versions which relied on theTCP, HTTP/3 uses QUIC, a transport protocol built on UDP.<br>
The same request methods, status codes, and message fields, but encodes them and maintains session state differently<br>
due to the protocol's adoption of QUIC, HTTP/3 has lower latency and loads more quickly in real-world usage when compared with previous versions: in some cases over 3× faster than with HTTP/1.1<br>
- ---------------------------------
<h3>HTTP Codes</h3>
Informational responses (100 – 199)<br>
Successful responses (200 – 299)<br>
Redirection messages (300 – 399)<br>
Client error responses (400 – 499)<br>
Server error responses (500 – 599)<br>

<b>Informational responses</b><br>
100 Continue (the client should continue the request)<br>

<b>Successful responses</b><br>
200 OK<br>
201 CREATED<br>
202 Accepted<br>
204 No content<br>

<b>Redirection messages</b><br>
301 Moved permanently

<b>Client error responses</b><br>
400 Bad request (client error - malformed request syntax)<br>
401 Unauthorized<br>
403 Forbidden (client does not have access rights to the content)<br>
404 Not Found (server cannot find the requested resource)<br>
418 Im a teapot (server refuses the attempt to brew coffee with a teapot)<br>

<b>Server error responses</b><br>
500 Internal server error (server has encountered a situation it does not know how to handle)<br>
501 Not Implemented (The request method is not supported by the server and cannot be handled. The only methods that servers are required to support (and therefore that must not return this code) are GET and HEAD.)<br>
502 Bad Gateway (the server, while working as a gateway to get a response needed to handle the request, got an invalid response)<br>
503 Service Unavailable (the server is not ready to handle the request)<br>
- ---------------------------------
<h3>FTP</h3>
The ftp command opens the user interface to the Internet's File Transfer Protocol.<br>
This user interface, called the command interpreter, enables you to log in to a remote system and perform a variety of operations with its file system.<br>
- opens 2 connections, one is used to send commands, other is for sending data. commands are “send,” “get,” “change directory,” and “transfer.”
- uses three different modes: block, stream, and compressed. can perform perform large file size transfers.
- allows you to send multiple files at once.
- ---------------------------------
<h3>SSH</h3>
a network protocol that allows two devices to communicate and share data remotely over an unsecured network, like the Internet. The primary difference between Secure Shell Protocol and other login protocols is that SSH provides an encrypted connection.
- ---------------------------------
<h3>SFTP</h3>
Extension of SSH.<br>
FTP stands for File Transfer Protocol, while SFTP refers to Secure Shell (SSH) File Transfer Protocol. This gives you file transfers that are secured via SSH, which provides full access to shell accounts. A shell account is
one that sits on a remote server.SFTP uses a tunneling method to transfer data. With the benefit of additional security, FTP, which is less secure, uses direct transfer.

- --------------------------------
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **Check prime number**<br>
  `public boolean isPrime(int number) {`<br>
  `BigInteger bigInt = BigInteger.valueOf(number);`<br>
  `return bigInt.isProbablePrime(100);`<br>
  `}`<br>
  <h3>Spring Security</h3><br>
- **Bearer vs JWT Token**<br>
- Bearer tokens (access tokens) do not carry any specific information. Once validated, the server returns user information and permissions. require frequent communication with the server for each request. Can be easily revoked (advantage), but authorization server may face scalability issues when handling large number of bearer tokens
- JWT tokens (JSON Web Tokens) carry all the necessary information within the token itself. This includes details such as the token's issuer, expiration time, permissions, and user profile, eliminating the need for frequent communication with the authorization server for validation.
- **Hashing passwords**<br>
- Bcrypt + salting (random piece of data is added to the password before it runs through the hashing algorithm, making it unique and harder to crack)
- To verify file signatures and certificates - SHA-256
- pepper - while a salt is not secret (merely unique) and can be stored alongside the hashed output, a pepper is secret and must not be stored with the output
- - --------------------------------------------------------
- <h3>ACID</h3>