# Node.js Questions

## Q01. What is Node.js, and how is it different from a browser's runtime environment?

Node.js is a JavaScript runtime environment that allows us to run JavaScript outside the browser. It uses the V8 JavaScript engine and provides APIs for server-side tasks such as working with files, handling HTTP requests, and accessing the operating system.

The main difference between Node.js and a browser is the runtime environment and the APIs they provide. A browser provides APIs such as the DOM, window, and localStorage, while Node.js provides APIs such as the file system, HTTP, and process APIs. So, we mainly use the browser for client-side applications and Node.js for server-side applications.

## Q02. Explain the purpose of the JavaScript engine (V8) in Node.js.

V8 is the JavaScript engine used by Node.js to execute JavaScript code. It is developed by Google and is also used in Google Chrome. When we run a Node.js application, V8 takes our JavaScript code and executes it. Node.js also provides additional APIs for things like file systems, HTTP, and networking. So, V8 is responsible for executing JavaScript, while Node.js provides the runtime environment and additional features needed for server-side development.

## Q03. Why is Node.js considered single-threaded, and how does the event loop handle async operations?

Node.js is considered single-threaded because JavaScript code is executed on a single main thread. However, Node.js can still handle many asynchronous operations without blocking this thread.

When we start an asynchronous operation, such as a timer or an I/O operation, Node.js does not wait for it to finish on the main thread. The operation is handled by the operating system or by libuv, depending on the type of operation. When the operation is completed, its callback is placed in the appropriate queue. The event loop checks these queues and moves ready callbacks to the main thread for execution.

This is how Node.js can handle many concurrent operations while keeping JavaScript execution single-threaded and non-blocking.

## Q04. What is the difference between browser event loop and node.js event loop?

Browser event loop = JavaScript + Web APIs + DOM + Rendering
Node.js event loop = JavaScript + Node.js APIs + libuv + Server-side I/O

The basic purpose of the browser event loop and the Node.js event loop is the same. Both allow JavaScript to handle asynchronous operations without blocking the main thread. However, they work in different runtime environments.

The browser event loop works with Web APIs, the DOM, and the browser's rendering system. Node.js does not have a DOM or rendering system. Instead, it uses Node.js APIs and libuv to handle server-side operations such as file system and network I/O. Node.js also has specific event loop phases and provides process.nextTick(), which is not available in the browser.

So, the main difference is not the basic idea of the event loop, but the runtime environment, APIs, and scheduling mechanisms around it.

## Q05. Explain node.js event-loop phases.

The Node.js event loop is divided into several phases, and each phase handles a specific type of callback. The main phases are Timers, Pending Callbacks, Poll, Check, and Close Callbacks.

The Timers phase handles callbacks from setTimeout() and setInterval(). The Pending Callbacks phase handles some deferred I/O callbacks. The Poll phase handles I/O events and waits for new I/O when necessary. The Check phase handles setImmediate() callbacks. Finally, the Close Callbacks phase handles callbacks related to closing resources such as sockets.

The event loop continuously moves through these phases and repeats the cycle.

## Q06. Explain the role of libuv in Node.js.

Node.js
├── V8
│ └── JavaScript execute করে
│
├── libuv
│ ├── Event loop
│ ├── Async I/O
│ └── Thread pool
│
└── Node.js APIs
├── fs
├── http
├── process
└── etc.

libuv is a C library that provides the core infrastructure for asynchronous I/O in Node.js. It provides the event loop and helps Node.js handle operations such as file system and network I/O without blocking the main JavaScript thread.

libuv also provides a thread pool for certain operations that cannot be handled asynchronously by the operating system. When an asynchronous operation is completed, its callback can be processed by the Node.js event loop.

So, V8 is mainly responsible for executing JavaScript, while libuv is an important part of Node.js's non-blocking and asynchronous system.

## Q07. How do you create a simple web server using the built-in HTTP module?

We can create a simple web server in Node.js using the built-in http module, so we do not need to install any additional package. We use http.createServer() to create the server, which receives a request and response object. We can use the request object to check information such as the URL and HTTP method, and we use the response object to send a response to the client. Finally, we use server.listen() to make the server listen on a specific port.

## Q08. What's the difference between blocking and non-blocking code execution?

Blocking code means that the current execution has to wait until an operation is completed before it can continue. For example, a synchronous file operation can block the JavaScript thread while the file is being read.

Non-blocking code does not wait for a slow operation to finish. Instead, Node.js can start the operation and continue executing other code. When the operation is completed, its callback or promise can handle the result.

Node.js uses non-blocking I/O so that a slow operation, such as file or network I/O, does not block the main JavaScript thread. This allows Node.js to handle many concurrent requests efficiently.

## Q09. How do you use the require() function to import a node module?

In Node.js, we can use the require() function to import modules that use the CommonJS module system. For example, if a file exports a function using module.exports, we can load that function in another file using require(). We can also use require() to import built-in Node.js modules such as fs and http, or installed packages such as Express.

## Q10. What is Node Package Manager (NPM), and how do you use it to manage packages?

NPM stands for Node Package Manager. It is the package manager commonly used with Node.js to install and manage packages and their dependencies. We can use NPM to install, update, remove, and manage packages in a project.

For example, we can run npm install express to install Express. NPM adds the package to the project dependencies and stores the installed packages in the node_modules directory. The package information is also recorded in package.json, while package-lock.json keeps track of the exact dependency versions.

## Q11. Differentiate between local and global package installation using the command line interface.

A local installation installs a package only for the current project. The package is stored inside the project's node_modules folder and is usually listed in package.json. For example, we install Express locally because it is a dependency of the application.

A global installation installs a package at the system level using the -g flag. Global packages can be used from the command line anywhere on the machine. They are commonly used for CLI tools such as Nodemon or PM2.

In general, application dependencies are installed locally, while command-line tools are often installed globally.

## Q12. Explain the purpose of the package.json file.

The package.json file is the main configuration file of a Node.js project. It contains information about the project, its dependencies, development dependencies, and scripts.

For example, when we install Express, it can be added to the dependencies in package.json. We can also define scripts such as start or dev to run common commands.

Another important purpose is dependency management. When we share a project with another developer, they can run npm install, and NPM uses the package.json file to install the required dependencies.

## Q13. How do you handle error handling in asynchronous code with a callback function?

In callback-based asynchronous code, Node.js commonly uses the error-first callback pattern. The callback receives the error as the first argument and the result as the second argument.

We first check whether the error exists. If there is an error, we handle it and return from the callback. If there is no error, we continue working with the result.

For example, with fs.readFile(), we can check the err argument first and handle the file reading error before using the returned data.

## Q14. What are Promises, and what problem do they solve with asynchronous code?

A Promise is a JavaScript object that represents the eventual result of an asynchronous operation. It can be in a pending, fulfilled, or rejected state.

Promises help solve some problems with callback-based asynchronous code, especially deeply nested callbacks, which can make code difficult to read and maintain. Promises allow us to chain asynchronous operations using .then() and handle errors using .catch(). They also provide the foundation for async/await, which makes asynchronous code easier to read and write.

## Q15. Explain async/await and how it improves readability for async function calls.

Async and await are JavaScript features used to work with Promises in a cleaner and more readable way. An async function always returns a Promise, and await allows us to wait for a Promise to settle before continuing the execution of that async function.

The main benefit is readability. Instead of using multiple .then() calls or nested callbacks, we can write asynchronous operations in a sequential-looking way. We can also use a normal try...catch block to handle errors.

Importantly, await does not block the entire Node.js process. It only pauses the execution of the current async function while the Promise is being settled.

## Q16. How do you use the fs module for FS operations?

The fs module stands for File System, and it is a built-in Node.js module used to work with files and directories. We can use it to read, write, append, rename, and delete files, as well as create and manage directories.

For example, we can use fs.readFile() to read a file asynchronously and handle the result in a callback. The fs module provides both synchronous and asynchronous APIs. In server applications, asynchronous APIs are generally preferred because synchronous operations can block the JavaScript execution.

## Q17. Explain the difference between synchronous and asynchronous file system operations.

The main difference is that synchronous file system operations block the execution until the operation is completed, while asynchronous file system operations allow Node.js to continue executing other code while the operation is in progress.

For example, fs.readFileSync() is synchronous, so the code waits until the file is completely read. On the other hand, fs.readFile() is asynchronous, so Node.js can continue executing other code and handle the file result later through a callback or Promise.

For server applications, asynchronous file operations are generally preferred because they avoid blocking the main JavaScript execution.

## Q23. What are callbacks in Node.js?

A callback is a function. We pass it as an argument to another function. The other function can call the callback later.

Node.js uses callbacks for asynchronous operations. For example, we can use them when reading a file. We can also use them for network operations.

In the traditional Node.js pattern, the first argument is usually an error. The second argument contains the result.

A callback is not always asynchronous. We can also use callbacks in synchronous code.

## Q24. What is callback hell and how can it be avoided?

Callback Hell happens when we have many nested callbacks. It usually happens when we have several asynchronous operations.

The code becomes difficult to read and maintain. Error handling can also become difficult.

We can avoid Callback Hell by using named functions. We can also use Promises. In modern JavaScript, we often use async/await. It makes the code easier to read and follow.

## Q25. What are Promises and how are they used in Node.js?

A Promise is an object. It represents the future result of an asynchronous operation.

A Promise has three states. They are pending, fulfilled, and rejected. It is pending while the operation is running. It becomes fulfilled when the operation succeeds. It becomes rejected when the operation fails.

In Node.js, we can handle a Promise with `.then()` and `.catch()`. We use `.then()` for a successful result. We use `.catch()` for errors.

We can also use async/await with Promises. It makes asynchronous code easier to read.

## Q26. How does async/await work in Node.js?

Async/await is a simple way to work with Promises. An async function always returns a Promise. The await keyword waits for a Promise to complete.

When we use await, the execution of that async function pauses at that point. It does not block the whole Node.js process. Node.js can handle other work during this time. When the Promise is completed, the function continues.

We usually use try/catch to handle errors with async/await.

## Q27. What is the difference between synchronous and asynchronous methods in the fs module?

Synchronous methods block the execution until the operation is finished. For example, `readFileSync()` waits until the file is completely read.

Asynchronous methods do not block the execution. For example, `readFile()` starts reading the file. Node.js can handle other work during this time. We get the result through a callback or a Promise.

In server applications, we usually prefer asynchronous methods. They allow other work to continue.

## Q28. What is process.nextTick()?

`process.nextTick()` is a Node.js function. It takes a callback. Node.js runs this callback after the current operation finishes.

The callback usually runs before the Event Loop moves to the next phase. So, it is not the same as `setTimeout(..., 0)`.

Using too many `process.nextTick()` callbacks can delay other work in the Event Loop.

## Q29. What is the difference between process.nextTick(), setImmediate(), and setTimeout()?

`process.nextTick()` runs a callback after the current operation finishes. It uses the nextTick queue.

`setTimeout()` schedules a timer. Its callback runs in the timers phase. A delay of zero does not mean immediate execution.

`setImmediate()` runs a callback in the check phase of the Event Loop.

`process.nextTick()` usually runs first. The order between `setTimeout()` and `setImmediate()` can depend on the context. Inside an I/O callback, `setImmediate()` usually runs before `setTimeout(..., 0)`.

## Q30. What are the phases of the Node.js event loop?

## 🎯 Express.js Fundamentals

## Q43. What is Express.js and how does it relate to Node.js?

Express.js is a web framework for Node.js. It is mainly used to build web servers and REST APIs.

Node.js provides the runtime environment for running JavaScript on the server. Express.js runs on top of Node.js and makes server-side development easier.

Express provides features like routing, middleware, request handling, and response handling. It also makes it easier to organize and manage server code.

We can build a server using Node.js without Express. However, Express provides many useful features that reduce the amount of code we need to write.

So, Node.js is the runtime, and Express.js is a web framework built on top of Node.js.
