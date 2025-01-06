# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js: server unresponsiveness due to blocking long-running tasks.  The `server.js` file contains a simple HTTP server that simulates a long-running task (5 seconds), blocking the event loop and making the server unresponsive to new requests during that time.

The solution (`server-async.js`) demonstrates how to address this by using asynchronous techniques to prevent blocking.

## How to reproduce
1. Clone this repository.
2. Run `node server.js`.
3. Open multiple browser tabs and try to access `http://localhost:3000`.  Observe that only one request is handled at a time, and subsequent requests are delayed until the first one finishes.
4. Run `node server-async.js` and repeat step 3.  Note that requests are now handled concurrently.