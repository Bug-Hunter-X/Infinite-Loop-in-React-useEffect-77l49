# React UseEffect Infinite Loop Bug
This repository demonstrates a common mistake when using the `useEffect` hook in React that leads to an infinite loop.  The issue stems from directly updating the state variable inside the `useEffect`'s callback function without considering the asynchronous nature of state updates. 

## Bug Description
The `bug.js` file contains a React component that attempts to increment a state variable (`count`) within the `useEffect` hook. This creates an infinite loop because each state update triggers a re-render, which in turn re-executes the `useEffect` hook, leading to another state update, and so on. 

## Solution
The `bugSolution.js` file provides a corrected version of the component. The key change is using the previous state value to update the count.  This ensures that the `useEffect` hook doesn't trigger a continuous loop of re-renders and updates.