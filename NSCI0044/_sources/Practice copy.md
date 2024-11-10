
````{admonition}
:class: seealso, dropdown

## Example 1: denominator consists of distinct linear factors

Consider the rational expression:

```{math}
\frac{4x^2 + 3x - 16}{(x-2)(x+1)(2x-3)}
```

It can be shown that this can be expressed in the form:

```{math}
\frac{A}{x-2} + \frac{B}{x+1} + \frac{C}{2x-3}
```

(We can treat this fact as known). Our problem becomes finding the values of the unknown constants $A$, $B$, and $C$.

### Multiply up

We know that:

```{math}
\frac{4x^2 + 3x - 16}{(x-2)(x+1)(2x-3)} = \frac{A}{x-2} + \frac{B}{x+1} + \frac{C}{2x-3}
```

We start by multiplying both sides by $(x-2)(x+1)(2x-3)$. This gives:

```{math}
4x^2 + 3x - 16 = A(x+1)(2x-3) + B(x-2)(2x-3) + C(x-2)(x+1)
```

### Choose values

This is true for all values of $x$, so it's true for any values of $x$ we care to choose. The strategy is to choose values that make most of the terms vanish. In this case, those values are $x=2$, $x=-1$, and $x=\frac{3}{2}$.

- Starting with $x=2$, we obtain:

  ```{math}
  4(2)^2 + 3(2) - 16 = A(3) + B(0) + C(0)
  ```

  Therefore, $6 = 3A$, giving $A = 2$.

- Setting $x = -1$, we get:

  ```{math}
  4(-1)^2 + 3(-1) - 16 = A(0) + B(-3)(-5) + C(0)
  ```

  Therefore, $-15 = 15B$, giving $B = -1$.

- Finally, setting $x = \frac{3}{2}$ gives:

  ```{math}
  4\left(\frac{3}{2}\right)^2 + 3\left(\frac{3}{2}\right) - 16 = A(0) + B(0) + C\left(\frac{-2}{5}\right)
  ```

  Thus, $-25 = -45C$, giving $C = 2$.

### Substitute in

We now know the values of $A$, $B$, and $C$, and have that:

```{math}
\frac{4x^2 + 3x - 16}{(x-2)(x+1)(2x-3)} = \frac{2}{x-2} - \frac{1}{x+1} + \frac{2}{2x-3}
```

## Example 2: What happens if a factor is repeated?

Problem: Resolve into partial fractions:

```{math}
\frac{3x^2 + 6x + 5}{(x+2)^2(x-3)}
```

Two things change in these circumstances: first, the form of the partial fractions is altered, and secondly, our "choose values" technique from above will no longer take us all the way on its own.

The partial fractions form of this expression is actually:

```{math}
\frac{A}{x+2} + \frac{B}{(x+2)^2} + \frac{C}{x-3}
```

### Multiply up

We know that:

```{math}
\frac{3x^2 + 6x + 5}{(x+2)^2(x-3)} = \frac{A}{x+2} + \frac{B}{(x+2)^2} + \frac{C}{x-3}
```

We start by multiplying both sides by $(x+2)^2(x-3)$. This gives:

```{math}
3x^2 + 6x + 5 = A(x+2)(x-3) + B(x-3) + C(x+2)^2
```

### Choose values

Again, we try to choose values that make most of the terms vanish. In this case, those values are $x = -2$ and $x = 3$.

- Starting with $x = -2$, we obtain:

  ```{math}
  3(-2)^2 + 6(-2) + 5 = A(0) + B(-5) + C(0)
  ```

  Therefore, $5 = -5B$, giving $B = -1$.

- Setting $x = 3$, we get:

  ```{math}
  3(3)^2 + 6(3) + 5 = A(0) + B(0) + C(5^2)
  ```

  Therefore, $50 = 25C$, giving $C = 2$.

Unfortunately, this is where "choosing values" runs out of steam, and we don't yet know the value of $A$. We turn to...

### Compare like terms

The quickest way to calculate the value of $A$ is to compare the $x^2$ terms in:

```{math}
3x^2 + 6x + 5
```

and

```{math}
A(x+2)(x-3) + B(x-3) + C(x+2)^2
```

This gives us $3 = A + C$, from which we get $A = 3 - C = 3 - 2 = 1$.

### Substitute in

We now know the values of $A$, $B$, and $C$, and have that:

```{math}
\frac{3x^2 + 6x + 5}{(x+2)^2(x-3)} = \frac{1}{x+2} - \frac{1}{(x+2)^2} + \frac{2}{x-3}
```

## Example 3: What happens if there is a quadratic factor that can't be factorized?

Problem: Resolve into partial fractions:

```{math}
\frac{2x^2 + 7}{(x+2)(x^2+1)}
```

The partial fractions form of this expression is:

```{math}
\frac{A}{x+2} + \frac{Bx + C}{x^2 + 1}
```

### Multiply up

We know that:

```{math}
\frac{2x^2 + 7}{(x+2)(x^2 + 1)} = \frac{A}{x+2} + \frac{Bx + C}{x^2 + 1}
```

We start by multiplying both sides by $(x+2)(x^2+1)$. This gives:

```{math}
2x^2 + 7 = A(x^2 + 1) + (Bx + C)(x+2)
```

### Choose values

Again, we try to choose values that make most of the terms vanish. In this case, the only candidate is $x = -2$.

Setting $x = -2$, we obtain:

```{math}
2(-2)^2 + 7 = A((-2)^2 + 1) + (Bx + C)0
```

Therefore, $15 = 5A$, giving $A = 3$.

### Compare like terms

We start by comparing the $x^2$ terms in:

```{math}
2x^2 + 7
```

and

```{math}
A(x^2 + 1) + (Bx + C)(x + 2)
```

This gives us $2 = A + B$, from which we get $B = 2 - A = 2 - 3 = -1$.

We can then compare constant terms, obtaining $7 = A + 2C$, meaning $2C = 7 - A = 7 - 3 = 4$, and thus $C = 2$.

### Substitute in

We now know the values of $A$, $B$, and $C$, and have that:

```{math}
\frac{2x^2 + 7}{(x+2)(x^2 + 1)} = \frac{3}{x+2} + \frac{2 - x}{x^2 + 1}
```

---

Note that it's entirely possible for both a repeated linear factor and an unfactorisable quadratic factor to appear in the numerator, as in:

```{math}
\frac{5x^2 + 8x + 9}{(x-2)(x+1)^2(x^2+1)}
```

In which case these techniques are combined. The partial fractions form of this example, for instance, is:

```{math}
\frac{A}{x-2} + \frac{B}{x+1} + \frac{C}{(x+1)^2} + \frac{Dx + E}{x^2+1}
```

This fairly complicated example is left as an exercise to the keen reader (answer: $A = 1$, $B = -1$, $C = -1$, $D = 0$, $E = -2$).

Note also that in all these cases, the degree of the numerator is less than that of the denominator. If the degrees are equal, the partial fractions form of the expression has a constant term, and if that of the numerator is one more than that of the denominator, there's also an $x$-term; etc. For example, the partial fractions form of:

```{math}
\frac{x^3 + 2x^2 + 1}{(x+2)(x+1)}
```

is:

```{math}
\frac{A}{x+B} + \frac{Cx}{x+2} + \frac{D}{x+1}
```

This is also left as an exercise (answer: $A = 1$, $B = -1$, $C = -1$, $D = 2$).

````
