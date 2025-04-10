
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

Sources:
* USF: https://usfca.instructure.com/courses/1627052/pages/multivariate-calculus-with-matrices-video-15?module_item_id=18611421
* Much clearer explanation of Jacobian: https://www.youtube.com/watch?v=AdV5w8CY3pw&t=4s

### The Derivative

Remember that the derivative is a "rate of change" .  The definition of a derivative is as follows:

Supose we have a function f(x) = y, and we want to find the derivative at a specific value x = a.  We usually denote this derivative equation as: 

$$\text{f'(a) = }\lim_{x \to a}\frac{\text{f(x)-f(a)}{\text{x - a}}$$ 

.  This is also sometimes written equivalently as:

$$\text{f'(x) = }\lim_{h \to 0}\frac{\text{f(x+h)-f(x)}{h}}$$ 

.  This equation finds the rate of change at a specific point x=a.  So if we have the function f(x) = y = $x^2$ , and we're looking for the derivative f'(x) at x = a.  

```
import matplotlib.pyplot as plt

# Define the coordinates of the two points
x1, x2 = -20, 20
y2, y2 = 0, 0

# Create a new figure and axis
fig, ax = plt.subplots()

# Turn off the subplot backdrop
ax.set_axis_off()

# Plot the line
ax.plot([x1, x2], [y1, y2], color='blue', linestyle='-', linewidth=2)
ax.plot([y1, y2], [x1, x2], color='red', linestyle='-', linewidth=2)

# Set axis limits
ax.set_xlim(min(x1, x2) - 1, max(x1, x2) + 1)
ax.set_ylim(min(x1, x2) - 1, max(x1, x2) + 1)

# plot x = y = x**2
x = range(-19, 19)
y = [i**2 for i in x]

plt.plot(x, y, color='black')

y3=3.5*5

# Add dots at 2 points
plt.plot(2, 4, marker='o', color='black')
plt.plot(3, 9, marker='o', color='black')

ax.plot([1.5, 4.5], [1, y3], color='orange', linestyle='-', linewidth=2)

# Apply Labels
ax.text(x2 + 0.1, 0, 'x', fontsize=12, color='blue')
ax.text(0, x2 + 0.3, 'y', fontsize=12, color='red')
ax.text(5, 19, 'x=x^2', fontsize=12, color='black')

# Show the plot
plt.show()
```

<img width="551" alt="Screenshot 2025-04-11 at 10 49 16" src="https://github.com/user-attachments/assets/85b56317-12ab-4e58-8895-38d640591e84" />

The orange line passes through 2 points on the equation line y = x^2.  You can see that the slope of the orange line approximates but does not match the slope of the equation line.  

What the above equation for the derivative says is that, as the distance between the 2 points converge (x --> a, or the distance h between them approaches 0), the slope of the equation line become equal to the slope of the line it approximates.  That is, it will become a tangent line at a = a.

Thus the derivative gives the slope of the tangent line (equivalently, of the equation) at any particular point.  There are some exceptions to this expectation -- e.g. the line must be continuous, and cannot be at a right angle.  

The slope from the derivative formula can also be thought of as a rate of change.  Thus, depending on the inputs x, the formula may yield a very steep or mild slope = rate of change.  This has consequences for analytic approaches like gradient descent, where the peak or valley will have a low rate of change.  

We can also think of the slope as a **local approximation** of f(x).  That is, the slope or tangent value given by the derivative formula will be almost equal to y as x approaches a.  Thus we can say that $\text{f(x)}\approx\text{f'(x)(x-a)+f(a)}$ .  In words, this is "f(x) approximately equals the slope you got from the derivative formula, times whatever little difference there is between x and a, plus whatever y value you have from f(a)".  Or: "y approximately equals your approximation of y using a, plus the slope times the difference between x and a".

We don't however use this formal limit formula to compute the derivative though.  Instead, we apply a battery of rules to the formula for f(x) = y, and these function as shortcuts to finding f'(x).  

Examples of the derivative shortcuts:
* polynomials: if we have $x^n\text = f(x0}$, we apply the rule $\text{f'(x) = }nx^{n-1}$ .
* addition: f(x) = g(x) + h(x); f'(x) = g'(x) + h'(x) .
* multiplication: f(x) = g(x)h(x); f'(x) = g'(x)h(x) + g(x)h'(x)
* the "chain rule": f(x) = g(h(x)); f'(x) = g'(h(x))*h'(x)

#### The Critical Point of a Derivative

The (or a) critical point of a function f(x) is any point x=a such that f'(a) = 0.  These are called "critical" because a slope of 0 marks a place where y is at a local min or max.  To find the critical point of a function, we:
* calculate the derivative formula
* set the formula = 0
* solve for x.  This will tell us the x value at which y is a local maximum.

### The Partial Derivative

When we take the partial derivative of a function having more than one input, e.g. $f\left(x_1,x_2\text{...}x_n\right)$, we take the derivative with respect to just one input variable $x_i$, while holding all other variables constant.  Each variable can be considered as a "direction", so that taking the derivative w.r.t variable indicates the direction in which that variable moves.

To illustrate this concept, we can consider the function z = f(x,y), which gives us a surface in 3-space :

```
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# Define the function z = f(x, y)
def f(x, y):
    return -np.sin(y)

# Create the data
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = f(X, Y)

# Create a 3D plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# Plot the surface
ax.plot_surface(X, Y, Z, cmap='viridis')

# Set axis labels
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z')

# Show the plot
plt.show()
```

<img width="443" alt="Screenshot 2025-04-11 at 11 59 33" src="https://github.com/user-attachments/assets/b0b6aa7d-e83c-44c4-a2d2-6f0a65cfe37e" />

Suppose we took the derivative of a particular point "a" with respect to x, then $\frac{\partial f}{\partial x}\left(a\right)$ will represent the slope of the tangent line at point a, in the x direction.  Similarly, $\frac{\partial f}{\partial y}\left(a\right)$ will represent the slope of the tangent line at point a, in the y direction.  In this particular picture/function, dx has a constant slope of 0 while dy may be 0, >0, <0 depending on the a selected.  

Considering the partial derivatives as slope scalars, in the context of linear algebra, we can think of them as multiplying basis vectors: 

$$\frac{\partial f}{\partial x}\left(a\right)\left[{\begin{array}{cc}
1 \\
0 \\
0 \\
\end{array} }\right]
\text{, and }
\frac{\partial f}{\partial y}\left(a\right)\left[{\begin{array}{cc}
0 \\
1 \\
0 \\
\end{array} }\right]
$$

.  In 3-space, 2 independent vectors multiplied in this way define a plane.  For the reasons discussed here, this plane must be tangent to the surface generated by f(x,y).  This exemplifies how vectors and matrices combined with partial derivatives can describe the linear space that is tangent to a higher order function.  This capability of describing lower dimension tangent space extends to any dimension.  

#### Partial Derivative Example 1:

Suppose we have the function f(x,y) 2xy + $x^2$ .

Then the partial derivatives of f w.r.t x and y are $\frac{\partial f}{\partial x}\text{ = 2y + 2x}\text{; }\frac{\partial f}{\partial y}\text{ = 2x}\rightarrow0\text{ (goes to 0 because no y expression)}$ .

### The Jacobian Matrix

Jacobian matrix functionality has 2 aspects or "sub functions":
* Columns in row space m are mapped to rows in column space n: $f\text{:}\mathbb{R}^m\rightarrow\mathbb{R}^n$ .

We can thus think of the Jacobian function as having n functions processing i...m values:
$f\left(f_1\left(x_1\text{,...,}x_m\right)\text{,}f_2\left(x_1\text{,...,}x_m\right)\text{,...,}f_n\left(x_1\text{,...,}x_m\right)\right)$ .  With this in mind we can imagine taking partial derivatives of f1, f2 ... up to fn.  All such partial derivatives could be arranged in a matrix.  This matrix is called **the Jacobian** .

#### Notes on Jacobian Explanation

* A major contextual point about the Jacobian is that you're using it in situations where a vector of variables is being mapped to a vector of functions, each of which [I believe] must use all the variables (for reasons of matrix multiplication).  This wasn't super clear to me at first.  Anyway, that is why, if you have for example a vector of 2 variables, and a vector of 2 functions, you're going to end up with a 2x2 matrix of partial derivatives.
* Note that a vector of variables might also be mapped to a single function which uses all the variables.  --I think that is a typical case in the context of neural networks, where at the end all the inputs and their respective weights are reduced to a single function.  

#### Jacobian Matrix Definition

The Jacobian of a function f is given by the following matrix:

$$
\left[
  \begin{matrix}
  \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & {...} & \frac{\partial f_1}{\partial x_m}\\
  \frac{\partial f_2}{\partial x_1} & {...} & {...} & \frac{\partial f_2}{\partial x_m}\\
  \vdots & {...} & {...} & {...}\\
  \frac{\partial f_n}{\partial x_1} & {...} & {...} & \frac{\partial f_n}{\partial x_m}\\
  \end{matrix}
\right]
\text{ = }J_f
\text{ = }\left(\frac{\partial f_i}{\partial x_j}\right)_{ij}
$$ 

What this matrix stores or maps out is a multivariate version of a derivative.  When we have a function going from 1 d space to 1 d space, we have only one derivative.  But when we ahve many different outputs annd inputs, the matrix for collecting them is this Jacobean format.  It is in effect a derivative in an arbitrarily high dimension space.

As with the plane example in 3d above, this derivative gives us a local approximation of our function.  But now, with its Jacobean arrangement allows us to do matrix multiplication.  So for example f(x) around a particular point p will be approximately the Jacobean of p, that is: $f\left(x\right)\approxJ_f\left(p\right)\left(\v{x}-\v{p}\right)\text{ + }f\left(p\right)$ .

#### Jacobian Matrix Example

Suppose we have a function that maps x and y to two new values, using two "coordinate" functions:

$$
f\left(\left[{\begin{array}{cc}
x \\
y \\
\end{array} }\right]\right)
\text{ = }
\left[{\begin{array}{cc}
x^2y+2x \\
y^3+2xy \\
\end{array} }\right]
$$

To take the Jacobean of this function, we follow the mapping plan shown above.  The first row will be partials with respect to the first function, and the second row will be partials with respect to the second function.  As we move from left to right across the row, we will first take the derivative w.r.t. x, then w.r.t y.

Thus the Jacobean for this case:

$$
f(x,y)
\text{ = }
\left[{\begin{array}{cc}
{2xy\text{ + }2} & x^2 \\
2y & {3y^2\text{ + }2x} \\
\end{array} }\right]
$$

.  If we then want to look at a particular point described by (x,y) vector v1, say **$v_1$** = (1,2), the new approximate point result is given by plugging these values into the Jacobean.

In this case:

$$
J_{f}\left({1,2}\right)
\text{ = }
\left[{\begin{array}{cc}
{2xy\text{ + }2} & x^2 \\
2y & {3y^2\text{ + }2x} \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}{cc}
{2\*1\*2+2} & {1^2} \\
{2*2} & {3\*2^2+2x} \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}{cc}
6 & 7 \\
4 & 14 \\
\end{array} }\right]
$$

The final output matrix of numbers represents the slope of the overall approximation of the function f(x,y) at the point (1,2).  




## Gradient Descent

## Linear Regression

## Orthonormality

## Projection Matrices

## Positive Semidefinite Matrices

## Singular Value Decomposition
