# Linear Algebra References

Author: Jirawut Thongraar		License: CC BY-SA 4.0		Repository: https://github.com/non-j/classnotes

## Vector Space

A **Vector Space** is any set of objects that satisfy the following constraints.

| Name                                           | Constraints                                                  |
| ---------------------------------------------- | ------------------------------------------------------------ |
| Closure of Addition                            | $\operatorname{operator}{+}(v:\text{Vector},u:\text{Vector}):\text{Vector}$ |
| Associativity of Addition                      | $v+(u+w)=(v+u)+w$                                            |
| Commutativity of Addition                      | $v+u=u+v$                                                    |
| Identity Element of Addition                   | $v+\vec{0}=v$                                                |
| Inverse Elements of Addition                   | $v+(-v)=\vec{0}$                                             |
| Closure of Scalar Multiplication               | $\operatorname{operator}\cdot(v:\text{Vector},k:\text{Scalar}):\text{Vector}$ |
| Scalar Distributivity of Scalar Multiplication | $k\cdot(v+u)=k\cdot v+k\cdot u$                              |
| Vector Distributivity of Scalar Multiplication | $(k_1+k_2)\cdot v=k_1\cdot v+k_2\cdot v$                     |
| Compatibility of Scalar Multiplication         | $k_1\cdot(k_2\cdot v)=(k_1\cdot k_2)\cdot v$                 |
| Identity Element of Scalar Multiplication      | $1\cdot v=v$                                                 |

**Subspace** is a non-empty subset of a larger vector space that also satisfies all the above constraints. 

> **Theorem**
>
> $W$ is a subspace of $V$ exactly when **Closure of Addition** and **Closure of Scalar Multiplication** are satisfied.
>
> $W$ is a subspace of $V$ exactly when $\vec{0}\in W$ and $(u+k\cdot v)\in W$ for all $u,v$ in $W$.
>
> Intersection of subspaces is itself a subspace.

**Homogeneous Linear System**

A linear system $Ax=\vec{0}$ is called homogeneous when its right hand expression is $\vec{0}$. Its solution is a subspace of $\R^n$, also called **null space**.

## Linear Combination, Span, and Dimension

**Linear Combination** is an expression of a vector by combinations of addition and scalar multiplication of other vectors.

The space of all linear combination is called **span**.

> **Theorem**
>
> $\operatorname{span}(V)=\operatorname{span}(U)$ exactly when all vectors in $V$ and $U$ can be expressed as linear combination of vectors in the other set. 
>
> **Solving for Span**
>
> Setup a system of linear equation $Ax=v$ where $A$ is matrix which each column is a vector, $x$ is vector of linear combination coefficient, $v$ is vector to check whether it is in the span. 

Consider a set of vector $S$; if there exists multiple non-trivial paths that makes a closed cycle, then the set of vectors is **linearly dependent**. More formally, there exists non–trivial solutions to express zero vector as linear combination of set $S$. 

> **Theorem**
>
> $S$ is linearly dependent exactly when any vector in $S$ can be expressed as linear combination of the other vectors.
>
> If $\vec{0}\in S$, then $S$ is linearly dependent.
>
> If $|S|=1$, then $S$ is linearly independent as long as that one vector is not $\vec{0}$.

> **Wronskian and Linear Dependency of Functions**
>
> Functions - which satisfy the requirements of a vector space - are linearly dependent exactly when they can be expressed as linear combination of other functions. As in one of the function can be defined as linear combination of the others. 
>
> One way to check is to evaluate the functions at various positions.
> $$
> k_1f_1(x_1)+k_2f_2(x_1)+\dots+k_nf_n(x_1)=0\\
> k_1f_1(x_2)+k_2f_2(x_2)+\dots+k_nf_n(x_2)=0\\
> \vdots\\
> k_1f_1(x_n)+k_2f_2(x_n)+\dots+k_nf_n(x_n)=0\\
> $$
> If, for all values of $x$, there exists non-trivial solution of $k_1,k_2,\dots,k_n$, then the set of functions is linearly dependent.
>
> Another way to check is by using derivations of the functions, evaluated at the same value of $x$:
> $$
> k_1f_1(x)+k_2f_2(x)+\dots+k_nf_n(x)=0\\
> k_1f_1'(x)+k_2f_2'(x)+\dots+k_nf_n'(x)=0\\
> \vdots\\
> k_1f_1'^{(n-1)}(x)+k_2f_2'^{(n-1)}(x)+\dots+k_nf_n'^{(n-1)}(x)=0\\
> $$
> Expressed as homogenous linear system:
> $$
> \begin{bmatrix}
> f_1(x) & f_2(x) & \dots & f_n(x)\\
> f_1'(x)& f_2'(x)& \dots & f_n'(x)\\
> \vdots & \vdots & \ddots& \vdots\\
> f_1'^{(n-1)}(x) & f_2'^{(n-1)}(x) & \dots & f_n'^{(n-1)}(x)
> \end{bmatrix}
> k=\vec{0}
> $$
> 
>
> Wronskian for a set of (n-1)-differentiable functions is defined as follows:
> $$
> W(x)=\operatorname{det}\left(
> \begin{bmatrix}
> f_1(x) & f_2(x) & \dots & f_n(x)\\
> f_1'(x)& f_2'(x)& \dots & f_n'(x)\\
> \vdots & \vdots & \ddots& \vdots\\
> f_1'^{(n-1)}(x) & f_2'^{(n-1)}(x) & \dots & f_n'^{(n-1)}(x)
> \end{bmatrix}
> \right)
> $$
> Linearly independent means that there exists a value of $x$ such that no function is expressible as linear combination of the others. From the above homogeneous linear system, we wanted to know if there exists a value of $x$ such that the only solution of $k$ is $\vec{0}$. That means that if there exists $x$ such that $W(x)\ne0$, then the functions are linearly independent.

A set of vector $S$ is a **basis** for vector space $V$ if $S$ is linearly independent and $\text{span}(S)=V$.

For every vector, its linear combination expression of basis vectors is unique and is called **coordinates**.

> **Theorem**
>
> All bases for ﬁnite dimensional vector space have the same number of vectors as the dimension size.
>
> If the size of a set of vectors is larger than dimension size, then it is linearly dependent; if it is smaller, then it doesn’t span the full vector space.  
>
> If a set of vectors where its size is equal to the dimension size, then it is a basis exactly when it is linearly independent or it span the full vector space.
>
> If $W$ is a subspace of vector space $V$, then $W=V$ exactly when $\dim(W)=\dim(V)$.
>
> **Standard Basis**
>
> The basis that only consists of 0 and 1, rotating position such that the full vector space is expressible.
>
> **Change of Basis**
>
> Create a transformation matrix $A$ for the basis system, where each column of $A$ is the basis vector. The inverse, $A^{-1}$, is the transformation back to standard basis, allowing conversion back and forth between the standard basis and the basis system.
>