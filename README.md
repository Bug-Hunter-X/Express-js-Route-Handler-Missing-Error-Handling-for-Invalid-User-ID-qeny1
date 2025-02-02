# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The example shows a route that fetches a user by ID.  The code attempts to parse the ID as an integer but fails to handle the case where the ID is not a valid integer, which can lead to unexpected behavior or crashes.

## Bug

The `bug.js` file contains the buggy code.  It attempts to parse the user ID as an integer without error handling.  If the ID is not a valid integer, `parseInt(userId)` will return `NaN`, and the `find` method will not find the user, leading to a `404` error. However, a more descriptive error message would improve user experience and help in debugging.

## Solution

The `bugSolution.js` file shows the corrected code.  It includes error handling to check if the parsed ID is a valid integer before attempting to find the user.  If the ID is not a valid integer, it sends a more informative error response.