# Next JS

[Source](https://nextjs.org/learn/basics/assets-metadata-css)

Next.js is a React framework that gives you building blocks to create web applications.

You can use React to build your UI, then incrementally adopt Next.js features to solve common application requirements such as `routing`, `data fetching`, ``integrations` - all while improving the developer and end-user experience.

## Client-Side Navigation

The `Link component` enables client-side navigation between two pages in the same Next.js app.

`Client-side navigation` means that the page transition happens using JavaScript, which is faster than the default navigation done by the browser.

## Code splitting and prefetching

Next.js does `code splitting` automatically, so each page only loads what’s necessary for that page. 

That means when the homepage is rendered, the code for other pages is not served initially.

This ensures that the homepage loads quickly even if you have hundreds of pages.

Only loading the code for the page you request also means that pages become isolated. If a certain page throws an error, the rest of the application would still work.

Whenever Link components appear in the browser’s viewport, Next.js automatically prefetches the code for the linked page in the background. By the time you click the link, the code for the destination page will already be loaded in the background, and the page transition will be near-instant!

## Assets, MetaData and CSS

## Assets

Next.js can serve `static assets`, like images, under the top-level public directory. 

Files inside public can be referenced from the root of the application similar to pages.

The public directory is also useful for `robots.txt`, `Google Site Verification`, and any other static assets.

**Image Component and Image Optimization**

Next.js also has support for Image Optimization by default. 

This allows for `resizing, optimizing, and serving` images in modern formats like WebP when the browser supports it. 

This avoids shipping large images to devices with a smaller viewport. It also allows Next.js to automatically adopt future image formats and serve them to browsers that support those formats.

## Metadata

`<Head>` is a React Component that is built into Next.js. It allows you to modify the <head> of a page.

To modify thr metadata of the page we modify whatever is inside the '<Head>' component.

## Third Party JavaScript

`Third-party JavaScript` refers to any scripts that are added from a third-party source. 

Usually, third-party scripts are included in order to introduce newer functionality into a site that does not need to be written from scratch, such as analytics, ads, and customer support widgets.

Scripts that need to load and execute as soon as possible are usually added within the <head> of a page. 

`next/script` is an extension of the HTML <script> element and optimizes when additional scripts are fetched and executed.

`strategy` controls when the third-party script should load.

A value of `lazyOnload` tells Next.js to load this particular script lazily during browser idle time.

`onLoad` is used to run any JavaScript code immediately after the script has finished loading.

Example

```
<Script
        src="https://connect.facebook.net/en_US/sdk.js"
        strategy="lazyOnload"
        onLoad={() =>
          console.log(`script loaded correctly, window.FB has been populated`)
        }
      />
```

## CSS

`CSS modules` allow you to locally scope CSS at the component-level by automatically creating unique class names.

Next.js’s code splitting feature works on CSS Modules as well. It ensures the minimal amount of CSS is loaded for each page. This results in smaller bundle sizes.

You can style your Next.js application in a variety of ways, including:

1. Sass
2. PortCSS libraries like Tailwind CSS
3. CSS-in-JS libraries such as `styled-jsx`, `styled components` and `emotion`.

The default export of `_app.js` is a top-level React component that wraps all the pages in your application. 

In Next.js, you can add global CSS files by importing them from `pages/_app.js.` You cannot import global CSS anywhere else.

The reason that global CSS can't be imported outside of pages/_app.js is that global CSS affects all elements on the page


## React Context for Beginners

[source](https://www.freecodecamp.org/news/react-context-for-beginners/)

It lets you easily share state in your applications.

`React context` allows us to pass down and use (consume) data in whatever component we need in our React app without using props.

**When should you use React Context**

It is great when you are passing data that can be used in any component in your application.

These types of data include: 

1. Theme data
2. User data
3. Location-specific data

You can think of React context as the equivalent of global variables for our React components.

**Problems React Context Solves**

React context helps us avoid the problem of `props drilling`.

Props drilling is when you pass props down multiple levels to a nested component, through components that don't need it.

**How to Use React context**

Context is an API that is built into React, starting from React version 16.

This means that we can create and use context directly by importing React in any React project.

***Four steps to using React Context***

1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.

## The Use Context Hook

We can pass the entire context object to React.useContext() to consume context at the top of our component.

Example

```
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  const value = React.useContext(UserContext);  
    
  return <h1>{value}</h1>;
}
```
The benefit of the useContext hook is that it makes our components more concise and allows us to create our own custom hooks.

Don't reach for context right away. See if you can better organize your components to avoid prop drilling.