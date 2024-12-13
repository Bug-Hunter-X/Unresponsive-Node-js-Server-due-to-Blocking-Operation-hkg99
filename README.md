# Unresponsive Node.js Server due to Blocking Operation

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation that blocks the event loop.  The `bug.js` file contains the problematic code. The solution, in `bugSolution.js`, uses asynchronous operations and demonstrates proper handling of long tasks to prevent blocking.

## Problem

Node.js is single-threaded.  Long-running synchronous operations in the event loop prevent other requests from being processed, leading to unresponsiveness. The example code simulates this by keeping the CPU busy for 5 seconds before responding.

## Solution

The solution involves using asynchronous operations (e.g., `setTimeout`, `setImmediate`, or worker threads). This allows the event loop to continue handling other requests while the long-running task completes in the background.