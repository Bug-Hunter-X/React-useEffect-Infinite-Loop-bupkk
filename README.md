# React useEffect Infinite Loop
This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by incorrectly updating state within the hook's dependency array.

## The Problem
The `useEffect` hook, when called without a dependency array, runs after every render.  If you modify the state inside this hook, it triggers a re-render, leading to another execution of the `useEffect`, and so on - an infinite loop.

## How to Reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console; the count will increase infinitely, eventually crashing the browser or causing performance issues.

## The Solution
The provided solution (`bugSolution.js`) demonstrates the correct approach: ensuring the state update does not trigger a re-render by avoiding dependence on the current state within the dependency array. The corrected `useEffect` only runs once after the initial render and then no longer causes any issues.