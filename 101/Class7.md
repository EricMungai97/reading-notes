# **Programming with JavaScript**

## ***MDN Control Flow***

The *control flow* is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.

## JavaScript Functions

A JavaScript function is a block of code designed to perform a particular task.

A JavaScript function is executed when "something" invokes it (calls it).

```
Example
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}
```

## JavaScript Function Syntax

A JavaScript function is defined with the function keyword, followed by a `name`, followed by parentheses `()`.

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include `parameter` names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}

```
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

Function **arguments** are the values received by the function when it is invoked.

Inside the function, the arguments (the parameters) behave as local variables.

## *Function Invocation*

The code inside the function will execute when "something" invokes (calls) the function.

## *Function Return*

When JavaScript reaches a return statement, the function will stop executing.

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

Functions often compute a **return value** .The return value is "returned" back to the "caller":

```
Example
Calculate the product of two numbers, and return the result:

let x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```
The result in x will be:

12

The `()` Operator Invokes the Function.

## *Why Functions*

1. You can reuse code: Define the code once, and use it many times.

2. You can use the same code many times with different arguments, to produce different results.

## ***JavaScript Operators***

The assignment operator (=) assigns a value to a variable.

The addition operator (+) adds numbers.

The multiplication operator (*) multiplies numbers.

[Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)

[Comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators)

[Arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#arithmetic_operators)
