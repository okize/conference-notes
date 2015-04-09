## Interactive Datavis with React
### Taming the complexity of changing state

### Ilya Boyandin

__Summary:__
The urge to support interactivity in modern visualizations introduces many challenges for developers. Ensuring that changes in state are always treated correctly and the data representations are consistent often requires a lot of debugging, because of intricate dependencies and complex data flows. In this talk, Ilya will discuss how the use of React, Flux and immutable data structures can facilitate a simple and efficient approach to managing and rendering changing application state. He will demonstrate using React together with D3 through examples and code.

---

#### every new feature added to the system adds new potential for state change in a combinatorial manner

1. Get the app state right
2. Define how any state is rendered

* for datavis where every portion of the dom may be updated, React's diffing will not help and may work against you; compromise by offloading to D3 with componentWillUPdate
