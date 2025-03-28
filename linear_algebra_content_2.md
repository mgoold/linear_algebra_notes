
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



