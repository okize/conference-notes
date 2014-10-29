## Tuning Node

### Joe McCann

__Summary:__
Ever wondered how to write performant Node apps? What about how V8 optimizes the JavaScript you write in your Node.js application? Should you use the cluster module for load balancing? As Node grows in popularity and its use cases expand from simple chat applications, best practices and patterns for writing performant applications have started to surface but haven't been widely adopted. At NodeSource, we work with loads of clients whom have varying challenges when it comes to performance, scale and productivity. Joe will share some of the findings and talk a bit more about the future of Node.js application development.

---

two types of engineers:

* how does it work?
* what can I make with it?

two steps to performance node apps:

* write performance code
* micro-optimize by setting flags

__performant code:__

* V8 is super smart and will outsmart you
* V8 converts your JS to assembly
* V8 wants to optimize your code
* _don't make V8 think!_

performance wins:

* keep function arguments the same length and same types, every time (monomorphic or polymorphic _not_ megamorphic)
* use constructors and factory methods to ensure same properties are adde in same order
* keep object maps the same, declass all properties and values (even if null/undefined) so V8 can create proper maps
* avoid mixing types in arrays (also allocated size when possible)
* avoid excessive anonymous closure usage - use named functions
* keep your functions overall size to fewer than 600 characters (bytes) in length... Yes, seriously (also, comments count towards total)

__setting flags:__

* --max_inlined_source_size = 1000; increases byte threshold for inline functions
* --allow-natives-syntax; allows calling out to C++ function from inside js