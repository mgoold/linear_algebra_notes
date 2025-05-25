
# Primary Sources:
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/ax-b-and-the-four-subspaces/the-geometry-of-linear-equations/

## Overview of Linear Algebra

Sources:
* Strang: https://youtu.be/0oBJN8F616U

Linear algebra begins with vectors, then progresses to matrices and then subspaces.

Vectors are used in [linear combinations](#linear-combination) -- this is the key thing you can do with them.
A matrix is a set of vectors displayed as a box of number columns.  See the section on [geometry of linear equations](#geometry-of-linear-equations) for more on this.

## Geometry of Linear Equations

Sources:
* Strang: https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/resources/lecture-1-the-geometry-of-linear-equations/
* Related Recitations: 

Suppose we have 3 linear equations:

$$2x - y = 0$$
$$-x + 2y - z = -1$$
$$    -3y + 4z = 4$$

In linear algebra, we always construe these equations as a system in a matrix:
$$Ax=b$$

$$
\
  \left[ {\begin{array}{cc}
   2 & -1 & 0\\
   -1 & 2 & -1\\
   0 & -3 & 4\\
  \end{array} } \right]
\
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}=
\begin{bmatrix}
0 \\
-1 \\
4 \\
\end{bmatrix}
$$

... where by convention A is the matrix of scalars which is said to "act on" or "multiply" the variable x to get the result vector b.

### Visual Picture of 3 Equations in 3 Unknowns

Sources:
Strang, p35.

The main thing to understand about the below picture is how the 3 equations, construed as *Ax*, impact the result *b*.

This picture is a graph of the vectors for 3 different equations in 3 unknowns in 3d space.  These equations point off in 3 different directions, so they really do extend into 3d space, but it's quite possible to have 3 equations that would turnout to be just multiples of each other and thus would really only extend into 2 or even 1 dimension.  Anyway, these equations are unrelated to other content in this doc.

![Screenshot 2025-02-28 at 18 39 04](https://github.com/user-attachments/assets/b3c6101f-4f03-40f3-a75c-3c89273d69d8)

Contemplating things a bit, you can see that by adjusting the values of variables x,y, and z, you'd eventually be able to get **coordinates for any point b in 3 dimensional space.**

**-- This ability to make b into any coordinate in a specified n-dimension space is what Strang and others mean when they talk about "filling the whole plane", "filling all of 3d space", etc.**

### Coefficient Matrices

The matrix of scalars on the left that is multiplied by the variable (x,y,z) vector is sometimes called a "coefficient" matrix.

### The "Basis" of A System of Linear Equations

Sources:
* Strang: https://youtu.be/0oBJN8F616U?t=2228

The number of independent linear equations, i.e. the number of dimensions it fills, is sometimes called the "basis".  The basis may be smaller than the number of equations.  E.g. you might equations for 3 lines, but the basis of the system would be 2, because one of the equations is dependent on another.

Note that if the basis is the same as the number of equations -- meaning that all the equations are linearly independent, then **the matrix should be invertible.**  Strang says that "an invertible matrix is one with a basis sitting in its columns.  It is a transform that has an inverse transform."  ??



## How to Multiply $Ax=b$.

Notes:

Given an example matrix * vector Ab pair:

$$
\
  \left[ {\begin{array}{cc}
   2 & 5\\
   1 & 3\\
  \end{array} } \right]
\
\begin{bmatrix}
1 \\
2 \\
\end{bmatrix}
$$

There are two ways to multiply it:

### Column-Wise:

$$
1\begin{bmatrix}
2 \\
1 \\
\end{bmatrix}+2\begin{bmatrix}
5 \\
3 \\
\end{bmatrix}=\begin{bmatrix}
12 \\
7 \\
\end{bmatrix}
$$

### Row-Wise:

You can also do it in row*vector pairs for each row in the matrix:

2\*1 + 5\*2 = 12

1\*1 + 3\*2 = 7

This is a form of taking the dot product in that the components 2 vectors are multiplied pair-wise to yield a single result vector.

Either way you'll end up with a result vector (12,7).  

We should always think of Ax as a combination of the columns of A.

## 3 Ways to Write $Ax=b$.

Notes:
There are 3 equivalent ways to write this equation system:

### Row-wise Linear Equations
The "row picture" of a linear system is a common list of equations that you can diagram and possibly solve simultaneously if the lines intersect.  It does not use linear algebra notations.

### Column-wise - Linear Combinations

The column-wise view of linear equations takes each set of variables, and the results, as a column modified by a variable:

$$x\begin{bmatrix}
2 \\
-1 \\
0 \\
\end{bmatrix}+y\begin{bmatrix}
-1 \\
2 \\
-3  \\
\end{bmatrix}+z\begin{bmatrix}
0 \\
-1 \\
4  \\
\end{bmatrix}=\begin{bmatrix}
0 \\
-1 \\
4  \\
\end{bmatrix}
$$

This way of writing the linear equation system is known as a **linear combination** and is the most fundamental operation in linear algebra.

### Linear Equation Systems as a Matrix

Finally, the system of linear equations can be written maxtrix wise in the $Ax=b$ format shown above.

If the linear equations are all **independendent** -- that is if they do not line on the same line or plane, and if no one of them equals a linear combination of another one, then modifying x,y,z (or however many dimensions) can be made to fill all of that space.

In general, a system of linear equations can fill the number of independent equations it has.

A linear equation system where one or more equations are combinations of others in the set is said to be a **singular matrix**, and its equations are **dependent** on other equations.

Notice that geometrically terms line "plane" and "space" become relative.  In a 9-dimension matrix, if the 9th column was dependent on the 8th and was a combination of it, we could say that the matrix actually gives a kind of 8-dimension "plane" in 9-dimension space.  In fact this "plane" can be called a "subspace" of 9 dimensions.

## Matrix Multiplication (Five Ways)

Sources:
* Strang, p68.
* Strang: https://youtu.be/FX4C-JpTFgY

### Most Common Method: A row times all B Columns

By convention, the components of a matrix are indexed first by row, then by column.  So the component in row 1, column 1 of matrix A would be subscripted $a_{1,1}$.  In any matrix the rows are conventionally designated by i, and the columns j.  

Here is a picture from Strang p68:
![Screenshot 2025-02-26 at 20 58 06](https://github.com/user-attachments/assets/dccd5090-492c-434a-a7c8-d7e1387a9a60)

Notice that in matrix A, the row i (2) is held constant, while the columns progress from 1 to 5.  In matrix B, the column j (3) is held constant while the rows progress from 1 to 5.  When the matrices are multiplied in this example, $a_{21}$ is multplied by $b_{13}$, $a_{22}$ is multplied by $b_{23}$ and so on.  What matters is that the components from A and B are paired and multiplied together on a A column j = B column i basis.  All of these products are summed together and this becomes the C matrix entry $AB_{ij}$ as illustrated above. This summation is a **dot product**, and the result matrix C is this a matrix of dot products.

Because components from A and B are paired and multiplied together on a A column j = B column i basis, **you can only multiply matrices if the number of columns in A = number of rows in B.**  

Some other things follow:
* Notice the irregular shapes of A and B in the above illustration.  Matrix B can have any number of columns, as long as it has the same row count as the number of columns in matrix A.
* Given that matrix A has shape (m rows X n columns), and matrix B has (n rows X p columns) entries, result matrix C will have shape (m rows X p columns).
* Matrix multiplication can only be done on square matrices if they are the same size.

This is definitely a picture = 1k words thing.  Here is another picture illustrating the matrix multiplication process:

<img width="643" alt="Screenshot 2025-01-28 at 19 17 09" src="https://github.com/user-attachments/assets/7fdf93a0-0d7b-4a7d-87e1-17b74253fc52" />

Generally the notation for dot product $c_{i,j}$ in result result matrix C, given that AB = C is:

$$c_{i,j}\text{ = }\left(\text{row i of A}\right)\cdot\left(\text{column j of B}\right)$$
$$\text{ = }a_{i,1}b_{1,j}\text{ + }a_{i,2}b_{2,j}\text{ + ...}a_{i,n}b_{n,j}$$
$$=\sum_{k=1}^na_{i,k}b_{k,j}$$

**The following are alternate matrix multiplication methods.**

### Matrix Multiplication Method 2: Matrix A Times a Column of B

Sources:
* Strang, p68.
* Strang: https://youtu.be/FX4C-JpTFgY

Assume that matrices A and B have valid shapes for multiplcation (A row count = B column count). Then it is also valid to think of matrix muliplication as multiplying the entire matrix A times a column of B, for one column B at a time.  Doing it this way is an instance of the common Ax = b process of multiplying a matrix times a vector, but in this case the result vector b would be a column of results in C.  

Here is an illustration re-using the same matrices:

<img width="490" alt="Screenshot 2025-02-27 at 13 39 20" src="https://github.com/user-attachments/assets/ee617ec1-96a8-478a-bf7b-b4fa7b1e07f4" />

We can say that the columns of C are linear combinations of the matrix A times a column vector of B.

### Matrix Multiplication Method 3: Row of Matrix A times a Rows of B

We can also consider matrix multiplication as taking a single row of A times the matrix B to yield a single **row** of C.
That is, the rows of C in this construal are linear combinations of B times a row of A.

Here is an illustration re-using the same matrices:

<img width="503" alt="Screenshot 2025-02-27 at 14 02 32" src="https://github.com/user-attachments/assets/0288c59f-d508-4856-a0af-2f9f2335dbee" />

### Matrix Multiplication Method 4: Column of matrix A times Row of matrix B

It's worthwhile to to consider an exercise of multiplying a single column times a row vector (that is, a transposed column vector).
For example, we can multiply

$$
\begin{bmatrix}
2 \\
3 \\
4 \\
\end{bmatrix}\[\text{1 6}\]
$$

This is technically the same as multiplying a 3x1 matrix times a 1x2 matrix.  This will yield a 3x2 matrix:

$$
\
  \left[ {\begin{array}{cc}
   2 & 12\\
   3 & 18\\
   4 & 24\\
  \end{array} } \right]
\
$$

.

**Notice**: all of these lines lie on the same line passing through vector (1,6).  All the row vectors and column vectors are in the same direction.  Another way of saying this is that the **"row space" is just a line**, namely the line through vector (1,6).  Likewise, the "column space" is also on a line.  All the columns lie on the line passing through vector (2,3,4).  The result matrix is thus very minimal because the column and row vectors multiplied to create it are constrained to 1 dimension.  

#### AB = Sum of (Columns of A)(Rows of B)

We can also multiply columns of A times rows of B.  Again, the A column count = B row count condition must be true.  We can then think of the AB multiplication as a linear combination of column*row pairs like so:

$$
\
  \left[ {\begin{array}{cc}
   2 & 7\\
   3 & 8\\
   4 & 9\\
  \end{array} } \right]
\
\
  \left[ {\begin{array}{cc}
   1 & 6\\
   0 & 0\\
  \end{array} } \right]
\
=\begin{bmatrix}
2 \\
3 \\
4 \\
\end{bmatrix}\[\text{1 6}\]\text{ + }
\begin{bmatrix}
7 \\
8 \\
9 \\
\end{bmatrix}\[\text{0 0}\]
$$

.

### Matrix Multiplication Method 5: Block-wise Multiplication

Suppose that we have 2 matrices A and B, and the A column count = B row count condition for matrix multiplication is true.  In this example, we have 2 square matrices of equal size, but they do not have to be square.

Suppose A & B are both 4 x 4 matrices:

$$
A=\
  \left[ {\begin{array}{cc}
   a_{11} & a_{12} & a_{13} & a_{14}\\
   a_{21} & a_{22} & a_{22} & a_{24}\\
   a_{31} & a_{32} & a_{23} & a_{34}\\
   a_{41} & a_{42} & a_{24} & a_{44}\\
  \end{array} } \right]
\,
B=\
  \left[ {\begin{array}{cc}
   b_{11} & b_{12} & b_{13} & b_{14}\\
   b_{21} & b_{22} & b_{22} & b_{24}\\
   b_{31} & b_{32} & b_{23} & b_{34}\\
   b_{41} & b_{42} & b_{24} & b_{44}\\
  \end{array} } \right]
\
$$

We can construe these as sets of blocks of components like so:

$$
A=\
  \left[ {\begin{array}{cc}
   A_{1} & | & A_{2}\\
   A_{3} & | & A_{4}\\
  \end{array} } \right]
\,
B=\
  \left[ {\begin{array}{cc}
   B_{1} & | & B_{2}\\
   B_{3} & | & B_{4}\\
  \end{array} } \right]
\,
$$

The blocks can then be multiplied in the same order used in other methods of matrix multiplication (the columns of A across a row * the rows of B down its column), for example: $A_{1}\*B_{1} + A_{2}\*B_{3}$ yields C1 in result table 1.  Within each of these block multiplications, the same order of multplication and summing would be followed for their respective components, then the blocks are summed together.  You need to have as many blocks across as you're multiplying down, and for a given multiplication of two blocks the rows=columns restriction would need to obtain.

When you think about it, you can see that the additive nature of the common matrix multiplication formula:

$$\text{ = }a_{i,1}b_{1,j}\text{ + }a_{i,2}b_{2,j}\text{ + ...}a_{i,n}b_{n,j}$$

... would allow you to divide up the work in this way.  

Here is an illustration using square matrices.  Again, they don't need to be square.

<img width="663" alt="Screenshot 2025-02-27 at 17 26 40" src="https://github.com/user-attachments/assets/7466f52c-dfe6-4bba-be36-a001768e4e33" />



## Vector

### definitions

#### Definition 1
source: Strang p12
content: A vector is a list of numeric values. The values do not need to be real numbers.

#### notes
source: Strang p12
* Vectors can be written as rows, read from left to right, but are typically written as columns read from top to bottom.
* A vector is noted as an italicized capital letter, e.g. **v** or **u**.
* In the vector **v**, each vector component is written as: 

$$**v**=\begin{bmatrix}
v_{1} \\
v_{2} \\
\vdots \\
v_{m} \\
\end{bmatrix}
$$

.

source: Strang p13
* Implicitly, each vector component is understood to be the value for a separate variable and is not initially interacting with any other component.  Operations on the vector might combine the values.
* The order of addition makes no difference: v + w equals w + v. 
* The order of operations in a linear combination is as with regular math: multiplication of the vectors happens first, then the like components of each vector are added together.

source: Strang p14
* there are four special types of linear combination:

1v + 1w = sum of vectors
1v - 1v = difference of vectors 
0v + 0w = zero vector (one way to get a zero vector).
cv + 0w = vector in cv "in the direction of v" (implictly, from the origin to the point deterimined by vector v).

## Zero Vector

### definitions
#### Definition 1
source: Strang p12
content: A vector which has only values of zero for its components.  

### notes
source: Strang p13
* A zero vector is written as a bold italized **0**.  This is not the same as the value 0.
* Every vector space includes the zero vector, since obviously you can add a vector of 0s to anything without effect.

## Linear Combination
### definitions

#### Definition 1
source: Strang p12
content: A linear combination is an operation on two or more vectors in which the vectors are multiplied by a scalar, and then added together.

By convention, linear combinations are written like this:

$$c**v** + d**w** = c\begin{bmatrix}
1 \\
1 \\
\end{bmatrix} +  d\begin{bmatrix}
2 \\
3 \\
\end{bmatrix} = \begin{bmatrix}
c + 2d \\
c + 3d \\
\end{bmatrix}
$$

#### notes
source: Strang p12
* Implicitly, in a linear combination where a vector has no scalar, it is understood to be multiplied by 1.
* Vectors are only added; subtraction is handled by giving the vector components negative values.
* If two vectors are not on the same line, their linear combination can fill in an entire two dimensional plane by modifying the scalars c and v
  
source: Strang p13
* When vectors are added together, each component can only be added to the corresponding components in the other vectors.  For example:
  
![Screenshot 2025-01-30 at 12 25 28](https://github.com/user-attachments/assets/29c19001-001b-4ea7-a17c-946e8982382c)

source: Strang p14
* Illustration of linear combination:
![Screenshot 2025-01-30 at 14 58 51](https://github.com/user-attachments/assets/00a47439-8b55-4822-902d-bca686d54169)

source: Strang p16
So long as the vectors do not lie on the same line and are not zero vectors, the following things are true about linear combinations:

1. The combinations cu fill a line.
2. The combinations cu + dv fill a plane.
3. The combinations cu + dv + ew fill three-dimensional space.

## Dot Product

### definitions
#### Definition 1
source: Strang p11
content: a "dot product" or "inner product" is when the like components of two vectors are multiplied together, and then these products are then summed together.  

#### Definition 2
source: Strang p11
content: a "dot product" or "inner product" of v = $$\left(v_1,v_2\right)$$ and w = $$\left(w_1,w_2\right)$$ is the number $$v \cdot w$$:

$$v \cdot w = v_1 w_1 + v_2 w_2$$

### notes
source: Strang p11
* using trigonometry, the angle between two vectors can be calculated.

## Zero Dot Product

### definitions
#### Definition 1
A dot product with a value of 0.

### notes
source: Strang p11
* a zero dot product means that the vectors are perpendicular to each other.
* by solving for a dot product set to 0, the "balance" point of 2 (or more?) vectors can be calculated.
* similarly, solving for a dot product set to 0 where the vector q is quantity and vector p is price can find the balance point at which the "books balance". --This requires considering negative quantity values as "quantity sold".

source: Strang p14

* The Pythagorean theorem can be demonstrated in terms of vectors:

"The pythagoras law for the sides of a right triangle is $$a^{2} + b^{2} = c^{2}$$:

  $$\text{Perpendicular vectors }{\mid\mid v \mid\mid}^{2} + {\mid\mid w \mid\mid}^{2} = {\mid\mid v-w \mid\mid}^{2}$$

To understand this equation, first notice that the $${\mid\mid v \mid\mid}^{2}$$ notation means that the vector in the vertical braces is a length, which means it is already a dot product and by definition a vector of squared components resulting from the vector being multipled by itself.  The braces which denote it as a length mean that it is the square root of that dot product. So $${\mid\mid v \mid\mid}^{2}$$ is in effect $${\sqrt{v^{2}}}^{2}$$, which reduces to $$v^{2}$$, which corresponds to $$a^{2}$$ in the Pythagorean theorem.  Same with vector w.  

To understand $${\mid\mid v-w \mid\mid}^{2}$$, imagine v as vector (0,1) on the y axis and w as (1,0) on the x axis.  You can see that the dot product ($$vv^{2}$$) would give you 1, the dot product of w would give you 1 also, and v-w would give you vector (1,1), and the dot product of (1,1) would give you 1+1 = 2, which is a demo or instance of the pythagorean theorem.  

In the dot product content, we already said that a dot product = 0 means that its vectors are perpendicular to each other.  Strang now goes on to show this by solving the Pythagorean law in terms of vectors:

$$\text{Pythagoras }\left({v}_1^{2} + {v}_2^{2}\right) + \left({w}_1^{2} + {w}_2^{2}\right) = {\left({v}_1 + {w}_1\right)}^{2} + {\left({v}_2 + {w}_2\right)}^{2}.$$

If you contemplate this, you will see that it works out to the vector length-based equation just discussed.

Strang goes on to solve this equation algebraically, and shows that it reduces to $$v_1w_1 + v_2w_2 = 0$$.  This is an algebraic vector-based proof that the dot product of perpendicular vectors = 0.

## Non-zero Dot Product

### definitions
#### Definition 1
A dot product with a value not equal to 0.  The value can be positive or negative.

### notes
#### source Strang p12
* dot products with a value > 0 have an angle to each other < $$90^{\circ}$$.
* dot products with a value < 0 have an angle to each other > $$90^{\circ}$$.

A mix of multiplication and and geometry shows the intuition behind these assertions.

Consider this illustration from Strang p14:

![Screenshot 2025-01-31 at 11 16 31](https://github.com/user-attachments/assets/50c03f99-3ef3-4609-aba0-c9261ae7ac6d)

This graph shows vectors 

$$**v** = \begin{bmatrix}
4 \\
2 \\
\end{bmatrix}\text{ , }**w** = \begin{bmatrix}
-1 \\
2 \\
\end{bmatrix}
$$

We're taking it as given that v*w = 0, meaning that they are perpendicular to each other.  We must therefore assume that the line which extends between the end points of v and w from (-1,2) to (4,2) opposite to that right angle must be a hypotenuse.  Let's call it h.

We want to show that any vector $$v_{1}$$ that originates from intersection of v and w, and extends out to some point between the quandrant plane between them, will be > 0 when we multiply $$v\cdot v_{1}$$.  

Continue to imagine $$v_{1}$$ as a vector of arbitrary length originating from the intersection of v and w and sweeping between them.  Now limit the coordinates of $$v_{1}$$ to (i,2) so that x can be any number, but y must always be 2.  This means that the endpoint of $$v_{1}$$ will always be on the hypotenuse h for legs v and w.  

Consider a range of h for (i >-1 and i <2,2). It is apparent that no negative product of -i\*4 on this range can be <-4.  Therefore any dot product of $$v\cdot w$$ on this range of h, resulting from changes to i, must be positive. 

Now consider end points for $$v_{1}$$ where x and y can take any values in the quandrant between v and w.  It is obvious that any coordinates for $$v_{i}$$ which are in the same x,y quandrant as v must be give a positive dot product, because multiplying either 2 positives or two negatives will yield a postive product.  

So, consider any vector $$v_{1}$$ with endpoints in the (x<0,Y>0) area between the y axis and line extending through vector w.  Because of the way this area is bounded, $$\mid\mid x \mid\mid$$ can never be greater than y.  This means that $$y_{v_{1}}*y_{v}$$ will alway increase more quickly than $$x_{v_{1}}*x_{v}$$.  Therefore the dot product will always be positive.  

If the coordinates for $$v_{1}$$ fall on the line of w, they must necessarily yield a dot product with v.

If the coordinates for $$v_{1}$$ fall outside/past the line of w, the y>x constraint will be broken, and the $$v\cdot w$$ dot product will begin to be negative.

## Length

### definitions

#### Definition 1
source: Strang p12
The length of a vector, also know as the norm, is the square root of the dot product of the vector with itself.  

#### Definition 2
The length $$\lvert\lvert v \lvert\lvert$$ of a vector v is the square root of $$v \cdot v$$:

$$Length = norm \left(v\right) = \lvert\lvert v \lvert\lvert = \sqrt{v \cdot v} .$$

### notes
source: Strang p12
* Per the above, the dot product of a vector with itself is thus the length of the vector squared.
* It can be easy to look at the above definitions and miss what the length is: it's the hypotenuse of a right triangle.  Consider a vector v with just two components (2,3), which you could think of as a=2, b=3.  If you take the dot product, you're squaring x and y and adding them together, in other words executing the pythagorean formula where $c^2$ is the dot product $2^2 + 3^2 = 13$.  The square root of 13 is then the square root of $c^2$, or the length of the hypotenuse.  This should work for a vector of any length.

## Unit Vectors

### definitions

#### Definition 1
source: Strang p12
A unit vector is a vector with a length of 1, or $$u \cdot u = 1$$.

#### Definition 2
source: Strang p14

A unit vector is a vector $$v$$ divided by its length $$\mid\mid v \mid\mid$$, and will always be the same direction as the vector $$v$$.

### notes
source: Strang p12

Dividing a set of components of a vector by that vector's length will yield components of the corresponding unit vector.

![Screenshot 2025-01-30 at 17 27 49](https://github.com/user-attachments/assets/b390fb30-ac25-4d2f-99e4-50e6de6ca72c)

source: Strang p13

## Unit Vector Trigonometry

### definitions
#### Definition 1
source: Strang p13

A unit vector trigonometry is simply trigonometry done with unit vectors.  Because all unit vectors have a length of oneit becomes is possible to calculate the angle $$\theta$$ between two unit vectors using trigonometry.

### notes

source: Strang p13

* The standard unit vector along the x and y axies are written *i* and *j*.  In the xy plane, the unit vector that makes the angle $$\theta$$ with the x axis is thus $$\left(cos\theta, sin\theta\right)$$:

$$**i** = \begin{bmatrix}
1 \\
0 \\
\end{bmatrix}\text{ and }**j** = \begin{bmatrix}
0 \\
1 \\
\end{bmatrix}\text{ and }**u** = \begin{bmatrix}
\cos\theta \\
\sin\theta \\
\end{bmatrix}
$$

.

source: Strang p15
* For an angle $$\theta$$ between two unit vectors, reasoning from trigonometry:
  * the non-hypotenuse side of the triangle that is not opposite theta is called the "adjacent" side, and the $$\cos\theta = \frac{adjacent}{hypotenuse}$$
  * the non-hypotenuse side of the triangle that *is* opposite theta is simply called the "opposite" side, and the $$\sin\theta = \frac{opposite}{hypotenuse}$$.
  * therefore, for a unit vector with respect to a given angle $$\theta$$, the coordinates of that unit vector will be
    
$$
**u** = \begin{bmatrix}
\cos\theta \\
\sin\theta \\
\end{bmatrix}
$$

.

  This is easiest to see in the following illustration:
  ![Screenshot 2025-01-31 at 16 47 48](https://github.com/user-attachments/assets/40f99823-1ce7-4c3c-9fcd-7724ce26ef93)

  * It also follows that ror two unit vectors u and U, the dot product $$u\cdot U = \cos\theta$$.  Again, this is most obvious when u is "lying down" on the x axis so that the dot product is $$\cos\theta * 1 + \sin\theta * 0)$$ .  But you can see that it would be true for any two unit vectors.
  * The dot product between two unit vectors $$u\cdot U = \cos\theta$$, and the absolute value $$\mid u\cdot U\mid\leq1$$.  You can see that the because the legs of a right triangle must each always be shorter than the hypotenuse, it follows that greatest value the dot product could have would be when both u and U are laying on the the positive side of the x axis ($$\mid u\cdot U\mid\=1$$) or U lays on the negative x axis ($$\mid u\cdot U\mid\=-1$$), so $$\mid u\cdot U\mid\leq1$$.
  * When v and w are not unit vectors and are non-zero vectors, then divide each of them by their respective lengths to get the cosine of the angle between them:
    $$\frac{v\cdot u}{\mid\mid v \mid\mid\text{ }\mid\mid w \mid\mid}\text{ = }\cos\theta$$

## Triangle Inequality

### definitions
#### Definition 1
* source: Strang p16
* source: Strang p3
* source: https://www.youtube.com/watch?v=KlKYvbigBqs

It is useful to review what is meant by vector addition using an earlier illustration from Strang:

![Screenshot 2025-02-04 at 15 55 16](https://github.com/user-attachments/assets/96f611bc-e2bf-48ae-b1b6-dc14cf0cc195)

Reviewing this picture, we can see that when we add two vectors, say v and w, we can say that we create a new vector v + w that could connect the end points of v and w if it were moved appropriately.  In this sense we create the third side of a triangle.

Triangle Inequality Formula: $$\mid\mid v + w \mid\mid \leq \mid\mid v \mid\mid + \mid\mid w \mid\mid$$

Recall that the length of a vector is ultimately the hypotenuse for a right triangle, which comes via a dot product for a vector with an arbitrary number of components.

The triangle inequality says that the length of one side of a triangle cannot be greater than the sum of the remaining sides.  This can be easily imagined by taking two vectors that share a common origin and an noticing that the maximum length of the remaining side between the end points of those vectors could be no greater than side 1 length - side 2 length.  If it were greater it could not remain connected.  When side 3 = side 1 - side 2, they all lay on the same line and the triangle is said to be "degenerate".

### notes

* most proofs of Cauchy-Schwarz are not shown in linear algebra notation, but are instead written in terms of the product of summations.

* Here's a proof of the Cauchy Scwharz inequality.
  * Source: https://www.youtube.com/watch?v=r2PogGDl8_U

## Cauchy-Schwarz Inequality

### definitions
#### Definition 1
source: Strang p16

The Cauchy-Schwarz Inequality is defined as $$\mid v \cdot w \mid\text{ }\leq\text{ }\mid\mid v \mid\mid\\mid\mid w \mid\mid$$ .

In words, this says that the dot product of two vectors can never be greater than the dot product of their lengths.  It also turns out that the only time both sides are equal to each other is when the vectors are collinear (parallel or on the same line).

Strang says that this inequality is the most important one in mathematics.  It's difficult to see what is remarkable about it, but  all sorts of other proofs are said to depend on it as a shortcut, and these proofs would be more difficult without it.

### notes

* most proofs of Cauchy-Schwarz are not shown in linear algebra notation, but are instead written in terms of the product of summations.

* Here's a proof of the Cauchy Scwharz inequality which relies on visualization.
  * Source: [https://www.youtube.com/watch?v=r2PogGDl8_U](https://www.youtube.com/shorts/Xy97t7l6MYg)

Imagine a rectangle composed of 4 sub rectangles in the following way:
![Screenshot 2025-02-04 at 16 55 07](https://github.com/user-attachments/assets/5f09cda4-6036-4551-b7a1-a825f817ea51)

It is obvious that the two unshaded (white) rectangles have areas |a|$\cdot$|x| and |b|$\cdot$|y| by the area formula for rectangles.  Therefore the total area of the unshaded part is the sum of those two areas: |a|$\cdot$|x| + |b|$\cdot$|y|.

It's also clear that we can divide the colored triangles diagonally and rearrange them so that their total area remains the same within the boundaries of the full box.  It follows that the toal unshaded (black) area is still unchanged, although its shape has changed to a parallelogram:

![Screenshot 2025-02-04 at 17 04 17](https://github.com/user-attachments/assets/2b5ea894-27ab-4d15-839a-fb5b80c6d4dc)

You can see that the sides of the parallelogram are given by the pythagorean theorem.  

![Screenshot 2025-02-04 at 17 05 32](https://github.com/user-attachments/assets/d24ac2ea-eb7c-4d69-883a-81ee5aa3c56f)

The area of the parallelogram is now given by the product of the side lengths multiplied by the sine of the angle between them.  Because the area has not changed while the shape has shifted from a rectangle to a parallelogram, it follows that the two formulas are equal to each other:

$$\mid a \mid\cdot\mid x \mid + \mid b \mid\cdot\mid y \mid = \sqrt{a^2 + b^2}\cdot\sqrt{x^2+y^2}\cdot\sin\left(z\right)$$
.

The sin(z) is always less than or equal to 1.  Therefore when the sin(z) is removed, the right side must get larger or remain the same, and the left side by comparison becomes smaller or equal to it:

$$\mid a \mid\cdot\mid x \mid + \mid b \mid\cdot\mid y \mid \leq \sqrt{a^2 + b^2}\cdot\sqrt{x^2+y^2}$$
.


## Matrices

### definitions
source: Strang p22

Imagine we have the following 3 vectors:

$$**u**=\begin{bmatrix}
{1} \\
{-1} \\
{0} \\
\end{bmatrix}\text{  }**v**=\begin{bmatrix}
{0} \\
{1} \\
{-1} \\
\end{bmatrix}\text{  }**w**=\begin{bmatrix}
{0} \\
{0} \\
{1} \\
\end{bmatrix}
$$

The linear combinations of them would be as follows:

$$c\begin{bmatrix}
{1} \\
{-1} \\
{0} \\
\end{bmatrix}\text{ + }d\begin{bmatrix}
{0} \\
{1} \\
{-1} \\
\end{bmatrix}\text{ + }e\begin{bmatrix}
{0} \\
{0} \\
{1} \\
\end{bmatrix}\text{ = }\begin{bmatrix}
{c} \\
{d-c} \\
{e-d} \\
\end{bmatrix}
$$

These vectors can be combined into a matrix *A*

$$c\begin{bmatrix}
{1 0 0} \\
{-1 1 0} \\
{0 -1 1} \\
\end{bmatrix}
.

Matrix A is said to "multiply" or "act on" the matrix x = (c,d,e):

*Ax = b* .

$$\begin{bmatrix}
{\text{1 0 0}} \\
{\text{-1 1 0}} \\
{\text{0 -1 1}} \\
\end{bmatrix}\begin{bmatrix}
{c} \\
{d} \\
{e} \\
\end{bmatrix}\text{ = }\begin{bmatrix}
{c} \\
{d-c} \\
{e-d} \\
\end{bmatrix}
$$

This way of multiplying a matrix times a vector is equivalent to the linear combination shown above.

To emphasize this, we can set vector *x* components (c,d,e) to (*x_1,x_2,x_3*) and set the results of the multiplication *Ax* equal to a new result vector b, where each component of b is equal to the corresponding result of multiplying *Ax*:

$$Ax = \begin{bmatrix}
{\text{1 0 0}} \\
{\text{-1 1 0}} \\
{\text{0 -1 1}} \\
\end{bmatrix}\begin{bmatrix}
{x_1} \\
{x_2} \\
{x_1} \\
\end{bmatrix}\text{ = }\begin{bmatrix}
{x_1} \\
{x_2-x_1} \\
{x_3-x_2} \\
\end{bmatrix}\text{ = }\begin{bmatrix}
{b_1} \\
{b_2} \\
{b_3} \\
\end{bmatrix}\text{ = b}
$$

This kind of matrix *b* is known as a difference matrix.  

$$x = \begin{bmatrix}
{\text{1}} \\
{\text{4}} \\
{\text{9}} \\
\end{bmatrix}\text{ = squares Ax = }\begin{bmatrix}
{\text{1 - 0}} \\
{\text{4 - 1}} \\
{\text{9 - 4}} \\
\end{bmatrix}\text{ = }\begin{bmatrix}
{1} \\
{3} \\
{5} \\
\end{bmatrix}\text{ = b}
$$

These equations *Ax = b* can also be solved in reverse, asking what combination of Ax (or linear combination cu + dv +ew) gives you b:

<img width="890" alt="Screenshot 2025-02-20 at 18 33 45" src="https://github.com/user-attachments/assets/364a2ac2-a8b5-49f1-a98c-66a4420b0b1c" />

* You can see that this is easily solved via substitution.  But many equations are difficult or insoluable.  This one is solvable because it uses a *lower triangular* matrix.
* A key relationship that is so obvious that it can be missed is that the differences of x (as shown above) = b, and therefore recipriocally the sums of b = x.  That is, you subtract x variables to get b and add values of b to get values of x.

Extending this insight about differences of x yielding b and sums of by yielding x, we can see that sums of components of b can be considered as b multiplied by a summation matrix of 1s and 0s (not -1s which would be a "difference matrix):

<img width="891" alt="Screenshot 2025-02-20 at 19 05 05" src="https://github.com/user-attachments/assets/a611dafe-f81b-4457-9735-7561b0bb30fb" />

The fuller reciprocal relationship is shown here, where *Ax=b* and *Sb=x*:

<img width="896" alt="Screenshot 2025-02-20 at 19 17 39" src="https://github.com/user-attachments/assets/8f575d6f-0a04-4eed-a16b-28539310b810" />

*S* is considered the **"inverse matrix"** of *A* and can be written as *A^{-1}*.  In notation, we can say that:

*Ax = b* is solved by $x = A^{-1}b = Sb$.



## Inverse Matrices

Sources:
* https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/multiplication-and-inverse-matrices/
* https://www.youtube.com/watch?v=zWxhmBCdvFs&pp=ygUUaW52ZXJzZSBtYXRyaXggcnVsZXM%3D
* https://youtu.be/zWxhmBCdvFs

The inverse of a matrix is noted as $A^{-1}$. **Matrices must be square to have an inverse.**  The "squareness requirement" comes from the definition of an inverse matrix.

### Inverse Matrix Definition
Sources:
* Strang, p81ff.

The matrix A is invertible if there exists a matrix $A^{-1}$ such that $A^{-1}A\text{ = }I\text{ and }AA^{-1}\text{ = }I$ .

This definition implies that we have to be able to multiple $A^{-1}A$ and $AA^{-1}$ in both directions.  But that would mean, according to matrix multiplication rules, that A has to have the same number of columns as $A^{-1}$ has rows, and $A^{-1}$ has to have same number of columns as A has rows.  Which means that their rows have to equal their columns.  So you can only take the inverse of a square matrix.

In the context of linear algebra, AB is not necessarily equal to BA. In fact it may not be possible to multiply both AB and BA (they would need to be square).  So in linear algebra, "handedness" (whether a matrix A is on the left or right side of B in multiplication) matters.  Handedness wouldn't wouldn't in "regular" algebra, where multiplying scalar variables ab=ba.  With this in mind, Strang finds it worth noting that the "left side inverse equals the right side inverse" ($A^{-1}$ in $A^{-1}A$) .  --Strang says that this statement is actually difficult to prove.

An inverse matrix looks like if you took the lower left to upper right diagonal and spun everything around it once so that the positions were reversed.  Then non-diagonal values are have their signs reversed so that $AA^{-1}$ will yield the identity matrix I$. An Identity Matrix is a matrix of but 1s on the diagonal and 0s everywhere else, so that when you multiply a matrix * I you get back the original matrix unchanged).  

Here is an example of A and its inverse.

$$
A=
\
  \left[ {\begin{array}{cc}
   4 & 3\\
   3 & 2\\
  \end{array} } \right]
\,
A^{-1}=
\
  \left[ {\begin{array}{cc}
   -2 & 3\\
   3 & -4\\
  \end{array} } \right]
\
$$

**The inverse of a matrix may not exist.**  

There are algorithms for creating the inverse of a matrix.  As the dimensions increase, these calculations quickly become complex and difficult.  So shortcut rules for deciding an inverses do/don't exist, so that you can skip the calculation, are valuable.
Figuring out whether a matrix has an inverse is one of the most important activities in linear algebra.  

A matrix that has an inverse is said to be "invertible" or "non-singular".  More useful things can be done with invertible matrices.  A matrix with no inverse is "non-invertible" or "singular".

### Inverse Matrix Properties and Notes

Sources:
* Strang, p81ff.

These notes are not listed in Strang's original order, because I had not yet dealt with pivots and determinants when I read this material.  So I've prioritized the notes that seem more self-evident.

#### Note 1: A Matrix Has Only One Inverse.

This assertion stems from the definition of a matrix where a matrix times its inverse equals the identity matrix, and that both the left and right handed inverse matrices are identical: $A^{-1}A\text{ = }I\text{ and }AA^{-1}\text{ = }I$ . The proof involves not showing uniqueness directly, but rather demonstrating than any inverse matrices that exist must be identical to each other.   To see this, substitute the letters B and C for 2 potential inverse matrices, so that BA = I and AC = I.  Again, notice that per the inverse matrix definition, B and C can be on the left or right of A.  Since both  BA = I and AC = I, we can say that:

$$B\left(AC\right)\text{ = }\left(BA\right)C\text{ = }BI\text{ = }IC\text{; therefore }Btext{ = }C$$ .

#### Note 2: If A is invertible, then the only solution to [x in] $Ax\text{ = }b$ is $x = A^{-1}Ax\text{ = }A^{-1}b$ .

To see the sense of this statement, remember that the values for matrix A and vector b are fixed, and we are solving for x.  Also remember that a matrix can only have 1 unique inverse, if it has one at all.  Now consider that since we are solving for x, we will want to isolated it.  In regular algebra with 2 scalar variables you would isolate x by multiplying Ax=b on both sides by $\frac{1}{A}$, but there is no such thing as fractions in linear algebra.  Instead you multiply both sides by $A^{-1}$.  On the left side of the equation, $A^{-1}Ax$ will reduce to $Ix$ will will just leave you with vector x.  On the ride side, you'll be left with $A^{-1}b$.  Strang lists whole setup as:

$$\text{Multiply }Ax = b\text{ by }A^{-1}\text{.  Then }x\text{ = }A^{-1}Ax\text{ = }A^{-1}b.$$

Again, a matrix has at most one inverse, so IF an inverse exists, this will be the only solution to x.  I don't know if for singular, non-invertible matrices there can be more than one solution (or none) for x in Ax=b.

#### Note 3: If there is a non-zero vector x such that Ax = 0, then A cannot have an inverse.  

You can kind of see this by contemplating Note 2 again: 

$$\text{Multiply }Ax = b\text{ by }A^{-1}\text{.  Then }x\text{ = }A^{-1}Ax\text{ = }A^{-1}b.$$

Look at the far right side of this equation: if b were 0 as a result of multiplying matrix A times non-zero vector x, there would be no matrix you could multiply by both sides of the equation Ax = b to give you (1) non-zero matrix x on the right side, because every matrix time **0** would yield a zero matrix (2) on the left side, that same inverse matrix used on the right would have to somehow yield the identity matrix I so that Ix = x.  These two conditions are irreconcilable and impossible.

#### Note 4: An inverse exists if and only if elimination produces n pivots.  

Basically this means that if you can solve Ax = b for x using elimination, then the conditions for having a matrix also exist.  If you can't they don't.  When you solve Ax = b via elimination, you never actually show/solve for $A^{-1}$, but you indirectly prove that the index exists.

#### Note 5: A **diagonal matrix** has an inverse if it has no 0 entries on its diagonal.

A diagonal matrix is a matrix in which all the entries NOT ON THE MAIN DIAGONAL are 0.  Although it's no proof, you can easily imagine that having only values on the diagonal would make finding an inverse easier.  In fact, when the conditions listed here hold, the inverse of a diagonal matrix is just 1/the value of main diagonal entry, for every entry, keeping the original order:

![Screenshot 2025-02-28 at 13 39 34](https://github.com/user-attachments/assets/e6c4df82-24d2-4cce-bbad-a85362a30a22)

#### Note 6: A matrix is invertible only if its determinant is not 0.

More on determinants later.

#### Note 7: Invertible matrices, the only solution to Ax=0 is that x is the 0 vector.

Source: Strang p132.

### Indications that Matrix is Non-invertible

Here is an example of a singular (non-invertible) matrix:

$$
A=
\
  \left[ {\begin{array}{cc}
   1 & 3\\
   2 & 6\\
  \end{array} } \right]
\
$$

Why does this matrix have no inverse?  


### Relating this equation to calculus.

Sources: 
* Strang, p24.

* For a difference matrix Ax, we can change the vector x to *x(t)*.  The differences Ax, generated by A acting on x, can then be re-written as *dx/dt = b(t)*.  Phrasing things in terms of differentiation and integration, we can phrase the fundamental theorem of calculus in this way:

  $$Ax = b\text{ and }x = Sb\text{, or }\frac{dx}{dt}\text{ = }b\text{ and }x(t) = \int_0^t b$$.

#### Taking the "Derivative of a Matrix"

Sources: 
* https://www.youtube.com/watch?v=e73033jZTCI

Notes:
* **First, note that it's actually invalid to speak of taking the "derivative of a matrix A".**   What we really do is take a derivative of the **linear transformation** Ax with respect to x.
* Next, note that Strang uses the letter A to indicate that A is a "difference matrix" or matrix in which components of x, when multiplied by A, may be subtracted from each other.  
  * Correspondly, we are going to differentiate Ax in keeping with this notation.
* Correspondingly, the letter S is used for a "summation matrice", and so we'll integrate Sb when we discuss matrix integration.
* Remember that difference matrix A acts on vector x, so we when differentiate Ax we are differentiating an example like this:

$$
\
Ax=
  \left[ {\begin{array}{cc}
   1 & 2 \\
   3 & 4 \\
  \end{array} } \right]
\
\begin{bmatrix}
x_1 \\
x_2 \\
\end{bmatrix}
$$

* This example of *A* from a non-Strang source doesn't contain differences, but the operations would be the same.
* Continuing this example, the product of Ax yields a system of 2 functions:

$$
\begin{bmatrix}
x_1 + 2x_2 \\
3x_2 + 4x_2 \\
\end{bmatrix}
$$

* We can give function names to each of these functions:
  * $f_1\left(x_1,x_2\right)\text{ for }x_1 + 2x_2$
  * $f_2\left(x_1,x_2\right)\text{ for }3x_1 + 4x_2$

Re-writing Ax in these terms makes it easier to consider what taking the derivative of Ax involves, because its customary to take a derivative of an equation rather than a matrix*vector.  It also lets us talk in familiar terms like "taking the derivative of $f_1$ with respect to $x_1$".

We can now rewrite the process of taking the derivative of Ax as:

$$
\
\frac{d}{dx}Ax=
  \left[ {\begin{array}{cc}
   \frac{df_1}{dx_1} &  \frac{df_1}{dx_2}\\
   \frac{df_2}{dx_1} &  \frac{df_2}{dx_2} \\
  \end{array} } \right]
\
$$

* Notice in the above equation how we are still following the conventions of matrix*vector multiplication by keeping the r1c1, r2,c2 arrangement of the matrix components.
  * So taking the derivative of a matrix A consists of taking the derivative of each function $f_{1,2}\left(x_1,x_2\right)$ with respect to $x_{1,2}$ in the order we'd normally use for *Ax* multiplication.
  * For example, the Ax component $\frac{df_1}{dx_1}$, or "derivative of f1 w/r/t x1" reduces to 1, because $x_1$ is to the power of 1, and the derivative of $2x_2$ w/r/t $x_1$ is 0.
 
* Extending this process, $\frac{d}{dx}Ax$ becomes:

$$
\
  \left[ {\begin{array}{cc}
   1 & 2\\
   3 & 4\\
  \end{array} } \right]
\
$$

* **Notice that this result is just the matrix "A" from our original linear transformation Ax**.  This makes intuitive sense, because if $\frac{d}{dx}kx=k$ where the derivative of a constant (scalar) k w/r/t x is k, it seems like it should follow that the derivative of a matrix of constants A times a vector of variables x should equal A.

#### Taking the "Derivative of a Linear Transformation with Transpose"

Sources:
* https://www.youtube.com/watch?v=e73033jZTCI

* Suppose that we want to take the derivative of a linear system with uses a transposition of a vector, for example:
$$x^TAx$$.

The transpose of x transforms the columns of x into rows, so $x^T$ is $\left(x_1,x_2\right)$, and in full $x^AXx$ becomes:

$$
\left(x_1,x_2\right)
\
  \left[ {\begin{array}{cc}
   a_11 & a\\
   a & a_22\\
  \end{array} } \right]
\
\begin{bmatrix}
x_1 \\
x_2 \\
\end{bmatrix}
$$

Notice that matrix A here is "symmetric", meaning that components $a_12$ and $a_21$ are identical.  This was chosen to make the example easier.

The right side Ax reduces to:

$$
\
  \left[ {\begin{array}{cc}
   a_{11}x_1 & ax_2\\
   ax_1 & a_{22}x_2\\
  \end{array} } \right]
\
$$

Now we multiply the left transposed vector $\left(x_1,x_2\right)$ by the above to get:

$$a_{11}x_1^2 + ax_1x_2 + $$
$$ax_1x_2 + a_{22}x_2^2$$

  * Notice that when calculating the product of Ax yielded a vector of the interactions of their components.  However, when we multiply the vector $x^T$ times the vector of results from Ax, we get *a single equation that sums all the components together*.  This is because a multipling two compatible vectors together gives us a **dot product** and remember that taking a dot product involves a final *summation of terms*.

We can continue on to combine the duplicated term $ax_1x_2$ to get $a_{11}x_1^2 + 2ax_1x_2 + a_{22}x_2^2$.  --We were able to do this because we selected a symmetric matrix for our example.  This function can be construed as an equation:

$$f\left(x_1,x_2\right)\text{ = }a_{11}x_1^2 + 2ax_1x_2 + a_{22}x_2^2$$

Since we only have one function $f\left(x_1,x_2\right)$, taking the derivative *df* or  $\frac{d}{dx}x^TAx$ will yield just a simple vector:

$$
\begin{bmatrix}
\frac{df}{dx_1} \\
\frac{df}{dx_2} \\
\end{bmatrix}
$$.

The nature of this function $x^TAx$, involving a transpose, chase caused us to end up with a single function $f_1$.  The previous excercize in taking the derivative *Ax* gave us two functions.  --Taking the derivative of any combination of vector and matrices reduces to taking the number or resultant functions * number of variables and yield a new matrix with every pair-wise derivative.

Continuing this example, we resolve this vector of derivatives as:

$$\frac{df}{x_1}a_{11}x_1^2 + 2ax_1x_2 + a_{22}x_2^2\text{  =  }2a_{11}x_1 + 2ax_2$$
$$\text{, and}$$
$$\frac{df}{x_2}a_{11}x_1^2 + 2ax_1x_2 + a_{22}x_2^2\text{  =  }2ax_1 + 2a_{22}x_2$$

.

equivalently:

$$
\begin{bmatrix}
2a_{11}x_1 + 2ax_2 \\
2ax_1 + 2a_{22}x_2 \\
\end{bmatrix}
$$

.

This can be simplified.  For example remember that a scalar c times a vector u equals the scalar times each component in u.  So the reverse is true as well, and we can extract 2 from every component to get:

$$
2
\begin{bmatrix}
a_{11}x_1 + ax_2 \\
ax_1 + a_{22}x_2 \\
\end{bmatrix}
$$

.
Further, the remain terms can be deconstructed into a matrix A of a-components times an x vector of x-components:

$$
2
\
  \left[ {\begin{array}{cc}
   a_{11} & a\\
   a & a_{22}\\
  \end{array} } \right]
\
\begin{bmatrix}
x_1 \\
x_2 \\
\end{bmatrix}
$$

Notice that **this gives us back the original matrix A and vector x**.  So the derivative $\frac{d}{dx}x^TAx$ ultimately reduces to 2ax.

The result $\frac{d}{dx}Ax\text{ = }A$ was intuitive because $\frac{d}{dx}kx\text{ = }k$.

The result $\frac{d}{dx}x^TAx=2ax$ is also intuitive, because it is analogous to the result that $\frac{d}{dx}kx^2\text{ = }2kx\$.  In this way, $x^TAx=2ax$ can be said to be analogous to quadratic equations.  

#### Taking the Integral of A Matrix

More content TBD.  However, the integral of a matrix multiplication Sb amounts to taking the integral of each component in the result matrix of that multiplication.

### The Product of Inverse Matrices

Sources:
* Strang: https://youtu.be/MsIvs_6vC38
* Supposed you have the product of AB of two intertible matrices A and B.  Then the correct way to multiply their inverses to recover AB is $B^{-1}A^{-1}$.  To see that this is so, consider the equation $ABB^{-1}A^{-1}\text{ = }I$.  You can see that this is the matrix arrangement that would reduce to $AIA^{-1}\text{ = }I$.  Then AI=I, and $AA^{-1}=I$.

## Transposed Matrices

Sources:
* Strang: https://youtu.be/MsIvs_6vC38
* Strang: https://youtu.be/JibVXBElKL0
* Strang, p107.

Transposing a matrix swaps row placement for column placement, so that row 1 becomes column 1, row 2 becomes column 2, etc.  Here is an example:

$$
A\text{ = }
\left[ {\begin{array}{cc}
  1 & 2 & 3\\
  0 & 0 & 4\\
\end{array} } \right]
\text{ , }
A^T\text{ = }
\left[ {\begin{array}{cc}
  1 & 0 \\
  2 & 0 \\
  3 & 4 \\
\end{array} } \right]
$$

In general, we can say that that $A^T_{ij}=A_{ji}$ for row i and column j.

Note that:
* the transpose of the identity matrix I is necessarily I.
* a symmetric matrix is identical to its transpose: $A=A^T$.
* multiplying a retangular matrix by its tranpose will give you a symmetric matrix.  For example, with a 2x3 matrix this would cause the off diagonal sum A_11*B_12+A_12*B_22 to be calculated with an identical value from as A_21*B_11+A_22*B_12, so that all the off-diagonal values end up duplicated.

### Matrix Notation for Nested Transposes

Suppose we have a rectangular matrix R.  We know that $R^{T}R$ will yield a symmetric matrix.  We also know that the transpose of a symmetric matrix is that same symmetric matrix. Using matrix notation, we can see that the transpose of $R^{T}R$ , $\left(R^{T}R\right)^T$, also yields a symmetric matrix.  When taking the transpose of a product of matrices like $R^{T}R$, the practice is to reverse the order of items in the parentheses, then transpose each term.  So $\left(R^{T}R\right)^T\text{ = }R^TR^{TT}$.  But $R^{TT}$ is just R, so the result is just $R^{T}R$ as before, which we know is a symmetric matrix.  --This is proof in matrix notation that taking additional transposes of symmetric matrix products, e.g. $R^{T}R$, leaves them unchanged.


### Inverting Transposed Matrices

Remember that invertible matrices are by definition square.

In order to understand what the inverse of a transposed matrix is we begin with the formula $AA^{-1}=I$.  If transpose both sides, I is unchanged but we must reverse the order of the matrices in order for them to still equal I:

$${A^{-1}}^TA^T=I$$

For us, what is important about this is that it reveals what the inverse of a transposed matrix looks like, and also the multiplication order required for $AA^{-1}=I={A^{-1}}^TA^T$.  By extension, it shows us how to solve for ${A^{-1}}^T$ when we know $A^{-1}$.

For a single matrix, you can do transposing and inversing in either order.

Here is an example to make it concrete:

$$AA^{-1}=I$$

$$
\left[ {\begin{array}{cc}
  2 & 3\\
  1 & 4\\
\end{array} } \right]
\left[ {\begin{array}{cc}
  \frac{4}{5} & -\frac{3}{5} \\
  -\frac{1}{5} & \frac{2}{5} \\
\end{array} } \right]
\text{ = }
\left[ {\begin{array}{cc}
  1 & 0 \\
  0 & 1 \\
\end{array} } \right]
$$

$${A^{-1}}^TA^T=I$$

$$
\left[ {\begin{array}{cc}
  2 & 3\\
  1 & 4\\
\end{array} } \right]
\left[ {\begin{array}{cc}
  \frac{4}{5} & -\frac{1}{5} \\
  -\frac{3}{5} & \frac{2}{5} \\
\end{array} } \right]
\text{ = }
\left[ {\begin{array}{cc}
  1 & 0 \\
  0 & 1 \\
\end{array} } \right]
$$


## Cyclic Matrices

Sources:
* Strang: https://youtu.be/0oBJN8F616U?t=1873
* Strang, p25.

A cyclic difference matrix is just one in which identical values in each row of the matrix are consistently shifted one to the right (or left), so that a cyclic pattern is adhered to, and eventually a row of a matrix would repeat the value sequence of a previous row (this repetition may or may not happen depending on the number of rows).  Here is an example:

$$
Cx\text{ = }
\
  \left[ {\begin{array}{cc}
   1 & 0 & -1\\
   -1 & 1 & 0\\
   0 & -1 & 1\\
  \end{array} } \right]
\
\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{bmatrix}
\text{ = }
\begin{bmatrix}
x_1\text{ - }x_3 \\
x_2\text{ - }x_1 \\
x_3\text{ - }x_2 \\
\end{bmatrix}
\text{ = }b
$$

### Notes about this equation:

#### More on Meaning of the Word "Cyclic"
* Strang says that this equation results in a "cyclic difference matrix C".  That is true: you can see that the difference matrix b shows a pattern of shifting the subtractions of x variables one to the right with each rows.
* When I first read this passage, I read to much into the word "cyclic".  I tried for a while to figure out how, in the difference matrix, row 1 somehow was a result of operations on row 2, which somehow was a result of row 3, which somehow was a result of row 1...  **That is not what "cyclic" means in this context.**. They are only talking about the "consistent shifting to the right(left)" pattern of identical values.
* Strang concludes remarks about this equation using a cyclic matrix by asking "which b's do we get when we look at all combinations of these 3 dependent vectors?".  What he means is that he wants to consider how the vectors in matrix C determine b.  Because each vector sums to 0, it follows that b will a zero vector or "all the vectors that sum to 0".  The larger point is to contemplate the characteristics of the vectors in the matrix in the linear equation in order to get a sense in advance of the equations characteristics.

#### Summing Vectors on Both Sides of an Equation
* Using this example, Strang notes that **you can sum the vectors on both sides of a linear equations** like so:

$$
\begin{bmatrix}
x_1\text{ - }x_3 \\
x_2\text{ - }x_1 \\
x_3\text{ - }x_2 \\
\end{bmatrix}
\text{ = }\begin{bmatrix}
b_1 \\
b_2 \\
b_3 \\
\end{bmatrix}
$$

...can be written as ...

$$x_1\text{ - }x_3 + x_2\text{ - }x_1 + x_3\text{ - }x_2\text{ = }b_1\text{ + }b_2\text{ + }b_3$$

... which ends up being ...

**0**$\text{ = }b_1\text{ + }b_2\text{ + }b_3$ .  

I call this out because I didn't realize until I saw it that this "sum both sides" action was allowed.  Anyway, **0**$\text{ = }b_1\text{ + }b_2\text{ + }b_3$ shows that the equation only makes sense if b = **0** (the zero vector).  Then reactive to this, we can figure out that:

![Screenshot 2025-03-01 at 10 18 06](https://github.com/user-attachments/assets/08b1df68-9982-492d-aba0-0f177a329f9a)

So any constant c solves the equation, which may not be useful.

#### Uses of Cyclic Matrices

Because of the talk in Strang of this equation having "no solution or infinite solutions", you may assume that cyclic matrixes are always degnerate and problematic.  But actually they are useful wherever the problem domain involves periodicity.  An example is time series analysis.  Maybe the prime example is the identity matrix, which is used everywhere in linear algebra. 

## Matrix Elimination

Sources:
* Strang: https://youtu.be/QVKj3LADCnA
* Strang, Sec. 2.3, 2.4

Matrix elimination is a method invented by Gauss which finds the inverse of a matrix by solving linear equations systems without the use of determinants.  Not all systems have solutions. Every use of matrix elimination has the objective of eliminate variables from the equations by solving them in terms of each other.  This is done in such a way that one equation is reduced to a single variable being equal to a constant, and the next equation being equal to that variable + one more variable equal to a constant, and so on.  Thus the equations can be resolved successively by substituting the known variable values in a successive chain through a process called "back substitution".

### Matrix Elimination Example 1:

Suppose we have this linear equation system for Ax = b:

x  + 2y + z = 2
3x + 8y + z = 12
     4y + z = 2
.

We can re-write the left hand coefficients into a matrix A:

$$
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1\\
   3 & 8 & 1\\
   0 & 4 & 1\\
  \end{array} } \right]
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}\begin{bmatrix}
2 \\
12 \\
2 \\
\end{bmatrix}
$$

.

For a start, we focus on just the matrix A, and we want to eliminate the 3 in the row (3, 8, 1).  To do this we will multiply the row (1,2,1) by 3 and then subtract row 1 from row 2.  Row 1 will then have all 3 values and row 2 will replace 3 with 0.  The value "1" in (1,2,1), which is the first component that will be left remaining on the "main diagonal" (down from left to right) is known as a "pivot".  Nothing though is really "pivoted" as far as I can see.

Multiplying (1,2,1) by 3 will give (3,6,3), which when subtracted from corresonding components in (3, 8, 1) leaves (0,2,-2).  The updated matrix is then:

$$
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1\\
   0 & 2 & -2\\
   0 & 4 & 1\\
  \end{array} } \right]
\
$$

.

Notice that row 1 is left unchanged.  I'm not sure why that's allowed, but it is.  Implicitly, row 1 is multiplied by 0 and subtracted from row 3, but in real life we would ignore this step because row 3 already has a zero in column 1.  Now we eliminate for in (0,4,1) by multiplying (0,2,-2) by 2 and subtracting it from row 3.  Finally we are left with:

$$
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1\\
   0 & 2 & -2\\
   0 & 0 & 5\\
  \end{array} } \right]
\
$$

.

Some notes about this result:
* A matrix in this arrangement is said to be "upper triangular" and is often designated by a "U".  This is actually the most common calculation in scientific computing.
* **Pivots can never be 0**.  If they are, the matrix cannot be solved by this method.  On a related note: a 0 pivot on the main diagonal means that the matrix is not invertible.
  * The reason why 0 can't be a pivot is that you'll end up with an insoluable statement like "0y = 8".  There is no value for y that could make this statement true.  Even if there is more than one variable in the row, if your 0 is at the pivot position you'll end up in the same kind of jam.
  * You can also end up with statements like "0y = 0", which has infinitely many solutions and therefore no solution.
* For a matrix in this arrangement, the determinant is the result of multiplying the pivots.

### Notes on Failure/Challenges to Matrix Inversion

* Only square matrices can have inverses.
* If 2 rows or columns are identical, a 0 pivot must result, and the matrix will have no inverse.
* In general, the matrix will be unsolvable if we cannot escape having a 0 pivot.  
* Swapping rows is allowed.  If there are 0s at a pivot position for an equation, this may be resolvable by swiching rows, as long as the non-zero values can be used in a pivot point somewhere.  For example, if (0,2,-2) in the above example had initially been in row 1, we could resolve this problem by swapping its place wherever (1,2,1) was.
* Row switching can be done at any stage of thep process. For example, if elimination by multiplication-and-subtraction of one row with another caused a zero pivot, we may still be able to resolve the problem through row-switching. 

### Using Back Substitution

To continue solving the equation system, we include b in the matrix after the elimination process is complete, like so:

$$
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1 & 2\\
   0 & 2 & -2 & 6\\
   0 & 0 & 5 & -10\\
  \end{array} } \right]
\
$$

This way of including the b vector in the A matrix is known as an "augmented matrix".  Although we did not show it, the values in the b column were multiplied and subtracted in exactly the same way, for the corresponding rows, as was done to the matrix on the left hand side.  That is why b does not equal its original values here.  

By convention, the left hand side matrix that results from elimination operations on A is relabled to "U", and the post-elimination b column is relabled to "c".

We can re-write our original equations after the elimination process:

x  + 2y +   z = 2
     2y + -2z = 6
           5z = -10

We can relable this equation system as "Ux=c".  Now we can do "back substitution", solving for z first in the 3rd line down, then y in the second line, and finally x in the first line.  The result is that z = -2, y = 1, and x = 2.

### Expressing the Elimination Steps as Matrices

Initially, we implemented elimination by multiplying scalars to a row and subtracting it from another row.  This could also be done matrix multplication. For example, the matrix $E_{21}$:

$$
\
  \left[ {\begin{array}{cc}
  1 & 0 & 0 \\
  -3 & 1 & 0 \\
  0  & 0 & 1 \\
  \end{array} } \right]
\\text{ when multiplied times }
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1\\
   3 & 8 & 1\\
   0 & 4 & 1\\
  \end{array} } \right]
\\text{ will yield }
\
  \left[ {\begin{array}{cc}
   1 & 2 & 1\\
   0 & 2 & -2\\
   0 & 4 & 1\\
  \end{array} } \right]
\
$$

... just like before.

We can effect the remaining row eliminations using further matrix multiplications.  Notice that designating the "elementary matrix" as $E_{21}$ is supposed to show which rows are used for elimination based on the subscripts of E.

#### "E" Matrices are "Elementary Matrices"

Note that the "E", when using "E" matrix multiplication to do elimination, stands for "elementary", not "elimination" as you might think.  A true elementary matrix will consist of nothing but 1s on the main diagonal, and multipliers on lower diagonals.  This form turns out to be kind of a big deal in making computation easier, because their inverse is simply the same matrix, with the off-diagonal signs reversed on the multipliers.  

For example if 
$
E_{21}\text{ = }
\
  \left[ {\begin{array}{cc}
   1 & & \\
   -a & 1 & \\
   0 & 0 & 1 \\
  \end{array} } \right]
\
\text{, then }
{E_{21}}^{-1}\text{ = }
\
  \left[ {\begin{array}{cc}
   1 & & \\
   a & 1 & \\
   0 & 0 & 1 \\
  \end{array} } \right]
\
$

.

In the "A=LU" form of elimination, this attribute is very valuable, because L is nothing but the product of the inverses of E in reverse order.

### Combining the Matrices Used in Elimination

Remember that the final, post-elimination and post-substitution result matrix is "U", and that the original matrix was A.  We multiplied A by $E_{21}$ and $E_{32}$ to get U.  Using the notation for matrix multiplication, we can write the entire process as $E_{32}\left(E_{21}A\right)\text{ = }U$.

Notice that you cannot change the left-right order of these matrices; they must operate on A in the order specified in order to get U.  However, by the *associative law* of multiplication, you can move the parentheses to  
$\left(E_{32}E_{21}\right)A\text{ = }U$ , so that I'm multiplying the 2 elementary matrices first in the order operations.  In principal, you can do this, but it is actually inefficient.

Remember that, in Matrix Multiplication:
* **The associative property is true (AB)C=A(BC).**, but
* **The commutative property is false $AB\neqBA$.**

### Using Permutation Matrices in Matrix Elimination

If you need to swap rows during the elimination process, this can also be done using only matrix multiplication.  To do this, you use a "permutation matrix", which is nothing but an identity matrix with the 1s and 0s shuffled such that multiplying by it will reorder the rows without changing the values or their column order within a row.  **This must be done with the permutation matrix on the left hand side of the matrix it is operating on rearranging**.

An analogous thing can be done to exchange columns via multiplication.  **HOWEVER, column rearrangement must be done via multiplication using an permutation matrix on the right hand side**.  

A permutation matrix is often designated with a P and a subscript indicating which rows (columns) are being swapped.

### Gauss-Jordan $AI=IA^{-1}$ Matrix Elimination.

Sources:
* https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/inverse-matrices/
* Strang: p83

A challenging problem involves seeking the inverse of the following matrix A, which has only coefficients of 1, and only 2 variables:

$$
A=
\
  \left[ {\begin{array}{cc}
   a & b & b\\
   a & a & b\\
   a & a & a\\
  \end{array} } \right]
\
$$

The reader is asked to "find the conditions on a and b that make A invertible, and find $A^{-1}$ when it exists."  The meaning is that we should find the a and b values of an inverse matrix of A.

It is immediately obvious that a cannot be 0, or you will have the failure condition of a 0 pivot.  Related to this, b cannot equal a, because elimination steps will then subtract b-a, resulting in zero pivots.

This matrix can be used to illustrate the $\[A|I\]\rightarrow\[I|A^{-1}\]$ approach to finding a matrix inverse.

In this approach, we begin by specifying an "augmented matrix" that has the identity matrix I and A side by side, and then its opposite on the right of an arrow in the form:

$$\[A|I\]{{...}^{\rightarrow}}[I|A^{-1}\]$$

Some notes about this notation:
* The "..." signals that multiple steps may be needed on the right hand side of the arrow to get the right side into final "I$A^{-1}$ form.
* This is not an equation.  Rather it is saying "we will transform AI into I$A^{-1}$".
  * In this process, it's typical to just show the successive modifications of the "right side of the arrow", which are displayed as changes to the left side.  This was confusing to me for two reasons:
    * although it's not an equation, it did seem like we were suddenly free to change only one side of an equation, ignoring the original "left side".
    * it was strange to act on entire rows.  Up to this point, a separate matrix E has been multiplied times both sides of an equation EAx=Eb. Suddently there's just one matrix, apparently acting on nothing, with its entire row modified.
  * These apparent contradictions if we understand $\[A|I\]{{...}^{\rightarrow}}[I|A^{-1}\]$ to indicate a process in which *both sides* the equation $\[A|I\]=\[A|I\]$ of the equation are acted on in an identical manner.  This would be allowed, and the left-right redundancy means we can just show successive pictures of the "right side".  Ultimately we will end up with $[I|A^{-1}\]=[I|A^{-1}\]$ on both sides of the equation, or fail.  Thus, "successive changes to an identity equation" are what is meant by the "{{...}^{\rightarrow}}" process arrow.

In the below example, the left hand side of the arrow has been filled in by rote as $\[A|I\]$. The arrow connects the current state on the left with its post-operation(s) state on the right hand side.  

The right hand side of the arrowd has been filled in with calculations using two successive steps.  The first step subtracted line 1 from line 2, and the second step subtracted line 1 from line 3.  

$$
\left[
  \begin{matrix}
    a & b & b \\
    a & a & b \\
    a & a & a \\
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
{{...}^{\rightarrow}}
\left[
  \begin{matrix}
    a & b & b \\
    0 & {a-b} & 0 \\
    0 & {a-b} & {a-b} \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
     1 & 0 & 0\\
     -1 & 1 & 0\\
     -1 & 0 & 1\\
    \end{matrix}
  \right.
\right]
$$

Notice the following things
* The "$A^{-1}$" portion of the matrix on the right of the arrow.  We obtained this also in two steps that were identical to what we did on the "I" portion: we subtracted row 1 from row 2, and then row 1 from row 3.  --**This is the possible computational advantage of the $\[A|I\]\rightarrow\[I|A^{-1}\]$ G-J approach, which you may wish to use.**  Specifically, instead of imagining a matrix E or P that could be multiplied by A to bring it closer to a triangular form, the computation task is reduced to (multiplying by a scalar and) subtracting one row from another.  Depending on the problem, this may be easier.

At this point, we can just look at each successive steps of operations we to get to $I|A^{-1}|$.

We continue by subtracting line 2 from line 3 for both the "I" and "$A^{-1}|$" portions:

$$
\rightarrow
\left[
  \begin{matrix}
    a & b & b \\
    0 & {a-b} & 0 \\
    0 & 0 & {a-b} \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
     1 & 0 & 0\\
     -1 & 1 & 0\\
     0 & -1 & 1\\
    \end{matrix}
  \right.
\right]
$$

We have "I" in triangular form, so now we have to begin to turn the diagonal values of "I" into 1, and the off-diagonal elements into 0.  Again, duplicating these operations on the "$A^{-1}|$" portion will simultaneously yield the inverse matrix if one exists.

We continue with 3 steps, the results of which are shown here:
1. We divide the first row by 1 to get 1 in the (1,1) position.
2. We divide the second row by a-b to get 1 in the (2,2) position.
3. We divied row 3 by a-b to get 1 in the (3,3) position.

$$
\rightarrow
\left[
  \begin{matrix}
    1 & \frac{b}{a} & \frac{b}{a} \\
    0 & 1 & 0 \\
    0 & 0 & 1 \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
     \frac{1}{a} & 0 & 0\\
     \frac{-1}{a-b} & \frac{1}{a-b} & 0\\
     0 & \frac{-1}{a-b} & \frac{1}{a-b}\\
    \end{matrix}
  \right.
\right]
$$

Finally, we need to turn $\frac{b}{a}$ in row 1 into 0 to complete the identity matrix, and the corresponding changes to the "$A^{-1}$ portion should then be complete as well.
Contemplateing the "I" portion of the augmented matrix a while, you can see that the operation we need times is to subtract $\text{-}\frac{b}{a}\left(row 2 + row 3\right)$ from row 1.  For example component 1,2 $\frac{b}{a}$, you can see that $\frac{b}{a}\text{ - }{\frac{b}{a}\left(1+ 0\right)}\text{ = }\frac{b}{a}\text{ - }\frac{b}{a}\text{ = }0$.  

When we do this, we get:

$$
\rightarrow
\left[
  \begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1 \\
  \end{matrix}
  \left|
    \
    \begin{matrix}
     \frac{1}{a-b} & 0 & \frac{-b}{a\left(a-b\right)}\\
     \frac{-1}{a-b} & \frac{1}{a-b} & 0\\
     0 & \frac{-1}{a-b} & \frac{1}{a-b}\\
    \end{matrix}
  \right.
\right]
$$

The right side of this is now $A^{-1}$.  It can be cleaned up by pulling out the $\frac{1}{\left(a-b\right)}$:

$$
A^{-1}\text{ = }
\frac{-1}{\left(a-b\right)}
  \left[
    \begin{matrix}
     1 & 0 & \frac{-b}{a}\\
     -1 & 1 & 0\\
     0 & -1 & 1\\
    \end{matrix}
  \right]
$$

## Matrix Elimination = Factorization: A = LU

Sources:
* Strang: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/factorization-into-a-lu/
* Strang, sec. 2.6, p95.

### General Notes on LU Notation in ITLA:

* "E" refers to the set of matrices that multiply the orginal matrix A to get the "upper triangular" matrix U.  It is called U to emphasize the fact that after E acts on A, only values on or above the diagonal will have non-zero values.
    * Each "sub E" [my words], denoted for example like $E_21$ is an identity matrix isolating a single subtraction that it enacts on A.  The sub matrices are written from right to left with the first matrix that acts on A being right-most, and the last matrix left-most. It is the product of all these sub-Es, multiplied in order, which gives you E.          * Following from these facts, the product of E acting on A is the upper triangular matrix U, or EA = U .
* $E^{-1}$ references the product of the inverses of these matrices, with the each sub- $E^{-1}$ [again, my phrase] isolating an addition it enacts on U.  The sub-matrices are show in reverse of the order shown for E.  When this set of matrices act on the result U in EA = U, they reverse the effect and are said to "recover A".
    * It is crucial to remember that, as an inverse, each component $E^{-1}$ has its off-diagonal values reversed.  Also, each component of $E^{-1}$ is multiplied succesively by the matrix to the left of it. to get the full  $E^{-1}$.
    * L confusingly is **exactly the same thing as $E^{-1}$ **.  It stands for "lower triangular", because when all the sub- $E^{-1}$ matrices are multiplied together, you get a matrix with only non-zero values on or below the diagonal.
    * Following from these facts, the convention is to say that A = LU.
* L is lower triangular, and U is upper triangular.  The phrase "LU decomposition" comes from the fact that in the equation A = LU, A is "decomposed" into the product of a lower and an upper matrix.
* Related to these processes is Gaussian matrix multiplication, which performs elimination on an "augmented" matrix combining A and b from the equation Ax = b into [A b].  Performing elimination on this matrix is said to update it to [U c] which can then be noted in the equation "Ux = c".
* "LDU" is an extension of LU, in which the diagonal elements of U are isoluated in 

### Motivation for A = LU Decomposition/Factorization

#### Sources:
* ITLA,v6 p49FF: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/MIT_18_06_unit_1_exam_solutions.pdf

* I found it difficult to get a clear statement of motivation for LU decomposition in Strang, but here are three important reasons:
    * **computation efficiency in finding a matrix inverse:**
      * for an invertible matrix, Gauss-Jordan elimination to find the inverse is pretty painless.  However, for large matrices it gets computationally expensive.
        * with this in mind, note that on Strang 49 we find that $A^{-1}\text{ = }\left(LU\right)^{-1}\text{ = }U^{-1}L^{-1}$ . --Remember that when you take the inverse of a product of two matrices you reverse the order of their multiplication.
        * It turns out that decomposing A into L and U, and then multiplying the $U^{-1}L^{-1}$ , is a computationally less expensive way of getting the inverse of a matrix than just doing G-J on A itself, at least for large matrices.  This has to do partly with the way you can calculate L out of its $E^{-}$ components with actually multiplying the components together.
    * **ease of calculating a determinant**
      * once you get a matrix A decomposed into LU, and assuming that U has no 0 pivots, the determinant is just the product of the diagonal values of U.
    * **it's faster to do back substitution on U than to solve A directly** .

**Note that matrix elimination using the A = LU process is impossible if row exchanges are necessary.**

#### A 2x2 Example of A = LU:

Suppose we have a simple matrix A, which we operate on with E in order to produce U.  Assume that no row exchanges are necessary.

We can easily imagine $E_{21}$ in this case:

$$
  \left[
    \begin{matrix}
    1 & 0 \\
    -4 & 1 \\
    \end{matrix}
  \right]
  \left[
    \begin{matrix}
     2 & 1 \\
     8 & 7 \\
    \end{matrix}
  \right]
\text{ = }
  \left[
    \begin{matrix}
     2 & 1 \\
     0 & 3 \\
    \end{matrix}
  \right]
$$

The A = LU form of this equation is:

$$
\left[
  \begin{matrix}
   2 & 1 \\
   8 & 7 \\
  \end{matrix}
\right]
\text{ = }
  \left[
    \begin{matrix}
    1 & 0 \\
    4 & 1 \\
    \end{matrix}
  \right]
  \left[
    \begin{matrix}
     2 & 1 \\
     0 & 3 \\
    \end{matrix}
  \right]
$$

... where the 4 component in L simply adds back what -4 in E removed.
Notice that L is in a "lower triangular" format.  L stands for "lower".
Notice also that L has ones on the diagonal, whereas U has the pivots on the diagonal.  In such cases, sometimes the pivots are separated out into an "LDU" format, in which the diagonals are factored out like so:

$$...=LDU$$

$$
\left[
  \begin{matrix}
  1 & 0 \\
  4 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
   2 & 1 \\
   0 & 3 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
   1 & \frac{1}{2} \\
   0 & 1 \\
  \end{matrix}
\right]
$$

Where the diagonals in D are factored out of U by diving U row 1 of u by 2, and row 2 of U by 3.

Assume that no row exchanges are necessary.

Now suppose we have 3x3 matrices for EA=U.  We can use notation to describe the process: $E_{32}E_{31}E_{21}A=U$.  Remember that the steps used to modify A are displayed in the reverse left-right order in which they act (E21 acts on A first).  

To construe this as A=LU, we can simply apply the inverses of E, but in the opposite order: $A={E_{21}}^{-1}{E_{31}}^{-1}{E_{32}}^{-1}U$

This A=LU is the preferred form.  To see why, look at a simple 3x3 matrices example requiring only 2 elementary matrices, which we multiply out to see their product:

$$
E_{32}E_{21}\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & -5 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  -2 & 1 & 0 \\
  0 & 0 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  -2 & 1 & 0 \\
  10 & -5 & 1 \\
  \end{matrix}
\right]
\text{ = E}
$$

This is suboptimal, because the order of operations causes the $_{31}$ position to be populated (an in general, LU positions to be populated), which makes further operation more computationally difficult.

If we instead multiply the E inverses in reverse order, the result is computationally easier.
Notice that with modified identity matrices like these E examples, all that is required for the inverse is to reverse the sign.

$$
{E_{21}}^{-1}{E_{32}}^{-1}\text{ = }
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
  0 & 5 & 1 \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  2 & 1 & 0 \\
  0 & 5 & 1 \\
  \end{matrix}
\right]
\text{ = L}
$$

Because of the multiplication order, the 10 in the 31 position is now 0.  This result matrix L can be used on the right side of the equation A = LU.  This is computationally easier because the multipliers go "directly into L", meaning that the were not modified from their original value in A, without generating additional multipliers (as in the EA = U approach).  This makes the A = LU approach superior.


#### Matrix Elimination = Computational Expense

Suppose you want to multiply EA to get U, and A is 100x100 square matrix with no 0 values, for which no row exchanges are necessary. So consider n= rows = columns = 100.  Suppose you consider an addition + subtraction of two components as a single "operation".  Then the first operation in the process would be 100^100, after which the numbers in row 1 and column 1 would remain unchanged.  The next changes would be done to a smaller square of 99^2 components from row 2--100 and column 2--100, and so on.  The result is that these "100x100" operations are done 100 times, but for a square of diminishing size, so that we can estimate the total computations required as p*n^3, where p dis some fraction reflecting the reduction in total computations because the square of rows and columns steadily diminishes.  "p" is 1/3.  Interestingly, this reflects the fact that we've integrated x2 over x in the calculus sense, where the integral of x^3 would be $\frac{1}{3}x^2$.

The computational cost of operating on the n-row column b is n^2.  The cost for every right hand side is always n^2.  


### Matrix Elimination = LU Decomposition Example

Sources:
* MIT 18.06: https://youtu.be/-eA2D_rIcNA

Suppose we have this 3x3 matrix:

$$
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  a & a & a \\
  b & b & a \\
  \end{matrix}
\right]
$$

We want to do LU-style decomposition for this matrix if it is possible, and state the conditions under which it will be possible.  
First off, we can note that it won't work if a = 0, or probably if a=b, since we'll end up with a 0 pivot.
Next, to initiate the process, we can begin multiplying A by elementary matrices to generate 0s below the pivots.

$$E_{21}A=U_1$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  -a & 1 & 0 \\
  0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  a & a & a \\
  b & b & a \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  0 & a & 0 \\
  b & b & a \\
  \end{matrix}
\right]
$$

$$E_{31}U_1=U_2$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  -b & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  0 & a & 0 \\
  b & b & a \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  0 & a & 0 \\
  0 & b & a-b \\
  \end{matrix}
\right]
$$


$$E_{32}U_2=U$$

$$
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & -b/a & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  0 & a & 0 \\
  0 & b & a-b \\
  \end{matrix}
\right]
\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 1 \\
  0 & a & 0 \\
  0 & 0 & a-b \\
  \end{matrix}
\right]
$$

Next, to obtain L, we take the product of the inverses of the elementary matrixs multiplied in reverse order.  Remember that for an elementary matrix, the inverse is identical to E, but with the off-diagonal multipliers having reversed signs.  So:

$$L\text{ = }{E_{21}}^{-1}{E_{31}}^{-1}{E_{32}}^{-1}$$

$$
L\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  a & 1 & 0 \\
  0 & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  b & 0 & 1 \\
  \end{matrix}
\right]
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & b/a & 1 \\
  \end{matrix}
\right]
$$

With elementary matrices in this arrangement, L is obtained by simply "filling" in the diagonal multiplier values:

$$
L\text{ = }
\left[
  \begin{matrix}
  1 & 0 & 0 \\
  a & 1 & 0 \\
  b & \frac{b}{a} & 1 \\
  \end{matrix}
\right]
$$

.

### Permutaions

### Sources
* Strang: https://youtu.be/JibVXBElKL0

Permutations are typically denoted P, and act on a matrix to effect row exchanges.

Let P stand for a permutation matrix that acts on A to exchange its rows.  For a 3 by 3 matrix, there are 6 possible permutation matrices: I, which exchanges nothing, 3 P matrices which swap 2 rows (e.g. P_21), and 2 matrices which can exchange all rows.  

**Any square matrix of row count n will have n! possible permutation matrices.**

Additional Notes:
* permutation matrices are "their own inverse" with respect to the matrix A on which they act: for example, if P_21 acts on A to swap rows 2 and 1, P_21 acting on A again will reverse the change.
* the inverse of a permutation matrix is actually the transpose: $P^{-1}\text{ = }P^T$.  Consequently, $PP^T=I$.

#### Matrix Elimination = Factorization: A = LU With Row Exchange

When permutations are necessary, they can be enacted on A prior to the elimination process, such that $PA\text{ = }LU$.

### Symmetric Matrices

### Sources
* Strang: https://youtu.be/JibVXBElKL0

In many applications we use Symmetric matrices because of their computation-friendly properties.
Symmetric matrices related to transposed matrices definitionally, because transposition does not change the arrangement of their components.  The identidy matrix I is the most obvious example.
Additionally, multiplying a matrix by its transpose will guarantee a result that is symmetric, because of the order in which the respective components are multiplied together.

## Vector Spaces and Subspaces

### Sources
* Strang: https://youtu.be/JibVXBElKL0
* Strang: p120FF.

### Definition of (Real) Vector Space

* In terms of vectors and components: the space $R^n$ consists of all real number vectors v with n components.
* In terms of constraints on math operations: A (real) vector space is a set of "vectors" together with rules for vector addition and for multiplication by real numbers.
  * These conditions are:
    * the result of any addition of the vectors stays in the same space
    * the result of any multiplication of the vectors by a scalar stays in the same space
      * in short, all of its linear combinations have to remain in the space.

Say we took the quarter of R2 vector space belonging to all non-negative values (e.g. for x and y gtet 0).  Then any addition of these components would still be in the same space.  However, subtracting them would take me out of this quadrant and yield negative values.  This situation is described by saying that the vector space is "closed" for addition, but not subtraction.

### Definition of (Real) Vector Subspace

A subspace of a vector is a space meeting the conditions of its larger space.  This includes all of the vectors and components in the large space.  

For example, what are the possible subspaces of R2?  They include:
* all of R2
* any line going through the origin
* the 0 vector, sometimes noted as subspace Z.

If a space exists correctly within a larger space, meaning that it remains "closed" inside the larger space when math operations are performed on its values, then it is said to be a "sub space" of the larger space.  -- For example, a subspace of R^n.  An easy example is a vector being a subspace of R^n.  

Note that every subspace has to contain the 0 vector.  The reason is that you always have to be able to multiply the subspace by 0 ... which will then equal the 0 vector.  Consequently any line in the space has to pass thorough the origin to be in the subspace.  However, the linear combination of 2 or more vectors, each of which are in the subspace, may yield results that are not on vectors passing through the origin (see example below).

The same would be true for R3, but would also include any plane through the origin as an additional subspace.

### Definition of Column Space

The column space consists of all linear combinations of the columns.  These linear combinations contain all possible values of Ax, and fill the column space of C(A).

**It follows that Ax = b is solvable if and only if b is in the column space of A.**

### Vector Spaces and Functions

#### Sources
* ITLA, 5th Ed., Chapter 3.1.
* https://youtu.be/SzZaQnzstfE

#### Notes
* Linear algebra mostly focuses on linear equations, so variables of a higher order than x (e.g. $x^2$ ) may not "belong" to linear algebra and not be represented in a formula like Ax = b, depending on whom you ask.  That said:
    * A polynomial of a higher order than x can be represented, but in a regular Ax = b or Ax = 0 format the information about the variable's order or degree will be lost.  Here is a typical example:
        * Say you have the system 1-x, 1 + x, and $x^2$ .
        * Because x is already "taken" as a variable, you can represent each function as being multiplied by a separate value t, and add them together and set them = 0.  This must be allowed because (1) t could equal 1, which would make no change to the equations, and (2) we are stipulating that the equations are a system and that they are in the same vector space of all functions using real numbers, which means that under the addition requirement for a vector space they can be added, and in solving them as a system we can stipulate that they have some common solution, in this case 0.  So we say that:
          
          $$t_{1}\left(\text{ - }x\right)\text{ + }t_{2}\left(\text{ + }x\right)\text{ + }t_{3}x^2\text{ = }0$$ .

          We can then rearrange this equation in terms of factors commonly multiplied by the degree of variable, from constant to $x^2$, thus:

          $$\left(t_{1}\text{ + }t_{2}\right)1\text{ + }\left(t_{2}\text{ - }t_{1}\right)x\text{ + }t_{3}x^2\text{ = }0$$ .

          Then we can set x = 0 and construe the equation as:

          $$\left(t_{1}\text{ + }t_{2}\right)\text{ = }0$$
          $$\left(t_{2}\text{ - }t_{1}\right)\text{ = }0$$
          $$t_{3}\text{ = }0$$

This can then be construed as a matrix A times a vector t = 0 and A can be row-reduced to give finally give It = 0.  Notice that: 
* in doing this, we demonstrate (or could fail to demonstrate) that the polynomial system is linearly independent.
* we have lost all info about the degree of variable: I don't believe there is anything that would work backward from It = 0 to return you to the original polynomial.  An infinite number of original equations could row-reduce to It = 0.
* the variables are in the place of b in "Ax = b", while the variables t that we introduce took the place of "x" in "Ax = b".

Finally, it is possible to use linear algebra notation to capture variables with a degree greater than 1 by using a transpose.  For example $x^2$ can be $x^{T}Ix$ .  
I'm not sure though whether the info that would let you return to the original formulas could be preserved as a system is solved.

### Column Spaces Defined in Terms of M components.

Suppose you have an mxn matrix with components in R real numbers.  You can see that the set of potential columns would be limited to those that have m rows.  So you can think of column spaces as being subspaces of $R^m$ (not $R^n$ ).

### 8 Rules for Vector Spaces

There are 8 rules for vector spaces.  Remember that these are **spaces** , not just vectors.  So we're talking about vectors such that the rules of addition, multiplication, and inclusion of the zero vector remain true for the vector in question.

#### x + y = y + x
#### x + (y + z) = (x + y) + z
#### There is a unique "zero vector" such that x + 0 = x for all x.
#### For each x there is a unique vector -x such that x + (-x) = **0**.
#### 1 timex x = x .
#### $\left(c_{1}c_{2}\right)x\text{ = }c_{1}\left(c_{2}x\right)$
#### c(x + y) = cx + cy
#### $\left(c_{1}\text{ = }c_{2}\right)x\text{ = }c_{1}x\text{ + }c_{2}x$

### S and V Spatial Notation

We can also consider a space as any set of vectors S in a vector space V.  The subspace SS would then equal all *possible* linear combinations of vectors in S.

### Notes on Vector Space Linear Combination, Unions, and Intersections

#### Sources
* MIT 18.06: https://youtu.be/QQpvGlF_1Qo
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/qqpvglf_1qo-1/

Suppose you had two vectors:

$$
x_1\text{ = }
\
  \left[ {\begin{array}{cc}
   0 \\
   1 \\
   3 \\
  \end{array} } \right]
\
\text{, }x_2\text{ = }
\
  \left[ {\begin{array}{cc}
   2 \\
   4 \\
   0 \\
  \end{array} } \right]
\
$$

Consider the following questions:
What is the (smallest) $V_1$ subspace generated by $x_1$?
What is the (smallest) $V_2$ subspace generated by $x_2$?
Describe $V_1\cap{V_2}$.

Answers:
* Note the phrase "generated by" here.  It indicates we're talking about doing linear operations on $x_1$ or $x_2$.  Reflecting on it, you can see that any multiplier of these vectors would result in extending the vector into a line.  In order to stay in the subspace, the line would have to extend through the origin so that the **0** vector can be a result of the 0 multiplier.  Mathematically, we can also see that any additions via linear operations on $x_1$ or $x_2$ would have to have a result equal to n times that vector, thus ensuring the result remained on the same line.
* When we talk about the "smallest" subspace, we could either refer to a line or possibly a point.  Y
* For $V_1\cap{V_2}$, you can see via diagram, and also looking at the vectors values, that the only place they can interesect is at the origin.  The origin fits all the requirements of being in both $x_1$ and $x_2$ subspaces, and it is the only one that does.

Find $V_3$ = subspace generated by linear operations on {$x_1$,$x_2$}.

Answer:
When we combine $x_1$,$x_2$ into a single linear combination, you can see that this linear combination could generate an entire plane on which these vectors would both lie.  

Is $V_3$ equal to $V_1\cup{V_2}$?

Answer: It's strange to think of a "union" of two lines.  However, when you consider that a union means "all of the things in one set together with all the things in another set", you can see that it would just be all the points in one line together with all the points in another: in other words, a "cross" of the two lines, intersecting at the origin.

From this, it's clear that a cross of specific points is not equal to the larger plane which would contain it.

Find a subspace S of such that $x_{1}\notin{S}\text{, }x_{2}\notin{S}$. 
Answer: you can see that may linear combinations of $x_{1}$ and $x_{2}$ would yield a point that is not a member of $V_1\cup{V_2}$.

What is the intersection of $V_3$ with the XY plane?
The intersection of the $V_3$ plane with the XY plane would be a straight line again.  Because the xy plane is 0 on the z axis, the only line that satisfies this condition is V2, so the intersection of V3 and xy plane must be V2.


### Vector Spaces and Linear Combination: Examples

Sources:
MIT 18.06: https://youtu.be/S8DQZjE4V8U

Notes: 
In these examples, learning to use the analytic approaches involves is more important that being able to understand the solutions.  Keep these in mind and try cycling through them when you look at a new linear formula.
* In example 1, the problem is re-written as a matrix tiems a vector and set = 0 in Ax=0 format.  This makes it easier to consider whether any results of addtion or subtraction of the formula's Ax antecedents would stay in the same space.
* In example 2, we simply try a few scalar multipliers to see if the results stay in the same space.  The formula is kept as a formula.
* In example 3, we are given a vector of static scalar values plus 2 vectors of values multiplied by distinct scalar variables.  The approach used is to consider whether the static values vector is a linear combination of the other two.  Since it is a linear combination, we can simplify the equation and then consider whether any linear combination in this simplified version would keep its results in the space.  I'm not sure how you decide whether a scalar vector plus cv + dw ... combinations are valid linear systems.
* In example 4, we simply consider the results of the linear system geometrically and ask whether they stay in the same space.

It's also important to practice inferring whether the notation refers 

Here are additional notes on vector subspaces, using a linear combinations of a vector of 3 values: 

$$
\
  \left[ {\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } \right]
\
$$ 

.  

Consider whether each one is a subspace of $R^3$:

Note that R3 with respect to a vector like this can sometimes be written as: 

$$
\mathbb{R}^3\text{ = }\left\\{
\left[{\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } \right]
\right\\}
$$

.

Looking a variety of sets can reinforce our understanding of what a subset is.  For each of these, we'll reason out why the are or aren't subsets of $R^3$.
Remember that:
* a sub space is one such that all linear combinations of the components will yield a result that is still in the same "space" as the components.
* a null space is the set of values x the matrix A can act on to yield a zero vector b.
* a column space is the set of all results that can be obtained via linear combinations of the columns.  This set of all results is sometimes called the "span" of the columns.

#### Example 1: $b_1\text{ + }b_2\text{ - }B_3\text{ = }0$ .

Answer:
This example can be re-written as 

$$
\left[1,1,-1\right]
\left[{\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } 
\right]
$$

Notice that  $\left[1,1,-1\right]$ is a matrix.  When acted on the this matrix A and set equal to 0, this vector of b values describes the null space for Ab, *which is a subspace.*  This is easier to see when you consider addition and multiplication: any additon of two vectors b that were able to yeild a 0 vector would also yield a vector that when acted on by A would yield the zero vectors.  Of course, multiplying the b vector would do the same since it would multiply every b value equally.

#### Example 2: $b_1b_2\text{ - }B_3\text{ = }0$ .

Answer: 
These values are not a subspace.  It is easiest to see by multipying a vector b values that solve Ab=0.  One such vector is (1,1,1) which yields 1\*1-0.  But multiplying this vector, say times 2, yeilds 2\*2-2=0, which is false.  The result of multiplication does not stay in the same "space" as its antecedents.

#### Example 3: 

$$
\left[{\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } \right]
\text{ = }
\left[{\begin{array}{cc}
   1 \\
   0 \\
   0 \\
  \end{array} } \right]
\text{ + }c_1
\left[{\begin{array}{cc}
   1 \\
   0 \\
   -1 \\
  \end{array} } \right]
\text{ + }c_2
\left[{\begin{array}{cc}
   1 \\
   0 \\
   1 \\
  \end{array} } \right]
$$

Answer:

Yes, it is a subspace of $\mathbb{R}^3$.  The last 2 vectors are linearly independent and make a plane.  The vector $\left[{\begin{array}{cc}
   1 \\
   0 \\
   0 \\
  \end{array} } \right]$ is a linear combination of the other two, specifically $\frac{1}{2}
\left[{\begin{array}{cc}
   1 \\
   0 \\
   -1 \\
  \end{array} } \right]
\text{ + }\frac{1}{2}
\left[{\begin{array}{cc}
   1 \\
   0 \\
   1 \\
  \end{array} } \right]
$

.

Therefore, the whole thing can be re-written as:

$$
\left[{\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } \right]
\text{ = }
\left(\frac{1}{2}\text{ + }c1\right)
\left[{\begin{array}{cc}
   1 \\
   0 \\
   -1 \\
  \end{array} } \right]
\text{ + }
\left(\frac{1}{2}\text{ + }c2\right)
\left[{\begin{array}{cc}
   1 \\
   0 \\
   1 \\
\end{array} } \right]
$$

I infer that the parenthetic notation, e.g. (1/2 + c1), must mean just a value in this case and not a vector, since a 2-component vector cannot multiply a 3-component vector.

It is clear that any value of c1 and c2 will yield a pair of vectors that remain in the same plane.  Adding these resultant vectors together will also yield a vector in the same plane. The addition of any two such results will remain in the same plane.  Multiplying such a pair of results, or the addition of their results, will remain in the same plane.

#### Example 4: 

$$
\left[{\begin{array}{cc}
   b_1 \\
   b_2 \\
   b_3 \\
  \end{array} } \right]
\text{ = }
\left[{\begin{array}{cc}
   0 \\
   1 \\
   0 \\
  \end{array} } \right]
\text{ + }c_1
\left[{\begin{array}{cc}
   1 \\
   0 \\
   -1 \\
  \end{array} } \right]
\text{ + }c_2
\left[{\begin{array}{cc}
   1 \\
   0 \\
   1 \\
  \end{array} } \right]
$$

Answer: 

No, it cannot be a subspace. The first vector (0,1,0) is on the y plane .There are no coefficients c1 and c2 that can set the whole equation equal to the 0 vector, because they do not include the y plane.  Consequently the results of the equation cannot include the 0 vector, so this cannot be a subspace.

#### Example 5

Suppose you have vectors v_1 = (1,2,0) and v_2 = (2,3,0).
* Are they linearly independent?
  * Answer: yes, you can see that they are not combinations of each other.
* Are they a basis for some space?
  * Answer: the space of all combinations of cv_1 + dv_2. 
* What space V do they span?
  * The space contains all vectors (x,y,0).
  * Note: span is based on the original (not row-reduced) form of the matrix.
* What is the dimension of V?
  * The dimension of V is 2 because because the basis contains 2 [independent] vectors.  This is the definition of the dimension of V
  * Notes:
      * **so the "dimension" must be the number of independet vectors.** The vectors are in "m" space, but the vectors cannot extend more than n dimensions, however big m might be.
      * the dimension of V is the number of independent column vectors, which need not be based on the row-reduced form.  The row-reduced form is only a tool for assessing independence.
* Which matrices A have V as their column space?
  * Any 3xn matrix, where all the columns are combinations of v_1 + v_2, particularly the 3x2 matrix c_v1 + dv_2.
* Which matrices have V as their nullspace?
  * Any mx3 matrix where all the rows are multiples of (0,0,1), particularly the matrix [0 0 1].  Remember that the nullspace of A must be vectors that are perpendicular to A, so that they can form a 0 dot product.  That is why the columns of N(A) = rows of R(A).
* Describe all vectors v_3 that complete a basis v_1,v_2,v_3 for $\mathbb{R}^3$ .
  * any 3x1 vector where the last component is not zero, so that it will be linearly independent of the other 2 vectors and extend into R3.





