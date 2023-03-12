# [Garbage collection](https://javascript.info/garbage-collection)

Memory management in JavaScript is performed automatically and invisibly to us. There’s a background process in the JavaScript engine that is called [garbage collector](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)). It monitors all objects and removes those that have become unreachable.

1.  There’s a base set of inherently reachable values, that cannot be deleted for obvious reasons.
    
    For instance:
    
    -   The currently executing function, its local variables and parameters.
    -   Other functions on the current chain of nested calls, their local variables and parameters.
    -   Global variables.
    -   (there are some other, internal ones as well)
    
    These values are called _roots_.
    
2.  Any other value is considered reachable if it’s reachable from a root by a reference or by a chain of references.
    
    For instance, if there’s an object in a global variable, and that object has a property referencing another object, _that_ object is considered reachable. And those that it references are also reachable. Detailed examples to follow.

That’s the concept of how garbage collection works. JavaScript engines apply many optimizations to make it run faster and not introduce any delays into the code execution.

Some of the optimizations:

-   **Generational collection** – objects are split into two sets: “new ones” and “old ones”. In typical code, many objects have a short life span: they appear, do their job and die fast, so it makes sense to track new objects and clear the memory from them if that’s the case. Those that survive for long enough, become “old” and are examined less often.
-   **Incremental collection** – if there are many objects, and we try to walk and mark the whole object set at once, it may take some time and introduce visible delays in the execution. So the engine splits the whole set of existing objects into multiple parts. And then clear these parts one after another. There are many small garbage collections instead of a total one. That requires some extra bookkeeping between them to track changes, but we get many tiny delays instead of a big one.
-   **Idle-time collection** – the garbage collector tries to run only while the CPU is idle, to reduce the possible effect on the execution.