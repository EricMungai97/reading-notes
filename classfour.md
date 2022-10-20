# React and Forms

## React Docs - Forms

[cite](https://reactjs.org/docs/forms.html)

***What is a ‘Controlled Component’?***

A component in which form's data is handled by the componenet state.

***Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.***

We should update the state with their responses as soon as they enter them. This is because the react component that renders a form also controls what happens in that form on subsequent user input.

How do we target what the user is entering if we have an event handler on an input field?

We assign the ```value``` of that field input to  ```event.target.value```.

## The Conditional (Ternary) Operator Explained

Why would we use a ternary operator?

It makes our code dry by shortening ```if``` statements into one line of code.

Rewrite the following statement using a ternary statement:

```
if(x===y){
  console.log(true);
} else {
  console.log(false);
}
```

```
x===y ? console.log(true) : console.log(false)
```
