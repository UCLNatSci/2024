# Solving Non-Linear Ordinary Differential Equations

Non-linear ordinary differential equations (ODEs) form the cornerstone of many real-world phenomena where the relationships between variables are inherently non-linear. Understanding and solving non-linear ODEs is critical for exploring many systems in physics, biology, engineering, and economics.

## Why Are Non-Linear ODEs Important?

1. **Real-World Applications**: Many different systems are governed by non-linear dynamics, examples include:
   - Climate models.
   - Population dynamics in ecology.
   - Circuit designs in electrical engineering.
   - Fluid mechanics and turbulence.

2. **Rich Behavior**: Non-linear systems can exhibit phenomena absent in linear systems, such as:
   - **Chaos**: Extreme sensitivity to initial conditions.
   - **Limit Cycles**: Stable, repeating oscillations.
   - **Bifurcations**: Sudden qualitative changes in behavior as parameters vary.

3. **Challenges in Analysis**: Unlike linear ODEs, non-linear equations often cannot be solved explicitly, we have to make use of different methods like perturbation theory, numerical analysis, and qualitative techniques to gain some intution.

---

## Examples of Non-Linear ODEs

### Pendulum
The equation for the angular displacement $\theta(t)$ of a simple pendulum is:
```{math}
\frac{\mathrm{d}^2\theta}{\mathrm{d}t^2} + \frac{g}{l}\sin\theta = 0
```
This equation is non-linear due to the $\sin\theta$ term. For small angles, it simplifies to the linearized form used in simple harmonic motion.

### Van der Pol Oscillator
A model for electrical circuits and heartbeats:
```{math}
\frac{\mathrm{d}^2x}{\mathrm{d}t^2} - \mu(1-x^2)\frac{\mathrm{d}x}{\mathrm{d}t} + x = 0
```
This exhibits limit cycles and is a classic example of a self-sustaining oscillatory system.

### Logistic Growth with Harvesting
A non-linear model for population dynamics with external harvesting:
```{math}
\frac{\mathrm{d}N}{\mathrm{d}t} = rN\left(1 - \frac{N}{K}\right) - hN
```
Here $r$ is the growth rate, $K$ is the carrying capacity, and $h$ is the harvesting rate.

### Duffing Oscillator
Modeling non-linear stiffness in mechanical systems:
```{math}
\frac{\mathrm{d}^2x}{\mathrm{d}t^2} + \delta \frac{\mathrm{d}x}{\mathrm{d}t} + \alpha x + \beta x^3 = \gamma \cos(\omega t)
```

### Ermakov-Pinney equation:
Modelling a time varying mass term in harmonic motion systems:
```{math}
{\mathrm{d}^{2}x \over \mathrm{d}t^{2}}+\omega(t)^{2}x={\frac {h(t)^{2}}{x^{3}}}
```


### The Thomas-Fermi equation:
Modelling the electric potential in different types of atom:
```{math}
\frac {\mathrm{d}^{2}y}{\mathrm{d}x^{2}}={\frac {1}{\sqrt {x}}}y^{3/2}
```

Subject to the boundary conditions:

```{math}
y(0) = 1, \quad 
  \begin{cases} 
  y(\infty) = 0, & \text{for neutral atoms}, \\ 
  y(x_0) = 0, & \text{for positive ions}, \\ 
  y(x_1) - x_1 y'(x_1) = 0, & \text{for compressed neutral atoms}.
  \end{cases}
```

### The Ginzburg-Landu equation:
Modelling the evolution of small disturbances near a stable state of certain dynamical systems:
```{math}
\frac{\partial A}{\partial t} = \mu A - g A|A|^{2} + \nu \nabla^{2}A
```


We can find a longer list of non-linear ordinary differential equations [online](https://en.wikipedia.org/wiki/List_of_nonlinear_ordinary_differential_equations).


---

## Scope of the Notes

In these notes, we will:
- Explore analytical, semi-analytical, and numerical techniques to solve non-linear ODEs.
- Study the qualitative behavior of solutions using phase plane analysis.
- Apply these techniques to classic problems, such as the ones outlined above, and introduce more advanced systems as the notes progress.

Non-linear ODEs are a fascinating and vital area of study, offering insights into the complexity of the natural world and engineered systems.
