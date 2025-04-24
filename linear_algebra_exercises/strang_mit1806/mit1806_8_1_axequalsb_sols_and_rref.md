
# Exercises on Solving Ax = b and Row Reduced Echelon Form R

## Problem 8.1

Explain why all of the following are false:

a) The complete solution [of any system Ax=b] is any linear combination of xp and xn.
(Assuming xn means the null space.)

My Answers:
* A complete solution may or may not include x_p, depending on the kind of RREF form it has.  The zero vector Z may be its only solution.
* A system Ax=b may have no solution.

Textbook answer:

"The coefficient of xp must be one." --So "the complete solution" is a clue that they specifically mean the "xp + xs" solution format.  For such cases, they point out that the coefficient of xp can only be the constant 1 (because it's a particular point), and that is not what is meant by a "linear combination", in which each vector is multiplied by a scalar *variable*.

b) The system Ax = b has at most one particular solution.

My Answer:

Exception: Ax=b systems in r=m=n rref form have an infinite number of solutions. 

Textbook answer:

If $x_n$ ∈ N(A) is in the nullspace of A and $x_p$ is one particular solution, then $x_p$ + $x_n$ is also a particular solution.  -- I think this is another way of providing an exception like I did.

c) If A is invertible there is no solution xn in the nullspace.

My answer:

Exception: A full column rank r=m=n matrix will always be invertible, and the Z vector **0** will be its only N(A) solution.

Textbook Answer:

There’s always $x_n$ = 0. -- I didn't get this at first, but I think $x_n$ mean "that set of x values that yield the null space when A operates on x".

## Problem 8.2

$$
\text{Let U =}\left[
  \begin{matrix}
  1 & 2 & 3 \\
  0 & 0 & 4 \\
  \end{matrix}
\right]
\text{and c =}\left[
  \begin{matrix}
  5 \\
  8 \\
  \end{matrix}
\right]
$$

### Part 1
Use Gauss-Jordan elimination to reduce the matrices [U 0] and [U c] to [R 0] and [R d].

Notes: 

I didn't understand what was meant by their matrix notation here, although its plain to see.  For each of these items, they want you to make an augmented matrix.  So for [U 0] put a 0 matrix to the right of U, horizontally, and similarly for Uc.  BUT, then they want you to solve for Rx = d, not Rd = 0.

[U 0] --> [R 0]:

$$
\text{Let U =}\left[
  \begin{matrix}
  1 & 2 & 3 & 0\\
  0 & 0 & 4 & 0\\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 2 & 3 0\\
  0 & 0 & 1 0\\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 2 & 0 0\\
  0 & 0 & 1 0\\
  \end{matrix}
\right]
\text{ = R0}
$$


[U c] --> [R d]:

$$
\text{[U c] = }
\text{Let U =}\left[
  \begin{matrix}
  1 & 2 & 3 & 5\\
  0 & 0 & 4 & 8\\
  \end{matrix}
\right]
\rightarrow
\text{Let U =}\left[
  \begin{matrix}
  1 & 2 & 3 & 5\\
  0 & 0 & 1 & 2\\
  \end{matrix}
\right]
\rightarrow
\text{Let U =}\left[
  \begin{matrix}
  1 & 2 & 0 & -1\\
  0 & 0 & 1 & 2\\
  \end{matrix}
\right]
\text{ = [R d]}
$$

### Part 2

Solve Rx = 0 and Rx = d.

### Rx = 0:

Note: 
Although we had to turn [U 0] --> [R 0], this question reverts us to dealing with Rx =0 .

Given 
$$
\left[
  \begin{matrix}
  1 & 2 & 0 0\\
  0 & 0 & 1 0\\
  \end{matrix}
\right]
$$

, we set the free variable in column 2 ($x_2$) equal to 1.  Then by back-substitution we have:

1$x_1$ + 1\*1 + 0$x_3$ = 0 -->  $x_1$ = -2

                1$x_3$ = 0 -->  $x_3$ = 0
  
So understanding that we can now multiply x by any constant c, we have:

$$
cx\text{ = }
\left[
  \begin{matrix}
  -2 \\
  1 \\
  0 \\
  \end{matrix}
\right]
$$

Correct.

### Rx = d:

$$
[R d]\text{ = }
\left[
  \begin{matrix}
  1 & 2 & 0 -1\\
  0 & 0 & 1 2\\
  \end{matrix}
\right]
$$

, or the equations:

1$x_1$ + 2$x_2$ + 0$x_3$  = -1
                  1$x_3$  =  2

Giving us I across columns 1 and 3, and F in column 2.  We can find the special solutions by toggling 1,0 values for the free variables in F columns as follows:

$$
c_1
\left[
  \begin{matrix}
  -3 \\
  1 \\
  2 \\
  \end{matrix}
\right]
$$

## Problem 8.3

Suppose Ax = b and Cx = b have the same (complete) solutions for every b. Is it true that A = C?

Yes ... I didn't really understand why the approach taken by the textbook was necessary.  You might think that including the phrase "complete solution" would add some complexity, but they don't use "xp + xs" language in the solution.  Thus, I would have thought it was enough to say that:

* Ax = b and Cx = b have the same (complete) solutions for every b.
* Therefore Ax = Cx, and x is identical on both sides of the equation.
* Therefore A must equal C.

Textbook Answer:

Yes. In order to check that A = C as matrices, it is enough to check that Ay = Cy for all vectors y of the correct size (or just for the standard basis vectors, since multiplication by them “picks out the columns”). So let y be any vector of the correct size, and set b = Ay. Then y is certainly a solution to Ax = b, and so by our hypothesis must also be a solution to Cx = b; in other words, Cy = b = Ay.

Note:
I also don't know what is meant by "multiplication picks out the columns".

Definition:
**Standard basis vector**: a vector of length 1 that is perpendicular to the vector being considered.

OK, so y would be normally be thought of as perpendicular to x.  And a standard basis vector, being by definition perpendicular to x, has the form [0,1] (for example).  So that is what is meant by "multiplication picking out the columns" -- the relevant column will be set to itself (identity), and the others set to 0.  I still don't get why they prefer their explanation.


