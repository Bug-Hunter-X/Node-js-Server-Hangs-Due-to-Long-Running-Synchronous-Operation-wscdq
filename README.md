# Node.js Server Hang - Long-Running Synchronous Operation

This repository demonstrates a common Node.js issue: a server hanging due to a long-running synchronous operation within the request handler.  The synchronous `while` loop blocks the event loop, preventing the server from responding to subsequent requests.

The `server.js` file contains the buggy code.  The `serverSolution.js` file provides a solution using asynchronous operations to avoid blocking the event loop.

## Bug

The server uses a synchronous `while` loop to simulate a long-running task.  This blocks the event loop and prevents any other requests from being processed while the loop is running.

## Solution

The solution uses asynchronous techniques (e.g., `setTimeout`) to avoid blocking the event loop. The long-running task is offloaded, allowing the server to remain responsive.