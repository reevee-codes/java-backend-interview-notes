# Java Backend Notes

- ---------------------------------
<h3>Core Java</h3>

- **Generics**<br>

-
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
  -- **Streams**
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
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>
- **How to make class immutable?**<br>