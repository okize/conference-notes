# Async Redux

### Freddy Rangel

===


##### Overview or React, Redux, and Asyc

##### Redux Crash Course

##### Redux Middleware

##### Async with Thunks and Promises

##### Async with Generators and Sagas


===

## React & Redux

__React is not your architecture!__

React provides a platform to build on but you need to make decisions about all the other stuff, like Flux pattern for state management


* Redux is a great step forward but isn't really a Flux pattern (implementation of the Elm lib)
* removes business logic out of your React views

#### Redux is a workflow, not a complete architecture

* Redux doesn't have async (as well as a bunch of other things) out of the box
* Async is the new frontier in JS. is unsettled

### Redux middleware

* a 3rd-party extension point between dispatching an action and the moment it reaches the reducer.

* `pending` operation is in progess
* `fullfilled` operation is finished
* `rejected` operation failed

### Redux Thunk

* normal actions are objects

### RxJS

* don't use with Redux

### Redux Sagas

* based on generators
* saga is a failure management pattern (think daemons)

===

* Redux is a predictable state container; it's a function approach to managing state

### 3 parts of redux

1. the store
	* only one store; generally if you need multiple stores, you need multiple apps
	* single source of truth; think of it as a json store (possible to store functions but don't do that)
	* can call getState() at any point to the state of your app
2. actions (dispatcher)
	* state is immutable (ie. read-only)
	* to change the state you need to dispatch an event
	* this follows Redux's one-way data-flow
3. the reducer
	* a pure function with no side-effects (not supposed to do http calls, or local storage gets inside a reducer)
	* takes the current state, an action and then returns the next state
	* state needs some kind of default to start (redux doesn't like null values)

===

## Redux Middleware

* computer software that provides services to apps beyond those available from the OS. it can be desribed as 'software glue'.
* middleware on the server is used to address cross-cutting concerns like authentication, authorizing, logging, gathering performance metrics, etc.

### How does Redux apply the middleware pattern

* in the case of Redux middleware the main execution task is the store's dispatch ffunction
* the dispatch function is responsivble for sending actions to one or many reducer functions for state changes
* redux uses currying and composition

### Async in Redux

* everything that has side efects has to happen in middleware

### Implementation details

* Redux chains together middleware you provide, passing in special functions to your...

* for all intents and purposes it's the Redux store (technically, it's a little different)

===

## Redux Thunk

* easy to forget error handling and pending state

#### FSA: flux standard action

* a set of standards for describing what an action should look like
* an action must have a `type`
* an action may have a payload
* an action may have meta data
* specifies how to dispatch an error

===

## Generators

* generators are functions that can be exited and later reentered
* 2 parts: a generator function and a genertaor object
* generator objects have a `next()` method that returns an object with `value` and `done` attributes

===

## Redux Saga

* a Redux implementatio of the Saga Pattern
* based on generators
* instead of dispatching Thunks, you create Saga to gether all your Side Effects logic in a central place
* this means application logic lives in 2 places:
	* reducers are responsible for handling state transitions between actions
	* sagas are responsible for orchestrating complex/async operations
	
	

