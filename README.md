# Java Backend Notes

- ---------------------------------
<h3>Core Java</h3>

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
<h3>Internet</h3>
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