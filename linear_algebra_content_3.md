
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
{\begin{array}
2 & 4 \\
1 & 2 \\
\end{array} } 
\right]
$$

, and we want to find the nullity of A.  We can begin this process by doing RREF on A, which leaves us with:

$$
A\text{ = }
\left[
{\begin{array}
1 & 2 \\
0 & 0 \\
\end{array} } 
\right]
$$

Which means that N(A) will be 

$$
N(A)\text{ = c}
\left[
{\begin{array}
-2 \\
1 \\
\end{array} } 
\right]
\text{, }
N(A)\text{ = c}
\left[
{\begin{array}
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

$$\text{f'(a) = }\lim_{x \to a}\frac{\text{f(x) - f(a)}}{\text{x - a}}$$ 

.  This is also sometimes written equivalently as:

$$\text{f'(x) = }\lim_{h \to 0}\frac{\text{f(x + h)-f(x)}}{h}$$ 

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

$$\frac{\partial f}{\partial x}\left(a\right)\left[{\begin{array}
1 \\
0 \\
0 \\
\end{array} }\right]
\text{, and }
\frac{\partial f}{\partial y}\left(a\right)\left[{\begin{array}
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

As with the plane example in 3d above, this derivative gives us a local approximation of our function.  But now, with its Jacobean arrangement allows us to do matrix multiplication.  So for example f(x) around a particular point p will be approximately the Jacobean of p, that is: $f\left(x\right)\approx{J_f}\left(p\right)\left(\overrightarrow{x}-\overrightarrow{p}\right)\text{ + }f\left(p\right)$ .

#### Jacobian Matrix Example

Suppose we have a function that maps x and y to two new values, using two "coordinate" functions:

$$
f\left(
\left[
{\begin{array}
x \\
y \\
\end{array}}
\right]
\right)
\text{ = }
\left[
{\begin{array}
x^2y+2x \\
y^3+2xy \\
\end{array}}
\right]
$$

To take the Jacobean of this function, we follow the mapping plan shown above.  The first row will be partials with respect to the first function, and the second row will be partials with respect to the second function.  As we move from left to right across the row, we will first take the derivative w.r.t. x, then w.r.t y.

Thus the Jacobean for this case:

$$
f(x,y)
\text{ = }
\left[{\begin{array}
{2xy\text{ + }2} & x^2 \\
2y & {3y^2\text{ + }2x} \\
\end{array} }\right]
$$

.  If we then want to look at a particular point described by (x,y) vector v1, say **$v_1$** = (1,2), the new approximate point result is given by plugging these values into the Jacobean.

In this case:

$$
J_{f}\left({1,2}\right)
\text{ = }
\left[{\begin{array}
{2xy\text{ + }2} & x^2 \\
2y & {3y^2\text{ + }2x} \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}
{2\*1\*2+2} & {1^2} \\
{2*2} & {3\*2^2+2x} \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}
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

  $$f\left(x,y\right)\text{ = }\left(f_1\left(x,y\right),f_2\left(x,y\right)\right)\text{ = }\left(x^2\text{ - }y^2,3xy\right)$$

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

Gradients **apply to** a class of functions which take multiple inputs and combine them into a function that yields a single value.  A real example of such a function is $f\left(x,y\right)\text{ = }3x^2\text{ + }y^2$ .  A gradient is a collection of partial derivatives of such functions.  We can collect all the partials of the function in a column vector.  The gradient of f() at point a where the input variables are $x_1,...x_n$ and the value at a point a for the "coordinate" inputs of these variables is $\left(a_{1}\text{,...,}a_{n}\right)$ is then:

$$
\nabla{f\left(a\right)}\text{ = }
\left[
{\begin{array}
\frac{\partial f}{\partial x_1}\left(a\right) \\
\frac{\partial f}{\partial x_2}\left(a\right) \\
\vdots \\
\frac{\partial f}{\partial x_n}\left(a\right) \\
\end{array}}
\right]
$$

--In this notation, the partial derivative and the point value that is plugged into it are combined into a single component.  Remember that there is just one function, so all the components down the column are denoted with just "df" instead of "df1...dfn".  The derivative is taken of the same function over and over, but w.r.t. a different, successive input variable.  In this sense, I believe this column down is what would normally be the first row in an mxn Jacobian matrix, where m>1.   --In fact, the instructor goes on to say that we can think of this as the transpose $\left(J^{T}_f\right)$ for f.  The whole resultant vector is called the "gradient vector".

### Simple Example of Gradient Descent

Suppose our function takes to inputs, x and y, and combines them in an output function $f\left(x_1,x_2\right)\text{ = }3{x_1}^2\text{ + }{x_2}^2$ .  Then the gradient consists of taking partial derivatives with respect to $x_1$, then $x_2$.  The gradient would then be:

$$
\nabla{f}\left(x\right)\text{ = }
\left[
{\begin{array}
\frac{\partial f}{\partial x_1}\text{ = }6x_1 \\
\frac{\partial f}{\partial x_2}\text{ = }2x_2 \\
\end{array}}
\right]
$$

At a point a = (1,2), the gradient would thus be (6,2).

### Excursus: Meaning of the Gradient of a Function

The meaning of the gradient is that it is a vector on the tangent plane to a function "surface" showing the direction of fastest increase of that function.  OK.  **Why is it in the direction of the fastest rate of increase?** It turns out the answer is one of those "by definition things" where, when you understand how the gradient is positioned, it has to point in the "fastest rate change direction".  The shortest answer is that it always points "straight up|down the hill".  The detailed explantion breaks into several parts:

#### Remember What the Chain Rule Is

Formally, the chain rule is 

$$
\frac{d}{dx}
\left[
  f\left(
    g
    \left(
     x
    \right)
  \right)
\right]
\text{ = }
f'\left(g\left(x\right)\right)g'\left(x\right)
$$   

This says that the derivative of a nested function with respect to a variable x in the inner function is the derivative of the outer function, times the derivative of the inner function with respect to x.  Since this is multiplication, the order doesn't matter, so some descriptions reverse which derivative is taken first.

For example: $\frac{d}{dx}\left(5x\text{ + }3\right)^4\text{ = }4\left(5x\text{ + }3\right)^3\left(5\right)$ .

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

$$\Large{a_N\text{ = }a_{N-1}\text{ - }\gamma\nabla{f}\left(a_{N-1}\right)}$$

In words, this is "The gradient at point N equals the gradient at the previous point - gamma * gradient at previous point..." .  Where gamma is the "step size", or  scaling parameter that can adjust the impact of learning thus farm, since a given gradient can be large.  This is also called the "learning rate".

#### Gradient Descent Recursion Example

Suppose again our function takes to inputs, x and y, and combines them in an output function $f\left(x_1,x_2\right)\text{ = }3{x_1}^2\text{ + }{x_2}^2$ . Also suppose that we are beginning our recursion at point (1,1), and that the $\gamma$ step size is .01.  Then the gradient consists of taking partial derivatives with respect to $x_1$, then $x_2$.  The gradient would then be:

$$
\nabla{f}\left(x\right)\text{ = }
\left[
{\begin{array}
\frac{\partial f}{\partial x_1}\text{ = }6x_1 \\
\frac{\partial f}{\partial x_2}\text{ = }2x_2 \\
\end{array}}
\right]
$$

And the initial gradient is 

$$
\nabla{f}\left(x\right)\text{ = }
\left[
{\begin{array}
6 \\
2 \\
\end{array}}
\right]
$$

.  In the first step, we subtract gamma times this gradient from the inital point:

$$
a_1\text{ = }
\left[
{\begin{array}
1 \\
1 \\
\end{array}}
\right]
\text{ - }
.01
\left[
{\begin{array}
6 \\
2 \\
\end{array}}
\right]
\text{ = }
\left[
{\begin{array}
.4 \\
.8 \\
\end{array}}
\right]
$$

.  Repeating this step gives us:

$$
a_1\text{ = }
\left[
{\begin{array}
.4 \\
.8 \\
\end{array}}
\right]
\text{ - }
.01
\left[
{\begin{array}
6(.4) = 2.4 \\
2(.8) = 1.6 \\
\end{array}}
\right]
\text{ = }
\left[
{\begin{array}
.16 \\
.64 \\
\end{array}}
\right]
$$

. **NOTICE THAT:** 
* at each step, the coordinate values of the new resultant point after gamma times the gradient ( $\gamma\nabla{f}\left(a_{N-1}\right)$ ) has been subtracted from it, is plugged back into the gradient.  This is the recursive part.
* the values of the gradient diminish toward 0.  This zero "point" is what we're seeking, since it marks a minimum point for prediction error.
* the starting point (1,1) was randomly chosen.  The rationale by which you would pick a point is not clear to me.   I believe in real life the gradient descent function seeds several such points and runs the gradient procedure on multiple simultaneous "threads" in order to save time.
* the functionality that slows or stops the recursion before the desired 0 gradient is "overrun" or "missed" is external to the formula itself.


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

## Orthogonal Vectors and Subspaces

### Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/least-squares-determinants-and-eigenvalues/orthogonal-vectors-and-subspaces/

### Vectors and Orthogonality

To be orthogonal means that, in n-dimensional space, the angle between two vectors is 90 degrees.  Remember that for 2 orthogonal vectors, their sum will be the hypotenuse.  

Remember that the test for orthogonality of 2 vectors is that their dot product is 0.  For some reason, Strang favors denoting the dot product as $x^Ty$, perhaps because it more straightforwardly implies the multiplication and summation that is to be done than the "dot" does.   Anyway, $x^Ty$ is the same thing as $x\cdot{y}$ and if the result is 0, then x and y are $\perp$ .

Why is it the case that $x^Ty\text{ = }0$ then the vectors are orthognal? 

We know that ${\|\|x\|\|}^2\text{ + }{\|\|y\|\|}^2\text{ = }{\|\|{x + y}\|\|}^2$ .  This is only true when the vectors x and y are orthogonal to each other.   

Consider what length *is* .  What is length squared?  If we consider the vector:

$$
x\text{ = }
\left[{\begin{array}
1 \\
2 \\
3 \\
\end{array} }\right]
$$

the dot product is sqrt(1 + 4 + 9) = sqrt(14), so the length squared is 14.  This is also the same thing as saying that the length squared is $x^Tx$ .  Suppose now we have 2 orthogonal vectors:

$$
x\text{ = }
\left[{\begin{array}
1 \\
2 \\
3 \\
\end{array} }\right]
\text{,  }x\text{y = }
\left[{\begin{array}
2 \\
-1 \\
0 \\
\end{array} }\right]
$$

The (length of y) squared is then 4 + 1 + 0 = 5 .  And the (length of x + y) squared is then (3+1, 2+-1, 3+0) squared --> 4 + 1 + 9 = 19 .  And indeed 14 + 5 = 19.  **But also you can theck the orthogonality of 2 vectors by just the sum of their respective component products, which will sum to 0 if they are orthogonal.**  

So far we've just checked that the Pythagorean theorem applies.  We haven't actually proven anything.  

If we do the above process in notation, we get: $x^Tx\text{ + }y^Ty\text{ = }\left({x + y}\right)^T\left({x + y}\right)$  .  Again, remember that this is only true when the vectors are orthognal. 

On the right side of this equation, we can simplify $\left({x + y}\right)^T\left({x + y}\right)\rightarrowx^Tx\text{ + }y^Ty\text{ + }x^Ty\text{ + }y^Tx$ .  Then on both sides of the equation, we can cancel $x^Tx$ and $y^Ty$.  Having done this, we can notice that there is no difference between $x^Ty\text{ and }y^Tx$ , so long as both vectors are real.  Thus we can say that they sum to $2x^Ty$ .  

So in the end, the whole equation for lengths equalling the hypotenuse boiled down to:

$$2x^Ty\text{ = }0$$ .  We can of course cancel the 2, so we are left with $x^Ty\text{ = }0$ , which confirms the proof w.r.t. for $\perp$ vectors, and incidentally the Pythagorean treatment of lengths above.

What if one of the vectors is the 0 vector?  --They are still orthogonal.  **In fact, the 0 vector is orthogonal to all vectors.**

### Subspaces and Orthogonality

This linear algebra course sometimes features a picture of four 4 rectangles, each representing a sub-space, in relation to each other.  The picture finally makes sense in the context of orthogonality: the picture's only point is that the rowspace R(A) is orthogonal to the nullspace N(A), and the column space C(A) is orthogonal to the "left nullspace" of $N\left(A^T\right)$ .

Reviewing the dimensions of each sub-space, we know that they are as follows:

|Subspace|Dimension|
| :---: | :---: |
| R(A) | r |
| N(A) | n-r |
| C(A) | r |
| $N\left(A^T\right)$ | m-r |

Focusing on the "point" or "angle" where these pairs of subspaces (R(A) : N(A), C(A) : $N\left(A^T\right)$ ) meet, we can deal with what it means to say they're orthogonal.  It is critical to understand this in order further understand these subspaces.

A subspace S is orthogonal to subspace T when every vector in S is to every vector in T.  To understand this, it helps to distinguish linear systems or representations of subspace from corresponding pictures.  2 planes intersecting at a right angle (say, a wall and the floor) would **not** be orthogonal, because vectors in those planess could go off at 40 degs and 35 degs respectively.  These would not be orthogonal.  What would be orthogonal would be a linear system such that one plane consists of all vertical vectors, and the other of all horizontal vectors, defined in such a way that they are at right angles to each other.  Note that the intersection line would be excluded from such orthogonal planes as it extends in a direction that is orthogonal to them both. **In fact, if 2 subspaces intersect at some vector, they will by definition be non-orthogonal, since they include that non-orthogonal vector** --The only exception to this stipulation is the 0 vector.  

Non-intersection is not sufficient for non-orthogonality.  Obviously, 2 planes could be parallel, and non-orthogonal.  

In the context of a plane, a line through the origin will never be orthogonal to that whole plane.  [I don't actually see why this is true.]  
A line through the origin is always orthogonal to the zero subspace.
A line through the origin is only orthogonal to another line through the origin if they meet at 90 degrees.

These things are also true for R(A) and N(A).

### R(A) and N(A) Orthogonality

N(A) contains the vectors in x that solve Ax = 0.  So when x is in the nullspace, Ax = 0.  But why is N(A) orthogonal to the rows of A?  If we just write out Ax = 0, and think about it, you can see that based on what we know about 2 vectors having a 0 dot product when they are orthogonal, and the fact that x is kind of a column vector, then you can imagine that the rows of A would have to be like transposed columns that yield a 0 dot product with x.  

This draws attention to something you might not normally consider: that to have A multiply x yields a "b column" of dot products -- in this case, 0.

Beyond this self-evident appearance of orthogonality, we must also show that x is orthogonal to *every* vector in the rowspace, including the any combinations of those rows.  --To see that this is also true, start by considering that row already has a relation to the x's in N(A) such that the dot product is 0.  --This is a result not just of the values in x of N(A) but also the inner mathematical relationship of the components in the row.  --But this means that if you multiply the row by any scalar, every component will be multiplied in the same way, and therefore the inner relationship will not be changed.  Therefore, its dot product with x will be unchanged and still equal 0 .

One additional point: 

Suppose we are in R3 dimensions, and we have two lines that are perpendicular to each other.  They each constitute a trivial subspace.  However, they cannot constitute a rowspace and nullspace that are orthogonal to each other.  The reason is that the dimension relationships of R(A) and N(A) are r and n-r respectively, and these should add up to 3 in this case, but they only fill 2 dimensions.

This highlights another property of orthogonality.  In a given specified space, say R3, the two subspaces that are orthogonal **must be complements to each other**  .  Here, orthogonal complements means that they fill out the full specified space.  So if you're in R3, and the matrix R(A) describes a line after RR (r=1), the dimension of N(A) must be n-r = 2 since it is in 3 space.


### C(A) and Left Nullspace Orthogonality

This is the same demonstration as for R(A) and N(A).

### Orthogonality and Ax = b with No Solution

Orthogonality relates to the practice of finding approximate solutions for Ax = b, when there is no exact solution.  --In other words, when b is not in the column space of A.  When this is the case, we try to find the closest approximate solution.

It often happens when A is retangular (m<>r) that there is no solution for Ax = b.  When m>r, there will be many right hand sides (columns in b) that have no solution (are not in C(A)).  

The basic problem is that so far we have the ability, using elimination, to tell **if there is a perfect solution or not** to Ax = b.

We want to move beyond this **to an optimal, approximate solution** .  The key to realizing this goal is the use of the square matrix $A^A$ .  Here are some things we can anticipate about $A^TA$:

### Properties of $A^TA$:

*  Clearly, $A^TA$ is going to be square, because multiplying an nxm matrix times an mxn matrix is going to leave you with an nxn matrix.
*  $A^TA$ will be symmetric.  Consider this $A^TA$ example:

$$
A^A\text{ = }
\left[
{\begin{matrix}
1 & 2 \\
3 & 4 \\
\end{matrix} } 
\right]
\left[
{\begin{matrix}
1 & 3 \\
2 & 4 \\
\end{matrix} } 
\right]
\text{ = }
\left[
{\begin{matrix}
5 & 11 \\
11 & 25 \\
\end{matrix} } 
\right]
$$

$a_ij$ in A is always multiplied times $a_ji$ in $A^T$.  Strang's symbolic shorthand for this is $\left(A^TA\right)^T\text{ = }A^TA^{TT}\text{ = }A^TA$ .  In words, this says that if you transponse a symmetric matrix, you should get the same matrix again.  Since $A^TA$ after transposition ends up being $A^TA$, it must be symmmetric.

Additional properties to clarify:
* Is $A^TA$ invertible?

Answer: it may be.  Consider the 3x2 matrix:

$$
A\text{ = }
\left[
{\begin{matrix}
1 & 1 \\
1 & 2 \\
1 & 5 \\
\end{matrix} } 
\right]
$$

It's rank is 2; r<m; m>n.  The columns are independent.

Ax=b should be unsolvable; it is 3 equations in 2 unknowns.  One variable will always have to have 2 different values.  As ever, we can only solve b if b is in the column space C(A).  --Note: Strang says that the core of linear algebra is cv + dw = b, or that its the concept of subspaces, or their orthogonality, or ... whatever.  But I feel that the contemplation of this assertion that we can only solve b if b is in the column space C(A) , is the most remarkable statement in linear algebra so far. In algebra or calculus, the two sides of the equation are by definition said to be simultaneously equal.  In linear algebra, you move from left to right and say something like "all the things that can be are all the things that have already been".

$A^TA$ in this case is invertible, but it won't always be, and neither will its nullspace.

** In fact $A^TA$ is invertible i.o.i. its nullspace $N\left(A^TA\right)$ is only the 0 vector.  This only happens when A has independent columns. **

* What is the null space of $A^TA$ ?  The nullspace of A^TA$ is equal to the null space of A.
* What is the rank of $A^TA$ ?  The rank of $A^TA$ will always be the rank of A.
* If $A^TA$ is not invertible, what is its null space?

### $A^TA\hat{x}=A^b$ for Optimizing Ax = b 

The central equation for optimizing a solution to Ax = b, when no perfect solution exists, is $A^TAx=A^b$ .  

As a way of acknowledging that the x in $A^TAx=A^b$ is an estimate rather than the exact solution, we further modify the equation to be **$A^TA\hat{x}=A^b$** .

## Projections onto Subspaces

### Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/least-squares-determinants-and-eigenvalues/projections-onto-subspaces/

Suppose we have a projection of b onto a:

```import matplotlib.pyplot as plt
import numpy as np

# Define the vectors
a = np.array([3, 1])
b = np.array([2, 4])

# Calculate the projection of b onto a
projection = (np.dot(b, a) / np.dot(a, a)) * a

# Create the figure and axis
fig, ax = plt.subplots()

# Plot the vectors
ax.arrow(0, 0, projection[0], projection[1], head_width=0.2, head_length=0.2, color='red', label='Vector a')
ax.arrow(0, 0, b[0], b[1], head_width=0.2, head_length=0.2, color='blue', label='Vector b')

# Plot the vector from the projection to b
ax.arrow(b[0],b[1],projection[0]-b[0],projection[1]-b[1], head_width=0.2, head_length=0.2, color='purple', label='Projection b onto a')

# Set limits and aspect ratio
ax.set_xlim(-6, 6)
ax.set_ylim(-6, 6)
ax.set_aspect('equal')

# Add title and legend
ax.set_title('Vector Projection')
ax.legend()

# Show the plot
plt.show()
```

<img width="435" alt="Screenshot 2025-04-17 at 10 10 59" src="https://github.com/user-attachments/assets/5c72f19f-a9ff-4c24-84b6-e4669a88cd2f" />

We can think of the purple projection a onto b as "e" for the error.  Because it is at a right angle to a, we can reliably calculate how far wrong b is from a.  --Consider this in the context of linear regression parameter estimation.--  Specifically consider a point p on a which is where e touches a.  This point is the **"projection".**  The distance from b to p is the extent of the error.

The process that calculates this distance in linear algebra is computationally easier than trig-based approaches.  

We know that p is some multiple of a; it is on the line a.  We will call this multiple x of a, or "xa".  x is the number we want to find.  The key to the process is the perpendicularity $e\perp{a}$ at the intersection p.  We can denote this relationship as $a^T\left(e\right)$, and e = b-xa , so we state the key relationship as  $a^T\left(b\text{ - }xa\right)=0$ , remembering that the dot product of 2 perpendicular vectors is 0.  This equation is saying that a is perpendicular to e, and this will tell us what x is.  

This becomes clearer when we simplify the equation to: $xa^Ta\text{ = }a^Tb$ .  Then we can divide by $a^Ta$ to get $x\text{ = }\frac{a^Tb}{a^Ta}$ .  This is the right x to get the needed projection p .  

This x value actually has $\cos{\theta}$ built into it, although we don't need to investigate the actual angles.  

The value p is then given as p = xa (or ax) .  

Reviewing the above, our crucial equations are:

* $xa^Ta\text{ = }a^Tb$ , which leads us to
* $x\text{ = }\frac{a^Tb}{a^Ta}$
* p = ax to get our projection p .
* $P=\frac{aa^T}{a^Ta}b$

Consider p = ax reformulated as $p\text{ = }a\frac{a^Tb}{a^Ta}$ .  What would happen if we doubled b in this formula?  Thinking through the math, you could see that the whole value would exactly double.  Geometrically, you can imagine that b in the picture above would extend 2x as far as before.  The correct error or projection line p would then no longer extend from the tip of b to a, but as long as its length x doubled proportionally it would still be the right length to touch an imaginary extension of a in a perpendicular manner.

What happens if we double a, the vector onto which we're projecting?  Again, the projection value is not changed.  The length of a extends, but the line extending to it perpendicularly does not move. 

### The Projection Matrix

This project can be considered as being carried out by a matrix, which we'll call "P".  It acts on a vector b to produce the propection p.  That is, p = Pb .  From the above formula $p\text{ = }a\frac{a^Tb}{a^Ta}$ , we see that $P=\frac{aa^T}{a^Ta}b$ . We have moved the parentheses for emphasis, without any mathematical impact.  The emphasis is to show the matrix P that acts on b.   Note that the --"aTa" terms in the fraction do not cancel.  Their ordering is different; the numerator is a column \* a row, while the denominator is a matrix (a row times a column).  

What are the properties of the projection Matrix P?

#### Properties of Projection Matrix P

* The column space C(P) is the line through a.  
* The rank of P is therefore always 1.
 * You can see that this is so by considering its structure in the above formula -- the matrix consists of a column times a row.
 * The columm that multiplies the row is the basis for the column space.
* P is symmetric.  The denominator in $\frac{aa^T}{a^Ta}$ is a number, and the transpose of the numerator is again $aa^T$ .  Thus, $P^\text{ = }P^T$ .  **This is a key property of projection matrices.**
* If we do the same projection twice, that is if we take $P^2$, we still get P.
* **Thus, the 2 key properties that distinguish a projection matrix are:**
 * $P^T\text{ = }P$ , and
 * $P^2\text{ = }P$
   * This last property can be a bit hard to swallow, so consider a real example:

$$
P\text{ = }\frac{1}{9}
\left[
{\begin{matrix}
1 & 2 & 2 \\
1 & 2 & 2 \\
1 & 2 & 2 \\
\end{matrix} } 
\right]
$$

  * In order for $P^2\text{ = }P$, all values of P must be positive.  An additional property results:
    * P is positive semidefinite: $x^TPx\geqq{0}$ , for all x.  Because all vectors in P are $geqq{0}$ , and all x components are squared.

If you squared P (multiplied it times itself), of course the P's resultant values *do* change.  However, the internal proportions of the matrice's values wouldn't change, and so you could factor out $\frac{1}{9}$ and be right back to $\frac{1}{9}P$ again.  This is what is meant by the property $P^2\text{ = }P$ .

### Projection in Higher Dimensions

Again, with projection, our goal is to find optimal approximations for Ax = b when the equation does not have precise solutions.  In such cases, the remedy is to solve the equation Ax = b that most closely resembles the true equation.

The "closest resemblance" is defined by finding a vector p that:
* *is* in the column space C(A), and
* is closest in distance to b .

So, we solve for Ax = p instead of Ax = b.  p is the projection of b onto C(A).    From here on out, we'll adopt the convention of denoting x in Ax = p with a "hat" to indicate that it is in the set of x that yield the p estimate when acted on by A, i.e. $A\hat{x}\text{ = }p$ .  

Suppose we have a plane in 3 space, and a vector b that is not in that plane.  We want to project b down into the plane.  We begin to do this by positiving to vectors, a1 and a2, in that plane, which form a basis for it.  These vectors do not need to be perpendicular to anything, but they do need to be independent.  This is the plane of a1 & a2.  The plane is the column space of a1 and a2, and can be written as a matrix A that stores the columns a2 and a2.  So we have a matrix A with 2 columns (but it could be n columns).  

We want to calculate e  = b - p, where e is the line down to the projection point p on a vector a in the plane.  By geometry, e must be perpendicular to the plane.  --Essentially what happens is that by subtracting p from b, I take away every dimension that is not perpendicular to the plane.

This means we must calculate p.  As stated previously, p = xa, and in this case A consists of 2 basis vectors.  Therefore, p must equal x1a1 + x2a2 .  It is better however to think of this as ax or $a\hat{x}$ to indicate that x is a vector of estimates.  

In an n-space, the projection p = $A\hat{x}$  and our problem is to find $\hat{x}$ .  The key is that e = b - $a\hat{x}$ .  Again, in n-space, x consists of as many components as you have basis vectors.  In this case, we have a plane, meaning 2 basis vectors, so we'll need to solve for $\hat{x}_1$ and $\hat{x}_2$ .  We know that e is perpendicular to the plane, so it must consist of :

${a_1}^T\left(b\text{ - }A\hat{x}\right)\text{ = }0$ and ${a_2}^T\left(b\text{ - }A\hat{x}\right)\text{ = }0$ .

These will be easier to process if we put them in matrix form:

$$
A\text{ = }
\left[
{\begin{array}
{a_1}^T \\
{a_1}^T \\
\end{array} } 
\right]
\left(b\text{ - }A\hat{x}\right)
\text{ = }
\left[
{\begin{array}
0 \\
0 \\
\end{array} } 
\right]
left(b\le
$$

This detailed breakout is the same as the formula $A^T\left(b\text{ - }A\hat{x}\right)\text{ = }0$ . 

Note that:
* The matrix A in this equation is the n-space correspondence to the single line little "a" in our previous equation.  If you substituted that in, you would have the same equation as previously.
* We should consider what subspace e is in.  Because it is multiplied times A, and is meant to yield the 0 vector, we know that it must be in the **nullspace of A^T** .  By extension, we know that the nullspace of A transpose, $N\left(A^T\right)$, is always orthogonal to the columnspace of A, C(A).
 * Thus, saying that e is in the nullspace of A transpose means that it is perpendicular to the column space of A.

Continuing in matix notation, we can write the equation as $A^TA\hat{x}\text{ = }A^Tb$ .  Then we solve for x.  

### Solving for Matrix P in Final Form

Coming back to our key 1 dimension equations, we can also re-write them in matrix n-space terms:

* $\hat{x}\text{ = }\left(A^TA\right)^{-1}A^Tb$ --you can see that the inverse portion here is the way of making it a "fraction" as in the one dimension case.
* p is then p = $A\hat{x}\text{ = }A\left(A^TA\right)^{-1}A^Tb$ .
 * --Looking at this, you can see that the portion multiplying b to get P is in fact the projection matrix.  It must be, by definition, since mulitiplying b gives you p.
 * Note: you cannot in this case use the rule for inverses to turn $A\left(A^TA\right)^{-1}A$ into $AA^{-1}\left(A^T\right)^{-1}A^T$ .  If you do, the last two terms $\left(A^T\right)^{-1}A^T$ become the identity I .  This seems mathematically like a glitch at first, but the reason applying the rule for inverses isn't allowed here is that **A is not a square matrix, and therefore does not have an inverse.** Thus, you mustn't apply the rule for inverses here (I don't know why you'd care to) because it won't always work.  [I don't get then why, if a matrix does not have an inverse, you're allowed to treat it as though it was one??]
 * Anyway, remember that you're doing this Axhat = b stuff in general because A has more rows m than rank r, and so doesn't have a precise solution.
  * If A was a square, invertible matrix, its C(A) would be the whole of R^n .  If were were projecting onto the whole space, P(A) would be the identity matrix.  You can kind of see this when you consider that yes, $A^TA$ is indeed I after row reduction.  Another way of thinking about it is that if I'm projecting b into the whole space, then b is already in the column space.

### Properties of P in n-Space

The projection matrix P will still have the same properties as it a projection did in the 1-d case:
* It will be symmetric: $P^T\text{ = }P$.
* $P^2\text{ = }P$ .  --If you were to multiply out the full function times itself: $A\left(A^TA\right)^{-1}\color{red}{A^TA\left(A^TA\right)^{-1}}A^T$, you'll see the left side of it (in red) has $A^TA$ multiplying it's inverse, which gives an identity matrix, so that the whole thing reduces to its original form  $A\left(A^TA\right)^{-1}A^T$ .

## Least Squares with Projection

### Sources
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/least-squares-determinants-and-eigenvalues/projection-matrices-and-least-squares/
* https://www.youtube.com/watch?v=MC7l96tW8V8
* Example: https://www.youtube.com/watch?v=8mAZYv5wIcE&list=PL39469144F25ACECE

The most common application of P is fitting points to a line.

### Basics of Least Squares Approximation

Suppose you have a system of equations that can be construed as the formula Ax = b in the usual way for linear algebra, where A is the coefficients for the equations, x is the vector of variables for these equations, and y is the solution for the equation.  In the context of linear regression from a grind data, this would look like $\beta_1x_1\text{ = }\beta_2x_2\text{ ... }\beta_nx_n\text{ = }y$, where y is the variable we hope to predict.  Each row of data would be considered a separate equation predicting its own y.  Mapping this on to the linear algebra Ax = b format, the values in the columns i...m are the coefficients, the imaginary variables from columns i ... n that the coefficients multiply are the variables in the vector x, and the i...m y values we expect to predict are in the beta vector.  

Usually there is not an exact solution for x, and this is usually because there are two many rows in A, so you just can't find a set of x values that will solve for all the values of b.

So in this situation Ax cannot = b.  In other words, b is not in A's column space C(A).  But you can immagine that in the column space C(A) of all possible Ax linear combinations, there is some set of x values $\hat{x}$ such that the vector of errors or differences $A\hat{x}$ - b will be as small as possible.  We know what A is, but so far the ideal $A\hat{x}$ that minimizes errors is unknown because we haven't found $\hat{x}$.  This $A\hat{x}$ is called a "projection" p because it can be thought of as a projection or shadow of b on Ax, where b and p are identical in all respects except the errors.  

These error values $A\hat{x}$ - b are thought of as being orthogonal to C(A).  **This is very important, because the projection p that is closest to b, which minimal error, will be the only one that is orthogonal.** To see that this is true, you can look up 3d illustrations of this concept where a line b is not in a 2d plane of C(A) and by reasoning and eyeballing it you can see that the shortest line e between b and p would have to intersect p at a right angle.  The Kahn youtube videos referenced above give a good account.  For higher dimensions you have to take it on faith or look up more complicated proofs.  

In order to make mathematical use of this orthogonality to find the projection $A\hat{x}$ , we do a couple things:

* first we know that if $A\hat{x}$ - b is orthogonal to C(A), that means it is by definition in the left nullspace of C(A).  That is, $A\hat{x}$ - b is in $N\left(A^T\right)$, which contains all values orthogonal to C(A).
* next, we note that again by definition, if $A\hat{x}$ - b is in $N\left(A^T\right)$ , then $A^T\left(A\hat{x}\text{ - }b\right)\text{ = }0$ , because:
  * $A^T$ is orthogonal to $N\left(A^T\right)$ and
  * if vectors are orthogonal to each other, their dot product is 0.
* finally we distribute $A^T$ over $\left(A\hat{x}\text{ - }b\right)$ by multiplication, and then move $A^Tb$ to the right side of the equation to get: $A^TA\hat{x}\text{ = }A^Tb$ .
* This puts us in a position to solve for x by treating putting [A b] into RREF in the usual way.  This process is easier than finding $\hat{x}$ via a projection matrix to multiply on b.


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
\left[{\begin{array}
1 \\
1 \\
1 \\
\end{array} }\right]
\text{,  b = }
\left[{\begin{array}
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
\left[{\begin{array}
1 \\
0 \\
2 \\
\end{array} }\right]
\text{ - }\frac{3}{3}
\left[{\begin{array}
1 \\
1 \\
1 \\
\end{array} }\right]
\text{ = }
\left[{\begin{array}
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

## Covariance Matrices

## Symmetric Matrices and Positive Definiteness

### Sources:
* USF: https://usfca.instructure.com/courses/1627052/pages/positive-semidefinite-matrices-video-18?module_item_id=18611427
* MIT: https://www.youtube.com/watch?v=UCc9q_cAhho

### Eigenvectors and Eigenvalues

### Sources:
* https://www.youtube.com/watch?v=cdZnhQjJu4I

### Notes:
* eigenvectors and eigenvalues only come from square matrices
* the sum of eigenvalues must equal the sum of the diagonal in A, aka the "trace" (not nec. = the pivots in R).

## Symmetric Matrices, Eigenvalues, and Eigenvectors

### Symmetric Matrices

* A matrix A is symmetric if A = $A^T$ .

#### Symmetric Matrices Have Real Eigenvalues

* As a result of this symmetric matrix structure:
  * eigenvalues of a symmetric matrices, where all the values in A are $\in{\mathbb{R}}$, are real.  The eigenvectors will not be complex as we saw with rotation matrices Q.
    * Why is are the eigenvalues Real?  Consider the canonical equation $Ax\text{ = }\lambda{x}$ :
      * For a first step, we can take the complex conjugate of an equation: $Ax\text{ = }\lambda{x}\rightarrow{}A\overline{x}\text{ = }\overline{\lambda}\overline{x}$  As a reminder, a **complex conjugate** is complex formulation of a set of terms such that adding them together will remove the imaginary elements, e.g. a + ib = a - ib (here, a would be the only term remaining).
        * This already tells us that if Ax has an eigenvalue lambda and eigenvector x, it also has an eigenvalue $\overline{\lambda}$ and $\overline{x}$ .
      * We can also transpose $A\overline{x}\text{ = }\overline{\lambda}\overline{x}$ to $\overline{x}^TA^T\text{ = }\overline{x}^T\overline{\lambda}$ .  Since $\lambda$ is just a number, we don't transpose it.
      * At this point, we note that since A is symmetric, then $A^T$ is the same as A.  We can then multiply both sides by x:
        * $\overline{x}^TAx\text{ = }\overline{x}^T\overline{\lambda}x$ .  Notice that the left hand side is the same as if we had just multiplied the original equation by $\overline{x}^T$:
        * $\overline{x}^TAx\text{ = }\lambda{}\overline{x}^Tx$
        * --but since the two different right hand sides have an identical left hand side, the two different right hand sides must be equal to each other.  That is: $\lambda\overline{x}^Tx\text{ = }\overline{\lambda}\overline{x}^Tx$ .  It is clear from this equation, where the only difference is the conjugate of $\lambda$, that $\lambda\text{ = }\overline{\lambda}$ .  Note that this conclusion assumes that $\overline{x}^Tx$ is > 0 .
        * **Then $\overline{x}^Tx$ can be cancelled, with the conclusion that the $\lambda$ and $\overline{\lambda}$ are identical and therefore real.**  --It is a rule that if a number is equal to its own complex conjugate then there is no imaginary portion and the only remaining part is real.  This makes sense if you look back to a simple complex conjugate like a + ib = a - ib, where adding them together would cancel the imaginary portions.
      * Coming back to the qualification that $\overline{x}^Tx$ > 0:
        * remember that, as far as we know in this equation context, x is a complex number:  a column vector of complex numbers is being multiplied by a row of its complex conjugates.
        * remember that the basic formulation of a complex number multiplied by its conjugate is (a + ib)(a - ib), and also that i is $\sqrt{-1}$ .  This means that a vector of complex numbers multiplied by its transpose will result in a vector of positive numbers, because the middle terms will cancel out, and $i^2$ = -1, so you get $a^2$ +aib -aib - $b^2i^2$ = $a^2$ - $b^2$ (-1) = $a^2\text{ + }b^2$.
        * **consequently, multiplying a vector x by its conjugates ensures a vector of positive, real results.**
        * **this maneuver also shows us that we can change complex number vectors to real number vectors by multiplying them with their transpose.**
          * **this result is also the length squared of x.**
      * What if A has been a matrix of complex numbers?
        * Consider the properties of a "good matrix" (one that is computationally easy).  It has:
          * real $\lambda$ values
          * perpendicular x's
          * symmetric: A = $A^T$
        * However, if A is complex, the proofs we looked at above will still work, provided $\overline{A}^T\text{ = }A$ .

#### Symmetric Matrix Decomp to Proj Matrices

* Consider the formula $A\text{ = }Q\Lambda{}Q^T$ .  This says that A can be decomposed into a matrix Q of eigenvectors multiplying a matrix of eigenvalues, times the transpose of Q.  This is true for the symmetric case A = $A^T$ .
   * We can break this down further to show the composition:

$$
A
\text{ = }
\left[
{\begin{matrix}
\vdots & \vdots & \vdots \\
q_1 & \ldots & q_n \\
\vdots & \vdots & \vdots \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
\lambda_1 & {} & {} \\
{} & \lambda_2 & {} \\
{} & {} & \lambda_mn \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
\ldots & q_1 & \ldots \\
\ldots & \vdots & \ldots \\
\ldots & q_n & \ldots \\
\end{matrix}}
\right]
\text{ = }
\lambda_1q_1q_1^T\text{ + }\lambda_2q_2q_2^T\ldots
$$

...so the result is a set of addtions considing of lambdas times eigenvectors in an orthonormal relationship, since they are multiplied times their transpose.  
  * **Every symmetric matrix consists of additions, using real lambdas, in this pattern.**
  * **Every symmetric matrix is a combination of mutually perpendicular projection matrices.**
    * the spectral theorem is sometimes construed as the decomposition of a symmetric matrix into these mutually perpendicular projection matrices.
  * each $q_1q_1^T$ pair is a projection matrix.  

#### Symmetric Matrices and Stability

* Because symmetric matrices have real eigenvalues, we can look at whether they are positive or negative, which tells us things like the stability of a system (depending on the application).
* Some facts about eigenvalues that are computationally useful.
  * It is a fact, in a symmetric matrix, that the signs of the pivots must match the signs of the eigevenvalues.
  * It is also a fact that the product of the pivots in a symmetric matrix equals the product of the eigenvalues.  This is because both of these products equal the determinant, assuming for the product of the pivots that no row exchanges occurred.

#### Symmetric Matrices Have n Orth Eigenvectors

* a complete set of eigenvectors can be selected to be perpendicular 
    * for example, the I matrix is symmetrical, and all vectors x are necessarily eigenvectors since they are unchanged by I.  But among these, vectors perpendicular to each other could be selected.  --This is not (necesarily? always?) the case for other matrix types.
* A matrix A can typically be decomposed into its eigenvalue matrix $\Lambda$ and its eigenvector matrix S as $A\text{ = }S\Lambda{S^{-1}}$ .
  * However, in the case of a symmetric matrix, not only is having n perpendicular (orthonormal) eigenvectors guaranteed, but also we can scale them to be unit vectors.  This special composition of the eigen decomposition of A is denoted by using the matrix Q instead of S: $A\text{ = }Q\Lambda{Q^{-1}}$ .  Note that inverse of Q is the same as $Q^T$ .
  * Thus: $A\text{ = }Q\Lambda{Q^{-1}}\text{ = }Q\Lambda{Q^T}$ is the factorization of a symmetric matrix.  This is known as the **"spectral theorem"** , owing to applications in optics and light. In mechanics, it is known as the principal axis theorem.  
    * We can consider $A\text{ = }Q\Lambda{Q^T}$ as the "factorization of a symmetric matrix".  Note: this formula implies that A is symmetric, because the definition of a symmetric matrix is that $A\text{ = }A^T$, and it is clear that transposing $Q\Lambda{Q^T}$ would equal $Q^{T}Q\Lambda{}$ which is equivalent to $Q\Lambda{Q^T}$ .



## Diagonalization, Eigenvectors, Powers of A

### Sources
* MIT: https://www.youtube.com/watch?v=13r9QY6cmjc
* Youtube Rando: https://www.youtube.com/watch?v=uuB0WE31318

### Notes

#### Basic Diagonalization 

* In **diagonalization of a matrix** we arrange eigenvalues and eigenvectors in a way that is optimal for computation.
* The key formula for this process is $S^{-1}AS\text{ = }A$
  * Suppose A has n independent **eigenvectors**, and we put them in the columns of the "eigenvector matrix" S.
    * When we multiply A times S we get:

$$
AS\text{ = }A
\left[
{\begin{matrix}
\vdots & \vdots & \vdots \\
x_1 & \ldots & x_n \\
\vdots & \vdots & \vdots \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
\vdots & \vdots & \vdots \\
\lambda_1x_1 & \ldots & \lambda_nx_n \\
\vdots & \vdots & \vdots \\
\end{matrix}}
\right]
$$

... to understand this, remember that by definition an eigenvector is unchanged in its parallelism to x by being multiplied by A.  This means that A will have no effect on the eigenvector in s except for whatever eigenvalue scalar it contributes.  Therefore each multiplication of A on each column storing an eigenvector in S will result in a new matrixx with columns having $\lambda_ix_i$ .

Next, we want to separate the x and lambda components into separate matrices.  We can do this by factoring the xs into a matrix of columns, times a diagonal matrix of lambdas:

$$
\left[
{\begin{matrix}
\vdots & \vdots & \vdots \\
\lambda_1x_1 & \ldots & \lambda_nx_n \\
\vdots & \vdots & \vdots \\
\end{matrix}}
\right]
\text{ = } 
\left[
{\begin{matrix}
\vdots & \vdots & \vdots \\
x_1 & \ldots & x_n \\
\vdots & \vdots & \vdots \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
\lambda_1 & \vdots & \vdots \\
\vdots & \ddots & \vdots \\
\vdots & \vdots & \lambda_n \\
\end{matrix}}
\right]
$$

... we can refer to the matrix of eigenvector x columns as S, and the diagonal matrix of $\lambdas$ as $\Lambda$.  So altogether, AS\text{ = }\Lambda$.

The reason why we mentioned n **independent** eigenvectors is to stress that the matrix S is invertible.  Thus we can also write the formula as $S^{-1}AS\text{ = }\Lambda$ , by multiplying each side by the inverse of S.  This is **diagonalization** of the eigenvalues.  Further, we can calculate A by reformulation this as $A\text{ = }S\LambdaS^{-1}$ .  Having stepped through the above diagonalization process, the first formulas are undestandable; the last is a lot of abstraction to swallow.  This is a new formulation which which we can replace previous ones such as A = LU , or Graham - Schmidt.

#### Diagonalization Applications: Powers of A Matrix

Below, we work out a system for dealing with powers of a matrix.  While useful in itself, it also prepares us for dealing with differentials of a matrix.

We can use these formulas to understand the eigenvalues of $A^2$ :

Beginning with $Ax\text{ = }\lambda{}x$ .  If this formula is true, then $A^2x\text{ = }\lambda{}Ax$ .  

But by the initial formula Ax = $\lambda{}x$, so we can substitute

$A^2x\text{ = }\lambda{}^2x$ .

Based on these formulations, we can conclude that **the eigenvalues of A squared are lambda squared.  The eigenvectors are the same on both sides of the equation. **That is, if you square a matrix (having n independent eigenvalues), its eigenvalues will be squared, and its eigenvectors will be unchanged.** 

Returning to the formulation $A\text{ = }S\LambdaS^{-1}$ , we can also look at the impact of squaring A:

$A^2\text{ = }S\LambdaS^{-1}S\Lambda{}S^{-1}\text{ = }S\Lambda{}^2S^{-1}$  -- contemplating the right side a little, you'll see that the combinations of S and its inverse will yield identity matrix I, leaving the $\Lambda$ by itself to be squared.  In words, this means again, as with the other formulation immediately above, that the eigenvectors are unchanged but the eigenvalues are squared. 

Of course, this formula could be multiplied to $A^k$ power for an arbitrarily large k, with the same result -- only the eigenvectors would be multiplied.   This is another way to describe **eigen decomposition** .

We can use this information to understand when the powers of a matrix go to 0, which can also be thought of as a matrix becoming stable.  In regular algebra, when a variable is taken to the power of 0 it is equal to 1.  In linear algebra, a matrix taken to a power of 0 becomes the identity matrix.  -- A theorem describes this fact:

**Matrix Powers Theorem:**

For $S\LambdaS^{-1}$ :

* $A^k\rightarrow{}0$ as $k\rightarrow{}\inf$ if all $\|\lambda\|$ <1 .  We have to qualify on the absolute value of lambda, because we remember that lambda can be a complex number and result in a negative value.  Remember also that we're assuming that A has n independent eigenvectors.  This is the only situation in which eigendecomposition or "diagonalization", which purely uses eigenvectors, can work.  This is because S is not invertible if A does not have n independent eigenvectors.

Key point for diagonalizability: **A is sure to have n independent evectors and be diagonalizable if A has n distinct eigenvalues.**  --I.e., no eigenvalue is repeated.

However, if an eigenvalue is repeated, the matrix A may or may not have n independent eigenvectors.  Take the extreme case of the identity matrix, for which every vector is an eigenvector.  If A = I, then we can choose n independent vectors for A, and when we use the equation $S^{-1}\Lambda{}S$ we get I as a result again.  This makes sense because if $\Lambda$ is already diagonal, then the $\Lambda$ is the same as the matrix -- a diagonal matrix already has its eigenvalues resolved.  

If however the matrix is triangular and has non-distinct eigenvalues, for example 

$$
A\text{ = }
\left[
{\begin{matrix}
2 & 1 \\
0 & 2 \\
\end{matrix}}
\right]
$$


... then diagonalization is impossible.  --This matrix yields eigenvectors (2,2), but after subtracting the eigenvalues the matrix will be "degenerate" like so:

$$
A2\text{ = }
\left[
{\begin{matrix}
0 & 1 \\
0 & 0 \\
\end{matrix}}
\right]
$$

... "degenerate" means that there are fewer dimensions to the eigenvector (in this case only one) than were in the original matrix.  The only eigenvector in the nullspace of A2 is (1,0).  (0,1) is not in the nullspace.  Another way to say this is the algebraic multiplicity is 2 (the algebraic solution has 2 roots), but the geometric multiplicity is 1 .  It is not diagonalizable because you cannot find 2 eigenvectors such that you can write A = $S^{-1}\Lambda{}S$.

#### Diagonalization Applications: Powers of A Matrix Times a Vector

Suppose we have a vector $u_{k+1}\text{ = }Au_k$ .  We start with a given vector $u_0$, and at every step k+1 $u_{k+1}$ is the result of multiplying $u_k$ by A as $Au_k$ .  In other words, if we start with a vector $u_0$ and multiply it by A 100x, what do we have? 

Clearly, $u_k\text{ = }A^ku_0$ .  Imagine that k = 100.

--Incidentally, we can call this a first-order system, because k is only increased one level, and the vector being multiplied by a matrix makes it a system.

To really solve for $u_0$, write it as a combination of components of u multiplied by components of $\Lambda$ : $u_0\text{ = }c_1x_1\text{ + }c_2x_2\text{ +...+ }c_nx_n$ .

In order to find $u_100$, the easy thing is to diagonalize A (assuming n disting eigenvectors), so that we can reduce the problem to taking powers of $\Lambda$, and then multiplying that times $u_0$.

Strang writes out the solution to this (in this lecture and in ITLA) in basically 2 steps to show the actual computations involved:

* construe $X^{-1}u$ as the components of u (c1 ... cn) times each eigenvector x1...xn of $X^{-1}$ like so: $u_0\text{ = }c_1x_1\text{ + }c_2x_2\text{ +...+ }c_nx_n$ .  The textbook gives this as "c = " rather than $u_0\text{ = }$ .  In this way of thinking, both the vector u and the inverse eigenvector matrix $X^{-1}$ are portioned out into c components.
* multiply these components times corresponding eigenvalues and eigenvectorx from X, like so: $Au_0\text{ = }c_1\lambda_1x_1\text{ + }c_2\lambda_2x_2\text{ +...+ }c_n\lambda_nx_n$ .

Remember that by definition, we have said that A has n independent eigenvectors, which again by definition are unaffected by multiplication with A.  As we have shown above, only the eigenvalues are therefore multiplied when multiply A by k in $A^k$ . Thus we can say that:

* $A^ku_0\text{ = }c_1\lambda_1{}^kx_1\text{ + }c_2\lambda_2{}^kx_2\text{ +...+ }c_n\lambda_n{}^kx_n$ .

We can also re-write this as:

* $A^ku_0\text{ = }\Lambda^kSc$ , where c contains the set of vectors that portion out the eigenvectors with their respective component multipliers from $u_0$ .

#### Diagonalization Applications: Powers of A Matrix Fibonnaci Example

We can apply the above to find the 100th Fibonnaci number, and understand the rate of growth for the Fibonnaci numbers.  The rate of growth will be given by the eigenvalues of a Fibonnaci matrix.

The Fibonnaci rule is $F_{k+2}\text{ = }F_{k+1}\text{ + }F_k$ .

So far, we've been solving systems where a matrix operates on a vector.  Strang addresses 2 problems with solving an equation like this via the linear algebra processes we have so far:
* it is an equation, rather than a "system" in which we get a result from a matrix acting on a vector.
* it is "second-order" : it involves 2 steps  -- first getting fk, then fk+1, rather than just one step as we have in our linear algebra systems so far.  Strang compares this situation to taking a second-order derivative; I am not sure how literal this comparison is.

In order to address these issues and turn this Fibonacci formula into a matrix system, Strang puts the 2 values on the right side of the equation into a vector:

$$
u_k
\text{ = }
\left[
{\begin{matrix}
F_{k+1} \\
F_k \\
\end{matrix}}
\right]
$$

The two items on the right side of the equation are simply values, so they should be fine to put in a vector.  Using this vector, we can construe a system with a matrix as $u_{k+1}\text{ = }Au_k$ , where A has the to-be-determined values that multiples $u_k$ to get $u_{k+1}$ .  The matrix that operates on it can then be a 2x2 matrix.  Essentially what happens is that because a matrix operates on both items, we are able to solve both items at once in one step, reducing the equation to what Strang calls a "first order difference".  I don't know why he says "difference" instead of "sum".  Strang's essential comment here is that introducing the vector $u_k$ allows him to "have a first order matrix system instead of a second order scalar equation."  

To the intial Fibonnaci equation Strang adds a second equation:

* $F_{k+2}\text{ = }F_{k+1}\text{ + }F_k$
* $F_{k+1}\text{ = }F_{k+1}$

... I am not sure yet how this fits into the discussion.  Strang doesn't immediate verbalize a reason for it.  Later he says that he is making an artificial system of equations.  I think it must be to fill out the 2x2 matrix somehow because he says "this [the 2 equations] is my system, the vector $u_k$ is my unknown, and the one-step [first order] equation altogetehr is...

$$
u_{k+1}\text{ = }A
\left[
{\begin{matrix}
F_{k+1} \\
F_k \\
\end{matrix}}
\right]
\text{ = }Au_k
$$


...", where A is some tbd matrix that operates on $u_k$ on the right to give the left side result .  

The matrix A must then be

$$
A\text{ = }
\left[
{\begin{matrix}
1 & 1 \\
1 & 0 \\
\end{matrix}}
\right]
\text{ = }Au_k
$$

--- this will obviously give you back $F_{k+2}\text{ = }F_{k+1}\text{ + }F_k$ for the first component of $F_{k+2}$.  I'm not sure why you then want the second component $F_{k+1}$ since you just want a single result?  

To my surprise, Strang stops to take the eigenvalues and eigenvectors.  We remember that the det will be the product of the eigenvalues, and the trace will be the sum of the eigenvalues, and also that a symmetric matrix will have real eigenvalues. We also know that we have n independent vectors.  

The eigenvalue solution process yields the formula $\lambda^2-\lambda-1\text{ = }0$ .  Rather than factor this, Strang takes the quadratic formula.  --I couldn't mentally factor this equation it in such a way to get **both** the determinant and the trace, so I guess that's a clue that the quadractic formual is the way to go.  In the end Strang gets  

$\Large{\lambda{}\text{ = }\frac{1\pm\sqrt{5}}{2}}$ ; $\Large{\lambda_1\text{ = }\frac{1}{2}\left(1+\sqrt{5}\right)}$ , $\Large{\lambda_2\text{ = }\frac{1}{2}\left(1-\sqrt{5}\right)}$

... these values do indeed add to 1, and multiply to -1 ; they are roughly 1.618 and -.618.

Note that at this point we can see the rate of increase for the Fibonacci numbers.  Somehow, the eigenvalues control the growth of these Fibonnaci numbers.  Strang doesn't articulate it, but looking at the above, we can imagine 2 successive numbers out of the Fib sequence as being the result of our matrix system, and their progression lying on a line that is controlled by the value $\approx$ 1.618 .  **He says that the "biggest" value controls the growth. --I have missed out somehow on why this is so.**  (See next paragraph for explanation).  Therefore, the 100th value of the Fib sequence is $\approx{}c_1\left(1.618\right)^{100}$ , where c_1 is some constant . $\approx$ 1.618 is the factor by which the Fib numbers grow.  I don't like how the constant came out of nowhere. 

Note that this finding relates back to diagonalization.  The initial value $u_0$ was. $u_0\text{ = }c_1x_1\text{ + }c_2x_2\text{ +...+ }c_nx_n$ .  That is, it is a combination of the components of a vector times the corresponding eigevectors of X inverse.  When we start computing the series of Fibonnaci numbers and multiply by A 100 times, we end up taking $c_1\lambda_{1}^100x_1$ -- this term takes over. **Note this also shows us where "c_1" came from immediately above.**  By contract, the second term $c_2\lambda_{2}^100x_2$ diminishes to nothing because it is multiplying a term <1. 

Solving for eigenvectors in this system, we get:

$$
A-\lambda{}I
\text{ = }
\left[
{\begin{matrix}
{1\text{ - }\lambda} & 1 \\
1 & {-\lambda} \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
\lambda \\
1 \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
0 \\
0 \\
\end{matrix}}
\right]
$$

... the first term of eigenvector x here is by no means obvious -- you'll not resolve it with simple algebra.  It's only when you see him point to the earlier formulation $\lambda^2\text{ - }\lambda{ - }1\text{ = }0$ that you see it could be true [and I think only true for specific values of lambda].  Getting the second term of eigenvector x is simple though.  Thus $x_1$ = ( $\lambda_1$ , 1)  and $x_2$ = ( $\lambda_12$ , 1) .  -- Somehow, he unpacks 2 lambda values out of 1 lambda to get the 2 eigenvectors.  He says that this "trick" is available in the 2x2 case, perhaps meaning that this maneuver isn't available for larger matrices. 

To completely resolve this excercise, we can calculate u0 per the above equations.  Strang begins this process by noting that "u0" was "F1, F0", or 

$$
u_0
\text{ = }
\left[
{\begin{matrix}
F_1 \\
F_0 \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
1 \\
0 \\
\end{matrix}}
\right]
$$

... which makes sense, considering that he started the reformulation of Fib sequence into a matrix system at u0 = $F{k+2}\tex{ = }F{k+1}+F_k$ .

We therefore need to find constants multiplying the eigenvectors we calculated such that they will produce the vector (1,0):

$$
c_1x_1\text{ + }c_2x_2\text{ = }
\left[
{\begin{matrix}
1 \\
0 \\
\end{matrix}}
\right]
$$

We know the eigenvectors, so if we find c1, c2, we are home and dry.  The central idea here is that when things are involving in time by a first order system, starting from an original value $u_0$, the key is to find the eigenvectors and eigenvalues of A.  The eigenvalues will tell you whether the solution is increasing, going to zero, etc.  

#### Diagonalization Continue: Fibonnaci Example Cont.

As stated above: remembering that we made $F_{k+1}$ equal to $u_0$, we can use the $u_0$ formula as 

$$
c_1x_1\text{ + }c_2x_2\text{ = }
\left[
{\begin{matrix}
1 \\
0 \\
\end{matrix}}
\right]
$$

... just as with Fk - style reformulation, Fk+1 + Fk is c1x_1, and Fk+1 is c2_x2 ; the Fk+2 or u0 component is given as (1,0).  (1,0) is initial state we posit as 2 successive items in the Fib series; I guess we could have picked any two such?  

We can re-format our eigenvector inputs into an Ax = b formlation like:

$$
\left[
{\begin{matrix}
\lambda_1 & \lambda_2 \\
1 & 1 \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
c_1 \\
c_2 \\
\end{matrix}}
\right]
\text{ = }
\left[
{\begin{matrix}
1 \\
0 \\
\end{matrix}}
\right]
$$

From the second row of this matrix, we can see that c1 + c2 must = 0 so c1 = - c2, or equivalently c2 = -c1.   We know the values of lambda, so in order to solve for the first row, we can substitute in -c2 for c1 like so:

$$\frac{\left(1+\sqrt{5}\right)}{2}c_1\text\{ - }frac{\left(1+\sqrt{5}\right)}{2}c1\text{ = }1$$ 

... here, we used the equation c2 = -c1.  This equation then reduces to $c_1\text{ = }\frac{1}{\sqrt{5}}$ ; $c_2\text{ = -}\frac{1}{\sqrt{5}}$ .

Substituting these back into our u0 or uk formulation and taking for example k = 3, we get:

$$
u_k\text{ = }c_1\lambda_1^kx_1\text{ + }c_2\lambda_2^kx_2\text{ = }
\frac{1}{\sqrt{5}}\frac{\left(1+\sqrt{5}\right)}{2}^3
\left[
{\begin{matrix}
frac{\left(1+\sqrt{5}\right)}{2} \\
1 \\
\end{matrix}}
\right]
\text{ - }
\frac{1}{\sqrt{5}}\frac{\left(1-\sqrt{5}\right)}{2}^3
\left[
{\begin{matrix}
frac{\left(1-\sqrt{5}\right)}{2} \\
1 \\
\end{matrix}}
\right]
$$

so for k=10 using this formulation in python, you will get 144 (89 + 55) which is indeed correct.  In reality if you do this in python the "k" constant may not index the number you expect, because python for example starts from a base 0 in a range and goes to range-end - 1.  But the calculations will be correct once you sort that out.  Here is some python code implementing the above:

#### Diagonalization Continue: Fibonnaci Python Notes

```
l1=(1+np.sqrt(5))/2
l2=(1-np.sqrt(5))/2
c1=(1/np.sqrt(5))
c2=-1*(1/np.sqrt(5))

for k in range(0,11):
    result = ((c1*l1**k*l1)+(c1*l1**k*1))-((c2*l2**k*l2)+(c2*l2**k*1))
    print(k,round(result))
```

It's well worth reviewing backwards and forwards how an algebraic "2nd order" system is wound into a 2x2 matrix "first order" system and vice-versa.  It helped me to note that what the above is going to give you is a single number because it is the **result** of a 2x2 matrix operating on a 2x1 vector and so is already summed up -- visually it is still taken apart as a vector of components (in this example, 89 + 55).

## Positive Definite Matrices
*  These matrices are a subclass of symmetric matrices.
*  All the eigenvalues are > 0.
*  The pivots are also are > 0.

These 2 items are a sufficient test of whether a matrix is positive definite.

Consider the matrix:

$$
\left[
{\begin{matrix}
5 & 2 \\
2 & 3 \\
\end{matrix}}
\right]
$$

The pivots are 5, and 11/5, because the determinant is the product of the pivots, and in this case the determinant is 11.  
Because the pivots are both positive, we know that the eigenvalues are positive.
To check that a matrix is positive definite using determinants, we must verify not just that the overall determinant is positive, but also that the **"subdeterminants"** are positive.  So in this case considering component $a_11$ = 5 as a 1x1 matrix, we can say that the "sub" determinant = 5 > 0.  Then expanding the matrix outward from there to 2x2 dimensions, we can say that the determinant 11 is also positive.  

### Motivation and Uses of PSD Evaluation

* Covariance matrices are always positive semidefinite, or positive definite.
* Optimization typically uses positive semidefinite matrices.
  * this often involves a min or max of a function over several variables
  * one of the conditions for verifying that a min/max is a true min/max (global min/max) is to review the Hessian matrix for a functions surface, and verify that its positive definite or negative definite.  

### Positive Semidefiniteness Definition

A matrix $A_{nxn}$ is positive semidefinite if for every vector x $\in\text{ = }\mathbb{R}^n$ , we have : $x^TAx\text{ }\geq{}\text{ }0$ .  This is true for all vectors x.  

"Positive semidefinite" for matrices is thus analogous to "non-negative" for scalars.  

Note that:
* **Positive Definiteness** is the same thing, but where every vector x is always > 0 .

### Intuition for Positive Semidefiniteness

*  We know that $a\in\text{ = }\mathbb{R}^n$ is non-negative if $a\text{ }\geq{}\text{ }0$ .  This is the same thing as saying that for any $x\in\mathbb{R}^n$ , $ax^2\text{ }\geq{}\text{ }0$ , where a is > 0. Thus, we can re-write $ax^2\text{ }\geq{}\text{ }0$ as $xax\text{ }\geq{}\text{ }0$ .
*  We can generalize the scalar-based equation $xax\text{ }\geq{}\text{ }0$ to a matrix form as $x^TAx\text{ }\geq{}\text{ }0$ .  In the matrix form, the first vector x is transposed, so that the vector $x^Tx$ in this inequality is squared.  Necessarily, since the inequality is $\geq{0}$ , A must be non-negative (aka "positive semidefinite").
 *  The resultant value or quantity based on x, which we can call $q_A\left(x\right)\text{ = }x^Tx$, is also called the "quadratic form" of the matrix A.

### Assessing Matrix Positiveness, Definiteness

* Question: do we need to care about what RREF does to the matrix?
* A must be symmetric and square.  Given a square matrix $A_{mxm}$ and a mx1 vector x, multiply $x^TAx$ . A quadratic form should result.

If the matrix is <=2:
  * Solve the quadratic form for the variables.  Because the parenthetic expression is squared, it should necessarily be non-negative and thus positive semi-definite.
  * If it can be shown via the solution process that the result can never be 0, then the matrix is **positive definite** (always positive).
  * This is easy when matrix is 2x2.  If the matrix is 

If the matrix rank >2:
* If the matrix is larger than 2x2, consult the following equivalent conditions:
 * All eigenvalues are >= 0, OR
 * If there is some matrix B such that $B^TB\text{ = }A$ where all components of B are >0.  The reason this makes sense is that $B^TB\text{ = }A$ has the effect of squaring every matrix component, thus ensuring that all A components are positive.
 * The conditions for positive definiteness are similar, except that:
  * All eigenvalues are > 0, OR
  * If there is some matrix B such that $B^TB\text{ = }A$ where all components of B are >0, AND all columns of B are linearly independent.
  * All sub-determinants are positive.  That is, all sub-matrices on the diagonal also have det > 0.
 * Mutatis mutandis, the same conditions apply for negative semidefinite, negative definite matrices.
 * Assuming no row exchanges, the signs of the pivots of a symmetric matrix in rre form are the signs of its eigenvalues.  Consequently, you can use this criteria to assess positive (semi) definiteness, etc.

## Complex Matrices and Fast Fourier

### Sources
* https://www.youtube.com/watch?v=M0Sa8fLOajA

### Handling Complex Numbers in Linear Algebra

In dealing with eigenvalues we noted that a matrix of real numbers can have complex eigenvalues.  We need methods to handle complex numbers in both vector and matrix settings.  The Fourier matrix is the most important matrix for this purpose.  The Fourier Transform, and Fast Fourier Transforms or FFTs are the canonical approaches.  These two transforms have transformed entire industries.  Normally, multiplying by an nxn matrix would require n-squared multiplications, assuming we have a full matrix with orthogonal columns.  The FFT concept reduces the calculation count from $n^2$ to n $\text{log}_2\text{(n)}$, which is markedly smaller.

Consider a vector z that has complex numbers:

$$
z\text{ = }
\left[
{\begin{matrix}
z_1 \\
z_1 \\
\vdots \\
z_n \\
\end{matrix}}
\right]
$$

... where the "n" indicates that the vector is in "complex n-dimensional space".  --This is why z's column vector's are not indexed to m.  For a vector having complex numbers, calculating length as a dot product or $z^Tz$ does not work because a length should be positive, but complex numbers can yield a length <= 0.  For example (1, i) when squared would give 1 + -1 = 0.  What we need instead is a vector concept that uses complex conjugates.  Remember that a complex conjugate for a complex number has the same real part, but an imaginary component with the opposite sign.  Then the product of a pair of complex conjugates z+ and z- is z+\*z- = $\|z_1\|^2$ , or the magnitude of z1 squared.   To summarize, to take the length of z, we want $\overline{z}^Tz$ .  In general, whenever we transpose, we should take conjugates "for safety's sake".

Symbolically, the way to show that conjugates are useds in a transpose multiplication is " $z^Hz$ ", where the H stands for "Hermite", an influential mathematician in this area.  We would pronounce this as "z Hermitian z" .  If the Hermitian is done correctly, it should match the **inner product** of the vectors, which is the same thing.  This is true for both a dot product of different vectors and of identical vectors.

We also need to change the idea of symmetric matrices.  Again, these do not work if A is comple.  In order to address this problem, we now qualify A has having paired complex conjuguates in the off-diagonal positions, and only real numbers on the diagonal.  An example is:

$$
\overline{A}^T\text{ = }A\text{ = }
\left[
{\begin{matrix}
2 & {3+i} \\
{3-i} & 5 \\
\end{matrix}}
\right]
$$

These are called Hermitian matrices.  

Consider orthogonality with respect to complex numbers.  For a set of orthornomal vectors $q_1,q_2,...q_n$, for any 2 such vectors, $\overline{q}_{i}^Tq_j$ equals 0 if assuming i $\neq$ j , and 1 if i = j.  

This implies that $Q^TQ$ = I  would be composed of complex vectors, so instead we must take $Q^HQ$ = I .  Just as the word "symmetric" became "hermitian", so some people say "unitary" instead of "orthogonal".  

### Fourier Matrices

**n-by-n case**

For the full matrix F_n:

$$
F_n\text{ = }
\left[
{\begin{matrix}
1 & 1 & 1 & \ldots & 1^{n-1}\\
1 & w & w^2 & \ldots & w^{n-1}w \\
1 & w^2 & w^4 & \ldots & w^{2\left(n-1\right)} \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
1 & w^{n-1} & w^{2\left(n-1\right)} & \ldots w^{\left(n-1\right)^2} \\
\end{matrix}}
\right]
$$

... where i,j=0...n-1 . w is a special number who's nth power is 1.  There are n numbers like this.  1 is such a number.  The value of w is $w\text{ = }e^{i\frac{2\pi}{n}}$ .  --To be clear, "i" here is for the imaginary number rather than being an index.

In the complex plane, w is on the unit circle.  $i\frac{2\pi}{n}$ equals $cos\theta\frac{2\pi}{n}\text{ + }sin\frac{2\pi}{n}$ .  However, working with imaginary circle coordinates is not ideal when taking powers of a number as shown in the matrix above.  Therefore, we just calculate using $w\text{ = }e^{i\frac{2\pi}{n}}$ .  The benefit of using this number is that any power we use will still be on the unit circle, because taking it to any power will still yield a value of 1 (or -1?).  Any power value of n just ends up being a % of 360 degrees (which is 2 times pi), be cause w divides 2pi by n .

A 4x4 F4 Fourier matrix thus looks like:

$$
F_4\text{ = }
\left[
{\begin{matrix}
1 & 1 & 1 & 1 \\
1 & i & i^2 & i^3 \\
1 & i^2 i^4 & i^6 \\
1 & i^3 & i^6 & i^9 \\
\end{matrix}}
\right]
$$

Notice that the exponent is the row number times the column number (with a base 0).  The use of the value "i" in this way, raised by powers, causes the resultant values to toggle between i, -i, 1, -1 in a symmetric matrix like so:

$$
F_4\text{ = }
\left[
{\begin{matrix}
1 & 1 & 1 & 1 \\
1 & i & -1 & -i \\
1 & -1 & 1 & -1 \\
1 & -i & -1 & i \\
\end{matrix}}
\right]
$$

Strang references this latter matrix form as a "four point" matrix, I guess because it has 4 distinct possible values?  He says we use it to multiply on a vector with 4 components, using either F4 or its inverse depending on the case.  The inverse is also a nice (computation-friendly) matrix which looks very similar.  The inverse comes from the vadt that the columns are orthogonal and therefore is relatively easy to figure out.  

Fourier created this matrix, but didn't notice about it something with Gauss later did, which is that its composition makes it easy to divide into pieces so that it (or its inverse) can be multiplied very rapidly.  

The orthogonality of the F-matrix columns can be seen by noticing that the inner product of any 2 columns is 0.  For some columns, this is not obvious, but conjugation for an inner product causes their signs to change so that you do get 0.

The columns are **not** orthonormal; they all have length 2 so F4 can be made orthonormal by multiplying the matrix by 1/2.

The Hermitian of F4, that is $F_4^{H}F_4$ = I.  

$F_64$ is a matrix with a "w" value that is the 64th root of one.  That is it is $i\frac{2\pi}{64}$ .  Thus any F-matrices that are multiples of each other are connected in that they use multiples of "w" , and squaring a w will give you a w that is divided by that power.  So for example $\left(w_64\right)^2$ is $w_32$ .  As a result of this relationship, it is true for example that F_64 is connected to a matrix containing 2 copies of F_32 in which the F_32s are on the diagonal, and the remaining values are 0 matrices, like so:

$$
F_64\text{ = }
\left[
{\begin{matrix}
F_32 & 0 \\
0 & F_32 \\
\end{matrix}}
\right]
$$

.  As will be shown, the 0 matrices are crucial for multiplication purposes.  

These 2 matrices, F_64 and 2xF_32, are NOT equal.  In order to make them equal, they have to be put in a system relationship with some TBD additional matrices like so:

$$
F_64\text{ = }
\left[
{\begin{matrix}
{} & {} \\
{} & {} \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
F_32 & 0 \\
0 & F_32 \\
\end{matrix}}
\right]
\left[
{\begin{matrix}
{} & {} \\
{} & {} \\
\end{matrix}}
\right]
$$

... the additional "fixup" matrices to be added consist almost entirely of zeros.   

It's pretty abstract, but from a computation pov this is where the benefit of Fourier matrices begin to be visible.  If you think about it F_64 will take 64^2 calculations, but F32_x only takes 2x32^2 + "fixup" calculations, which is much less.

The matrix to the right of the 2xF_32 matrix is a permutation matrix P consisting of odd and even numbers.  What it does is to take the even numbered components, and then the odd-numbered components.  The effect is to separate an original vector into even and odd components, so that the 2xF_32 matrix can process them separately.  Then we will re-assemble the results.

The left side of the 2xF_32 is structured like so:

$$
\left[
{\begin{matrix}
I & D \\
I & -D \\
\end{matrix}}
\right]
$$

.  That is, it is constucted of identity and diagonal matrices.  The "fix up" cost computationally is therefore the cost of multiplying by D, because there's essentially no cost to processing the I portion or the Permutation matrix part.  The "fix up" cost will be n multiplications -- e.g. for F_32 it will be 32 multiplications.

The diagonal matrix D in this equation is powers of w, ordered on the diagonal from w_0=1 to n_31 in this example.

The above outlines the concept of FFT.  As you would guess, the 32s in this example can be further decomposed in this way, for added computational benefit.  In other words, FFT processing is recursive.  If the original matrix is entirely broken down into "fixup" components, there will be $\frac{1}{2}nlog_2n$ computations to do.

To give an example of computation savings in real numbers, a common case would be to have n=1024 components in n=1024 computations, and $n^2$ is > 1M.  1/2nlog_2n however is only 1024 (10/2) = 5 x 1024 = 5120. 


## Singular Value Decomposition

### Sources:
* Eigendecomposition: https://www.youtube.com/watch?v=KTKAp9Q3yWg&t=84s
* SVD simple example: https://youtu.be/NGHBniMyteo
* MIT: https://www.youtube.com/watch?v=TX_vooSnhm8

### Introduction

* Singular Value Decomposition, or SVD , **can be applied to ANY matrix whatsoever** (whereas eigendecomposition requires a square matrix of full rank).
* Recall that a matrix A can be decomposed into these forms:
  * $A\text{ = }Q\Lambda{}Q^T$ , where Q is a matrix of orthogonal unit vectors.
  * $A\text{ = }S\Lambda{}S^{-1}$ , where S is a symmetric matrix.
* SVD uses symmetric positive definite matrices, which are critical because their eigenvectors were orthogonal due to their symmetry, which means that they can be used to produce an orthogonal matrix Q.  Because these matrices are positive definite, the $\Lambda$ will be positive.
  * When the matrix to be decomposed in SVD is symmetric positive definite, we can use the same matrix Q on both sides of the Lambda diagonal matrix (because of symmetry) for SVD as shown in the equation $A\text{ = }Q\Lambda{}Q^T$.  We don't need a different matrix U and V on left and right sides, as will be shown in the SVD process below.
  * The equation $A\text{ = }S\Lambda{}S^{-1}$ (S is a "symmetric matrix") by contrast is usually not useful, because the eigenvector matrix is usually not orthogonal.  --This situation will not be used for SVD. What we want instead is **"orthogonal times diagonal times orthogonal"**.  

When we do singular value decomposition, were are looking for an orthogonal basis that remains orthogonal when taken from the row space to the column spaces (i.e. when A operates on x).  That is, we are looking for a matrix of vectors multiplied by A that remain orthogonal to each other and do not change direction (though they may change extent or reverse direction).  We can easily find the orthogonal basis of a row space using the Graham-Scmidt process.  However, finding an orthogonal basis in the row space is no guarantee that the same vectors will be an orthogonal basis in the column space.  

So far we've not discussed the nullspace (of the rows) in the discussion.  Nullspaces do not present a problem; they will show up on the diagonal of sigma. The difficulty is to find the orthogonal basis in R(A) Rn that remains orthogonal in C(A) Rm. 

Say that the orthogonal vectors in C(A) are "vs".  We can consider this orthogonal relationship from R(A) to C(A) as 

$$
A
\left[
\begin{matrix}
\vdots & \vdots & \ldots & \vdots \\
v_1 & v_2 & \ldots & v_r \\
\vdots & \vdots & \ldots & \vdots \\
\end{matrix}
\right]
$$

.  Notice that the vectors are up to $v_r$ , the basis of A, rather than $v_n$ .  This is in keeping with the assertion that SVD works on any matrix, including those where r < n .  

In this construal, A is multiplying each vector in turn.

We can construe the vectors v in V as unit vectors u in an orthormal matrix U.  Further, when we contextualize this vector u in the equation $Ax\text{ = }\lambda{x}$ , we can change Ax to Av as shown above and we can change $\lambda$ to $\sigma$ to denote this new orthonormal relationship.  The updated formula is then $\sigma_1u_1\text{ = }Av_1$ . Implicitly, sigma is arranged in such a way (e.g. a diagonal matrix) that it can multiply a vector u just as A does v.  This is done for each vector in A in turn, so for example $\sigma_2u_2\text{ = }Av_2$ .  

Note that because U and V are orthonormal, they are **square, orthogonal** matrices.  This is important below.

If we express these processes fully in a matrix equation, we have AV = $U\Sigma$ , where V is the matrix of orthogonal vectors in A's rowspace, and U is the matrix of orthogonal vectors in A's columnspace, and Sigma is the diagonal matrix of sigma values.  Again, our goal is to find an orthogonal basis in the rowspace of A that will still be an orthogonal basis in the column space of U , so that we've sort of diagonalized (aka decomposed) the matrix into its orthogonal and multiplier (sigma) parts.  Note that V can be thought of as a matrix on the left that facilitates the diagonalization of A represented on the right.  Note also that although the bases are said to be orthogonal on both sides of the equation, the differing letters V and U connote that they are *not necessarily identical.*  If the matrix were *orthonormal* on both sides, when we could have just one letter/matrix "Q" in this equation.  

### Motivation and Meaning of "Singular Values"

* Consider first the idea of an eigenvector, which is a vector x which is parallel to the original vector x even after it is transformed by A.  Logically, the parallelism of the eigenvector cannot be shifted by any eigenvalue $\lambda$ which acts on it, since that eigenvalue would act on all of the eigenvectors equally and thus keep the same proportions.  **It follows that the role of the eigenvalue is only to indicate the direction of the eigenvector and how much it stretches that eigenvector.**  The eigenvalue could reverse the eigenvector's direction (sign), but not its parallelism to x.
* The cannonical formula for eigenvectors and eigenvalues is $Ax = \lambda{x}$ .  A **singular value** $\sigma$ is the square root of eigenvectors from $AA^T$  for A in this formula .
  * As a consequence:
    * $\sigma$ will always be positive
    * relative to other singular values for the matrix, the size of the singular values must indicate vector components of A stretch the vector x the most.  This relative size can be taken as an indicator of importance.
    * additionally, a subset of the singular values will account for the majority of the change that happens to the vector x.  The implication is that a sufficient estimate of the effect on x can be had with a smaller set of columns or features, which pays off in computation costs and efficiency.

### Preparing for SVD: Eigendecomposition

#### Motivation

*  Note: "eigendecomposition" is also called (e.g. by Strang) "diagonalization".  The latter term is more encompassing, since it can accomodate both eigendecomposition and SVD.
*  A primary reason for performing eigendecompositions is that they simplify the common data science task of computing a matrix taken to a power.
  *  A basic of linear algebra is that a matrix is multiplied on a vector in order to map it to another vector, or equivalently, to map it into a new space.
  *  In real life, this often involves applying this linear transformation at every step of an algorithm.  This often ends up being equivalent to multiplying a vector by a matrix taken to a power.  Without eigendecomposition, taking a matrix A to the power of p involves $log_2\left(p\right)$ such computations --this fact reflects the max number of pair-wise computational shortcuts you can take without eigendecomposition.
  *  As shown below, eigendecomposition transforms (decomposes) A into $U\Lambda{}U^{-1}$ .  This can then be decomposed into p $u\lambda{u^T}$ computations multiplied times each other.  Any incidence of $uu^T$ can them be factor out as an identity I, leaving the simplification $u\Lambda^pu^{-1}$, which is much easier to compute.

#### Contrast: Eigendecomposition vs SVD
*  Eigendecomposition can be done only on square matrices; SVD can be done on ANY matrix.
*  Eigenvalues are used along with eigenvectors in eigendecomp; SVD uses the **square root** of eigenvalues instead of the original eigenvalues themselves; these square roots are called "singular values".
*  Eigendecomposition does not require that the decomposed matrices be orthonormal; SVD does require that the decomposed matrices be orthormal. 

#### Definition
*  For a square matrix (only square matrices have Eigenvectors|values), the eigendecomposition is a $U\Lambda{}U^{-1}$ which breaks A into p individual $u\lambda{u^T}$ matrices, requiring only 2 matrix multiplications, regardless of the complexity.

#### Performing an Eigendecomposition:

Suppose we have matrix A:

$$
A\text{ = }
\left[{\begin{matrix}
1 & 4 \\
9 & 1 \\
\end{matrix} }\right]
$$

*  Calculate the eigenvalues, in this case $\lambda_1\text{ = }7$ , $\lambda_2\text{ = }-5$ .
*  Calculate the eigenvectors, in this case:

$$
v_1\text{ = }
\left[
\begin{matrix}
2 \\
3 \\
\end{matrix}
\right]
\text{ corresponds to }\lambda_1\text{, and }
v_2\text{ = }
\left[
\begin{matrix}
2 \\
-3 \\
\end{matrix}
\right]
\text{ corresponds to }\lambda_2
$$

* Normalize the eigenvectors, meaning that they sum to 1:

$$
u_1\text{ = }
\left[
\begin{matrix}
\frac{2}{\sqrt{13}} \\
\frac{3}{\sqrt{13}} \\
\end{matrix}
\right]
\text{ corresponds to }\lambda_1\text{, and }
u_2\text{ = }
\left[
\begin{matrix}
\frac{2}{\sqrt{13}} \\
\frac{-3}{\sqrt{13}} \\
\end{matrix}
\right]
\text{ corresponds to }\lambda_2
$$

* Put the above results into the following format, which is the same as the $Ax\text{ = }\lambda{x}$ equation:

  *  $Au_1\text{ = }\lambda_1u_1$
  *  $Au_1\text{ = }\lambda_1u_1$

  * The left and right sides of these equations have different structures, because the left is a matrix times a vector, while the right is a value times a vector, so you need to put the right side lambdas into a matrix format, with the equation becoming a matrix system like so:
 
$$
\text{A}
\left[
\begin{matrix}
\vdots & \vdots \\
u_1 & u_2 \\
\vdots & \vdots \\
\end{matrix}
\right]
\text{ = }
\left[
\begin{matrix}
\vdots & \vdots \\
u_1 & u_2 \\
\vdots & \vdots \\
\end{matrix}
\right]
\left[
\begin{matrix}
\lambda_1 & 0 \\
0 & \lambda_2 \\
\end{matrix}
\right]      
$$

Note: in this construal, $u_1,u_2$ are both vectors comprising the matrix U.

* In matrix form, this formula is now: $AU\text{ = }U\Lambda{}$ , which can be re-written to isolate A as: $A\text{ = }U\Lambda{}U^{-1}$ .
  * **This final formulation is what is known as the "eigendecomposition".**  It is so called because it breaks A into its component matrices in a way that isolates the eigenvalues.
  * To see that this works, you can multiply out the above simple matrices.

### Computing Singular Value Decomposition SVD

* Recall that:
  * Rank is the number of linearly independent columns in a matrix, or equivalently the number of pivots, and that the rank p must be less than or equal to n columns.
  * the eigendecomposition only applied to diagonalizable square matrices.
    * the SVD applies to non-square matrices, so it extends decomposition to a wider set of matrix types.
  * Eigendecomposition takes the form $M_{mxm}\text{ = }U\Lambda{}U^{-1}$ , where M is a diagonalizable square matrix, U is the matrix of normalized eigenvectors, and $\Lambda$ is the diagonal matrix of eigenvalues.
   * A consequence of being able to decompose M into these 3 right-side components is that it can be expressed as the sum of "atomic" **rank 1** matrices like:

      $$M\text{ = }\sigma_1u_1v_1^T\text{+,...,+}\sigma_pu_pv_p^T$$

     , where:
       * $\sigma$ is a singular value coefficient,
       * u is a vector of m rows (i.e. an mx1 matrix),
       * and v is a vector of n columns (i.e. an 1xn matrix).
     * each u and v multiplied together make a rank 1 matrix.
       * A rank 1 matrix is a matrix that can be expressed as the multiplication of a mx1 vector and a 1xm vector.  Usually this is expressed as the multiplication of $uv^T$ .  It sounds kind of like a dot product but the result is a matrix and you don't add the components to get a single number.
         * the reason it is not a single number is that the column in u is multiplying the row in v, so procedurally you get a matrix.  If u and v were reverse in order, you would get a single number.
         * v is the transpose of u.  this is necessary in order to get a square, symmetric matrix
         * each u,v pair is thus made from a single row from the original matrix.
     * these atomic matrices must be linearly independent from each other in order to be summed this way.
   * We can write this summation of atomic matrices in a higher-level matrix form as:

$$
M\text{ = }
\left[{\begin{matrix}
\vdots & \cdots & \vdots\\
u_1 & \cdots & u_p \\ 
\vdots & \cdots & \vdots\\
\end{matrix} }\right]
\left[{\begin{matrix}
\sigma_1 & {} & {} \\
{} & \cdots & {} \\ 
{} & {} & \sigma_p \\
\end{matrix} }\right]
\left[{\begin{matrix}
\cdots & v_1 & \cdots \\
\vdots & \vdots & \vdots \\ 
\cdots & v_p & \cdots \\
\end{matrix} }\right] 
$$
  
where the dimensionality of each matrix is $\Sigma\text{:pxp}$ , and V:pxn .  The multiplication of all the matrices will result in a final matrix of mxn, matching that of the original matrix A .

Just as with eigendecomposition, U will be an orthonormal matrix, and thus V will as well.  Also remember that each column in U is indepdendent.  As a consequence of these facts, $U^TU$ and $V^TV$ will both be reducible to identity matrices.  

All the sigmas are on the diagonal of $\Sigma$ . 

Notice that multiplying both sides by $V$ will yield $MV\text{ = }U\Sigma{}$ and similarly that multiplying by $U^T$ will yield $U^TM\text{ = }\Sigma{}U^T$ .  
*  In $MV\text{ = }U\Sigma{}$ , the columns of V which had been the rows of $V^T$ are known as the **right singular vectors** of M.
*  In parallel, since U has been on the left of $\Sigma{}$ , the vectors in U are called the **left singular vectors** of M.
*  Sigma itself is called the ** singular values** of M.

Presumably, the "singular" bit references the isolation of each column in M when calculating $\sigma$ . 

### Computing SVD : Simple Example

Given the matrix 

$$
A\text{ = }
\left[
{\begin{matrix}
1 & 1 \\
0 & 1 \\
-1 & 1 \\
\end{matrix}}
\right]
$$

Let A = $U\Sigma{}V^T$ be svd of A .

Steps:
* Compute V = $A^TA$:

$$
A^T\text{ = }
\left[{\begin{matrix}
2 & 0 \\
0 & 3 \\
\end{matrix} }\right]
$$

* Find eigenvalues of $A^TA$ :

$\lambda^2\text{ - }s_1\lambda\text{ + }s_2\text{ = }0$ is the characteristic equation of the matrix $A^TA$ :
* $s_1\text{ = }T\left(A^A\right)\text{ = 2 + 3 = 5}$ , where T = trace.
* $s_2$ = determinant of matrix = ad - bc = 6 - 0 = 6 .

Plugging these into the characteristic equation, we get: $\lambda^2\text{ - }5\lambda\text{ + }6\text{ = }0$ : $\lambda\in\text{ = 3,2}$ .  These are the **eigenvalues** .  We don't technically have to write these in decreasing order, but for organizational reasons it is customary to do so.  This is so you can more quickly find the most important sigmas later.

* Find eigenvectors based on eigenvalues:
  * Let x1 = (a, b) be e.v. of $A^TA$ .  Then $\left(A^TA\right)x_1\text{ = }\lambda{x_1}$ :

$$
\left[{\begin{matrix}
2 & 0 \\
0 & 3 \\
\end{matrix} }\right]
\left[{\begin{array}
a \\
b \\
\end{array}}\right]
\text{ = }
3
\left[{\begin{array}
a \\
b \\
\end{array}}\right]
$$

and 

-a + 0b = 0
0a + 0b = 0

Both equations are the same.  Therefore, we can toggle a = 0 and b = 1 (or vice-versa).  These values satisfy both equations and therefore can serve as an eigenvector.  We then normalize x_1 = (0,1) --> u_1 = (0,1) .  The same process yields x_2 = (1,0) --> x_2 = (1,0) .

The v matrix of normalized eigenvectors is thus:

$$
V\text{ = }
\left[{\begin{matrix}
0 & 1 \\
1 & 0 \\
\end{matrix} }\right]
$$

.  

* Find $V^T$, which is the same since V is a symmetric matrix.

$$
V^T\text{ = }
\left[{\begin{matrix}
0 & 1 \\
1 & 0 \\
\end{matrix} }\right]
$$

.

* Compute $\Sigma$ matrix:
  * Note that the order of sigma must be the same as the order of A.
  * Find sigmas, which are simply the sqrts of the eigenvectors above:
    * $s_1\text{ = }\sqrt{\lambda_1}\text{ = }\sqrt(3)$
    * $s_2\text{ = }\sqrt{\lambda_2}\text{ = }\sqrt(2)$
  * Remember that the number of non-zero singular values (and eigenvalues) must be equal to the rank p of the matrix.
  * the matrix $\Sigma$ is thus:

$$
\Sigma
\left[{\begin{matrix}
\sqrt{3} & 0 \\
0 & \sqrt{2} \\
0 & 0 \\
\end{matrix}}\right]
$$

-- Note that a row of 0s are added so that Sigma fulfills its dimensionality requirements.  It should be equal to the dimensions of A.

* Compute Matrix U = $AA^T$:

$$
$AA^T$\text{ = }
\left[{\begin{matrix}
2 & 1 & 0 \\
1 & 1 & 0 \\
0 & 1 & 2 \\
\end{matrix}}\right]
$$

Let $\lambda^3\text{ - }s_1\lambda^2\text{ + }s_2\lambda\text{ - }s_3\text{ = }0$ be the characteristic equation of $AA^T$ .

### SVD Example 2: Real Numbers

Say we had a 2x2 matrix like 

$$
A2\text{ = }
\left[
\begin{matrix}
4 & 4 \\
-3 & 3 \\
\end{matrix}
\end]
$$

... for this matrix, we again want to find that vectors that remain orthonormal from R(A) to C(A).  So we are seeking:
* $v_1,v_2$ for R(A) in $R^2$ .
* $u_1,u_2$ for C(A) in $R^2$ .
* $\sigma_1,\sigma_2$ where both scaling factor values are > 0 .

Vectors v (to each other) and vectors u will be orthonormal as well.  

If there is nullspace in R(A) or C(A), we want to add in the bases for those as well. These are added as [special solutions? 0 vectors?] in U and V, and as off-diagonal 0s in $\Sigma$ .  This fills V out to n and U out to m per the size of the original mxn matrix A.  

Returning to matrix A2 above: it is problematic because it isn't symmetric.  We still want to transform A2 into 

$Av_1\text{ = }\sigma_1u_1$
$Av_2\text{ = }\sigma_2u_2$

... and arrange them in the matrices $AV\text{ = }U\Sigma$ .  

If we mulltiply both sides of $AV\text{ = }U\Sigma$ we get $A\text{ = }U\Sigma{}V^{-1}$  .  Because V is a square, orthogonal matrix (unlike A, which may not be).  This means that $V^{-1}$ is the same as $V^T$, so we can say that $A\text{ = }U\Sigma{}V^{-1}\text{ = }U\Sigma{}V^T$ .  

There is a problem with this configuration, however, because it contains 2 orthonormal matrices.  In order to solve for their content, it is necessary to isolate them one at a time.  In order to do this, we multiply both sides by $A^T$ -- the left side by $A^T$, and the right side by its re-written form.  A is $U\Sigma{}V^T$, so $A^T$ is $VU^T\Sigma{}^T$, and 

$$A^TA\text{ = }VU^T\Sigma{}^TU\Sigma{}V^T$$

... at first this looks more complicated, but the U terms in the middle reduce to I, leaving $V\Sigma^T\Sigma{}V$ .  The $\Sigma$ matrices are diagonal matrices, so their product is just a diagonal of squared sigmas.  Thus **we have isolated V** , which is the current goal, in the reformulation of $A^T$ :

$$
A^TA
\text{ = }
V
\left[
\begin{matrix}
\sigma_1^2 & {} & {} \\
{} & \ddots & {} \\
{} & {} & \sigma_r^2 \\
\end{matrix}
\end]
V^T
$$

The matrices V are in fact  eigenvectors, and the sigmas (remember) are eigenvalues.  $A^TA$ has actually be turned into $Q\Lambda{}Q$ .  This is possible because $A^TA$ is by definition symmetric positive definite.  

So far we have isolated the V matrices.  To solve for U, we can again multiply the equation above by A-transpose, except now we multiply it as $AA^T$ instead of $A^TA$ .  This will cause the Vs to be in the middle of the right side of the equation, instead of the U matrices.  Then $V^TV$ will drop out as I, and we can solve for the isolated Us via a similar diagonalization/decomposition.

Thus the overall picture is that the Vs are the eigenvectors of $A^TA$, and the U's are the eigenvectors of $AA^T$ .  The $\Sigma$ matrices contain the positive square roots of the eigenvalues.  

Returning to the example matrix above, we will now call "A2" as "A" for convenience:

$$
A2\text{ = }
A\text{ = }
\left[
\begin{matrix}
4 & 4 \\
-3 & 3 \\
\end{matrix}
\end]
$$

$$
A^TA
\left[
\begin{matrix}
25 & 7 \\
7 & 25 \\
\end{matrix}
\end]
$$

$$
\text{The eigenvectors of }
A^TA
\text{ are }
\left[
\begin{matrix}
1 \\
1 \\
\end{matrix}
\end]
\text{ and }
\left[
\begin{matrix}
1 \\
-1 \\
\end{matrix}
\end]
$$

... this is allegedly clear (says Strang) because if we multiply the matrix by (1,1) we get 32(1,1).  The square root of this eigenvalue will be sigma for $A^TA$ .  
Because of the trace, the second eigenvalue must be 18.  
Remembering that we are creating orthonormal matrices, we must also normalize these eigenvectors as $\left(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}\right)$ , and $\left(\frac{1}{\sqrt{2}},\frac{-1}{\sqrt{2}}\right)$ .  These normalizations do not change the eigenvalues.

Putting together all these pieces so far, A is :

$$
A
\text{ = }
\left[
\begin{matrix}
4 & 4 \\
-3 & 3 \\
\end{matrix}
\end]
U
\left[
\begin{matrix}
\sqrt{32} & 0 \\
0 & \sqrt{18} \\
\end{matrix}
\end]
\left[
\begin{matrix}
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} &  \frac{-1}{\sqrt{2}} \\
\end{matrix}
\end]
$$

To find the U's, we do the following:

$$AA^T\text{ = }U\Sigma{}V^TV\Sigma^TU^T\text{ = }U\Sigma{}\Sigma^TU^T$$

$$
AA^T
\text{ = }
\left[
\begin{matrix}
32 & 0 \\
0 & 18 \\
\end{matrix}
\end]
$$

... luckily, the result is diagonal, so the first eigenvector is (1,0) and the second is (0,1), with eigenvalues of 32 and 18.  Note that the eigenvalues of $A^TA$ and $AA^T$ are the same.  This is a known property: the eigenvalues of AB and BA are identical. 
The two eigenvectors together make a 2x2 identity matrix. Thus the whole equation is now:

$$
A
\text{ = }
\left[
\begin{matrix}
4 & 4 \\
-3 & 3 \\
\end{matrix}
\end]
\left[
\begin{matrix}
1 & 0 \\
0 & 1 \\
\end{matrix}
\end]
\left[
\begin{matrix}
\sqrt{32} & 0 \\
0 & \sqrt{18} \\
\end{matrix}
\end]
\left[
\begin{matrix}
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} &  \frac{-1}{\sqrt{2}} \\
\end{matrix}
\end]
$$

... and indeed if you multiply out the right side of this equation, you will get the left side. \[Actually, Strang recorded an error in this equation, but as a method example at least it is correct.\]

### SVD Example 3: Real Numbers, Rank 1 Singular Matrix

Suppose we had a singular matrix:

$$
A
\text{ = }
\left[
\begin{matrix}
4 & 3 \\
8 & 6 \\
\end{matrix}
\end]
$$

... obviously the rows are not independent and r < m, r < n.  Nevertheless, SVD can be done on this matrix.

Given the properties of this matrix, it is clear that the row space is a line extending through multiples of (4,3), while null space will consist of lines perendicular to that line.  The column space is a line going through multiples of (4,8) , and the nullspace of A-transpose is perpendicular to that.  Choosing the orthogonal bases for this matrix is thus no problem

Remember that matrices U and V should be a orthonormal.  For V there is only 1 vector (4,3) to choose from so we make it into a unit vector as $v_1\text{ = }\left(\frac{4}{5},\frac{3}{5}\right)$ or equivalently (.8,.6) .  For $v_2$, the vector is in the nullspace direction, relative to A, so it must be (.6,-.8).

Correspondingly $u_1\text{ = }\left(\frac{1}{\sqrt{5}},\frac{2}{\sqrt{5}}\right)$  .  Again, to complete the nullspace in an orthonormal manner, $u_2\text{ = }\left(\frac{2}{\sqrt{5}},\frac{-1}{\sqrt{5}}\right)$

Because $A^TA$ is a size 2x2 matrix of rank 1, we know that one eigenvalue must be 0.  Its trace is 125, so the other eigenvalue must necessarily be 125.  Sigma is the square root of the eigenvalue, so sigma is $\sqrt{125}$ .

Continuing with the SVD, we put the parts A = $U\SigmaV^T$ together as:

$$
A
\text{ = }
\left[
\begin{matrix}
4 & 3 \\
8 & 6 \\
\end{matrix}
\end]
\text{ = }
\frac{1}{\sqrt{5}}
\left[
\begin{matrix}
1 & 2 \\
2 & -1 \\
\end{matrix}
\end]
\left[
\begin{matrix}
\sqrt{125} & 0\\
0 & 0 \\
\end{matrix}
\end]
\left[
\begin{matrix}
.8 & .6 \\
.6 & -.8 \\
\end{matrix}
\end]
$$

... we we abstract the $\frac{1}{\sqrt{5}}$ out of U.  

### SVD: Review of Basic Activity

Remember that:
* In V:
  * $v_1$ up to $v_r$ is an orthonormal basis for the row space.
  * $v_{r+1}$ up to $v_n$ is an orthonormal basis for the null space. 
* In U:
  * $u_1$ up to $u_r$ is an orthonormal basis for the column space.
  * $u_{r+1}$ up to $u_m$ is an orthonormal basis for the (left) null space of $A^T$ .

-- It is these bases *which make the matrix diagonal* , AND $Av_i\text{ = }\sigma_iu_i$ .
-- The overall insight about this summary is that it diagonalizes the matrix into its consituent components while correctly accounting for all 4 fundamental subspaces.  





