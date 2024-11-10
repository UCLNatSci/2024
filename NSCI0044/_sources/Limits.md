# Limits and Infinities

When finding limits, there are a few important ideas and strategies to keep in mind:

## Limit Behavior as $ x \to \infty $

- As $ x \to \infty $, rational functions can be evaluated by considering the degree of the numerator and denominator. The limit is typically determined by the highest degree terms in both.
- **Key Idea**: 
  ```{math}
  \lim_{x \to \infty} \frac{1}{x} = 0
  ```
  This result holds for any function of the form $ \frac{1}{x} $ where the denominator grows without bound as $ x \to \infty $.


### Simplification and Rewriting

- In many cases, simplifying or rewriting the limit expression is necessary. Techniques such as:
  - Dividing both the numerator and denominator by the highest power of $ x $.
  - Canceling common factors.
  - Expanding or factoring expressions help resolve indeterminate forms.

### Recognizing Common Limits

Some limits are well-known and can be used directly:
- $ \lim_{x \to \infty} \frac{1}{x} = 0 $
- $ \lim_{x \to 0} \frac{\sin(x)}{x} = 1 $
- $ \lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e $

## Indeterminate Forms

- Limits often result in indeterminate forms such as $ \frac{0}{0} $ or $ \frac{\infty}{\infty} $. These require further manipulation to resolve. Common techniques include:
  - **Factorization**: Factor and simplify the expression.
  - **Substitution**: Use substitution to simplify complex expressions.
  - **Dominant Terms**: For limits involving infinity, focus on the highest-degree terms in both the numerator and denominator.

### Limits of the form $ \frac{0}{0} $

A limit of the form $ \frac{0}{0} $ is indeterminate, so it requires further simplification.

#### Approach:
- **Factorization**: Factor the numerator and denominator and cancel common terms.
- **Simplification**: Try simplifying the expression by combining like terms or using algebraic manipulations.
- **Substitution**: Use substitutions to make the limit easier to evaluate.

#### Examples:

*Example 1:*

```{math}
\lim_{x \to 3} \frac{x^2 - 9}{x - 3}
```

- Direct substitution gives $ \frac{0}{0} $, so we factor the numerator:

```{math}
x^2 - 9 = (x - 3)(x + 3)
```

Thus, the expression becomes:

```{math}
\frac{(x - 3)(x + 3)}{x - 3}
```

Cancel the $ x - 3 $ terms:

```{math}
\lim_{x \to 3} (x + 3) = 6
```

So, the limit is $ 6 $.

*Example 2:*

```{math}
\lim_{x \to 0} \frac{x^2 + 2x}{x}
```

- Direct substitution gives $ \frac{0}{0} $. Factor out $ x $ in the numerator:

```{math}
x^2 + 2x = x(x + 2)
```

Thus, the expression becomes:

```{math}
\frac{x(x + 2)}{x}
```

Cancel the $ x $ terms:

```{math}
\lim_{x \to 0} (x + 2) = 2
```

So, the limit is $ 2 $.

---

### Limits of the form $ \frac{\infty}{\infty} $

Limits of the form $ \frac{\infty}{\infty} $ are also indeterminate. To resolve them, simplify the expression by focusing on dominant terms.

#### Approach:
- **Simplify by Dominant Terms**: Identify the highest-degree terms in the numerator and denominator and focus on those.
- **Divide by the Highest Power**: If the numerator and denominator are polynomials, divide both by the highest power of $ x $ in the denominator.

#### Examples:

*Example 1:*

```{math}
\lim_{x \to \infty} \frac{5x^3 + 3x}{2x^3 - 4x^2 + 1}
```

- As $ x \to \infty $, the dominant term in the numerator is $ 5x^3 $ and in the denominator is $ 2x^3 $. To simplify, divide both the numerator and denominator by $ x^3 $:

```{math}
\frac{5x^3 + 3x}{2x^3 - 4x^2 + 1} = \frac{5 + \frac{3}{x^2}}{2 - \frac{4}{x} + \frac{1}{x^3}}
```

As $ x \to \infty $, the terms involving $ \frac{1}{x} $ vanish, and the expression simplifies to:

```{math}
\frac{5}{2}
```

So, the limit is $ \frac{5}{2} $.

*Example 2:*

```{math}
\lim_{x \to \infty} \frac{4x^2 - x + 2}{3x^2 + 5x - 7}
```

- As $ x \to \infty $, the dominant terms in both the numerator and denominator are $ 4x^2 $ and $ 3x^2 $, respectively. To simplify, divide both by $ x^2 $:

```{math}
\frac{4x^2 - x + 2}{3x^2 + 5x - 7} = \frac{4 - \frac{1}{x} + \frac{2}{x^2}}{3 + \frac{5}{x} - \frac{7}{x^2}}
```

As $ x \to \infty $, the terms involving $ \frac{1}{x} $ and $ \frac{1}{x^2} $ vanish, and the expression simplifies to:

```{math}
\frac{4}{3}
```

So, the limit is $ \frac{4}{3} $.

---

### Limits of the form $ \frac{0}{0 - 0} $

This type of limit occurs when the denominator is a difference of two terms, both tending to zero. Simplifying the expression carefully can help resolve the limit.

#### Approach:
- **Simplify the Expression**: Try to factor or expand the terms in the numerator and denominator.
- **Use Substitution**: If necessary, introduce a substitution to handle the difference of terms in the denominator.

#### Examples:

*Example 1:*

```{math}
\lim_{x \to 0} \frac{x}{x^2 - x}
```

- Direct substitution results in $ \frac{0}{0 - 0} $. First, factor the denominator:

```{math}
x^2 - x = x(x - 1)
```

Thus, the expression becomes:

```{math}
\frac{x}{x(x - 1)} = \frac{1}{x - 1}
```

Now, evaluate the limit:

```{math}
\lim_{x \to 0} \frac{1}{x - 1} = \frac{1}{-1} = -1
```

So, the limit is $ -1 $.

*Example 2:*

```{math}
\lim_{x \to 0} \frac{x}{x^2 + 2x}
```

- Direct substitution gives $ \frac{0}{0 - 0} $. Factor the denominator:

```{math}
x^2 + 2x = x(x + 2)
```

Thus, the expression becomes:

```{math}
\frac{x}{x(x + 2)} = \frac{1}{x + 2}
```

Now, evaluate the limit:

```{math}
\lim_{x \to 0} \frac{1}{x + 2} = \frac{1}{2}
```

So, the limit is $ \frac{1}{2} $.

---

## Summary of Techniques:
- *Factorization*: Factor both the numerator and denominator, cancel common terms, and simplify.
- *Dominant Terms*: For limits involving infinity, focus on the highest-degree terms in both the numerator and denominator.
- *Simplification*: Break down complex expressions by simplifying algebraically or using substitutions.

By applying these techniques, you can resolve most limits involving indeterminate forms such as $ \frac{0}{0} $, $ \frac{\infty}{\infty} $, and $ \frac{0}{0 - 0} $.
