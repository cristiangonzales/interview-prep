Interview Questions
---
* Differences between top 3 PLs
* Difference between a thread and a process?
* Difference between an abstract class and an interface?
* Internship/project experience
   * Projects you did at work
   * Describe a time where a customer asked for another feature. What did you do?
   * Describe a time where you had a project and you got stuck with a bug. What did you do?
* What area do you want to work in?
* Why Microsoft?
* Explain \_\_\_\_\_\_\_\_ to a five year old.
* How would you design a vending machine?

Interview must-dos
---
* Mock interviews
  * Phone screening with headset/speaker (setup environment)
  * Whiteboard questions
  * Rehearse stories from interview prep grid
* Write thank you letter/email to your recruiter after the interview
* Do heavy research on the tech of the company

Tell me about yourself...
---


Questions to ask the interviewer
---
* Why do you work at Microsoft?


Tools
---
### Docker
### Git
* Git is a distributed VCS that allows you to track changes and revert to previous changes
* Does not rely on central server to store all versions
* Every developer clones a local copy of the repo (hence, making it distributed)
* There is one central repo/Git server to commit changes
* Commit objects contain
  * Set of files
  * Reference to parent commit object
  * SHA1 name, a 40-character string that uniquely identifies the commit object

Languages (similarities and differences)
---
### Java
* **Type system:** Strong, Static
* **Paradigms supported:** Object-oriented, structured, imperative, generic, concurrent
* **Nuances:**
   * Compiled
   * General purpose
   * Cross-platform (WORA)
   * Class based objects
   * Compiler implementation: JIT
   * JVM ⊂ JRE ⊂ JDK
   * Not 100% object oriented (primitve data types not objects)
   * Compile time polymorphism: method overloading
   * Runtime polymorphism: inheritance/interface, method overriding
   * Automatic memory management
   * Performance: Worse than C/C++
   * Syntax: Influenced by C++, generics

### C
* **Type system:** Weak, Static
* **Paradigms supported:** Imperative, structured
* **Nuances:**
   * Compiled
   * General purpose
   * Cross-platform
   * Preprocessor performs macro definition, source code file inclusion, and conditional compilation
   * Ad hoc runtime polymorphism: function & data pointers
   * Static, automatic, and dynamic memory management
   * Data types
    * Pointers
    * Arrays
   * Performance: Excellent above other programming languages
   * Syntax: Influenced by ALGOL 68, FORTRAN, Assembly
   * Uses: Systems programming, operating systems, embedded systems, website programming, compilers, libraries, interpreters

### Python
* **Type system:** Weak, Dynamic, Duck
* **Paradigms supported:** Functional, imperative, Object-oriented, reflective
* **Nuances:**
   * Interpreted
   * General purpose
   * Functions and classes are first-class objects
   * Extensible and modular
   * Whitespace indentation as delimiters
   * Automatic memory management
   * GIL does not allow for *true* multithreading
   * Uses: Scripting, scientific computing, AI, information security

### SQL
* **Type system:** Strong, Static
* **Paradigms supported:** Declarative, procedural
* **Nuances:**
   * Cross platform
   * Inspired by Edgar Codd's relational model
   * Specifically designed to query data contained in a relational database
   * Set based, not an imperative programming language
    * Based on relational algebra and tuple relational calculus
   * SQL can be thought of as "sublanguages"
    * Data query language (DQL)
    * Data definition language (DDL) (schema creation/modification)
    * Data control language (DCL)
    * Data manipulation language (DML) (insert/update/delete)
   * Procedural/object-oriented programmability available through DBMS integration with other languages
   * SQL implementations are largely incompatible between vendors (PostgreSQL strives to stay compliant with ANSI/ISO standards)
    * Including but not limited to: date/time syntax, string concatenation, `NULL`s, comparison case sensitivity

### CSS
* Style-sheet language (not Turing-complete) designed to enable separation of presentation and content
  * Content accessibility
  * Flexibility in specification of presentation characteristics
  * Enable web pages to share formatting, reducing complexity
* The same markup page can be presented in different styles for different rendering methods
* MIME type: `text/css`
* *Cascading* because the priority scheme in place to determine which style rule applies if there is more than one rule match
* Aside from HTML, CSS also supports the following markup languages
  * XHTML
  * Vanilla XML
  * SVG
  * XUL

### HTML
* Markup language (not Turing-complete) that is the standard for creating web pages/applications
* Describes structure of web page semantically
* Can embed programs written in a scripting language (e.g. JavaScript) to make the page dynamic, and CSS definees the aesthetics/layout of content

### JavaScript
* **Type system:** Dynamic, Duck
* **Paradigms supported:** Event-driven, functional, imperative, object-oriented
* **Nuances:**
   * Interpreted
   * Prototype based objects
   * Ran in JavaScript runtime environments (e.g. engines of web browsers)
    * Processes messages from a queue until the event loop has terminated
    * Program I/O performed using events and callbacks
   * Enabled both client-side (web browsers) and server-side (web servers)
   * Functions are first class objects
   * Functions = methods (this isn't necessarily the case in C)
   * Functions double as object constructors
   * Objects are associative arrays
   * Uses prototypes for inheritance
   * Supports function-based implementations of Role patterns
   * Supports anonymous and variadic functions
   * Performance limitations due to dynamic nature, though JavaScript engines have become increasingly fast
   * Security issues
    * Cross-site scripting
    * Misplaced trust in clients and developers
    * Sandbox implementation errors
    * Browser and plugin coding errors
   * Uses:
    * Client and server-side web development
    * Embedded scripting (e.g. Chrome extensions)
    * Application platforms (e.g. Apache Cordova, ActionScript)
    * Scripting engines (e.g. Microsoft's Active Scripting)

### Shell
* Different dialects
  * Bash (Bourne Again Shell) (`bash`)
  * Bourne shell (`sh`)
    * Influenced by ALGOL
  * C shell (`csh`)
  * KornShell (`ksh`)
  * Secure Shell (`ssh`)
* Convenient variation of a system command––new script to act as a normal Unix command
* Batch jobs (several commands to be executed automatically that normally would be entered one at a time)
  * *Generalization*: using loop, control flow constructs to add more flexibility
* *Verisimilitude*: Invocation of the interpreters for each shell dialect is handled by an operating system feature
* Little/no support for type systems, classes, threading, complex math
* Slower than compiled or interpreted languages

### Swift
* **Type system:** Static, Strong
* **Paradigms supported:** protocol-oriented, object-oriented, functional, imperative, block structured
* **Nuances:**
  * Compiled
  * Largely influenced by Objective-C
    * Dynamic dispatch
    * Late binding
    * Extensible programming (applied to types, structs, classes)
    * Protocols, closures, and categories kept from Objective-C
  * Syntactic sugar (contrast from Objective-C)
  * Access control: `open`, `public`, `internal`, `fileprivate`, `private`
    * Ignores inheritance hierarchies
  * Option types allow for references to behave like C (e.g. a pointer may refer to a value or null)
    * Optional chaining is offered by the language to test if the instance is nil and unwrap it if the value is non-null
  * Does not expose pointers and unsafe accessors to programmers (in contrast to Objective-C)
  * Pass-by-reference for objects (pointers are copied around to access the object on the heap), pass-by-value for basic types
   * Swift allows support for both with `class` declarations (pass-by-reference) and `struct` declarations (pass-by-value)
   * Using value types and copy-on-write for objects allow for significant performance improvements
  * Supports *categories* (referred to as `extension`s) and *protocols* from Objective-C (interfaces)
    * Methods are implemented through extensions, and used through generics
    * Combination of protocols, defaults, protocol inheritance, and extensions allows functionality with classes/inheritance to be implemented on value types, leading to a dramatic performance increase
  * Same runtime as Objective-C, and Objective-C can be used directly in Swift code
  * Heavily influenced by C and Objective-C, but has stark differences to Objective-C as well
  * Uses Automatic Reference Counting (ARC) to manage memory
    * Creating a *strong reference cycle* can create memory leaks (up to the programmer to manage this with weak references)
  * Uses: iOS, macOS, Linux, Cocoa and Cocoa Touch frameworks (to write code for Apple products)
