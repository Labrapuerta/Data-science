### Addition
In the addition of [[Matrix definitions|matrices]] with the same shape ([[Matrix definitions#Different examples of matrices|square matrix]]), each element will be added to it's corresponding element of the other matrix.
Ex. matrices with form $2 \times 2$ 


$$
\left(\begin{array}{cc} 
a & b\\
c & d
\end{array}\right)
+
\left(\begin{array}{cc} 
e & f\\ 
g & h
\end{array}\right) = 
\left(\begin{array}{cc} 
a+e & b+f\\ 
c+g & d+h
\end{array}\right)
$$ ```
```python
x = np.array([[0,0,0],[1,3,5], [2,4,6]]) #Define the matrix
y = np.array([[3,0,0],[0,4,7], [8,9,0]])
#### To perform addition we can use in built functions or np.add
x + y 
np.add(x,y)
#Both methods will give the exact same value
```
### Scalar multiplication
Each element of the matrix will be multiplied by the scalar
$$
\left(\begin{array}{cc} 
a & b\\
c & d
\end{array}\right)
\times
K = 
\left(\begin{array}{cc} 
ak & bk\\ 
ck & dk
\end{array}\right)
$$
```python
x = np.array([[0,0,0],[1,3,5], [2,4,6]]) #Define the matrix
y = 3 #Scalar
#### To perform addition we can use in built functions or np.multiply
x*y
np.multiply(x,y)
#Both methods will give the exact same value
```
### Multiplication
Ex. Matrices with form $2 \times 2$ 
$$\left(\begin{array}{cc} 
a & b\\
c & d
\end{array}\right)
\times
\left(\begin{array}{cc} 
e & f\\ 
g & h
\end{array}\right) = 
\left(\begin{array}{cc} 
ae+ bg & af+bh\\ 
ce+dg & cf+dh
\end{array}\right)$$
_Matrices do not commute under multiplication_
If we change the order of the multiplication, the result will be different.

$$
\left(\begin{array}{cc} 
e & f\\ 
g & h\end{array}\right)
\times
\left(\begin{array}{cc} 
a & b\\
c & d
\end{array}\right)
= 
\left(\begin{array}{cc} 
ea+ fc & eb+fd\\ 
ga+hc & gb+hd
\end{array}\right)$$

### Multiplication rule
When performing multiplication we're going across the columns $n$ of the first matrix along the rows of the second one. In order to be able to do the operation, the columns $n$ of the first matrix and the rows $m$ of the second matrix should be the same size 
$$(m \times n) \times (n \times p) = (m \times p); \text{ with p being any dimension}$$


```python
x = np.array([[0,0,0],[1,3,5], [2,4,6]]) #Define the matrix
y = np.array([[3,0,0],[0,4,7], [8,9,0]])
### For matrix multiplication use np.matmul
np.matmul(x,y)
### Do not use x * y or np.mul, this will treat the matrices as scalars
```

## Formula for matrix multiplication
Let´s start with the multiplication of two matrices with unknown shape $$C = A \times B$$
To perform the multiplication we need to go across every column of $A$ and multiply it by every row of $B$ to get each value of $C$; So to obtain values of $C$ we can use this formula
$$c_{ij} = \sum_{k = 1}^n a_{ik}b_{kj}$$
Where $i$ indicates the row and $j$ the column. $k$ is the current index and $n$ is the number of columns of the first matrix or the number of rows of the second matrix.

```python
x = np.array([[0,0,0],[1,3,5], [2,4,6]]) #Define the matrix
y = np.array([[3,0,0],[0,4,7], [8,9,0]])
A = np.zeros((3,3))
for i in range(x.shape[0]):
	for j in range(y.shape[1]):
		for k in range(x.shape[0]):
			A[i,j] += x[i,k] * y[k,j]
# Iterate trough rows, columns and k to perform the summatory
```
## Exercises  

1.  Let $A = \left(\begin{array}{cc} 1 & 2 \\ 2 & 4\end{array}\right)$, $B = \left(\begin{array}{cc} 2 & 1 \\ 1 & 3\end{array}\right)$ and $C = \left(\begin{array}{cc} 4 & 3 \\ 0 & 2\end{array}\right)$. Verify that $AB = AC$ and yet $B \neq C$  
For:
$$AB = \left(\begin{array}{cc} 2+2 & 1+6 \\ 4+4 & 2+12\end{array}\right) = \left(\begin{array}{cc} 4 & 7 \\ 8 & 14\end{array}\right) $$
$$AC = \left(\begin{array}{cc} 4+0 & 3+4 \\ 8+0 & 6+8\end{array}\right) = \left(\begin{array}{cc} 4 & 7 \\ 8 & 14\end{array}\right) $$
This means
$$AB = AC \text{ and }B \neq C$$
2. Let $A$ be an $m\times n$ matrix, $B$ an $n\times p$ matrix, and C a $p\times q$ matrix. Then prove that $A(BC)=(AB)C$ 
Shape operations to determine the shape result and compare the dimensions.

Solving for $A(BC)$
$$A(BC) = A((n\times p)(p \times q))$$
$$A(BC) = A(n\times q)$$
$$A(BC) = (m \times n)(n\times q)$$
$$A(BC) = (m \times q)$$
Solving for $(AB)C$
$$(AB)C = ((m\times n)(n \times p))C$$
$$(AB)C = (m\times p)C$$
$$(AB)C = (m\times p)(p \times q)$$
$$(AB)C = (m\times q)$$

Where both $A(BC) \text{ and }(AB)C$ are the same shape
