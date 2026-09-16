<h1 align="center">JavaScript Interview Questions</h1>

## 🎯 JavaScript Fundamentals

## Q01. What are the data types present in JavaScript?

JavaScript has 8 data types. Seven of them are primitive data types, and one is a non-primitive data type.

The seven primitive data types are String, Number, BigInt, Boolean, Undefined, Null, and Symbol.

The non-primitive data type is Object. Arrays and Functions are also considered objects in JavaScript.

For example, String is used for text, Number is used for numeric values, Boolean stores true or false, and Object can store multiple related values.

## Q02. What is the difference between null and undefined?

undefined and null both represent the absence of a value, but they have different meanings.

undefined usually means that a variable has been declared but no value has been assigned to it yet.

On the other hand, null is an intentional empty value. It means that the developer has explicitly set the value to null to show that there is currently no value.

For example, if we write let user;, the value of user is undefined. If we write let user = null;, the value is null.

One more important point is that typeof null returns "object". This is an old behavior in JavaScript, and null itself is not actually an object.

## Q03. How does JavaScript handle type coercion?

JavaScript handles type coercion by converting a value from one data type to another when it is needed.

There are two types of coercion. The first one is implicit coercion, where JavaScript automatically converts the type. For example, when we write "10" + 5, JavaScript converts the number 5 into a string, so the result is "105".

The second one is explicit coercion, where we convert the type ourselves. For example, Number("10") converts the string "10" into the number 10.

The == operator can also perform type coercion during comparison, while the === operator does not perform type coercion. It checks both the value and the type.

## Q04. Explain the concept of hoisting in JavaScript.

Hoisting is a JavaScript behavior where variable and function declarations are processed before the code is executed.

For example, a variable declared with var can be accessed before its declaration, and it returns undefined because the var declaration is hoisted and initialized with undefined.

let and const are also hoisted, but they stay in the Temporal Dead Zone until the code reaches their declaration. If we access them before that point, JavaScript throws a ReferenceError.

Function declarations are also hoisted, so we can call a function before its declaration in the code.

## Q05. What is the scope in JavaScript?

Scope defines where a variable can be accessed in JavaScript.

JavaScript mainly has global scope, function scope, and block scope. A variable in the global scope can be accessed from different parts of the code. A variable declared inside a function is normally available only inside that function. Variables declared with `let` and `const` are block-scoped, so they can only be accessed inside the block where they are declared.

If JavaScript cannot find a variable in the current scope, it looks for it in the outer scope. This process is called the scope chain.

## Q06: What is the difference between == and === ?

## Q07. Describe closure in JavaScript. Can you give an example?

## Q08. What is the 'this keyword' and how does its context change?

## Q09. What are arrow functions and how do they differ from regular functions?

## Q10. What are template literals in JavaScript?

## 🎯 JavaScript Functions and Higher-Order Functions

## Q11. What is a higher-order function in JavaScript?

## Q12. Can functions be assigned as values to variables in JavaScript?

## Q13. How do functional programming concepts apply in JavaScript?

## Q14. What are IIFEs (Immediately Invoked Function Expressions)?

## Q15. How do you create private variables in JavaScript?

## 🎯 Asynchronous JavaScript

## Q36. What is the JavaScript event loop?

The JavaScript Event Loop is a mechanism that helps JavaScript handle asynchronous code. JavaScript is single-threaded, so it executes one piece of code at a time on the Call Stack.

When an asynchronous operation starts, JavaScript does not wait for it to finish. The runtime handles that operation, and its callback becomes ready later.

The Event Loop coordinates the Call Stack and the different queues. When the Call Stack is empty, it moves a ready callback from a queue to the Call Stack. JavaScript then executes that callback.

The Microtask Queue is usually processed before the Task Queue. Because of this, a Promise callback usually runs before a `setTimeout()` callback.

## Q37. What is the difference between the call stack, task queue, and microtask queue?

The Call Stack is where JavaScript keeps the functions and code that are currently being executed. It follows the Last In, First Out rule.

The Task Queue stores callbacks from tasks such as `setTimeout()` and DOM events. The Microtask Queue stores callbacks from Promises and `queueMicrotask()`.

When the Call Stack becomes empty, the Event Loop checks the queues. It processes the Microtask Queue before taking a task from the Task Queue. This is why a Promise callback usually runs before a `setTimeout()` callback.

## Q38. Why do Promise callbacks execute before setTimeout() callbacks?

Promise callbacks execute before `setTimeout()` callbacks because they use different queues. Promise callbacks go to the Microtask Queue, while `setTimeout()` callbacks go to the Task Queue.

After the synchronous code finishes, the Call Stack becomes empty. The Event Loop then processes the Microtask Queue before taking a task from the Task Queue.

So, the Promise callback usually runs before the `setTimeout()` callback. This happens because of the Event Loop scheduling rules. It does not mean that Promises are simply faster than timers.

## Q39. How do callbacks work in JavaScript?

A callback is a function that is passed as an argument to another function. The other function can call the callback when it needs to.

Callbacks can be used for both synchronous and asynchronous operations. For example, `forEach()` accepts a callback, and `setTimeout()` also accepts a callback.

In asynchronous operations, the callback can run after the operation is completed. The callback becomes ready and is later moved to the Call Stack based on the Event Loop's scheduling rules.

Callbacks are an important part of asynchronous JavaScript. However, many nested callbacks can make the code difficult to manage. Promises and `async/await` can help reduce this problem.

## Q40. What are Promises and what problem do they solve?

A Promise is an object that represents the future result of an asynchronous operation. A Promise can have three states: Pending, Fulfilled, and Rejected.

It becomes Fulfilled when the operation is successful. It becomes Rejected when the operation fails.

Promises make asynchronous code easier to manage. They help reduce nested callbacks and Callback Hell. We can use `.then()` to handle a successful result and `.catch()` to handle errors.

Promises also allow us to chain multiple asynchronous operations. The `async/await` syntax is also built on Promises.

## Q41. What are the different states of a Promise?

A Promise has three states: Pending, Fulfilled, and Rejected.

When a Promise is created, it starts in the Pending state. It means the asynchronous operation has not finished yet.

If the operation is successful, the Promise becomes Fulfilled. If the operation fails, it becomes Rejected. Fulfilled and Rejected are both called settled states.

Once a Promise is settled, its state cannot change again.

## Q42. How does Promise chaining work?

Promise chaining is a way to handle multiple asynchronous operations using multiple `.then()` methods. Each `.then()` usually returns a new Promise.

If a `.then()` returns a value, the next `.then()` receives that value. If it returns a Promise, the next `.then()` waits for that Promise to settle and receives its result.

This allows us to handle dependent asynchronous operations in a clean and readable way. We can use `.catch()` to handle errors from the chain.

## Q43. What is async/await and how does it work with Promises?

`async/await` is a cleaner way to work with Promises. It is not an alternative to Promises. It works on top of the Promise system.

The `async` keyword makes a function return a Promise. The `await` keyword is used to wait for a Promise result.

When `await` gets a pending Promise, the current async function is paused. It does not block the whole JavaScript runtime. When the Promise settles, the function continues from that point.

`async/await` makes asynchronous code easier to read and write. We usually use `try...catch` to handle errors with `async/await`.

## Q44. What happens if you do not await an async function?

An `async` function always returns a Promise. So, if you call an async function without using `await`, you get the Promise instead of its final value.

For example, `const result = getUser()` gives us a Promise. We can use `await` or `.then()` to get the actual result from that Promise.

The async function can still start executing without `await`. The caller simply does not wait for the Promise to settle. This can be useful when we do not need the result immediately.

## Q45. What is callback hell and how can it be avoided?

Callback Hell is a situation where many dependent callbacks are nested inside each other. This makes the code difficult to read and maintain.

It can also make error handling more difficult. When many callbacks are nested, the code can look like a pyramid. This is also called the Pyramid of Doom.

We can avoid Callback Hell by using Promises. Promise chaining makes the code flatter and easier to read.

We can also use `async/await`. It makes Promise-based asynchronous code easier to write and understand.

## Q46. What is the difference between Promise.all(), Promise.allSettled(), Promise.race(), and Promise.any()?

`Promise.all()` waits for all Promises to fulfill. If any Promise rejects, it rejects immediately. We use it when all asynchronous operations need to succeed.

`Promise.allSettled()` waits for all Promises to finish. It does not reject when one of them fails. It gives us the final status of every Promise.

`Promise.race()` returns the result of the first Promise that settles. The first Promise can be fulfilled or rejected.

`Promise.any()` returns the result of the first Promise that fulfills. It ignores rejected Promises and keeps waiting for a successful one. It rejects only when all Promises reject.

## 🎯 DOM & Event Handling

## Q47. What is the Document Object Model (DOM)?

DOM stands for Document Object Model. It is an object-based representation of an HTML document created by the browser.

When the browser loads an HTML page, it represents the document as a tree structure. The elements and text in the document become nodes in this tree.

JavaScript can use the DOM to access and modify HTML elements. We can change content, attributes, and styles. We can also create or remove elements and add event listeners.

So, the DOM provides a way for JavaScript to interact with the webpage.

## Q48. How do you select DOM elements using JavaScript?

We can select DOM elements using different JavaScript methods. The most common ones are `getElementById()`, `querySelector()`, and `querySelectorAll()`.

`getElementById()` selects an element by its ID. `querySelector()` uses a CSS selector and returns the first matching element. `querySelectorAll()` returns all elements that match the selector.

We can also use `getElementsByClassName()` and `getElementsByTagName()`. These methods select elements by class name and tag name.

## Q49. How do you create, append, and remove DOM elements?

We can create a new DOM element using `document.createElement()`. After creating it, we can set its text, attributes, or other properties.

We can use `append()` or `appendChild()` to add the element to the DOM. To remove an element, we can use the `remove()` method. We can also use `removeChild()` through the parent element.

For example, we can create a new button, add it to a container, and remove it later when it is no longer needed.

## Q50. What is event propagation in the DOM?

Event propagation is the process of an event traveling through the DOM tree. When an event happens on an element, it can travel from the parent elements toward the target during the capturing phase.

When the event reaches the target element, the target phase occurs. After that, the event can travel from the target back to the parent elements during the bubbling phase.

Event propagation is important for understanding event bubbling, event capturing, and event delegation. We can use `event.stopPropagation()` when we need to stop further event propagation.
