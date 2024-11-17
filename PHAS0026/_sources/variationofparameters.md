# Variation of Parameters

## Definition

The **Variation of Parameters** method provides a way to solve $ n $-th order linear ODEs of the form:
```{math}
y^{(n)}(x) + \sum_{i=0}^{n-1} a_i(x) y^{(i)}(x) = f(x),
```
where the solution is constructed using the linearly independent solutions $ u_1(x), u_2(x), \dots, u_n(x) $ of the homogeneous equation:
```{math}
y^{(n)}(x) + \sum_{i=0}^{n-1} a_i(x) y^{(i)}(x) = 0.
```

---

## The 2x2 Case: Detailed Steps

For a second-order ODE:
```{math}
y''(x) + p(x)y'(x) + q(x)y(x) = r(x),
```
assume the homogeneous solutions $ u_1(x) $ and $ u_2(x) $ are known. The general solution is:
```{math}
y(x) = A(x) u_1(x) + B(x) u_2(x),
```
where $ A(x) $ and $ B(x) $ are functions to be determined.

### Step 1: Differentiating the General Solution

1. **First derivative:**
   ```{math}
   y'(x) = A'(x) u_1(x) + A(x) u_1'(x) + B'(x) u_2(x) + B(x) u_2'(x).
   ```

2. **Simplifying condition:**
   To simplify the system, impose the condition:
   ```{math}
   A'(x) u_1(x) + B'(x) u_2(x) = 0.
   ```
   This removes the terms involving $ A'(x) $ and $ B'(x) $ in the first derivative. Substituting this condition:
   ```{math}
   y'(x) = A(x) u_1'(x) + B(x) u_2'(x).
   ```

3. **Second derivative:**
   Compute the second derivative:
   ```{math}
   y''(x) = A'(x) u_1'(x) + A(x) u_1''(x) + B'(x) u_2'(x) + B(x) u_2''(x).
   ```

---

### Step 2: Substituting into the ODE

Substitute $ y(x) $, $ y'(x) $, and $ y''(x) $ into the original ODE:
```{math}
y''(x) + p(x) y'(x) + q(x) y(x) = r(x).
```

1. Using the homogeneous equation, the terms involving $ A(x) u_1''(x) + B(x) u_2''(x) $ vanish:
   ```{math}
   u_1''(x) + p(x) u_1'(x) + q(x) u_1(x) = 0, \quad
   u_2''(x) + p(x) u_2'(x) + q(x) u_2(x) = 0.
   ```

2. The remaining terms are:
   ```{math}
   A'(x) u_1'(x) + B'(x) u_2'(x) = r(x).
   ```

This gives two equations:
1. From the simplifying condition:
   ```{math}
   A'(x) u_1(x) + B'(x) u_2(x) = 0,
   ```
2. From the substituted ODE:
   ```{math}
   A'(x) u_1'(x) + B'(x) u_2'(x) = r(x).
   ```

---

### Step 3: Writing as a Matrix System

The two equations can be written in matrix form:
```{math}
\begin{pmatrix}
u_1(x) & u_2(x) \\
u_1'(x) & u_2'(x)
\end{pmatrix}
\begin{pmatrix}
A'(x) \\
B'(x)
\end{pmatrix}
=
\begin{pmatrix}
0 \\
r(x)
\end{pmatrix}.
```

Here, the determinant of the coefficient matrix is the **Wronskian**:
```{math}
W(x) = 
\begin{vmatrix}
u_1(x) & u_2(x) \\
u_1'(x) & u_2'(x)
\end{vmatrix}
= u_1(x) u_2'(x) - u_2(x) u_1'(x).
```

---

### Step 4: Solving for $ A'(x) $ and $ B'(x) $

1. **Invert the coefficient matrix:**
   The inverse of the 2x2 matrix is:
   ```{math}
   \frac{1}{W(x)}
   \begin{pmatrix}
   u_2'(x) & -u_2(x) \\
   -u_1'(x) & u_1(x)
   \end{pmatrix}.
   ```

2. **Multiply by the right-hand side vector:**
   ```{math}
   \begin{pmatrix}
   A'(x) \\
   B'(x)
   \end{pmatrix}
   =
   \frac{1}{W(x)}
   \begin{pmatrix}
   u_2'(x) & -u_2(x) \\
   -u_1'(x) & u_1(x)
   \end{pmatrix}
   \begin{pmatrix}
   0 \\
   r(x)
   \end{pmatrix}.
   ```

3. **Perform the multiplication:**
   ```{math}
   A'(x) = \frac{-u_2(x) r(x)}{W(x)}, \quad B'(x) = \frac{u_1(x) r(x)}{W(x)}.
   ```

---

### Step 5: Integrating to Find $ A(x) $ and $ B(x) $

Finally, integrate to find $ A(x) $ and $ B(x) $:
```{math}
A(x) = \int A'(x) \, \mathrm{d}x = -\int \frac{u_2(x) r(x)}{W(x)} \, \mathrm{d}x,
```
```{math}
B(x) = \int B'(x) \, \mathrm{d}x = \int \frac{u_1(x) r(x)}{W(x)} \, \mathrm{d}x.
```

Thus, the particular solution is:
```{math}
y_p(x) = A(x) u_1(x) + B(x) u_2(x).
```

---

### Example

Solve the ODE:
```{math}
y'' + 4y' + 3y = \cosh(2x),
```
with homogeneous solutions:
```{math}
u_1(x) = e^{-x}, \quad u_2(x) = e^{-3x}.
```

The Wronskian is:
```{math}
W(x) = 
\begin{vmatrix} 
e^{-x} & e^{-3x} \\
-e^{-x} & -3e^{-3x}
\end{vmatrix}
= -2e^{-4x}.
```

Using the formulae for $ A'(x) $ and $ B'(x) $, integrate:
```{math}
A(x) = -\frac{1}{2} \int e^{4x} e^{-3x} \cosh(2x) \mathrm{d}x, \quad 
B(x) = \frac{1}{2} \int e^{4x} e^{-x} \cosh(2x) \mathrm{d}x.
```

Solve these integrals to find the full solution.

---


## General Case: $ n $-th Order ODEs*

* This is section not examinable!

For an $ n $-th order ODE:
```{math}
a_n(x) y^{(n)} + a_{n-1}(x) y^{(n-1)} + \dots + a_1(x) y' + a_0(x) y = f(x),
```
assume the $ n $ linearly independent solutions $ u_1(x), u_2(x), \dots, u_n(x) $ of the corresponding homogeneous equation are known:
```{math}
a_n(x) y^{(n)} + a_{n-1}(x) y^{(n-1)} + \dots + a_1(x) y' + a_0(x) y = 0.
```

The general solution is:
```{math}
y(x) = \sum_{i=1}^n k_i(x) u_i(x),
```
where $ k_i(x) $ are functions to be determined.

### Step 1: Imposing Conditions to Simplify the System

To determine $ k_i(x) $, impose $ n $ independent conditions. The simplest and most effective choice is:
```{math}
\sum_{i=1}^n k_i'(x) u_i^{(j)}(x) = 
\begin{cases}
0 & \text{for } j = 0, 1, \dots, n-2, \\
f(x) & \text{for } j = n-1.
\end{cases}
```

This forms a system of $ n $ linear equations for $ k_i'(x) $. Explicitly, the equations can be written in matrix form as:
```{math}
\begin{pmatrix}
u_1(x) & u_2(x) & \cdots & u_n(x) \\
u_1'(x) & u_2'(x) & \cdots & u_n'(x) \\
\vdots & \vdots & \ddots & \vdots \\
u_1^{(n-1)}(x) & u_2^{(n-1)}(x) & \cdots & u_n^{(n-1)}(x)
\end{pmatrix}
\begin{pmatrix}
k_1'(x) \\
k_2'(x) \\
\vdots \\
k_n'(x)
\end{pmatrix}
=
\begin{pmatrix}
0 \\
0 \\
\vdots \\
f(x)
\end{pmatrix}.
```

The coefficient matrix is the **Wronskian**, denoted by $ W(x) $:
```{math}
W(x) = 
\begin{vmatrix}
u_1(x) & u_2(x) & \cdots & u_n(x) \\
u_1'(x) & u_2'(x) & \cdots & u_n'(x) \\
\vdots & \vdots & \ddots & \vdots \\
u_1^{(n-1)}(x) & u_2^{(n-1)}(x) & \cdots & u_n^{(n-1)}(x)
\end{vmatrix}.
```

---

### Step 2: Using Cramer’s Rule to Solve for $ k_i'(x) $

Cramer’s Rule provides an elegant way to solve this system. It states that for a system of linear equations $ W(x) \mathbf{k}' = \mathbf{b} $, the solution for $ k_i'(x) $ is:
```{math}
k_i'(x) = \frac{\det(W_i(x))}{\det(W(x))},
```
where:
- $ \det(W(x)) $ is the determinant of the Wronskian matrix.
- $ \det(W_i(x)) $ is the determinant of the matrix obtained by replacing the $ i $-th column of $ W(x) $ with the right-hand side vector $ \mathbf{b} $:
```{math}
\mathbf{b} =
\begin{pmatrix}
0 \\
0 \\
\vdots \\
f(x)
\end{pmatrix}.
```

Thus, for each $ i $, the modified Wronskian matrix $ W_i(x) $ is:
```{math}
W_i(x) =
\begin{pmatrix}
u_1(x) & \cdots & 0 & \cdots & u_n(x) \\
u_1'(x) & \cdots & 0 & \cdots & u_n'(x) \\
\vdots & \ddots & \vdots & \ddots & \vdots \\
u_1^{(n-1)}(x) & \cdots & f(x) & \cdots & u_n^{(n-1)}(x)
\end{pmatrix}.
```

Each $ 0 $ replaces the $ i $-th column, and the last row contains $ f(x) $.

---

### Step 3: Computing $ k_i(x) $

Once $ k_i'(x) $ is determined, integrate to find $ k_i(x) $:
```{math}
k_i(x) = \int k_i'(x) \, \mathrm{d}x.
```

The particular solution is then:
```{math}
y_p(x) = \sum_{i=1}^n k_i(x) u_i(x).
```

---

### Example: Third-Order ODE

Consider a third-order ODE:
```{math}
y'''(x) + p(x)y''(x) + q(x)y'(x) + r(x)y(x) = f(x),
```
with homogeneous solutions $ u_1(x), u_2(x), u_3(x) $. The system of equations for $ k_1'(x), k_2'(x), k_3'(x) $ is:
```{math}
\begin{pmatrix}
u_1(x) & u_2(x) & u_3(x) \\
u_1'(x) & u_2'(x) & u_3'(x) \\
u_1''(x) & u_2''(x) & u_3''(x)
\end{pmatrix}
\begin{pmatrix}
k_1'(x) \\
k_2'(x) \\
k_3'(x)
\end{pmatrix}
=
\begin{pmatrix}
0 \\
0 \\
f(x)
\end{pmatrix}.
```

The Wronskian is:
```{math}
W(x) =
\begin{vmatrix}
u_1(x) & u_2(x) & u_3(x) \\
u_1'(x) & u_2'(x) & u_3'(x) \\
u_1''(x) & u_2''(x) & u_3''(x)
\end{vmatrix}.
```

Using Cramer’s Rule:
```{math}
k_1'(x) = \frac{\det(W_1(x))}{W(x)}, \quad
k_2'(x) = \frac{\det(W_2(x))}{W(x)}, \quad
k_3'(x) = \frac{\det(W_3(x))}{W(x)}.
```

Here:
- $ W_1(x) $ replaces the first column with $ \begin{pmatrix} 0 \\ 0 \\ f(x) \end{pmatrix} $,
- $ W_2(x) $ replaces the second column with $ \begin{pmatrix} 0 \\ 0 \\ f(x) \end{pmatrix} $,
- $ W_3(x) $ replaces the third column with $ \begin{pmatrix} 0 \\ 0 \\ f(x) \end{pmatrix} $.

Integrate $ k_1'(x), k_2'(x), k_3'(x) $ to find $ k_1(x), k_2(x), k_3(x) $, and construct the particular solution:
```{math}
y_p(x) = k_1(x) u_1(x) + k_2(x) u_2(x) + k_3(x) u_3(x).
```

### Example: Solving $ y''' - y' = e^x $

We solve the third-order ODE:
```{math}
y'''(x) - y'(x) = e^x
```
using the variation of parameters method.

---

#### Step 1: Solve the Homogeneous Equation

The corresponding homogeneous equation is:
```{math}
y'''(x) - y'(x) = 0.
```

Assume a solution of the form $ y = e^{\lambda x} $. Substituting this into the equation gives:
```{math}
\lambda^3 e^{\lambda x} - \lambda e^{\lambda x} = 0.
```
Factoring out $ e^{\lambda x} $, we find:
```{math}
\lambda^3 - \lambda = 0 \quad \implies \quad \lambda (\lambda^2 - 1) = 0.
```

The roots are:
```{math}
\lambda = 0, \quad \lambda = 1, \quad \lambda = -1.
```

Thus, the solutions to the homogeneous equation are:
```{math}
u_1(x) = 1, \quad u_2(x) = e^x, \quad u_3(x) = e^{-x}.
```

---

#### Step 2: Write the General Solution

The general solution is of the form:
```{math}
y(x) = k_1(x) u_1(x) + k_2(x) u_2(x) + k_3(x) u_3(x).
```

---

#### Step 3: Set Up the System of Equations

Using the variation of parameters method, impose the conditions:
```{math}
k_1'(x) u_1(x) + k_2'(x) u_2(x) + k_3'(x) u_3(x) = 0,
```
```{math}
k_1'(x) u_1'(x) + k_2'(x) u_2'(x) + k_3'(x) u_3'(x) = 0,
```
```{math}
k_1'(x) u_1''(x) + k_2'(x) u_2''(x) + k_3'(x) u_3''(x) = e^x.
```

Substitute the known solutions $ u_1(x) = 1 $, $ u_2(x) = e^x $, $ u_3(x) = e^{-x} $:
```{math}
\begin{aligned}
&k_1'(x) (1) + k_2'(x) (e^x) + k_3'(x) (e^{-x}) = 0, \\
&k_1'(x) (0) + k_2'(x) (e^x) - k_3'(x) (e^{-x}) = 0, \\
&k_1'(x) (0) + k_2'(x) (e^x) + k_3'(x) (-e^{-x}) = e^x.
\end{aligned}
```

---

#### Step 4: Write in Matrix Form

In matrix form:
```{math}
\begin{pmatrix}
1 & e^x & e^{-x} \\
0 & e^x & -e^{-x} \\
0 & e^x & -e^{-x}
\end{pmatrix}
\begin{pmatrix}
k_1'(x) \\
k_2'(x) \\
k_3'(x)
\end{pmatrix}
=
\begin{pmatrix}
0 \\
0 \\
e^x
\end{pmatrix}.
```

The coefficient matrix is the Wronskian $ W(x) $, which is:
```{math}
W(x) =
\begin{vmatrix}
1 & e^x & e^{-x} \\
0 & e^x & -e^{-x} \\
0 & e^x & e^{-x}
\end{vmatrix}.
```

---

#### Step 5: Compute the Wronskian

Expand the determinant along the first row:
```{math}
W(x) = 1 \cdot
\begin{vmatrix}
e^x & -e^{-x} \\
e^x & e^{-x}
\end{vmatrix}
- 0 + 0.
```

The 2x2 determinant is:
```{math}
\begin{vmatrix}
e^x & -e^{-x} \\
e^x & e^{-x}
\end{vmatrix}
= (e^x)(e^{-x}) - (e^x)(-e^{-x}) = 1 + 1 = 2.
```

Thus:
```{math}
W(x) = 2.
```

---

#### Step 6: Solve for $ k_1'(x), k_2'(x), k_3'(x) $ Using Cramer’s Rule

With $ W(x) = 2 $, compute the determinants $ W_1(x), W_2(x), W_3(x) $ to find $ k_1'(x), k_2'(x), k_3'(x) $.

#### Compute $ W_1(x) $:
Replace the first column with $ \begin{pmatrix} 0 \\ 0 \\ e^x \end{pmatrix} $:
```{math}
W_1(x) =
\begin{vmatrix}
0 & e^x & e^{-x} \\
0 & e^x & -e^{-x} \\
e^x & e^x & e^{-x}
\end{vmatrix}.
```

Expanding along the first column:
```{math}
W_1(x) = e^x \cdot
\begin{vmatrix}
e^x & -e^{-x} \\
e^x & e^{-x}
\end{vmatrix}.
```

The 2x2 determinant is $ 2 $, so:
```{math}
W_1(x) = e^x \cdot 2 = 2e^x.
```

#### Compute $ W_2(x) $:
Replace the second column with $ \begin{pmatrix} 0 \\ 0 \\ e^x \end{pmatrix} $:
```{math}
W_2(x) =
\begin{vmatrix}
1 & 0 & e^{-x} \\
0 & 0 & -e^{-x} \\
0 & e^x & e^{-x}
\end{vmatrix}.
```

Expanding along the second column:
```{math}
W_2(x) = -e^x \cdot
\begin{vmatrix}
1 & e^{-x} \\
0 & -e^{-x}
\end{vmatrix}.
```

The 2x2 determinant is $ -e^{-x} $, so:
```{math}
W_2(x) = -e^x \cdot (-e^{-x}) = 1.
```

#### Compute $ W_3(x) $:
Replace the third column with $ \begin{pmatrix} 0 \\ 0 \\ e^x \end{pmatrix} $:
```{math}
W_3(x) =
\begin{vmatrix}
1 & e^x & 0 \\
0 & e^x & 0 \\
0 & e^x & e^x
\end{vmatrix}.
```

Expanding along the third column:
```{math}
W_3(x) = e^x \cdot
\begin{vmatrix}
1 & e^x \\
0 & e^x
\end{vmatrix}.
```

The 2x2 determinant is $ e^x $, so:
```{math}
W_3(x) = e^x \cdot e^x = e^{2x}.
```

#### Using Cramer’s Rule:
```{math}
k_1'(x) = \frac{W_1(x)}{W(x)} = \frac{2e^x}{2} = e^x, \quad
k_2'(x) = \frac{W_2(x)}{W(x)} = \frac{1}{2}, \quad
k_3'(x) = \frac{W_3(x)}{W(x)} = \frac{e^{2x}}{2}.
```

---

#### Step 7: Integrate to Find $ k_1(x), k_2(x), k_3(x) $

1. $ k_1'(x) = e^x $, so:
   ```{math}
   k_1(x) = \int e^x \, \mathrm{d}x = e^x + C_1.
   ```

2. $ k_2'(x) = \frac{1}{2} $, so:
   ```{math}
   k_2(x) = \int \frac{1}{2} \, \mathrm{d}x = \frac{1}{2}x + C_2.
   ```

3. $ k_3'(x) = \frac{e^{2x}}{2} $, so:
   ```{math}
   k_3(x) = \int \frac{e^{2x}}{2} \, \mathrm{d}x = \frac{1}{4}e^{2x} + C_3.
   ```

---

#### Step 8: Write the General Solution

The general solution is:
```{math}
y(x) = k_1(x) u_1(x) + k_2(x) u_2(x) + k_3(x) u_3(x).
```

Substitute:
```{math}
y(x) = (e^x + C_1) \cdot 1 + \left(\frac{1}{2}x + C_2\right) \cdot e^x + \left(\frac{1}{4}e^{2x} + C_3\right) \cdot e^{-x}.
```

Simplify:
```{math}
y(x) = \left(1 + C_2 + \frac{1}{4} + \frac{1}{2}x\right)e^x + C_1 + C_3 e^{-x}.
```

Let $ C_4 = 1 + C_2 + \frac{1}{4} $, the final solution is:
```{math}
y(x) = C_1 e^x + C_2 + C_3 e^{-x} + \frac{1}{2}x\,e^x 
```

---


### Summary

- Use the homogeneous solutions to construct the Wronskian $ W(x) $.
- Use Cramer’s Rule to compute $ k_i'(x) $ by solving the linear system.
- Integrate $ k_i'(x) $ to find $ k_i(x) $.
- Combine the $ k_i(x) $ with $ u_i(x) $ to construct the particular solution.

This approach extends naturally to any $ n $-th order ODE.


---
