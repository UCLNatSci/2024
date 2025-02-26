# Thomas Fermi Equation

# Notes on Solving the Thomas-Fermi Equation

The Thomas-Fermi equation is a nonlinear ordinary differential equation that can be studied as a mathematical problem, focusing on the methods for solving and analyzing it.

---

## The Equation

The Thomas-Fermi equation is given by:
```{math}
\frac{\mathrm{d}^2\phi}{\mathrm{d}x^2} = \frac{1}{\sqrt{r}} \phi^{3/2}(x),
```
with the boundary conditions:
- $\phi(0) = 1$: The potential is normalized at the origin.
- $\phi(x) \to 0$ as $x \to \infty$: The potential vanishes at large distances.

Here, $x > 0$ is some radial distance, and $\phi(x)$ is the unknown function to solve for.

---

## Boundary Conditions and Their Implications

- At $x = 0$: Regularity requires $\phi'(0) = 0$ to avoid divergence in the second derivative.
- As $x \to \infty$: The solution decays to zero, ensuring a well-behaved function at large distances.

These conditions guide the numerical or analytical approach to solving the equation.

---

## Semi-Analytic Analysis and Methods

### Reduction of Order

We can use a variable transformation $z=y/x$ converts the equation to

```{math}
\frac{1}{x^2}\frac{d}{dx}\left(x^2\frac{dz}{dx}\right) - z^{3/2}=0
```

The original equation is invariant under the transformation $x\rightarrow c x, \ y\rightarrow c^{-3} y$. Hence, the equation can be made equidimensional by introducing $y=x^{-3} u$ into the equation, leading to

```{math}
x^2 \frac{d^2u}{dx^2} - 6x\frac{du}{dx} + 12 u = u^{3/2}
```

so that the substitution $x=e^t$ reduces the equation to

```{math}
\frac{d^2u}{dt^2} - 7\frac{du}{dt} +12 u = u^{3/2}
```

Treating $w =du/dt$ as the dependent variable and $u$ as the independent variable, we can reduce the above equation to

```{math}
w \frac{dw}{du} - 7w = u^{3/2}-12 u
```

But this first order equation has no known explicit solution, hence, the approach turns to either numerical or approximate methods.

### Sommerfeld's approximation

The TF equation has a particular solution $y_p(x)$, which satisfies the boundary condition that $y\rightarrow 0$ as $x\rightarrow\infty$, but not the  boundary condition $y(0)=1$:

```{math}
y_p(x) = \frac{144}{x^3}
```



### Asymptotic Analysis

#### Near $r = 0$
Assuming a power-series solution $\phi(r) = 1 - kr^{n}$, substitution gives:
```{math}
\phi(r) \approx 1 - \frac{2}{3}r^{3/2} +\dots
```

#### Far from the Origin ($r \to \infty$)
The decay of $\phi(r)$ is slow. Using asymptotic expansion methods, one finds:
```{math}
\phi(r) \sim \frac{A}{r^3},
```
where $A$ is determined numerically or from matching conditions.

---



## Extended Forms of the Thomas-Fermi Equation  

Each extension modifies the right-hand side of the classical Thomas-Fermi equation in a different way, leading to distinct ODEs.  Each extension adds corrections for a specific physical effect, improving accuracy for different regimes such as high temperature, exchange interactions, inhomogeneities, and relativistic effects.


---

### Finite Temperature Corrections (Finite-T Thomas-Fermi Equation)  
At finite temperature, the electron density follows a **Fermi-Dirac distribution** instead of a sharp cutoff. This modifies the right-hand side of the ODE by introducing temperature dependence via the **Fermi integral**:

```{math}
\frac{\mathrm{d}^2 \phi}{\mathrm{d} x^2} = x^{-\frac{1}{2}} F_{1/2} \left(\frac{\phi(x)}{T} \right).
```

where:  
- $ F_{1/2} (\eta) $ is the **Fermi-Dirac integral**,

  ```{math}
  F_{1/2} (\eta) = \int_0^\infty \frac{t^{1/2} \, \mathrm{d}t}{e^{t-\eta} + 1}.
  ```

- $ T $ is the dimensionless temperature parameter.

Effect:  
- At **low temperatures** ($ T \to 0 $), the classical Thomas-Fermi equation is recovered.  
- At **high temperatures**, the screening length increases due to the smearing of the electron density.

---

### Thomas-Fermi-Dirac (TFD) Equation (Exchange Corrections)  
To account for **exchange interactions**, Dirac introduced a correction term that modifies the power-law dependence on $ \phi $:

```{math}
\frac{\mathrm{d}^2 \phi}{\mathrm{d} x^2} = x^{-\frac{1}{2}} \phi^{\frac{3}{2}} \left(1 - \lambda \phi^{-\frac{1}{6}}\right).
```

where:  
- $ \lambda = \frac{3}{2} \left(\frac{3}{\pi}\right)^{1/3} \approx 0.276 $ is a numerical constant.

Effect:  
- The exchange correction **lowers** the electron density compared to the classical Thomas-Fermi model.
- The asymptotic decay remains the same as $ \phi(x) \sim x^{-3} $ for large $ x $, but with a modified prefactor.

---

### Thomas-Fermi-Weizsäcker (TFW) Model (Gradient Corrections)  
This model introduces a **kinetic energy correction** to account for inhomogeneities in the electron density. The ODE now includes a second derivative term:

```{math}
\frac{\mathrm{d}^2 \phi}{\mathrm{d} x^2} = x^{-\frac{1}{2}} \phi^{\frac{3}{2}} + \lambda \frac{\mathrm{d}^3 \phi}{\mathrm{d} x^3}.
```

where $ \lambda $ is a parameter that determines the strength of the correction.

Effect:  
- This equation is now a **third-order** ODE instead of second-order.
- It accounts for spatial variations in the electron density, improving accuracy in non-uniform systems (e.g., molecules and solids).
- The boundary conditions require an additional constraint on $ \frac{\mathrm{d} \phi}{\mathrm{d} x} $ at $ x = 0 $.

---

### Relativistic Thomas-Fermi Equation  
For high-$ Z $ (large nuclear charge) atoms, relativistic effects become significant. The relativistic Thomas-Fermi equation modifies the exponent on $ \phi $:

```{math}
\frac{\mathrm{d}^2 \phi}{\mathrm{d} x^2} = x^{-\frac{1}{2}} \phi^p, \quad p = \frac{4}{3}.
```

Effect:  
- The exponent changes from **$ 3/2 $ (non-relativistic) to $ 4/3 $** (relativistic).  
- The asymptotic behavior changes to **$ \phi(x) \sim x^{-3/2} $** instead of $ x^{-3} $.  
- This correction improves predictions for high-energy physics and heavy-element behavior.




