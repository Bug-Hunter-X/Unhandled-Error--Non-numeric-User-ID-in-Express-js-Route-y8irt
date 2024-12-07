# Unhandled Error: Non-numeric User ID in Express.js Route

This repository demonstrates a common error in Express.js route handlers: failure to handle non-numeric or invalid user IDs. The `bug.js` file contains the problematic code, while `bugSolution.js` provides the corrected version.

## Bug Description
The original code assumes the `userId` parameter will always be a valid number.  It directly uses `parseInt` without checking for errors. If a non-numeric ID is provided, `parseInt` returns `NaN`, causing the `users.find` method to fail silently or throw an error, leading to a 500 server error or unexpected behavior.  This example uses a simple in-memory array for brevity, but the principle applies to any database query.

## Solution
The improved code in `bugSolution.js` adds comprehensive error handling.  It checks if `parseInt(userId)` results in a valid number, handling both cases where the ID is missing or not a number. This ensures graceful error handling and avoids unexpected crashes.