
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
