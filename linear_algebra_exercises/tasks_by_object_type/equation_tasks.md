
# Equation Spaces

## Example 1,2: 2x2 Equation Spaces 1,2

### Sources
* ITLA, p18: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "What multiple $l_{21}$ of equation 1 should be subtracted from equation 2 ?

$$2x\text{ + }3y\text{ = }1$$
$$10x\text{ + }9y\text{ = }11$$

* After elimination, write down the upper triangular system and circle the two pivots.
* Use back substitution to find x and y and check.
* If equation 1 is added to equation 2, which things are changed:
    * the lines in the row picture
    * the vectors in the column picture
    * the coefficient matrix
    * the solution?
      
### Solutions
* One way is to multiply line 1 by 5 and subtract.
* Solution is x = 2, y = -1.
* Checks out.
* The solution given in the book is that the row and column picture and coefficient matrix change.  The question wasn't clear to me, but they did mean to add both equations into a single equation, reducing the system to a 1x2 matrix.

## Example 3: 2x2 Equation Spaces 3

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the equations:

$$3x\text{ + }3y\text{ = }1$$
$$10x\text{ + }9y\text{ = }11$$

, complete answers for the right side so that the system will have:
* no solution
* infinite solutions."

### Solutions
* no solution: (10,10); 2 different equations with the same variables cannot resolve to the same non-zero value.
* infinite solutions: (10,20) -- this reduces the two equations to just one equation, where any multiple of x=10, y=-2x will yield a result of 10.

## Example 4: 2x2 Equation Spaces 4

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the equations:

$$2x\text{ + }by\text{ = }16$$
$$4x\text{ + }8y\text{ = }g$$

...choose coefficient b that makes the system:
* singular: b =4
* choose coefficient g that makes system solvable: g = 32
* find 2 solutions for the singular-but-solvable case. (4,2) (2,3)

## Example 5: 2x2 Equation Spaces 5

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the equations:

$$3x\text{ - }2y\text{ = }b_1$$
$$6x\text{ - }4y\text{ = }b_2$$

* what test on $b_1$, $b_2$ decides whether this system has a solution?
* how many solutions the system will have?

### Solutions
* what test on $b_1$, $b_2$ decides whether this system has a solution? If $b_1$ and $b_2$ have the same proportions that the left side equation coefficients have.  This includes the 0 vector.
* how many solutions the system will have? If the right side proportions match the left side proportions, the system will reduce to a 1x2 matrix and have infinite solutions.  If the proportions are not kept, it will have no solutions.

## Example 6: 2x2 Equation Spaces 6

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the equations:

$$3x\text{ + }2y\text{ = }10$$
$$6x\text{ 4 }4y\text{ = __}$$

... choose a right side that gives
* no solution
* infinitely many solutions
* list 2 such solutions."

### Solutions
* no solution: (10,0)
* infinitely many solutions: (10,20)
* list 2 such solutions. (10,-10), (20,-25)

## Example 7: Equation Spaces 7

### Sources
* ITLA, 5th Ed, p131.
  
### Problem Text
* "The functions f(x) = $x^2$ and g(x) = 5x are "vectors" in F, the vector space of all real functions.  The functions are defined for x between positive and negative infinity.  The combination of 3f(x) - 4g(x) = h(x) = ___________.

### Solution
* h(x) = $3x^2\text{ - }20x$ .


# Equation Row Exchanges

## Example 1: Row Exchange 1

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given equations:

$$ax\text{ + }3y\text{ = }-3$$
$$4x\text{ + }6y\text{ = }6$$

... select the values for a under which elimination breaks down:
* permanently: a = 2 
* temporarily: a = 0
* Solve for x and y after firxing the temporary breakdown using a row exchange." x = 3, y = -1

# Equation Row Reduction

## Example 1: Row Reduction 1

### Sources
* ITLA, p18: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "What multiple of equation 1 should be subtracted from equation 2 ?

$$2x\text{ - }4y\text{ = }6$$
$$-x\text{ + }5y\text{ = }0$$

* After elimination, write down the upper triangular system and circle the two pivots.  Use back substitution to find x and y."

### Solutions
* Divide equation 1 by 1/2 and subtract from equation 2
* x = 4, y = 1 .
* If the right changes sign, then the solution must change sign to (-5,-1) .
  
## Example 2: Row Reduction 2

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "What multiple of l of equation 1 should be subtracted from equation 2 to remove c?

$$ax\text{ + }by\text{ = }f$$
$$cx\text{ + }dy\text{ = }g$$

* What formula for the second pivot does elimination provide?
* What is y?
* Note: the second pivot is missing when ad = bc, so that the matrix is singular [and btw will have no determinant.]

### Solutions
* $\frac{a}{c}$
* second pivot: $d\text{ - }\left(\frac{cb}{a}\right)$
* After elimination, $y\text{ = }\frac{\left(ag\text{ - }cf\right)}{\left(ad\text{ - }bc\right)}$

## Example 3: Row Reduction 3

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the following 2 equations:

$$kx\text{ + }3y\text{ = }6$$
$$3x\text{ + }ky\text{ = }6$$

* For which 3 values of k does elimination break down?
* Which is fixed by a row exchange?
* Is the number of solutions 0, 1, or infinity?
  
### Solutions
* For which 3 values of k does elimination break down? 0, 3, -3
* Which is fixed by a row exchange? 0
* Is the number of solutions 0, 1, or infinity? If k = 0, then there is 1 solution.  If k is 3 then the system becomes unsolveable.  If k = -3, then there are infinitely many solutions.
  
## Example 4: Row Reduction 4

### Sources
* ITLA, p46: https://github.com/mgoold/linear_algebra_notes/blob/main/linear_algebra_exercises/strang_mit1806/ila6sols.pdf

### Problem Text
* "Given the equations:

$$x\text{ + }y\text{ = }5$$
$$x\text{ + }2y\text{ = }6$$

* draw the lines for these equations, and the line for y that results from elimination on their matrix.
* Which line $5x\text{ - }4y\text{ = }c$ goes through the solution of these equations?

### Solutions
* draw the lines for these equations, and the line for y that results from elimination on their matrix. The line y = 1 results from elimination.  The solution is (4,1).
* Which line $5x\text{ - }4y\text{ = }c$ goes through the solution of these equations? 5(4) - 4(1) = 16 = c goes through the solution of these equation.


