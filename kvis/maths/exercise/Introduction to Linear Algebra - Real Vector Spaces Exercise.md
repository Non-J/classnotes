# Introduction to Linear Algebra - Real Vector Spaces Exercise

2. Let $V$ be the set of all points $(x, y, z)$ in $\mathbb{R}^3$ such that $x+y+z=0$, with the usual addition and scalar multiplication. Is $V$ a vector space? Prove or disprove it.

   Let $u=(x_u,y_u,z_u)$, $v=(x_v,y_v,z_v)$, and $w=(x_w,y_w,z_w)$ where $\{u,v,w\}\subset V$.

   1. $$
      u+v=(x_u,y_u,z_u)+(x_v,y_v,z_v)=(x_u+x_v,y_u+y_v,z_u+z_v)\\
      x_u+x_v+y_u+y_v+z_u+z_v=(x_u+y_u+z_u)+(x_v+y_v+z_v)=0+0=0\\
      \text{Thus, }(u+v)\in V
      $$

   2. $$
      \begin{aligned}
      u+v	&=(x_u,y_u,z_u)+(x_v,y_v,z_v)\\
      		&=(x_u+x_v,y_u+y_v,z_u+z_v)\\
      		&=(x_v+x_u,y_v+y_u,z_v+z_u)\\
      		&=(x_v,y_v,z_v)+(x_u,y_u,z_u)\\
      		&=v+u
      \end{aligned}
      $$

   3. $$
      \begin{aligned}
      u+(v+w)	&=(x_u,y_u,z_u)+((x_v,y_v,z_v)+(x_w,y_w,z_w))\\
      				&=(x_u,y_u,z_u)+(x_v+x_w,y_v+y_w,z_v+z_w)\\
      				&=(x_u+x_v+x_w,y_u+y_v+y_w,z_u+z_v+z_w)\\
      				&=(x_u+x_x,y_u+y_v,z_u+z_v)+(x_w,y_w,z_w)\\
      				&=((x_u,y_u,z_u)+(x_v,y_v,z_v))+(x_w,y_w,z_w)\\
      				&=(u+v)+w
      \end{aligned}
      $$

   4. Let $0_v=(0,0,0)$
      $$
      0_v+v=(0,0,0)+(x_v,y_v,z_v)=(0+x_v,0+y_v,0+z_v)=(x_v,y_v,z_v)=v\\
      \text{By 2.2) }0_v+v=v+0_v=v
      $$

   5. Let $-v=(-x_v,-y_v,-z_v)$
      $$
      v+(-v)=(x_v,y_v,z_v)+(-x_v,-y_v,-z_v)=(x_v-x_v,y_v-y_v,z_v-z_v)=(0,0,0)=0_v\\
      \text{By 2.2) }v+(-v)=(-v)+v=0_v
      $$

   6. Let $k,m$ be real scalars.
      $$
      kv=k(x_v,y_v,z_v)=(kx_v,ky_v,kz_v)\\
      kx_v+ky_v+kz_v=k(x_v+y_v+z_v)=k0=0\\
      \text{Thus, }kv\in V
      $$

   7. $$
      \begin{aligned}
      k(u+v)	&=k(x_u+x_v,y_u+y_v,z_u+z_v)\\
      				&=(kx_u+kx_v,ky_u+xy_v,kz_u,kz_v)\\
      				&=(kx_u,ky_u,kz_u)+(kx_v,ky_v,kz_v)\\
      				&=ku+kv
      \end{aligned}
      $$

   8. $$
      \begin{aligned}
      (k+m)v	&=(k+m)(x_v,y_v,z_v)\\
      				&=((k+m)x_v,(k+m)y_v,(k+m)z_v)\\
      				&=(kx_v+mx_v,ky_v+my_v,kz_v+mz_v)\\
      				&=k(x_v,y_v,z_v)+m(x_v,y_v,z_v)\\
      				&=ku+mu
      \end{aligned}
      $$

   9. $$
      \begin{aligned}
      k(mv)	&=k(mx_v,my_v,mz_v)\\
      			&=(kmx_v,kmy_v,kmz_v)\\
      			&=((km)x_v,(km)y_v,(km)z_v)\\
      			&=(km)u
      \end{aligned}
      $$

   10. $$
       1u=1(x_v,y_v,z_v)=(1x_v,1y_v,1z_v)=(x_v,y_v,z_v)=u
       $$
   Therefore, $V$ is a vector space.

3.  Let $V$ be the set of all ordered pairs of real numbers, and consider the following addition and scalar multiplication operations on $u=(u_1,u_2)$ and $v = (v_1,v_2)$:
   $$
   u+v=(u_1+v_1-1,u_2+v_2-1), ku=(ku_1,ku_2)
   $$
   ​	a. Find $\vec{0}$
   $$
   \begin{aligned}
   u												&=\vec{0}+u\\
   (u_1,u_2)								&=(\vec{0}_1+u_1-1,\vec{0}_2+u_2-1)\\
   \text{Thus, }\vec{0}		&=(1,1)
   \end{aligned}
   $$
   ​	b. Show that the Axioms 4 holds by producing an ordered pair $-u$ such that $u+(-u)=\vec{0}$ for $u = (u_1,u_2)$.
   $$
   \text{Let }{-u}=(-u_1+2,-u_2+2)\\
   u+(-u)=(u_1-u_1+2-1,u_1-u_2+2-1)=(1,1)=\vec{0}
   $$
   ​	c. Let $k$ and $m$ be real scalars.
   $$
   k(u+v)=k(u_1+v_1-1,u_2+v_2-1)=(ku_1+kv_1-k,ku_2+kv_2-k)\\
   ku+kv=(ku_1,ku_2)+(kv_1,kv_2)=(ku_1+kv_1-1,ku_2+kv_2-1)\\
   k(u+v)\ne ku+kv
   $$

   ------

   $$
   (k+m)u=((k+m)u_1,(k+m)u_2)=(ku_1+mu_1,ku_2+mu_2)\\
   ku+mu=(ku_1,ku_2)+(mu_1.mu_2)=(ku_1+mu_1-1,ku_2+mu_2-1)\\
   (k+m)u\ne ku+mu
$$
   
4. Let $V$ be the set of all points $(x,y)$, where $x,y>0$ such that $x+y=1$, and consider the following addition and scalar multiplication operations on $(x_1,y_1)$ and $(x_2,y_2)$:
   $$
   (x_1,y_1)+(x_2,y_2)=\left(\frac{x_1x_2}{x_1x_2+y_1y_2},\frac{y_1y_2}{x_1x_2+y_1y_2}\right),k(x_1,y_1)=\left(\frac{x_1^k}{x_1^k+y_1^k},\frac{y_1^k}{x_1^k+y_1^k}\right)
   $$
   ​	a. Show that $\vec{0}=\left(\frac{1}{2},\frac{1}{2}\right)$
   $$
   \begin{aligned}
   (x_1,y_1)+\vec{0}	&=\left(\frac{x_10.5}{x_10.5+y_10.5},\frac{y_10.5}{x_10.5+y_10.5}\right)\\
   									&=\left(\frac{x_10.5}{0.5},\frac{y_10.5}{0.5}\right)		&\text{Uses }x+y=1\\
   									&=(x_1,y_1)
   \end{aligned}
   $$
   ​	b. Find the inverse of $(x_1,y_1)$

   ​		Let $(x_i,y_i)$ be the inverse of $(x_1,y_1)$
   $$
   (x_1,y_1+(x_i,y_i)=\left(\frac{x_1x_i}{x_1x_i+y_1y_i},\frac{y_1y_i}{x_1x_i+y_1y_i}\right)=\left(\frac{1}{2},\frac{1}{2}\right)
   $$
   ​		So, $x_1x_i=1$ and $y_1y_i=1$

   ​		Hence, $(x_i,y_i)=\left(\frac{1}{x_1},\frac{1}{y_1}\right)$

   ​	c. Is $V$ a vector space? Prove or disprove it.

   ​		No, $V$ fails Associative Property for Vector Addition:

   <img src="Introduction to Linear Algebra - Real Vector Spaces Exercise.assets/a1.png" style="zoom: 33%;" />

5. Show that the zero vector in any vector spaces is unique.

   Suppose there are two zero vectors: $\vec{0}$ and $\overrightarrow{MyNewZeroVectorLol}$.

   From $\vec{0}+u=u$:
   $$
   \vec{0}+\overrightarrow{MyNewZeroVectorLol}=\overrightarrow{MyNewZeroVectorLol}
   $$
   But since $\overrightarrow{MyNewZeroVectorLol}$ is also zero vector:
   $$
   \overrightarrow{MyNewZeroVectorLol}+\vec{0}=\vec{0}
   $$
   From $u+v=v+u$:
   $$
   \vec{0}+\overrightarrow{MyNewZeroVectorLol}=\overrightarrow{MyNewZeroVectorLol}+\vec{0}=\overrightarrow{MyNewZeroVectorLol}=\vec{0}
   $$
   Thus $\overrightarrow{MyNewZeroVectorLol}=\vec{0}$, and therefore there can only be one zero vector.

   