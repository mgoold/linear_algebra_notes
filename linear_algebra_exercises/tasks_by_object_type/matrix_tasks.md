
# Undefined Matrices

## Example 1

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise
* An undefined mxn matrix A and vector x are stipulated.  m and n, and x are not specified.
* An example result vectors b are given:
    * a vector b that has no solution is given
    * another vector b is said to have exactly 1 solution.
 
### Problem Text:

"This question is about an mxn matrix A for which 

$$
Ax\text{ = }
\left[
{\begin{array}{cc}
1 \\
1 \\
1 \\
\end{array}} 
\right]
$$

... has no solution and 

$$
Ax\text{ = }
\left[
{\begin{array}{cc}
0 \\
1 \\
0 \\
\end{array}} 
\right]
$$

... has exatly one solution.

### Tasks:
*  "Give all possible info about m, n and the rank r of A."
*  "Find all solutions Ax = 0, and explain your answer."
*  "Write down an example of a matrix A that fits the description in part (a)."

## Example 2

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise

A 3x3 matrix A is said to reduce to the identity matrix I via a list or row operations.

### Problem Text

"The 3x3 matrix A reduces to the identiy matrix I by the following 3 row operations (in order):
* $E_{21}:$  subtract 4 times row 1 from row 2.
* $E_{31}:$  subtract 3 times row 1 from row 3.
* $E_{23}:$  subtract row 3 from row 2.

### Tasks:
* Write the inverse matrix $A^{-1}$ in terms of the E's.  Then compute $A^{-1}$ .
* Give the original matrix A.
* List the lower triangular factor L in A = LU.

## Example 3:

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise:
* Given the dimensions of a matrix, give all possible info about its nullspace.

### Problem Text:
* "If A is a 3x5 matrix, what information do you have about the nullspace of A?

## Example 4:

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise:
* Given the vector or matrix space of all m x n matrices, give the subspace S spanned by all possible RRE forms of R.

### Problem Text:
* " In the vector space M of all 3x3 matrices (you could call this a matris space), what subspace S is spanned by all possible RRE frorms R?

### Tasks
* give the symbolic form of of the upper triangular matrix R repesenting a 3x3 matrix in RREF.
* to give the basis, or subspace S that could be spanned by R, list the possible eschalon forms that R could take.

## Example 5

### Premise

A list of undefined non-zero vectors are said to span a subspace of a defined R space.  List the possible dimensions that the vectors can occupy.

### Problem Text
*  "Suppose u, v and w are non-zero vectors in R7. They span a subspace of R7. What are the possible dimensions of that vector space?"

### Solution or Solution Steps
* The answer is 1, 2 or 3. The dimension can’t be higher because a basis for this subspace has at most three vectors.
* It can’t be 0 because the vectors are non-zero.

## Example 6: 

### Premise
* Given a matrix R of mxn dimensions in RRE with r pivots, describe the nullspace of R.

### Problem Text
* "Suppose a 5 by 3 matrix R in reduced row echelon form has r = 3 pivots.  What's the nullspace of R?"

### Solution or Solution Steps
* Compare n to number of pivots r:
   * if r = n, then all columns are independent and only the 0 vector will be in the nullspace.
   * if r < n and r<m (by definition given mxn = 5x3) then there will either only 0 or infinite solutions for the nullspace bc there will be a free variable.

## Example 7: Describe Undefined Matrix A, with x Complete Solution and Defined b

### Premise
* Given undefined matrix A, a complete soluton x, and a defined b, describe the dimensions and content of matrix A.

### Problem Text

"Suppose we know that 

$$
Ax\text{ = }
\left[
{\begin{array}{cc}
2 \\
4 \\
2 \\
\end{array}} 
\right]
$$

and that 

$$
x\text{ = }
\left[
{\begin{array}{cc}
2 \\
0 \\
0 \\
\end{array}} 
\right]
\text{ + }
\left[
{\begin{array}{cc}
1 \\
1 \\
0 \\
\end{array}} 
\right]
\text{ + }
\left[
{\begin{array}{cc}
0 \\
0 \\
1 \\
\end{array}} 
\right]
$$

is a complete solution.  Note that in this problem A is undefined.

* What is the shape of the matrix A?
* What's the dimension of the row space of A?
* What is the content of A?
* For what vectors b does Ax = b have a solution x?

### Solution or Solution Steps
* For the shape of the matrix A, note that:
   * Matrix A must be 3 columns wide, because the complete solution x has 3 columns -- 1 particular solution for the pivot and 2 free variables.
   * Matrix A must be 3 rows deep, because b has 3 components.
* For the dimensions of the rowspace A, we can see that there are 2 free variables and 1 pivot variable.  You can consider that the rank of the column and rowspace must = the number of pivot variables = 1, or equivalently that it is the number of columns n - number of free columns in nullspace 2 = 1.
* For the content of A:
   * The key is to consider the columns of the complete solution together in a matrix. Do not consider their multipliers c,d etc.  If you get the math right on the matrix, the solution will work with any multipliers c and d.
      * Remember that each row of A will be multiplied as a dot product with each column of x, and the 3 dot products summed together to make a component of b.  So for example $b_1$ = A row 1 * x col 1 + A row 1 + x col 2 + A row 1 * x col 3.  With this in mind, you can see that the first column of A row 1 * x column 1 can do all the work delivering the desired value for the corresponding row of b, and then for the other 2 columns of x the desired outcome is that they should sum to 0.
* For the question on "For what vectors b does Ax = b have a solution x?":
   * Remember that:
      * Ax = b only has a solution when b is in the column space of A.
      * In a "complete solution" for x in Ax = b, the columns corresponding to the free variables are the solution for the null space.
      * The remaining columns (in this case, column 1) is thus the column space of A; any solution for b will have to be a multiple of column 1.
      * There don't have to be free variables always.  Depending on A's content, the column space of A could have been 2 columns or all columns.


# Block Matrices

## Example 1: RRE Form Assessment

### Premise
* Given a generic block matrix of mxn dimensions, describe its RRE form.

### Problem Text
* "Let B be the 10x3 matrix

$$
B\text{ = }
\left[
{\begin{array}{cc}
R \\
2R \\
\end{array}} 
\right]
$$ 

.  What's the RRE form of B?  

### Solution or Solution Steps
* Any capital letter in a block matrix format is assumed to have the same content everywhere in the matrix.  Thus R can be multiplied and subtracted from 2R just as in regular row operations, yielding:

$$
B_{rre}\text{ = }
\left[
{\begin{array}{cc}
R \\
0 \\
\end{array}} 
\right]
$$ 

.

## Example 2: Rank of Block Matrix

### Premise
* Given a generic block matrix of mxn dimensions, describe its rank.

### Problem Text
* "What is the rank of B?" (see above).

### Solution or Solution Steps
* Note whether RRE has changed the block description into something fragmented such that there are 0s on the same row.
   * If there aren't then only rows have been eliminated but the pivots are still the same as the column count (in this case 3).
   * If the post-rre form has 0s on the same row as the original block, then some columns have been made redundant during row operations, so < 3.

## Example 3: RRE Form of 2x2 Block Matrix

### Premise
* Describe the RRE form of a 2x2 block matrix

### Problem Text
* "What is the RRE form of 

$$
C\text{ = }
\left[
{\begin{matrix}{cc}
R & R\\
R & 0 \\
\end{matrix}} 
\right]
$$ 

?"

### Solution or Solution Steps
* Just as with explicitly defined rows, you can do row operations on the blocks.
* In this case, the result ends up as:

$$
C\text{ = }
\left[
{\begin{matrix}{cc}
R & R\\
R & 0 \\
\end{matrix}} 
\right]
\rightarrow
\left[
{\begin{matrix}{cc}
R & 0\\
0 & R \\
\end{matrix}} 
\right]
\text{ = }R
$$ 

## Example 4: Rank of 2x2 Block Matrix

### Premise
* Give the rank of a 2x2 block matrix.

### Problem Text
* "What is the rank of C?" (above)

### Solution or Solution Steps
*  Note whether/how the blocks in current matrix are defined.  In this case, C is created from R blocks, which had a rank of 3.
*  Since C is 2xR wide and there are no other columns, the rank of C must be 6.

## Example 5: Dimension of Nullspace of Block Matrix Transpose

### Premise
* Given a block matrix with defined dimensions, give the dimensions of its transpose.

### Problem Text
* "What is the dimension of the nullspace of $C^T$ ?"

### Solution or Solution Steps
* Remember that taking the transpose of a matrix is the same as handling its rows in a column-wise manner.  Therefore the nullspace of a matrix transpose is the same as its left nullspace $N\left(C^T\right)$.
* Remember that rank of the rowspace is the same as for the column space, in this case 6.
* Remember that when the matrix is transpose, the rows become columns, so the column count is now 10 = m.
* Remember that the **rank of the left nullspace** is m-r = 10 - 6 = 4.

# Defined Matrix, >2x2, with Variable(s) in Content

## Example 1

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise

A > 2x2 matrix with defined dimensions contains both numbers and a variable(s).

### Problem text

"This 3x4 matrix depends on c:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 2 & 4 \\
3 & c & 2 & 8 \\
0 & 0 & 2 & 2 \\
\end{matrix}} 
\right]
$$

### Tasks:
* For each c, find a basis for the column space of A.
* For each c, find a basis for the nullspace of A.
* For each c, find the complete solution x to

$$
Ax\text{ = }
\left[
{\begin{array}{cc}
1 \\
c \\
0 \\
\end{array}} 
\right]
$$ 

.

# Defined RREF Matrix R, >2x2

## Example 1

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Premise

Given a 3x5 matrix in RREF form, give all possible info about the columns.

### Problem Text

"Suppose row operations on A lead to this matrix R = rref(A):"

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 4 & 0 & 0 & 0\\
0 & 0 & 0 & 1 & 0\\
0 & 0 & 0 & 0 & 1\\
\end{matrix}} 
\right]
$$ 

### Tasks
"Write all known information about the columns of A."

## Example 2

### Premise

Given a 3x5 matrix in RREF form, give all possible info about the columns.

### Problem Text

"Suppose row operations on A lead to this matrix R = rref(A):"























