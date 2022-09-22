# Reading Notes 8

## Flexbox is designed for one-dimensional content. Explain what this means?

Flexbox is a tool designed  to help you layout group items that only have a width and a length.

## Explain the difference between the main axis and cross axis?

The main axis is acquired from the `flex-direction` property. If your flex-direction property is row the main axis would be along the row.The cross axis runs in the opposite direction to the main so it runs along the column.

## How can using certain properties of flexbox negatively impact accessibility?

Reversing flow of items using `flex-direction` property like `row-reverse` or `column-reverse` only reorders visual order and not logical order. This hinders the screen readers as they read the content using the logical order.

## What are some advantages of using flexbox over float?

1. You can center a block of content inside its parent.
2. You can easily make all the children of a container take up an equal amount of the available width/height, regardless of how much width/height is available.
3. You can easily make all columns in a multiple-column layout adopt the same height even if they contain a different amount of content.

[cite](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

## How does this topic connect with your long term goals?

This topic will help me to be able to easily structure the wireframe of website making me a better developer.
