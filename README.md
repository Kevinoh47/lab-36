![CF](http://i.imgur.com/7v5ASc8.png) LAB
=================================================

## Lab 36 React Context 
Create a Counter application using Context to provide access to global state. React Context is the underlying framework exploited by Redux.

### Author: Kevin O'Halloran

### Links and Resources
* [code sandbox 1 - recreating the class demo](https://codesandbox.io/s/1onnr8q6ol)
* [code sandbox 2 - a counter app using context](https://codesandbox.io/s/j1jpy752z3)

### Modules

#### `CounterProvider`
##### Exported Values and Methods
The /src/components/context/counter.js file creates and exports the CounterProvider class. The class exposes a render method, which wraps any children of the CounterContext.Provider object with the abilitity to subscribe to Counter state changes.

To manage state changes, the class uses the following internal methods: increaseCounter, decreaseCounter, changeCounter, and checkPolarity. The increaseCounter and decreaseCounter methods each call changeCounter. ChangeCounter changes the counter value and also checks the polarity (+ , - or null ) of the resulting value, and sets the new state.

#### `Counter`
##### Exported Values and Methods
The /src/components/counter-consumer/index.js file creates and exports the Counter class. This class has a single render() method. It wraps its return statement with the CounterContext.Consumer object, to subscribe to Counter state changes. It then renders the current count, and sets a class to the polarity value. It uses the context.increment and decrement settings as callbacks for the Add and Subtract buttons to change the counter values. 

#### `App`
##### Exported Values and Methods
The /src/components/app.js file creates and exports the App class. This class is used to marshal the various child components. It exposes a  render() method whose return statement wraps the Counter component with the CounterContext component, allowing it to subscribe to context state.

#### `Main`
##### Exported Values and Methods
The /src/index.js file creates the Main() functional element, which provides the entry point to the application. This element returns the App component, and is itself rendered under the root element of the DOM.

#### Tests
* How do you run tests?
* What assertions were made?
* What assertions need to be / should be made?

#### UML
Link to an image of the UML for your application and response to events
