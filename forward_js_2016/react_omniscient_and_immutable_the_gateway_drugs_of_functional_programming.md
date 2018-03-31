# React, Omniscient, and Immutable: the gateway drugs of functional programming
### Erin Depew

---


```
const ComponentLifecycleFunc = {
  shouldComponentUpdate() {
    // object nextProps
  }
};

const GenericComponent = component('GenericComponent', [ComponentLifecyleFunc], function({text}) {
  return (
    <h1>{text}</h1>
  );
});
```

For simple components, where you're not using immutable data structures, this is actually a performance anti-pattern.

Omniscient: ShouldComponentUpdate function

ImuutableJS: Cheap reference check compoarisons

## Unidirectional Data Flow

App state:
* immutable structure with Immstruct wrapper
* changes trigger shouldComponentUpdate

Actions -> App State -> f(state) = </> -> dom

## Data cursors and reference checking

Immutable structurs:
* Reference check vs. deep evaluation
* Improved performance for deeply nested data structures
* cursor.update() triggers swap event

Reference cursors always point to current data => no stale data

## Immutable API: withMutations()

__Problem:__ performance and memory penalty from temporary immutables objects

__Immutable data with mutations:__ 
* temporary mutable copy for performant series mutations
* transaction integrity in stores
* can only be used with set and merge

## React + Omniscient Virtual DOM

* re-render initiated by Immstruct corsor swap notification

## Drawbacks

* steep learning curve
* new technology = lack of standard
* verbose propagation
* accidentally dereferencing cursors
* converting back and forth between Immutable and JS
* cursor API shadows Immutable API which can cause confusion
* No concept of read/write cursors
* Immutable structures have static performance penalty

## Benefits

* Simplified app state updates and data structure
* Faster checking for state changes
* Fewer unintended side effects
* Component based structure promotes reusability
* Enhanced testing and easier debugging
* Reduced browser re-rendering / re-painting

