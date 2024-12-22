# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer, but it doesn't handle the scenario where the `id` is not a valid integer, resulting in potential crashes or unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug
The main issue lies in the absence of input validation and error handling for the `userId`.  If a non-numeric value is provided as the ID, `parseInt(userId)` will return `NaN`, leading to issues when comparing it with the `user.id`.

## Solution
The solution involves adding error handling to check if `parseInt(userId)` results in a valid number and returns a 400 error if the ID is invalid.