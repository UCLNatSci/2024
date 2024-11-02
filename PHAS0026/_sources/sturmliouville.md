# Sturm-Liouville Theory


Lets consider a class of second order ordinary differential equation what exhibits certain symmetries and therefore allows us to make progress solving them.  These **Sturm-Liouville** equations are very common in physics, most notably in quantum mechanics and therefore knowing more about their structure and the form of their solutions is very useful.

## The Sturm-Liouville form

Sturm-Liouville (SL) differential equations take the form:
```{math}
p(x) \frac{d^2 y}{\mathrm{d}x^2} + r(x) \frac{dy}{\mathrm{d}x} + q(x) y + \lambda \rho(x) y = 0,
```

Additionally we will specify $ x $ belongs to the interval $ a \leq x \leq b $ and all the functions here are real.  

Functions $ p(x) $ and $ \rho(x) $ are positive, $ r(x) = \frac{dp(x)}{\mathrm{d}x} $ and we will require $ r(x) $ to be continuous - i.e. $ p(x) $ is smooth.

Function $ \rho(x) $ is called the "weight" or "density" function. The value of $ \lambda $ is not specified by the differential equation  itself, but is defined via boundary conditions that $ y(x) $ must satisfy. For example:

```{math}
a_1 y(a) + a_2 y'(a) = 0, \quad b_1 y(b) + b_2 y'(b) = 0.
```

When the boundary conditions are defined, the above equation becomes a Sturm-Liouville (SL) boundary problem, and $ y(x) $ and $ \lambda $ are called the eigenfunction and eigenvalue, respectively.

---

## Other representations of the SL form

The SL form can also be written as:

```{math}
\left[ p(x) \frac{d^2}{\mathrm{d}x^2} + \frac{dp(x)}{\mathrm{d}x} \frac{d}{\mathrm{d}x} + q(x) \right] y(x) = \lambda \rho(x) y(x),
```

or

```{math}
\left[ \frac{d}{\mathrm{d}x} \left( p(x) \frac{d}{\mathrm{d}x} \right) + q(x) \right] y(x) = \lambda \rho(x) y(x).
```

The operator:

```{math}
\bar{L}(x) = \left[ \frac{d}{\mathrm{d}x} \left( p(x) \frac{d}{\mathrm{d}x} \right) + q(x) \right],
```

is called the Sturm-Liouville operator. Using this definition, the ODE becomes:

```{math}
\bar{L}(x) y(x) = \lambda \rho(x) y(x),
```

i.e., $ \lambda $ and $ y(x) $ are the eigenvalue and eigenfunction of the SL differential operator $ L(x) $.

---

## Conversion to the SL form

Any equation of the form:

```{math}
a_2(x) y'' + a_1(x) y' + a_0(x) y + \lambda f(x) y = 0,
```

can be converted to the SL form:

```{math}
\frac{d}{\mathrm{d}x} \left( p(x) \frac{d}{\mathrm{d}x} \right) + q(x) + \lambda \rho(x).
```

Therefore, all results obtained for the SL form are valid for any equation of this type.

To demonstrate this equivalence, set:

```{math}
p(x) = F(x) a_2(x), \quad q(x) = F(x) a_0(x), \quad \rho(x) = F(x) f(x),
```

and

```{math}
F(x) = \exp\left( \int_0^x \frac{a_1(u) - a_0'(u)}{a_2(u)} du \right).
```

Then, notice that:

```{math}
(py')' &= (F a_2 y')' \\
&= F' a_2 y' + F a_2' y' + F a_2 y'' \\
&= \left(\frac{a_1-a_2'}{a_2} F a_2y' + F a_2' y' + F a_2 y'' \right)
&= F(a_2 y'' + a_1 y').
```

Thus,

```{math}
(py')' + q y + \lambda \rho y = F(a_2 y'' + a_1 y' + a_0 y + \lambda f y) = 0,
```

i.e., the SL form is equivalent to the original SL equation.

### Example

Consider the Hermite equation:

```{math}
y'' - 2x y' + 2v y = 0.
```

In the SL form, we have:

```{math}
p(x) &= e^{-x^2} \\
q(x) &= 0 \\
\rho(x) &= e^{-x^2} \\
\lambda &= 2v
```

## Self-adjoint Linear Differential Operators

### Lagrange's identity

If we start by considering $\bar{L}[x]$ in an integral:

```{math}
\int_a^b (\bar{L}[u]) v \, \mathrm{d}x = \int_a^b \left[ - (p u')' + q u \right] v \, \mathrm{d}x,
```

for two functions $ u(x) $ and $ v(x) $, which have continuous second derivatives for $ a \leq x \leq b $. Integrating the right-hand side by parts gives:

```{math}
\int_a^b (\bar{L}[u]) v \, \mathrm{d}x = - \int_a^b (p u')' v \, \mathrm{d}x + \int_a^b q u v \, \mathrm{d}x = - \left[ (p u') v \right]_a^b + \int_a^b u' (p v') \, \mathrm{d}x + \int_a^b q u v \, \mathrm{d}x,
```

i.e.,

```{math}
\int_a^b (\bar{L}[u]) v \, \mathrm{d}x = - p [u'v - uv'] \Big|_a^b + \int_a^b u \bar{L}[v] \, \mathrm{d}x.
```

Thus,

```{math}
\int_a^b \left( \bar{L}[u] v - u \bar{L}[v] \right) \, \mathrm{d}x = \left[ p(x) W(u, v)(x) \right]_a^b,
```

where $ W(u, v)(x) = u'v - uv' $ is the Wronskian of the two functions.  This is known as **Lagrange’s identity**.

Using the boundary conditions given above in the SL form defintion, we find:

```{math}
\left[ p(x) W(u, v)(x) \right]_a^b = 0,
```

so

```{math}
\int_a^b \left( \bar{L}[u] v - u \bar{L}[v] \right) \, \mathrm{d}x = 0.
```

---

### Adjoint operator

In general, for complex functions $ u(x) $ and $ v(x) $ and $L(x)$ is some differential operator, we can write:

```{math}
\int_a^b v^*(x) \cdot [L u(x)] \, \mathrm{d}x = \int_a^b [L^\dagger v(x)]^* \cdot u(x) \, \mathrm{d}x + F(a, b).
```

Hence, if $ L(x)$ is a *linear* differential operator, its adjoint operator can be found by integrating by parts.

We have shown by integration by parts that for the SL operator:

```{math}
\bar{L} = \bar{L}^\dagger,
```

i.e., the SL operator is **self-adjoint**.

If the boundary conditions or the operator are selected so that:

```{math}
\int_a^b v^*(x) \cdot [L u(x)] \, \mathrm{d}x = \int_a^b [L^\dagger v(x)]^* \cdot u(x) \, \mathrm{d}x,
```

the operator $ L(x) $ is called a **Hermitian operator**.

---

## Properties of Eigenfunctions of Sturm-Liouville Equations

### Inner product of two functions

The inner product of real functions $ u(x) $ and $ v(x) $ (also known as overlap integral or scalar product) is defined as:

```{math}
(u, v) = \int_a^b u(x) v(x) \, \mathrm{d}x.
```

For complex functions $ u(x) = u_1(x) + i u_2(x) $ and $ v(x) = v_1(x) + i v_2(x) $, where $ u_1 $, $ u_2 $, $ v_1 $, and $ v_2 $ are real functions, the inner product is defined as:

```{math}
(u, v) = \int_a^b (u_1(x) + i u_2(x))(v_1(x) - i v_2(x)) \, \mathrm{d}x.
```

Note that:

```{math}
(u, u) = \int_a^b u(x) u^*(x) \, \mathrm{d}x = \int_a^b \left( u_1(x)^2 + u_2(x)^2 \right) \, \mathrm{d}x.
```

In these notations, Lagrange’s identity is:

```{math}
(\bar{L}[u], v) - (u, \bar{L}[v]) = 0.
```

If $ u(x) $ is an eigenfunction of $ L(x) $, then the inner product of $ \bar{L}[u] $ and $ v $ is:

```{math}
(\bar{L}[u], v) = \int_a^b \lambda \rho(x) u(x) v(x) \, \mathrm{d}x.
```

---

### Eigenvalues of the SL problem are real

Let us assume that we have found $ \lambda $ and $ \phi(x) $, which satisfy the SL boundary problem:

```{math}
\bar{L}\phi = \lambda \rho \phi,
```

with the boundary conditions given before. Assume that $ \lambda $ and $ y(x) $ are complex:

```{math}
\lambda = \mu + i \nu, \quad \phi(x) = u(x) + iv(x).
```

Clearly:

```{math}
(\bar{L}[\phi], \phi) = (\phi, \bar{L}[\phi]).
```

Since $ \phi(x) $ is an eigenfunction, this becomes:

```{math}
(\lambda \rho \phi, y) = (y, \lambda \rho y),
```

which simplifies to:

```{math}
(\lambda - \lambda^*) \int_a^b \rho(x) \phi(x) y^*(x) \, \mathrm{d}x = 0.
```

Since $ \rho(x) > 0 $ and $ |\phi(x)|^2 > 0 $, the only possibility is that:

```{math}
\lambda = \lambda^*.
```

Thus, eigenvalues $ \lambda $ of the SL problem are real.

---

### Eigenfunctions of the SL problem are real

Consider the equation:

```{math}
L y = \lambda \rho y,
```

and its complex conjugate:

```{math}
(L y)^* = (\lambda \rho y)^*.
```

Since $ L(x) $, $ \rho(x) $, and $ \lambda $ are all real:

```{math}
(L y)^* = L y^* = \lambda^* \rho y^* = \lambda \rho y^*.
```

If $ \phi(x) $ is complex, we can set $ \phi(x) = u(x) + iv(x) $, where $ u(x) $ and $ v(x) $ are real functions, and construct two non-trivial linear combinations of $ \phi(x) $ and $ \phi^*(x) $:

```{math}
\phi_1(x) = \phi(x) + \phi^*(x) = 2u(x), \quad \phi_2(x) = i(\phi(x) - \phi^*(x)) = 2v(x).
```

Applying $ \bar{L} $ to $ \phi_1 $ and $ \phi_2 $ gives:

```{math}
\bar{L} \phi_1 = \bar{L}(2u) = \lambda \rho(2u), \quad \bar{L} \phi_2 = \bar{L}(2v) = \lambda \rho(2v),
```

i.e., real functions $ u(x) $ and $ v(x) $ are eigenfunctions of $ L $ with the same eigenvalues as $ \phi(x) $ and $ \phi^*(x) $. Thus, eigenfunctions of the SL problem can always be chosen as real.

---

### Orthogonality of Eigenfunctions

If two eigenvalues of the SL problem differ ($ \lambda_1 \neq \lambda_2 $), the corresponding eigenfunctions $ \phi_1 $ and $ \phi_2 $ obey:

```{math}
\int_a^b \rho(x) \phi_1(x) \phi_2(x) \, \mathrm{d}x = 0,
```

i.e., they are orthogonal with respect to the weight function $ \rho(x) $.

---
### Non-degenerate Eigenstates

If two eigenvalues of the Sturm-Liouville (SL) problem differ ($ \lambda_1 \neq \lambda_2 $), the corresponding eigenfunctions $ \phi_1 $ and $ \phi_2 $ obey:
```{math}
\int_a^b \rho(x) \phi_1(x) \phi_2(x) \, \mathrm{d}x = 0,
```
i.e., they are said to be orthogonal with the weight $ \rho(x) $.

Indeed, let us consider two eigenfunctions and two corresponding eigenvalues of an SL operator $ \bar{L} $ with appropriate boundary conditions:
```{math}
\bar{L} \phi_1 = \lambda_1 \rho \phi_1 \quad \text{and} \quad \bar{L} \phi_2 = \lambda_2 \rho \phi_2.
```

Using the Lagrange identity for $ \phi_1 $ and $ \phi_2 $:
```{math}
(\lambda_1 \rho \phi_1, \phi_2) - (\phi_1, \lambda_2 \rho \phi_2) = 0.
```

For real eigenfunctions, this gives
```{math}
(\lambda_1 - \lambda_2) \int_a^b \rho(x) \phi_1(x) \phi_2(x) \, \mathrm{d}x = 0.
```

Thus, if $ \lambda_1 \neq \lambda_2 $, then
```{math}
\int_a^b \rho(x) \phi_1(x) \phi_2(x) \, \mathrm{d}x = 0.
```

---

### The case of degenerate eigenvalues

Suppose an operator $L$ has eigenvalues

```{math}
\lambda_1, \lambda_2, \dots, \lambda_{k-1}, \lambda_k, \lambda_{k+1}, \lambda_{k+2}, \dots, \lambda_{k+n}, \lambda_{k+n+1}, \dots
```

and one of the eigenvalues, $ \lambda $, is $ n $-times degenerate, i.e.

```{math}
\lambda_{k+1} = \lambda_{k+2} = \dots = \lambda_{k+n} = \lambda.
```

Then any linear combination of the corresponding eigenfunctions

```{math}
\phi = c_1 \phi_{k+1} + c_2 \phi_{k+2} + \dots + c_n \phi_{k+n},
```

is also an eigenfunction of $L$ with the same eigenvalue

If $ \phi $ is also an eigenfunction of $ L $ with the same eigenvalue $ \lambda $, then
```{math}
L \phi = \sum_{i=1}^{n} c_{k+i} [L \phi_{k+i}] = \sum_{i=1}^{n} c_{k+i} [\lambda_{k+i} \rho \phi_{k+i}] = \lambda \rho \sum_{i=1}^{n} c_{k+i} \phi_{k+i} = \lambda \rho \phi.
```
Thus, an infinite number of eigenfunctions with the eigenvalue $ \lambda $ can be constructed.

Since the eigenfunctions corresponding to $ \lambda_1 $ and $ \lambda_2 $, where $ \lambda_1 \neq \lambda_2 $, are orthogonal, linear combinations
```{math}
\phi = c_1 \phi_{k+1} + c_2 \phi_{k+2} + \dots + c_{n-1} \phi_{k+n-1} + c_n \phi_{k+n}
```
are orthogonal to the eigenfunctions $ \phi_m $ of $ L $ for all $ m \leq k $ and all $ m > k+n $ for any selection of the coefficients $ c_i $.

One question to ask here is it possible to define such combinations of the coefficients $ c^{(j)}_i $ ($ 1 \leq i, j \leq n $) that any two of the functions:
```{math}
\phi^{(i)} = \sum_{j=1}^{n} c^{(i)}_j \phi_{k+j}, \quad (i = 1, 2, \dots, n)
```
i.e.,
```{math}
\phi^{(1)} = c^{(1)}_1 \phi_{k+1} + c^{(1)}_2 \phi_{k+2} + \dots + c^{(1)}_{n-1} \phi_{k+n-1} + c^{(1)}_n \phi_{k+n}
```
```{math}
\phi^{(2)} = c^{(2)}_1 \phi_{k+1} + c^{(2)}_2 \phi_{k+2} + \dots + c^{(2)}_{n-1} \phi_{k+n-1} + c^{(2)}_n \phi_{k+n}
```
```{math}
\vdots
```
```{math}
\phi^{(n)} = c^{(n)}_1 \phi_{k+1} + c^{(n)}_2 \phi_{k+2} + \dots + c^{(n)}_{n-1} \phi_{k+n-1} + c^{(n)}_n \phi_{k+n},
```
are also orthogonal for any $ i \neq j $?


---

### Gram-Schmidt Orthogonalization

This is one of the main methods used for orthogonalization of linearly independent functions. We can set:

```{math}
\phi^{(1)} = \phi_{k+1},
```

and normalize it so that:

```{math}
\int_a^b \phi^{(1)}(x) \phi^{(1)}(x) \rho(x) \, \mathrm{d}x = 1.
```

Then, construct $ \phi^{(2)} $ as

```{math}
\phi^{(2)} = \phi_{k+2} - \phi^{(1)} \left( \int_a^b \phi^{(1)} \phi_{k+2} \rho \, \mathrm{d}x \right).
```

To check that $ \phi^{(1)} $ and $ \phi^{(2)} $ are orthogonal, we can calculate:

```{math}
\int_a^b \phi^{(1)} \phi^{(2)} \rho \, \mathrm{d}x = \int_a^b \phi^{(1)} \phi_{k+2} \rho \, \mathrm{d}x - \left( \int_a^b \phi^{(1)} \phi^{(1)} \rho \, \mathrm{d}x \right) \left( \int_a^b \phi^{(1)} \phi_{k+2} \rho \, \mathrm{d}x \right) = 0.
```

In order to proceed further, normalize $ \phi^{(2)} $ and construct $ \phi^{(3)} $ as

```{math}
\phi^{(3)} = \phi_{k+3} - \phi^{(1)} \left( \int_a^b \phi^{(1)} \phi_{k+3} \rho \, \mathrm{d}x \right) - \phi^{(2)} \left( \int_a^b \phi^{(2)} \phi_{k+3} \rho \, \mathrm{d}x \right),
```

and so on for $ \phi^{(4)}, \dots, \phi^{(n)} $.

Thus, the eigenfunctions of the SL boundary problem are either orthogonal (for $ \lambda_i \neq \lambda_j $) or can be made orthogonal (for $ \lambda_i = \lambda_j $).

---

## Basis set

Suppose functions $ \phi_i(x) $ ( $ i = 1, 2, \dots $) are normalized and orthogonal to each other. These functions are called **orthonormal**, and they are convenient to use as a basis set in order to represent reasonably well-behaved functions as linear combinations of the type:

```{math}
f(x) = \sum_{i=1}^{\infty} c_i \phi_i(x).
```

To find the coefficients $ c_n $, multiply both parts of the above expression by $ \phi_n^*(x) \rho $ and integrate over $ \mathrm{d}x $ (use the orthonormality of $ \phi_n $):

```{math}
\int_a^b \phi_n^*(x) f(x) \rho(x) \, \mathrm{d}x = \sum_{i=1}^{\infty} c_i \int_a^b \phi_n^*(x) \phi_i(x) \rho(x) \, \mathrm{d}x = c_n.
```

Thus, the coefficients are:

```{math}
c_n = \int_a^b \phi_n^*(x) f(x) \rho(x) \, \mathrm{d}x.
```

---

### Dirichlet conditions

A "reasonably well-behaved function" $ f(x) $, for $ x \in [a, b] $, where $ a $ and $ b $ are finite, satisfies the following conditions:

1. It must be single-valued.
2. It must be continuous except for a finite number of discontinuities.
3. It must have a finite number of maxima and minima.
4. The integral $ \int_a^b |f(x)| \, \mathrm{d}x $ must converge.

---

### Completeness of a basis set

If the basis set $ \phi_i(x) $ is such that the expansion

```{math}
f(x) = \sum_{i=1}^{\infty} c_i \phi_i(x)
```

holds for any reasonably well-behaved function $ f(x) $, the basis set is said to be **complete**.

Can we express the completeness of a basis set formally? Substituting the expression for the coefficients $ c_i $:

```{math}
f(x) = \sum_{i=1}^{\infty} \phi_i(x) c_i = \sum_{i=1}^{\infty} \phi_i(x) \left( \int_a^b \phi_i^*(t) f(t) \rho(t) \, \mathrm{d}t \right) = \int_a^b f(t) \rho(t) \sum_{i=1}^{\infty} \phi_i^*(t) \phi_i(x) \, \mathrm{d}t.
```

Compare this expression with the following representation:

```{math}
f(x) = \int_a^b f(t) \delta(x - t) \, \mathrm{d}t.
```

Hence, if the basis set is complete, we should have:

```{math}
\rho(t) \sum_{i=1}^{\infty} \phi_i^*(t) \phi_i(x) = \delta(x - t),
```

which is called the **completeness** or **closure condition**.

---

### Practical basis sets

In practical calculations, basis sets are always finite. In this case, the completeness of a basis set can be expressed in terms of deviations of a function $ f(x) $ from its approximate value:

```{math}
\sum_{i=1}^{N} \phi_i(x) c_i = \sum_{i=1}^{N} \phi_i(x) \left( \int_a^b \phi_i^*(t) f(t) \rho(t) \, \mathrm{d}t \right),
```

for all $ x \in [a, b] $. As $ N $ increases, these deviations should become smaller. Hence, for a complete basis $ \phi_i $:

```{math}
\lim_{N \to \infty} \int_a^b \left| f(x) - \sum_{i=1}^{N} \phi_i(x) c_i \right|^2 \rho(x) \, \mathrm{d}x = 0.
```

This condition also gives a criterion for estimating the proximity of a finite and, in general, incomplete basis set to a complete basis set.

---

### Examples

- In materials modeling: Representation of Slater exponential functions using a finite number of Gaussian-type functions.
- Expansion of electron density over a basis set of plane waves.

---

### Examples of complete basis sets

Two widely used examples of complete basis sets include:

1. A set of $ \sin(nx) $ and $ \cos(nx) $, where $ n = 0, 1, 2, \dots $, which forms a special case of a bi-orthogonal complete basis set for $ x \in [0, 2\pi] $.
2. Polynomial functions $ p_n(x) = x^n $, where $ n = 0, 1, 2, \dots $. Special linear combinations of $ p_n(x) $ are considered below.

---

## Construction of Green's Functions and Representation of the $\delta$-Function

Suppose $ \phi_n(x) $ and $ \lambda_n $ are eigenfunctions and eigenvalues of a Hermitian operator:

```{math}
\bar{L}(x) = -\left[ \frac{d}{\mathrm{d}x} \left( p(x) \frac{d}{\mathrm{d}x} \right) + q(x) \right],
```

i.e.,

```{math}
\bar{L} \phi_n(x) = \lambda_n \rho(x) \phi_n(x), \quad x \in [a, b],
```

and functions $ \phi_n(x) $ satisfy boundary conditions that make the operator $ L $ Hermitian. Thus, according to what we have proven above, $ \phi_n(x) $ and $ \lambda_n $ are real, and functions $ \phi_n(x) $ are orthogonal, i.e.,

```{math}
\int_a^b \phi_k(x) \phi_n(x) \rho(x) \, \mathrm{d}x = 0 \quad \text{if} \quad k \neq n.
```

Importantly, $ \phi_n(x) $ forms a complete basis set.

Now, let us solve the ODE:

```{math}
\bar{L}y(x) = f(x).
```

A solution $ y(x) $ can be represented as an expansion over functions $ \phi_n $:

```{math}
y(x) = \sum_{n=1}^{\infty} c_n \phi_n(x).
```

Then, function $ f(x) $ can be written as:

```{math}
f(x) = \bar{L}y(x) = \bar{L} \left( \sum_{n=1}^{\infty} c_n \phi_n(x) \right) = \sum_{n=1}^{\infty} c_n [L \phi_n(x)] = \sum_{n=1}^{\infty} c_n \lambda_n \rho(x) \phi_n(x).
```

If $ \phi_n $ and $ \lambda_n $ are known, we can determine all coefficients $ c_n $. For that, multiply both parts by $ \phi_n $ and integrate over $ \mathrm{d}x $ (use the orthogonality of $ \phi_n $):

```{math}
\int_a^b \phi_k(x) f(x) \mathrm{d}x = \sum_{n=1}^{\infty} \int_a^b c_n \lambda_n \phi_k(x) \phi_n(x) \rho(x) \mathrm{d}x = c_k \lambda_k \int_a^b \phi_k(x) \phi_k(x) \rho(x) \mathrm{d}x.
```

If functions $ \phi_k(x) $ are normalized so that:

```{math}
\int_a^b \phi_k(x) \phi_k(x) \rho(x) \mathrm{d}x = 1,
```

we have:

```{math}
c_k = \frac{1}{\lambda_k} \int_a^b \phi_k(x) f(x) \mathrm{d}x.
```

Use these coefficients to write down a solution to the ODE:

```{math}
y(x) = \sum_{n=1}^{\infty} c_n \phi_n(x) = \sum_{n=1}^{\infty} \frac{1}{\lambda_n} \phi_n(x) \left( \int_a^b \phi_n(t) f(t) \mathrm{d}t \right).
```

We can rearrange the terms and rewrite $ y(x) $ as:

```{math}
y(x) = \int_a^b \left( \sum_{n=1}^{\infty} \frac{1}{\lambda_n} \phi_n(x) \phi_n(t) \right) f(t) \mathrm{d}t.
```

Compare this expression with the Green’s function, which we looked at earlier in the module:

```{math}
y(x) = \int_a^b G(x, t) f(t) \mathrm{d}t.
```

From here we find that the Green’s function can be expressed as:

```{math}
G(x, t) = \sum_{n=1}^{\infty} \frac{1}{\lambda_n} \phi_n(x) \phi_n(t),
```

which is called **spectral representation**.

Finally, previously we established that $ G(x, t) $ should satisfy the equation:

```{math}
L [G(x, t)] = \delta(x - t).
```

Let us apply $ L $ to both parts of the spectral representation of $ G(x, t) $ using the SL operator:

```{math}
\sum_{n=1}^{\infty} \frac{1}{\lambda_n} \left[ \bar{L} \phi_n(x) \right] \phi_n(t) = \sum_{n=1}^{\infty} \frac{1}{\lambda_n} \left[ \lambda_n \rho(x) \phi_n(x) \right] \phi_n(t) = \rho(x) \sum_{n=1}^{\infty} \phi_n(x) \phi_n(t) = \delta(x-t).
```

which is the condition for the completeness of the basis set formed by $ \phi_n(x) $.

---

### Generalization to more complex equations

We can generalize this approach to more complex equations of the form:

```{math}
Ly(x) - \mu \rho(x) y(x) = f(x),
```

where $ L $ is Hermitian, and $ \mu $ is a constant. Similarly to what we discussed earlier, search for a solution $ y(x) $ in the form of a series $ \sum c_n \phi_n(x) $. To find the coefficients $ c_n $, substitute $ y(x) $ into the ODE:

```{math}
\rho(x) \sum_{n=1}^{\infty} (\lambda_n - \mu) c_n \phi_n(x) = \rho(x) \sum_{n=1}^{\infty} \phi_n(x) \left( \int_a^b \phi_n(t) f(t) \mathrm{d}t \right).
```

Multiply both parts by $ \phi_k(x) $ and integrate over $ \mathrm{d}x $:

```{math}
(\lambda_k - \mu) c_k = \int_a^b \phi_k(t) f(t) \mathrm{d}t,
```

i.e.,

```{math}
c_k = \frac{1}{\lambda_k - \mu} \int_a^b \phi_k(t) f(t) \mathrm{d}t.
```

Thus, the solution is:

```{math}
y(x) = \sum_{n=1}^{\infty} c_n \phi_n(x) = \sum_{n=1}^{\infty} \frac{1}{\lambda_n - \mu} \phi_n(x) \left( \int_a^b \phi_n(t) f(t) \mathrm{d}t \right).
```

Clearly, if there exists $ k $ such that $ \mu = \lambda_k $, the solution $ y(x) $ becomes infinite. To avoid this singularity, we request that:

```{math}
\int_a^b \phi_k(t) f(t) \mathrm{d}t = 0,
```

for the particular $ k $, ensuring that the ratio:

```{math}
\frac{1}{\lambda_k - \mu} \int_a^b \phi_k(t) f(t) \mathrm{d}t
```

is finite.

---

## Examples of Orthogonal Polynomials

### Legendre Functions

Legendre’s differential equation:

```{math}
(1 - x^2) y'' - 2x y' + \ell(\ell + 1) y = 0
```

is a particular case of the Sturm-Liouville form with:
```{math}
p(x) &= 1 - x^2 \\
q(x) &= 0 \\
\rho(x) &= 1 \\
\lambda &= \ell(\ell + 1) 
```

We can look for solutions of this equation in the form:

```{math}
y(x) = \sum_{n=0}^{\infty} a_n x^n.
```

Substituting this into Legendre’s equation gives:

```{math}
\sum_{n=0}^{\infty} \left[ n(n-1) a_n x^{n-2} - n(n-1) a_n x^n - 2n a_n x^n + \ell(\ell+1) a_n x^n \right] = 0,
```

from which we can obtain the recurrence relation by comparing coefficients of $x^n$:

```{math}
(n+2)(n+1) a_{n+2} - \left[ n(n+1) - \ell(\ell + 1) \right] a_n = 0.
```

Thus,

```{math}
a_{n+2} = \frac{n(n + 1) - \ell(\ell + 1)}{(n + 1)(n + 2)} a_n,
```

i.e., any coefficient $ a_k $ can be calculated if $ a_{k-2} $ is known (for $ k \geq 2 $).

Using this recurrence relations we find two different types of solution generated:

1. Let us set $ a_0 = 1 $ and $ a_1 = 0 $. Then, the even coefficients $ a_2, a_4, \dots $ can be calculated as follows:

```{math}
a_2 = \frac{-\ell(\ell + 1)}{1 \cdot 2} a_0 = \frac{-\ell(\ell + 1)}{2},
```

```{math}
a_4 = \frac{2(2 + 1) - \ell(\ell + 1)}{3 \cdot 4} a_2 = \frac{(\ell-2)\ell(\ell+1)(\ell+3)}{4!}.
```

Therefore, the solution with even powers of $x$ is:

```{math}
y_{\text{even}}(x) = 1 - \frac{\ell(\ell + 1)}{2!} x^2 + \frac{(\ell - 2)\ell(\ell + 1)(\ell + 3)}{4!} x^4 + \dots.
```

2. For the odd powers, let us set $ a_0 = 0 $ and $ a_1 = 1 $. Then, the odd coefficients $ a_3, a_5, \dots $ are:

```{math}
a_3 = \frac{1 \cdot 2 - \ell(\ell + 1)}{2 \cdot 3} a_1,
```

and the corresponding solution contains only odd powers of $ x $:

```{math}
y_{\text{odd}}(x) = x - \frac{(\ell - 1)(\ell + 2)}{3!} x^3 + \dots.
```

The general solution of the ODE is a linear combination of the even and odd solutions:

```{math}
y(x) = c_1 y_{\text{even}}(x) + c_2 y_{\text{odd}}(x).
```

For integer values of $ \ell $, the series for $ y_{\text{even}}(x) $ becomes finite if $ \ell $ is even, and the series for $ y_{\text{odd}}(x) $ becomes finite if $ \ell $ is odd.

Such functions $ y(x) $ are denoted $ P_\ell(x) $ and called **Legendre polynomials**. They are normalized such that:

```{math}
P_\ell(1) = 1.
```

For example, the first few Legendre polynomials are:
```{math}
P_0(x) &= 1 \\
P_1(x) &= x \\
P_2(x) &= \frac{1}{2}(3x^2 - 1) \\
P_3(x) &= \frac{1}{2}(5x^3 - 3x)
```
---

### Rodrigues' Formula

Legendre polynomials can also be expressed using Rodrigues’ formula:

```{math}
P_\ell(x) = \frac{1}{2^\ell \ell!} \frac{d^\ell}{\mathrm{d}x^\ell} \left( x^2 - 1 \right)^\ell.
```

To prove this, let $ u = (x^2 - 1)^\ell $. Then:

```{math}
u' = 2 \ell x (x^2 - 1)^{\ell - 1}.
```

Applying the derivative $ \ell $ times and simplifying the result leads to the expression for $ P_\ell(x) $.

---

### Orthogonality of Legendre Polynomials

Polynomials $ P_k(x) $ and $ P_n(x) $ are orthogonal over the interval $ x \in [-1, 1] $ if $ k \neq n $. To prove this, consider:

```{math}
\left[ (1 - x^2) P_k' \right]' + k(k + 1) P_k = 0,
```

multiply it by $ P_n $ and integrate by parts. The result is:

```{math}
\int_{-1}^1 P_k(x) P_n(x) \mathrm{d}x = 0 \quad \text{for} \quad k \neq n.
```

---

### Chebyshev Polynomials

Chebyshev polynomials are solutions of the differential equation:

```{math}
(1 - x^2) y'' - x y' + \nu^2 y = 0.
```

For integer $ \nu $, these solutions are called **Chebyshev polynomials**. There are two types of Chebyshev polynomials:

1. **Chebyshev polynomials of the first kind** $ T_n(x) $ are given by:

```{math}
T_n(x) = \cos(n \arccos(x)).
```

2. **Chebyshev polynomials of the second kind** $ U_n(x) $ are given by:

```{math}
U_n(x) = \frac{\sin((n+1) \arccos(x))}{\sqrt{1 - x^2}}.
```

---