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
- Transformation is bijection (one-to-one and onto; it span the full output space)
- $\dim(\operatorname{row}(M))=\dim(\operatorname{col}(M))=n$
- $\dim(\operatorname{null}(M))=0$

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
- Eigenvalues are simply the values in the main diagonal.

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
2. For each entry in that row or column, calculate the cofactor:
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

### Adjoint Matrix

The matrix of cofactor is simply the matrix whose entries are replaced with the cofactor of that entry. Transpose the matrix of cofactor gives the adjoint matrix, $\operatorname{adj}(M)$.
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

The eigenvectors (there's infinite set of them) associated with eigenvalue is found by solving for $x$ in
$$
(M-\lambda I)x=0
$$
The set of solution of this is the eigenspace (that is $\{x\ |\ (M-\lambda I)x=0\}$). The dimension size of this is called geometric multiplicity.

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
- Dot product preserving: $Mv\cdot Mw=v\cdot w$
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

# Basis and Dimension

Basis is a set of linearly independent vectors which spans the subspace of interest. The number of basis vector for a subspace is the dimension of that subspace. Math symbol: $\dim(\ldots)$.

For a subspace, the choice of basis are not unique. They can be arbitrarily chosen for the purpose of simplifying calculations. The dimension is always the same for all valid choices.

> Tip: If there's a need to proof that a set of vectors is linearly independent, try fixing the order of the vectors and try proving it inductively from the first one.

Any vector in a subspace has a **unique** representation of linear combination using the basis vectors. 

If $S$ spans $V$ but is not a basis, then try remove some vectors to make it a basis. 
If $S$ is linearly independent but not a basis of $V$, then try add some vectors to make it a basis.

Linearly independent subset of $\mathbb{R}^n$ can have at most $n$ vectors. This means that a basis of a subspace in $\mathbb{R}^n$ also has at most $n$ vectors. A dimension of a subspace in $\mathbb{R}^n$ cannot exceed $n$.

The space $\{0\}$ has no basis. Even though $0$ spans this space, it is not a basis because $0$ is never linearly independent. Dimension is of zero space is zero.

If we have a vector $u$ in $\mathbb{R}^n$, the subspace perpendicular to $u$, that is $\{w\in\mathbb{R}^n\ |\ w\cdot u=0\}$ has $\dim=n-1$. This is also called a *hyperplane*. 
The reverse is also possible. If given a subspace with $\dim=n-1$, it is a hyperplane and you can find a line that is perpendicular to it.

If $V$ is subspace of $W$, $\dim(V)\leq\dim(W)$. When $\dim(V)=\dim(W)$, then $V=W$.

## Fundamental Spaces

Row space, $\operatorname{row}(\ldots)$, is the space spanned by row vectors of a matrix.
Column space, $\operatorname{col}(\ldots)$, is the space spanned by column vectors of a matrix.
Null space, $\operatorname{null}(\ldots)$, is the solution space of $Mx=0$ of a matrix $M$.

Of course: $\operatorname{row}(M^T)=\operatorname{col}(M)$ and $\operatorname{col}(M^T)=\operatorname{row}(M)$.

Rank is $\operatorname{rank}(M)=\dim(\operatorname{row}(M))=\dim(\operatorname{col}(M))$.
Nullity is $\operatorname{nullity}(M)=\dim(\operatorname{null}(M))$.

Orthogonal complement of $S$ (where $S$ is a non-empty subset, but necessary a subspace, of $\mathbb{R}^n$) is $S^\perp$, all vectors perpendicular to every vectors in $S$. Note that $S^\perp$ is always a subspace, even when $S$ is not.

This table shows example of orthogonal complement:

| $S$            | $S^\perp$                        |
| -------------- | -------------------------------- |
| $\mathbb{R}^n$ | $\{0\}$                          |
| $v\neq 0$      | $v^\perp$ (hyperplane through 0) |
| $\{0\}$        | $\mathbb{R}^n$                   |

Properties:
- $V\cap V^\perp=\{0\}$
- $(V^\perp)^\perp=V$
- $S^\perp=\operatorname{span}(S)^\perp$ (this one is meant for when $S$ is just a subset, not a subspace)
- $\operatorname{row}(M)=\operatorname{col}(M^T)=\operatorname{null}(M)^\perp$
- $\operatorname{row}(M^T)=\operatorname{col}(M)=\operatorname{null}(M^T)^\perp$
- Elementary row operation preserves $\operatorname{row}(M)$ and $\operatorname{null}(M)$

To get the basis for $\operatorname{span}(S)$, create a matrix $M$ whose rows are the vectors in $S$ (i.e., $\operatorname{span}(S)=\operatorname{row}(M)$), reduce the matrix, and the non-zero rows are the basis. 

To get the basis for $\operatorname{span}(S)$ and the basis must comes from $S$, then:
1) Put them into a column vectors
2) Reduce the matrix
3) The column with leading ones tells the position of the independent vectors
	- If column $i$ has leading ones, $S[i]$ is independent. 
- Note: The result is the basis of the column space. If the linear combination of linearly dependent vectors is desired, continue reduce the matrix fully and use the fact that row reduction doesn't change coordinates for linear combination

To get the basis for $\operatorname{span}(S)^\perp$, use the property $\operatorname{span}(S)^\perp=\operatorname{null}(S)$.

To check whether $b$ is in $\operatorname{span}(S)$, create a matrix $M$ whose column vectors are vectors in $S$, then solve $Mx=b$.

### CR Decomposition

A matrix $M$, we want $M=CR$ where $C$'s columns are the basis of column space and $R$'s rows are the basis of row space. Procedure:
1) Reduce the matrix $M$ fully
2) Copy non-zero rows into $R$ (from reduced matrix)
3) Copy the corresponding pivot columns into $C$ (from original matrix $M$)

## Dimension Theory

For matrix $M$ of size $m\times n$, the transformation goes from $n$ dimensions to $m$ dimensions:
- $\operatorname{rank}(M)$ is the dimensions of output of using $M$ which is $m-\text{"lost dof"}$
- $\operatorname{nullity}(M)=(n-m)+\text{"lost dof"}$
- "lost dof" refers to how, even though the output size is $m$, the degree of freedom of the output is actually less than $m$, thus some dof that can theoretically be encoded in the output is somehow "lost".
- Conclusion: $\operatorname{rank}(M)+\operatorname{nullity}(M)=n$ 
	- ($=m-\text{"lost dof"}+(n-m)+\text{"lost dof"}$)
- $\dim(W)+\dim(W^\perp)=n$

- $\operatorname{rank}(M)=\operatorname{rank}(M^T)$
- $\operatorname{rank}(M)\leq \min(m,n)$
- $\operatorname{rank}(M)+\operatorname{nullity}(M^T)=m$

The matrix produced by $u\otimes v$ (outer product) has $\operatorname{rank}=1$. Every matrix with $\operatorname{rank}=1$ can be factored into $u\otimes v$.
The matrix produced by $u\otimes u$ is also symmetric, and symmetric matrix with $\operatorname{rank}=1$ can be factored into $u\otimes u$ or its equivalent $-u\otimes u$.

When $Mx=b$ is consistent, the augmented matrix $[M\ b]$ has the same rank as $M$.

Full column rank is when column vectors are linearly independent and are the basis of the column space, also $\dim(\operatorname{col}(M))=\operatorname{rank}(M)=n$.
Full row rank is when row vectors are linearly independent and are the basis of the row space, also $\dim(\operatorname{row}(M))=\operatorname{rank}(M)=m$.
Note: Some matrix may only be full column/row rank, but not the other.

## Projection and Approximation

Project vector $x$ onto $a$ (a vector):
$$
\operatorname{proj}_a(x)=\frac{x\cdot a}{\|a\|^2}a
$$
Or alternatively using projection matrix:
$$
P=\frac{1}{a\cdot a}(a\otimes a)
$$

Any vector can be expressed as the projected component and the perpendicular component:
$$
x=(\operatorname{proj}_a(x))+(x-\operatorname{proj}_a(x))
$$
This expression is **unique**.

Also works with subspace:
$$
x=(\operatorname{proj}_W(x))+(\operatorname{proj}_{W^\perp}(x))
$$
To project a vector onto a subspace:
$$
\operatorname{proj}_W(x)=M(M^TM)^{-1}M^Tx
$$
with $M$ being a matrix whose columns are the basis of $W$.
> Note: If $W=\{0\}$, $x=0+x$ and technically, any vector is "orthogonal" to zero.

$P$ is matrix for orthogonal projection (that is $Px=\operatorname{proj}_W(x)$) if and only if $P$ is symmetric, idempotent, and $\operatorname{rank}(P)=\dim(W)$. $W=\operatorname{col}(P)$. 
Additional properties:
- $\operatorname{tr}(P)=\operatorname{rank}(P)$

> Idempotent matrix is a matrix where $M=M^2$. So many application of the transformation have the same effect as applying it once.

### Best Approximation

With a point $p$ and a subspace $W$, we can find $x\in W$  is closest to $p$ using projection: $x=\operatorname{proj}_W(p)$.

With linear equation system $Mx=p$, we can find the closest solution by solving the equation $M^TMx=M^Tp$.
The vector $p-Wx$ is called the *least squares error vector* and its size is the *least squares error*.

## Orthogonal Basis

For $v_1,v_2,\ldots,v_n$ bases which are orthonormal, we can project a vector onto this subspace using:
$$
\operatorname{proj}_W(x)=(x\cdot v_1)v_1+(x\cdot v_2)v_2+\ldots+(x\cdot v_n)v_n
$$
If the bases are not normalized, simply scale them appropriately. If $x$ is in subspace already, this gives a coordinates.

The Gram-Schmidt Process converts regular bases into orthogonal bases. Input is $u_1,u_2,\ldots,u_n$.
$$
\begin{aligned}
v_1&=u_1 \\
v_2&=u_2-\operatorname{proj}_{v_1}(u_2) \\
v_3&=u_3-\operatorname{proj}_{v_1}(u_3)-\operatorname{proj}_{v_2}(u_3) \\
v_4&=u_4-\operatorname{proj}_{v_1}(u_4)-\operatorname{proj}_{v_2}(u_4)-\operatorname{proj}_{v_3}(u_4) \\
\end{aligned}
$$
and so on. Optionally normalize.

### QR Decomposition

With a matrix $M$, put the column vectors into Gram-Schmidt process to get $Q$. We can then get:
$$
M=QR
$$
where $R$ is invertible upper triangular matrix. $R=Q^{-1}M=Q^TM$.
Only works with full rank square matrix $M$.

Using QR decomposition, the least squares solution of $Mx=b$ can be found by solving the system $Rx=Q^Tb$.

### Householder Matrix
	
Reflects a vector $x$ about a hyperplane perpendicular to a vector $a$.
$$
x=x-2\operatorname{proj}_a(x)
$$
$$
H_a=I-\frac{2}{a\cdot a}(a\otimes a)
$$
## Change of Basis Matrix

To change from basis $B$ to $B'$, do:
1) Create matrix $\begin{bmatrix}B' & B\end{bmatrix}$ (column vectors)
2) Row reduce this matrix fully
3) Extract the change of basis from the right side. 

### Standard Basis to Another Basis

A matrix $P$ with column vectors $p_1,p_2,\ldots,p_n$ is the change of basis from $\{p_1,p_2,\ldots,p_n\}$ to standard basis. 

### Linear Transformation Under Different Basis

If $P$ changes basis $B$ to $B'$, a linear transformation under one basis can be changed to under another:
$$
T_{B'}=P\ T_B\ P^{-1}
$$
# Diagonalization

## Similar Matrix

Matrix $A$ and $B$ are similar if they can be expressed as: $B=P^{-1}\ A\ P$

They have the same:
- determinant
- rank
- nullity
- trace
- characteristic polynomial (eigenvalues have same algebraic and geometric multiplicity)

If we know that $x$ is an eigenvector of $B$, then $Px$ is an eigenvector of $A$ with the same eigenvalue. 
Steps: Write $Bx=P^{-1}APx=\lambda x$, then rearrange into $APx=P\lambda x=\lambda(Px)$.

## Diagonalization Process

For $n\times n$ matrix $M$, find $n$ linearly independent eigenvectors and diagonalize a matrix as:
$$
M=PDP^{-1}
$$
where $D$ is a diagonal consisting of eigenvalues and $P$'s columns are eigenvectors.

## Orthogonal Diagonalization

Orthogonal diagonalization adds the requirement that $P$ is orthogonal. Only possible exactly when $M$ is symmetric. To do this, apply Gram-Schmidt after regular diagonalization.

## Cayley-Hamilton Theorem

A square matrix which has an expanded characteristic polynomial of:
$$
\lambda^n+c_1\lambda^{n-1}+c_2\lambda^{n-2}+\ldots+c_n=0
$$
also satisfies:
$$
M^n+c_1M^{n-1}+c_2M^{n-2}+\ldots+c_nI=0
$$
With this theorem, the equation can be rearranged to form inverse of $M$:
$$
M(M^{-1})=M(-\frac{1}{c_n}M^{n-1}-\frac{c_1}{c_n}M^{n-2}-\frac{c_2}{c_n}M^{n-3}-\ldots-\frac{c_{n-1}}{c_n}I)=I
$$

## Evaluate Function

For $f$ whose Maclaurin series expansion converges on interval containing eigenvalues of $M$, it can be evaluated like this:
$$
f(M)=P\begin{bmatrix} f(\lambda_1) & 0 & \ldots & 0 \\ 0 & f(\lambda_2) & \ldots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \ldots & f(\lambda_n)\end{bmatrix}P^{-1}
$$
## Quadratic Form

Quadratic forms are polynomials made out of $x_i^2$ or $x_ix_j$. They can be expressed with matrix:
$$
Q_M(x)=x^TMx
$$
For diagonal $M$:
$$
x^TMx=\begin{bmatrix}x_1 & x_2 & \ldots & x_n\end{bmatrix}\begin{bmatrix} \lambda_1 & 0 & \ldots & 0 \\ 0 & \lambda_2 & \ldots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \ldots & \lambda_n\end{bmatrix}\begin{bmatrix}x_1 \\ x_2 \\ \vdots \\ x_n\end{bmatrix}=\lambda_1x_1^2+\lambda_2x_2^2+\ldots+\lambda_nx_n^2
$$
### Principal Axes Theorem

If $M$ is symmetric and $P$ orthogonally diagonalizes $M$, then we can remove the cross term using:
$$
x^TMx=(Py)^TM(Py)=y^T(P^TMP)y=y^TDy=\lambda_1y_1^2+\lambda_2y_2^2+\ldots+\lambda_ny_n^2
$$

### Conic Section

Ellipses have the form $x^2/a^2+y^2/b^2=1$ and hyperbolas have the form $x^2/a^2-y^2/b^2=1$ or $y^2/b^2-x^2/a^2=1$. 
If the equation of the form $ax^2+2bxy+cy^2+f=0$ is given, rewrite it as $x^TMx=-f$, diagonalize to get rid of the $xy$ term, and determine the type.

Alternative mean of identification: $x^TMx=1$ is ellipse if it is positive definite, $x^TMx=1$ is hyperbola if it is negative definite, $x^TMx=1$ has no graph if it is indefinite.

### Definite

For all vector $x\neq0$:

| Condition    | Result                |
| ------------ | --------------------- |
| $x^TMx>0$    | Positive Definite     |
| $x^TMx\geq0$ | Positive Semidefinite |
| $x^TMx\leq0$ | Negative Semidefinite |
| $x^TMx<0$    | Negative Definite     |
| Otherwise    | Indefinite            |

Matrix $M$ is positive definite exactly when eigenvalues of $M$ are all positive. Same goes for negative definite. Indefinite matrix contains a mix of positive and negative eigenvalues. 

Symmetric $M$ is positive definite exactly when $\det(M(1:k,1:k))$ is positive for all $k$. 
Additional equivalent properties when $M$ is positive definite:
- There is symmetric positive definite $A$ such that $M=A^2$
- There is invertible $B$ such that $M=B^TB$

## Singular Value Decomposition

Any matrix $M$ have SVD.
$$
M=U\Sigma V^T
$$
where $U$ and $V$ are orthogonal matrix and $\Sigma$ is diagonal matrix

Steps for square matrix:
1) Get $V$ which diagonalizes $M^TM$
2) Diagonal entries of $\Sigma$ are $\sigma_i=\sqrt{\lambda_i}$ where $\lambda_i$ are eigenvalues of $M^TM$ in order of $V$
3) Optionally sort the order by $\sigma_i$
4) Get $u_1,u_2,\ldots,u_k$ as orthonormal basis of $\operatorname{col}(M)$
5) Extend $u_i$s up to $u_n$ so that it spans the full $\mathbb{R}^n$ while remaining orthonormal.

Steps for general matrix:
1) Get eigenvalues and eigenvectors of $M^TM$ and $MM^T$
2) Put eigenvectors of $M^TM$ into $V$
3) Put eigenvectors of $MM^T$ into $U$
4) Put the square roots of eigenvalues of either $M^TM$ or $MM^T$ (they should both be equal) into $\Sigma$
