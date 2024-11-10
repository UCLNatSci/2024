# Series 

## Defintions

Consider a collection of numbers, such as the first 10 integer powers of 2:

```{math}
\{2,\, 4,\, 8,\, 16,\, 32,\, 64,\, 128,\, 256,\, 512,\, 1024\}
```

and we call this collection a **Sequence**. We can write this using mathematical notation:

```{math}
a_n = 2^n
```

where $a_n$ is the $n^{th}$ element in the sequence. Another very common sequence is the so-called **Fibonacci Sequence**, where the next term is the sum of the previous two:

```{math}
\{1,\, 1,\, 2,\, 3,\, 5,\, 8,\, 13\, \dots\}
```

which we can write in mathematical notation as a recurrence relation:

```{math}
a_{n+2} = a_{n+1} + a_n
```

If we have such an ordered collection of numbers, then we can also add them together, which we call a **Series**. We can write a series in mathematical notation:

```{math}
S = \sum_{n=1}^{N}a_n
```

We call this a **Finite** series and in the limit $N \rightarrow \infty$, we can define an **Infinite** series:

```{math}
S = \sum_{n=1}^{\infty}a_n
```

## Arithmetic Series

An **Arithmetic Series** $S_n$ has $n$ terms, with **First Term** $a$ and **Common Difference** $d$:

```{math}
S_n = a + (a+d) + (a+2d) + \dots + (a + (n-1)d) = \sum_{k=0}^{n-1}(a + kd)
```

We can sum up an arithmetic series by manipulating the order of the series and adding:

```{math}
\begin{array}{ccccccccc}
S_n & = & a & + & (a+d) & + & \dots & + & (a + (n-1)d) \\
S_n & = & (a + (n-1)d) & + & (a+(n-2)d) & + & \dots & + & a \\
\Rightarrow 2S_n & = & (2a + (n-1)d) & + & (2a+(n-1)d) & + & \dots & + & (2a + (n-1)d) \\
2S_n & = & n(2a + (n-1)d) &&&&&&\\
\Rightarrow S_n & = & \frac{n}{2}(2a + (n-1)d) &&
\end{array}
```

An example, find the sum of first 100 integers, 

$S_1 =  1 + 2 + \dots + 100= \sum_{n=1}^{100}n$

```{math}
\Rightarrow a &= 1,\, d=1,\, n=100 \\
S_1 &= \frac{1}{2}100(2 + 99) = 5050
```

## Geometric Series

A **Geometric Series** $S_n$ has $n$ terms, with first term $a$ and **Common Ratio** $r$:

```{math}
S_n = a + ar + ar^2 + \dots + ar^{n-1} = \sum_{k=0}^{n-1} ar^k
```

and likewise we can sum up a geometric series by shifting powers and subtracting:

```{math}
\begin{array}{ccccccccccccccc}
S_n & = & a & + & ar & + & ar^2 & +& \dots & + & ar^{n-2} & + & ar^{n-1} \\
rS_n & = &&& ar & + & ar^2 & + & \dots & + & ar^{n-2} & + & ar^{n-1} & + & ar^n \\
S_n - rS_n & = & a - ar^n \\
\Rightarrow S_n &= \frac{a(1-r^n)}{1-r}
\end{array}
```

An example, find 

$S_2 = \sum_{n=1}^{10}\sin^n(\theta),\, 0 \leq \theta < 2\pi$

```{math}
\Rightarrow a &= \sin(\theta),\, r = \sin(\theta),\, n=10 \\ 
S_2 &= \frac{\sin(\theta)(1 - \sin^{10}(\theta))}{1-\sin(\theta)}
```

We can also define an **Infinite Geometric Series** $S_{\infty}$:

```{math}
S_\infty = a + ar + ar^2 + \dots = \sum_{k=0}^\infty ar^k 
```

There is a formula for $S_\infty = \frac{a}{1-r}$, although whether or not we can use this formula depends on whether the series will **converge**, which here depends on if $|r| < 1$. 

An example, find the sum of the series 

$S_3 = \frac{1}{3} + \frac{1}{9} + \frac{1}{27} + \dots = \sum_{n=1}^\infty\frac{1}{3^n} $

$\Rightarrow a =\frac{1}{3}$, $r = \frac{1}{3}$ and since $|r| = \frac{1}{3} <1 $, series converges, therefore:

```{math}
S_\infty = \frac{1/3}{1 - 1/3} = \frac{1/3}{2/3} = \frac{1}{2}
```

## Convergence

For a finite series:

```{math}
S_n = \sum_{n=1}^N a_n = a_1 + a_2 + \dots + a_N
```

it should be fairly clear that provided the form of the terms $a_n$ remains finite, then the value of the series itself will be finite, we say that the series **Converges**. However, if the series is infinite:

```{math}
S_n = \sum_{n=1}^\infty a_n = a_1 + a_2 + \dots
```

then it turns out even if $a_n$ remains finite, the series may not sum to a finite value. Such a series **Diverges**.  

An example of a convergent series:

```{math}
S_1 = \sum_{n=0}^\infty \frac{1}{2^n} = 1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \dots
```

Recall this is a geometric series with $a = 1, \, r = \frac{1}{2}$, and the series converges to:

```{math}
S_1 = \frac{1}{1 - \frac{1}{2}} = \frac{1}{\frac{1}{2}} = 2
```

If we plot the **Partial Sums** of the series, which we find by adding up all $n$ terms while increasing the value of $n$:

![Inverse Powers of 2](InversePowers2.png)

it appears to show the limiting behavior as we approach ever increasing $n$.

Now suppose we had an infinite geometric series with $a = 1, \, r = 1$:

```{math}
S_2 = \sum_{n=1}^\infty 1^n = 1 + 1 + 1 + \dots
```

$S_2$ would be an example of a divergent series because this sum will just keep growing to infinity. In fact, for a geometric series, we can prove that provided $|r| < 1$ and $a$ is finite, then the series will *always* converge.

Another example of a divergent series is the **Harmonic Series**:

```{math}
S_3 = \sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \dots
```

If we plot the partial sums this time, we find:

![Harmonic Partial Sums](HarmonicPartialSums.png)

You might think from looking at the plot that the series would converge, however, it turns out that the terms increase just a little too quickly for this to happen.

In order to prove this, we need to develop some more rigorous mathematical tools, known as **Convergence Tests**. The *sign* of the terms in the series is also important. To see this, consider the terms of the harmonic series with alternating signs:

```{math}
S_4 = \sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots
```

By plotting the partial sums, we see the series is bounded from above *and* below, and thus it converges (it turns out $S_4 = \ln(2) \approx 0.69$):

![Alternating Harmonic Series](AlternatingHarmonicSeries.png)


## Convergence Tests

We can define an infinite series $ S $

```{math}
S = \sum_{n=1}^\infty a_n
```

and ask the question, is $ S $ a finite number or does it tend to infinity for different choices of $ a_n $? To help us work this out, we have a number of standard tests we can employ:

- **Preliminary Test**  
  The preliminary test is a simple way to identify, before doing any heavy mathematical lifting, whether or not the terms in the series are strictly increasing: $ a_{n+1} > a_n $.  
  If in the infinite limit, $ \lim_{n \rightarrow \infty} a_n $ the terms do not approach zero, then the series will diverge.  
  Note that this is not saying the series will definitely converge, however it is a helpful first indicator as to whether or not subsequent tests should be employed.

  An example:

  ```{math}
  S_1 = \sum_{n=1}^\infty 2^n = 2^1 + 2^2 + 2^3 + \dots
  ```

  Clearly we can see that:

  ```{math}
  \lim_{n \rightarrow \infty} a_n \rightarrow \infty
  ```

  and so $ S_1 $ fails the preliminary test and will diverge.

- **Ratio Test**  
  We can define the limit:

  ```{math}
  \rho = \lim_{n\rightarrow \infty} \left| \frac{a_{n+1}}{a_n} \right|
  ```

  and find three separate cases for the value of $ \rho $:

  ```{math}
  \rho \rightarrow 
  \begin{cases} 
    \text{< 1} & \text{series converges} \\
    \text{= 1} & \text{test inconclusive} \\
    \text{> 1} & \text{series diverges}
  \end{cases}
  ```

  An example:

  ```{math}
  S_2 = \sum_{k=1}^{\infty} \frac{k^2}{2^k}
  ```

  ```{math}
  \rho = \lim_{k \rightarrow \infty} \left | \frac{(k+1)^2}{2^{k+1}} \frac{2^k}{k^2} \right| = \lim_{k \rightarrow \infty} \left| \frac{2^k}{2^{k+1}} \frac{(k+1)^2}{k^2} \right| = \lim_{k \rightarrow \infty} \left| \frac{1}{2} \frac{(k+1)^2}{k^2} \right| = \lim_{k \rightarrow \infty} \left| \frac{1}{2} \left(1 + \frac{1}{k}\right)^2 \right| \Rightarrow \frac{1}{2} < 1 \Rightarrow \text{converges}
  ```

- **Comparison Test**  
  Sometimes it is possible to see that a series converges by comparing it to a known convergent series.  

  An example:

  ```{math}
  S_3 = \sum_{n=1}^{\infty} 2^{-n} \cos(n)
  ```

  We know that the related but simpler series:

  ```{math}
  S_4 = \sum_{n=1}^{\infty} 2^{-n}
  ```

  is a geometric progression with $ a = r = 2^{-1} $ and therefore is convergent to $ S_4 = 1 $. Additionally, since $ -1 < \cos(n) < 1,\, \forall n \in \mathbb{Z} $, the value of some of $ S_3 $'s terms will be *less* than those in $ S_4 $, hence $ S_3 $ will converge to a finite value less than $ S_4 $, and therefore by the comparison test, $ S_3 $ is convergent. (It turns out that while $ S_4 = 1 $, $ S_3 = 0.028\dots $.)

## Interval of Convergence

Consider the series:

```{math}
S_5 = \sum_{i=1}^\infty \left( \frac{x}{2} \right)^i
```

Clearly, if $ x=1 $ here, then $ S_5 $ will be a convergent series, but are there values of $ x $ that will change this statement?

We can apply the ratio test again here:

```{math}
\rho = \lim_{i \rightarrow \infty} \left| \frac{\left(\frac{x}{2}\right)^{i+1}}{\left(\frac{x}{2}\right)^i} \right| = \left|\frac{x}{2}\right|
```

If we are aiming for convergence, then we need $ \rho < 1 $, which means:

```{math}
\left| \frac{x}{2} \right| < 1 \Rightarrow |x| < 2 \Rightarrow -2 < x < 2
```

for the series $ S_5 $ to be convergent. Any values of $ x $ outside of this interval, and the series will fail the ratio test and thus diverge.

An example: find the interval of convergence for the series:

```{math}
S_6 = \sum_{n=1}^\infty \frac{2^n}{x^{n} n^2}
```

Applying the ratio test:

```{math}
\rho = \lim_{n \rightarrow \infty} \left| \frac{2^{n+1}}{x^{n+1} (n+1)^2} \frac{x^n n^2}{2^n} \right| = \lim_{n \rightarrow \infty} \left| \frac{2}{x (1 + \frac{1}{n})^2} \right| = \left| \frac{2}{x} \right|
```

For convergence, we need $ \rho < 1 $, which corresponds to $ |x| > 2 \Rightarrow x > 2,\, x < -2 $.

## Method of Differences 

### Finite Case

Sometimes it is possible to evaluate the result of a series 

```{math}
S = \sum_{n=1}^N a_n
```

due to the fact that some terms in the series cancel out. An example:

```{math}
S_1 = \sum_{n=1}^5 \left( \frac{1}{n} - \frac{1}{n+1} \right)
```

We can expand out this series term by term and see some cancellation occurs:

<div align="center">
    \begin{tabular}{rcccrccl}
       $S_1 = \frac{1}{1} - \frac{1}{2}$ &&&& $S_1 = \frac{1}{1} \,- \not{\frac{1}{2}}$&&\medskip \\
       $ + \frac{1}{2} - \frac{1}{3}$ &&&& $ + \not{\frac{1}{2}} \,- \not{\frac{1}{3}}$&& \medskip \\
       $ + \frac{1}{3} - \frac{1}{4}$ &&$\Rightarrow$&& $ + \not{\frac{1}{3}}\, - \not{\frac{1}{4}}$ &&$ \Rightarrow S_1 = 1 - \frac{1}{6} = \frac{5}{6}$ \medskip \\
       $ + \frac{1}{4} - \frac{1}{5}$ &&&& $ + \not{\frac{1}{4}} \,- \not{\frac{1}{5}}$&& \medskip \\
       $ + \frac{1}{5} - \frac{1}{6}$ &&&& $ + \not{\frac{1}{5}} \,- \frac{1}{6}$&& \medskip\\
    \end{tabular}
</div>

A question may appear not to have an obvious difference set out, an example:

```{math}
S_2 = \sum_{n=1}^{5} \frac{2}{n(n+2)}
``` 

For a fraction of this form, we can make use of *partial fractions*:

```{math}
\frac{2}{n(n+2)} = \frac{A}{n} + \frac{B}{n+2} = \frac{A(n+2) + Bn}{n(n+2)} 
```

Equating numerators gives:

```{math}
(A+B)n + 2A = 2 
```

```{math}
\Rightarrow A = 1, B = -1
```

So looking again at the series:

```{math}
S_2 = \sum_{n=1}^{5} \left( \frac{1}{n} - \frac{1}{n+2} \right)
```

which is now in the form of the method of differences.

Expanding out the first few and last few terms allows us to spot the pattern:

<div align="center">
    \begin{tabular}{rcccrccl}
       $S_2 = \frac{1}{1} - \frac{1}{3}$ &&&& $S_2 = \frac{1}{1} \,- \not{\frac{1}{3}}$&&\medskip \\
       $ + \frac{1}{2} - \frac{1}{4}$ &&&& $ + \frac{1}{2} \,- \not{\frac{1}{4}}$&& \medskip \\
      $ + \frac{1}{3} - \frac{1}{5}$ &&$\Rightarrow$&& $ + \not{\frac{1}{3}} \,- \not{\frac{1}{5}}$&&$ \Rightarrow S_2 = 1 + \frac{1}{2} - \frac{1}{6} - \frac{1}{7} = \frac{25}{21}$ \medskip \\
       $ + \frac{1}{4} - \frac{1}{6}$ &&&& $ + \not{\frac{1}{4}} \,- \frac{1}{6}$&& \medskip \\
       $ + \frac{1}{5} - \frac{1}{7}$ &&&& $ + \not{\frac{1}{5}} \,- \frac{1}{7}$&& \medskip
    \end{tabular}
</div>

### Infinite Case

If we have a series which is composed of an infinite number of terms, it is possible to apply the method of differences to see if it converges. An example:

```{math}
S_3 = \sum_{n=1}^\infty \left( \frac{1}{n} - \frac{1}{n+1} \right)
```

which we can rewrite as:

```{math}
S_4 = \sum_{n=1}^N \left( \frac{1}{n} - \frac{1}{n+1} \right)
```

and after solving by the method of differences, take the limit $ N \rightarrow \infty $:

```{math}
S_4 = 1 - \frac{1}{N+1} \Rightarrow S_3 = \lim_{N \rightarrow \infty} \left( 1 - \frac{1}{N+1} \right) = 1
```

## Sums of Series

We can use the method of differences to find the sums of different power series:

```{math}
\begin{array}{lccl}
 \sum_{r=1}^N \bigg((r+1)^2 - (r-1)^2\bigg) & \Longrightarrow & & \sum_{r=1}^N r = \frac{1}{2}N(N+1) \\ \\
 \sum_{r=1}^N \bigg( (r+1)^3 - r^3 \bigg) & \Longrightarrow & & \sum_{r=1}^N r^2 = \frac{1}{6}N(N+1)(2N+1) \\ \\
 \sum_{r=1}^N \bigg( r^2\, (r+1)^2 - (r-1)^2\,r^2 \bigg)  & \Longrightarrow & & \sum_{r=1}^N r^3 = \frac{1}{4}N^2(N+1)^2 
\end{array}
```

