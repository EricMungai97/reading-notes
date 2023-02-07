# React

[Source](https://reactjs.org/docs/hello-world.html)

## Introducing JSX

A syntax extension to JavaScript

Example

`const element = <h1>Hello, world!</h1>;`

After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.

Since JSX is closer to JavaScript than to HTML, React DOM uses `camelCase` property naming convention instead of HTML attribute names.

For example, class becomes className in JSX, and tabindex becomes tabIndex.

## Components and Props

Components let you split the UI into independent, reusable pieces.

`Props` which stands for properties

`Props`are read only.

All react components must act like pure functions with respect to their props.

`Keys` help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

## Next JS

[Source](https://nextjs.org/learn/basics/create-nextjs-app)
 
`Next. js` is a front-end framework that makes it easy to build fast websites with React—which is a free and open-source front-end JavaScript library for building user interfaces based on UI components.

Next JS does the following for us:

1. Bundles our code
2. Does production optimizations such a `code splitting.`
3. Statically pre-renders some pages for performance and SEO. Also enables us to use server-side rendering.
4. Makes is possible to connect our React app to a data store.

Next.js aims to have best-in-class developer experience and many built-in features, such as:

1. An intuitive page-based routing system (with support for dynamic routes)
2. Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
3. Automatic code splitting for faster page loads
4. Client-side routing with optimized prefetching
5. Built-in CSS and Sass support, and support for any CSS-in-JS library
6. Development environment with Fast Refresh support
7. API routes to build API endpoints with Serverless Functions
8. Fully extendable

## Things I want to Know More About

How to use NEXT JS to build out an app.