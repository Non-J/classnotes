# Electromagnetic Waves Worksheet 2

**Jirawut Thongraar**

1. It is speculated that isolated magnetic “charges” (magnetic monopoles) may exist somewhere in the universe. Which of Maxwell’s equations, (1) Gauss’s Law for Electric Fields, (2) Gauss’s Law for Magnetic Fields, (3) Faraday’s Law of Induction, and/or (4) the Maxwell-Ampere Law, would be altered by the existence of magnetic monopoles?

   only (2)

2. Maxwell’s equations predict that there are no magnetic monopoles. If these monopoles existed, how would the motion of charged particles change as they approached such a monopole?

   It would orbit around the source of the magnetic monopole.

3. Do all current-carrying conductors emit electromagnetic wave?, Explain.

   Electromagnetic waves propagate due to Faraday’s Law of Induction and Maxwell-Ampere Law being time-dependent of one another. Suppose a current-carrying conductors are not time-dependent (i.e., they are static), then no electromagnetic waves can be produced as the time-dependent part will be zero.

4. Why electromagnetic wave is a transverse wave? Is it possible to have longitudinal electromagnetic wave?

   Supposed we solved the wave equation for electromagnetic wave as $E=f(kx+\omega t)$ where $f$ is some twice-differentiable function.

   From the assumption that $\nabla\cdot\vec{E}=0$, since $E$ is not dependent on y or z, $\frac{\partial{E_x}}{\partial{x}}=0$. This means that the component of electric field is static in the direction of travel, so the electric field wave cannot be longitudinal. And since magnetic field wave is perpendicular to the direction of travel and electric field wave, it too is not longitudinal. 
   
5. During normal beating, the heart creates a maximum $4.00\ \text{mV}$ potential across $0.300\ \text{m}$ of a person’s chest, creating a $1.00\ \text{Hz}$ electromagnetic wave. (a) What is the maximum electric field strength created? (b) What is the corresponding maximum magnetic field strength in the electromagnetic wave? (c) What is the wavelength of the electromagnetic wave? 
   $$
   E_0=\frac{v}{d}=\frac{4\ \text{mV}}{0.3\ \text{m}}=13.3333\ \text{mV/m}\\
   B_0=\frac{1}{c}E_0=4.44752\times10^{-11}\ \text{T}\\
   \lambda=\frac{c}{f}=299792458\ \text{m}
   $$

6. Consider each of the following electric and magnetic-field orientations. In each case, what is the direction of propagation of the wave?
   (A) $\vec{E}=E\hat{e}_i,\vec{B}=−B\hat{e}_j$ Direction: $-\hat{e}_k$
   (B) $\vec{E}=E\hat{e}_j,\vec{B}=B\hat{e}_i$ Direction: $-\hat{e}_k$
   (C) $\vec{E}=-E\hat{e}_k,\vec{B}=−B\hat{e}_i$ Direction: $\hat{e}_j$
   (D) $\vec{E}=E\hat{e}_i,\vec{B}=−B\hat{e}_k$ Direction: $\hat{e}_k$

7. An electromagnetic wave is propagating, due east. 

   Therefore, either *the $\vec{E}$ field may point north-south, the $\vec{B}$ up-down only* or *the $\vec{E}$ field may point up-down, the $\vec{B}$ north-south only* can give a wave propagating due east.

8. What is the phase difference between the sinusoidal oscillations of the electric fields $\vec{E}$ and magnetic fields $\vec{B}$ in Figure 1?

   <img src="Electromagnetic Waves Worksheet 2.assets/WS-2-2020-VecCal MaxwellEqns-Adv-1.jpg" style="zoom: 33%;" />
   $$
   0^\circ
   $$

9. An electromagnetic wave propagates in the negative y direction. The electric field at a point in space is momentarily oriented in the positive x direction. In which direction is the magnetic field at that point momentarily oriented?

   The positive z direction

10. An electromagnetic wave with a peak magnetic field magnitude of $1.50\times10^{−7}\ \text{T}$ has an associated peak electric field of what magnitude?
    $$
    E_0=c\cdot B_0=44.9689\ \text{V/m}
    $$

11. A plane electromagnetic wave of frequency $20\ \text{GHz}$ moves in the positive y-axis direction such that its electric field is pointed along the z-axis. The amplitude of the electric field is $10\ \text{V/m}$. The start of time is chosen so that at $t=0 $, the electric field has a value $10\ \text{V/m}$ at the origin. (A) Write the wave function that will describe the electric field wave. (B) Find the wave function that will describe the associated magnetic field wave.

    Assuming $\sin$ wave.
    $$
    \vec{E}=(10\ \text{V/m})\sin(\frac{2\pi (20\ \text{GHz})}{c}y-2\pi (20\ \text{GHz})t)\hat{z}\\
    \vec{B}=(\frac{10\ \text{V/m}}{c})\sin(\frac{2\pi (20\ \text{GHz})}{c}y-2\pi (20\ \text{GHz})t)\hat{x}
    $$

12. An electromagnetic wave of wavelength $435\ \text{nm}$ is travelling in vacuum in the −z direction. The electric field has amplitude $2.7\times10^{−3}\ \text{V/m}$ and is parallel to the x-axis. What are (A) the frequency and (B) the magnetic-field amplitude? (C) Write the vector equations for $\vec{E}(z,t)$ and $\vec{B}(z,t)$.
    $$
    f=\frac{c}{\lambda}=6.89178\times10^{14}\ \text{Hz}\\
    B_0=\frac{E_0}{c}=9.00623\times10^{-12}\ \text{T}\\
    \vec{E}(z,t)=E_0\sin(\frac{2\pi}{\lambda}z+2\pi ft)\hat{x}\\
    \vec{B}(z,t)=-B_0\sin(\frac{2\pi}{\lambda}z+2\pi ft)\hat{y}
    $$

13. The electric field of an electromagnetic wave traveling in vacuum is described by the following wave function: 
    $$
    \vec{E}=(5\ \text{V/m})\cos(kx-(6.0\times10^9\text{s}^{-1})t+0.4)\hat{j}
    $$
    where $k$ is a wave number in $\text{rad/m}$, $x$ is in $\text{m}$, $t$ is in second. Find the following quantities: (A) amplitude of electric wave and magnetic wave (B) frequency (C) wave length (D) the direction of the travel of the wave and the associated magnetic field wave.
$$
E_0=5\ \text{V/m}\\
    B_0=1.66782\times10^{-8}\ \text{T}\\
    f=9.54930\times10^8\ \text{Hz}\\
    \lambda=3.13942\times10^{-1}\ \text{m}
$$
​		The wave travels in positive x direction, the magnetic field oscillates in the z axis.

14. The magnetic field of a plane electromagnetic wave propagating along the z axis is given by $\vec{B} = B_0\cos(kz−\omega t)\hat{j}$, where $B_0=5.0\times10^{−10}\ \text{T}$ and $k=3.14\times10^{−2}\ \text{m}^{−1}$. (A) Write an expression for the electric field associated with the wave. (B) What are the frequency and wavelength of the wave.
    $$
    \vec{E}=cB_0\cos(kz-\omega t)\hat{i}\\
    f=1.49820\times10^6\ \text{Hz}\\
    \lambda=2.00101\times10^2\ \text{m}
    $$

15. Consider the two oppositely traveling electric-field waves, $\vec{E}_1=\hat{x}E_0\cos(kz-\omega t)$, and $\vec{E}_2=\hat{x}E_0\cos(kz+\omega t)$. The sum of these two waves is the standing wave, $2\hat{x}E_0\cos(kz)\cos(\omega t)$. (A) Find the magnetic field associated with this electric standing wave by finding $\vec{B}$ fields associated with each of above traveling $E$ fields and then adding them. (B) Find the magnetic field by using Maxwell’s equations to find $\vec{B}$ field associated with electric wave $2\hat{x}E_0\cos(kz)\cos(\omega t)$.

    (A)
    $$
    \vec{B}_1=\hat{y}\frac{E_0}{c}\cos(kz-\omega t)\\
    \vec{B}_2=\hat{y}\frac{E_0}{c}\cos(kz+\omega t)\\
    \vec{B}_1+\vec{B}_2=2\hat{y}\frac{E_0}{c}\cos(kz)\cos(\omega t)
    $$
    (B)

    With the free space assumption, the Ampere-Maxwell Equation is 
    $$
    \nabla\times\vec{B}=\mu_0\varepsilon_0\frac{d\vec{E}}{dt}=-2\mu_0\varepsilon_0\hat{x}E_0\cos(kz)\omega\sin(\omega t)
    $$
    Notice that in the expanded $\nabla\times\vec{B}$, most of the terms are zero. So the simplified result is
    $$
    -\frac{\partial{B_y}}{\partial{z}}\hat{x}+\frac{\partial{B_y}}{\partial{x}}\hat{z}=-2\mu_0\varepsilon_0\hat{x}E_0\cos(kz)\omega\sin(\omega t)
    $$
    Which yields the following relations
    $$
    \frac{\partial{B_y}}{\partial{z}}=2\mu_0\varepsilon_0E_0\cos(kz)\omega\sin(\omega t)\\
    \frac{\partial{B_y}}{\partial{x}}=0
    $$
    By solving the first one, we can get the following
    $$
    B_y=2\mu_0\varepsilon_0\frac{\omega}{k}E_0\sin(kz)\sin(\omega t)+(const)\\
    B_y=2\frac{E_0}{c}\sin(kz)\sin(\omega t)+(const)
    $$

16. It is known that the electric field intensity of a spherical wave in free space is 
    $$
    \vec{E}(R,\theta,t)=\frac{10^{-3}}{R}\sin\theta\cos(2\pi10^9t-kR)\hat{e}_\theta
    $$

    unit in $\text{V/m}$. Determine the magnetic field $\vec{B}(R,\theta,t)$

    Start with Ampere-Maxwell Equation with free space assumption
    $$
    \nabla\times\vec{B}=\mu_0\varepsilon_0\frac{d\vec{E}}{dt}=\mu_0\varepsilon_0\frac{2\pi10^6}{r}\sin\theta\sin(2\pi10^9t-kr)\hat{\theta}
    $$
    $\nabla\times\vec{B}$ in spherical coordinate is
    $$
    \nabla\times\vec{B}=\frac{1}{r\sin\theta}(\frac{\partial}{\partial{\theta}}(B_\varphi\sin\theta)-\frac{\partial{B_\theta}}{\partial\varphi})\hat{r}+\frac{1}{r}(\frac{1}{\sin\theta}\frac{\partial{B_r}}{\partial\varphi}-\frac{\partial}{\partial{r}}(rB_\varphi))\hat{\theta}+\frac{1}{r}(\frac{\partial}{\partial{r}}(rB_\theta)-\frac{\partial{B_r}}{\partial{\theta}})\hat{\varphi}
    $$
    Consider the $\hat{\theta}$ axis
    $$
    \frac{1}{r}(\frac{1}{\sin\theta}\frac{\partial{B_r}}{\partial\varphi}-\frac{\partial}{\partial{r}}(rB_\varphi))=\mu_0\varepsilon_0\frac{2\pi10^6}{r}\sin\theta\sin(2\pi10^9t-kr)
    $$

    Since the wave travels in $\hat{r}$, $B_r=0$
    $$
    -\frac{\partial{(rB_\varphi)}}{\partial{r}}=2\times10^6\mu_0\varepsilon_0\pi\sin\theta\sin(2\pi10^9t-kr)\\
    B_\varphi=2\times10^6\mu_0\varepsilon_0\pi\frac{k(const)-\cos(kr)\cos(2\pi ft)\sin(\theta)-\sin(kr)\sin(2\pi ft)\sin(\theta)}{kr}
    $$
    

