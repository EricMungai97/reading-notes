# Dynamic Routes

[sources](https://nextjs.org/learn/basics/dynamic-routes)

*Dynamic routing* in Next.js is a way of creating URL patterns that can change based on user inputs. 

In Next.js, dynamic routes are defined using square brackets **[]** in the page file names. For example, a file named **[id]**.js would create a dynamic route that can match any URL with the format /<id>. 

The value of <id> can then be accessed within the component as a prop named params.

Dynamic routing is useful in many scenarios such as when creating a blog or a portfolio website, where you want to display different pages for different blog posts or projects.

To implement dynamic routing in Next.js, you need to create a `getStaticPaths` and a `getStaticProps` method in your component. The getStaticPaths method returns an array of possible values for the dynamic parameter, while the getStaticProps method returns the data to be rendered on the page based on the dynamic parameter value.

In summary, dynamic routing in Next.js allows you to create `flexible` and customizable URLs, making it easier to display dynamic content in your web application.

## Static file serving

[sources](https://nextjs.org/docs/basic-features/static-file-serving)

Next.js can serve `static files`, like images, under a folder called public in the root directory. Files inside public can then be referenced by your code starting from the base URL `(/)`.

Example

```
import Image from 'next/image'

function Avatar() {
  return <Image src="/me.png" alt="me" width="64" height="64" />
}

export default Avatar
```

