
# Exercises on Elimination with Matrices

## Problem 2.1: 

In the two-by-two system of linear equations below, what multiple of the first equation should be subtracted from the second equation when using the method of elimination? Convert this system of equations to matrix form, apply elimination (what are the pivots?), and use back substitution to find a solution. 

Try to check your work before looking up the answer.

$$2x + 3y = 5 $$
$$6x + 15y = 12$$

In *augmented* matrix form:

$$
\
  \left[ {\begin{array}{cc}
  2 & 3 & 5 \\
  6 & 15 & 12 \\
  \end{array} } \right]
\
$$

Answer:

The first row is multiplied by 3 and subtracted from the second row to yield:

$$2x + 3y =	5$$
$$0x + 6y = -3$$ .

Using multiplication of the augmented matrix by an elimination matrix, this looks like:

$$
\
  \left[ {\begin{array}{cc}
  1 & 0 \\
  -3 & 1 \\
  \end{array} } \right]
\
$$
\
  \left[ {\begin{array}{cc}
  2 & 3 & 5 \\
  6 & 15 & 12 \\
  \end{array} } \right]
\
\text{ = }
\
  \left[ {\begin{array}{cc}
  2 & 3 & 5 \\
  0 & 6 & -3 \\
  \end{array} } \right]
\
$$

Then by back substitution, y = $-\frac{1}{2}$, and after some gsheet fiddling, x ends up being 3.25.
Plugging these values back into the original linear equation system (in a gsheet) we can see that these x and y values do indeed yield the original respective values of 5 and 12.

## Problem 2.1: 

(2.3 #29. Introduction to Linear Algebra: Strang) 

Find the triangular matrix E that reduces “Pascal’s matrix” to a smaller Pascal:

$$
\
  \left[ {\begin{array}{cc}
  1 & 0 & 0 & 0  \\
  1 & 1 & 0 & 0  \\
  1 & 2 & 1 & 0  \\
  1 & 3 & 3 & 1  \\
  \end{array} } \right]
\\text{ = }
\
  \left[ {\begin{array}{cc}
  1 & 0 & 0 & 0  \\
  0 & 1 & 0 & 0  \\
  0 & 1 & 1 & 0  \\
  0 & 1 & 2 & 1  \\
  \end{array} } \right]
\
$$

First of all, a "Pascal Matrix" is a Pascal triangle in matrix form, and a Pascal triangle is one where the row values in each column increment by the value to the left of the previous row.

Call the initial matrix on the left hand side A, and the result matrix on the right hand side U.
To get the desired result matix U, we need to multiply it by an elimination matrix E.  We are doing row elimination, so E will be on the left hand side of A when we multiply it.

Eyeballing it, the first row in A is unchanged, and the values in every other row are decremented by 1 except for the last in the right most column.  

We actually require multiple elimination matrices at first.  Through experimentation, we can determine that the successive elimination matrices required are:

$$
E1=
\
  \left[ {\begin{array}{cc}
  1	& 0	& 0	& 0\\
  -1 & 1 & 0	& 0\\
  0	& -1 & 1	& 0\\
  0	& 0	& -1	& 1\\
  \end{array} } \right]
\,
E2=
\
  \left[ {\begin{array}{cc}
  1	& 0	& 0	& 0\\
  0 & 1 & 0	& 0\\
  0	& -1 & 1	& 0\\
  0	& 0	& -1	& 1\\
  \end{array} } \right]
\,
E3=
\
  \left[ {\begin{array}{cc}
  1	& 0	& 0	& 0\\
  0 & 1 & 0	& 0\\
  0	& 0 & 1	& 0\\
  0	& 0	& -1	& 1\\
  \end{array} } \right]
\
$$

.

When we multiply these together as E1E2E3 = M, we get:

$$
M=
\
  \left[ {\begin{array}{cc}
  1	& 0	& 0	& 0\\
  -1 & 1 & 0 & 0\\
  1	& -2 & 1	& 0\\
  -1	& 3	& -3 & 1\\
  \end{array} } \right]
\
$$

.

The ability to do this comes from the fact that the associative property is true for matrix multiplication.
Strang makes the point that because this matrix M acting on A = I, it must necessarily be the (the only) inverse of A.






