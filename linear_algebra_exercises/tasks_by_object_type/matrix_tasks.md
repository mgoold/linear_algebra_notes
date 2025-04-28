
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

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Premise
* A list of undefined non-zero vectors are said to span a subspace of a defined R space.  List the possible dimensions that the vectors can occupy.

### Problem Text
*  "Suppose u, v and w are non-zero vectors in R7. They span a subspace of R7. What are the possible dimensions of that vector space?"

### Solution or Solution Steps
* The answer is 1, 2 or 3. The dimension can’t be higher because a basis for this subspace has at most three vectors.
* It can’t be 0 because the vectors are non-zero.

## Example 6: 

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Premise
* Given a matrix R of mxn dimensions in RRE with r pivots, describe the nullspace of R.

### Problem Text
* "Suppose a 5 by 3 matrix R in reduced row echelon form has r = 3 pivots.  What's the nullspace of R?"

### Solution or Solution Steps
* Compare n to number of pivots r:
   * if r = n, then all columns are independent and only the 0 vector will be in the nullspace.
   * if r < n and r<m (by definition given mxn = 5x3) then there will either only 0 or infinite solutions for the nullspace bc there will be a free variable.

## Example 7: Describe Undefined Matrix A, with x Complete Solution and Defined b

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

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

### Problem Text

# Block Matrices

## Example 1: RRE Form Assessment

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

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

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

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

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

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

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Premise

Given 2 matrices that are to be multiplied together, give the basis for their nullspace, and their complete solution, without doing the matrix multiplication.

### Problem Text

* "Suppose:
  
$$
\text{A = CD = }
\left[
{\begin{matrix}{cc}
1 & 1 & 0 \\
0 & 1 & 0 \\
1 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & -1 & 2 \\
0 & 1 & 1 & -1 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

.  Without performing matrix multiplication CD, answer the following:

* Give the basis for the Nullspace of B
* Find the complete solution to

$$
Bx\text{ = }
\left[
{\begin{array}{cc}
1 \\
0 \\
1 \\
\end{array}} 
\right]
$$

.

### Solution or Solution Steps

* For the basis of the nullspace of B:
   * Remember that for the product B of any 2 matrices C and D multiplied together, $m_1xn_1$ times $m_2xn_2$ = $m_1xn_2$ .
   * Assess whether either matrix is invertible:
      * D cannot be; it is rectangular.
      * C is square and all columns are independent.  There are 2 rules, either of which would show this:
         * the matrix is square and all n columns are independent (it has n pivots).
         * the RRE form has no 0s on the diagonal.
   * Remember that if 2 matrices are multiplied, and one of them is invertible, then the nullspace for the resultant matrix will have to come from the non-invertible matrix.  The state problem solution states this as "Because C is invertible, the nullspace of B is the same as [whatever nullspace may exist for] D."  To see that this is so, consider that the matrix C and be reduced through RRE to the identity matrix due to its having values on every diagonal and all independent columns.  Thus CD reduces to ID, which means any nullspace will have to come from D.  The problem text that "C is invertible" is a round-about way of saying this.
   * Evaluate whether either matrix is in RRE form.  Easiest way is to try RR on both and see if you can make any changes.  C will reduce to I, but you can't make any changes to D.
   * Note that D has 2 pivots and 2 free variables.  Therefore, it will have a special solution.  When we solve for it, N(D) will be N(B):
        * To get D's special solution, set one of the free variables to 1, and the others to 0.  Then plug these into the RR form of the equations and solve the remaining variables via back-substitution.  Do this for each free variable, toggling it to one and the others to zero.  This process will yield:

      $$
      \text{N(B) = N(B) = }
      \left[
      {\begin{array}{cc}
      1 \\
      -1 \\
      1 \\
      0 \\
      \end{array}} 
      \right]
      \text{, }
      \left[
      {\begin{array}{cc}
      1 \\
      -1 \\
      1 \\
      0 \\
      \end{array}} 
      \right]
      $$

* For the complete solution to:

$$
Bx\text{ = }
\left[
{\begin{array}{cc}
1 \\
0 \\
1 \\
\end{array}} 
\right]
$$

, we can:

* remember that a complete solution for Ax = b is $x_{particular}$ + $x_{nullspace}$ .  We already have the special solution for the nullspace, so we just need to find $x_{particular}$ .  To do this, we:
   * take the equations of D for row 1 and 2
   * substitute in 0 for the free variables into this 2-equation system
   * use back substitution to find the pivot variables -- in this case, for $x_1$ and $x_2$ .
   * plug all these into a vector for $x_{particular}$ .  This plus $x_{nullspace}$ is then our complete solution.
 
# Matrix Q & A

## Q1

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* Given a share matrix A who's nullspace is just {**0**} what is the nullspace of $A^T$?
### Answer: 
* $N\left(A^T\right)$ is also {**0**} because A is square.
### Notes: 
* it's easy to just mis-read this as "A is a 1x1 matrix" because there's just one number in the nullspace.  But the nullspace is the 0 vector, and this answer applies to a square matrix of any size.  
### Relevant facts:
* If the nullspace of a square matrix is only [0], it means the matrix is invertible.
* Any invertible matrix can be reduced to I through row reduction, and the transpose of I is I, so the nullspace of $A^T$ would not be changed and would also be 0.

## Q2

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* Do the invertible matrices form a subspace of the vector space of 5x5 matrices?

### Answer: 
* No.  To be a subspace, you must be able to any 2 instances of the elements in the subspace and get the same kind of instance (stay in the subspace).  In ths case, adding 2 invertible matrices may not give you an invertible matrix, so invertible matrices can't make a subspace.
* Also, 0 is not invertible, and a subspace must contain 0.
  
### Notes: 
* 0 is not invertible because, by definition, a matrix is invertible if there exists a matrix A such that $AA^$T\text = }I$.  But because there are no 1's in {0} this is impossible.  So the conditions that both a 0 matrix be in the subspace, and that the 0 matrix be invertible, are opposed and impossible.

## Q3

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "True or false: If $B^2$ = 0, then it must be true that B = 0." 
* Alternate form: "Find a matrix B such that $B^2$ = 0 and B $\neq$ 0."

### Answer: 
* False.  It could be that

$$
B\text{ = }
\left[
{\begin{matrix}{cc}
0 & 1 \\
0 & 0 \\
\end{matrix}} 
\right]
$$

.

## Q4

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "True or false: A system Ax = b of n equations with n unknowns is solvable for every right hand side b if the columns of A are independent."

### Answer: 
* True.  "n equations of n unknowns" means an nxn or square matrix.  If every column of A is indepdendent, then A will reduce to I.  Then any b = Ix.  Equivalently, we can say that $x\text{ = }A^{-1}b$ is a unique solution for any b and x.

## Q5

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "True or false: if m = n then the row space equals the column space."

### Answer: 
* False.  "m and n" typically refers to the row and column **dimensions** before RR.  Row and column **space** refer to bases discovered post-rr.  So a matrix might have enough potential dimension to fill a plane, for example, but only have the bases to fill a line.

## Q6

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "The matrices A and -A share the same four spaces."

### Answer: 
* True.  -A is the same as multiplying every component by -1, so it should just be all the same vectors in the opposite direction, and thus in the same subspaces.

## Q7

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
"True or false: If A and B have the same four subspaces, then A is a multiple of B."

### Answer: 
False. For example A = (1,1) and B =(1,2) should be in the same subspace of 2x1 matrices, but no single multiplier can turn A into B .

## Q8

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "If we exchanges 2 rows of A, which subspaces stay the same?"

### Answer: 
* The rowspace and the nullspace.

### Notes:
* It's clear that the set of formulas that the rows represent would not be changed just by changing their order.
   * Remember that when we swap rows, the corresponding components of b are moved as well.
* It's less clear that the nullspace would be unchanged.  I take this means "without further row operations".

## Q9

### Sources
* https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18.06_exam_1_review.pdf

### Question: 
* "Why can't the vector

$$
v\text{ = }
\left[
{\begin{matrix}{cc}
1 \\
2 \\
3 \\
\end{matrix}} 
\right]
$$

... be in the nullspace of A and also be a row of A?"  

### Answer: 
* Because the nullspace is orthogonal to the rowspace, and must therefore have a 0 dot product.  A vector in the nullspace and a row would, have a dot product of 14, which means it is by definition not in the nullspace.

### Notes:
* It's clear that the set of formulas that the rows represent would not be changed just by changing their order.
   * Remember that when we swap rows, the corresponding components of b are moved as well.
* It's less clear that the nullspace would be unchanged.  I take this means "without further row operations".

# Generic Matrix Tasks

## Matrix Assessment

* Evaluate whether any columns sum to 0.
* Evaluate whether any rows sum to 0.
  * IF a combination of rows of A gives a 0 row, then b must sum to 0 via the same combination.  This is a "condition of solvability".
* Evaluate whether any columns are linear combinations of other columns.
  * If they are not:
    * The columns are independent.
    * The only vector in N(A) will be [0].  --The only value of x that sets Ax = 0 is the 0 vector.
  * If they are:
    * The maximum number of dimensions the matrix can fill is the number of independent columns.
* Compare expected counts pre-RRE: r vs n vs m:
  * if r = m = n, then 1 solution x = b.
  * if r = n < m, then 0 or 1 solution, 0 vector is only vector in N(A)
  * if r = m < n, then R = IF, infinite solutions.
  * if r < m, r < n then 0 or infinite solutions.

### Matrix Facts:
 * The number of *potential* dimensions that a matrix can fill is its row count.
 * The maximum number of dimensions that a matrix can *actually* fill is the number of post-RRE independent columns.
 * The relationship of these two is summed by saying that the matrix has a "[# of columns]-dimensional subspace of [number of rows]".

### Transposed Matrices

#### Facts

* Transposing a matrix swaps row placement for column placement, so that row 1 becomes column 1, row 2 becomes column 2, etc.
* In general, we can say that that $A^T_{ij}=A_{ji}$ for row i and column j.

* Note that:
  * the transpose of the identity matrix I is necessarily I.
  * a symmetric matrix is identical to its transpose: $A=A^T$.
  * multiplying a retangular matrix by its tranpose will give you a symmetric matrix.  For example, with a 2x3 matrix this would cause the off diagonal sum A_11*B_12+A_12*B_22 to be calculated with an identical value from as A_21*B_11+A_22*B_12, so that all the off-diagonal values end up duplicated.
  * When taking the transpose of a product of matrices like $R^{T}R$, the practice is to reverse the order of items in the parentheses, then transpose each term.  So $\left(R^{T}R\right)^T\text{ = }R^TR^{TT}$.
  * Taking additional transposes of symmetric matrix products, e.g. $R^{T}R$, leaves them unchanged.
  * If you take the inverse of a transpose you have to reverse the order: $AA^{-1}=I={A^{-1}}^TA^T$ .


#### Assess Matrix Invertibility

##### Facts

* A matrix must be square to be invertible.
* $A^{-1}$ does not mean $\frac{1}{A}$ .
* An nxn matrix must have n independent columns to be invertible.
* A matrix is invertible if $AA^T\text{ = }I$ .
* If A is invertible, the one and only solution to Ax = b is $x\text{ = }A^{-1}b$ .
* If there is a non-zero vector such that Ax = b, then A has dependent columns, and cannot be invertible.
* A 2x2 matrix is invertibile i.o.i. ad — bc is not zero .
  *  A matrix is invertible i.o.i. its determinant is not equal to 0.
* A triangular matrix is invertible if no diagonal entries are zero.
* B(AC) = (BA)C gives BI=IC or B=C. A left and right inverse matrices are identical.
* When matrices are multiplied, you must reverse their order if you take the inverse of their product: $\left(ABC\right)^{-1}\text{ = }C^{-1}B^{-1}A^{-1}$ .

#### Find the Inverse of A 3x3 Matrix

* We are unlikely to be asked to find the inverse of a matrix larger than 3x3.
* Whatever the size, the fastest way to do it is always Gauss-Jordan $AI\text{ = }IA$ Elimination:
  * Set the matrix A into an "AI --> IA" Equation:
    * Set A (which must be square) and an equally sized I together side by side as if they were to be multiplied.
    * Now set A into RRE form.  Every time you do something to a row of A, *do it to the entire row* , including the components of I in the same row.
    * If you successfully set A into RRE, I will have been transformed into $A^{-1}$ .  If you can't set A into RRE, t means that A has no inverse even though it looked invertible.
    * Check your work by multiplying $AA^{-1}$ .  You should get I.  If you don't, you have an error.

## Matrix Operations

### Matrix Multiplication

![image](https://github.com/user-attachments/assets/c4cd6169-87f0-4e40-9722-9dd3a3722a23)

### Facts
* Matrix dimensions are describe in rows x columns order.

#### Determine if Matrix Multiplication Is Possible
##### Facts:
* In order to multiply matrices AX, or A vector [x], A must have the same column count has X or [x] has rows.

### Solving Matrices for x in Ax = b .

#### Steps:

* Assess matrix to develop intuitions.
* Put matrix in augmented form and do Gaussian rre process.

* Compare r, n, and m and select approach: 

* **Full Column Rank: m=r=n:**
  * Structure: R = I .
  * all columns are independent
  * the matrix will always be invertible
  * its rref form will be I
  * the matrix will have 1 solution x=b because its rref form is I.
 
* **Full Column Rank: r=n<m:**
  * Structure:

$$
R\text{ = }
\left[ {\begin{array}{cc}
   I \\
   0 \\
  \end{array} } \right]
$$

  * only x = 0 can be in N(A)
  * probably no solution except trivial case of b explicitly in A, or x = [1]
   * x in Ax = b will be one specific point.
  * the matrix cannot be invertible (not square)
  * there will be 1 or 0 solutions to x in Ax = b.
   
* **Full Row Rank: r=m<n:**
  * Structure: $R\text{ = }\left[\text{IF or I and F interspersed; I must have first column.}\right]$
  * You must have free variable(s), so there will be an infinite number of solutions.  There is no solvability constraint.
  * Use general Ax = b solution process detailed for m>n; r<n, r<m .

* **Not Full Column or Row Rank: r<n ; r<m**
  * Structure:
  
  $$
  R\text{ = }
  \left[ {\begin{matrix}{cc}
    I & F \\
    0 & 0 \\
   \end{matrix} } \right]
  $$

  * There will be 0 or infinite solutions.
  * A 0 row is a solvability constraint; b must sum to 0 in the way specified for A rows via Gauss RRE process.
  * Establish the particular point in x:
    * Set free (non-pivot) variables to 0.
    * Using back substitution, solve for specific values of pivot variables.
    * Particular point then becomes vector containing resultant specific pivot variable values and 0s.
  * Solve for special solution:
    * Insert 1 into the first of the free variables in the equation system.
    * Using back substitution, solve for the remaining values.
    * Place values of all solved variables into a vector
  * Repeat process, toggling each free variable to 1, and all others to 0, in succession, untill all special solutions are found.
  * Complete solution is c * specific point + d \* special point + e \* special point ... n \* special point.


#### Matrix Row Elimination

Steps:

#### Facts
* Pivots can never be zero
* You **can** multiply/divide a single row by anything.
* In RR, swapping rows is allowed.  This is the same as if you multiplied the matrix by a permutation matrix.
* For a SQUARE matrix in RR form, the determinant = the result of multipling the pivots.
* If you do get the SQUARE matrix into RRE form, its inverse will simply be the same, but with the signs reverse on the off-diagonal multipliers.
* You can simultaneously divide ("pull out") a factor from every component in a matrix in order to simplify it.  This factor should then be show multiplying the matrix from its left-hand side.

### Solving Matrices for Ax = 0

#### Steps

* If matrix is square and full rank in RREF, 0 vector should be only solution.
* If matrix is not square and\|or has 0 in pivot in RREF Ax = 0 will require special solution.
 * If n > m, there will be some solutions to Ax = 0.
  * In this situation, you must not change N(A), but may change C(A).
  * Divide the columns into those with non-zero pivot columns from the zero-pivot "free variable" columns.
  * Set the value of the first free variable column to 1, and the other free variables to 0.
   * Use back-substitution to solve the equations in the rows of the RRE form.
   * Repeat this process for each free variable in succession.  The number of free variables will always be n-r.
  * The complete set of solutions is then the sum of each of these vectors in a linear combination, presented in a "cv + dw = 0" format:

$$
c\left[ {\begin{array}{cc}
   -2 \\
   1 \\
   0 \\
   0 \\
  \end{array} } \right]
\text{ + }
d\left[ {\begin{array}{cc}
   2 \\
   0 \\
   -2 \\
   1 \\
  \end{array} } \right]
\text{ = }0
$$

### Projection Matrices

### Facts: 

## Assess Equations

### Describe set of S Points for Equation System
 * If equation is set equal to a value:
  * Linear Combinations/Span can fill at most n-1 dimensions in specified $R^n$ space.
   * Example: x - 5y + 2z = 9 can fill at most a 2d plane in 3d space.  Specifying the right side value has "n-1" d.f. type effect.
  * Identical equations set to different values cannot be solved simultaneously, and describe a situation of parallelism.

## Compute Jacobian of Matrix

### Steps:
* Using a Jacobian begins with two elements:
  * There will be a function that maps a column of inputs to a column of output functions.  Review which inputs map to which outputs.
  * A specific point at which to plot the Jacobian.
* Take partial derivatives:
  * Creat the Jacobian:
    * To create the first Jacobian row, take a partial derivative of the first output function w.r.t the first input variable.  Move across each column in the row, taking the derivative of the same output function w.r.t. each successive input variable.
    * Repeat this process for the next Jacobian row, using the next output function in order after the first, w.r.t. each successive input variable.
    * Repeat this process until all output variables have been process w.r.t each input variable.
  * Plug the coordinates for the given point into the derivative functions and process the resultant math.  The result is then the slope of a line in a subspace of $R^n$ which points toward the local maxima of the function.
 
## Assess Independence, Basis, Dimension

### Facts:

* The potential larges space A might occupy, prior to RRE, is its m rows.  C(A) is said to be in "m space".
* Only vectors can be said to be "in|dependent". This term cannot applie to matrices.
* Only vectors span a space.
 * The fact that vectors span a space says nothing about their independence.  
* Only vectors form a basis.
* The dimension is always a number.
  * we refer to the dimension of a column space C(A), not of a matrix
* If post RRE, r=n, then the number of vectors is "correct".  If m<n, not all vectors will be independent.  If r < n, the vectors will not span the complete potential space.
* A square matrix guarantees vector independence and therefore that the matrix is a basis for its m space.
  
### Assess Basis:

Vectors are a basis for a space or subspace if they:
* are independent (all the vectors in A must be independent to be a basis for anything)
* span the space; their linear combinations completely fill the specified dimension space of A

### Assess Dimension:

* The dimension of an m space (row count) is simply the post RRE rank of C(A).
  * we refer to the dimension of a column space C(A), not of a matrix
* The dimension of a nullspace N(A) is the number of independent columns in N(A).
  * Therefore, the dimension of N(A) is the number of its free variables.














