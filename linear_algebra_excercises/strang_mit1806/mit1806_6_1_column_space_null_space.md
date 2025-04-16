
# Exercises on Column Spaces and Null Spaces

## Problem 6.1

Suppose S and T are two subspaces of a vector space V.

Definition: The sum S + T contains all sums s + t of a vector s in S and a vector t in T. 

### Problem 6.1.1

Show that S + T satisfies the requirements (addition and scalar multiplication) for a vector space.

Book answer:

(s + t) + (s' + t') = (s + s') + (t + 't) and c(s + t) = cs + ct.

Because S and T are both valid subspaces, it follows that any two draws s and s' and t and t' could be added together.  To the extent that vectors s and t can be added together, it follows that these two draws can be rearranged as (s + t) + (s' + t').  Per the distributive property, to the extent that s + t can be added together, cs and ct must also be valid.
However, the above proof that S + T satisfies subspace requirements is not clear to me yet.  I don't see why it's valid that because s + s' is valid, s and t can be added together.  I guess the definition is stipulating that there is a valid subspace s + t.

### Problem 6.1.2

Question: If S and T are lines in Rm, what is the difference between S + T and S ∪ T?  That union contains all vectors from S and T or both. 
Answer: 
S and T are said to be subspaces, which means they must go through the origin if they are lines, and must therefore intersect there.  Then S + T becomes all the linear combinations of the vectors in these lines, which would be a plane.  S ∪ T would just be the vectors in either line, which would just be the line.

### Problem 6.1.3
Explain this statement: The span of S ∪ T is S + T.  

This lame idiom is a way of saying that all the linear combinations you can do with the vectors in S and T are what comprise S + T, since S + T is all the valid combinations s + t.

## Problem 6.2

The plane x − 3y − z = 12 is parallel to the plane x − 3y − x = 0.  One particular point on this plane is (12, 0, 0). All points
on the plane have the form (fill in the first components):

$$
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}
\text{ = }
\begin{bmatrix}
{ }  \\
0 \\
0 \\
\end{bmatrix}=
\text{ + y}
\begin{bmatrix}
{ } \\
1 \\
0 \\
\end{bmatrix}
\text{ + z}
\begin{bmatrix}
{ } \\
0 \\
1 \\
\end{bmatrix}
$$

Answer:

The equation x − 3y − z = 12 can be set to solve for x as x = 12 + 3y + z.  Then the missing elements can be solved in terms of this:

$$
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}
\text{ = }
\begin{bmatrix}
\text{12 + 3y + z} \\
y \\
z \\
\end{bmatrix}
\text{ = }
\begin{bmatrix}
12  \\
0 \\
0 \\
\end{bmatrix}=
\text{ + y}
\begin{bmatrix}
3 \\
1 \\
0 \\
\end{bmatrix}
\text{ + z}
\begin{bmatrix}
1 \\
0 \\
1 \\
\end{bmatrix}
$$

You can see how multiplying the scalars times their respective vectors would give you the vector of formulas $\begin{bmatrix}
\text{12 + 3y + z} \\
y \\
z \\
\end{bmatrix}$ .  However, I don't understand how you get back to x .... maybe x is shown here to be dependent on/derivative of the other variables?  Anyway, I definitely need more context to fully understand this one.

## Problem 6.3

How is the nullspace N(C) related to the spaces N(A) and N(B) if 

$$
C\text{ = }\begin{bmatrix}
A \\
B \\
\end{bmatrix}
$$

?

Note:
Remember that in the formula Ax=b, the nullspace is the set of values for x that yield the 0 vector for b.

Answer:
$N\left(C\right)\text{ = }N\left(A\right)\cap{N\left(B\right)}$ contains all vectors that are in both nullspaces.

Notes:
First, we're assured that C consists solely of values in A and B.  And if N(C) is the nullspace for C, and C = a matrix of whatever values are in A and B, then it follows that the nullspace for C  can only be the values of A and B that yield that same nullspace.  Moreover it must be the intersection of N(A) and N(B), since there would be no reason to have redundant values.

$$
Cx\text{ = }\begin{bmatrix}
Ax \\
Bx \\
\end{bmatrix}
\text{ = }0
$$

if and only if Ax = 0 and Bx = 0.

Notes: this is just a way of saying that if anything in the set of values for A and B matrixes time x does NOT equal 0, then Cx cannot = 0 either.



