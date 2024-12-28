# React Native useEffect Infinite Loop Bug

This repository demonstrates a common bug in React Native applications involving the `useEffect` hook and functions within its dependency array.  The bug leads to an infinite loop because the function is recreated on every render, triggering the effect repeatedly.

The `bug.js` file shows the problematic code. The `bugSolution.js` file presents the corrected version using `useCallback` to memoize the function, resolving the issue.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npx react-native run-android` or `npx react-native run-ios` to start the app. Observe the infinite loop in the console (or app crash).
4. Switch to `bugSolution.js` and re-run to see the corrected behavior.

## Solution

The solution involves using React's `useCallback` hook to memoize the function.  `useCallback` returns a memoized version of the function, which only changes if one of its dependencies changes.  This prevents the function from being recreated on every render, thereby resolving the infinite loop.