## Q01. What is React, and why is it used?

React is a JavaScript library used to build interactive and component-based user interfaces.

With React, we can divide a user interface into small and reusable components. React also helps update the UI when the application state or data changes, so we usually do not need to manually manipulate the DOM.

The main reasons to use React are its component-based architecture, reusability, declarative approach, and easier maintenance of large user interfaces.

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
