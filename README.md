# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations and promises.  This prevents the event loop from blocking and maintains responsiveness.

## Bug Description

A synchronous operation that takes a considerable amount of time (e.g., a complex calculation, database query, or file I/O) can block the Node.js event loop.  This leads to the server becoming unresponsive to new requests until the long-running operation completes. 

## Solution

The solution involves refactoring the code to use asynchronous operations.  This allows the event loop to continue processing other tasks while the long-running operation executes in the background.