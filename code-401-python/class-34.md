# React IV - Next.js Dynamic Routes and Deployment

## Next.js Dynamic Routes

Source: [Next.js docs - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)

With dynamic routes, a Next.js app can determine its pages based on provided data, rather than having them hard coded.

Dynamic routes are defined by pages that contained in `[ ]`, such as `[id].js`.

A getStaticPaths method is used to retrieved an array of objects representing possible data (in this case, id's).

A getStaticProps method then retrieves and passes the data associated with an id to `[id].js`.

## Next.js Deployment

Source: [Next.js docs - Deploying your App](https://nextjs.org/learn/basics/deploying-nextjs-app)

The easiest way to deploy a Next.js app is using the Vercel platform. It is serverless and allows for importing of existing repositories from Github.

Since Vercel is made by the creators of Next.js, it has first class support for Next.js apps.

**DPS**: **D**evelop, **P**review, **S**hip

Next.js apps can also be hosted by any provider who supports Node.js.

Ensure that your package.json is built correctly, and includes the following:

```js
{
  "scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start"
  }
}
```
