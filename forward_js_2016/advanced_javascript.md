# Advanced Javascript

### Kyle Simpson

===

## Law #1 - If you don't know why a piece of code worked then you can't know why it broke.

### Scope - where to look for things
- vairables & identifiers
- who's doing the looking?

js is NOT interpreted
js is a compiled langue; JIT runs in the engine constantly

if it was interpreted language (like, say, Bash) you would never see an error on line 4 without line 1, 2 or 3 running (something which happens frequently).

Javascript is not single pass; js should be thought of as *at least* two pass.

registry of all of identifiers into their related scopes.

2 phases:
1) complile phase
2) execution phase

Not distributing binaries is the least interesting part of what makes a com[iled language (in fact, it's not the definition).

Compiler is how you verify correctness. Test suite is how you verify accuracy.

The JS compiler is much more sophisticated than any other compiler we've written. We expect the js compiler to run in mere microseconds.

The JS dynamic typing actually makes the compiler work harder than other compilers have to.

It was thought that there was no such thing as static analysis of a dynamic language. Type-inferencing happens constantly in JS.

```
var foo = 'bar';

function bar() {
  var foo = 'baz';
}

function baz(foo) {
  foo = 'bam';
  bam = 'yay';
}

// ================

var foo;

// `var foo` happens at compile time
// `foo = 'bar'` happens at execution time
// declaration in global scope
// "hey global scope, I've got a variable called `foo` do you know about it?"
// - always a yes/no answer

// formal declaration for function bar
function bar() {
  // formal declaration in nested scope
  var foo;
}

// formal declaration for function baz
// formal declaration for parameter foo
function baz(foo) {
  // foo = 'bam';
  // this is not declared at compile time
  // can't know that next line won't be `var bam = 'foo';` so we cannot assume we meant to declare a variable
  // so we have to defer; at compile time bam is not registered
  // bam = 'yay';
}

// ================

// compile time is done, now it's time for js engine
// technicall it's now byte-code but we'll pretend

foo = 'bar';

// we stored meta information about this variable
// L-value (LSH - left hand side)
// R-value (RSH - right hand side)
// left-hand side and right-hand side of assignment; but should think of it as `target` and `source`
// "hey global scope" I have an LHS reference for foo, ever heard of it?
// yes I have heard of foo, it was declared during compilation, so I have a reference to it in memory.
// scope manager does NOT do the assignment, the js engine does
function bar() {
  // hey scope of bar, I have a LHS reference for foo, have you ever heard of it?
  // when you declare two variables of the same name, it's called `shadowing`
  // inside bar scope we can now no longer access the global foo
  foo = 'baz';
}

function baz(foo) {
  // hey baz scope, I have a variable called foo have you ever heard of it?
  // yes because we declared it as a parameter
  foo = 'bam';
  // hey scope of baz, I have an LHS reference for a variable called `bam`, have you ever heard of him?
  // no! so now we have to go ask in the next level of scope, which, in this case, is the global scope
  // hey global scope, I have an LHS reference for a variable called `bam`, have you ever heard of him?
  // *BAD JS DECISION*: if you run accross an unfulfilled LHS reference, instead of throwing an error,
  // the global scope will go ahead and create it for you :/
  // in the browser, window is sort of an alias to the global object, they're not *technically* the same
  // in `strict mode` we would have had a ReferenceError thrown `bam is not defined`; this error should have been `ban is not declared`
  // importantl to know undeclared != undefined
  // the notion of being undefined is that it's definitely been declared but it's value is just currently undefined
  bam = 'yay';
}
```

```
var foo = 'bar';

function bar() {
  var foo = 'baz';

  function baz(foo) {
    foo = 'bam';
    bam = 'yay';
  }
  // hey scope of baz, I have an RHS reference for baz, have you heard of it?
  baz();
}

// is it an LHS? is it receiving the value of an assignment?
// if it's not an LHS, it MUST be an RHS!
// hey global scope, I have an RHS reference for bar do you know it?
// yes, let's execute it; look up of the value, then an execute
// if bar was `null` we would have got a runtime TypeError
bar(); // no param so foo == undefined
foo; // bar
bam; // yay
baz(); // ReferenceError


// an unfulfilled LHS creates the global
// an unfulfilled RHS throws a ReferenceError

// trying to execute an undefined value throws
// TypeError `undefined is not a function`

// a function is a formal declaration if the word `function` is the first thing that appears in the line
// function declaration: function foo() {};
// function expression: var bar = function foo() {};

// a function in a function expression identifier gets added to it's *own* scope
// named function expression's identifier (foo) is read only
```

===

## named function expression vs. anonymous function expressions

always prefer named to anonymous

### 3 reasons why:
1) it is sometimes the case that you need to refer to the name of the function in the function itself (self-reference) for, say recursion
2) extremely helpful for debugging and giving names to functions in your stack trace
3) if it's named well it'll make the code more readable (ie. what does this function do?)

## Lexical scope vs. Dynamic scope

Lexical scope is staticand fixed and set up at compile time
Dynamic scope is determined at run time

oops, there's 2 different ways to break this

1) `eval` takes a string and treats the contents of that string as though it were code that was there at compie time
2) `with`

```
var foo;

try {
  foo.length;
}
catch (err) {
  console.log(err); // TypeError
}

console.log(err); // ReferenceError

// =======

var bar = 'bar';

function foo(str) {
  eval(str); // cheating!
  console.log(bar); // 42
}

foo('var bar = 42;');

### Lexical scope can be cheated!

// you've made your code harder to understand
// you've made your program slower!

// people usually say eval is bad because it's insecure, but if your code allows user contributed code via eval your problem is much deeper than just eval
// the performance argument is the true reason not to use it; the engine will do a regex fast scan in your code for `eval` and if it finds it, it will abandon all perf optimizations

// cases for eval
// eval could be used if you're writing a js compiler *in* javascript (function constructor is actually the better solution)
// if you're doing syntactic feature testing (ie. does this browser runtime support spread operator?) (function constructor is the better option here)
// this is done per file;

// eval behavior is modified in strict mode; it gets it's own little scope
// it doesn't matter because engines still do fast regex scan, so perf is still terrible

// =======

var obj = {
  a: 2,
  b: 3,
  c: 4
};

obj.a = obj.b + obj.c;
obj.c = obj.b - obj.a;

// instead of doing above
with (obj) {
  a = b + c;
  c = b - a;
  d = 3;
}

obj.d; // undefined
d; // 3 -- oops!

// creates a contruct that is impossible to predict until runtime; terrible idea
```

### principle of least exposure/privilege

we want to keep everything private as much as possible and only expose the minimum necessary for the software to run

### Dynamic scope

Dynamic scope is a model for scoping that determins scope at runtime (Bash script is dynamic scope as is Perl). Almost every other language is lexical scope.

## Closure

What you need to know definition:

Closure is when a function "remembers" its lexical scope, and continues to be able to access, even when the function is executed in a different lexical scope.

First class functions == functions are values that can be passed around

Closure sort of falls out of the requirement of a lexicaly scoped language that has first class languages.

## Module pattern

Two characteristics that makes something the module pattern
1) there has to be an outer-enclosing function that runs at least once
2) secondly that function has to return at least one tinner function that closes over it's internals

===
## Object-Orienting
* this
* protyope
* "inheritance" vs behavior-

Every function, while executing, has a ference to its current execution context, called `this`.


### default binding-rule
in non-strict mode use the global object
in strict mode use undefined

### implicit binding rule
if there's a context-object at the call site, use that for this
you never want your this keyword pointing to your global object

### explicit binding rule
pass in context using call/apply

### new keyword
`new` keyword has nothing to do with instantiating classes
when you put the new keyword in front of a function name the following 4 things happen:
1) a brand new empty object is created out of thin air
2) that brand new empty object gets linked to another object*
3) that newly created, linked object is now passed in as the dynamic `this` binding
4) if the function does not already return it's own object it assumes that you meant to return `this`

find the call site...
1) was the function called with the new keyword?
2) was the function called with call/apply, specifying an explicit this
3) was the function called via a containing/owning object (context)
4) DEFAULT: global object (except strict mode)

===

Every single "object" is build by a constructor call.

Blueprint-builder metaphor: the class is a bluebprint but we don't have a building until a builder comes and creates (instatiates) it

Genetic metaphor: copy operation

A constructor makes an objct *linked to* its own prototype.

Rather than a copy-down, it's a linked-up.

It's not "prototypal inheritance" it's "behavior delegation"

### Delegation Design Pattern

Not `parent-child` think `peer-peer`.
