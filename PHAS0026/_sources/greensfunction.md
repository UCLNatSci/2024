# Green’s functions

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
y(x) = \int_a^b G(x, t)f(t) \, dt,
```

where $a \leq x \leq b$.

A question to ask is *Does $G(x,t)$ exist and, if so, how to find it?*

Let us derive a differential equation with respect to $G(x, t)$. Apply the operator $L(x)$ to both sides of the equation:

```{math}
L(x)y(x) = f(x) = \int_a^b L(x)G(x,t)f(t) \, dt,
```

and compare this equation with

```{math}
f(x) = \int_a^b \delta(t - x) f(t) \, dt.
```

Note that the integral is a definite one: $a$ and $b$ define the interval of possible values of $x$.

The operator $L(x)$ in the RHS of Equation (3.7) is acting on the function $G(x, t)$ only; it does not act on $f(t)$ because $L(x)$ depends on the variable $x$ and $f(t)$ depends on the variable $t$.

Since the left-hand sides in Equations (3.7) and (3.8) are the same, we have to equate their right-hand sides:

```{math}
\int_a^b \delta(t - x) f(t) \, dt = \int_a^b L(x)G(x, t) f(t) \, dt,
```

which means that

```{math}
\int_a^b \left[\delta(t - x) - L(x)G(x, t)\right] f(t) \, dt = 0.
```

This equation is valid for any $f(t)$ if the function $G(x,t)$ satisfies:

```{math}
L(x)G(x, t) = \delta(t - x),
```

or

```{math}
L(x)G(x, t) = \delta(t - x),
```

i.e., the function $G(x, t)$ should satisfy the same ODE as function $y(x)$, but with a specific right-hand side.

### Other restrictions on $G(x,t)$:

1. **Boundary conditions**. If, for example, $y(a) = y(b) = 0$, we can request that $G(a, t) = G(b, t) = 0$ for any value of $t$. Clearly, Equation (3.6) will be satisfied in this case.

2. **Continuity and discontinuity of $G(x, t)$, $G'(x, t)$, ..., $G^{(n-1)}(x, t)$ at $x = t$**. (The function $\delta(t - x)$, see Equation (3.9), is a generalized function which turns to infinity at $x = t$.)

## Continuity of $G(x, t) at x = t$: 2nd order ODE

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

Integrate both parts of the equation for $ G(x, t) $ with respect to $ x $ near $ x = t $, i.e., in the interval $ x \in [t - \epsilon, t + \epsilon] $, where $ \epsilon $ is small. Integration of the right-hand side gives

```{math}
\int_{t - \epsilon}^{t + \epsilon} \delta(x - t) dx = 1.
```

Integration of the left-hand side gives three terms:

```{math}
I_0(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} \delta(x - t) dx = 1.
```

```{math}
I_1(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} a_1(x) G'(x, t) dx = \left[ a_1(x) G(x, t) \right]_{t - \epsilon}^{t + \epsilon}.
```

```{math}
I_2(t, \epsilon) = \int_{t - \epsilon}^{t + \epsilon} a_2(x) G''(x, t) dx = \left[ a_2(x) G'(x, t) \right]_{t - \epsilon}^{t + \epsilon}.
```

After rearranging the contributions in $ I_k(t, \epsilon) $, we obtain:

```{math}
I_0(t, \epsilon) + I_1(t, \epsilon) + I_2(t, \epsilon) = 1.
```

Thus, we have

```{math}
\left[ a_2(x) G'(x, t) \right]_{t + \epsilon}^{t - \epsilon} + \left[ a_1(x) G(x, t) \right]_{t + \epsilon}^{t - \epsilon} + \left[ a_0(x) G(x, t) \right]_{t - \epsilon}^{t + \epsilon} = 1.
```

### Define the linear combinations of coefficients

We assume that coefficients $ a(x) $ and their derivatives are continuous functions. Then, their linear combinations are also continuous functions. For simplicity, set:

```{math}
p_0(x) = a_0(x) - a_1(x) + a_2(x), \quad p_1(x) = a_1(x) - a_2(x), \quad p_2(x) = a_2(x).
```

Then, the equation becomes:

```{math}
\int_{t - \epsilon}^{t + \epsilon} p_0(x) G(x, t) dx + \left[ p_1(x) G(x, t) \right]_{t - \epsilon}^{t + \epsilon} + \left[ p_2(x) G'(x, t) \right]_{t - \epsilon}^{t + \epsilon} = 1.
```

### Limit as $ \epsilon \to 0 $

Let us consider the limit of the left-hand side of the equation as $ \epsilon \to 0 $. Since $ p_k(x) $ are continuous functions, we can define $ J_k $ as:

```{math}
J_0 = \lim_{\epsilon \to 0} \int_{t - \epsilon}^{t + \epsilon} p_0(x) G(x, t) dx = p_0(t) \lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right),
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

then the continuity of $ G(x, t) $ and $ G(x, t) \, dx $ holds, which leads to $ J_2 = 0 $, $ J_1 = 0 $, and $ J_0 = 0 $, contradicting the equation.

Alternatively, if we assume that $ G'(x, t) $ has a finite discontinuity at $ x = t $, i.e.,

```{math}
\lim_{\epsilon \to 0} \left( G'(t + \epsilon, t) - G'(t - \epsilon, t) \right) = 1,
```

then $ G(x, t) $ and $ G(x, t) \, dx $ are continuous functions, i.e., $ J_2 = 1 $, $ J_1 = J_0 = 0 $, and consequently:

```{math}
J_0 + J_1 + J_2 = 1,
```

as required by the equation.

Thus, the continuity and discontinuity conditions for $ G(x, t) $ are:

```{math}
\lim_{\epsilon \to 0} \left( G'(t + \epsilon, t) - G'(t - \epsilon, t) \right) = 1,
```

```{math}
\lim_{\epsilon \to 0} \left( G(t + \epsilon, t) - G(t - \epsilon, t) \right) = 0.
```


## Continuity of $ G(x, t) $ at $ x = t $: nth order ODE

Consider an infinitely small region of $ x $ in the vicinity of $ x = t $: $ x \in [t-\epsilon, t+\epsilon] $. Integrate both parts of Eq. (3.9) over $ x \in [t-\epsilon, t+\epsilon] $. Integration of the right-hand side gives by the definition of the Dirac delta function.

Before integrating the left part of Eq. (3.9), let us introduce auxiliary functions:

```{math}
S_k(g(x)) = \int_{t-\epsilon}^{t+\epsilon} g(x) dx
```

and

```{math}
I_k(g(x)) = \int_{t-\epsilon}^{t+\epsilon} g(x) dx G(x, t)
```

For convenience, we can express $ g(x) $ as:

```{math}
g(x) = g(t+\epsilon) G^{(n-k)}(t+\epsilon, t) - g(t-\epsilon) G^{(n-k)}(t-\epsilon, t)
```

Integration of the first term on the left-hand side (LHS) of Eq. (3.9) gives:

```{math}
I_1(a_n) = \int_{t-\epsilon}^{t+\epsilon} a_n(x) dx^n G(x, t) dx
```

which, when integrated by parts, becomes:

```{math}
I_1(a_n) = a_n(x) dx^{n-1} G(x, t)
```

Using the auxiliary functions $ I_k(g(x)) $ and $ S_k(g(x)) $, we notice that:

```{math}
I_1(a_n) = S_1(a_n) - I_2(a_0n)
```

where:

```{math}
I_2(a_0n) = \int_{t-\epsilon}^{t+\epsilon} a_0n(x) G^{(n-1)}(x, t) dx
```

and:

```{math}
S_1(a_n) = a_n(t + \epsilon) G^{(n-1)}(t + \epsilon, t) - a_n(t - \epsilon) G^{(n-1)}(t - \epsilon, t)
```

Similarly, integration of the second term on the LHS of Eq. (3.9) gives:

```{math}
I_2(a_{n-1}) = \int_{t-\epsilon}^{t+\epsilon} a_{n-1}(x) dx^{n-1} G(x, t) dx = S_2(a_{n-1}) - I_3(a_{0n-1})
```

where:

```{math}
I_3(a_{0n-1}) = \int_{t-\epsilon}^{t+\epsilon} a_{0n-1}(x) G^{(n-2)}(x, t) dx
```

Note that $ I_2(a_0n) - I_2(a_{n-1}) = I_2(a_0n - a_{n-1}) $. Thus, integrating the first two terms of Eq. (3.9) gives:

```{math}
I_1(a_n) + I_2(a_{n-1}) = S_1(p_1) + S_2(p_2) - I_3(p_0)
```

For convenience, we introduce functions $ p_k(x) $, which are linear combinations of various derivatives of $ a_m(x) $, such that:

```{math}
p_1(x) = a_1(x) - a_0(x)
```

```{math}
p_2(x) = a_2(x) - a_1(x)
```

and so on.

Thus, the equation becomes:

```{math}
I_1(a_n) + I_2(a_{n-1}) + \ldots + I_{n+1}(a_0)
```

The integral of the right-hand side of Eq. (3.9) is 1, so:

```{math}
I_1(a_n) + I_2(a_{n-1}) + \ldots + I_n(a_1) + I_{n+1}(a_0) = 1
```

Taking the limit of Eq. (3.14) for $ \epsilon \to 0 $, since the functions $ p_k(x) $ are derived from continuous functions $ a_m(x) $, they are also continuous. Therefore, for each:

```{math}
S_k(p_k): \lim_{\epsilon \to 0} S_k(p_k) = \lim_{\epsilon \to 0} \left[ p_k(t + \epsilon) G^{(n-k)}(t + \epsilon, t) - p_k(t - \epsilon) G^{(n-k)}(t - \epsilon, t) \right]
```

If $ G^{(n-k)}(x, t) $ is continuous at $ x = t $, then:

```{math}
\lim S_k(p_k) = 0
```

In our case, we have:

```{math}
\lim_{\epsilon \to 0} \int_{t-\epsilon}^{t+\epsilon} p_{n+1}(x) G(x, t) dx = 1
```

This is satisfied if the $ (n-1) $-th derivative of $ G(x, t) $ in Eq. (3.14) has a finite discontinuity at $ x = t $:

```{math}
p_1(t) \lim_{\epsilon \to 0} \left[ G^{(n-1)}(t + \epsilon, t) - G^{(n-1)}(t - \epsilon, t) \right] = 1
```

And all lower derivatives of $ G(x, t) $ are continuous:

```{math}
\lim_{\epsilon \to 0} \left[ G^{(n-k)}(t + \epsilon, t) - G^{(n-k)}(t - \epsilon, t) \right] = 0 \quad \text{(for } k = 2, 3, \dots, n\text{)} 
```

Thus, the single discontinuity condition and $ n-1 $ continuity conditions for the function $ G(x, t) $ at $ x = t $ are:

```{math}
\lim_{\epsilon \to 0} \frac{d^k G(x, t)}{dx^k} \Big|_{x = t + \epsilon} = 0 \quad \text{(for } k = 0, 1, \dots, n-2\text{)}
```

```{math}
\lim_{\epsilon \to 0} \frac{d^{n-1} G(x, t)}{dx^{n-1}} \Big|_{x = t + \epsilon} = 1
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
y(x) = \int_0^{\frac{\pi}{2}} G(x, t) f(t) \, dt = \int_0^x G_{x > t}(x, t) f(t) \, dt + \int_x^{\frac{\pi}{2}} G_{x < t}(x, t) f(t) \, dt.
```

For $ x > t $:

```{math}
\int_x^{\frac{\pi}{2}} G(x, t) f(t) \, dt = \int_x^{\frac{\pi}{2}} -\sin(t) \cos(x) f(t) \, dt.
```

For $ x < t $:

```{math}
\int_0^x G(x, t) f(t) \, dt = \int_0^x -\cos(t) \sin(x) f(t) \, dt.
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

### Boundary conditions for an nth order ODE

An nth order ODE requires $ n $ boundary conditions, which can be given in a variety of forms. For example, $ n $-point conditions:

```{math}
y(x_1) = y_1, \, y(x_2) = y_2, \dots, y(x_n) = y_n,
```

or the one-point boundary conditions:

```{math}
y(x_0) = a, \, y'(x_0) = b, \dots, y^{(n)}(x_n) = c.
```

### Inhomogeneous boundary conditions

So far, we applied homogeneous boundary conditions. For inhomogeneous ones, use substitution:

```{math}
u(x) = y(x) - h(x),
```

where $ h(x) $ is a polynomial function of order $ n - 1 $ (i.e., it has $ n $ coefficients) that satisfies the inhomogeneous boundary conditions. Then, the function $ u(x) $ will satisfy homogeneous boundary conditions.
