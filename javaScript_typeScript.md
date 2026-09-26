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
