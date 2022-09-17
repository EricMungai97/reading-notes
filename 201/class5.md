# **Using Images in HTML**

## Real world use case for the alt attribute being used in a website.

If you have an image of a giraffe on your website you could use the alt attribute on your image element to improve accessibility by screen readers and SEO's.

Example
```
img src="images/giraffe.jpg" alt="Giraffe" />
```


## How to improve accessibility of images in an HTML document?

Using the alt attribute

Putting the images for your website on the same server as your HTML.

## When the figure element would be useful in an HTML document.

When we want to put an image, illustration or diagram to our html and be able to  move it to another part of the document or appendix without affecting the main flow of a document.
## Difference between a gif image and an svg

**GIF**, just like other image formats, are not resolution-independent, and will therefore look pixelated when scaled up or viewed on higher resolutions. **SVG** is scalable and resolution-independent, and will look crisp clear on any screen resolution.

[Citation](https://www.sarasoueidan.com/blog/svg-vs-gif/#:~:text=GIF%2C%20just%20like%20other%20image,clear%20on%20any%20screen%20resolution.)

## ***Image type to use to display a screenshot on your website and why?***

PNG this is because  a screenshot is an image without that much color data but has rapid transition between colors that need to remain sharp.

## **Using Color in CSS AND Styling html Text  Elements**

## ***difference between foreground and background colors of an HTML element***

foreground defines the color of HTML elements content whereas backgound-color is the text's background color.

## ***Your friend asks you to give his colorless blog website a touch up. How would you use color to give his blog some character?***

I would add in a background-color to his entire page.

Add color to  diffreent html elements of his using  color property.

## ***What should you consider when choosing fonts for an HTML document?***

1. Are we using a websafe font.
2. Is your font clear and legible.
3. FontFamily

## What do font-size, font-weight, and font-style do to HTML text elements?

* font-size; sets the size of the font.
* font-weight;sets how bold text is.
* font-style;used to turn italic text on or off.

## Two ways you to add spacing around the characters displayed in an h1 element.

```
h1::first-line{
  word-spacing: 4px;
}
```
```
h1::first-line{
  letter-spacing: 4px
}