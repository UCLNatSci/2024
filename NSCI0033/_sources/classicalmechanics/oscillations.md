# Oscillations

<img src="Figs/PicOscillations.jpg" width="500">

*Image Credit: Team Leverage EDU*

In this unit, we will study systems whose motion displays characteristics which repeat in time - that is, they are <mark>periodic</mark>. We will also examine the physical processes through which periodic dynamics can arise.

## Simple Harmonic Motion

<div id="sec:shmo"></div>

### Harmonic Oscillator
We start by considering the simple system of a mass $m$ which is attached to one end of a horizontal spring, whose other end is fixed to a wall - see {numref}`fig:shmplot`. The equilibrium position of the mass is that position where the force on it is zero, which also corresponds to the position of minimum potential energy of the system, as we shall see.


```{figure} Figs/shmplot.png
---
name: fig:shmplot
---
A horizontal spring carrying a mass $m$, stretched in the $x$ direction, experiences a restoring force as shown. In general, the restoring force points towards the equilibrium position $x=0$ where there is zero force on the mass.
```

For simplicity, we use a single coordinate $x$ to describe the position of the mass, and take $x=0$ for its equilibrium position. For positive displacements $x>0$ the spring is stretched, and so will exert a negative restoring force on the mass which attempts to move it back towards equilibrium. Similarly, a compressed spring ($x<0$) exerts a positive restoring force. If this restoring force can be written as $F = -kx$, where $k$ is a positive constant, then the equation of horizontal motion becomes:
```{math}
:label: eq:shm
m\,\ddot{x} = -kx \rightarrow \ddot{x} = -kx/m.
```

One possible solution of this equation is:
```{math}
:label: eq:shmxsoln
x = A\,\sin(\omega_0\,t + \phi_0),
```
where $A$ and $\phi_0$ are constants, and the constant $\omega_0$ is known as the <mark>angular frequency</mark>.
In order to satisfy {eq}`eq:shm`, we require <mark>$\omega_0=\sqrt{k/m}$</mark>. Sometimes we use the term "frequency" to refer to the reciprocal of the oscillation period, $f_0=1/T_0$ (we can think of $f_0$ as representing the number of cycles of oscillation per unit time).

The displacement of the mass at time zero is $x_0 = A\,\sin\phi_0$. The motion repeats itself after the argument of the sine function increases by $2\pi$; that is, the period of the motion $T_0$ satisfies $\omega_0\,(t+T_0) = \omega_0\,t + 2\pi$. Hence $T_0 = 2\pi/\omega_0$ and so the period of the motion depends on the constant $k$, which describes the "stiffness" of the spring, and the mass $m$. The amplitude of the motion $A$ describes the fact that the motion is <mark>bounded</mark>, i.e., $x$ varies between values of $-A$ and $A$.  {numref}`fig:xvsomtplot` illustrates the behaviour of $x$ as a function of $\omega_0\,t$, emphasising the periodic property of the motion.

```{figure} Figs/xvsomtplot.png
---
name: fig:xvsomtplot
---
Position versus $\omega_0 t$ for the simple harmonic oscillator (from the book by Fowles and Cassiday).
```

We also note that the maximum value of the displacement $x_m$ occurs at times $t_m$ when the argument of the sine function is $\pi/2 + 2n\pi$, for any integer $n$. Thus $\omega_0\,t_m = (\pi/2 - \phi_0) + 2n\pi$.

In general, if we specify the values at time zero of displacement, $x_0$, and velocity, $v_0$, we must have:
```{math}
:label: eq:shmconstr
x_0 = A\,\sin\phi_0, \quad v_0 = \dot{x}(0) = \omega_0\,A\,\cos\phi_0,
```
from which we obtain $\tan\phi_0 = \omega_0 x_0 / v_0$. Note that if the mass is released from rest at time zero ($v_0 = 0$) from some non-zero positive displacement $x_0$, then $\phi_0 = \pi/2$ and so $x_0$ will be the maximum positive displacement, which will re-occur during the motion with the period $T_0$.

Note that the equations in {eq}`eq:shmconstr` can also be used to show that the amplitude of the motion must satisfy $A^2 = x_0^2 + v_0^2/\omega_0^2$.

### Simple Harmonic Motion: Rotating Vector Representation

Consider {numref}`fig:rotvecplot`, which shows the rotating position vector $\mathbf{A}$ of a point P which executes circular motion with a uniform speed. The angle made by this vector with the $x$ axis is $\theta = \theta_0 + \omega_0\,t$. The $x$ coordinate of P, for the given geometry, will therefore be $x=A\,\cos(\omega_0\,t+\theta_0)$. 

We could also use the angle $\phi = \phi_0+\omega_0\,t$ made with the $y$ axis to describe this motion, and note that $x = A\sin\phi = A\,\sin(\omega_0\,t+\phi_0)$. Whichever choice we make, we observe that the value of $x$ (the projection of the vector onto the $x$ axis) oscillates according to simple harmonic motion as the rotation of P proceeds. This suggests that a linear combination of sine and cosine functions could be used to represent the general solution for simple harmonic motion.

```{figure} Figs/rotvecplot.png
---
name: fig:rotvecplot
---
Simple harmonic motion as a projection of uniform circular motion (from the book by Fowles and Cassiday).
```

### Harmonic Oscillator with Constant External Force

In the last section, we considered harmonic motion in the horizontal direction, where the only force on the moving mass was that due to the spring being stretched or compressed. The character of the motion changes in interesting ways if we add an external force to the system. As a simple example, we consider (see {numref}`fig:shmvert`) a mass on a mounted spring which can only move in the *vertical* direction, and we include the effects of the vertical downward acceleration, $g$, due to gravity.

We obtain the following equation of motion by adding a gravitational term to an equation similar to the "spring equation" from the last section. We also use here a non-zero quantity $X_e$ to represent the unperturbed length of the spring. We take the convention of the mass position $X$ being positive downwards for this example:
```{math}
m\,\ddot{X} = -k\,(X-X_e) + mg.
```

```{figure} Figs/shmvert.png
---
name: fig:shmvert
---
Vertical case for the harmonic oscillator (from the book by Fowles and Cassiday).
```


We note that the new equilibrium position of the mass, where there is zero total force on it, is the value of $x$ for which the right side of the above equation is zero. This value is $X_e' = mg/k + X_e$. It is convenient to rewrite the equation of motion now in terms of the displacement relative to the equilibrium location, $x = X-X_e'$:

```{math}
m\,\dfrac{\mathrm{d}}{\mathrm{d}t^2}(X-X_e') = -k\,(X-X_e) + mg \rightarrow m\,\ddot{x} = -k\,(X-X_e') -k\,(X_e'-X_e) + mg \rightarrow m\,\ddot{x} = -k\,x.
```

This is an important result. Any constant external force does not change harmonic motion, <mark>provided we measure displacement from the shifted equilibrium position</mark> which is introduced by that force.

<div id="sec:pendulum"></div>

#### Simple Pendulum
The simple pendulum consists of a plumb bob of mass $m$ attached to the end of a light string of fixed length $l$, whose other end is mounted at a fixed point (see {numref}`fig:pendulum`). The position can be described by the angle $\theta$ or equivalently the arc length $s = l\,\theta$. The component of the gravitational force on the bob along its direction of motion is $F = -m\,g\,\sin\theta$ (with $g>0$). Even though the bob moves in a curved path, its equation of motion is one-dimensional:

```{math}
m\,\ddot{s} = -m\,g\,\sin\theta.
```

We can now make the assumption that the amplitude of the swinging bob is small, such that $\sin\theta\approx\theta$. Hence:

```{math}
m\,l\,\ddot{\theta} = -m\,g\,\theta \rightarrow \ddot{\theta} = -\dfrac{g}{l}\,\theta
```

This now has the same form as the harmonic motion equations we have encountered previously. Provided the small-amplitude approximation is valid, the pendulum motion is periodic, with angular frequency $\omega_0=\sqrt{g/l}$ and period $T_0 = 2\pi\,\sqrt{l/g}$. Using these expressions, we find, for example, that a small-amplitude pendulum moving at sea level, at latitude $45^{\circ}$, where $g=9.8062\,\mathrm{m\cdot s^{-2}}$, will have a period of $2\,\mathrm{s}$ if it is of length $0.9936\,\mathrm{m}$.

```{figure} Figs/pendulum.png
---
name: fig:pendulum
---
The simple pendulum (from the book by Fowles and Cassiday).
```

#### Simple Harmonic Motion: Energy
If we recall the form of restoring force for the simple harmonic oscillator from the section on [SHM](#sec:shmo), $F=-k\,x$, where $x$ is the displacement from equilibrium of the oscillating mass, we observe that this same force can be expressed as $F=-\dfrac{\mathrm{d}V}{\mathrm{d}x}$, where the function <mark>$V=\frac{1}{2}kx^2$</mark> can be identified as the <mark>potential energy</mark> of the system. If, for example, we apply an external force $F_{ext}$ to the mass, equal and opposite to the force exerted by the spring, we could move it from equilibrium $x=0$ to some final displacement $x=x_f$. The work we need to do in order to achieve this is
```{math}
W = \int_{x=0}^{x_f} kx\,\mathrm{d}x = \frac{1}{2} k x_f^2.
```
Hence, the physical meaning of the potential energy is the work which needs to be done in order to compress or expand the spring by a certain amount. In a sense, it represents energy "stored" in the spring.

As well as being able to calculate the potential energy $V$ of the system, we can also determine the kinetic energy of the oscillating mass according to $K = \frac{1}{2} m \dot{x}^2$. The total energy is therefore:
```{math}
:label: eq:shmE
E = K + V = \frac{1}{2}kx^2 + \frac{1}{2} m \dot{x}^2.
```
If there are no losses in energy during motion (due to e.g., heating, friction) then $E$ is a constant of the motion, and we can rearrange to solve for $\dot{x}$:
```{math}
\dot{x} = \pm\sqrt{\frac{1}{m}\,(2E - kx^2)}.
```
The different choice of sign indicates that the mass will have the same magnitude of velocity at those two points during the motion when it is at equal but opposite displacements with respect to the equilibrium point $x=0$. We can now integrate the above equation to find:
```{math}
\int \dfrac{\mathrm{d}x}{\pm\sqrt{\frac{1}{m}\,(2E - kx^2)}} = t \rightarrow  \mp \sqrt{m/k} \, \cos^{-1}(x/A) + C = t.
```
Here, $C$ is a constant of integration and $A = \sqrt{2E/k}$.

We also note from equation \ref{eq:shmE} that, at times when $\dot{x}=0$ and the mass is changing direction, it must be at the extreme points of its displacement. We see from this equation that $x=\pm\sqrt{2E/k}$ when $\dot{x}=0$, and thus $A$ can be identified as the <mark>amplitude</mark> of the motion.

{eq}`eq:shmE` also shows us that the maximum speed of the mass occurs when $x=0$ and is given by $|\dot{x}|_{max} = \sqrt{2E/m} =\sqrt{k/m}\,A$. The total energy is conserved during the motion, but is continually converted between kinetic and potential energy. All of the energy is kinetic when $x=0,\dot{x} = \pm\sqrt{k/m}\,A$ and all potential when $x=\pm A, \dot{x}=0$.

We can apply these same energy-related concepts to the case of the simple pendulum from the section [before](#sec:pendulum). In this case, the potential energy of the pendulum bob can be written as $V = mgh$, where $h$ is its vertical displacement with respect to some reference level of zero potential, which we can conveniently choose to be the equilibrium point corresponding to $s = \theta = 0$.

We see from the geometry of {numref}`fig:pendulum` that $h=l - l\,\cos\theta$. For small $\theta$, a second-order accurate form for the function $\cos\theta$ is $1-\frac{1}{2}\,\theta^2$. The corresponding approximate potential energy is $V(\theta) = \frac{1}{2}\,mgl\,\theta^2$, or $V(s) = \frac{1}{2}\,mg\,s^2/l$. Total energy can thus be written as:
```{math}
E = \dfrac{1}{2}\,m \dot{s}^2 +\dfrac{1}{2}\,\dfrac{mg}{l}\,s^2.
```

## Damped Harmonic Motion
In this section, we explore solutions for the motion of a mass moving on the end of a spring, with the inclusion of a viscous retarding force, which is a linear function of velocity. We can write this as $ F_v = -c \dot{x} $, where $ c $ is a positive constant, and $ x $ again denotes displacement from the equilibrium position. The modified equation of motion is:
```{math}
    \ddot{x} + \frac{c}{m} \dot{x} + \frac{k}{m} x = 0.
```
This is a second-order, linear differential equation with constant coefficients. Its general solution is of the form:
```{math}
x(t) = A_1 \exp(\lambda_1 t) + A_2 \exp(\lambda_2 t).
```
Here, the $ A_i $ are constants, and the $ \lambda_i $ are the two roots of the quadratic equation which corresponds to the form of the differential equation itself:
```{math}
    \lambda^2 + \frac{c}{m} \lambda + \frac{k}{m} = 0.
```
Hence, we can define:
```{math}
\lambda_1 = \lambda_+ = \frac{-c/m + \sqrt{c^2/m^2 - 4k/m}}{2}
= -\gamma + \sqrt{\gamma^2 - \omega_0^2},
```
```{math}
\lambda_2 = \lambda_- = \frac{-c/m - \sqrt{c^2/m^2 - 4k/m}}{2}
= -\gamma - \sqrt{\gamma^2 - \omega_0^2},
```
where $ \gamma = c / (2m) $ and $ \omega_0 = \sqrt{k/m} $ is the angular frequency of the simple harmonic case without the retarding force.

The physical description of the motion falls into three cases, according to the value of the parameter $ q = \sqrt{\gamma^2 - \omega_0^2} $. We now consider these three cases, which are: <mark>overdamping</mark> ($ q $ real and positive); <mark>critical damping</mark> ($ q = 0 $); and <mark>underdamping</mark> ($ q $ imaginary).

#### Overdamping

For this case, both terms in the general solution become decaying exponential functions with decay time constants equal to 
$ \tau_1 = 1 / (\gamma - q) $ and $ \tau_2 = 1 / (\gamma + q) $. The coefficients $ A_i $ will depend on the initial conditions of the problem. In general, the mass, initially displaced and then released from rest, will gradually return to the equilibrium position but will not exhibit oscillation due to the strong damping force (see {numref}`fig:ovcritdamp`).

```{figure} Figs/ovcritdamp.png
---
name: fig:ovcritdamp
---
Displacement versus time for critically damped and overdamped oscillators, released from rest after an initial displacement (from the book by Fowles and Cassiday).
```

#### Critical Damping
In this case, the values of both $ \lambda_1 $ and $ \lambda_2 $ become equal to $ -\gamma $. So, to find two independent solutions, we return to the original differential equation and use $ \omega_0^2 = \gamma^2 $:
```{math}
\ddot{x} + 2 \gamma \dot{x} + \gamma^2 x = 0
```
```{math}
\frac{\mathrm{d}}{\mathrm{d}t}(\dot{x} + \gamma x) + \gamma\,(\dot{x} + \gamma x) = 0.
```
If we define the function $ u = (\dot{x} + \gamma x) $, we find that the solution for $ u $, according to this form of the equation, is $ u = A \exp(-\gamma t) $, where $ A $ is a constant. Hence:
```{math}
u = A \exp(-\gamma t) = \dot{x} + \gamma x
```
```{math}
\Rightarrow A = \exp(\gamma t)\,(\dot{x} + \gamma x) = \frac{\mathrm{d}}{\mathrm{d}t}(x\,\exp(\gamma t)).
```
```{math}
x\,\exp(\gamma t) = At + B \rightarrow x = At \exp(-\gamma t) + B \exp(-\gamma t).
```
Here, $ B $ is another constant of integration. The two distinct terms are a decaying exponential modulated by a function linear in time and a decaying exponential. Again, the motion is non-oscillatory and returns to equilibrium asymptotically (see {numref}`fig:ovcritdamp`).

#### Underdamping
Physically, the retarding force in this case is weak enough that it does not suppress oscillatory behavior entirely. Let us quantify this behavior by exploring the nature of the solution for $ x $ when $ q $ is 
imaginary.

Let us define $ q = i\omega_d $, where $ \omega_d = \sqrt{k/m - c^2 / (4m^2)} $ is positive and real, and, as we shall see, is associated with the oscillatory part of the solution. Note that $ \omega_d = \sqrt{\omega_0^2 - \gamma^2} $, which tells us that the frequency $ \omega_d $ of our damped oscillator is not the same as the frequency $ \omega_0 $ for undamped motion.

Let's now rewrite the general solution in terms of $ \gamma $ and $ \omega_d $:
```{math}
x(t) = C_+\,\exp(-(\gamma - i\omega_d)t) + C_-\,\exp(-(\gamma + i\omega_d)t).
```
```{math}
= \exp(-\gamma t)\,(C_+\,\exp(i\omega_d t) + C_-\,\exp(-i\omega_d t)).
```
To ensure $ x(t) $ is real-valued, we require that:
```{math}
C_+^* = C_- = C,
```
```{math}
C_-^* = C_+ = C^*,
```
```{math}
x(t) = \exp(-\gamma t)\,(C^*\,\exp(i\omega_d t) + C\,\exp(-i\omega_d\,t)).
```
Representing $ C $ as $ \frac{A}{2} \exp(-i\theta_0) $, where $ A $ and $ \theta_0 $ are real-valued, the solution becomes:
```{math}
x(t) = \exp(-\gamma t) \frac{A}{2}\,\left(e^{i(\omega_d t + \theta_0)} + e^{-i(\omega_d t + \theta_0)} \right),
```
or, using $ \cos\theta = \frac{1}{2} (e^{i\theta} + e^{-i\theta}) $:
```{math}
x(t) = \exp(-\gamma t) A \cos(\omega_d t + \theta_0).
```
We note that the presence of the real factor $ \exp(-\gamma t) $ produces an exponential decay of the oscillation amplitude with time. The underdamped oscillator has a frequency smaller than the undamped one.

## Phase Space Representations

A different representation of a single particle undergoing motion is to plot its trajectory as a series of points in a phase space, where both the particle's position and its velocity act as coordinates.

For example, a particle whose position can be represented with a single coordinate $x$ will have a trajectory in a plane in phase space consisting of all the points $(x(t), \dot{x}(t))$. We expect harmonic motion without energy dissipation to repeat its phase space trajectory with each cycle of oscillation. We do not have this same expectation for motion which is damped (i.e., where energy is being dissipated or lost, and the sum of kinetic plus potential energy is not conserved).

Let's commence by revisiting the solution $x(t) = A\,\sin(\omega_0\,t + \phi_0)$ for the position of the one-dimensional simple harmonic oscillator. The velocity $\dot{x}(t) = A\,\omega_0\,\cos(\omega_0\,t + \phi_0)$. Setting $y = \dot{x}(t)$, we find:

```{math}
\frac{x^2}{A^2} + \frac{y^2}{A^2\omega_0^2} = 1.
```

Hence, in the phase space $xy$ plane, the trajectory of the particle takes the geometrical form of an ellipse with semi-major axes of length $A$ along the $x$ axis (position coordinate) and $A\omega_0$ along the $y$ axis (velocity coordinate). During one cycle (i.e., a time $T = \frac{2\pi}{\omega_0}$), the phase space coordinates $(x, y)$ trace out the shape of this ellipse once. The initial values $(x(0), \dot{x}(0))$ uniquely determine the rest of the phase space trajectory. The mathematical form of the trajectory is equivalent to a statement that energy is conserved. Thus, two harmonic oscillators with distinct total energies will trace out two distinct elliptical trajectories, and those trajectories will not intersect at any point in phase space.

Let us now explore the phase-space trajectory of the weakly damped harmonic oscillator.

We remind ourselves that the solution for the position can be written:

```{math}
x(t) = e^{-\gamma t}\,A\,\sin(\omega_d\,t + \phi_0).
```

We can thus differentiate with respect to time to obtain velocity:

```{math}
\dot{x}(t) = -A\,e^{-\gamma t}\left[\gamma\,\sin(\omega_d\,t + \phi_0) - \omega_d\,\cos(\omega_d\,t + \phi_0)\right].
```

We can relate the constants $\gamma$, $\omega_d$, $\phi_0$ to the initial conditions as follows:

At $t = 0$:

```{math}
x(0) &= A\,\sin\phi_0, \\
\dot{x}(0) &= -A\left(\gamma\,\sin\phi_0 - \omega_d\,\cos\phi_0\right).
```

If the motion starts from rest and $\dot{x}(0) = 0$, then:

```{math}
\tan\phi_0 = \frac{\omega_d}{\gamma}.
```

We can rewrite the solutions in a form that is more easily interpreted as a geometric figure by defining functions $\rho = A\,e^{-\gamma t}$, $\theta = \omega_d\,t + \phi_0$, and $y = \dot{x} + \gamma\,x$:

```{math}
x(t) &= \rho\,\sin\theta, \\
y(t) &= \omega_d\,\rho\,\cos\theta.
```

Hence:

```{math}
\frac{x^2}{\rho^2} + \frac{y^2}{\omega_d^2\,\rho^2} = 1.
```

This is *not* the equation of an ellipse of a fixed size, since $\rho$ is not a constant in general, but a function of time. A plot of the shapes corresponding to this equation, for the cases $\gamma = 0.05\,\mathrm{s^{-1}}$ and $\gamma = 0.25\,\mathrm{s^{-1}}$, is shown in {numref}`fig:phasplots` (we use $\omega_0 = 0.5\,\mathrm{s^{-1}}$ in order to calculate $\omega_d = \sqrt{\omega_0^2 - \gamma^2}$, and start the motion from rest at $x = 1$).

We show the plotted trajectory in the usual phase space definition, with $\dot{x}$ plotted versus $x$; and also in the modified phase space, with $y = \dot{x} + \gamma x$ plotted versus $x$.

```{figure} Figs/pplot.png
---
name: fig:phasplots
---
Plotted trajectories in phase space for oscillators which are damped to different degrees, according to parameter $\gamma$.
```

We see from these plots that the general form of the phase space trajectory is that it moves towards the origin, performing a 'decaying spiral' pattern as it does so. The origin thus represents a stable equilibrium point, which physically corresponds to the long-term approach of the oscillator towards its steady state: stationarity at its equilibrium position.

For the critically damped oscillator, we have:

```{math}
x(t) = (A t + B)\,e^{-\gamma t}.
```

Hence:

```{math}
\dot{x}(t) + \gamma\,x(t) = A\,e^{-\gamma t}.
```

The last equation indicates that the trajectory in the usual phase space ($\dot{x}$ versus $x$) would approach a straight line with slope $-\gamma$ and intercept zero as $t \rightarrow \infty$.

We finish this section by considering the phase space trajectory of the overdamped oscillator. We recall that the general solution for this case takes the form:

```{math}
x(t) = A_1\,e^{-(\gamma - q)t} + A_2\,e^{-(\gamma + q)t},
```

where, by definition, $q < \gamma$ and, for the overdamped oscillator, $q$ is real and positive. We can differentiate to obtain the velocity:

```{math}
\dot{x}(t) = -(\gamma - q)\,A_1\,e^{-(\gamma - q)t} - (\gamma + q)\,A_2\,e^{-(\gamma + q)t}.
```

We note that:

```{math}
\dot{x}(t) + \gamma\,x(t) = q\left[A_1\,e^{-(\gamma - q)t} - A_2\,e^{-(\gamma + q)t}\right].
```

Hence, as $t \rightarrow \infty$, the phase space trajectory traced by $\dot{x}$ versus $x$ will approach a straight line of slope $\gamma$. Let's explore this a bit further.

We assume that the overdamped oscillator starts from rest at $x = x_0$. This implies that $A_1 + A_2 = x_0$ and $(\gamma - q)A_1 = -(\gamma + q)A_2$. To satisfy both initial conditions, we need to have:

```{math}
A_1 = \frac{(\gamma + q)\,x_0}{2q}, \quad A_2 = -\frac{(\gamma - q)\,x_0}{2q}.
```

With some algebra, we then find:

```{math}
\dot{x} + (\gamma - q)\,x &= (\gamma - q)\,x_0\,e^{-(\gamma + q)t}, \\
\dot{x} + (\gamma + q)\,x &= (\gamma + q)\,x_0\,e^{-(\gamma - q)t}.
```

Note that the first of these equations contains an exponential term which decays quite rapidly compared to that of the second equation. Thus we would expect that the behavior $\dot{x} \rightarrow -(\gamma - q)\,x$ emerges earlier, and that the phase space plot would start its approach towards the origin by approaching a line of slope $-(\gamma - q)$ relatively quickly. This is indeed the usual case for the overdamped oscillator.


## Forced Harmonic Motion and Resonance

In this section, we extend our study of harmonic motion to investigate the interesting dynamical effects of adding an external force to the oscillator problem. We will consider a periodic external force of a frequency which is generally different from the “natural” frequency of the oscillator (which we have studied in the preceding sections). We will determine how the nature of the motion is affected by how similar or different the frequencies of the driving force and the natural oscillation in the absence of this driving are.

We will start by considering the general problem of an oscillator subject to both <mark>damping</mark> and the <mark>driving</mark> influence of the external force. We will see that the general solution is a superposition of oscillations at different frequencies and that the amplitude of the oscillations depends on how close the natural and the driving frequencies are.

To make the mathematics more tractable, we will represent oscillating functions in time as complex-valued. For example, the complex function $ e^{i\omega t} $ implicitly represents a periodically varying physical quantity represented by its real part: $ \Re(e^{i\omega t}) = \cos(\omega t) $.

We now write the equation of motion:
```{math}
m\,\ddot{x} = -k\,x - c\,\dot{x} + F_0\,e^{i\omega t}.
```
The terms on the right-hand side are, respectively, the restoring force (e.g., from a spring), the damping term proportional to velocity, and the external force of amplitude $ F_0 $ and angular frequency $ \omega $. As before, we take $ \omega_0 = \sqrt{k/m} $ to be the natural frequency, which would arise in the absence of any damping or driving. Using this definition, we can rewrite the equation of motion as:
```{math}
\ddot{x} = -\omega_0^2\,x - 2\gamma\,\dot{x} + (F_0/m)\,e^{i\omega t},
```
where $ \gamma = c/(2m) $.

The general solution consists of two parts: the <mark>homogeneous</mark> solution (in the absence of a driving force) and a <mark>particular</mark> solution.

The homogeneous solution is of the form:
```{math}
x_h(t) = A_+ e^{\alpha_+ t} + A_- e^{\alpha_- t},
```
where the $ \alpha $ values are the roots of the corresponding quadratic equation $ \lambda^2 + 2\gamma\,\lambda + \omega_0^2 = 0 $, given by:
```{math}
\alpha_{\pm} = -\gamma \pm \sqrt{\gamma^2 - \omega_0^2}.
```

To find a particular solution, we try $ x_p(t) = A e^{i\omega t} $ and solve for $ A $:
```{math}
-A \omega^2 = -\omega_0^2 A - 2 \gamma i \omega A + F_0/m,
```
yielding
```{math}
A = \frac{F_0/m}{2 i \gamma \omega + \omega_0^2 - \omega^2}.
```
To ensure a real-valued amplitude, we can convert this complex number into polar form, where
```{math}
A e^{i \omega t} = A_{\mathrm{d}r} e^{i (\omega t - \phi_{\mathrm{d}r})}.
```
With algebra, we can show that $ A_{\mathrm{d}r} = \dfrac{F_0/m}{\sqrt{(\omega_0^2 - \omega^2)^2 + 4\gamma^2 \omega^2}} $ and
```{math}
\tan\phi_{\mathrm{d}r} = \frac{2\gamma\omega}{\omega_0^2 - \omega^2}.
```
Thus, the particular solution can be written as:
```{math}
x_p(t) = \frac{F_0/m}{\sqrt{(\omega_0^2 - \omega^2)^2 + 4\gamma^2 \omega^2}} e^{i(\omega t - \phi_{\mathrm{d}r})}.
```

The homogeneous solution decays as $ e^{-\gamma t} $. Physically, this means that for times $ t >> (1/\gamma) $, the homogeneous solution decays away, leaving the steady-state solution as:
```{math}
:label: eq:ddhoss
\mathrm{Re}(x_p(t)) = \frac{F_0/m}{\sqrt{(\omega_0^2 - \omega^2)^2 + 4\gamma^2 \omega^2}} \cos(\omega t - \phi_{\mathrm{d}r}).
```

This steady-state behavior has two important aspects: (1) the response of the oscillating mass lags the driving force by phase $ \phi_{\mathrm{d}r} $; and (2) the amplitude of the position depends on the driving frequency. This leads to the phenomenon of <mark>resonance</mark>, where the amplitude maximizes when the driving frequency is close to the natural frequency.

#### Amplitude of the Motion
{eq}`eq:ddhoss` reveals that the real-valued amplitude of the steady-state motion of the driven, damped oscillator is a function of the driving frequency and other parameters of the motion, as given by:
```{math}
:label: eq:ampfn
A_{\mathrm{d}r}(\omega) = \frac{F_0/m}{\sqrt{(\omega_0^2 - \omega^2)^2 + 4\gamma^2 \omega^2}}.
```
The maximum amplitude occurs at the <mark>resonant frequency</mark>:
```{math}
\omega_r = \sqrt{\omega_0^2 - 2 \gamma^2}.
```
As $ \gamma \rightarrow 0 $, $ \omega_r \rightarrow \omega_0 $.

For strong damping $ \gamma > \sqrt{2}\,\omega_0 $, there is no local maximum, and the amplitude decreases monotonically with the driving frequency $ \omega $.

We can obtain the maximum amplitude of the motion for the case where there is a real value of $\omega_r$ by substituting $\omega = \omega_r$ into {eq}`eq:ampfn`. The result is:
```{math}
A_{max} = \dfrac{F_0/m}{2\gamma \sqrt{\omega_0^2-\gamma^2}}.
```

For weak damping $ \gamma << \omega_0 $, the maximum amplitude approximates
```{math}
A_{max} \approx \frac{F_0}{2 \gamma m \omega_0}.
```
In practical applications, resonance may be avoided to prevent large oscillations. Damping can be implemented in systems, such as stiff rubber mountings in electric motors, to ensure that resonant frequency is far from the operating frequency.

#### "Sharpness" of the Resonance: Quality Factor

{numref}`fig:ampplot` shows a plot of the function $ A(\omega) $ from {eq}`eq:ampfn`. The “sharpness” of the peak in amplitude, which occurs at frequency $ \omega_{\mathrm{d}r} $, depends on the damping parameter $ \gamma $. We can quantify how “sharp” or broad this local maximum is.

```{figure} Figs/ampplot.png
---
name: fig:ampplot
---
A plot of the steady-state amplitude of the damped, driven oscillator as a function of the driving frequency. The legend indicates example values of $ \gamma / \omega_0 $ used. Note that the vertical axis is on a logarithmic scale, and both quantities are normalized according to the natural scales shown in the axis labels.
```

We focus on the band of frequencies close to $ \omega_0 $ (the natural frequency without damping or driving), i.e., frequencies $ \omega $ such that $ |\omega - \omega_0| / \omega_0 << 1 $. Writing $ \omega = \omega_0 (1 + \delta) $ with $ |\delta| << 1 $, we approximate the amplitude function to first order as:

```{math}
:label: eq:ampfnapprox
A_{\mathrm{d}r}(\omega) \approx \frac{F_0/m}{2 \omega_0 \sqrt{(\omega_0 - \omega)^2 + \gamma^2}}.
```

For $ \gamma << \omega_0 $, this is further approximated as:

```{math}
:label: eq:ampfnappro2x
A_{\mathrm{d}r}(\omega) \approx \frac{A_{max} \gamma}{\sqrt{(\omega_0 - \omega)^2 + \gamma^2}}.
```

Thus, at the two frequencies $ \omega = \omega_0 \pm \gamma $, the amplitude value is $ \frac{A_{max}}{\sqrt{2}} $. Since the total (potential plus kinetic) energy scales as the amplitude squared, these frequencies are the <mark>half-power points</mark> of the oscillator response. A practical measure of the “sharpness” of the resonance peak is the ratio $ Q = \omega_0 / (2 \gamma) $, the approximate frequency of maximum amplitude divided by the frequency interval between the half-power points. This value, $ Q $, is known as the <mark>quality factor</mark>. Another interpretation of $ Q $ is that $ 1 / Q \approx 2 \gamma / \omega_0 $, the fractional width of the resonance peak relative to the resonant frequency.

#### Phase Difference

Now, let's examine the phase difference between the damped, driven oscillator and the external driving force, which determines the steady-state response:

```{math}
\phi_{\mathrm{d}r}(\omega) = \arctan \left( \frac{2 \gamma \omega}{\omega_0^2 - \omega^2} \right).
```

```{figure} Figs/phiplot.png
---
name: fig:phiplot
---
A plot of the steady-state phase difference of the damped, driven oscillator as a function of the driving frequency. The legend indicates example values of $ \gamma / \omega_0 $ used. Both quantities are normalized according to the natural scales shown in the axis labels.
```

In {numref}`fig:phiplot`, the phase difference undergoes a $ \pi $ shift as the driving frequency crosses the resonant frequency, with a sharper change for smaller values of $ \gamma / \omega_0 $. When $ \omega << \omega_0 $, $ \phi_{\mathrm{d}r} \rightarrow 0 $, and the driving force and response are in phase, with the mass moving slowly under the external force.

At resonance, the response amplitude can be significant. The ratio of the maximum amplitude to the amplitude in the low-frequency limit is $ A_{max} / A(\omega \rightarrow 0) = \frac{\omega_0^2}{2 \gamma \sqrt{\omega_0^2 - \gamma^2}} $. For $ \gamma << \omega_0 $, this approaches the quality factor $ \omega_0 / (2 \gamma) $.

At $ \omega = \omega_0 $, $ \phi_{\mathrm{d}r} = \pi/2 $, meaning the oscillator lags a quarter cycle behind the driving force. For high frequencies $ \omega >> \omega_0 $, the phase difference reaches $ \pi $, and the amplitude decreases to $ F_0 / (m \omega^2) $. Here, the high-frequency driving force causes the mass to behave as if it is free, with the spring imposing an antiphase relation between the driving force and the oscillator's response.
