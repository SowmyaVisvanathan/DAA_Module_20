# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 11/03/2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.

## Algorithm
1. Input:
   - An integer n (number of elements).
   - A list arr of n integers.
   - An integer x (target sum).
2. Generate All Subsets:
   - For each possible subset size i from 0 to n:
   - Generate all combinations of arr with size i.
3. Check Subset Sums:
   - For each generated subset:
   - Compute the sum of its elements.
   - If the sum equals x, print the subset.

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: Sowmya V
Register Number: 212222110045
*/

from itertools import combinations;
def subsetSum(n, arr, x):
	for i in range(n+1):
		for subset in combinations(arr, i):
			if sum(subset) == x:
				print(list(subset))
n=int(input())
arr=[]
for i in range(0,n):
    a=int(input())
    arr.append(a)
x = int(input())
subsetSum(n, arr, x)

```
## Output:
![image](https://github.com/user-attachments/assets/c27d506b-584c-47cd-8b16-9ea1e2361135)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
