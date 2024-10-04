# Algebra

## Quadratic Equations

A **Quadratic** equation is one where the highest power of $x$ is two:
```{math}
ax^2 + bx + c = 0
```
where $a, b, c$ are all constants. Quadratic equations appear frequently in mathematics and the sciences, so it is important to confidently solve them. Since the highest power in the equation is two, there are (up to) two real solutions to this equation.

## Brackets and FOIL

To think about how to solve quadratics, let's first consider how to expand brackets, starting with a simple problem:
```{math}
f(x) = (x+a)(x+b) = 0
```
We can use an ordered method, known as **FOIL**—**F**irst, **O**utside, **I**nside, **L**ast—to expand the two brackets:
```{math}
f(x) = x^2 + bx + ax + ab = x^2 + (a+b)x + ab
```
If presented with a quadratic, we can revise this process, factorizing it into a set of brackets to solve the equation. For example, solve the quadratic:
```{math}
x^2 + 3x + 2  =  0
```
We need two numbers that add to 3 and multiply to 2. A good choice is $1$ and $2$:
```{math}
x^2 + 3x + 2 = (x+1)(x+2) = 0
```
Once the terms are in brackets, since the right-hand side equals zero, **one** of the two brackets must **also** equal zero:
```{math}
(x+1)(x+2) = 0 \Rightarrow (x+1) = 0 \quad \text{OR} \quad (x+2) = 0
```
which rearranged means the solutions to the quadratic are:
```{math}
x = -1 \quad \text{OR} \quad x = -2
```
The equation we factorize **must** equal zero. To see why, suppose we had:
```{math}
x^2 + 3x + 2 = 2 \Rightarrow (x+1)(x+2) = 2
```
We might be tempted to say here that $(x+1) = 1$ and $(x+2) = 2$, but we could also say it should be $(x+1) = \sqrt{2}$ and $(x+2) = \sqrt{2}$, etc. It turns out there are an infinite number of solutions here, which clearly is not true! The beauty of having zero on the right-hand side is that one of the brackets **must** equal zero.

## Completing the Square

The goal of this method is to bring the equation close to the form of a perfect square:
```{math}
f(x) = (x-a)^2 = x^2 + 2a + a^2
```
This is known as **Completing the Square**. To see how this is useful, let's start with the quadratic form:
```{math}
ax^2 + bx + c = 0
```
First, factor out the coefficient $a$:
```{math}
a\left(x^2 + \frac{b}{a} x\right) + c = 0
```
Next, to bring this into the form of a perfect square, we add and subtract the term $\frac{b^2}{4a^2}$, which is just the coefficient of the $x$ term squared and divided by 4:
```{math}
\left(x^2 + \frac{b}{a} x + \frac{b^2}{4a^2} - \frac{b^2}{4a^2}\right) + c = 0
```
Now we see that we have a perfect square in the first three terms, which we can factorize:
```{math}
a\left(\left(x + \frac{b}{2a}\right)^2  - \frac{b^2}{4a^2}\right) + c = 0
```
Rearrange to make $x$ the subject of the formula:
```{math}
a\left(x + \frac{b}{2a}\right)^2  - \frac{b^2}{4a} + c = 0
```
```{math}
a\left(x + \frac{b}{2a}\right)^2 = \frac{b^2}{4a} - c = \frac{b^2 - 4ac}{4a}
```
```{math}
\left(x + \frac{b}{2a}\right)^2 = \frac{b^2 - 4ac}{4a^2}
```
```{math}
x + \frac{b}{2a} = \pm\sqrt{\frac{b^2 - 4ac}{4a^2}} \Rightarrow x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
```
Hence, we derive the quadratic formula!

An example: complete the square on $f(x) = x^2 + 6x + 5 = 0$:
```{math}
\left(x^2 + 6x + \frac{6^2}{4} - \frac{6^2}{4}\right) + 5 \Rightarrow \bigg(x^2 + 6x + 9\bigg) - 4 = 0
```
Hence, we see that $(x+3)^2 = 4 \Rightarrow x = -3 \pm 2 = (-5, -1)$. To check:
```{math}
f(-5) = 25 -30 + 5 = 0,\quad f(-1) = 1 - 6 + 5 = 0
```

## Roots

Take a polynomial function:
```{math}
f(x) = (x-a)(x-b)
```
Since $f(a) = f(b) = 0$, we call $a$ and $b$ the **Roots** of the function. If we were to plot the $f(x)$, then $x=a, b$ would be where the graph cuts the $x$-axis.

An example:
```{math}
f(x) = (x+1)(x-2) = x^2 - x - 2
```
![RootsPlot](RootsPlot.png)

Notice the roots at $x=-1, 2$.

## Remainders

Suppose we have a polynomial $f(x)=(x-a)(x-b)$ and wanted to see if a function $g(x)=(x-c)$ was a factor. We could perform long division, however, if $g(x)$ does not exactly divide $f(x)$, then there will be a **Remainder** $r$ left over:
```{math}
\frac{(x-a)(x-b)}{x-c} = h(x) + \frac{r}{x-c}
```
and we find that $f(c) = r$. 

An example: $f(x) = x^2 - x - 2$, $g(x) = x-1 \Longrightarrow r = f(1) = -2$:
```{math}
\frac{x^2 - x - 2}{x-1} = \frac{x(x-1) -2}{x-1} = x - \frac{2}{x-1}
```
Another example: $f(x) = x^2 - x - 2$, $g(x) = x+2 \Longrightarrow r = f(-2) = 4$:
```{math}
\frac{x^2 - x -2}{x+2} = \frac{x^2 +2x - 3x -6 + 6-2}{x+2} = \frac{x(x+2) - 3(x+2) + 4}{x+2} = x - 3 + \frac{4}{x+2}
```

---

## Surds

**Surds** are the technical name for things like square roots $\sqrt{}$, cube roots $\sqrt[3]{}$, etc. An important point is that expressions with surds are **exact**, unlike, say, a decimal **approximation**, such as:
```{math}
\sqrt{2} \approx 1.414\dots
```
We need to be a little careful in how we treat surds, to avoid a common error like:
```{math}
\sqrt{2} + \sqrt{3} \neq \sqrt{2 + 3}
```
For multiplication and division, we can manipulate some expressions into a single root:
```{math}
\frac{\sqrt{3}}{\sqrt{2}} = \sqrt{\frac{3}{2}}, \quad \sqrt{2}\sqrt{5} = \sqrt{10}
```
We have to be careful, however, if there are fractions involved, as the general rule is to move surds entirely from the denominator of a fraction:
```{math}
\frac{1}{\sqrt{3}} = \frac{1}{\sqrt{3}}\times\frac{\sqrt{3}}{\sqrt{3}} = \frac{\sqrt{3}}{3}
```
This can be a little more complicated if the denominator is a mixture of rational numbers and surds.

An example:
```{math}
\frac{1}{2 + \sqrt{3}}
```
The rule of thumb here is to find the **Conjugate** of the denominator and then multiply top and bottom by this, moving any surds into the numerator:
```{math}
\frac{1}{2 + \sqrt{3}} = \frac{1}{2 + \sqrt{3}}\times\frac{2 - \sqrt{3}}{2 - \sqrt{3}} = \frac{2 - \sqrt{3}}{4 - 3} = 2 - \sqrt{3}
```
This technique works because we are finding a difference of two squares expression:
```{math}
\frac{1}{a+b} = \frac{1}{a+b}\times\frac{a-b}{a-b} = \frac{a-b}{a^2 - b^2}
```
which clearly removes surds from the denominator. The next level of complication is expressions with two surds in the denominator.

An example:
```{math}
\frac{2}{\sqrt{7} - \sqrt{5}}
```
which we can manipulate as:
```{math}
\frac{2}{\sqrt{7} - \sqrt{5}} \times \frac{\sqrt{7} + \sqrt{5}}{\sqrt{7} + \sqrt{5}} = \frac{2(\sqrt{7}+\sqrt{5})}{7-5} = \sqrt{7} + \sqrt{5}
```

## Remainders

Suppose we have a polynomial $f(x)=(x-a)(x-b)$ and wanted to see if a function $g(x)=(x-c)$ was a factor. We could perform long division, however, if $g(x)$ does not exactly divide $f(x)$, then there will be a **Remainder** $r$ left over:
```{math}
\frac{(x-a)(x-b)}{x-c} = h(x) + \frac{r}{x-c}
```
and we find that $f(c) = r$. 

An example: $f(x) = x^2 - x - 2$, $g(x) = x-1 \Longrightarrow r = f(1) = -2$:
```{math}
\frac{x^2 - x - 2}{x-1} = \frac{x(x-1) -2}{x-1} = x - \frac{2}{x-1}
```
Another example: $f(x) = x^2 - x - 2$, $g(x) = x+2 \Longrightarrow r = f(-2) = 4$:
```{math}
\frac{x^2 - x -2}{x+2} = \frac{x^2 +2x - 3x -6 + 6-2}{x+2} = \frac{x(x+2) - 3(x+2) + 4}{x+2} = x - 3 + \frac{4}{x+2}
```

---

## Surds

**Surds** are the technical name for things like square roots $\sqrt{}$, cube roots $\sqrt[3]{}$, etc. An important point is that expressions with surds are **exact**, unlike, say, a decimal **approximation**, such as:
```{math}
\sqrt{2} \approx 1.414\dots
```
We need to be a little careful in how we treat surds, to avoid a common error like:
```{math}
\sqrt{2} + \sqrt{3} \neq \sqrt{2 + 3}
```
For multiplication and division, we can manipulate some expressions into a single root:
```{math}
\frac{\sqrt{3}}{\sqrt{2}} = \sqrt{\frac{3}{2}}, \quad \sqrt{2}\sqrt{5} = \sqrt{10}
```
We have to be careful, however, if there are fractions involved, as the general rule is to move surds entirely from the denominator of a fraction:
```{math}
\frac{1}{\sqrt{3}} = \frac{1}{\sqrt{3}}\times\frac{\sqrt{3}}{\sqrt{3}} = \frac{\sqrt{3}}{3}
```
This can be a little more complicated if the denominator is a mixture of rational numbers and surds.

An example:
```{math}
\frac{1}{2 + \sqrt{3}}
```
The rule of thumb here is to find the **Conjugate** of the denominator and then multiply top and bottom by this, moving any surds into the numerator:
```{math}
\frac{1}{2 + \sqrt{3}} = \frac{1}{2 + \sqrt{3}}\times\frac{2 - \sqrt{3}}{2 - \sqrt{3}} = \frac{2 - \sqrt{3}}{4 - 3} = 2 - \sqrt{3}
```
This technique works because we are finding a difference of two squares expression:
```{math}
\frac{1}{a+b} = \frac{1}{a+b}\times\frac{a-b}{a-b} = \frac{a-b}{a^2 - b^2}
```
which clearly removes surds from the denominator. The next level of complication is expressions with two surds in the denominator.

An example:
```{math}
\frac{2}{\sqrt{7} - \sqrt{5}}
```
which we can manipulate as:
```{math}
\frac{2}{\sqrt{7} - \sqrt{5}} \times \frac{\sqrt{7} + \sqrt{5}}{\sqrt{7} + \sqrt{5}} = \frac{2(\sqrt{7}+\sqrt{5})}{7-5} = \sqrt{7} + \sqrt{5}
```
## Indices

Algebra allows us to group together terms with a common factor or power, which can greatly simplify how we represent terms in our equations. For example, $ a + a + a = 3a $ or $ b \times b \times b = b^3 $. We recall that powers follow simple rules:

```{math}
\begin{aligned}
    x^A \cdot x^B &= x^{A+B} \\
    \frac{x^A}{x^B} &= x^{A-B} \\
    \frac{1}{x^A} &= x^{-A} \\
    \left(x^A\right)^B &= x^{AB} \\
    x^{1/A} &= \sqrt[A]{x} \\
    x^0 &= 1
\end{aligned}
```

---

## Logarithms

We can be given a problem with a known input $x$ and exponent $n$ and asked to find $y$:
```{math}
y = x^n
```
or we could be given $n$ and $y$ and need to work out $x$:
```{math}
x = y^{1/n}
```
and this can be achieved after some calculation. A harder problem, however, is what if we are given $x$ and $y$ and need to work out $n$? This is where **Logarithms** come into use! A logarithm allows us to reverse the problem. So if $y = x^n$, then:
```{math}
\log_x y = n
```
Here, $x$ is known as the **Base** of the logarithm and $n$ is the **Exponent** (power) that we raise the base to in order to get $y$. Logarithms for any base (that is a real number) can be computed straightforwardly, though calculators typically have two built-in logarithm functions:

- **log** refers to logarithms to the base 10, $\log(x) = \log_{10}(x)$
- **ln** refers to logarithms to the base $e$, $\ln(x) = \log_e(x)$

Logarithms also follow rules, which are somewhat similar to the exponent rules:

```{math}
\begin{aligned}
    \log_x (A) + \log_x (B) &= \log_x(AB) \\
    \log_x (A) - \log_x (B) &= \log_x\left(\frac{A}{B}\right) \\
    -\log_x (A) &= \log_x\left(\frac{1}{A}\right) \\
    B\log_x (A) &= \log_x A^B \\
    \log_x x &= 1 \\
    \log_x 1 &= 0
\end{aligned}
```

**Example:** Find the value of $n$ that satisfies $20 = 10^n$:
```{math}
\log_{10} (20) = \log_{10} (10^n) = n \log_{10} (10) = n \\
\Rightarrow n = \log_{10} (20) \approx 1.30\dots
```

**Another example:** Solve $5 = 2^n$:
```{math}
\ln (5) = \ln(2^n) = n \ln (2) \quad \text{or} \quad \log (5) = \log(2^n) = n \log (2) \\
\Rightarrow n = \frac{\ln (5)}{\ln (2)} \approx 2.32\dots \quad \text{or} \quad n = \frac{\log (5)}{\log (2)} \approx 2.32\dots
```

To find the logarithms in one base, say $a$, in terms of another base, say $b$:
```{math}
y = \log_a (x) \Longleftrightarrow a^y = x \\
\Rightarrow \log_b (a^y) = \log_b (x) \Rightarrow y \log_b (a) = \log_b (x) \\
\Rightarrow \log_a (x) = \frac{\log_b (x)}{\log_b (a)}
```


### Exponential Function

The number $e \approx 2.718\dots$ is related to the **Exponential Function** $e^x$, which has many mathematical properties. To understand some of these, consider the following situation:

- Suppose we put £1 in a new bank account and ask the bank to earn interest at an annual rate of £$x$, compounded monthly, so the interest earned each month is $\frac{x}{12}$ of the current account value. Hence, the monthly total account value is:
  ```{math}
  \left(1 + \frac{x}{12}\right)
  ```
  and at the end of the year, the total account value is:
  ```{math}
  \left(1 + \frac{x}{12}\right)^{12}
  ```

- If the interest is compounded daily, the end-of-year value becomes:
  ```{math}
  \left(1 + \frac{x}{365}\right)^{365}
  ```

- If compounded hourly, since there are $365 \times 24 = 8760$ hours/year, the total becomes:
  ```{math}
  \left(1 + \frac{x}{8760}\right)^{8760}
  ```

- Letting the number of time intervals per year grow without bound leads to the limit definition of the exponential function:
  ```{math}
  e^x = \lim_{n\rightarrow\infty}\left(1 + \frac{x}{n}\right)^n
  ```

## Partial Fractions

Consider the problem of adding different fractions, for example:

$$
\frac{1}{2} + \frac{1}{3} = \frac{?}{??}
$$

The easiest way to write this as one single fraction is to rewrite each fraction in terms of a common denominator and then just add the numerators. To find the common denominator, we need to find the lowest common multiple (LCM) of the denominators, here LCM$(2,3) = 6$ and hence:

$$
\frac{1}{2} = \frac{3}{6}, \quad \frac{1}{3} = \frac{2}{6} \Rightarrow \frac{1}{2} + \frac{1}{3} = \frac{2 + 3}{6} = \frac{5}{6}
$$

If we have two algebraic fractions, we can follow a similar process.

An example:

$$
\frac{2}{n+1} + \frac{3}{n+2} = \frac{2(n+2) + 3(n+1)}{(n+1)(n+2)} = \frac{5n + 7}{(n+1)(n+2)}
$$

The idea behind partial fractions is to reverse this process, breaking up a composite fraction into its smaller fractional parts.

An example:

$$
\frac{3}{(n-1)(n+2)}
$$

First, split this up into:

$$
\frac{3}{(n-1)(n+2)} = \frac{A}{n-1} + \frac{B}{n+2}
$$

Then, recombine to set up equations to find the unknown coefficients:

$$
\frac{3}{(n-1)(n+2)} = \frac{A(n+2) + B(n-1)}{(n-1)(n+2)} \Rightarrow 3 = A(n+2) + B(n-1)
$$

There are two (equally valid) methods to use at this point to find $A, B$:

- We can substitute in $n=1$ and $n=-2$ into the equation, in each case:

  $$
  \begin{aligned}
  n = 1: &\quad 3 = 3A \Rightarrow A = 1 \\
  n = -2: &\quad 3 = -3B \Rightarrow B = -1
  \end{aligned}
  $$

- We can compare coefficients of $n^0$ and $n^1$ (which by the fundamental theorem of algebra are independent), producing a set of simultaneous equations:

  $$
  \begin{aligned}
  n^1: &\quad A + B = 0 \Rightarrow B = -A \\
  n^0: &\quad 2A - B = 3 \Rightarrow 2A + A = 3 \\
       &\quad \Rightarrow A = 1, B = -1
  \end{aligned}
  $$

If we have repeated roots in the denominator, the decomposition now has terms for each of the roots and an additional one for the repeated root.

An example:

$$
g(n) = \frac{9}{(n+2)(n+5)^2} = \frac{A}{n+2} + \frac{B}{n+5} + \frac{C}{(n+5)^2}
$$

To find the partial fractions, recall we first combine:

$$
g(n) = \frac{A(n+5)^2 + B(n+2)(n+5) + C(n+2)}{(n+2)(n+5)^2}
$$

and then substitute in values:

$$
\begin{aligned}
n=-5: &\quad (-3)C = 9 \Rightarrow C = -3 \\
n = -2: &\quad 3^2A = 9 \Rightarrow A = 1 \\
n=0: &\quad 25A + 10B + 2C = 9 \Rightarrow B=-1
\end{aligned}
$$

Thus:

$$
g(n) = \frac{1}{n+2} - \frac{1}{n+5} - \frac{3}{(n+5)^2}
$$

### An Application with Prime Factors

For a fraction like $ \frac{1}{18}$, can we decompose this into fractions of the prime factors $18 = 2 \cdot 3^2$? The full partial fraction decomposition would have the form:

$$
\frac{1}{18} = \frac{A}{2} + \frac{B}{3} + \frac{C}{3^2}
$$

First, we have to present the system in a way that is meaningful to use partial fractions:

$$
f(n) = \frac{1}{(n+2)(n+3)^2} = \frac{A}{n+2} + \frac{B}{n+3} + \frac{C}{(n+3)^2}
$$

So that we reduce to the original problem at $f(0)$. Now we just follow the process:

$$
\frac{1}{(n+2)(n+3)^2} = \frac{A(n+3)^2 + B(n+2)(n+3) + C(n+2)}{(n+2)(n+3)^2}
$$

Substituting in values we find:

$$
\begin{aligned}
n=-3: &\quad (-1)C = 1 \Rightarrow C = -1 \\
n = -2: &\quad 1^2A = 1 \Rightarrow A = 1 \\
n=0: &\quad 9A + 6B + 2C = 1 \Rightarrow B = -1
\end{aligned}
$$

Giving the final decomposition:

$$
f(n) = \frac{1}{n+2} - \frac{1}{n+3} - \frac{1}{(n+3)^2} \Rightarrow f(0) = \frac{1}{18} = \frac{1}{2} - \frac{1}{3} - \frac{1}{3^2}
$$

## Brackets

From our discussion of brackets before, we know that to expand out a quadratic, we can use the **FOIL** method:

$$(a+b)^2 = a^2 + 2ab + b^2$$

If the power is higher than two, we can reduce the problem to a longer calculation:

$$(a+b)^3 = (a+b)(a+b)^2 = (a+b)(a^2 + 2ab + b^2) = (a^3 + 3a^2 + 3ab^2 + b^3)$$

This becomes more and more tedious for higher powers and also means that to find the answer to a higher power, say $(a+b)^{10}$, we would need to know the answers to the previous nine powers, which is highly inefficient! A better method can be found by looking at the symmetries of the brackets.

### Pascal's Triangle

Let's look at the expansion for $(a+b)^2$, where we have put in all of the powers of $a, b$:

$$(a+b)^2 = a^2b^0 + 2a^1b^1 + a^0b^2$$

We see that going from left to right, the powers of $a$ start at two and reduce down to zero, and equally, the power of $b$ starts at zero and increases up to two. The only additional complication is that the coefficients for each term are not all the same, so provided we can work these out, we could more easily calculate the full expansions for higher powers. The coefficients follow a simple pattern, known as **Pascal's Triangle**:

|   |   |   |   |   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|   |   |   |   |   |   | 1 |   |   |   |   |   |   |
|   |   |   |   |   | 1 |   | 1 |   |   |   |   |   |
|   |   |   |   | 1 |   | 2 |   | 1 |   |   |   |   |
|   |   |   | 1 |   | 3 |   | 3 |   | 1 |   |   |   |
|   |   | 1 |   | 4 |   | 6 |   | 4 |   | 1 |   |   |
|   | 1 |   | 5 |   | 10|   | 10|   | 5 |   | 1 |   |


Each number in each line of the triangle is formed by the addition of the two numbers diagonally above. However, although we have greatly simplified the calculation of the terms in higher-order brackets, we still have to calculate the $n-1$ lines of the triangle to find the coefficients for $(a+b)^n$.


### Binomial Theorem

Each of the terms in Pascal's triangle is called a **Binomial Coefficient**, and we can use the **Binomial Theorem** to expand out $(a+b)^n$ for *any* power $n$:

$$(a+b)^n = a^n + \frac{n!}{r!(n-r)!}\,a^{n-r}\,b^r + \dots + b^n$$

$$
= a^n + n\,a^{n-1}\,b + \frac{n(n-1)}{2!}\,a^{n-2}\,b^2 + \frac{n(n-1)(n-2)}{3!}\,a^{n-3}\,b^3 + \dots + b^n
$$

An example, find all the terms in the expansion of $(a+b)^5$:

$$(a+b)^5 = a^5 + a^4\,b^1\,\frac{5!}{1!(5-1)!} + a^3\,b^2\,\frac{5!}{2!(5-2)!} + a^2\,b^3\,\frac{5!}{3!(5-3)!} + a^1\,b^4\,\frac{5!}{4!(5-4)!} + b^5$$

$$
= a^5 + 5\,a^4\,b + 10\,a^3\,b^2 + 10\,a^2\,b^3 + 5\,a\,b^4 + b^5
$$

Which matches our earlier expression from Pascal's triangle.

Another example, find the constant term in $\left( x^8 - \frac{2}{x^2}\right)^{10}$:

Firstly, to make sense of the problem, let’s expand out a few terms:

$$
\left( x^8 - \frac{2}{x^2}\right)^{10} = x^{80} + 10\,x^{72}\left(-\frac{2}{x^2}\right) + \frac{10\times 9}{2}\,x^{64} \left(-\frac{2}{x^2}\right)^{2} + \dots + \left(-\frac{2}{x^2}\right)^{10}
$$

$$
= x^{80} - 20 \,x^{70} + 180 \,x^{60} + \dots + 1024 \,x^{-20}
$$

Notice that powers of $x$ decrease by 10, from $x^{80}$ up to $x^{-20}$, so there should be a term with $x^0$ - which would be the constant term. Since the combined sum of the powers totals 10, we have a term of the form:

$$
\frac{10!}{8!(10-8)!}(x^8)^2\left(-\frac{2}{x^2}\right)^8 = \frac{10!}{8!(10-8)!} 2^8 = \frac{1}{2}\times10\times9\times 2^8 = 11520
$$



### Binomial Series

It turns out that the Binomial theorem can be applied to any problem in binomial form, even if the exponent $n$ is not an integer; however, there will be an infinite number of terms resulting here. An example:

$$(1+x)^{1/2} = 1 + \frac{1}{2} x + \frac{1}{2}\bigg(-\frac{1}{2}\bigg)\frac{1}{2!} x^2 + \frac{1}{2}\bigg(-\frac{1}{2}\bigg)\bigg(-\frac{3}{2}\bigg)\frac{1}{3!} x^3 + \dots$$

There are, however, strict criteria as to when we can use such a series, which here require that the size of $x$ is small, $|x| \ll 1$, otherwise the expansion here is not valid. We will see why when we study series and convergence.
