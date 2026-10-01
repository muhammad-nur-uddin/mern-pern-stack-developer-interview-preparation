## 🎯 JavaScript Fundamentals & Execution

## Q01. What are the data types present in JavaScript?

JavaScript has two main categories of data types: primitive and non-primitive.

There are seven primitive data types: String, Number, BigInt, Boolean, Undefined, Null, and Symbol.

The main non-primitive type is Object. Arrays, functions, dates, maps, and sets are part of the object category.

Primitive types represent single values. Objects are used to represent more complex data and collections.

## Q02. What is the difference between null and undefined?

null and undefined both represent the absence of a value, but they have different meanings.

undefined usually means that a variable or property has not been assigned a value yet. For example, if I declare let username;, its value is undefined.

null is an explicit value that a developer assigns when they want to represent the absence of a value.

There is also a difference with the typeof operator. typeof undefined returns "undefined", while typeof null returns "object". This is a historical behavior of JavaScript.

## Q03. How does JavaScript handle type coercion?

Type coercion is the process of converting a value from one data type to another when JavaScript needs it.

It can happen in two ways. Implicit coercion happens automatically. For example, "5" + 2 returns "52" because JavaScript converts 2 to a string. But "5" - 2 returns 3 because JavaScript converts "5" to a number.

Explicit coercion happens when we convert the type ourselves. For example, we can use Number("5"), String(5), or Boolean(1).

The == operator can perform type coercion during comparison. The === operator does not perform type coercion. It compares both the value and the type.

## Q04. What is the difference between == and ===?

== and === are both used to compare equality, but they handle types differently.

== is called loose equality. It can perform type coercion before comparing the values. For example, 5 == "5" returns true because the string can be converted to a number.

=== is called strict equality. It does not perform type coercion. It compares both the value and the type. So 5 === "5" returns false because one value is a Number and the other is a String.

In general, === is preferred when we want predictable comparisons.

## Q05. Explain hoisting in JavaScript for var, let, const, and function declarations.

Hoisting is a JavaScript behavior where bindings for declarations are created before the code in that scope starts executing.

With var, the variable is hoisted and initialized with undefined. So we can access it before the declaration, and the result is undefined.

let and const are also hoisted in the sense that their bindings are created early. But they are not initialized before their declaration is reached. This period is called the Temporal Dead Zone, or TDZ. Accessing them during this period causes a ReferenceError.

Function declarations are fully hoisted. So we can call a function before its declaration in the code.

## Q06. What is the Temporal Dead Zone (TDZ)?

The Temporal Dead Zone, or TDZ, is the period when a let or const variable exists in its scope but has not been initialized yet.

If we try to access the variable during this period, JavaScript throws a ReferenceError.

For example, if console.log(name) appears before let name = "Nur", accessing name causes a ReferenceError. The TDZ ends when the declaration is executed and the variable is initialized.

## Q07. What is the difference between an undeclared variable and a variable with the value undefined?

The main difference is whether the variable has a binding.

If a variable is declared but no value is assigned, its value is undefined. For example, let name; creates a variable whose value is undefined.

An undeclared variable has no declaration or binding. If we try to access it directly, JavaScript throws a ReferenceError.

There is one special case with the typeof operator. typeof returns "undefined" for an undeclared identifier instead of throwing an error. But direct access still causes a ReferenceError.

## Q08. What is lexical scoping in JavaScript?

Lexical scoping is a scope rule in JavaScript. It determines where a variable can be accessed.

It depends on where the code is written. If a function cannot find a variable in its own scope, JavaScript looks in its outer lexical scope. It continues this process through the outer scopes.

The place where a function is called does not change its lexical scope. The place where the function is defined determines its lexical scope.

## Q09. What is the difference between var, let, and const?

var, let, and const are used to declare variables in JavaScript. They have different rules for scope, reassignment, redeclaration, and hoisting.

var is function-scoped. It can be redeclared in the same scope. It can also be reassigned. Its declaration is hoisted and initialized with undefined.

let is block-scoped. It can be reassigned, but it cannot be redeclared in the same scope. It is also in the Temporal Dead Zone before its declaration is reached.

const is block-scoped as well. It cannot be reassigned or redeclared. It must be initialized when it is declared. It also has a Temporal Dead Zone.

In modern JavaScript, we usually use let when the value needs to change. We use const when the variable should not be reassigned.

## Q10. What is an execution context in JavaScript?

An Execution Context is an environment where JavaScript code is executed.

When JavaScript runs code, it creates an execution context. It provides the environment needed to manage variables, functions, scope, outer scope, and the this value.

The main types are the Global Execution Context and the Function Execution Context. The Global Execution Context is created when the program starts. A new Function Execution Context is created whenever a function is called.

These execution contexts are managed through the Call Stack. When a function finishes, its execution context is removed from the stack.

## Q11. What is scope in JavaScript?

Scope is a boundary in JavaScript. It determines where a variable or identifier can be accessed.

JavaScript mainly has global scope, function scope, and block scope.

A variable in the global scope can be accessed from its accessible inner scopes. A variable declared inside a function is normally available only inside that function. let and const are block-scoped. They are available only inside their block.

If JavaScript cannot find a variable in the current scope, it looks in the outer scope. It continues this process through the outer scopes. This is called the scope chain.

## What is the difference between scope and lexical scope?

Scope is a boundary. It determines where a variable can be accessed.

Lexical scope is a rule for determining that scope. In JavaScript, the scope depends on where the code is written. For functions, it depends on where the function is defined.

So, scope tells us where a variable is accessible. Lexical scoping tells us how that scope is determined.

Function Scope vs Block Scope

Function scope means that a variable is accessible within a function. var is function-scoped.

Block scope means that a variable is accessible only inside a block. A block is usually created with { }. let and const are block-scoped.

So, a var variable declared inside an if block can be accessed outside that block. A let or const variable cannot be accessed outside the block.

## Q12. What is a closure in JavaScript? Give an example.

A closure is a function that can access variables from its outer lexical scope.

The outer function can finish its execution.
The inner function can still access those variables.

For example:
function outer() {
let count = 0;

return function () {
count++;
return count;
};
}

const counter = outer();

console.log(counter()); // 1
console.log(counter()); // 2

Here, counter is a closure.
It remembers the count variable from outer.
So, count is still accessible after outer finishes its execution.

## Q13. What is the difference between a function declaration and a function expression?

A function declaration and a function expression are two ways to create a function.

In a function declaration, we directly declare a function with the function keyword.

function greet() {
console.log("Hello");
}

In a function expression, we create a function and assign it to a variable.

const greet = function () {
console.log("Hello");
};

One important difference is hoisting. A function declaration can be called before its declaration. A function expression cannot normally be called before its initialization. With let or const, this causes a ReferenceError because of the Temporal Dead Zone.

## Q14. What are arrow functions and how do they differ from regular functions?

An arrow function is a shorter way to write a function in JavaScript. It uses the => syntax.

The main difference is the this behavior. A regular function can have its own this based on how it is called. An arrow function does not have its own this. It uses this from its outer lexical scope.

Arrow functions also do not have their own arguments object. They cannot be used as constructors with new. They also do not have a prototype property.

Arrow functions are commonly used for callbacks because they have a shorter and cleaner syntax.

## Q15. What is a higher-order function?

A Higher-Order Function is a function that works with other functions. It can take another function as an argument. It can also return a function. JavaScript supports this because functions are first-class values. This means we can store functions in variables, pass them as arguments, and return them from other functions. Common examples include map(), filter(), and reduce().

## What is a First-Class Value?

A first-class value is a value that can be used like other ordinary values in a programming language. In JavaScript, functions are first-class values. We can store them in variables, pass them as arguments, and return them from other functions.

## What is a First-Class Function?

A first-class function is a function that can be treated like a regular value. It can be stored in a variable. It can be passed as an argument. It can also be returned from another function.

## Q16. Can functions be assigned to variables in JavaScript?

Yes, functions can be assigned to variables in JavaScript. Functions are first-class values in JavaScript. We can store a function in a variable and call it later using that variable. This capability is also important for concepts like callbacks, Higher-Order Functions, and closures.

## Q17. What is an IIFE (Immediately Invoked Function Expression)?

IIFE stands for Immediately Invoked Function Expression. It is a function expression that runs immediately after it is created. We use () at the end to invoke the function immediately. IIFEs were commonly used to create a private scope and prevent variables from being accessed outside the function. Their use is less common in modern JavaScript because we have block scope and ES Modules.

## Q18. How can you create private variables in JavaScript?

There are several ways to create private variables in JavaScript. A traditional approach is to use closures. We keep the variable inside an outer function and return inner functions that can access it. We can also use IIFEs to create a private scope. In modern JavaScript, we can use # for private class fields. Private variables are mainly used for encapsulation. They prevent internal data from being accessed or modified directly from outside.

## Q19. What is currying and why is it useful?

Currying is a technique where a function that takes multiple parameters is transformed into a series of functions. Each function takes one parameter and returns another function. The final function returns the result after receiving all parameters. Currying is useful for function reuse and partial application. It is also closely related to closures.

## Q20. What is function composition?

Function Composition is a technique of combining multiple functions to create a new function. The output of one function becomes the input of another function. For example, we can use trim() to remove extra spaces from a string. We can then use toLowerCase() to convert the result to lowercase. This allows us to combine small and reusable functions to perform a complete task. It also makes the code easier to maintain and test.
