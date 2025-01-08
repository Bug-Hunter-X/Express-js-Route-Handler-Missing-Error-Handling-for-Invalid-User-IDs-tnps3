# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the code attempts to parse a user ID from the request parameters as an integer without checking if the input is valid. This can lead to unexpected behavior or crashes if the ID is not a number.

The `bug.js` file contains the erroneous code.  The `bugSolution.js` file shows how to correctly handle the error.

## Bug

The primary issue is the lack of input validation.  If a user provides a non-numeric ID, `parseInt(userId)` will return `NaN`, and the subsequent `users.find()` operation will fail silently or throw an error depending on the implementation of `users.find()`. 

## Solution

The solution involves adding input validation to check if the `userId` is a valid number before attempting to use it.  This prevents unexpected errors and enhances the application's robustness.