# Silent Failure in Express.js Async Route

This repository demonstrates a common but easily missed error in Node.js Express.js applications: unhandled promise rejections in asynchronous routes.  When an asynchronous operation within a route fails and no error handling is present, the error is silently swallowed, making debugging significantly more challenging.

The `bug.js` file contains the flawed code.  The `bugSolution.js` file provides the corrected version.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express`
3. Run `node bug.js`
4. Observe that the server starts, but errors (approximately half the time) are not reported to the console.
5. Run `node bugSolution.js`
6. Observe that errors are now properly caught and reported.

## Lesson

Always handle promise rejections in your asynchronous code, especially in Express.js routes.  Use `.catch()` to gracefully handle errors and prevent silent failures.