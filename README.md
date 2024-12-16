# React useEffect Cleanup and setTimeout Misuse
This repository demonstrates a common bug in React applications involving the `useEffect` hook and the `setTimeout` function.  The example showcases an incorrect usage of `setTimeout` inside of `useEffect` which leads to a memory leak if the component unmounts before the timeout completes. Additionally, the example demonstrates the proper use of cleanup functions within useEffect to prevent this memory leak.

## Bug
The initial `bug.js` file demonstrates a component that uses the `useEffect` hook to update a counter every second. However, it incorrectly handles the `setTimeout` function, not saving the returned timeout ID and failing to clear the timeout when the component unmounts.  This can result in unintended behavior and memory leaks.

## Solution
The `bugSolution.js` file provides the corrected implementation. The fix involves saving the timeout ID returned by `setTimeout` and then using that ID to clear the timeout in the cleanup function of the `useEffect` hook.  This ensures that the timeout is cleared before the component unmounts, preventing memory leaks and ensuring predictable behavior.
