# React 19 useEffect Infinite Loop Bug

This repository demonstrates a common bug in React 19 where the `useEffect` hook runs after every render, leading to an infinite loop and performance issues.  The problem arises from omitting the dependency array in the `useEffect` hook, causing it to re-run on every state change, even if the dependencies haven't changed.

## Bug Description
The `useEffect` hook in the provided `MyComponent` is missing a dependency array. This causes the `console.log` statement to execute continuously. For each render the console is spammed by messages and it becomes slow.

## Solution
The solution involves adding a dependency array to the `useEffect` hook.  This array lists the values that the effect depends on. The effect will only run when these values change.