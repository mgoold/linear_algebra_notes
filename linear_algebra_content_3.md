
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
* Clearer explantion of meaning of Jacobian output: https://www.youtube.com/watch?v=bohL918kXQk
* Good video on relation of linear map to Jacobian, especially illustrating conventions of ordering from inputs to Jacobian derivative ordering.

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

* A major contextual point about the Jacobian is that you're using it in situations where a vector of input variables is being mapped to a vector of functions that give outputs.  The vectors need not be of equal length.  For example, inputs x and y could be mapped to a vector of 3 functions that each use x and y.  However, not every output function needs to use every input function.  When creating the Jacobian though, the derivative must be calculated for every input variable against every function.  Two things follow from these rules:
 * The Jacobian need not be square, but it being a matrix it must be rectangular.
   * If you have for example a vector of 2 variables, and a vector of 2 functions, you're going to end up with a **2x2** matrix of partial derivatives.  When I started learning about Jacobians, I anticipated that a set of 2 functions with 2 variables would for example be broken into a 2x2 matrix, that would act on a 2x1 input matrix and yield a 2x1 output matrix.  That's totally wrong.
 * It is possible to have 0s in the Jacobian, if the derivative w.r.t. an input variable is taken for a function that does not use it.  
* Note that a vector of variables might also be mapped to a **single function** which uses all the variables.  --I think that is a typical case in the context of neural networks, where at the end stage of calculations all the inputs and their respective weights are reduced to a single function that yields a single number.

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

**Notes on this explanation.**

What the Jacobian actually is, for a given point or vector of input values, is a grid of the changes to the output of each function that is effected by a tiny change with respect to each input variable (that is df1/dx1, df1/dx2, etc).  It is in this sense that the grid represents a "slope", although for a large grid of functions and dimensions the notion of a slope would quickly become obsure. 

* The map of changes across a single row of the Jacobian contains a single function's change  with respect to a change in each of its successive variables.  This makes straightforward, by-definition sense.
* On the other hand, I got stuck on **why** it should be that the first number in $J_11$ should correspond to change in x for a change in x, $J_21$ must correspond to change in y for a change in x, and so on.  What was the source of logical necessity that drives this ordering and makes it reliable?
 * The answer is one of those things that are so basic that people smarter than me don't even mention it, and assume that you'll understand the implicit step.  Consider this input-to-output example:

  $$f\left(x,y\right\text{ = }\left(f_1\left(x,y\right),f_2\left(x,y\right)\right)\text{ = }\left(x^2\text{ - }y^2,3xy\right)$$

  In this example, we would understand by convention that the input x maps to the output of f1, and y maps to the output of f2.  That is, f1 is what x becomes, and f2 is what y becomes.  Extending this custom to the conventions of linear algebra, when calculate a Jacobian (and I assume, do other similar operations), the output functions are translated from the above left-to-right presentation to a top-to-bottom ordered column, to facilitate creating the partial derivatives matrix.  This custom is the only reason why we can rely on $J_11$ to apply to change in x w.r.t. x, $J_21$ to apply to change in y w.r.t. x, etc.  

#### Jacobian Matrices: Connection to Other Concepts

**Critical Points**

In the context of the Jacobian, a point is a critical point if the rank of the Jacobian is not maximal (r<n).  For example, we had a 2x2 matrix in the above example.  If there are point values (x,y) that yield a result matrix with a rank of 1 or 0 (<2), these will be critical points for the function.  Obviously, the 0 vector for variables is one example.  But in the above example, having 0 in x or y would have done it as well.  

#### Jacobian Matrices: Additional Properties

* for square Jacobian matrices, full rank implies invertibility of the function f.  If the matrix is invertible, then the function is also invertible (locally).
* crucially, **a series of Jacobians can be multiplied by each other** to yield a final output.  This matters in the context of neural networks, where each Jacobian represents a phase in the network's learning process, and the question is how a set of initial inputs, having an impact across successive phases, impacts the final prediction.  

## Gradient Descent

### Sources
* USF: https://usfca.instructure.com/courses/1627052/pages/gradient-descent-video-16?module_item_id=18611423
* Rundowns on why gradients are fastest route of ascent|descent:
 * https://www.youtube.com/watch?v=_ZFiDtXOGhc
 * https://www.youtube.com/watch?v=QQPz3eXXgQI&t=144s
* Brief intro to parametric curves: https://www.youtube.com/watch?v=bb4bSCjlFAw

**Gradient Notation**

Gradients apply to a class of functions which take multiple outputs and output a single value.  A gradient function looks like : $f\left(x_1,x_2,x_3\text{,...,}x_n\right)$ .  We can collect all the partials of f in a column vector.  The gradient of f at point $left(a_1\text{,...,}a_n2\right)$ is then:

$$
\nabla{f\left(a\right)}\text{ = }
\left[{\begin{array}{cc}
\frac{\partial f}{\partial x_1}\left(a\right) \\
\frac{\partial f}{\partial x_2}\left(a\right) \\
\vdots \\
\frac{\partial f}{\partial x_n}\left(a\right) \\
\end{array} }\right]

--In this notation, the partial derivative and the point value that is plugged into it are combined into a single component.  Remember that there is just one function, so all the components down the column are denoted with just "df" instead of "df1...dfn".  The derivative is taken of the same function over and over, but w.r.t. a different, successive input variable.  In this sense, I believe this column down is what would normally be the first row in an mxn Jacobian matrix, where m>1.   --In fact, the instructor goes on to say that we can think of this as the transpose $\left(J^{T}_f\right)$ for f.  The whole resultant vector is called the "gradient vector".

Along with the derivative being given, I believe the notation means that the corresponding point value is plugged into it and the whole component being calculated. 

### Excursus: Meaning of the Gradient of a Function

The meaning of the gradient is that it is a vector on the tangent plane to a function "surface" showing the direction of fastest increase of that function.  OK.  **Why is it in the direction of the fastest rate of increase?** It turns out the answer is one of those "by definition things" where, when you understand how the gradient is positioned, it has to point in the "fastest rate change direction".  The shortest answer is that it always points "straight up|down the hill".  The detailed explantion breaks into several parts:

#### Remember What the Chain Rule Is

Formally, the chain rule is $\frac{d}{dx}\left[f\left(g\left(gleft(x\right)\right)\right]\text{ = }f'\left(g\left(gleft(x\right)\right)g'\left(x\right)$ .

This says that the derivative of a nested function with respect to variable in the inner function is the derivative of the outer function, times the derivative of the inner function with respect to x.  Since this is multiplication, the order doesn't matter, so some descriptions reverse which derivativ is taken first.

For example:

$f\left(x\right)\text{ = }\left(2x\text{ + }3\right)^5)\text{; }f'\left(x\right)\text{ = }\left(5\left(2x\text{ + }3\right)-4\right)\*2\right)\text{=}10\left(2x+3\right)^4\right)$ .

#### Dot Product Angles

Remember that for 2 vectors, a 0 dot product means that they are "orthogonal" (at a right angle) to each other.   This is so because the dot product is also equal to the product of the lengths of the vectors times the cosine of the angle between them.  But when the angle between them is 90 degrees, the cosine will  = 0, and so $\overrightarrow{a}\cdot\overrightarrow{b}\text{ = }\|\overrightarrow{a}\|\|\overrightarrow{b}\|\left(0\right)\text{ = }0$.

#### Understanding Level Curves

Imagine that you had a simple slope such as a parabolic d3 space.  Imagine this is intersected by a plane parallel to the xy plane, so that the intersection with the slope will form a line that everywhere has a constant height z = k, as pictured here:

![Screenshot 2025-04-14 at 16 33 21](https://github.com/user-attachments/assets/bdeee70b-06d3-4603-90c8-fed31368053d)

You can think of the function for this constant line in a parametrized format, where a vector of value for t is consumed by a function that uses them in 2 separate functions to yield pairs of x and y coordinates for each value t.  That is: 

$$\Large{\overrightarrow{r}\left(t\right)\text{ = }x\left(t\right)\hat{i}\text{ + }y\left(t\right)\hat{j}}$$ 

such that f(x(t),y(t)) = k.  

In case it's not clear, this is saying that the f(x(t),y(t)) consumes the x,y pairs given by the parameterized function $\overrightarrow{r}\left(t\right)\$ .  In other words, 

$$\Large{\overrightarrow{r}\left(t\right)\}$$ 

is nested in f();  

$$\Large{f\left(\overrightarrow{r}\left(t\right)\right)\text{ = }C}$$ .

This nested arrangement puts us in place to take the derivative of this function via the chain rule.  When we do, we get a result like:

$$\Large{\frac{\partial{f}}{\partial{x}}\frac{dx}{dt}\text{ + }\frac{\partial{f}}{\partial{y}}\frac{dy}{dt}}$$ .  

With some consideration, you can see that this could be considered as the result of taking a dot product of two vectors, which would have been multiplied like so:

$$\Large{\left(\frac{\partial{f}}{\partial{x}}\hat{i},\frac{\partial{f}}{\partial{y}}\hat{j}\right)\cdot\left(\frac{dx}{dt}\hat{i},\frac{dy}{dt}\hat{j}\right)\text{ = }0}$$ .

In this formulation, we know that since the dot product is = 0, the two vectors must be orthoganal to each other.

#### A Gradient $\cdot$ Level Curve Dot Product is 0, So.

The final step is to consider the first vector in the dot product: $\Large{\left(\frac{\partial{f}}{\partial{x}}\hat{i},\frac{\partial{f}}{\partial{y}}\hat{j}\right)}$ .  You can see that this is a set of partial derivatives breaking down the output of function f in terms of its x and y directional components.  This is exactly the definition of the gradient of f.  The second vector is a tangent to the level line, which we have said is parallel to the x,y plane, and consequently the tangent is parallel to the x,y plane while also intersecting the slope at a constant height.

The formula can thus be given a final short form as:

$$\Large{\nabla{f}\cdot\frac{d\overrightarrow{r}}{dt}\text{ = }0}$$

Consequently, since the gradient itself is perpendicular to the tangent line, and is at its point on the slope, it must point straight "uphill" in the direction of greatest ascent|descent (change).  In fact, it is not actually on the slope, but it meets that tangent line at the corresponding point in the x,y plane.  

**Additional Note** the negative or positive value of the gradient tells you whether the gradient is pointing "uphill or downhill".  In gradient descent algorithms, it is typical to pursue the negative values, since these are associated with minima, which in turn are associated with error minimization.

A 0 gradient corresponds to a critical point, or "local peak/valley" on a surface.  Remember that for a Jacobian, a non-maximal rank corresponds to a critical point, so in the context of a gradient this critical point (non-maximal rank) will be a vector of 0s.  

### Gradient Descent Recursive Algorithm

When gradient descent is used to minimize error/approximate a value in machine learning, the gradient is calculated many times in such a way that as the gradient values get progressively smaller, the algorithm slows down and quits so as not to overshoot the peak or valley. 

Formally, this approache looks like this recursive formula:

$$\Large{a_N\text{ = }a_{N-1}-\gamma\nablaf\left(a_{N-1}right\)}$$

In words, this is "The gradient at point N equals the gradient at the previous point - gamma * gradient at previous point..." .  Where gamma is the "step size", or  scaling parameter that can adjust the impact of learning thus farm, since a given gradient can be large.  This is also called the "learning rate".


## Linear Regression

* Linear regression as matrix operation.
* Use of dot products.
* How is error minimized?  By finding critical point, where all partial derivatives are equal to 0.
* Use of TSS summation equation --> translate to matrix presentation.
* Starting at about 15.00
* The derivative of a summation is the summation of the derivatives.
* Application of chain rule, to obtain gradient of summation with respect to each beta.
* Remember that a gradient is just one column, i.e. "the first row of a Jacobian" transposed.  So just expect one column of partials.
* Understand the "2xT" thing at 17.44.

## Orthogonality and Gram-Schmidt

### Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/lecture-17-orthogonal-matrices-and-gram-schmidt/
* [Graham Schmidt](https://www.linkedin.com/in/graham-schmidt-bb42543a?trk=people-guest_people_search-card)

Note that we will use the letter Q to indicate orthogonal matrices.

An orthonormal matrix need not be square.

### Motivation

The reason to make vectors orthonormal is it makes computation with them much easier.  I suppose that then you have to change them back via some reverse process, at the end of your calculations.

### Orthogonality and Projection Matrices

A projection matrix P equals a multiplication of 4 orthogonal matrices:

$$\Large{P\text{ = }Q\left(Q^TQ\right)^{-1}Q^T}\text{ = }QQ^T\left(\text{ = I if Q is square}\right)$$

**...this is true when we have an orthonormal basis for in the column space.**

What makes this equation nice is that $\left(Q^TQ\right)^{-1}$ is the identity I .  Thus we don't need to do any inversion.  This means that a projection matrices ends up being simply $P=QQ^T$ 

Remember the properties of a projection matrix:
* a projection matrix is symmetric.  A square matrix Q is certainly symmetric.
* if you apply a projection matrix 2x, the second application will not have an effect.  Therefore, $\left(QQ^T\right)\left(QQ^T\right)\text{ = }\left(QQ^T\right)$ .  You can see this right away, since 
* This property should fall out right away, since $QQ^T\left(\text{ = I if Q is square}\right)$ .  In fact you can see $QQ^T$ in the middle of this identity, so it's clear that $\left(QQ^T\right)\left(QQ^T\right)\text{ = }\left(QQ^T\right)$ becomes $\left(QIQ^T\right)\text{ = }\left(QQ^T\right)$

Suppose the matrix Q is square.  Then if the square matrix is full rank, and the columns are all orthonormal, then they span the full space of C(A). The projection matrix onto this whole space will then be the identity matrix (i.o.i. Q is square).  

### The Orthonormal Basis

Most of the difficulty in our matrix equations is eliminated when dealing with matrices that have an orthonormal basis.  Several examples of this resolution are given below.

#### The "Normal" Equation

Remember the normal equation: $A^TA\hat{x}\text{ = }A^Tb$ .  In an orthonormal setting, A is replaced by Q: $Q^TQ\hat{x}\text{ = }Q^Tb$ .  This reduces to $\hat{x}\text{ = }Q^Tb$, since the left side becomes $I\hat{x}$ .  What this equation is saying is that the ith component of x, $\hat{x}_i\$, is equal to the i-th basis vector times b.  This is one of the most important identities in some areas of math, as it states that if we have an orthonormal basis, then the projection on the ith basis vector is just $q^T_ib$ .  In other words, this number x we're seeking is just a dot product.  

### Gram-Schmidt: Making Independent Vectors Orthonormal

With the G-S approach, the goal is to make the columns of a matrix orthonormal.  Since it involves row manipulation, it may feel like the RREF process, but the goal is different.

We begin with vectors a and b. They might be in a space of any number of dimensions.  What matters is that they are independent of each other.  The goal is to produce orthonormal vectors A and B out of them.  Then it is easy to get orthonormal vectors q1 and q2 from that.

With 2 vectors, we only need to make the second, "B" orthogonal to the first.  So there's kind of an "n-1" thing with the vectors that you have.

With this in mind, we consider b as projecting on a in one "x" dimension.  We then need to find the "y" dimension.  But in fact this missing y dimension IS the orthogonal vector B that we're seeking.  

Considering b as a projection on a, we say that orthogonal vector B = b - its projection on A.  This is soft of obvious, since b's projection on a, and B, would make the non-hypotenuse legs of a right triangle to which b would be the hypotenuse.  We know that B won't be zero, because we stipulated that the vectors were independent of each other.

The linear algebra approach (this is G-S's contribution) to subtracing the projection from b is: $\large{B\text{ = }b\text{ - }\frac{A^Tb}{A^TA}A}$ .  The result will give us B perp to A.  How would we know/check that this is true?  Of course, we know that the dot product of perpendicular vectors = 0, so we can take multiply B by $A^T$ and get 0 to check.

**I don't understand why it has to be A transpose.** However, checking that  $A^TB\text{ = }0$ formulaically does show that it needs to be $A^T$ :

$$\large{A^TB\text{ = }A^T\left(b\text{ - }\frac{A^Tb}{A^TA}A\right)\text{ = }0}$$ 

.  You can see that multiplying the right side would give you $frac{A^TA}{A^TA}$, which would cancel and leave you with $A^Tb\text{ - }A^Tb$ , which indeed is 0.

### Gram-Schmidt with 3 Vectors

Suppose we have 3 independent vectors a,b,c.  What does making them into orthogonal vectors A,B,C look like?

The first 2 steps look the same: take A as-is, and use G-S to find B as we did above.  

Finding C is analogous, in that we subtract something from c: C = c - $\frac{A^Tc}{A^TA}A$ - $\frac{B^Tc}{B^TB}B$  .  This strips away the A and B components from an independent vector c, leaving only B. To imagine this geometrically, you can imagine 3 independent vectors in 3 space, in which vectors a and b are in the positive quadrant of the x, y plane.  Then imagine the positive quandrant of x,y,z , extending above the x,y plane.  You can see that from its end point would drop a line to the x,y plane.  This would be the short leg C of a right triangle, where c is the hypotenuse.  When the x and y contributions to c's position were subtracted, vector c would be left extending up the z axis from the origin, orthogonal to x and y.  (This assumes you've already done G-S on the other 2 vectors).

### Gram-Schmidt with Real Numbers

Suppose we have the vectors 

$$
a\text{ = }
\left[{\begin{array}{cc}
1 \\
1 \\
1 \\
\end{array} }\right]
\text{,  b = }
\left[{\begin{array}{cc}
1 \\
0 \\
2 \\
\end{array} }\right]
$$

Again, we take A as is.  

Note that $A^Tb$ = 3, and $A^TA$ = 3 .

B is then 

$$
B\text{ = }
\left[{\begin{array}{cc}
1 \\
0 \\
2 \\
\end{array} }\right]
\text{ - }\frac{3}{3}
\left[{\begin{array}{cc}
1 \\
1 \\
1 \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}{cc}
0 \\
-1 \\
1 \\
\end{array} }\right]
$$

q1 and q2, the orthonormal forms of A and B, is then just the vectors divided by their respective lengths.  Remember that the length is the square root of the dot product of a vector with itself.  So each vector A, B, will have each of its respective component divided by this length, and that will be q1 and q2.

Note that these orthonormal vectors, as modifications of the original vectors, will remain in the same column space as the original ones.  It's just that they've been optimized for calculations.

### Gram-Schmidt Considered in Matrix Terms

Just as the result of row elimination could be considered in LU matrix terms, G-S can be considered in matrix terms.

By convention, people don't write out the G-S transformations.  Rather they say that "A=QR", as a way of saying that the matrix A's vectors can be put into orthonormal relations.

## Projection Matrices

## Positive Semidefinite Matrices

## Singular Value Decomposition
