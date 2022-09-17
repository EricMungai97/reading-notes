# **Activating web pages with JavaScript**

*JavaScript (JS)* is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions.

## **JavaScript Variables**

4 Ways to Declare a JavaScript Variable:

- Using var
- Using let
- Using const
- Using nothing

## *Variables*

*Variables* are containers for storing data (storing data values).

In this example, x, y, and z, are variables, declared with the var keyword:

```Example
var x = 5;
var y = 6;
var z = x + y
```

In this example, x, y, and z, are variables, declared with the let keyword:

```Example
let x = 5;
let y = 6;
let z = x + y;
```

In this example, x, y, and z, are undeclared variables:

```Example
x = 5;
y = 6;
z = x + y;
```

If you want a general rule: always declare variables with `const`.

If you think the value of the variable can change, use `let`.

***Variables*** are containers for storing values.

## ***JavaScript Identifiers***

All JavaScript variables must be identified with unique names.

These unique names are called identifiers.

Identifiers can be short names (like x and y) or more descriptive names (age, sum, totalVolume).

*The general rules for constructing names for variables (unique identifiers) are:*

1. Names can contain letters, digits, underscores, and dollar signs.
2. Names must begin with a letter
3. Names can also begin with $ and _ (but we will not use it in this tutorial)
4. Names are case sensitive (y and Y are different variables)
5. Reserved words (like JavaScript keywords) cannot be used as names

JavaScript identifiers are ***case-sensitive***.

## **The Assignment Operator**

In JavaScript, the equal sign (=) is an "assignment" operator, not an "equal to" operator.

This is different from algebra. The following does not make sense in algebra:

```x = x + 5```

In JavaScript, however, it makes perfect sense: it assigns the value of x + 5 to x.

(It calculates the value of x + 5 and puts the result into x. The value of x is incremented by 5.)

*The "equal to" operator is written like `==` in JavaScript.*

## Javascript Data Types

- Numbers
- Text strings

## Declaring a JavaScript Variable

Creating a variable in JavaScript is called "declaring" a variable.

You declare a JavaScript variable with the var or the let keyword:

```
var carName;
or:
let carName;
```

After the declaration, the variable has no value (technically it is undefined).

To assign a value to the variable, use the equal sign:

```
carName = "Volvo";
```

