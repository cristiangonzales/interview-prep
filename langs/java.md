Java nuances in deep detail
---
### JRE (Java Runtime Environment)
* Runtime environment where Java bytecode can be executed
* Software package that contains what is required to run a Java program
* *Implements* JVM and provides libraries and files for JVM at runtime

### Java Virtual Machine (JVM)
* *Specification* for runtime environment
* Specification: describes the implementation of the JVM
* Implementation: Program that meets requirements of the JVM specification
* Runtime instance: instance of JVM is created whenever you write a java command on the command prompt

### Java Development Kit (JDK)
* Necessary to compile/package Java programs
* Along with the JRE, includes compiler, interpreter/loader, archiver, document generator

### Good way to think about it: JVM ⊂ JRE ⊂ JDK

### Explain `public static void main(String args[])`
* `public`: defines visibility, accessible by any class
* `static`: class-based
* `main`: name of method searched for by JVM as a starting/entry point for application for a particular function signature
* `String args[]`: paramater passed to the main method (`args` is just a convention, this string array can be named anything)

---

* Java is *Write once read anywhere (WORA)* because bytecodes can run on any system, with no recompilation
* Java is *not* 100% object oriented because its primitive data types are not objects
* *Wrapper classes* converts Java primitive types into reference types (objects)
  * e.g.: `Integer(5)` => `int`
* A *constructor* is a block of code used to initialize an object. There are two types.
  1. Default constructor
  2. Parameterized constructor
* A *singleton class* instance can only be created/instantiated once any time in one JVM instance
  * We make the visibility of the constructor of the singleton class `private` to create it as a singleton class
* The builtin `equals()` method compares the *values* of two *objects*, `==` compares primitive types and objects

---
### Stack versus Heap Memory

| Features | Stack Memory | Heap Memory |
| --------|---------|-------|
| Usage | Contains local primitive and reference variables to objects in heap space | Whenever an object is created, it is always stored in heap space |
| Memory  | Used by only one thread of execution | Used by all parts of the application |
| Access  | Can't be accessed by other threads | Objects stored in heap memory are globally accessible |
| Memory Management  | Follows LIFO to free memory | Based on generation associated with each object |
| Lifetime | Exists until the end of the execution thread | Lives from the start to the end of application execution |

---
* *Compile-time polymorphism*: method overloading
* *Run-time polymorphism*: method overriding, inheritance, interfaces
  * Call to an overriden method is resolved at runtime rather than compile time (overridden method is called through reference variable of a superclass)

---
### Abstract Classes versus Interfaces
| Abstract Classes | Interfaces |
| --------|---------|
| Can provide complete code or just details to be overridden | Interface provides no code, just the function signature |
| A class may extend only one abstract class | A class may implement several interfaces |
| Abstract classes can have non-abstrct methods | All methods of an interface are abstract |
| *Can* have instance variables | *Cannot* have instance variables |
| Visibility: `public`, `private`, `protected` | Visibility: `public`, or none |
| If we add a new method to an abstract class then we can provide default implementation to extended classes of the abstract class | If a new method is added to an interface, we have to track down all implementations and define the new method |
| *Can* contain constructors | *Cannot* contain constrcutors |
| Abstract classes are fast | Interfaces are slow as you have to find the corresponding methods in the implementation class(es) |

---
### Method Overloading
* Methods of same class share same name but function signature of each method *must* have have different number of parameters, and the paramaters must have different types/order
* Overloading adds/extends more functionality to the method's existing behavior
* Method overloading is *compile-time* polymorphism
* You may or may not need to use inheritance in method overloading

### Method Overriding
* Subclass has *same* method with name and function signature as its super class
* Intended to change existing behavior of method
* Runtime polymorphism
* *Always* requires inheritance

---
* You cannot override a *private* or *static* method in Java
* Java doesn't support multiple inheritance (diamond problem)
  * Compiler has hard time deciding which method to execute from child class
* *Association*: all objects have their own lifestyle and there is no owner
  * *Aggregation*: all objects have their own lifestyle but there is ownership and child object *cannot* belong to another parent object
  * *Composition*: child object does not have their lifecycle and if the parent object is deleted, all child objects of that parent will be deleted

---
### JDBC (Java DB Connectivity) Driver
* JDBC – ODBC bridge driver
* Native API driver
* Network Protocol driver
* Thin driver

### Connecting to a DB
1. Registering the driver class
2. Creating connection
3. Creating statement
4. Executing queries
5. Closing connection

### `DriverManager` class
* Manages registered drivers
* Factory method that returns instance of `Connection`

### Misc. DB functions
* `ResultSet()`: Row of a table
* `execute()`
* `executeQuery()`
* `executeUpdate()`

---

### Difference between *Error* and *Exception*
* *Error*: irrecoverable condition that occurs at runtime (execution of application will come to a halt)
* *Exception*: occurs because of bad input or human error (possible to recover from an exception in most cases)

---
* Keywords: `try`, `catch`, `finally`, `throw`, `throws` (know what each one does)
* *Checked* exception: classes that extend the `Throwable` class (except `RuntimeException` and `Error`) are checked at compile time
* *Unchecked* exception: classes that extend `RuntimeException` are *not* checked at compile time
* `final`: `final` class can't be inherited, `final` method can't be overridden, and `final` variable can't be changed
* `finally`: executed code whether an exception is handled or not (will not be called in the case of a system exit or fatal error)
* `finalize()`: used to perform clean up processing just before an object is garbage collected; called by the garbage collector on an object when there are no more references to the object

---
### `throw` versus `throws`
| `throw` | `throws` |
| --------|---------|
| Throw an exception (only one) | Declare an exception (multiple OK) |
| Checked exceptions *cannot* be propogated with `throw` | Checked exceptions *can* be propogated with `throws` |
| Followed by an instance | Followed by a class |
| Used within a method | Used in method signature |

---
### Thread versus process
|  | Process | Thread |
| --------|---------|---------|
| Definition | An executing instance of a program | Subset of a process |
| Communication | Processes use interprocess communication to talk to other processes | Threads can communicate with other threads of its process |
| Control | Can only exercise control over child processes | Can exercise control over threads of the same process |
| Changes | Changes in parent process does *not* affect child processes | Changes in main thread may affect behavior of other threads in process |
| Memory | *Seperate* memory spaces | *Shared* memory spaces |
| Controlled by | OS | Programmer in a program |
| Dependence | Independent | Dependent |

### Synchronization (multithreading)
* Synchronized block of code can be executed by only one thread at a time
* Synchronization keeps all concurrent threads in execution to be in sync
* Avoids memory consistency errors due to inconsistent view of shared memory
* When method is declared synchronized, the thread holds the monitor for that method's object

---
### Variable scope
* Member variables – class level
* Local variables – method level
* Loop variables – block scope

---
* `this` – reference to the current object within instance method/constructor
* `Object` class: superclass for every class
* The main method can be overloaded, but the JVM loocks for the function signature, so we still need to have the original one there
* Object cloning is creating an exact copy of the original object (to use, you must implement the `Cloneable` interface and override `clone()` method from `Object` class)
* More on inheritance
  * Members of grandparent class are not directly accessible
  * Protected members of class A are accessible in other class B of same package, even if B doesn't inherit from A
  * Private members of base class are not accessible by children
  * Methods are virtual by default
  * Default constructor of parent class is automatically called, but if we want to call parameterized constructor we must use `super()`

* Blank final variables are not initialized during declaration
* Functions cannot be overloaded if they differ only in return type, since the return type is not part of the mangled name which is generated by the compiler for identifying each function
* `super` refers to parent class objects
  * parent instance variable
  * parent class method
  * parent constructor

---
### `HashMap` versus `HashTable`
* `HashMap` => non-synchronized/not thread safe
* `HashMap` allows one null key and multiple null values, and `HashTable` allows none of these
* `HashMap` is preferred if thread synchronization is not needed

---
### `Set` versus `List`
* Both part of the `Collection` interface
* `List` can hold duplicate values but `Set` doesn't allow this
* `List` => order preserved
* `Set` => order *not* preserved

---
* Java source code compiles to byte code, and the JVM turns this bytecode into machine code
* Strings in Java are immutable primitive types, `StringBuffer` is a mutable data structure
