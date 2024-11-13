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

*Derivative of Sine*:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} \sin(x) = \cos(x)
   ```
   - The derivative of $\sin(x)$ is $\cos(x)$.
   - This is because the slope of the sine curve at any point $x$ is given by the value of $\cos(x)$ at that point.

*Derivative of Cosine*:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} \cos(x) = -\sin(x)
   ```
   - The derivative of $\cos(x)$ is $-\sin(x)$.
   - The negative sign appears because the cosine curve decreases where sine increases, and vice versa.

*Higher Derivatives:*

Differentiating $\sin(x)$ twice returns it as $-\sin(x)$:
  ```{math}
  \frac{\mathrm{d}^2}{\mathrm{d}x^2} \sin(x) = -\sin(x)
  ```

Similarly, differentiating $\cos(x)$ twice returns it as $-\cos(x)$:
  ```{math}
  \frac{\mathrm{d}^2}{\mathrm{d}x^2} \cos(x) = -\cos(x)
  ```

This cyclical pattern in higher derivatives of sine and cosine is often useful in applications like oscillations and wave equations.

Below is a graph showing the sine function $ y = \sin(x) $ and its derivative $ y' = \cos(x) $.

![Sine and Cosine Derivative Graph](sine_cosine_derivative_graph.png)

Below is a graph showing the cosine function $ y = \cos(x) $ and its derivative $ y' = -\sin(x) $.

![Cosine and Negative Sine Derivative Graph](cosine_negative_sine_derivative_graph.png)



### Exponential Functions

*Derivative of the Natural Exponential Function*:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} e^x = e^x
   ```
   - The exponential function $ e^x $ is unique because it is its own derivative.
   - This means that the rate of change of $ e^x $ at any point $ x $ is exactly the value of $ e^x $ at that point.

*Derivative of $ a^x $ (Exponential Function with Base $ a $)*:

To find the derivative of an exponential function with base $ a $, such as $ y = a^x $, we can use the definition of the exponential function in terms of $ e $ and apply the chain rule.

*Step 1: Express $ a^x $ in Terms of $ e $*
Any exponential function $ a^x $ can be rewritten in terms of the natural exponential function $ e^x $ by noting that:
```{math}
a^x = e^{x \ln(a)}
```
This is because $ e^{x \ln(a)} $ represents "raising $ e $" to a power that is equivalent to $ a^x $. Here, $ \ln(a) $ is the natural logarithm of $ a $.

*Step 2: Differentiate Using the Chain Rule*
Now, to differentiate $ y = a^x = e^{x \ln(a)} $ with respect to $ x $, we can use the chain rule:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x} a^x = \frac{\mathrm{d}}{\mathrm{d}x} e^{x \ln(a)}
```

Using the chain rule, we differentiate the outer function $ e^{x \ln(a)} $, treating $ x \ln(a) $ as the inner function:
```{math}
= e^{x \ln(a)} \cdot \frac{\mathrm{d}}{\mathrm{d}x} (x \ln(a))
```

Now, differentiate the inner function $ x \ln(a) $:
```{math}
= e^{x \ln(a)} \cdot \ln(a)
```

*Step 3: Substitute Back for $ e^{x \ln(a)} $*
Since $ e^{x \ln(a)} = a^x $, we can substitute back:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} a^x = a^x \ln(a)
```

Thus, the derivative of $ a^x $ is:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} a^x = a^x \ln(a)
```
The term $ \ln(a) $ acts as a scaling factor that depends on the base $ a $, meaning that each base $ a $ scales the exponential growth rate differently.

*Example Calculation:*
For example, if $ y = 2^x $, then:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} 2^x = 2^x \ln(2)
```
This tells us that $ 2^x $ grows faster than $ e^x $ by a factor of $ \ln(2) $, which is approximately $ 0.693 $.

*Higher Derivatives:*

The exponential function $ e^x $ has the special property that all higher derivatives are also $ e^x $:
- **Second Derivative of $ e^x $**:
  ```{math}
  \frac{\mathrm{d}^2}{\mathrm{d}x^2} e^x = e^x
  ```

For other exponential functions $ a^x $:
- **Second Derivative of $ a^x $**:
  ```{math}
  \frac{\mathrm{d}^2}{\mathrm{d}x^2} a^x = a^x (\ln(a))^2
  ```
  - Each derivative introduces another factor of $ \ln(a) $.

Below is a graph showing $ y = e^x $ and its derivative $ y' = e^x $ on the left and a graph showing $ y = 2^x $ and its derivative $ y' = 2^x \ln(2) $ to the right.

![Exponential Derivative Graph](exponential_derivative_graph.png)


### Logarithmic Functions

*Derivative of $ \ln(x) $*:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} \ln(x) = \frac{1}{x}
   ```
   - This derivative tells us that the rate of change of $ \ln(x) $ at any point $ x $ is inversely proportional to $ x $.
   - It is only defined for $ x > 0 $ because the natural logarithm $ \ln(x) $ is only defined for positive $ x $ values.

*Derivative of Logarithms with Other Bases:*
For logarithms with bases other than $ e $, such as $ \log_a(x) $ where $ a $ is the base, we can use the change of base formula to rewrite it in terms of $ \ln(x) $:
```{math}
\log_a(x) = \frac{\ln(x)}{\ln(a)}
```

Using this, we can derive the derivative as follows:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} \log_a(x) = \frac{1}{x \ln(a)}
```
- The factor $ \ln(a) $ appears in the denominator and scales the rate of change according to the base $ a $.

*Higher Derivatives:*

The higher derivatives of $ \ln(x) $ can be calculated by successive differentiation:
- **Second Derivative of $ \ln(x) $**:
  ```{math}
  \frac{\mathrm{d}^2}{\mathrm{d}x^2} \ln(x) = -\frac{1}{x^2}
  ```
  - This shows that the concavity of $ \ln(x) $ changes as $ x $ increases.

Below is a graph showing $ y = \ln(x) $ and its derivative $ y' = \frac{1}{x} $ on the left and a graph showing $ y = \log_2(x) $ and its derivative $ y' = \frac{1}{x \ln(2)} $ on the right.

![Natural Logarithm Derivative Graph](ln_derivative_graph.png)


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


*Chain Rule with Sine and Cosine:*

When differentiating compositions involving sine and cosine, use the chain rule:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x} \sin(f(x)) = \cos(f(x)) \, f'(x)
```
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} \cos(f(x)) = -\sin(f(x)) \, f'(x)
```

*Examples:*
1. For $ y = \sin(3x) $:
   ```{math}
   y' = 3 \cos(3x)
   ```
   
2. For $ y = \cos(5x^2) $:
   ```{math}
   y' = -10x \sin(5x^2)
   ```


*Chain Rule with Exponential Functions:*

When differentiating compositions involving exponential functions, use the chain rule:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x} e^{f(x)} = e^{f(x)} \cdot f'(x)
```
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} a^{f(x)} = a^{f(x)} \ln(a) \, f'(x)
```

*Examples:*
1. For $ y = e^{3x} $:
   ```{math}
   y' = 3 e^{3x}
   ```
   
2. For $ y = 2^{5x^2} $:
   ```{math}
   y' = 10x \cdot 2^{5x^2} \ln(2)
   ```


*Chain Rule with Logarithmic Functions:*

When differentiating compositions involving logarithmic functions, use the chain rule:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x} \ln(f(x)) = \frac{1}{f(x)} \, f'(x)
```
```{math}
\frac{\mathrm{d}}{\mathrm{d}x} \log_a(f(x)) = \frac{1}{f(x) \ln(a)} \, f'(x)
```

*Examples*
1. For $ y = \ln(3x) $:
   ```{math}
   y' = \frac{1}{3x} \cdot 3 = \frac{1}{x}
   ```

2. For $ y = \log_2(x^2 + 1) $:
   ```{math}
   y' = \frac{1}{(x^2 + 1) \ln(2)} \cdot 2x = \frac{2x}{(x^2 + 1) \ln(2)}
   ```


### Implicit Differentiation

Implicit differentiation is used when a function is given in an **implicit form** rather than an explicit form. In implicit functions, $ y $ is not isolated on one side of the equation, so we differentiate both $ x $ and $ y $ as we work through the equation.

*Steps for Implicit Differentiation:*

1. Differentiate both sides of the equation with respect to $ x $.
2. When differentiating terms involving $ y $, treat $ y $ as a function of $ x $ and apply the chain rule: 
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} \, y = y' = \frac{\mathrm{d}y}{\mathrm{d}x}
   ```
3. Solve for $ y' $ (or $ \frac{\mathrm{d}y}{\mathrm{d}x} $).

*Examples:*

1. For the equation $ x^2 + y^2 = 25 $, differentiate both sides with respect to $ x $:
```{math}
2x + 2y \cdot \frac{\mathrm{d}y}{\mathrm{d}x} = 0
```
Solving for $ \frac{\mathrm{d}y}{\mathrm{d}x} $ (i.e., $ y' $):
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = -\frac{x}{y}
```

2. For the equation $ x^2y + y^2 = 4 $, differentiate both sides with respect to $ x $:

Differentiate Each Term:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} (x^2y) + \frac{\mathrm{d}}{\mathrm{d}x} (y^2) = \frac{\mathrm{d}}{\mathrm{d}x} (4)
   ```
Apply the Product Rule to $ x^2y $ and the Chain Rule to $ y^2 $:
   ```{math}
   (2x)y + x^2 \cdot \frac{\mathrm{d}y}{\mathrm{d}x} + 2y \cdot \frac{\mathrm{d}y}{\mathrm{d}x} = 0
   ```
Combine Terms and solve for $ \frac{\mathrm{d}y}{\mathrm{d}x} $:
   ```{math}
   x^2 \frac{\mathrm{d}y}{\mathrm{d}x} + 2y \frac{\mathrm{d}y}{\mathrm{d}x} = -2xy
   ```
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} (x^2 + 2y) = -2xy
   ```
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} = \frac{-2xy}{x^2 + 2y}
   ```

3. For the equation $ \sin(xy) = x + y $, differentiate both sides with respect to $ x $:

Differentiate Both Sides:
   ```{math}
   \frac{\mathrm{d}}{\mathrm{d}x} \sin(xy) = \frac{\mathrm{d}}{\mathrm{d}x} (x + y)
   ```
Apply the Chain Rule on the left side and differentiate $ x + y $ on the right side:
   ```{math}
   \cos(xy) \cdot \frac{\mathrm{d}}{\mathrm{d}x} (xy) = 1 + \frac{\mathrm{d}y}{\mathrm{d}x}
   ```
Use the Product Rule for $ \frac{\mathrm{d}}{\mathrm{d}x} (xy) $:
   ```{math}
   \cos(xy) \cdot \left( x \frac{\mathrm{d}y}{\mathrm{d}x} + y \right) = 1 + \frac{\mathrm{d}y}{\mathrm{d}x}
   ```
Expand and Collect Terms for $ \frac{\mathrm{d}y}{\mathrm{d}x} $:
   ```{math}
   x \cos(xy) \frac{\mathrm{d}y}{\mathrm{d}x} + y \cos(xy) = 1 + \frac{\mathrm{d}y}{\mathrm{d}x}
   ```
Move All Terms Involving $ \frac{\mathrm{d}y}{\mathrm{d}x} $ to One Side:
   ```{math}
   x \cos(xy) \frac{\mathrm{d}y}{\mathrm{d}x} - \frac{\mathrm{d}y}{\mathrm{d}x} = 1 - y \cos(xy)
   ```
Factor Out $ \frac{\mathrm{d}y}{\mathrm{d}x} $ and Solve:
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} (x \cos(xy) - 1) = 1 - y \cos(xy)
   ```
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} = \frac{1 - y \cos(xy)}{x \cos(xy) - 1}
   ```

These examples demonstrate how implicit differentiation can handle complex relationships between $ x $ and $ y $, applying both the chain rule and product rule as needed.

### Parametric Differentiation
In parametric differentiation, functions are given in **parametric form** where both $ x $ and $ y $ are defined in terms of a third variable, usually $ t $, called the parameter.

*Steps for Parametric Differentiation:*

1. Differentiate $ x(t) $ and $ y(t) $ with respect to $ t $ to obtain $ \frac{\mathrm{d}x}{\mathrm{d}t} $ and $ \frac{\mathrm{d}y}{\mathrm{d}t} $.
2. Use the formula for $ \frac{\mathrm{d}y}{\mathrm{d}x} $:
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} = \frac{\frac{\mathrm{d}y}{\mathrm{d}t}}{\frac{\mathrm{d}x}{\mathrm{d}t}}
   ```
   This gives the derivative of $ y $ with respect to $ x $ in terms of $ t $.

*Examples:*

For the parametric equations $ x = t^2 $ and $ y = t^3 - 3t $:
1. Differentiate $ x $ and $ y $ with respect to $ t $:
   ```{math}
   \frac{\mathrm{d}x}{\mathrm{d}t} = 2t, \quad \frac{\mathrm{d}y}{\mathrm{d}t} = 3t^2 - 3
   ```
2. Use the formula for $ \frac{\mathrm{d}y}{\mathrm{d}x} $:
   ```{math}
   \frac{\mathrm{d}y}{\mathrm{d}x} = \frac{3t^2 - 3}{2t}
   ```


These methods allow us to differentiate functions that are not explicitly given as $ y = f(x) $, and they’re especially useful in fields like physics and engineering, where complex relationships between variables often occur.



## Finding Stationary Points

A **stationary point** of a function $ f(x) $ occurs where the derivative $ f'(x) = 0 $. At a stationary point, the function’s slope is zero, which means the graph has a horizontal tangent line.

To find stationary points:
1. Calculate the derivative $ f'(x) $.
2. Set $ f'(x) = 0 $ and solve for $ x $.
3. Substitute these $ x $-values back into $ f(x) $ to find the corresponding $ y $-values.

### Maxima and Minima (Using the Second Derivative Test)
Once you have identified the stationary points, you can use the second derivative $ f''(x) $ to determine if these points are **local maxima** or **local minima**:

- **Local Maximum**: If $ f''(x) < 0 $ at a stationary point, $ f(x) $ has a local maximum at that point. The curve is concave down.
- **Local Minimum**: If $ f''(x) > 0 $ at a stationary point, $ f(x) $ has a local minimum at that point. The curve is concave up.
- **Inconclusive**: If $ f''(x) = 0 $, the second derivative test is inconclusive. In this case, higher-order derivatives might provide more information.

*Examples:*

1. For $ f(x) = x^3 - 3x^2 + 4 $:
   - Find $ f'(x) $ and set it to zero to locate stationary points.
   - Use $ f''(x) $ at those points to determine if they are maxima or minima.

### Points of Inflection (Using the Third Derivative)
A **point of inflection** occurs where the behaviour of $ f(x) $ changes from concave up to concave down or vice versa

To confirm a point of inflection:
1. Calculate $ f''(x) $ and if $f''(x) = 0$ we have potential inflection points.
2. Use the **third derivative test**:
$ f'''(x) \neq 0 $, then $ x $ is a point of inflection.

*Example:*

For $ f(x) = x^4 - 4x^2 $:
   - Find $ f''(x) $ and set it to zero to identify potential points of inflection.
   - Use $ f'''(x) $ at these points to determine if they are true inflection points.

### Summary Table

| Feature            | Condition                               | Test                             |
|--------------------|-----------------------------------------|----------------------------------|
| Stationary Point   | $ f'(x) = 0 $                        | Solve $ f'(x) = 0 $            |
| Local Maximum      | $ f'(x) = 0 $ and $ f''(x) < 0 $   | Second derivative test           |
| Local Minimum      | $ f'(x) = 0 $ and $ f''(x) > 0 $   | Second derivative test           |
| Point of Inflection| $ f''(x) = 0 $ and $ f'''(x) \neq 0 $ | Third derivative test          |

These steps provide a methodical approach to identifying and analysing key features of a function’s graph, which is essential for understanding its behaviour.

An application of differentiation is to find a function $f(x)$'s **Stationary Points** (SP's), where we are searching for solutions to $f'(x) = 0$. There are three distinct types of SP:

![Stationary Points](StationaryPoints3.png)


We see that we need the first derivative to be zero, but the sign of the second derivative can indicate the type of stationary point.  


*Example:* find the coordinate(s) and nature of all the stationary point(s) for:
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

