
# Excercises on the Four Fundamental Subspaces

## Problem 10.1

A is an m by n matrix of rank r. Suppose there are right sides b for which Ax = b has no solution.

a) What are all the inequalities (< or ≤) that must be true between m, n, and r?

Answer:

If Ax = b has right side values for which there is no solution, it means that 1 or more columns will be dependent so that they can't fill all the potential space Rn of the matrix.  So, not every column will have a pivot.  Therefore r < n.  
In order for there to be less pivots than columns AND have right sides b with no solution, there must be a column in which there COULD be a pivot, but there isn't.  In other words, the matrix must be mxn where m >= n.  
Therefore, since there is a column with a missing potential pivot, r will also be < m.

b) How do you know that $A^{T}y\text{ = }0$ has solutions other than y = 0?

Answer:

It has at least free variable column -- under RRE, this will guarantee at least one zero row.  Solving for $N\left(A^{T}\right)$ using the AI --> RE approach, we are sure to find that the 0 row in R will correspond to some non-zero row in E.

## Problem 10.2

$A^{T}y\text{ = }d$ is solvable when d is in which of the four subspaces? 
Answer:
Rowspace.

The solution y is unique when the _left nullspace________________ contains only the zero vector.

