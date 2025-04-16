
# LU Decomposition

Exercises on factorization into A = LU

## Problem 4.1:

What matrix E puts A into triangular form EA = U? Multiply by $E^{−1}$ = L to factor A into LU.

$$
A\text{ = }
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  2 & 4 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
$$

$$E_{21}A=U1$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  -2 & 1 & 0 \\
  0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  2 & 4 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  0 & -2 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
$$

$$E_{31}U1=U2$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  -2 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  0 & -2 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  0 & -2 & 0 \\
  0 & -6 & 1 \\
  \end{matrix}
\right]
$$

$$E_{32}U2=U$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & -3 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  0 & -2 & 0 \\
  0 & -6 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 3 & 0 \\
  0 & -2 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
$$

Now we can multiply the inverses of E, in reverse order, to obtain L.  

From the inside out, the order of E operating on A was: $E_{32}E_{31}E_{21}A=U$ .

Therefore the order of matrices operating in L will be: $L={E_{21}}^{-1}{E_{31}}^{-1}{E_{32}}^{-1}$ .

Remember that the inverses of elementary matrices are just the same matrix with the signs reversed on the off-diagonal multipliers.
Also, we can obtain L by just "filling" in the off-diagonal multipliers from each elementary matrix E into the identity matrix:

$$L={E_{21}}^{-1}{E_{31}}^{-1}{E_{32}}^{-1}\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  2 & 1 & 0 \\
  0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  2 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & 3 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  2 & 1 & 0 \\
  2 & 3 & 1 \\
  \end{matrix}
\right]
$$

.

##Problem 4.2: 

(2.6 #13. Introduction to Linear Algebra: Strang) Compute L
and U for the symmetric matrix

$$
A\text{ = }
\left[
  \begin{matrix}
  a & a & a & a \\
  a & b & b & b \\
  a & b & c & c \\
  a & b & c & d \\
  \end{matrix}
\right]
$$

We can use the following elimination matrices to transform A into U:

$$E{33}E{32}E{21}A=U$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 & 0 \\
  -1 & 1 & 0 & 0 \\
  -1 & 0 & 1 & 0 \\
  -1 & 0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 & 0 \\
  0 & 1 & 0 & 0 \\
  0 & -1 & 1 & 0 \\
  0 & -1 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 & 0 \\
  0 & 1 & 0 & 0 \\
  0 & 0 & 1 & 0 \\
  0 & 0 & -1 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  a & a & a & a \\
  a & b & b & b \\
  a & b & c & c \\
  a & b & c & d \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  a & a & a & a \\
  0 & b-1 & b-1 & b-1 \\
  0 & 0 & c-b & c-b \\
  0 & 0 & 0 & d-c \\
  \end{matrix}
\right]
$$

We can then multiply the inverse matrices in E in reverse order to get L: ${E{21}}^{-1}{E{32}}^{-1}{E{33}}^{-1}\text{ = }L$, so that 

$$
L\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  1 & 1 & 1 & 0 \\
  1 & 1 & 1 & 1 \\
  \end{matrix}
\right]
$$




