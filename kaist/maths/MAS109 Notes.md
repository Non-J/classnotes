# Linear Equation System

Solutions set can be:
- Empty, no solution. Also called *inconsistent* system.
- There's only one solution.
- There're infinitely many solutions. This happens when multiple input maps to the same output; the dimension was crushed. 

Homogeneous linear system refers to the case where the desired output is 0. We're asking for the set of input that makes the output 0.
- Always have 0 as a solution. Also called *trivial* solutions.
- Other solutions exist when dimension got crushed.

Can be solved via row reduction operations, which includes:
- Scale a row
- Swap 2 rows
- Add scaled row to another row

Row equivalent: Matrices belongs to the same row equivalent class if the row reduction operations give the same output. 

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
The trace can be used to relate inner-product (aka, dot-product) and outer-product (aka, tenser-product):
$$
u\cdot v=\operatorname{tr}(u\otimes v)
$$

Properties:
- $(M^T)^T=M$
- $(A+B)^T=A^T+B^T$
- $(AB)^T=B^TA^T$
- $(A^T)^{-1}=(A^{-1})^T$
- $\operatorname{tr}(A^T)=\operatorname{tr}(A)$
- $\operatorname{tr}(A+B)=\operatorname{tr}(A)+\operatorname{tr}(B)$
- $\operatorname{tr}(AB)=\operatorname{tr}(BA)$

## Invert

The matrix $M$, if it's invertible into $M^{-1}$, then the invert paring is unique and $(M)(M^{-1})=I$. If it's not invertible, then it is called *singular*.

To find the invert, apply row reduction operations on the matrix $\begin{bmatrix} M & I \end{bmatrix}$ and the result is $\begin{bmatrix} I & M^{-1} \end{bmatrix}$ (if it is invertible).

Properties: 
- $(M^{-1})^{-1}=M$
- $(M^T)^{-1}=(M^{-1})^T$
- $(kM)^{-1}=\frac{1}{k}M^{-1}$
- $(AB)^{-1}=B^{-1}A^{-1}$

TFAE (assuming square matrix $M$):
- $M$ is reducible to row echelon form
- $M$ is expressible as product of elementary matrices
- $M$ is invertible
- $Mx=v$ always have only one solution. The solution can be found using the inverted matrix.
- Columns and rows are linearly independent
- $\det(M)\neq 0$
- Transformation is bijection (one-to-one and onto (it span the full output space))

## Subspace

A subspace must satisfies:
- Closed under scalar multiplication: pick any vector $w\in W$ and any scalar $c$, then $cw$ stays in $W$.
- Closed under addition: pick any two vectors $v\in W$ and $w\in W$, then $v+w$ stays in $W$.

Example of subspace: 
- The smallest subspace is ${0}$. Any other subspace must also contain $0$.
- $\mathbb R^n$
- Solution set of a linear equation system, called solution space
- Solution set of $Mx=0$, called null space 
- Span is a subspace reachable by linear combination of basis vectors.

## Linearly Dependent

Vectors in a set is linearly independent when there are no constants $c_i$ which satisfies:
$$
c_1v_1+c_2v_2+c_3v_3+\ldots+c_nv_n=0
$$
(doesn't count if all $c_i$ are zero)

If you have more than $n$ vectors in $\mathbb{R}^n$ space, there are linearly dependent vectors among us ඞ. 

## Special Matrices

### Diagonal Matrix

Diagonal matrix $D$ has a form:
$$
D=\begin{bmatrix}d_1 & 0 & 0 & \ldots & 0 \\ 0 & d_2 & 0 & \ldots & 0 \\ 0 & 0 & d_3 & \ldots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \ldots & d_n\end{bmatrix}
$$
The invert is easily found as:
$$
D=\begin{bmatrix}1/d_1 & 0 & 0 & \ldots & 0 \\ 0 & 1/d_2 & 0 & \ldots & 0 \\ 0 & 0 & 1/d_3 & \ldots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \ldots & 1/d_n\end{bmatrix}
$$
Raising power (with positive integer) is also easily found:
$$
D^k=\begin{bmatrix}d_1^k & 0 & 0 & \ldots & 0 \\ 0 & d_2^k & 0 & \ldots & 0 \\ 0 & 0 & d_3^k & \ldots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \ldots & d_n^k\end{bmatrix}
$$

### Triangular Matrix

Upper triangular:
$$
M=\begin{bmatrix}* & * & * & \ldots & * \\ 0 & * & * & \ldots & * \\ 0 & 0 & * & \ldots & * \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \ldots & *\end{bmatrix}
$$

Lower triangular:
$$
M=\begin{bmatrix}* & 0 & 0 & \ldots & 0 \\ * & * & 0 & \ldots & 0 \\ * & * & * & \ldots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ * & * & * & \ldots & *\end{bmatrix}
$$

- Diagonal matrix are both upper and lower matrix.
- Invertible if all diagonal entries are not zero. The invert of lower/upper triangular is also lower/upper triangular.
- Product of lower/upper triangular matrices is also lower/upper triangular matrix.
- Determinant is simply the product of the main diagonal.

### Symmetric and Skew

Symmetric: $M=M^T$
Skew: $M^T=-M$
Zero matrix and both symmetric and skew (only one that are both simultaneously).

Product of symmetric matrices is symmetric when product is commutative: $(AB)^T=B^TA^T=BA=AB$
If symmetric matrix is invertible, the invert is also symmetric

For a square matrix, $M$, $MM^T$ and $M^TM$ are all either invertible or not invertible (they are all linked together). $M$ doesn't have to be symmetric.

### Nilpotent Matrix

Square matrix where $M^k=0$ for some $k$. Basically, it converges to 0 at some point.
For nilpotent $M$, $I-M$ is invertible and $(I-M)^{-1}=M^0+M^1+M^2+\ldots=I+M^1+M^2+M^3+\ldots+M^{k-1}$ (because $M^0=I$ and $M^k$ and above are all zero)

## LU Decomposition

For a square matrix $A$, we want $A=LU$ where $L$ is lower triangular matrix and $U$ is upper triangular matrix. 
LU decomposition might not exist. LU decomposition might not be unique.

If $A$ can be reduced to row echelon form (using Gaussian process) without swapping rows, then it can be LU decomposed.
> Note: For a random matrix, chances are swapping rows is not necessary. It is necessary when there is a 0 in the diagonal, which is unlikely for a random matrix.

Steps to do LU decomposition:
- Do the Gaussian process
- Write the Gaussian process steps as: $(E_n\ldots E_3E_2E_1)M=U$ 
- Move the elementary matrices to the right side: $M=(E_n\ldots E_3E_2E_1)^{-1}U$ 
- Compute $L=E_1^{-1}E_2^{-1}E_3^{-1}\ldots E_n^{-1}$

Same method but with alternative computation step:
We want to decompose $A$. Start with $(I)(A)$. For each step in the Gaussian process, say $E_1$, apply the step like so: $(IE_1^{-1})(E_1A)$. For the next step $E_2$, apply like so: $(IE_1^{-1}E_2^{-1})(E_2E_1A)$. Keep doing and the right term will yield row-echelon form (upper triangular) and the left side will be lower triangular form. 

### LDU Decomposition

The $L$ can be further decomposed into $LD$, where the diagonal values are moved to $D$, leaving the $L$ part with 1 on the diagonal. The result is: $A=LDU$
This decomposition is unique.

### PLU Decomposition

Accumulate all of the row swapping permutations into the matrix $P^{-1}$. Then, do LU decomposition as usual: $P^{-1}A=LU$ or $A=PLU$.

## Determinants

Properties:
- $\det(M)=\det(M^T)$
- $\det(kM)=k^n\det(M)$
- $\det(AB)=\det(A)\det(B)$
- $\det(M^{-1})=1/\det(M)$

### Product of Permutation

1. Generate a permutation $p$ of 1 to n.
2. Calculate the product $M(1,p_1)M(2,p_2)M(3,p_3)\ldots M(n,p_n)$
3. Multiply with $-1$ if permutation length is odd.
	- Permutation length is the minimum number of swaps required to go from 1,2,3,...,n to the permutation
	- For $n\ge 2$, $n!$ is the number of all permutations, and the number of even permutation = number of odd permutation = $n!/2$
5. Sum up all such value for all possible permutations

### Cofactor Expansion

1. Pick a row or column, ideally with as many zero as possible
2. For each entry in that row or column:
	- Copy the matrix, remove the entry's row and column from the copy
	- Calculate the determinant of that copy
	- Multiply with sign determined by the pattern: $$\begin{bmatrix} + & - & + & - & + & \ldots\\ - & + & - & + & - & \ldots\\ + & - & + & - & + & \ldots\\ - & + & - & + & - & \ldots\\+ & - & + & - & + & \ldots\\ \vdots & \vdots & \vdots & \vdots & \vdots & \ddots \end{bmatrix}$$
3. Sum up all such value for all entry in the picked row or column

### Reverse of Row Reduction

1. Use row reduction operations
2. Keep track of the operations and it's effect on determinant:
	- Scale a row with $k$, determinant is also multiplied by $k$
	- Swap 2 rows, determinant sign is flipped (= multiplied by -1)
	- Add scaled row to another row, no effect
3. Apply the reverse effect on 1

### Matrix of Cofactor

The matrix of cofactor is simply the matrix whose entry are replaced with the cofactor of that entry. Math symbol: $\operatorname{adj}(M)$.
Can be used to find invert: $M^{-1}=\frac{1}{\det(M)}\operatorname{adj}(M)$.

### Cramer's Rule

For linear system $Mx=v$, the solution is:
$$
x_i=\frac{\det(M^*_i)}{\det(M)}
$$
where $M^*_i$ is a copy of matrix $M$ with column $i$ replaced with $v$.

### Cross product

$$
v\times w=\begin{vmatrix} \hat i & \hat j & \hat k \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3\end{vmatrix}
$$
$$
u\cdot(v\times w)=\begin{vmatrix} u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3\end{vmatrix}
$$

## Eigenvalues and Eigenvectors

> Concept: 
> Start with $Mx=\lambda x$. Make right side matrix: $Mx=\lambda Ix$. Rearrange the equation: $(M-\lambda I)x=0$. Solve.

The **characteristic polynomial** of $M$ is
$$
\det(M-\lambda I)
$$
Eigenvalues can be found by solving for the root of this polynomial. 
The solution space is the eigenspace.

The eigenvectors (there's infinite set of them) associated with eigenvalue is found by solving for $x$ in
$$
(M-\lambda I)x=0
$$

For matrix $M$ of size $n\times n$, 
$$\det(M-\lambda I)=(\lambda-\lambda_1)^{m_1}(\lambda-\lambda_2)^{m_2}(\lambda-\lambda_3)^{m_3}\ldots(\lambda-\lambda_r)^{m_r}=0$$with distinct $\lambda_i$s (some of these might be complex).
Then $m_i$ is called algebraic multiplicity of $\lambda_i$ with $m_i>0$ and their sum must equals $n$ (the size of matrix).

>Fun Property:
> $\det(M)=\lambda_1\lambda_2\lambda_3\ldots\lambda_n$  and  $\operatorname{tr}(M)=\lambda_1+\lambda_2+\lambda_3+\ldots+\lambda_n$
> with eigenvector repeated according to their multiplicity

Fixed points, points that doesn't move under linear transformation, are eigenvector with eigenvalue of 1

# Linear Transformation

Linear transformation satisfies:
- $T(c\vec v)=cT(\vec v)$
- $T(\vec v+\vec w)=T(\vec v)+T(\vec w)$ 

Matrix multiplication is linear transformation.
Affine translation is not linear transformation.

A square matrix is **orthogonal** (aka, **orthonormal**) if $M^TM=I$. So, $M^T=M^{-1}$. Orthogonal linear operator have the following properties:
- Dot product preserving: $Mv\cdot Mw=v\cdot w$ (dot-product preserving)
- Length preserving: $||Mv||=||v||$
- Columns/rows of $M$ are orthonormal (perpendicular and size of 1)
- $\det(M)=1$ or $-1$
> Note: can be generalized to non-square matrices as well, but have to be careful about matrix size or transformation dimension.

There are only 2 orthogonal linear operator on $\mathbb{R}^2$: rotation and reflection (or some combination of the two).
For 3 dimension, there are 3 types: rotation about line then origin ($\det=1$), reflection about a plane that pass through origin (aka, a plane perpendicular to some vector $u$, denoted as $u^\perp$) ($\det=-1$), and rotation using the first one followed by reflection using the second one ($\det=-1$).

For the rotation, we can extract the axis by finding the eigenvector with eigenvalue of 1. 
After this, to find the angle, try apply the transformation on $v^\perp$ (where $v$ is the rotation axis) and measure the changes in angle.
For the reflection, we can extract the plane's normal by finding the eigenvector with eigenvalue of -1.
For the combined rotation and reflection, do both of the above.

## 2D Rotation and Reflection

Rotated by $\theta$:
$$
R_{\theta}=\begin{bmatrix} \cos(\theta)&-\sin(\theta) \\ \sin(\theta)&\cos(\theta) \end{bmatrix}
$$

Reflected by a line of angle $\theta$ with x-axis:
$$
H_{\theta}=\begin{bmatrix} \cos(2\theta)&\sin(2\theta) \\ \sin(2\theta)&-\cos(2\theta) \end{bmatrix}
$$

## Kernel and Range

$\ker(T)$ is the vectors that maps to 0 after $T$, that is $\{v\ |\ T(v)=0\}$
Kernel always contain 0. Kernel is a subspace.
Null space, $\operatorname{null}(M)$, is the same as $\ker(T_M)$. 

For a linear transformation $T:\mathbb{R}^n\rightarrow\mathbb{R}^m$, it simply sends a subspace of $\mathbb{R}^n$ to a subspace of $\mathbb{R}^m$.
Then, $\operatorname{ran}(T)=T(\mathbb{R}^n)=\{w\in\mathbb{R}^m\ |\ w=T(v),\ v\in\mathbb{R}^n\}$.
It is equivalent to $\operatorname{col}(M)$, the column space of $M$. As in, extract the column of $M$ as vectors and span them out.

$T$ is
- onto (surjective) if $\operatorname{ran}(T)=\mathbb{R}^m$ (maps to full output space)
- one-to-one (injective) if ( $T(v)=T(v')\Leftrightarrow v=v'$ )
	- Only when $\ker(T)=\{0\}$
- bijective = surjective + one-to-one
