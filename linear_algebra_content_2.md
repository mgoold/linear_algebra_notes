
## Column Space

Sources: 
Strang: https://youtu.be/8o5Cmfpeo6g

Remember the definition of a vector space: a vector space is set of vectors and the operations done on them such that:
* the result of v + w remains in the space
* the result of cv + dw remains in the space
* consequently, the results of all linear combinations of v and w remain in the space

Remember that subspaces of a space fullfill these requirements as well, but may not take up the entire space in which they're found.
* suspaces must go through the origin, since all subspaces can be multplied by 0/the zero vector.

Now suppose I have 2 valid subspaces, P & L, where P is a plane and L is a line. L does not lie on P.  Suppose I take the union of P & L.  Is this also a subspace?
No, it fails because of the addition constraint: if you add a vector from plane P, and a add from line L, you'll get a result vector that is in neither of them.  You will be "outside the space."

Suppose I take the intersection of P & L.  Is this a subspace?  Yes, because by definition they have to intersect at the 0 vector, which is valid for both the addition and multiplication constraints.  In fact, the definition of subspace, requiring its going through the origin, guarantees that any subspaces will have to intersect through the 0 vector.  But further, intersection by its definition will reduce the two subspaces to a common valid subspace.  So for example the intersection of 2 planes will be a line which by definition is a subspace.  Any 2 vectors on that line added together will be on that line, and cV for any vector V on that line will be on that line.

Strang stresses the logical proof of this rather than examples:  suppose I have 2 subspaces S & T.  Any vector in the intersection must be by definition both in S & T.  Consequently any 2 vectors from the intersection added will be in both, and their result will be in both, and the same for multiplication.

### Definition of Column Space

The column space of a matrix A consists of **all linear combinations of the columns.**  I don't see how this is different from the definition of a sub-space.  These linear combinations contain all possible values of Ax, and fill the column space of C(A).  The column space is sometimes said to "span" the columns.  I don't understand what "span" could mean or clarify in this context.

### Dimension m of a Column Space

Sources:
* Strang, p. 132

For an mxn matrix A in the system Ax=b, x is said to be in the $R^n$ subspace, while the column space of A is in $R^m$ subspace.  This can seem counter-intuitive because it's common to speak of a matrix having "n columns".  --Which it does.  The idea however is that the variables $x_1$ ... $x_n$ across the columns are gathered into a vector x that has (from the respective columns) n components.  Each column, on the other hand, is a vector of m rows, and the number m may be much less than n.  This m is thus the vector space (and subspace) of the individual column or columns.  

**It follows that Ax = b is solvable if and only if b is in the column space of A.**

Generally speaking, you cannot solve a linear system Ax=b if A has more rows than it has columns (for example 4 rows and 3 columns, or "4 equations in 3 unknowns"), then we can't fill out the same dimension space as the number of rows.  Typically a 4x3 matrix A would imply that the "fourth dimension"  would go undefined, with the vector x in Ax=b containing only variables (x,y,z).  However, there are examples where a rows>columns matrix A in Ax=b can be solved, e.g.:

$$
\left[
  \begin{matrix}
  1 & 1 & 2 \\
  2 & 1 & 3 \\
  3 & 1 & 4 \\
  4 & 1 & 5 \\
  \end{matrix}
\right]
\
  \left[ {\begin{array}{cc}
   1 \\
   0 \\
   0 \\
  \end{array} } \right]
\
\
  \left[ {\begin{array}{cc}
   1 \\
   2 \\
   3 \\
   4 \\
  \end{array} } \right]
\
$$

The reason this is solvable is that the answer b is already in A.  This is a trivial example of the larger point: 
**Ax = b is solvable if and only if b is in the column space of A.**
Again, the column space of A, or C(A) is the set of all linear combinations of A.

## Column Spaces, (In)Dependence, and Subspaces

Again, look at the matrix $A\text{ = }
\left[
  \begin{matrix}
  1 & 1 & 2 \\
  2 & 1 & 3 \\
  3 & 1 & 4 \\
  4 & 1 & 5 \\
  \end{matrix}
\right]
$.  Any one of these columns could be said to be a linear combination of the other two.  We could for example, throw out column 3 since it lies on the same plane as columns 1 and 2. This would leave us with 2 dimensions in the sense that we'd only have 2 unknowns.

**We can thus call this a "2 dimensional subspace of R4".** --This highlights important conventions:
* "R4", the row count tells us the number of potential dimensions.
* "... dimensional subspace" (the number of independent columns or unknowns) tells us the subspace actually occupied by the system.

## Null Spaces

Sources: 
Strang: https://youtu.be/8o5Cmfpeo6g

For Ax=b, the null space N(A) is the set of solutions x that cause Ax=0.

Looking again at this matrix:

$$
A\text{ = }
\left[
  \begin{matrix}
  1 & 1 & 2 \\
  2 & 1 & 3 \\
  3 & 1 & 4 \\
  4 & 1 & 5 \\
  \end{matrix}
\right]
$$
,  you can see that the vector $\
  \left[ {\begin{array}{cc}
   1 \\
   1 \\
   -1 \\
  \end{array} } \right]
\$

would cause b to be the zero vector.  In general any value c times $\left[ {\begin{array}{cc}
   1 \\
   1 \\
   -1 \\
  \end{array} } \right]
\$

will cause Ax=0.  Note that this includes negative numbers.  

In this case, we have 3 values in **x**, so the solution (nullspace) is in $R^3$, although the column space C(A) was in $R^4$.  

You can see that c$\left[ {\begin{array}{cc}
   1 \\
   1 \\
   -1 \\
  \end{array} } \right]
\$ would make a line using all values of c, and that it would go through the origin where c=0.  This is one condition of the nullspace being a subspace.  

We can also see that the addtion requirement holds.  Suppose that v and w were two different results for different values of 0.  If Av is 0 and Aw is 0, then A(v + w) will also be 0. And A(v + w) = Av + Aw, which is 0 + 0 =0.
Multiplication also holds: any value Av will = 0.  Suppose v was the vector (1,1,-1) and c some value like 12.  Then by association A(12v) = 12Av = 12*0 = 0.
All these property checks together prove that the nullspace is a valid subspace.

The solutions x of the column space, however, when the null space is excluded so that b cannot be the **0** vector, is **not** a subspace in this example.  The reason is that any valid subspace must include the 0 vector.

Note:
* By common usage, **Z** is the letter used for a null space consisting of nothing but zeros.

## Special Solutions to Ax=0

The following process is a complete algorithm for finding all the solutions to Ax=0.

Sources:
*  Strang: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/solving-ax-0-pivot-variables-special-solutions/

By "special solutions", we mean cases when the matrix is structurally difficult to solve because it's not square, or has 0s in the pivot positions, etc.

Suppose we have this matrix: 

$$
\text{A = }
\left[
  \begin{matrix}
  1 & 2 & 2 & 2\\
  2 & 4 & 6 & 8\\
  3 & 6 & 8 & 10\\
  \end{matrix}
\right]
$$

.  You can see right away that column 2 is a multiple of column 1; it's not independent.  Also row 3 = row 1 + row 2; it's not independent of the other rows.  This implies that there will be 0s in the pivot position.

Because there are 3 equations in 4 unknowns, we know there will be some solutions to this equation system.

How do we do elimination in this case, when the matrix is retangular and will have 0s in the pivot position?

There are guideline for elimination under these conditions:
* we will not change the **nullspace** N(A).  That is, we must not change the values of x under which Ax = 0.
* we may change the **column space** C(A).  Remember that the column space is the set of all linear combinations that can be done with the columns.

Thus, Strang says the solutions to the system are not changed because the null space Ax = 0 is unchanged.  That is, the simultaneous solution of all the variables, if such a solution exists, will not be changed.

Beginning elimination, we multiply 2 x the first row and subtract it from the second, and 3 x the first row and subtract it from the third.  This leaves us with:

$$
\text{A = }
\left[
  \begin{matrix}
  1 & 2 & 2 & 2\\
  0 & 0 & 2 & 4\\
  0 & 0 & 2 & 4\\
  \end{matrix}
\right]
$$

Already we have a difficulty, because there are 0 pivots in the second column for both the 2nd and 3rd rows -- so a row exchange is impossible.  

Suppose though that we keep going by doing the following:
* treating $a^{11}$ and $a^{23} as pivots.
* subtracting the 2nd row from the 3rd in order to get 0 in $a^{33}.

This leave us with an "upper" non-triangular matrix we can call "U":

$$
\text{U = }
\left[
  \begin{matrix}
  1 & 2 & 2 & 2\\
  0 & 0 & 2 & 4\\
  0 & 0 & 0 & 0\\
  \end{matrix}
\right]
$$

This form is called "echelon form" because the progression of pivots resembles an irregular staircase rather than a triangle.  There are 3 rows but only 2 pivots.  

The number of pivots is known as the **rank** of the matrix.

We still want to solve Ax=0, but can solve Ux = 0.  Ux = 0 will somehow have the same nullspace as Ax = 0 because it is a transformation of Ax = 0.

Stopping at this point, we can try to do the back substitution.  The solutions process can be described as separating out the [non-zero] pivot columns from the "free variables".

**Free Variables** or better *Free Columns* are so-called because when solving for the transformed equation Ux=0, *any* number can be assigned to the variables for those columns.  In this example, we can assign any value to $x_2$ and $x_4$.  Making these assignments, we can then solve for the other [non-free] variables on the pivot columns.  

For example, we could assign $x_2=1$ and $x_4=0$;  

$$\left[ {\begin{array}{cc}
   { } \\
   1 \\
   { } \\
   0 \\
  \end{array} } \right]
\$$

.  

The current form of Ux=0, expressed as a system of formulas, is:

$$x_1\text{ + }2x_2\text{ + }2x_3\text{ + }2x_4\text{ = }0$$
$$\text{                    }2x_3\text{ + }4x_4\text{ = }0$$

In this situation, we already know that we can find $x_1$ and $x_3$ by back substitution.  But now we can also freely assign values to the other non-pivot variables $x_2$ and $x_4$.  
Using back substitution, we see that $x_3$ is 0, because in the 2nd of the above 2 equations, we've already set $x_4$ to 0.
Continuing back substitution, we solve for $x_1$ = -2.  Filling these in, we have a complete vector x which is in the nullspace:

$$x=\left[ {\begin{array}{cc}
   -2 \\
   1 \\
   0 \\
   0 \\
  \end{array} } \right]
\$$

What solution is this?  It says that -2 times the first column, plus 1 times the second column, gives the 0 column.  We saw this when we looked at the original matrix A, noting that column 2 was 2 times column 1.
We can see that any multiple c of vector **x** would give us another vector in the nullspace.  This would describe a line on the xy plane going through the orgin and -2,1.  This entire line would be in the nullspace.  Is it the entire nullspace? No, because we have 2 free variables, and only selected 1 values for each of them so far.

In fact, the solution algorithm for a special solution matrix like this is to toggle the value of 1 on each of the free variables in succession, and switching all the other free variables to 0.
So, setting $x_2$ to 0 and $x_1$ to 1, we back substitute into 

$$x_1\text{ + }2x_2\text{ + }2x_3\text{ + }2x_4\text{ = }0$$
$$\text{                    }2x_3\text{ + }4x_4\text{ = }0$$

to get

$$x=\left[ {\begin{array}{cc}
   2 \\
   0 \\
   -2 \\
   1 \\
  \end{array} } \right]
\$$

Again, any multiple d times this vector will also be in the nullspace.

Combining these "special" solutions, we can summarize the complete set of solutions to Ux=0, which will be a linear combination of these 2 vectors:

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
$$

The "special solutions" are these arrays that result from toggling 1|0 on the free variables.  **The total number of special solutions must equal the number of free variables.**

Note:
In Strang p. 136, a very similar exercise solves 2 equations having variables $x_1$ ... $x_4$, and then shows the solutions as 2 special solution vectors multiplied by scalars x2 and x4, respectively.  --This gives the [I believe] false impression that all variables in each respective special solution vector are factors of x2, or x4.  I think what Strang's actually doing is "re-using" the variables x2 and x4 just as c and d are arbitrarily selected above.  Not 100% sure about this.

Remember that the **rank** of the matrix was the number of pivots, which here was 2.  The number of special solutions was 2.

In general, the number of specials solutions (or free variables) for a matrix with m rows, n columns|variables, with rank r, will be n-r.

Note:
**If no variables are free, and there is a pivot for every row, then the only solution to Ax=0 is x=0. The null spaces for A and U will contain only the 0 vector.   This also means that all vectors in the matrix are independent.**

**The above is a complete algorithm for finding all the solutions to Ax=0.**

### Ax=0 Matrix: Reduced Row Echelon Form.

By convention, we can further organize the above solution matrix A into a matrix R, or "reduced row echelon form".

Returning back to the upper "echelon" matrix U:

$$
\text{U = }
\left[
  \begin{matrix}
  1 & 2 & 2 & 2\\
  0 & 0 & 2 & 4\\
  0 & 0 & 0 & 0\\
  \end{matrix}
\right]
$$

Row 3, which is all 0s, appeared because it was a combination of rows one and two.  

We can actually clean up the matrix further by doing elimination *upward*, so that we have 0s above the pivot.  In this example, we subtract row 2 from row 1, to get:

$$
\text{U = }
\left[
  \begin{matrix}
  1 & 2 & 0 & -2\\
  0 & 0 & 2 & 4\\
  0 & 0 & 0 & 0\\
  \end{matrix}
\right]
$$

This is the RREF(A) or reduced row echelon form of A.  We can clean up further, by setting the pivots equal to 1, when we divide equation 2 by 2.  Remember that the reason you can divide just one row is that each matrix row is originally a single equation in the system, so you could divide both sides by anything you like.  

This leaves you with the final matrix "R":

$$
\text{U = }
\left[
  \begin{matrix}
  1 & 2 & 0 & -2\\
  0 & 0 & 1 & 2\\
  0 & 0 & 0 & 0\\
  \end{matrix}
\right]
$$

.  Notice that we have a 2x2 identity matrix in the pivot columns 1,3 and pivot rows (1,2) in this R format, with 1s on the pivots and 0s above and below them.  The identity matrix is "distributed" across columns 1 to 3 (interrupted by column 2).  

We can re-write the equations for Ax = 0 in terms of this rref format to get "Rx = 0":

$$x_1\text{ + }2x_2\text{ + }0x_3\text{ + }-2x_4\text{ = }0$$
$$\text{                    }x_3\text{ + }2x_4\text{ = }0$$

Returning to the notes about the identity and pivot matrices in R, you can look at these formulae in terms of 2 distinct sub-matrices comprising the first two rows:

$$
\text{pivot matrix, or identity matrix I = }
\left[
  \begin{matrix}
  1 & 0\\
  0 & 1\\
  \end{matrix}
\right]
\text{, free variable matrix F = }
\left[
  \begin{matrix}
  2 & -2\\
  0 & 2\\
  \end{matrix}
\right]
$$

... additionally, there is a row of 0x below the matrices in these first 2 rows.

### RREF and Sign-reversal

Comparing the free variable matrix F to the vector values used in the linear combination format, we can see that the signs of F's values are reversed:

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
$$

.  Why does this reversal of values happen?  To illustrate, suppose we had an R matrix in block form like so:

$$
\text{R = }
\left[
  \begin{matrix}
  I & F\\
  0 & 0\\
  \end{matrix}
\right]
$$

where I is the identity matrix and F is the block of free variables.  We know that we want to find a vector N such that RN = 0.  This vector N would then need to have the form:

$$
\text{N = }
\left[ {\begin{array}{cc}
   -F \\
   I \\
  \end{array} } \right]
$$

.  ...It's pretty abstract, but if you multiply block matrix R by vector N in the usual way, just as they are, you'll see that this will end up giving you a 0 vector.  This shows you why the signs get reversed.

### Simplifying Rx=0 via RREF 

How is the equation Rx=0 simplified in light of the above.
Considering RN=0 as a system of equations Rx=0, we've said that R = [IF], and **x** is comprised of ($x_pivotvariables$, $x_freevariables$), and Rx = 0.  Remember that we multiply a single row matrix Ax like a1\*x1 + a2\*x2 ... + an\*xn.  So, 

$$
\text{[IF]}
\left[{\begin{array}{cc}
   x_pivotvariables \\
   x_freevariables \\
\end{array} } \right]
\text{ = }
x_pivotvariables\text{ + }Fx_freevariables\text{ = 0; }
x_pivotvariables\text{ = }-Fx_freevariables
$$

This is a simplified as the formula Rx=0 can be.

### RREF Simplication: Additional Example

Suppose we now tried to simplify and solve the transpose of A above:

$$
A^T\text{ = }
\left[
  \begin{matrix}
  1 & 2 & 3\\
  2 & 4 & 6\\
  2 & 6 & 8\\
  2 & 8 & 10\\
  \end{matrix}
\right]
$$

We can immediately see that row 2 will be a 0 row as it is a multiple of row 1.  And column 3 will be a 0 column as it is a sum of columns 1 and 2.

Simplifying the matrix looks like this:

* 2 x row 1 subtracted from row 2 (yields 0 row)
* 3 x row 1 subtracted from row 3.
* 2 x row 1 subtracted from row 4.

then:

* row exchange 3 to 2
* 2 x row 2 subtracted from row 4 (yields 0 row)

$$
A^T\text{ = }
\left[
  \begin{matrix}
  1 & 2 & 3\\
  0 & 0 & 0\\
  0 & 2 & 2\\
  0 & 4 & 4\\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 2 & 3\\
  0 & 2 & 2\\
  0 & 0 & 0\\
  0 & 0 & 0\\
  \end{matrix}
\right]
$$

This takes us from initial matrix A to matrix form U.  Again, the rank of this matrix is 2, because it has 2 pivots.  

**In fact, the number of pivot columns for A and A^T will always be identical**.

However, there will only be n-r = 1 special solutions this time.  The pivots are columns 1 and 2, and the free variables are column 3 (0).

We begin the substitution process for the free variable in **x**, which has just 3 variables.  We set $x_3$ to 1, because if we set it to 0 we'll just get the trivial solution of all 0s.

$$
\text{ x = }
\left[ {\begin{array}{cc}
   1 \\
   2 \\
   1 \\
  \end{array} } \right]
$$

The corresponding equation system looks like:

$$x_1\text{ + }2x_2\text{ + }3x_3\text{ = }0$$
$$\text{      }2x_2\text{ + }2x_3\text{ = }0$$

When $x_3$ = 1, then x_2=-1, and x_1 = -1. Looking over the columns in A, you can see that when they are multiplied by these values they will 0 out. The full nullspace will be c**x**, which is a line.  

Continuing to revise U to rref form R looks like this:

* subtract row 2 from row 1
* divide row 2 by 2

$$
\left[
  \begin{matrix}
  1 & 2 & 3\\
  0 & 2 & 2\\
  0 & 0 & 0\\
  0 & 0 & 0\\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 0 & 1\\
  0 & 1 & 1\\
  0 & 0 & 0\\
  0 & 0 & 0\\
  \end{matrix}
\right]
$$

Again we see that the matrix form R is comprised of an identity matrix and a remainder of free variables F.  Notice again that after rref reduction the nullspace **x** looks like:

$$
\text{ x = }
\left[ {\begin{array}{cc}
   -1 \\
   -1 \\
   1 \\
  \end{array} } \right]
$$

, where 1 is actually the identity matrix, and -1,-1 are the pivot variables, repeating the necessary N = (-F,I) pattern we saw in the previous example.

### Ax=0 Special Solutions: Recitation Example

Source:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/solving-ax-0/

### Part 1:

Find the set of S points (x,y,z) s.t. x - 5y + 2z = 9 is a _______ in $R^3$.

Answer: a plane in R3.

The lecturer asserts that if you have the 3d space R3, asserting an equation in that space will lose you 1 degree of freedom, thus your equation can only move in 2 dimensions.  I believe what she means is that, since an equation with 3 variables is constrained to equal a specific value, only 2 variables can freely assign values before the third must have its value determined.  The equation has all its variables to the power of one, and since only 2 of them can move at a time, the most space it can occupy is a plane.  

Incidentally, using matplotlib, the plane should look something like this:

<img width="452" alt="Screenshot 2025-03-18 at 17 35 01" src="https://github.com/user-attachments/assets/79a20ae3-7390-4f78-9654-4ffc80d4c0dd" />

It is _paralell______________ to the __plane___________ $S_0$ P(x,y,z) s.t. x - 5y + 2z = 0.

Answer: $S_0$ is also a plane by this consideration.  Looking at the 2 equations, it's obvious that they would be parallel.  But if you tried to solve it as a system of two equations, after one step you would end up with 0=9, which is impossible.  The fact that no values which can satisfy both equations means that they can ot intersect, and the only condition in which they cannot intersect is parallelism.

### Part 2:

We are told that all points of S have the form:

$$
\left[ {\begin{array}{cc}
   x \\
   y \\
   z \\
  \end{array} } \right]
\text{ = }
\left[ {\begin{array}{cc}
   { } \\
   0 \\
   0 \\
  \end{array} } \right]
\text{ + }c_1
\left[ {\begin{array}{cc}
   { } \\
   1 \\
   0 \\
  \end{array} } \right]
\text{ + }c_2
\left[ {\begin{array}{cc}
   { } \\
   0 \\
   1 \\
  \end{array} } \right]
$$

To understand the answer to this question, consider the following:

* Call the space $S_0$ the plane for the equation x - 5y + 2z = 0 .  It is clear that (0,0,0) is a point in that plane, since this would yield the result = 0. 
* Call the space S the plane for the equation x - 5y + 2z = 9 . The point P (9,0,0) must be a point in the plane for this equation, since it would yield the result = 9.
* We can thus think of the point P (9,0,0) as one end of a vector that extends up from (0,0,0) to (9,0,0).
* It follows from this that we can reach any point in S (x - 5y + 2z = 9) by going to the point (9,0,0) on it, and then adding the vector from 0,0,0 to some point on the parallel plane $S_0$.
* In words, this means that any point in S = point P + Any corresponding point in $S_0$.

How would calculating a point in S like using this approach actually work?  Consider that we are solving for 3 variables x,y,z.  So that vector of variables will be one side of the equation.  To solve for that vector on the other side of the equation, we start with the fixed point P (9,0,0), which starts us in the plane S. Then we add to it 2 fixed vectors for $S_0$ that can each be multiplied by respective scalars to "stretch" as needed.  These 2 moving vectors when added to (9,0,0) will create a new vector extending to the desired point.

Consider that $S_0$ can be re-written as a system comprised of a matrix of scalars times a vector of its variables, viz:

$$
\left[1,-5,2\right]
\left[ {\begin{array}{cc}
   x \\
   y \\
   z \\
  \end{array} } \right]
\text{ = }\left[0\right]
$$

Like any other system, we begin by doing row reductions on the matrix.  It happens that this one is already entirely reduced.  The 1 in [1 -5 2] is in the only pivot position, and is actually a tiny identity matrix, and the -5,2 elements are free variables.  I think if the value in the pivot position were not already = 1, then you'd have to divide the equation to reduce it to 1.

We know there is a procedure for solving for these free variables serially, by setting each one to 1, and the other free variables to 0, in turn, and solving for the remaining variable.

Doing this procedure for x - 5y + 2z = 0, we get:

* y = 1, z = 0, so x = 5
* y = 0, z = 1, so x = -2

#### Key Notes on Free Variable Process:

* Considering these results, we can see that the procedure **decompose** a single equation into two vectors, each operating in only 2 dimensions at once. Added together, they yield the result of the single formula x - 5y + 2z = 0.
* We can see indirectly why it's "convenient" to divide the pivot variable down to a value of 1.  --It sets any value for x in terms of "1x" rather than "cx".  

Now we can plug these 2 values for x into the two decomposed vectors, along with their respective scalar variables, into the formula for any point in S:

$$
\left[ {\begin{array}{cc}
   x \\
   y \\
   z \\
  \end{array} } \right]
\text{ = }
\left[ {\begin{array}{cc}
   9 \\
   0 \\
   0 \\
  \end{array} } \right]
\text{ + }c_1
\left[ {\begin{array}{cc}
   5 \\
   1 \\
   0 \\
  \end{array} } \right]
\text{ + }c_2
\left[ {\begin{array}{cc}
   -2 \\
   0 \\
   1 \\
  \end{array} } \right]
$$

The end.

## Complete Solutions for Ax=b

The purpose of this content is to detail how rank (the number of pivots in the matrix), relative to the number of rows m and columns n, tells you how many solutions exist for a given matrix system Ax=b.  It also explains why these limits occur.

### Sources
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/solving-ax-b-row-reduced-form-r/

Ax = b does not always have a solution.  If it does have a solution, we want to completely determine what they are.

Consider the following equation system:

$x_1\text{ + }2x_2\text{ + }2x_3\text{ + }2x_4\text{ = }b_1$
$2x_1\text{ + }4x_2\text{ + }6x_3\text{ + }8x_4\text{ = }b_2$
$3x_1\text{ + }6x_2\text{ + }8x_3\text{ + }10x_4\text{ = }b_3$

Remember that equation 3 is the sum of equation 1 + 2, and column 2 is a multiple of column 1.

On the right side, b3 must equal b1 + b2, since that is how the left side works.  Otherwise, there will be no solution to the system.  I believe "no solution" means that the equations do not intersect.

Turning the above equation into a matrix system using an augmented matrix format, we have:

$$
\left[Ab\right]\text{ = }
\left[ {\begin{array}{cc}
   1 & 2 & 2 & 2 & b_1 \\
   2 & 4 & 6 & 8 & b_2 \\
   3 & 6 & 8 & 10 & b_3 \\
  \end{array} } \right]
$$

...which we can turn into the following through row reduction:

$$
\left[Ab\right]\text{ = }
\left[ {\begin{array}{cc}
   1 & 2 & 2 & 2 & b_1 \\
   0 & 0 & 2 & 4 & b_2-b_1 \\
   0 & 0 & 0 & 0 & b_3-b_2-b_1 \\
  \end{array} } \right]
$$

Note that the last equation (row 3) says that 0 = b3-b2-b1.  We have already said that b3 must equal b2 + b1, so this makes sense.  We can all this the "condition for solvability."  --Any solution must have this specific left-right relationship shown in the 3rd row.  So for example, if our numbers for **b** were (1,5,6) then results in the row reduced form above would be, for row 1: 1, for row 2: b2-2b1=3, and b3-b2-b1=0, which checks.  

From this point, we can continue to solve the 2 remaining equations, which were not dependent other equations, in terms of 4 unknowns.  As we do so, we want to continue to track the conditions on b that make the equation solvable, i.e. its "solvability" for Ax=b.  

Note/remember that we *can* define solvability in terms of the column space: Ax=b is solvable i.o.i. b is in the column space of A, or "C(A)".  All this means is that b has to be a result of a linear combination of the columns.  

We can also phrase solvability requirements in terms of rows: IF a combination of rows of A gives a 0 row, then b must sum to 0 via the same combination.  

Both of these statements, in terms of rows and of columns, give different solvability conditions that yield the same solution.  They must therefore somehow be equivalent.  

The primary question and focus of this activity is: does a given system have 0, 1, or >1 solutions?  The summary to these answers will be given below.

Continuing to solve the above matrix with a complete solution to Ax=b for the above matrix, we begin by finding a particular solution "$x_{particular}$".  To do this, we:
* set all the free (non-pivot) variables to zero.  In this case, the free variables are $x_2$ and $x_4$.
* then, solve Ax=b for pivot variables. Remember that we've already **b** to a specific point (1,3)

In this example, setting the free vars to zero and setting the b values from a specific point reduces the 2 remaining equations in the system to:

$x_1\text{ + }2x_3\text{ = }1$
$2x_3\text{ = }3$

Via back-subsitution, $x_3=\frac{3}{2}$, and $x_1$=-2.  So the final point "x particular" or $x_p$ looks like:

$$
x_p\text{ = }
\left[ {\begin{array}{cc}
   -2 \\
   0 \\
   \frac{3}{2} \\
   0 \\
  \end{array} } \right]
$$

Next, we take this particular point and plug it into the original system. To do this, you had to $x_p$ any (all the) points out of the null space.  That is:

**The complete solution to Ax=b = $x_p$ + $x_nullspace$.**

Why does this pattern occur?  --It occurs wherever we have linear equations.  Answer:

* Note that:
  * A$x_p$ = b.
  * A$x_nullspace$ = 0.
 
Thus xp + x0 is b + 0 = b.

So if we have one solution, we can add anything in the null space, because anything in the null space has a zero right hand side, and I still have the correct right hand side b.  

Returning to our example (the nullspace x solutions are taken from an earlier solve elsehwere for Ax=0 on this same matrix).

$$
x_{complete}\text{ = }
\left[ {\begin{array}{cc}
   -2 \\
   0 \\
   \frac{3}{2} \\
   0 \\
  \end{array} } \right]
\text{ + }c_1
\left[ {\begin{array}{cc}
   -2 \\
   1 \\
   0 \\
   0 \\
  \end{array} } \right]
\text{ + }c_2
\left[ {\begin{array}{cc}
   -2 \\
   0 \\
   -2 \\
   1 \\
  \end{array} } \right]
$$

Note that we have constants to multiply the nullspace vectors in this complete solution, but no constant multiplies the particular solution; this is dissallowed.  That is, we cannot multiply $x_p$ because it was solved such that A could act on it to yield a specific point b in $Ax_p\text{ = }b$.  If we multiply $x_p$ by anything it will no longer yield that specific point, and the whole solution would be off.  --I found this confusing at first because I kept confusing $x_p$ with its antecedent b=(1,5,6).  I believe it *is* true that you could take for example (3,4,7) for b in this example, which also yields a 0 solution, and then solve for $x_p$ in terms of that, and everything would work out.

The solution for Ax=b has four unknowns, so the solution is in R4.  The solutions do not form a subspace, but the nullspace, which has 2 dimensions in this case is a subspace in 2 dimensions because it has 2 parameters.  In R4, it will be a plane, although not extending into in 3 dimensions.

**In fact, a subspace's dimensions equals the numbers of parameters it has-- the number of free, independent constants what we can choose.**

How does the function in this example actually work?  

The key is to understand that the null solution extends from the particular point.  In this way this solution is very similar to [this recitation example](#ax=0-special-solutions-recitation-example) .  At first, I expected that all the solutions for b that were covered here were just one point, and the null space.  This didn't make sense to me because I reasoned that you could solve for (in this example) (3,4,7) instead of (1,5,6), thus meeting the same solveability condition, and go through the same process with a slightly different, exclusive outcome that would not be covered by whatever you did for b = (1,5,6).  Based on the video lecture though, I believe that extending from xp for b=(1,5,6) via the special nullspace solution will also extend to xp for b=(3,4,7) and any other b that meets the solvability criterion.

### General Findings on r,n,m and Number of Solutions

In this section we consider the solutions available for m x n matrices with a rank of r.

Remember that: 
* the definition of rank is the number of pivot variables in the matrix after row reduction.
* r may be less than m, but it cannot be greater.  r <= m.
* r may be less than n (consider a 2 by 4 matrix), but it cannot be greater. r <= n.

#### Full Column Rank r=n

* Remember that:
  * with full column rank r=n here are as many pivots as columns.
    * in this situation, by definition there can be no free variables, since fv=n-r.
      * thus only the particular point will be a solution for Ax=b, if it exists, since there can be no special solutions
      * the nullspace N(A) will thus be nothing but the zero vector
    * the matrix will not be invertible; all vectors will be independent
    * **full column rank r=n means there will be 1 or 0 solutions**

A typical full column rank r=n example:

$$
A\text{ = }
\left[ {\begin{array}{cc}
   1 & 3 \\
   2 & 1 \\
   6 & 1 \\
   5 & 1 \\
  \end{array} } \right]
$$

This would have the RREF form:

$$
R\text{ = }
\left[ {\begin{array}{cc}
   1 & 0 \\
   0 & 1 \\
   0 & 0 \\
   0 & 0 \\
  \end{array} } \right]
$$

Only the first 2 rows are independent.  It fulfills the r=n full rank condition.  A solution x for b, when x is solved for in terms of this rref matrix, will be one that is a combination of the columns in A, for example b = (4,3,7,6), in which case x = (1,1) exclusively.  Otherwise x will have no solution.  

#### Full Column Rank r=m

We can generate a typical example of an r=m matrix by transposing the above matrix A:

$$
A^{T}\text{ = }
\left[ {\begin{array}{cc}
   1 & 2 & 6 & 5 \\
   3 & 1 & 1 & 1 \\
  \end{array} } \right]
$$

Its RREF form would be:

$$
A^{T}\text{ = }
\left[ {\begin{array}{cc}
   1 & 0 & 4 & 3 \\
   0 & 1 & 1 & 1 \\
  \end{array} } \right]
$$

Obviously there are m pivots.  There may be more columns than pivots though, as there are here, in which case you can have > 1 solution since you will can haz n-(r=m) free variables.

Columns 1 and 2 here are the I matrix, and columns 3 and 4 are the F matrix.

For which right hand sides can we solve an r=m matrix?  Actually we can solve Ax=b for every b. A solution always exists.  This is because we didn't get any zero rows, as in [this example](#complete-solutions-for-ax=b) .  Thus there is not constraint that vector **b** equate to 0 using the same combination as the left hand side.  

#### Full Column Rank r=m=n

* This case will obviously be a square matrix.
* It will always be invertible.
* The zero vector Z will be its only solution N(A) because all the pivots are full and there are no free variables.
* The RREF form will be I.
* There are no conditions to solve Ax=b because the RREF is I.  Therefore x can always be b, and any b can be selected.
* Because r=n, there is also a unique solution \[I believe what this means is for a *single* vector **b**, there is only one solution, which is x=b.  Contrast this with situations where there are free variables, so that there might be >1 solution x for the nullspace.\]

### R,M,N Relations and Ax=B Solutions Summary

#### r=m=n

* R=I
* 1 solution, all **b** vectors allowed, no constraint on solvability.

#### r=n<m

Meaning r=n, but there may be extra rows

$$
R\text{ = }
\left[ {\begin{array}{cc}
   I \\
   0 \\
  \end{array} } \right]
$$

* 0, or 1 solutions to Ax=b

#### r=m<n

r=m, but there may be extra columns

Described as typically having the form:

$$
R\text{ = }\left[\text{I F}\right]
$$

... however, the I columns may be interspersed with F columns.

* A solution always exists.
* There are no zero rows, so there is no constraint that b = 0 in a way corresponding to the left side of the equation.
* Infintely many solutions, because the free variables confer infinite numbers in the null space.

#### r<m, r<n

$$
R\text{ = }
\left[ {\begin{array}{cc}
   I & F \\
   0 & 0 \\
  \end{array} } \right]
$$

... where I and F columns may be interspersed.

* Either no solution, because we didn't get 0=0 for some bs (we couldn't meet the **b** = 0 solvability constraint), or there are infinitely many solutions because the constraints can be met AND the free variables confer infinite solutions in the nullspace.

### Solving Ax=b in RREF: Recitation Notes

Sources:
* MIT 18.06:

#### Problem 1:

Find all solutions, depending on b1,b2,b3:

$x\text{ - }2y\text{ - }2z=b_1$
$2x\text{ - }5y\text{ - }4z=b_2$
$4x\text{ - }9y\text{ - }8z=b_3$

Taking this as an augmented matrix [Ab], we can first do row reduction:

$$
A\text{ = }
\left[ {\begin{array}{cc}
   1 & -2 & -2 & b_1\\
   2 & -5 & -4 & b_2\\
   4 & -9 & -8 & b_3\\
\end{array} } \right]
\rightarrow
\left[ {\begin{array}{cc}
   1 & -2 & -2 & b_1\\
   0 & -1 & 0 & {b_2-2b_1}\\
   0 & -1 & 0 & {b_3-4b_1}\\
\end{array} } \right]
\rightarrow
\left[ {\begin{array}{cc}
   1 & -2 & -2 & b_1\\
   0 & -1 & 0 & {b_2-2b_1}\\
   0 & 0 & 0 & {b_3-2b_1-b_2}\\
\end{array} } \right]
\text{ = }U
$$

At this point we can note that the updated matrix U has a solvability condition on row 3.  
Considered as an equation, it says that b_3-2b_1-b_2 must equal 0. An example should be (b1=1,b2=1,b3=3).  If we cannot find a solution that equals 0, it will mean that the system has no solution.

Continuing on, we bring the matrix to its final RREF form:

$$
\rightarrow
\left[ {\begin{array}{cc}
   1 & -2 & -2 & b_1\\
   0 & -1 & 0 & {-2b_1+b_2}\\
   0 & 0 & 0 & {-2b_1-b2+b3}\\
\end{array} } \right]
\rightarrow
\left[ {\begin{array}{cc}
   1 & 0 & -2 & {5b_1-2b_2}\\
   0 & 1 & 0 & {2b_1-b_2}\\
   0 & 0 & 0 & {-2b_1-b2+b3}\\
\end{array} } \right]
\text{ = }R
$$

This leaves the identity matrix (pivot variables) in columns 1 and 2, and a free variable in column 3.  For a matrix of this form, the solution if it exists should be a particular solution for a specific point plus a special solution.  

We solve this in the following way:

Particular Solution:

* Set the free variable z to 0.
* Calculate the valuesfor x and y.  The key here is to understand that since we solving for x, we formulate the solution in terms of b:

$$
x_p\text{ = }\left[{\begin{array}{cc}
{5b_1-2b_2} \\
{2b_1-2b_2} \\
0 \\
\end{array}}\right]
$$

Special Solution:

Here we are solving for Ax=0, meaning that we are solving by back substitition on the left hand side for each equation set to 0.
There are as many special solutions as we have free variables.  We begin by setting our only free variable z = 1.  If there had been additional free variables, they would have been set to 0 while we solved for z's special solution, then we would have set each = 1 in turn.

(reverse order for back substitution):

z = 1;
1y = 0 --> y = 0;
1x - 2z --> x = 2;

so:

$$
x_s\text{ = }c\left[{\begin{array}{cc}
2 \\
0 \\
1 \\
\end{array}}\right]
$$

Putting these together, all solutions have the form: ${\overrightarrow{x}\text{ = }\overrightarrow{x_p}\text{ = }c\cdot\overrightarrow{x_s}}$ .

We should further be able to substitute in a specific point for $x_p$:

We selected a point (1,1,3) that fulfilled the 0 solvability requirement on line 3 for b.

Our remaining right-side equations are:
5b_1-2b_2 --> 3
2b_1-b_2 --> 1

On the left side, our remaining left-side equations are:

1x -2y = 3 --> x = 5
y = 1

Thus our particular point should be:

$$
x_p\text{ = }\left[{\begin{array}{cc}
5 \\
1 \\
0 \\
\end{array}}\right]
$$

.  Remember that we cannot apply a multiplier constant "c" to the particular point.

## Independence, Basis, and Dimension

Key concepts in this section are linear independence and dependence, the space spanned by a set of linear combinations, and the basis for a subspace of vector, as well as the dimension of that subspace.

Some notes on these terms:
* Only vectors can be said to be "in|dependent".  This term cannot applie to matrices.  
* Only vectors span a space.  
* Only vectors form a basis.
* The dimension is always a number.

Suppose we have an mxn matrix A where m < n.

This means the matrix will have m equations, and more unknowns than equations.  
Therefore, there will be something in the nullspace of A N(A).  There will be some non-zero x values such that Ax = 0.  These will use special solutions.  The basic reason is that, in our RREF solution algorithm, there must be free variables when m < n.  

### Vector Independence

#### Definition

Vectors $x_1$. $x_2$. $x_3$ ... $x_n$ are dependent in some non-zero linear combination of then equals 0.  Conversely if no non-zero combination = 0 they are **independent**.  

#### Examples:

* Suppose we have 2 vectors $v_1$ and $v_2$, such that $v_2$ is just 2$v_1$.  These are clearly dependent, since 2$v_1$-$v_2$ = 0.  
* Suppose we have 2 vectors $v_1$ and $v_2$, $v_1$ extends to 1,1 and $v_2$ is the zero vector.  You might think that these are independent, since no multiple $c_1$ of $v_1$ **except 0** will yield $c_{1}v_1$ + $c_{2}v_2$ will yield 0 except $c_{1} = 0$. But actually it's **dependent**, because if you multiply 0 times $c_1$, you can them multiply any *non-zero value* times the zero vector, thus fulfilling the definition for **dependence.**
  * Thus generally, if any vector in the system is the zero vector, the system must be dependent.
* Suppose we have 2 vectors in 2d extending into the upper right quandrant.  These will be independent.
* Suppose we have 3 vectors in 2d.  These will be dependent, because m < n, and therefore there will be a special non-zero vector solution to Ax = 0.
  
When $x_1$. $x_2$. $x_3$ ... $x_n$  are variables in an equation system, and we're in m dimensional space, then we can always assess in|dependence of the vectors by putting them in the columns of a matrix.  Again, the vectors are independent if the nullspace of A N(A) is Z, only the zero vector.  The columns are dependent if N(A) is anything else.  

In the independent case of Ax = 0, the rank will be r = n with 0 pivots.  Correspondingly, the dependent case of Ax = 0 will have r < n.    


### Vector Spanning

#### Definition of Spanning

To say that vectors $v_1$ ... $v_l$ "span" a space means that the space consists of all linear combinations of those vectors.   Such a space will be the smallest space that can containing those vectors.  The value of the word "span" really ends up being convenience: one word for "consists of all linear combinations of those vectors".  

The span of a column|vector space tells you nothing about the independence of those vectors.  To assess independence, you'd need more information about the particular columns of that matrix.  

What about a set of vectors that spans a space and *is* independent?  In such a case, we have the "correct number of vectors." If we didn't have all of them, we wouldn't have the whole space.  If we had too many vectors, they wouldn't be independent.  This notion of the "correct number of vectors" relative to a space, brings up the concept of **basis**.    

### Basis

#### Definition of Basis

A basis for a vector space is a sequence of vectors V1, V2 ... Vd which have 2 properties:
* the vectors are independent
* span the space

A basis thus completely defines a given subspace.

#### Examples of Basis

* Example 1: Suppose we have a space $\mathbb{R}^3$.

One basis for this space would be a list of 3 so-called "basis" vectors, each which have 1 for a single dimension and 0 otherwise:

$$
\left[{\begin{array}{cc}
1 \\
0 \\
0 \\
\end{array}}\right]
\text{ , }
\left[{\begin{array}{cc}
0 \\
1 \\
0 \\
\end{array}}\right]
\text{ , }
\left[{\begin{array}{cc}
0 \\
0 \\
1 \\
\end{array}}\right]
$$

Example 2: Suppose we had columns:

$$
\left[{\begin{array}{cc}
1 \\
1 \\
2 \\
\end{array}}\right]
\text{ , }
\left[{\begin{array}{cc}
2 \\
2 \\
5 \\
\end{array}}\right]
$$

These columns are independent, but to not *span* R3.  Consequently they are *not* a basis for R3.   They do make a space in R3, namely a plane, since they're independent.  We can say that they span the plane, but not R3.  Since they are independent and span the plane, we can say they are a basis for that plane in R2. If a 3rd vector was added that was not independent, it would also stay in this plane, but then the vectors would not be a basis any more, because they are no longer independent.

To span R3, we need to add a 3rd vector, which must not be a combination of the other 2 vectors.  Having added a likely candidate 3rd vector, we would then need to do row reduction on them as a matrix of columns, and see if there are any free variables.  

For a square matrix like this 3x3 one, we need to see if the matrix is invertible.  If it is invertible, its only 0 solution will be the 0 vector Z and the 3 columns will be independent.

**Given a space, every basis must have the same number of vectors -- that is, it must have the same number as the dimension of that space.  For example, if one basis has 6 vectors, then every basis in that space will have 6 vectors.**

### Dimension

#### Definition of Dimension

The number of independent vectors in any basis for a space.

#### Examples:

Suppose the space is C(A):

$$
\left[{\begin{array}{cc}
1 & 2 & 3 & 1\\
1 & 1 & 2 & 1 \\
1 & 2 & 3 & 1 \\
\end{array}}\right]
$$

These vectors can be said to **"span"** the column space of the matrix, because they define that column space of the matrix.  That is, the span is just all the linear combinations of these columns.

However, they cannot form a **basis** for C(A), because they are not independent of each other.  Thus, there will be non 0 values in the null space.

A valid basis for this matrix would be 1 & 2, which are independent.  These are the pivot columns.  The rank of the matrix is thus 2.  

This exemplifies another fact:

**The rank of a matrix is the number of pivot columns AND is also the dimension of the column space C(A).**

**That is: dim C(A) = r.**

So:

* We take the rank of a matrix.
* This is a number of pivot columns.
* This is the dimension of the **column space of A** C(A).  The rank is *not* the dimension of the matrix A.

* We refer to the dimension of a column space, not a matrix.
* Similarly, it is incorrect about the rank of a subspace.  Rather, it is the **matrix** which has rank.
* What is the basis of this matrix?  The first 2 columns, or columns 1 & 3 are examples.  But also, **any 2 vectors that are independent and have the correct length will be a basis for A **.

What about the null space of C(A)? We know that the rank of A in this example is 2 (columns 1 & 2), leaving n-r = 2 free variables (1 & 3).  Toggling 1,0 for these columns and using back-substitution, we find that the 2 special solutions are:

$$
\left[{\begin{array}{cc}
-1 \\
-1 \\
1  \\
0 \\
\end{array}}\right]
\text{ , }
\left[{\begin{array}{cc}
-1 \\
0 \\
0  \\
1 \\
\end{array}}\right]
$$

These 2 special solutions indicate the combinations of the columns that will yield a 0 result.  

Are these 2 vectors a basis for the null space?  They are independent, and span the null space, so yes.  

This illustrates another key fact.

**For a matrix A, the dimension of its null space will be the number of its free variables.**

**That is: dim N(A) = n-r. **


## Independence, Basis, and Dimension Recitation

Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/basis-and-dimension/

### Problem 1

Find the dimension of the vector space spanned by the vectors:

$$\left(1,1,-2,0,-1\right)$$
$$\left(1,2,0,-4,1\right)$$
$$\left(0,1,3,-3,2\right)$$
$$\left(2,3,0,-2,0\right)$$

... and find a basis for that space.

Answer: 

This problem is confusing, because the book tells us that a notation for vectors like () means that the are column vectors, c.f. Strang p5: "But v = (1,1, -1) is
not a row vector! It is in actuality a column vector, just temporarily lying down."  Nevertheless, the TA treats solves them first as a 4x5 matrix:

$$
\text{A = }
\left[{\begin{array}{cc}
1 & 1 & -2 &  0 & -1 \\
1 & 2 &  0 & -4 &  1 \\
0 & 1 &  3 & -3 &  2 \\
2 & 3 &  0 & -2 &  0 \\
\end{array}}\right]
$$

Note that taking the matrix all the way to RRE form is not needed for this kind of analysis.  The RR form is:

$$
\text{U = }
\left[{\begin{array}{cc}
1 & 1 & -2 &  0 & -1 \\
0 & 1 &  2 & -4 &  2 \\
0 & 0 &  1 &  1 &  0 \\
0 & 0 &  0 &  0 &  0 \\
\end{array}}\right]
$$

This gives us a matrix with 3 pivots. In other words, its of rank 3.  It's stated that the 3 rows are linearly independent.  At least one reason for this independence must be their reduced form, because having 0s to the left of the pivot columns means that they could not possibly be a linear form of any other row.  And because the rows are transformations of the original set of equations in terms of each other, they still span the same space.  This includes situations where a row is zeroed out, because it proves that the remaining non-zero rows are sufficient to span whatever space was originally there.

Btw, remember that "spanning the space" is just shorthand for a set of vectors being sufficient to embody all values resulting from linear combinations of those vectors.  So a row reduced form will do that as well as and more succinctly than the original set of vectors.

Remember that a basis is the set of vectors in a matrix which are linearly independent and which span the space.  We've just shown that the 3 row vectors remaining fulfill these conditions, so they define the **basis** for this matrix.  

There is an advantage to analyzing the matrix row-wise in this manner, in that the RR analysis on this matrix form will then give you the basis without further qualification.  The **dimension** of the vector space is then just the count of the rows in RR form, namely 3.

The TA also makes the point that in this particular case you could have just used the first 3 rows unaltered, but that is not always the case because row-swaps may be needed &c.

### Problem 2

Analyzing the transpose of the same matrix.

The TA then goes on to analyze the transpose of the above matrix.  That she calls it a transpose guarantees I think that the problem really did not intend to treat the row-wise displays as vertical columns.  But I'm not sure then whether, when we need to define the dimensions and basis of a matrix, we are suddenly free to treat what would normally be columns as rows, or what.  

Anyway, with transposition and row elimination, you have:

$$
\text{A = }
\left[{\begin{array}{cc}
1 & 1 & 0 & 2 \\
1 & 2 & 1 & 3 \\
-2 & 0 & 3 & 0 \\
0 & -4 & -3 & -2 \\
\end{array}}\right]
$$

... which after elimination becomes:

$$
\text{A = }
\left[{\begin{array}{cc}
1 & 1 & 0 & 2 \\
0 & 1 & 1 & 1 \\
0 & 0 & 1 & 2 \\
0 & 0 & 0 & 0 \\
\end{array}}\right]
$$

Of course you still get 3 pivots, but now there is one free variable row as well.  So with this approach is is necessary to remember that the only the pivot columns are linearly independent, and map these columns back to the corresponding matrix rows to understand which ones form the basis for the column space.  These pivot columns define the dimension 3 for the vector space as well.

However, the TA says that you cannot say that the columns are elements of the basis, because elimination has changed the column space of the vectors -- the last 2 rows are zeroed out.  I think by pointing this out she means to indicate that the the column space of the untransformed matrix would be changed, which is certainly true.  So to get basis in this approach you map your final pivot columns back to the columns in your original matrix.

Considering all this, as best I can tell, the good approach for analyzing the basis and dimensions of a matrix (as contrasted with solving for Ax =0 or Ax =b ) is to:
* figure out whether the vectors of the matrix are initially construed column-wise or row-wise
* accordingly arrange them into a row-wise format
* do elimination on the rows
* this should leave you with results that show matrix rank, and column space dimension and basis, without further transformation.

Note that the two approaches will give you 2 different versions for the same vector space.  This is fine -- in fact you should be able to get an infinite number of bases via arbitrary multiplication of the row values during the elimination process.

## The Four Fundamental Subspaces

### Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/the-four-fundamental-subspaces/
* Strang, p184ff.

### Column Space C(A)

The column space is C(A) is a subspace of Rm.  That is, a given column in A has m components.

### Null Space N(A)

The null space is N(A) is a subspace of Rn.  Because x in Ax = 0 is a column, it's easy to confuse this and think that it should be in Rm.  But if you consider it, you see that the number of components in x is set by the number of columns n in A.

### Row Space R(A)

#### Sources:
* Strang, p171.

The rowspace is C($A^T$), and is a subspace of Rn.  That is, a given row of A is n components wide.

* The row space of A is all combinations of its rows.  In other words, the rows "span" the rowspace.
* The rows may or may not be a basis for R(A) -- they may or may not be independent. 
* What is in R(A)?  All combinations of the rows of A.
* To work with the rows as column vectors, we can transpose the matrix A.  Then we say that R(A) is all combinations of $A^T$.  Further, we can say that R(A) = C($A^T$).  

### Null Space A Transpose N($A^T$)

Aka "the left nullspace of A".  By Ursula K LeGuin.

The left nullspace N($A^T$) is in Rm.  The reasoning here corresponds to why x is in Rn, except that N($A^T$) is on the left-hand side of A. 

### Summary: Locating the Four Fundamental Sub-spaces

When A is an mxn matrix, what is the location of each of these subspaces?

* Null space of A N(A) is in $R^n$.
* Column space of A C(A) is in $R^m$.
* R(A) = Column Space of C($A^T$) is in $R^n$.
* Null space of A N($A^T$) is in $R^m$.

Note: there is an obvious symmetry here, but I failed to see it on the first reading.  For columns, you have the column space and null space: C($A^T$) and N($A^T$) are just the corresponding concepts for rows (treated as columns via transposition).  

### Bases for the Four Fundamental Sub-spaces 

* Column Space: The columns of the original matrix A corresponding to the pivot columns from the matrix in RR form.
* Null Space: the count of special solutions = n-r
* Row Space:

The answer for the basis of Row Space is more involved.  Suppose that we had a matrix A of form:

$$
\text{A = }
\left[{\begin{array}{cc}
1 & 2 & 3 & 1 \\
1 & 1 & 2 & 1 \\
1 & 2 & 3 & 1 \\
\end{array}}\right]
$$

Under row reduction, A becomes:

$$
\text{R = }
\left[{\begin{array}{cc}
1 & 0 & 1 & 1 \\
0 & 1 & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{array}}\right]
$$

Notice that R is comprised of a block I in the upper left, a block F in the upper right, and a zero row on the bottom.

Notice that the **column space** changed: C(A) does not equal C(R).  For example (1 1 1) is in C(A) but not C(R).  -- I find this assertion that the column space changed (materially) a bit hard to digest, but I think it helps to remember the definition of column space **is**, namely the set of all results obtainable via linear combinations of the columns in A.  So Strang says you can't get the same column space from A as from R.  Related to this C(A) vs C(R) disparity: if you think about it, row reduction kind of preserves information as it zeros out or alters rows, because the alterations are done to **one row in terms of another** .  For example, if you zero out a row, you can do so because the zeroed row was a transformation of another row that was subtracted from it.  So you prove, in the zeroing process, that all essential info was lost in the remaining non-zeroed rows.  A similar thing is **not** happening w/r/t column-to-column comparisons, even while their values are being changed.  

Row operations have preserved the same row space from A to R.  They have "exactly the same vectors in them".  --After the remarks on changed column vectors, Strang much surely mean that the "row vectors" are the same, even though "row vector" seems like a contraction to earlier methods (see chapter one) for rows into matrices.  He notes that the vectors still have the same number of components, and are still combinations of the same essential (non-zero) rows.  Another way to say that the rows "have exactly the same vectors in them" is that you can get an identical span by taking all lin combos of the rows in either matrix.  --If this is true, it means that whatever is a basis for the row space of R will be a basis for the row space of A.  

In the above example matrix R, it is clear that the first two rows will be the basis for R (or by extension A).  -- Counting the pivots in the RRE form, we can say that the basis is the first "r" rows in R.  This is true because we have reduced the rows via RR to just those which are independent.  Note that depending on A, it may sometimes be true that that the basis in R's r rows may be the same for A, but not necessarily.  

Why are these two vectors in the row space? (Notice he's calling them "vectors"; hurts my head.)  Because they are in the most essential form post-RRE. 

Note that when we have the rows reduced to RRE, they are then by definition a **basis** for the row space.  We can also say that they span the entire row space of A, because you can demonstrate that one form of the rowspace (A) reduces to the other (R) by simply reversing the steps of row reduction.  

* Left Null Space N($A^T$): 

Say we have a matrix A with vectors y such that $A^T$y = 0.  If $A^T$y = 0, then y is in the null space of $A^T$, that is, y is the set of values such that the 0 vector is yielded when $A^T$ acts on or is multiplied times y.  We can consider $A^T$y = 0 as a matrix times a column equaling 0.  In this situation, we want to solve for y, so we will isolate it on the left.  In order to do this, we can take the transpose of both sides of $A^T$y = 0.  On the right side of the equation , the 0 vector is changed from vertical to horizontal orientation.  On the left, we get $y^{T}A^{TT}$ or "y transpose times A transpose transpose".  Remember that the order of multiplications is changed when you take the transpose, so Y comes first.  Althogether: $y^{T}A^{TT}\text{ = }\left[\text{ 0 }\right]$.  Of course, $A^{TT}$ reduces to just "A".  So we are left with $y^{T}A\text{ = }\left[\text{ 0 }\right]$ .  

Considering this result, we can see that $y^{T}$ is now a row vector multiplying A **from the left** to get a 0 row vector on the right.  This multiplication from the left side is why it is called a "left null space".  However, Strang actually dislikes this arrangement, which obliges us to turn the row vector y into a column vector, so he usually avoids this procedure, and stays with $A^Ty=0$.  But anyway, the above note explains the "left null space" description.

**How do we get a basis for this left null space?**

Returning to this example:

$$
\text{A = }
\left[{\begin{array}{cc}
1 & 2 & 3 & 1 \\
1 & 1 & 2 & 1 \\
1 & 2 & 3 & 1 \\
\end{array}}\right]
$$

Under row reduction, A becomes:

$$
\text{R = }
\left[{\begin{array}{cc}
1 & 0 & 1 & 1 \\
0 & 1 & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{array}}\right]
$$

We can see columns (3 and 4) in R hold the special solutions, but those are special solutions to Ax = 0.  Now however we're looking at A transpose.

Suppose we take again the mxn matrix $\left[A_{mxn}\right]$.  Consider again the Gauss-Jordan example.  In that example, we first had a square identity matrix, and we were finding its inverse.  Now the matrix A isn't square, but we can still add on an identity matrix of proportions mxn:

$\left[A_{mxn}I_{mxm}\right]$ .  Note that matrix I must be by definition square.  Now we take the RRE form of this augmented AI matrix, and we get: 

$\left[A_{mxn}I_{mxm}\right]\rightarrow\left[R_{mxn}E_{mxm}\right]$ , where A is turned into R as usual, and E signifies some as-yet-to-be qualified matrix that I turns into, and which has the same proportions as I.  

Given the nature of I, and of the Gauss-Jordan process, it is clear that matrix "E" will just contain a record of the transformation steps done to turn A --> R.  Consequently, this process amounts to multiplying AI by E: $E\left[A_{mxn}I_{mxm}\right]$ .  --This last fact is a little hard to verbalize, but you can see it by contemplating the transformation $\left[A_{mxn}I_{mxm}\right]\rightarrow\left[R_{mxn}E_{mxm}\right]$.

Thus, having obtained E, we can say that EA = R.  In words, this means that the row reduction steps that we took to turn A to R are captured in the I --> E transformation.  

Reviewing the invertible square case, we remember that:
  * when A was square and invertible, we could take AI, do row elimination, and the R that resulted was in fact I.  That is, with 2 square matrices AI undergoing RRE, AI --> IA , and we consider I as the R matrix in this case.
  * Remember that by definition, the inverse of a matrix A is the matrix which multiplies A to give I.  In the equation EA = R, if R is I, then we know E must be A inverse since EA = I in this square matrix case.

Considering the rectangular case for A, we see that there is still a matrix E that can be calculated and multiplied to act on A.  

Suppose that we had used the G-J approach on our initial matrix A attaching a square matrix I so that it recorded the changes to A, and itself became E.  Then we would have EA = R:

$$
\left[{\begin{array}{cc}
-1 & 2 & 0 \\
1 & -1 & 0 \\
-1 & 0 & 1 \\
\end{array}}\right]
\left[{\begin{array}{cc}
1 & 2 & 3 & 1 \\
1 & 1 & 2 & 1 \\
1 & 2 & 3 & 1 \\
\end{array}}\right]
\text{ = }
\left[{\begin{array}{cc}
1 & 0 & 1 & 1 \\
0 & 1 & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{array}}\right]
$$

At this point, we know the dimension of the left null space: A has dimension m, and right side R has r pivots, and we know that left null space should have dimension m-r, or 3-2 = 1.  So in this example E should be one dimensional.  That is, there should be a basis for the **left null space** that only has one vector in it.  What is that vector?  It is the last row of E, because that row (-1 0 1) times A would give a 0 row.  In fact, row indices of 0 rows in R will be indices for the rows in E that are the basis of the left null space.    

#### Algorithm for Finding Basis of N($A^T$).

**The above process illustrates the whole algorithm for analysing the basis for $N\left$A^T\right)$:**

1. To the right of matrix $A_{mxn}$, add $I_{mxm}$ .
2. Using row elimination, transform AI to RE; that is A will be updated to R, and I will be updated to E.
3. As noted above, EA = R, but you can keep the AI --> RE format, since the insight will be the same.
4. Find the row indices of zero rows in R.
5. These zero row indices in R will be the indices of the basis in E of the left null space.

### Dimensions for the Four Fundamental Sub-spaces 

Sources:
* Strang, p184

**Notice that the rank of a matrix A shows the dimension of all four fundamental subspaces related to that matrix.**

* Column Space: the rank r of the column space (the number of its pivot variables).  = Number of independent vectors in matrix.
* Null space: number of special solutions  = n-r
* Row Space: also r, same as column space.  Dim of C($A^T$) = Dim C(A)
* Left Null Space N($A^T$):  m-r; note that m is the number of columns in $A^T$ .


### Review of Four Fundamental Sub-spaces:

* The row space and null space are in $R^n$, and their dimension add to n.
* The column space and left null space are in $R^m$, and their dimensions add to m.

### Recitation: Computing the Four Fundamental Sub-Spaces

Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/computing-the-four-fundamental-subspaces/

Problem:

Suppose a matrix B was as follows:

$$
B\text{ = }
\left[{\begin{array}{cc}
1 & { } & { } \\
2 & 1 & { } \\
-1 & 0 & 1 \\
\end{array}}\right]
\left[{\begin{array}{cc}
5 & 0 & 3 \\
0 & 1 & 1 \\
0 & 0 & 0 \\
\end{array}}\right]
$$

Find a basis for and compute the dimension of each of the four fundamental sub-spaces for the product of this graph.

We can reduce B to a product of the two matrices, and then apply row reduction to it:

#### Dimensions:

Note that I assumed you first had to multiply the two matrices, then do RRE on the product.  But none of that was necessary.  Instead, the TA indicates that one of the matrices or the other is adequate to answer the question, without indicating why.

For reference, we can refer to the above lower triangular matrix as L and the right upper triangular matrix as U.

* C(A): from the lecture, we know that the dimension of C(A) is the number of its pivots.  In this case the second upper triangular matrix has 2 pivots.
* N(A): we also know that the dimension of N(A) will be columns-pivots = 3-2 = 1.
* R(A): we know that the dimension of the row space will be the same as C(A), so 2.
* N($A^T$): we know that the dimension of N($A^T$) is m-r, so 1.

#### Bases:

* C(A): in the lecture, we learned to do RRE and then take the pivot columns from the original matrix.  I would have thought the "original" matrix here was the product of the lower and upper triangular matrices, but the TA laconically said that the pivots columns could be taken from the lower triangular matrix.  I think the idea was that taking the columns of the left hand matrix that will act on the right hand matrix was the same as taking the pivot columns of their product.  --Actually, you can see that's true when you consider that the pivot columns in the product of LU times RU are (5 10 -5), and (0 1 0).  Clearly you could reduce the first of these vectors to (1 2 -1).
* N(A): for this, the TA selects the upper triangular matrix and takes the 3rd column (corresponding to the free variable).  1 is plugged into the vector for the free variable, and by substitution the other variables are (-3/5 -1 1) .  
* R(A): since elimination doesn't change the row space, we can use the two pivot **rows** of the upper triangular matrix: (5 0 3) and (0 1 1). 
* N($A^T$):

The first step is to invert L to change it to E, and set it equal to U:

$$
L^{-1}\text{ = }E\text{ = }
\left[{\begin{array}{cc}
1 & { } & { } \\
-2 & 1 & { } \\
1 & 0 & 1 \\
\end{array}}\right]
B\text{ = }
\left[{\begin{array}{cc}
5 & 0 & 3 \\
0 & 1 & 1 \\
0 & 0 & 0 \\
\end{array}}\right]
$$

.

Now we can see that the 3rd row of E corresponds to the 3rd row of U.  When this 3rd row in E is multiplied on B, the 3rd row of 0s in U results.  Thus the 3rd row (1 0 1) in E is in the left null space.  


### Additional Recitation 1 on Calculating Dimension and Basis for N($A^T$):

Sources:
* Khan Academy: https://www.youtube.com/watch?v=qBfc57x_RSg

Suppose we have a matrix A:

$$
A\text{ = }
\left[{\begin{array}{cc}
2 & -1 & -3 \\
-4 & 2 & 6 \\
\end{array}}\right]
$$

$A^T$ is then:

$$
A^T\text{ = }
\left[{\begin{array}{cc}
2 & -4 \\
-1 & 2 \\
-3 & 6 \\
\end{array}}\right]
$$

This is R(A), since R(A) = C(A^T).

... and $R^T$ is:

$$
A^T\text{ = }
\left[{\begin{array}{cc}
1 & -2 \\
-1 & 2 \\
-1 & 2 \\
\end{array}}\right]
\rightarrow
\left[{\begin{array}{cc}
1 & -2 \\
0 & 0 \\
0 & 0 \\
\end{array}}\right]
\text{ = }R^T
$$

Then "left nullspace", or $N\left(A^T\right)\text{ = }\\{\overrightarrow{x}\in\mathbb{R}^{2}\text{ | }A^{T}\text{ }\overrightarrow{x}\text{ = }\left[0\right]\\}$  .  In words: the null space of $A^T$ is a vector x in R2, such that $A^T$ times x = a zero vector."  The zero vector result will be in R3 (the space n of the rows before transposition).

The nullspace of R^T will be the same as that of A^T.  That is:

$$
\left[{\begin{array}{cc}
1 & -2 \\
0 & 0 \\
0 & 0 \\
\end{array}}\right]
\left[{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}}\right]
\text{ = }
\left[{\begin{array}{cc}
0 \\
0 \\
0 \\
\end{array}}\right]
$$

The first column in R is the pivot column, so $x_1$ will be a pivot variable, and $x_2$ will be a free variable.  Matching the pivot column in $R^T$ back to the corresponding column in $A^T$, the pivot column (2 -1 -3) in $A^T$ should span its column space.  

Returning to $R^T$ and multiplying it by [x], we have that $x_1$ - 2$x_2$ = 0 , or $x_1$ = 2$x_2$ .  So all the vectors that satisfy these conditions will be in the nullspace of $A^T$ .  

We can write this as:

$$
N\left(A\right)\text{ = }
\left\\{
\left[{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}}\right]\|
\left[{\begin{array}{cc}
x_1 \\
x_2 \\
\end{array}}\right]
\text{ = }
x_{2}
\left[{\begin{array}{cc}
1 \\
2 \\
\end{array}}\right]
\right\\}
$$

and correspondingly, 

$$
C\left(A\right)\text{ = span}
\left\(
\left[{\begin{array}{cc}
1 \\
-1 \\
-3 \\
\end{array}}\right]
\right\)
$$

.  

C($A^T$) can also be called R(A).  

## Matrix Determinants

Sources:
* USF: https://usfca.instructure.com/courses/1627052/pages/matrix-determinant-video-10?module_item_id=18611412
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/lecture-18-properties-of-determinants/
* Huggingface chat.

### Meaning and Significance of the Determinant

It's challenging to get a short, clear expression of the meaning or signficance of a determinant, but here are some notes:
* the absolute value of a determinant is the volume of the vectors in its matrix, when the rank r of that matrix is equal to its columns n.  Note that a matrix in RRE form with r<n will have a determinant (and volume) of 0.
* Strang states that the primary importance of determinants is their use in calculating eigenvectors.
* The determinant serves as a test for invertibility: A square matrix is invertible i.o.i. it has a non-zero determinant.

### Relation to a Square Matrix

* Only certain square matrices have determinants.  
* A matrix is singular when the determinant is 0.

### Determinant Notation

A determinant is typically noted as "det A" for determinant A, or sometimes as |A|, which means "the determinant of A", and not "the absolute value of A".  When discussing the determinant as an explit matrix where the components are shown, the determinant is noted like:

$$
\|A\|\text{ = }
\left\|{\begin{array}{cc}
1 & 0\\
-2 & 1\\
\end{array}}\right\|
$$

.  You actually have to pay attention to the presence of vertical bars, because it can be easy to mistake a determinant in this format for the square brackets of a matrix.

### Properties of Determinants

Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/lecture-18-properties-of-determinants/

Strang begins the subject of determinants by listing their properties, rather than defining what a determinant *is*.  There are 10 properties of determinants.  The first 3 properties are the basis for all the higher-numbered properties:

#### Property 1

**det I = 1.  "The determinant of the identity is 1."**  Considering the 2x2 matrix determinant formula for

$$
\|A|\text{ = }
\left\|{\begin{array}{cc}
a & b\\
c & d\\
\end{array}}\right\|
$$

as $ad - bc$, you can immediately see that this would be so.  For a larger order square matrix, if you are familiar with the process of calculating the determinant by breaking it into recursive summed 2x2 matrices, you can see that I of any size would probably multiply out to 1 as well.  I believe this is what Strang has in mind when he says that this property "scales the identity matrix so that det|I| [always] = 1."

#### Property 2  

**Exchanging rows of a matrix "flips" or reverses the sign of the determinant.**  Exchange Rows -- > Reverse the sign.  This means that:
    * an odd number of row exchanges will reverse the sign
    * an even number of row exhcnages will keep the original sign.  

Notice that based on properties 1 and 2 alone we now know the determinant of all permutations matrices P.  Remember that a permutation matrix P is just I with reordered rows, so that when you multiply I times a matrix A, A's rows will be re-ordered.  Since P is a re-ordered I, we know that all matrices P will be in {-1,1}, depending on whether their count of row swaps is odd or even.

#### Property 3

Property 3 can be broken into 2 assertions:

**3a:**

$$
\left\|{\begin{array}{cc}
ta & tb\\
c & d\\
\end{array}}\right\|
\text{ = t}
\left\|{\begin{array}{cc}
a & b\\
c & d\\
\end{array}}\right\|
$$

In words: if I multiply one of the rows by a scalar, I can extract that scalar as being multiplied times the determinant.  It is difficult to see why this is allowed, because there is not obvious way to reverse the arrangement: having extracted t as a multiplier of the determinant, no information is preserved to tell you by which row it should be multiplied to return it to the original (ta tb) row.  --To make this easier to digest, it is helpful to remember the || vs [] distinction: determinant operations always describe an algebraic interaction in a (recursive, algorithmically applied) formula, even if we can picture the components and vectors geometrically or arranged like a matrix.  It is easier to accept this operation (in this case, the distributibe property) applying to a subset of terms in an overall formula, than as an operation on a single row when the components are arranged like a matrix.

**3b:**

Suppose you have a determinant:

$$
\left\|{\begin{array}{cc}
{a + a\`} & {b + b\`}\\
c & d\\
\end{array}}\right\|
$$

Then this can be broken into:

$$
\left\|{\begin{array}{cc}
a & b\\
c & d\\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
a\` & b\`\\
c & d\\
\end{array}}\right\|
$$

You can see that properties 3a and 3b define *linear combinations for the first row.*  The other rows are somehow brought along unchanged.  Strang says that "the determinant behaves like a linear function, if [while?] all the other rows stay the same."  He is very keen to distinguish this from a statement like "det |A + B| = det |A| + det |B|".  I think he's emphasising that the non-first rows are kept *in common* while only the first row is decomposed, despite the visual suggestion that a matrix (it's not a matrix; it's a determinant), has been split into two matrices.  

The linear combination operations that are done on the first row apply to all the other rows as well.  You can see this by considering that you could use P, and the oppositite of P, to move the row of interest to first row position, operate on it, and then move it back to its original position.  The key thing is that we only operate linearly one one row at a time.  

From properties 1,2 & 3, all the other properties are derived.

#### Property 4

If 2 rows in a determinant matrix are equal then, then the determinant will be zero.  2 equal rows --> 0 determinant. 

Suppose we have a 7x7 matrix with 2 identical rows.  If I exchange the 2 identical rows, the resultant matrix will be unchanged.  However, because the rows were exchanged, per property 2, the sign of the determinant must change.  

This property corresponds to the fact that if a matrix has 2 equal rows it will not be invertible because the rank must necessarily be less than n when one of those rows zeroes out in RRE.  

#### Property 5

In row elimination, we multiply one row i by some scalar l and subtract it from another row k, in order to produce the result 0 in some off-diagonal position.  

**Property 5 states that RRE does not change the determinant.**  If a determinant exists for a matrix A, it will not change from A --> U --> R.

Suppose we have a determinant:

$$
\left\|{\begin{array}{cc}
a & b\\
c & d\\
\end{array}}\right\|
$$

to zero out c, we will subtract:

$$
\left\|{\begin{array}{cc}
a & b\\
{c-la} & {d-lb}\\
\end{array}}\right\|
$$

By property 3b, we can split this determinant into a sum of 2 determinants:

$$
\left\|{\begin{array}{cc}
a & b \\
{c-la} & {d-lb} \\
\end{array}}\right\|
\text{ = }
\left\|{\begin{array}{cc}
a & b \\
c & c \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
a & b \\
-la & -lb \\
\end{array}}\right\|
$$

By property 3a, we can abstract out the - l:

$$
\text{ ... = }
\left\|{\begin{array}{cc}
a & b \\
c & c \\
\end{array}}\right\|
\text{ -l }
\left\|{\begin{array}{cc}
a & b \\
a & b \\
\end{array}}\right\|
$$

Then by property four, 

$$
\text{ -l }
\left\|{\begin{array}{cc}
a & b \\
a & b \\
\end{array}}\right\|
$$

... must equal 0, leaving us with just the original determinant

$$
\left\|{\begin{array}{cc}
a & b \\
c & c \\
\end{array}}\right\|
$$

.  This demonstrates that det A = det U = det R.  RRE does not change the determinant.

#### Property 6

A row of zeroes in A means that det A will equal 0.

You can see that this is true based on property 3a.  For a row of 0s in det A, it is clear that you can abstract out a 0, which gives you 0 x det A which is 0.

#### Property 7

The determinant of an upper triangular matrix is the product of all its pivots.  

* This also shows why a 0 for a matrix where r < n would mean the determinant must be 0.

This fact is actually the efficient way to calculate a determinant (and determine if one exists).  All software uses this approach.
Remember that if RRE involves an odd number of row exchanges, the original sign of the determinant will change.

You can use property 3a to show that this is so.  For any matrix with r=n, it will be possible to reduce the matrix to having non-zero values only in the diagonal.  Having done this, you can use property 3a to factor out any non-zero values and reduce the diagonal value to 1.  Doing this for all diagonals, the matrix will be transformed to I, multiplied by all the abstracted diagonal values $d_1\text{ ... }d_n$ times the determinant of I.  But we know that det I = 1 (property 1).  Thus the determinant of any matrix with r = n will be the product of its diagonals.

This calculation method can be checked against the common formula used to calculate the determinante of a 2x2 matrix, in order to show that the two approaches are equivalent.  If we have:

$$
\text{det A = }
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
$$

we are saying that a*d is equivalent to ad - bc.  If we subject A to elimination as the first step in the "multiply the diagonals" method, we'll get:

$$
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
\rightarrow
\left\|{\begin{array}{cc}
a & b \\
{c-{\frac{c}{a}a}\text{ = }0} & {d-{\frac{c}{a}b}} \\
\end{array}}\right\|
\text{ = R}
$$

... and multiplying $a\text{ * }\left(d-{\frac{c}{a}b}\right)$ will yield ad - bc with is the other method.  This shows that multiplying the diagonals and using the traditional formula are equivalent.

#### Property 8

The determinant of matrix A is 0 exactly when A is singular.  Therefore, the existence of a non-zero determinant verifies whether the matrix is invertible.

#### Property 9

The product of det AB = det A * det B .  This is somewhat surprising, because det A + det B is NOT the sum of its determinants.  

Property 9 is useful for determining the determinate of A inverse:

We know that $A^{-1}A=I$ .  We can then take determinants of both sides, so that  $\text{det }A^{-1}\text{det }A\text{ = }1$ (using property 1).  But this tells us that $\text{det }A^{-1}\text{ = }\frac{1}{\text{det }A}$ .  Notice that this reconciles with the rule that a non-singular (invertible matrix) cannot have a 0 determinant, because if it did, we would have $A^{-1}\text{ = }\frac{1}{0}$ .

To give an example, suppose:

$$
A\text{ = }
\left[{\begin{array}{cc}
2 & 0 \\
0 & 3 \\
\end{array}}\right]
\text{, then}A^{-1}\text{ = }
\left[{\begin{array}{cc}
\frac{1}{2} & 0 \\
0 & \frac{1}{3} \\
\end{array}}\right]
$$

And indeed the determinant of A would be 6, while the determinate of $A^{-1}$ = 1/6, which is just what $A^{-1}\text{ = }\frac{1}{\text{det }A}$ predicts.  

We can also use this prroperty to understand the role of exponents.  What is the determinant of $A^2$ ?  What even is a squared matrix?  The determinant of $A^2$ per rule 9 should be det A * det A.  

However, if we double the matrix, what happens to the determinant?  What is det 2A?  That is the same as det (A + A).  To make sense of this, consider that A must be a square nxn matrix.  We are proposing to double every entry in the matrix.  

The answer is that det 2A = $2^n$ det A.  Why?  The reason is that, having doubled every entry in the matrix, we would then factor a 2 out of every row (property 3a), and there are n rows.  

#### Property 10

**The determinant of 1 transpose = determinant of A.  det $A^T$ = det A.**

We can check this against the 2x2 ad - bc formula.

$$
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
\text{ would give the same result as }
\left\|{\begin{array}{cc}
a & c \\
b & d \\
\end{array}}\right\|
$$

..because the diagonal would not change.  

**Property 10 tells us that if a column is 0, the determinant will also be 0.**  Because via transposition, a column can become a row.  So whatever determinant properties apply to rows, also apply to columns.

## Determinants Considered Geometrically

Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/lecture-20-cramers-rule-inverse-matrix-and-volume/
* USF: https://usfca.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=18d6d01c-7f28-42ca-ade1-b01f0171e3cb&start=45.892811

### General Claim: Determinant A = Volume of Box

Assertion: det A is volume of a box.

Suppose the dimension=rank of a column space C(A) of a 3x3 matrix A is 3 (they are linearly independent) .  In that case, the absolute value of a determinant for that 3x3 matrix will give the volume of the 3d space taken by those vectors.  The proper term for this 3d volume consisting of 3 independent vectors is a "parallelopiped".

It is possible for the determinant to be negative.  In that case, it means that the box extends into a negatively signed space.  This is sometimes called "left handed".  This is why we take the absolute value of the determinant, but a negative value is not irrational.

### Determinants in 2D Space

Suppose we have 2 linearly independent vectors:

$$
v\text{ = }
\left[{\begin{array}{cc}
1 \\
2 \\
\end{array}}\right]
\text{, }w\text{ = }
\left[{\begin{array}{cc}
0 \\
1 \\
\end{array}}\right]
$$

... and we arrange them in a matrix A:

$$
A\text{ = }
\left[{\begin{array}{cc}
1 & 0\\
2 & 1\\
\end{array}}\right]
$$

You can immediately see that there are underlying basis vectors, so they're going to be linearly independent.  Plotting them, they look like:

```
# Create a new figure
fig, ax = plt.subplots()

# Plot x and y axis lines
ax.axhline(y=0, color='black', linestyle='--')
ax.axvline(x=0, color='black', linestyle='--')

# Define the vectors to plot
vectors = [(1, 2), (0, 1)]

# Plot the vectors as arrows
for vector in vectors:
    ax.arrow(0, 0, vector[0], vector[1], head_width=0.2, head_length=0.3, color='blue')

# Set axis limits
ax.set_xlim(-1, 7)
ax.set_ylim(-1, 7)

# Set axis labels
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')

# Show the plot
plt.show()
```

<img width="593" alt="Screenshot 2025-04-01 at 22 16 11" src="https://github.com/user-attachments/assets/b4a105a2-07e4-4498-9eeb-a1b4af678a64" />

You can also see that the vectors could make a parallelogram.  This would happen either by duplicating them, or as shown here by adding and subtrtracting them.  A diagonal of the parallelogram is shown in red:

```
# Create a new figure
fig, ax = plt.subplots()

# Plot x and y axis lines
ax.axhline(y=0, color='black', linestyle='--')
ax.axvline(x=0, color='black', linestyle='--')

# Define the vectors to plot
# vectors = [(0, 0),(1, 2),(1, 3),(0, 1),(0, 0)]
vectors = [[0, 0,1, 2],[1, 2,0, 1],[1, 2,0, 1],[1, 3,-1, -2],[0, 1,-0, -1]]

# Plot the vectors as arrows
for i in range(0,len(vectors)):
    vec=vectors[i]
    ax.arrow(vec[0], vec[1], vec[2], vec[3], head_width=0.1, head_length=0.1, color='blue')

ax.arrow(0, 0, 1, 3, head_width=0.1, head_length=0.1, color='red',linestyle='dotted')

# Set axis limits
ax.set_xlim(-1, 7)
ax.set_ylim(-1, 7)

# Set axis labels
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')

# Show the plot
plt.show()
```

<img width="601" alt="Screenshot 2025-04-02 at 07 17 25" src="https://github.com/user-attachments/assets/8835ca11-14b0-4e4d-b5a4-994012cfbbd1" />


Remember that we index the components of a vector from top to bottom.  The area of this parallelogram is then given by the formula $\left\|v_{1}w_{2}\text{ - }v_{2}w_{1}\right\|$ .  In this case, the area = 1 [note: I believe the instructor here is in error; he asserts that abs(1*1-2*0)=2].

What if the vectors in the matrix are linearly dependent instead?  Suppose we had two vectors extending from the origin to (-1,-1) and (-2,2):

```
# Create a new figure
fig, ax = plt.subplots()

# Plot x and y axis lines
ax.axhline(y=0, color='black', linestyle='--')
ax.axvline(x=0, color='black', linestyle='--')

# Define the vectors to plot
vectors = [[0, 0,-1, -1],[0, 0,-2, -2]]

# Plot the vectors as arrows
for i in range(0,len(vectors)):
    vec=vectors[i]
    ax.arrow(vec[0], vec[1], vec[2], vec[3], head_width=0.1, head_length=0.1, color='green')


# Set axis limits
ax.set_xlim(-3, 5)
ax.set_ylim(-3, 5)

# Set axis labels
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')

# Show the plot
plt.show()
```

<img width="602" alt="Screenshot 2025-04-02 at 07 41 30" src="https://github.com/user-attachments/assets/e8a49308-c72b-44df-b3ee-2967681b4760" />

In this case, the vectors lie on the same line and the area of their parallelogram will be 0.  Again, applying the formula $\left\|v_{1}w_{2}\text{ - }v_{2}w_{1}\right\|$ , we get |-1*-2 - -1*-2|, which is clearly 0.

The value given by $v_{1}w_{2}\text{ - }v_{2}w_{1}$ inside the absolute value brackets is called the **determinant**. In general, the 2x2 determinant for a matrix 

$$
v\text{ = }
\left[{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right]
$$

is **ad - bc** .  And for any square nxn matrix, there is a function f on the matrix entries [aka components] which will return this scalar value called the determinant.  


### A Determinant in 3D Space: Cubes

In the below illustration, we show the 3d volume that could be spanned by three basis vectors if any 2 were held constant and multiplied by each other to make a square, and then multiplied by a 3rd which has a range on its non-zero value from 0 to 2.

```
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from itertools import product, combinations

axsrt=-5
axend=5
axendpls=axend*1.01

# Create a 3D axes object
fig = plt.figure(figsize=(10, 10))
ax = fig.add_subplot(111, projection='3d')

# Turn off the subplot backdrop
ax.set_axis_off()

# Set the axes limits
ax.set_xlim(axsrt, axend)
ax.set_ylim(axsrt, axend)
ax.set_zlim(axsrt, axend)

# x_data = xline.get_xdata()
x_data = xline._verts3d
y_data = yline._verts3d
z_data = zline._verts3d

# Print the coordinates
# print("X coordinates:", x_data)
# print("Y coordinates:", y_data)
# print("Z coordinates:", z_data)

# draw cube
r = [0, 2]
for s, e in combinations(np.array(list(product(r, r, r))), 2):
    if np.sum(np.abs(s-e)) == r[1]-r[0]:
        ax.plot3D(*zip(s, e), color="lightgrey", linewidth=1)

# Draw the axes
xline, = ax.plot([axsrt, axend], [0, 0], [0, 0], color='red', linestyle='-', linewidth=2)
yline, = ax.plot([0, 0], [axsrt, axend], [0, 0], color='green', linestyle='-', linewidth=2)
zline, = ax.plot([0, 0], [0, 0], [axsrt, axend], color='blue', linestyle='-', linewidth=2)

# Plot the vectors
ax.quiver(0, 0, 0, 2, 0, 0, color='black', linewidth=2, arrow_length_ratio=0.1)
ax.quiver(0, 0, 0, 0, 2, 0, color='black', linewidth=2, arrow_length_ratio=0.1)
ax.quiver(0, 0, 0, 0, 0, 2, color='black', linewidth=2, arrow_length_ratio=0.1)

# Add labels to the axes
ax.text(axendpls, 0, 0, 'x', color='red')
ax.text(0, axendpls, 0, 'y', color='green')
ax.text(0, 0, axendpls, 'z', color='blue')

# Add labels to the vectors
ax.text(2, 0, 0, '(2,0,0)', color='black')
ax.text(0, 2, 0, '(0,2,0)', color='black')
ax.text(0, 0, 2, '(0,0,2)', color='black')

# Show the plot
plt.show()
```


<img width="539" alt="Screenshot 2025-04-03 at 17 28 49" src="https://github.com/user-attachments/assets/d2ea6f02-d1c0-4505-8df7-0153b89d3148" />

Note that, by implication, the "volume taken" by these vectors must be different than the "space they span", which would be all linear combinations.  

If the vectors are linearly *dependent*, the volume of the 3d space will again be 0.  

You can see that the determinant will be the volume of a **cube** when the matrix consists of basis vectors, in other words **when A = I.**  In fact, this proves property 1, where we say that the determinant of I = 1.  Now we can see that we are also saying that **the volume of I = 1.**  This also demonstrates the reverse: that det I = 1 shows that the determiant of a matrix = the volume of that matrix.  Again remember that this is relative to the "potential space" of the matrix: a square matrix where r < m = n will have a volume of 0.

Suppose we have an **orthognal** matrix Q, i.o.w. a matrix with **orthonormal** columns.  That is, each column vector in the matrix has a length of 1 (its columns are unit vectors) and is perpendicular (orthogonal) to all other column vectors in the matrix.  Note that by determinant property 10? the determinant of the matrix is also the determinant of the transpose, so we can say that the same results will come from the rows of an orthoganal matrix as well.  In the case of an **orthognal** matrix, the volume must again be a cube, since all the vectors are independent and perpendicular.  The difference is that now the cube may be rotated any which way, while its volume remains 1.  This means that the determinant must also be in {-1,1} . 

For an orthoganal matrix, we know that multiplying it by its transpose must give the identity matrix: $Q^TQ\text{ = }I$ .  From this property, we can see that the determinant must be in {-1,1} :

1. Take the determinant of both sides: $\|Q^T\|\|Q|\text{ = }|I|\rightarrow\|Q^T\|\|Q|\text{ = }1$ , by property 1 on the right, and property 9 on the left.
2. The determinant of the transpose = the determinant, by property 10.  So $\|Q^T\|\|Q|$ is just $|Q|^2$.
3. But the determinant of Q is 1, so  $|Q|^2$ must be in {-1,1} .

So in general, for cubes, we have shown that determinant = volume.

### Determinants for 3D Space: General Parallelograms

Imagine that you take a cube, and stretch one edge [vector] of it so that it doubles the length.  By multiplication, the volume of the resultant 3d object must be doubled.  --This is also determinant property 3a in effect.  Property 3a was that if we had a determinant [not a matrix] with a factor t in one row, we could factor it out of that row.

To generalize the proof that the determinant is the volume of a parallelogram, we have to show that it applies to non-cubes (non-orthogonal objects) .  --Doing this involves determinant property 3b, which said that a determinant could be decomposed into sums of determinants.  So we state that:

|det A| = volume of a box, where the box has:
* property 1 -- if the box is a unit cube, its volume is 1.
* property 2 -- if we reverse rows in the box, it changes the sign, but not the volume
* property 3a -- we can factor out a common factor from an individual row in the determinant

Now we need to role of property 3b to complete the generalization that a determinant is the volume of any paralellogram (box).

$$
\left\|{\begin{array}{cc}
\text{a + a'} & \text{b + b'} \\
c & d \\
\end{array}}\right\|
\text{ = }
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
{a'} & {b'} \\
c & d \\
\end{array}}\right\|
$$

Consider that in a parallelogram, the opposite corner's coordinates are the sum of its consituent vectors:

```
import matplotlib.pyplot as plt
import numpy as np
from mpl_toolkits.mplot3d import Axes3D

# Create a new figure
fig, ax = plt.subplots()

# Plot x and y axis lines
ax.axhline(y=0, color='black', linestyle='--')
ax.axvline(x=0, color='black', linestyle='--')

# Define the vectors to plot

a=2
b=1
c=1
d=2

vectors = [[0, 0,a,b],[0,0,c,d],[a,b,c,d],[c,d,a,b]]

# Plot the vectors as arrows
for i in range(0,len(vectors)):
    vec=vectors[i]
    ax.arrow(vec[0], vec[1], vec[2], vec[3], head_width=0.1, head_length=0.1, color='blue')

# Set axis limits
ax.set_xlim(-1, 7)
ax.set_ylim(-1, 7)

# Set axis labels
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')

# Add labels to the vectors
ax.text(-.5, -.5, '(0,0)', color='black')
ax.text(.8, 2.5, '(c,d)', color='black')
ax.text(2.5, 1, '(a,b)', color='black')
ax.text(3.5, 3, '(a+c,b+d)', color='black')

# Show the plot
plt.show()
```

<img width="598" alt="Screenshot 2025-04-05 at 09 44 50" src="https://github.com/user-attachments/assets/965b8553-6c9d-4a91-86f7-97defd829607" />

You can see from this diagram that determinants reduce the task of finding a parallelograms area to a trivial excercise: ad - bc, so long as we can shift a corner to the origin.  A similar thing applies to triangles, which become 1/2 of that parallelogram:

$$\text{ area of a triangle = }\frac{1}{2}
\left\|{\begin{array}{cc}
x_1 & y_1 & 1 \\
x_2 & y_2 & 1 \\
x_3 & y_3 & 1 \\
\end{array}}\right\|
$$

...where the column of 1s is a trick to shift the corner to the origin.

## Determinant Formulas and Cofactors

### Determinant Formula for a 2x2 Matrix

We can use properties 1-3 of determinants to create a formula for a 2x2 matrix.  Property 1 tells us that the det I = 1.  Property tells us to change the sign of the determinant when we exchange rows.  Property 3 tells us that if we keep the other rows the same, we're allowed to use linearity in the first row (or in any single row).  

Thus by property 3 we can say that:

$$
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
\text{ = }
\left\|{\begin{array}{cc}
a & 0 \\
c & d \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
0 & b \\
c & d \\
\end{array}}\right\|
$$

... because we only operated on one row.  

We can further use property 3 to decompose these determinants further:

$$
\text{... = }
\left\|{\begin{array}{cc}
a & 0 \\
c & 0 \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
a & 0 \\
0 & d \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
0 & b \\
c & 0 \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
0 & b \\
0 & d \\
\end{array}}\right\|
$$

... one of the properties (9?)  states that the determinant of a matrix with a 0 column is 0, so 2 of these matrices can now be zeroed out.  That leaves us with 

$$
\text{... = }
\left\|{\begin{array}{cc}
a & 0 \\
0 & d \\
\end{array}}\right\|
\text{ + }
\left\|{\begin{array}{cc}
0 & b \\
c & 0 \\
\end{array}}\right\|
$$

... continuing to use the properties, we know that the first matrix, now in diagonal form, will have the product of its diagonals for its determinant.  The second matrix will first require a row-swap, causing its sign to reverse before its diagonal can be multiplied.  Thus, using fundamental properties of matrices, we finally get to the familar 2x2 determinant formula ad - bc.

### Determinant Formula for a 3x3 Matrix

Suppose we had to do this process for 3x3 matrices.  We would again have to operate on one row at a time, so that for the components of row 1 we would have 3 matrices, each isolating a separate row one component.  You might think this would lead to 9 total steps, but it actually ends up being 27 because each of these separate row items requires further decomposition.  To see that this is so, review the 2x2 scenario above.  Just as with the 2x2 process, in a 3x3 determinant "decomposition" many of the matrixes would have 0 columns and be zeroed out.  This means we only need to pay attention to those matrices that will not be zeroed out.

Note: when you "decompose" a matrix as with the 2x2 process above, you repeat the *entire* matrix, zeroing out this or that element to isolate others, in various permutations.  You do NOT create sub matrices out of the larger matrix, as one would do with "i,j minor" matrices in a "Laplacian Expansion" approach (this other approach is detailed elsewhere).

To understand which decomposed items will not be zeroed out, we can consider this matrix:

$$
\left\|{\begin{array}{cc}
a_{11} & a_{12} & a_{12} \\
a_{21} & a_{22} & a_{22} \\
a_{31} & a_{32} & a_{33} \\
\end{array}}\right\|
$$

We know that the following matrix will not zero out, because it has no 0 columns:

$$
\left\|{\begin{array}{cc}
a_{11} & 0 & 0 \\
0 & a_{22} & 0 \\
0 & 0 & a_{33} \\
\end{array}}\right\|
$$

... and this example will also not zero out.

$$
\left\|{\begin{array}{cc}
a_{11} & 0 & 0 \\
0 & 0 & a_{23} \\
0 & a_{32} & 0 \\
\end{array}}\right\|
$$

... in general, the "sub matrices" that are not zeroed out will have one entry from each row and each column.  Finding all these different combinations of subscripted components is very like using a permutation matrix.  In fact it eventually ends up being a permutation matrix, in the sense that one factors out the actual numbers, leaving P matrices of 1s and 0s.  With this in mind, you can see that these two example matrices would end up being $a_{11}a_{22}a_{33}$ and - $a_{11}a_{32}a_{23}$ (see that the row swap on the second matrix imposes a sign change).  

In these 2 examples of non-zeroed 3x3 matrices both contained a_{11}.  You can see that a similar process would be used for a_{12} and so on, and similarly for every component, eliminating those combinations that ended up being redundant. This would give you a formula for the determinant based solely on the first 3 properties of determinants.

**Definition:** Note that each of these "sub-matrices" or matrices of non-redundant ombinations that survive being zeroed out, are formally called **terms**.  

**Notes on determinant "terms":**
* A given nxn matrix will have n! such terms.  The fact that there are always n! terms comes from the diminshing "degrees of freedom" that each successive row imposes on the next: as the permutations for original componennt positions in the top rows are used up, the possibilities for original combinations using the components in lower rows become fewer.
* Half the terms, expressed as products of their non-zero components will have + sign, and the other half will have a minus sign.  

Note that, depending on the dimensions of the nxn matrix, the sign of any given combination will be based on the direction of the diagonal it is on --downward left to right, or downward right to left.  

### General Determinant Formula 

Aka "the BIG FORMULA" for nxn determinants.

${det A = }\sum\frac{+}{-}a_{1\alpha}a_{2\beta}a_{3\gamma}\text{...}a_{n\omega}$

Where 1...n are the matrix rows, and alpha ...omega are the columns, and the overall permutation of rows and columns are unique for each term.  All the terms are summed, taking account of the sign +/- designated by the number of their row swaps.

### Determinant Cofactors Formula

Co-factors is a way to connect the large general formula from nxn matrices to ones which are n-1xn-1.

Suppose we had a 3x3 matrix again:

$$
\text{det A =}
\left\|{\begin{array}{cc}
a_{11} & a_{12} & a_{12} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} \\
\end{array}}\right\|
$$

It is clear that the "terms" of the determinant could be organized via the distributive property to extract out common multipliers.  So:

$\text{det A = }a_{11}\left(a_{22}a_{33} - a_{23}a_{32}\right)\text{ + }a_{21}\left(\text{ ... }\right)\text{ + }a_{31}\left(\text{ ... }\right)\text{ +  ... etc.}$

The components inside the parentheses are known as "co-factors".  In this example, you can see that the parenthetic co-factor expressions fit the "ad-bc" pattern of a 2x2 matrix determinant.  When using this co-factor approach, the convention is to always keep the sign of the factor (outside the parenthesis) positive, and use sign in the appropriate items in the co-factor to track sign changes.  

In general, we can say that the cofactor of any determinant component $a_{ij}$ is :

$C_{ij}=\frac{+}{-}\text{ det }\left(\text{n-1 matrix} with row i, column j erased\right)$ .  The sign for the cofactor is determined by whether i + j is odd or even.  Even --> + ; Odd --> - .  Before the sign is added, the co-factor is also known as a "minor".  

Using the above, we can then say that the "cofactor formula" for a determinant is:

$\text{det A = }a_{11}C_{11}+a_{12}C_{12}...a_{1n}C_{1n}...a_{nn}C_{nn}$ .

What is the co-factor formulation of a 2x2 matrix?  Again if we have:

$$
\left\|{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right\|
$$

... and use the co-factor approach, we will get ad, then bc, which must use a row-swap to get in correct order, so that we end with ad - bc as expected.

### Determinant Cofactors with Tri-diagonal Matrix

Suppose we had the following tri-diagonal matrix "A4":

$$
A_4\text{ = }
\left\|{\begin{array}{cc}
1 & 1 & 0 & 0 \\
1 & 1 & 1 & 0 \\
0 & 1 & 1 & 1 \\
0 & 0 & 1 & 1 \\
\end{array}}\right\|
$$

We could also designate "A1" as the top left 1x1 matrix containing 1, "A2" as the top left 2x2 matrix, and "A3" as the top left 3x3 matrix.  Considering RR and sign changes for row swaps, the determinants would then be det A1 = 1, det A2 = 0, det A3 = -1, det A4 = 1 .  Using cofactors, the determinant of A4 is:

det A3 - det A2.  An in general the determinant for an nxn matrix is det $A_n$ = det $A_{n-1}$ - det $A_{n-2}$ .  The relevance of this is: it puts you in a position to assess calculation in the least possible steps, and also provides some cross-checks.  

### The General Formula for Determinants: Laplace Expansion (LE)

For a square matrix of any size, where r = n, there is a method called LaPlace Expansion which will calculate the determinant.  LaPlace Expansion was also the name of a suburb I lived in as a child, but I'm sure that's just a coincidence.  For a matrix over size 3x3, I would guess LPE might be less efficient then just doing RRE and multiplying the diagonals.  Anyway ...

LE starts with a definition.  **The "i,j minor of a matrix" is the determinant of the matrix $M_{i,j}$ obtained by deleting row i and column j .  **  This is the same as a co-factor.  

Thus, for a matrix:

$$
\left[{\begin{array}{cc}
1 & 3 & 7 \\
0 & 2 & 0 \\
-2 & 0 & -7 \\
\end{array}}\right]
$$

... the minor $M_{1,2}$ would be the matrix obtained by deleting the first row and the second column.  It isn't explicit in this definition, but the minor is the determinant for all of the matrix not covered by the deleted row and column.  So for example, if this had been a 4x4 matrix, $M_{ij}$, or $C_{ij}$ in cofactor terms, would be the determinant for a matrix comprised of components in column one from $a_{21}$ to $a_{41}$ and the square area from $a_{32}$ to $a_{44}$ taken all together.  

So for Laplace Expansion, for an nxn matrix, we can compute the determinant in terms of its minors, which will be n-1xn-1 matrices.  For any fixed row i, 

$$\text{det A = }\sum_{j = 1}{N}\left(-1\right )^{i + j}a_{ij}\text{det }M_{ij}$$  -- This is effectibely the same thing as Strang's "big formula".

Mapping this formula to the a 3x3 matrix with generic components:

$$
\text{det A =}
\left\|{\begin{array}{cc}
a_{11} & a_{12} & a_{12} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} \\
\end{array}}\right\|
$$

... say we fix i = 1, j =1 to begin.  Then we would multiply $a_{11}$ by $M_{ij}$, where $M_{ij}$ is the determinant of the matrix remaining when row 1 and column 1 are deleted.  The sign of this product is ${-1}^{1 + 1}$, or equivalently we use "+ if i + j is even; - if i + j is odd ".  Next, we would multiply $a_{12}$ by $M_{12}$ and give it a minus sign, and so on.  

## Applications of Determinants

### Using Determinants To Find $A^{-1}$ 

Sources:
* https://usfca.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=18d6d01c-7f28-42ca-ade1-b01f0171e3cb&start=45.892811
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/lecture-20-cramers-rule-inverse-matrix-and-volume/

The formula for calculating the inverse of a 2x2 matrix (taking this as given) is:

$$
{\left[{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right]}^{-1}
\text{ = }
\frac{1}{ad - bc}
\left[{\begin{array}{cc}
d & -b \\
-c & a \\
\end{array}}\right]
$$

Now we want to extrapolate this to generalize to larger matrices.  Per [property 9](#property-9) , we understand why it makes sense to divide by the determinant, but we need to understand the pattern for the matrix it acts on.  This matrix is actually a matrix of cofactors.  You can see this using the co-factor elimination method: d is the cofactor of a, which is in position 11, and d is what you'd get if you struck out row 1 and column 1, would be d, and similarly with the other elements in this matrix.  Similarly -b is the cofactor of c, because c is in position 21, and striking out this respective row and column would get you -b (with negative sign because i + j is odd).

From these observations, we can generalize to a formula for the inverse which incorporates the determinant:

$$A^{-1}\text{ = }\frac{1}{det A}C^T$$ 

, where C is the transposed matrix of cofactors.  Reviewing the above matrix C for the 2x2 example, you can see that these cofactors are in fact transposed when you look at their relation to A: a and d on the left side of the equation are matched in the same position as their corresponding co-factors, but the b and c are in the opposite corners to their corresponding cofactors.  This is due to transposition.

We can continuing inspecting the formation of $C^T$ but looking at the 3x3 case.  Consider $A^{-1}$ as:

$$
{\left[{\begin{array}{cc}
a & b & c \\
d & e & f \\
g & h & i \\
\end{array}}\right]}^{-1}
\text{ = } 
\frac{1}{ det A }
C^T
$$

We know that det A will be a sum of of 3! products, and each of these products will be use a combination of n entries, e.g. a\*e\*i.  The components $C^T$ will involve products of n-1 entries, e.g. ei - fh.  

In order to check that 

$$A^{-1}\text{ = }\frac{1}{det A}C^T$$ 

is true, we can reformulate it as:

$$AC^T\text{ = }{det A}I$$ 

Which is to say that A times the transposed matrix of cofactors gives you the determinant of A.  If you contemplate this reformulation, you can see that we got it by multiplying both sides by A, so that $A^{-1}A$ became I on the left side, and det A $AC^T$ on the other side.  Then both sides were multiple by $\frac{1}{ det A}$, so that we end with $AC^T\text{ = }{det A}I$ .

In more detail, this gives us A multiplied by the cofactor matrix C:

$$
\left[{\begin{array}{cc}
a_{11} & {...} & a_{1n} \\
{...} & {...} & {...} \\
a_{n1} & {...} & a_{nn} \\
\end{array}}\right]
\left[{\begin{array}{cc}
c_{11} & {...} & c_{n1} \\
{...} & {...} & {...} \\
c_{1n} & {...} & c_{nn} \\
\end{array}}\right]
$$

Notice that for C, the row-column indices are reversed because of transposition.  Consider what we would get in the index 1,1 entry of the results from this multiplication.  This would give us a summation of $a_{11}c_{11} - a_{12}c_{12} ... + a_{nn}c_{nn}$, assuming the signs are correctly managed ... this is just exactly the [cofactor formula](#determinant-cofactors-formula) for the determinant of A.  Note that the result will NOT be a single determinant of A, but rather a matrix with sub-products of det A down the diagonal.  AND the rows and columns of A and C are matched so that any off-diagonal value will be C.  To illustrate this, return to the 2x2 matrix scenario, where:

$$
A^{-1}\text{ = }{\left[{\begin{array}{cc}
a & b \\
c & d \\
\end{array}}\right]}^{-1}
\text{,C = }
\left[{\begin{array}{cc}
d & -b \\
-c & a \\
\end{array}}\right]
$$

You can see that when you multiply $A^{-1}$ row (a b) times C column (-b a) you will get zero.  But further, in this mode of matrix multiplication with the matrices oriented as they are, the effect for the off diagonal cofactors (minor determinants) is that we're taking the determinant of matrices that have identical first and last rows, and which must therefore zero out.  -- Anyway, the right side of the equation ends up being a matrix of det A components down the diagonal, with all 0s off diagonal.  By property 8? this can then be turned into the product of the diagonals \* I \* I = det A * I.  

### Using Determinants to Find Ax = b

This means specifically to solve for x in Ax = b.

We know that x = $A^{-1}b$ .  This means that $x\text{det = }A^{-1}b\text{ = }\frac{1}{ det A }C^Tb$ .

#### Solving x in Ax = b: Cramer's Rule

When solving for **x**, we can of course consider **x** as a vector of components $x_1$, $x_2$ etc.  We also know by the above formula that any solution for x will be multiplied by $\frac{1}{ det A }$ .  Thus, we can consider the series of vector x components as having a form like:

$$x_1\text{ = }\frac{1}{ det A }{ some TBD element }b$$ .

We can assume that the TBD element will be a corresponding component of C.  That is, we're multiplying some co-factor from C times a component of b.  Since we are multiplying a co-factor by a component of b, we assume we are getting a determinant of something.  We can call that "something" det $B_1$, updating our equation for $x_1$ as:

$$x_1\text{ = }\frac{det B_1}{ det A , }x_2\text{ = }\frac{det B_2}{ det A }\text{ ... etc }$$ .

The "B" matrices contain the vector b from "Ax = b" in the correct column, and n-1 columns of A otherwise.  That is:

$$
B_1\text{ = }\left[{\begin{array}{cc}
b & {\text{n-1 columns of A} \\
\end{array}}\right]
$$

What ever the index of B is, that column replaces the columns of A on the right hand side of this equation.  Doing this somehow gives the correct matrix multiplication excerpt from $C^Tb$ to solve for $x_1$ in $x_1\text{ = }\frac{det B_1}{ det A }$ .  The mechanism of the matrix B_1 such that b1 is multiplied by c11, b2 by c21, and so on.

In general, $B_j$ is A with column j replaced by b.  The determinant of this matrix B_j is divided by det A to get x_j.  That is, $x_j\text{ = }\frac{ det B_j }{ det A}$ .

### Determinants and Volume
















