# Reading Notes 3

## Creating a basic link.

To create a basic link, we wrap text or other content inside an `<a>` lement and using the `href` attribute.
For example

``` 
<p>
Link to
<a href ="https://www.google.com">Google Homepage</a>.
</p>
```

## The href attribute contains what information?

The url the hperlink points to.

## What are some ways we can ensure links on our pages are accessible to all readers?

Keeping our link text short as possible.

Avoiding using  link text like click here as it throws off screen readers.

Avoiding repetition of url as part of link text.
## Normal Flow

 how the browser lays out HTML pages by default when you do nothing to control page layout. Let's look at a quick HTML example:
```
<p>I love my cat.</p>

<ul>
  <li>Buy cat food</li>
  <li>Exercise</li>
  <li>Cheer up friend</li>
</ul>
```

[cite normal flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)

<p>The end!</p>

## Differences between block-level and inline elements

 1. Content model  Block level elements can contain both inline elements and other block element.
 2. Default formatting - block elements begin on new lines whereas inline elements can begin anywhere.

## Positioning

**Static positioning** is the default for every html element.

## Advantages of using absolute positioning on an element

Absolute positioned elements sit on their own layer therefore we can use them to create isolated ui interfaces e.g. pop upinfo boxes.

## Key difference between fixed and absolute positioning

An absolute positioning fixes an element in place relative to its nearest positioned ancestor while a fixed positioning fixes an element in place relative to the visible portion of the viewport.

## Difference between a function declaration and a function invocation

The act of creating a function is function declaration while the act running a function is function invocation.

## Difference between a parameter and an argument

Function parameters are the names listed in the function's definition. Function arguments are the real values passed to the function.

example
```
function example(parameter) {
  console.log(parameter); // Output = foo
}

const argument = "foo";

example(argument);
```

[parameter vs argument cite](https://developer.mozilla.org/en-US/docs/Glossary/Parameter)

## Pick 2 benefits to pair programming and reflect on how these benefits could help you on your coding journey.

* Greater efficiency;this would help in that working with my teammate we could catch mistakes faster reducing the chance of debugging later.

* Social skills; my interpersonal skills would improve a great deal working with someone else with a different coding style and personality.This is because I would come out of my shell so we could the work done.