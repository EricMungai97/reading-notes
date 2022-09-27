# Reading Notes 10

## Explain how the ability to use   and audio on the web has evolved since the early 2000s.

In the early 2000s audio and video on the web was made possible by proprietary plugin-based technologies. This technologies had  security and accessibility issues. Today we use HTML to add audio and video elements together with other API's.

## Describe the use of the src and controls attributes in the `<video>` element

The `src` (source) attribute contains a path to the video you want to embed whereas the `control` attribute enables the web user to control the video and audio playback.

## Why is it important to have fallback content inside the `<video>` element?

The fallback content is displayed if the browser accessing the page doesn't support the `video` element.


## Write a very short story where `<audio>` and `<video> `are characters.
`<audio>` and `<video>` are two close friends that have nearly the same personalties except but a few which makes both of them unique. `<audio>`
 doesnt support width and height attributes because it has nothing to display.

## How does Grid layout differ from Flex?

Grid is made for Two-dimensional layout while flexbox is for one. Flexbox can work on either row or columns at a time , but Grid can work on both.

[cite](https://www.geeksforgeeks.org/comparison-between-css-grid-css-flexbox/#:~:text=Grid%20is%20made%20for%20two,in%20this%20type%20of%20scenario.)

## Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences

1. Grid container - the element on which `display: grid` is applied.
2. grid item -the children of the grid container
3. grid line- the dividing lines that make up the structure of the grid.

## Besides making a site visually appealing across different screen sizes, why should developers make images responsive?

It helps us deliver the optimal file size and improves the loading time for your website improving user experience.

[cite](https://www.lab21.gr/blog/use-responsive-images/#:~:text=Having%20responsive%20images%20is%20important,for%20creating%20a%20responsive%20image.)

## Define the following `<img>` attributes srcset and sizes. Write an example of how they are used.

`screst`- defines the set of images we will allow the browser to choose between, and what size each image is.

`sizes`- defines a set of media conditions (e.g. screen widths) and indicates what image size would be best to choose, when certain media conditions are true.

[cite](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

## How is srcset more helpful for responsive images than CSS or JavaScript?

`Screst` - provides additional source images along with hints to help the browser pick the right image for the specific screen size, which CSS mor JS can't do.
