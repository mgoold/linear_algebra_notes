
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

## Example 8: Exchanged Matrix for Undefined Invertible Matrix

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* If columns 1 and 2 of invertible matrix A are exchanged, what is the effect on $A^{-1}$?

### Solutions
* If columns of an **invertible** matrix are exchanged, the the corresponding rows of $A^{-1}$ must also be exchanged in order for $AA^{-1}$ to remain equal to I .
      * This makes sense when you remember that to multiply matrices is essentially to take a series of dot products (a row multiplied by a column of equal length).  So if you move a column on a matrix A that has proven invertible, you have to move the corresponding row in its inverse $AA^{-1}$ in order to still generate the same 1 or 0 in the resulting matrix I.
      * I actually got caught thinking about whether Ax could still yield the same result when columns were switched, but that has nothing to do with this question.

## Example 9: 3x3 Elimination Matrices

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Give the 3x3 Matrices that produce these elimination steps:
   * $E_{21}$ subtracts 5 times row 1 from row 2.
   * $E_{32}$ subtracts -7 times row 2 from row 3.
   * P exchanges rows 1 and 2, then rows 2 and 3."

### Solutions

* $E_{21}:$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-5 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-5 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$ 

* $E_{32}:$

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -7 & 1 \\
\end{matrix}} 
\right]
$$ 

* $P_{21}:$

$$
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$ 

* $P_{32}:$

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0 \\
\end{matrix}} 
\right]
$$ 

* Applying $E_{21}$ and then $E_{32}$ to b = (1,0,0) gives

$$
E_{21}E_{32}b\text{ = }
\left[
{\begin{array}{cc}
1 \\
-5 \\
35 \\
\end{array}} 
\right]
$$

* Applying $E_{32}$  and then $E_{21}$ to b = (1,0,0) gives

$$
E_{21}E_{32}b\text{ = }
\left[
{\begin{array}{cc}
1 \\
-5 \\
0 \\
\end{array}} 
\right]
$$

When E_{32} comes first, row 3 feels no effect from row 1. ??


### Notes
* I think the answer for $E_{32}$ is actually in error; should be -7 not 7.
* Remember that when you show a progression of changes for a permutation matrix P:
      * "P" refers to the whole potential series of row swaps, each one swap having its own matrix.
      * When you show the series of swap matrices constituting P, you show the first one at the right, and the most recent change at the far left.  The final result is show on the right of the equals sign, and on the left, the right most "first" matrix is multiplied by the one to its left and so on, until you get the final result on the right side of the equal sign, viz:

$$
P\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0 \\
\end{matrix}} 
\right]
$$ 

* The solutions say that "When E_{32} comes first, row 3 feels no effect from row 1."  This is an odd and lazy way to put it.  It would be better say that third row of the result matrix from $E_{32}E_{21}$ and the first row of b don't interact, or that their product = 0.

## Example 10: 3x3 Elimination Matrices

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text:
* "Suppose E subtracts 7 times row 1 from row 3.
   * To invert that step you should do what?
   * What "inverse matrix $E^{-1}$ takes that reverse step so that $E^{-1}E\text{ = }I$ ?
   * If the reverse step is applied first (and then E) show that $EE^{-1}\text{ = }I$ ."

### Solutions

   * To invert that step you should do what? Multiply add 7 times row 1 to row 3.
   * What "inverse matrix $E^{-1}$ takes that reverse step so that $E^{-1}E\text{ = }I$ ?
   * If the reverse step is applied first (and then E) show that $EE^{-1}\text{ = }I$ ."

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
7 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
-7 & 0 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$ 

* the reverse also = I .

## Example 11: 2x2 Undefined Matrix Determinant

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text:
* "Suppose that matrix M is:

$$
\left[
{\begin{matrix}{cc}
a & b \\
c & d \\
\end{matrix}} 
\right]
$$ 

.  The determinant formula for a 2x2 matrix is ad - bc.  Multiply row 1 by l and subtract it from row 2 to create a new matrix $M^{\*}$ .  Show that the determinant formula ad - bc also applies to this new M and to every M so obtained.

### Solutions

* "Suppose the ne matrix $M^{\*}$ is:

$$
\left[
{\begin{matrix}{cc}
a & b \\
c-\ell{a} & d-\ell{b} \\
\end{matrix}} 
\right]
$$ 

Then the determinant is $a\left(d-\ell{b}\right)\text{ - }b\left(c-\ell{a}\right)$ , and $ad - a\ell{b} - bc + b\ell{a}$ --> $ad - a\ell{b} - bc + a\ell{b}$ -- ad - bc.  This should be true for any $\ell$ .

## Example 12: 3x3 Undefined Matrix E & P

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text and Solutions:
* Find a matrix M1 that both subtracts row 1 from row 2, and exchanges rows 2 and 3, in one step.
* Find a matrix M2 that exchanges rows 2 and 3 and subtracts row 1 from row 3, in one step.
* Explain why M1 and M2 are identical, but the Es they represent are different.  -- It's simply that the E in M2 causes the same effect by adjusting for the rows exchanged first by P so that it acts on the same values as in M1.

## Example 13: 3x3 Undefined Matrix E & P

### Sources
* ITLA Sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* Find a matrix M1 that adds row 1 to row 3 and **at the same time** adds row 3 to row 1.
* Find a matrix M2 that adds row 1 to row 3 **and then** adds row 3 to row 1.

### Solutions

$$
M1\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 1 \\
\end{matrix}} 
\right]
$$ 

$$
M2\text{ = }
\left[
{\begin{matrix}{cc}
2 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 1 \\
\end{matrix}} 
\right]
$$ 

## Example 13: 3x3 Undefined Matrix E & P

### Sources
* ITLA Sols, p30: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Why are there n! permutation matrices of order n? You can see that if you select any one row, the other n-1 rows remain to be selected, an when you select another row, n-2 rows remain to be selected &c.  

## Example 14: 3x3 Undefined Matrix E & P

### Sources
* ITLA Sols, p30: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* If $P_1$ and $P_2$ are permutation matrices, so is  $P_{1}P_{2}$ , and this product will still have the rows of I in some order.
* Give examples with :
      * $P_{1}P_{2}\neq{P_{2}P_{1}}$
      * $P_{3}P_{4}\neq{P_{4}P_{3}}$

### Solutions
* $P_{1}P_{2}\neq{P_{2}P_{1}}$

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\neq{}
\left[
{\begin{matrix}{cc}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0 \\
\end{matrix}} 
\right]
$$ 

* $P_{3}P_{4}\neq{P_{4}P_{3}}$

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0 \\
\end{matrix}} 
\right]
$$

## Example 15: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text and Solutions:
* "Give a reason that each is true or false:
      * A square matrix has no free variables.  False: it might be square, but under row reduction would have free variables.
      * An invertible matrix has no free variables.  True.  To be invertible, the matrix must be square, and must have a r=n=m pivot variables.
      * An m by n matrix has no more than n pivot variables.  True.  By definition, the potential pivot variables r are reckoned in terms of n.  But n might be less than m.
      * An m by n matrixs has no more than m pivot variables.  True.  Potential pivot variables are reckoned in terms of n, but to have r=n, m must be >= n.

## Example 16: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text:
* Put as many 1s and possible into a 4x7 updated matrix U with the following pivot columns:
      * 2,4,5
      * 1,3,6,7
      * 4,6

### Solutions:

* 2,4,5

$$
\left[
{\begin{matrix}{cc}
0 & 1 & 1 & 1 & 1 & 1 & 1 \\
0 & 0 & 0 & 1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

* 1,3,6,7

$$
\left[
{\begin{matrix}{cc}
1 & 1 & 1 & 1 & 1 & 1 & 1 \\
0 & 0 & 1 & 1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 0 & 1 \\
\end{matrix}} 
\right]
$$

* 4,6

$$
\left[
{\begin{matrix}{cc}
0 & 0 & 0 & 1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

## Example 17: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text:
* Put as many 1s as possible in a 4 by 8 RREF matrix R so that the free columns are:
      * 2,4,5,6
      * 1,3,6,7,8

### Solutions:
* 2,4,5,6 (pivots 1,3,7,8)

$$
\left[
{\begin{matrix}{cc}
1 & 1 & 0 & 1 & 1 & 1 & 0 & 9 \\
0 & 0 & 1 & 1 & 1 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
\end{matrix}} 
\right]
$$

* 1,3,6,7,8 (pivots 2,4,5)

$$
\left[
{\begin{matrix}{cc}
0 & 1 & 1 & 1 & 0 & 1 & 1 & 1 \\
0 & 0 & 0 & 1 & 0 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

### Notes
* the rule for this is that if it is a pivot column, you can clear all the values above the pivot.  Otherwise it reduces to 1 (or whatever).  Also every column before the first pivot has to be cleared to 0.

## Example 18: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text & Solutions:
* "Suppose column 4 of a 3 by 5 matrix is all zero.  Then $x_4$ is certainly a " answer: free variable.
* The special solution for this variable is the vector x = (0,0,0,1,0), because 1 will multiply that zero column to give Ax = 0.

## Example 19: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text & Solutions:
* "Suppose column 3 and 5 of a 3x5 matrix are the same (and not 0 columns).  Which column is a free variable? Answer: column 5.
* Find the special solution for this variable: (-1,0,0,0,1).

### Notes
* See that when 2 columns are the same, the first will be the pivot, and the second must be the free variable.  Because the free variable is 1, the pivot must be set to -1 to offset it.  Since column 5 is set to 1, all the other columns, whether pivot or free, would be set to 0.

## Example 20: Matrix Free and Pivot Variables

### Sources
* ITLA, 5th Ed., p143

### Problem Text & Solutions:
* Suppose an m by n matrix has r pivots.  The number of special solutions is: answer: n-r.
* The null space contains only x = 0 when : answer: r = n.  [Note that the matrix doesn't need to be square.]
* The column space is all of Rm when: answer: r = m.  [Again, note that the matrix doesn't need to be square.]

## Example 20: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p201

### Problem Text & Solutions:
* Suppose that S is a six-dimensional subspace of 9-dimensional space $R^9$ .
      * What are the possible dimensions of subspaces orthogonal to S?
         * Answer: If S is six-dimensional in R9, subspaces orthogonal to S can have dimensions 0, 1, 2, 3.  Note: the key here is to consider what basis S would have to have.  Since it's said to be six dimensions, it must really have 6 linearly independent columns out of 9.  This leaves up to 3 dimensions that can be orthogonal complements of S -- special solutions for N(A) for example.
      * What are the possible dimensions of the orthogonal complement $S^{\perp}$ of S?
         * Answer: the orthogonal complement must have a dimension of 3.  Note: by definition, an orthogonal complement contains every vector perpendicular to every vector in what it complements, so it has to have the full set of potential vectors in its basis.  It is the "largest orthogonal subspace".
      * What is the smallest size of a matrix A that has row space S?
         * Answer: the question says that it is row space S, so in order to actually be 6 dimensional, it must have a basis of 6 rows, because the dimension is by definition the number of independent vectors in a basis. -- but a row space includes the whole row, and the potential size was up to 9 dimensions, so the matrix must be at least size 6 by 9.
      * What is the smallest possible size of a matrix B that has nullspace $S^{\perp}$ ?
         * Answer: referencing the previous question, S is the 6x9 sized matrix just discussed,  In order for a matrix to have an orthogonal complement of $S^{\perp}$, it would have to be the same size S.  Therefore, B must be at least the same size as A.

## Example 21: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p201

### Problem Text:
* Construct any 2x3 matrix of rank 1.  Show the bases for each subspace.  Which vectors are orthogonal?

### Solutions

Example matrix:

$$
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
2 & 4 & 6 \\
\end{matrix}} 
\right]
$$

* C(A) : (1,2), dimension 1.
* R(A) : (1,2,3), dimension 1.
* N(A) : (-2,1,0),(-3,0,1), dimension 2.
* N(AT) : (2,-1), dimension 1.

* C(A) and N(A) are orthogonal, R(A) and N(AT) are orthogonal.

## Example 21: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p201

### Problem Text:
* Construct any 3,2 matrix of rank 2.  Show the bases for each subspace.  Which vectors are Z (zero vector)?

### Solutions:

Example matrix:

$$
\left[
{\begin{matrix}{cc}
1 & 2 \\
2 & 5 \\
3 & 6 \\
\end{matrix}} 
\right]
$$

* C(A) : (1,2),(2,5) dimension 2.
* R(A) : (1,2,3), (2,5,6), dimension 2.
* N(A) : empty.
* N(AT) : (2,0,-1), dimension 1.

## Example 22: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p201

### Problem Text and Solutions:

* "Construct a matrix with the required property, or say why it is impossible to have a matrix with that property."
      * Column space contains (1,2,3) and (2,3,5) and the nullspace contains (1,1,1).
         * Answer: the key word is "contains" -- this leaves the door open to having more than the 2 columns listed, so that it could be a 3x3 matrix and thus be multiplied times a 3x1 vector in its nullspace. The example matrix is then:

$$
\left[
{\begin{matrix}{cc}
1 & 2 & -3\\
2 & -3 & 1 \\
3 & 5 & -2 \\
\end{matrix}} 
\right]
$$

   * Rowspace contains (1,2,-3) and (2,-3,5), nullspace contains (1,1,1).  Note: all of these vectors are presented in column brackets in problem text.
      * Answer: the book says that this is impossible "because N(A) and C(A^T) aka R(A) are orthogonal subspaces."  The only way this makes sense to me is if it implies that we're disallowed from adding an additional column to the matrix when talking about rowspace -- we **could** add an additional column to the column space in other questions, when the matrix is described as "containing" columns.  If that is true then its also true that you can't multiply a 3x2 set of columns by a 3x2 nullspace vector, which is what you do with rows and the null space.
   * Every row is orthogonal to every column (A is not the zero matrix).
      * Answer: Note: in general it's good to try and do a 2x2 matrix to test questions like these so that you can try the most arrangements in the shortest time.  Also note that to say every row is orthogonal to every column is to say that every row times every column = 0.  Here is an example that works:

$$
B\text{ = }
\left[
{\begin{matrix}{cc}
1 & -1 \\
1 & -1 \\
\end{matrix}} 
\right]
$$ 

   * Columns add up to a column of zeros, rows add up to a column of 1s.
      * The book answer is that this can't be done; the actual wording is cryptic and I couldn't understand it.  Anyway I couldn't produce a 2x2 matrix that met the conditions.

## Example 22: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p201

### Problem Text:
* If AB = 0 then the columns of B are in the __________ of A.  The rows of A are in the _____________ of B.  With AB = 0, why can't A and B be 3x3 matrices of rank 2?

### Solutions:
* Nullspace
* Left Nullspace
* To say that an entire matrix is in the nullspace or left nullspace of another matrix is to say that they are orthogonal.  In order for entire matrices orthogonal, every row has to be orthogonal to every column.  If they were rank 2 3x3 matrices this would not be possible by definition.

## Example 23: Orthogonal Complements

### Sources
* ITLA, 5th Ed., p202

### Problem Text:
* "If Ax = b has a solution and $A^Ty\text{ = }0$, is $y^Tx\text{ = }0$ , or $y^Tb\text{ = }0$ ?"
* "If $A^Ty$ = (1,1,1) has a solution and Ax = 0, what does that tell us?"

### Solutions:
* "If Ax = b has a solution and $A^Ty\text{ = }0$, is $y^Tx\text{ = }0$ , or $y^Tb\text{ = }0$ ?"
      * Answer: If Ax = b has a solution, then by definition b is in C(A).  If $A^Ty\text{ = }0$ , then y is perpendicular to $A^T$ by definition of dot product.  To be perpendicular, it must be a horizontal matrix.  Since b is in C(A), and y is a horizontal matrix, they must be perpendicular to each other.  Therefore $b^Ty\text{ = }0$ .  Further, the solutions book says that $b^Ty\text{ = }left(Ax\right)^Ty\text{ = }x^T\left(A^t\right)y\text{ = }0$ .  This is so because:
         * we already demonstrated that $b^Ty\text{ = }0$
         * by extension, Ax is the column space of A and Ax = b, so it follows that $left(Ax\right)^Ty\text{ = }0$ .
         * by the rules of transformation, $left(Ax\right)^T$ = $x^T\left(A^t\right)$, so it follows that $x^T\left(A^t\right)y\text{ = }0$ .
* "If $A^Ty$ = (1,1,1) has a solution and Ax = 0, what does that tell us?"
      * Answer: "If $A^Ty$ = (1,1,1) has a solution, then that solution is a linear combination of the rows of A and is in R(A).  It must therefore be orthogonal to every x in the nullspace."
         * This is one of those things where its so obvious that it can be hard to tell what response the question wants to elicit.  First of all, realize that $A^Ty$ is a way of describing the rowspace, variously called R(A) or $C\left(A^T\right)$ .  It seems weird that when we talk about columns space, we're multiply rows of A times the column x, and when we're talking of rowspace, we transpose the rows into columns and multiply across their rows (what would be the columns of A) times the column vector y.  But anyway, just as if b is a solution to Ax = b it is in C(A), so too if $A^Ty$ = (1,1,1) has solution, it must be in R(A).  But R(A) is perpendicular to the nullspace, and therefore the solution to $A^Ty$ = (1,1,1) must be perpendicular to every x in N(A).

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

## Example 5: Transposed Block Matrix

### Sources
* ITLA sols, p30: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* The transpose of a block matrix M =

$$
\left[
{\begin{matrix}{cc}
A & B \\
C & D \\
\end{matrix}} 
\right]
M^T\left{ = }
\left[
{\begin{matrix}{cc}
A & C \\
B & D \\
\end{matrix}} 
\right]
$$

... what conditions on A,B,C,D would the block matrix be symmetric? 

#### Solutions:
* You can see that A and D have to be the same when transposed, and that C and B have to equal each other when transposed.

## Example 6: Transposed Block Matrix 2

### Sources
* ITLA sols, p30: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* True of false:
      * the block matrix
  
$$
\left[
{\begin{matrix}{cc}
0 & A \\
A & 0 \\
\end{matrix}} 
\right]
$$

is automatically symmetric.  False: A would itself need to be symmetric but doesn't have to be.
* If A and B are symmetric then their product AB is symmetric. False.  The transpose of AB is $B^TA^T\text{ = }BA$ , so $\left(AB\right)^T\text{ = }AB$ needs BA = AB.
   * Note: what the textbook answer is getting at is that if a matrix is truly symmetric then A = $A^T$, and if that's true then the product AB must also equal $B^TA^T$ , which would mean that AB = BA, which is often not the case.
* If A is not symmetric then $A^{-1}$ is not symmetric .  True.
* When A,B,C are symmetric, the transpose of ABC is CBA. True.

## Example 7: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "Suppose the 3x3 matrix A is invertible.  Write down the bases for the four subspaces for A, and also for the 3 by 6 matrix B = [A A] .

### Solutions
* All invertible matrices reduce to I in RREF form.  Therefore for the 3x3 invertible matrix A:
   * The basis for C(A) will be all columns, and the basis for R(A) will be all rows, each having 3 dimensions.
   * The basis for N(A) and N(A^T) will be empty (or the 0 vector, depending on how you want to describe it).
* For B = [A A]
   * The basis for C(A) is not change, but now either of 2 duplicate columns can be used so long as you get a unique combination of the 3 columns.
   * It is not possible to eliminate any rows, so the basis for R(A) is still all the rows of A.
   * N(A) will have 3 special solutions for the 3 free columns, each one matching the same column in A as 1,-1 and all other columns being 0.
   * N(A^T) will be empty.

## Example 8: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "What are the dimension of the 4 subspaces for A,B,C if I is the 3x3 identity matrix and 0 is the 3x2 0 matrix for the following matrices:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
I & 0 \\
\end{matrix}} 
\right]
\text{, }B\text{ = }
\left[
{\begin{matrix}{cc}
I & I \\
{0^T} & {0^T} \\
\end{matrix}} 
\right]
\text{, }C\text{ = }
\left[
{\begin{matrix}{cc}
0 \\
\end{matrix}} 
\right]
$$

### Solutions
* For A dimensions:
      * C(A): 3, R(A): 3, N(A): 2, N(A^T): empty
* For B dimensions:
      * C(B): 3, R(B): 3, N(B): 3, N(B^T): 2
* For C dimensions:
      * C(B): 0, R(B): 0, N(B): 2, N(B^T): 3

### Notes
* for the 3x2 0 grid: the nullspace and left nullspace are not empty.  The reason is that since all the rows are 0, "ironically" any non-zero vector could be multiplied with them to yield a 0 dot product.
* All the columns and rows being 0 is also why the nullspace and left nullspace is equal to the respective full row or column count of the 0 grid -- the grid is sort of nothing but free variables.

## Example 9: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "Which subspaces are the same for these matrices of differing sizes?"

$$
\left(a\right)
\left[
{\begin{matrix}{cc}
A \\
\end{matrix}} 
\right]
\text{ and }
\left[
{\begin{matrix}{cc}
A \\
A \\
\end{matrix}} 
\right]
\left(b\right)
\left[
{\begin{matrix}{cc}
A \\
A \\
\end{matrix}} 
\right]
\text{ and }
\left[
{\begin{matrix}{cc}
A & A \\
A & A \\
\end{matrix}} 
\right]
$$

... prove that all 3 of these matrices have the same rank r."

### Solutions

* For a, R(A) and N(A) should be the same.
* For b, C(A) and N(A^T) should be the same.
* When you create a matrix by duplicating a matrix either beside or below its original, all of the duplicate rows or columns thus generated will go into the nullspace or left nullspace of the matrix. This is why the rank r of the original matrix will remain unchanged.

## Example 10: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "If the entries of a 3x3 matrix A are chosen randomly between 0 and 1, what are the most likely dimensions of the four subspaces?"
* "What if this random matrix A is 3x5?"

### Solutions
* The most likely configuration is the identiy matrix I, because if you have at least one 1 in each diagonal position you can rowref until you get I and there is a better than 50% change of this being the case.  Then C(A) and R(A) dimension = 3, and N(A) and N(A^T) dimensions = 0.
* Same thing, but now you are most likely to have 2 free variables, so N(A) dimension = 2, N(A^T) dimensions = 0.

# 2x2 Defined Matrix

## Example 1: Matrix Spaces

### Sources
* ITLA, 5th Ed., P131

### Problem Text
"The matrix A = 

$$
\left[
{\begin{matrix}{cc}
2 & -2 \\
2 & -2 \\
\end{matrix}} 
\right]
$$

is a "vector" in the space M of all 2x2 matrices.  
* Write down the 0 vector for this space, the vector $\frac{1}{2}A$, and the vector -A.
* What matrices are in the smallest subspace containing A?

### Solutions
* This is so easy you overthink it.  The 0 vector, $\frac{1}{2}A$, and -A are:

$$
0\text{ = }
\left[
{\begin{matrix}{cc}
0 & 0 \\
0 & 0 \\
\end{matrix}} 
\right]
\text{, }\frac{1}{2}A\text{ = }
\left[
{\begin{matrix}{cc}
1 & {-1} \\
1 & {-1} \\
\end{matrix}} 
\right]
-A\text{ = }
\left[
{\begin{matrix}{cc}
-2 & 2 \\
-2 & 2 \\
\end{matrix}} 
\right]
$$

* What matrices are in the smallest subspace containing A?

Answer: the smallest subspace is cA -- it is also the largest subspace.  The point is to think about the definition of the subspace, and whether it is divisible.  In this case, you can't have less or more than a 2x2 matrix, so cA is the subspace.  A subspace is a space that stays closed under all linear combinations, while obeying the definition constraints of the larger space.  So if the initial space were "R2", then a subspace could be a 2x2 matrix or a line for example, so long as they went through the origin.

## Example 2: Matrix Spaces

### Sources:
* ITLA, 5th ed, p131.

### Problem Text
* "Describe a subspace of M [the space of 2x2 matrices in R] that contains

$$
M\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
0 & 0 \\
\end{matrix}} 
\right]
$$

but not 

$$
M\text{ = }
\left[
{\begin{matrix}{cc}
0 & 0 \\
0 & -1 \\
\end{matrix}} 
\right]
$$

* If a subspace of M does contain A and B, must it contain I?
* Describe a subspace of M that contains no non-zero matrices."

### Solutions

* Describe a subspace of M that contains...
  * cA should be such a subspace, because it could go on the origin, and be added to itself, and would never contain B.
* If a subspace of M does contain A and B, must it contain I?
  * I believe so, because if they're both in the subspace then you should be able to add A and B together, which you could then change to I.
* Describe a subspace of M that contains no nonzero diagonal matrices.
   * I think $A^2$ should be an example.  The answer from the book is "matrices whose main diagonal is all 0."




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

# Defined Matrix > 2x2

## Matrix Elimination Example 1

### Source
* ITLA sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf
  
### Problem Text:
* "Which of the 3 matrices $E_{21}E_{31}E_{32}$ put A into triangular form U?

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 0 \\
4 & 6 & 1 \\
-2 & 2 & 0 \\
\end{matrix}} 
\right]
\text{ and }
E_{32}E_{31}E_{21}A\text{ = }EA\text{ = }U\text{.}
$$

* Include b = (1,0,0) as a fourth column to A in order to produce augmented matrix [A b] ,  Carry out the elimination steps on this augmented matrix to solve Ax = b."
* Suppose $A_{33}$ = 7, so that the 3rd pivot is 5.  If you change $A_{33}$ to 11, what is the third pivot?  What value for $A_{33}$ will give no pivot?

### Solutions

$$
E_{32}E_{31}E_{21}\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-4 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
2 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -2 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-4 & 1 & 0 \\
10 & -2 & 1 \\
\end{matrix}} 
\right]
$$

* Multiplying these in reverse order gives $E^{-1}$, which will restore the matrix to its original form.
* Including b = (1,0,0) in an augmented matrix [A b] b and applying the above matrix E will give you b = (1, -4, 10).  Then back substitution gives you z = -5, y = $\frac{1}{2}$ , and x = $\frac{1}{2}$ . This solves Ax = (1,0,0).
* Suppose $A_{33}$ = 7, so that the 3rd pivot is 5.  If you change $A_{33}$ to 11, what is the third pivot? Answer: 9.  What value for $A_{33}$ will give no pivot? Answer: 2. 


### Notes
* I'd forgotten how to do this.  Remember that by doing elimination on [A b], all you're doing is performing the elimination steps for the coefficients on both sides of the equation for A and b in Ax = b.  This is just what you'd have to do if you were solving any equation anyway, but it's easier to process as an augmented matrix.

## Matrix Elimination Example 2

### Source
* ITLA sols, p22: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf
  
### Problem Text:
* "Suppose every column of A is a multiple of (1,1,1), for example:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
1 & 2 & 3 \\
1 & 2 & 3 \\
\end{matrix}} 
\right]
$$

... then Ax will always be a multiple of (1,1,1).  In the above example, how many pivots are produced by elimination? 

### Solutions
* Because the rows are duplicates, only $A_{11}$ can remain as a pivot.

## Example 1: Matrix Multiplication

### Source
* ITLA v6, 1.3: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text
"Muluply Az and By and Iz using dot products as in $\left(\text{rows of A}\right)\cdot{x}$ :"

$$
Ax\text{ = }
\left[
{\begin{matrix}{cc}
2 & 1 & 2 \\
4 & 2 & 4 \\
0 & 1 & 0 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
1 \\
2 \\
5 \\
\end{array}} 
\right]
\text{, By = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
1 & 1 & 0 \\
1 & 1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
4 \\
4 \\
10 \\
\end{array}} 
\right]
\text{, Ix = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
z_1 \\
z_2 \\
z_3 \\
\end{array}} 
\right]
$$

### Solutions
* The first matrix reduces considerably, after which Ax = (6,2,0).
* Matrices B and I reduce to the identity matrix, so their products are the same as their respective x vectors.

## Example 2: Matrix Multiplication 2

### Source
* ITLA v6, 1.3: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text:
* "Multiply the same A times x and B times y and I times 2z using combinations of the columns of A and B and I, as in Az = 1(column 1) + 2(column 2) + 5(column 3)."

### Solutions:
* Yields the same results as in example 1.

## Example 3: Matrix Multiplication 3

### Source
* ITLA v6, 1.4: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf
* https://catonmat.net/mit-linear-algebra-part-three

### Problem Text:

"The following table shows the various approaches for multiplying 2 matrices $A_{mxn}$ and $B_{nxp}$ :

|Method      |Description   |
|:-----------|:-------------|
|dot product (rows times columns)     |Multiply each row of A times each column of b as a dot product.  Results in m x p columns resulting in mxp dot products. |
|column     |Multiply the columns of A times each scalar in a column of b, and add the scaled columns, as with a linear combination cv + dw ... .  Results in p columns of m rows. |
|row     |Multiply a row of A times each successive column (vector) of B, as with Ax multiplication.  Do it across the row, then move to next row.  Results in p columns of m rows. No substantive difference vs dot product method.|
|columns times rows     |Multiply each A column times corresponding row of B, resulting in a row C of dot products.  Results in 2 rank 1 matrices that are then summed together. |

"Rewrite this four-way table for AB = C when A is m by n and B is n by p."

### Solutions:
* See mxn notes in table above.

## Example 4: Matrix Multiplication 4

### Source
* ITLA v6, 1.4: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf
* https://catonmat.net/mit-linear-algebra-part-three

### Problem Text:
* "If all columns of A = [ a a a ] contain the same a # 0. what are C and R ?"

### Solutions:
* The RRE form of A (aka R) should reduce to a single row, with 2 free variable columns. A is a rank 1 matrix.  Therefore, C will be the independent column, and R will be the top (independent row).

## Example 5: Matrix Multiplication 5

### Source
* ITLA v6, 1.4: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf
* https://catonmat.net/mit-linear-algebra-part-three

### Problem Text:
* "Multiply A times B for each of the 3 examples below by using dot products: (each row) $\cdot$ (each column)."

$$
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
1 & 1 & 0 \\
1 & 1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-1 & 1 & 0 \\
1 & -1 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$

$$
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
4 \\
5 \\
6 \\
\end{matrix}} 
\right]
\text{ = }
32
$$

$$
\left[
{\begin{matrix}{cc}
4 \\
5 \\
6 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
4 & 8 & 12 \\
5 & 10 & 15 \\
6 & 12 & 18 \\
\end{matrix}} 
\right]
$$

### Solutions:
* See above.

## Example 6: Matrix Multiplication 6

### Source
* ITLA v6, 1.4: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text:
* "Test the truth of the associative law (AB)C = A(BC) :"

$$
\left[
{\begin{matrix}{cc}
1 & 1 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
1 \\
1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
\end{matrix}} 
\right]
$$

### Solutions
* (AB)C : AxB = 2; 2[1 1 1] = [2 2 2]
* A(BC) : This is tricker.  The solution is given in the book, but I don't see how you get to it.

## Example 7: Matrix Multiplication 7

### Source
* ITLA v6, 1.4: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text:
* "Why is it impossible for a matrix A with 7 columns and 4 rows to have 5 independent columns?"

### Solution
* There are not enough rows for each unique variable in the row to make a "unique contribution" for the dimension that it adds to the others, so 3 columns must end up being derivative of the 4 pivot columns.

## Matrix LU Decomposition Example 1

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Suppose we have a matrix

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 5 \\
1 & 2 & 7 \\
\end{matrix}} 
\right]
$$

* What matrix eliminates the pivot at $A_{21}$?
* What matrix L reverses that step?
* Show this reversal by multiplying it times [U c] to get [A b]
* Write the 2 triangular systems Lc = b, and Ux = c . Check the first, and find x for the second.

### Solutions:

* What matrix eliminates the pivot at $A_{21}$?
  
$$
E\text{ = }E_{21}\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
-1 & 1 \\
\end{matrix}} 
\right]
$$
  
* What matrix L reverses that step?

$$
L\text{ = }-E_{21}\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
1 & 1 \\
\end{matrix}} 
\right]
$$

* Show this reversal by multiplying it times [U c] to get [A b]

$$
L\text{ = }-E_{21}\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 1 & 5 \\
0 & 1 & 2\\
\end{matrix}} 
\right]
\rightarrow
\left[
{\begin{matrix}{cc}
1 & 1 & 5 \\
1 & 2 & 7\\
\end{matrix}} 
\right]
$$

* Write the 2 triangular systems Lc = b, and Ux = c . Check the first, and find x for the second.

$$
Lc\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
5 \\
2 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
5 \\
7 \\
\end{array}} 
\right]
\text{ = }b
$$

$$
Ux\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 \\
0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
5 \\
2 \\
\end{array}} 
\right]
\text{, }
\left[
{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
3 \\
2 \\
\end{array}} 
\right]
$$

## Matrix LU Decomposition Example 2

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Given the matrix:

$$
A
\text{ = }
\left[
{\begin{matrix}{cc}
2 & 1 & 0 \\
0 & 4 & 2 \\
6 & 3 & 5 \\
\end{matrix}} 
\right]
$$

* Give the matrix E that puts A into triangular form.
* Find L to show the LU decomposition.

### Solutions:

* Give the matrix E that puts A into triangular form.

$$
E\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
-3 & 0 & 1 \\
\end{matrix}} 
\right]
$$

* Find L to show the LU decomposition.

$$
LU\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
3 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
2 & 1 & 0 \\
0 & 4 & 2 \\
0 & 0 & 5 \\
\end{matrix}} 
\right]
$$

## Matrix LU Decomposition Example 3

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Given the matrix A:

$$
A
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
2 & 4 & 5 \\
0 & 4 & 0 \\
\end{matrix}} 
\right]
$$

... 
* Find the two elimination matrices that put A into upper triangular form $E_{32}E_{21}A\text{ = }U$ . 
* Multiply by $E_{32}^{-1}$ and $E_{21}^{-1}$ to factor A into $LU\text{ = }E_{21}^{-1}E_{32}^{-1}U$

### Solutions

* Find the two elimination matrices that put A into upper triangular form $E_{32}E_{21}A\text{ = }U$ .
  
$$
E_{32}E_{21}A
\text{ = }
\left[
{\begin{array}{cc}
1 & 0 & 0 \\
-2 & 1 & 0 \\
0 & 0 & 1 \\
\end{array}} 
\right]
\left[
{\begin{array}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -2 & 1 \\
\end{array}} 
\right]
\left[
{\begin{array}{cc}
1 & 1 & 1 \\
2 & 4 & 5 \\
0 & 4 & 0 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
1 & 1 & 1 \\
0 & 2 & 3 \\
0 & 0 & -5 \\
\end{array}} 
\right]
\text{ = }U
$$

* Multiply by $E_{32}^{-1}$ and $E_{21}^{-1}$ to factor A into $LU\text{ = }E_{21}^{-1}E_{32}^{-1}U$

$$
A\text{ = }
LU\text{ = }
\left[
{\begin{array}{cc}
1 & 0 & 0 \\
2 & 1 & 0 \\
0 & 2 & 1 \\
\end{array}} 
\right]
\left[
{\begin{array}{cc}
1 & 1 & 1 \\
0 & 2 & 3 \\
0 & 0 & -5 \\
\end{array}} 
\right]
$$

## Matrix LU Decomposition Example 3

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Given the matrix A:

$$
A
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 1 \\
2 & 2 & 2 \\
3 & 4 & 5 \\
\end{matrix}} 
\right]
$$

* Show the 3 E matrices that turn A into U
* Show the LU factorization of A."

### Solutions:

* Show the 3 E matrices that turn A into U

$$
E_{32}E_{31}E_{21}A
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -2 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
-3 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-2 & 1 & 0 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 1 \\
2 & 2 & 2 \\
3 & 4 & 5 \\
\end{matrix}} 
\right]
$$

* Show the LU factorization of A."

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 1 \\
2 & 2 & 2 \\
3 & 4 & 5 \\
\end{matrix}} 
\right]
\text{ = }
LU
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
2 & 1 & 0 \\
3 & 2 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 1 \\
0 & 2 & 0 \\
0 & 0 & 2 \\
\end{matrix}} 
\right]
$$

## Matrix LU Decomposition Example 4

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Compute L and U for the symmetric matrix A:"

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
a & a & a & a \\
a & b & b & b \\
a & b & c & c \\
a & b & c & d \\
\end{matrix}} 
\right]
$$

### Solution 

$$
LU\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 1 & 0 \\
1 & 1 & 1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
a & a & a & a \\
0 & b-a & b-a & b-a \\
0 & 0 & c-b & c-b \\
0 & 0 & 0 & d-c \\
\end{matrix}} 
\right]
$$

## Matrix LU Decomposition Example 5

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Compute L and U for the symmetric matrix A:"

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
a & r & r & r \\
a & b & s & s \\
a & b & c & t \\
a & b & c & d \\
\end{matrix}} 
\right]
$$

### Solutions

$$
LU\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 1 & 0 \\
1 & 1 & 1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
a & r & r & r \\
0 & b-r & s-r & s-r \\
0 & 0 & c-s & t-s \\
0 & 0 & 0 & d-t \\
\end{matrix}} 
\right]
$$

## Matrix LU Decomposition Example 6

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 
* "Solve the triangular system Lc =b to find c.  Then solve Ux = c to find x:

$$
L\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
4 & 1 \\
\end{matrix}} 
\right]
\text{ and }U\text{ = }
\left[
{\begin{matrix}{cc}
2 & 4 \\
0 & 1 \\
\end{matrix}} 
\right]
\text{ and }b\text{ = }
\left[
{\begin{array}{cc}
2 \\
11 \\
\end{array}} 
\right]
$$

### Solution

$$
Lc\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
4 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
2 \\
3 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
2 \\
11 \\
\end{array}} 
\right]
\text{ = }b
$$

$$
Ux\text{ = }
\left[
{\begin{matrix}{cc}
2 & 4 \\
0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
2 \\
3 \\
\end{array}} 
\right]
\text{; = }x_1\text{ = }-5\text{;}x_2\text{ = }3
$$

## Matrix LU Decomposition Example 7

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 

* "Given the matrices:

$$
L\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
1 & 1 & 0 \\
1 & 1 & 1 \\
\end{matrix}} 
\right]
\text{ and }U\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
0 & 1 & 1 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
\text{ and }b\text{ = }
\left[
{\begin{array}{cc}
4 \\
5 \\
6 \\
\end{array}} 
\right]
$$

* "Solve Lc = b to find c.  Then solve Ux = c to find x.  What was A?

##
c\text{ = }
\left[
{\begin{array}{cc}
4 \\
1 \\
1 \\
\end{array}} 
\right]
\text{, }x\text{ = }
\left[
{\begin{array}{cc}
3 \\
0 \\
1 \\
\end{array}} 
\right]
\text{, }A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
1 & 2 & 2 \\
1 & 2 & 3 \\
\end{matrix}} 
\right]
$$



## Matrix LDU Decomposition Example 1

### Source:
* ITLA Sols, p27: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text 

* "Given the matrices

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 4 \\
4 & 11 \\
\end{matrix}} 
\right]
\text{, B = }
\left[
{\begin{matrix}{cc}
1 & 4 & 0 \\
4 & 12 & 4 \\
0 & 4 & 0 \\
\end{matrix}} 
\right]
$$

* Show the triple LDU factorizations of each.
* Say how U is related to L for these symmetric matrices."

### Solutions

* Show the triple LDU factorizations of each.

$$
LDU_A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
2 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
2 & 0 \\
0 & 3 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 2 \\
0 & 1 \\
\end{matrix}} 
\right]
$$

$$
LDU_B\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
4 & 1 & 0 \\
0 & -1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & -4 & 0 \\
0 & 0 & 4 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 4 & 0 \\
0 & -1 & -1 \\
0 & 0 & 1 \\
\end{matrix}} 
\right]
$$

## Matrix Special Solutions Example 1

### Sources
* ITLA 5th Ed., p.141.

### Problem Text

* "Reduce A and B to their triangular forms U.  Which variables are free?

   $$
   A\text{ = }
   \left[
   {\begin{matrix}{cc}
   1 & 2 & 2 & 4 & 6 \\
   1 & 2 & 3 & 6 & 9 \\
   0 & 0 & 1 & 2 & 3 \\
   \end{matrix}} 
   \right]
   \text{,  }B\text{ = }
   \left[
   {\begin{matrix}{cc}
   1 & 4 & 2 \\
   0 & 4 & 4 \\
   0 & 8 & 8 \\
   \end{matrix}} 
   \right]  
   $$

* Find a special solution for each matrix.
* Further reduce U to R for each matrix.  State whether N(R) = N(U), and if so why.

### Solutions:

   * U and R forms:
     
   $$
   U_{A}\text{ = }
   \left[
   {\begin{matrix}{cc}
   1 & 2 & 2 & 4 & 6 \\
   0 & 0 & 1 & 2 & 3 \\
   0 & 0 & 0 & 0 & 0 \\
   \end{matrix}} 
   \right]
   \text{,  }U_{B}\text{ = }
   \left[
   {\begin{matrix}{cc}
   2 & 4 & 2 \\
   0 & 0 & 2 \\
   0 & 0 & 0 \\
   \end{matrix}} 
   \right]  
   $$

   $$
   R_{A}\text{ = }
   \left[
   {\begin{matrix}{cc}
   1 & 2 & 0 & 0 & 0 \\
   0 & 0 & 1 & 2 & 3 \\
   0 & 0 & 0 & 0 & 0 \\
   \end{matrix}} 
   \right]
   \text{,  }R_{B}\text{ = }
   \left[
   {\begin{matrix}{cc}
   1 & 0 & -1 \\
   0 & 1 & 1 \\
   0 & 0 & 0 \\
   \end{matrix}} 
   \right]  
   $$


* For $U_A$ , columns 2,4,5 are free, for $U_B$ ,  column 3 is free .
* Special solutions:
      * Remember that the number of special solutions = number of free variables = n - r.
      * For $U_A$ : (-2,1,0,0,0), (0,0,-2,1,0), (0,0,-3,0,1) .
      * For $U_B$ : (1,-1,1)

* See above for RREF forms.  N(R) = N(U) = N(A), because row reduction does not change the mathematical relationships of the equations to each other.

## Matrix Special Solutions Example 2

### Sources
* ITLA 5th Ed., p.141.

### Problem Text

* "For the following matrices A and B, find the special solutions to Ax = 0 and Bx = 0.

   $$
   A\text{ = }
   \left[
   {\begin{matrix}{cc}
   -1 & 3 & 5 \\
   -2 & 6 & 10 \\
   \end{matrix}} 
   \right]
   \text{,  }B\text{ = }
   \left[
   {\begin{matrix}{cc}
   -1 & 3 & 5 \\
   -2 & 6 & 7 \\
   \end{matrix}} 
   \right]
   $$

  * For A: (3,1,0), (5,0,1) .  For B: (3,1,0)
 
## Matrix Complete Solutions Example 1

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "Given the matrix equation Ax = b:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
2 & 4 & 6 & 4 \\
2 & 5 & 7 & 6 \\
2 & 3 & 5 & 2 \\
\end{matrix}} 
\right]
x\text{; b = }
\left[
{\begin{array}{cc}
4 \\
3 \\
5 \\
\end{array}} 
\right]
$$

... 

* find the column space of A
* find the null space of A
* find the complete solution to Ax = b."

### Solutions

* First, [U c] =

$$
\left[
{\begin{matrix}{cc}
2 & 4 & 6 & 4 & b_1 \\
0 & 1 & 1 & 2 & b_2\text{ - }b_1 \\
0 & 0 & 0 & 0 & b_2\text{ - }2b_1\text{ + }b_2 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
2 & 4 & 6 & 4 & 4 \\
0 & 1 & 1 & 2 & -1 \\
0 & 0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

...So:
* the first 2 columns are the pivot columns, and the first 2 corresponding columns of A are the column space C(A).
* toggling the free variable columns 3,4 to 1 and 0, and back substituting in U, the nullspace is all combinations $c_1s_1$ = (-1,-1,1,0) and $c_2s_2$ = (2,-1,0,1) .
* further reducing [U c] to [R d] and back-substituting in R where columns 3 and 4 variables are 0, we get $x_p$ = (4,-1,0,0).  The complete solution is then $x_p\text{ + }c_1s_1\text{ + }c_2s_2$ .

## Matrix Complete Solutions Example 2

### Sources
* ITLA 5th Ed., p.158.

### Problem Text

* "For the matrix

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
2 & 1 & 3 \\
6 & 3 & 9 \\
4 & 2 & 6 \\
\end{matrix}} 
\right]
$$

and b = (10,30,20) ...

Find the pivot columns, column space, [U c], [R d], and complete solution."

### Solutions

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
2 & 1 & 3 & 10\\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

So column 1 is the pivot column, and (2,6,4) is C(A).  The null space is s1 = (-1/2,1,0), s2 = (-3/2,0,1) .

$$
\[R d\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & \frac{1}{2} & \frac{3}{2} & 5\\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

So $x_p$ = (5,0,0) and the complete solution is $x_p\text{ + }c_1s_1\text{ + }c_2s_2$ .

## Matrix Complete Solutions Example 3

### Sources
* ITLA 5th Ed., p.158.

### Problem Text

* "For the matrix

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 3 & 1 \\
2 & 6 & 9 & 5 \\
-1 & -3 & 3 & 5 \\
\end{matrix}} 
\right]
$$

and b = (1,5,5) ...

find the pivot columns, column space, [U c], [R d], and complete solution."

### Solutions

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 3 & 1 \\
0 & 0 & 3 & 3 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

... so the pivot columns are 1 and 3, and C(A) = (1,2-1), (3,9,3) .  The nullspace $c_1_s_1$ = (-3,1,0) .

$$
\[R d\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 0 & -2 \\
0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

and $x_p$ = (-2,0,1) .  The complete solution = $x_p\text{ + }c_1_s_1$ .

## Matrix Complete Solutions Example 4

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "Given the matrix:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 1 & 2 \\
2 & 6 & 4 & 8 \\
0 & 0 & 2 & 4 \\
\end{matrix}} 
\right]
$$

and b = (1,3,1) ... find the pivot columns, column space, [U c], [R d], and complete solution."

### Solution

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 1 & 1 & 1\\
0 & 0 & 2 & 4 & 1\\
0 & 0 & 0 & 0 & 0\
\end{matrix}} 
\right]
$$

* pivot columns are 1,3.  C(A) is (1,2,0), (1,4,2).  N(A) = (-3,1,0,0), (0,0,-2,1) .
* $x_p$ = (1/2,0,1/2,0)

## Matrix Complete Solutions Example 5

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "Given the matrix:

$$
\[A b\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & -2 & b_1 \\
2 & 5 & -4 & b_2 \\
4 & 9 & -8 & b_3 \\
\end{matrix}} 
\right]
$$

under what conditions is this system solvable? Include b as a fourth column in elimination.  Find all solutions when that condition holds."

### Solution:

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & -2 & {b_1} \\
0 & 1 & 0 & {b_2\text{ - }2b_1} \\
0 & 0 & 0 & {b_3\text{ - }2b_1\text{ - }b_2} \\
\end{matrix}} 
\right]
$$

Since the coefficient matrix 0s out, it is a "solvability condition", and ${b_3\text{ - }2b_1\text{ - }b_2}$ must = 0 for the system to be solvable.

Further reducing the augmented matrix to [R d] we get:

$$
\[R d\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & -2 & {5b_1\text{ - }2b2} \\
0 & 1 & 0 & {b_2\text{ - }2b_1} \\
0 & 0 & 0 & {b_3\text{ - }2b_1\text{ - }b_2} \\
\end{matrix}} 
\right]
$$

Remember that for the "x particular" part of a complete solution to Ax = b, we set the free variable to 0.  So then x_p = 

$$
\left[
{\begin{array}{cc}
{5b_1\text{ - }2b2} \\
{b_2\text{ - }2b_1} \\
0 \\
\end{array}} 
\right]
$$

and x_s = (2,0,1) .

### Notes
* when you see the "include column b as a column" qualifiication, it indicates that you should solve with b as an augmented matrix in the usual way, except with all variables.  This allows you to specify x_p purely in terms of b variables (not actual values), but also specify x_s in the normal way of setting all equations in [U c] to 0 and using back-substitutions.
* when you have multiple rows in the coefficient matrix that 0 out, you can represent them as just one 0 in the bottom of your x_p matrix.

## Matrix Complete Solutions Example 6

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "Given the matrix A:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 \\
2 & 4 \\
2 & 5 \\
3 & 9 \\
\end{matrix}} 
\right]
$$

with $b\text{ = \left(b_1,b_2,b_3,b_4\right) , what conditions on b make the system solveable.  Find x in this solveable case.

### Solutions:

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & b_1 \\
0 & 1 & b_3\text{ - }2b_1 \\
0 & 0 & b_4\text{ - }3b_3\text{ + }3b_1 \\
0 & 0 & b_2\text{ - }2b_1\\
\end{matrix}} 
\right]
$$

... so solvability contions are $b_4\text{ - }3b_3\text{ + }3b_1$ = 0 and $b_2\text{ - }2b_1$ = 0 .  There are no free variables, so reducing [U c] to [R d] gives us

$$
\[R d\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 5b_1\text{ - }2b_2 \\
0 & 1 & b_3\text{ - }2b_1 \\
0 & 0 & b_4\text{ - }3b_3\text{ + }3b_1 \\
0 & 0 & b_2\text{ - }2b_1\\
\end{matrix}} 
\right]
$$

.  Then $x_p$ = 

$$
\left[
{\begin{array}{cc}
5b_1\text{ - }2b_2 \\
b_3\text{ - }2b_1 \\
0 \\
\end{array}} 
\right]
$$

## Matrix Complete Solutions Example 7

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "Given the matrix A:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
2 & 4 & 6 \\
2 & 5 & 7 \\
3 & 9 & 12 \\
\end{matrix}} 
\right]
$$

with $b\text{ = \left(b_1,b_2,b_3,b_4\right) , what conditions on b make the system solveable.  Find x in this solveable case.

### Solutions

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 3 & b_1 \\
0 & 1 & 1 & b_3\text{ - }2b_1 \\
0 & 0 & 0 & b_4\text{ - }3b_3\text{ + }4b_1 \\
0 & 0 & 0 & b_2\text{ - }2b_1 \\
\end{matrix}} 
\right]
$$

... so the solvability conditions are $b_4\text{ - }3b_3\text{ + }4b_1$ = 0 and $b_2\text{ - }2b_1$ = 0.  Then [R d] =

$$
\[R d\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 1 & 5b_1\text{ - }2b_1 \\
0 & 1 & 1 & b_3\text{ - }2b_1 \\
0 & 0 & 0 & b_4\text{ - }3b_3\text{ + }4b_1 \\
0 & 0 & 0 & b_2\text{ - }2b_1 \\
\end{matrix}} 
\right]
$$

and x_p = 

$$
x_p\text{ = }
\left[
{\begin{array}{cc}
5b_1\text{ - }2b_1 \\
b_3\text{ - }2b_1 \\
0 \\
\end{array}} 
\right]
$$

and x_s = (-1,-1,0)

## Matrix Complete Solutions Example 7

### Sources
* ITLA 5th Ed., p.158.

### Problem Text

* "Given the matrix A:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 1 \\
3 & 8 & 2 \\
2 & 4 & 0 \\
\end{matrix}} 
\right]
$$

... what combination of the rows of A gives the zero row?"

[U c]

$$
\[U c\]\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 & 1 & b_\\
0 & -1 & -1 & b_2\tex{ -}3b_1 \\
0 & 0 & 0 & b_3\text{ - }2b_2\text{ + }4b_1 \\
\end{matrix}} 
\right]
$$

So the solvability condition is $b_3\text{ - }2b_2\text{ + }4b_1$ = 0 .

## Matrix Complete Solutions Example 8

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* Given the following matrices A and B:
      * tell which columns are in the column space
      * tell which combinations of rows will give 0.

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 1 \\
2 & 6 & 3 \\
0 & 2 & 5 \\
\end{matrix}} 
\right]
\text{, B = }
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
1 & 2 & 5 \\
2 & 4 & 8 \\
\end{matrix}} 
\right]
$$

### Solutions

* For A: under row reduction, all columns have a pivot, so all columns of A are in the column space, and only the 0 vector will give return 0.
* For B: Under row reduction, only columns 1 and 2 of B have pivots.  The combination of rows that gives 0 is b3-2b2, or row 3 - 2 times row 2.

## Matrix Complete Solutions Example 8

### Sources
* ITLA 5th Ed., p.158.

### Problem Text
* "For the following equation system:

Ax = B is

$$x_1\text{ + }2x_2\text{ + }3x_3\text{ + }5x_4\text{ = }b_1$$
$$2x_1\text{ + }4x_2\text{ + }8x_3\text{ + }12x_4\text{ = }b_2$$
$$3x_1\text{ + }6x_2\text{ + }7x_3\text{ + }13x_4\text{ = }b_3$$

...where a particular solution to Ax = (0,6,-6) , do the following:

* transform the equation system into LU format, and verify that LU = A and that Lc = b.
* combine the pivot columns of A with the numbers -9 and -3 in the particular solution x_p.  What is that linear combination and what is its significance?

### Solutions

The matrix [A b] can be written as 

$$
\left[
{\begin{matrix}{cc}
1 & 2 & 3 & 5 & b_1 \\
2 & 4 & 8 & 12 & b_3 \\
3 & 6 & 7 & 13 & b_3 \\
\end{matrix}} 
\right]
$$

Using E notations to transform A into, we get E[A b] = [U c] as 

$$
E_{2}E_{1}
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 1 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
-2 & 1 & 0 \\
-3 & 0 & 1 \\
\end{matrix}} 
\right]
\left[
{\begin{matrix}{cc}
1 & 2 & 3 & 5 & b_1 \\
2 & 4 & 8 & 12 & b_3 \\
3 & 6 & 7 & 13 & b_3 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 3 & 5 & b_1 \\
0 & 0 & 2 & 2 & b_2\text{ - }2b_1 \\
0 & 0 & 0 & 0 & b3\text{ + }b_2\text{ - }4b_1 \\
\end{matrix}} 
\right]
$$

$E^{-1}\text\text{ = }L$ is then

$$
E^{-1}
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
2 & 1 & 0 \\
3 & -1 & 1 \\
\end{matrix}} 
\right]
$$

And LU does = A.  Also Lc = b.

* The meaning of the values 9,3 is that they are the values of the transformed particular solution for b given in the original problem, when Ab --> Rd.  The values 9,3 can be made into a particular point when the free variable columns 2 and 4 are set to 0, so x_p = (9,0,3,0). 

## Example 9: Matrix Orthogonality

### Sources
* ITLA 5th Ed., p.202

### Problem Text
* "This system of equations Ax = b has no solution: (they lead to 0 = 1):

$$x\text{ + }2y\text{ + }2z\text{ = }5$$
$$2x\text{ + }2y\text{ + }3z\text{ = }5$$
$$3x\text{ + }4y\text{ + }5z\text{ = }9$$

... find a vector y of numbers to multiply the equations so that they add to 0 = 1.  In what subspace is this vector y?  Its dot product $y^Tb$ is 1, so there is no solution $x$ ."

### Solutions & Notes
* When the problem wording is "find numbers [or find a vector] to multiply the equations so that they sum" ... what it wants is find numbers by which to multiply the entire equation **on both sides** .  Then you sum the equations vertically.  In this case, if you multiply equations 1,2,3 by 1,1,-1 respectively, you'll get 0 = 1.  When you multiply the entire equation this way, it's the same effect as using dot product-style multiplication in $A^Ty$ or $\left(y^TA\right)x$ or $y^Tb$.  All of these are ways of saying that (1,1,-1) would be in the left nullspace.  However, the results on the 2 sides (0 = 1) don't match, so this doesn't solve the equation.

## Example 10: Matrix Orthogonality

### Sources
* ITLA 5th Ed., p.202

### Problem Text & Solution
* In the context of orthogonality, how do we know that $Ax_r$ is equal to Ax?
* How do we know that this vector is in the column space?
* If

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 \\
1 & 1 \\
\end{matrix}} 
\right]
\text{ and  x = }
\left[
{\begin{matrix}{cc}
1 \\
0 \\
\end{matrix}} 
\right]
$$

... what is r?

### Solutions
* In the context of orthogonality, how do we know that $Ax_r$ is equal to Ax?
* * How do we know that this vector is in the column space?
      * Answer: The book says that "x = $x_r$ + $x_n$ , where $x_r$ is in the row space and $x_n$ is in the nullspace.  Then $Ax_n$ = 0 and Ax = $Ax_r$ + $Ax_n$ = Ax."  So this is a "by definition" justification, saying that only the parts of Ax that are in the "column space" (another phrase for Ax) come from $Ax_r$ .  --If it were otherwise, it would be in the nullspace.
      * Note: I'm not sure it says so anywhere explicitly, but the r in $x_r$ seems to stand for "the part of x or Ax that comes from the pivot columns and rows", since the pivot columns/rows are denoted as "r" or a matrix' "rank".  Correspondingly the n in $x_n$ is for null.
* What is r?
      * The book says that we should split x into (1/2, 1/2) and (1/2,-1/2).  I see that when you multiply A times the first (1/2, 1/2) you get 1 and when you multiply it times (1/2,-1/2) you get 0, and if you add them you get 1,0 = x.  What I don't get is the algo for doing these computations.

## Example 11: Matrix Orthogonality

### Sources
* ITLA 5th Ed., p.202

### Problem Text 
* "Suppose that A is a symmetric matrix $A^T$ = A.  Why is its column space perpendicular to its rowspace?"

### Solution
* For a symmetric matrix, its columns are the same as its rows.  The nullspace (the xs for which Ax = 0) are columns that are perpendicular to the rows.  But in the case of a symmetric matrix, the columns are identical to the rows, so we can say that the column space is perpendicular to the nullspace.


# Matrix Spaces

## Example 1: Space Definition

### Source
* ITLA v6, 1.3: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text
"Which columns are dependent on other columns?":

$$
A_1\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9 \\
\end{matrix}} 
\right]
\text{, = }A_2\text{ = }
\left[
{\begin{matrix}{cc}
1 & 4 & 7 \\
2 & 5 & 8 \\
3 & 6 & 9 \\
\end{matrix}} 
\right]
$$

### Solutions
* Both matrices have column 3 = 2x column 2 - column 1.  So both make a plane in R3.

## Example 2: Assess Column Space

### Sources
* ITLA v6, 1.3: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text
* "Describe the column spaces in $R^3$ of B and C:

$$
B\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 \\
2 & 1 \\
3 & 3 \\
\end{matrix}} 
\right]
\text{, C = }
\left[
{\begin{matrix}{cc}
B & -B \\
\end{matrix}} 
\right]
$$

."

### Solution
* Note that in this kind of word problem one matrix may be defined in terms of a preceding one.  Here, matrix C is composed of B.
* B reduces to a structure like

$$
R_B\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
0 & 1 \\
0 & 0 \\
\end{matrix}} 
\right]
\text{ = }
\left[
{\begin{array}{cc}
I \\
0 \\
\end{array}} 
\right]
$$

... so the column space will be the 2d plane.  For any b there will just be one solution.  Only the 0 vector will be in the nullspace.

*  C(C) will also be in the 2d plane, because at 2 columns are dependent on the others.  N(C) will have more than 1 solution.

## Example 3: Matrix Space Definition

### Source
* ITLA v6, 1.3: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

### Problem Text
"Describe the column space of these matrices: a point, a line, a plane, all of 3D:

$$
A_1\text{ = }
\left[
{\begin{matrix}{cc}
2 & 2 \\
1 & 1 \\
5 & 6 \\
\end{matrix}} 
\right]
A_2\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 & 0 \\
1 & 1 & 0 \\
1 & 1 & 1 \\
\end{matrix}} 
\right]
A_3\text{ = }
\left[
{\begin{matrix}{cc}
1 & 5 \\
2 & 10 \\
1 & 5 \\
\end{matrix}} 
\right]
A_4\text{ = }
\left[
{\begin{matrix}{cc}
0 & 0 \\
0 & 0 \\
0 & 0 \\
\end{matrix}} 
\right]
$$

### Solutions
* A1: plane in 2D
* A2: identity matrix in 3D
* A3: line in 3D
* A4: 0 vector

# Matrix Space Assessment

## Example 1: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "If a 7 by 9 matrix has rank 5, what are the dimensions of the 4 subspaces?  What is the sum of all four dimensions."
      * C(A): 5
      * N(A): 9-5 = 4
      * R(A): 5
      * $N\left(A^T\right)$ 7-5 = 2
*  "If a 3 x 4 matrix has rank 3, what are its column space and left nullspace?"
      *   C(A) = 3, $N\left(A^T\right)$ = 0 .

## Example 2: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* Find bases and dimensions for the four subspaces associated with matrices A and B:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 4 \\
2 & 4 & 8 \\
\end{matrix}} 
\right]
\text{, }B\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 & 4 \\
2 & 5 & 8 \\
\end{matrix}} 
\right]
$$

### Solutions
* A:
      * C(A) = (1,2), dimension = 1.
      * R(A) = (1,2,4), dimension = 1.
      * N(A) = (-2,1,0), (-4,0,1), dimension = 2.
      * $N\left(A^T\right)$ = (-2,1), dimension = 1.

* B:
      * C(A) = (1,2), (2,5) dimension = 2.
      * R(A) = (1,2,4), (2,5,8) dimension = 2.
      * N(A) = (-4,0,1), dimension = 1.
      * $N\left(A^T\right)$  = 0, dimension = 0.

### Notes:
* Remember that the bases for C(A), R(A) are the complete rows or columns of A that correspond to the pivot rows and columns in R after row-reduction.
      * For some reason, I tend to think that R(A) is only the portion of the row that is in the pivot columns.  That is wrong.  The basis for R(A) is the complete row of A.
* The bases for N(A) and $N\left(A^T\right)$ are not taken from A but rather from U.
      * N(A) is found by back substitution.
      * $N\left(A^T\right)$ is the vector y which you could multiply $A^T$ to return as 0 vector.  It may be easiest to think of it as the list of coefficients by which you'd need multiply the rows so that if you added the rows together down the columns they'd total to 0.
         * If you can't easily see what the basis for $N\left(A^T\right)$ is, the way to get it is to figure out $E^{-1}$ = L.  The row(s) of L that corresponds to any zero rows in U will be the basis for  $N\left(A^T\right)$.

## Example 3: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* Find bases and dimensions for the four subspaces associated with matrix A:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
0 & 1 & 2 & 3 & 4 \\
0 & 1 & 2 & 4 & 6 \\
0 & 0 & 0 & 1 & 2 \\
\end{matrix}} 
\right]
$$

### Solutions

$$
R\text{ = }
\left[
{\begin{matrix}{cc}
0 & 1 & 2 & 3 & 4 \\
0 & 0 & 0 & 1 & 2 \\
0 & 0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
$$

* Bases:
* C(A) : (1,1,0), (3,4,1)
* R(A) : first 2 rows of A.
* N(A) : (1,0,0,0,0), (0,-2,1,0,0), (0,2,0,-2,1)
* $N\left(A^T\right)$ : figure out L, then the left nulls basis is the row of L that corresponds to the zero row(s) in U.  In this case it's (1,-1,1).

## Example 4: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "For the following situations, construct a matrix having the required properties, or explain why the situation is impossible:"
      * Column space contains 3x1 vectors (1,1,0), (0,0,1), row space contains 2x1 vectors (1,2),(2,5).
      * Column space has 3x1 basis (1,1,3), nullspace has 3x1 basis (3,1,1).
      * Dimension of nullspace = 1 + dimension of left nullspace.
      * Nullspace contains 2x1 (1,3), column space contains 2x1 (3,1).
      * Row space = column space, and nullspace is not equal to the left nullspace.

### Solutions
* Column space contains (1,1,0), (0,0,1), row space contains (1,2),(2,5).
      * Answer: This is possible, because after row reduction the column space will only have r = 2 like the row space.  The basis for both the row and column space in this example will reduce to I, so their actually equal despite initial different appearance.
* Column space has 3x1 basis (1,1,3), nullspace has 3x1 basis (3,1,1).
      * Answer: Impossible, because to be in the nullspace of A a vector would have to have 1x3 dimensions to generate the 0 dot product.
* Dimension of nullspace = 1 + dimension of left nullspace.
      * Answer: possible.  You can imagine for example a 2x3 matrix, where the first two rows and columns are non-zero, and the third column is free.  Then the dimension of the left nullspace does equal 0 and the dimension of N(A) = 0 + 1 = 1.
* Nullspace contains 2x1 basis (1,3), column space contains 2x1 basis (3,1).
      * Answer: possible  The key word is "contains".  It would be impossible for them do have only these vectors as thier basis, because their dimensions wouldn't match up correctly for the dot product.  But it would be possible for C(A) to have 2x2 dimensions and contain/include (3,1) so that the nullspace could be (1,3).
* Row space = column space, and nullspace is not equal to the left nullspace.
   * Impossible.  Remember that a "space" is the set of all linear combinations of column or row vectors.  If you think about it, column and row *spaces* to match without their each having the same number of components (m = n); otherwise the columns will extend into a dimension that the rows cannot, or vice versa.  But then if m = n, then it is impossible for the nullspace and left nullspace to not match, because nullspace = n-r, and left nullspace = m - r, but r=m=n, so both nullspace and left nullspace must be 0.

## Example 5: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "If V is the subspace spanned by (1,1,1) and (2,1,0) find a matrix A that has V as its rowspace.  Find a matrix B that has V as its nullspace.  Multiply AB."

### Solutions
* A:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
2 & 1 & 0 \\
\end{matrix}} 
\right]
$$

* B:

$$
B\text{ = }
\left[
{\begin{matrix}{cc}
1 \\
-2 \\
1 \\
\end{matrix}} 
\right]
$$

* AB = 0

### Notes
* This problem may seem ill-worded because it breaks the convention of denoting a column vector using horizontal "(1,1,1) and (2,1,0)" notation.  So it can be confusing to have the task of what would normally be column vectors in a row space.  So the purpose of the problem seem seems to be to encourage us to think of the parenthetic () notation as just lists of numbers in a conceptual vector space "V" when explicitly told to do so.  Also, the problem reminds us that if we can find a row matrix that is in the nullspace of a set of columns (A transpose) -- effectively a left nullspace, then we should always expect the dot product to be 0.

## Example 6: Find Bases, Dimensions of Subspaces

### Source
* ITLA v5, p190.

### Problem Text
* "Without using elimination, find dimensions and bases fro the four subspaces for these matrices:

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
0 & 3 & 3 & 3 \\
0 & 0 & 0 & 0 \\
0 & 1 & 0 & 1 \\
\end{matrix}} 
\right]
\text{, }B\text{ = }
\left[
{\begin{matrix}{cc}
1 \\
4 \\
5 \\
\end{matrix}} 
\right]
$$

### Solutions

* A:
      * C(A) = (3,0,0) and (3,0,1) -- note that either column (3,0,1) can be used.  Dimension : 2.
      * N(A) = (1,0,0,0), (0,1,0,-1).  Dimension: 2.
      * R(A) = (0,3,3,3) and (0,1,1,1).  Dimension : 2.
      * N(A^T) = (0,1,9).  Dimension : 1.

* B:
      * C(A) = (1,4,5).  Dimension : 1.
      * N(A) = Empty basis.
      * R(A) = 1.  Dimension : 1.
      * N(A^T) = (-4,1,1),(5,0,-1).  Dimension : 2.

### Notes:
* Note that when only the 0 vector is in the nullspace it is correct to say that the nullspace has "an empty basis", not that the nullspace is the 0 vector with dimension = 1.
* Expect to have one vector for each empty/free column or row, whether in N(A) or N(A^T).

  
### Solutions


## Example 4: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* "Given the following vectors:

$$
v_1\text{ = }
\left[
{\begin{array}{cc}
1 \\
0 \\
0 \\
\end{array}} 
\right]
\text{, }v_2\text{ = }
\left[
{\begin{array}{cc}
1 \\
1 \\
0 \\
\end{array}} 
\right]
\text{, }v_3\text{ = }
\left[
{\begin{array}{cc}
1 \\
1 \\
1 \\
\end{array}} 
\right]
\text{, }v_4\text{ = }
\left[
{\begin{array}{cc}
2 \\
3 \\
4 \\
\end{array}} 
\right]
$$

* Show that v_1,v_2,v_3 are independent, but v_1,v_2,v_3,_v4 are dependent.
* Solve $c_1v_1\text{ + }c_2v_2\text{ + }c_3v_3\text{ + }c_4v_4\text{ = }0$ or Ax = 0.  The v's go in the columns of A."

### Solutions
* Show that v_1,v_2,v_3 are independent, but v_1,v_2,v_3,_v4 are dependent.
   * It is clear that only x =0 will give Ax = 0 when only v_1,v_2,v_3 are in A.
* When v_1,v_2,v_3,v_4 are all in A, you can solve for 0 by toggling the free variable column 4 to 1 and solving for Ax = 0 using back-substitution.  Then you get N(A) = c(1,1,-4,1), which is not c = 0, so the 4 columns are dependent.

## Example 4: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* "find the largest possible number of independent vectors among:

$$
v_1\text{ = }
\left[
{\begin{array}{cc}
1 \\
-1 \\
0 \\
0 \\
\end{array}} 
\right]
\text{, }v_2\text{ = }
\left[
{\begin{array}{cc}
1 \\
0 \\
-1 \\
0 \\
\end{array}} 
\right]
\text{, }v_3\text{ = }
\left[
{\begin{array}{cc}
1 \\
0 \\
0 \\
-1 \\
\end{array}} 
\right]
\text{, }v_4\text{ = }
\left[
{\begin{array}{cc}
0 \\
1 \\
-1 \\
0 \\
\end{array}} 
\right]
\text{, }v_5\text{ = }
\left[
{\begin{array}{cc}
0 \\
1 \\
0 \\
-1 \\
\end{array}} 
\right]
\text{, }v_6\text{ = }
\left[
{\begin{array}{cc}
0 \\
0 \\
1 \\
-1 \\
\end{array}} 
\right]
$$

### Solution
* It is self-evident that the first 3 vectors are independent, since the first value = 1 but each vector has its only non-zero value in a unique position.
* The answer the book gives is that "all of the vectors are in the plane (1,1,1,1)*v = 0, so no four of these six vectors can be independent."  --This is not obvious to me, and I don't understand why being in the plane (1,1,1,1)*v = 0 means that a max of 3 and not 4 vectors can be independent.  But what is clear is that under row reduction you're left with 3 pivot columns, so I take RREF as the surer way to decide this question.

## Example 5: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text

* "Given the following matrix:

$$
\left[
{\begin{array}{cc}
a & b & c \\
0 & d & e \\
0 & 0 & f \\
\end{array}} 
\right]
$$

... prove that if a, d, or f = 0 that the columns of U are dependent."

### Solution

* Book solution: "If a = 0 then column 1 = 0; if d = 0 then b(column 1)− a(column 2) = 0; if f = 0 then all columns end in zero (they are all in the xy plane, they must be dependent)."
* Notes:
      * this solution hangs on the strict definition of linear independence for a matrix: "if a combination gives 0, when the [scalars that multiply the vectors] are not all 0, then the vectors are *dependent*."  --Since the vectors can be shown to be 0 regardless of their scalar multiplier, then they are dependent.
      * the comment about being on a plane makes sense, but is a less obvious (to me) way to make the point.  It shows though that dependence is something like "filling out fewer than the available dimensions in a matrix", or, what is related to this,  "having more columns or rows than the full rank r".

## Example 6: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* "Given the following matrix:

$$
\left[
{\begin{array}{cc}
a & b & c \\
0 & d & e \\
0 & 0 & f \\
\end{array}} 
\right]
$$

... show that if a, d, and f are all non-zero that the columns of U are all independent."

### Solution
* I initially said: "If a, d, and f are all non-zero then it will not be possible to eliminate the pivots and this square matrix will be full rank.  A consequence is that each column will extend into at least 1 dimension that the others do not, and therefore they must all be linearly independent."
* I think this is correct at least in the case of a square matrix, but what the book does it to show that you can consider the matrix U as multiplying x in Ux = 0.  Because it's upper triangular, you solve Ux = 0 using back-substituion and show that the components of x are always 0.  Going back to the definition of independence: since the only way to get Ux = 0 is when the scalars in x are all 0, then the columns of U are independent.  --This approach is prob the safe proof so go with that.


## Example 7: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* "Given the following vectors:
   * vectors (1,3,2), (2,1,3) and (3,2,1)
   * vectors (1,-3,2),(2,1,-3) and (-3,2,1)

..."show the independence or dependence of each."

### Solutions
* vectors (1,3,2), (2,1,3) and (3,2,1): when put into a matrix, the matrix reduces to I under RREF.
* vectors (1,-3,2),(2,1,-3) and (-3,2,1): the 3rd vector is the sum of the each of the first 2 vectors, when each is multiplied by -1.

## Example 8: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* Given the following matrices:

$$
U\text{ = }
\left[
{\begin{matrix}{cc}
2 & 3 & 4 & 1 \\
0 & 6 & 7 & 0 \\
0 & 0 & 0 & 9 \\
0 & 0 & 0 & 0 \\
\end{matrix}} 
\right]
\text{, }U\text{ = }
\left[
{\begin{matrix}{cc}
2 & 3 & 4 & 1 \\
0 & 6 & 7 & 0 \\
0 & 0 & 0 & 9 \\
4 & 6 & 8 & 2 \\
\end{matrix}} 
\right]
$$

... choose 3 independent columns of U.  Then find 2 other unique combinations of 3 independent columns.  Do the same for A.

### Solutions
* U is an updated form of A.  Any 3 columns except for 1,2,3 are independent in both of them.
* Note: one point of this problem is to **separate the concept of pivot columns from the concept of independent columns.**  Only 1,2,4 are pivot columns, but 3 can be independent of other columns, depending on the columns selected.  A column need not be a pivot column to be independent.

## Example 9: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
* If w_1,w_2,w_3 are independent vectors, show that the sums v_1 = w_2 + w_3, v_2 = w_1 + w_3, v_3 = w_1 + w_2 are independent.

## Solutions
* This is done by first construing the formula in terms of a linear combination of vs, where c_1v_1 + c_2v_2 + c_3v_3 = 0. Then substituted in the w formulas: c_1(w_2 + w_3) + c_2(w_1 + w_3) + c_3(w_1 + w_2) .  When the cs are distributed and the terms re-arranged and abstracted, you get (c_2 + c_3)w_1 + (c_1 + c_3)w_2 + (c_1 + c_2)w_3 = 0.  This shows that the w's are independent, or at least reformuates everything in terms of a linear combination of 3 independent vectors equal to 0.  Considering them as independent means that the only scalar multipliers that will return the 0 vector must be cs = 0, or c_2 + c_3 = c_1 + c_3 = c_1 + c_2 = 0.  This works out to saying that all the cs must equal 0.  Only this combination of independent vectors times c (or x) = 0 returns 0, so the vectors are independent.

## Example 10: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text and Solutions
* Suppose v_1,v_2,v_3,v_4 are vectors in $\mathbb{R}^3$ .
      * These four vectors are dependent because columns are in m-space, so saying that you have four columns in R3 means you have a 4x3 matrix, which guarantees at least one free variable column.  So there will be one non-zero solution to Ax = 0, which is the definition of dependent.
      * The two vectors v1 and v2 will be dependent if : answer: one is a multiple of the other.  Another way the book says is is that [v1 v2] is a rank 0 or rank 1 matrix, meaning that at least one of the rows would zero out.
      * The vector v1 and (0,0,0) are dependent because: answer: a nontrivial combination of v_1 and 0 gives 0: e.g. 0v_1 + 3(0,0,0) = 0.  --What this means is that if the values of a vector are 0 itself, then someting other than a scalar c = 0 gives the 0 vector.  This is a definition of dependence, although it's strange.


## Example 11: Matrix Linear Independence

### Sources
* ITLA, 5th ed.  p175.

### Problem Text
*  Find 2 independent vectors on the plane x + 2y - 3z - t = 0.  Then find 3 independent vectors.  Why not four?  The plane is in the nullspace of what matrix?
      *  The coefficient matrix is a 1x4 matrix = A, so it's got 3 free variables for a max of 3 indepdent vectors among them (this is why not four).  The vectors are (-2,1,0,0), (3,0,1,0), (1,0,1,0).  The these 3 vectors can be considered as a matrix and all of N(A) is some linear combination of them.

## Example 12: Projection Matrices

### Sources
* ITLA, 5th ed.  p214.

### Problem Text
* "Project the vector b onto the line through a. Check that e is perpendicular to a.  Then find the projection matrix P = $\frac{aa^T}{a^Ta}$ .  Verify that P^2 = P.  Multiply Pb to compute the projection p.

$$
\text{(a) b = }
\left[
{\begin{array}{cc}
1 \\
2 \\
2 \\
\end{array}} 
\right]
\text{, and a = }
\left[
{\begin{array}{cc}
1 \\
1 \\
1 \\
\end{array}} 
\right]
$$

$$
\text{(b) b = }
\left[
{\begin{array}{cc}
1 \\
3 \\
1 \\
\end{array}} 
\right]
\text{, and a = }
\left[
{\begin{array}{cc}
-1 \\
-3 \\
-1 \\
\end{array}} 
\right]
$$

### Solutions:
* (a) xhat = 5/3, axhat = p = (5/3,5/3,5/3), e = (-2/3,1/3,1/3); e is perpendicular to a.

P = $\frac{aa^T}{a^Ta}$ = 

$$
\frac{1}{3}
\left[
{\begin{matrix}{cc}
1 & 1 & 1 \\
1 & 1 & 1 \\
1 & 1 & 1 \\
\end{matrix}} 
\right]
$$

$P^2$ does = P.  Pb = (5/3,5/3,5/3) as listed above.

* (b) xhat = -1, axhat = p = (1,3,1), e = (1,3,1)-(1,3,1) = (0,0,0); e is perpendicular to a.

P = $\frac{aa^T}{a^Ta}$ = 

$$
\frac{1}{11}
\left[
{\begin{matrix}{cc}
1 & 3 & 1 \\
3 & 9 & 3 \\
1 & 3 & 1 \\
\end{matrix}} 
\right]
$$

$P^2$ does = P; Pb = (1,3,1) as listed above.

## Example 13: Projection Matrices

### Sources
* ITLA, 5th ed.  p214.

### Problem Text
* "Compute the project p from b and a.  Then construct the projection matrices P1 and P2 onto the lines through the a's.  Is it true that $\left(P_1\text{ + }P_2\right)^2\text{ = }P_1\text{ + }P_2$ ?  This *would* be true if $P_1P_2\text{ = }0$ .

$$
\text{(a) b = }
\left[
{\begin{array}{cc}
{\text{cos}\theta} \\
{\text{sin}\theta} \\
\end{array}} 
\right]
\text{, and a = }
\left[
{\begin{array}{cc}
1 \\
0 \\
\end{array}} 
\right]
$$

$$
\text{(b) b = }
\left[
{\begin{array}{cc}
1 \\
1 \\
\end{array}} 
\right]
\text{, and a = }
\left[
{\begin{array}{cc}
-1 \\
-1 \\
\end{array}} 
\right]
$$

## Solutions
* (a) xhat = ${\text{cos}\theta}$, p = $\left({\text{cos}\theta},0\right)$ .

$$
P_1\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
0 & 0 \\
\end{matrix}} 
\right]
$$

* (b) xhat = 0, p = (0,0) .

$$
P_2\text{ = }
\frac{1}{2}
\left[
{\begin{matrix}{cc}
1 & -1 \\
-1 & 1 \\
\end{matrix}} 
\right]
$$

* It is not the case that $\left(P_1\text{ + }P_2\right)^2\text{ = }P_1\text{ + }P_2$ .

## Example 14: Projection Matrices

### Sources
* ITLA, 5th ed.  p214.

### Problem Text
* Compute the projection matrices P1 from a1 = (-1,2,2) and P2 from a2 = (2,2,-1).  Multiply the 2 matrices P1P2 and explain why the result is like it is.
* Project b = (1,0,0) onto the lines through a1 and a2, as well as a3 = (2,-1,2).  Add up the 3 projections p1 + p2 + p3.
* Find the projection matrix P3 onto a3 = (2,-1,2).  Verify that P1 + P2 + P3 = I.  This is because the bases a1, a2, and a3 are orthogonal to each other.

### Solutions

$$
P_1\text{ = }
\frac{1}{9}
\left[
{\begin{matrix}{cc}
1 & -2 & -2 \\
-2 & 4 & 4 \\
-2 & 4 & 4 \\
\end{matrix}} 
\right]
$$

$$
P_2\text{ = }
\frac{1}{9}
\left[
{\begin{matrix}{cc}
4 & 4 & -2 \\
4 & 4 & -2 \\
-2 & -2 & 1 \\
\end{matrix}} 
\right]
$$

$$
P_3\text{ = }
\frac{1}{9}
\left[
{\begin{matrix}{cc}
4 & -2 & 4 \\
-2 & 1 & -2 \\
4 & -2 & 4 \\
\end{matrix}} 
\right]
$$

$$
P_1+P_2+P_3\text{ = }
\frac{1}{9}
\left[
{\begin{matrix}{cc}
9 & 0 & 0 \\
0 & 9 & 0 \\
0 & 0 & 9 \\
\end{matrix}} 
\right]
\text{ = }I
$$

* P1P2 = [0] matrix of same dimensions.  Because a1 and a2 are perpendicular to each other their respective matrices are perpendicular to each other.

* xhat1 = -1/9 and p1 = (1/9,-2/9,-2/9)
* xhat2 = 2/9 and p2 = (4/9,4/9,-2/9)
* xhat3 = 2/9 and p3 = (4/9,-2/9,4/9)

So p1 + p2 + p3 = (1,0,0) which is b.

## Example 15: Projection Matrices

### Sources
* ITLA, 5th ed.  p214.

### Problem Text
* "Project the vector b = (1,1) onto the lines through a1 = (1,0) and a2 = (1,2).  Verify that the projections do not add up to b.  This is because they are not orthogonal."
* The projection of vector b = (1,1) onto the *plane* of a1 and a2 will equal b.  Find P = $A\left(A^TA\right)^{-1}A^T$ for A = [a1 a2] .

### Solutions

* p1 = xhat1a1 = 1(1,0) = (1,0) = p1 .
* p2 = xhat2a2 = 3/5(1,2) = (3/5,3/10) = p2 .
* p1 + p2 does not equal (1,1).
* P = $A\left(A^TA\right)^{-1}A^T$ for A = [a1 a2]  = I , and I is the projection matrix on to all of $R^2$ .



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

## Transposed Matrices

### Facts

* Transposing a matrix swaps row placement for column placement, so that row 1 becomes column 1, row 2 becomes column 2, etc.
* In general, we can say that that $A^T_{ij}=A_{ji}$ for row i and column j.

* Note that:
  * the transpose of the identity matrix I is necessarily I.
  * a symmetric matrix is identical to its transpose: $A=A^T$.
  * multiplying a retangular matrix by its tranpose will give you a symmetric matrix.  For example, with a 2x3 matrix this would cause the off diagonal sum A_11*B_12+A_12*B_22 to be calculated with an identical value from as A_21*B_11+A_22*B_12, so that all the off-diagonal values end up duplicated.
  * When taking the transpose of a product of matrices like $R^{T}R$, the practice is to reverse the order of items in the parentheses, then transpose each term.  So $\left(R^{T}R\right)^T\text{ = }R^TR^{TT}$.
  * Taking additional transposes of symmetric matrix products, e.g. $R^{T}R$, leaves them unchanged.
  * If you take the inverse of a transpose you have to reverse the order: $AA^{-1}=I={A^{-1}}^TA^T$ .

### Transposed Matrix Example 1

#### Sources
* ITLA sols, p30. https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

#### Problem Text
* "Find $A^T$ and $A^{-1}$ and $\left(A^{-1}\right)^T$ and $\left(A^T\right)^{-1}$ for

$$
A_1\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
9 & 3 \\
\end{matrix}} 
\right]
\text{ and }A_2\text{ and }
\left[
{\begin{matrix}{cc}
1 & c \\
c & 0 \\
\end{matrix}} 
\right]
$$

#### Solutions

$$
{A_1}^T\text{ = }
\left[
{\begin{matrix}{cc}
1 & 9 \\
0 & 3 \\
\end{matrix}} 
\right]
{{A_1}^{-1}}^T\text{ = }
\left[
{\begin{matrix}{cc}
1 & -3 \\
0 & \frac{1}{3} \\
\end{matrix}} 
\right]
$$

$$
{A_2}^T\text{ = }
\left[
{\begin{matrix}{cc}
1 & c \\
c & 0 \\
\end{matrix}} 
\right]
{{A_2}^{-1}}^T\text{ = }
\frac{1}{c^2}
\left[
{\begin{matrix}{cc}
0 & c \\
c & -1 \\
\end{matrix}} 
\right]
$$

### Transposed Matrix Example 2

#### Sources
* ITLA sols, p30. https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

#### Problem Text
* Given the matrices

$$
A\text{ = }
\left[
{\begin{matrix}{cc}
1 & 0 \\
2 & 1 \\
\end{matrix}} 
\right]
\text{, }B\text{ = }
\left[
{\begin{matrix}{cc}
1 & 3 \\
0 & 1 \\
\end{matrix}} 
\right]
$$

... show the results for $B^{T}A^{T}$ and $A^{T}B^{T}$ 

$$
B^{T}A^{T}\text{ = }
\left[
{\begin{matrix}{cc}
1 & 2 \\
3 & 7 \\
\end{matrix}} 
\right]
$$

$$
A^{T}B^{T}\text{ = }
\left[
{\begin{matrix}{cc}
7 & 2 \\
3 & 1 \\
\end{matrix}} 
\right]
$$

### Transposed Matrix Example 3

#### Sources
* ITLA sols, p30. https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

#### Problem Text
* Show the order of operations for $\left(\left(AB\right)^{-1}\right)^T$ comes from $\left(A^{-1}\right)^T$ and $\left(B^{-1}\right)^T$ .
* If U is upper triangular then $\left(U^{-1}\right)^T$ is what?

#### Solutions
* Show the order of operations for $\left(\left(AB\right)^{-1}\right)^T$ comes from $\left(A^{-1}\right)^T$ and $\left(B^{-1}\right)^T$ .
      * Answer: $\left(B^T\right)^{-1}\left(A^T\right)^{-1}$ .
* If U is upper triangular then $\left(U^{-1}\right)^T$ is what?
      * Answer: lower triangular, because you can swap the transpose and inverse operators, so that U will be lower before you invert it.

### Transposed Matrix Example 4

#### Sources
* ITLA sols, p30. https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

#### Problem Text
* "Show that $A^2$ = 0 is possible but $A^TA\left{ = }0$ is not possible, unless A = 0 .

#### Solutions
* I can't find a proof but the intuition is that with $A^2$ you can work out some scheme where positive and negative values 0 out.  However, when you multiply A by its transpose you make it so some negative values are multiplied times each other so that positive non-zero values.

### Transposed Matrix Example 5

#### Sources
* ITLA sols, p30. https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

#### Problem Text
* Compute the number

$$
x^TAy\text{ = }\left[0 1\right]
\left[
{\begin{matrix}{cc}
1 & 2 & 3 \\
4 & 5 & 6 \\
\end{matrix}} 
\right]
\left[
{\begin{array}{cc}
0 \\
1 \\
0 \\
\end{array}} 
\right]
$$

* This is the row $x^TA = ?
* This is the row $x^T\left{ = }\left[0 1\right]$ times the column $Ay\text{ = }$   .

#### Solutions

* Compute the number = 5.
* This is the row $x^TA = (4, 5, 6)
* This is the row $x^T\left{ = }\left[0 1\right]$ times the column
  
  $$
  Ay\text{ = }
  \left[
   {\begin{array}{cc}
   2 \\
   5 \\
   \end{array}} 
   \right]
  $$
  




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














