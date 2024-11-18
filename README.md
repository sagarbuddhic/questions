# Questions

### [GIT](#git-topics)
### [Javascript](#javascript-topics)
### [-ReactJS](#reactjs-topics)
### [-NodeJS](#nodejs-topics)
### [-ExpressJS](#expressjs-topics)
### [-NextJS](#nextjs-topics)
### [-Rest Apis](#rest-apis-topics)
### [CSS](#css-topics)
### [-Containerization](#containerization-topics)
### [-AWS](#aws-topics)
### [-Jenkins](#jenkins-topics)
### [-Testing](#testing-topics)
### [-MySql](#mysql-topics)
### [Heroku](#heroku-topics)
### [-12 Factor](#12-factor-topics)
### [Python](#python)
### [Data Structures](#data-structures)


## GIT Topics

***Package Manager***

Package managers or Package Management Systems are collections of tools that help you install, remove, modify, upgrade, configure computer programs, as well as audit dependencies and report which ones should be upgraded to mitigate potential vulnerabilities.

https://www.geeksforgeeks.org/difference-between-npm-and-yarn/

***yarn vs npm***

Dependencies:

yarn:

Yarn installs dependencies using the yarn command. It installs dependencies concurrently, i.e., in parallel, allowing you to add multiple files simultaneously.
yarn produces yarn.lock. 
Yarn outperforms NPM when installing bigger files.

npm:

NPM installs dependencies one by one through the npm install command. 
it produces package.json.

Security:

Both yarn and npm does secuirty check on packages.

Plug'n'Play - Yarn produces a single .pnp.cjs file that maps project dependencies instead of utilizing the node modules folder. This results in more streamlined dependency trees and quicker project launch and package installation.

Zero installation - Works with Plug'n'Play, as it uses the .pnp.cjs file to map packages stored in the offline cache. This allows you to quickly retrieve and install packages that have been saved.

License check - Yarn has a built-in licensing checker when obtaining and installing packages.

***GIT INIT***

The git init command creates a new Git repository. It can be used to convert an existing, unversioned project to a Git repository or initialize a new, empty repository. Most other Git commands are not available outside of an initialized repository, so this is usually the first command you'll run in a new project.

Executing git init creates a .git subdirectory in the current working directory, which contains all of the necessary Git metadata for the new repository. This metadata includes subdirectories for objects, refs, and template files. A HEAD file is also created which points to the currently checked out commit.

***Remote Repos***

To add a new remote, use the git remote add command on the terminal, in the directory your repository is stored at.

The git remote add command takes two arguments:

A remote name, for example, origin
A remote URL, for example, https://github.com/user/repo.git

***git push***

Git Push Origin and Git Push Origin Master had a big difference before the git version 1.7.11. At that time 

git push origin 
by default pushes all your branches to the origin. While

git push origin master 
pushing your master branch to the origin.

## Javascript Topics

***white label***

White label software is a fully customizable software, enabling companies to rebrand it as their own. It is typically sold as part of a subscription, as the software developer lends rights to use and customize the front-end aspects for a specific period.

***Tricky Logic***

```
console.log('2' + 3) // 23 - If one string is present, other values are strings.

console.log(2 + true); // 3 - Boolean will be made integer(true is 1 & false is 0)

console.log("5" - 2); // 3 - for minus integer will be parsed from string.

console.log("x" * 2); // NAN - x is parsed and it is NAN.

const numArray = [0, 1, 2, 3];
numArray[10] = 11;
console.log(numArray);// 0, 1, 2, 3,,,,,,, 11 - returns array with 11 values with empty values in between.

function test3(num) {
  return
    [num]
}
console.log(test3(10)); // undefined. return adds semicolon at the end and returns undefined.

var y = 1;
if (function f() {}) {
  y += typeof f;
}
console.log(y); // 1undefined

(function() {
  var a = b = 5;
})();
console.log(b); // 5 - b is defined globally.

for (var i = 0; i < 4; i++) {
  setTimeout(() => console.log(i), 0)
} // 4 4 4 4 - for loop runs and increments value to 4, setTimeout is moved to webAPIs once the loop runs
// and que is emoty then setTimeout is added to queue and to callstack and runs four times to show 4.

const clothes = ['jacket', 't-shirt'];
clothes.length = 0;
clothes[0]; // undefined - length = 0 sets empty array.

// foo = [] creates a new array and assigns a reference to it to a variable. Any other references are unaffected and still point to the original array.
// foo.length = 0 modifies the array itself. If you access it via a different variable, then you still get the modified array.
var foo = [1,2,3];
var bar = [1,2,3];
var foo2 = foo;
var bar2 = bar;
foo = [];
bar.length = 0;
console.log(foo, bar, foo2, bar2);

const length = 4;
const numbers = [];
for (var i = 0; i < length; i++);
{ 
  // a simple block
  numbers.push(i + 1);
}
console.log(numbers); // [5]

0.1 + 0.2 == 0.3 // false 0.1 + 0.2 = 0.30000

console.log(myVar);   // undefined - hoisting moves declarations to the top.
console.log(myConst); // reference error - const & let does not support hoisting.
var myVar = 'value';
const myConst = 3.14;

var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
// outer func:  this.foo = bar
// outer func:  self.foo = bar
// inner func:  this.foo = undefined
// inner func:  self.foo = bar

```

***undefined vs not defined***

```
let x;
console.log(x); // undefined
console.log(type0f(x)); // 'undefined'
console.log(y)// ReferenceError: y is not defined
```

***string terms***

* Palindrome - reverse words should read the same.(racecar)
* Anagram - An anagram of a string is another string that contains the same characters, only the order of characters can be different(secure) - (rescue).
* Vowels - a,e,i,o,u.

***IIFE(Immediately Invoked Function Expression)***

If you want to create a function and execute it immediately after the declaration, we can declare an anonymous function.

Anonymous functions are functions without names.
Anonymous functions can be used as an argument to other functions or as an immediately invoked function execution.

***apply,call,bind***

call:

The call() method is a predefined JavaScript method.

It can be used to invoke (call) a method with an owner object as an argument (parameter).

```
function fullName() {
    return this.firstName + " " + this.lastName;
  }
  
const person1 = {
  firstName:"Jhn",
  lastName: "Doe"
}

console.log(fullName.call(person1)); // Jhn Doe
```

apply:
The apply() method accepts arguments in an array:

```
const person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
  }
}

const person1 = {
  firstName:"John",
  lastName: "Doe"
}

person.fullName.apply(person1, ["Oslo", "Norway"]);
```

bind:

```
const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}

const member = {
  firstName:"Hege",
  lastName: "Nilsen",
}

let test = person.fullName.bind(member);
test();
```

```
const person = {
  firstName:"John",
  lastName: "Doe",
  display: function () {
    let x = document.getElementById("demo");
    x.innerHTML = this.firstName + " " + this.lastName;
  }
}

let display = person.display.bind(person);
setTimeout(display, 3000);
```

***Intersection Observer***

The Intersection Observer API lets code register a callback function that is executed whenever an element they wish to monitor enters or exits another element (or the viewport), or when the amount by which the two intersect changes by a requested amount.

***Object Freeze***

Freezing an object is equivalent to preventing extensions and then changing all existing properties' descriptors to configurable: false, writable: false.

```
const person = Object.freeze({name: "Geeksforgeeks"});
    
     // TypeError in strict mode
     //in non-strict mode it prints "Geeksforgeeks"
     person.name = "gfg";
```

The const keyword ensures that the variable created is read-only. But It doesn’t mean that the actual value to which the const variable reference is immutable. Even though the person variable is constant. However, you can change the value of its property. But you cannot reassign a different value to the person constant.

```
const person = {
        name: "Geeksforgeeks"
    };
         
// No TypeError
person.name = "gfg";
console.log(person.name);
```

***object seal***

The Object.seal() method seals an object. Sealing an object prevents extensions and makes existing properties non-configurable. A sealed object has a fixed set of properties: new properties cannot be added, existing properties cannot be removed, their enumerability and configurability cannot be changed, and its prototype cannot be re-assigned. Values of existing properties can still be changed as long as they are writable. seal() returns the same object that was passed in.

***undefined vs null***

undefined means a variable has been declared but has not yet been assigned a value.
null is an assignment value. It can be assigned to a variable as a representation of no value.

 undefined and null are two distinct types: undefined is a type itself (undefined) while null is an object.

```
null === undefined // false
null == undefined // true
null === null // true
```

***AAA***

The AAA (Arrange-Act-Assert) pattern has become almost a standard across the industry. It suggests that you should divide your test method into three sections: arrange, act and assert. Each one of them only responsible for the part in which they are named after.
So the arrange section you only have code required to setup that specific test. Here objects would be created, mocks setup (if you are using one) and potentially expectations would be set. Then there is the Act, which should be the invocation of the method being tested. And on Assert you would simply check whether the expectations were met. More info can be found HERE.

***forEach vs map***

The forEach() method returns “undefined“.
Not mutating the original array.

***History***

The term “history” and "history object" in this documentation refers to the history package.

```
history.back();     // equivalent to clicking back button
history.go(-1);     // equivalent to history.back();
```

The following terms are also used:
“browser history” - A DOM-specific implementation, useful in web browsers that support the HTML5 history API.
“hash history” - A DOM-specific implementation for legacy web browsers
“memory history” - An in-memory history implementation, useful in testing and non-DOM environments like React Native

***Location***

window.location.replace('https://developer.mozilla.org/en-US/docs/Web/API/Location.reload'); // does not save previous url in history

window.location.href

window.location.assign

***Window***

getSelection - object representing range of text or current position of cursor.
getRangeAt
getClientRects, getBoundingClientRects.

// point a cursor
const inputRange = document.createRange();
inputRange.selectNodeContents(editDiv.current);
inputRange.collapse(false);
selection.removeAllRanges();
selection.addRange(inputRange);


***Location vs History***

The difference from the assign() method is that after using replace() the current page will not be saved in session History, meaning the user won't be able to use the back button to navigate to it.

***single Threaded***

Javascript is a single threaded language.This means it has one call stack and one memory heap.
Javascript engine (V8, Spidermonkey, JavaScriptCore, etc...) has Web API(Javascript uses low level programming languages like C++ to perform these behind the scenes.)
 that handle these tasks in the background. The call stack recognizes functions of the Web API and hands them off to be handled by the browser. Once those tasks are finished by the browser, they return and are pushed onto the stack as a callback.

 http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D

***CDN***

CDN stands for Content Delivery Network. CDNs deliver cached, static content from a network of servers across the globe.

***Declarative vs Imperative***

try / catch is great but it only works for imperative code, React components are declarative and specify what should be rendered.

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

***Hoisting Tricky Question***

var bar = 1;

function test() {
   bar = 10;
   return bar;
   function bar () {}; // using hoisting bar is initialized later to a function.

}

test();
console.log(bar); // returns 1 instead 10.

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

Examples: Map, Filter Function.

***In Operator***

The in operator returns true if the specified property is in the specified object or its prototype chain.

```
'test' in {'test': 't'} // true
```

***Callback***

https://stackoverflow.com/questions/70237742/can-someone-please-explain-me-how-is-nodejs-single-threaded-being-asynchronous

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

Callback Hell - Hard to read & maintain callbacks.
Asynchronous operations are ALL implemented in native code (usually C/C++ code) by nodejs.

Promises - 
A promise will gain control over the results of callbacks: resolve and reject functions;
All promise objects have the then () method.

Async functions can contain zero or more await expressions. Await expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected. The resolved value of the promise is treated as the return value of the await expression. Use of async and await enables the use of ordinary try / catch blocks around asynchronous code.

***This keyword***

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

All JavaScript objects inherit properties and methods from a prototype.

inheritance

```
//Student.prototype = Person.prototype;
Student.prototype = new Person();
Student.prototype.constructor = Student;

```

The JavaScript prototype property allows you to add new properties to object constructors:

```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.nationality = "English";
```

***Event Emitter***

```
class EventEmitter {
 constructor() {
   this.events = {};
  }
	
  on(eventName, fn) {
  	if(!this.events[eventName]) {
    	this.events[eventName] = [];
    }
    this.events[eventName].push(fn);
  }
  
  emit(eventName, data) {
  	const events = this.events[eventName];
    if(events) {
    	events.forEach(fn => {
      	fn(data);
      });
    }
  }
}

let emitter = new EventEmitter();
let first = function (data) {
  console.log(`first ${data}`);
}

let second = function (data) {
  console.log(`second ${data}`);
}

emitter.on('ADD', first);
emitter.on('ADD', second);

emitter.emit('ADD', 1);

//"first 1"
//"second 1"
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

***promise***

Promise.all returns first reject.

```
const timeout = new Promise((resolve, reject) => {
  setTimeout(() => resolve(110), 1000);
});

const rejected = new Promise((resolve, reject) => {
 reject("Bankrupt");
});

const allPromises = Promise.all([timeout, rejected]);
allPromises.then (
  value => console.log(value),
  reason => console.log(reason)
);

// "Bankrupt"
```

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

Arrow functions dont have hoisting, normal functions have hoisting. 

```
foo(); // 'FOOOOO'
function foo() {
  console.log('FOOOOO');
}

foo1(); Uncaught ReferenceError: foo1 is not defined
var foo1 = () => {
  console.log('FOOOOO');
};
```

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

***React Classes***

Super(): It is used to call the constructor of its parent class. This is required when we need to access some variables of its parent class.

 If we want to use this in the constructor, we need to pass it to super. If we want to use this.props inside the constructor we need to pass it with the super() function. Otherwise, we don’t want to pass props to super() because we see this.Props are available inside the render function.

***create react app***

What are each of these files and folders for?

*  README.md is a markdown file that includes a lot of helpful tips and links that can help you while learning to use Create React App.
* node_modules is a folder that includes all of the dependency-related code that Create React App has installed. You will never need to go into this folder.
* package.json that manages our app dependencies and what is included in our node_modules folder for our project, plus the * scripts we need to run our app.
* .gitignore is a file that is used to exclude files and folders from being tracked by Git. We don't want to include large folders such as the node_modules folder
* public is a folder that we can use to store our static assets, such as images, svgs, and fonts for our React app.
* src is a folder that contains our source code. It is where all of our React-related code will live and is what we will primarily work in to build our app.

***Source Map Explorer***

Source map explorer analyzes JavaScript bundles using the source maps. This helps you understand where code bloat is coming from.

***depcheck***

Depcheck is a tool for analyzing the dependencies in a project to see: how each dependency is used, which dependencies are useless, and which dependencies are missing from package.json.

***change app's metadata***

public/index.html

***build folder***

contains static/js, static/css, assetmanifest.json

***React Folder Structure***

src/js
src/style

src - contains js, style.js.

src: It stands for source and is the raw code before minification or concatenation or some other compilation it has been used to read or edit the code.

The /src folder comprises of the raw non-minified code.

dist: It stands for distribution and is the minified or concatenated version it has been actually used on production sites.

***minification***
Developers write code that is optimized for human readability. This code might contain extra information that is not necessary for the code to run, such as comments, spaces, indents, and multiple lines.

***build folder***

static/js
static/css

***React Scripts***

react-scripts

***React Render***

```
// client side
import ReactDOM from 'react-dom/client';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

```
// server side
import ReactDOM from 'react-dom/server';
ReactDOMServer.renderToString(<App/>);
```

***React Router***

once `BrowserRouter` is added we can start using router anywhere.

```
<Route path="/" element={<Home />} />
```

***React DOM***

```
import ReactDOM from "react-dom/client";

const root = ReactDOM.createRoot(
  document.getElementById("root")
);
root.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

***React Build***

React build combine all components and css into minified version, will be added to respective bundles.

* Minified versions of JavaScript files (bundle.js)
* Minified versions of CSS files (style.css)

dist folder 
* bundle.js
* style.css

```
npm install compression //installation
var compression = require(‘compression’); //import to app	
app.use(compression());
```

compression is a process in which the size of a file is reduced by re-encoding the file data to use fewer bits of storage than the original file.

***bundle***

bundle analyzer: This analysis provides a clear picture of each library used in your project and how they affect the JavaScript bundle size.
Compressing Bundles: Gzip and Brotli are the most commonly used compression techniques, and you can use their Webpack plugins to simplify the entire process.

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


***Uncontrolled Components***

In most cases, we recommend using controlled components to implement forms. In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself.

To write an uncontrolled component, instead of writing an event handler for every state update, you can use a ref to get form values from the DOM.

***Composition Vs Inheritance***

Sometimes we think about components as being “special cases” of other components. For example, we might say that a WelcomeDialog is a special case of Dialog.In React, this is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props:

```
function Dialog(props) {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        {props.title}
      </h1>
      <p className="Dialog-message">
        {props.message}
      </p>
    </FancyBorder>
  );
}

function WelcomeDialog() {
  return (
    <Dialog
      title="Welcome"
      message="Thank you for visiting our spacecraft!" />
  );
}
```

***Virtual DOM***

The virtual DOM (VDOM) is a programming concept where an ideal, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called reconciliation.

***Render Props***

The term “render prop” refers to a technique for sharing code between React components using a prop whose value is a function.

A component with a render prop takes a function that returns a React element and calls it instead of implementing its own render logic.Example Downshift.

```
<DataProvider render={data => (
  <h1>Hello {data.target}</h1>
)}/>
```

***JSX***

Each JSX element is just syntactic sugar for calling React.createElement(component, props, ...children). So, anything you can do with JSX can also be done with just plain JavaScript.
JSX is a syntax extension to JavaScript. It is similar to a template language, but it has full power of JavaScript. JSX gets compiled to React.createElement() calls which return plain JavaScript objects called “React elements”.

***props.children***

props.children
props.children is available on every component. It contains the content between the opening and closing tags of a component. 

```
<Welcome>Hello world!</Welcome>

function Welcome(props) {
  return <p>{props.children}</p>;
}
```

***Keys***

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity. We don’t recommend using indexes for keys if the order of items may change.

```
const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);
```

***Lifting State Up***

***react dom***

The react-dom package provides DOM-specific methods that can be used at the top level of your app and as an escape hatch to get outside the React model if you need to.

***State***

A component needs state when some data associated with it changes over time. For example, a Checkbox component might need isChecked in its state, and a NewsFeed component might want to keep track of fetchedPosts in its state.

The most important difference between state and props is that props are passed from a parent component, but state is managed by the component itself. A component cannot change its props, but it can change its state.

***Controlled vs. Uncontrolled Components***

React has two different approaches to dealing with form inputs.

An input form element whose value is controlled by React is called a controlled component. When a user enters data into a controlled component a change event handler is triggered and your code decides whether the input is valid (by re-rendering with the updated value). If you do not re-render then the form element will remain unchanged.

An uncontrolled component works like form elements do outside of React. When a user inputs data into a form field (an input box, dropdown, etc) the updated information is reflected without React needing to do anything. However, this also means that you can’t force the field to have a certain value.

***Strict Mode***

StrictMode is a tool for highlighting potential problems in an application. Like Fragment, StrictMode does not render any visible UI. It activates additional checks and warnings for its descendants.Strict mode checks are run in development mode only; they do not impact the production build.

Identifying components with unsafe lifecycles
Warning about legacy string ref API usage
Warning about deprecated findDOMNode usage
Detecting unexpected side effects
Detecting legacy context API
Ensuring reusable state

***Typechecking With PropTypes***

React has some built-in typechecking abilities. To run typechecking on the props for a component, you can assign the special propTypes property:
 When an invalid value is provided for a prop, a warning will be shown in the JavaScript console.

```import PropTypes from 'prop-types'```

```
import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};

Greeting.defaultProps = {
  name: 'sagar'
}
```

***Refs***

In the typical React dataflow, props are the only way that parent components interact with their children. To modify a child, you re-render it with new props. However, there are a few cases where you need to imperatively modify a child outside of the typical dataflow. The child to be modified could be an instance of a React component, or it could be a DOM element. For both of these cases, React provides an escape hatch.

When to Use Refs
There are a few good use cases for refs:

Managing focus, text selection, or media playback.
Triggering imperative animations.
Integrating with third-party DOM libraries.

***React Fiber***

Fiber is the new reconciliation engine in React 16. Its main goal is to enable incremental rendering of the virtual DOM.

***React Portals***

Portals provide a first-class way to render children into a DOM node that exists outside the DOM hierarchy of the parent component.
A typical use case for portals is when a parent component has an overflow: hidden or z-index style, but you need the child to visually “break out” of its container. For example, dialogs, hovercards, and tooltips.

```
render() {
  // React does *not* create a new div. It renders the children into `domNode`.
  // `domNode` is any valid DOM node, regardless of its location in the DOM.
  return ReactDOM.createPortal(
    this.props.children,
    domNode
  );
}
```

***React Profiler***

The Profiler measures how often a React application renders and what the “cost” of rendering is. Its purpose is to help identify parts of an application that are slow and may benefit from optimizations such as memoization.

***React Optimizations***

Avoid re-renders by providing array of values in useEffect.\
Big Calculations useMemo to store the output.\
useMemo or memo HOC for re-render only when a prop changes(Table rows).
useCallback to store the function.\
code splitting, React.lazy, dynamic import.
Error Boundaries.

***React Error Boundaries***

As of React 16, errors that were not caught by any error boundary will result in unmounting of the whole React component tree.
This change means that as you migrate to React 16, you will likely uncover existing crashes in your application that have been unnoticed before. Adding error boundaries lets you provide better user experience when something goes wrong.

For example, Facebook Messenger wraps content of the sidebar, the info panel, the conversation log, and the message input into separate error boundaries. If some component in one of these UI areas crashes, the rest of them remain interactive.

***React Fragments***

A common pattern in React is for a component to return multiple elements. Fragments let you group a list of children without adding extra nodes to the DOM.

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

***Babel***

Babel is a JavaScript transpiler that converts edge JavaScript into plain old ES5 JavaScript that can run in any browser (even the old ones). It makes available all the syntactical sugar that was added to JavaScript with the new ES6 specification, including classes, fat arrows and multiline strings.

***Compilers***

A JavaScript compiler takes JavaScript code, transforms it and returns JavaScript code in a different format. The most common use case is to take ES6 syntax and transform it into syntax that older browsers are capable of interpreting. Babel is the compiler most commonly used with React.

***HOC***

A higher-order component (HOC) is an advanced technique in React for reusing component logic. HOCs are not part of the React API, per se. They are a pattern that emerges from React’s compositional nature.Concretely, a higher-order component is a function that takes a component and returns a new component.

***IOC***

One Example in react is passing the component itself as props.

***React.lazy***

The React.lazy function lets you render a dynamic import as a regular component.
This will automatically load the bundle containing the OtherComponent when this component is first rendered.

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

https://stackoverflow.com/questions/70237742/can-someone-please-explain-me-how-is-nodejs-single-threaded-being-asynchronous

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
const client = new MongoClient(uri, {
    useNewUrlParser: true,
    useUnifiedTopology: true,
    serverApi: ServerApiVersion.v1,
  });

  await client.connect();

  const db = client.db("sample_work");
  db.collection("users")
    .find()
    .toArray((err, results) => {
      if (err) throw err;
      const output = results.map((result) => ({
        id: result.id,
        name: result.name,
        email: result.email,
        gender: result.gender,
        status: result.status,
      }));
    });
```

### ExpressJS Topics

***Request Object***

params - /candidates/:id - req.params.id property is an object containing properties mapped to the named route “parameters”.
query - /candidates/?skills='aws' - req.query contains all query.
body - req.body contains all body.

***app.use()***

The app.use() function is used to mount the specified middleware function(s) at the path which is being specified. It is mostly used to set up middleware for your application.
app.use(express.static('public'))
```
app.use(express.json()); // The express.json() function is a built-in middleware function in Express. It parses incoming requests with JSON payloads and is based on body-parser
```

***Next function***

The next() function is not a part of the Node.js or Express API, but is the third argument that is passed to the middleware function.
If you pass an error to next() and you do not handle it in a custom error handler, it will be handled by the built-in error handler.
The error will be written to the client with the stack trace. The stack trace is not included in the production environment.

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

* Webpack Integrated, Compiler replaces babel for individual files and terser for minifying output bundles.
* Pre-rendering
* With Links, Nextjs code splits, prefetches and does client side navigation.
* Incremental Static Generation.
* Automatic static optimization.
* Dynamic import, lazyload using suspense.

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

 ***ruleset***

 ***css integration***

 * style tags in the head section.
 * inline styling.
 * css in seperate file and linking to the html page.

 ***sprites***

 An image sprite is a collection of images put into a single image.

 ***css image repetition***

 The background-repeat property is used to control the image.

 ```
 background-image: url(‘url_of_image’);

  background-repeat: no-repeat;

  background-attachment: fixed;
 ```

 ***RGB***

 In CSS, a color can be specified as an RGB value, using this formula: rgb(red, green, blue) Each parameter (red, green, and blue) defines the intensity of the color between 0 and 255.

***CSS [attribute] Selector***

The [attribute] selector is used to select elements with a specified attribute.

```
a[target] {11
  background-color: yellow;
}
```

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

* Client - Performs Docker build pull and run operations to open up communication with the Docker Host.
* Host - Contains Docker daemon, containers, and associated images.
* Registry- This is where Docker images are stored. There are two of them, a public registry and a private one. Docker Hub and Docker Cloud are two public registries available for use by anyone.

***Commands***

* docker pull image
* docker run image
* docker system prune

***docker vs kubernettes vs jenkins***

* Docker is a container engine that can make and handle containers.
* Jenkins is a CI/CD model that can run/build/test the application.
* Kubernetes is a container-orchestration system for automating computer applications with the external help of CI/CD.

## AWS Topics

Amazon Web Services, Inc. is a subsidiary of Amazon that provides on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered pay-as-you-go basis. These cloud computing web services provide distributed computing processing capacity and software tools via AWS server farms.

***Parameter store***

Parameter Store, a capability of AWS Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon Machine Image (AMI) IDs, and license codes as parameter values.

***S3 Bucket***

Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can store and protect any amount of data for virtually any use case, such as data lakes, cloud-native applications, and mobile apps.

***Large Files in AWS***

When you upload large files to Amazon S3, it's a best practice to leverage multipart uploads. If you're using the AWS Command Line Interface (AWS CLI), then all high-level aws s3 commands automatically perform a multipart upload when the object is large. These high-level commands include aws s3 cp and aws s3 sync.

Multipart upload is a three-step process: You initiate the upload, you upload the object parts, and after you have uploaded all the parts, you complete the multipart upload. Upon receiving the complete multipart upload request, Amazon S3 constructs the object from the uploaded parts, and you can then access the object just as you would any other object in your bucket.

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

## Data Structures & Algorithms

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


## Analytics

***Google Analytics***

***Group Stats***

InHouse tracking.

***Mixpanel***

Mixpanel events. Provides test and prod environment. Live events can be seen.

Mixpanel is a leading product analytics software company, currently helping the world answer 81 million product questions every year. Our pioneering event-based tracking solution gives product teams the ability to gain insights into how to best acquire, convert, and retain their users across web and mobile platforms.

***HotJar***

See where the users are active.

## MongoDB Topics:

***Cluster***

“cluster” is the word usually used for either a replica set or a sharded cluster. A replica set is the replication of a group of MongoDB servers that hold copies of the same data.

***Replica Set***

A MongoDB replica set ensures replication is enforced by providing data redundancy and high availability over more than one MongoDB server.

***Shards***

A sharded cluster in MongoDB is a collection of datasets distributed across many shards (servers) in order to achieve horizontal scalability and better performance in read and write operations.

***Database Access***

Use "Database Access" Tab in mongo to edit the password.

***Network Access***

In Network Access Tab, adding 0.0.0.0/0 allows access to any ips.

***Database***

MongoDB stores data records as documents (specifically BSON documents) which are gathered together in collections. A database stores one or more collections of documents.









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

***Semantic Elements***

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: <div> and <span> - Tells nothing about its content.

Examples of semantic elements: <form>, <table>, and <article> - Clearly defines its content.



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

## Formatting

EditorConfig - VSCode will format according to the options in this file. If EditorConfig or prettierrc is not available then vscode will use its formatter.
ESLint - Create React App comes with ESLint and it can be extended.
ESLint - shows errors.
Prettier - we can show as warnings and it has better formatting. https://prettier.io/docs/en/comparison.html

```
"[javascript]": {

        "editor.formatOnSave": true,

        "editor.defaultFormatter": "esbenp.prettier-vscode",

        // "editor.defaultFormatter": "dbaeumer.vscode-eslint",

    },
```

sudo apt-get install ubuntu-desktop
