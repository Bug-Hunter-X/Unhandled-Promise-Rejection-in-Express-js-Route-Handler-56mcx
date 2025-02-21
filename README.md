# Unhandled Promise Rejection in Express.js Route Handler

This repository demonstrates a common error in Express.js applications: failing to handle promise rejections within asynchronous route handlers.  Unhandled rejections can lead to application instability and make debugging difficult.

The `bug.js` file showcases the problematic code.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Problem

The original code includes an asynchronous operation (`someAsyncOperation`) within a route handler. If the asynchronous operation rejects (fails), the error is not caught, resulting in an unhandled promise rejection.  This is a silent failure that can be hard to track down.

## Solution

The solution involves adding a `.catch` block to the promise chain. This block handles any errors thrown by the asynchronous operation, allowing for graceful error handling (such as sending an error response to the client, logging the error, or taking other appropriate actions).