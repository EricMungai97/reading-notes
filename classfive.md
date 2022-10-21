# Thinking in react

[SOURCE](https://reactjs.org/docs/thinking-in-react.html)

***What is the single responsibility principle and how does it apply to components?***

A component should ideally only do one thing.If it ends up growing it should be decomposed into smaller components.

***What does it mean to build a ‘static’ version of your application?***

It means building a version that takes your data model and renders the UI but has no interactivity.

***Once you have a static application, what do you need to add?***

We need to add states to our components to make our UI interactive.

***What are the three questions you can ask to determine if something is state?***

1. Is it passed in from a parent via props? If so, it probably isn’t state.
2. Does it remain unchanged over time? If so, it probably isn’t state.
3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

***How can you identify where state needs to live?***

1. Identify every component that renders something based on that state.
2. Find a common owner component (a single component above all the components that need the state in the hierarchy).
3. Either the common owner or another component higher up in the hierarchy should own the state.
4. If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

## High-Order Functions

[SOURCE](https://eloquentjavascript.net/05_higher_order.html#c_POEf7pMCk0)

***What is a “higher-order function”?***

They are functions that operate on other functions either by taking them as arguments or by returning them.

***Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?**

Takes in n and returns a  boolean based on if m is greater than n.

***Explain how either map or reduce operates, with regards to higher-order functions.***

Map would apply the argument function to each element in the array.
