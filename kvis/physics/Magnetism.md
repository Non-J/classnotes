# Magnetism

## Magnetic Field

Magnetic field is closed loop.
$$
\nabla\cdot\vec B =0\quad\text{or}\quad\oint\vec B\cdot d\vec A=0
$$
Magnetic field due to current-carrying wire can be computed using *Biot-Savart Law*.
$$
d\vec B=\frac{\mu_0}{4\pi}\frac{Id\vec l\times\hat r}{r^2}
$$
Using *Biot-Savart Law*, the magnetic field due to current-carrying loop or short piece of current-carrying wire can be derived.
$$
\begin{align*}
    B&=\frac{\mu_0I}{2}\frac{R^2}{(R^2+Z^2)^{3/2}}		&& \text{Magnetic field due to current-carrying loop}\\
    B&=\frac{\mu_0I}{4\pi}\frac{2a}{R\sqrt{R^2+a^2}}		&& \text{Magnetic field due to current-carrying wire}
\end{align*}
$$
Magnetic field can also be computed using *Ampère's Law* in the case where current is static.
$$
\oint\vec B\cdot d\vec l=\mu_0I
$$

#### Effect of Magnetic Field

Magnetic force on a charged particle or current-carrying wire.
$$
\vec F=q\vec v\times\vec B=I\vec l\times\vec B
$$
A closed loop of current-carrying wire is called *magnetic dipole*.
$$
\begin{align*}
    \vec\mu&=I\vec A					&& \text{Magnetic dipole moment}\\
    \vec\tau&=\vec\mu\times\vec B		&& \text{Torque on magnetic dipole}\\
    U&=\vec\mu\cdot\vec B				&& \text{Magnetic dipole potential}
\end{align*}
$$

## Induction

Magnetic flux is the amount of magnetic field passing through a surface.
$$
\Phi_B=\int\vec B\cdot d\vec A
$$
A change in magnetic flux induce a current in a loop in the opposite direction of the change.
$$
\varepsilon=-\frac{d\Phi_B}{dt}
$$
A rotation coil in uniform magnetic field can be used as an electric generator.
$$
\varepsilon=BA\omega\sin(\omega t)
$$

#### Inductor

An inductor is an electric device designed to store magnetic field, with its *inductance* being $L=\frac{N\Phi_B}{I}$.

Energy can be stored in this form of magnetic field.
$$
U_B=\frac{1}{2}LI^2
$$
An inductor or other electric device may induce a current in itself, which is referred to as *self-inductance.*
$$
\varepsilon=-L\frac{dI}{dt}
$$

#### RL Circuit

A constant EMF is applied to a circuit with resistance and inductance, which charges and discharges the inductor.
$$
\begin{align*}
	I&=\frac{\varepsilon}{R}(1-e^{-t/\tau_L})		&&\text{When EMF is applied}\\
	I&=I_0e^{-t/\tau_L}								&&\text{When EMF is removed}\\
	\tau_L&=L/R										&&\text{Inductive time constant}\\
\end{align*}
$$

## Alternating Current and Circuit

#### LC Circuit

A circuit in which energy oscillates between the inductor and capacitor.
$$
U=U_B+U_C=\frac{1}{2}LI^2+\frac{1}{2}\frac{q^2}{C}
$$
The energy transfer happens at a certain frequency.
$$
\omega=\frac{1}{\sqrt{LC}}
$$

#### RLC Circuit

A circuit in which energy oscillates between the inductor and capacitor, but the energy transfer is damped by the resistor. However, EMF can be introduced into the circuit to make up for the energy lost due to the resistor.
$$
L\frac{d^2q}{dt^2}+R\frac{dq}{dt}+\frac{q}{c}=0\\
\begin{align}
\varepsilon&=\varepsilon_0\sin(\omega_dt)\\
I&=I_0\sin(\omega_dt-\phi)
\end{align}
$$
where $\omega_d$ is the driving angular frequency which corresponds to the frequency of the EMF source.

###### Resistive Load

The resistive load acts to dissipate energy and prevent large build-up of current in the circuit.

With only resistive load, the phase constant $\phi=0$, and $V_R=I_RR$

###### Capacitive Load

The capacitive load acts similar to a spring in spring-mass system, and helps to bridge the current gap in AC circuit.

With capacity load, define *capacitive reactance* as $X_C=1/\omega_dC$, and we get $V_C=I_CX_C$.

The phase constant in this case is $\phi=-\pi/2$, i.e, the phase of current leads the phase of EMF.

###### Inductive Load

The inductive load acts similar to a mass in spring-mass system, and helps to slow down the rate of change of current in the circuit.

With inductive load, define *inductive reactance* as $X_L=\omega_dL$, and we get $V_L=I_LX_L$.

The phase constant in this case is $\phi=+\pi/2$, i.e, the phase of current lags the phase of EMF.

###### Combined Circuit

In a combined circuit, define *impedance* as $Z=\sqrt{R^2+(X_L-X_C)^2}$, and we get $\varepsilon_0=I_0Z$.

When $\omega_d=\omega_\text{natural frequency}$, the circuit *resonates*, achieving the maximum possible $I_0$, $X_C=X_L$, and $\phi=0$.

When $\omega_d<\omega_\text{natural frequency}$, the circuit is more capacitive, $X_C>X_L$, and $\phi<0$.

When $\omega_d>\omega_\text{natural frequency}$, the circuit is more inductive, $X_C<X_L$, and $\phi>0$.

#### Power Consumption

$$
\begin{align*}    P&=I^2R=I_0^2\sin(\omega t)^2R	&& \text{The equation for power}\\    \bar{P}&=\frac{I_0^2R}{2}		&& \text{Average of }\sin(\omega t)^2\ \text{is}\ \frac{1}{2}\\    \bar{P}&=I_{rms}^2R=I_{rms}V_{rms}\cos(\phi)			&& rms\ \text{is root-mean-square where}\ I_{rms}=I_0/2, V_{rms}=V_0/2\end{align*}
$$

#### Transformer

The proportion of the number of coil is equal to the proportion of voltage, but is inverse to the proportion of current.
$$
\frac{N_1}{N_2}=\frac{V_1}{V_2}=\frac{I_2}{I_1}
$$

## 