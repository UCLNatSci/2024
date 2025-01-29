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

The non-linear pendulum equation cannot generally be solved in terms of elementary functions. However we can use different methods to understand how to characterise it's behaviour.


---

## Analytical Methods



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

### Period of Oscillation 

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

Lets look at the limits of integration, the passage of the arc from the lowest point $\alpha = 0$ to the maximum deviation $\alpha = \alpha_0$ corresponds to a quarter of the oscillation period $\frac{T}{4}$. It follows from the relationship between the angles $\alpha$ and $\theta$ that $\sin \theta = 1$ or $\theta = \frac{\pi}{2}$ at $\alpha = \alpha_0$. 

Therefore, we obtain the following expression for the period of oscillation of the pendulum:

```{math}
\sqrt{\frac{g}{L}} \frac{T}{4} = \int\limits_0^{\frac{\pi}{2}} \frac{d\theta}{\sqrt{1 - k^2 \sin^2\theta}} \;\; \text{or} \;\; T = 4\sqrt{\frac{L}{g}} \int\limits_0^{\frac{\pi}{2}} \frac{d\theta}{\sqrt{1 - k^2 \sin^2\theta}}.
```

The integral on the right cannot be expressed in terms of elementary functions. It is the so-called **complete elliptic integral of the first kind**:

```{math}
K(k) = \int\limits_0^{\frac{\pi}{2}} \frac{d\theta}{\sqrt{1 - k^2 \sin^2\theta}}.
```

We can see how this looks with a plot:
````{admonition} Elliptic Function
:class: dropdown

```python 
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import ellipk

# Generate k values from 0 to 1 (excluding 1)
k_values = np.linspace(0, 0.99, 500)
elliptic_values = ellipk(k_values**2)

# Plotting
plt.figure(figsize=(8, 6))
plt.plot(k_values, elliptic_values, lw=2)
plt.title('Complete Elliptic Integral of the First Kind', fontsize=14)
plt.xlabel(r'$k$', fontsize=12)
plt.ylabel(r'$K(k)$', fontsize=12)
plt.grid(True, alpha=0.5)
plt.show()

````

What is also interest is that $K(k)$ can also be represented as a power series:

```{math}
K(k) = \frac{\pi}{2} \left\{ 1 + \left(\frac{1}{2}\right)^2 k^2 + \left(\frac{1 \cdot 3}{2 \cdot 4}\right)^2 k^4 + \left(\frac{1 \cdot 3 \cdot 5}{2 \cdot 4 \cdot 6}\right)^2 k^6 + \ldots + \left[\frac{\left(2n - 1\right)!!}{\left(2n\right)!!}\right]^2 k^{2n} + \ldots \right\},
```

where the double factorials $\left(2n - 1\right)!!$ and $\left(2n\right)!!$ denote the product, respectively, of odd and even natural numbers.

Note that if we restrict ourselves to the zero term of the expansion, assuming that $K(k) \approx \frac{\pi}{2}$, we obtain the known formula for the period of small oscillations:

```{math}
T_0 = 4\sqrt{\frac{L}{g}} K(k) \approx 4\sqrt{\frac{L}{g}} \frac{\pi}{2} = 2\pi \sqrt{\frac{L}{g}}.
```

Further terms of the series for $n \ge 1$ allow consideration of the anharmonicity of the oscillations of the pendulum and the nonlinear dependence of the period $T$ on the oscillation amplitude $\alpha_0$.


Higher-order terms account for anharmonicity and the nonlinear dependence of $T$ on ${\theta_0}$.




## Perturbative  Methods

### Introduction to perturbation

Lets look at a perturbation series solution of the equation:

```{math}
y'' + \varepsilon y' = 1, \varepsilon \ll 1
```

This problem has a closed-form exact solution, which is a linear combination of homogeneous solutions  plus a particular solution:

```{math}
y_E(x) = \frac{x}{\varepsilon} + c_1 e^{-\varepsilon x} + c_2.
```

The coefficients $c_1,\, c_2$ can be determined from the boundary conditions of the system, lets pick some simple boundary conditions here:

```{math}
y(0) &= 1 \\
y(1) &= 0
```
NB we could pick intital conditions (e.g. $y(0), \,y'(0)$), this is just a choice!

So we find here:


```{math}
y(0) = c_1 + c_2 = 1,
```
```{math}
y(1) = \frac{1}{\varepsilon} + c_1 e^{-\varepsilon} + c_2 = 0.
```

From these:
```{math}
c_1 = \frac{1 + 1/\varepsilon}{1 - e^{-\varepsilon}}, \quad c_2 = 1 - c_1 = 1 - \frac{1 + 1/\varepsilon}{1 - e^{-\varepsilon}}
```

This solution can be used to test the convergence of the perturbative solution.

---

### Perturbative Solution

Now lets assume a series solution to $y(x)$ which also depends on the perturbative parameter $\varepsilon$, we can do this in the form of some Taylor style series expansion in $\varepsilon$, which in the limit of $\varepsilon \rightarrow 0$ will produce just one solution $y_0(x)$ which satisfies $y_0(x)'' = 1$:

```{math}
y(x, \varepsilon) = y_0(x) + \varepsilon y_1(x) + \varepsilon^2 y_2(x) + \cdots
```

Substituting into the differential equation:

```{math}
y_0''(x) + \varepsilon y_1''(x) + \varepsilon y_2''(x) +\cdots + \varepsilon\left(y_0'(x) + \varepsilon y_1'(x) + \varepsilon y_2'(x)+ \cdots\right) = 1.
```

Applying boundary conditions, which is crucial to solving these problems:

```{math}
y(0) = y_0(0) + \varepsilon y_1(0) + \varepsilon^2 y_2(0) + \cdots = 1 + \varepsilon\,0 + \varepsilon^2\,0 + \dots = 1,
```

```{math}
y(1) = y_0(1) + \varepsilon y_1(1) + \varepsilon^2 y_2(1) + \cdots = 0 + \varepsilon\,0 + \varepsilon^2\,0 + \dots = 0.
```

Note that we apply these boundary conditions order by order, so the easiest way to think about these here is to have the zeroth order ones slightly different to the first order and higher ones - again this is a choice!

---

### Sorting by Powers of $\varepsilon$

**Order $\varepsilon^0$:**

```{math}
y_0''(x) = 1, \quad y_0(0) = 1, \quad y_0(1) = 0.
```

Solving gives:
```{math}
y_0(x) = \frac{x^2}{2} - \frac{3x}{2} + 1.
```

---

**Order $\varepsilon^1$:**

```{math}
y_1''(x) + y_0'(x) = 0 \implies y_1''(x) = -y_0'(x) = - x + \frac{3}{2}
```

Solution:

```{math}
y_1(x) = -\frac{x^3}{6} + \frac{3x^2}{4} + c_3 x + c_4.
```

Using boundary conditions:
```{math}
y_1(0) &= c_4 = 0\\
y_1(1) &= -\frac{1}{6} + \frac{3}{4} + c_3 = 0 \implies c_3 = -\frac{7}{12}\\
```

Thus:

```{math}
y_1(x) = -\frac{x^3}{6} + \frac{3x^2}{4} - \frac{7x}{12}
```

---

**Order $\varepsilon^2$:**

```{math}
y''_2(x) + y'_1(x) = 0, \quad y_2(0) = 0, \quad y_2(1) = 0.
```

Substituting $ y'_1(x) $:
```{math}
y''_2(x) = x^2 - \frac{3}{2}x + \frac{7}{12}.
```

Integrating twice:
```{math}
y_2(x) = \frac{x^4}{24} - \frac{x^3}{4} + \frac{7x^2}{24} + c_5 x + c_6.
```

Using boundary conditions:
```{math}
y_2(0) &= c_6 = 0\\
y_2(1) &= \frac{1}{24} - \frac{1}{4} + \frac{7}{24} + c_5 = 0 \implies c_5 = -\frac{1}{12}.
```

Thus:
```{math}
y_2(x) = \frac{x^4}{24} - \frac{x^3}{4} + \frac{7x^2}{24} - \frac{x}{12}.
```
---

### Observations

The upper-left panel of the Figure shows the exact solutions for $\varepsilon = 1, 2, 3$ matched against the pertubative. Despite $\varepsilon$ being relatively large, the exact solutions vary smoothly and linearly with $\varepsilon$, suggesting that the perturbation series in powers of $\varepsilon$ might be accurate.

The remaining panels plot the error of the 0th, 1st, and 2nd-order perturbation series approximations. Key observations:

- The 0th-order series has a maximum error proportional to $\varepsilon$.
- The 1st-order series has a maximum error proportional to $\varepsilon^2$.
- The 2nd-order series has a maximum error proportional to $\varepsilon^3$.

For $\varepsilon = 1$, the 2nd-order perturbation series has a maximum error of 0.0025, demonstrating the excellent accuracy of the series across a wide range of $\varepsilon$.

---

![Exact and Perturbative Solutions](plots.png)

## Numerical Methods

Numerical integration provides us with some working solutions for any initial conditions and non-linearity.

Remember we need to write the system as a set of coupled first order ODEs, but once we get it into Python, using methods like Runge-Kutta (RK45), the equations can integrated over time. We can compare these results with the small angle SHM solutions: 

![Exact and Approx Solutions](plot3.png)

The solid red line is the full numerical solution and the dashed blue line is the equivalent SHM system.

## Non-Linear Pendulum

Lets think about the non-linear pendulum system

```{math}
\frac{\mathrm{d}^2\theta}{\mathrm{d}\tau^2} + \omega^2 \sin\theta = 0 \Rightarrow \frac{\mathrm{d}^2\theta}{\mathrm{d}t^2} + \sin\theta = 0, \quad \theta(0) = \varepsilon \ll 1, \quad \frac{\mathrm{d}\theta}{\mathrm{d}t}(0) = 0. \tag{P}
```

We’ve nondimensionalized time $t$ by multiplying it by the linear pendulum frequency $ \omega = (g/L)^{1/2} $, i.e. $t = \omega\,\tau$ , changing the coefficient of $ \sin\theta $ from $ \omega^2 = g/L $ to 1.

In this system we will set up the initial condition as perturbative and given we expect $ \theta(t) $ to oscillate between $ \pm\varepsilon $, we substitute the series:

```{math}
\theta(t) = \varepsilon\theta_1(t) + \varepsilon^2\theta_2(t) + \varepsilon^3\theta_3(t) + \dots
```

Substituting into the ODE $ (P) $, and keeping terms through to $ \mathcal{O}(\varepsilon^3) $:

```{math}
\varepsilon\theta_1''(t) + \varepsilon^2\theta_2''(t) + \varepsilon^3\theta_3''(t) + \sin(\varepsilon\theta_1(t) + \varepsilon^2\theta_2(t) + \dots) = 0
```

Expanding $ \sin\theta $ using a Taylor series:

```{math}
\sin\theta = \theta - \frac{\theta^3}{6} + \dots,
```

we substitute into the ODE:

```{math}
\sin(\varepsilon\theta_1(t) + \varepsilon^2\theta_2(t) + \varepsilon^3\theta_3(t)) = \varepsilon\theta_1(t) + \varepsilon^2\theta_2(t) + \varepsilon^3\theta_3(t) - \frac{(\varepsilon\theta_1(t) + \varepsilon^2\theta_2(t) + \varepsilon^3\theta_3(t))^3}{6} + \dots
```

The cubic term can be expanded as:

```{math}
(\varepsilon\theta_1 + \varepsilon^2\theta_2 + \varepsilon^3\theta_3)^3 = \varepsilon^3\theta_1^3 + 3\varepsilon^4\theta_1^2\theta_2 + 3\varepsilon^5\theta_1\theta_2^2 + \varepsilon^5\theta_2^3 + 3\varepsilon^5\theta_1^2\theta_3 + \dots
```

Keeping terms up to $ \mathcal{O}(\varepsilon^3) $, only the cubic term $ \varepsilon^3\theta_1^3 $ contributes.

The ODE now becomes:

```{math}
\varepsilon\theta_1''(t) + \varepsilon^2\theta_2''(t) + \varepsilon^3\theta_3''(t) + \left(\varepsilon\theta_1 + \varepsilon^2\theta_2 + \varepsilon^3\theta_3 - \frac{\varepsilon^3\theta_1^3}{6}\right) = 0.
```


**Order $\varepsilon^1$:**
```{math}
  \theta_1''(t) + \theta_1 = 0, \quad \theta_1(0) = 1, \quad \theta_1'(0) = 0 
```

We can solve this using $\theta_1(t) = A\cos(t) + B \sin(t)$ but applying the boundary conditions leaves us with:
```{math}
\theta_1(t) = \cos(t)
```

**Order $\varepsilon^2$:**
```{math}
  \theta_2''(t) + \theta_2 = 0, \quad \theta_2(0) = 0, \quad \theta_2'(0) = 0 
```
We can solve this using $\theta_2(t) = A\cos(t) + B \sin(t)$ but applying the boundary conditions leaves us with:
```{math}
\theta_2(t) = 0

**Order $\varepsilon^3$:**
  ```{math}
  \theta_3''(t) + \theta_3 = \frac{\theta_1^3}{6} = \frac{\cos^3(t)}{6}, \quad \theta_3(0) = 0, \quad \theta_3'(0) = 0.
  ```

Expanding $ \cos^3(t) $ using the trigonometric identity:

```{math}
\cos^3(t) = \frac{3\cos(t) + \cos(3t)}{4},
```

the equation becomes:

```{math}
\theta_3''(t) + \theta_3(t) = \frac{1}{6} \cdot \frac{3\cos(t) + \cos(3t)}{4} = \frac{\cos(t)}{8} + \frac{\cos(3t)}{24}.
```

Thus, the ODE is:

```{math}
\theta_3''(t) + \theta_3(t) = \frac{\cos(t)}{8} + \frac{\cos(3t)}{24}.
```

We can solve this with homogeneous and particular solution method of second order ODEs, another way to approach this problem is to use Laplace transforms, however after some work we can find:

```{math}
\theta_3(t) = \frac{1}{16}t\sin(t) + \frac{1}{192}\cos(t) - \frac{1}{192}\cos(3t).
```

### Final Solution

The perturbative solution therefore is:

```{math}
\theta(t) = \varepsilon\cos(t) + \varepsilon^3\left[\frac{1}{16}t\sin(t) + \frac{1}{192}\cos(t) - \frac{1}{192}\cos(3t)\right] + \dots
```

### Secular Terms

The $ \mathcal{O}(\varepsilon^3) $ term grows linearly with $ t $ - we call these **secular terms**. At large times $ t = \mathcal{O}(\varepsilon^{-2}) $, this term dominates, and the perturbation series loses validity. This growth corresponds to phase drift due to slower nonlinear oscillation compared to linear oscillation.  Secular terms therefore can grow without bound and can cause solutions to diverge, which invalidates perturbation theory. 

Using a more advanced perturbation method, such as method of **multiple scales**, we can remove secular terms systematically.


### Plotting the solutions

![Comparison of numerical and perturbation series solutions to the nonlinear pendulum problem
](plot2.png)

We notice that the secular terms ruin the pertubative solutions for larger $\varepsilon$.  For low $\varepsilon$ we see a great agreement between the numerical and the perturbative.




## Exercises 

````{admonition} Exercises with ODE solvers
1\. Get some numerical solutions out of Python, compare with the linearised solutions and the perturbative solutions.  

2\. Get a phase portrait out and look at small (SHM solutions are valid) and large angle results (SHM solutions are not valid) - what conclusions can we draw?

3\. How could we include damping in this system now? Add this to your code and compare.

4\. Looking at the time period, add more perurbative terms into the expression to show how it changes for larger and larger $\theta$.
````


