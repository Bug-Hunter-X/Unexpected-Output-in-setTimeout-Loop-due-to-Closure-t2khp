# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript bug related to closures within `setTimeout` loops.  The expected behavior is to print the numbers 0 through 9, each after a one-second delay.  However, due to how closures work in JavaScript, the output will incorrectly print the value 10 ten times.

## Problem

The problem lies in how the variable `i` is accessed within the `setTimeout` callback.  By the time the `setTimeout` callbacks finally execute, the `for` loop has already completed, and `i` is 10.

## Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, ensuring that the correct value of `i` is captured in each callback.

## How to run the code

1. Clone the repository
2. Open `bug.js` and `bugSolution.js` to view the buggy and corrected code, respectively.
3. Run either `bug.js` or `bugSolution.js` in a JavaScript environment (such as Node.js or a browser's console) to see the different outputs.