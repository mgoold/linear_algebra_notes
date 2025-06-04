
# Cheat Sheet

The most concise-yet-recoverable set of notes I can manage.

## Unit Vectors
  * Suppose that is a unit vector. What is the value of the dot product $v\cdot\left(-v\right)$ ?

## Fit, Least Squares

* "Suppose I want to find the linear function of best fit for my data $\\{\left(x_1,y_1,z_1\right)\text{,}\left(x_2,y_2,z_2\right)\text{,...}\left(x_N,y_N,z_N\right)\\}$ where
x,y are the independent variables and z is the target variable.  How many parameters does a general linear function have in this scenario?"
  * Answer: 3.  Count the number of variables for this kind of question.

* "Suppose I have 10 data points $\left(x_i,y_i\right)$ and I want to find the line of best fit. The total sum of squares is given by the following dot product:

$$\left(\overrightarrow{y}\text{ - }X\overrightarrow{\beta}\right)\cdot\left(\overrightarrow{y}\text{ - }X\overrightarrow{\beta}\right)$$

... how many columns does X have in this equation?" **Answer:** 2 (in fact, X could have an aribtrarily large number of columns, but I think what they're getting at is that it has at least the intercept + x term, which is 2 columns.)

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
    * error vector e will be orthogonal to a and thus $a^Te$ will have a 0 dot product.

### Solving $A^TA\hat{x}\text{ = }A^Tb$
* Compute $A^TA$ and $A^Tb$ .
* Put $A^TA$ and $A^Tb$ into an augmented matrix, then put that matrix into RREF form.  The result of the augmented portion is $\hat{x}$ .
* Multiply A on $\hat{x}$ to get p in; this is the closest possible approximation to Ax = b.
* The error term e is then b - p, and the total sum of squared components of e is E. This is the measure of how close p was to b.


## Matrix Properties

### Independence
* "Suppose you have 3 vectors that are 2-dimensional, i.e. $\overrightarrow{v}_1,\overrightarrow{v}_2,\overrightarrow{v}_3\text{ }\in\text{ }\mathbb{R}^2$ .  Is it possible that they are linearly independent?" -- NO

### Number of Solutions

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

#### Example:
* How many solutions does the following linear system have?

$$10x\text{ - }2y\text{ + }z\text{ = }1$$
$$x\text{ - }2y\text{ + }3z\text{ = }0$$
$$-2x\text{ + }2y\text{ - }6z\text{ = }1$$

Answer: 0 (it had a zero row).

### Invertibility
* "Suppose a square NxN matrix is invertible. Which of the following is NOT true:
  * The rows of the matrix are linearly dependent -- TRUE
  * The determinant is non-zero -- FALSE 
  * The matrix is full rank -- TRUE
  * The columns of the matrix form the basis for an N-dimensional space."  -- TRUE

* Given the matrix

$$
A\text{ = }
\left[
\begin{matrix}{cc}
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
\begin{matrix}{cc}
.25 & 0 & .25 \\
-.25 & 0.5 & .25 \\
.75 & 0 & .25 \\
\end{matrix} 
\right]
$$

So B_11 = .25.  In general, the answer to finding the inverse of an invertible matrix is the AI -- > IA G-J transformation.

## Singular Value Decomposition
* Understand SVD of $A^TA\hat{x}\text{ = }A^Tb$ .

## Positive Semidefiniteness
* Relation of projection matrices to positive semidefiniteness.
* True: All projection matrices are positive semidefinite.

## Rules for Subspace Orthogonality

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

### Getting Bases for Each Subspace

* The columns or rows of A that correspond to the pivot columns and rows of R are the *$bases** of C(A) or R(A).
* The special solution columns of A are the basis of N(A).
* For the left nullspace:
  1. To the right of matrix $A_{mxn}$, add $I_{mxm}$ .
  2. Using row elimination, transform AI to RE; that is A will be updated to R, and I will be updated to E.
  3. As noted above, EA = R, but you can keep the AI --> RE format, since the insight will be the same.
  4. Find the row indices of zero rows in R.
  5. These zero row indices in R will be the indices of the basis in E of the left null space.

### Orthogonality

* Orthogonal means that 2 vectors (or vector spaces) are at a right angle to each other and thus have a dot product of 0.
* An orthogonal complement is a subspace for which every vector in one subspace is orthogonal to every vector in the other subspace.
* R(A) is an orthogonal complement to N(A).
* C(A) is an orthogonal complement to $N\left(A^T\right)$, aka the "left nullspace".

## Subspaces
A set of vectors in linear combination are a subspace of something if:
* multiplying the vectors produces results that still fit the rules for the subspace
* adding the vecotrs produces results that still fit the rules for the subspace
* the 0 vector is included in the results

When A is an mxn matrix, what is the location of each of these subspaces?

* Null space of A N(A) is in $R^n$.
* Column space of A C(A) is in $R^m$.
* R(A) = Column Space of C($A^T$) is in $R^n$.
* Null space of A N($A^T$) is in $R^m$.

### Dimensions for the Four Subspaces

* Column Space: the rank r of the column space (the number of its pivot variables).  = Number of independent vectors in matrix.
* Null space: number of special solutions  = n-r
* Row Space: also r, same as column space.  Dim of C($A^T$) = Dim C(A)
* Left Null Space N($A^T$):  m-r; note that m is the number of columns in $A^T$ .
* The row space and null space are in $R^n$, and their dimension add to n.
* The column space and left null space are in $R^m$, and their dimensions add to m.

### Getting Bases for Four Subspaces

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
* eigenvectors and values only exist for square matrices with determinants.

### Computing Eigenvalues and Eigenvectors:

*  For a given equation Ax = 0:
  *  Reformat Ax = 0 to $\left(A\text{ - }\lambda{I}\right)\text{ = }0$, where I and A are matrices of the same size.
  *  Subtract the product of $\lambda{I}$ from A.  This should result in a matrix A that is unchanged except for the diagonal components having lambda subrtracted from them.  --Which this in mind, you could just skip to subtracting lambda from every diagonal term.
  *  Using row reduction, put the matrix A into a upper "U" format.
  *  Take the determinant as the product of the diagonal components, = 0 .  Multiply out and solve for 0.  The results are your eigenvalues.
    *  Note: it is possible to have multiple identical eigenvalues.
    *  It's difficult to calculate eigenvalues for a matrix greater than 2x2.  Hence a test question is likely to be for a 2x2 matrix.
      * This means the quadratic equation $x\text{ = }\frac{-b\pm\sqrt{b^2\text{ - }4ac}}{2a}$ will likely come in handy.
      * If you do have to do a 3x3 matrix, put it into U format as usual, and multiply the determinants to get the polynomial equation to solve for the eigenvalues.
  *  Having computed the eigenvalues, for each eigenvalue, you complete the following steps:
    *  plug each eigenvalue into the matrix M = $\left(A-\lambda{I}$ to get a matrix of values.
    *  reduce M into $U_M$
    *  multiply $U_{M}x$ into its set of equations in x, each set = 0, and solve for each x component ( $x_1,x_2\text{,... etc}$ ).
      * if A is > 2x2, the solution may well involve "special solutions", where the E space involves multiple vectors and scalars.

## Jacobians

### Compute a Jacobian 

* A Jacobian Matrix is simply a way of organizing the partial derivatives of a set of functions.
  * For a set of input variables consumed by a set of functions:
    * For the first function, take the derivative of that function with w.r.t. each input variable in turn, from left to right, storing the resultant partial derivatives in a row from left to right.
    * Follow this process for the next function, using the next row.
    * The result should be a matrix with the same function across the variables stored in a row, and the same variable stored across the functions down each column.
    * Do not omit any functions or variables in the placements, even if a function does not use a variable (in which case its partial is simply 0).
    * The Jacobian is this matrix of partials, but it is typically given an input point.  If this point is zero, or it has zero rows or columns, the point is considered critical -- an "inflection point" in a "slope".

## Determinants

### 2x2 Determinant Formula
 = ad - bc

### >2x2 Determinants
* = Product of diagonals of U (ala determinant "property #7" ).
  * Calculate U through row reduction.
  * Multiply diagonals of U.  This is not the same as product of I diagonals, which is always = 5.

## Properties of Vectors vs Points

### True Statements:
* We can add and subtract vectors, but not points.
* We always think of a vector in relationship to an origin point.
* Vectors have an inherent "direction".


  
