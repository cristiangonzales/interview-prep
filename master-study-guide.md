Interview Questions
---
* Differences between your top 3 PLs
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
* I am currently a junior at the University of California, Santa Cruz majoring in Computer Science
* I will be graduating in June 2019
* I have priorly interned at Northrop Grumman Corporation as a Technical Intern, where I created a proof-of-concept visualization tool tracking health statuses of satillites
  * It is here I became comfortable working with a large codebase, and gained exposure to object-oriented design patterns
* I currently have a standing offer with NGC to return full-time in a software position
* I'm interviewing with \_\_\_\_\_\_ (Microsoft, Amazon, Zillow, etc.) today because, quite frankly, I want to work with the best engineers in the world on the most exciting tech

Why Microsoft?
---
* I want to work at Microsoft because I imagine there are an ample amount of opportunities to work on distributed systems as Microsoft scales huge data centers around the world
  * Microsoft currently has Leslie Lamport, a pioneer in the distributed computing community, employed as a distinguished scientist
  * I have read the following whitepapers published by MS Research
    * *PacificA: Replication in Log-Based Distributed Systems Storage*
    * *Replicated Data Consistency Explained Through Baseball*
      * Uses baseball analogies to illustrate the data consistency needs of different clients
      * Talks about Amazon S3, Dynamo, and other infrastructure/platform services being available and partition tolerant because of their needs, and Azure being strongly consistent and partition tolerant
      * Illustrates that clients should be able to choose their desired consistency, and even simple databases may have users with diverse needs
      * From strong consistency to eventual consistency, all consistency guarantees are useful
* Another thing that excites me in particular is the contributions that Microsoft has made to the FOSS movement, namely TypeScript and VSCode
  * I'm excited to see what tools and technologies that Microsoft open-sources next

Questions to ask the interviewer
---
* Why do you work at Microsoft?
* From my short experience learning about it, I love distributed systems and computing, and I would like to work more with it. I imagine there are plenty of opportunities to work on problems pertaining to distributed systems with the Azure, Office 365, Outlook, Skype, Xbox Live, Bing, and OneDrive services. Aside from these services and the work that Microsoft Research does, what opportunities are there to work with distributed systems?
* Microsoft has contributed to the free and open source software (FOSS) movement, namely making a big splash with TypeScript and VSCode. How much of the codebase is maintained by full-time employees at Microsoft? Are there specific departments dedicated to maintaining these projects?
* According to Microsoft's latest 10-K (SEC filing), they name Apple and Google as their main competitors in the "software products and alternative platforms and devices" space. What is the outlook of the future in terms of staying ahead of their competitors, and what is Microsoft doing differently in terms of acquiring the best talent? As I understand, Microsoft is known amongst the software community for having a great work-life balance and company culture. Can you talk a little bit more about the company culture as well?

Tools
---
### Docker
##### What is Docker?
* Containerization platform which packages an app and its dependencies in a container so the app works in any environment
* Docker containers wrap software (the app) in a complete filesystem that contains everything needed to run (e.g. runtime, system tools, system libraries, anything that can be installed on a server)
* Thus, software will run the same regardless of the environment
* VMs have their own OS, while Docker uses the host OS

##### What is a Docker image?
* Used to create containers are created with the `docker build` command, and will produce a container with the `docker run` command
* Images are stored in the Docker registry because they can become large
* Images are composed of *layers* of other images so not a lot of data is sent over the network

##### What is a Docker container?
* Docker containers include the application and dependencies but share the host kernel with other containers, running as isolated processes in the user space on the host OS
* Docker containers are not tied to any specific infrastructure, and hence, they can be ran anywhere
* Created by running a build Docker image or using a Docker Hub image (containers are basically runtime instances of Docker images)

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

Language Agnostic
---
### REST fundamentals
* *Definition of REST*: Architectural style for designing loosely coupled applications over HTTP
* Guiding Principles of REST––What makes a service *RESTful*?
1. Client-server
  * Improve UI portability across platforms and server scalability
2. Stateless
  * Session state kept entirely by the client, not dependent on the server
3. Cacheable
  * Responses must be labeled as cacheable or noncacheable (if cacheable, cached information can be used in subsequent events)
4. Uniform interface
  * Identification of resources
  * Manipulation of resources through representations
  * Self-descriptive messages
  * Hypermedia as the engine of application state (HATEOAS)
5. Layered system
  * Each component cannot "see" beyond the immediate layer they are interacting with
6. Code on demand
  * Download/execute code in the form of applet/scripts

### Design patterns
##### Dependency injection
* One object supplies the dependencies of another object
* Intent: decouple objects so no client code has to be changed because an object it depends on needs to be changed to a different object
* Injecting code (the injector) constructs services and calls the client to inject them
* Three common means for client to accept a dependency injection
  * setter-based injection
  * interface-based injection
  * constructor-based injection
* Four roles
  * *Service* object to be used
  * *Client* object that is depending on the services it uses
  * *Interfaces* that define how the client may use the services
  * *Injector*, responsible for constructing the services and injecting them into the client
* Google Guice uses annotations (`@Inject`) (see more in the Guice tutorial `guice-tutorial.pdf` in the root directory)
