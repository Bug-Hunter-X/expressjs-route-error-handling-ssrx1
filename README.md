# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  The `bug.js` file shows the problematic code, which fails to handle cases where the user ID is not a number or the user is not found.  The `bugSolution.js` file provides a corrected version with comprehensive error handling.

## Bug

The original code attempts to parse the user ID from the request parameters as an integer and then finds the corresponding user.  However, it lacks error handling for scenarios where:

1. The user ID is not a valid integer.
2. No user with the given ID exists.

These omissions can lead to unexpected behavior, such as crashes or the display of internal server errors to the client.

## Solution

The solution includes robust error handling to address both scenarios:

1. It uses a `try...catch` block to handle potential errors during the parsing of the user ID.
2. It explicitly checks if the user is found and returns a 404 status code if not.

This approach ensures a more robust and user-friendly experience by providing informative error messages and preventing crashes.