# Electromagnetic Waves Worksheet 2

**Jirawut Thongraar**

1. Why $\vec{E}$ and $\vec{B}$ of Electromagnetic wave are perpendicular each other? Give a brief explanation with supporting laws of electromagnetism.

   Suppose there is an electromagnetic whose electric field wave component oscillates in $\hat{x}$ axis. The Ampere-Maxwell’s equation is
   $$
   \nabla\times\vec{B}=\mu_0\varepsilon_0\frac{\partial{\vec{E}}}{\partial{t}}
   $$
   Since the only component of $\vec{E}$ that is time dependent is in the $\hat{x}$ axis, the above equation can be reformulated as follow
   $$
   \frac{\partial{B_z}}{\partial{y}}-\frac{\partial{B_y}}{\partial{z}}=\mu_0\varepsilon_0\frac{\partial{E_x}}{\partial{t}}
   $$
   Notice that the $B_x$ is zero, and how this procedure is not specific to the chosen axis ($\hat{x}$). Thus, $\vec{E}$ and $\vec{B}$ must be perpendicular.

2. If a high frequency current is passed through a solenoid containing a metallic core, the core becomes hot due to the induction. Explain why the material rises in temperature in this situation.

   By passing high frequency current through a solenoid, a fast-changing magnetic field is also generated inside the solenoid. This rapid changes of magnetic field induces current inside the metallic core which, when encountered with the resistance of metal, produces heat.

3. In the region of free space the electric ﬁeld at an instant of time is $\vec{E}=(80\hat{i}+32\hat{j}+64\hat{k})\ \text{N/C}$ and the magnetic ﬁeld $\vec{B}=(0.200\hat{i}+0.080\hat{j}+0.290\hat{k})\ \mu\text{T}$. Determine  the Poynting vector at the given instant time of these ﬁeld.
   $$
   \vec{S}=\frac{\vec{E}\times\vec{B}}{\mu_0}=(3.31042\hat{i}-8.27606\hat{j}+0\hat{k})\ \text{W}/\text{m}^2
   $$
   
4. The beam from a small laboratory laser typically has an intensity of about $1.0\times10^{−3}\ \text{W}/\text{m}^2$. Assuming that the beam is composed of plane waves, calculate the amplitudes of the electric and magnetic ﬁelds in the beam. 

$$
I=c\cdot\bar{u}_{em}=\frac{1}{2}c\varepsilon_0E_0^2=\frac{1}{2\mu_0}cB_0^2\\
E_0=8.68021\times10^{-1}\ \text{V/m}\\
B_0=2.89541\times10^{-9}\ \text{T}
$$

5. A 150-W lightbulb emits 5% of its energy as electromagnetic radiation. What is the magnitude of the average Poynting vector 10 m from the bulb?
   $$
   |\vec{S}|=\frac{P}{A}=\frac{0.05\cdot150\ \text{W}}{4\pi\cdot(10\ \text{m})^2}=5.96831\times10^{-3}\ \text{W}/\text{m}^2
   $$
   