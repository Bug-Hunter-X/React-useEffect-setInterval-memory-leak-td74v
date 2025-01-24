# React useEffect setInterval Memory Leak

This example demonstrates a common issue in React applications: memory leaks caused by improper use of `setInterval` within the `useEffect` hook.  The provided `MyComponent` doesn't include a cleanup function to stop the interval when the component unmounts, leading to a memory leak.  The solution demonstrates the correct way to handle this scenario using the cleanup function provided by `useEffect`'s return value.

## Bug
The bug is in `MyComponent`. The `setInterval` function within the `useEffect` hook starts an interval that continuously increments the state. However, this interval is never stopped when the component unmounts, resulting in a memory leak.  The counter will continue to increment even after the component is removed from the DOM.