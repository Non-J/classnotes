# Linear Equation System

Solutions set can be:
- Empty, no solution. Also called *inconsistent* system.
- There's only one solution.
- There're infinitely many solutions. This happens when multiple input maps to the same output; the dimension was crushed. 

Homogeneous linear system refers to the case where the desired output is 0. We're asking for the set of input that makes the output 0.
- Always have 0 as a solution. Also called *trivial* solutions.
- Other solutions exist when dimension got crushed.

Can be solved via row reduction operations, which includes:
- Swap 2 rows
- Scale a row
- Add scaled row to another row

# Matrix

## Matrix Multiplication
Adapted [[MAS102.Notes#Matrix Multiplication]].

### Matrix Multiplication by Entry

Each entry in the result is the dot-product of the corresponding $A$'s row and $B$'s column.

$$AB(i,j)=A(i,)\cdot B(,j)$$

### Matrix Multiplication by Column Vector

Matrix multiplication can be seen as applying the matrix transformation $A$ on each of the column vector of $B$.

$$
AB=A\begin{bmatrix}B(,1) & B(,2) & \ldots & B(,n)\end{bmatrix}=\begin{bmatrix}AB(,1) & AB(,2) & \ldots & AB(,n)\end{bmatrix}
$$

### Matrix Multiplication by Row Vector

Similar interpretation as [[MAS109 Notes#Matrix Multiplication by Column Vector|Matrix Multiplication by Column Vector]], but with row and it is to the right.

$$
AB=\begin{bmatrix} A(1,) \\ A(2,) \\ \vdots \\ A(n,) \end{bmatrix}B=\begin{bmatrix} A(1,)B \\ A(2,)B \\ \vdots \\ A(n,)B \end{bmatrix}
$$

### Matrix Multiplication by Tensor Product

Outer product (or Tensor product) for $x\in\mathbb{R}^n,\,y\in\mathbb{R}^m$:
$$
x\otimes y=(x)(y^T)
$$
Basically, this operation constructs a matrix by using $x$ as the row-header and $y$ as the column-header, and then each entry is simply the multiplication of the headers.

[[MAS109 Notes#Matrix Multiplication by Entry|Usual matrix multiplication]] is done row-by-col. But what if we take the tensor product by doing col-by-row:

$$
AB=\begin{bmatrix} A(,1) & A(,2) & \ldots & A(,n) \end{bmatrix} \begin{bmatrix} B(1,) \\ B(2,) \\ \vdots \\ B(n,) \end{bmatrix}=\sum_{i=1}^nA(,i)\otimes B(i,)
$$
## Transpose

### Trace
Trace is the sum of the diagonal of a square matrix.
$$
\operatorname{tr}(M)=M(1,1)+M(2,2)+\ldots+M(n,n)
$$
The trace can be used to relate inner-product (a.k.a., dot-product) and outer-product (a.k.a., tenser-product):
$$
u\cdot v=\operatorname{tr}(u\otimes v)
$$

Properties:
- $(M^T)^T=M$
- $(A+B)T=A^T+B^T$
- $(AB)^T=B^TA^T$
- $(A^T)^{-1}=(A^{-1})^T$
- $\operatorname{tr}(A^T)=\operatorname{tr}(A)$
- $\operatorname{tr}(A+B)=\operatorname{tr}(A)+\operatorname{tr}(B)$
- $\operatorname{tr}(AB)=\operatorname{tr}(BA)$

## Invert

The matrix $M$, if it's invertible into $M^{-1}$, then the invert paring is unique and $(M)(M^{-1})=I$. If it's not invertible, then it is called *singular*.

To find the invert, apply row reduction operations on the matrix $\begin{bmatrix} M & I \end{bmatrix}$ and the result is $\begin{bmatrix} I & M^{-1} \end{bmatrix}$ (if it is invertible).
