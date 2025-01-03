# React useEffect Hook Missing Dependency

This repository demonstrates a common React bug related to the `useEffect` hook: a missing dependency in the dependency array. This can lead to unexpected behavior, such as infinite rendering loops or stale closures.

## Bug
The `bug.js` file contains the erroneous code. The `useEffect` hook is used to log a message to the console whenever the component renders. However, the dependency array is empty (`[]`), meaning the effect runs only once on mount.  Since the `count` state variable changes, the component re-renders, but the effect doesn't re-run because it's not listening to the changes. This will not cause an error, but may lead to unexpected results.

## Solution
The `bugSolution.js` file demonstrates the corrected code.  The `count` variable is added to the dependency array, ensuring the effect re-runs whenever the `count` value changes.