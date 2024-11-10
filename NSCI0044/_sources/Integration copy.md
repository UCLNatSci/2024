# Areas and Integration

## Definition of Integration

Let's start with a function $ f(x) $, suppose we are interested in finding the area between the $ x $ axis and the function? If the function is constant or at least linear, this is fairly straightforward:

![Linear Function](LinearFunction.png)

```{math}
\text{(Constant)} \quad \text{Area} = (b-a)\times c \quad\quad\quad \text{(Linear)} \quad \text{Area} = \frac{1}{2}(b - a)\times (c + d)
```

If the function is more complicated, say a polynomial, then we can break up the function interval $ x \in [a,\,b] $ into small rectangular segments and then sum them all up:

![Function Area](FunctionArea.png)
![Function Area 2](FunctionArea2.png)

Clearly, this is just an estimate of the function area, although we can improve this estimate by chopping up the interval into smaller segments:

![Finite Integral Function](FiniteIntegralFunction.png)

If we break up $ [a,\,b] $ into $ N $ intervals, of uniform width $ \Delta x $:

```{math}
\Delta x = x_{i} - x_{i-1} = \frac{b-a}{N}
```

then over the interval sliced up into $ N $ pieces:

```{math}
a = x_0 < x_1 < x_2 < \dots < x_{N-1} < x_N = b
```

The total area under the function is:

```{math}
A = \sum_{i=0}^{N} f(x_i) \Delta x
```

We can now take the limit of $ \Delta x \rightarrow 0 $ to get an infinitesimal $ \mathrm{d}x $, so we can go from summing up small finite areas to infinitesimal areas:

```{math}
\lim_{\Delta x \rightarrow 0} \left(\sum_{i=1}^{N} f(x_i) \Delta x \right) \longrightarrow \int_a^b f(x)\,\mathrm{d}x
```

We call this quantity the **Definite Integral** of the function $ f(x) $ between the **limits** $ [a,\,b] $, and the symbol $ \int $ is known as the **Integration Operator**. The function $ f(x) $ here is also called the **Integrand** and the process of finding an integral is known as **Integration**. If we want to work out the value of an integral without specific limits, this turns out to be a well-understood mathematical process too, known as finding the **Indefinite Integral**:

```{math}
\int f'(x)\,\mathrm{d}x = f(x) + C
```

where $ C $ is a constant. This process is called finding the **Anti-Derivative** and knowing a function’s anti-derivative means we can find the value of a function’s definite integral:

```{math}
\int_a^b f'(x)\,\mathrm{d}x = \Bigg[ f(x)\Bigg]_a^b = f(b) - f(a)
```

This statement is known as **The Fundamental Theorem of Calculus**. 

An example: Find $ \int_0^1 x\,\mathrm{d}x $:

First, we have to split up the interval, and $ f(x) $, into $ N $ equally spaced sections:

```{math}
\Delta x = \frac{1}{N} \Longrightarrow f(x_i) = \frac{i}{N}
```

We can also switch limits from $ \Delta x \rightarrow 0 $ to $ N \rightarrow \infty $:

```{math}
I = \lim_{\Delta x \rightarrow 0} \left[ \sum_{i=1}^{N} \left(\frac{i}{N}\right)\left(\frac{1}{N}\right)\right] = \lim_{N \rightarrow \infty} \left[\frac{1}{N^2}\left(\sum_{i=1}^{N} i \right)\right] = \lim_{N \rightarrow \infty}\frac{N(N+1)}{2N^2} = \frac{1}{2}
```

where we have used the expression for the sum: $ \sum_{i=1}^N i = \frac{1}{2}N(N+1) $.

We can apply what we know about differentiation to reverse the process to evaluate common integrals, for instance, if we know that:

```{math}
f(x) = x^n \Rightarrow f'(x) = n\,x^{n-1} \Longrightarrow f(x) = \frac{x^{n+1}}{n+1} \Rightarrow f'(x) = x^n
```

Since $\frac{\mathrm{d}}{\mathrm{d}x}\big(x^0\big) = 0$, indefinite integrals must include a constant:

```{math}
\int f'(x)\,\mathrm{d}x = f(x) + C
```

### Signed and Unsigned Areas

The value of the definite integral $\int_a^b f(x)\,\mathrm{d}x$ is the area between the function and the $x$ axis over the interval $[a,\,b]$ and it turns out the value of this integral is signed:

![Signed Area](SignedArea.png)

Areas above the $x$ axis produce a positive value of the integral and areas below the $x$ axis produce a negative value of the integral. The unsigned area is given by:

```{math}
\left|\int_a^b |f(x)|\,\mathrm{d}x \right|
```

An example:

```{math}
I_1 = \int_1^2 (-4x)\,\mathrm{d}x = \left[-\frac{4}{2}x^2\right]_0^1 = -2\bigg[ 2^2 - 1^2\bigg] = -2(3) = -6 < 0
```

```{math}
I_2 = \int_1^2 4x\,\mathrm{d}x = \left[\frac{4}{2}x^2\right]_0^1 = 2\bigg[ 2^2 - 1^2\bigg] = 2(3) = 6 > 0
```

### Limits

The limits of a definite integral can be swapped around, introducing a minus sign, this is equivalent to evaluating the integral the opposite way round:

```{math}
\int_a^b f'(x)\,\mathrm{d}x = f(b)-f(a) = -\bigg(f(a) - f(b) \bigg) = - \int_b^a f'(x)\,\mathrm{d}x
```

An example:

```{math}
I_3 = \int_1^4 x^2\,\mathrm{d}x = \bigg[\frac{1}{3}x^3\bigg]_1^2 = \frac{1}{3}\left(4^3 - 1^3\right) = \frac{63}{3} = 21
```

```{math}
I_4 = \int_4^1 x^2\,\mathrm{d}x = \bigg[\frac{1}{3}x^3\bigg]_2^1 = \frac{1}{3}\left(1^3 - 4^3\right) = -\frac{63}{3} = -21
```

### Area Between Curves

Suppose we have two functions, we can find the area between the two curves by subtracting the two integrals:

![Area Between Curves](AreaBetweenCurves.png)

which is written as:

```{math}
\int_a^b \bigg( g(x) - f(x)\bigg)\,\mathrm{d}x
```

where $g(x)$ is the upper curve and $f(x)$ is the lower curve. If the area between the curves is above the $x$ axis, then this is area should be positive and if we find a negative answer, then we have switched the order of the curves.

### Mean Value of a Function

For a function, $f(x)$, being integrated over a range $[a,\,b]$, is it possible to find a constant function which would have the same area over that range?

```{math}
c = \frac{1}{b-a}\int_a^b f(x)\,\mathrm{d}x
```

![Constant Function](ConstantFunction.png)


## Common Anti-Derivatives

#### Polynomial

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ a $ | $ 0 $ |
| $ a x^n $ | $ \frac{a x^{n+1}}{n+1} $ |
| $ (ax+b)^n $ | $ \frac{1}{a} \frac{(ax+b)^{n+1}}{n+1} $ |
| $ \frac{a}{x} $ | $ a\ln(x) $ |
| $ \frac{1}{ax+b} $ | $ \frac{1}{a}\ln(ax+b) $ |

#### Trigonometric

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ \sin(x) $ | $ -\cos(x) $ |
| $ \sin(ax+b) $ | $ -\frac{1}{a}\cos(ax+b) $ |
| $ \cos(x) $ | $ \sin(x) $ |
| $ \cos(ax+b) $ | $ \frac{1}{a}\sin(ax+b) $ |
| $ \sec^2(x) $ | $ \tan(x) $ |
| $ \sec(x)\,\tan(x) $ | $ \sec(x) $ |
| $ \csc(x)\,\cot(x) $ | $ -\csc(x) $ |
| $ \csc^2(x) $ | $ -\cot(x) $ |

#### Exponential

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ ae^x $ | $ ae^x $ |
| $ e^{ax+b} $ | $ \frac{1}{a}e^{ax+b} $ |
| $ a^x $ | $ \frac{a^x}{\ln(a)} $ |

#### Hyperbolic

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ \sinh(x) $ | $ \cosh(x) $ |
| $ \sinh(ax+b) $ | $ \frac{1}{a}\cosh(ax+b) $ |
| $ \cosh(x) $ | $ \sinh(x) $ |
| $ \cosh(ax+b) $ | $ \frac{1}{a}\sinh(ax+b) $ |
| $ \mathrm{sech}^2(x) $ | $ \tanh(x) $ |
| $ \mathrm{sech}(x)\,\tanh(x) $ | $ -\mathrm{sech}(x) $ |
| $ \mathrm{cosech}(x)\,\cot(x) $ | $ -\mathrm{cosech}(x) $ |
| $ \mathrm{cosech}^2(x) $ | $ -\coth(x) $ |

#### Inverse Trigonometric

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ \frac{1}{\sqrt{a^2 - x^2}} $ | $ \arcsin\left(\frac{x}{a}\right) $ |
| $ -\frac{1}{\sqrt{a^2 - x^2}} $ | $ \arccos\left(\frac{x}{a}\right) $ |
| $ \frac{1}{a^2 + x^2} $ | $ \frac{1}{a}\arctan\left(\frac{x}{a}\right) $ |

#### Inverse Hyperbolic

| $ f'(x) $ | $ f(x) $ |
|-------------|------------|
| $ \frac{1}{\sqrt{x^2 + a^2}} $ | $ \textrm{arsinh}\left(\frac{x}{a}\right) $ |
| $ \frac{1}{\sqrt{x^2 - a^2}} $ | $ \textrm{arcosh}\left(\frac{x}{a}\right) $ |
| $ \frac{1}{a^2 - x^2} $ | $ \textrm{artanh}\left(\frac{x}{a}\right) $ |


## Integration by Parts

Recall the product rule:
```{math}
\frac{\mathrm{d}d}{\mathrm{d}x}\bigg(f(x) \,g(x) \bigg) = \frac{\mathrm{d}f(x)}{\mathrm{d}x} g(x) + f(x) \frac{\mathrm{d}g(x)}{\mathrm{d}x}
```

We can rearrange this and integrate *w.r.t.* $x$:
```{math}
\frac{\mathrm{d}f(x)}{\mathrm{d}x} g(x) = \frac{\mathrm{d}d}{\mathrm{d}x}\bigg(f(x) \,g(x) \bigg) -  f(x) \frac{\mathrm{d}g(x)}{\mathrm{d}x}
```
```{math}
\int \frac{\mathrm{d}f(x)}{\mathrm{d}x} g(x)\,\mathrm{d}x = \int\frac{\mathrm{d}d}{\mathrm{d}x}\bigg(f(x) \,g(x) \bigg)\,\mathrm{d}x -  \int f(x) \frac{\mathrm{d}g(x)}{\mathrm{d}x}\,\mathrm{d}x
```

By the fundamental theorem of calculus, the first term on the RHS becomes simplified:
```{math}
\int f'(x) \,g(x)\,\mathrm{d}x = f(x) \,g(x) - \int f(x) \,g'(x)\,\mathrm{d}x
```

Sometimes this form of an integral allows us to make progress in solving a problem, because the term $\int f(x)\,g'(x)\,\mathrm{d}x$ may be easier to integrate than $\int f'(x) \,g(x) \,\mathrm{d}x$.

An example:
```{math}
I_1 = \int x \, e^{x}\,\mathrm{d}x
```

Firstly we need to split it up into $f'$ and $g$:
```{math}
f' = e^x, \quad g = x
```
```{math}
f = e^x,\quad g' = 1
```
```{math}
I_1 = x e^x - \int e^x\,\mathrm{d}x = (x-1)e^x + C
```

Given the form of a particular integration, how do we know which function to pick for $f'(x)$ and which for $g(x)$? A simple way is to use the mnemonic **LATE**:

- **L**ogarithmic Term
- **A**lgebraic Term
- **T**rigonometric Term
- **E**xponential Term

This list tells the order of preference for the term to be differentiated – $g(x) \rightarrow g'(x)$. The exponential function is at the bottom because it is usually the easiest to integrate, while the logarithmic term is usually the hardest.

An example, integrate:
```{math}
I_2 = \int x \ln(x)\,\mathrm{d}x
```

Since **L** falls before **A** in **LATE**, we pick:
```{math}
f' = x, \quad g = \ln(x)
```
```{math}
f = \frac{1}{2}x^2, \quad g' = \frac{1}{x}
```

And so integrating by parts we find:
```{math}
I_2 = \frac{1}{2} \,x^2 \,\ln(x) - \int \frac{1}{2} \,x \,\mathrm{d}x = \frac{1}{2} \, x^2 \left(\ln(x) - \frac{1}{2} \right) + C
```

What about definite integrals? Same story but with limits:
```{math}
\int_a^b f' \,g\,\mathrm{d}x = \bigg[f \,g\bigg]_a^b -  \int_a^b f \, g'\,\mathrm{d}x
```

Sometimes it is not always obvious that there *are* two functions in the integration expression. However, this can be remedied using a simple trick.

An example:
```{math}
I_3 = \int \ln(x)\,\mathrm{d}x
```

This should be seen as:
```{math}
I_3 = \int x^0\,\ln(x)\,\mathrm{d}x
```

Since we have both **L** and **A** from **LATE**, we pick:
```{math}
f' = x^0, \quad g = \ln(x)
```
```{math}
f = x^1
```
## Integration Techniques

- **Chain Rule in Reverse**
  1. 
  ```{math}
  I = \int [f(x)]^n\,f'(x)\,\mathrm{d}x = \frac{\left[f(x)\right]^{n+1}}{n+1} + C
  ```
  An example: 
  ```{math}
  I_1 = \int \sin^2(x)\cos(x)\,\mathrm{d}x \\ 
  f(x) = \sin(x) \Rightarrow f'(x) = \cos(x) \\ 
  I_1 = \frac{1}{3}\sin^3(x) + C
  ```

  2. 
  ```{math}
  I = \int \frac{f'(x)}{f(x)}\,\mathrm{d}x = \ln(f(x)) + C
  ```
  An example:
  ```{math}
  I_2 = \int \frac{x}{3x^2 + 7}\,\mathrm{d}x \\ 
  f(x) = 3x^2 + 7 \Rightarrow f'(x) = 6x \\ 
  I_2 = \frac{1}{6} \int \frac{6x}{3x^2 + 7}\,\mathrm{d}x = \frac{1}{6} \ln(3x^2 + 7) + C
  ```
  
  A trigonometric example:
  ```{math}
  I_3 = \int \tan(x)\,\mathrm{d}x = \int \frac{\sin(x)}{\cos(x)}\,\mathrm{d}x\\
  f(x) = \cos(x) \Rightarrow f'(x) = - \sin(x)\\ 
  I_3 = -\int \frac{-\sin(x)}{\cos(x)}\,\mathrm{d}x = - \ln(\cos(x)) + C 
  ```

  3. 
  ```{math}
  I = \int f'(x) e^{f(x)}\,\mathrm{d}x = e^{f(x)} + C
  ```
  An example:
  ```{math}
  I_4 = \int \cos(x) \,e^{\sin(x)}\,\mathrm{d}x\\
  f(x) = \sin(x) \Rightarrow f'(x) = \cos(x) \\
  I_4  = e^{\sin(x)} + C 
  ```


- **Integrating Twice**  
Consider the following integral:
```{math}
I_7 = \int e^x\, \sin(x)\,\mathrm{d}x
```
this is a good candidate to integrate by parts, we have **T** and **E** in **LIATE**:
```{math}
f'(x) = e^x, \quad g(x) = \sin(x) 
```
```{math}
f(x) = e^x, \quad g'(x) = \cos(x) 
```
```{math}
I_7 = e^x\, \sin(x) - \int e^x\,\cos(x)\,\mathrm{d}x
```
This does not appear to be any easier to work out! However, if we integrate by parts again:
```{math}
f'(x) = e^x, \quad g(x) = \cos(x) 
```
```{math}
f(x) = e^x, \quad g'(x) = -\sin(x) 
```
```{math}
I_7 = e^x\, \sin(x) - e^x\,\cos(x) - \int e^x\,\sin(x)\,\mathrm{d}x 
```
It appears we still have not simplified the problem, but now look at the last term:
```{math}
I_7 = e^x\, \sin(x) - e^x\,\cos(x) - I_7 + C
```
```{math}
\Rightarrow 2I_7 = e^x\, \sin(x) - e^x\,\cos(x) + C
```
```{math}
I_7 = \frac{1}{2}\,e^x\, \left(\sin(x) - \cos(x)\right) + C
```
and so we see by integrating twice, the integral has been solved.  

