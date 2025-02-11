# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React components: a memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The provided solution shows how to correctly use the cleanup function to avoid these issues. 

## Bug
The `bug.js` file demonstrates a React component that uses `setInterval` to update a counter every second. However, it fails to include a cleanup function within the `useEffect` hook, resulting in an interval that continues to run even when the component unmounts.  This leads to a memory leak and unexpected behavior.

## Solution
The `bugSolution.js` file shows the corrected implementation. By returning a cleanup function from `useEffect`, `clearInterval` is called when the component unmounts, preventing the memory leak.  Always remember to cleanup any timers or other resources created within useEffect.