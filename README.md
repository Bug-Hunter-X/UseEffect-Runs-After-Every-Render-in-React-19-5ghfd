# React 19 useEffect Bug: Excessive Re-renders

This repository demonstrates a common issue in React 19 where the `useEffect` hook runs after every render, leading to performance problems. The example shows a simple counter component; however, in larger applications, this could cause significant performance degradation.

## Problem

The `useEffect` hook is designed to perform side effects after a component renders.  However, the current implementation causes it to run on every render, even if the state that triggers it hasn't changed. This is inefficient and can lead to unexpected behavior.

## Solution

The solution involves using the `useEffect` hook's optional dependency array to specify what values to watch. By only including `count` in the dependency array, the effect will only run when the `count` state changes, improving performance.

## How to Reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs showing that the effect runs on every click, even when no other state variables have changed.

## How to Fix

Refer to the `bugSolution.js` file for the corrected code. By adding the dependency array `[count]`, the effect only runs when `count` changes.