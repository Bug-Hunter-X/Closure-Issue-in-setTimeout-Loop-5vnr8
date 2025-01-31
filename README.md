# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure issue in JavaScript when using `setTimeout` within a loop. The expected behavior is to print numbers 0 through 9 with a one-second delay between each. However, due to the way closures work, the final value of `i` (which is 10) is printed ten times.

## Bug Description
The problem lies in how JavaScript handles closures and the asynchronous nature of `setTimeout`.  By the time `setTimeout`'s callback function executes, the loop has already completed, and `i` holds its final value.

## Bug Solution
The solution involves creating a new scope for each iteration of the loop, thereby ensuring that each callback function captures its own value of `i`.  This can be achieved using an immediately invoked function expression (IIFE) or `let` within the loop.