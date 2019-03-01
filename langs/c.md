C nuances in deep detail
---
* Type system: static and weak
* Paradigm: Imperative (procedural), structured
* Supports
  * Structured programming
  * Lexical variable scope
  * Recursion
* Low level access to memory, constructs map to machine instructions, minimal runtime support
* Function and data pointers permit ad hoc runtime polymorphism
* Preprocssor performs macro definition, source code file inclusion, and conditional compilation
* Modularity: files can be compiled seperately and linked together
* Complex functionality (e.g. I/O) delegated to library routines
* Memory management
  * *Static* memory allocation: space for the object is provided in the binary at compile-time
  * *Automatic* memory allocation: temporary objects stored in stack memory, space is freed and resuable after that block has exited
  * *Dynamic* memory allocation: blocks of memory (arbitrary size) can be requested at runtime from heap memory; this memory persists until freed by programmer
* `malloc()` versus `calloc()`: both allocate memory from heap memory (dynamic memory allocation), but `calloc()` fills allocated memory with 0s
* Global variables can't be automatic, local variables are automatic by default (see more on the C keyword, `auto`)
* `break` can only be declared in looping control/switch statements
* A negative integer is stored as the two's complement of that integer
* If a header file is in `<>`, the compiler searches for files only within the builtin include path
   * If it is in quotes, the compiler searches in the current working directory, then the builtin include path
* Static local variables retain its value between the function call
* `extern`: used to resolve the scope of global symbol
* `sprintf()`: prints formatted output onto character array
* *Base address*: starting address of an array
* Frequently used variables should be declared using *register storage specifier*, so compiler gives CPU register for its storage to optimize the lookup time of the variable
* *Dangling pointer*: pointer initially holding an adress, but later freed
* `typedef`: alias the existing type
* Parameters
  * *Actual parameters*: parameters sent to the function at the calling end
  * *Formal parameters*: parameters sent to the function at the receiving end
* `main()` required for executing a program, but not compiling a program
* We declare a void pointer when we don't know what type of memory address the pointer is going to hold
* Every local/`auto` variable is stored is stack memory
* *Nested structure*: structure containing the element of another structure as its member
* Variable *declaration* versus variable *definition*
  * *Variable declaration*: associates a type to a variable
  * *Variable definition*: gives a value to a variable
* *Self-referential structure*: structure containing same structure pointer variable as its element
* *Token*: keyword, identifier, constant, string literal, or symbol
* *Preprocssor*: Directive to compiler to perform certain things before compilation
* *Arrow operator*: If the structure variable is a pointer, you can access structure elements using this
* *Static function*: Make a function static if it should only be called within the same source code
* *Enumerations*: List of integer constants with names associated with each of them
* *Structure*: Collection of heterogenous data items
