# Questions

## Javascript

**Var keyword vs let & const?**

variables with var keyword has default hoisting. 
Declaring a variable after its usage is allowed in javascript,
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

Constructor
getDerivedStateFromProps
Render
ComponentDidMount

getDerivedStateFromProps
ShouldComponentUpdate
Render
getSnapshotBeforeUpdate()
ComponentDidUpdate

**useEffect Lifecycles:**

componentDidMount, componentDidUpdate, componentWillUnmount