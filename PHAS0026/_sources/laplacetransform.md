# Laplace Transforms

## Definition

A function is called *piecewise continuous* on an interval if the interval can be broken into a finite number of subintervals on which the function is continuous on each open subinterval (i.e., the subinterval without its endpoints) and has a finite limit at the endpoints of each subinterval.

Suppose that $f(t)$ is a piecewise continuous function. The Laplace transform of $f(t)$ is denoted $\mathcal{L}[f(t)]$ and defined as

```{math}
\mathcal{L}[f(t)] = \int_0^\infty e^{-pt} f(t) \,\mathrm{d}t
```

There is an alternate notation for Laplace transforms. For convenience, we will often denote Laplace transforms as:

```{math}
\mathcal{L}[f(t)] = F(p)
```

With this alternate notation, note that the transform is really a function of a new variable, $p$, and that all the $t$’s will\mathrm{d}rop out in the integration process.

We can start with a few facts about Laplace transform:

- By definition, $\mathcal{L}[f]$ does not depend on the behavior of $f(x)$ for $x < 0$.
- Note that function $F(p)$ might be undefined for some values of $p$.
- Laplace transform is a linear operation:

```{math}
\mathcal{L}[c_1 f(x) + c_2 g(x)] = c_1 \mathcal{L}[f(x)] + c_2 \mathcal{L}[g(x)]
```

It is straightforward to find the Laplace transform $F(p)$ of any given function $f(x)$. To find the function $g(x)$ given its Laplace transform $G(p)$, refer to a table of Laplace transforms.

## Fourier Transform [#](#fourier-transform)

There is some relationship between Laplace transforms and Fourier transforms.

One definition of a Fourier transform is:

```{math}
\mathcal{F}[f(x)] = \tilde{f}(k) = \frac{1}{\sqrt{2\pi}}\,\int_{-\infty}^\infty f(x)\,e^{-ikx}\,\mathrm{d}x
```

with the inverse transform looking like:

```{math}
f(x) = \mathcal{F}^{-1}[\tilde{f}(k)] = \frac{1}{\sqrt{2\pi}}\,\int_{-\infty}^\infty \tilde{f}(x)\,e^{ikx}\,\mathrm{d}x
```

and hence this means $\tilde{f}(k)$ is explicitly complex.


## The prototype Laplace integral

If $c \neq 0$, evaluate the following integral:

```{math}
\int_0^\infty e^{ct} \,\mathrm{d}t
```

Remember that you need to convert improper integrals to limits as follows:

```{math}
\int_0^\infty e^{ct} \,\mathrm{d}t = \lim_{n \to \infty} \int_0^n e^{ct} \,\mathrm{d}t
```

Now, do the integral, then evaluate the limit:

```{math}
\int_0^\infty e^{ct} \,\mathrm{d}t = \lim_{n \to \infty} \left( \frac{1}{c} e^{ct} \right)_0^n = \lim_{n \to \infty} \left( \frac{1}{c} e^{cn} - \frac{1}{c} \right)
```

Now, at this point, we’ve got to be careful. The value of $c$ will affect our answer. We’ve already assumed that $c$ was non-zero, now we need to worry about the sign of $c$. If $c$ is positive, the exponential will go to infinity. On the other hand, if $c$ is negative, the exponential will go to zero.

So, the integral is only convergent (i.e., the limit exists and is finite) provided $c < 0$. In this case, we get:

```{math}
\int_0^\infty e^{ct} \,\mathrm{d}t = -\frac{1}{c}, \quad \text{provided } c < 0
```

Now that we remember how to do these, let’s compute some Laplace transforms.

## Transforming a constant

Compute $\mathcal{L}[1]$.

```{math}
\mathcal{L}[1] = \int_0^\infty e^{-pt} \,\mathrm{d}t
```

Now, at this point, notice that this is nothing more than the integral in the previous example with $c = -p$. Therefore, all we need to do is reuse our previous result with the appropriate substitution. Doing this gives:

```{math}
\mathcal{L}[1] = \int_0^\infty e^{-pt} \,\mathrm{d}t = -\frac{1}{-p}, \quad \text{provided } -p < 0
```

Or, with some simplification we have:

```{math}
\mathcal{L}[1] = \frac{1}{p}, \quad \text{provided } p > 0
```

Notice that we had to put a restriction on $p$ in order to actually compute the transform. All Laplace transforms will have restrictions on $p$. At this stage, this restriction is something that we tend to ignore, but we really shouldn’t ever forget that it’s there.

In general for a constant $a$, $\mathcal{L}[a]$ is found as:

```{math}
\mathcal{L}[a] = \frac{a}{p}
```

## Transforming an exponential function

Compute $\mathcal{L}[e^{at}]$.

Plug the function into the definition of the transform and do a little simplification:

```{math}
\mathcal{L}[e^{at}] = \int_0^\infty e^{-pt} e^{at} \,\mathrm{d}t = \int_0^\infty e^{(a-p)t} \,\mathrm{d}t
```

Once again, notice that we can use our previous result, provided $c = a-p$:

```{math}
\mathcal{L}[e^{at}] = \int_0^\infty e^{(a-p)t} \,\mathrm{d}t = -\frac{1}{a-p}, \quad \text{provided } a-p < 0
```

With some simplification we have:

```{math}
\mathcal{L}[e^{at}] = \frac{1}{p-a}, \quad \text{provided } p > a
```

## Transforming a trigonometric function

Compute $\mathcal{L}[\sin(at)]$.

Plug the function into the definition:

```{math}
\mathcal{L}[\sin(at)] = F(p) = \int_0^\infty e^{-pt} \sin(at) \,\mathrm{d}t
```

Now we can do one of two methods to find the result here:

1. Integrate by parts:

```{math}
\begin{split}
u = e^{-pt} &\qquad v' = \sin(at)\\
u' = -pe^{-pt} &\qquad v = -\frac{1}{a}\cos(at)
\end{split}
```

which results in:

```{math}
F(p) = \left[ -\frac{1}{a}\,e^{-pt}\,\cos(at)\right]_0^{\infty} - \frac{p}{a}\int_0^\infty e^{-pt} \cos(at) \,\mathrm{d}t
```

We then have to integrate by parts again on the second integral:

```{math}
\begin{split}
u = e^{-pt} &\qquad v' = \cos(at)\\
u' = -pe^{-pt} &\qquad v = -\frac{1}{a}\sin(at)
\end{split}
```

which gives:

```{math}
F(p) = \left[ -\frac{1}{a}\,e^{-pt}\,\cos(at) + \frac{p}{a^2}\frac{1}{a}\sin(at)\right]_0^{\infty} - \frac{p^2}{a^2}\frac{p}{a}\int_0^\infty e^{-pt} \sin(at) \,\mathrm{d}t
```

We can recognize the last integral also as $F(p)$, hence:

```{math}
\left(1 + \frac{p^2}{a^2}\right) F(p) = \left[ -\frac{1}{a}\,e^{-pt}\,\sin(at) + \frac{p}{a^2}\frac{1}{a}\cos(at)\right]_0^{\infty} 
```

Using the limit definition, we have:

```{math}
\begin{split}
\left(1 + \frac{p^2}{a^2}\right) F(p) &= \lim_{n \rightarrow \infty} \left[ -\frac{1}{a}\,e^{-pt}\,\cos(at) + \frac{p}{a^2}\frac{1}{a}\sin(at)\right]_0^n\\
&= \lim_{n \rightarrow \infty}\left(\frac{1}{a} - \frac{1}{a}e^{-pn}\cos(an) + \frac{p}{a^2}e^{-pn}\sin(an)\right) = \frac{1}{a}
\end{split}
```

which means that:

```{math}
\left(1 + \frac{p^2}{a^2}\right) F(p) = 1 \Rightarrow F(p) = \frac{\frac{1}{a}}{\left(1 + \frac{p^2}{a^2}\right)} = \frac{a}{p^2+a^2}
```

2. Using complex exponentials:

You can express trigonometric functions as:
```{math}
\sin(at) &= \frac{e^{iat}-e^{-iat}}{2i} \\
\cos(at) &= \frac{e^{iat}+e^{-iat}}{2}
```
Then, since the Laplace transform is linear, you can compute the two transforms separately and combine them back at the end. As we see:
```{math}
\mathcal{L}[\sin(at) &= \frac{1}{2i}\int_0^\infty \left(e^{(ia-p)t}-e^{-(ia+p)t}\right)\,\mathrm{d}t = \frac{1}{2i}\left(\frac{1}{p-ia} - \frac{1}{p+ia}\right) = \frac{a}{p^2+a^2}\\
\mathcal{L}[\cos(at) &= \frac{1}{2}\int_0^\infty \left(e^{(ia-p)t}+e^{-(ia+p)t}\right)\,\mathrm{d}t  = \frac{1}{2}\left(\frac{1}{p-ia} + \frac{1}{p+ia}\right) = \frac{p}{p^2+a^2}
```


This gives the same answer with much less work.

The first method is pretty messy, and as you can see, integration by parts gets very complicated very quickly. The complex exponential method tends to be easier and more reliable, so we will stick with that in future problems.

## Transforming a power of $t$

Compute $\mathcal{L}[at]$.

Plug the function into the definition:
```{math}
\mathcal{L}[at] = F(p) = \int_0^\infty e^{-pt} at \,\mathrm{d}t
```
Now we can integrate by parts:
```{math}
\begin{split} 
u = at &\qquad v' = e^{-pt} \\
u' = a &\qquad v = -\frac{1}{p}e^{-pt} 
\end{split}
```
which results in:
```{math}
F(p) = \left[ -\frac{a}{p}\,t\,e^{-pt}\right]_0^{\infty} + \frac{a}{p}\int_0^\infty e^{-pt} \,\mathrm{d}t
```
The first term goes to zero in the infinite limit, and the second term is related to the Laplace transform $\mathcal{L}[1]$, so we have:
```{math}
\mathcal{L}[at] = \frac{a}{p}\frac{1}{p} = \frac{a}{p^2}
```
What about higher powers? For $t^2$:
```{math}
\mathcal{L}[at^2] = F(p) = \int_0^\infty e^{-pt} at^2 \,\mathrm{d}t
```
Now we can integrate by parts:
```{math}
\begin{split} 
u = at^2 &\qquad v' = e^{-pt} \\
u' = 2at &\qquad v = -\frac{1}{p}e^{-pt} 
\end{split}
```
which results in:
```{math}
F(p) = \left[ -\frac{a}{p}\,t^2\,e^{-pt}\right]_0^{\infty} + \frac{2a}{p}\int_0^\infty \,t\,e^{-pt} \,\mathrm{d}t
```
The first term goes to zero in the infinite limit, and the second term is related to the Laplace transform $\mathcal{L}[t]$, so we have:
```{math}
\mathcal{L}[at] = \frac{2a}{p}\frac{1}{p^2} = \frac{2a}{p^3}
```
So, the effect of the integration by parts procedure is to differentiate the power of $t$. In general:
```{math}
\mathcal{L}[at^n] = F(p) = \int_0^\infty e^{-pt} at^n \,\mathrm{d}t
```
Now we can integrate by parts:
```{math}
\begin{split} 
u = at^n &\qquad v' = e^{-pt} \\
u' = nat^{n-1} &\qquad v = -\frac{1}{p}e^{-pt} 
\end{split}
```
which results in:
```{math}
\begin{split} 
F(p) & = \left[ -\frac{a}{p}\,t^n\,e^{-pt}\right]_0^{\infty} + \frac{na}{p}\int_0^\infty t^{n-1}\,e^{-pt} \,\mathrm{d}t \\
\Rightarrow \mathcal{L}[at^n] & = \frac{na}{p}\mathcal{L}[t^{n-1}] - \frac{na}{p}\frac{1}{p}\mathcal{L}[t^{n-2}] = \dots = \frac{an!}{p^{n+1}} 
\end{split}
```
Note that this final step requires that $n \in \mathbb{N}$ so that the final term in the chain is $\mathcal{L}[1]$. For other values of $n$, we will consider them later.

---

### Side note

Before moving on to the next section, a small side note: On occasion, you will see the following as the definition of the Laplace transform:
```{math}
\mathcal{L}[f(t)] = \int_{-\infty}^\infty e^{-pt} f(t) \,\mathrm{d}t
```
Note the change in the lower limit from zero to negative infinity. In these cases, there is almost always the assumption that the function $f(t)$ is defined as follows:
```{math}
\begin{split} 
f(t) = \begin{cases} 
f(t) & \text{if } t \geq 0 \\
0 & \text{if } t < 0 
\end{cases} 
\end{split}
```
In other words, it is assumed that the function is zero if $t < 0$. The first half of the integral will\mathrm{d}rop out since the function is zero, and we will get back to the original definition.

We will return to this idea when we discuss the step function.

---

## Linearity of the Laplace Transform

Given $f(t)$ and $g(t)$:
```{math}
\mathcal{L}[af(t) + bg(t)] = aF(p) + bG(p)
```
for any constants $a$ and $b$.

In other words, constants, sums, and differences of functions do not affect Laplace transforms. Just take the transform of individual functions, then add or subtract the results.

### Worked examples

Find the Laplace transforms of the following functions:

1. $f(t) = 6e^{-5t} + e^{3t} + 5t^3 - 9$
```{math}
F(p) = \frac{6}{p+5} + \frac{1}{p-3} + \frac{30}{p^4} - \frac{9}{p}
```

2. $g(t) = 4 \cos(4t) - 9 \sin(4t) + 2 \cos(10t)$
```{math}
G(p) = \frac{4p}{p^2 + 16} - \frac{36}{p^2 + 16} + \frac{2p}{p^2 + 100}
```

3. $h(t) = 3 \sinh(2t) + 3 \sin(2t)$
```{math}
H(p) = \frac{6}{p^2 - 4} + \frac{6}{p^2 + 4}
```

4. $g(t) = e^{3t} + \cos(6t) - e^{3t} \cos(6t)$
```{math}
G(p) = \frac{1}{p-3} + \frac{p}{p^2 + 36} - \frac{p-3}{(p-3)^2 + 36}
```
## Laplace Transform of Derivatives

Consider Laplace transforms of $ f'(x) $ and $ f''(x) $, lets find these explicitly:

1. $ \mathcal{L}[f'] $:

   ```{math}
   \mathcal{L}[f'] = \int_0^\infty f'(x) e^{-pt}\,\mathrm{d}t
   ```

   Using integration by parts:

   ```{math}
   \begin{split}
   u = e^{-pt} & \qquad v' = f'(t) \\
   u' = -p\,e^{-pt} & \qquad v = f(t)
   \end{split}
   ```

   Which means that:

   ```{math}
   \begin{split}
   \mathcal{L}[f'] &= \left[ e^{-pt} f(t) \right]_0^\infty + p \int_0^\infty f(x) e^{-pt} \,\mathrm{d}t = -f(0) + p \mathcal{L}[f] \\
   &= -f(0) + p F(p)
   \end{split}
   ```

2. $ \mathcal{L}[f''] $:

   ```{math}
   \mathcal{L}[f''] = \int_0^\infty f''(t) e^{-pt}\,\mathrm{d}t
   ```

   Using integration by parts:

   ```{math}
   \begin{split}
   u = e^{-pt} & \qquad v' = f''(t) \\
   u' = -p\,e^{-pt} & \qquad v = f'(t)
   \end{split}
   ```

   This gives:

   ```{math}
   \begin{split}
   \mathcal{L}[f''] &= \left[ e^{-pt} f'(t) \right]_0^\infty + p \int_0^\infty f(x) e^{-pt} \,f'(t)\,\mathrm{d}t \\
   &= -f'(0) + p \mathcal{L}[f'(t)] \\
   &= p(-f(0) + p F(p)) - f'(0) =  p^2\,F(p) - p f(0) - f'(0)
   \end{split}
   ```

This means that the general result is that:

```{math}
\mathcal{L}[f^{(n)}(t)] = p^n\, F(p) - p^{n-1}\, f(0) - p^{n-1} \,f'(0) - \dots - p\,f^{(n-2)}(0) - f^{(n-1)}(0)
```

A related set of transform come in the form of $\mathcal{L}[t\,f(t)]$:

```{math}
\mathcal{L}[t\,f(t)] = \int_0^\infty t\,f(t)\,e^{-pt}\,\mathrm{d}t
```

There is a temptation to evaluate this by parts, but this is not a fruitful method. Instead, consider taking a derivative with respect to $p$ on a regular Laplace transform of $f(t)$:

```{math}
F(p) =  \int_0^\infty f(t)\,e^{-pt}\,\mathrm{d}t \Rightarrow \frac{\mathrm{d} F(p)}{\mathrm{d}p} = -\int_0^\infty t\,f(t)\,e^{-pt}\,\mathrm{d}t
```

since here $\frac{\mathrm{d}}{\mathrm{d}p} e^{-pt} = -te^{-pt}$.

So this means that:

```{math}
F'(p) = -\mathcal{L}[t\,f(t)]
```

Likewise for $t^2$:

```{math}
\frac{\mathrm{d^2} F(p)}{\mathrm{d}p^2} = \int_0^\infty t^2\,f(t)\,e^{-pt}\,\mathrm{d}t = \mathcal{L}[t^2\,f(t)]
```

which means the general expression is:

```{math}
F^{(n)}(p) = \mathcal{L}[t^n\,f(t)]
```

This is a useful way to calculate Laplace transforms for functions which involve factors of $t$.

#### Worked examples

Find the transform of each of the following functions:

1. $f(t) = t \cosh(3t)$

2. $h(t) = t^2 \sin(2t)$

3. $f(t) = t g'(t)$

#### Worked example solutions

1. For $f(t) = t \cosh(3t)$, we need to consider using both the rule for compound functions with $t$:

   ```{math}
   F(p) = \mathcal{L}[t g(t)] = -G'(p), \quad \text{where } g(t) = \cosh(3t)
   ```

   and use the fact that $\cosh(t) = \cos(it)$.

   So, we then have:

   ```{math}
   G(p) = \frac{p}{p^2 - 9}, \quad G'(p) = - \frac{p^2 + 9}{(p^2 - 9)^2}
   ```

   Hence the transform looks like:

   ```{math}
   F(p) = \frac{p^2 + 9}{(p^2 - 9)^2}
   ```

2. For $h(t) = t^2 \sin(2t)$, we could use the fact that:

   ```{math}
   H(p) = \mathcal{L}[t f(t)] = -F'(p), \quad \text{where } f(t) = t \sin(2t)
   ```

   Or we could use:

   ```{math}
   H(p) = \mathcal{L}[t^2 f(t)] = F''(p), \quad \text{where } f(t) = \sin(2t)
   ```

   So calculating all the derivatives:

   ```{math}
   F(p) = \frac{2}{p^2 + 4}, \quad F'(p) = - \frac{4p}{(p^2 + 4)^2}, \quad F''(p) = \frac{12p^2-16}{(p^2+4)^3}
   ```

   The transform is then:

   ```{math}
   H(p) = \frac{12p^2 - 16}{(p^2 + 4)^3}
   ```

3. For $f(t) = t g'(t)$:

   ```{math}
   \mathcal{L}[t g'(t)] = -\frac{d}{dp} \mathcal{L}[g'(t)] = -\frac{d}{dp} \{p G(p) - g(0)\}
   ```

   Then we have:

   ```{math}
   = - \left( G(p) + p G'(p) - 0 \right) = - G(p) - p G'(p)
   ```

## Fractional powers of $t$

If the powers of $t$ are not a positive integer, then the situation is more complicated. We relied on the fact that:

```{math}
\mathcal{L}[t^n] = \frac{n}{p}\mathcal{L}[t^{n-1}] = \frac{n(n-1)}{p^2}\mathcal{L}[t^{n-2}] = \dots = \frac{n!}{p^{n+1}}
```

But if $n$ is not a natural number, then we will need to rely on the Gamma function $\Gamma(p)$, which is a natural generalization of the factorial function:

```{math}
\Gamma(p) = \int_0^\infty t^{p-1}\,e^{-t}\,\mathrm{d}t
```

This has the property that:

```{math}
\Gamma(p+1) = p\,\Gamma(p) \Rightarrow \Gamma(p) = (p-1)!
```

where $p > 0$ is the only requirement for this function now.

For $t^n$, we can use this result. There are some values of $\Gamma(p)$ which are exact and useful, the most important being $\Gamma\left(\frac{1}{2}\right) = \sqrt{\pi}$. Using this result, we see that to find $\mathcal{L}[t^{1/2}]$:

```{math}
\mathcal{L}[t^{1/2}] = \int_0^\infty t^{1/2}\,e^{-pt}\,\mathrm{d}t 
```

Solving this by parts:

```{math}
\begin{split}
u = t^{1/2} & \qquad v' = e^{-pt} \\
u' = \frac{1}{2}t^{-1/2} & \qquad v = -\frac{1}{p}e^{-pt}
\end{split}
```

This means that:

```{math}
\mathcal{L}[t^{1/2}] = -\left[ \frac{t^{1/2}}{p}e^{-pt} \right]_0^\infty + \frac{1}{2p}\int_0^\infty t^{-1/2}\,e^{-pt}\,\mathrm{d}t 
```

We notice that $\Gamma\left(\frac{1}{2}\right)$ has the form:

```{math}
\Gamma\left(\frac{1}{2}\right) = \int_0^\infty t^{-1/2}\,e^{-t}\,\mathrm{d}t = \sqrt{\pi}
```

So by changing variables, we see that:

```{math}
\int_0^\infty t^{-1/2}\,e^{-pt}\,\mathrm{d}t  = \frac{1}{p^{-1/2}\,p}\int_0^\infty (pt)^{-1/2}\,e^{-pt}\,\mathrm{d}(pt) = \frac{\sqrt{\pi}}{p^{1/2}}
```

Thus:

```{math}
\mathcal{L}[t^{1/2}] = -\left[ \frac{t^{1/2}}{p}e^{-pt} \right]_0^\infty + \frac{1}{2p}\frac{\sqrt{\pi}}{p^{1/2}}
```

Since the first term goes to zero, this means:

```{math}
\mathcal{L}[t^{1/2}] = \frac{\sqrt{\pi}}{2p^{3/2}}
```

#### Worked examples

1. $g(t) = t^{3/2}$
2. $f(t) = (10t)^{3/2}$

#### Worked examples solutions

1. For $g(t) = t^{3/2}$, we’ll need to notice that:

```{math}
\int_0^t \sqrt{v} \, dv = \frac{2}{3} t^{3/2} \quad \Rightarrow \quad t^{3/2} = \frac{3}{2} \int_0^t \sqrt{v} \, dv
```

Now, using:

```{math}
f(t) = \sqrt{t}, \quad F(p) = \frac{\sqrt{\pi}}{2p^{3/2}}
```

Then we get:

```{math}
G(p) = \frac{3 \sqrt{\pi}}{4 p^{5/2}}
```

2. For $f(t) = (10t)^{3/2}$, we will use the previous result. To see this, note that if $g(t) = t^{3/2}$, then:

```{math}
f(t) = g(10t)
```

Therefore, the transform is:

```{math}
F(p) = \frac{1}{10} G\left(\frac{p}{10}\right) = \frac{1}{10} \left( \frac{3 \sqrt{\pi}}{4 \left( \frac{p}{10} \right)^{5/2}} \right) = \frac{10^{3/2} 3 \sqrt{\pi}}{4 p^{5/2}}
```

## Solving ODE Using the Laplace Transform

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
## Inverse Laplace Transform

Consider a 2nd-order ODE

```{math}
A y''(t) + B y'(t) + C y(t) = f(t),
```

where the boundary conditions imposed on the function $ y $ are $ y(0) = y'(0) = 0 $, $ t \geq 0 $, and $ A $, $ B $, $ C $ are constant coefficients.

The Laplace transform of this equation gives

```{math}
A p^2 Y(p) + B p Y(p) + C Y(p) = F(p),
```

where $ Y(p) $ is the Laplace transform of $ y(t) $ and $ F(p) $ is the transform of $ f(t) $. From here, we find

```{math}
Y(p) = \frac{F(p)}{A p^2 + B p + C} = \frac{F(p)}{A(p + a)(p + b)},
```

where $ a $ and $ b $ are constants.

We already know the inverse Laplace transform of $ F(p) $ (it is given to us as $ f(t) $) and we can always find the inverse transform of

```{math}
\frac{1}{A(p + a)(p + b)}
```

by inspecting the table of Laplace transforms. Can we find the inverse transform of $ Y(p) $?

More generally, assume that inverse Laplace transforms of $ H(p) $ and $ G(p) $ are known functions $ h(t) $ and $ g(t) $, respectively. How do we find the inverse Laplace transform of $ H(p) G(p) $?

## Calculating Inverse Transforms by Convolution

Consider the product $ H(p) G(p) $, where $ H(p) $ and $ G(p) $ are Laplace transforms of $ h(t) $ and $ g(t) $, respectively.

```{math}
H(p) G(p) = \int_0^\infty h(s) e^{-ps}\mathrm{d}s\int_0^\infty g(t) e^{-pt}\mathrm{d}t= \int_0^\infty \int_0^\infty h(s) g(t) e^{-p(s + t)}\mathrm{d}s\mathrm{d}t.
```

Introduce a new variable $ r = s + t $ for any fixed $ t $. Then, $ s = r - t $ and $\mathrm{d}s=\mathrm{d}r $. To define the limits of integration with respect to $\mathrm{d}r $, we notice that $ r = t $ if $ s = 0 $ and $ r = \infty $ if $ s = \infty $. Therefore,

```{math}
H(p) G(p) = \int_0^\infty \left( \int_t^\infty h(r - t) g(t) e^{-pr}\mathrm{d}r \right) \mathrm{d}t.
```

The figure (a) below shows schematically the order of integration in this equation: each horizontal line corresponds to the inner integration from $r=t$ to $r = \infty$, so all lines together cover one half of the first quadrilateral, which corresponds to the outer integral for $0 \leq t < \infty $

![(a) Inner integral (over $r$): $t \leq r < 1$, outer integral (over $t$): $0 \leq t < 1$;(b) Inner integral (over $t$): $0 \leq t < r$, outer integral (over $r$): $0 \leq r < 1$.](convolution_integration.png)

We can change the order of integration with respect to $t$ and $r$ in the equation, as illustrated in the above figure (b), so as:

```{math}
H(p) G(p) = \int_0^\infty \left( \int_0^r h(r-t) g(t) \mathrm{d}t\right) e^{-pr} \,dr = \int_0^\infty \left[h \ast g\right]e^{-pr} \,dr .
```

This inner integral is called the convolution of functions $ g(x) $ and $ h(x) $:

```{math}
h \ast g = \int_0^r h(r-t) g(t) \mathrm{d}t
```
Thus, this integral can be written as

```{math}
H(p) G(p) = \int_0^\infty [h \ast g] e^{-pr}\mathrm{d}r,
```

i.e., the Laplace transform of a convolution of functions $ h(x) $ and $ g(x) $ equals the product of the Laplace transforms of these functions. In other words, $ h \ast g $ is the inverse Laplace transform of $ H(p) G(p) $.

What is interesting about this convolution integral is that it is commutative:

```{math}
h \ast g = g \ast h \Rightarrow \int_0^r h(r-t) g(t) \mathrm{d}t = \int_0^t g(t-r) h(r) \mathrm{d}r
```
---

### Example

Find the solution of the equation

```{math}
y'' + 3y' + 2y = e^{-t} \quad \text{with} \quad y(0) = y'(0) = 0
```

using the convolution method. After Laplace transform:

```{math}
p^2 Y(p) + 3p Y(p) + 2 Y(p) = \mathcal{L}(e^{-t}),
```

which gives

```{math}
Y(p) = \frac{\mathcal{L}(e^{-t})}{(p^2 + 3p + 2)} = \frac{\mathcal{L}(e^{-t})}{(p+1)(p+2)}.
```

The inverse transform of

```{math}
\frac{1}{(p+1)(p+2)} = \frac{1}{p+1} - \frac{1}{p+2}
```

is $ e^{-t} - e^{-2t} $.

Therefore,

```{math}
Y(p) = \mathcal{L}(e^{-t} - e^{-2t})\mathcal{L}(e^{-t}).
```

To find $ y(t) $, we need to calculate the convolution of $ e^{-t} - e^{-2t} $ and $ e^{-t} $:

```{math}
y(t) = \int_0^t g(\tau)\,h(t-\tau)\,\mathrm{d}\tau = \int_0^t \left[ e^{-\tau} - e^{-2\tau} \right] e^{-(t - \tau)} d\tau.
```

This simplifies to:

```{math}
y(t) = t e^{-t} + e^{-2t} - e^{-t}.
```

## Tables of Transforms

### Table of Functions 

We can put together these transforms into a table:

| $f(t)$  | $L\{f(t)\} = F(p)$ | Conditions |
|-----------|----------------------|------------|
| 1         | $\frac{1}{p}$      | $p > 0$  |
| $t$     | $\frac{1}{p^2}$    | $p > 0$  |
| $t^n$   | $\frac{n!}{p^{n+1}}$| $p > 0$  |
| $e^{at}$| $\frac{1}{p-a}$    | $p > a$  |
| $\sin(at)$| $\frac{a}{p^2 + a^2}$ | $p > 0$ |
| $\cos(at)$| $\frac{p}{p^2 + a^2}$ | $p > 0$ |
| $\sinh(at)$| $\frac{a}{p^2 - a^2}$ | $p > |a|$ |
| $\cosh(at)$| $\frac{p}{p^2 - a^2}$ | $p > |a|$ |
| $e^{at} \sin(bt)$| $\frac{b}{(p-a)^2 + b^2}$ | $p > a$ |
| $e^{at} \cos(bt)$| $\frac{p-a}{(p-a)^2 + b^2}$ | $p > a$ |
| $t \sin(bt)$| $\frac{2bp}{(p^2 + b^2)^2}$ | $p > 0$ |
| $t \cos(bt)$| $\frac{p^2 - b^2}{(p^2 + b^2)^2}$ | $p > 0$ |

### Table of Properties

Given the functions $f(t)$ and $g(t)$, and their respective Laplace transforms $F(p)$ and $G(p)$ such that:

```{math}
\begin{align}
f(t) &= \mathcal{L}^{-1}[F(p)],\\
g(t) &= \mathcal{L}^{-1}[G(p)],
\end{align}
```

then we can define a bunch of different Laplace Transforms properties:

| **Property**                  | **Time domain $t$**        | **Laplace domain $p$**            |
|--------------------------------|------------------------------|--------------------------------------|
| Linearity                      | $ a f(t) + b g(t) $        | $ a F(p) + b G(p) $               |
| Frequency-domain derivative     | $ t f(t) $                | $ -F'(p) $                        |
| Frequency-domain general derivative | $ t^n f(t) $         | $ (-1)^n F^{(n)}(p) $             |
| Derivative                     | $ f'(t) $                 | $ p F(p) - f(0^{-}) $             |
| Second derivative              | $ f''(t) $                | $ p^2 F(p) - p f(0) - f'(0) $     |
| General derivative             | $ f^{(n)}(t) $            | $ p^n F(p) - \sum_{k=1}^{n} p^{n-k} f^{(k-1)}(0) $ |
| Frequency shifting             | $ e^{at} f(t) $           | $ F(p - a) $                      |
| Time shifting I                | $ f(t - a) \,H(t - a) $   | $ e^{-ap} F(p) $ *                |
| Time shifting II               | $ f(t) \,H(t - a) $       | $ e^{-ap} \mathcal{L}\{f(t + a)] $ * |
| Time scaling                   | $ f(at) $                 | $ \frac{1}{a} F \left( \frac{p}{a} \right) $ |

*where $H(t)$ is the Heaviside step function.

