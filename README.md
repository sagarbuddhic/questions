# Questions

### [GIT](#git-topics)
### [Data Structures](#dsa)
### [-Design Principle](#design-principles)
### [Javascript](#javascript-topics)
### [-ReactJS](#reactjs-topics)
### [-NextJS](#nextjs-topics)
### [-Rest Apis](#rest-apis-topics)
### [-NodeJS](#nodejs-topics)
### [-ExpressJS](#expressjs-topics)
### [-Cloud](#cloud)
### [-AWS](#aws)
### [-Jenkins](#jenkins-topics)
### [CSS](#css-topics)
### [-Testing](#testing-topics)
### [-MySql](#mysql-topics)
### [Heroku](#heroku-topics)
### [-12 Factor](#12-factor-topics)
### [Python](#python)

## GIT Topics

**package manager**

**yarn vs npm**

**git init**

**.git subdirectory**

**remote repos**

**git push**

**semantic versioning**

**yarn workspaces**

**github actions vs jenkins**

## DSA

collection of values and the format they are stored in, steps taken to solve a problem.

**linked list vs arrays**

ADT        DS

List    Dynamic Array, Linked List
Queue   Linked List Based, Array Based, Stack Based
Map     TreeMap, HashMap, HashTable

DIfferent Big O:

Upper Bound of the complexity in the worst case, 

O(1)
O(n)
O(log n)
Example: Binary Search

O(n logn) - merge sorting, heap sorting. quasilinear runtime.
O(n<sup>2</sup>)
O(n!) - n * (n-1) * (n -2) ....

Algorithms(set of tasks):

linear search - sequential or simple search.
binary search - cutting to half.
brute force - same as linear , exponential runtimes.
divide and conquer - merge sort.
selection sort - O (n2)
quick sort - O (n log n)

Data Structures:

Linked List
double linked list
Stack - LIFO.
Queue - Linear Data Structure models real world queues, enqueue and dequeue(FIFO).
Priority Queue
Indexed Priority Queue
Heap
Union Find
Tree
Leaf Node
Binary Tree
BFS
Hash Table
Object Data
Fenwick tree
Suffix Array
LCP
BBST
Balanced Binary Tree

Efficiency:

Time Complexity
Space Complexity

## Design Principles

**SOLID**

* S - This principle states that every method/class should handle a single responsibility.
* O - open to extension, closed for modification(inheritance).
* L - Liskov - A child class should be able to do what parent does. Example - Human - child - parent.
* I - Interface segregation principle - avoid generalized interface for a class,segregated interfaces with smaller functionalities.
* D - Dependency inversion principle - Every dependency in the design should be directed toward an abstract class or interface.
      No dependency should target a concrete class.

**Observer Pattern**

**Decorator Pattern**

**Singleton Pattern**

**Factory Pattern**

**Builder**

**Prototype**

**Adapter pattern**

**Iterator Pattern**

**Microfrontend**

Webpack module federation

Routing in Microfrontend

communicating in Microfrontend

## Javascript Topics

**single threaded & asynchronous**

**javascript Interpreted or compiled**

**Window**

**window vs document**

getSelection.  
getRangeAt  
getClientRects, getBoundingClientRects.  

**CDN**

typescript compiled to JS.

**typescript vs javascript**

**abstract syntax tree**

**garbage collection**

**mark and sweep**

**web workers**

**debounce vs throttle**

**primitive vs non primitive**

**shallow copy vs deep copy**

**structured clone**

**hoisting**

**memory leaks**

**var VS let & const keyword?**

**prototype**

chaining

**declarative vs imperative**

**type coercion**

**set vs array**

**pure functions**

**undefined vs not defined**

**undefined vs null**

**typeof(x) === "undefined"**

**function vs arrow**

**apply,call,bind**

**foreach vs for**

**forEach vs map**

**string terms**

* Palindrome - reverse words should read the same.(racecar)
* Anagram - An anagram of a string is another string that contains the same characters, only the order of characters can be different(secure) - (rescue).
* Vowels - a,e,i,o,u.

**IIFE(Immediately Invoked Function Expression)**

**Closures:**

A closure is a function having access to the parent scope, even after the parent function has closed.

**Currying:**

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

**Recursive**

**AAA**

**History**

```
history.back();     // equivalent to clicking back button
history.go(-1);     // equivalent to history.back();
```

**Location**

window.location.replace('https://developer.mozilla.org/en-US/docs/Web/API/Location.reload'); // does not save previous url in history.  
window.location.href  
window.location.assign  

// point a cursor  
const inputRange = document.createRange();
inputRange.selectNodeContents(editDiv.current); 
inputRange.collapse(false);  
selection.removeAllRanges();  
selection.addRange(inputRange);

**spread vs rest**

**Destructuring**

**Logical AND (&&)**

```
12 && 13 && 14 // 14
12 && 0 && false && 15 // 0
```

**Logical OR (||)**

```
12 || 13 || 15 // 12
undefined || false // false
```

**Nullish coalescing operator (??)**

```
'' ?? 'test' // ''
null ?? 'test' // 'test'
```

**object freeze vs seal vs const**

**white label**

**Tricky Logic**

**Web Socket vs HTTP**

**Higher order function**

Examples: Map, Filter Function.

**decorator**

**In Operator**

**Callback**

Callback Hell - Hard to read & maintain callbacks.

**Promises**

**functions vs methods**

**this keyword**

**strict mode**

**Event Emitter**

**Event Bubbling**

**Event Propagation**

**Parse Int**

```
parseInt('32', 10) // 32
```

**Intersection Observer**

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

**Math.Ceil**

The Math.ceil() function always rounds a number up to the next largest integer.

**Math.round()**

The Math.round() function returns the value of a number rounded to the nearest integer.

console.log(Math.round(5.95), Math.round(5.5), Math.round(5.05));
// expected output: 6 6 5

**Common javascript functions**

**Map**

 **Filter**

**Reducer**

**Some**

**Every**

**Includes**

**Slice**

```
slice(start, end)

start - start index.
end - index of the value to be excluded.
```

**Splice**

```
Remove 0 (zero) elements before index 2, and insert "drum"

let myFish = ['angel', 'clown', 'mandarin', 'sturgeon']
let removed = myFish.splice(2, 0, 'drum')
```

**Shift & Unshift**

**Fill**

```
const heights2 = [1, 2, 4, 5, 6, 7, 1, 1];
heights2.fill(0, 4);
console.log(heights2); // [1, 2, 4, 5, 0, 0, 0, 0]
```

**Reverse**

```
const reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]
```

**Sort**

```
const numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
  return a - b;
});
console.log(numbers);

```

**Object.entries**

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

**Find**

```
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// expected output: 12
```

**Flat**

```
const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// expected output: [0, 1, 2, 3, 4]
```

**JSON Parse**

deep copy
JSON.Parse && JSON.stringify

**defer attribute**

**Concatenation**

```
let test = 'test' + 'best' // testbest
```

**Template literals (Template strings)**

**delete operator**

**eval**

**window objects**

* local storage
* session storage
* history
* innerHeight
* innerWidth
* sessionStorage.
* navigator.geoLocation
* pageXOffset
* screen
* document.cookie

**singleton**

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

## ReactJS Topics

**jsx vs js**

**jsx vs tsx**

**React Classes**

Super()

passing props to super.

**React Lifecycle:**

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

**useEffect Lifecycles:**

componentDidMount, componentDidUpdate, componentWillUnmount

**Bundling**:
minification to build folder, Tree Shaking, Code Splitting

**transpiler**

**React Without Bundler/Transpiler**

**Compilers**

**Virtual DOM**

**Reconciliation**

**React Diff Algorithm**

**React Fiber**

**Keys**

**Repaint vs Reflow**

**React Error Boundaries**

getDerivedStateFromError

**Composition Vs Inheritance**

**HOC**

**Render Props vs custom hooks**

Example Downshift.
MouseTracker

**props.children**

**React Portals**

**Lifting State Up**

**Redux**

@reduxjs/toolkit

**React Thunk**

**Pure Components vs React.Memo**

**State vs props**

**Controlled vs. Uncontrolled Components**

**Refs**

**Strict Mode**

**Typechecking With PropTypes**

**React Profiler**

**Container presentational layout**

**React Fragments**

**React JS Multiple SetStates**

React 18:

Batch Updates are available for all events.

**How does Redux compare to the React Context API ?**

**create react app**

What are each of these files and folders for?

*  README.md.
* node_modules - semantic-  ^, *, ~.
* package.json.
* .gitignore
* public 
* src

**change app's metadata**

**build folder**

contains static/js, static/css, assetmanifest.json

src - contains js, style.js.

**dependencies vs devdependencies vs peerdependencies**

**Source Map Explorer**

**depcheck**

**React Scripts**

// client side
import ReactDOM from 'react-dom/client';

import ReactDOM from 'react-dom/server';

**React Router**

Nested routes - outlets

Link vs NavLink

compression is a process in which the size of a file is reduced by re-encoding the file data to use fewer bits of storage than the original file.

**React Optimizations**

Avoid prop drilling

**Call Endpoint Once to Fetch Initial Data**

UseEffect with empty Array is called only after first render.

**Function with big calculations**

UseMemo - Runs the function only if arguments change other it will return the stored value.

**Difference with useMemo vs useCallback**

useMemo
useCallback
usedebugvalue
useTransition

code splitting, lazy.
using keys for list.
 
PureComponents, React.memo for re-render only when a prop changes(Table rows).

**Refresh Table specific row**

Create seperate component for rows. Use PureComponents or React.Memo to render only when props changes. Re-render will only happen for rows with value change.

**Microfrontend**

exposes, remote, webpackmodulefederation plugin, webpack config file.
each MFE handles their own routes and parent routes in defined in host
each app with its own docker containers, ECS handles containers.
nginx routing can be configured to each container.

## Microservices

https://nodesource.com/blog/microservices-in-nodejs

## OAuth

Client ID, Client Secret, Access Token

Authorization: Bearer Tokenm

## NextJS Topics

**Nextjs Advantages**

**next js folder structure**

**Webpack Integrated, Compiler replaces babel for individual files and terser for minifying output bundles.**

**Pre-rendering**

Server side rendering - getServerSideProps - Next.js will pre-render this page on each request.
Static Generation - getStaticProps - Next.js will pre-render this page at build time(Automatic static optimization.)
Incremental Static Generation -  static pages, but content updates automatically without rebuilding the whole app.

**With Links, prefetches and does client side navigation.**

**Dynamic routing**

**Dynamic import, lazyload using suspense.**

**What is hydration**

**SWR**


## REST Apis Topics

***Stateless***

Client provides all information required for the server in the form of url, query string, header or through a body.

***CRUD***

Create - Post
Read - GET
Update - PUT, PATCH 
Delete - delete

## NodeJS Topics

**single threaded event loop architecture**

**libuv thread pool**

**middlewares**

**Handling a Large Volume of Customers in Node.js**

Optimize Database Queries & Caching(redis) <br/>
Use Asynchronous & Non-Blocking Code <br/>
connection loop to reuse db connections <br/>
compressions for response <br/>
Load Balancing & Scaling with Clustering <br/>
Rate Limiting & API Throttling <br/>
monitor and log <br/>

**child processes**

**concurrent**

**worker thread**

**v8 engine**

**debugging issue which is only in production not in dev docker**

cors, bodyparser, compression, cookie parser, rate limiting

**async and await vs .then**

**create query executed and disk storage in database becomes full solution for this**

**Process environment**

Config values are set in parameter store in AWS, those values set to process environment during jenkins build, and those are accessed in code.

**Connect to MySql**

**Connect to MongoDB**

**content negotiation**

**third party libraries**

**axios vs fetch**

## ExpressJS Topics

***Request Object***

params, query, body

***app.use()***

***Next function***

***Middleware function***

***Error handling functions***

## Cloud

**Containerization**

**Virtualization vs Containerization**

**image**

**containers**

**docker**

**components of docker**

**docker file**

**NGINX**

**docker engine**

**docker hub**

**docker client**

**docker host**

**Commands**

* docker build image
* docker pull image
* docker run image
* docker system prune

**docker vs kubernettes vs jenkins**

## AWS

**ECS(Elastic Container Service)**

**Docker Compose**

**EC2(Elastic Compute Cloud)**

**Cluster**

**ECR**

**Serverless**

**Lambda**

**SQS**

**Amazon API Gateway**

**Dynamo DB**

**S3 Bucket**

**step functions**

**Cloud Front with Custom routing**

**VPC**

**JWT**

**app sync**

**Cloud Watch**

**Parameter store**

**Robots.txt, , route 53**

**Large Files in AWS**

**DockerFile & JenkinsFile**

## Jenkins Topics

Jenkins is typically run as a standalone application in its own process with the built-in Java servlet container/application server (Jetty).

## CSS Topics

**Box Model**

**border box**

**Visibility vs Display vs Opacity**

**display**

**align items**

**align-self**

**justify-contents**

**grid vs flex**

**text-align**

**vertical align**

**Descendant Selector (space)**

**Child Selector (>)**

**Adjacent Sibling Selector (+)**

**General Sibling Selector (~)**

***pseudo***

A pseudo-class is used to define a special state of an element.

Example: Style an element when a user mouses over it.

```
a:hover {
  color: #FF00FF;
}
```

**Pseudo-element**

```
h1::after {
  content: url(smiley.gif);
}
```

**css transform**

CSS transforms allow you to move, rotate, scale, and skew elements.

**position**

The five different position values are fixed, static, absolute, sticky, and relative.

* Static
* Relative
* Absolute
* Fixed
* Sticky

**mixin**

Mixins allow document authors to define patterns of property value pairs, which can then be reused in other rulesets.

```
@mixin theme($theme: DarkGray) {
  background: $theme;
  box-shadow: 0 0 1px rgba($theme, .25);
  color: #fff;
}

.info {
  @include theme;
}
.alert {
  @include theme($theme: DarkRed);
}
.success {
  @include theme($theme: DarkGreen);
}

https://sass-lang.com/guide
```

**float**

**Table**

```
divWrapper {
  overflow: scroll;
}

table {
  layout: fixed
  width: 100%
}

colgroup {

}

tbody {
  
}
```

**margin vs padding**

**ruleset***

**css vs scss**

**scss vs emotions**

**css integration**

**sprites***

**css image repetition***

 The background-repeat property is used to control the image.

 ```
 background-image: url(‘url_of_image’);

  background-repeat: no-repeat;

  background-attachment: fixed;
 ```

**RGB**

**CSS [attribute] Selector**

## HTML

***Semantic vs non***

semantic elements: <form>, <table>, <article>
non semantic elements:  <div>, <span>

**important meta tags**

<!DOCTYPE>
<head>
<link> - best place to use it  in head tags
<script> - best place for script tags

## Testing Topics

**Test runners**

Examples: Mocha, Jest.

**Mocha**

```
describe('Array', function () {
  describe('#indexOf()', function () {
    it('should return -1 when the value is not present', function () {
      assert.equal([1, 2, 3].indexOf(4), -1);
    });
  });
});
```

**Assertion libraries with mocha**

**should**

```
user.should.have.property('name', 'tj');
user.should.have.property('pets').with.lengthOf(4);
```

**Expect**

```
expect(window.r).to.be(undefined);
expect({ a: 'b' }).to.eql({ a: 'b' })
expect(5).to.be.a('number');
expect([]).to.be.an('array');
expect(window).not.to.be.an(Image);
```

**chai**

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

**Mocha vs Jest**

Mocha requires other libraries to work such as sinon for stubbing.
Jest does not require any pre configuration.

**Jest**

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

**React Testing Library**

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

## Analytics

**Google Analytics**

**Group Stats**

**Mixpanel**

**HotJar**

## Database:

DBMS vs RDBMS

Primary Key vs Foreign Key

ACID

Constraints

DDL & DML

DROP vs TRUNCATE

Difference Between Delete, Drop, and Truncate

Group By vs Order by

Where vs Having

Aggregate Functions in SQL

Indexing and Clustered Indexing in SQL

UNION vs UNION ALL in SQL

Views

triggers

stored procedures

SQL Query to Find the Second Highest Value in a Table

text to dates

## No SQL:

difference with no sql and sql

tyoes of no sql DBS 

Popular NoSQL Databases & Their Use Cases

CAP Theorem

advantages and disadvantages of no sql.

Types of Indexing in NoSQL Databases

## MongoDB Topics:

**Cluster**

**Replica Set**

***Shards***

***Database Access***

Use "Database Access" Tab in mongo to edit the password.

***Network Access***

In Network Access Tab, adding 0.0.0.0/0 allows access to any ips.

## MySql topics

* sudo systemctl start mysql.service
* show databases;
* create database sagar;
* use sagar;
* create table user (id int, name varchar(50), email varchar(50), gender varchar(10), status varchar(10));
* show tables;
* select user();
* INSERT INTO user (id, name, email, gender, status) VALUES (1, 'sagar', 's', 'M', 'active');"


## Heroku Topics

* heroku CLI
* heroku
* heroku create
* heroku local web
* git push heroku master
* heroku logs

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

Design patterns are reusable solutions to common problems in software design

## Formatting

EditorConfig - VSCode will format according to the options in this file. If EditorConfig or prettierrc is not available then vscode will use its formatter.

ESLint - Create React App comes with ESLint and it can be extended. shows syntax errors.

Prettier - we can show as warnings and it has better formatting. https://prettier.io/docs/en/comparison.html

## Python

order of precedance
x = 10+3*2**2
print(x)
parenthesis
exponentiation
multiplication or division
addition or subtraction

elif - used for else if

for value in ['test']

none similar to null object
