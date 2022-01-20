# ES6, React, Tailwind CSS, and Next.js

## ES6 and React

Remember Javascript and React? Strap in, because we're going back.

* [ES6 Refresher Overview](https://www.taniarascia.com/es6-syntax-and-feature-overview/)
* [React Docs](https://reactjs.org/)
  * [Hello World](https://reactjs.org/docs/hello-world.html)
  * [JSX](https://reactjs.org/docs/introducing-jsx.html)
  * [Rendering Elements](https://reactjs.org/docs/rendering-elements.html)
  * [Components & Props](https://reactjs.org/docs/components-and-props.html)
  * [State & Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
  * [Handling Events](https://reactjs.org/docs/handling-events.html)

It's like riding a bike!

## Tailwind

Source: [tailwindcss.com - Utility-First Fundamentals](https://tailwindcss.com/docs/utility-first)

Tailwind is awesome.

So, normally to style things you would write CSS to go along with your HTML.

Not with Tailwind.

Tailwind is **utility driven styling framework** that uses pre-existing classes to style your HTML.

Docs Example:

```HTML
<div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-lg flex items-center space-x-4">
  <div class="shrink-0">
    <img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo">
  </div>
  <div>
    <div class="text-xl font-medium text-black">ChitChat</div>
    <p class="text-slate-500">You have a new message!</p>
  </div>
</div>
```

Every class in the above HTML relates to a Tailwind style setting.

* `flex`, `shrink-0`, `p-6` - flexbox and padding to control overall layout
* `max-w-sm`, `mx-auto` - max-width and margin utilities to apply width constraints
* `bg-white`, `rounded-xl`, `shadow-lg` - background color, border radius, and box-shadow for appearance
* `w-12`, `h-12` - size of logo image
* `space-x-4` - spacing between logo and text
* `text-xl`, `text-black`, `font-medium` - text styling.

Does it look busy? Yes. Is it a lot to type? Sure. But it's **so convenient** and Tailwind has a ridiculous number of utility classes. You can quickly spin up a custom look in no time, flat.

And the best part? **No custom CSS required.** Really.

It may feel like in-line styling, but Tailwind also allows for responsive design and state variants in styling. Hover, focus, and other states are usable out of the box.

Worried about repetition? Extract components. React is great at that. If that's not enough for you, you can even create custom Sass classes that apply the classes for you. (Sass is supported out fo the box in Next.js).

Which brings us to....

## Next.js

Source: [nextjs.org - Create a Next.js App](https://nextjs.org/learn/basics/create-nextjs-app)

### What is Next.js?

So let's get a little less candid.

Next.js is a React Framework that aims to have best-in-class developer experience. It includes the following features:

* Intuitive page-based routing
* Pre-rendering, both static (SSG) and server-side (SSR), on a per-page basis
* Automatic code splitting
* Client-side routing with prefetching
* CSS and Sass support
* Dev environment with Fast Refresh support
* API routes for building API endpoints
* Fully extendable

Tons of people and companies use Next.js, probably for good reason.

### Actually getting started

So first of all you'll need Node.js, version 10.13 or later.

Run this command:

`npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/learn-starter"`

To run the dev server:

`cd nextjs-blog`

`npm run dev`

Now your dev server is live on port 3000. Navigating to it will bring you to a default page with information about Next.js, including links to the docs and some tutorials.

You can customize the page by going to `pages/index.js`, changing something, and saving your change. Next supports fast refresh while the dev server is running, so your page should already reflect the change.

That's it for getting started! Now it's off to the races. Time to get Reacty again.
