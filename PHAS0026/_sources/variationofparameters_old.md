
# Variation of Parameters



````{admonition} Definition
The variation of parameters method can be used to solve $n^{th}$ degree linear  ODEs of the form:
```{math}
y^{(n)}(x) + \sum^{n-1}_{i=0} a_i(x)\,y^{(i)}(x) = f(x)
```
which can be shown to have the solution:
```{math}
\sum_{i=1}^{n} u_i(x)\, \int \frac{W_i(x)}{W(x)}\,\mathrm{d}x
```
where $u_i(x),\, i \in \{1,\, 2,\, \dots,\, n\}$ are the the homogeneous solutions of the ODE, $W(x)$ is the Wronskian of these homogeneous solutions:
```{math}
W \Big(u_{1}, \ldots ,u_{n}\Big)=
\begin{vmatrix}
u_{1}(x) & u_{2}(x) & \cdots & u_{n}(x)\\
u_{1}'(x) & u_{2}'(x) & \cdots & u_{n}'(x)\\
\vdots &\vdots &\ddots &\vdots \\
u_{1}^{(n-1)}(x) & u_{2}^{(n-1)}(x) & \cdots & u_{n}^{(n-1)}(x)
\end{vmatrix}
```
and $W_i(x)$ is the reduced Wronskian:
```{math}
W_i(x) = \begin{vmatrix}
u_{1}(x) & u_{2}(x) & \cdots & 0 & \cdots & u_{n}(x)\\
u_{1}'(x) & u_{2}'(x) & \cdots & 0& \cdots & u_{n}'(x)\\
\vdots &\vdots &\ddots &\vdots &\vdots &\vdots \\
u_{1}^{(n-1)}(x) & u_{2}^{(n-1)}(x) & \cdots & f(x)& \cdots & u_{n}^{(n-1)}(x)
\end{vmatrix}
```
where the $i^{th}$ column of the Wronskian $W(x)$ has been replaced with:
```{math} 
\begin{pmatrix}
0 \\ 0 \\ \vdots \\ f(x)
\end{pmatrix}
```

````


Let’s begin again with the form of the inhomogeneous second order equation:
```{math}
L\,y(x) = y^{\prime\prime}(x)+p(x)\,y^{\prime}(x)+q(x)\,y(x) = r(x)
```
firstly we aim to solve the homogeneous equation:
```{math}
L\,y(x) = y^{\prime\prime}(x)+p(x)\,y^{\prime}(x)+q(x)\,y(x) = 0
```
which will admit solutions $u_1(x),\, u_2(x)$. Hence we will construct a solution to the general equation of the form:
```{math}
y(x) = A(x)\,u_1(x) + B(x)\,u_2(x)
``` 
We note that if $A(x),\, B(x)$ here were just constants, then this would be a linear superposition of the homogeneous solutions - therefore in general these should contain some additive constant with each function.  In order to have two equations with two unknowns, we need to enforce a separate condition on $A(x),\, B(x)$, as we will see the most helpful condition to simplify later algebra turns out to be:
```{math}
A'(x)\,u_1(x) + B'(x)\,u_2(x) = 0
```
If we try to constuct the form of the second order equation using this first condition, we will find:
```{math}
y'(x) &= \Big(A(x)\,u_1(x) + B(x)\,u_2(x)\Big)' \\
&= A'(x)\,u_1(x) + B'(x)\,u_2(x) + A(x)\,u_1'(x) + B(x)\,u_2'(x)\\
&= A(x)\,u_1'(x) + B(x)\,u_2'(x)
```
where we have used our second condition to reach the final line.  Likewise for second derivatives:
```{math}
y''(x) = A(x)\,u_1''(x) + B(x)\,u_2''(x) + A'(x)\,u_1'(x) + B'(x)\,u_2'(x)
```
and so using the linear derivative operator:
```{math}
L\, y(x) &= A(x)\,u_1''(x) + B(x)\,u_2''(x) + A'(x)\,u_1'(x) + B'(x)\,u_2'(x) \\ &+ p(x)\,(A(x)\,u_1'(x) + B(x)\,u_2'(x)) \\ &+ q(x)\,(A(x)\,u_1(x) + B(x)\,u_2(x)) = f(x)\\
&= A(x)(u''(x) + p(x\,)u'(x) + q(x)\,u(x)) + B(x)(u''(x) + p(x)\,u'(x) + q(x)\,u(x)) \\
&+ A'(x)\,u_1'(x) + B'(x)\,u_2'(x)\\
&= A'(x)\,u_1'(x) + B'(x)\,u_2'(x) + A(x)\,L\,u_1(x) + B(x)\,L\,u_2(x)\\
&= A'(x)\,u_1'(x) + B'(x)\,u_2'(x)
```
where we have used the fact that the terms with $A(x),\, B(x)$ coefficients are actually just the homogeneous equations, hence they equal zero.  So this leaves a coupled ODE system:
```{math}
A'(x)\,u_1(x) + B'(x)\,u_2(x) &= 0\\
A'(x)\,u_1'(x) + B'(x)\,u_2'(x) &= r(x)
```
which if we write as a matrix system $W(x)\,a = b$:
```{math}
\begin{pmatrix}
u_1(x) & u_2(x) \\
u_1'(x) & u_2'(x)
\end{pmatrix}
\begin{pmatrix}
A'(x) \\
B'(x)
\end{pmatrix} = 
\begin{pmatrix}
0 \\
r(x)
\end{pmatrix}
```
where $W(x)$ is the Wronskian of the system. 

So to find the solutions $a = W^{-1}\,b$ we can invert this matrix as:
```{math}
\begin{pmatrix}
A'(x) \\
B'(x)
\end{pmatrix} = \frac{1}{W}\begin{pmatrix}
u_2'(x) & -u_2(x) \\
-u_1'(x) & u_1(x)
\end{pmatrix}
\begin{pmatrix}
0 \\
f(x)
\end{pmatrix} = \frac{1}{W}\begin{pmatrix}
-u_2(x)\,r(x) \\
u_1(x)\,r(x)
\end{pmatrix}
```
which means the final solutions can be found from:
```{math}
A(x) &= -\int \frac{1}{W}\,u_2(x)\,r(x) \,\mathrm{d}x \\
B(x) &= \int \frac{1}{W}\,u_1(x)\,r(x) \,\mathrm{d}x \\
```

````{admonition} Worked example
:class: seealso
Lets try and solve the ODE:
```{math}
y'' + 4y' + 3y = \cosh(2x)
```
subject to the conditions $y(0) = -\frac{7}{15}, \,y'(0)=\frac{1}{15}$.  We note that this could be solved with method of undetermined coefficients, but this 
means we can double check our results later!

The solutions to the homoegenous ODE can be found from the ansatz $y = e^{\lambda\,x}$:

```{math}
\lambda^2 + 4\lambda + 3 = 0 &\Rightarrow \lambda = -1,\, -3 \\
u_1(x) &= e^{-x} \\
u_2(x) &= e^{-3x}
```
which means that in order to construct the full solution:
```{math}
y(x) = A(x)\,u_1(x) + B(x)\,u_2(x)
```
We need the Wronskian $W(x)$ of the system, here given by:
```{math}
W = \begin{vmatrix} 
e^{-x} & e^{-3x} \\
-e^{-x} & -3e^{-3x}
\end{vmatrix} = -3e^{-4x} - (-e^{-4x}) = -2e^{-4x}
```
and so using {eq}`varparsolns`:
```{math}
A(x) &= \frac{1}{2}\int e^{4x}\,e^{-3x}\,\cosh(2x) \,\mathrm{d}x  = \frac{1}{4}\int \Big(e^{3x}+e^{-x}\Big) \,\mathrm{d}x = \frac{1}{4}\Big(\frac{1}{3}e^{3x} - e^{-x}\Big) + C_1 \\
B(x) &= -\frac{1}{2}\int e^{4x}\,e^{-x}\,\cosh(2x) \,\mathrm{d}x = -\frac{1}{4}\int \Big(e^{5x} + e^{x}\Big) \,\mathrm{d}x = -\frac{1}{4}\Big(\frac{1}{5}e^{5x} + e^{x}\Big) + C_2
```
wher $C_1,\, C_2$ are constants.  This means the final solution is given by:
```{math}
y &= \Big(\frac{1}{12}e^{3x} - \frac{1}{4}e^{-x}\Big)e^{-x} - \Big(\frac{1}{20}e^{5x} - \frac{1}{4}e^{x}\Big)e^{-3x} + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big) \\
&= \frac{1}{12}e^{2x} - \frac{1}{4}e^{-2x} - \frac{1}{20}e^{2x} - \frac{1}{4}e^{-2x} + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big)\\
&= \frac{1}{60}\Big(2e^{2x} - 30e^{-2x} \Big) + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big)
```
Given the initial conditions, we find that:
```{math}
y(0) &= \frac{-28}{60} + \Big(C_1 + C_2\Big) = -\frac{7}{15} \Rightarrow C_1 + C_2 = 0\\
y'(x) &= \frac{1}{60}\Big(4e^{2x} + 60e^{-2x} \Big) + \Big(-C_1\,e^{-x} -3 C_2\,e^{-3x}\Big)\\
y'(0) &= \frac{64}{60} + \Big(-C_1 - 3C_2\Big) = \frac{1}{15} \Rightarrow -C_1 - 3C_2 = -1
```
which we can solve as $C_1 = 1/2,\, C_2 = -1/2$, which gives final solutions as:
```{math}
y(x) = \frac{1}{30}\Big(e^{2x} - 15e^{-2x} +15e^{-x} - 15 \,e^{-3x}\Big)
```
which we can check gives the right answer as:
```{math}
y(x) &= \frac{1}{30}\Big(e^{2x} - 15e^{-2x} +15e^{-x} - 15 \,e^{-3x}\Big)\\
y'(x) &= \frac{1}{30}\Big(2e^{2x} + 30e^{-2x} - 15e^{-x} + 45 \,e^{-3x}\Big)\\
y''(x) &= \frac{1}{30}\Big(4e^{2x} - 60e^{-2x} + 15e^{-x} - 135 \,e^{-3x}\Big) \\
\Rightarrow y'' + 4y' + 3y &= \frac{1}{30}\Big[(4+8+3)e^{2x} + (-60 + 120 -45) e^{-2x} \\
&+ (15-60+45)e^{-x} + (-135+180-45)\,e^{-3x}\Big] \\
&= \frac{1}{30}\Big(15e^{2x} + 15 e^{-2x}\Big) = \cosh(2x)
```
and so the solutions are correct!
````
## The General Case

Let us solve the ODE:

```{math}
a_n(x) y^{(n)} + a_{n-1}(x) y^{(n-1)} + \dots + a_1(x) y' + a_0(x) y = f(x)
```

where the coefficients $ a_i(x) $ may or may not be functions of $ x $. First, assume that the complementary solution of the homogeneous equation:

```{math}
a_n(x) y^{(n)} + a_{n-1}(x) y^{(n-1)} + \dots + a_1(x) y' + a_0(x) y = 0
```

is known and is represented as:

```{math}
y_c(x) = c_1 y_1(x) + c_2 y_2(x) + \dots + c_n y_n(x)
```

where $ c_i $ are constants and $ y_i(x) $ are known linearly independent functions.

We now consider a particular solution of the inhomogeneous equation in the form:

```{math}
y_p(x) = k_1(x) y_1(x) + k_2(x) y_2(x) + \dots + k_n(x) y_n(x)
```

where the coefficients $ k_i(x) $ are, in general, functions of $ x $. These functions can be determined by imposing $ n $ non-equivalent conditions. The ODE itself gives one of these conditions. How to choose the others?




#### Example: $ n = 2 $

Consider the equation:

```{math}
a_2(x) y'' + a_1(x) y' + a_0(x) y = f(x)
```

Assume that the solutions of the corresponding homogeneous equation $ y_1(x) $ and $ y_2(x) $ are known. Then:

```{math}
y_c(x) = c_1 y_1(x) + c_2 y_2(x)
```

is the complementary function. We now seek a particular solution in the form:

```{math}
y_p(x) = k_1(x) y_1(x) + k_2(x) y_2(x)
```

Substitute $ y_p(x) $ into the original equation:

```{math}
f(x) = a_0 (k_1 y_1 + k_2 y_2) + a_1 (k_1' y_1 + k_2' y_2 + k_1 y_1' + k_2 y_2') + a_2 (k_1'' y_1 + k_2'' y_2 + k_1' y_1' + k_2' y_2')
```

If we impose the condition:

```{math}
k_1' y_1 + k_2' y_2 = 0
```

then the remaining terms must satisfy:
```{math}
f(x) = a_2 (k_1' y_1' + k_2' y_2')
```

This means that we have two simultaneous equations and tow unknowns $k_1(x)\,k_2(x)$ and we find that:

```{math}
k_1'(x) = -k_2'(x) \frac{y_2(x)}{y_1(x)}
```

This process continues until we obtain the functions $ k_1(x) $ and $ k_2(x) $.

