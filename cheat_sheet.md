
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
* To fit points $\left(t_1,b_1\right)\text{,...,}\left(t_m,b_m\right)$ by a straight line, A has columns (1,....1) and $\left(t_1\text{,...,}t_m\right)$ .
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

## Compute a Gradient

## Eigenvalues, Eigenvectors, Jacobians

### Compute a Jacobian 

## Determinants

### 2x2 Determinant Formula
 = ad - bc

### >2x2 Determinants
-- Product of diagonals of U.

## Number of System Solutions

## Properties of Vectors vs Points

### True Statements:
* We can add and subtract vectors, but not points.
* We always think of a vector in relationship to an origin point.
* Vectors have an inherent "direction".


  
