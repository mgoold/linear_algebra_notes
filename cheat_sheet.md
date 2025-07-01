
# Cheat Sheet

## Vectors

### Vector Facts

* vectors are defined in relation to an origin
* vectors have inherent direction
* we can add, subtract, and multiply vectors, but not points

## Unit Vectors, Lengths

### Facts

* Any value squared could be considered as the squared hypotenuse of a symmetric right triangle.
* It follows that the dot product (the sum of all of a vector's squared components), noted as $v\cdot{}v$, is then an overall squared "hypotenuse" to its component right triangles.
* The **length** of a vector is the square root or hypotenuse of that dot product.
* a **unit vector** is a vector with every component divided by the vector's length. The unit vector's dot product, which squares every component, will then = 1, and the square root of that dot product must likewise equal 1.
  * example:
    * v = (1,2,3)
    * $v^2$ = 14 ; the length of v "lv" is $\lvert\lvert{v}\rvert\rvert$ = $\sqrt{14}$
    * u = (1/lv,2/lv,3/lv).
    * Thus, $u\cdot{}u$ = 1, so length of u = $\lvert\lvert{v}\rvert\rvert$ = $sqrt(1)$ = 1.

### Examples
* Suppose that v is a unit vector. What is the value of the dot product $v\cdot\left(-v\right)$ ?
  * Answer: -1.  A unit vector always has a "hypotenuse" (in the 2d case) or length squared of 1; the sum of its squared components = 1.  So $v\cdot\left(-v\right)$ ends up meaning So $vs\cdot\left(-1\right)v$ or "the sum of every unit component multiplied by its negative", which must equal -1.

## Fit, Least Squares

### Facts
* Solving $A^TA\hat{x}\text{ = }A^Tb$ gives the projection p = $A\hat{x}$ of b onto the column space of A.
* When Ax = b has no solution $\hat{x}$ is the "least-squares solution" : ${\text{||}b\text{ - }A\hat{x}\text{||}}^2$ = minimum.
* Setting partial derivatives of E = ${\text{||}A\hat{x}\text{ - }b\text{||}}^2$ to zero $\left(\frac{\partial{E}}{x}\text{ = }0\right)$ also produces $A^TA\hat{x}\text{ = }A^Tb$ .
  * How do do this:
    1. For each variable, write out the error terms as $E\text{ = }{\left(C\text{ + }t_{i}Dt\text{ - }b_{i}\right)}^2\text{ + }{\left(C\text{ + }t_{i+1}Dt\text{ - }b_{i+1}\right)}^2\text{,...,}{\left(C\text{ + }t_{m}Dt\text{ - }b_{m}\right)}^2$ , where i is the row index, C is the y intercept constant (typically 1), D is an independent variable (in an Ax = b context, a component of the vector x), and b is the corresponding component of b from the same row.  Across the equation row-wise, there should be one squared error for every row i to m.  The **exact same equation** should then be repeated once for each component of x, so that you have a set of identical equations composed of nxm square errors.
    2. For each equation, take the derivative of E on both sides with respect to a different component of x, so that you work through the x components from i to m, one per equation.
    3. For each equation, sum the common terms.
    4. You will finally end up with the same equation $A^TA\text{ = }A^Tb$ , which can then be solved in the same way.
* To fit points $\left(t_1,b_1\right)\text{,...,}\left(t_m,b_m\right)$ by a straight line, A has columns (1,....1) and $\left(t_1\text{,...,}t_m\right)$ .
  * IN OTHE WORDS, THE MAIN POINT OF THIS: you get 1 term for a constany y intercept, plus one term for each independent variable, to solve for the dependent var b.
* In that case $A^TA$ is the 2x2 matrix

$$
\left[
\begin{matrix}
m & \sum{t_i} \\
\sum{t_i} & \sum{t_{i}^2} \\
\end{matrix} 
\right]
$$

### Fitting a Line b to C(A)
* for a vector b, with a specified vector a in C(A).
  * calculate the projection of b onto a at point p = $\hat{x}a$ :
    * $\hat{x}$ = aTa/aTb 
    * p = $\hat{x}a$
    * error e = b - p; E = sum of squares of every e in b - p .
    * error vector e will be orthogonal to a and thus $a^Te$ will have a 0 dot product. --Use this as a QA check.

### Solving $A^TA\hat{x}\text{ = }A^Tb$
* For a given matrix A and vector b, where Ax = b does not have an exact solution:
  * Compute $A^TA$ and $A^Tb$ .
  * Put $A^TA$ and $A^Tb$ into an augmented matrix, then put that matrix into RREF form.  The result of the augmented portion is $\hat{x}$ .
  * Multiply A on $\hat{x}$ to get p; p is the closest possible approximation b Ax = b.
  * The error term e is then b - p, and the total sum of squared components of e is E. This is the measure of how close p was to b.

### Examples
* "Suppose I want to find the linear function of best fit for my data $\\{\left(x_1,y_1,z_1\right)\text{,}\left(x_2,y_2,z_2\right)\text{,...}\left(x_N,y_N,z_N\right)\\}$ where
x,y are the independent variables and z is the target variable.  How many parameters does a general linear function have in this scenario?"
  * Answer: 3.  Count the number of variables including the target variable for this kind of question.
* "Suppose I have 10 data points $\left(x_i,y_i\right)$ and I want to find the line of best fit. The total sum of squares is given by the following dot product:

$$\left(\overrightarrow{y}\text{ - }X\overrightarrow{\beta}\right)\cdot\left(\overrightarrow{y}\text{ - }X\overrightarrow{\beta}\right)$$

... how many columns does X have in this equation?" 
  * **Answer:** 2 (in fact, an unspecified matrix X could have an aribtrarily large number of columns, but I think what they're getting at is that it has at least the intercept + x term, which is 2 columns.)

#### Fitting Partial Derivatives

* TBD

#### Matrix Fit: line
* Find the closest line to the points (0, 6), (1, 0), and (2, 0):
  * Formulate each point as Constant + D(x_1) = y:
    * 1 + D\*0 = 6
    * 1 + D\*1 = 0
    * 1 + D\*2 = 0
  * Formulate as a matrix system Ax = b:

$$
A\text{ = }
\left[
\begin{matrix}
1 & 0 \\
1 & 1 \\
1 & 2 \\
\end{matrix} 
\right]
\left[
\begin{matrix}
C \\
D \\
\end{matrix} 
\right]
\text{ = }
\left[
\begin{matrix}
6 \\
0 \\
0 \\
\end{matrix} 
\right]
$$

* apply the formulas listed above to obtaine ATA, ATb, p, and e.

#### Parabola Fit

* **Example**
  * Given a set of points (-1,1/2), (1,-1), (2,-1/2), (3,2), suppose that a parabola is the best line of fit.
  * The equation for a parabola is : y = $Bx^2\text{ + }Cx\text{ + }D$ .
  * Always use the last component of the points as y.  The first element is taken to the first and second powers, and a constant = 1 is added like so:


$2\text{ = }B\left(3\right)^2\text{ + }C\left(3\right)\text{ + }D$  
$\frac{1}{2}\text{ = }B\left(-1\right)^2\text{ + }C\left(-1\right)\text{ + }D$  
$-1\text{ = }B\left(1\right)^2\text{ + }C\left(1\right)\text{ + }D$  
$-\frac{1}{2}\text{ = }B\left(2\right)^2\text{ + }C\left(2\right)\text{ + }D$  

This is then turned into a matrix A, x variable and target variable b as follows:

$$
A\text{ = }
\left[
\begin{matrix}
1 & -1 & 1 \\
1 & 1 & 1 \\
4 & 2 & 1 \\
9 & 3 & 1 \\
\end{matrix}
\right]
\text{; x = }
\left[
\begin{matrix}
B \\
C \\
D \\
\end{matrix}
\right]
\text{; b = }
A\text{ = }
\left[
\begin{matrix}
\frac{1}{2} \\
-1 \\
-\frac{1}{2} \\
2 \\
\end{matrix}
\right]
$$

The usual formulas are then applied.

## Matrix Properties

### Examples

### Facts

#### Number of Solutions

* r = number of pivot variables after row reduction. It is the same for RREF R(A) and C(A).
* Always: r <= n; r <= m.

#### If r=m=n (Square Matrix)
* R = I
* 1 solution, all b vectors are allowed, no constraint on solvability.

#### If r=n and n<=m Full Rank, Possible m>n
* Either 0 or 1 solutions to Ax = b.

#### If r=m and n>m (Extra Columns)
* Typically has form [I F], but F can be interspersed with I.
* Solution always exists.
* No zero rows.
* Infinite solutions because of free variables.

#### If r<m and r<n Extra Rows and Columns
* I and F columns may be interspersed.
* No solution or infinitely many solutions.

#### Examples

* "Suppose you have 3 vectors that are 2-dimensional, i.e. $\overrightarrow{v}_1,\overrightarrow{v}_2,\overrightarrow{v}_3\text{ }\in\text{ }\mathbb{R}^2$ .  Is it possible that they are linearly independent?" -- NO
* How many solutions does the following linear system have?

$$10x\text{ - }2y\text{ + }z\text{ = }1$$
$$x\text{ - }2y\text{ + }3z\text{ = }0$$
$$-2x\text{ + }2y\text{ - }6z\text{ = }1$$

Answer: 0 (it has a zero row = 1).

### Invertibility

#### Facts
* A matrix is only invertible if all columns are independent.
  * Alternate phrases, identical significance:
    * "An inverse exists if and only if elimination produces n pivots."
    * A **diagonal matrix** has an inverse if it has no 0 entries on its diagonal.
* A matrix has only one inverse.
* If A is invertible, then the only solution to [x in] $Ax\text{ = }b$ is $x = A^{-1}Ax\text{ = }A^{-1}b$ .
* If there is a non-zero vector x such that Ax = 0, then A cannot have an inverse.
  * Alternate phrase, identical significance:
     * For invertible matrices, the only solution to Ax=0 is that x is the 0 vector.

#### Examples
* "Suppose a square NxN matrix is invertible. Which of the following is NOT true:
  * The rows of the matrix are linearly dependent -- NOT TRUE
  * The determinant is non-zero -- TRUE 
  * The matrix is full rank -- TRUE
  * The columns of the matrix form the basis for an N-dimensional space."  -- TRUE

* Given the matrix

$$
A\text{ = }
\left[
\begin{matrix}
1 & 0 & -1 \\
-1 & 2 & -1 \\
3 & 0 & 1 \\
\end{matrix} 
\right]
$$

... compute the inverse $A^{-1}$.  What is the entry B =  $A^{-1}$ corresponding to the first row and first column (that is, $b_{11}$ ?  Round your answer to nearest 2 decimals.  

* Answer: 

$$
A\text{ = }
\left[
\begin{matrix}
.25 & 0 & .25 \\
-.25 & 0.5 & .25 \\
.75 & 0 & .25 \\
\end{matrix} 
\right]
$$

So B_11 = .25.  In general, the answer to finding the inverse of an invertible matrix is the AI -- > IA G-J transformation.

### Transposition

#### Facts
*  The transposes of Ax and AB and $A^{-1}$ are $x^TA^T$ and $B^TA^T$ and $\left(A^T\right)^{-1}$ .
*  The transpose of AB is $B^TA^T$ . The transpose of $A^{-l}$ is the inverse of $A^T$ .
*  The dot product (inner product) is x · y = $x^Ty$ . This is (1 x n)(n x 1) = (1 x 1).
*  The outer product is $xy^T$ = column times row = ( n x 1) ( 1 x n) = n x n matrix.
*  An orthogonal matrix has $Q^T\text{ = }Q^{-1}$ . The columns of Q are orthogonal unit vectors.
*  A permutation matrix P has the same rows as I (in any order). There are n ! different orders.
*  When S is symmetric $\left(S^T\text{ = }S\right)$ , its LDU factorization is symmetric: $S\text{ = }LDL^T$  .

### Projection, Projection Matrices

#### Projection Key Equations:

Given a vector a in C(A), a vector b not in C(A), and a factor x by which multiply a to obtain p:

* $xa^Ta\text{ = }a^Tb$ , which leads us to
* $x\text{ = }\frac{a^Tb}{a^Ta}$
* p = ax to get our projection p .
* error e = b - p .
* $P=\frac{aa^T}{a^Ta}b$
* E = sum of squared e components (b1 - p1) ... (bn - pn).

#### Properties of Projection Matrix P

* The column space C(P) is the line through a.  
* The rank of P is therefore always 1.
 * You can see that this is so by considering its structure in the above formula -- the matrix consists of a column times a row.
 * The columm that multiplies the row is the basis for the column space.
* P is symmetric.  The denominator in $\frac{aa^T}{a^Ta}$ is a number, and the transpose of the numerator is again $aa^T$ .  Thus, $P^\text{ = }P^T$ .  **This is a key property of projection matrices.**
* If we do the same projection twice, that is if we take $P^2$, we still get P.
* **Thus, the 2 key properties that distinguish a projection matrix are:**
 * $P^T\text{ = }P$ , and
 * $P^2\text{ = }P$
   * This last property can be a bit hard to swallow, so consider a real example:

$$
P\text{ = }\frac{1}{9}
\left[
{\begin{matrix}
1 & 2 & 2 \\
1 & 2 & 2 \\
1 & 2 & 2 \\
\end{matrix} } 
\right]
$$

  * In order for $P^2\text{ = }P$, all values of P must be positive.  An additional property results:
    * P is positive semidefinite: $x^TPx\geqq{0}$ , for all x.  Because all vectors in P are $geqq{0}$ , and all x components are squared.

## LU Decomposition

### Steps/Method
* LU Factorization or Decomposition of A multiplies A by a series of "elimination" matrices E.
* It requires fewer computation steps than G-J AI transformation, but is maybe less human-friendly than G-J in a testing context. So for a test, the trick is to do G-J in an orderly way so that you can preserve your thought process, then abstract the Es and ultimately L out of the E-inverses. 

To do LU decomp in a test:
* **If follow-up test questions go on to reduce U to R, then do G-J A->I elimination.**  Otherwise regular row elimination on A is sufficient.
* in the middle of your scratch page copy A.
* put the first update to A resulting from your first row elimination step to the right of it.
* do only one unique row elimination step at a time, on the right side of the page, in a column showing each successive change to A in order top to bottom.  Stop when you get to U; no further elimination is advisable.
* when you have gotten to U:
  * moving to the left of A in the first row, write in the elimination matrix E_1 that would multiply A to get the first modified A_2 result on the right.
  * move to the next row.  In the middle column, copy in A_2.  To the left of it, write in the matrix E_2 that would multiply A_2 in the middle column to give the result A_3 on the right, and so on.  
  * When you have finished the last row ending in U, calculate L.

* Calculating L:
  * starting from the bottom row of your work, create $E^{-1}$ out from your last row's E, and put it in a new row toward the right of your page, leaving room to the left.
    * if you have been careful to do only one discrete elimination step at a time, creating $E^{-1}$ should only involve changing a sign on a single off-diagonal value in the corresponding E.
    * to the left of your first $E^{-1}$, put the next $E^{-1}$ created from the E in the second-to-last row.  Proceed in this way till you process the E in the top-most row.
    * Multiply these inverse matrices from left to right.  Their product is L, which is also called $E^{-1}$ in the literature.

* QA: check that LU = A .

## EA = R Updating

* EA = R updating is the same process as multiplying successive Es on A as was used in LU = A factorization.
* However, we continue to multiply Es on A until A becomes R.
* The Es are multiplied left to right in original order into one E.  Check that this E multiplied on A = R.

## Ax = 0 Special Solutions

### Facts
* If for a matrix R, r pivots < n columns, there will be n-r special solutions for n-r "free columns".
* If the size of A has n > m, there will always be at least 1 free column.
* The process for calculating solutions to Ax = 0 when r < n involves:
  * reducing the matrix to R
  * toggling each free variable to 1, and the others to 0, in order, then solving via substitution for the remaining values.
    * **when you solve the equations, they should be set to 0, since you're solving for the nullspace.**

### Examples:

#### Create Matrix from Special Solutions
* Details: For a set of special solutions, create a matrix R to which those special solutions would apply.

* Example:
* Create a 3 by 4 matrix R whose special solutions to Rx = 0 are $s_1$ and $s_2$:

$$
s_1
\text{ = }
\left[
{\begin{matrix}
-3 \\
1 \\
0 \\
0 \\
\end{matrix}}
\right]
\text{and  }s_2\text{ = }
\text{ = }
\left[
{\begin{matrix}
-2 \\
0 \\
-6 \\
1 \\
\end{matrix}}
\right]
$$

Solution: 
*  Note the size of the matrix and compare it to the number of pivots shown in the special solutions.  There are 2 special solutions and 4 columns, making 2 pivots. Because r is the same for C(R) and R(R), there is one row without pivots, which means row 3 will zero out in R.
*  The toggle 1 and 0 values in the special solutions tell you where the pivot columns are in C(R).
  *  Create an empty matrix of the prescribed size, filling in any pivots =1 (because it is R), and any known 0 rows at the bottom.
  *  Anything to the left of a pivot column must be 0.
  *  Comparing the values of the special solution to the remaining empty spaces in the pivot rows, you should be able to work out the values by elimination.
    *  For example, since the first special solution above has -3,1 in its first 2 components, and opposed 1,3 in the pivot row will cause the values to 0 out.

## Ax = b Complete Solutions

### Facts
* A has full column rank r = n when its nullspace N(A) = zero vector: no free variables.
* When Rx = d is solvable, one very particular solution $x_p$ has all free variables equal to zero.
* A has full column rank r = n when its nullspace N(A) = zero vector: no free variables.
* A has full row rank r = m when its column space C(A) is Rm : Ax= b is always solvable.

### Method
For a matrix A with m < n , where b in Ax = b is not equal to 0:
* Reduce Ab to Rd
* If for some reason b is a vector of variables, and a row is reduced to 0's, then b's arrangement of variables in state d are a "solvability condition" on R.
* Write out the remaining pivot rows as equations.
* Obtain the **particular solution** by setting the **free** variables to 0, and solving for the remaining pivot variables via back-substitution.
* Now obtain the special solutions by toggling each free variable to 1 in turn, and setting other free variables to zero. **Set the entire equations = 0, because you are solving for the nullspace.**  Solve for the remaining values via back-substitution.  You should have 1 special solution for each free variable.
* The complete solution is written as : vector for particular solution + (free variable 1 * vector for special solution 1) + ... + (free variable n * vector for special solution n) , e.g:

$$
x\text{ = }x_p\text{ + }x_n\text{ = }
\left[
{\begin{matrix}
2 \\
1 \\
0 \\
\end{matrix}}
\right]
\text{ = }x_3
\left[
{\begin{matrix}
-3 \\
2 \\
1 \\
\end{matrix}}
\right]
$$

## Singular Value Decomposition

### Facts
* The SVD produces orthonormal basis of v's and u's for the four fundamental subspaces.
* Using those bases, A becomes a diagonal matrix $\Sigma$ and $Av_i\text{ = }\sigma_iu_i$ : $\sigma_i$ = singular value.
* The two-bases diagonalization $A\text{ = }U\Sigma{}V^T$ often has more information than A = $X\Lambda{}X^{-1}$ .
  * U and V are orthonormal; that is why the formula can use the transpose rather than the inverse (which is the same as the inverse in the orthonormal case).  $A\text{ = }U\Sigma{}V^{-1}\text{ = }U\Sigma{}V^T$
* $U\Sigma{V^T}$ separates A into rank-1 matrices $\sigma_1u_1v_1^T+\ldots+\sigma_ru_rv_r^T$ , in order -- $\sigma_1u_1v_1^T$ is the largest value.
* A is $U\Sigma{V^T}$, so $A^T$ is $V\Sigma{}^TU^T$, and $A^TA\text{ = }V\Sigma{}^TU^TU\Sigma{}V^T$ . The sigmas then are eliminated as "I". Similarly, $AA^T$ moves U to the middle for elimination.

* The SVD factors A into $U\Sigma{V^T}$ , with r singular values $\sigma_1\geq{}\ldots\geq{\sigma_r}>0$ .
2. The numbers $\sigma_1^2,\ldots,\sigma_r^2$ are the nonzero eigenvalues of $AA^T$ and $A^TA$ .
3. The orthonormal columns of U and V are eigenvectors of $AA^T$ and $A^TA$ .
4. Those columns hold orthonormal bases for the four fundamental subspaces of A.
5. Those bases diagonalize the matrix: $Av_i\text{ = }\sigma_iu_i$ for $i\le{r}$ . This is $AV\text{ = }U\Sigma$ .
6. A = $\sigma_1u_1v_1^T+\ldots+\sigma_ru_rv_r^T$ ; and $\sigma_1$ is the maximum of the ratio $\|\|Ax\|\|/\|\|x\|\|$ .

### SVD: Review of Basic Activity

Remember that:
* In V:
  * $v_1$ up to $v_r$ is an orthonormal basis for the row space.
  * $v_{r+1}$ up to $v_n$ is an orthonormal basis for the null space. 
* In U:
  * $u_1$ up to $u_r$ is an orthonormal basis for the column space.
  * $u_{r+1}$ up to $u_m$ is an orthonormal basis for the (left) null space of $A^T$ .

-- It is these bases *which make the matrix diagonal* , AND $Av_i\text{ = }\sigma_iu_i$ .
-- The overall insight about this summary is that it diagonalizes the matrix into its consituent components while correctly accounting for all 4 fundamental subspaces.  

## Positive Semidefiniteness
* Relation of projection matrices to positive semidefiniteness.
* True: All projection matrices are positive semidefinite.
* 

## Rules for Subspace Orthogonality

*  Orthogonal vectors have $v^Tw$ = 0. Then $\text{||v||}^2\text{ + }\text{||w||}^2\text{ = }\text{||v + w||}^2\text{ = }\text{||v - w||}^2$ .
*  Subspaces V and W are orthogonal when $v^Tw$ = 0 for every v in V and every w in W.
*  The row space of A is orthogonal to the nullspace. The column space is orthogonal to $N\left(A^T\right)$ .
*  N(A) is the orthogonal complement of the row space C(AT ) (in $R^n$ ).
*  $N\left(A^T\right)$ is the orthogonal complement of the column space C(A) (in $R^m$ ).
*  The columns $q_1......q_n$ are orthonormal if

$$
q_i^Tq_j
\begin{Bmatrix}
\text{0 for i }\neq{j} \\
\text{1 for i = }j  \\
\end{Bmatrix}
$$ 

.  Then $Q^TQ\text{ = }I$ .

* If Q is also square, then $QQ^T\text{ = }I$ and $Q^T\text{ = }Q^{-1}$.  Q is an orthogonal matrix.

### Independence, Basis, Dimension

* Only vectors can be said to be "in|dependent". This term cannot applie to matrices.
* The rows x columns measure is the **size** of a matrix.
* The set of column vectors with pivots in RREF is the rank r of a matrix. r is the same for columns and rows.

* The number of columns or rows in the the bases are the **dimensions** of C(A) or R(A).  The dimension is a number (count) of basis vectors.
* The set of all linear combinations in C(A) or R(A) is called their span.
* If a set of vectors in a basis for C(A) or R(A) are said to "span" the space of C(A) or R(A).  The vectors being unique, minimal, and sufficient to span the space is said to confirm their status as a basis.
* Only vectors span a space.
* Only vectors form a basis.
* Vectors are *independent* if no vector is a linear combination of any other vectors.  Equivalently, vectors are independent if no vectors can be subtracted from linear combinations of others to = 0.

### Getting Bases for Four Subspaces

* The columns or rows of A that correspond to the pivot columns and rows of R are the **bases** of C(A) or R(A).
* The special solution columns of A are the basis of N(A).
* For the left nullspace:
  1. To the right of matrix $A_{mxn}$, add $I_{mxm}$ .
  2. Using row elimination, transform AI to RE; that is A will be updated to R, and I will be updated to E.
  3. As noted above, EA = R, but you can keep the AI --> RE format, since the insight will be the same.
  4. Find the row indices of zero rows (if any) in R.
  5. These zero row indices in R will be the indices of the basis in E of the left null space.

### Orthogonality

* Orthogonal means that 2 vectors (or vector spaces) are at a right angle to each other and thus have a dot product of 0.
* An orthogonal complement is a subspace for which every vector in one subspace is orthogonal to every vector in the other subspace.
* R(A) is an orthogonal complement to N(A).
* C(A) is an orthogonal complement to $N\left(A^T\right)$, aka the "left nullspace".

## Subspaces

A set of vectors in linear combination are a subspace of something if:
  * multiplying the vectors produces results that still fit the rules for the subspace
  * adding the vectors produces results that still fit the rules for the subspace
  * the 0 vector is included in the results
* functions, and particular matrix types, can be the bases for subspaces.
* Note: "still fit the rules for the subspace" is frequently phrased as "staying in the space"

### Nullspaces

#### Facts
* The nullspace N(A) in $R^n$ contains all solutions x to Ax = 0. This includes x = 0.
* Elimination (from A to U to R) does not change the nullspace: N(A) = N(U) = N(R).
* Every matrix with m < n has nonzero solutions to Ax = 0 in its nullspace.

When A is an mxn matrix, what is the "location" of each of these subspaces (i.e. which dimension limits them) ?

* Null space of A, N(A) is in $R^n$.
* Column space of A, C(A) is in $R^m$.
* Row Space R(A) = Column Space of C($A^T$) is in $R^n$.
* Left Null space of A, N($A^T$) is in $R^m$.

### Dimensions for the Four Subspaces
* Note: "dimensions" are pivot counts r in R; "sizes" are row m and column n counts in A.
* Column Space: the rank r of the column space (the number of its pivot variables).  = Number of independent vectors in matrix.
* Null space: number of special solutions  = n-r
* Row Space: also r, same as column space.  Dim of R(A) = Dim C($A^T$) = Dim C(A)
* Left Null Space N($A^T$):  m-r; note that m is the number of rows in A or columns in $A^T$ .
* The row space and null space are in $R^n$, and their dimension add to n.
* The column space and left null space are in $R^m$, and their dimensions add to m.

## Compute a Gradient At a Point

Given a function, e.g. $f\left(x,y\right)\text{ = }2y\text{ + }4x^2y\text{ + }1$, and a point, e.g. (1,1):

* For each variable in the equation:
  * for each variable take the partial derivative of that same function.  Do this in the left-right column order of the variables.
  * put the resultant partial derivatives in a single transposed column, starting with the left-most variable's derivative at the top.
* When this process is complete, plug the values from the point corresponding to each variable into the partial derivatives.

### Recursively Update A Gradient

*  Having computed the initial gradient, e.g. (6x, 2y), and given a gamma step value, e.g. .01, and an inital point e.g. (1,1).
  *  Plug the point values into the gradient to get the gradient point a1, e.g. (6,2).
  *  Subtract the product of the gamma step times a1, e.g. .01(6,2) from the intial point, e.g. (1,1) - .01(6,2) = (.4,.8).  The result is updated point a2, e.g. a2 = (.4,.8).
  *  Repeat the process the specified number of times:
    *   an = an-1 - gamma times gradient(an-1), e.g. a2 = (.4,.8) - .01(6(.4),2(.8)) = (.16,.64).

## Eigenvalues, Eigenvectors

### Facts
* **eigenvalues and eigenvectors only exist for square matrices
* **non-zero eigenvalues only exist for square matrices with non-zero determinants.**
* **Review of Eigenvector & Eigenvalues Proof**: an eigenvector is a vector such that Ax = $\lambda{}x$; that is A makes no change in x's direction, and only extends it by some value $\lambda$.  This being the case:
  * Ax = $\lambda{}x$ can be set to $Ax\text{ - }\lambda{}x\text{ = }0$ and the identity matrix inserted, with no change to the equation results to get $Ax\text{ - }\lambda{}Ix\text{ = }0$ .  The distributive property reduces this to $\left(A\text{ - }\lambda{}I\right)x\text{ = }0$ .  It follows that if this equation equals 0, then $x\in{}N\left(A\text{ - }\lambda{}I\right)$ . This is, x is in then nullspace of $N\left(A\text{ - }\lambda{}I\right)$.
  * Assume that $x\in{}N\left(A\text{ - }\lambda{}I\right)$ is not 0.
  * Note that $\left(A\text{ - }\lambda{}I\right)$ is by itself a matrix.  Call it M.
     * M's columns are independent, and its determinant $\neq{}$ 0, iff. $N\left(M\right)$ = 0.  But $x\in{}N\left(M\right)$ is $\neq{}$ 0.  Therefore M's columns are **not** independent, and **$\text{det }\|A\text{ - }\lambda{}I\|\text{ = }0$.**
       * **--It is this finding that lets us solve for eigenvalues $\lambda{}$ in the equation $\text{det}\|A\text{ - }\lambda{}I\|\text{ = }0$ by itself, and then plug the result into $Ax\text{ - }\lambda{}x\text{ = }0$ to obtain the eigenvector x.**
* $\left(A\text{ - }\lambda{}I\right)x\text{ = }0$ is called the **characteristic equation** .  Strang shows this equation with the term $\left(A\text{ - }\lambda{}I\right)$ ; others like Kahn academy reverse it as $\left(\lambda{}I\text{ - }A\right)$ , but the results come out the same either way.
  * For such a matrix A of n columns there will be n eigenvectors.
* If you know the eigevector, you can multiply A on X to see which $\lambda{}x$ reveals $\lambda{}$.
* If you know the eigenvalues, solve $\left(A\text{ - }\lambda{}I\right)x\text{ = }0$ to find x.
* The eigenvalues of AB $\neq$ eigenvalues of A + eigenvalues of B.
* Eigenvalues of AB **are not equal to** eigenvalues of A times eigenvalues of B.
* Eigenvalues of AB and BA **are equal** .
* The product of the n eigenvalues equals the determinant.
* The sum of the n eigenvalues equals the sum of the n diagonal entries (the "trace").

### Computing Eigenvalues and Eigenvectors:

#### 2x2 Case:

* Set up characteristic equation:

$$
\left(A\text{ - }\lambda{}I\right)
\text{ = }
\left[
{\begin{matrix}
1 & 2 \\
4 & 3 \\
\end{matrix}}
\right]
\text{ - }
\left[
{\begin{matrix}
\lambda & 0 \\
0 & \lambda \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
{1\text{ - }\lambda} & 2 \\
4 & {3\text{ - }\lambda} \\
\end{matrix}}
\right]
$$

* take determinant = 0 via 2x2 ad - bc equation:

$$
\text{det}
\left|
{\begin{matrix}
{1\text{ - }\lambda} & 2 \\
4 & {3\text{ - }\lambda} \\
\end{matrix}}
\right|
\text{ = }\left(1\text{ - }\lambda{}\right)\left(3\text{ - }\lambda{}\right)\text{ - }8
\text{ = }\lambda^2\text{ - }4\lambda{}\text{ - }5\text{ = }0
$$

* solve "add terms to get middle, multiply to get outer" --> $\lambda$ : {1,-5} .
* when the matrix A is originally triangular (0 in lower left), the quadratic is already equal to 0 and 2 $\lambda$ terms will be positive.
  * if the matrix A is originally triangular, you may end up with a "degenerate" matrix reduced to R with 1 in the upper or lower left, and 0 otherwise.  In that case, only one eigenvector, some permutation of (1,0), will exist.
* plug each eigenvalue into characteristic equation to compute its eigenvector:

$$
E_{-5}\text{ = }
\left(A\text{ - }\lambda{}I\right)\text{ = }
\left[
{\begin{matrix}
1 & 2 \\
4 & 3 \\
\end{matrix}}
\right]
\text{ - }
\left[
{\begin{matrix}
5 & 0 \\
0 & 5 \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
-4 & 2 \\
4 & -2 \\
\end{matrix}}
\right]
$$

* row reduce result:

$$
\left[
{\begin{matrix}
1 & -\frac{1}{2} \\
0 & 0 \\
\end{matrix}}
\right]
$$

* plug into initial $\left(A\text{ - }\lambda{}I\right)x\text{ = }0$ equation:

$$
\left(A\text{ - }\lambda{}I\right)x\text{ = }
\left[
{\begin{matrix}
1 & -\frac{1}{2} \\
0 & 0 \\
\end{matrix}}
\right]
\left[
{\begin{array}
x_1 \\
x_2 \\
\end{array}}
\right]
\text{ = }0
$$

... so eigenvector $E_{-5}$ is ...

$$
E_{-5}\text{ = }c
\left[
{\begin{matrix}
\frac{1}{2} \\
1 \\
\end{matrix}}
\right]
\text{ = }0
$$

... where c is some scalar.

#### 2x2: Other Methods

* Remember that:
  * the determinant must be the product of the pivots of U.
  * the sum of the eigenvalues = the trace.
  * the product of the eigenvalues = the determinant in the 2x2 case (at least).
  * there is also the formula that the eigenvalues = $m\pm\sqrt{m^2\text{ - }p}$ , where m = mean of a+d, and p = the determinant (aka the product).
  * In the case of a symmetric positive 2x2 matrix, where:
 
$$
A
\text{ = det}
\left(
\left[
\begin{matrix}
{a\text{ - }\lambda} & b \\
b & {a\text{ - }\lambda} \\
\end{matrix}
\right]
\right)
\text{ = }0
$$

...then:

$\rightarrow\left(a\text{ - }\lambda\right)^2\text{ - }b^2\text{ = }0$
$\rightarrow\left(a\text{ - }\lambda\right)^2\text{ = }b^2\rightarrow{a\left{ - }\lambda}\text{ = }\pm{b}$
**$\rightarrow\lambda\text{ = }a\pm{b}$**

Example:

$$
A
\text{ = det}
\left(
\left[
\begin{matrix}
25 & 7 \\
7 & 25 \\
\end{matrix}
\right]
\right)
$$

$\rightarrow{}\lambda_1\text{ = }25\text{ + }7\text{ =}32$ , so $\lambda_2\text{ = }25\text{ - }7\text{ =}18$ , which is also trace = 50 - 18 .

#### 3x3 Case

* This is straight out of: https://www.youtube.com/watch?v=11dNghWC4HI&list=PL472D7015831DBF51&index=5

* Given the matrix:

$$
A\text{ = }
\left[
{\begin{matrix}
-1 & 2 & 2 \\
2 & 2 & -1 \\
2 & -1 & 2 \\
\end{matrix}}
\right]
$$

* Subtract $\lambda{}I$ from A.  (For notational convenience, we will designate the resulting matrix as "M"):

$$
\left(A\text{ - }lambda{}I\right)\text{ = }
\left[
{\begin{matrix}
{-1\text{ - }\lambda} & 2 & 2 \\
2 & {2\text{ - }\lambda} & -1 \\
2 & -1 & {2\text{ - }\lambda} \\
\end{matrix}}
\right]
\text{ = }M
$$

Find the determinant.  (You use product of determinants of U; Kahn uses "rule of Sarrus" and that is probably easier).

* **Rule of Sarrus:**
* For a **3x3 matrix** , make a 3x5 augmented matrix by copying the first 2 columns to the right of initial 3x3, so that they become columns for and 5.
* Add and subtract the diagonal products in the following way:
  * Starting with the first column, take the product of the diagonals from **rc positions** 11 to 33.  To this product add the products of the diagonals for 12 to 34 and 13 to 35.
  * To these sums, subtract diagonals from 15 to 33, 14 to 32, and 13 to 31.
  * The overall pattern product additions and subtractions is 11 to 33 + 12 to 34 + 31 to 35 - 15 to 33 - 14 to 32 - 13 to 31.
  * The pattern looks like this:
 
![Screenshot 2025-06-06 at 4 33 58 PM](https://github.com/user-attachments/assets/d75de182-bfdc-49ff-981f-0d3d90401df3)

  * In this example, the resulting determinant is: $\lambda^3\text{ - }3\lambda^2\text{ - }9\lambda\text{ + }27$ . 

* Find the roots of the determinant polynomial.  In test examples, the roots will typically be integer roots of the constant term (here, 27 --> 1,3,9,27 ).  Try factoring these into the equation.
  * **Remember that:**
    * You can expect n eigenvalues.
    * Eigenvalues can be repeated.
    * Having found a root, you can divide (lambda - that root) into the polynomial to find the other roots, viz:
      ![Screenshot 2025-06-06 at 4 48 11 PM](https://github.com/user-attachments/assets/59eec287-87d7-4c64-ab3e-6ee0465c7682)

      * In this case, the $\lambda$ roots, or eigenvalues, are $\lambda$ : {3,-3}, with 3 being repeated 2x.
 * Plug the eigenvalues into the characteristic equation as with the 2x2 case, to find the eigenvectors.

 
## Jacobians

### Compute a Jacobian 

* A Jacobian Matrix is simply a way of organizing the partial derivatives of a set of functions.
  * For a set of input variables consumed by a set of functions:
    * For the first function, take the derivative of that function with w.r.t. each input variable in turn, from left to right, storing the resultant partial derivatives in a row from left to right.
    * Follow this process for the next function, using the next row.
    * The result should be a matrix with the same function across the variables stored in a row, and the same variable stored across the functions down each column.
    * Do not omit any functions or variables in the placements, even if a function does not use a variable (in which case its partial is simply 0).
    * The Jacobian is this matrix of partials, but it is typically given an input point.  If this point is zero, or it has zero rows or columns, the point is considered critical -- an "inflection point" in a "slope".

### Jacobian Examples

* https://tutorial.math.lamar.edu/Solutions/CalcIII/ChangeOfVariables/Prob2.aspx

* Note that the 3rd and 4th terms are the ad-bc determinant formula results.

#### Example 1

$x\text{ = }4u\text{ - }3v^2$ ; $y\text{ = }u^2\text{ - }6v$


$$
\frac{\partial \left(x,y\right)}{\partial \left(u,v\right)}
\text{ = }
\left|
\begin{matrix}
\frac{\partial \left(x\right)}{\partial \left(u\right)} & \frac{\partial \left(x\right)}{\partial \left(v\right)} \\
\frac{\partial \left(y\right)}{\partial \left(u\right)} & \frac{\partial \left(y\right)}{\partial \left(v\right)} \\
\end{matrix}
\right|
\text{ = }
\left|
\begin{matrix}
4 & -6v \\
2u & -6 \\
\end{matrix}
\right|
\text{ = }
24\text{ - }\left(-12uv\right)\text{ = }-24\text{ + }12uv
$$

#### Example 2

$x\text{ = }u^2v^3$ ; $y\text{ = }4\text{ - }2\sqrt{u}$

$$
\frac{\partial \left(x,y\right)}{\partial \left(u,v\right)}
\text{ = }
\left|
\begin{matrix}
\frac{\partial \left(x\right)}{\partial \left(u\right)} & \frac{\partial \left(x\right)}{\partial \left(v\right)} \\
\frac{\partial \left(y\right)}{\partial \left(u\right)} & \frac{\partial \left(y\right)}{\partial \left(v\right)} \\
\end{matrix}
\right|
\text{ = }
\left|
\begin{matrix}
2uv^3 & 3u^2v^2 \\
-u^{-\frac{1}{2}} & 0 \\
\end{matrix}
\right|
\text{ = }
0\text{ - }\left(-3uu^{\frac{3}{2}}v^2\right)\text{ = }3u^{\frac{3}{2}}v^2
$$


#### Example 3

$x\text{ = }\frac{v}{u}$ ; $y\text{ = }u^2\text{ - }4v^2$

$$
\frac{\partial \left(x,y\right)}{\partial \left(u,v\right)}
\text{ = }
\left|
\begin{matrix}
\frac{\partial \left(x\right)}{\partial \left(u\right)} & \frac{\partial \left(x\right)}{\partial \left(v\right)} \\
\frac{\partial \left(y\right)}{\partial \left(u\right)} & \frac{\partial \left(y\right)}{\partial \left(v\right)} \\
\end{matrix}
\right|
\text{ = }
\left|
\begin{matrix}
-\frac{v}{u^2} & \frac{1}{u} \\
2u & -8v \\
\end{matrix}
\right|
\text{ = }
\frac{8v^2}{u^2}\text{ - }2
$$

## Determinants

### Facts

* Only square matrices have determinants.
  * Only non-singular matrices have non-zero determinants 
  * Only matrices with n pivots have have non-zero determinants 
* When using row reduction during determinant calculations:
  * the determinant changes sign for each row swap
    * consequently, an even number of swaps gives the determinants original sign; an odd number of swaps reverses the original sign.
* the determinant of A = product of pivots in U

### 2x2 Determinant Formula
 = ad - bc

### >2x2 Determinants

#### For a >2x2 Matrix of Real Numbers
* = Product of diagonals of U (ala determinant "property #7" ).
  * Calculate U through row reduction.
  * Multiply diagonals of U.  This is not the same as product of I diagonals, which is always = 5.
 
### For a 3x3 Matrix Using Formulas:
* Use the "Rule of Sarrus" --see above in eigenvector section.

## Properties of Vectors vs Points

### True Statements:
* We can add and subtract vectors, but not points.
* We always think of a vector in relationship to an origin point.
* Vectors have an inherent "direction".

# Appendices

## Derivation Rules
* I've not done derivatives in ages.  These are so you don't get burned doing gradients, Jacobians, etc.

* Constant rule: the derivative of a constant = 0.
  * Example: $f\left(x\right)\text{ = }8\text{; }f'\left(8\right)\text{ = }0$ .
* Power Rule: The derivative of $x^n$ is $nx^{n-1}$. For example, if f(x) = $x^3$, then f'(x) = $3x^2$ .
  * The derivative of a variable to no power (i.e. a power of 1) is 1: $x\text{ = }4u\text{ - }3v^2$ ; $\frac{\partial{x}}{\partial{u}}\text{ = }4$ .
* Product Rule: If f(x) = u(x) * v(x), then f'(x) = u'(x)v(x) + u(x)v'(x).
  * Example: If we set f(x) = $x^2\text{ + }2$ and g(x) = $3x^3\text{ − }5x$ , then f'(x)=2x and g'(x)=9x2−5 .
  * Thus, p'(x)=f'(x)g(x)+g'(x)f(x)=(2x)(3x3−5x)+(9x2−5)(x2+2).
  * Simplifying, we have p'(x)=15x4+3x2−10.
  * To check, we see that p(x)=3x5+x3−10x and, consequently, p'(x)=15x4+3x2−10.
    
* Quotient Rule: If f(x) = u(x) / v(x), then f'(x) = (v(x)u'(x) - u(x)v'(x)) / $\text{[v(x)]}^2$ .
  * Example: use the quotient rule to find the derivative of $q\left(x\right)\text{ = }\frac{5x^2}{4x\text{ + }3}$
    * Let f(x)= $5x^2$ and g(x) = 4x + 3. Thus, f'(x)=10x and g'(x)=4.
    * Substituting into the quotient rule, we have $q\`\left(x\right)\text{ = }\frac{f\`\left(x\right)g\left(x\right)\text{ - }g\`\left(x\right)f\left(x\right)}{\left(g\left(x\right)\right)^2}\text{ = }\frac{10x\left(4x\text{ + }3\right)\text{ - }4\left(5x^2\right)}{\left(4x\text{ + }3\right)^2}$ .
    * Simplifying, we get $q\`\left(x\right)\text{ = }\frac{20x^2\text{ + }30x}{4x\text{ + }3}$
* Chain Rule: If h(x) = f(g(x)), then $h\`\left(x\right)\text{ = }f\`\left(g\left(x\right)\right)\cdot{g\`\left(x\right)}$ .
  * Example: find the derivative of $h\left(x\right)\text{ = }\frac{1}{\left(3x^2\text{ + }1\right)^2}$ .
    * $h\left(x\right)\text{ = }\left(3x^2\text{ + }1\right)^{-2}$
* Sum/Difference Rule: The derivative of a sum or difference of functions is the sum or difference of their derivatives. For example, if f(x) = u(x) + v(x), then f'(x) = u'(x) + v'(x).
* Constant Multiple Rule: The derivative of a constant times a function is the constant times the derivative of the function. If f(x) = k * g(x), where k is a constant, then f'(x) = k * g'(x).
  * Example $\frac{d}{dx}\left(3x^2\right)\text{ = }3\frac{d}{dx}\left(x^2\right)\text{ = }3\*2x\text{ = }6x$.
  * g(x) = $3x^2\text{ + }1$ ; g`(x) = 6x.
  * h`(x) = $-2\left(3x^2\text{ + }1\right)^-3\cdot{6x}\text{ = }\frac{-12}{\left(3x^2\text{ + }1\right)^3}$ .
* General Power Rule: combines power rule and chain rule. If f(x) = $\text{[u(x)]}^n$ , then f'(x) = $\text{n[u(x)]}^{(n-1)}$ * u'(x) .

### Derivation Notes

* When you take the derivative of a multi-variable clause w/r/t a specific variable, you only keep variables related via multiplication. So:
  * $x\text{ = }u^2v^3$ ; $\frac{\partial{x}}{\partial{u}}\text{ = }2uv^3$, but
  * $y\text{ = }u^2\text{ - }4v^2$ ; $\frac{\partial{y}}{\partial{u}}\text{ = }2u$
* When taking the derivative of a fraction of 2 variables, e.g. $\frac{u}{v}$ , it's easier to derive after you arrange them as a product using negative powers, e.g. $uv^-1$.  But when you return to doing regular math on them, return them to fraction form so that you can spot how they cancel out &c more easily.
* 



  
