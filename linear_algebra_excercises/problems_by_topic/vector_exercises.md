
# Vector Related Exercises

## Sources:
* USF: https://usfca.instructure.com/courses/1627052/quizzes/2457172/take
* Strang, ITLA 6th Edition PS 1.1, p6.
* MIT 18.06: https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/resources/mit18_06scf11_ses1-1prob/


## Problems

### USF

1. Though we can think of both as an N-tuple of real values (in other words an ordered list of N-many continuous real numbers), what is the fundamental difference between a point and a vector? 

2. The __________is a special vector. It stays the same vector no matter what we scale it by. If we add or subtract to another vector $\overrightarrow{v}$ , the resulting vector is $\overrightarrow{v}$. 

3. True or False: If one scales a vector by a non-zero value, the resulting vector will lie along the same line. 

### Strang

Under what conditions on a, b, c, d is 

$$
\left[
\begin{array}{cc}
c \\ 
d \\  
\end{array} 
\right]
$$

a multiple m of

$$
\left[
\begin{array}{cc}
a \\ 
b \\  
\end{array} 
\right]
$$

?   Start with the two equations c = ma and d = mb. By eliminating m, find one equation connecting a,b,c,d. You can assume no zeros in these numbers.

2.  Going around a triangle from (0, 0) to (5.0) to (0, 12) to (0, 0), what are those three vectors u, v, w? What is u + v + w? What are their lengths ||u|| and ||v|| and ||w||?
    The length squared of a vector $\large{u\text{ = }\left(u_1,u_2\right)\text{ is }{\|\|u\|\|}^2\text{ = }u_1^2 + u_2^2}$ .

3.  Descnbe geometrically (line, plane, or all of R3) all linear combinations of

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

4.  Draw

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

and v+w and v-w in a single plane.

5.  If

$$
\text{v + w = }
\left[
\begin{array}{cc}
5 \\ 
1 \\  
\end{array} 
\right]
\text{ and v - w = }
\left[
\begin{array}{cc}
1 \\ 
5 \\  
\end{array} 
\right]
$$

, commpute and draw the vectors v and w.

6.  From

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

, find the components of 3v + w and cv + dw .

7.  Compute u + v + w and 2u + 2v + w. How do you know u, v, w lie in a plane?

Follow-up:  These lie in a plance because w = cu + dv.  Find c and d:

$$
\text{u = }
\left[
\begin{array}{cc}
1 \\
2 \\
3 \\
\end{array} 
\right]
\text{ v = }
\left[
\begin{array}{cc}
-3 \\
1 \\
-2 \\
\end{array} 
\right]
\text{ w = }
\left[
\begin{array}{cc}
2 \\
-3 \\
-1 \\
\end{array} 
\right]
$$

.

8.  Every combination of v = (1,-2,1) and w = (0, 1, —1) has components that add to ____________. Find c and d so that cv + dw = (3,3, —6). Why is (3, 3, 6) impossible?

9.  In the xy plane mark all nine of these linear combinations:

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

... with c = 0,1,2 and d = 0,1,2 .

10.  (Not easy) How could you decide if the vectors u = (1,1,0) and v = (0,1, 1) and  w = (a, b, c) are linearly independent or dependent ?

## Solutions

### USF

1.  All of the above.
2.  Zero (vector)
3.  True

### Strang

1.  c = ma and d = mb lead to ad = amb = bc. With no zeros, ad = bc is the equation for a 2 ×2 matrix to have rank 1.
    Notes:
    * with the double equality ad = amb = bc I am not used to modifying 2 items simultaneously, but apparently you can.  Implicitly, what they've done is to first say that c/a = m = d/b.  Then the outer terms on either side multiply the other two terms by a and b, respectively.  That's why you get "amb" as the middle term.
    * I couldn't prove that "the equation for a 2 ×2 matrix to have rank 1" by row elimination.  But you can prove it algebraically at least:
        * If the rank is 1, the second row must be a scalar multiple of the first row. This means there exists a scalar k such that: (c, d) = k(a, b).
            * This translates to the equations:
                * c = ka
                * d = kb
        * Then: ad - bc = a(kb) - b(ka) = kab - kab = 0 .

2.  The three edges going around the triangle are u = (5, 0), v = (−5, 12), w = (0,−12).   Their sum is u + v + w = (0, 0). Their lengths are ||u||= 5, ||v||= 13, ||w||= 12.
    Notes:
    * When you're doing this "walk around the straight edges of a triangle or parallelogram" thing, always remember to check that your result vectors sum to 0.
3.  The combinations give (a) a line in R3 (b) a plane in R3 (c) all of R3.
    * Basically, you're trying to make vector a product of every other vector.
    * Always remember to try and make them sum to zero without multipliers, just to see if its true.
5.  v = (3,3); w = (2,-2)
    Notes:
    * The key here is to note that each component v1, v2 and w1, w2 is being used in 2 different equations.  So what you do is take the vectors apart and then reorganize them so that the pair of equations with v1, w1 can be solved simultaneously using substitution.  From there, you continue substitution to solve the rest.

6.  3v + w = (7, 5) and cv + dw = (2c + d, c + 2d).  This is just scalars multiplying vectors.
7.  Answer: "u+v = (−2, 3, 1) and u+v +w = (0, 0, 0) and 2u+2v+w = ( add first answers) = (−2, 3, 1). The vectors u, v, w are in the same plane because a combination u + v + w gives (0, 0, 0). Stated another way : u=−v−w is in the plane of v and w."
    Notes:
    * again, your just trying to make every vector = the result of multiplying that vector by a scalar.  The good algorithm for this "show that they're in such and such a dimension space" is:
      * see if they easily add to zero
      * failing that, see if any vector is just another vector multiplied by a scalar
      * failing that, see if you can get any one vector to be the sum of two other vectors multiplied by scalars

8.  The components of every cv + dw add to zero because the components of v = (1,−2, 1) and of w = (0, 1,−1) add to zero. c = 3 and d = 9 give 3v + 9w = (3, 3,−6). There is no solution to cv + dw = (3, 3, 6) because 3 + 3 + 6 is not zero.
    Notes:
    * "The components of every cv + dw add to zero because the components of v = (1,−2, 1) and of w = (0, 1,−1) add to zero."  --Don't make the mistake of thinking their saying "the result of cv + dw will always be the zero vector." They just mean that the components of the result vector from cv + dw will always sum to zero if you add them together.
    * If you try to solve the "Why is (3, 3, 6) impossible?" part algebraically, you'll show that either c or d has to have negative and positive values simultaneously, which is impossible.  When Strang says "because it doesn't sum to zero", that's a linear algebra way of talking.  It begins to touch on the idea that (3,3,6) is not in the column space of A(v,w).  

9.  There's nothing to do here but mark out the points.  If you do, you'll see that you could draw a lattice by connecting them.  The solution uses language like "lie on a lattice", which I thought was some special linear algebra term, but they just mean it in the ordinary sense.

10.  This is sort of tough, but if you just write the 3 vectors out vertically, you'll see that "Certainly x1 has to be a. Certainly x2 has to be c. So the middle components give the requirement a + c = b."  So generally when you get a question that sounds like this, the approach is to write them out, and see if isolation makes any one variable easy to solve, so that you can sole the others apart via substitution.

## Facts

1. Vectors have a relationship to an origin point, without which they don't have meaning.  This origin point need not be the 0 origin.
2. Vectors have an inherent direction
3. Vectors can be added and subtracted.  Points cannot.

