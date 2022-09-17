# Reading Notes 1

## Basics of HTML,CSS & JS

This topic matters to me because it introduces me to useful terminology and their applications for someone who is just starting to learn this langauges. Learning the basic s is how you become great at something.

## Importance of using semantic elemnts in HTML

1. It makes your website ven more discoverable on search engines.
2. Makes it easy to find blocks of code
3. They assist visually impaired naviagate web pages.
4. Help us know something function.

## Headings

There are 6 level of headings in HTML.

That is,`<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`.

## Uses of  `<sub>` and `<sup>`

* Marking up dates
* Chemical formulae
* Marking up math equations

## `<abbr>` element

To provide the full expansion of a term we use the `titel` attribute.

For example:

```
<p>I think <abbr title="Reverend">Rev.</abbr> Green did it in the kitchen with the chainsaw.</p>
```

## Ways we can apply CSS to our HTML

There are 3 ways to do this:

1. External CSS
2. Internal CSS
3. Inline CSS

## External CSS

Enables us to change an entire website by changing justone file.

External styles are defined within the <link> element, inside the <head> section of an HTML page:

```
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
```

## Internal CSS

We use this when we want a HTML page to have it's own unique style.

WE define it with the `style` element, inside the `head` section of an HTML page:

```
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}
<style>
</head>
```

## Inline CSS

Used to style a single element.

To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property

```
<p style="color: red">I love cats</p>
```

## Review the block of code below and answer the following questions

What is representing the selector? `h2`

Which components are the CSS declarations? ```color: black;```
              ```padding: 5px;```

Which components are considered properties?

`color`

`padding`

```
  h2 {
     color: black;
     padding: 5px;
   }
   ```

## What data type is a sequence of text enclosed in single quote marks?

A string  for example

```
let name = 'Eric'
```

## List 4 types of JavaScript operators.

1. Addition
2. Assignment
3. Strict equality
4. Subtraction

## Describe a real world Problem you could solve with a Function.


An if statement checks a `condition` and if it evaluates to true, then the code block will execute.

What is the use of an else if?

To specify a new condition to test, if the first condition is false.

## 3 types of comparison operators.
``
•	`===` and `!==` — test if one value is identical to, or not identical to, another.

•	`<` and` >` — test if one value is less than or greater than another.

•	`<=` and `>=` — test if one value is less than or equal to, or greater than or equal to, another.

•	`&&` — AND; allows you to chain together two or more expressions so that all of them have to individually evaluate to true for the whole expression to return true.

•	`||` — OR; allows you to chain together two or more expressions so that one or more of them have to individually evaluate to true for the whole expression to return true.


## What is the difference between the logical operator && and ||?

`&&` helps you put together 2 or more expressions such that all of them has to evaluate to true for the whole expression to return true while `||` allows you to put 1 or more expressions together such that 1 or more  has to evaluate to true for the whole expression to return true.

[comparison operators citation](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)