# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by incorrectly updating state within the effect's callback.  The `bug.js` file contains the faulty code, and `bugSolution.js` provides the corrected version.

## Bug Description
The original code attempts to reset the `count` state to 0 whenever it exceeds 5.  However, this creates an infinite loop because each time `setCount(0)` is called, the `useEffect` hook runs again, re-evaluating the condition and triggering the update again. 

## Solution
The solution in `bugSolution.js` addresses this by using a conditional check outside the `useEffect` hook. The state update only happens if the original count is greater than 5. This prevents the infinite loop.