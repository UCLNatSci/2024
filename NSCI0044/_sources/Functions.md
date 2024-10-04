# Functions
### Inverse Functions

So far we have defined a function $ y=y(x) $, but given this, is it possible to reverse the function to find $ x=x(y) $? This reversing of the function process is called finding the **Inverse** function. The notation for the inverse of a function $ f(x) $ is $ f^{-1}(x) $. This is often confused with the **Reciprocal** function $ \frac{1}{f(x)} $. For trigonometric functions, the prefix "arc" is commonly added to indicate the inverse function, such as $ \arcsin(x) $ etc.

### Algorithm for Finding Inverse
A simple method of finding the inverse of a function is first to write it out using two variables, for example, using $ x $ as the independent variable and $ y $ as the dependent variable:

```{math}
f(x): \quad y = (x+1)^2 - 3
```

Then swap the variable letters:

```{math}
f^{-1}(x): \quad x = (y+1)^2 - 3
```

Finally, rewrite this equation making $ y $ the subject:

```{math}
f^{-1}(x): \quad x + 3 = (y+1)^2 \Rightarrow \sqrt{x+3}  = y + 1
```
```{math}
f^{-1}(x): \quad y = \sqrt{x+3} - 1
```

This is now our inverse function.

In finding the inverse, we need to first consider the domain and co-domain. Strictly speaking, these swap around. For example:

```{math}
f(x) = x^2, \, x \in (-\infty,\infty), \, f(x) \in [0,\infty)
```
```{math}
f^{-1}(x) = \sqrt{x}, \, x \in [0,\infty), \, f^{-1}(x) \in [0,\infty)
```

### Examples of Well-Known Inverse Functions
The exponential and logarithm functions are the inverse of each other, and if we plot them, we can see the mirror image over the line $ y = x $.

![Exponential and Logarithm](ExpLog.png)

![Inverse Trigonometric Functions](ArcSinCos2.png)


