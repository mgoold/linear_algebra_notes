
# Linear Algebra Tasks

The purpose of this do is to index all the tasks/algorithms I've had to do while learning linear algebra.  I find it difficult to organize this kind of content in my head, so I'm trying to recuded it down to task: solution pairs, e.g, "find inverse of matrix -- > do GJ elimination on an AI:I-A format" .  In doing so, I'm collating tasks from USF's MSDS course, and MIT 18.06.  At the start, I'm prioritizing and distinguising tasks, so not every task will have a solution.   As always, feel free to reach out with corrects &c.

HTH

## Vector Operations

### Scale Vector

### Facts:

* True\|False: "If one scales a vector by a non-zero value, the resulting vector will lie along the same line." -- True.
* Differences between point and vector:
  * 

### Turn Equation System Into Vectors


#### Count Equation System Solutions

### Taking dot products

* To take a dot product of 2 vectors, multiply each component in v by the corresponding component in w, and sum the products.  

### Computing Vector Length

* To compute the length of a vector, take the dot product of a vector with itself.  The square root of this dot product is the vector length.
* The reverse of this is that the dot product of a vector is the length squared.

## Find Value of Length 2 Vectors Subtracted from Each Other

### Steps
* subract the components for one vector from the corresponding components of the other
* take the dot product of the resulting vector of differences
  * take the square of every component, and sum the components
* take the square root of that dot product

### Find Length of Difference Between Orthoganal Vectors
** Same process, except that the resultant difference vector will always be a vector of 1s.  Consequently, the dot product will be n, and the length will be sqrt(n).

### Unit Vectors

* A vector is a vector whose components sum to 1.
* Create a unit vector by:
  * computing its length
  * dividing every component by that length, so that the components sum to 1.

### Unit Vector Trigonometry

## Matrix Assessment

* Evaluate whether any columns sum to 0.
* Evaluate whether any rows sum to 0.
  * IF a combination of rows of A gives a 0 row, then b must sum to 0 via the same combination.  This is a "condition of solvability".
* Evaluate whether any columns are linear combinations of other columns.
  * If they are not:
    * The columns are independent.
    * The only vector in N(A) will be [0].  --The only value of x that sets Ax = 0 is the 0 vector.
  * If they are:
    * The maximum number of dimensions they matrix can fill is the number of independent columns.
* Compare expected counts pre-RRE: r vs n vs m:
  * if r = m = n, then 1 solution x = b.
  * if r = n < m, then 0 or 1 solution, 0 vector is only vector in N(A)
  * if r = m < n, then R = IF, infinite solutions.
  * if r < m, r < n then 0 or infinite solutions.

### Matrix Facts:
 * The number of *potential* dimensions that a matrix can fill is its row count.
 * The maximum number of dimensions that a matrix can *actually* fill is the number of independent columns.
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
* If there is a non-zero vector such that Ax = b, then A has dependent columns, and annot be invertible.
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

## Finding Determinants

### Find Determinant of a 2x2 Matrix

## Assess Linear Independence

### Determine if All/Which Vectors in Matrix are Linearly Independent

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

### Compute Eigenvectors

## Compute Gradient

### Compute Gradient of a Function

This is the same process as a Jacobian, except for one function -- thus it is the transpose of the first row of a Jacobian.

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

## Four Fundamental Subspaces

### For A Given Matrix:
 * Assess the independence, rank, basis, and dimension.
 * Find the solution for Ax = b, Ax = 0.

### Facts:

A vector "space" consists of a set of vectors that obey these math constraints:
* the result of any addition of the vectors stays in the same space
* the result of any multiplication of the vectors by a scalar stays in the same space
  * in short, all of its linear combinations have to remain in the space.
  * all subspaces must include the 0 vector
* the union of 2 valid subspaces, a plane and a vector not in that plane will not be a subspace, because the adding a vector from each will yield a vector not in either of them.  It will be "outside the space".
  * the intersection of them will be a valid subspace, since by definition it must be at the origin, and the 0 vector itself is always a valid subspace.

* Definition of (Real) Vector Subspace:
  * if a space obeys the math constraints whitin a larger space, then it is said to be a "subspace" of that larger space.  A plane through the origin is a subspace of R3.
  * all subspaces include the 0 vector -- otherwise, it wouldn't be possible to multiply them by 0 and have them stay in the space

### Column Space C(A)

*  All linear combinations of columns in A.
*  Ax = b is solveable i.o.i. b is in C(A)
*  C(A) is a subspace of $R^m$ (not $R^n$ ).
*  In Ax = b, x is in $R^n$ subspaces, while C(A) is in $R^m$ .
  * N(A) is in $R^n$, while C(A) is in $R^m$ .  Thus is is possible to have C(A) and N(A) in spaces of different dimensions.
* To get basis for C(A):
  * put the matrix in RREF
  * find the leading 1s
    * the columns of the original matrix that correspond to the columns with leading 1s are the basis of C(A)

### Nullspace N(A)

* For Ax=b, the null space N(A) is the set of solutions x that cause Ax=0.
* The basis for N(A) is the set of independent vectors that span N(A).  
* If A is square and has full rank, its columns will all be independent, and only 0 will be in the nullspace.
* If any vector x causes Ax = 0, then any vector cx will also be in the nullspace, and N(A) will have infinitely many solutions.
* N(A) is in $R^n$, while C(A) is in $R^m$ .  Thus is is possible to have C(A) and N(A) in spaces of different dimensions.
* In the context of Ax = 0, a row in A is multiplied by x in N(A) to yield a dot product 0 component in the 0 vector.  This tells you that R(A) and N(A) are orthogonal to each other.
* By common usage, Z is the letter used for a null space consisting of nothing but zeros.

### Rowspace R(A) (or $C\left(A^T\right)$
* The basis of a rowspace is whatever independent rows remain after RRE.  Present them as columns.
  * In other words, R(A) = $C\left(A^T\right)$ .
* The row space of A is all combinations of its rows. In other words, the rows "span" the rowspace.
* The rows may or may not be a basis for R(A) -- they may or may not be independent.
* What is in R(A)? All combinations of the rows of A.
* To work with the rows as column vectors, we can transpose the matrix A. Then we say that R(A) is all combinations of A T . Further, we can say that R(A) = C( A T ).
* The rowspace is orthogonal to the nullspace.

### Leftnullspace aka Null Space A Transpose

* The left nullspace N($A^T$) is in Rm.  The reasoning here corresponds to why x is in Rn, except that N($A^T$) is on the left-hand side of A.
* C(A) and  N($A^T$ are orthogonal to each other.
* The nullspace of $A^T$ is all of the vectors x in $A^Tx\text{ = 0}$ .  In this equation, the matrix A is transposed so that the rows can be treated as a column space, viz $C\left(A^T\right)$ .
 * The nullspace is then $A^Tx\text{ = }0$ .  To treat it as rows again, we can transpose both sides: $\left(A^Tx\right)^T\text{ = }0^T$ .  As may be recalled, transposing a product like this requires reversing the order of their multiplication, so we get: $x^T\left(A^T\right)^T\text{ = }0^T$, which becomes $x^TA\text{ = }0^T$ .  In this formulation, x is a row "vector" which multiplies the columns of A to give a row vector of 0s. Because it acts on A from the left side, it is sometimes called the "left nullspace" .
 * To obtain the left nullspace, you solve $C\left(A^T\right)\text{ = }0$ using rre and regular or special solutions as needed.  The remaining independent columns that span the space are then the nulls space of A transpose aka the left nullspace.

## Left\|Right Inverse

### Determine Whether Matrix Has Left Inverse

* Facts:
* If a matrix is square and full rank after RRE, it will have both a left and right inverse (the left and right are identical).  
* Determining the "left or right" inverse of a matrix is thus the same as computing the inverse in general.

### Find Basis for $\mathbb{R}^n$

#### Determine Orthonormal Basis for $\mathbb{R}^n$ .

## Singular Value Decomposition

### Eigendecomposition

### Using SVD

$\beta$ in $\hat{\beta}\text{ = }{\left(X^TX\right)}^{-1}X^TY$

## Functions --> Linear Algebra

### Assess Number of Parameters

*  For a given linear regression formula, the number of parameters required should be the number of predictor variables, plus one parameter for the intercept.
