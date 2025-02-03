# React setInterval Memory Leak

This repository demonstrates a common mistake in React components: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks, as the interval continues even after the component unmounts.

The `bug.js` file contains the flawed code. The `bugSolution.js` file provides the corrected implementation.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory in the terminal.
3. Run `npm install` to install the necessary packages.
4. Run `npm start` to start the development server.
5. Observe the count in the component. The count continues even after unmounting the component.

## Solution

The solution involves returning a cleanup function from the `useEffect`'s callback, to stop the interval before unmounting. See `bugSolution.js` for details.