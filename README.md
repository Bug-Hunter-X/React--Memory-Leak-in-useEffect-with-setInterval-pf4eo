# React Memory Leak Example

This repository demonstrates a common memory leak in React applications caused by the improper use of `setInterval` within the `useEffect` hook.  The provided `bug.js` file showcases the erroneous implementation, while `bugSolution.js` offers the correct approach to avoid memory leaks. 

## Problem

When using `setInterval` inside `useEffect` without a cleanup function, the interval continues to run even after the component unmounts.  This leads to a memory leak as the component's state and other associated resources are not released. The `bug.js` file shows this problem. 

## Solution

The solution, shown in `bugSolution.js`, involves returning a cleanup function from the `useEffect` callback. This function clears the interval when the component is unmounted, preventing the memory leak.  The cleanup function ensures that the `setInterval` is stopped when no longer needed.