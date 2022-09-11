# **Javascript basics**

## *How HTTP sends data between computers*

The browser goes to the DNS server and finds the real address of the server that the website lives on.

Browser sends an HTTP request message to the server, asking it to send a copy of the website to the client.

If the server approves the client's request, the server sends the client a "200 OK" message which means ofcourse you can look at the website.

Server sends files to browser in a series of small chunks called data packets.

The browser assembles the small chunks into a complete webpage and displays it to you.

## *How HTML, CSS and JS files are "parsed" in the browser.*

The browser parses the HTML first, and that lead to the browser recognizing any `<link>` element references to external CSS stylesheets and `<script>`
element references to scripts.

As the browser parses the HTML, it sends requests back to the server for any CSS file it has found from `<link>` elements, and any Javascript files it has found `<script>`elements, and from those, then parses the CSS and JavaScript.

The browser generates an in-memory DOM tree from the parsed HTML, generates an in-memory CSSOM structure from the parsed CSS, and compiles and executes the parsed JavaScript.
 
As the browser builds the DOM tree and applies the styles from the CSSOM tree and executes the JavaScript, a visual representation of the page is painted to the screen, and the user sees the page content and can begin to interact with it.

## **How to find images to add to your website**

Go to google images and search for something suitable.

1. When you find the image you want, click on the image to get an enlarged view of it.
2. Right-click the image (Ctrl + click on a Mac), choose Save Image As…, and choose a safe place to save your image. Alternatively, copy the image's web address from your browser's address bar for later use.

3. To reduce your likelihood of violating copyright, you can use Google's license filter. Click on the Tools button, then on the resulting Usage rights option that appears below. You should choose the option Creative Commons licenses.

## How do you create a string vs a number in Javascript

For a string you have to enclose it in single quote marks, for a number you do not.

For example

```
let x = 'Player'
let y = 1
```

## *Variables in Javascript*

Variables are containers that store value.

We need variables to do anything interesting in programming.. If values couldn't change, then you couldn't do anything dynamic, like personalize a greeting message or change an image displayed in an image gallery.

## What is an HTML attribute

Special words used inside the opening tag to control the element's behaviour. Modifier of an HTML element type.

## Anatomy of an HTML element

* **The opening tag**: This consists of the name of the element (in this example, p for paragraph), wrapped in opening and closing angle brackets. This opening tag marks where the element begins or starts to take effect. In this example, it precedes the start of the paragraph text.

* **The content**: This is the content of the element. In this example, it is the paragraph text.

* **The closing tag**: This is the same as the opening tag, except that it includes a forward slash before the element name. This marks where the element ends. Failing to include a closing tag is a common beginner error that can produce peculiar results.


## Difference between `<article>` and `<section>` element tags

`<article>` encloses a block of related content that makes sense on its own without the rest of the page (e.g., a single blog post).

`<section>` is similar to `<article>`, but it is more for grouping together a single part of the page that constitutes one single piece of fuctionality functionality (e.g., a mini map, or a set of article headlines and summaries), or a theme.

## What elements does a typical website include

`<main>` is for content unique to this page. Use it only once per page, and put it directly inside `<body>`. Ideally this shouldn't be nested within other elements.

`<article>` encloses a block of related content that makes sense on its own without the rest of the page (e.g., a single blog post).

`<section>` is similar to `<article>`, but it is more for grouping together a single part of the page that constitutes one single piece of functionality (e.g., a mini map, or a set of article headlines and summaries), or a theme. It's considered best practice to begin each section with a heading; also note that you can break `<article>`s up into different `<section>`s, or `<section>`s up into different `<article>`s, depending on the context.

`<aside>` contains content that is not directly related to the main content but can provide additional information indirectly related to it (glossary entries, author biography, related links, etc.).

`<header>` represents a group of introductory content. If it is a child of `<body>` it defines the global header of a webpage, but if it's a child of an `<article>` or `<section>` it defines a specific header for that section (try not to confuse this with titles and headings).

`<nav>` contains the main navigation functionality for the page. Secondary links, etc., would not go in the navigation.

`<footer>` represents a group of end content for a page.

## How Metadata influences Search Engine Optimization

Specifying a description that includes keywords relating to the content of your page is useful as it has the potential to make your page appear higher in relevant searches performed in search engines.

Metadata elements such as author of the page and content of the page are a good example.

## How to use `<meta>` tag to specify metadata

You can use `<meta>` to specify your documents character encoding as shown below

```
<meta charset="utf-8">
```

You can also use it to add author and description.

```
<meta name="description" content="The MDN Web Docs site
  provides information about Open Web technologies
  including HTML, CSS, and APIs for both Web sites and
  progressive web apps.">
```

## First step to designing a website

To begin, you'll need to answer these questions:

1. What is your website about? Do you like dogs, New York, or Pac-Man?
2. What information are you presenting on the subject? Write a title and a few paragraphs and think of an image you'd like to show on your page.
3. What does your website look like, in simple high-level terms? What's the background color? What kind of font is appropriate: formal, cartoony, bold and loud, subtle?

## Most important question to answer when designing a website

What exactly do I want to accomplish?

• How will a website help me reach my goals?
• What needs to be done, and in what order, to reach  my goals?

All of this is called project ideation and is a necessary first step to reach your goal, whether you are a beginner or an experienced developer.

## `<h1>` element over a `<span>` element to display top level heading

The `<h1>` lement is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."

```
<h1>This is a top level heading</h1>
```

By default, most browser's user agent stylesheet will style an `<h1>` with a large font size to make it look like a heading (although you could style it to look like anything you wanted).

On the other hand, you could make any element look like a top level heading. Consider the following:

```
<span style="font-size: 32px; margin: 21px 0;">Not a top-level heading!</span>
```

This will render it to look like a top level heading, but it has no semantic value, so it will not get any extra benefits as described above. It is therefore a good idea to use the right HTML element for the right job.

## Benefits of using semantic tags in html

1. Search engines will consider its contents as important keywords to influence the page's search rankings (see SEO)
2. Screen readers can use it as a signpost to help visually impaired users navigate a page
3. Finding blocks of meaningful code is significantly easier than searching through endless divs with or without semantic or namespaced classes
4. Suggests to the developer the type of data that will be populated
5. Semantic naming mirrors proper custom element/component naming

## 2 Things that require Javascript un the browser

1. Displaying timely content updates.
2. Animated 2D/3D graphics.
3. Interactive maps.

## How to add Javascript to a HTML document

### *Internal Javascript*

Add the following in your head — just before your closing `</head>` tag:

```
<script>

  // JavaScript goes here

</script>
```

### *External Javascript*

* First, create a new file in the same directory as your sample HTML file. Call it script.js — make sure it has that .js filename extension, as that's how it is recognized as JavaScript.
* Replace your current `<script>` element with the following:

```
<script src="script.js" defer></script>
```

## Things I want to know more about

