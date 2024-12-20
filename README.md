# React Native useEffect Cleanup Function Error

This repository demonstrates a common but subtle bug in React Native involving the `useEffect` hook and its cleanup function.  The bug occurs when the cleanup function attempts to access component state or props after the component has already unmounted. This often leads to errors like `Cannot read properties of undefined (reading 'count')`.

## Problem

The provided `bug.js` file contains a component that uses `useEffect` to set up an interval. The cleanup function attempts to log the component's `count` state after clearing the interval. If the component unmounts before `clearInterval` is executed, this will cause an error.

## Solution

The `bugSolution.js` file demonstrates a solution that addresses this issue.  It uses a ref to track whether the component is still mounted, ensuring that the cleanup function only executes if the component is still active. This prevents the error and ensures cleaner unmounting behavior.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install`.
3. Run the app using your preferred React Native method.
4. Observe the error in the console when you quickly navigate away from the screen that renders `MyComponent`. 

## How to use the solution

Replace the code in `bug.js` with the code in `bugSolution.js` to see how the issue is resolved.