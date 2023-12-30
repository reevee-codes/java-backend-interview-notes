# Java Backend Notes
- ---------------------------------
<h3>Core Java</h3>
- **Generics**<br>
- **Streams**
- - **Anonymous classes**<br>
- They enable you to declare and instantiate a class at the same time. They are like local classes except that they do not have a name. Use them if you need to use a local class only once.
- **Lambda expressions**<br>
- Lambda expressions let you express instances of single-method classes.
- 
- **Optional**<br>
  may or may not contain a non-null value. If a value is present,
  `isPresent()` will return true and get() will return the value<br>
  `orElse(T other)`
     Return the value if present, otherwise return other.
-  use of identity-sensitive operations (including reference equality (==), identity hash code, or synchronization) on instances of Optional may have unpredictable results and should be avoided
