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

**treemap vs hashmap vs hashtable**

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

**Observer Pattern**

**Singleton Pattern**

**Prototype**

**Adapter pattern**

**Decorator Pattern**

**Factory Pattern**

**Builder**

**Facade**

**Iterator Pattern**

**Microfrontend**

Webpack module federation

Routing in Microfrontend

communicating in Microfrontend

## Javascript Topics

**single threaded & asynchronous**

**web workers**

**javascript Interpreted or compiled**

**abstract syntax tree**

**window vs document**

* local storage
* session storage
* cookie
* history
* navigator
* location
* screen

window.location.replace('https://developer.mozilla.org/en-US/docs/Web/API/Location.reload'); // does not save previous url in history.  
window.location.href  
window.location.assign 

**declarative vs imperative**

**typescript vs javascript**

**ES5 vs ES6**

**strict mode**

**garbage collection**

**mark and sweep**

**memory leaks**

**primitive vs non primitive**

**decorators**

**debounce vs throttle**

**this keyword**

**pure functions**

**function vs arrow**

**functions vs methods**

**apply,call,bind**

**hoisting**

**var vs let vs const keyword?**

**shallow copy vs deep copy**

**type coercion**

**undefined vs not defined vs null**

**typeof(x) === "undefined"**

**prototype**

chaining

**set vs array**

**map vs object**

**Higher order function**

Examples: Map, Filter Function.

**forEach vs map vs for vs for ..in vs for .. of**

**in operator**

**string terms**

* Palindrome - reverse words should read the same.(racecar)
* Anagram - An anagram of a string is another string that contains the same characters, only the order of characters can be different(secure) - (rescue).
* Vowels - a,e,i,o,u.

**CDN**

**IIFE(Immediately Invoked Function Expression)**

**Closures:**

**Currying:**

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

// point a cursor  
const inputRange = document.createRange();
inputRange.selectNodeContents(editDiv.current); 
inputRange.collapse(false);  
selection.removeAllRanges();  
selection.addRange(inputRange);

**spread vs rest**

**Destructuring**

**object freeze vs seal vs const**

**white label**

**Web Socket vs HTTP**

**Callback**

Callback Hell - Hard to read & maintain callbacks.

**Promises**

**async**

**Event Bubbling**

**Event Propagation**

**Intersection Observer**

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

**Parse Int**

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
structured clone

**Concatenation**

```
let test = 'test' + 'best' // testbest
```

**Template literals (Template strings)**

**delete operator**

**eval**

## ReactJS Topics

**ReactJS Patterns**

**jsx vs js vs tsx**

**React Classes**

Super() passing props to super

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

Bundling, transpiling, minification, tree shaking, code splitting

**React Without Bundler/Transpiler**

**Virtual DOM vs React Diff Algorithm vs Reconciliation vs React Fiber**

**Keys**

**Repaint vs Reflow**

**State vs props**

**Pure Components vs React.Memo**

**Refs**

**React Error Boundaries**

getDerivedStateFromError

**Composition Vs Inheritance**

props.children

**Controlled vs. Uncontrolled Components**

**HOCS vs Render Props vs custom hooks**

Example Downshift.
MouseTracker

**Container presentational layout**

**React Portals**

**Lifting State Up**

**Context api**

**Redux**

**flux**

@reduxjs/toolkit

Redux Persistance
How to stop a store
Jenkins Pipeline

**React Thunk**

**Strict Mode**

**Typechecking With PropTypes**

**React Profiler**

**React Fragments**

**React JS Multiple SetStates**

React 18:

Batch Updates are available for all events.

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

MonoRepo

**React Optimizations**

compressions

Avoid prop drilling

code splitting, lazy.

using keys for list.

**Call Endpoint Once to Fetch Initial Data**

UseEffect with empty Array is called only after first render.

**Function with big calculations**

UseMemo - Runs the function only if arguments change other it will return the stored value.

**Difference with useMemo vs useCallback**

useMemo
useCallback
usedebugvalue
useTransition
useReducer
Profiler
 
PureComponents, React.memo for re-render only when a prop changes(Table rows).

**spas**

**NFRs**

**Refresh Table specific row**

Create seperate component for rows. Use PureComponents or React.Memo to render only when props changes. Re-render will only happen for rows with value change.

## Microfrontend

exposes, remote, webpackmodulefederation plugin, webpack config file.
each MFE handles their own routes and parent routes in defined in host.
each app with its own docker containers, ECS handles containers.
nginx routing can be configured to each container.

routing in MFE

passing props in MFE

## Microservices

## OAuth

Client ID, Client Secret, Access Token

Authorization: Bearer Token

## NextJS Topics

**Next Js version10 vs 15**

**App vs Page Based Routing**

**React Server Components**

**next js folder structure**

**Fetch with cache and revalidate**

**middlewares in nextjs**

**next.config.js**

**Nextjs Advantages**

**Webpack Integrated, Compiler replaces babel for individual files and terser for minifying output bundles.*

**Pre-rendering**

Server side rendering - getServerSideProps - fetch with no cache - Next.js will pre-render this page on each request.
Static Generation - getStaticProps - fetch with cache - Next.js will pre-render this page at build time(Automatic static optimization.)
Incremental Static Generation - revalidate - useful for dashboards -  static pages, but content updates automatically without rebuilding the whole app.

**With Links, prefetches and does client side navigation.**

**Images**

**Dynamic routing**

**Dynamic import, lazyload using suspense.**

**What is hydration**

**SWR**

## REST Apis Topics

***headers***

***Stateless***

Client provides all information required for the server in the form of url, query string, header or through a body.

***CRUD***

Create - Post
Read - GET
Update - PUT, PATCH 
Delete - delete

## graphql

caching in graphql

**compare graphql vs rest**

## Elastic Search & Search Box

## NodeJS Topics

**node js design patterns**

**single threaded event loop architecture**

**libuv thread pool**

**child processes**

**concurrent**

**worker thread**

**middlewares**

**Handling a Large Volume of Customers in Node.js**

Optimize Database Queries & Caching(redis) <br/>
Use Asynchronous & Non-Blocking Code <br/>
connection loop to reuse db connections <br/>
compressions for response <br/>
Load Balancing & Scaling with Clustering <br/>
Rate Limiting & API Throttling <br/>
monitor and log <br/>

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

**third party services integration**

ElasticSearch,SendGrid, Twilio,Cloudinary

**axios vs fetch**

## ExpressJS Topics

**Request Object**

params, query, body

**app.use()**

**Next function**

**Middleware function**

**Error handling functions**

## Cloud

**Virtualization vs Containerization**

**containers**

**components of docker**

**image**

**docker engine**

**docker hub**

**docker client**

**docker host**

**docker file**

**NGINX**

**Commands**

* docker build image
* docker pull image
* docker run image
* docker system prune

**docker vs kubernettes vs jenkins**

## AWS

**Docker Compose**

**ECS(Elastic Container Service)**

**EC2(Elastic Compute Cloud)**

**Cluster**

**ECR**

**Serverless**

**Lambda**

**SQS**

**Amazon API Gateway**

**Dynamo DB**

**S3 Bucket**

Image storing in S3, lambda, cloudfront.

**step functions**

**Cloud Front with Custom routing**

**VPC**

**Cloud Watch**

**Parameter store**

**JWT**

**NGINX**

**app sync**

**Robots.txt, , route 53**

**Large Files in AWS**

**DockerFile & JenkinsFile**

## Jenkins Topics

Jenkins is typically run as a standalone application in its own process with the built-in Java servlet container/application server (Jetty).

## CSS Topics

**tailwind**

**media queries**

**material UI**

**Box Model**

**border box**

**margin vs padding**

**Visibility vs Display vs Opacity**

**display**

**float**

**align items**

**align-self**

**justify-contents**

**text-align**

**vertical align**

**grid vs flex**

**selectors**

**Descendant Selector (space)**

**Child Selector (>)**

**Adjacent Sibling Selector (+)**

**General Sibling Selector (~)**

***pseudo***

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

**position**

The five different position values are fixed, static, absolute, sticky, and relative.

* Static
* Relative
* Absolute
* Fixed
* Sticky

top and left

**mixin**

**Table**

```
divWrapper {
  overflow: scroll;
}

table {
  layout: fixed
  width: 100%
}

```

**ruleset**

**responsive**

**css integration**

**css vs scss vs emotions**

**sprites**

**css image repetition***

 The background-repeat property is used to control the image.

 ```
 background-image: url(‘url_of_image’);

  background-repeat: no-repeat;

  background-attachment: fixed;
 ```

**RGB vs hex vs HSL**

## HTML

**Semantic vs non**

semantic elements: <form>, <table>, <article>
non semantic elements:  <div>, <span>

**important meta tags**

<!DOCTYPE>
<head>
<link> - best place to use it  in head tags
<script> - best place for script tags

defer vs async
in head vs body

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

ORM:(sequalize, prisma)

Kinesis, kafka, confluent

DBMS vs RDBMS

ACID vs CAP

DDL & DML

Primary Key vs Foreign Key

clustered and non clustered indexing in sql

constraints

DROP vs TRUNCATE vs DELETE

WHERE, ORDER BY, GROUP BY, HAVING

Aggregate Functions in SQL

UNION vs UNION ALL in SQL

Views

triggers

stored procedures

SQL Query to Find the Second Highest Value in a Table

## No SQL:

difference with no sql and sql

types of no sql DBS

Popular NoSQL Databases & Their Use Cases

CAP Theorem

advantages and disadvantages of no sql.

Types of Indexing in NoSQL Databases

## MongoDB Topics:

**Cluster**

**Replica Set**

**Shards**

**Database Access**

Use "Database Access" Tab in mongo to edit the password.

**Network Access**

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

DATADIOS@DD.COM


sagarsagar405


Challenging in Analyzer:

Every Data Source Comparison
What comes from the endpoint and what we decide in the UI.
Colors from ColorHunt, w3schools


COntainer Presentation:
HOCs - push stats
custom hooks - 
compound components - children - Error Boundaries
Controlled vs Uncontrolled - refs
