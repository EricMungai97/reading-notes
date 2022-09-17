# Reading Assignement 2

## When to use an unordered list

It is used for listing items whose order is meaningless.

## Changing the bullet style of unordered list items

To do this we just use the attribute `type` to set the bullet style we want.

For example
```
<ul type='circle'></ul>
```
## When to use ordered list vs unordered list

We use an ordered list when we want the order of the list to be have meaning. For example directions to a place or instructions for a manual.
The unordered list however is for when the order of items is not meaningful i.e. they can be any order.

## Ways to change numbers on list items in an ordered list

To do this we use the tye attribute.

For example
```
<ol type="i">
  <li>Boil water</li>
  <li>Add oil and salt</li>
  <li>Put in rice</li>
</ol>
```
## CSS properties of margin and padding

## 4 parts of an HTML elements box

1. *Content box*: The area where your content is displayed.
2. *Padding box*: The padding sits around the content as white space.
3. *Border box*: The border box wraps the content and any padding; size it using border and related properties.
4. *Margin box*: The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements.

[citation for 4 parts of an html elements box](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

## Data Types you can store in an array

* Strings
* Numbers
* Objects
* Other Arrays

## Is the people array a valid JavaScript array? If so, how can I access the values stored? If not, why?

```
const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];
```
Yes it is, you can guess the values we will use the `for ... of statement.

for example

```
const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];

for (const people){
  console.log(people);
}
```

will print all the values in peopleArr.

## Shorthand operators for assignment in Javascript

Addition assignment `x += f()` - adds the value of the right operand to a variable and assigns the result to the variable.

Subtraction assignment `x -= f()` - subtracts the value of the right operand from a variable and assigns the result to the variable.

Division `x /= f()` -  divides a variable by the value of the right operand and assigns the result to the variable.

Multiplication `x *= f()` - multiplies a variable by the value of the right operand and assigns the result to the variable.

Remainder assignment `x %= f()`- divides a variable by the value of the right operand and assigns the remainder to the variable.

[cite operator assignemnts](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

## Read the code below and evaluate the last expression and explain what the result would be and why.

```
 let a = 10;
 let b = 'dog';
 let c = false;

 // evaluate this
 (a + c) + b;
 ```

 The result would be `10dog` because c is a boolean.

## Real world xample of when a conditional statement should be used in a JavaScript program.

You want to put your favorite song on repeat mode.

## Give an example of when a Loop is useful in JavaScript.

To complete a repetitive task , for example creating a guessing game for a user of your website.