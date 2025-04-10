
# Linear Algebra Content 3

## Matrix Rank and "Linear Maps"

### Sources:
* USF: https://usfca.instructure.com/courses/1627052/pages/matrix-rank-and-linear-maps-video-11?module_item_id=18611414
* pivots: [pivots](https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_content.md#matrix-elimination-example-1)
* [row reduction](https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_content_2.md#ax0-matrix-reduced-row-echelon-form#special-solutions-to-ax=0)
* [column rank](https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_content_2.md#full-column-rank-rn#general-findings-on-r,n,m-and-number-of-solutions)

As we saw [here](https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_content.md#matrices) , it is standard practice to arrange a linear combination of column vectors as a matrix "A" acting on a vector of variables [x], where the number of columns in A = number of rows in [x].  The columns in A are then said to be the "column space", or "C(A)", which is then said to "span" the columns.  The word "span" is shorthand for "encompasses all values from all possible linear combinations of C(A)."  

### Matrix Rank Fact Review
* The column "rank" of a matrix A is the number of pivots it has after row reduction.  This is also the "dimension" of C(A).  
* The row "rank" of a matrix A is the number of pivots it has after row reduction.  This is also the "dimension" of the row space R(A).
* The row rank is always equal to the column rank.
* The rank of C(A) is therefore equal to $C\left(A^T\right)$.
* The rank of C(A) will always be $\leq$ min(m,n) after row reduction.
* A "full rank" matrix has a post-RR pivot in every column.
* A square full rank matrix will be invertible.
  * consequently a square matrix with full rank will have a non-zero determinant(s) -- it has non-zero determinant if and only if it has full rank.

### Matrices as "Linear Maps"

Suppose we have A**x** = **y** .  

If A is mxn, then x has to be an n-dimensional vector, and y must be an m-dimensional vector.  In this sense, the function maps  column "n" space to row "m" space. Again, this is equivalent to "spanning" C(A) by taking all possible results from linear combinations of the columns.

Thus, the column space C(A) is said to be equal to the "image" the linear map, where "image" means "all possible outputs of linear map".  A "linear map" is another way to say that vector operations are done in such a way as to preserve addition and multiplication effects in vector operations so that the output of these operations stay in the same subspace as the input vectors.

Thus, **the rank of A gives the dimension of an image of a linear map.** 

### Null Spaces

The nullspace of A, or N(A) is the set of vectors in x such that Ax = **0** .  
The "nullity" of A is the *dimension* of the nullspace of A.
x in Ax maps both to C(A) and N(A); the two subspaces are complements of each other.
One of the most famous theorems in linear algebra is the **"rank-nullity" theorem.** 

This theorem states that for a matrix $A_{mxn}$, the Rank(A) + Nullity(A) = the number of columns in A = n.  Another way to say this is that the rank of dimension of the image of a + the the nullity of A = n columns in A.

So if we have n vectors in A, every vector in n dimensions is either mapped into the image or to the 0 vector.  The dimension of these spaces, added together, will = n.  

Thus for square matrices full rank implies that the nullity (the number of columns in N(A)) = 0.

#### Rank Nullity Theorem Example

Suppose we have the matrix  

$$
A\text{ = }
\left[
{\begin{array}{cc}
2 & 4 \\
1 & 2 \\
\end{array} } 
\right]
$$

, and we want to find the nullity of A.  We can begin this process by doing RREF on A, which leaves us with:

$$
A\text{ = }
\left[
{\begin{array}{cc}
1 & 2 \\
0 & 0 \\
\end{array} } 
\right]
$$

Which means that N(A) will be 

$$
N(A)\text{ = c}
\left[
{\begin{array}{cc}
-2 \\
1 \\
\end{array} } 
\right]
\text{, }
N(A)\text{ = c}
\left[
{\begin{array}{cc}
2 \\
-1 \\
\end{array} } 
\right]
$$

Since rank of A post rref = 1, the nullity must equal 1, since C(A) = 2.



## Multivariate Calculus with Matrices

## Gradient Descent

## Linear Regression

## Orthonormality

## Projection Matrices

## Positive Semidefinite Matrices

## Singular Value Decomposition
