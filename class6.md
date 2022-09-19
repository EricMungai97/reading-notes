# Reading Notes 8

## How would you describe an object to a non-technical friend you grew up with?

An **object** is a collection of related data.

## What are some advantages to creating object literals?

* *Convenience.

* Gives us flexibility in declaration

* Enables us to use less code during declaration.

## How do objects differ from arrays?

An **array** is a variable that can be used to store values whereas an object is data type we can use to store a collection of data.
An object can contain both functions and variables in it whereas an array cannot.

## Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.

If an object property name is defined at run time you can't use dot dot notation to access the value, but you can pass the name as a variable.

Example

```
const person = {
  name: ['Bob', 'Smith'],
  age: 32
}
const input = prompt('Get name or age?')
console.log(person[input])
```

[cite](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)

## Evaluate the code below. What does the term this refer to and what is the advantage to using this?

```
const dog = {
  name: 'Spot',
  age: 2,
  color: 'white with black spots',
  humanAge: function (){
    console.log(`${this.name} is ${this.age*7} in human years`);
  }
}
```

`this` refers to the current object the code is being written inside. It helps us use the same method for every object definiton you create.

## What is the DOM?

Progaramming interface for web documents.

## Briefly describe the relationship between the DOM and JavaScript.

Javascript interacts with DOM to access a document and its elements.