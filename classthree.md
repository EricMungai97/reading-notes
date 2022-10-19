# React Docs - lists and keys

***What does ```.map()`` return?***
It returns a new array populated with the results of calling a provided function on every element in the calling array.

[cite](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)

***If I want to loop through an array and display each value in JSX, how do I do that in React?***
You would have to use the JavaScript ```map()``` function to loop through the array and return into JSX.

Each list item needs a unique ```key```.

***What is the purpose of a key?***

They help React identify which items that have changed,are added, or are removed.

## The Spread Operator

***What is the spread operator?***

An ellipsis of three dots ```(...)``` used to expand an iterable object into the list of arguments.

***List 4 things that the spread operator can do***

1. Add items to arrays
2. Combine arrays
3. Combine objects
4. Using Math Functions

Give an example of using the spread operator to combine two arrays.

```
let myArr = [1,2,3];
let yourArr = [4,5,6];
let ourArr = [...myArr,...yourArr]
```

Give an example of using the spread operator to add a new item to an array.

```
let mineArr = [1,2,3];
let oursArr = [4,5,6,...mineArr];
```

Give an example of using the spread operator to combine two objects into one.

```
const hello = {hello: "😋😛😜🤪😝"}
const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

const helloWorld = {...hello,...world}
```

## How to Pass Functions Between Components

***In the video, what is the first step that the developer does to pass functions between components?***

We create a function wherever the state is that we are gonna change.

***In your own words, what does the increment function do?***

It loops through the people array and changes the count of the object thats passed in if it matches the name passed in the increment function.It then creates a new arr with that includes the new object with that includes the person with the changed counts.

***How can you pass a method from a parent component into a child component?***
 
 By converting that method to a prop.

***How does the child component invoke a method that was passed to it from a parent component***

You first need to pass that method as as a prop in your object at the parent component, and then call that prop in your child component.