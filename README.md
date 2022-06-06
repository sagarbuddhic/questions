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

**React Optimizations**

Avoid re-renders by providing array of values in useEffect.
Big Calculations useMemo to store the output.

**Call Endpoint Once to Fetch Initial Data**

UseEffect with empty Array is called only after first render.

**Function with big calculations**

UseMemo - Runs the function only if arguments change other it will return the stored value.

**Difference with useMemo vs useCallback**

useMemo - stores value
useCallback - stores function


