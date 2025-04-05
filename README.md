# Questions

### [GIT](#git-topics)
### [Data Structures](#dsa)
### [-Design Principle](#design-principles)
### [Javascript](#javascript-topics)
### [-ReactJS](#reactjs-topics)
### [-NodeJS](#nodejs-topics)
### [-ExpressJS](#expressjs-topics)
### [-NextJS](#nextjs-topics)
### [-Rest Apis](#rest-apis-topics)
### [CSS](#css-topics)
### [-Cloud](#cloud)
### [-AWS](#aws)
### [-Jenkins](#jenkins-topics)
### [-Testing](#testing-topics)
### [-MySql](#mysql-topics)
### [Heroku](#heroku-topics)
### [-12 Factor](#12-factor-topics)
### [Python](#python)

## GIT Topics

**Package Manager**

**yarn vs npm**

**GIT INIT**

.git subdirectory - metadata - subdirectories for objects, refs, template files. HEAD file current checked out commit.

**Remote Repos**

**git push**

## DSA

collection of values and the format they are stored in, relation between values and the operations on those values.
steps taken to solve a problem.

Algorithm           ArrayList   LinkedList
seek front            O(1)         O(1)
seek back             O(1)         O(1)
seek to index         O(1)         O(N)
insert at front       O(N)         O(1)
insert at back        O(1)         O(1)
insert after an item  O(N)         O(1)

ADT        DS

List    Dynamic Array, Linked List
Queue   Linked List Based, Array Based, Stack Based
Map     TreeMap, HashMap, HashTable

DIfferent Big O:

Upper Bound of the complexity in the worst case, 
helping to quantify performance as the input size becomes arbitrarily large.

O(1) - not based on input size. constant time.
O(log n) - n/2 until we reach 1. It can also be denoted as 2<sup>n</sup>. cutting half of the items.
Example: Binary Search
O(n) - traverse all items. linear time algorithm.
O(n logn) - merge sorting, heap sorting. quasilinear runtime.
O(n<sup>2</sup>) - two dimensional array or traversing items for n array n times. quadratic runtime.cubic runtime.
O(n!) - n * (n-1) * (n -2) ....

Algorithms(set of tasks):

linear search - sequential or simple search.
binary search - cutting to half.
brute force - same as linear , exponential runtimes.
divide and conquer - merge sort.
selection sort - O (n2)
quick sort - O (n log n)

Data Structures:

Linked List - Nodes contain reference to the next node.
double linked list - contains both previous and next node reference.
Stack - One Ended linear data structure, push and pop(LIFO).
Queue - Linear Data Structure models real world queues, enqueue and dequeue(FIFO).
Priority Queue
Indexed Priority Queue
Heap - A heap is a tree based DS that satisfies the heap variant(ordered).
Union Find - DS keeps track of elements which are split into one or more disjoint sets(find and union).
Tree - Undirected graph with nodes.
       Leaf Node - without children.
Binary Tree - At most two children(greater value to the right side).
BFS -  Breadth First Search.
Hash Table - mapping from keys to values called hashing. they use functions to generate keys.
Object Data - non-scalar objects in javascript behave as associated arrays, 
so an object itself can behave as a basic hash table.
Fenwick tree - sum range queries.
Suffix Array - non empty substring at the end of a string of characters.
LCP - longest common prefix array. 
BBST - Balanaced Binary Search Tree self balancing binary search tree it will adjust itself.
Balanced Binary Tree - height of the tree is O(Log n) where n is the number of nodes.
It is a type of binary tree in which the difference between the height of the left and the right subtree for each node is either 0 or 1.
The difference between the heights of the left subtree and the right subtree for any node is known as the balance factor of the node.
AVL - Trees with rotation to make it balanced.


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

**prototype**

chaining

**type coercion**

**declarative vs imperative**

**var VS let & const keyword?**

**set vs array**

**primitive vs non primitive**

**shallow copy vs deep copy***

structured clone.

**pure functions**

**hoisting**

**undefined vs not defined**

**undefined vs null**

**typeof(x) === "undefined"**

**function vs arrow**

**apply,call,bind**

**forEach vs map**

**foreach vs for**

**Window**

**window vs document**

getSelection.  
getRangeAt  
getClientRects, getBoundingClientRects.  
***CDN***

**string terms**

* Palindrome - reverse words should read the same.(racecar)
* Anagram - An anagram of a string is another string that contains the same characters, only the order of characters can be different(secure) - (rescue).
* Vowels - a,e,i,o,u.

**IIFE(Immediately Invoked Function Expression)**

**Intersection Observer**

**Object Freeze vs seal vs const**

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

In programming terms, a recursive function can be defined as a routine that calls itself directly or indirectly.

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

Amazon CloudFront

**web workers**

cannot access window, cpu intensive tasks.

**white label**

**Tricky Logic**

**Web Socket vs HTTP**

**Higher order function**

Examples: Map, Filter Function.

**In Operator**

**Callback**

Callback Hell - Hard to read & maintain callbacks.
Asynchronous operations are ALL implemented in native code (usually C/C++ code) by nodejs.

Promises

**this keyword**

 In a method, this refers to the owner object and in a function, this refers to the global object.

**Event Bubbling**

**Event Propagation**

event.stopPropagation() stops the move upwards, but on the current element all other handlers will run.
To stop the bubbling and prevent handlers on the current element from running, there’s a method event.stopImmediatePropagation(). After it no other handlers execute.

**Parse Int**

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

The find() method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

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

**Event Emitter**

**Concatenation**

```
let test = 'test' + 'best' // testbest
```

**Template literals (Template strings)**

**delete operator**

**eval**

**window objects**

* localStorage - No Expiration date.

```
localStorage.getItem("test1");
```

* history
* innerHeight
* innerWidth
* sessionStorage.
* navigator.geoLocation
* pageXOffset
* screen
* document.cookie

**promise**

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

| Features          | Map                       | Object                 |
| Accidental Keys   | no keys by default        |  prototype             |
| Security          | safe                      |  allow an attacker to override the object's prototype |
| Key Types         | map key can be functions  |  must be a string 
                       objects  
| size property     | number of items           |  Object.keys().length
| Iteration         | map is iterable           |  Object.entries()
| Performance       | better                    |  not optimized
| Serializing
 & parsing          | no native support         | native support for serialization


**css**

style.display
style.

## ReactJS Topics

**React Classes**

Super()

passing props to super.

**create react app**

What are each of these files and folders for?

*  README.md.
* node_modules - semantic-  ^, *, ~.
* package.json.
* .gitignore
* public 
* src

**Source Map Explorer**

**depcheck**

**change app's metadata**

public/index.html

**build folder**

contains static/js, static/css, assetmanifest.json

**React Folder Structure**

src/js
src/style

src - contains js, style.js.

The /src folder comprises of the raw non-minified code.

dist: It stands for distribution and is the minified or concatenated version it has been actually used on production sites.

**minification**

Developers write code that is optimized for human readability. This code might contain extra information that is not necessary for the code to run, such as comments, spaces, indents, and multiple lines.

**build folder**

static/js
static/css

**React Scripts**

react-scripts

Creating a React App Without Webpack and Babel

**React Render**

// client side
import ReactDOM from 'react-dom/client';

import ReactDOM from 'react-dom/server';

**React Router**

once `BrowserRouter` is added we can start using router anywhere.

**React Thunk**

Nested routes - outlets

Link vs NavLinnk

**React DOM**

import ReactDOM from "react-dom/client";

**React Build**

React build combine all components and css into minified version, will be added to respective bundles.

* Minified versions of JavaScript files (bundle.js)
* Minified versions of CSS files (style.css)

dist folder 
* bundle.js
* style.css

compression is a process in which the size of a file is reduced by re-encoding the file data to use fewer bits of storage than the original file.

**bundle**

bundle analyzer: This analysis provides a clear picture of each library used in your project and how they affect the JavaScript bundle size.
Compressing Bundles: Gzip and Brotli are the most commonly used compression techniques, and you can use their Webpack plugins to simplify the entire process.

**Bundling**:
minification to build folder, , Tree Shaking, Code Splitting

**Babel**

**Compilers**

**Virtual DOM**

**Reconciliation**

**React Diff Algorithm**

Element Type Checking
Key Based

**React Fiber**

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

**Composition Vs Inheritance**

no hierarchies with composition.
no parent child relationship.
Composition with HOCs(Adds behavior without modifying the original component).

**HOC**

**Render Props**

Example Downshift.
MouseTracker

**Pure Components**

**Lifting State Up**

**props.children**

**React Portals**

**JSX**

**Keys**

**State vs props**

**Controlled vs. Uncontrolled Components**

**Strict Mode**

**Typechecking With PropTypes**

**Refs**

**React Profiler**

**React Error Boundaries**

getDerivedStateFromError

**React Fragments**

**React JS Multiple SetStates**

React 18:

Batch Updates are available for all events.

**Redux**
@reduxjs/toolkit

**How does Redux compare to the React Context API ?**

Similarities

avoid prop drilling

Differences

**Call Endpoint Once to Fetch Initial Data**

UseEffect with empty Array is called only after first render.

**Function with big calculations**

UseMemo - Runs the function only if arguments change other it will return the stored value.

**Difference with useMemo vs useCallback**

useMemo - stores value.\
useCallback - stores function

usedebugvalue

**allow transition in state**

useTransition

**React Optimizations**

code splitting, lazy.
using keys for list.

react patterns

Avoid re-renders by providing array of values in useEffect.
single render with empty array in useeffect.\

Big Calculations useMemo to store the output.\  
useCallback to store the function.\  
PureComponents, React.memo for re-render only when a prop changes(Table rows).

Error Boundaries.

**Refresh Table specific row**

Create seperate component for rows. Use PureComponents or React.Memo to render only when props changes. Re-render will only happen for rows with value change.

## NodeJS Topics

**single threaded event loop architecture**

**libuv thread pool**

**middlewares**

**Handling a Large Volume of Customers in Node.js**

Load Balancing & Scaling with Clustering <br/>
Optimize Database Queries & Caching(redis) <br/>
Use Asynchronous & Non-Blocking Code <br/>
connection loop to reuse db connections <br/>
compressions for response <br/>
Rate Limiting & API Throttling <br/>
monitor and log <br/>

**child processes**

concurrent

**worker thread **

**v8 engine**

**debugging issue which is only in production not in dev docker**

cors, bodyparser, compression, cookie parser

**use async and await**

**create query executed and disk storage in database becomes full solution for this***

***Process environment***

Config values are set in parameter store in AWS, those values set to process environment during jenkins build, and those are accessed in code.

***Connect to MySql***

**Connect to MongoDB**

**content negotiation**

**third party libraries**

### ExpressJS Topics

***Request Object***

params, query, body

***app.use()***

***Next function***

***Middleware function***

***Error handling functions***

## NextJS Topics

**Nextjs Advantages**

* Webpack Integrated, Compiler replaces babel for individual files and terser for minifying output bundles.

* Pre-rendering

Server side rendering - getServerSideProps - Next.js will pre-render this page on each request.
Static Generation - getStaticProps - Next.js will pre-render this page at build time
Incremental Static Generation -  static pages, but content updates automatically without rebuilding the whole app.

* With Links, prefetches and does client side navigation.

* Automatic static optimization.

* Dynamic routing *

* Dynamic import, lazyload using suspense.

**What is hydration**

**ISR**

**SWR**

**Client Side Navigation**

## REST Apis Topics

***Stateless***

Client provides all information required for the server in the form of url, query string, header or through a body.

***CRUD***

Create, Read, Update, Delete

POST,  GET,   PUT,    DELETE.

POST:

POST methods are used to create a new resource into the collection of resources.

PUT:

Use PUT APIs primarily to update an existing resource (if the resource does not exist, then API may decide to create a new resource or not).

PATCH:

HTTP PATCH requests are to make a partial update on a resource.

## CSS Topics

***Box Model***

In CSS, the term "box model" is used when talking about design and layout.
The CSS box model is essentially a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content. 

***Visibility vs Display vs Opacity***

* visibility: hidden - Element is still part of DOM, So the element takes up space.
* display: none - Element is removed from the DOM.
* opacity: 0 - This is used for transition mainly. Element is still part of DOM, So the element takes up space.

***display***

* contents - Makes the container disappear, making the child elements children of the element the next level up in the DOM
* inline - 	Displays an element as an inline element (like <span>). Any height and width properties will have no effect.
* block - Displays an element as a block element (like <p>). It starts on a new line, and takes up the whole width.
* flex - Displays an element as a block-level flex container
* grid - Displays an element as a block-level grid container
* inline-block	Displays an element as an inline-level block container. The element itself is formatted as an inline element, but you can apply height and width values
* inline-flex, inline-grid, inline-table.

Explanation

An element with display: flex is similar to an element with display: block, whereby it occupies the whole row. However, its child elements can be positioned flexibly and dynamically, compared to previously-available layout properties.

If we change this to display: inline-flex, it:

makes the parent container display inline
still applies all flex properties to the children, no differently form display: flex
This means that if the child elements aren't too big, two containers with display: inline-flex can sit side-by-side.
Other display properties also have an inline counterpart:

block has inline-block
table has inline-table
and even grid has inline-grid

https://codepen.io/clairecodes/pen/POjKXY

***grid vs flex***

The basic difference between CSS Grid Layout and CSS Flexbox Layout is that flexbox was designed for layout in one dimension - either a row or a column. Grid was designed for two-dimensional layout - rows, and columns at the same time.
fr - fractional unit.
grid-template-columns: repeat(3, 1fr)

***vertical align***

baseline - baseline of parent.
percentage, pixels allowed.

**align items***

The align-items property specifies the default alignment for items inside the flexible container.

align-self - overrides align items.

The align-content property modifies the behavior of the flex-wrap property. It is similar to align-items, but instead of aligning flex items, it aligns flex lines.

text-align

justify-contents - center in flexbox.

***Descendant Selector (space)***

The descendant selector matches all elements that are descendants of a specified element. selects all paragraph below.

```
div p {
  background-color: yellow;
}

<div>
  <p>Paragraph 1 in the div.</p>
  <p>Paragraph 2 in the div.</p>
  <section><p>Paragraph 3 in the div.</p></section>
</div>
```

***Child Selector (>)***

The child selector selects all elements that are the children of a specified element.

```
div > p {
  background-color: yellow;
}

<div>
  <p>Paragraph 1 in the div.</p>
  <p>Paragraph 2 in the div.</p>
  <section>
    <!-- not Child but Descendant -->
    <p>Paragraph 3 in the div (inside a section element).</p>
  </section>
  <p>Paragraph 4 in the div.</p>
</div>
```

***Adjacent Sibling Selector (+)***

The adjacent sibling selector is used to select an element that is directly after another specific element.

```
<h2>Adjacent Sibling Selector</h2>

<p>The + selector is used to select an element that is directly after another specific element.</p>
<p>The following example selects the first p element that are placed immediately after div elements:</p>

<div>
  <p>Paragraph 1 in the div.</p>
  <p>Paragraph 2 in the div.</p>
</div>

<p>Paragraph 3. After a div.</p>
<p>Paragraph 4. After a div.</p>

<div>
  <p>Paragraph 5 in the div.</p>
  <p>Paragraph 6 in the div.</p>
</div>

<p>Paragraph 7. After a div.</p>
<p>Paragraph 8. After a div.</p>

```

***General Sibling Selector (~)***

The general sibling selector selects all elements that are next siblings of a specified element.

```
<p>Paragraph 1.</p>

<div>
  <p>Paragraph 2.</p>
</div>

<p>Paragraph 3.</p>
<code>Some code.</code>
<p>Paragraph 4.</p>
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
***hover***

margin not considered on hover.

***css transform***

CSS transforms allow you to move, rotate, scale, and skew elements.

***position***

The five different position values are fixed, static, absolute, sticky, and relative.

* Static - The element is positioned according to the normal flow of the document.
* Relative - The element is positioned according to the normal flow of the document, and then offset relative to itself based on the values of top, right, bottom, and left.
* Absolute - The element is removed from the normal document flow, and no space is created for the element in the page layout.
Absolutely positioned elements are positioned with respect to a containing block, which is the nearest postioned ancestor. If there is no positioned ancestor, the viewport will be the containing block.
* Fixed - The element is removed from the normal document flow, and no space is created for the element in the page layout.
Elements with fixed positioning are fixed with respect to the viewport—the viewport is always their containing block.
* Sticky - The element is positioned according to the normal flow of the document, and then offset relative to its nearest scrolling ancestor and containing block (nearest block-level ancestor), including table-related elements, based on the values of top, right, bottom, and left.

***mixin***

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

***float***

The CSS float property specifies how an element should float.
In its simplest use, the float property can be used to wrap text around images.

The CSS clear property specifies what elements can float beside the cleared element and on which side.
When clearing floats, you should match the clear to the float: If an element is floated to the left, then you should clear to the left. Your floated element will continue to float, but the cleared element will appear below it on the web page.

***Table***

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

***Margin vs Padding***

 the margin property controls the space outside an element, and the padding property controls the space inside an element.

**ruleset***

**css integration***

 * style tags in the head section.
 * inline styling.
 * css in seperate file and linking to the html page.

**sprites***

 An image sprite is a collection of images put into a single image.

**css image repetition***

 The background-repeat property is used to control the image.

 ```
 background-image: url(‘url_of_image’);

  background-repeat: no-repeat;

  background-attachment: fixed;
 ```

**RGB***

 In CSS, a color can be specified as an RGB value, using this formula: rgb(red, green, blue) Each parameter (red, green, and blue) defines the intensity of the color between 0 and 255.

***CSS [attribute] Selector***

The [attribute] selector is used to select elements with a specified attribute.

```
a[target] {11
  background-color: yellow;
}
```

<!DOCTYPE>
<head>
<link> - best place to use it  in head tags
<script> - best place for script tags
custom tag names - inline

inline vs block
inline block
replaced element - images
box model

## Cloud

**Containerization**

**Virtualization vs Containerization**

Virtualization is an abstract version of a physical machine, 
containerization is the abstract version of an application.

**Docker**

**Docker Image**

**docker file**

**Docker Engine**

**docker hub**

**Components of docker**

* client
* host

**Commands**

* docker pull image
* docker run image
* docker system prune

**docker vs kubernettes vs jenkins**

## AWS

**ECS(Elastic Container Service)**

**EC2(Elastic Compute Cloud)**

**VPC**

**Serverless**

**Lambda**

**SQS**

**Amazon API Gateway**

**S3 Bucket**

**Dynamo DB**

**step functions**

**JWT**

**Cloud Watch**

**Cloud Front with Custom routing**

**Parameter store**

**Robots.txt, , route 53**

**Large Files in AWS**

## Jenkins Topics

Jenkins is typically run as a standalone application in its own process with the built-in Java servlet container/application server (Jetty).

## Testing Topics

***Test runners***

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

**Assertion libraries with mocha**

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

## Analytics

***Google Analytics***

***Group Stats***

InHouse tracking.

***Mixpanel***

Mixpanel events. Provides test and prod environment. Live events can be seen.

***HotJar***

See where the users are active.

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

SQL Query to Find the Second Highest Value in a Table

Views

text to dates

triggers

stored procedures

## No SQL:

difference with no sql and sql

tyoes of no sql DBS 

Popular NoSQL Databases & Their Use Cases

CAP Theorem

advantages and disadvantages of no sql.

Types of Indexing in NoSQL Databases

data consistency 

eventual consistency

## MongoDB Topics:

***Cluster***

***Replica Set***

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

## HTML

***Semantic vs non***

semantic elements: <form>, <table>, <article>
non semantic elements:  <div>, <span>


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

## Microservices

https://nodesource.com/blog/microservices-in-nodejs

## OAuth

Client ID, Client Secret, Access Token

Authorization: Bearer Token

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
