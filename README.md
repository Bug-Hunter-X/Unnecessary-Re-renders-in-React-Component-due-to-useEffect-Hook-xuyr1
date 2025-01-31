# Unnecessary Re-renders in React Component

This repository demonstrates a common React bug involving the `useEffect` hook.  The provided component experiences unnecessary re-renders due to an improperly configured dependency array.  The solution illustrates the correct use of the dependency array to ensure optimal performance.

## Bug
The `MyComponent` function uses the `useEffect` hook to log a message to the console. However, the dependency array is empty (`[]`), causing the effect to run only once on mount. This isn't necessarily a problem, but the intent is likely to log each time `count` changes.  In this case, the log statement executes every single time the component re-renders, regardless of changes to the count state.

## Solution
The solution includes the `count` variable in the dependency array: `[count]`. This ensures the effect only runs when the `count` value changes, resolving unnecessary re-renders and improving performance.