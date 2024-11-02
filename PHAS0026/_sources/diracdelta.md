# The Dirac Delta Function

## Some Motivation

Before we get to a definition, lets just think about the mean value theorem for a continuous function $f(x)$ over some interval $x \in [a,\,b]$:

```{math}
\bar{f} = \frac{1}{b-a}\int_a^b f(x)\,\mathrm{d}x
```

So if we define a function $D(x)$ using the piecewise definition:

```{math}
D(x)=
\begin{cases}
\frac{1}{b-a} & \text{if } a \leq x \leq b\\
0 & \text{if } \text{otherwise} 
\end{cases}
```
If we therefore integrate this function alongside a continuous function $f(x)$ over the same range:
```{math}
\int_a^b D(x)\,f(x)\,\mathrm{d}x = \frac{1}{b-a} \int_a^b f(x)\,\mathrm{d}x = \bar{f}
```

Let's now think about shrinking his range down to $x \in[a,\,a+\epsilon]$ and find the limit of this as $\epsilon \rightarrow 0$.  
```{math}
\lim_{\epsilon \rightarrow 0} \int_a^{a+\epsilon} D(x)\,f(x)\,\mathrm{d}x
```
Recall the fundamental theorem of calculus (FTC) for definite integrals:
```{math}
\int_a^b f'(x)\,\mathrm{d}x = f(b) - f(a)
```
So if we pick some function $f(x) = g'(x)$, lets find:
```{math}
\lim_{\epsilon \rightarrow 0} \int_a^{a+\epsilon} D(x)\,g'(x)\,\mathrm{d}x = \lim_{\epsilon \rightarrow 0} \frac{1}{\epsilon}\int_a^{a+\epsilon} \,g'(x)\,\mathrm{d}x
```
Which using the FTC reduces to:
```{math}
\lim_{\epsilon \rightarrow 0} \frac{1}{\epsilon}\left[g(a+\epsilon) - g(a) \right]
```
Given that $g=g(x)$, we can think of this as a function expression in $x$ evaluated at a particular point $x=a$, so:
```{math}
\lim_{\epsilon \rightarrow 0} \frac{1}{\epsilon}\left[g(x+\epsilon) - g(x) \right]_{x=a}
```
But now we see that is the definition of the derivative of $g(x)$! So this means:
```{math}
\lim_{\epsilon \rightarrow 0} \frac{1}{\epsilon}\left[g(x+\epsilon) - g(x) \right]_{x=a} = \left[g'(x) \right]_{x=a} = g'(a) = f(a)
```
Which is the original function in the integrand, but evaluated at $x=a$:
```{math}
\lim_{\epsilon \rightarrow 0}\int_a^{a+\epsilon} D(x)\,f(x)\,\mathrm{d}x = f(a)
```

The function which has this particular property is known as the Dirac Delta function $\delta(x)$. It is perhaps poor use of terminology to call this a **function**, it is best thought of a *distribution* at best.  The definition of $\delta(x)$ does not really live outside of the integral definitions, but its properties can be well understood when it acts on other functions.




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
\int_{-\infty}^{\infty} \delta(x) \,\mathrm{d}x = \int_{-\infty}^{\infty} \delta(x-a) \,\mathrm{d}x= 1.
```

This function is also called the impulse function because it can be used to represent external perturbations: finite in magnitude and infinitely short in duration.

The $ \delta $-function belongs to a class of generalized functions, i.e., its properties are determined by the properties of integrals with probe functions $ f(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) \delta(x - a) \,\mathrm{d}x= f(a).
```

Where:
1. The function $ f(x) $ is defined on a required interval of $ x $, e.g., $ x \in (-1, +1) $;
2. $ f(x) $ and all of its derivatives are continuous and finite functions of $ x $;
3. $ f(x) = 0 $ for all values of $ x $ outside of some finite interval $ [x_1, x_2] $.

## More motivation 

Consider the following step-function:
```{math}
f_k(x) = \left\{
        \begin{array}{rl}
        k/2, & \text{if } |x| < 1/k, \\
        0, & \text{if } |x| > 1/k.
        \end{array} \right.
```

Clearly we can see that an important property of this function is that
```{math}
\int_{-\infty}^{\infty} f_k(x) dx = 1.
```
As $k$ increases, $f_k(x)$ gets taller and thinner (see the figure below). We define the Dirac delta function to be
```{math}
\delta(x) = \lim_{k \rightarrow \infty} f_k(x),
```
although, of course, this limit doesn’t exist in the usual mathematical sense. Effectively $\delta(x)$ is infinite at $x = 0$ and zero at all other values of $x$. The key property however, is that its integral (area under the curve) is one.

![Graph of $f_k(x)$ for $k = 1$ (green), $k = 2$ (red) and $k = 4$ (blue).](fig2-1.png)

### Sifting property of the delta function

The delta function is most useful in how it interacts with other functions. Consider
```{math}
\int_{-\infty}^{\infty} g(x) \delta(x) \, dx,
```
where $g(x)$ is a continuous function defined over $(-\infty, \infty)$. Using our definition of the delta-function we can rewrite this as
```{math}
\begin{align*}
\lim_{k \rightarrow \infty} \int^\infty_{-\infty} g(x) f_k(x) \, dx &= \lim_{k \rightarrow \infty} \int^{1/k}_{-1/k} \frac{k}{2} g(x) \, dx\\
&= \lim_{k \rightarrow \infty} \frac{k}{2} g(\bar{x}) \left(\frac{1}{k} - \left(-\frac{1}{k} \right) \right),
\end{align*}
```
for some $\bar{x}$ in $[-1/k, 1/k]$, using the mean-value theorem for integrals. Clearly, as $k \rightarrow \infty$, we must have $\bar{x} \rightarrow 0$. The expression above simplifies to
```{math}
g(0) \frac{k}{2} \frac{2}{k} = g(0).
```
We have therefore established that for any continuous function $g$:
```{math}
\int_{-\infty}^{\infty} g(x)\delta(x) \, dx = g(0).
```
This result can easily be generalized to
```{math}
\int_{-\infty}^{\infty} g(x)\delta(x - a) \, dx = g(a).
```


### The Gaussian distribution.

The normal distribution, also known as the Gaussian distribution, is given by

```{math}
g(x, \mu, \sigma) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}.
```

lets simplify, centre on the origin so $\mu = 0$ and take $2\sigma^2 = a^2$:

```{math}
g(x,a) = \frac{1}{a\sqrt{\pi}}e^{-(x/a)^2}
```
in the limit of $a \rightarrow 0$, the function $ g(x, a) $ behaves similarly to $ \delta(x) $, we can see this in the figure below:

![Gaussian approximation of the delta function](Dirac_function_approximation.gif)

This means that:

```{math}
\lim_{\sigma \to 0} \int_{-\infty}^{\infty} f(x) g(x, a)\mathrm{d}x = f(0).
```


Yet, we will not equate $ \delta(x) $ and $ \lim_{\sigma \to 0} g(x, a) $ because $ \delta(x) $ is a generalised function defined via its integral definition with other functions, whilst $ g(x, a) $ is a function defined in the usual sense.





## Properties of the $ \delta $-function

It follows from the definition that a product of $ \delta(x - a) $ and any finite function is zero everywhere except at $ x = a $. Hence,

```{math}
\int_{-\infty}^{\infty} f(x) \delta(x - x_0) \,\mathrm{d}x= f(x_0) \int_{-\infty}^{\infty} \delta(x - x_0) \,\mathrm{d}x= f(x_0).
```

To find $ \delta(- x) $, we need to consider the integral

```{math}
\int_{-\infty}^{\infty} f(x) \delta(-x) \, dx.
```

After substituting $ x = -t $ and $\mathrm{d}x= -dt $, we have

```{math}
\int_{-\infty}^{+\infty} f(x) \delta(-x) \,\mathrm{d}x= \int_{+\infty}^{-\infty} f(-t) \delta(t) (-dt) = \int_{-\infty}^{+\infty} f(-t) \delta(t) \,\mathrm{d}t= f(0).
```

Thus,

```{math}
\int_{-\infty}^{+\infty} f(x) \delta(-x) \,\mathrm{d}x= \int_{-\infty}^{+\infty} f(t) \delta(t) \, dt.
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
Lets start with $a > 0$, substitute $ ax = t $, then $\mathrm{d}x= \frac{dt}{a} $:

```{math}
\int_{-\infty}^{\infty} f(x) \delta(ax) \,\mathrm{d}x= \int_{-\infty}^{\infty} \frac{1}{a}f\left(\frac{t}{a}\right) \delta(t) \,\mathrm{d}t= \frac{1}{a}f\left(\frac{0}{a}\right) = \frac{1}{a}f(0) = \int_{-\infty}^{\infty} f(s)\,\delta(s)\,\mathrm{d}s
```

Hence,

```{math}
\delta(ax) = \frac{1}{a} \delta(x).
```

It also follows that for $ a < 0 $:

```{math}
\delta(ax) = \delta(-|a|x) = \delta(|a|x)
```

from our earlier property.  This therefore means that:

```{math}
\delta(ax) = \delta(|a|x) = \frac{1}{|a|}\delta(x)
```

By combining $ \delta(-x) = \delta(x) $ and $ \delta(ax) = \frac{1}{a} \delta(x) $, we obtain

```{math}
\delta(ax) = \frac{1}{|a|} \delta(x)
```

for any $ a \in \mathbb{R}$.

## Laplace transform of the Dirac delta function.

Evaluate $ L[\delta(t - a)] $:

```{math}
L[\delta(t - a)] = \int_{0}^{\infty} \delta(t - a) e^{-pt}\mathrm{d}x= e^{-pa} \quad (\text{for } a > 0)
```

## Derivatives of the Dirac delta function.

To attach meaning to $ \delta'(x - a) $, consider

```{math}
\int_{-\infty}^{\infty} f(x) \delta'(x - a)\mathrm{d}x= \left[f(x) \delta(x - a)\right]_{-\infty}^{+\infty} - \int_{-\infty}^{\infty} f'(x) \delta(x - a)\mathrm{d}x= - f'(a).
```

The term $ \left[f(x) \delta(x - a)\right]_{-\infty}^{+\infty} $ equals zero because probe functions $ f(x) = 0 $ for all $ x $ outside of some finite interval $ [x_1, x_2] $.

Similarly, we can find the nth derivative of $ \delta(x - a) $ by calculating:

```{math}
\int_{-\infty}^{\infty} f(x) \delta^{(n)}(x - a) dx.
```

Integrating by parts $ n $ times gives:

```{math}
\int_{-\infty}^{\infty} f(x) \delta^{(n)}(x - a)\mathrm{d}x= (-1)^n \int_{-\infty}^{\infty} f^{(n)}(x) \delta(x - a)\mathrm{d}x= (-1)^n f^{(n)}(a).
```

### Other generalized functions.

Consider the following examples:

1) $ x \delta(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x \delta(x)]\mathrm{d}x= \int_{-\infty}^{\infty} [f(x) x] \delta(x)\mathrm{d}x= 0 \cdot f(0) = 0.
```

2) $ x \delta'(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x \delta'(x)]\mathrm{d}x= x f(x) \delta(x) \Big|_{-\infty}^{\infty} - \int_{-\infty}^{\infty} [f(x) + x f'(x)] \delta(x)\mathrm{d}x= - f(0).
```

3) $ x^2 \delta''(x) $:

```{math}
\int_{-\infty}^{\infty} f(x) [x^2 \delta''(x)]\mathrm{d}x= x f(x) \delta(x) \Big|_{-\infty}^{\infty} + \int_{-\infty}^{\infty} [2x f(x) + x^2 f'(x)] \delta(x)\mathrm{d}x= 2 f(0).
```

Thus,

- $ x \delta(x) = 0 $,
- $ x \delta'(x) = - \delta(x) $,
- $ x^2 \delta''(x) = 2 \delta(x) $.

## The (Heaviside) Step Function

Lets think about a different function for the moment, a simple step function entered on the origin:
```{math}
H(x) = \begin{cases}
1 & \text{if } x > 0\\
0 & \text{if } x < 0
\end{cases}
```
We will return to $H(0)$ shortly, but it does not change the fundamental concepts of this function.

The first property to note about the step function is that it has a sifting property also, so if we wish to restrict a function too a specific open ended range, such as $x > a$, we can just use:
```{math}
H(x-a)\,f(x) = \begin{cases}
f(x) & \text{if } x > a\\
0 & \text{if } x < a
\end{cases}
```

And if we want to include a closed range of values $a < x < b$ we can include another step function:
```{math}
H(x-a)\,H(b-x)\,f(x) = \begin{cases}
f(x) & \text{if } a < x < b \\
0 & \text{if } \text{otherwise} 
\end{cases}
```

This differs from the Dirac delta function which only picks out a value of a function $f(x)$ at $x=a$.

The second property to note is that the derivative of the step function is zero almost everywhere - except at the point where the jump occurs, so we can think of the step functions derivative as being related to the Dirac delta function:
```{math}

\frac{\mathrm{d}}{\mathrm{d}x}\Big(H(x-a) \Big) = \delta(x-a)
```



### Laplace Transform

Now that we have a new function to find the Laplace transform of:

```{math}
\mathcal{L}[H(t-a)] &= \int_0^\infty H(t-a)\,e^{-pt}\,\mathrm{d}t = \int_a^\infty e^{-pt}\,\mathrm{d}t \\
&= \left[ -\frac{1}{p}e^{-pt}\right]_a^\infty = \frac{e^{-pa}}{p}  \quad (\text{for } a > 0)
```


