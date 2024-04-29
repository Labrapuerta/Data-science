Introduction to some special [[Matrix definitions| matrices]] that are used all the time in linear algebra

## Zero matrix: $m \times n$
Actually I don't understand it's importance or relevance, the example presented is to perform shape transformations or solve equations.
Can be any size, but all it's components should be zero
$$ 2 \times 2: 0 = 
\left(\begin{array}{cc} 
0 & 0\\
0 & 0
\end{array}
\right)
$$
$$Ax = 0$$
## Identity matrix :$n \times n$ 
On contrast to the zero matrix, the identity matrix plays the role of one. It's represented with the $I$ symbol, and has commute properties
 $$AI = A = IA$$
 Ex. $2 \times 2$ 
 $$I = \left(\begin{array}{cc} 
1 & 0\\
0 & 1
\end{array}
\right)$$
## Diagonal matrix 
Has only elements in the diagonal and zeros everywhere else.
 $$D = \left(\begin{array}{cc} 
d_1 & 0 & 0\\
0 & d_2 & 0\\
0 & 0 & d_3
\end{array}
\right)$$
## Banded matrix
Similar to the diagonal matrix but the elements above and below to the main diagonal are filled with values too but only in the slash type of format,  the rest of the elements are zeros
$$D = \left(\begin{array}{cc} 
d_1 & a_1 & 0\\
b_1 & d_2 & a_2\\
0 & b_2 & d_3
\end{array}
\right)$$
## Triangular matrices
It's called triangular because if you draw a perimeter line where the elements are, you're getting a triangle
### Upper triangular
$$U = \left(\begin{array}{cc} 
a & b & c\\
0 & d & e\\
0 & 0 & f
\end{array}
\right)$$
### Lower triangular
$$L = \left(\begin{array}{cc} 
a & 0 & 0\\
b & c & 0\\
d & e & f
\end{array}
\right)$$

## Orthogonal matrix

An orthogonal matrix need to fill the condition where the [[Transpose and inverses#Transpose|transpose ]]of the matrix is equal to the [[Transpose and inverses#Inverse matrix|inverse]] of the same matrix
$$A^T = A^{-1}$$
Meaning that $$AA^T = I = A^TA$$
It's like multiplying each row of $A$ by each column of $A$
_The columns and rows of an orthogonal matrix forms orthonormal vectors_

## Exercises
1. Let $A = \left(\begin{array}{cc} -1 & 2\\4 & -8\end{array}\right)$. Construct a $2 \times 2$ matrix $B$ such that $AB$ is the zero matrix.
$$AB = \left(\begin{array}{cc} 0 & 0\\0 & 0\end{array}\right)$$
$$\left(\begin{array}{cc} -1 & 2\\4 & -8\end{array}\right)\times 
\left(\begin{array}{cc} b_{11} & b_{12}\\b_{21} & b_{22}\end{array}\right)
= \left(\begin{array}{cc} 0 & 0\\0 & 0\end{array}\right)$$
_Getting the equations_

$1. -b_{11} + 2b_{21} = 0$
$2. -b_{12} + 2b_{22} = 0$
$3. \space 4b_{11} - 8b_{21} = 0$
$3. \space 4b_{12} - 8b_{22} = 0$

_Solving for equations with the same variables_

$1. -b_{11} + 2b_{21} =  \space 4b_{11} + 8b_{21}$
$2. -b_{12} + 2b_{22} = \space 4b_{12} + 8b_{22}$

$1.\space 6b_{21} =  \space -5b_{11}$

