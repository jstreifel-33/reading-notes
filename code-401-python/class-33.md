# React III - Next.js and React Context

## Next.js

Source: [Next.js Docs](https://nextjs.org/learn/basics/navigate-between-pages)

### Navigation With Next.js

In Next.js our pages are organized a `pages/` folder. Coincidentally, this also determines the routes out app (convenient!). `pages/index.js` will correspond to `mysite.com/index` when deployed and this convention follows for other pages, and even nested folders within pages directory.

The `Link` component can be imported from Next.js, and uses the `/index` simplified conventions to pointing to pages within an app. This effectively handles routing for us.

NOTE: `Link` handles client-side navigation, and transitions are accomplished using javascript. This means we aren't loading an entirely new webpage when navigating between Next.js pages.

### Assets

Next.js can serve up static assets placed in the `public` folder, and this folder can be accessed from the root, similarly to `pages`.

For images, next provides an optimized `Image` component that can be imported and used in place of the original HTML `img` tag.

```jsx
import Image from 'next/image'

const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
)
```

### Metadata

Metadata may change while navigating our page, so Next.js also includes a `Head` component for easy control of metadata. Add it to any page component to change things like the favicon or Title of the page.

## React Context

Source: [FreeCodeCamp - React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)

React Context allows for the passing down and using of data within React **without using props**. React context should not be used for all data, and is best when used for data that does not require frequent updating.

**Context** is an API built into React, starting at version 16. Using it requires 4 steps:

1. Create context using `createContext`
2. Wrap the context provider around your component tree
3. Use the `value` prop to place a value on the context
4. Read the value within a component using a context consumer

```jsx
//Code example from FreeCodeCamp:

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
  return (
    <UserContext.Consumer>
      {value => <h1>{value}</h1>} 
      {/* prints: Reed */}
    </UserContext.Consumer>
  )
}
```

Context can also be consumed using the `useContext` hook, to make our code more concise. There isn't really a "right" way of using context though so it's up to preference.

```jsx
//useContext example from FreeCodeCamp:

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

React Context is useful for situations where data has to be read in multiple places, but should not be used heavily for performance reasons. Additionally, if state that you would place in Context will be updated frequently, it would be wise to use a global state manager like Redux instead.
