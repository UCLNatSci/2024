# Rates of Change and Differentiation

## Definition

A question that often crops up in mathematics and science is, how do we find the rate at which a quantity changes? Let's start by considering the simplest case of a function, a straight line, which follows the equation $y = mx + c$:
  
![2DSlope](2DSlope.png)

As we see, the rate of change, known as the **Gradient**, $m$, is found from the ratio of the changes in the $y$ and $x$ directions:
  
```{math}
m = \frac{\Delta y}{\Delta x} = \frac{y_2 - y_1}{x_2 - x_1}
```

But what about for a curve? Clearly, the gradient of this curve varies from point to point:
  
![Tangent-calculus](Tangent-calculus.png)

We can start at a point $x$ and find the gradient of the **Tangent** to the curve; however, we could also overshoot the curve and draw a line connecting the curve with a neighboring point $x+h$ (known as a **Secant** line). By drawing more secant lines for smaller choices of $h$, we can gradually build up a value for the gradient at the point:

![FindingTangent](FindingTangent.png)

We can do this mathematically, for the function $y = f(x)$, by taking the limit for decreasing $h$, which we denote by a change $\Delta x$:
  
```{math}
\lim_{\Delta x \rightarrow 0}\frac{y(x + \Delta x) - y(x)}{\Delta x} = \frac{\textrm{d}y}{\textrm{d}x} 
```

We call this the **Derivative** of the function, and the process of finding the derivative is known as **Differentiation**. The quantities $\textrm{d}y$ and $\textrm{d}x$ are known as **Infinitesimals** and represent changes of a variable, say $x$, in the limit of $\Delta x \rightarrow 0$. Sometimes, if we are just using $f(x)$ to describe a function, we use the notation $f'(x)$ for the derivative. We should note that the derivative is properly called a **Mathematical Operator**, which means we have to be careful how it is used. Technically speaking, we are finding $\frac{\textrm{d}}{\textrm{d}x}\bigg(y\bigg)$, and for the choice of a function, such as $y = x^2 + 2x + 1$, we could write:
  
```{math}
\frac{\textrm{d}}{\textrm{d}x}\left(x^2 + 2x + 1\right)
```

The limit definition allows us to find the derivatives for different types of functions. 

An example: find the derivative of $y = x^2$:
  
```{math}
\frac{\textrm{d}y}{\textrm{d}x} = \lim_{\Delta x \rightarrow 0}\frac{y(x + \Delta x) - y(x)}{\Delta x} = \lim_{\Delta x \rightarrow 0}\frac{(x + \Delta x)^2 - x^2}{\Delta x}
```
  
```{math}
= \lim_{\Delta x \rightarrow 0} \frac{(x^2 + 2x\Delta x + \Delta x^2) - x^2}{\Delta x} = \lim_{\Delta x \rightarrow 0} \left(2x + \Delta x \right) = 2x
```

For polynomials in general, using the binomial theorem, for $y = x^n$:

```{math}
\frac{\textrm{d}y}{\textrm{d}x} = \lim_{\Delta x \rightarrow 0}\frac{(x + \Delta x)^n - x^n}{\Delta x} = \lim_{\Delta x \rightarrow 0} \frac{(x^n + nx^{n-1}\Delta x + \mathcal{O}(\Delta x^2) + \dots) - x^n}{\Delta x}
```
  
```{math}
= \lim_{\Delta x \rightarrow 0} \left( nx^{n-1} + \mathcal{O}(\Delta x) + \dots \right) = nx^{n-1}
```

where $\mathcal{O}(\Delta x)$ is mathematical notation for terms of order $\Delta x$.

## Differentiating Polynomial Functions
Using the limit definition, we can find the derivative for a range of different functions. We recall that for polynomials:

$$
f(x) = a\,x^n \Rightarrow f'(x) = a\,n\,x^{n-1}
$$

where $a$ is a constant, and this follows from the limit definition and binomial theorem. For the case of a constant:

$$
f(x) = a = a\,x^0 \Rightarrow f'(x) = 0
$$

which makes sense since if the function is constant, the gradient is zero, hence zero derivative. We should notice that for the same function with a shift, we see the gradient will be the same:

![Finding Tangent Polynomial](FindingTangentPolynomial.png)

## Differentiating Functions
We can use the limit definition to differentiate different types of functions:

### Trigonometric Functions
  
```{math}
  \frac{\textrm{d}}{\textrm{d}x}\bigg(\sin(x)\bigg) &= \lim_{\Delta x \rightarrow 0}\left(\frac{\sin(x + \Delta x) - \sin(x)}{\Delta x} \right)\\
  &= \lim_{\Delta x \rightarrow 0}\left(\frac{\sin(x)\cos(\Delta x) + \cos(x)\sin(\Delta x) - \sin(x)}{\Delta x} \right)\\
  &= \lim_{\Delta x \rightarrow 0}\left(\frac{\sin(x)(\cos(\Delta x)-1) + \cos(x)\sin(\Delta x)}{\Delta x} \right)
```

```{math}
  \frac{\textrm{d}}{\textrm{d}x}\bigg(\cos(x)\bigg) &= \lim_{\Delta x \rightarrow 0}\left(\frac{\cos(x + \Delta x) - \cos(x)}{\Delta x} \right) \\
  &= \lim_{\Delta x \rightarrow 0}\left(\frac{\cos(x)\cos(\Delta x) - \sin(x)\sin(\Delta x) - \cos(x)}{\Delta x} \right)\\
  &= \lim_{\Delta x \rightarrow 0}\left(\frac{\cos(x)(\cos(\Delta x)-1) -\sin(x)\sin(\Delta x)}{\Delta x} \right)
```

  Next, we can show (from geometric considerations) in the limit of $ |\Delta\theta| \ll 1 $:

```{math}
  \frac{\sin(\Delta\theta)}{\Delta\theta} &= 1 + \mathcal{O}\left(\Delta \theta^2\right) + \dots\\
  \frac{\cos(\Delta \theta) - 1}{\Delta \theta}  &= -\frac{1}{2}\Delta \theta + \mathcal{O}\left(\Delta \theta^3\right) + \dots
```

  Which means the derivatives are:

```{math}
  \frac{\textrm{d}}{\textrm{d}x}\bigg(\sin(x)\bigg) = \cos(x) \quad \quad \frac{\textrm{d}}{\textrm{d}x}\bigg(\cos(x)\bigg) = -\sin(x)
```

### Exponential Functions

```{math}
  \frac{\textrm{d}}{\textrm{d}x}\bigg(e^x\bigg) = \lim_{\Delta x \rightarrow 0}\left(\frac{e^{x +\Delta x} - e^x}{\Delta x} \right) =  e^x\left(\lim_{\Delta x \rightarrow 0}\left(\frac{e^{\Delta x} - 1}{\Delta x} \right)\right)
```

Using the definition of the exponential:
 
```{math}
  e^{\Delta x} &= \lim_{n\rightarrow\infty}\left(1 + \frac{\Delta x}{n}\right)^n \\
  \Rightarrow \frac{\textrm{d}}{\textrm{d}x}\bigg(e^x\bigg) &= e^x\lim_{\Delta x \rightarrow 0}\lim_{n\rightarrow\infty}\left[\frac{1}{\Delta x}\left(\left(1 + \frac{\Delta x}{n}\right)^n - 1 \right)\right]\\
  &=  e^x \lim_{\Delta x \rightarrow 0}\lim_{n\rightarrow\infty}\left[\frac{1}{\Delta x}\left(\left(1 + n\frac{\Delta x}{n} + \frac{n(n-1)}{2!}\frac{(\Delta x)^2}{n^2} + \dots \right)- 1 \right)\right]\\
  &= e^x \lim_{\Delta x \rightarrow 0}\lim_{n\rightarrow\infty}\left(1 + \mathcal{O}\left(\frac{\Delta x}{n}\right) + \dots\right)\\
  \Rightarrow \frac{\textrm{d}}{\textrm{d}x}\bigg(e^x\bigg) &= e^x
```

### Logarithmic Functions

```{math}
  \frac{\textrm{d}}{\textrm{d}x}\bigg(\ln(x)\bigg) &= \lim_{\Delta x \rightarrow 0}\left(\frac{\ln(x +\Delta x) - \ln(x)}{\Delta x} \right) =  \lim_{\Delta x \rightarrow 0}\left(\frac{1}{\Delta x} \ln\left( 1 + \frac{\Delta x}{x}\right)\right)\\
  &= \lim_{\Delta x \rightarrow 0}\left(\ln\left( 1 + \frac{\Delta x}{x}\right)^{1/\Delta x}\right)
```

Using the definition of the exponential, with $ n = 1 / \Delta x $:

```{math}
  e^{1/x} &= \lim_{\Delta x \rightarrow 0}\left(1 + \frac{\Delta x}{x}\right)^{1/\Delta x}\\
  \Rightarrow \frac{\textrm{d}}{\textrm{d}x}\bigg(\ln(x)\bigg) &= \ln\bigg(e^{1/x}\bigg) = \frac{1}{x}
```



## Differentiation Rules
There are three main differentiation rules:

### Product Rule

  $$
  y = f(x) \,g(x) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{\textrm{d}f(x)}{\textrm{d}x} g(x) + f(x) \frac{\textrm{d}g(x)}{\textrm{d}x}
  $$

  An example:

  $$
  y = x^2 \sin(x) \\
  \frac{\textrm{d}y}{\textrm{d}x} = 2x \sin(x) + x^2 \cos(x)
  $$

### Quotient Rule

  $$
  y = \frac{f(x)}{g(x)} \Rightarrow y'(x) = \frac{f'(x) g(x) - f(x) g'(x)}{g^2(x)}
  $$

  An example:

  $$
  y = \tan(x) = \frac{\sin(x)}{\cos(x)} \\
  \frac{\textrm{d}y}{\textrm{d}x} = \frac{\cos(x) \cos(x) - (-\sin(x))\sin(x) }{\cos^2(x)} =  \frac{1}{\cos^2(x)} \\
  = \sec^2(x)
  $$

### Chain Rule

  $$
  y = y(f(x)) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{\textrm{d}y}{\textrm{d}f}\frac{\textrm{d}f}{\textrm{d}x}
  $$

  An example:

  $$
  y = \sin(x^2) \\
  y = \sin(f),\, f = x^2 \\
  \frac{\textrm{d}y}{\textrm{d}f} = \cos(f), \, \frac{\textrm{d}f}{\textrm{d}x} = 2x \\
  \frac{\textrm{d}y}{\textrm{d}x} = \frac{\textrm{d}y}{\textrm{d}f}\frac{\textrm{d}f}{\textrm{d}x} = 2x \cos(f) \\
  = 2x \cos(x^2)
  $$

There are two further differentiation techniques you need to know:

### Implicit Differentiation

  $$
  f(y) = g(x) \Rightarrow f'(y) \frac{\textrm{d}y}{\textrm{d}x} = g'(x)
  $$

  An example: Find an expression for $ \frac{\textrm{d}y}{\textrm{d}x} $ given $ \sin(y) = x^2 $:

  $$
  \cos(y) \frac{\textrm{d}y}{\textrm{d}x} = 2x \\
  \frac{\textrm{d}y}{\textrm{d}x} = \frac{2x}{\cos(y)} = \frac{2x}{\sqrt{1-\sin^2(y)}} \\
  = \frac{2x}{\sqrt{1-x^4}}
  $$

### Parametric Differentiation

  $$
  x=x(t),\quad y=y(t) \\
  \frac{\textrm{d}y}{\textrm{d}x} = \frac{\textrm{d}y}{\textrm{d}t}\frac{\textrm{d}t}{\textrm{d}x} = \frac{\textrm{d}y}{\textrm{d}t} \left/\frac{\textrm{d}x}{\textrm{d}t}\right.
  $$

  An example, find $ \frac{\textrm{d}y}{\textrm{d}x} $ given:

  $$
  x = \sin(t),\, y = \cos(t)
  $$

  To proceed, we first differentiate $ x,\,y $ with respect to $ t $:

  $$
  x'(t) = \cos(t),\, y' = -\sin(t)
  $$

  and then to find the derivative of $ y $ with respect to $ x $:

  $$
  \frac{\textrm{d}y}{\textrm{d}x} = -\frac{\sin(t)}{\cos(t)} = -\frac{x}{y}
  $$

  To check, we can try to eliminate $ t $ and differentiate implicitly:

  $$
  x^2 + y^2 = \cos^2(t) + \sin^2(t) = 1 \\
  \Rightarrow 2x + 2y \frac{\textrm{d}y}{\textrm{d}x} = 0 \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = -\frac{x}{y}
  $$

  although it is not always possible to do this explicitly!

## Differentiation Tricks
By applying some of these rules, we find a series of patterns in different functions that can make differentiation easier and quicker to perform:

### Trigonometric

  $$
  y = \sin(f(x)) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = f'(x) \cos(f(x))
  $$

  An example: 

  $$
  \sin(ax+b) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = a \cos(ax+b)
  $$

### Hyperbolic

  $$
  y = \cosh(f(x)) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = f'(x) \sinh(f(x))
  $$

  An example: 

  $$
  \cosh(ax^3+bx) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = (3ax^2 + b) \sinh(ax^3+bx)
  $$

### Inverse Trigonometric

  $$
  y = \arcsin(x)
  $$

  The easiest way to deal with these is to invert the function, then differentiate implicitly and finally simplify the resulting expression:

  $$
  \sin(y) = x \\
  \cos(y) \frac{\textrm{d}y}{\textrm{d}x} = 1 \\
  \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{1}{\cos(y)} = \frac{1}{\sqrt{1-\sin^2(y)}} = \frac{1}{\sqrt{1 - x^2}}
  $$

  The next level of complication comes for functions like $ y = \arctan(x) $:

  $$
  y = \arctan(x) \\
  \tan(y) = x \\
  \sec^2(x)\frac{\textrm{d}y}{\textrm{d}x} = 1 \\
  \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{1}{\sec^2(y)} = \frac{1}{1 + \tan^2(y)} = \frac{1}{1 + x^2}
  $$

### Exponential

  $$
  y = e^{f(x)} \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = f'(x) e^{f(x)}
  $$

  An example: 

  $$
  y = e^{ax^2+b} \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = 2ax e^{ax^2+b}
  $$

### Logarithmic

  $$
  y = \ln(f(x)) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{f'(x)}{f(x)}
  $$

  An example: 

  $$
  y = \ln(x^2 + 3) \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} = \frac{2x}{x^2+3}
  $$

### Powers

  $$
  y = a^x
  $$

  Although we have a simple derivative for $ y = e^x $, the derivative of other numbers to the power of $ x $ is less simple, such as $ y = 2^x $. However, a trick can be employed here, by applying logarithms:

  $$
  y = 2^x \Rightarrow \ln y = \ln (2^x) = x \ln 2
  $$

  Now exponentiate both sides: 

  $$
  y = e^{x \ln 2}
  $$

  and so the derivative is just a slightly more complicated exponential type: 

  $$
  \frac{\textrm{d}y}{\textrm{d}x} = e^{x \ln 2} \ln 2 = 2^x \ln 2 
  $$

  So the general expression is 

  $$
  y = a^x \Rightarrow \frac{\textrm{d}y}{\textrm{d}x} =  a^x \ln a
  $$

## Finding Stationary Points
An application of differentiation is to find a function $f(x)$'s **Stationary Points** (SP's), where we are searching for solutions to $f'(x) = 0$. There are three distinct types of SP:

![Stationary Points](StationaryPoints2.png)

We see that we need the first derivative to be zero, but the sign of the second derivative can indicate the type of stationary point.  
An example, find the coordinate(s) and nature of all the stationary point(s) for:
```{math}
f(x) = x^3 - 27x
```
Firstly, find expressions for all the relevant derivatives:
```{math}
f(x) = x^3 - 27x \Longrightarrow f'(x) = 3x^2 - 27 \Longrightarrow f''(x) = 6x
```
Then find the $x$ coordinates for the SP's using $f'(x) = 0$:
```{math}
f'(x) = 3x^2 - 27 = 3(x^2-9) = 3(x+3)(x-3) = 0 \Rightarrow x = \pm 3
```
Finally, substitute in $x$ values to find the $y$ coordinates and so identify the type of SP:
```{math}
\begin{array}{lcl}
    f(3) = 3^3 - 27(3) = -54 & & f(-3) = (-3)^3 - 27(-3) = 54  \\
    f''(3) = 18 > 0 & & f''(-3) = -18 < 0
\end{array}
```
Therefore $f(x)$ has two SP's, a minima at $(3, -54)$ and a maxima at $(-3, 54)$.  

