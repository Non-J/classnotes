# Introduction to Linear Algebra - Subspaces Exercise

1\. Determine which of the following are subspaces of $\mathbb{R}^3$

   b. The set of all vector of the form $(a,b,c)$, where $a=b+c$.

   ​	Let $q=(q_0,q_1,q_2), w=(w_0,w_1,w_2)$ such that they are in the above subspace.
$$
   \begin{aligned}
   q+w							&=(q_0+w_0,q_1+w_1,q_2+w_2)\\
   q_1+w_1+q_2+w_2	&=(q_1+q_2)+(w_1+w_2)\\
   								&=(q_0)+(w_0)				&\text{Uses }a=b+c\\
   								&=q_0+w_0\\
   \end{aligned}\\
   \text{Thus, }q+w\text{ is in the above subspace.}
$$
   ​	Let $k$ be real scalar.
$$
   \begin{aligned}
   kw				&=(kw_0,kw_1,kw_2)\\
   kw_1+kw_2	&=k(w_1+w_2)\\
   					&=k(w_0)		&\text{Uses }a=b+c\\
   					&=kw_0
   \end{aligned}\\
   \text{Thus, }kw\text{ is in the above subspace.}
$$
   ​	Therefore, the above subspace is a subspace of $\mathbb{R}^3$.

2\. Determine which of the following are subspaces of $M_{3\times3}(\mathbb{R})$

   b. The set of all $3\times3$ matrices $A$ such that $AB=BA$ for fixed $3\times3$ matrix B.

​		Let $q,w$ be matrices in the above subspace.
$$
\begin{aligned}
(q+w)B	&=B(q+w)	\\
qB+wB		&=Bq+Bw		& \text{Distributive Property}\\
qB+qB		&=qB+wB		& \text{Uses }AB=BA
\end{aligned}\\
\text{Thus, }q+w\text{ is in the above subspace.}
$$
​		Let $k$ be real scalar.
$$
\begin{aligned}
(kw)B	&=B(kw)\\
k(wB)	&=k(wB)\\
\end{aligned}\\
\text{Thus, }kw\text{ is in the above subspace.}
$$
​		Therefore, the above subspace is a subspace of $M_{3\times3}(\mathbb{R})$.

3\. Determine which of the following are subspaces of $P_3$.

   a. All polynomials $a_0+a_1x+a_2x^2+a_3x^3$ for which $a_0+a_1+a_2+a_3=0$

   ​	Let $q,w$ be polynomials in the above subspace.
$$
   \begin{aligned}
   q+w	&=q_0+q_1x+q_2x^2+q_3x^3+w_0+w_1x+w_2x^2+w_3x^3\\
   		&=(q_0+w_0)+(q_1+w_1)x+(q_2+w_2)x^2+(q_3+w_3)x^3\\
   \end{aligned}\\
   q_0+w_0+q_1+w_1+q_2+w_2+q_3+w_3=(q_0+q_1+q_2+q_3)+(w_0+w_1+w_2+w_3)=0+0=0\\
   \text{Thus, }q+w\text{ is in the above subspace}
$$
   ​	Let $k$ be real scalar.
$$
   kw=kw_0+kw_1x+kw_2x^2+kw_3x^3\\
   kw_0+kw_1+kw_2+kw_3=k(w_0+w_1+w_2+w_3)=k(0)=0\\
   \text{Thus, }kw\text{ is in the above subspace.}
$$

4\. In each part, determine whether the given vectors span $\mathbb{R}^3$

   c. $v_1=(3,1,4),v_2=(2,-3,5),v_3=(5,-2,9),v_4=(1,4,-1)$
$$
   \begin{bmatrix}
   3	&	2 & 5 & 1 \\
   1	&	-3 & -2 & 4\\
   4 & 5 & 9 & -1
   \end{bmatrix}
   \sim
   \begin{bmatrix}
   1	&	0 & 1 & 1 \\
   0	&	1 & 1 & -1\\
   0 & 0 & 0 & 0
   \end{bmatrix}
$$
   The given set of vector does not span $\mathbb{R}^3$.

5\. Suppose that $v_1=(2,1,0,3)$, $v_2=(3,−1,5,2)$, and $v_3=(−1,0,2,1)$. Is $(1,1,1,1)\in \text{span}(\{v_1,v_2,v_3\})$?
$$
   \begin{bmatrix}
   2	&	3  & -1 & 1\\
   1	&	-1 & 0  & 1\\
   0 & 5  & 2  & 1\\
   3 & 2  & 1  & 1
   \end{bmatrix}
   \sim
   \begin{bmatrix}
   1	&	0 & 0 & 0\\
   0	&	1 & 0 & 0\\
   0 & 0 & 1 & 0\\
   0 & 0 & 0 & 1
   \end{bmatrix}
$$
   $(1,1,1,1)\notin \text{span}(\{v_1,v_2,v_3\})$

7\. Let $v_1$, $v_2$, and $v_3$ be nonzero vectors in vector space. Show that
$$
\text{span}(\{v_1,v_2,v_3\})=\text{span}(\{v_1+v_2,v_2+v_3,v_3+v_1\})
$$
​	Let $S_1=\{v_1,v_2,v_3\}$ and $S_2=\{v_1+v_2,v_2+v_3,v_3+v_1\}$

​	Consider that if each element in $S_1$ and $S_2$ can be written as linear combination of elements of the other set, then $\text{span}(S_1)=\text{span}(S_2)$.

​	Each element of $S_1$ can be written as linear combination of $S_2$ as follow:
$$
\begin{aligned}
v_1	&=\frac{1}{2}((v_1+v_2)-(v_2+v_3)+(v_3+v_1))\\
v_2	&=\frac{1}{2}((v_2+v_3)-(v_3+v_1)+(v_1+v_2))\\
v_3	&=\frac{1}{2}((v_3+v_1)-(v_1+v_2)+(v_2+v_3))\\
\end{aligned}
$$
​	It is obvious that $S_2$ can be written as linear combination of $S_1$.

​	Therefore, $\text{span}(\{v_1,v_2,v_3\})=\text{span}(\{v_1+v_2,v_2+v_3,v_3+v_1\})$