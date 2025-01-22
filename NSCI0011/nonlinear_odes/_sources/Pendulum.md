# Solving the Non-Linear Pendulum

```{figure} ./pendulum.png
---
name: Pendulum
---
Free force diagram of a hanging pendulum. Note that while the angle is labeled as $\alpha$ in this diagram, the derivation below assumes $\theta = \alpha$.
```




The non-linear pendulum equation is given by:

```{math}
\frac{\mathrm{d}^2\theta}{\mathrm{d}t^2} + \frac{g}{L} \sin\theta = 0,
```

where:
- $\theta(t)$: Angular displacement,
- $g$: Gravitational acceleration,
- $L$: Length of the pendulum.

Below, we explore three approaches to solving this equation: analytical, perturbative, and numerical.

---

## Analytical Methods

The non-linear pendulum equation cannot generally be solved in terms of elementary functions. However we can use different methods to understand how to characterise it's behaviour.


In the case of small oscillations, one can set $\sin \theta \approx \theta$. As a result, we have a linear differential equation:

```{math}
\frac{{{d^2}\theta }}{{d{t^2}}} + \frac{g}{L}\theta  = 0\;\; \text{or}\;\;\frac{{{d^2}\theta }}{{d{t^2}}} + {\omega ^2}\theta  = 0,
```

where $\omega  = \sqrt {\frac{g}{L}} $ is the angular frequency of oscillation.

The period of small oscillations is described by the well-known formula:

```{math}
T = \frac{{2\pi }}{\omega } = 2\pi \sqrt {\frac{L}{g}}.
```

However, with increasing amplitude, the linear equation ceases to be valid. 

---

## Period of Oscillation 

Suppose that the pendulum is described by the nonlinear second-order differential equation:

```{math}
\frac{{{d^2}\theta }}{{d{t^2}}} + \frac{g}{L}\sin \theta  = 0.
```

We consider the oscillations under the following initial conditions:

```{math}
\theta \left( {t = 0} \right) = {\theta _0},\;\;\; \frac{{d\theta }}{{dt}}\left( {t = 0} \right) = 0.
```

The angle ${\theta _0}$ is the **amplitude of oscillation**.

The order of the equation can be reduced by finding a suitable integrating factor. Multiply this equation by $\frac{{d\theta }}{{dt}}$, leading to:

```{math}
\frac{{{d^2}\theta }}{{d{t^2}}}\frac{{d\theta }}{{dt}} + \frac{g}{L}\sin \theta \frac{{d\theta }}{{dt}} = 0,\;\; \Rightarrow \frac{d}{{dt}}\left[ {\frac{1}{2}{{\left( {\frac{{d\theta }}{{dt}}} \right)}^2}  -  \frac{g}{L}\cos\theta } \right] = 0.
```

After integration, we obtain the first-order differential equation:

```{math}
{\left( {\frac{{d\theta }}{{dt}}} \right)^2} - \frac{{2g}}{L}\cos\theta  = C.
```

Using the initial conditions, the constant $C$ is found as:

```{math}
C =  - \frac{{2g}}{L}\cos{\theta _0}.
```

The equation then becomes:

```{math}
{\left( {\frac{{d\theta }}{{dt}}} \right)^2} = \frac{{2g}}{L}\left( {\cos\theta  - \cos{\theta _0}} \right).
```

Using the **double angle identity**:

```{math}
\cos\theta  = 1 - 2\,{\sin ^2}\frac{\theta }{2},
```

this simplifies to:

```{math}
\frac{{d\theta }}{{dt}} = 2\sqrt {\frac{g}{L}} \sqrt {{{\sin }^2}\frac{{{\theta _0}}}{2} - {{\sin }^2}\frac{\theta }{2}} .
```

After integrating:

```{math}
\int {\frac{{d\left( {\frac{\theta }{2}} \right)}}{{\sqrt {{{\sin }^2}\frac{{{\theta _0}}}{2} - {{\sin }^2}\frac{\theta }{2}} }}}  = \sqrt {\frac{g}{L}} \int {dt}.
```

Introducing the substitution $\sin {\frac{{{\theta _0}}}{2}} = k$ and $\sin \frac{\theta }{2} = k\sin \phi$, the equation becomes:

```{math}
\int {\frac{{d\phi}}{{\sqrt {1 - {k^2}\,{{\sin }^2}\phi } }}}  = \sqrt {\frac{g}{L}} \int {dt}.
```

The oscillation period is given by:

```{math}
T = 4\sqrt {\frac{L}{g}} \int\limits_0^{\frac{\pi }{2}} {\frac{{d\phi}}{{\sqrt {1 - {k^2}\,{{\sin }^2}\phi } }}} .
```

This integral, a **complete elliptic integral of the first kind**, is expressed as:

```{math}
K\left( k \right) = \int\limits_0^{\frac{\pi }{2}} {\frac{{d\phi}}{{\sqrt {1 - {k^2}\,{{\sin }^2}\phi } }}} .
```

Approximating $K(k) \approx \frac{\pi}{2}$ for small amplitudes, the period becomes:

```{math}
T_0 \approx 2\pi \sqrt {\frac{L}{g}} .
```

Higher-order terms account for anharmonicity and the nonlinear dependence of $T$ on ${\theta_0}$.





### Energy Conservation
The total mechanical energy $E$ of the pendulum is the sum of its kinetic energy ($T$) and potential energy ($U$):

```{math}
E = T + U.
```

- **Kinetic Energy**:
  The kinetic energy arises from the motion of the pendulum bob. If the angular displacement of the pendulum is $\theta$ and the angular velocity is $\dot{\theta} = \frac{d\theta}{dt}$, the kinetic energy is given by:
  ```{math}
  T = \frac{1}{2} I \dot{\theta}^2,
  ```
  where $I = mL^2$ is the moment of inertia for a point mass $m$ at a distance $L$ from the pivot. Substituting for $I$, the kinetic energy becomes:
  ```{math}
  T = \frac{1}{2} mL^2 \dot{\theta}^2.
  ```

- **Potential Energy**:
  The potential energy depends on the height of the pendulum bob relative to its lowest point. For an angular displacement $\theta$, the vertical displacement $h$ of the bob from its lowest position is:
  ```{math}
  h = L(1 - \cos\theta).
  ```
  The corresponding potential energy is:
  ```{math}
  U = mgh = mgL(1 - \cos\theta).
  ```

Thus, the total mechanical energy is:

```{math}
E = \frac{1}{2} mL^2 \dot{\theta}^2 + mgL(1 - \cos\theta).
```

---

In an ideal pendulum (no damping or external forces), mechanical energy is conserved. Therefore, the total energy $E$ remains constant during the motion. This conservation law can be expressed as:

```{math}
\frac{1}{2} mL^2 \dot{\theta}^2 + mgL(1 - \cos\theta) = E_0,
```

where $E_0$ is the total energy of the system, determined by the initial conditions (e.g., the initial angular displacement $\theta_0$).

At the maximum displacement ($\theta = \theta_0$), the angular velocity is zero ($\dot{\theta} = 0$), so the total energy is purely potential:

```{math}
E_0 = mgL(1 - \cos\theta_0).
```

---

## Perturbation Methods

When the angular displacement $\theta$ is small, we approximate $\sin\theta \approx \theta - \frac{\theta^3}{6}$. The equation becomes:
```{math}
\frac{\mathrm{d}^2\theta}{\mathrm{d}t^2} + \omega_0^2 \theta - \frac{\omega_0^2}{6} \theta^3 = 0, \quad \omega_0 = \sqrt{\frac{g}{L}}.
```

### Zeroth-Order Solution (SHM)
The zeroth-order solution assumes no non-linear effects:
```{math}
\theta_0(t) = A \cos(\omega_0 t),
```
where $A$ is the amplitude of oscillation.

### First-Order Correction
To account for non-linearity, we expand:
```{math}
\theta(t) = \theta_0(t) + \epsilon \theta_1(t),
```
where $\epsilon$ is a small parameter. Substituting into the equation and solving order-by-order:

1. **First-order equation:**
   ```{math}
   \frac{\mathrm{d}^2\theta_1}{\mathrm{d}t^2} + \omega_0^2 \theta_1 = \frac{\omega_0^2}{6} \theta_0^3.
   ```

2. **Expand $\theta_0^3$:**
   Using $\cos^3x = \frac{3}{4} \cos x + \frac{1}{4} \cos(3x)$,
   ```{math}
   \theta_0^3 = \frac{3}{4} A^3 \cos(\omega_0 t) + \frac{1}{4} A^3 \cos(3\omega_0 t).
   ```

3. **First-order solution:**
   ```{math}
   \theta_1(t) = \frac{A^3}{8 \omega_0^2} t \sin(\omega_0 t) + \frac{A^3}{216 \omega_0^2} \cos(3\omega_0 t).
   ```

4. **Total perturbative solution:**
   ```{math}
   \theta(t) \approx A \cos(\omega_0 t) + \frac{A^3}{8 \omega_0^2} t \sin(\omega_0 t) + \frac{A^3}{216 \omega_0^2} \cos(3\omega_0 t).
   ```


We can see the difference between the zeroth and first order ODE solutions using a Python plot:

````{admonition} Comparative Plot
:class: dropdown
```python 
import numpy as np
import matplotlib.pyplot as plt

# Parameters
g = 1  # gravitational acceleration
l = 1  # pendulum length
omega_0 = np.sqrt(g / l)  # natural frequency
A = np.pi / 4  # initial amplitude (45 degrees)
t = np.linspace(0, 10, 1000)  # time

# Zeroth-order solution (SHM)
theta_0 = A * np.cos(omega_0 * t)

# Forcing terms for the first-order correction
forcing_cos_omega = (g / (6 * l)) * (3 / 4) * A**3 * np.cos(omega_0 * t)
forcing_cos_3omega = (g / (6 * l)) * (1 / 4) * A**3 * np.cos(3 * omega_0 * t)

# First-order correction
theta_1_omega = (forcing_cos_omega / (omega_0**2)) * t  # Particular solution for omega_0
theta_1_3omega = (forcing_cos_3omega / (9 * omega_0**2))  # Particular solution for 3 * omega_0
theta_1 = theta_1_omega + theta_1_3omega

# Total perturbative solution
theta_total = theta_0 + theta_1

# Plot the solutions
plt.figure(figsize=(10, 6))
plt.plot(t, theta_total, label="1st Order Perturbative Solution", linewidth=2)
plt.plot(t, theta_0, '--', label="0th Order Solution (SHM)", linewidth=2)
plt.title("Perturbative Solution for Non-Linear Pendulum")
plt.xlabel("Time (s)")
plt.ylabel("Angular Displacement (rad)")
plt.legend()
plt.grid()
plt.show()
````

---

## Numerical Methods

Numerical integration provides an exact solution for any initial conditions and non-linearity.

### Define the System
The equation can be written as a first-order system:
```{math}
\frac{\mathrm{d}\theta}{\mathrm{d}t} = \omega, \quad \frac{\mathrm{d}\omega}{\mathrm{d}t} = -\frac{g}{L} \sin\theta.
```

### Solving Numerically
Using methods like Runge-Kutta (RK45), the equations are integrated over time. Below is an example:

````{admonition} ODE code using ivp.solve
:class: dropdown
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Define the differential equations for the non-linear pendulum
def pendulum(t, y, g, l):
    theta, omega = y
    dydt = [omega, -g / l * np.sin(theta)]
    return dydt

# Define the linearized solution for small-angle approximation
def linearized_solution(t, theta_0, g, l):
    omega_0 = np.sqrt(g / l)  # natural frequency
    return theta_0 * np.cos(omega_0 * t)

# Parameters
g = 1  # gravitational acceleration
l = 1  # pendulum length
theta_0 = np.pi / 4  # initial angle (45 degrees)
omega_0 = 0  # initial angular velocity
t_span = (0, 10)  # time range
t_eval = np.linspace(*t_span, 1000)

# Solve the non-linear pendulum numerically
solution = solve_ivp(pendulum, t_span, [theta_0, omega_0], t_eval=t_eval, args=(g, l))
time = solution.t
theta_nonlinear = solution.y[0]

# Compute the linearized solution
theta_linear = linearized_solution(t_eval, theta_0, g, l)

# Plot both solutions
plt.figure(figsize=(10, 6))
plt.plot(time, theta_nonlinear, label="Non-linear Solution", linewidth=2)
plt.plot(t_eval, theta_linear, '--', label="Linearized SHM Solution", linewidth=2)
plt.title("Comparison of Non-Linear and Linearised Pendulum Solutions")
plt.xlabel("Time (s)")
plt.ylabel("Angular Displacement (rad)")
plt.legend()
plt.grid()
plt.show()
````


## Exercises 

````{admonition} Exercises with ODE solvers
1\. Get some numerical solutions out of Python, compare with the linearised solutions and the perturbative solutions.  

2\. Get a phase portrait out and look at small and large angle results (where the SHM solutions are not valid)

3\. How could we include damping in this system now? Add this to your code and compare.
````


