# Questions

## Javascript

**Var VS let & const keyword?**

Variables with var keyword has default hoisting.\
Declaring a variable after its usage is allowed in javascript,all declaration will be moved up by default which is called hoisting.

It is a good practice to declare a variable before it is used.

**Closures:**

A closure is a function having access to the parent scope, even after the parent function has closed.

**Recursive**

In programming terms, a recursive function can be defined as a routine that calls itself directly or indirectly.

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

**Parse the stringified JSON**

JSON.Parse

**defer attribute**

The defer attribute specifies that the script should be executed after the page has finished parsing, but it only works for external scripts.

**Concatenation**

**typeof ob === "undefined"**

One reason to use typeof is that it does not throw an error if the variable has not been declared.

**let vs const**

both are block scoped.
we can change let values but if we try to change const values we get Uncaught TypeError.

**Arrow function vs Normal function**

With a regular function this represents the object that calls the function.
With an arrow function this represents the owner of the function.

**Tree Shaking**

Tree shaking is a term commonly used within a JavaScript context to describe the removal of dead code.

In modern JavaScript applications, we use module bundlers (e.g., webpack or Rollup) to automatically remove dead code when bundling multiple JavaScript files into single files. This is important for preparing code that is production ready, for example with clean structures and minimal file size.

## React


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

**React Optimizations**

Avoid re-renders by providing array of values in useEffect.\
Big Calculations useMemo to store the output.\
useCallback to store the function.\
code splitting, React.lazy, dynamic import.

**Dynamic Import**

When importing statically significantly slows the loading of your code and there is a low likelihood that you will need the code you are importing, or you will not need it until a later time.

Use dynamic import only when necessary. The static form is preferable for loading initial dependencies, and can benefit more readily from static analysis tools and tree shaking.

**Bundling**

Most React apps will have their files “bundled” using tools like Webpack, Rollup or Browserify. Bundling is the process of following imported files and merging them into a single file: a “bundle”. This bundle can then be included on a webpage to load an entire app at once.

**code splitting**

To avoid winding up with a large bundle, it’s good to get ahead of the problem and start “splitting” your bundle. Code-Splitting is a feature supported by bundlers like Webpack, Rollup and Browserify (via factor-bundle) which can create multiple bundles that can be dynamically loaded at runtime. The best way to introduce code-splitting into your app is through the dynamic import() syntax.

**React.lazy**

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

**Nextjs Advantages**

Comes with webpack.\
Dynamic import, lazyload using suspense.\
Compiler replaces babel for individual files and terser for minifying output bundles.\
prerendering.\
Automatic static optimization.

**What is pre-rendering**

This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. Pre-rendering can result in better performance and SEO.

**What is hydration**

Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive.

**getServerSideProps vs getStaticProps**

Next.js will pre-render this page on each request using the data returned by getServerSideProps.\
Next.js will pre-render this page at build time using the props returned by getStaticProps.

**ISR**

Incremental Static Generation uses revalidate.
Next.js allows you to create or update static pages after you’ve built your site. Incremental Static Regeneration (ISR) enables you to use static-generation on a per-page basis, without needing to rebuild the entire site. With ISR, you can retain the benefits of static while scaling to millions of pages.
When a request is made to a path that hasn’t been generated, Next.js will server-render the page on the first request.
Future requests will serve the static file from the cache. ISR on Vercel persists the cache globally and handles rollbacks.

**SWR**

react library - stale while revalidate.

**Dynamic routing**

In Next.js you can add brackets to a page ([param]) to create a dynamic route (a.k.a. url slugs, pretty urls, and others).The matching paths will be available in the query string.

**Client Side Navigation**

Adding links, useRouter.

## Containerization

**What is Container**

Containers are deployed applications bundled with all necessary dependencies and configuration file.

**Virtualization**

Virtualization is the means of employing software (such as Hypervisor) to create a virtual version of a resource such as a server, data storage, or application

AWS ECS is just a logical grouping (cluster) of EC2 instances, and all the EC2 instances part of an ECS act as Docker host i.e. ECS can send command to launch a container on them (EC2). If you already have an EC2, and then launch ECS, you'll still have a single instance. If you add/register (by installing the AWS ECS Container Agent) the EC2 to ECS it'll become the part of the cluster, but still a single instance of EC2.

To simplify it further, if you have launched an Amazon ECS with no EC2 instances added to it, it's good for nothing i.e. you can't do anything about it. ECS makes sense only once one (or more) EC2 instances are added to it.

The next confusing thing here is the container term - which is not fully virtualized machine instances, and Docker is one technology we can use to create container instances. Docker is a utility you can install on our machine, which makes it a Docker host, and on this host you can create containers (same as virtual machines - but much more light-weight). To sum up, ECS is just about clustering of EC2 instances, and uses Docker to instantiate containers/instances/virtual machines on these (EC2) hosts. 

**Virtualization vs Containerization**

Virtualization is an abstract version of a physical machine, while containerization is the abstract version of an application.

**docker file**

**Components of docker**

Client - Performs Docker build pull and run operations to open up communication with the Docker Host.
Host - Contains Docker daemon, containers, and associated images.
Registry- This is where Docker images are stored. There are two of them, a public registry and a private one. Docker Hub and Docker Cloud are two public registries available for use by anyone.

**Commands**

docker pull image
docker run image
docker system prune

## AWS

**Parameter store**

Parameter Store, a capability of AWS Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon Machine Image (AMI) IDs, and license codes as parameter values.

**S3 Bucket**

Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can store and protect any amount of data for virtually any use case, such as data lakes, cloud-native applications, and mobile apps.

**Large Files in AWS**

When you upload large files to Amazon S3, it's a best practice to leverage multipart uploads. If you're using the AWS Command Line Interface (AWS CLI), then all high-level aws s3 commands automatically perform a multipart upload when the object is large. These high-level commands include aws s3 cp and aws s3 sync.

Multipart upload is a three-step process: You initiate the upload, you upload the object parts, and after you have uploaded all the parts, you complete the multipart upload. Upon receiving the complete multipart upload request, Amazon S3 constructs the object from the uploaded parts, and you can then access the object just as you would any other object in your bucket.

You can list all of your in-progress multipart uploads or get a list of the parts that you have uploaded for a specific multipart upload. Each of these operations is explained in this section.

**Amazon VPC**

Amazon VPC gives you full control over your virtual networking environment, including resource placement, connectivity, and security.

**Serverless**

Serverless is a cloud-native development model that allows developers to build and run applications without having to manage servers. There are still servers in serverless, but they are abstracted away from app development.

**Dynamo DB**

Amazon DynamoDB is a fully managed, serverless, key-value NoSQL database designed to run high-performance applications at any scale. DynamoDB offers built-in security, continuous backups, automated multi-Region replication, in-memory caching, and data export tools.

**Amazon API Gateway**

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

**Amazon EC2**

An Amazon EC2 instance is a virtual server in Amazon's Elastic Compute Cloud (EC2) for running applications on the Amazon Web Services (AWS) infrastructure. 

## NodeJS

**Concurrency**

As soon as Node js starts, it initializes an event loop. The event loop works on a queue (which is called an event queue) and performs tasks in FIFO(First In First Out) order. It executes a task only when there is no ongoing task in the call stack. The call stack works in LIFO(Last In First Out) order. The event loop continuously checks the call stack to check if there is any task that needs to be run. Now whenever the event loop finds any function, it adds it to the stack and runs in order.

**Process environment**

Config values are set in parameter store in AWS, those values set to process environment during jenkins build, and those are accessed in code.

### ExpressJS

**Static files**

app.use(express.static('public'))

**Request params**

The req.params property is an object containing properties mapped to the named route “parameters”. For example, if you have the route /student/:id, then the “id” property is available as req.params.id. This object defaults to {}.

**Next function**

Calling this function invokes the next middleware function in the app, The next() function is not a part of the Node.js or Express API, but is the third argument that is passed to the middleware function.

If you pass an error to next() and you do not handle it in a custom error handler, it will be handled by the built-in error handler. The error will be written to the client with the stack trace. The stack trace is not included in the production environment.

res.statusCode & res.statusMessage.

So when you add a custom error handler, you must delegate to the default Express error handler, when the headers have already been sent to the client.

**Middleware function**

Express is a routing and middleware web framework that has minimal functionality of its own: An Express application is essentially a series of middleware function calls.

Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

Middleware functions can perform the following tasks:

Execute any code.\
Make changes to the request and the response objects.\
End the request-response cycle.\
Call the next middleware function in the stack.

**Error handling functions**

Define error-handling middleware functions in the same way as other middleware functions, except error-handling functions have four arguments instead of three: (err, req, res, next).

## REST Apis

**Stateless**

Client provides all information required for the server in the form of url, query string, header or through a body.

**CRUD**

Create, Read, Update, Delete
POST,  GET,   PUT,    DELETE.

**Jenkins**

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











