## Transpose 
The transpose of a [[Matrix definitions|matrix]] usually represented with the $T$ symbol in the matrix $A^T$. It's an operation where the rows of the matrix becomes the columns and the columns the rows.
$$3 \times 4:A = \left(\begin{array}{cc} 
a_{11} & a_{12} & a_{13} & a_{14}\\
a_{21} & a_{22} & a_{23} & a_{24}\\
a_{31} & a_{32} & a_{33} & a_{34}
\end{array}
\right)$$

So the transpose of A...
$$4 \times 3 :A^T = \left(\begin{array}{cc} 
a_{11} & a_{21} & a_{31}\\
a_{12} & a_{22} & a_{32}\\
a_{13} & a_{23} & a_{33}\\
a_{14} & a_{24} & a_{34}\\
\end{array}
\right)$$
Each element in the transpose can be obtained by flipping the $ij$ indexes of the elements

$$a_{ij}^T = a_{ji}$$
### Algebra for transposed matrices

- The transpose of a transposed matrix is the original matrix.
$$(A^T)^T = A$$
- The transpose of the addition of two matrices is equal to the sum of the transposes of the matrices
$$(A + B)^T = A^T + B^T$$
- The transpose of the product of two matrices is equal to the reverse product of the transposes of the matrices
$$(A \times B)^T = B^T \times A^T$$
### Special transposed matrices

#### Symmetric matrix
The transpose of this matrix is equal to the matrix, the matrix shape should be $m = n$
$$A^T = A$$
Ex. $$ A = 
\left(\begin{array}{cc} 
a & b & c\\
b & d & e\\
c & e & f \\
\end{array}\right)\longrightarrow
A^T = \left(\begin{array}{cc} 
a & b & c\\
b & d & e\\
c & e & f \\
\end{array}\right)
$$
#### Skew symmetric matrix
The transpose is equal to the negative of the original matrix, the matrix shape should be $m = n$.
$$A^T = -A$$
Ex.$$ A = 
\left(\begin{array}{cc} 
0 & b & c\\
-b & 0 & e\\
-c & -e & 0 \\
\end{array}\right)\longrightarrow
A^T = \left(\begin{array}{cc} 
0 & -b & -c\\
b & 0 & -e\\
c & e & 0 \\
\end{array}\right)$$
```python
import numpy as np
x = np.array([[0,0,0],[1,3,5], [2,4,6]]) #Define the matrix
x.transpose()
```
## Inner and outer products

### Inner product
Were using column vectors $1 \times 3$ 
$$U = 
\left(\begin{array}{cc} 
u_1 \\
u_2\\
u_3 \\
\end{array}\right) \text{, } V = 
\left(\begin{array}{cc} 
v_1 \\
v_2\\
v_3 \\
\end{array}\right)$$
The inner product is the same as the dot product but using the transpose of the first vector, this will have as a result a scalar
$$
U^T V= 
\left(\begin{array}{cc} 
u_1 & u_2 & u_3
\end{array}\right)
\left(\begin{array}{cc} 
v_1 \\
v_2\\
v_3 \\
\end{array}\right) = u_1v_1 + u_2v_2 + u_3v_3$$
```python
a = np.array([1,2,3])
b = np.array([0,1,0])
np.inner(a, b)
```
#### Definitions
In case the product equals 0, we say that the vectors are orthogonal
$$U^TV = 0 \rightarrow U,V\text{ Orthogonal}$$
##### Norm of a vector
Is equivalent to the length of the vector
$$\text{norm} = ||U|| = (U^TU)^{1/2} = \sqrt{u_1^2 + u_2^2 + u_3^2}$$
```python
import numpy as np
x = np.array([[0,0,0],[1,3,5], [2,4,6]])
np.linalg.norm(x)
```
We can say that $U$ is normalized if $||U|| = 1$
If the vectors are orthogonal and normalized, we say they're _orthonormal_
### Outer product
The multiplication between the first vector and the transpose of the second one, unlike the inner product, this will have as result a $n \times n$ matrix

$$
UV^T= 
\left(\begin{array}{cc} 
u_1 \\
u_2\\
u_3 \\
\end{array}\right)
\left(\begin{array}{cc} 
v_1 & v_2 & v_3
\end{array}\right)
 = \left(\begin{array}{cc} 
u_1v_1 & u_1v_2 & u_1v_3\\
u_2v_1 & u_2v_2 & u_2v_3\\
u_3v_1 & u_3v_2 & u_3v_3 \\
\end{array}\right)$$
```python
a = np.array([1,2,3])
b = np.array([0,1,0])
np.outer(a, b)
```
## Inverse matrix
Not all matrices are invertible, if a matrix is invertible we can write
$$A A^{-1} = I = A^{-1}A$$
Where $I$ stands for the [[Special matrices#Identity matrix $n times n$|identity matrix]] and $A$ has to be a [[Matrix definitions#Different examples of matrices |square matrix]]

### Definitions
- The inverse of two invertible square matrices is similar to how the transpose works
$$(AB)^{-1} = A^{-1}B^{-1}$$
- Inverse of a transpose matrix
$$(A^T)^{-1} = (A^{-1})^{T}$$


Let $A A^{-1} = I$ where $A$ is a $2 \times 2$ matrix
$$\left(\begin{array}{cc} 
a & b \\
c & d\\
\end{array}\right)
\left(\begin{array}{cc} 
x_1 & x_2 \\
y_1 & y_2\\
\end{array}\right) = 
\left(\begin{array}{cc} 
1 & 0 \\
0 & 1\\
\end{array}\right)$$

Where $A = \left(\begin{array}{cc} a & b \\c & d\\\end{array}\right) \text{, } A^{T} = \left(\begin{array}{cc} x_1 & x_2 \\y_1 & y_2\\\end{array}\right) \text{ and } I = \left(\begin{array}{cc} 1 & 0 \\0 & 1\\\end{array}\right)$

In order to obtain the values of $A^{-1}$ we need to obtain the equations that satisfies the conditions

- $1.\text{ } ax_1 + by_1 = 1$
- $2.\text{ } cx_1 + dy_1 = 0$
- $3.\text{ } ax_2 + by_2 = 0$
- $4.\text{ } cx_2 + dy_2 = 1$

Solving for the homogeneous equations ($eq = 0$)

$$x_1 = -\frac{d}{c}y_1$$
$$x_2 = -\frac{b}{a}y_2$$
Replacing on the other equations

$$a(-\frac{d}{c}y_1) + by_1 = 1$$
$$c(-\frac{b}{a}y_2) + dy_2 = 1$$

Solving for the equations
$$-\frac{ad}{c}y_1 + \frac{bc}{c}y_1 = 1$$
$$-\frac{cb}{a}y_2 + \frac{da}{a}y_2 = 1$$
...
$$y_1(\frac{-ad+bc}{c}) = 1$$
$$y_2(\frac{-cb+da}{a}) = 1$$
$y_1$ in terms of $A$
$$y_1 = \frac{c}{-ad+bc}$$
$y_2$ in terms of $A$
$$y_2 = \frac{-a}{-ad+bc}$$
Replacing $y_1 \& y_2$ to obtain $x_1\&x_2$
$$x_1 = -\frac{d}{c}\frac{c}{-ad+bc} = \frac{-d}{-ad+bc}$$
$$x_2 = -\frac{b}{a}\frac{-a}{-ad+bc} = \frac{b}{-ad+bc}$$

Since all the variables have the same basis we can conclude
$$A^{-1} =\frac{1}{bc-ad}\left(\begin{array}{cc} -d & b \\c & -a\\\end{array}\right)$$
Where $bc-ad$ is the determinant of $A$ 
*Note: if the determinant of an inverse matrix is equal to $0$ then the matrix is not invertible*


