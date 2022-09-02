# **Operators and Loops**

## ***Expressions and operators***

An *expression* is a valid unit of code that resolves to a value. There are two types of expressions: those that have side effects (such as assigning values) and those that purely evaluate.

The expression `x = 7` is an example of the first type. This expression uses the `=`operator to assign the value seven to the variable x.

The expression `3 + 4` is an example of the second type. This expression uses the + operator to add 3 and 4 together and produces a value, 7.

The precedence of operators determines the order they are applied when evaluating an expression. For example:

```
const x = 1 + 2 * 3;
const y = 2 * 3 + 1;
```

## **Assignment operators**

An assignment operator assigns a value to its left operand based on the value of its right operand.

[Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)

## ***Comparison operators***

A *comparison* operator compares its operands and returns a logical value based on whether the comparison is true. The operands can be numerical, string, logical, or object values.

[Comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators)

## **LOOPS**

Loops offer a quick and easy way to do something repeatedly.

## *for statement*

A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

A for statement looks as follows:

```
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement
```
```
function howMany(selectObject) {
  let numberSelected = 0;
  for (let i = 0; i < selectObject.options.length; i++) {
    if (selectObject.options[i].selected) {
      numberSelected++;
    }
```

## *while statement*

A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

```
while (condition)
  statement
```
If the condition becomes false, statement within the loop stops executing and control passes to the statement following the loop.

The condition test occurs before statement in the loop is executed. If the condition returns true, statement is executed and the condition is tested again. If the condition returns false, execution stops, and control is passed to the statement following while.

To execute multiple statements, use a block statement ({ }) to group those statement

The following while loop iterates as long as n is less than 3:

```
let n = 0;
let x = 0;
while (n < 3) {
  n++;
  x += n;
}
```
