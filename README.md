# Express.js Route Error Handling Bug

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The `bug.js` file contains the buggy code, which fails to handle cases where the user ID is not a valid integer.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug Description

The original code attempts to parse the user ID from the request parameters as an integer and then uses it to find a user in an array.  If the ID is not a valid integer (e.g., it's a string or contains non-numeric characters), the `parseInt` function will return `NaN`, leading to a potential crash or unexpected results.

## Solution

The corrected code (`bugSolution.js`) adds error handling to check if the parsed user ID is a valid integer before attempting to use it.  If the ID is invalid, it returns a 400 Bad Request error.  This ensures that the application responds gracefully to invalid input, preventing unexpected behavior or crashes.