Python nuances in deep detail
---
* Difference between lists and tuples

| Lists | Tuples |
|-------|--------|
| Mutable | Unmutable |
| Slower | Faster |

* Features
  * Interpreted, high-level, general purpose programming language designed to be extensible
  * Type system: Strong and dynamic (uses duck typing)
  * Supports multiple paradigms: object-oriented, imperative, functional, procedural
  * Functions and classes are first-class objects
* Difference between *shallow* and *deep* copy
  * *Shallow* copies duplicate as little as possible. A shallow copy of a collection is a copy of collection *structure* (two collections now share *individual* elements)
  * *Deep* copies duplicate everything: A deep copy is two colletions with *all elements in the original collection duplicated*
* How is multithreading achieved in Python?
  * The GIL lets only one "thread" execute at once, so the GIL is passed between threads after doing a little bit of work (threads *seem* to be executing in parallel, but are not)
    * This adds a lot of overhead
* *Ternary* operators are used to show conditional statements
* How is memory managed in Python?
  * Python private heap space contains all objects/data structures (interpreter manages this heap)
  * Allocation for heap space done by Python's memory manager
  * Built-in garbage collector
  * Note: Python's memory management is not [thread safe](https://softwareengineering.stackexchange.com/a/186909), hence the need to have a GIL
* Python inheritance
  * Single inheritance
  * Multi-level inheritance
  * Hierarchical inheritance (inherit any number of child classes from a base class)
  * Multiple inheritance (derived class is inherited from >= 1 base class)
* Flask
  * Web microframework, dependent on Werkzeug and Jinja2
  * In a "flask", a session uses a signed cookie so the user can look at and modify session contents
  * User can modify the session only with the secret key
* `help()`: display docstrings and help related to modules, keywords, etc.
* `dir()`: display defined symbols
* When Python exits, objects with circular references and objects referenced by the global namespace are not always freed
  * Impossible to deallocate portions of memory reserved by the C library
  * Python memory manager tries to destroy every other object on exit
* Dictionaries
  * 1-to-1 relationships between keys and values
  * Indexed by keys
* *Monkey patching*: dynamic modifications of a class/module at runtime
* `*args`: stored list or tuple of arguments, or we don't know how many arguments
* `**kwargs`: we don't know how many keyword arguments there are; pass the values of a dictionary as keyword arguments
* Negative indexes
  * `-1, -2, ...` (last index, second to last index,...)
  * Used to remove newline spaces from strings and allow strings to omit all characters beginning with the nth to last character (e.g. `s[:-1]` will omit the last character)
  * Also used to show the index to represent the string in the correct order
* Compilation and Linking
  * Python interpreter can provide dynamic loading of configuration setup files and rebuild interpreter
* `re` module in Python
  * `split()`: splits string into list
  * `sub()`: finds all regex matches in a string and replaces them with a different string
  * `subn()`: similar to `sub()`, returns new string along with number of replacements
* `range` and `xrange`
  * generates list of integers, `range` returns a list and `xrange` returns an xrange object
  * `xrange` doesn't generate a static list at runtime, but rather, yields each item, using generators, *as you need them*
    * this is memory-efficient
* *Pickling*: A module that accepts an object and converts it into a string, and dumps it into a file
  * *Unpickling*: Turning a string back into a Python object
* `map` function
  * Executes the function as the first argument on all the elements of the iterable given as the second argument
* Decorators
  * Modify/inject code in functions/classes
  * Wrap class/function so code can be executed before/after execution of original code
  * Can be used to check for permissions, modify arguments passed to a method, logging calls to a sepcific method, etc.
* Uses
  * Scripting language for web apps
  * Domain-specific scientific computing
  * Artificial Intelligence
  * Ships with most Linux distributions
  * Information Security
