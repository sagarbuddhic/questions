# Questions

### [CSS](#css-topics)
### [Javascript](#javascript-topics)
### [-ReactJS](#reactjs-topics)
### [-NodeJS](#nodejs-topics)
### [-ExpressJS](#expressjs-topics)
### [-NextJS](#nextjs-topics)
### [-Rest Apis](#rest-apis-topics)
### [-Containerization](#containerization-topics)
### [-AWS](#aws-topics)
### [-Jenkins](#jenkins-topics)
### [-Testing](#testing-topics)
### [-12 Factor](#12-factor-topics)

## CSS Topics

***Descendant Selector (space)***

The descendant selector matches all elements that are descendants of a specified element.

```
div p {
  background-color: yellow;
}
```

***Child Selector (>)***

The child selector selects all elements that are the children of a specified element.

```
div > p {
  background-color: yellow;
}
```

***Adjacent Sibling Selector (+)***

The adjacent sibling selector is used to select an element that is directly after another specific element.

```
div + p {
  background-color: yellow;
}
```

***General Sibling Selector (~)***

The general sibling selector selects all elements that are next siblings of a specified element.

```
div ~ p {
  background-color: yellow;
}
```

***pseudo***

A pseudo-class is used to define a special state of an element.

Example: Style an element when a user mouses over it.

```
a:hover {
  color: #FF00FF;
}
```

***Pseudo-element***

```
h1::after {
  content: url(smiley.gif);
}
```

***CSS [attribute] Selector***

The [attribute] selector is used to select elements with a specified attribute.

```
a[target] {
  background-color: yellow;
}
```

## Javascript Topics

***Web Socket vs HTTP***

Web Socket:

WebSocket is a bidirectional communication protocol that can send the data from the client to the server or from the server to the client by reusing the established connection channel. The connection is kept alive until terminated by either the client or the server.

Almost all the real-time applications like (trading, monitoring, notification) services use WebSocket to receive the data on a single communication channel.

All the frequently updated applications used WebSocket because it is faster than HTTP Connection.

HTTP Connection:

The HTTP protocol is a unidirectional protocol that works on top of TCP protocol which is a connection-oriented transport layer protocol, we can create the connection by using HTTP request methods after getting the response HTTP connection get closed.

Simple RESTful application uses HTTP protocol which is stateless.

When we do not want to retain a connection for a particular amount of time or reuse the connection for transmitting data; An HTTP connection is slower than WebSockets.

***web socket***

```
// Create WebSocket connection.
const socket = new WebSocket('ws://localhost:8080');

// Connection opened
socket.addEventListener('open', function (event) {
    socket.send('Hello Server!');
});

// Listen for messages
socket.addEventListener('message', function (event) {
    console.log('Message from server ', event.data);
});
```

***web workers***

Web Workers are a simple means for web content to run scripts in background threads.A worker is an object created using a constructor (e.g. Worker()) that runs a named JavaScript file — this file contains the code that will run in the worker thread; workers run in another global context that is different from the current window.you can't directly manipulate the DOM from inside a worker, or use some default methods and properties of the window object.

The magic of workers happens via the postMessage() method and the onmessage event handler. When you want to send a message to the worker, you post messages to it like this (main.js):

```
first.onchange = function() {
  myWorker.postMessage([first.value, second.value]);
  console.log('Message posted to worker');
}

second.onchange = function() {
  myWorker.postMessage([first.value, second.value]);
  console.log('Message posted to worker');
}

```

```
onmessage = function(e) {
  console.log('Message received from main script');
  const workerResult = 'Result: ' + (e.data[0] * e.data[1]);
  console.log('Posting message back to main script');
  postMessage(workerResult);
}
```

***Var VS let & const keyword?***


Declaring a variable after its usage is allowed in javascript,all declaration will be moved up by default which is called hoisting.Variables with var keyword has default hoisting.\

It is a good practice to declare a variable before it is used.

***Destructuring***

The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

```
[a, b, ...rest] = [10, 20, 30, 40, 50];

console.log(rest);
// expected output: Array [30,40,50]
```

***Logical AND (&&)***

The operator returns the value of the first falsy operand encountered when evaluating from left to right, or the value of the last operand if they are all truthy.

```
12 && 13 && 14 // 14
12 && 0 && false && 15 // 0
```

***Logical OR (||)***

The logical OR (||) operator (logical disjunction) for a set of operands is true if and only if one or more of its operands is true.
The operator returns the value of the first truthy operand encountered when evaluating from left to right, or the value of the last operand if they are all falsey.

```
12 || 13 || 15 // 12
undefined || false // false
```

***Nullish coalescing operator (??)***

The nullish coalescing operator (??) is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.

This can be seen as a special case of the logical OR (||) operator, which returns the right-hand side operand if the left operand is any falsy value, not only null or undefined. In other words, if you use || to provide some default value to another variable foo, you may encounter unexpected behaviors if you consider some falsy values as usable (e.g., '' or 0). See below for more examples.

```
'' ?? 'test' // ''
null ?? 'test' // 'test'
```

***Higher order function***

In Javascript, functions can be assigned to variables in the same way that strings or arrays can. They can be passed into other functions as parameters or returned from them as well.

A “higher-order function” is a function that accepts functions as parameters and/or returns a function.

***in operator***

The in operator returns true if the specified property is in the specified object or its prototype chain.

```
'test' in {'test': 't'} // true
```

***this keyword***

The JavaScript this keyword refers to the object it belongs to. This has different values depending on where it is used. In a method, this refers to the owner object and in a function, this refers to the global object.

***Event Bubbling***

When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.The process is called “bubbling”, because events “bubble” from the inner element up through parents like a bubble in the water.

***Event Propagation***

If an element has multiple event handlers on a single event, then even if one of them stops the bubbling, the other ones still execute.

In other words, event.stopPropagation() stops the move upwards, but on the current element all other handlers will run.

To stop the bubbling and prevent handlers on the current element from running, there’s a method event.stopImmediatePropagation(). After it no other handlers execute.

***Anonymous Functions***

Anonymous functions can be used as an argument to other functions or as an immediately invoked function execution.

***Closures:***

A closure is a function having access to the parent scope, even after the parent function has closed.

***Currying:***

Currying is translating a function from callable as f(a, b, c) into callable as f(a)(b)(c).

Example below of using closures, currying and recursive function.

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

***Recursive***

In programming terms, a recursive function can be defined as a routine that calls itself directly or indirectly.

***Spread***

Spread syntax (...) allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.

```
let obj1 = { foo: 'bar', x: 42 };
let obj2 = { foo: 'baz', y: 13 };

let mergedObj = { ...obj1, ...obj2 };
```

***Rest***

The rest parameter syntax allows a function to accept an indefinite number of arguments as an array, providing a way to represent variadic functions in JavaScript.

***Parse Int***

The parseInt method parses a value as a string and returns the first integer.

A radix parameter specifies the number system to use:

2 = binary, 8 = octal, 10 = decimal, 16 = hexadecimal.

```
parseInt('32', 10) // 32
```

***Math Floor***

The Math.floor() function returns the largest integer less than or equal to a given number.

```
console.log(Math.floor(5.95));
// expected output: 5

console.log(Math.floor(5.05));
// expected output: 5

console.log(Math.floor(5));
// expected output: 5

console.log(Math.floor(-5.05));
// expected output: -6
```

***Math.Ceil***

The Math.ceil() function always rounds a number up to the next largest integer.

***Math.round()***

The Math.round() function returns the value of a number rounded to the nearest integer.

console.log(Math.round(5.95), Math.round(5.5), Math.round(5.05));
// expected output: 6 6 5

***JSON Parse***

JSON.Parse && JSON.stringify

***defer attribute***

The defer attribute specifies that the script should be executed after the page has finished parsing, but it only works for external scripts.

***prototype***

inheritance

```
//Student.prototype = Person.prototype;
Student.prototype = new Person();
Student.prototype.constructor = Student;

```

***Concatenation***

```
let test = 'test' + 'best' // testbest
```

***Template literals (Template strings)***

Template literals are literals delimited with backtick (`) characters, allowing for multi-line strings, for string interpolation with embedded expressions, and for special constructs called tagged templates.

```
`string text ${expression} string text`
```

***typeof ob === "undefined"***

One reason to use typeof is that it does not throw an error if the variable has not been declared.

***window vs document***

Window is the main JavaScript object root, aka the global object in a browser, and it can also be treated as the root of the document object model. You can access it as window.

window.screen or just screen is a small information object about physical screen dimensions.

window.document or just document is the main object of the potentially visible (or better yet: rendered) document object model/DOM.

Since window is the global object, you can reference any properties of it with just the property name - so you do not have to write down window. - it will be figured out by the runtime.

***delete operator***

The JavaScript delete operator removes a property from an object;

delete object.property

When you delete an array element, the array length is not affected.When the delete operator removes an array element, that element is no longer in the array. In the following example, trees[3] is removed with delete.

```
var trees = ['redwood', 'bay', 'cedar', 'oak', 'maple'];
delete trees[3];
if (3 in trees) {
    // this is not executed
}
```

***eval***

The eval() method evaluates or executes an argument.

```
let text = "x * y";
let result = eval(text);
```

With eval(), malicious code can run inside your application without permission.

With eval(), third-party code can see the scope of your application, which can lead to possible attacks.

***window objects***

localStorage - No Expiration date. 
 
history
innerHeight
innerWidth
localStorage.getItem("test1");
sessionStorage.
navigator.geoLocation
pageXOffset
screen
document.cookie

***singleton***


```
var Singleton = (function () {
    var instance;

    function createInstance() {
        var object = new Object("I am the instance");
        return object;
    }

    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();

function run() {

    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();

    console.log("Same instance? " + (instance1 === instance2));
}
```


***let vs const***

both are block scoped.
we can change let values but if we try to change const values we get Uncaught TypeError.

***Arrow function vs Normal function***

Arrow functions don't have their own bindings to this, arguments or super, and should not be used as methods.\
Arrow functions don't have access to the new.target keyword.\
Arrow functions aren't suitable for call, apply and bind methods, which generally rely on establishing a scope.\
Arrow functions cannot be used as constructors.\
Arrow functions cannot use yield, within its body.

***Tree Shaking***

Tree shaking is a term commonly used within a JavaScript context to describe the removal of dead code.

In modern JavaScript applications, we use module bundlers (e.g., webpack or Rollup) to automatically remove dead code when bundling multiple JavaScript files into single files. This is important for preparing code that is production ready, for example with clean structures and minimal file size.

***Common javascript functions***

***Map***

The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.\

```
const filteredNumbers = numbers.map((num, index) => {
  if (index < 3) {
    return num;
  }
});
 ```

 ***Filter***

The filter() method creates a new array with all elements that pass the test implemented by the provided function.\

```
const result = ages.filter(checkAdult);

function checkAdult(age) {
  return age >= 18;
}
```

***Reducer***

The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

```
reduce((previousValue, currentValue, currentIndex, array) => { /* ... */ }, initialValue)
```

***Some***

The some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array.

```
const array = [1, 2, 3, 4, 5];

// checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
```

***Every***

Every element should satisfy the condition.

***Includes***

Check if an array includes a value. We can also check strings.

```
Includes(searchElement, fromIndex)

const array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true
```

***Slice***

The slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included)where start and end represent the index of items in that array. The original array will not be modified.

```
slice(start, end)

start - start index.
end - index of the value to be excluded.
```

***Splice***

The splice() method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place. 

```
Remove 0 (zero) elements before index 2, and insert "drum"

let myFish = ['angel', 'clown', 'mandarin', 'sturgeon']
let removed = myFish.splice(2, 0, 'drum')
```

***Shift & Unshift***

shift() removes the first element from an array, unshift() adds a new element to the start of the array.

***Fill***

```

const heights2 = [1, 2, 4, 5, 6, 7, 1, 1];
heights2.fill(0, 4);
console.log(heights2); // [1, 2, 4, 5, 0, 0, 0, 0]
```

***Reverse***

```
const reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]
```

***Sort***

```
const numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
  return a - b;
});
console.log(numbers);

```

***Object.entries***

```
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// expected output:
// "a: somestring"
// "b: 42"
```

***Find***

The find() method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// expected output: 12
```

***Flat***

```
const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// expected output: [0, 1, 2, 3, 4]
```

***css***

style.display
style.

## ReactJS Topics

***React Lifecycle:***

Mount Phase:

Constructor\
getDerivedStateFromProps\
Render\
ComponentDidMount

Update Phase:

getDerivedStateFromProps\
ShouldComponentUpdate\
Render\
getSnapshotBeforeUpdate()\
ComponentDidUpdate

UnMount Phase:

ComponentWillUnmount

***useEffect Lifecycles:***

componentDidMount, componentDidUpdate, componentWillUnmount

***React Optimizations***

Avoid re-renders by providing array of values in useEffect.\
Big Calculations useMemo to store the output.\
useCallback to store the function.\
code splitting, React.lazy, dynamic import.

***React JS Multiple SetStates***

On a button click with multiple set states, react has optimization which runs in set state in batches.

React batches state updates that occur in event handlers and lifecycle methods. Thus, if you update state multiple times in a <div onClick /> handler, React will wait for event handling to finish before re-rendering.This only works in React-controlled synthetic event handlers and lifecycle methods. State updates are not batched in AJAX and setTimeout event handlers.

React 18:

Batch Updates are available for all events.

***Redux***

The whole global state of your app is stored in an object tree inside a single store. The only way to change the state tree is to create an action, an object describing what happened, and dispatch it to the store. To specify how state gets updated in response to an action, you write pure reducer functions that calculate a new state based on the old state and the action.

```
function counterReducer(state = { value: 0 }, action)
```

```
store.dispatch({ type: 'counter/incremented' })
```

***How does Redux compare to the React Context API?***

Similarities

Both Redux and React's Context API deal with "prop drilling". That said, they both allow you to pass data without having to pass the props through multiple layers of components. Internally, Redux uses the React context API that allows it to pass the store along your component tree.

Differences

With Redux, you get the power of Redux Dev Tools Extension. It automatically logs every action your app performs, and it allows time traveling – you can click on any past action and jump to that point in time. Redux also supports the concept of middleware, where you may bind customized function calls on every action dispatch. Such examples include an automatic event logger, interception of certain actions, etc.

With React's Context API, you deal with a pair of components speaking only to each other. This gives you nice isolation between irrelevant data. You also have the flexibility of how you may use the data with your components, i.e., you can provide the state of a parent component, and you may pass context data as props to wrapped components.

There is a key difference in how Redux and React's Context treat data. Redux maintains the data of your whole app in a giant, stateful object. It deduces the changes of your data by running the reducer function you provide, and returns the next state that corresponds to every action dispatched. React Redux then optimizes component rendering and makes sure that each component re-renders only when the data it needs change. Context, on the other hand, does not hold any state. It is only a conduit for the data. To express changes in data you need to rely on the state of a parent component.

***Dynamic Import***

When importing statically significantly slows the loading of your code and there is a low likelihood that you will need the code you are importing, or you will not need it until a later time.

Use dynamic import only when necessary. The static form is preferable for loading initial dependencies, and can benefit more readily from static analysis tools and tree shaking.

***Bundling***

Most React apps will have their files “bundled” using tools like Webpack, Rollup or Browserify. Bundling is the process of following imported files and merging them into a single file: a “bundle”. This bundle can then be included on a webpage to load an entire app at once.

***code splitting***

To avoid winding up with a large bundle, it’s good to get ahead of the problem and start “splitting” your bundle. Code-Splitting is a feature supported by bundlers like Webpack, Rollup and Browserify (via factor-bundle) which can create multiple bundles that can be dynamically loaded at runtime. The best way to introduce code-splitting into your app is through the dynamic import() syntax.

***HOC***

A higher-order component (HOC) is an advanced technique in React for reusing component logic. HOCs are not part of the React API, per se. They are a pattern that emerges from React’s compositional nature.Concretely, a higher-order component is a function that takes a component and returns a new component.

***React.lazy***

The React.lazy function lets you render a dynamic import as a regular component.

```
import React, { Suspense } from 'react';
import MyErrorBoundary from './MyErrorBoundary';

const OtherComponent = React.lazy(() => import('./OtherComponent'));
const AnotherComponent = React.lazy(() => import('./AnotherComponent'));

const MyComponent = () => (
  <div>
    <MyErrorBoundary>
      <Suspense fallback={<div>Loading...</div>}>
        <section>
          <OtherComponent />
          <AnotherComponent />
        </section>
      </Suspense>
    </MyErrorBoundary>
  </div>
);
```

***Pure Components***

shouldComponentUpdate() is invoked before rendering when new props or state are being received. Defaults to true. This method is not called for the initial render or when forceUpdate() is used.Use shouldComponentUpdate() to let React know if a component’s output is not affected by the current change in state or props.The default behavior is to re-render on every state change, and in the vast majority of cases you should rely on the default behavior.

ReactJS has provided us a Pure Component. If we extend a class with Pure Component, there is no need for shouldComponentUpdate() Lifecycle Method. ReactJS Pure Component Class compares current state and props with new props and states to decide whether the React component should re-render itself or  Not.

In v16.6, React has a new utility called React.memo, a higher order function that takes a functional component as parameter and returns an optimized version of your component that updates only on props change.

```
import React, { memo } from 'react';

function areEqual(prevProps, nextProps) {
  return prevProps.contacts === nextProps.contacts;
  // the component will be updated only on `contact` props changes.
}

export default memo(
  function ContactList({ title, contacts }) {
    return <List title={title} data={contacts} />;
  },
  areEqual
);
```

React v16.8: It’s a hook called useMemo , that takes as first parameters a value (can be a component) and as second parameter an array of dependencies.

```
import React, { useMemo } from 'react';

function ContactList({ title, contacts }) {
  const listComponent = useMemo(() => {
    return <List title={title} data={contacts} />;
  }, [contacts]);
  //  ^^^^^^^^ `props.contacts` dependency
  
  return listComponent;
}
```


This will automatically load the bundle containing the OtherComponent when this component is first rendered.

***Call Endpoint Once to Fetch Initial Data***

UseEffect with empty Array is called only after first render.

***Function with big calculations***

UseMemo - Runs the function only if arguments change other it will return the stored value.

***Difference with useMemo vs useCallback***

useMemo - stores value.\
useCallback - stores function

***Dispatch & Action in useReducer ?***

dispatch is called with action which calls the reducer to return the state.

***devtools display state***

usedebugvalue

***allow transition in state***

useTransition

**Refresh Table specific row***

Create seperate component for rows. Re-render will only happen for rows with value change.
use redux cache to cache api response, fetch updated value from endpoint and update the complete cache. pass that to rows props.


## NodeJS Topics

***Concurrency***

As soon as Node js starts, it initializes an event loop. The event loop works on a queue (which is called an event queue) and performs tasks in FIFO(First In First Out) order. It executes a task only when there is no ongoing task in the call stack. The call stack works in LIFO(Last In First Out) order. The event loop continuously checks the call stack to check if there is any task that needs to be run. Now whenever the event loop finds any function, it adds it to the stack and runs in order.

https://www.geeksforgeeks.org/if-node-js-is-single-threaded-then-how-to-handles-concurrency/#:~:text=Node%20js%20uses%20an%20event,First%20In%20First%20Out)%20order.

***Process environment***

Config values are set in parameter store in AWS, those values set to process environment during jenkins build, and those are accessed in code.

***Connect to MySql***

```
const mysql = require('mysql');

const connection = mysql.createconnection((
  host: localhost,
  database: '',
  user: '',
  password: '',
));

connection.connect();
connection.query('select * from test', (err, rows, column) => {
console.log();
});

connection.end();
```

**Connect to MongoDB**

```
const MongoClient = require('mongodb').MongoClient;

MongoCLient.connect('mongodb://localhost:27017/animals', (err, client) => {
    const db = client.db('animals');
    db.collections('mammal').find().toArray((err, result) => {
       if (err) throw err

    console.log(result)
    });
})
```

### ExpressJS

***Static files***

app.use(express.static('public'))

***Request params***

The req.params property is an object containing properties mapped to the named route “parameters”. For example, if you have the route /student/:id, then the “id” property is available as req.params.id. This object defaults to {}.

***Next function***

Calling this function invokes the next middleware function in the app, The next() function is not a part of the Node.js or Express API, but is the third argument that is passed to the middleware function.

If you pass an error to next() and you do not handle it in a custom error handler, it will be handled by the built-in error handler. The error will be written to the client with the stack trace. The stack trace is not included in the production environment.

res.statusCode & res.statusMessage.

So when you add a custom error handler, you must delegate to the default Express error handler, when the headers have already been sent to the client.

***Middleware function***

Express is a routing and middleware web framework that has minimal functionality of its own: An Express application is essentially a series of middleware function calls.

Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

Middleware functions can perform the following tasks:

Execute any code.\
Make changes to the request and the response objects.\
End the request-response cycle.\
Call the next middleware function in the stack.

***Error handling functions***

Define error-handling middleware functions in the same way as other middleware functions, except error-handling functions have four arguments instead of three: (err, req, res, next).


## NextJS Topics

***Nextjs Advantages***

Comes with webpack.\
Dynamic import, lazyload using suspense.\
Compiler replaces babel for individual files and terser for minifying output bundles.\
prerendering.\
Automatic static optimization.
Adding Links which code splits, client side navigation and prefetches.

***What is pre-rendering***

This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. Pre-rendering can result in better performance and SEO.

***What is hydration***

Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive.

***getServerSideProps vs getStaticProps***

Next.js will pre-render this page on each request using the data returned by getServerSideProps.\
Next.js will pre-render this page at build time using the props returned by getStaticProps.

***ISR***

Incremental Static Generation uses revalidate.
Next.js allows you to create or update static pages after you’ve built your site. Incremental Static Regeneration (ISR) enables you to use static-generation on a per-page basis, without needing to rebuild the entire site. With ISR, you can retain the benefits of static while scaling to millions of pages.
When a request is made to a path that hasn’t been generated, Next.js will server-render the page on the first request.
Future requests will serve the static file from the cache. ISR on Vercel persists the cache globally and handles rollbacks.

***SWR***

react library - stale while revalidate.

***Dynamic routing***

In Next.js you can add brackets to a page ([param]) to create a dynamic route (a.k.a. url slugs, pretty urls, and others).The matching paths will be available in the query string.

***Client Side Navigation***

Client-side navigation means that the page transition happens using JavaScript, which is faster than the default navigation done by the browser.

Link

Using <a href=""></a> instead of <Link href="" />, The background color will be cleared on link clicks because the browser does a full refresh.Next.js does code splitting automatically, so each page only loads what’s necessary for that page. That means when the homepage is rendered, the code for other pages is not served initially.

In a production build of Next.js, whenever Link components appear in the browser’s viewport, Next.js automatically prefetches the code for the linked page in the background. By the time you click the link, the code for the destination page will already be loaded in the background, and the page transition will be near-instant!

Next.js automatically optimizes your application for the best performance by code splitting, client-side navigation, and prefetching (in production).

## REST Apis Topics

***Stateless***

Client provides all information required for the server in the form of url, query string, header or through a body.

***CRUD***

Create, Read, Update, Delete

POST,  GET,   PUT,    DELETE.

## Containerization Topics

***Virtualization vs Containerization***

Virtualization is an abstract version of a physical machine, while containerization is the abstract version of an application.


Containers are deployed applications bundled with all necessary dependencies and configuration file.


Virtualization is the means of employing software (such as Hypervisor) to create a virtual version of a resource such as a server, data storage, or application

***ECS***

AWS ECS is just a logical grouping (cluster) of EC2 instances, and all the EC2 instances part of an ECS act as Docker host i.e. ECS can send command to launch a container on them (EC2). If you have launched an Amazon ECS with no EC2 instances added to it, it's good for nothing i.e. you can't do anything about it. ECS makes sense only once one (or more) EC2 instances are added to it.Docker is a utility you can install on our machine, which makes it a Docker host, and on this host you can create containers (same as virtual machines - but much more light-weight).

To sum up, ECS is just about clustering of EC2 instances, and uses Docker to instantiate containers/instances/virtual machines on these (EC2) hosts. 

***Docker Image***

A Docker image is an immutable (unchangeable) file that contains the source code, libraries, dependencies, tools, and other files needed for an application to run.

Due to their read-only quality, these images are sometimes referred to as snapshots. They represent an application and its virtual environment at a specific point in time. This consistency is one of the great features of Docker. It allows developers to test and experiment software in stable, uniform conditions.

Since images are, in a way, just templates, you cannot start or run them. What you can do is use that template as a base to build a container. A container is, ultimately, just a running image. Once you create a container, it adds a writable layer on top of the immutable image, meaning you can now modify it.

The image-base on which you create a container exists separately and cannot be altered. When you run a containerized environment, you essentially create a read-write copy of that filesystem (docker image) inside the container. This adds a container layer which allows modifications of the entire copy of the image.

***docker file***

***Components of docker***

Client - Performs Docker build pull and run operations to open up communication with the Docker Host.
Host - Contains Docker daemon, containers, and associated images.
Registry- This is where Docker images are stored. There are two of them, a public registry and a private one. Docker Hub and Docker Cloud are two public registries available for use by anyone.

***Commands***

docker pull image
docker run image
docker system prune

***docker vs kubernettes vs jenkins***

Docker is a container engine that can make and handle containers, whereas Jenkins is a CI/CD model that can run/build/test the application. Kubernetes is a container-orchestration system for automating computer applications with the external help of CI/CD.

## AWS Topics

Amazon Web Services, Inc. is a subsidiary of Amazon that provides on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered pay-as-you-go basis. These cloud computing web services provide distributed computing processing capacity and software tools via AWS server farms.

***Parameter store***

Parameter Store, a capability of AWS Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon Machine Image (AMI) IDs, and license codes as parameter values.

***S3 Bucket***

Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can store and protect any amount of data for virtually any use case, such as data lakes, cloud-native applications, and mobile apps.

***Large Files in AWS***

When you upload large files to Amazon S3, it's a best practice to leverage multipart uploads. If you're using the AWS Command Line Interface (AWS CLI), then all high-level aws s3 commands automatically perform a multipart upload when the object is large. These high-level commands include aws s3 cp and aws s3 sync.

Multipart upload is a three-step process: You initiate the upload, you upload the object parts, and after you have uploaded all the parts, you complete the multipart upload. Upon receiving the complete multipart upload request, Amazon S3 constructs the object from the uploaded parts, and you can then access the object just as you would any other object in your bucket.

You can list all of your in-progress multipart uploads or get a list of the parts that you have uploaded for a specific multipart upload. Each of these operations is explained in this section.

***Amazon VPC***

Amazon VPC gives you full control over your virtual networking environment, including resource placement, connectivity, and security.
Get started by setting up your VPC in the AWS service console. Next, add resources to it such as Amazon Elastic Compute Cloud (EC2) and Amazon Relational Database Service (RDS) instances. Finally, define how your VPCs communicate with each other across accounts, Availability Zones, or AWS Regions. In the example below, network traffic is being shared between two VPCs within each Region.

***Serverless***

Serverless is a cloud-native development model that allows developers to build and run applications without having to manage servers. There are still servers in serverless, but they are abstracted away from app development.

***Dynamo DB***

Amazon DynamoDB is a fully managed, serverless, key-value NoSQL database designed to run high-performance applications at any scale. DynamoDB offers built-in security, continuous backups, automated multi-Region replication, in-memory caching, and data export tools.

***Amazon API Gateway***

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

***Amazon EC2***

An Amazon EC2 instance is a virtual server in Amazon's Elastic Compute Cloud (EC2) for running applications on the Amazon Web Services (AWS) infrastructure.

## Jenkins Topics

Jenkins is typically run as a standalone application in its own process with the built-in Java servlet container/application server (Jetty).

## Testing Topics

***Test runners***

They collect all the files and runs each test case and show pass and fail results in your console.
Examples: Mocha, Jest.

***Mocha***

```
describe('Array', function () {
  describe('#indexOf()', function () {
    it('should return -1 when the value is not present', function () {
      assert.equal([1, 2, 3].indexOf(4), -1);
    });
  });
});
```

Different Assertion libraries can be used with mocha.

***should***

```
user.should.have.property('name', 'tj');
user.should.have.property('pets').with.lengthOf(4);
```

***Expect***

```
expect(window.r).to.be(undefined);
expect({ a: 'b' }).to.eql({ a: 'b' })
expect(5).to.be.a('number');
expect([]).to.be.an('array');
expect(window).not.to.be.an(Image);
```

***chai***

Chai is a BDD / TDD assertion library for node and the browser that can be delightfully paired with any javascript testing framework.

```
Should
chai.should();

foo.should.be.a('string');
foo.should.equal('bar');
foo.should.have.lengthOf(3);
tea.should.have.property('flavors')
  .with.lengthOf(3);


Expect
var expect = chai.expect;

expect(foo).to.be.a('string');
expect(foo).to.equal('bar');
expect(foo).to.have.lengthOf(3);
expect(tea).to.have.property('flavors')
  .with.lengthOf(3);


Assert
var assert = chai.assert;

assert.typeOf(foo, 'string');
assert.equal(foo, 'bar');
assert.lengthOf(foo, 3)
assert.property(tea, 'flavors');
assert.lengthOf(tea.flavors, 3);
                
```

***Mocha vs Jest***

Mocha requires other libraries to work such as sinon for stubbing.
Jest does not require any pre configuration.

***Jest***

```
test('null', () => {
  const n = null;
  expect(n).toBeNull();
  expect(n).toBeDefined();
  expect(n).not.toBeUndefined();
  expect(n).not.toBeTruthy();
  expect(n).toBeFalsy();
});

test('zero', () => {
  const z = 0;
  expect(z).not.toBeNull();
  expect(z).toBeDefined();
  expect(z).not.toBeUndefined();
  expect(z).not.toBeTruthy();
  expect(z).toBeFalsy();
});

test('two plus two', () => {
  const value = 2 + 2;
  expect(value).toBeGreaterThan(3);
  expect(value).toBeGreaterThanOrEqual(3.5);
  expect(value).toBeLessThan(5);
  expect(value).toBeLessThanOrEqual(4.5);

  // toBe and toEqual are equivalent for numbers
  expect(value).toBe(4);
  expect(value).toEqual(4);
});
```

***React Testing Library***

```
import React from 'react'
import {rest} from 'msw'
import {setupServer} from 'msw/node'
import {render, fireEvent, waitFor, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Fetch from '../fetch'

const server = setupServer(
  rest.get('/greeting', (req, res, ctx) => {
    return res(ctx.json({greeting: 'hello there'}))
  }),
)

beforeAll(() => server.listen())
afterEach(() => server.resetHandlers())
afterAll(() => server.close())

test('loads and displays greeting', async () => {
  render(<Fetch url="/greeting" />)

  fireEvent.click(screen.getByText('Load Greeting'))

  await waitFor(() => screen.getByRole('heading'))

  expect(screen.getByRole('heading')).toHaveTextContent('hello there')
  expect(screen.getByRole('button')).toBeDisabled()
})

test('handles server error', async () => {
  server.use(
    rest.get('/greeting', (req, res, ctx) => {
      return res(ctx.status(500))
    }),
  )

  render(<Fetch url="/greeting" />)

  fireEvent.click(screen.getByText('Load Greeting'))

  await waitFor(() => screen.getByRole('alert'))

  expect(screen.getByRole('alert')).toHaveTextContent('Oops, failed to fetch!')
  expect(screen.getByRole('button')).not.toBeDisabled()
})
```

## 12 Factor Topics

Codebase (Github, Jenkins deployment)\
Dependencies (package.json, dockerfile)\
Config (parameter store in AWS)\
Backing Services (Endpoints, My Sql Database)\
Build, release, and Run (Jenksins Build, run tests, Release using jenkins)\
Processes (execute the app as one or more stateless processes)\
Port Binding (change ports in package.json)\
Concurrency (Scale out via the process model)\
Disposability (maximize the robustness with fast startup and graceful shutdown)\
Dev/prod parity (Running scripts to make prod same as stage)\
Logs (Kibana logs)\
Admin processes (Run admin/management tasks as one-off processes)\