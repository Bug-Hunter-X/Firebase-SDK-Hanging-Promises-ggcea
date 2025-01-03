# Firebase SDK Hanging Promises

This repository demonstrates a common, yet difficult-to-debug, issue in Firebase:  promises that neither resolve nor reject.  This can lead to unexpected behavior in your application, particularly deadlocks and unexpected pauses.

The `firebaseBug.js` file contains example code that reproduces the problem. The `firebaseBugSolution.js` offers potential solutions and strategies for handling these situations.

**Problem:**  Asynchronous operations using Firebase (database reads, authentication, etc.) may unexpectedly hang, neither fulfilling nor rejecting their promises. Standard `then` and `catch` blocks might not trigger, making debugging very difficult.

**Solutions:** This example explores techniques such as timeouts, promise cancellation (where applicable), and improved error handling to mitigate this issue.   It's crucial to understand the context of Firebase operations and the underlying network and server state to diagnose and prevent these hanging promises.