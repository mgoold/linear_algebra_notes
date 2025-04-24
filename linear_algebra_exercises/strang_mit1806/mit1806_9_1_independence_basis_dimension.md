
# Exercises on Independence, Basis and Dimension

## Problem 9.1

Find the largest possible number of independent vectors among:

$$
v_1\text{ = }
\left[
  \begin{matrix}
  1 \\
  -1 \\
  0 \\
  0 \\
  \end{matrix}
\right]
\text{, }v_2\text{ = }
\left[
  \begin{matrix}
  1 \\
  0 \\
  -1 \\
  0 \\
  \end{matrix}
\right]
\text{, }v_3\text{ = }
\left[
  \begin{matrix}
  1 \\
  0 \\
  0 \\
  -1 \\
  \end{matrix}
\right]
\text{, }v_4\text{ = }
\left[
  \begin{matrix}
  0 \\
  1 \\
  -1 \\
  0 \\
  \end{matrix}
\right]
\text{, }v_5\text{ = }
\left[
  \begin{matrix}
  0 \\
  1 \\
  0 \\
  -1 \\
  \end{matrix}
\right]
\text{, }v_6\text{ = }
\left[
  \begin{matrix}
  0 \\
  0 \\
  1 \\
  -1 \\
  \end{matrix}
\right]
$$

I did 


$$
A\text{ = }
\left[
  \begin{matrix}
  1 & 1 & 1 & 0 & 0 & 0\\
  -1 & 0 & 0 & 1 & 1 & 0\\
  0 & -1 & 0 & -1 & 0 & 1\\
  0 & 0 & -1 & 0 & -1 & -1\\
  \end{matrix}
\right]
$$

Answer:

I did this entirely wrongly the first time: I did row reduction on the matrix and then looked at dependence between columns.  The correct process is the exact reverse: first eliminate any columns based on dependence, then do row reduction on the remaining matrix.  When you do so, you must keep track of the original number of the columns you kept (v1, v2, etc).
The reason for this order is that row reduction may disguise the original dependency relations between columns.

With this in mind, we note that:
"Since v4 = v2 − v1, v5 = v3 − v1, and v6 = v3 − v2, the vectors v4, v5, and v6 are dependent on the vectors v1, v2 and v3. To determine the
relationship between the vectors v1, v2 and v3 we apply row reduction tothe matrix [v1 v2 v3]:"

$$
A\text{ = }
\left[
  \begin{matrix}
  1 & 1 & 1 \\
  -1 & 0 & 0 \\
  0 & -1 & 0 \\
  0 &  0 & -1 \\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 1 & 1 \\
  0 & 1 & 1 \\
  0 & -1 & 0 \\
  0 &  0 & -1 \\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 1 & 1 \\
  0 & 1 & 1 \\
  0 & 0 & 1 \\
  0 &  0 & -1 \\
  \end{matrix}
\right]
\rightarrow
\left[
  \begin{matrix}
  1 & 1 & 1 \\
  0 & 1 & 1 \\
  0 & 0 & 1 \\
  0 & 0 & 0 \\
  \end{matrix}
\right]
$$

These 3 pivot columns, corresponding to original vectors 1,2 & 3, are independent, and are the largest number.  The rank of the original matrix is thus 3.

## Problem 9.2

* Find a basis for the plane x − 2y + 3z = 0 in R3.

Answer:
I got the answer to this, but I thought of it in terms of 

$$
\left[
  \begin{matrix}
  0 \\
  0 \\
  0 \\
  \end{matrix}
\right]
\text{ = }y
\left[
  \begin{matrix}
  2 \\
  1 \\
  0 \\
  \end{matrix}
\right]
\text{ + }z
\left[
  \begin{matrix}
  -3 \\
  0 \\
  1 \\
  \end{matrix}
\right]
$$

... in other words, two vectors extending from the 0 vector.  Which I think is not mathematically wrong, but trivial.  
Remember that asserting an equation in a defined space will lose you one degree of freedom: to use a 3 variable equation in R3 means that you can at most move on a plane before the last variable is defined in terms of the other two and the constant.
Thus, knowing that the equation is set = 0, it is sufficient to definte the plane in terms of y and z.

I get that the plane is by definition the nullspace of [1 -2 3].  You can also get that it's the nullspace of the matrix 

$$
A\text{ = }
\left[
  \begin{matrix}
  1 & -2 & 3 \\
  0 & 0 & 0\\
  1 & 0 & 0\\
  \end{matrix}
$$

... when you consider that when it acts on (x y z) it will just give you whatever x y z is + additional 0s.  An obvious choice for x,y,z then is the 0 vector.  I thought that (-1,1,1) would also 
as a fixed point, but it's just a linear combo of the special solutions.  So you can see that just the special solutions alone are sufficient to define the plane when the equation is set to 0.

* Then find a basis for the intersection of that plane with the xy plane.

Answer: 

"The intersection of this plane with the xy plane contains v1 and does not contain v2; the intersection must be a line. Since v1 lies on this line it also provides a basis for it."

In other words, since the plane defined by the special solutions is in x,y and z space, and since it is an xy plane that intersects it, only the special solution vector that has 0 for z values can be used.  
Further, since by definition v1 is on the xy plan and is a line, it can serve as a basis for the intersection with the xy plane.  Remember that we're seekng a basis the intersection of our plane above, not of the whole xy plane.

* Then find a basis for all vectors perpendicular to the plane.

OK, so you know intuitively that any vector serving as a basis to that plane is going to have to be at right angles to them somehow, by definition.  But I don't think up to this point we've been introduced to the "cross product", which is exactly that.
Calculating a cross product gives you a vector that is perpendicular to other specified vectors.  More on this later.



