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

**parse the stringified JSON**

JSON.Parse

**defer attribute**

The defer attribute specifies that the script should be executed after the page has finished parsing, but it only works for external scripts.

**Concatenation**

**typeof ob === "undefined"**

**const vs let**

**arrow function vs normal function**

With a regular function this represents the object that calls the function.
With an arrow function this represents the owner of the function:

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

**Dynamic routinng**

the matching paths will be available in the query string.

**Client Side Navigation**

adding links, useRouter.

## Containerization

**docker file**

**Components of docker**

Client - Performs Docker build pull and run operations to open up communication with the Docker Host.
Host - Contains Docker daemon, containers, and associated images.
Registry- This is where Docker images are stored. There are two of them, a public registry and a private one. Docker Hub and Docker Cloud are two public registries available for use by anyone.

**What is Container**

Containers are deployed applications bundled with all necessary dependencies and configuration file

**Virtualization**

Virtualization is the means of employing software (such as Hypervisor) to create a virtual version of a resource such as a server, data storage, or application

**Virtualization vs Containerization**

Virtualization is an abstract version of a physical machine, while containerization is the abstract version of an application.

**Commands**

docker pull image
docker run image
docker system prune

## AWS

**S3 Bucket**

storage.

**Dynamo DB**

**Amazon Ec2**

## NodeJS

### ExpressJS

**static files**

app.use(express.static('public'))

**request params**

**next function**

Notice the call above to next(). Calling this function invokes the next middleware function in the app. The next() function is not a part of the Node.js or Express API, but is the third argument that is passed to the middleware function.
If you pass an error to next() and you do not handle it in a custom error handler, it will be handled by the built-in error handler; the error will be written to the client with the stack trace. The stack trace is not included in the production environment.
res.statusCode & res.statusMessage.
So when you add a custom error handler, you must delegate to the default Express error handler, when the headers have already been sent to the client:

**middleware function**

set request values.

## REST Apis

**stateless**

client provides all information required for the server in the form of url, query string, header or through a body.

**CRUD**

Create, Read, Update, Delete

**Error handling functions**

Define error-handling middleware functions in the same way as other middleware functions, except error-handling functions have four arguments instead of three: (err, req, res, next).

**process environment**

config values are set in parameter store in AWS, those values set to process environment during jenkins build, and those are accessed in code.

## AWS

**parameter store**

**S3 Bucket**

## 12 Factor

Codebase (Github, Jenkins deployment)
Dependencies (package.json, dockerfile)
Config (parameter store in AWS)
Backing Services (Endpoints, My Sql Database)
Build, release, and Run (Jenksins Build, run tests, Release using jenkins)
Processes (execute the app as one or more stateless processes)
Port Binding (change ports in package.json)
Concurrency (Scale out via the process model)
Disposability (maximize the robustness with fast startup and graceful shutdown)
Dev/prod parity (Running scripts to make prod same as stage)
Logs (Kibana logs)
Admin processes (Run admin/management tasks as one-off processes)











