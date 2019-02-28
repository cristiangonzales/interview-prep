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


