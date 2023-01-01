## Lab-Coursework-CE880
Lab Coursework For CE880

## ISSUES ENCOUNTERED


## In Question 5. I gave this solution I got this error that didn't seem to go away no matter what:

## QUESTION:

Write a function to calculate the `mean` and `standard deviation` of IRIS dataset (last column only). `Hint`: You can use NumPy aggregate functions. Create a list and append value to it and return the output. 

## SOLUTION:

def stats(X):
    """Write a functon to calculate mean and standard deviation of IRIS dataset (last column only)."""
    # YOUR CODE HERE
    my_stat = [X[3].mean(), X[3].std()]
    print(f"Returned Values {my_stat}")
    return my_stat
    raise NotImplementedError()

## RESULT:

Returned Values [1.199333333333334, 0.7622376689603465]

  Actual Values [1.1993333333333336, 0.7622376689603465]

## ERROR:

---------------------------------------------------------------------------
AssertionError                            Traceback (most recent call last)
~\AppData\Local\Temp\ipykernel_11716\2933274922.py in <module>
      1 """Check your output"""
      2 # Test case
----> 3 assert stats(X) == [1.1993333333333336, 0.7622376689603465]

AssertionError: 


## POSSIBLE REASON FOR ERROR

The error you are seeing is likely caused by the fact that the assert statement is comparing two lists of floating-point numbers, which may not be exactly equal due to the way they are represented in memory.

To fix this issue, you can use the assert math.isclose statement to check if the values are close to the expected values within a certain tolerance, specified by the rel_tol argument.

For example, you can modify the test case as follows:

## OUTCOME

import math

# Test case
assert math.isclose(stats(X)[0], 1.1993333333333336, rel_tol=1e-9)
assert math.isclose(stats(X)[1], 0.7622376689603465, rel_tol=1e-9)


