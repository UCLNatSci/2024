# Green’s functions

## Definition

We can represent the left-hand-side of an ODE

```{math}
a_n(x)y^{(n)} + a_{n-1}(x)y^{(n-1)} + \dots + a_2(x)y'' + a_1(x)y' + a_0(x)y = f(x)
```

in the form

```{math}
L(x)y(x) = f(x),
```

where the operator $L(x)$ is

```{math}
L(x) = a_n(x)\frac{d^n}{dx^n} + a_{n-1}(x)\frac{d^{n-1}}{dx^{n-1}} + \dots + a_1(x)\frac{d}{dx} + a_0(x).
```

Let us suppose that there is a function $G(x, t)$, such that the solution of this equation is derived by integrating $f(x)$ with $G(x,t)$:

```{math}
y(x) = \int_a^b G(x, t)f(t) \,\mathrm{d}t,
```

where $a \leq x \leq b$.

A question to ask is *Does $G(x,t)$ exist and, if so, how to find it?*

Let us derive a differential equation with respect to $G(x, t)$. Apply the operator $L(x)$ to both sides of the equation:

```{math}
L(x)y(x) = f(x) = \int_a^b L(x)G(x,t)f(t) \,\mathrm{d}t,
```

Note that the integral is a definite one: $a$ and $b$ define the interval of possible values of $x$.

The operator $L(x)$ in the RHS here is acting on the function $G(x, t)$ only; it does not act on $f(t)$ because $L(x)$ depends on the variable $x$ and $f(t)$ depends on the variable $t$.

If we compare this equation with a definition of $f(x)$ using a Dirac delta function:

```{math}
f(x) = \int_a^b \delta(t - x) f(t) \,\mathrm{d}t.
```


Since the left-hand sides in each are the same, we have to equate their right-hand sides:

```{math}
\int_a^b \delta(t - x) f(t) \,\mathrm{d}t = \int_a^b L(x)G(x, t) f(t) \,\mathrm{d}t,
```

which means that

```{math}
\int_a^b \left[\delta(t - x) - L(x)G(x, t)\right] f(t) \,\mathrm{d}t = 0.
```

This equation is valid for any $f(t)$ if the function $G(x,t)$ satisfies:

```{math}
L(x)G(x, t) = \delta(t - x),
```

or

```{math}
\left[a_n(x) \frac{\mathrm{d}^n}{\mathrm{d}x^n} + a_{n-1}(x) \frac{\mathrm{d}^{n-1}}{\mathrm{d}x^{n-1}} + \dots + a_1(x) \frac{\mathrm{d}}{\mathrm{d}x} + a_0(x)\right] G(x, t) = \delta(t - x)
```

i.e., the function $G(x, t)$ should satisfy the same ODE as function $y(x)$, but with a specific right-hand side.

### Restrictions on $G(x,t)$:

1. Boundary conditions -  If, for example, $y(a) = y(b) = 0$, we can request that $G(a, t) = G(b, t) = 0$ for any value of $t$. Clearly, $y(x) = \int_a^b G(x, t)f(t) \,\mathrm{d}t $ will be satisfied in this case.

2. Continuity and discontinuity of $G(x, t)$, $G'(x, t)$, ..., $G^{(n-1)}(x, t)$ at $x = t$. (Remember that $\delta(t - x)$ is a generalized function which turns to infinity at $x = t$.)

### Continuity of $G(x, t)$ at $x = t$

Let us consider the 2nd order equation

```{math}
a_n(x) \frac{d^n}{dx^n} + a_{n-1}(x) \frac{d^{n-1}}{dx^{n-1}} + \dots + a_1(x) \frac{d}{dx} + a_0(x) G(x, t) = \delta(t - x),
```

where

```{math}
a_2(x) y''(x) + a_1(x) y'(x) + a_0(x) y(x) = f(x), \quad y(a) = y(b) = 0.
```

The Green's function for this equation should satisfy

```{math}
a_2(x) G''(x, t) + a_1(x) G'(x, t) + a_0(x) G(x, t) = \delta(x - t),
```

and

```{math}
G(a, t) = G(b, t) = 0.
```

### Investigate the behaviour of $ G(x, t) $ near the point $ x = t $

Integrate both parts of the equation for $ G(x, t) $ with respect to $ x $ near $ x = t $, i.e., in the interval $ x \in [t - \epsilon, t + \epsilon] $, where $ \epsilon $ is small, i.e.

```{math}
\int_{t-\epsilon}^{t+\epsilon}\left[a_2(x) \frac{\mathrm{d}^2}{\mathrm{d}x^2} + a_{1}(x) \frac{\mathrm{d}}{\mathrm{d}x} + a_0(x)\right] G(x, t)\,\mathrm{d}x = \int_{t - \epsilon}^{t + \epsilon} \delta(x - t)\mathrm{d}x
```

Integration of the right-hand side gives:

```{math}
\int_{t - \epsilon}^{t + \epsilon} \delta(x - t)\mathrm{d}x = 1.
```

Integration of the left-hand side gives three terms:

```{math}
I_0(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} a_0(x)\, G(x, t)\,\mathrm{d}x = 1.
```

```{math}
I_1(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} a_1(x) G'(x, t)\mathrm{d}x = \left[ a_1(x) G(x, t) \right]_{t - \epsilon}^{t + \epsilon} - \int_{t - \epsilon}^{t + \epsilon} a_1'(x)\, G(x, t)\,\mathrm{d}x
```

```{math}
I_2(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} a_2(x) G''(x, t)\mathrm{d}x = \left[ a_2(x) G'(x, t) \right]_{t - \epsilon}^{t + \epsilon}- \int_{t - \epsilon}^{t + \epsilon} a_2'(x)\, G'(x, t)\,\mathrm{d}x = \left[ a_2(x) G'(x, t) - a_2'(x) G(x, t)\right]_{t - \epsilon}^{t + \epsilon} + \int_{t - \epsilon}^{t + \epsilon} a_2''(x)\, G(x, t)\,\mathrm{d}x 
```

After rearranging the contributions in $ I_k(t, \epsilon) $, we obtain:

```{math}
I_0(t, \epsilon) + I_1(t, \epsilon) + I_2(t, \epsilon) = 1.
```

Thus, we have

```{math}
\int_{t - \epsilon}^{t + \epsilon} (a_0 - a_1'+a_2')\, G'(x, t)\,\mathrm{d}x  + 
 \left[ (a_1-a_2') G(x, t) \right]_{t + \epsilon}^{t - \epsilon} + \left[ a_2(x) G'(x, t) \right]_{t - \epsilon}^{t + \epsilon} = 1.
```

### Define the linear combinations of coefficients

We assume that coefficients $ a(x) $ and their derivatives are continuous functions. Then, their linear combinations are also continuous functions. For simplicity, set:

```{math}
p_0(x) = a_0(x) - a_1'(x) + a_2''(x), \quad p_1(x) = a_1(x) - a_2'(x), \quad p_2(x) = a_2(x).
```

Then, the equation becomes:

```{math}
\int_{t - \epsilon}^{t + \epsilon} p_0(x) G(x, t)\mathrm{d}x + \left[ p_1(x) G(x, t) \right]_{t - \epsilon}^{t + \epsilon} + \left[ p_2(x) G'(x, t) \right]_{t - \epsilon}^{t + \epsilon} = 1.
```

### Limit as $ \epsilon \to 0 $

Let us consider the limit of the left-hand side of the equation as $ \epsilon \to 0 $. Since $ p_k(x) $ are continuous functions, we can define $ J_k $ as:

```{math}
J_0 = \lim_{\epsilon \to 0} \int_{t - \epsilon}^{t + \epsilon} p_0(x) G(x, t)\mathrm{d}x = p_0(t) \lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right),
```

```{math}
J_1 = \lim_{\epsilon \to 0} \left[ p_1(x) G(x, t) \right]_{t + \epsilon}^{t - \epsilon} = p_1(t) \lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right),
```

```{math}
J_2 = \lim_{\epsilon \to 0} \left[ p_2(x) G'(x, t) \right]_{t + \epsilon}^{t - \epsilon} = p_2(t) \lim_{\epsilon \to 0} \left( G'(t + \epsilon, t) - G'(t - \epsilon, t) \right).
```

From the equation, we have:

```{math}
J_0 + J_1 + J_2 = 1.
```

## Continuity and Discontinuity Conditions

If we assume that $ G'(x, t) $ is continuous at $ x = t $, i.e.,

```{math}
\lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right) = 0,
```

then the continuity of $ G(x, t) $ and $ G(x, t) \,\mathrm{d}x $ holds, which leads to $ J_2 = 0 $, $ J_1 = 0 $, and $ J_0 = 0 $, contradicting the equation.

Alternatively, if we assume that $ G'(x, t) $ has a finite discontinuity at $ x = t $, i.e.,

```{math}
\lim_{\epsilon \to 0} \left( G'(t + \epsilon, t) - G'(t - \epsilon, t) \right) = 1,
```

then $ G(x, t) $ and $ G(x, t) \,\mathrm{d}x $ are continuous functions, i.e., $ J_2 = 1 $, $ J_1 = J_0 = 0 $, and consequently:

```{math}
J_0 + J_1 + J_2 = 1,
```

as required by the equation.

Thus, the continuity and discontinuity conditions for $ G(x, t) $ are:

```{math}
a_2(x)\lim_{\epsilon \to 0} \left( G'(t + \epsilon, t) - G'(t - \epsilon, t) \right) = 1,
```

```{math}
\lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right) = 0.
```



## Solving ODEs using Green’s function - an example.

Find the general solution of the inhomogeneous equation

```{math}
\frac{d^2y}{dx^2} + y = f(x),
```

where $ y(x) $ satisfies the boundary conditions $ y(0) = y(\frac{\pi}{2}) = 0 $. First, consider the ODE with respect to $ G(x, t) $:

```{math}
\frac{d^2G(x, t)}{dx^2} + G(x, t) = \delta(t - x),
```

and write down solutions for the homogeneous equation for $ x < t $ and $ x > t $ (note that these solutions should be different because of the discontinuity at $ x = t $):

```{math}
\begin{cases}
G(x, t) = A(t) \sin(x) + B(t) \cos(x), & \text{for } x < t, \\
G(x, t) = C(t) \sin(x) + D(t) \cos(x), & \text{for } x > t.
\end{cases}
```

### Boundary conditions and continuity conditions

Use the two boundary conditions and the continuity and discontinuity conditions to determine $ A(t), B(t), C(t), D(t) $.

From the boundary conditions, we have for $ x < t $:

```{math}
G(0, t) = A(t) \sin(0) + B(t) \cos(0) = 0 + B(t) = B(t) = 0.
```

For $ x > t $:

```{math}
G\left(\frac{\pi}{2}, t\right) = C(t) \sin\left(\frac{\pi}{2}\right) + D(t) \cos\left(\frac{\pi}{2}\right) = C(t) \cdot 1 + D(t) \cdot 0 = C(t) = 0.
```

Hence,

```{math}
G(x, t) =
\begin{cases}
A(t) \sin(x), & \text{for } x < t, \\
D(t) \cos(x), & \text{for } x > t.
\end{cases}
```

### Continuity and Discontinuity conditions

- **Continuity condition for $ G(x, t) $ at $ x = t $:**

```{math}
D(t) \cos(t) - A(t) \sin(t) = 0.
```

- **Discontinuity condition for $ G'(x, t) $ at $ x = t $:**

```{math}
-A(t) \cos(t) - D(t) \sin(t) = 1.
```

From these conditions, we find:

```{math}
A(t) = -\cos(t), \quad D(t) = -\sin(t).
```

### General solution using Green’s function

Now use this $ G(x, t) $ to find $ y(x) $:

```{math}
y(x) = \int_0^{\frac{\pi}{2}} G(x, t) f(t) \,\mathrm{d}t = \int_0^x G_{x > t}(x, t) f(t) \,\mathrm{d}t + \int_x^{\frac{\pi}{2}} G_{x < t}(x, t) f(t) \,\mathrm{d}t.
```

For $ x > t $:

```{math}
\int_x^{\frac{\pi}{2}} G(x, t) f(t) \,\mathrm{d}t = \int_x^{\frac{\pi}{2}} -\sin(t) \cos(x) f(t) \,\mathrm{d}t.
```

For $ x < t $:

```{math}
\int_0^x G(x, t) f(t) \,\mathrm{d}t = \int_0^x -\cos(t) \sin(x) f(t) \,\mathrm{d}t.
```

### Particular solution

Thus, a particular solution is:

```{math}
y(x) = x - \frac{\pi}{2} \sin(x).
```

### General solution

Taking into account the solutions of the homogeneous equation, we can write a general solution as:

```{math}
y(x) = x - \frac{\pi}{2} \sin(x) + a_1 \sin(x) + a_2 \cos(x).
```

However, since the boundary conditions demand that $ y(0) = y(\frac{\pi}{2}) = 0 $, the constants $ a_1 $ and $ a_2 $ are necessarily equal to zero. Thus, the general solution is:

```{math}
y(x) = x - \frac{\pi}{2} \sin(x).
```