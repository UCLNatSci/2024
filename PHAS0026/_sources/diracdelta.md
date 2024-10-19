# The Dirac Delta Function

## Definition
Let us introduce a function $ \delta(x) $ with properties:

```{math}
\delta(x - a) =
\begin{cases}
0 & \text{if } x \neq a \\
\infty & \text{if } x = a
\end{cases}
```

where constant $ a $ is finite and

```{math}
\int_{-\infty}^{\infty} \delta(x) \, dx = 1.
```

This function is also called the impulse function because it can be used to represent external perturbations: finite in magnitude and infinitely short in duration.

The $ \delta $-function belongs to a class of generalized functions, i.e., its properties are determined by the properties of integrals with probe functions $ f(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) \delta(x - a) \, dx = f(a).
```

Where:
1. The function $ f(x) $ is defined on a required interval of $ x $, e.g., $ x \in (-1, +1) $;
2. $ f(x) $ and all of its derivatives are continuous and finite functions of $ x $;
3. $ f(x) = 0 $ for all values of $ x $ outside of some finite interval $ [x_1, x_2] $.

## Properties of the $ \delta $-function

It follows from the definition that a product of $ \delta(x - a) $ and any finite function is zero everywhere except at $ x = a $. Hence,

```{math}
\int_{-\infty}^{\infty} f(x) \delta(x - x_0) \, dx = f(x_0) \int_{-\infty}^{\infty} \delta(x - x_0) \, dx = f(x_0).
```

To find $ \delta(\delta x) $, we need to consider the integral

```{math}
\int_{-\infty}^{\infty} f(x) \delta(-x) \, dx.
```

After substituting $ x = -t $ and $ dx = -dt $, we have

```{math}
\int_{-\infty}^{\infty} f(x) \delta(-x) \, dx = \int_{-\infty}^{\infty} f(-t) \delta(t) (-dt) = \int_{-\infty}^{\infty} f(-t) \delta(t) \, dt = f(0).
```

Thus,

```{math}
\int_{-\infty}^{\infty} f(x) \delta(-x) \, dx = \int_{-\infty}^{\infty} f(t) \delta(t) \, dt.
```

For any probe function $ f(x) $, we obtain:

```{math}
\delta(-x) = \delta(x).
```

## Calculating $ \delta(ax) $

Similarly, to calculate $ \delta(ax) $, we need to consider the integral:

```{math}
\int_{-\infty}^{\infty} f(x) \delta(ax) \, dx.
```

Substitute $ ax = t $, then $ dx = \frac{dt}{a} $:

```{math}
\int_{-\infty}^{\infty} f(x) \delta(ax) \, dx = \int_{-\infty}^{\infty} f\left(\frac{t}{a}\right) \delta(t) \, dt = f\left(\frac{0}{a}\right) = f(0).
```

Hence,

```{math}
\delta(ax) = \frac{1}{|a|} \delta(x).
```

Thus, for negative $ b $:

```{math}
\delta(ax) = \frac{1}{|a|} \delta(x).
```

By combining $ \delta(-x) = \delta(x) $ and $ \delta(ax) = \frac{1}{a} \delta(x) $, we obtain

```{math}
\delta(ax) = \frac{1}{|a|} \delta(x)
```

for any real $ a $.

## Laplace transform of the Dirac delta function.

Evaluate $ L[\delta(x - a)] $:

```{math}
L[\delta(x - a)] = \int_{-\infty}^{\infty} \delta(x - a) e^{-px} dx = e^{-pa} \quad (\text{for } a > 0)
```

## Derivatives of the Dirac delta function.

To attach meaning to $ \delta'(x - a) $, consider

```{math}
\int_{-\infty}^{\infty} f(x) \delta'(x - a) dx = f(x) \delta(x - a) \Big|_{+1} - \int_{-\infty}^{\infty} f'(x) \delta(x - a) dx = - f'(a).
```

The term $ f(x) \delta(x - a) \Big|_{+1} $ equals zero because probe functions $ f(x) = 0 $ for all $ x $ outside of some finite interval $ [x_1, x_2] $.

Similarly, we can find the nth derivative of $ \delta(x - a) $ by calculating

```{math}
\int_{-\infty}^{\infty} f(x) \delta^{(n)}(x - a) dx.
```

Integrating by parts $ n $ times gives:

```{math}
\int_{-\infty}^{\infty} f(x) \delta^{(n)}(x - a) dx = (-1)^n \int_{-\infty}^{\infty} f^{(n)}(x) \delta(x - a) dx = (-1)^n f^{(n)}(a).
```

### Other generalized functions.

Consider the following examples:

1) $ x \delta(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x \delta(x)] dx = \int_{-\infty}^{\infty} [f(x) x] \delta(x) dx = 0 \cdot f(0) = 0.
```

2) $ x \delta'(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x \delta'(x)] dx = x f(x) \delta(x) \Big|_{-\infty}^{\infty} - \int_{-\infty}^{\infty} [f(x) + x f'(x)] \delta(x) dx = - f(0).
```

3) $ x^2 \delta''(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x^2 \delta''(x)] dx = x f(x) \delta(x) \Big|_{-\infty}^{\infty} + \int_{-\infty}^{\infty} [2x f(x) + x^2 f'(x)] \delta(x) dx = 2 f(0).
```

Thus,

- $ x \delta(x) = 0 $,
- $ x \delta'(x) = - \delta(x) $,
- $ x^2 \delta''(x) = 2 \delta(x) $.

## Gaussian distribution.

The normal distribution, also known as the Gaussian distribution, is given by

```{math}
g(x, a, \sigma) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x - a)^2}{2\sigma^2}}.
```

In the limit of infinitely small $ \sigma $ ($ \sigma \to 0 $), the function $ g(x, a, \sigma) $ behaves similarly to $ \delta(x - a) $ in that:

```{math}
\lim_{\sigma \to 0} \int_{-\infty}^{\infty} f(x) g(x, a, \sigma) dx = f(a).
```

Yet, we will not equate $ \delta(x - a) $ and $ \lim_{\sigma \to 0} g(x, a, \sigma) $ because $ \delta(x - a) $ is a generalized function defined via its integral with other functions, while $ g(x, a, \sigma) $ is a function in the usual sense.

