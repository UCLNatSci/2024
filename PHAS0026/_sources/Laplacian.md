#  Integral Transforms

## Laplace Transform

Finding solutions to differential equations can be made easier if the equation is converted to an algebraic form using the Laplace transform. The Laplace transform is an integral transformation defined as:

```{math}
\mathcal{L}[f(x)] = \int_0^\infty f(x) e^{-px} dx = F(p)
```

- By definition, $ \mathcal{L}[f] $ does not depend on the behavior of $ f(x) $ for $ x < 0 $.
- Note that function $ F(p) $ might be undefined for some values of $ p $.
- Laplace transform is a linear operation:

```{math}
\mathcal{L}[c_1 f(x) + c_2 g(x)] = c_1 \mathcal{L}[f(x)] + c_2 \mathcal{L}[g(x)]
```

It is straightforward to find the Laplace transform $ F(p) $ of any given function $ f(x) $. To find the function $ g(x) $ given its Laplace transform $ G(p) $, refer to a table of Laplace transforms.

#### Examples

1. For $ f(x) = a $ (constant):

```{math}
F(p) = \int_0^\infty a e^{-px} dx = \frac{a}{p}, \quad \text{for } \text{Re }(p) > 0
```

2. For $ f(x) = e^{-ax} $:

```{math}
F(p) = \int_0^\infty e^{-ax} e^{-px} dx = \frac{1}{a + p}, \quad \text{for } \text{Re }(a + p) > 0
```

3. For $ f(x) = \cos(ax) $:

```{math}
F(p) = \int_0^\infty \cos(ax) e^{-px} dx = \frac{p}{a^2 + p^2}, \quad \text{for } \text{Re }(p) > | \text{Im }(a) |
```

#### Laplace Transform of Derivatives

Consider Laplace transforms of $ f'(x) $ and $ f''(x) $.

1. $ \mathcal{L}[f'] $:

```{math}
\mathcal{L}[f'] = \int_0^\infty f'(x) e^{-px} dx = \left[ e^{-px} f(x) \right]_0^\infty + p \int_0^\infty f(x) e^{-px} dx = -f(0) + p \mathcal{L}[f]
```

2. $ \mathcal{L}[f''] $:

```{math}
\mathcal{L}[f''] = \int_0^\infty f''(x) e^{-px} dx = p^2 \mathcal{L}[f] - p f(0) - f'(0)
```

#### Solving ODE Using the Laplace Transform

Applying the Laplace transform method is convenient if:

- The variable $ x $ is defined in the interval $ [0, \infty) $ (e.g., coordinate of a point in a semi-infinite metal rod or time).
- The values of the function $ f(x) $ and its derivatives are zero for $ x = 0 $.

For example, consider the differential equation:

```{math}
f''(x) + 4 f'(x) + 4 f(x) = x^2 e^{-2x}
```

with initial conditions $ f(0) = 0 $ and $ f'(0) = 0 $. Taking the Laplace transform of the equation gives:

```{math}
p^2 \mathcal{L}[f] + 4 p \mathcal{L}[f] + 4 \mathcal{L}[f] = \mathcal{L}[x^2 e^{-2x}]
```

Given the initial conditions, we simplify:

```{math}
(p + 2)^2 \mathcal{L}[f] = \mathcal{L}[x^2 e^{-2x}]
```

Using a table of Laplace transforms, we find:

```{math}
\mathcal{L}[x^2 e^{-2x}] = \frac{2}{(p + 2)^3}
```

Thus, the transformed equation becomes:

```{math}
\mathcal{L}[f] = \frac{2}{(p + 2)^5}
```

By referring to a Laplace transform table, we find that the solution of the ODE is:

```{math}
f(x) = \frac{1}{12} x^4 e^{-2x}
```



## Table of Laplace Transforms

Given the functions $f(t)$ and $g(t)$, and their respective Laplace transforms $F(p)$ and $G(p)$ such that:

```{math}
\begin{align}
f(t) &= \mathcal{L}^{-1}\{F\}(p),\\
g(t) &= \mathcal{L}^{-1}\{G\}(p),
\end{align}
```
then we can define a bunch of different Laplace Transforms and their properties:

| **Property** | **Time domain $t$** | **Laplace domain $p$** |
|--------------|-----------------|--------------|
| **Linearity** | $ a f(t) + b g(t) $ | $ a F(p) + b G(p) $ |
| **Frequency-domain derivative** | $ t f(t) $ | $ -F'(p) $ |
| **Frequency-domain general derivative** | $ t^n f(t) $ | $ (-1)^n F^{(n)}(p) $ |
| **Derivative** | $ f'(t) $ | $ p F(p) - f(0^{-}) $ |
| **Second derivative** | $ f''(t) $ | $ p^2 F(p) - p f(0) - f'(0) $ |
| **General derivative** | $ f^{(n)}(t) $ | $ p^n F(p) - \sum_{k=1}^{n} p^{n-k} f^{(k-1)}(0) $ |
| **Frequency shifting** | $ e^{at} f(t) $ | $ F(p - a) $ |
| **Time shifting I** | $ f(t - a) u(t - a) $ | $ e^{-ap} F(p) $ *|
| **Time shifting II** | $ f(t) u(t - a) $ | $ e^{-ap} \mathcal{L}\{f(t + a)\} $ *|
| **Time scaling** | $ f(at) $ | $ \frac{1}{a} F \left( \frac{p}{a} \right) $ |

* where $u(t)$ is the Heavisde step function.


## Fourier Transform

There is some relationship between Laplace transforms and Fourier transforms.

One definition of a Fourier transform is:
```{math}
\mathcal{F}[f(x)] = \tilde{f}(k) = \frac{1}{\sqrt{2\pi}}\,\int_{-\infty}^\infty f(x)\,e^{-ikx}\,\mathrm{d}x
```

with the inverse transform looking like:

```{math}
f(x) = \mathcal{F}^{-1}[\tilde{f}(k) = \frac{1}{\sqrt{2\pi}}\,\int_{-\infty}^\infty \tilde{f}(x)\,e^{ikx}\,\mathrm{d}x
```