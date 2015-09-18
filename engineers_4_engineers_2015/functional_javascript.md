## Functional Javascript: Reverse-engineering the Hype

### Ben Anderson

---

## Learning to program (as a working programmer)

Higher bar to new programming metaphors as a working programmer (ie. how does this help me do my job?)

## Adopting big ideas (by making real apps)

* it took a generation to agree that high-level languages were a good idea
* it took another generation to agree that objects were a good idea
* it took two generations to agree that lambdas were a good idea
* "we need to wait for the previous generation to retire or die before we can get critical mass on the next big idea" -- Douglas Crockford

## FunctionalJS Agenda

1. why now? why javascript?
2. functional patterns, for real apps
3. revisiting the mental model

## Why javascript? Capability meets Opportunity

DOM is stateful, impreative
It will undermine your functional quest

fn(props, state) == UI

## Functional Domain Logic

"the Data"

Collections and Models

all of the data HAS to be immutable; like other models except you can't change them

## Immutable benefits

* you can trust immutable objects
* **your app** can trust immutable objects

## Services
* stateless function that accepts and transforms immutable data to fullfill a business operation

## Queries
* stateless function that accepts immutable data and transforms, calculates, reduces, repurposes
* want to actively cache this

## Actions (how we change the outside world)

## Mental model of Static vs. Dynamic
* redux: "predictable", "behave consistently"
