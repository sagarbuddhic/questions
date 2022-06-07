# Questions

## Javascript

**Var keyword vs let & const?**

variables with var keyword has default hoisting.\
Declaring a variable after its usage is allowed in javascript,\
all declaration will be moved up by default which is called hoisting.

It is a good practice to declare a variable before it is used.

**Closures:**

A closure is a function having access to the parent scope, even after the parent function has closed.

**Currying:**

Transforming a function.

```
function curry() {
    let a = 0;
    return function adder(b) {
      if(!b) {
      	return a;
      }
      a += b;
      return adder;
    };
  };

let curriedSum = curry();

alert( curriedSum(1)(2)(3)(4)() ); // 3
```

## React


**React Lifecycle:**

Constructor\
getDerivedStateFromProps\
Render\
ComponentDidMount

getDerivedStateFromProps\
ShouldComponentUpdate\
Render\
getSnapshotBeforeUpdate()\
ComponentDidUpdate

**useEffect Lifecycles:**

componentDidMount, componentDidUpdate, componentWillUnmount

**React Optimizations**

Avoid re-renders by providing array of values in useEffect.\
Big Calculations useMemo to store the output.\
useCallback to store the function.\
code splitting, React.lazy, dynamic import.

**Call Endpoint Once to Fetch Initial Data**

UseEffect with empty Array is called only after first render.

**Function with big calculations**

UseMemo - Runs the function only if arguments change other it will return the stored value.

**Difference with useMemo vs useCallback**

useMemo - stores value.\
useCallback - stores function

**Dispatch & Action in useReducer ?**

dispatch is called with action which calls the reducer to return the state.

**devtools display state**

usedebugvalue

**allow transition in state**

useTransition

## Nextjs

**nextjs advantages**

comes with webpack.\
dynamic import, lazyload using suspense.\
compiler replaces babel for individual files and terser for minifying output bundles.
automatic static optimization.

**What is pre-rendering**

This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. Pre-rendering can result in better performance and SEO.

**What is hydration**

Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive.

**getServerSideProps vs getStaticProps**

Next.js will pre-render this page on each request using the data returned by getServerSideProps.\
Next.js will pre-render this page at build time using the props returned by getStaticProps.

**ISR**

Incremental Static Generation uses revalidate.
When a request is made to a path that hasn’t been generated, Next.js will server-render the page on the first request.
Future requests will serve the static file from the cache. ISR on Vercel persists the cache globally and handles rollbacks.

**SWR**

react library - stale while revalidate.







