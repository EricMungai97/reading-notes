# **Design web pages with CSS**

## **What is CSS?**

*CSS (Cascading Style Sheets)* is a language for specifying how documents are presented to users — how they are styled, laid out, etc

*CSS* can be used for very basic document text styling — for example, for *changing the color* and size of headings and links. It can be used to create a layout — for example, turning a single column of text into a layout with a main content area and a sidebar for related information. It can even be used for effects such as animation.

## ***CSS syntax***

CSS is a *rule-based language* — you define the rules by specifying groups of styles that should be applied to particular elements or groups of elements on your web page.

For example, you can decide to have the main heading on your page to be shown as large red text. The following code shows a very simple CSS rule that would achieve the styling described above:

```
 h1 {
    color: red;
    font-size: 5em;
}
```

- The CSS rule opens with a selector. `h1`
- We then have a set of curly braces { }.nside the braces will be one or more declarations, which take the form of property and value pairs. We specify the property `color` in the above example).
- This example contains two declarations, one for `color` and the other for `font-size`. Each pair specifies a property of the element(s) we are selecting `h1` in this case), then a value that we'd like to give the property.

## **Three Ways to Insert CSS**

There are three ways of inserting a style sheet:

1. External CSS
2. Internal CSS
3. Inline CSS

## External CSS

With an external style sheet, you can change the look of an entire website by changing just one file!

Each HTML page must include a reference to the external style sheet file inside the 
`link` element, inside the head section.

```Example
External styles are defined within the <link> element, inside the <head> section of an HTML page:

<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

## Internal CSS

An internal style sheet may be used if one single HTML page has a unique style.

The internal style is defined inside the `style`
element, inside the head section.

Example
Internal styles are defined within the `style` element, inside the `head` section of an HTML page:

```
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

## Inline CSS

An inline style may be used to apply a unique style for a single element.

To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.

Example
Inline styles are defined within the "style" attribute of the relevant element:

```<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

## Multiple Style Sheets

If some properties have been defined for the same selector (element) in different style sheets, the value from the last read style sheet will be used. 


## Cascading Order

- Inline style (inside an HTML element)
- Internal style sheets (in the head section)
- External
- Browser default
