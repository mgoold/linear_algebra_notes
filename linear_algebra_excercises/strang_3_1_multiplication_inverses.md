
# Multiplication and Inverses

## Problem 3.1

Add AB to AC and compare with A(B + C) :

$$
A\text{ = }
\left[
  \begin{matrix}
   1 & 2 \\
   3 & 4 \\
  \end{matrix}
\right]
\text{B = }
\left[
  \begin{matrix}
   1 & 0 \\
   0 & 0 \\
  \end{matrix}
\right]
\text{C = }
\left[
  \begin{matrix}
   0 & 0 \\
   5 & 6 \\
  \end{matrix}
\right]
$$

AB + AC:

$$
AB\text{ = }
\left[
  \begin{matrix}
   1 & 2 \\
   3 & 4 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
   1 & 0 \\
   0 & 0 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
   1 & 0 \\
   3 & 0 \\
  \end{matrix}
\right]
\text{,AC = }
\left[
  \begin{matrix}
   1 & 2 \\
   3 & 4 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
   0 & 0 \\
   5 & 6 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
   10 & 12 \\
   20 & 24 \\
  \end{matrix}
\right]
$$

$$
\text{AB + AC}
\left[
  \begin{matrix}
   11 & 12 \\
   23 & 24 \\
  \end{matrix}
\right]
$$

A(B + C):

$$
\text{B + C = U =}
\left[
  \begin{matrix}
   1 & 0 \\
   5 & 6 \\
  \end{matrix}
\right]
\text{,AU = }
\left[
  \begin{matrix}
   11 & 12 \\
   23 & 24 \\
  \end{matrix}
\right]
$$

--Associative property for matrix multiplication is true.

## Problem 3.2:

(2.5 #24. Introduction to Linear Algebra: Strang) Use Gauss-Jordan elimination on [U I] to find the upper triangular $U^{-1}$ :

$$
UU^{-1}\text{ = }I\text{; }
\left[
  \begin{matrix}
   1 & a & b \\
   0 & 1 & c \\
   0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
    &  &  \\
   x_1 & x_3 & x_3 \\
    &  &  \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
   1 & 0 & 0 \\
   0 & 1 & 0 \\
   0 & 0 & 1 \\
  \end{matrix}
\right]
$$

This is the equivalent to $UI=IU^{-1}$.  To find $IU^{-1}$, we can take the identity UI=UI and succesively modify it until we end up with $IU^{-1}=IU^{-1}$, or fail.  We can denote the transformation process of this identity as: $UI{{...}^{\rightarrow}}IU^{-1}$ .
Because it is an identity, we will just show the right side of the equation:

$UI{{...}^{\rightarrow}}IU^{-1}$ 

$$
\left[
  \begin{matrix}
  1	& a	& b \\
  0	& 1	& c \\
  0	& 0	& 1 \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
   1 & 0 & 0\\
   0 & 1 & 0\\
   0 & 0 & 1\\
    \end{matrix}
  \right.
\right]
$$

$$
\rightarrow
\left[
  \begin{matrix}
  1	& 0	& b-ac \\
  0	& 1	& c \\
  0	& 0	& 1 \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
   1 & -a & 0\\
   0 & 1 & 0\\
   0 & 0 & 1\\
    \end{matrix}
  \right.
\right]
$$

$$
\rightarrow
\left[
  \begin{matrix}
  1	& 0	& b-ac \\
  0	& 1	& 0 \\
  0	& 0	& 1 \\
  \end{matrix}
  \left|
  \
  \begin{matrix}
  1 & -a & 0\\
  0 & 1 & -c\\
  0 & 0 & 1\\
  \end{matrix}
  \right.
\right]
$$

$$
\rightarrow
\left[
  \begin{matrix}
  1	& 0	& 0 \\
  0	& 1	& 0 \\
  0	& 0	& 1 \\
  \end{matrix}
  \left|
  \
  \begin{matrix}
  1 & -a & -b+ac\\
  0 & 1 & -c\\
  0 & 0 & 1\\
  \end{matrix}
  \right.
\right]
$$

So $U^{-1}$ is:

$$
  \left[
  \begin{matrix}
   1 & -a & -b+ac\\
   0 & 1 & -c\\
   0 & 0 & 1\\
  \end{matrix}
  \right]
$$

