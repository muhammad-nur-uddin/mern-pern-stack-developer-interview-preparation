## 🎯 React Fundamentals

## Q01. What is React, and why is it used?

React is a JavaScript library. It is used for building user interfaces.

React uses a component-based approach. We can divide the UI into small and reusable components. Each component can have its own logic and state.

React also follows a declarative and state-driven approach. We describe what the UI should look like for a particular state. When the state changes, React re-renders the component. It then updates the UI based on the new state.

React makes complex and interactive UIs easier to build. Component reusability also helps keep large applications organized and maintainable.

## Q02. What is a React component, and how do you create one?

A React component is an independent and reusable part of the user interface.

We can divide a large UI into smaller components. Each component can have its own logic and UI.

The common way to create a component is to use a function. The function returns JSX. The component name usually starts with a capital letter.

For example:

```jsx
function Welcome() {
  return <h1>Hello, Nur!</h1>;
}
```

We can use this component with `<Welcome />`. Components can also receive data through props. They can also manage their own state.

## Q03. What is JSX, and how does it work?

JSX is a syntax extension for JavaScript. It allows us to write HTML-like syntax inside JavaScript. React uses JSX to describe what the UI should look like.

JSX looks like HTML, but it is not HTML. The browser cannot understand JSX directly. JSX is transformed into JavaScript during the build process. React then uses that JavaScript to create and update the UI.

We can also write JavaScript expressions inside JSX. We use curly braces for this. For example, we can write `{name}` to display a JavaScript variable.

Modern React projects can use tools like Babel or SWC to transform JSX. The exact tool depends on the project setup.

## Q04. What is the difference between a functional component and a class component?

Functional components and class components are two ways to create React components.

A functional component is a JavaScript function. It returns JSX. It can use Hooks for state and other React features. For example, it can use `useState` and `useEffect`.

A class component is a JavaScript class. It extends `React.Component`. It usually uses the `render()` method to return JSX. It uses `this.state` for state. It uses `this.setState()` to update the state. It can also use lifecycle methods like `componentDidMount()`.

Functional components are more common in modern React. Class components are mainly found in older React codebases.

## Q05. What is the Virtual DOM, and why does React use it?

The Virtual DOM is a lightweight, in-memory representation of the UI. React uses it to manage UI changes.

When the state or props change, React creates a new UI representation. It compares the new representation with the previous one. This process is called reconciliation.

React then determines which DOM changes are needed. It applies those changes to the real DOM.

The main purpose of the Virtual DOM is to help React manage UI updates efficiently. The Virtual DOM is not simply a faster version of the real DOM. It is an abstraction used in React's update process.
## Q06. How does React update the UI when state or props change?
When state or props change, the related React component renders again. React creates a new UI result from the updated state or props.

React then compares the new result with the previous result. This process is called reconciliation. React determines which UI changes are needed.

React then applies the necessary changes to the real DOM. A re-render does not mean that the entire DOM is updated.

For example, if a counter changes from `0` to `1`, React creates the new UI result. It compares it with the previous result. It then updates the part of the DOM that needs to change.

## 🎯 Rendering, Reconciliation and Fiber

## Q21. What is reconciliation in React?

Reconciliation is the process React uses to compare the previous UI tree with the new UI tree and determine what has changed.

After finding the necessary changes, React applies those changes to the actual DOM. This means React does not need to recreate the whole DOM when only a small part of the UI changes.

For example, if only the text of a paragraph changes, React can update that part without recreating the other elements.

## Q22. How does reconciliation decide when and what to render?

Reconciliation does not decide when a component should render. Usually, a state, prop, context, or another update causes React to render the component again.

After rendering, React creates a new UI tree and compares it with the previous tree. It uses things such as element types, props, and keys for lists to determine which elements can be reused and what needs to change.

Then, during the commit phase, React applies the necessary changes to the actual DOM. So, a component re-rendering and the actual DOM being updated are not exactly the same thing.

## Q23. What is the difference between a React render and a DOM update?

A React render and a DOM update are not the same thing.

A React render means that the component runs again and produces a new React element tree. A DOM update happens after React compares the new tree with the previous tree and determines what actually needs to change in the browser DOM.

So, a component can re-render without causing a DOM update. React uses reconciliation to find the necessary changes and then applies only those changes to the DOM.

## Q24. What causes a React component to re-render?

A React component can re-render for several reasons. The most common reason is a change in its state. It can also re-render when it receives new props, when its parent re-renders, or when a consumed Context value changes.

A component can also re-render when relevant data in an external store that it subscribes to changes.

However, a re-render does not always mean a DOM update. React creates the new UI result and uses reconciliation to determine whether the actual DOM needs to change.

## Q25. How do you find the cause of an unnecessary re-render?

To find the cause of an unnecessary re-render, I would first use React DevTools Profiler to identify which component is rendering and when it is rendering.

Then I would check whether its state or props are changing, whether the parent is re-rendering, whether a Context value is changing, and whether new object or function references are being created.

After finding the actual cause, I would apply an appropriate optimization such as React.memo, useMemo, or useCallback when needed. I would measure the result again after the optimization.

## Q26. How can you prevent unnecessary re-renders in React?

To prevent unnecessary re-renders, I would first identify what is causing the re-render. Then, depending on the situation, I can use React.memo to skip rendering a child when its props have not changed.

I can use useMemo to cache an expensive calculation and useCallback to keep a function reference stable. Keeping state close to where it is needed and avoiding unnecessary object or function creation can also help.

I would not use these optimizations everywhere. I would first identify a real performance problem and then apply the appropriate optimization.

## Q27. What is React Fiber?

React Fiber is React's internal reconciliation architecture. It allows React to break rendering work into smaller units and gives React more control over how that work is processed.

React can pause, resume, or prioritize work when needed. This helps React handle complex UI updates in a more flexible way and keep the user interface responsive.

Fiber is not a public React API or a component. It is an internal architecture used by React for rendering and reconciliation.

## Q28. How does Fiber improve React's rendering process?

Fiber improves React's rendering process by allowing React to break rendering work into smaller units.

This gives React more control over the work. It can pause and resume work when needed and manage the priority of different updates. This helps React handle higher-priority work first and keep the user interface more responsive during complex updates.

Fiber is not simply a way to make every render faster. It provides the architecture that allows React to schedule and manage rendering work more effectively.

## Q29. What is the difference between the render phase and commit phase?

React updates the UI in two main phases: the Render Phase and the Commit Phase.

During the Render Phase, React executes the component, creates a new React tree, and compares it with the previous tree to determine what has changed. It does not update the actual DOM in this phase.

During the Commit Phase, React applies the necessary changes to the browser DOM, updates refs, and runs effects. The Render Phase is the calculation phase, while the Commit Phase is the DOM update phase.

## Q30. What happens when a component's state changes from the moment setState is called until the UI is updated?

When we call a state setter such as setState, React does not immediately update the DOM. It schedules the state update.

React then renders the component and creates a new React tree. It compares the new tree with the previous tree during reconciliation to determine what needs to change.

Finally, during the commit phase, React applies the necessary changes to the actual DOM, and the browser displays the updated UI.

So the general flow is: state update, scheduling, render, reconciliation, commit, and browser UI update.

## 🎯 Hooks

## Q31. What are React Hooks, and why were they introduced?

React Hooks are special functions that allow functional components to use state and other React features.

They were introduced to make it easier to use stateful logic in functional components and to reuse that logic between components. Hooks also make it easier to organize related logic without relying on class components or more complex patterns.

For example, useState allows a functional component to have state, and custom Hooks allow us to reuse stateful logic.

## Q32. What are the Rules of Hooks?

There are two main Rules of Hooks in React.

First, Hooks must be called at the top level of a component or a custom Hook. We should not call Hooks inside conditions, loops, or nested functions because React relies on the same Hook call order across renders.

Second, Hooks should only be called from React function components or custom Hooks. We should not call Hooks from regular JavaScript functions.

## Q33. How does useEffect work?

useEffect is a React Hook used to handle side effects and synchronize a component with external systems after rendering.

It can be used for things like API requests, event listeners, timers, and subscriptions. The dependency array tells React when the effect should run again.

An effect can also return a cleanup function. The cleanup is used to remove subscriptions, clear timers, or clean up other resources when the effect needs to be replaced or the component is unmounted.

## 🎯 React Performance Optimization

## Q41. What is React.memo, and when should you use it?

React.memo is a performance optimization that can help prevent unnecessary re-renders of a functional component.

When a parent re-renders, a child can also re-render. React.memo compares the child's previous and new props. If the props are the same, React can skip rendering the child.

One important point is that React.memo uses shallow comparison by default. This can cause a problem with object props. For example:

```jsx
<Child user={{ name: "Rahim" }} />
```

A new object is created every time the parent renders. Even though the object has the same data, its reference is different, so React can consider the prop changed.

If necessary, we can keep the object reference stable with useMemo:

```jsx
const user = useMemo(() => {
  return { name: "Rahim" };
}, []);
```

I would use React.memo when a component renders frequently, its props usually stay the same, and profiling shows that the re-renders are unnecessary. I would not use it for every component because memoization also has a cost.

React.memo also does not prevent every possible re-render. For example, changes to the component's own state or consumed Context can still cause it to re-render.

## Q42. What is the difference between useMemo and useCallback?

Both useMemo and useCallback are used for performance optimization, but they cache different things.

useMemo caches the result of a calculation. If its dependencies do not change, React can reuse the cached value.

useCallback caches a function reference. If its dependencies do not change, React can reuse the same function reference.

In simple terms, useMemo remembers a value, while useCallback remembers a function reference.

## Q43. When can useMemo and useCallback actually make performance worse?

useMemo and useCallback do not always improve performance. They also have some overhead because React needs to track dependencies and maintain the cached value or function reference.

If a calculation is very simple, or there is no real need to keep a function reference stable, using these Hooks may not provide a meaningful benefit. Also, if the dependencies change frequently, the benefit of memoization can be very small.

So, I would not use useMemo or useCallback everywhere. I would first measure the performance problem and then use them when they provide a real benefit.

## Q44. How do you optimize list rendering in React?

To optimize list rendering in React, I first use stable and unique keys for list items. This helps React identify which items have changed.

If list items re-render unnecessarily, I can use `React.memo` to skip some unnecessary renders. For very large lists, I can use list virtualization so that only the visible items are rendered.

I prefer to measure the performance problem first and then apply the needed optimization.

## Q45. Why are keys required when rendering a list with .map()?

Keys are required because React uses them to identify each item in a list.

When the list changes, the key helps React understand which item was added, changed, removed, or moved.

We should usually use a stable and unique ID as the key. Using the array index can cause problems when the list is reordered or items are removed.

## Q46. What happens if you use an array index as a React key?

Using the array index as a key is usually fine for a static list. But it can cause problems when items are added, removed, or reordered.

The index can change, so React may not correctly track the identity of each item. This can cause component state or DOM behavior to be associated with the wrong item.

So, for dynamic lists, I prefer to use a stable and unique ID.

## Q47. How would you optimize a component that renders a very large dataset?

For a very large dataset, I would avoid rendering all the data at once.

I can use pagination or server-side pagination to load smaller amounts of data. If many items need to be displayed, I can use virtualization so that only the visible items are rendered.

I can also reduce unnecessary re-renders using `React.memo` and, when needed, `useMemo` or `useCallback`. I would first identify the performance bottleneck before optimizing.

## Q48. How would you find and fix a component that is rendering slowly even though it displays only a small amount of data?

First, I would use the React DevTools Profiler to find why the component is slow and how often it renders.

Then I would check for unnecessary re-renders, expensive calculations, unstable object or function props, and slow child components.

Based on the problem, I may use `React.memo`, `useMemo`, or `useCallback`. After the fix, I would profile the component again to check the improvement.

## Q49. How would you optimize a heavy chart or data visualization in React?

To optimize a heavy chart or data visualization, I would first use the React DevTools Profiler to find the main performance bottleneck.

If the chart is re-rendering unnecessarily, I can use `React.memo` and keep its props stable. If creating the chart data requires an expensive calculation, I can use `useMemo` to avoid repeating that calculation when the data has not changed.

If the chart has too many data points, I can use aggregation or downsampling to reduce the number of points. For very complex visualizations, I can also consider Canvas-based rendering.

For real-time charts, I can batch or throttle updates so the chart does not re-render for every small data update.

The main idea is to profile first, find the actual problem, and then apply the right optimization.

## Q50. How would you diagnose and fix a React application that suddenly becomes slow after adding a new feature?

If a React application becomes slow after adding a new feature, I would first check whether the new feature is causing the performance problem.

Then I would use the React DevTools Profiler to find which components are rendering too often or taking too much time to render. I would check the new state updates, `useEffect` dependencies, expensive calculations, large lists, and unnecessary re-renders.

Based on the problem, I might use `React.memo`, `useMemo`, virtualization, or data optimization. After making the fix, I would profile the application again to verify the improvement.

I would measure the problem first instead of blindly adding performance optimizations.

## 🎯 Forms and User Input

## Q51. How do you handle forms in React?

In React, I usually handle forms using controlled components. I keep the input values in React state and update the state using the `onChange` event.

For form submission, I use the `onSubmit` event and call `event.preventDefault()` to stop the browser's default form submission. Then I validate the input and send the data to the API if needed.

For multiple inputs, I can use separate state variables or one form object. For larger forms, I can use a form library such as React Hook Form.

## Q52. What are controlled and uncontrolled components?

A controlled component is a form input whose value is controlled by React state. We usually use `value` and `onChange` for this. The React state is the source of truth.

An uncontrolled component is not continuously controlled by React state. The DOM keeps the input value, and we can access it using a ref when needed.

Controlled components are more common in React forms because they make form state and validation easier to manage.

## Q53. When should you use a controlled component versus an uncontrolled component?

I would use a controlled component when I need real-time control over the input value. For example, I may need real-time validation, live filtering, or UI updates based on the input.

I would use an uncontrolled component when the form is simple and I only need the input values when the user submits the form. In that case, I can use a ref to read the value from the DOM.

Controlled components are more common for business forms, but both approaches are valid depending on the use case.

## Q54. How do you validate form input in React?

In React, I validate form inputs by defining validation rules such as required fields, email format, minimum password length, and valid numbers.

For simple forms, I can validate the input on submit or while the user is typing. I can also use built-in HTML validation such as `required` and `type="email"`.

For complex forms, I can use tools like React Hook Form or Zod. I also keep server-side validation because client-side validation can be bypassed.

## Q55. How do you handle form submission and prevent the default browser behavior?

In React, I usually handle form submission using the `onSubmit` event on the form.

Inside the submit handler, I use `event.preventDefault()` to stop the browser's default form submission behavior, such as page reload or navigation.

Then I validate the form data and send an API request if needed. I prefer `onSubmit` instead of handling only the button click because the form can also be submitted by pressing Enter.

## Q56. After submitting a form, the form fields reset unexpectedly. Why does this happen, and how can you solve it?

A common reason is the browser's default form submission behavior. If I do not call `event.preventDefault()`, the browser may reload or navigate the page. The React component then starts again with its initial state, so the form fields are reset.

I can solve this by using `event.preventDefault()` and handling the form submission in React. I would also check whether the form state is being reset or whether the component is being remounted because its `key` has changed.

## Q57. How do you securely handle user input in a React application?

I never treat user input as trusted data.

I use client-side validation to check the input format and basic rules. I normally render user input as text and avoid rendering untrusted input as raw HTML because it can create XSS vulnerabilities.

If the application needs to support user-provided HTML, I use proper sanitization. I also validate the input again on the server because client-side validation can be bypassed.

So, I validate the input, render it safely, and validate it again on the server.

## 🎯 React Patterns and Advanced Concepts

## Q58. What are custom Hooks, and when should you create one?

A custom Hook is a reusable function created by the developer. Its name usually starts with `use`, and it can use other React Hooks inside it.

I create a custom Hook when the same stateful logic is needed in multiple components. For example, I can use one for data fetching, form logic, online status, or event subscriptions.

Custom Hooks help avoid repeating the same logic and keep reusable logic separate from the UI. However, a custom Hook shares logic, not the state itself.

## Q59. What is the compound component pattern in React?

Compound Component Pattern is a React design pattern where a parent component and its related child components work together as one reusable component system.

For example, we can have `Tabs`, `Tabs.Tab`, and `Tabs.Panel`. The parent can manage shared state, and the child components can use that state.

This pattern makes components more flexible and easier to use. React Context is often used to share the state between the parent and child components.

## Q60. What are Error Boundaries, and how do they work?

Error Boundary is a React feature that catches certain JavaScript errors in a child component tree and shows a fallback UI instead of crashing that part of the application.

It is traditionally implemented using a class component. We can use `getDerivedStateFromError()` to update the state and show the fallback UI. We can use `componentDidCatch()` to log the error.

Error Boundaries handle errors during rendering and some lifecycle methods. They do not automatically catch errors from event handlers or asynchronous code.
