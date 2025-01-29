# Thomas Fermi Equation

# Notes on Solving the Thomas-Fermi Equation

The Thomas-Fermi equation is a nonlinear ordinary differential equation that can be studied as a mathematical problem, focusing on the methods for solving and analyzing it.

---

## 1. The Equation

The Thomas-Fermi equation is given by:
```{math}
\frac{\mathrm{d}^2\phi}{\mathrm{d}r^2} = \frac{1}{\sqrt{r}} \phi^{3/2}(r),
```
with the boundary conditions:
- $\phi(0) = 1$: The potential is normalized at the origin.
- $\phi(r) \to 0$ as $r \to \infty$: The potential vanishes at large distances.

Here, $r > 0$ is the radial distance, and $\phi(r)$ is the unknown function to solve for.

---

## 2. Boundary Conditions and Their Implications

- **At $r = 0$**: Regularity requires $\phi'(0) = 0$ to avoid divergence in the second derivative.
- **As $r \to \infty$**: The solution decays to zero, ensuring a well-behaved function at large distances.

These conditions guide the numerical or analytical approach to solving the equation.

---

## 3. Reduction of Order

To simplify the problem, substitute $\phi(r) = r^{-1/2}y(r)$. Then:
```{math}
\frac{\mathrm{d}^2\phi}{\mathrm{d}r^2} = r^{-5/2} \left( y''(r) - \frac{1}{4}r^{-2}y(r) \right),
```
and the equation becomes:
```{math}
y''(r) = \frac{1}{4}r^{-2}y(r) + y^{3/2}(r).
```

This substitution removes the singularity at $r = 0$ and can make numerical solutions more stable.

---

## 4. Asymptotic Analysis

### Near $r = 0$
Assuming a power-series solution $\phi(r) = 1 - kr^{n}$, substitution gives:
```{math}
\phi(r) \approx 1 - \frac{2}{3}r^{3/2}.
```

### Far from the Origin ($r \to \infty$)
The decay of $\phi(r)$ is slow. Using asymptotic expansion methods, one finds:
```{math}
\phi(r) \sim \frac{A}{r^3},
```
where $A$ is determined numerically or from matching conditions.

---

## 5. Numerical Solution Techniques

### Shooting Method
1. Transform the boundary value problem into an initial value problem.
2. Guess initial slopes $\phi'(0)$ and adjust iteratively to satisfy $\phi(r) \to 0$ as $r \to \infty$.

### Finite Difference Method
1. Discretize the domain into small steps $r_i$ and approximate derivatives with finite differences.
2. Solve the resulting nonlinear algebraic equations iteratively.

---

## 6. Key Properties

- **Nonlinearity**: The term $\phi^{3/2}$ introduces a strong nonlinearity, complicating direct integration methods.
- **Singular Behavior**: The factor $\frac{1}{\sqrt{r}}$ requires careful handling near $r = 0$.

---

## 7. Example of Numerical Steps

1. Start with the substitution $\phi(r) = r^{-1/2}y(r)$ to remove singular behavior.
2. Choose a numerical grid for $r \in [\varepsilon, R]$ ($\varepsilon$ small to avoid division by zero, $R$ large enough to approximate infinity).
3. Use a method like Runge-Kutta or finite differences to integrate the equation.
4. Adjust boundary conditions iteratively to ensure smooth decay to zero.

---

## 8. Applications of the Solution

While derived in a physical context, the equation and its solutions are mathematically rich, providing insights into:
- Behavior of nonlinear ODEs.
- Singular boundary value problems.
- Numerical approximation methods.

The Thomas-Fermi equation is a valuable case study in solving challenging nonlinear differential equations.
