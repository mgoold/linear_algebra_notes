
# MIT 18.06 5.1: Exercises on Transposes, Permutations, Spaces

## Problem 5.1:

A: Find a 3 by 3 permutation matrix with P3 = I (but not P = I).

$$
P_{1,3}\text{ = }
\left[
  \begin{matrix}
  0 & 0 & 1 \\
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  \end{matrix}
\right]
$$

... will do the trick, when multiplied 3 times.

B: Find a 4 by 4 permutation $\hat{P}$ with $\hat{P}^4\neq{I}$.

This was a complete bust.  I never did understand the meaning of the question or the solution.

## Problem 5.2:

Suppose A is a four by four matrix. How many entries of A can be chosen independently if:

A.  A is symmetric?
If you number the cells that can be designated before duplication occurs, it comes to 10.

B.  A is skew-symmetric? (AT = −A).
Because the diagonal value is identical, the number of unique possible values is reduced to 6.

Problem 5.3:
True or false (check addition or give a counterexample):

I believe this ill-framed set of questions is meant to highlight the way in which symmetric matrices force, by definition, a set of dimensions that is equal to their size (e.g. a 3x3 symmetric matrix must have at least one vector extending into each of 3 dimensions).  I think this is the root reason why they are closed under addition and multiplication.

a) The symmetric matrices in M (with AT = A) form a subspace.
  
Each time we prove that a group of something forms a subspace, we have to prove that the results of addition will not leave the same space, and that the results of multiplication also will not leave that space.  

In this case we do it by referencing the fact that a symmetric matrix is identical to its transpose.  So when you do addition or multiplication on a symmetric matrix you don't end up changing the content at all, making it impossible for the result of these operations to "leave the space".

To be honest, I didn't understand the question in a way that would have yielded the provided solutions.  All the solution seems to be saying is that if you add the transpose of the sum of two symmetric matrices you'll still get a symmetric matrix, and transposing a symmetric matrix multiplied by a scalar still gives you a symmetric matrix:

Answer: True: $A^T\text{ = }A\text{ and }B^T\text{ = }B$ lead to:

$${\left(A\text{ + }B\right}^T\text{ = }A^T\text{ + }B^T\text{ = }A\text{ + }B\text{, and }{\left(cA\right)}^T\text{ = }cA.$$

It seems clear that if you multiply a symmetric matrix (or pretty much any matrix in $R^n$), you're going to get a result that keeps all the same vectors but stretches them all by the same value.  What I don't get is: I add 2 symmetric matrices A + B, I get another symmetric matrix C, fine.  *In what sense is C in the same space as A and B?*  

For example, 

$$
\left[
  \begin{matrix}
  1 & 2 & 1 \\
  2 & 1 & 3 \\
  1 & 3 & 1 \\
  \end{matrix}
\right]
\text{ + }
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  3 & 1 & 2 \\
  0 & 2 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  2 & 5 & 1 \\
  5 & 2 & 5 \\
  1 & 5 & 2 \\
  \end{matrix}
\right]
$$

Adding these two matrices clearly give a new matrix of vectors that cannot be on the same line, or in one case in the same plane, as the vectors in its constituent matrices.  I infer from this what what really matters is that the symmetric nature of the matrices force the result matrix to also have the same number of dimensions.  That they stay in the same number of dimensions of real space despite addition or multiplication is the sense in which they contstitute a "sub-space".

(See above notes on this question.)

b) The skew symmetric matrices in M (with AT = A) form a subspace.

A similar proof in matrix language is offered for this assertion:

Answer: True: $A^T\text{ = }-A\text{ and }B^T\text{ = }-B$ lead to:

$${\left(A\text{ + }B\right}^T\text{ = }A^T\text{ + }B^T\text{ = }-A\text{ - }B\text{, and }{\left(cA\right)}^T\text{ = -}cA.$$

Again, same issue for me as with part (a).

c)  The unsymmetric matrices in M (with $A^T\neq{A}$ form a subspace.

Answer: This is false:

$$
\left[
  \begin{matrix}
  1 & 1 \\
  0 & 0 \\
  \end{matrix}
\right]
\text{ + }
\left[
  \begin{matrix}
  0 & 0 \\
  1 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 1 \\
  1 & 1 \\
  \end{matrix}
\right]
$$

... the insight is that you can add 2 matrices whose vectors extend into only one dimension, and add them together to get a result that has all 2d vectors. Consequently, the result likes completely outside the possible space of either of its constituent vectors.  So unsymmetric matrics are not "closed" under addition.
