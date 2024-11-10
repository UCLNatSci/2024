# Series 

# Sequences and Series: Key Concepts with Examples

## Sequences
A sequence is an ordered list of numbers. The general term is denoted as $ a_n $.

### Arithmetic Sequence:
- **Definition**: Each term after the first is obtained by adding a constant difference $d$ to the previous term. The $n$-th term is:
  ```{math}
  a_n = a_1 + (n-1) d
  ```

- **Example 1:**
  Given the arithmetic sequence $2, 5, 8, 11, \dots$, find the $n$-th term.
  ```{math}
  a_1 = 2, \quad d = 3
  ```
  The $n$-th term is:
  ```{math}
  a_n = 2 + (n-1) 3 = 3n - 1
  ```

- **Example 2:**
  Given the arithmetic sequence $10, 7, 4, 1, \dots$, find the $n$-th term.
  ```{math}
  a_1 = 10, \quad d = -3
  ```
  The $n$-th term is:
  ```{math}
  a_n = 10 + (n-1) (-3) = 13 - 3n
  ```

### Geometric Sequence:
- **Definition**: Each term after the first is obtained by multiplying the previous term by a constant ratio $r$. The $n$-th term is:
  ```{math}
  a_n = a_1 r^{n-1}
  ```

- **Example 1:**
  Given the geometric sequence $3, 6, 12, 24, \dots$, find the $n$-th term.
  ```{math}
  a_1 = 3, \quad r = 2
  ```
  The $n$-th term is:
  ```{math}
  a_n = 3 \cdot 2^{n-1}
  ```

- **Example 2:**
  Given the geometric sequence $81, 27, 9, 3, \dots$, find the $n$-th term.
  ```{math}
  a_1 = 81, \quad r = \frac{1}{3}
  ```
  The $n$-th term is:
  ```{math}
  a_n = 81 \cdot \left(\frac{1}{3}\right)^{n-1}
  ```

## Series
A series is the sum of the terms of a sequence. The sum of the first $n$ terms of a sequence $a_n$ is called the partial sum, denoted by $S_n$.

### Arithmetic Series:
- **Definition**: The sum of the first $n$ terms of an arithmetic sequence is given by:
  ```{math}
  S_n = \frac{n}{2} (2a_1 + (n-1) d)
  ```
  or equivalently,
  ```{math}
  S_n = \frac{n}{2} (a_1 + a_n)
  ```

- **Example 1:**
  Find the sum of the first 5 terms of the arithmetic sequence $ 4, 7, 10, 13, \dots $.
  ```{math}
  a_1 = 4, \quad d = 3, \quad n = 5
  ```
  The 5th term is:
  ```{math}
  a_5 = 4 + (5-1) \cdot 3 = 16
  ```
  The sum of the first 5 terms is:
  ```{math}
  S_5 = \frac{5}{2} (4 + 16) = 50
  ```

- **Example 2:**
  Find the sum of the first 6 terms of the arithmetic sequence $ 1, 3, 5, 7, \dots $.
  ```{math}
  a_1 = 1, \quad d = 2, \quad n = 6
  ```
  The 6th term is:
  ```{math}
  a_6 = 1 + (6-1) \cdot 2 = 11
  ```
  The sum of the first 6 terms is:
  ```{math}
  S_6 = \frac{6}{2} (1 + 11) = 36
  ```

### Geometric Series:
- **Definition**: The sum of the first $n$ terms of a geometric sequence is:
  ```{math}
  S_n = a_1 \frac{1 - r^n}{1 - r} \quad \text{(if $r \neq 1$)}
  ```
  If $ |r| < 1 $, the infinite geometric series converges, and its sum is:
  ```{math}
  S_\infty = \frac{a_1}{1 - r}
  ```

- **Example 1:**
  Find the sum of the first 4 terms of the geometric sequence $ 5, 10, 20, 40, \dots $.
  ```{math}
  a_1 = 5, \quad r = 2, \quad n = 4
  ```
  The sum of the first 4 terms is:
  ```{math}
  S_4 = 5 \frac{1 - 2^4}{1 - 2} = 5 \frac{1 - 16}{-1} = 5 \cdot 15 = 75
  ```

- **Example 2:**
  Find the sum of the first 5 terms of the geometric sequence $ 2, 1, \frac{1}{2}, \frac{1}{4}, \dots $.
  ```{math}
  a_1 = 2, \quad r = \frac{1}{2}, \quad n = 5
  ```
  The sum of the first 5 terms is:
  ```{math}
  S_5 = 2 \frac{1 - \left(\frac{1}{2}\right)^5}{1 - \frac{1}{2}} = 2 \cdot \frac{1 - \frac{1}{32}}{\frac{1}{2}} = 2 \cdot \frac{\frac{31}{32}}{\frac{1}{2}} = 2 \cdot \frac{62}{32} = 3.875
  ```

### Infinite Geometric Series:
- **Definition**: An infinite geometric series converges if $ |r| < 1 $, and its sum is:
  ```{math}
  S_\infty = \frac{a_1}{1 - r}
  ```

- **Example 1:**
  Find the sum of the infinite geometric series $ 3 + 1.5 + 0.75 + 0.375 + \dots $.
  ```{math}
  a_1 = 3, \quad r = \frac{1}{2}
  ```
  The sum of the infinite series is:
  ```{math}
  S_\infty = \frac{3}{1 - \frac{1}{2}} = \frac{3}{\frac{1}{2}} = 6
  ```

- **Example 2:**
  Find the sum of the infinite geometric series $ 10 + 5 + 2.5 + 1.25 + \dots $.
  ```{math}
  a_1 = 10, \quad r = \frac{1}{2}
  ```
  The sum of the infinite series is:
  ```{math}
  S_\infty = \frac{10}{1 - \frac{1}{2}} = \frac{10}{\frac{1}{2}} = 20
  ```

## Convergence of Series
A series is said to converge if the sequence of partial sums converges to a finite number.

### Preliminary Test for Convergence (Test A):
- If $ a_n \to 0 $ as $ n \to \infty $, the series may converge, but this condition alone is not sufficient.

- **Example 1:**
  Consider the series $ \sum_{n=1}^{\infty} \frac{1}{n^2} $.
  - As $ n \to \infty $, $ a_n = \frac{1}{n^2} \to 0 $, but this is not enough to determine convergence.

- **Example 2:**
  Consider the series $ \sum_{n=1}^{\infty} \frac{1}{n} $.
  - As $ n \to \infty $, $ a_n = \frac{1}{n} \to 0 $, but the series diverges (harmonic series).

### Ratio Test (D’Alembert's Test) (Test B):
- For the series $ \sum_{n=1}^{\infty} a_n $, consider:
  ```{math}
  L = \lim_{n \to \infty} \left| \frac{a_{n+1}}{a_n} \right|
  ```
  - If $ L < 1 $, the series converges.
  - If $ L > 1 $, the series diverges.
  - If $ L = 1 $, the test is inconclusive.

- **Example 1:**
  Consider the series $ \sum_{n=1}^{\infty} \frac{3^n}{2^n} $.
  - We compute:
  ```{math}
  L = \lim_{n \to \infty} \left| \frac{\frac{3^{n+1}}{2^{n+1}}}{\frac{3^n}{2^n}} \right| = \lim_{n \to \infty} \frac{3}{2} = 1.5 > 1
  ```
  The series diverges.

- **Example 2:**
  Consider the series $ \sum_{n=1}^{\infty} \frac{1}{n!} $.
  - We compute:
  ```{math}
  L = \lim_{n \to \infty} \left| \frac{\frac{1}{(n+1)!}}{\frac{1}{n!}} \right| = \lim_{n \to \infty} \frac{1}{n+1} = 0 < 1
  ```
  The series converges.

## Method of Differences
The method of differences is used to find closed forms for sums of series, often involving differences between successive terms.

### General Approach:
If the sequence $f(k)$ can be written as a difference of two functions $ g(k) - g(k-1) $, then:
```{math}
\sum_{k=1}^{n} f(k) = \sum_{k=1}^{n} \left( g(k) - g(k-1) \right)
```
This simplifies to a telescoping series:
```{math}
\sum_{k=1}^{n} f(k) = g(n) - g(0)
```

- **Example 1:**
  Find the sum of $ \sum_{k=1}^{n} k $. We use the difference $ k = (k+1) - k $:
  ```{math}
  S_n = \sum_{k=1}^{n} k = \sum_{k=1}^{n} \left( (k+1) - k \right) = (1+2+\dots+n) = \frac{n(n+1)}{2}
  ```

- **Example 2:**
  Find the sum of $ \sum_{k=1}^{n} 2^k $. We use the difference $ 2^k = 2^{k+1} - 2^k $:
  ```{math}
  S_n = \sum_{k=1}^{n} 2^k = 2^{n+1} - 2
  ```
