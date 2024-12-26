# React setInterval Memory Leak
This repository demonstrates a common error in React applications: using `setInterval` within a `useEffect` hook without providing a cleanup function. This leads to a memory leak because the interval continues running even after the component unmounts.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it lacks the necessary cleanup function in the `useEffect` hook to stop the interval when the component is unmounted. This causes the interval to persist, leading to a memory leak.

## Solution
The `bugSolution.js` file provides the corrected implementation. It uses the return value of `useEffect` to provide a cleanup function that calls `clearInterval` to stop the interval when the component is unmounted.  This prevents the memory leak.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter in the browser.  The memory leak occurs when the component is unmounted (e.g. by navigating away from the page).
