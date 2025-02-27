# Partial Differential Equations

## Important PDEs

Consider a function $ u = u(x_1, x_2, \dots, x_n) $, which depends on $ n $ variables $ x_1, x_2, \dots, x_n $. In physical problems, these variables are usually spatial coordinates, e.g., $ x, y, z $, and time $ t $. Depending on the problem at hand, it can be convenient to consider the function $ u $ in Cartesian, polar, or spherical coordinate systems:

In Cartesian coordinates:  $u = u(x, y, z, t)$

In polar coordinates:  $u = u(r, \theta, z, t)$

In spherical coordinates:  $u = u(r, \theta, \phi, t)$

### The Wave Equation

In Cartesian coordinates:

```{math}
\nabla^2 u = \frac{1}{v^2} \frac{\partial^2 u}{\partial t^2}
```

In polar coordinates:

```{math}
\nabla^2 u = \left( \frac{\partial^2 u}{\partial r^2} + \frac{1}{r} \frac{\partial u}{\partial r} + \frac{1}{r^2} \left( \frac{\partial^2 u}{\partial \theta^2} + \frac{\partial^2 u}{\partial \phi^2} \right) \right)
```

In spherical coordinates:

```{math}
\nabla^2 u = \left( \frac{\partial^2 u}{\partial r^2} + \frac{2}{r} \frac{\partial u}{\partial r} + \frac{1}{r^2} \left( \frac{\partial^2 u}{\partial \theta^2} + \frac{\sin^2 \theta}{r} \frac{\partial^2 u}{\partial \phi^2} \right) \right)
```

where $ v $ is the wave velocity.

In the one-dimensional case, the wave equation is:

```{math}
\frac{\partial^2 u(x,t)}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 u(x,t)}{\partial t^2}
```

---

### The Diffusion Equation

```{math}
k \nabla^2 u = \frac{\partial u}{\partial t}
```

This equation is also used to describe heat flow.

---

### Laplace’s Equation

```{math}
\nabla^2 u = 0
```

---

### Poisson’s Equation

```{math}
\nabla^2 u = \rho({\bf r})
```

---

### Schrödinger’s Equation

```{math}
-\frac{\hbar^2}{2m}\nabla^2 u + V({\bf r}) u = \frac{i \hbar}{2m} \frac{\partial u}{\partial t}
```

## General form of the linear 1st order PDE
The general form of a linear first order partial differential equation with respect to function $ u(x,y) $ of two variables $ x $ and $ y $ can be written as:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} + C(x, y) u = R(x, y)
```

where $ A(x, y), B(x, y), C(x, y), $ and $ R(x, y) $ are functions of $ x $ and $ y $. Importantly, there could be many solutions due to:
1. Integrating constants
2. Existence of independent solutions.

### Case of $ C(x, y) = R(x, y) = 0 $

If $ C = R = 0 $, then the linear PDE equation becomes:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} = 0
```

Consider solutions of this equation in the form of:

```{math}
u(x, y) = f(p)
```

where $ p $ is a parameter formed by some fixed combination of $ x $ and $ y $ and hence $ p = p(x, y) $.

Using the multivariable chain rule we can obtain $ \frac{\partial u}{\partial x} $ and $ \frac{\partial u}{\partial y} $:

```{math}
\frac{\partial u(x, y)}{\partial x} = \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x}, \quad \frac{\partial u(x, y)}{\partial y} = \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial y}
```

Substituting these into our linear PDE equation and we obtain:

```{math}
\left[A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y}\right] \frac{df(p)}{\mathrm{d}p} = 0
```

This equation is satisfied if:

```{math}
\frac{df(p)}{\mathrm{d}p} = 0
```

which means that function $ f(p) $ is a constant, i.e., it has no dependence on $ p $ and, therefore, has no dependence on $ x $ and $ y $. Alternatively this equation is satisfied if:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} = 0
```

Notice that this equation is similar to our original linear PDE equation, in which $ u $ is replaced with $ p $.

On the other hand, for $ p $ to remain a constant combination of $ x $ and $ y $, we should have:

```{math}
\mathrm{d}p = \frac{\partial p}{\partial x}\mathrm{d}x + \frac{\partial p}{\partial y} dy = 0
```

Note that this equation is identical to our previous equation if we set:

```{math}
dx = \frac{A(x, y)}{B(x, y)} dy
```

Hence, instead of solving these two PDE equations directly, we can integrate the equation:
```{math}
\frac{\mathrm{d}x}{A(x, y)}  = \frac{\mathrm{d}y}{B(x, y)}
```
to find $ p $.

### Example

Consider the PDE:

```{math}
x^3 \frac{\partial u}{\partial x} + 3y^2 \frac{\partial u}{\partial y} = 0.
```
In this case, we have $ A(x, y) = x^3 $ and $ B(x, y) = 3y^2 $. Following the previous discussion, this equation is converted to
```{math}
\frac{dx}{x^3} = \frac{dy}{3y^2}.
```
After integration,
```{math}
-\frac{1}{2x^2} = -\frac{1}{3y} + C \quad \Rightarrow \quad \frac{1}{2x^2} = \frac{1}{3y} + C.
```
We can rearrange to find an expression for the constant here, which we will see is some fixed combination of $ x $ and $ y $ and denote it as $ p $ (as remember $\mathrm{d}p = 0$):
```{math}
C = \frac{1}{2x^2} - \frac{1}{3y} = \frac{3y - 2x^2}{6x^2y} = p.
```
Hence, the general solution of our PDE here is an arbitrary function of the argument $ \frac{3y - 2x^2}{6x^2y} $:
```{math}
u(x, y) = f \left( \frac{3y - 2x^2}{6x^2y} \right).
```

To find particular solutions, we have to introduce the boundary conditions. For example, if we demand that $ u(x, y) = 0 $ at the point where $ x = 2 $ and $ y = 2 $, then a *possible* particular solution is
```{math}
u(x, y) = \frac{3y - 2x^2}{6x^2y} + \frac{1}{24}.
```


### Case of $ R(x, y) = 0 $

If $ R = 0 $, our PDE equation becomes:

```{math}
A(x, y) \frac{\partial u}{\partial x} + B(x, y) \frac{\partial u}{\partial y} + C(x, y) u = 0
```

Apply the same logic as above but consider a solution in the form:

```{math}
u(x, y) = h(x, y) f(p)
```

In this case, we have:

```{math}
\frac{\partial u}{\partial x} = \frac{\partial h(x, y)}{\partial x} f(p) + h(x, y) \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x}
```

```{math}
\frac{\partial u}{\partial y} = \frac{\partial h(x, y)}{\partial y} f(p) + h(x, y) \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial y}
```

Substitute these derivatives into our PDE here:

```{math}
A(x, y) \left( \frac{\partial h}{\partial x} f(p) + h \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x} \right) + B(x, y) \left( \frac{\partial h}{\partial y} f(p) + h \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial y} \right) + C(x, y) h f(p) = 0
```

After rearranging the terms:

```{math}
\left[A(x, y) \frac{\partial h}{\partial x} + B(x, y) \frac{\partial h}{\partial y} + C(x, y)\,h\right]  f(p) + \left[A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} - \right]h \frac{df(p)}{\mathrm{d}p} = 0
```

The first term turns to zero if function $ h(x, y) $ is any solution of our PDE here. Let us assume that we have found such a function $ h(x, y) $. Then, only the second term remains:

```{math}
\left[A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y}\right] h \frac{df(p)}{\mathrm{d}p} = 0
```

Non-trivial solutions of this equation can be found by solving:

```{math}
A(x, y) \frac{\partial p}{\partial x} + B(x, y) \frac{\partial p}{\partial y} = 0
```

In other words, the problem is reduced to the previously considered case of $ C(x, y) = R(x, y) = 0 $.

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

Therefore, a general solution of our PDE here is given by:

```{math}
u(x, y) = h(x, y) f\left( x \exp\left(-\frac{y}{2}\right) \right),
```

where $ f $ is an arbitrary function.

It remains to find an expression for $ h(x, y) $. In the simplest case, we can consider $ h(x, y) $ as a function of $ x $ only. Therefore, the corresponding equation with respect to $ h(x) $

```{math}
A(x, y) \frac{\partial h}{\partial x} + B(x, y) \frac{\partial h}{\partial y} + C(x, y) h = 0
```
 is simplified to:
```{math}
x \frac{\partial h}{\partial x} - 2 h = 0
```

and its particular solution is $ h(x) = x^2 $.

Alternatively, we can consider $ h(x, y) $ as a function of $ y $ only. According to our PDE for $h(x, y)$ the corresponding equation with respect to $ h(y) $ is:

```{math}
2 \frac{\partial h}{\partial y} - 2h = 0,
```

which has a particular solution $ h(y) = e^y $.

Hence, the corresponding two sets of general solutions are:

```{math}
u_1(x, y) = x^2 f\left(x e^{-y/2} \right), \quad u_2(x, y) = e^y g\left(x e^{-y/2} \right),
```

where $ f $ and $ g $ are arbitrary functions of $ x \exp\left(-\frac{y}{2}\right) $. The superposition:

```{math}
u(x, y) = u_1(x, y) + u_2(x, y)
```

is also a solution of our PDE here.

### Homogeneity

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

## Linear 2nd Order PDEs

### Classification

The general form of the 2nd order PDE is given by:

```{math}
A(x, y) \frac{\partial^2 u}{\partial x^2} + B(x, y) \frac{\partial^2 u}{\partial x \partial y} + C(x, y) \frac{\partial^2 u}{\partial y^2} + D(x, y) \frac{\partial u}{\partial x} + E(x, y) \frac{\partial u}{\partial y} + F(x, y) u = R(x, y)
```

We will work with a specific form of this equation:

```{math}
A \frac{\partial^2 u}{\partial x^2} + B \frac{\partial^2 u}{\partial x \partial y} + C \frac{\partial^2 u}{\partial y^2} = 0
```

where $ A $, $ B $, and $ C $ are constants. These equations are split into three groups according to the relations between coefficients $ A $, $ B $, and $ C $:

- $ B^2 > 4AC $ – *hyperbolic equations*; they describe propagating oscillations (waves).
- $ B^2 = 4AC $ – *parabolic equations*; they describe transport processes, such as heat conduction and diffusion.
- $ B^2 < 4AC $ – *elliptic equations*; they describe stationary systems, such as steady electric fields and temperature distributions.

### Solving 2nd Order PDE

Similarly to the case of the 1st order PDE, consider solutions in the form $ u(x, y) = f(p) $. To find a suitable form of the parameter $ p $, inspect partial derivatives of $ u(x, y) $ with respect to $ x $ and $ y $.

First derivatives are:

```{math}
\frac{\partial u}{\partial x} = \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x}, \quad \frac{\partial u}{\partial y} = \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial y}
```

Then, second derivatives are:

```{math}
\frac{\partial^2 u}{\partial x^2} &= \frac{\partial}{\partial x} \left( \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x} \right) = \frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} \left( \frac{\partial p}{\partial x} \right)^2 + \frac{df(p)}{\mathrm{d}p} \frac{\partial^2 p}{\partial x^2} \\
\frac{\partial^2 u}{\partial y^2} &= \frac{\partial}{\partial y} \left( \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial y} \right) = \frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} \left( \frac{\partial p}{\partial y} \right)^2 + \frac{df(p)}{\mathrm{d}p} \frac{\partial^2 p}{\partial y^2} \\
\frac{\partial^2 u}{\partial y \partial x} &= \frac{\partial}{\partial y} \left( \frac{df(p)}{\mathrm{d}p} \frac{\partial p}{\partial x} \right) = \frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} \frac{\partial p}{\partial y} \frac{\partial p}{\partial x} + \frac{df(p)}{\mathrm{d}p} \frac{\partial^2 p}{\partial y \partial x} 
```

If we request that:

```{math}
\frac{\partial p}{\partial x} = \text{Constant} \quad \text{and} \quad \frac{\partial p}{\partial y} = \text{Constant},
```

all second derivatives will have the same common factor of $ \frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} $, which simplifies solving our second order PDE equation.

It follows from the conditions $ \frac{\partial p}{\partial x} = \text{Constant} $ and $ \frac{\partial p}{\partial y} = \text{Constant} $ that parameter $ p $ is a linear function of $ x $ and $ y $ simultaneously. Therefore, we choose it in the form:

```{math}
p = ax + by,
```

where $ a $ and $ b $ are some constants. Thus, we can search for solutions of second order PDE in the form:

```{math}
u(x, y) = f(ax + by).
```

Then, calculate the derivatives:

```{math}
\frac{\partial^2 u}{\partial x^2}, \quad \frac{\partial^2 u}{\partial x \partial y}, \quad \frac{\partial^2 u}{\partial y^2}
``` 
and substitute them into the original second order PDE, so that we obtain:

```{math}
\left(Aa^2 + B ab + Cb^2\right)\frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} = 0
```

This equation is satisfied if either:

```{math}
\frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} = 0 \quad \text{or} \quad Aa^2 + Bab + Cb^2 = 0.
```

The condition $ \frac{\mathrm{d}^2 f(p)}{\mathrm{d}p^2} = 0 $ means that $ f(p) $ is a linear function of $ p $. Integrating this equation gives:

```{math}
\frac{df(p)}{\mathrm{d}p} = k \quad \text{and} \quad f(p) = k p + m,
```

where $ k $ and $ m $ are some constants.

Using the expression for $ p = ax + by $, we obtain a solution:

```{math}
u(x, y) = f(p) = k p + m = k(ax + by) + m = \alpha x + \lambda y + \gamma,
```

where $ \alpha = ka $, $ \lambda = kb $, and $ \gamma = m $. 

Importantly, this form of $ u(x, y) $ has only zero second derivatives. Thus, it is a trivial solution of our second order PDE because any linear function of $ x $ and $ y $ is a solution of this equation.


Non-trivial solutions of the second order PDE here can be obtained by solving:

```{math}
A a^2 + B ab + C b^2 = 0.
```

This expression can be considered as a quadratic equation with respect to $ \lambda = \frac{b}{a} $:

```{math}
C \left(\frac{b}{a}\right)^2 + B \left(\frac{b}{a}\right) + A = 0.
```

Solving it gives:

```{math}
\left(\frac{b}{a}\right)_{1,2} = \lambda_{1,2} = \frac{-B \pm \sqrt{B^2 - 4AC}}{2C}.
```

Hence, parameter $ p $ may have two values:

```{math}
p_1 = a(x + \lambda_1 y), \quad p_2 = a(x + \lambda_2 y).
```

The prefactor $ a $ can be omitted without loss of generality, and we can write:

```{math}
p_1 = x + \lambda_1 y, \quad p_2 = x + \lambda_2 y.
```

Consequently, the solution $ u(x, y) $ becomes a superposition of two solutions:

```{math}
u(x, y) = f(x + \lambda_1 y) + g(x + \lambda_2 y),
```

where $ f $ and $ g $ are arbitrary functions.

### Discriminant and Classification

Note that we used the discriminant:

```{math}
D = B^2 - 4AC
```

of the quadratic equation:

```{math}
C \lambda^2 + B \lambda + A = 0.
```

The classification of the 2nd order PDE we have introduced above corresponds to different values of this discriminant:

1. If $ B^2 > 4AC $, the discriminant is positive, and $ \lambda_1 $ and $ \lambda_2 $ are real; such equations are called **hyperbolic**.
2. If $ B^2 < 4AC $, the discriminant is negative, i.e., $ \lambda_1 $ and $ \lambda_2 $ are complex; such equations are called **elliptic**.
3. If $ B^2 = 4AC $, the discriminant is zero, and $ \lambda_1 = \lambda_2 $; such equations are called **parabolic**.

### Example: Wave Equation vs Laplace Equation

Compare the two equations:

1. Wave Equation:

```{math}
\frac{\partial^2 v}{\partial x^2} - \frac{1}{c^2} \frac{\partial^2 v}{\partial t^2} = 0,
```

which corresponds to:

```{math}
1-\frac{\lambda^2}{c^2} = 0,
```

and has two real roots $ \lambda_1 = c $ and $ \lambda_2 = -c $. Hence, the solution is:

```{math}
u(x, t) = f(x + ct) + g(x - ct).
```

2. Laplace Equation:

```{math}
\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0,
```

where:

```{math}
1 + \lambda^2 = 0,
```

which has two imaginary roots $ \lambda_1 = i $ and $ \lambda_2 = -i $. Hence, its solution is:

```{math}
u(x, y) = f(x + iy) + g(x - iy).
```

### Parabolic Equation

Let us consider a special case where $ B = 4AC $. Then $ \lambda_1 = \lambda_2 $, and only one solution:

```{math}
u(x, y) = f\left( x - \frac{B}{2C}y \right)
```

exists. Similarly to the case of the 1st order PDE, we can try to find the second solution of the 2nd order PDE in the form:

```{math}
u(x, y) = h(x, y) g\left( x - \frac{B}{2C}y \right),
```

where $ g $ is an arbitrary function. The equation for $ h(x, y) $ can be obtained using the following considerations.

Calculate the first derivatives of $ u(x, y) $:

```{math}
\frac{\partial u}{\partial x} &= \frac{\partial h}{\partial x} g(p) + h \frac{\mathrm{d}g(p)}{\mathrm{d}p} \frac{\partial p}{\partial x} = \frac{\partial h}{\partial x} g(p) + h \frac{\mathrm{d}g(p)}{\mathrm{d}p} \\
\frac{\partial u}{\partial y} &= \frac{\partial h}{\partial y} g(p) + h \frac{\mathrm{d}g(p)}{\mathrm{d}p} \frac{\partial p}{\partial y} = \frac{\partial h}{\partial y} g(p) - h \frac{\mathrm{d}g(p)}{\mathrm{d}p} \frac{B}{2C}
```

and the second derivatives of $ u(x, y)$:

```{math}
\frac{\partial^2 u}{\partial x^2} &= \frac{\partial^2 h}{\partial x^2} g(p) + 2 \frac{\partial h}{\partial x} \frac{\mathrm{d}g(p)}{\mathrm{d}p} + h \frac{d^2 g(p)}{\mathrm{d}p^2}\\
\frac{\partial^2 u}{\partial x \partial y} &= \frac{\partial^2 h}{\partial x \partial y} g(p) + \frac{\partial h}{\partial x} \frac{\mathrm{d}g(p)}{\mathrm{d}p} - \frac{\partial h}{\partial y} \frac{\mathrm{d}g(p)}{\mathrm{d}p} \frac{B}{2C} - h \frac{d^2 g(p)}{\mathrm{d}p^2} \frac{B}{2C}\\
\frac{\partial^2 u}{\partial y^2} &= \frac{\partial^2 h}{\partial y^2} g(p) - 2 \frac{\partial h}{\partial y} \frac{\mathrm{d}g(p)}{\mathrm{d}p} \frac{B}{2C} + h \frac{d^2 g(p)}{\mathrm{d}p^2} \frac{B^2}{4C^2}
```

Substituting these into second order PDE and simplifying, we obtain an equation for $ h(x, y) $.

The contributions proportional to $\frac{\mathrm{d}g(p)}{\mathrm{d}p} $ and $\frac{d^2g(p)}{\mathrm{d}p^2} $ turn to zero exactly because $B^2 = 4AC$:

```{math}
\left( 2A \frac{\partial h}{\partial x} - B \frac{\partial h}{\partial x}\frac{B}{2C} \right) \frac{\partial h}{\partial x} \cdot \frac{\mathrm{d}g}{\mathrm{d}p} + \left( B \frac{\partial h}{\partial x} - 2C \frac{\partial h}{\partial y}\frac{B}{2C} \right) \frac{\partial h}{\partial y} \cdot \frac{\mathrm{d}g}{\mathrm{d}p} &= 0 \\
\left( A - \frac{B^2}{2C} + C\frac{B^2}{4C^2} \right) h \frac{d^2g(p)}{\mathrm{d}p^2} &= 0
```

Therefore, the equation with respect to $ h(x, y) $ is:

```{math}
\left( A \frac{\partial^2 h}{\partial x^2} + B \frac{\partial^2 h}{\partial x \partial y} + C \frac{\partial^2 h}{\partial y^2} \right) g = 0. 
```

We can use the simplest possible $h(x, y)$ that satisfies this equation, e.g., $ h(x, y) = x $.

Hence the general solution of the original second order PDE is:

```{math}
u(x, y) = f\left( x - \frac{B y}{2C} \right) + x g\left( x - \frac{B y}{2C} \right).
```

### Exercise

In the example above, $ h(x, y) = y $ also satisfies the second order PDE. What would be the general solution in this case? Demonstrate that it is equivalent to the solution given by the general form of the second order PDE. *Hint:* express $ x $ via $ p $ and $ y $.

## Poisson’s Equation

### Green’s functions in 3-dimensional space.

Let us consider a linear PDE:

```{math}
L \,u({\bf r}) = \rho({\bf r}),
```

where $ L $ is a linear PDE operator. Similarly to the case of ODEs, assume that we can find the solution $ u({\bf r} $ with the help of Green’s function $ G({\bf r}, {\bf r_0}) $:

```{math}
u({\bf r}) = \int G({\bf r}, {\bf r_0}) \rho({\bf r_0}) \, \mathrm{d}^3 {\bf r_0}
```

Note that here and below, $ \mathrm{d}^3 {\bf r} $ indicates integration over a volume in the space of coordinates $ {\bf r} $. Similarly, $ \mathrm{d}^2{\bf r}$ indicates integration over a surface.

Substitute this function $ u({\bf r}) $ into the original PDE and observe that $ G({\bf r},\, {\bf r_0}) $ should satisfy:

```{math}
L \,G({\bf r}, {\bf r_0}) = \delta({\bf r} - {\bf r_0}),
```

where $ {\bf r_0}$ is within the “volume of interest” $ V $.

Alternatively, $ G({\bf r}, {\bf r_0}) $ can be obtained as:

```{math}
G({\bf r}, {\bf r_0}) = \sum_{n=1}^{\infty} \frac{u_n({\bf r}) u_n^*({\bf r_0})}{-\lambda_n},
```

where $ u_n({\bf r}) $ and $ \lambda_n $ (with $ n = 1, 2, 3, \dots $) are eigenfunctions and eigenvalues of the PDE operator $ L $.

### Divergence Theorem

The integral form of divergence is 

```{math}
\nabla \cdot \mathbf{a} = \lim_{V \to 0} \left( \frac{1}{V} \int \mathbf{a} \cdot d\mathbf{S} \right)
```

Where here and below, $\mathrm{d}S $ is a small element of the surface $ S $, and $\mathrm{d}{\bf S} $ is a vector of magnitude $\mathrm{d}S $ oriented perpendicular to the surface element $\mathrm{d}S $.

For a suffici({\bf r})ently small but finite volume $ v $ enclosed by a surface $ s $, we can write:

```{math}
(\nabla \cdot \mathbf{a}) v \approx \int_s\mathbf{a} \cdot\mathrm{d}{\bf s}.
```

If a volume $ V $ is split into such small volumes $ v $, then summing over all $ v $ gives:

```{math}
\int_V (\nabla \cdot \mathbf{a}) \mathrm{d}V = \int_S \mathbf{a} \cdot\mathrm{d}{\bf s},
```

where $ S $ encloses the volume $ V $.

### Green’s Identity

If $ f({\bf r}) $ and $ g({\bf r}) $ are continuous differentiable *scalar* functions defined in a volume $V$ enclosed by a surface $S$, then one can construct vectors:
```{math} f({\bf r}) \nabla g({\bf r}) \quad \text{and} \quad g({\bf r}) \nabla f({\bf r})
```
Applying the divergence theorem to the first vector gives:

```{math}
\int_S (f \nabla g) \cdot\mathrm{d}s = \int_V \nabla \cdot (f \nabla g) \, \mathrm{d}V = \int_V \left[ f \nabla^2 g + (\nabla f) \cdot (\nabla g) \right] \mathrm{d}V.
```

A similar expression for $ g({\bf r}) \nabla f({\bf r}) $ is:

```{math}
\int_S (g \nabla f) \cdot\mathrm{d}s = \int_V \nabla \cdot (g \nabla f) \, \mathrm{d}V = \int_V \left[ g \nabla^2 f + (\nabla g) \cdot (\nabla f) \right] \mathrm{d}V.
```

By subtracting these two equations, we obtain:

```{math}
\int_S \left[ (f \nabla g) - (g \nabla f) \right] \cdot\mathrm{d}s = \int_V \left[ f \nabla^2 g - g \nabla^2 f \right] \mathrm{d}V. \tag{7.17}
```

This equality is called **Green’s second theorem**. Note that the terms in the square brackets on the left are vectors, and on the right are scalars.

### Poisson’s Equation

Consider the equation:

```{math}
\nabla^2 u({\bf r}) = \rho({\bf r}).
```

To find the solution of it, use Green’s second theorem:

```{math}
\int_V \left[ -f \nabla^2 g - g \nabla^2 f \right] \mathrm{d}V = \int_S \left[ f \nabla g - g \nabla f \right] \cdot\mathrm{d}s = \int_S \left( f \nabla g - g \nabla f \right) \cdot \mathbf{n}\mathrm{d}S
```

where $ \mathbf{n} $ is a vector of length 1 oriented perpendicular to the surface element $ \mathrm{d}S $.

Let us use $ f = u({\bf r}) $ and $ g = G({\bf r},\,{\bf r_0}) $. Then, according to Green's second theorem, we have:

```{math}
\int_V \left[ u({\bf r}) \nabla^2 G({\bf r},\,{\bf r_0}) - G({\bf r},\,{\bf r_0}) \nabla^2 u({\bf r}) \right] \mathrm{d}V = \int_S \left[ u({\bf r}) \frac{\partial G({\bf r}, \,{\bf r_0})}{\partial n} - G({\bf r}, \,{\bf r_0}) \frac{\partial u({\bf r})}{\partial n} \right]\mathrm{d}S,
```

where the normal derivatives are defined as:

```{math}
\frac{\partial u({\bf r})}{\partial n} = [\nabla u({\bf r})] \cdot \mathbf{n}, \quad \frac{\partial G({\bf r}, \,{\bf r_0})}{\partial n} = [\nabla_r G({\bf r}, \,{\bf r_0})] \cdot \mathbf{n}.
```

When applied to Poisson’s equation, i.e., using the fact that:
```{math}
\nabla^2 G({\bf r}, \,{\bf r_0}) = \delta({\bf r} - {\bf r_0}) \quad \text{and} \quad \nabla^2 u({\bf r}) = \rho({\bf r})
```
then Green’s theorem gives:

```{math}
\int_V \left[ u({\bf r}) \delta({\bf r} - {\bf r_0}) - G({\bf r}, \,{\bf r_0}) \rho({\bf r}) \right] \mathrm{d}V = \int_S \left[ u({\bf r}) \frac{\partial G({\bf r}, \,{\bf r_0})}{\partial n} - G({\bf r}, \,{\bf r_0}) \frac{\partial u({\bf r})}{\partial n} \right]\mathrm{d}S({bf r})
```
where $\mathrm{d}V ({bf r})$ and $\mathrm{d}S({\bf r})$ signify that the integration is carried out in the space of coordinates $\bf r$. Since $ \bf r_0 $ is inside $ V $, we obtain:

```{math}
u({\bf r_0}) = \int_V G({\bf r}, \,{\bf r_0}) \rho({\bf r}) \, \mathrm{d}V + \int_S \left[ u({\bf r}) \frac{\partial G({\bf r}, \,{\bf r_0})}{\partial n} - G({\bf r}, \,{\bf r_0}) \frac{\partial u({\bf r})}{\partial n} \right]\mathrm{d}s.
```

If $ u({\bf r}) $ satisfies homogeneous boundary conditions, i.e., $ u({\bf r}) = 0 $ everywhere at the surface $ S $, then the surface integral can be eliminated by demanding that the same conditions apply to $ G({\bf r}, \,{\bf r_0}) $, and we obtain the familiar expression of a Green's function:

```{math}
u({\bf r_0}) = \int_V G({\bf r}, \,{\bf r_0}) \rho({\bf r}) \, \mathrm{d}V.
```

## Boundary Conditions

Three types of boundary conditions are often considered:

1. *Dirichlet:* The value of $ u({\bf r}) $ is specified at each point of the boundary.

2. *Neumann:* The value of the normal derivative of $ u({\bf r}) $, i.e., 
```{math} 
\frac{\partial u}{\partial n} = \nabla u \cdot \mathbf{n}
```
is specified at each point of the boundary.

3. *Cauchy:* Both $ u({\bf r}) $ and $ \frac{\partial u}{\partial n} $ are specified at each point of the boundary.

In the 3D case, these boundary conditions are specified on a 2D surface $ S $ bounding the volume $ V $.


### Dirichlet Boundary Conditions

Let us require that $ u({\bf r}) = f({\bf r}) $ everywhere on the surface $ S $. The expression for the function $ u(r_0) $ can be simplified if we demand that $ G({\bf r},\,{\bf r_0}) = 0 $ for all $ r \in S $. Then:

```{math}
u(r_0) = \int_V G({\bf r},\,{\bf r_0}) \rho({\bf r}) \, \mathrm{d}V({\bf r}) + \int_S f({\bf r}) \frac{\partial G({\bf r},\,{\bf r_0})}{\partial n} \,\mathrm{d}s({\bf r}).
```

Since functions $ \rho({\bf r}) $ and $ f({\bf r}) $ are known, all that is left to do is to find $ G({\bf r},\,{\bf r_0}) $, which satisfies Dirichlet boundary conditions.

To this end, consider $ G({\bf r},\,{\bf r_0}) $ as a sum of two contributions:

```{math}
G({\bf r},\,{\bf r_0}) = F({\bf r},\,{\bf r_0}) + H({\bf r},\,{\bf r_0}),
```

where function $ F({\bf r},\, {\bf r_0}) $, called the *fundamental solution*, is defined so as:

```{math}
\nabla^2 G({\bf r},\,{\bf r_0}) = \nabla^2 F({\bf r},\,{\bf r_0}) = \delta(r - r_0),
```

i.e., $ F({\bf r},\,{\bf r_0}) $ corresponds to sources of, e.g., the electrostatic potential, *inside* volume $ V $. However, it does not necessarily satisfy the boundary conditions. Therefore, function $ H({\bf r},\,{\bf r_0}) $ is chosen so as:

```{math}
\nabla^2 H({\bf r},\,{\bf r_0}) = 0
```

inside volume $ V $, i.e., it corresponds to no sources inside $ V $, and it is fitted in such a way that the sum of $ F({\bf r},\, {\bf r_0}) $ and $ H({\bf r},\, {\bf r_0}) $ is required to satisfy the boundary conditions:

```{math}
G({\bf r},\, {\bf r_0}) = F({\bf r},\, {\bf r_0}) + H({\bf r},\, {\bf r_0}) = 0
```
for all $\bf r$ at the surface $S$ enclosing volume $V$ .

### Method of Images

A practical method for finding such $ G({\bf r},\, {\bf r_0}) $ is called the *Method of Images*. This method is applied in three steps as follows:

1. Determine the fundamental solution $ F({\bf r},\, {\bf r_0}) $ from:
```{math} \nabla^2 F({\bf r},\, {\bf r_0}) = \delta(r - r_0)
```
and appropriate boundary conditions. For example, for a 3D case and $ F({\bf r},\, {\bf r_0}) \to 0 $ for $ {\bf r} \to \infty $:

```{math}
F({\bf r},\, {\bf r_0}) = -\frac{1}{4 \pi |r - r_0|}.
```

2. Add image sources *outside* $ V $: Position the sources at the points $ {\bf r}_n $ and assign them amplitudes $ q_n $, where $ n = 1, 2, \dots, N $ and $ N $ is some integer. These sources can be represented as a superposition of delta functions:

```{math}
\sum_{n=1}^{N} q_n\, \delta({\bf r} - {\bf r}_n).
```

Note that at this point the values of $ q_n $ and $ {\bf r}_n $ (for $ n = 1, 2, \dots, N $) are undefined.

3. Note that sources *outside* $ V $ satisfy Laplace's equation (not Poisson’s) *inside* $ V $. Hence, we can write:

```{math}
G({\bf r},\, {\bf r_0}) = F({\bf r},\, {\bf r_0}) + \sum_{n=1}^N q_n\,F({\bf r},\, {\bf r}_n)
```
And fit parameters $q_n$ and ${\bf r}_n$ ($n = 1, 2, \dots, N$) so as to guarantee that $G({\bf r},\, {\bf r_0}) = 0 \quad \text{for } r \in S.$

### Neumann Boundary Conditions

Here, we request that the normal derivative of the function $ u({\bf r}) $ is known everywhere at the surface $ S $:

```{math}
\frac{\partial u}{\partial n} = f({\bf r}) \quad \text{for } r \in S.
```

Use this to simplify the general expression for $ u({\bf r_0}) $:

```{math}
u({\bf r_0}) = \int_V G({\bf r},\, {\bf r_0}) \rho({\bf r}) \, \mathrm{d}V({\bf r}) + \int_S \left[ u({\bf r}) \frac{\partial G({\bf r},\, {\bf r_0})}{\partial n} - G({\bf r},\, {\bf r_0}) \frac{\partial u({\bf r})}{\partial n} \right] \,\mathrm{d}S({\bf r}).
```
obtained earlier. Also, notice that, according to the divergence theorem:

```{math}
\int_S f({\bf r}) \,\mathrm{d}S = \int_V \nabla \cdot \mathbf{n} \,\mathrm{d}S = \int_V \nabla^2 u \, \mathrm{d}V = \int_V \rho({\bf r}) \, \mathrm{d}V.
```

The same condition for the corresponding Green’s function reads:

```{math}
\int_{S} \frac{\partial G({\bf r},\, {\bf r_0})}{\partial n} \,\mathrm{d}^2{\bf r} = \int_S \nabla G\,\cdot{\bf n} \,\mathrm{d}^2{\bf r} = \int_V \nabla^2 G \, \mathrm{d}^3{\bf r} = \int_V \delta({\bf r} - {\bf r_0}) \, \mathrm{d}V^3{\bf r}= 1.
```

Therefore, we cannot request that:

```{math}
\frac{\partial G({\bf r},\, {\bf r_0})}{\partial n} = 0 \quad \text{for} \quad r \in S.
```

However, in order to choose the simplest possible value for $ \frac{\partial G({\bf r},\, {\bf r_0})}{\partial n} $, we can request that:

```{math}
\frac{\partial G({\bf r},\,{\bf r_0})}{\partial n} = \frac{1}{A} \quad \text{for} \quad r \in S,
```

where $ A $ is the total area of the bounding surface $ S $.

With this, the solution of the Neumann boundary problem becomes:

```{math}
u({\bf r_0}) = \int_V G({\bf r},\,{\bf r_0}) \rho({\bf r}) \, \mathrm{d}V + A^{-1} \int_S u({\bf r}) \,\mathrm{d}s - \int_S G({\bf r},\,{\bf r_0}) f({\bf r}) \,\mathrm{d}s.
```

Note that 
```{math}
\frac{1}{A} \int_S u({\bf r}) \,\mathrm{d}s
```
is a constant equal to the average value of $ u({\bf r}) $ at the surface $ S $. If, for an infinite volume $ V $, we request that $ u({\bf r}) \to 0 $ as $ |r| \to \infty $, this term can be eliminated.

## Using Integral Transforms to Solve PDEs

We have already introduced the Laplace integral transform and used it in order to solve ordinary differential equations. Here we will use Laplace and Fourier integral transforms to solve partial differential equations. The strategy of the integral transform method is to reduce the number of variables in a PDE and convert it to a simpler PDE or an ordinary differential equation.

### Laplace Transform

The Laplace transform is a natural method of choice if the problem concerns a process where at least one of the variables can have values from zero to infinity. We will demonstrate the application of integral transforms to solving PDEs using specific examples.

**A example:**
Consider a semi-infinite tube filled initially with pure water and brought in contact with a salt solution maintained at a fixed concentration. Find the total amount of salt diffused into the tube by time $t$ if the diffusion constant is $k$.

The semi-infinite tube is a one-dimensional system. Therefore, the concentration of salt in the tube, $u$, can be described using two variables only: $x$ – the distance from the salt container, and $t$ – duration of the contact. Hence, $u = u(x, t)$.

The diffusion process is described by the equation:

```{math}
k \frac{\partial^2 u(x, t)}{\partial x^2} = \frac{\partial u(x, t)}{\partial t}
```

with the following conditions:

- $u(0, t) = u_0$, i.e., the concentration of the salt solution "at the source" is the same at all times.
- $u(x, 0) = 0$, i.e., the tube contained pure water before it was brought into contact with the salt reservoir at $t = 0$.
- $u(\infty, t) = 0$, i.e., salt will never reach the far end of the semi-infinite tube.
- $u(x, t)$ is finite for all $x$ and $t$.

Our strategy is to convert this PDE into an ODE by eliminating the dependence on one of the variables. Taking the Laplace transform of both sides with respect to $t$ gives:

```{math}
k \int_0^\infty \frac{\partial^2 u}{\partial x^2} e^{-st} \,\mathrm{d}t= \int_0^\infty \frac{\partial u}{\partial t} e^{-st} \,\mathrm{d}t.
```

Swap the order of the $\frac{\partial^2}{\partial x^2}$ and the $\int \dots\mathrm{d}t$ operations:

```{math}
k \frac{\partial^2}{\partial x^2} \left( \int_0^\infty u(x, t) e^{-st} \,\mathrm{d}t\right) = k \frac{\partial^2}{\partial x^2} U(x, s),
```

where $U(x, s)$ is the Laplace transform of $u(x, t)$. Integrate the right-hand side by parts:

```{math}
\int_0^\infty \frac{\partial u}{\partial t} e^{-st} \,\mathrm{d}t= u(x, t) e^{-st} \Big|_0^\infty + s \int_0^\infty u(x, t) e^{-st} \,\mathrm{d}t= s U(x, s) - u(x, 0).
```

Taking into account the boundary condition $u(x, 0) = 0$, the diffusion equation becomes:

```{math}
k \frac{\partial^2}{\partial x^2} U(x, s) = s U(x, s). 
```

This is an ordinary differential equation with respect to $U(x, s)$. The solution to this equation is:

```{math}
U(x, s) = A(s) \exp \left( \sqrt{\frac{s}{k}} x \right) + B(s) \exp \left( - \sqrt{\frac{s}{k}} x \right), 
```

where $A(s)$ and $B(s)$ are, in general, functions of $s$. Only one of the terms in this equation is physically meaningful for this problem. Since $u(\infty, t) = 0$, we have:

```{math}
U(x, s) = B(s) \exp \left( - \sqrt{\frac{s}{k}} x \right).
```

Function $B(s)$ can be determined from the boundary conditions by calculating the Laplace transform of $u(0, t) = u_0$:

```{math}
U(0, s) = \int_0^\infty u_0 e^{-st} \,\mathrm{d}t= u_0 \int_0^\infty e^{-st} \,\mathrm{d}t= \frac{u_0}{s}.
```

Hence,

```{math}
U(x, s) = \frac{u_0}{s} \exp \left( - \sqrt{\frac{s}{k}} x \right).
```

Now, using a table of Laplace transforms, we can find the appropriate function $u(x, t)$:

```{math}
u(x, t) = u_0 \left[ 1 - \text{erf} \left( \frac{x}{\sqrt{4kt}} \right) \right],
```

where

```{math}
\text{erf}(x) = \frac{2}{\sqrt{\pi}} \int_0^x e^{-p^2} \, \mathrm{d}p.
```

Finally, to find the total amount of salt diffused into the tube, we calculate:

```{math}
w(t) = \int_0^\infty u(x, t) \,\mathrm{d}x.
```

However, since the problem requires only $ w(t) $, we do not need to find $ u(x,t) $ explicitly.

To find $ w(t) $, we consider the Laplace transform of $ w(t) $:

```{math}
W(s) = \int_0^\infty w(t) e^{-st}\mathrm{d}t= \int_0^\infty \left( \int_0^\infty u(x,t)\mathrm{d}x \right) e^{-st}\mathrm{d}t= \int_0^\infty \left( \int_0^\infty u(x,t)  e^{-st}\mathrm{d}t\right)dx
```

The inner integral is the Laplace transform of $ u(x,t) $, and hence:

```{math}
W(s) = \int_0^\infty U(x,s)\mathrm{d}x
```

Substituting $ U(x, s) $, the integral can be evaluated:

```{math}
W(s) = \frac{u_0}{\sqrt{k}} \int_0^\infty e^{-\sqrt{\frac{s}{k}} x}\mathrm{d}x = \frac{u_0}{\sqrt{k}} \cdot \frac{1}{\sqrt{s}}
```

Thus:

```{math}
W(s) = \frac{u_0}{\sqrt{k s}}
```

Finally, $ w(t) $ can be found by consulting a table of Laplace transforms:

```{math}
w(t) = \frac{u_0 \sqrt{k}}{\sqrt{\pi}} t^{-1/2}
```


### Convolution Theorem in Laplace Transforms

Recall that the product $ H(p) G(p) $, where $ H(p) $ and $ G(p) $ are Laplace transforms of $ h(t) $ and $ g(t) $, respectively.

```{math}
H(p) G(p) = \int_0^\infty h(s) e^{-ps}\mathrm{d}s \int_0^\infty g(t) e^{-pt}\mathrm{d}t= \int_0^\infty \int_0^\infty h(s) g(t) e^{-p(s + t)}\mathrm{d}s\mathrm{d}t.
```
We can write this as:
```{math}
H(p) G(p) = \int_0^\infty \left( \int_0^r g(r - t) h(t) e^{-pr}\mathrm{d}t\right)\mathrm{d}r.
```

This inner integral is called the convolution of functions $ g(x) $ and $ h(x) $. 

```{math}
H(p) G(p) = \int_0^\infty [h \ast g] e^{-pr}\mathrm{d}r,
```

i.e., the Laplace transform of a convolution of functions $ h(x) $ and $ g(x) $ equals the product of the Laplace transforms of these functions. In other words, $ g \ast h $ is the inverse Laplace transform of $ H(p) G(p) $.

### Convolution in Fourier Transform

Let us consider two functions $ f(x) $ and $ g(x) $. Their Fourier transforms can be defined as

```{math}
F(k) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{+\infty} f(x) e^{-ikx} \, dx
```

and 

```{math}
G(k) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{+\infty} g(x) e^{-ikx} \, dx.
```

It follows that 

```{math}
F(k) G(k) = \frac{1}{(2\pi)} \int_{-\infty}^{+\infty} f(s) e^{-iks} \,\mathrm{d}s \int_{-\infty}^{+\infty} g(t) e^{-ikt} \,\mathrm{d}t.
```

Rewriting this, we get 

```{math}
F(k) G(k) = \frac{1}{(2\pi)} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(s) g(t) e^{-ik(s+t)} \,\mathrm{d}s \,\mathrm{d}t.
```

Note that other definitions of the Fourier transform may use a different factor in front of the integral.

Is it possible to give meaning to the product $ F(k) G(k) $? Rewrite $ F(k) G(k) $ as: 

```{math}
F(k) G(k) = \frac{1}{(2\pi)} \int_{-\infty}^{+\infty} f(s) e^{-iks} \,\mathrm{d}s \int_{-\infty}^{+\infty} g(t) e^{-ikt} \,\mathrm{d}t,
```
Which is:
```{math}
F(k) G(k) = \frac{1}{(2\pi)} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(s) g(t) e^{-ik(s+t)} \,\mathrm{d}s \,\mathrm{d}t
```
For any fixed $ t $, we can introduce a new variable $ p = s + t $. Then, $ s = p - t $ and $\mathrm{d}s =\mathrm{d}p $. Rewriting the last integral in terms of variables $ p $ and $ t $. Note that the integration limits remain unchanged:

```{math}
F(k) G(k) = \frac{1}{(2\pi)} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(p - t) g(t) e^{-ikp} \,\mathrm{d}p \,\mathrm{d}t. 
```

Change the order of integration with respect to $\mathrm{d}t $ and $\mathrm{d}p $ and multiply both parts of this last integral by $ \sqrt{2\pi}$

```{math}
\sqrt{2\pi} F(k) G(k) = \sqrt{2\pi} \int_{-\infty}^{+\infty} \left[ \int_{-\infty}^{+\infty} f(p - t) g(t) \,\mathrm{d}t \right] e^{-ikp} \,\mathrm{d}p. 
```

The integral in square brackets is the convolution (note that the integration limits are different from those defined for the case of the Laplace transform):

```{math}
f(x) \ast g(x) = \int_{-\infty}^{+\infty} f(p-t)\,g(t)\mathrm{d}t.
```

Thus the equation states that the product of the Fourier transforms of functions $ f(x) $ and $ g(x) $ is proportional to the Fourier transform of a convolution of these functions. This statement is called the *convolution theorem*.

We can also demonstrate that:

```{math}
f(x) \ast g(x) = \int_{-\infty}^{+\infty} f(p-t)\,g(t)\mathrm{d}t = \int_{-\infty}^{+\infty} f(t)\,g(p-t)\mathrm{d}t = g(x) \ast f(x)

```


**An example:** The temperature distribution in an infinite bar

An infinite metal bar has the initial temperature distribution along the bar $ f(x) $. Find the temperature distribution after time $ t $.

Let $ u(x,t) $ be the temperature at a point $ x $ along the bar at the time $ t $. Assume that the far ends of the bar remain cold, i.e.

```{math}
u(\pm \infty, t) = \frac{\partial u(x, t)}{\partial x} \Big|_{x=\pm \infty} = 0.
```

The temperature along the bar is described by the heat flow equation

```{math}
\frac{\partial^2 u}{\partial x^2} = \frac{\partial u}{\partial t}.
```

Natural boundary conditions for this problem are:
- The far ends of the bar remain cold: $ u(x,t) \to 0 $ for $ x \to \pm 1 $.
- The temperature does not change at the ends of the bar: $ \frac{\partial u(x, t)}{\partial x} \to 0 $ for $ x \to \pm 1 $.

Apply the Fourier transform to both parts of the equation:

```{math}
\frac{1}{2\pi} \int_{-\infty}^{+\infty} \frac{\partial^2 u}{\partial x^2} e^{-ikx}\mathrm{d}x = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \frac{\partial u}{\partial t} e^{-ikx}\mathrm{d}x.
```

The LHS can be integrated by parts:

```{math}
\int_{-\infty}^{+\infty} \frac{\partial^2 u}{\partial x^2} e^{-ikx}\mathrm{d}x = -k^2 \int_{-\infty}^{+\infty} u(x,t) e^{-ikx}\mathrm{d}x,
```

while in the RHS, $ \frac{\partial}{\partial t} $ can be moved outside of the integration. Thus, the PDE is transformed into:

```{math}
-k^2 U(k,t) = \frac{\partial U(k,t)}{\partial t}.
```

The latter equation has a solution of the form:

```{math}
U(k,t) = U(k,0) e^{-k^2 \alpha t}.
```

Function $ U(k,0) $ is defined from the initial condition at the time $ t = 0 $:

```{math}
U(k,0) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} u(x,0) e^{-ikx}\mathrm{d}x = F(k),
```

i.e. $ U(k,0) $ is given by the Fourier transform of the function $ f(x) $.

Thus,

```{math}
U(k,t) = 2\pi F(k)\, G(k,t),
```

where we introduced the function $ G(k,t) $ defined as:

```{math}
G(k,t) = e^{-k^2 \alpha t}.
```

Function $ G(k,t) $ can be considered as a Fourier transform of some function $ g(x,t) $. Since $ U(k,t) $ is represented as a product of two Fourier transforms, we can apply the convolution theorem to find $ u(x,t) $:

```{math}
u(x,t) = \int_{-\infty}^{+\infty} g(x-s,t) f(s)\mathrm{d}s.
```

In other words, the problem will be solved if we find function $ g(x,t) $ explicitly. Function $ g(x,t) $ can be found by the inverse Fourier transform of $ G(k,t) $:

```{math}
g(x,t) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{-k^2 \alpha t} e^{ikx} \mathrm{d}k.
```

To take this integral, first complete the square:

```{math}
g(x,t) = \frac{1}{\sqrt{4\pi \alpha t}} \int_{-\infty}^{+\infty} e^{-\frac{(k-ix)^2}{4\alpha t}} \mathrm{d}k.
```

Now, using the fact that:

```{math}
\int_{-\infty}^{+\infty} e^{-a s^2}\mathrm{d}s = \sqrt{\frac{\pi}{a}},
```

we obtain:

```{math}
g(x,t) = \frac{1}{\sqrt{4\pi \alpha t}} e^{-x^2/4\alpha t}.
```

Finally, the temperature distribution at time $ t $ can be calculated, using function $ g(x,\,t) $ and the initial temperature distribution $ f(x) $.

