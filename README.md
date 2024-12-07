# COBOL Off-by-One Error

This repository demonstrates a common off-by-one error in COBOL using a `PERFORM ... VARYING` loop. The error causes the last element of the table to remain uninitialized. The solution is to adjust the loop condition to ensure that all 100 elements are correctly populated.

## Bug

The bug resides in the `PERFORM VARYING` loop. The loop terminates when `WS-COUNT` becomes greater than 100, resulting in the last element of the `WS-TABLE` being skipped.

## Solution

The solution changes the loop condition to `UNTIL WS-COUNT > 100` to `UNTIL WS-COUNT >= 100`. This change ensures that the loop executes 100 times, populating all the table entries.  The `>=` ensures the last record is populated.