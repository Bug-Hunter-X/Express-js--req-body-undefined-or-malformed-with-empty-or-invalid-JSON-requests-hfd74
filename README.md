# Express.js - Handling Empty or Invalid JSON Request Bodies

This repository demonstrates a common issue in Express.js applications where the `req.body` object is undefined or malformed when dealing with empty or invalid JSON requests.  The problem stems from how Express.js parses JSON data; if the request body isn't valid JSON or if it's empty, it might not populate `req.body` as expected.

## Problem

The original `bug.js` demonstrates the faulty behavior. When sending an empty request or a request with malformed JSON, the server will either log an undefined `req.body` or receive a partially parsed representation, leading to unpredictable results and potential errors.

## Solution

The `bugSolution.js` file showcases a robust solution.  It uses an error-handling middleware to catch JSON parsing errors and provides a more graceful response to clients in such cases. It also explicitly checks if `req.body` is defined to prevent unexpected errors.

This approach ensures that the application handles both valid and invalid requests consistently, providing a better user experience and preventing potential application crashes.