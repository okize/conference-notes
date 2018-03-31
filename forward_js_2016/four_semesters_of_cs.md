# Four Semesters of Computer Science in Six Hours

### Brian Holt

===

read: [Introduction to Algorithms, Third Edition](https://mitpress.mit.edu/books/introduction-algorithms)

*Computer science is the science of tradeoffs.*


## Big O Analysis

[Big O cheatsheet](http://bigocheatsheet.com/)

`hot code path` = code that gets run a lot; needs to be as efficient as possible

Don't bother optimizing code that's not in the hot code path; generally you're going to make the code look worse, less readable, less understandable so it should be only done when absolutely necessary.

Big O helps us ignore the noise in an algorithm that doesn't really affect the performance; helps us focus on the meat, where the real cost lies.

We throw out the coefficient (1/3n would just be n) because we want worst case scenario (even if it could return faster).


``` 
function add(a, b) {
  return a + b;
}
```

Doesn't matter how large the values we put in there, it will always take the same amount of time. This is called `constant time` ie. O(1).

Protip: look for loops. A loop inside of a loop inside of a loop would likewise be O(n³).

3 sibling loops would be O(3n) but we throw the coefficient away so it's O(n).

If you see recursion, it's probably going to be O(log n).

With exponential algos, as you add inputs, it takes longer and longer. With logarithmic algos, as you add inputs, the time take levels out.

===

## Recursion

Recursion is when you define something in terms of itself.

As a tool, recursion has some fundamental tradeoffs. For example, the `call stack` can potentially get huge and lead to a `stack overflow`. This is not free or even cheap, so generally you want to use iteration instead of recursion (this is often be an initial point of optimization).

The `base case` is the designation of the leaf solution (ie. I'm in a solveable state, time to return the solution). This is the most important and first step of writing a recurisve function.

Use `tail call` recursion when possible.

===

## Sorting

For the bubble sort, you re-run the algorithm every time you have a swap in a pass; this means that when it's actually sorted you'll still have a final pass though. Not an efficient sort, it should never be used because basically every other sort is better.


`spacial complexity` is the amount of space code is taking up in memory.

Any time you see `divide & conquer` think `log n`.

===

## Data Structures

### Interfaces

`interfaces` are black boxes; they provide and api but you the consumer have no knowledge of the internals.

`Sets` have no order and no duplicates; this is useful for de-duplicating data.

`Maps` are key-value pairs. Keys are Sets so you cannot have duplicates.

`Stacks` adhere to "Last-In First-Out" (LIFO) and have push, pop and peak methods. 

`Queues` adhere to "First-In First-Out" (FIFO) and have enqueue, dequeue and peak methods. 

### Implementations

`implementations` are the internals; this is how we create the interfaces.

`Array List` values are co-located in memory and lookups are constant time; additions & deletions are expensive.

`Linked List` values are connected by pointers in memory which allows for faster additions & deletions; lookups are expensive. 

`Binary Search Tree` are useful if you need to search something very quickly; must have a definite sorted order.

`AVL Tree` keeps BSTs in balance.

`Hash Table` javascript uses hash tables to store objects.

### Functional Programming

`pure functions` take input return values and have no side effects

`functor` is anything you can map.

