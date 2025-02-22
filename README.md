# Lua Table Iteration Bug

This repository demonstrates a subtle bug that can occur when modifying a Lua table while iterating over it using the `pairs` iterator.  The `pairs` iterator doesn't guarantee a specific iteration order, and changes to the table during iteration can cause elements to be skipped or an infinite loop.

## Bug Description

The `bug.lua` file contains a function that recursively iterates over a table. If the table is modified during iteration, the results are unpredictable.  The provided example shows that the inner tables may not all be processed properly.

## Solution

The `bugSolution.lua` file demonstrates how to avoid this by creating a copy of the table before iteration or by iterating using a different approach (like ipairs) if order is important.  The most robust solution involves a copy to avoid modifying the original data and avoid potential issues.