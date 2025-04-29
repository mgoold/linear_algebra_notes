
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

# Vector Facts  
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

## Calculate dot product
* Given 2 vectors, take their dot product.

### General Solution
* multiply each component in v by the corresponding component in w, and sum the products.

### Dot Product Example 1
* "Calculate the dot products $u\cdot{v}$ and $u\cdot{w}$ and $u\cdot\left(v\text{ + }w\right)$ and $w\cdotv$ :

$$
u\text{ = ,}
\left[
\begin{array}{cc}
-.6 \\ 
.8 \\  
\end{array} 
\right]
v\text{ = ,}
\left[
\begin{array}{cc}
4 \\ 
3 \\  
\end{array} 
\right]
w\text{ = ,}
\left[
\begin{array}{cc}
1 \\ 
2 \\  
\end{array} 
\right]
$$


#### Solutions

* $u\cdot{v}$ = -.6(4) + .8(3) = 0
* $u\cdot{w}$ = -.6(1) + .8(2) = 1
* $u\cdot\left(v\text{ + }w\right)$ = -.6(5) + .8(5) = 7
* $w\cdot{v}$ = 4(1) + 3(2) = 10

## Calculate vector length
* To compute the length of a vector, take the dot product of a vector with itself. The square root of this dot product is the vector length.
    * The dot product of a vector is the length squared.

### Vector Length Example 1

### Sources
* ITLA v6, sec 1.2: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf
  
#### Problem Text:

"Compute the lengths ||u|| and ||v|| and ||w|| of these vectors:

$$
u\text{ = ,}
\left[
\begin{array}{cc}
-.6 \\ 
.8 \\  
\end{array} 
\right]
v\text{ = ,}
\left[
\begin{array}{cc}
4 \\ 
3 \\  
\end{array} 
\right]
w\text{ = }
\left[
\begin{array}{cc}
1 \\ 
2 \\  
\end{array} 
\right]
$$

."

### Solution
* ||u|| = $\sqrt{{-.6^2}\text{ + }.8^2}$ = 1
* ||v|| = $\sqrt{{4^2}\text{ + }3^2}$ = 5
* ||w|| = $\sqrt{{1^2}\text{ + }2^2}$ = $\sqrt{5}$

## Example 3: length of vector subtraction
*  Find Value of Length 2 Vectors Subtracted from Each Other

### Solution or Solution Steps
* subtract the components for one vector from the corresponding components of the other
* take the dot product of the resulting vector of differences
    * take the square of every component, and sum the components
* take the square root of that dot product

* NOTE: For orthognal vectors, the process is the same, but the resultant difference vector will always be a vector of 1s. Consequently, the dot product will be n, and the length will be sqrt(n).

## Create unit vector
* Create a unit vector from a defined vector.

### Solution or Solution Steps

* compute the vector's length
* divide every component by that length
* when the length is calculated with using these revised components, it will equal 1.  So for example if you had a vector v = (3,4) the dot product would be 3 squared + 4 squared = 25, and the length would be sqrt(25) = 5.  Then the unit vector is (3/5, 4/5).  When you calculate the length of that unit vector by taking the sum of its squared components, the result will be 1.

### Unit Vector Example 1

### Sources
* ITLA v6, sec 1.2: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

"For the following vectors:

$$
v\text{ = ,}
\left[
\begin{array}{cc}
4 \\ 
3 \\  
\end{array} 
\right]
w\text{ = }
\left[
\begin{array}{cc}
1 \\ 
2 \\  
\end{array} 
\right]
$$

, find the unit vectors, and find the cosine of their angle $\theta$ .  Choose vectors a,b,c that make $0\textdegree{}$ , $90\textdegree{}$, and $180\textdegree{}$ angles with w.

### Solutions

*  For computing unit vector:
   * unit vector v = (4/5, 1/5)
   * unit vector w = $\left(\frac{1}{\sqrt{5}},\frac{4}{\sqrt{5}}
*  For finding the cosine:
   *  $\text{cos}\theta\text{ = }\frac{10}{5\sqrt{5}}\text{ = }\frac{2}{\sqrt{5}}$ .
*  For angle selection:
   *  0 degrees = 
   *  90 degrees = 0 dot product; a = (-2,1)

### Unit Vector Example 2

### Sources
* ITLA v6, sec 1.2: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

* "For any unit vectors v and w, find the dot products (actual numbers) of:
      * v and -v : (1*-1) + (0*0) = -1.
      * v + w and v - w : (v + w)(v - w) = $v\cdot{v} -v\cdot{w} + v\cdot{w} - w\cdot{w} = (1) - 0 - 1 = 0; implies 90 degree angle.
      * v - 2w and v + 2w : (v - 2w)(v + 2w) = 1 + v2w - v2w - 4(1) = -3 .

### Unit Vector Example 2

### Sources
* ITLA v6, sec 1.2: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text:
* "Find unit vectors u1 and u2 in the directions of v = (1,3) and w = (2,1,2) .
* Find unit vectors U1 and U2 that are perpendicula to u1 and u2.

### Solutions

* For the unit vectors:
   * v = (1,3): length = $\sqrt{\text{1 + 9}}$ = $sqrt{10}$ ; u1 = $\left(\frac{1}{\sqrt{10}\text{, }\frac{3}{\sqrt{10}\right)$
   * 2 = (2,1,2); lenght = $\sqrt{\text{4 + 1 + 4}}$ = $sqrt{9}\text = }3$ ; u2 = $\left(frac{2}{3}\text{, }frac{1}{3}\text{, }frac{2}{3}\right)$
* For the perpendicular vectors:
  * U1 = $\left(-\frac{3}{\sqrt{10}\text{, }\frac{1}{\sqrt{10}\right)$
  * U2 = $\left(-frac{2}{3}\text{, }0\text{, }frac{2}{3}\right)$

## Example 5: vectors from coordinates

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

## Example 6: describe space of vector system

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

## Example 7: draw vectors and their operations 

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

## Example 8: compute the results of vectors in cv + dw formula

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

## Example 9: vector linear combinations

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
  
## Example 10: mapping possible linear combinations

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

## Example 11: vector linear independence with symbols

### Premise
*  Given a set of numeric and symbolic vectors, decide if they are linearly independent.

### Problem Text
* "(Not easy) How could you decide if the vectors u = (1,1,0) and v = (0,1, 1) and  w = (a, b, c) are linearly independent or dependent ?"

### Solution of Solution Steps
*  This is sort of tough, but if you just write the 3 vectors out vertically, you'll see that "Certainly x1 has to be a. Certainly x2 has to be c. So the middle components give the requirement a + c = b."  So generally when you get a question that sounds like this, the approach is to write them out, and see if isolation makes any one variable easy to solve, so that you can solve the others apart via substitution.

## Example 12: find orthogonal dot product

### Premise
*  Given a vector of numbers, find another vector that is orthogonal to it.

### Problem Text
* "Given the vector (1,2,3), find a vector that is orthogonal to it."

### Solution of Solution Steps
* Remember that 2 vectors, which must be of equal length, are orthogonal if their dot product = 0.
* Consider that the first variable v is the given list of values, and the unknown vector w is equal to (x,y,z ...) etc.
* Combine the 2 vectors in the dot product formula = 0.  Set all variables except one as = 1:
   * 1(1) + 2(1) + 3z = 0 .
   * z = -1.
   * w = (1,1,-1)









