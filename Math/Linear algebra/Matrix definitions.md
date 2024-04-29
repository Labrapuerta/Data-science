## Definition of a matrix
A matrix is a rectangular array of numbers, numbers can be symbols. We use capital letter to denote matrices $A, B$ 

### $m * n$ matrix
Where $m$ stands for the number of rows and $n$ stands for columns

#### Different examples of matrices

- Square matrix: Where $m = n$ 
$$ 2 \times 2: A = 
\left(\begin{array}{cc} 
a & b\\
c & d
\end{array}
\right)
$$
- Rectangular matrix: Where $m \neq n$ 
$$ 3 \times 2: B = 
\left(\begin{array}{cc} 
a & b\\
c & d \\
e & f
\end{array}\right)$$
$$ 2 \times 3: C = 
\left(\begin{array}{cc} 
a & b & c\\
d & e & f
\end{array}\right)$$

	- If any of the dimentions = 1; it's called a vector
- Column vectors typically denoted as $x$: Where $n = 1$ 
$$ 3 \times 1: x = 
\left(\begin{array}{cc} 
a \\
b \\
c
\end{array}\right) 
$$
- Row vectors typically denoted as $y$: Where m = 1
$$ 1 \times 3: y = 
\left(\begin{array}{cc} 
a & b & c \end{array}\right) 
$$

### General notation
The general notation for a $m \times n$ matrix is the following
 $$ A = 
\left(\begin{array}{cc} 
a_{11} & a_{12} & a_{1n}\\
a_{21} & a_{22} & a_{2n}\\
. & . & . \\
a_{m1} & a_{m2} & a_{mn}
\end{array}\right) 
$$
```python
import numpy as np
# Defining a matrix in python
matrix = np.array([[1,0,0],[0,1,0],[0,0,1]]) #Identity matrix (3x3)
```
## Building some matrices
### 1. Write a $3 \times 3$ matrix with 1's in the diagonal and 0's in the rest
 $$ A = 
\left(\begin{array}{cc} 
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1 \\
\end{array}\right) 
$$
### 2. Write a $4 \times 3$ matrix with 1's in the diagonal and 0's in the rest

 $$ A = 
\left(\begin{array}{cc} 
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1 \\
0 & 0 & 0 \\
\end{array}\right) 
$$
