
# Undefined Vectors

## Example 1

### Problem Text
* Though we can think of both as an N-tuple of real values (in other words an ordered list of N-many continuous real numbers), what is the fundamental difference between a point and a vector?

### Tasks
* List the differences between a point and a vector.

### Solution or Solution Steps

#### Facts
* We can add and subtract vectors, but not points.
* We always think of a vector in relationship to an origin point.
* Vectors have an inherent "direction".

# Vectors Facts  
* If one scales a vector by a non-zero value, the resulting vector will lie along the same line.
    *  Vectors are the only object in linear algebra that can be scaled.
* Zero Vector Facts:
  * The 0 vector stays the same for any scalar.  Subtracting the 0 vector from any other vector leaves it unchanged.
  * The 0 vector is part of any legitimate subspace; every legitimage subspace must pass through it.

# Vectors Defined by Symbols

## Example 1

### Premise
* Two vectors, each consisting only of variables unique to each vector, are given.  The user is asked to define the conditions under which one is a multiple of another.

### Problem Text
* "Under what conditions on a, b, c, d is"

$$
\left[
\begin{array}{cc}
c \\ 
d \\  
\end{array} 
\right]
$$

"a multiple m of"

$$
\left[
\begin{array}{cc}
a \\ 
b \\  
\end{array} 
\right]
$$

"?   Start with the two equations c = ma and d = mb. By eliminating m, find one equation connecting a,b,c,d. You can assume no zeros in these numbers."

### Solution or Solution Steps:
* c = ma and d = mb lead to ad = amb = bc. With no zeros, ad = bc is the equation for a 2 ×2 matrix to have rank 1.
    * Notes:
    * with the double equality ad = amb = bc I am not used to modifying 2 items simultaneously, but apparently you can.  Implicitly, what they've done is to first say that c/a = m = d/b.  Then the outer terms on either side multiply the other two terms by a and b, respectively.  That's why you get "amb" as the middle term.
    * I couldn't prove that "the equation for a 2 ×2 matrix to have rank 1" by row elimination.  But you can prove it algebraically at least:
        * If the rank is 1, the second row must be a scalar multiple of the first row. This means there exists a scalar k such that: (c, d) = k(a, b).
            * This translates to the equations:
                * c = ka
                * d = kb
        * Then: ad - bc = a(kb) - b(ka) = kab - kab = 0 .


# Defined Vectors

## Example 1
* Given 2 vectors, take their dot product.

### Solution or Solution Steps
* multiply each component in v by the corresponding component in w, and sum the products.

## Example 2
* To compute the length of a vector, take the dot product of a vector with itself. The square root of this dot product is the vector length.
    * The dot product of a vector is the length squared.

## Example 3 
*  Find Value of Length 2 Vectors Subtracted from Each Other

### Solution or Solution Steps
* subtract the components for one vector from the corresponding components of the other
* take the dot product of the resulting vector of differences
    * take the square of every component, and sum the components
* take the square root of that dot product

* NOTE: For orthognal vectors, the process is the same, but the resultant difference vector will always be a vector of 1s. Consequently, the dot product will be n, and the length will be sqrt(n).

## Example 4
* Create a unit vector from a defined vector.

### Solution or Solution Steps
* compute the vector's length
* divide every component by that length, so that the components sum to 1.

## Example 5

### Premise:
* Given a list of coordinates, devise the vectors they describe, and:
    * show the results of their addition and subtraction
    * show their lengths.

### Problem Text:
*  "Going around a triangle from (0, 0) to (5.0) to (0, 12) to (0, 0), what are those three vectors u, v, w?" 
*  "What is u + v + w? What are their lengths ||u|| and ||v|| and ||w||?"
    *  "The length squared of a vector $\large{u\text{ = }\left(u_1,u_2\right)\text{ is }{\|\|u\|\|}^2\text{ = }u_1^2 + u_2^2}$ ."

### Solution or Solution Steps:
*  The three edges going around the triangle are u = (5, 0), v = (−5, 12), w = (0,−12).   Their sum is u + v + w = (0, 0). Their lengths are ||u||= 5, ||v||= 13, ||w||= 12.
    *  Notes:  hen you're doing this "walk around the straight edges of a triangle or parallelogram" thing, always remember to check that your result vectors sum to 0.

## Example 6

### Premise:
*  Given a set of vectors, describe the space that their linear combinations fill.

### Problem Text:
"Descnbe geometrically (line, plane, or all of R3) all linear combinations of"

$$
\text{(a)  }
\left[
\begin{array}{cc}
1 \\ 
2 \\  
3 \\  
\end{array} 
\right]
\text{ and }
\left[
\begin{array}{cc}
3 \\ 
6 \\  
9 \\  
\end{array} 
\right]
\text{,  (b)  }
\left[
\begin{array}{cc}
1 \\ 
0 \\  
0 \\  
\end{array} 
\right]
\text{ and }
\left[
\begin{array}{cc}
0 \\ 
2 \\  
3 \\  
\end{array} 
\right]
\text{,  (c)  }
\left[
\begin{array}{cc}
2 \\ 
0 \\  
0 \\  
\end{array} 
\right]
\text{ and }
\left[
\begin{array}{cc}
0 \\ 
2 \\  
2 \\  
\end{array} 
\right]
\text{ and }
\left[
\begin{array}{cc}
2 \\ 
2 \\  
3 \\  
\end{array} 
\right]
$$

. 

### Solution or Solution Steps
*  The combinations give (a) a line in R3 (b) a plane in R3 (c) all of R3.
    * Basically, you're trying to make vector a product of every other vector.
    * Always remember to try and make them sum to zero without multipliers, just to see if its true.


## Example 7 

### Premise
* Given a list of vectors, draw them and their additions and subtractions.

### Problem Text

"Draw...

$$
\text{v = }
\left[
\begin{array}{cc}
4 \\ 
1 \\  
\end{array} 
\right]
\text{ and w = }
\left[
\begin{array}{cc}
-2 \\ 
2 \\  
\end{array} 
\right]
$$

and v+w and v-w in a single plane."

### Solution or Solution Steps

* The key here is to note that each component v1, v2 and w1, w2 is being used in 2 different equations.
  * So what you do is take the vectors apart and then reorganize them so that the pair of equations with v1, w1 can be solved simultaneously using substitution.
  * From there, you continue substitution to solve the rest.

## Example 8

### Premise
* Given a set of defined vectors, compute the results of specified linear combinations which use them.

### Problem Text
"From ..."

$$
\text{v = }
\left[
\begin{array}{cc}
2 \\ 
1 \\  
\end{array} 
\right]
\text{ and w = }
\left[
\begin{array}{cc}
1 \\ 
2 \\  
\end{array} 
\right]
$$

, find the components of 3v + w and cv + dw ."

### Solution or Solution Steps
* 3v + w = (7, 5) and cv + dw = (2c + d, c + 2d).  This is just scalars multiplying vectors.

## Example 9

### Given list of vectors:
* detail what their components sum to.
* specify which combinations are impossible.

### Problem Text
*. "Every combination of v = (1,-2,1) and w = (0, 1, —1) has components that add to ____________. 
*  Find c and d so that cv + dw = (3,3, —6). Why is (3, 3, 6) impossible?"

### Solution or Solution Steps
* 0 (both the individual vectors and the vectors added together sum to 0).
* take note of how the components vertically sum, prior to RRE &c:
    * solutions for b must be in the column space of A; therefore, solutions for b must add their components in the same way that the components of C(A) sum up.  In this case, 3,3,6 is impossible because the components do not sum to 0.
  
## Example 10

### Premise
*  Given a set of defined vectors, and an equation cv + dw, and a list of values for c and d, draw all of the vectors result from filling in c and d.  Describe the results.

### Problem Text

"In the xy plane mark all nine of these linear combinations:

$$
\text{c}
\left[
\begin{array}{cc}
2 \\
1 \\
\end{array} 
\right]
\text{ + d}
\begin{array}{cc}
\left[
0 \\
1 \\
\end{array} 
\right]
$$

... with c = 0,1,2 and d = 0,1,2 ."

### Solution or Solution Steps
*  Simple plug and play equations.

## Example 11

### Premise
*  Given a set of numeric and symbolic vectors, decide if they are linearly independent.

### Problem Text
* "(Not easy) How could you decide if the vectors u = (1,1,0) and v = (0,1, 1) and  w = (a, b, c) are linearly independent or dependent ?"

### Solution of Solution Steps
*  This is sort of tough, but if you just write the 3 vectors out vertically, you'll see that "Certainly x1 has to be a. Certainly x2 has to be c. So the middle components give the requirement a + c = b."  So generally when you get a question that sounds like this, the approach is to write them out, and see if isolation makes any one variable easy to solve, so that you can sole the others apart via substitution.












