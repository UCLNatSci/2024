# Partial Differential Equations

## Important PDEs

Consider a function $ u = u(x_1, x_2, \dots, x_n) $, which depends on $ n $ variables $ x_1, x_2, \dots, x_n $. In physical problems, these variables are usually spatial coordinates, e.g., $ x, y, z $, and time $ t $. Depending on the problem at hand, it can be convenient to consider the function $ u $ in Cartesian, polar, or spherical coordinate systems:

- In Cartesian coordinates:  
  ```{math}
  u = u(x, y, z, t)
  ```
- In polar coordinates:  
  ```{math}
  u = u(r, \theta, z, t)
  ```
- In spherical coordinates:  
  ```{math}
  u = u(r, \theta, \phi, t)
  ```

### The Wave Equation

In Cartesian coordinates:

```{math}
r^2 u = \frac{1}{v^2} \frac{\partial^2 u}{\partial t^2}
```

In polar coordinates:

```{math}
r^2 u = \left( \frac{\partial^2 u}{\partial r^2} + \frac{1}{r} \frac{\partial u}{\partial r} + \frac{1}{r^2} \left( \frac{\partial^2 u}{\partial \theta^2} + \frac{\partial^2 u}{\partial \phi^2} \right) \right)
```

In spherical coordinates:

```{math}
r^2 u = \left( \frac{\partial^2 u}{\partial r^2} + \frac{2}{r} \frac{\partial u}{\partial r} + \frac{1}{r^2} \left( \frac{\partial^2 u}{\partial \theta^2} + \frac{\sin^2 \theta}{r} \frac{\partial^2 u}{\partial \phi^2} \right) \right)
```

where $ v $ is the wave velocity.

In the one-dimensional case, the wave equation is:

```{math}
\frac{\partial^2 u(x,t)}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 u(x,t)}{\partial t^2}
```

---

### The Diffusion Equation

```{math}
k r^2 u = \frac{\partial u}{\partial t}
```

This equation is also used to describe heat flow.

---

### Laplace’s Equation

```{math}
r^2 u = 0
```

---

### Poisson’s Equation

```{math}
r^2 u = \rho(r)
```

---

### Schrödinger’s Equation

```{math}
r^2 u + V(r) u = \frac{i \hbar}{2m} \frac{\partial u}{\partial t}
```

## General form of the linear 1st order PDE

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} + C(x, y) u = R(x, y)
```

where $ A(x, y), B(x, y), C(x, y), $ and $ R(x, y) $ are functions of $ x $ and $ y $. Importantly, there could be many solutions due to:
1. Integrating constants
2. Existence of independent solutions.

### Case of $ C(x, y) = R(x, y) = 0 $

If $ C = R = 0 $, Eq. (7.1) becomes:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} = 0
```

Consider solutions of this equation in the form of:

```{math}
u(x, y) = f(p)
```

where $ p $ is a parameter formed by some fixed combination of $ x $ and $ y $. Note that $ p $ is a function of $ x $ and $ y $: $ p(x, y) $.

Use the chain rule of differentiation to obtain $ \frac{\partial u}{\partial x} $ and $ \frac{\partial u}{\partial y} $:

```{math}
\frac{\partial u(x, y)}{\partial x} = \frac{df(p)}{dp} \frac{\partial p}{\partial x}, \quad \frac{\partial u(x, y)}{\partial y} = \frac{df(p)}{dp} \frac{\partial p}{\partial y}
```

Substitute these into Eq. (7.2) and obtain:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} - \frac{df(p)}{dp} = 0
```

This equation is satisfied if:

```{math}
\frac{df(p)}{dp} = 0
```

which means that function $ f(p) $ is a constant, i.e., it has no dependence on $ p $ and, therefore, has no dependence on $ x $ and $ y $. Alternatively, Eq. (7.3) is satisfied if:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} = 0
```

Notice that this equation is similar to Eq. (7.2), in which $ u $ is replaced with $ p $.

On the other hand, for $ p $ to remain a constant combination of $ x $ and $ y $, we should have:

```{math}
dp = \frac{\partial p}{\partial x} dx + \frac{\partial p}{\partial y} dy = 0
```

Note that this equation is identical to Eq. (7.4) if we set:

```{math}
dx = \frac{A(x, y)}{B(x, y)} dy
```

Hence, instead of solving Eqs. (7.4) and (7.5), we can integrate the equation to find $ p $.

### Example

Consider:

```{math}
x^3 \frac{\partial u}{\partial x} + 3y^2 \frac{\partial u}{\partial y} = 0
```

In this case, we have $ A(x, y) = x^3 $ and $ B(x, y) = 3y^2 $. Following the previous discussion, this equation is converted to:

```{math}
\frac{dx}{x^3} = \frac{dy}{3y^2}
```

After integration:

```{math}
-\frac{1}{2x^2} = -\frac{1}{6y^3} + C
```

This simplifies to:

```{math}
1 = 1 + C \quad \text{where} \quad C = \frac{3y^2}{2x^3}
```

Thus, the general solution of Eq. (7.6) is:

```{math}
u(x, y) = f\left( \frac{3y - 2x^2}{6x^2y} \right)
```

### Case of $ R(x, y) = 0 $

If $ R = 0 $, Equation (7.1) becomes:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} + C(x, y) u = 0
```

Apply the same logic as above but consider a solution in the form:

```{math}
u(x, y) = h(x, y) f(p)
```

In this case, we have:

```{math}
\frac{\partial u}{\partial x} = \frac{\partial h(x, y)}{\partial x} f(p) + h(x, y) \frac{df(p)}{dp} \frac{\partial p}{\partial x}
```

```{math}
\frac{\partial u}{\partial y} = \frac{\partial h(x, y)}{\partial y} f(p) + h(x, y) \frac{df(p)}{dp} \frac{\partial p}{\partial y}
```

Substitute these derivatives into PDE (7.7):

```{math}
A(x, y) \left( \frac{\partial h}{\partial x} f(p) + h \frac{df(p)}{dp} \frac{\partial p}{\partial x} \right) + B(x, y) \left( \frac{\partial h}{\partial y} f(p) + h \frac{df(p)}{dp} \frac{\partial p}{\partial y} \right) + C(x, y) h f(p) = 0
```

After rearranging the terms:

```{math}
A(x, y) \frac{\partial h}{\partial x} + B(x, y) \frac{\partial h}{\partial y} + C(x, y) h f(p) + A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} - h \frac{df(p)}{dp} = 0
```

The first term turns to zero if function $ h(x, y) $ is any solution of the original PDE given by Eq. (7.7). Let us assume that we have found such a function $ h(x, y) $. Then, only the second term remains:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} - h \frac{df(p)}{dp} = 0
```
### Non-trivial Solutions of the Equation

Non-trivial solutions of this equation can be found by solving:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} = 0
```

In other words, the problem is reduced to the previously considered case of $ C(x, y) = R(x, y) = 0 $ given by Eq. (7.2).

### Example

Consider the equation:

```{math}
x \frac{\partial u}{\partial x} + 2 \frac{\partial u}{\partial y} - 2u = 0
```

Here, $ A(x, y) = x $, $ B(x, y) = 2 $, $ C(x, y) = -2 $. First, integrate:

```{math}
\frac{dx}{x} = \frac{dy}{2}
```

which gives:

```{math}
\ln x = \frac{1}{2} y + C, \quad x = c \exp\left(\frac{y}{2}\right),
```

where $ c $ is a constant, which can be associated with the parameter $ p $:

```{math}
p = x \exp\left(-\frac{y}{2}\right).
```

Therefore, a general solution of Equation (7.9) is given by:

```{math}
u(x, y) = h(x, y) f\left( -x \exp\left(-\frac{y}{2}\right) \right),
```

where $ f $ is an arbitrary function.

It remains to find an expression for $ h(x, y) $. In the simplest case, we can consider $ h(x, y) $ as a function of $ x $ only. Therefore, the corresponding equation with respect to $ h(x) $ is simplified to:

```{math}
A(x, y) \frac{\partial h}{\partial x} + B(x, y) \frac{\partial h}{\partial y} + C(x, y) h = 0
```

```{math}
x \frac{\partial h}{\partial x} - 2 h = 0
```

and its particular solution is $ h(x) = x^2 $.

Alternatively, we can consider $ h(x, y) $ as a function of $ y $ only. According to Eq. (7.10), the corresponding equation with respect to $ h(y) $ is:

```{math}
2 \frac{\partial h}{\partial y} - 2h = 0,
```

which has a particular solution $ h(y) = e^y $.

Hence, the corresponding two sets of general solutions are:

```{math}
u_1(x, y) = x^2 f\left( -x \exp\left(-\frac{y}{2}\right) \right), \quad u_2(x, y) = e^y g\left( -x \exp\left(-\frac{y}{2}\right) \right),
```

where $ f $ and $ g $ are arbitrary functions of $ x \exp\left(-\frac{y}{2}\right) $. The superposition:

```{math}
u(x, y) = u_1(x, y) + u_2(x, y)
```

is also a solution of the PDE (7.9).

## Homogeneity

- Homogeneous partial differential equation: If $ u(x, y) $ is a solution of a PDE, then $ v(x, y) = c \cdot u(x, y) $, where $ c $ is an arbitrary constant, is also a solution of the same PDE.
- Homogeneous boundary conditions: If $ u(x, y) $ satisfies the boundary conditions, then $ v(x, y) = c \cdot u(x, y) $, where $ c $ is an arbitrary constant, also satisfies the same boundary conditions.

### Solutions of Inhomogeneous Equations

Given the equation:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} + C(x, y) u(x, y) = R(x, y),
```

and the boundary condition, for example, $ u(0, y) = g(y) $, a general solution of this equation can be written as:

```{math}
u(x, y) = v(x, y) + w(x, y),
```

where $ v(x, y) $ is any solution of the non-homogeneous equation, and $ w(x, y) $ is a general solution of the homogeneous equation.

---

## Linear 2nd Order PDE

### Classification

The general form of the 2nd order PDE is given by:

```{math}
A(x, y) \frac{\partial^2 u}{\partial x^2} + B(x, y) \frac{\partial^2 u}{\partial x \partial y} + C(x, y) \frac{\partial^2 u}{\partial y^2} + D(x, y) \frac{\partial u}{\partial x} + E(x, y) \frac{\partial u}{\partial y} + F(x, y) u = R(x, y)
```

We will work with a specific form of Eq. (7.11):

```{math}
A \frac{\partial^2 u}{\partial x^2} + B \frac{\partial^2 u}{\partial x \partial y} + C \frac{\partial^2 u}{\partial y^2} = 0
```

where $ A $, $ B $, and $ C $ are constants. These equations are split into three groups according to the relations between coefficients $ A $, $ B $, and $ C $:

- $ B^2 > 4AC $ – hyperbolic equations; they describe propagating oscillations (waves).
- $ B^2 = 4AC $ – parabolic equations; they describe transport processes, such as heat conduction and diffusion.
- $ B^2 < 4AC $ – elliptic equations describe stationary systems, such as steady electric fields and temperature distributions.

### Solving 2nd Order PDE

Similarly to the case of the 1st order PDE, consider solutions in the form $ u(x, y) = f(p) $. To find a suitable form of the parameter $ p $, inspect partial derivatives of $ u(x, y) $ with respect to $ x $ and $ y $.

First derivatives are:

```{math}
\frac{\partial u}{\partial x} = \frac{df(p)}{dp} \frac{\partial p}{\partial x}, \quad \frac{\partial u}{\partial y} = \frac{df(p)}{dp} \frac{\partial p}{\partial y}
```

Then, second derivatives are:

```{math}
\frac{\partial^2 u}{\partial x^2} = \frac{\partial}{\partial x} \left( \frac{df(p)}{dp} \frac{\partial p}{\partial x} \right) = \frac{d^2 f(p)}{dp^2} \left( \frac{\partial p}{\partial x} \right)^2 + \frac{df(p)}{dp} \frac{\partial^2 p}{\partial x^2}
```

```{math}
\frac{\partial^2 u}{\partial y^2} = \frac{\partial}{\partial y} \left( \frac{df(p)}{dp} \frac{\partial p}{\partial y} \right) = \frac{d^2 f(p)}{dp^2} \left( \frac{\partial p}{\partial y} \right)^2 + \frac{df(p)}{dp} \frac{\partial^2 p}{\partial y^2}
```

If we request that:

```{math}
\frac{\partial p}{\partial x} = \text{Constant} \quad \text{and} \quad \frac{\partial p}{\partial y} = \text{Constant},
```

all second derivatives will have the same common factor of $ \frac{d^2 f(p)}{dp^2} $, which simplifies solving Equation (7.12).

It follows from the conditions $ \frac{\partial p}{\partial x} = \text{Constant} $ and $ \frac{\partial p}{\partial y} = \text{Constant} $ that parameter $ p $ is a linear function of $ x $ and $ y $ simultaneously. Therefore, we choose it in the form:

```{math}
p = ax + by,
```

where $ a $ and $ b $ are some constants. Thus, we can search for solutions of Eq. (7.12) in the form:

```{math}
u(x, y) = f(ax + by).
```

Then, calculate the derivatives for this particular form of the parameter $ p $ and substitute them in the original Equation (7.12). After the substitution, we obtain:

```{math}
-Aa^2 - B ab + Cb^2 = \frac{d^2 f(p)}{dp^2}
```

This equation is satisfied if either:

```{math}
\frac{d^2 f(p)}{dp^2} = 0 \quad \text{or} \quad Aa^2 + Bab + Cb^2 = 0.
```
### Condition for $ \frac{d^2 f(p)}{dp^2} = 0 $

The condition $ \frac{d^2 f(p)}{dp^2} = 0 $ means that $ f(p) $ is a linear function of $ p $. Integrating this equation gives:

```{math}
\frac{df(p)}{dp} = k \quad \text{and} \quad f(p) = k p + m,
```

where $ k $ and $ m $ are some constants.

Using the expression for $ p = ax + by $, we obtain a solution:

```{math}
u(x, y) = f(p) = k p + m = k(ax + by) + m = \alpha x + \beta y + \gamma,
```

where $ \alpha = ka $, $ \beta = kb $, and $ \gamma = m $. 

Importantly, this form of $ u(x, y) $ has only zero second derivatives. Thus, it is a trivial solution of Eq. (7.12) because any linear function of $ x $ and $ y $ is a solution of this equation.

### Non-trivial Solutions

Non-trivial solutions of Eq. (7.12) can be obtained by solving:

```{math}
A a^2 + B ab + C b^2 = 0.
```

This expression can be considered as a quadratic equation with respect to $ \beta = \frac{b}{a} $:

```{math}
C \beta^2 + B \beta + A = 0.
```

Solving it gives:

```{math}
\beta_{1,2} = \frac{-B \pm \sqrt{B^2 - 4AC}}{2C}.
```

Hence, parameter $ p $ may have two values:

```{math}
p_1 = a(x + \beta_1 y), \quad p_2 = a(x + \beta_2 y).
```

The prefactor $ a $ can be omitted without loss of generality, and we can write:

```{math}
p_1 = x + \beta_1 y, \quad p_2 = x + \beta_2 y.
```

Consequently, the solution $ u(x, y) $ becomes a superposition of two solutions:

```{math}
u(x, y) = f(x + \beta_1 y) + g(x + \beta_2 y),
```

where $ f $ and $ g $ are arbitrary functions.

### Discriminant and Classification

Note that we used the discriminant:

```{math}
D = B^2 - 4AC
```

of the quadratic equation:

```{math}
C \beta^2 + B \beta + A = 0.
```

The classification of the 2nd order PDE we have introduced above corresponds to different values of this discriminant:

1. **If $ B^2 > 4AC $**, the discriminant is positive, and $ \beta_1 $ and $ \beta_2 $ are real; such equations are called **hyperbolic**.
2. **If $ B^2 < 4AC $**, the discriminant is negative, i.e., $ \beta_1 $ and $ \beta_2 $ are complex; such equations are called **elliptic**.
3. **If $ B^2 = 4AC $**, the discriminant is zero, and $ \beta_1 = \beta_2 $; such equations are called **parabolic**.

### Example: Wave Equation vs Laplace Equation

Compare the two equations:

1. **Wave Equation**:

```{math}
\frac{\partial^2 v}{\partial x^2} - \frac{1}{c^2} \frac{\partial^2 v}{\partial t^2} = 0,
```

which corresponds to:

```{math}
\frac{B^2}{4AC} = 0,
```

and has two real roots $ \beta_1 = c $ and $ \beta_2 = -c $. Hence, the solution is:

```{math}
u(x, t) = f(x + ct) + g(x - ct).
```

2. **Laplace Equation**:

```{math}
\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0,
```

where:

```{math}
\frac{B^2}{4AC} = 0,
```

which has two imaginary roots $ \beta_1 = i $ and $ \beta_2 = -i $. Hence, its solution is:

```{math}
u(x, y) = f(x + iy) + g(x - iy).
```

### Parabolic Equation

Let us consider a special case where $ B = 4AC $. Then $ \beta_1 = \beta_2 $, and only one solution:

```{math}
u(x, y) = f\left( x - \frac{B y}{2C} \right)
```

exists. Similarly to the case of the 1st order PDE, we can try to find the second solution of the 2nd order PDE in the form:

```{math}
u(x, y) = h(x, y) g\left( x - \frac{B y}{2C} \right),
```

where $ g $ is an arbitrary function. The equation for $ h(x, y) $ can be obtained using the following considerations.

### Derivation of $ h(x, y) $

Calculate the first and second derivatives of $ u(x, y) $:

```{math}
\frac{\partial u}{\partial x} = \frac{\partial h}{\partial x} g(p) + h(x, y) \frac{dg(p)}{dp} \frac{\partial p}{\partial x},
```

```{math}
\frac{\partial u}{\partial y} = \frac{\partial h}{\partial y} g(p) + h(x, y) \frac{dg(p)}{dp} \frac{\partial p}{\partial y},
```

where $ p = x - \frac{B y}{2C} $. Substituting these into Eq. (7.12) and simplifying, we obtain an equation for $ h(x, y) $.

### General Solution

The general solution of the original PDE is:

```{math}
u(x, y) = f\left( x - \frac{B y}{2C} \right) + x g\left( x - \frac{B y}{2C} \right).
```

### Exercise

In the example above, $ h(x, y) = y $ also satisfies Eq. (7.14). What would be the general solution of Eq. (7.12) in this case? Demonstrate that it is equivalent to the solution given by Eq. (7.15). Hint: express $ x $ via $ p $ and $ y $.

## Poisson’s Equation

Green’s functions in 3-dimensional space.

Let us consider a linear PDE:

```{math}
L u(r) = \rho(r),
```

where $ L $ is a linear PDE operator. Similarly to the case of ODEs, assume that we can find the solution $ u(r) $ with the help of Green’s function $ G(r, r_0) $:

```{math}
u(r) = \int G(r, r_0) \rho(r_0) \, d^3 r_0. \tag{7.16}
```

(Here and below, $ d^3r $ indicates integration over a volume in the space of coordinates $ r $. Similarly, $ d^2r $ indicates integration over a surface.)

Substitute this function $ u(r) $ into the original PDE and observe that $ G(r, r_0) $ should satisfy:

```{math}
L G(r, r_0) = -\delta(r - r_0),
```

where $ r_0 $ is within the “volume of interest” $ V $.

Alternatively, $ G(r, r_0) $ can be obtained as:

```{math}
G(r, r_0) = \sum_{n=1}^{\infty} \frac{u_n(r) u_n^*(r_0)}{-\lambda_n},
```

where $ u_n(r) $ and $ \lambda_n $ (with $ n = 1, 2, 3, \dots $) are eigenfunctions and eigenvalues of the PDE operator $ L $.

### Divergence Theorem

Here and below, $ dS $ is a small element of the surface $ S $, and $ \mathbf{n} dS $ is a vector of magnitude $ dS $ oriented perpendicular to the surface element $ dS $.

For a sufficiently small but finite volume $ v $ enclosed by a surface $ s $, we can write:

```{math}
(\mathbf{r} \cdot \mathbf{a}) v \approx \mathbf{a} \cdot dS.
```

If a volume $ V $ is split into such small volumes $ v $, then summing over all $ v $ gives:

```{math}
\int_V (\mathbf{r} \cdot \mathbf{a}) dV = \int_S \mathbf{a} \cdot dS,
```

where $ S $ encloses the volume $ V $.

### Integral Form of Divergence

The integral form of the divergence is:

```{math}
\mathbf{r} \cdot \mathbf{a} = \lim_{V \to 0} \left( \int_S \mathbf{a} \cdot dS \right).
```

### Green’s Identity

If $ f(r) $ and $ g(r) $ are continuous differentiable scalar functions defined in a volume $ V $ enclosed by a surface $ S $, then one can construct vectors $ f(r) \nabla g(r) $ and $ g(r) \nabla f(r) $. Applying the divergence theorem to the first vector gives:

```{math}
\int_S (f \nabla g) \cdot dS = \int_V \nabla \cdot (f \nabla g) \, dV = \int_V \left[ f \nabla^2 g + (\nabla f) \cdot (\nabla g) \right] dV.
```

A similar expression for $ g(r) \nabla f(r) $ is:

```{math}
\int_S (g \nabla f) \cdot dS = \int_V \nabla \cdot (g \nabla f) \, dV = \int_V \left[ g \nabla^2 f + (\nabla g) \cdot (\nabla f) \right] dV.
```

By subtracting these two equations, we obtain:

```{math}
\int_S \left[ (f \nabla g) - (g \nabla f) \right] \cdot dS = \int_V \left[ f \nabla^2 g - g \nabla^2 f \right] dV. \tag{7.17}
```

This equality is called **Green’s second theorem**. Note that the terms in the square brackets on the left are vectors, and on the right are scalars.

### Solving Poisson’s Equation

Consider the equation:

```{math}
\nabla^2 u(r) = \rho(r).
```

To find the solution of it, use Green’s second theorem:

```{math}
\int_V \left[ -f \nabla^2 g - g \nabla^2 f \right] dV = \int_S \left[ f \nabla g - g \nabla f \right] \cdot dS.
```

Let us use $ f = u(r) $ and $ g = G(r, r_0) $. Then, according to Eq. (7.17), we have:

```{math}
\int_V \left[ u(r) \nabla^2 G(r, r_0) - G(r, r_0) \nabla^2 u(r) \right] dV = \int_S \left[ u(r) \frac{\partial G(r, r_0)}{\partial n} - G(r, r_0) \frac{\partial u(r)}{\partial n} \right] dS,
```

where the normal derivatives are defined as:

```{math}
\frac{\partial u(r)}{\partial n} = [\nabla u(r)] \cdot \mathbf{n}, \quad \frac{\partial G(r, r_0)}{\partial n} = [\nabla G(r, r_0)] \cdot \mathbf{n}.
```

When applied to Poisson’s equation, i.e., using the fact that $ \nabla^2 G(r, r_0) = -\delta(r - r_0) $ and $ \nabla^2 u(r) = \rho(r) $, Green’s theorem gives:

```{math}
\int_V \left[ u(r) \delta(r - r_0) - G(r, r_0) \rho(r) \right] dV = \int_S \left[ u(r) \frac{\partial G(r, r_0)}{\partial n} - G(r, r_0) \frac{\partial u(r)}{\partial n} \right] dS.
```

Since $ r_0 $ is inside $ V $, we obtain:

```{math}
u(r_0) = \int_V G(r, r_0) \rho(r) \, dV + \int_S \left[ u(r) \frac{\partial G(r, r_0)}{\partial n} - G(r, r_0) \frac{\partial u(r)}{\partial n} \right] dS.
```

If $ u(r) $ satisfies homogeneous boundary conditions, i.e., $ u(r) = 0 $ everywhere at the surface $ S $, then the surface integral can be eliminated by demanding that the same conditions apply to $ G(r, r_0) $, and we obtain the familiar expression (see Eq. 7.16):

```{math}
u(r_0) = \int_V G(r, r_0) \rho(r) \, dV.
```

## Boundary Conditions

Three types of boundary conditions are often considered:

1. Dirichlet: The value of $ u(r) $ is specified at each point of the boundary.
2. Neumann: The value of the normal derivative of $ u(r) $, i.e., $ \frac{\partial u}{\partial n} = \nabla u \cdot \mathbf{n} $, is specified at each point of the boundary.
3. Cauchy: Both $ u(r) $ and $ \frac{\partial u}{\partial n} $ are specified at each point of the boundary.

In the 3D case, these boundary conditions are specified on a 2D surface $ S $ bounding the volume $ V $.


### Dirichlet Boundary Conditions

Let us require that $ u(r) = f(r) $ everywhere on the surface $ S $. The expression for the function $ u(r_0) $ can be simplified if we demand that $ G(r, r_0) = 0 $ for all $ r \in S $. Then:

```{math}
u(r_0) = \int_V G(r, r_0) \rho(r) \, dV(r) + \int_S f(r) \frac{\partial G(r, r_0)}{\partial n} \, dS(r).
```

Since functions $ \rho(r) $ and $ f(r) $ are known, all that is left to do is to find $ G(r, r_0) $, which satisfies Dirichlet boundary conditions.

To this end, consider $ G(r, r_0) $ as a sum of two contributions:

```{math}
G(r, r_0) = F(r, r_0) + H(r, r_0),
```

where function $ F(r, r_0) $, called the fundamental solution, is defined so as:

```{math}
\nabla^2 G(r, r_0) = \nabla^2 F(r, r_0) = -\delta(r - r_0),
```

i.e., $ F(r, r_0) $ corresponds to sources of, e.g., the electrostatic potential, inside volume $ V $. However, it does not necessarily satisfy the boundary conditions. Therefore, function $ H(r, r_0) $ is chosen so as:

```{math}
\nabla^2 H(r, r_0) = 0
```

inside volume $ V $, i.e., it corresponds to no sources inside $ V $, and it is fitted in such a way that the sum of $ F(r, r_0) $ and $ H(r, r_0) $ is required to satisfy the boundary conditions:

```{math}
G(r, r_0) = F(r, r_0) + H(r, r_0) = 0 \quad \text{for all } r \in S.
```

### Method of Images

A practical method for finding such $ G(r, r_0) $ is called the **Method of Images**. This method is applied in three steps as follows:

1. **Determine the fundamental solution** $ F(r, r_0) $ from $ \nabla^2 F(r, r_0) = -\delta(r - r_0) $ and appropriate boundary conditions. For example, for a 3D case and $ F(r, r_0) \to 0 $ for $ r \to \infty $:

```{math}
F(r, r_0) = -\frac{1}{4 \pi |r - r_0|}.
```

2. **Add image sources outside $ V $**: Position the sources at the points $ r_n $ and assign them amplitudes $ q_n $, where $ n = 1, 2, \dots, N $ and $ N $ is some integer. These sources can be represented as a superposition of delta functions:

```{math}
\sum_{n=1}^{N} q_n \delta(r - r_n).
```

Note that at this point the values of $ q_n $ and $ r_n $ (for $ n = 1, 2, \dots, N $) are undefined.

3. **Use the fact that sources outside $ V $** satisfy Laplace's equation (not Poisson’s) inside $ V $. Hence, we can write:

```{math}
G(r, r_0) = 0 \quad \text{for } r \in S.
```

### Neumann Boundary Conditions

Here, we request that the normal derivative of the function $ u(r) $ is known everywhere at the surface $ S $:

```{math}
\frac{\partial u}{\partial n} = f(r) \quad \text{for } r \in S.
```

Use this to simplify the general expression for $ u(r_0) $:

```{math}
u(r_0) = \int_V G(r, r_0) \rho(r) \, dV(r) + \int_S \left[ u(r) \frac{\partial G(r, r_0)}{\partial n} - G(r, r_0) \frac{\partial u(r)}{\partial n} \right] \, dS(r).
```
obtained earlier. Also, notice that, according to the **divergence theorem**:

```{math}
\int_S f(r) \, dS = \int_V \nabla \cdot \mathbf{n} \, dS = \int_V \nabla^2 u \, dV = \int_V \rho(r) \, dV.
```

The same condition for the corresponding Green’s function reads:

```{math}
\int_{S} \frac{\partial G(r, r_0)}{\partial n} \, dS = \int_S \mathbf{r} \cdot \mathbf{G} \, dS = \int_V \nabla^2 G \, dV = \int_V -\delta(r - r_0) \, dV = 1.
```

Therefore, we cannot request that:

```{math}
\frac{\partial G(r, r_0)}{\partial n} = 0 \quad \text{for} \quad r \in S.
```

However, in order to choose the simplest possible value for $ \frac{\partial G(r, r_0)}{\partial n} $, we can request that:

```{math}
\frac{\partial G(r, r_0)}{\partial n} = \frac{1}{A} \quad \text{for} \quad r \in S,
```

where $ A $ is the total area of the bounding surface $ S $.

### Solution to Neumann's Boundary Problem

With this, the solution of the **Neumann boundary problem** becomes:

```{math}
u(r_0) = \int_V G(r, r_0) \rho(r) \, dV + A^{-1} \int_S u(r) \, dS - \int_S G(r, r_0) f(r) \, dS.
```

Note that $ \frac{1}{A} \int_S u(r) \, dS $ is a constant equal to the average value of $ u(r) $ at the surface $ S $. If, for an infinite volume $ V $, we request that $ u(r) \to 0 $ as $ |r| \to \infty $, this term can be eliminated.

## Problems - PDEs

1. Verify that any function of $ p $, where $ p = x^2 + 2y $, is a solution of:

```{math}
\frac{\partial u}{\partial x} = x \frac{\partial u}{\partial y}.
```

Then, determine whether $ v(x, y) $ is a solution of this PDE if:

1. $ v(x, y) = x^4 + 4x^2y + 4y^2 $,
2. $ v(x, y) = x^4 + 2x^2y + y^2 $,
3. $ v(x, y) = x^2(x^2 - 4) + 4y(x^2 - 2) + 4(y^2 - 1) $.

2. Find solutions of the PDE:

```{math}
\frac{1}{x} \frac{\partial u}{\partial x} + \frac{1}{y} \frac{\partial u}{\partial y} = 0,
```

with the following boundary conditions:

1. $ u(0, y) = y $ (one-dimensional boundary condition),
2. $ u(1, 1) = 1 $ (zero-dimensional boundary condition).

3. Find solutions of the PDE:

```{math}
\sin x \frac{\partial u}{\partial x} + \cos x \frac{\partial u}{\partial y} = \cos x,
```

with the following boundary conditions:

1. $ u(\pi/2, y) = 0 $,
2. $ u(\pi/2, y) = y(y + 1) $.

4. Find the general solution of the PDE:

```{math}
\frac{\partial^2 u}{\partial x^2} - 3 \frac{\partial^2 u}{\partial x \partial y} + 2 \frac{\partial^2 u}{\partial y^2} = 0,
```

and then:

1. Find $ u(x, y) $, for which $ u(x, 0) = -x^2 $ and $ \frac{\partial u}{\partial y}(x, 0) = 0 $,
2. Find the value of $ u(0, 1) $ for such $ u(x, y) $.

