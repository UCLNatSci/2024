### Two Dimensional Flows and Phase Diagrams

One can describe the dynamics of a two-dimensional, continuous-time process by a pair of differential equations and initial conditions:

\[
\frac{dx}{dt} = f(x, y), \quad \quad (1)
\]

\[
\frac{dy}{dt} = g(x, y), \quad \quad (2)
\]

\[
x(0) = x_0, \; y(0) = y_0, \quad \quad (3)
\]

whose solution is a **pair of functions of time, \( x(t) \) and \( y(t) \)**.

This process is also described using the notation:

\[
\frac{dx_1}{dt} = f_1(x_1, x_2),
\]

\[
\frac{dx_2}{dt} = f_2(x_1, x_2),
\]

\[
x_1(0) = x_{01}, \; x_2(0) = x_{02}.
\]

In vector notation, these dynamics are described as:

\[
\begin{pmatrix} \frac{dx_1}{dt} \\ \frac{dx_2}{dt} \end{pmatrix} = \begin{pmatrix} f_1(x_1, x_2) \\ f_2(x_1, x_2) \end{pmatrix}, \quad \text{or}
\]

\[
\mathbf{x}^T = (x_1, x_2), \quad \mathbf{f}^T(\mathbf{x}) = (f_1(x_1, x_2), f_2(x_1, x_2)),
\]

\[
\frac{d\mathbf{x}}{dt} = \mathbf{f}(\mathbf{x}), \quad \mathbf{x}^T(0) = (x_{01}, x_{02}).
\]

where **"T"** indicates the transpose from a column vector to a row vector.

---

### Linear Systems

The simplest two-dimensional, continuous-time process is the second-order, linear homogeneous system with constant coefficients:

\[
\frac{dx_1}{dt} = a \cdot x_1 + b \cdot x_2,
\]

\[
\frac{dx_2}{dt} = c \cdot x_1 + d \cdot x_2.
\]

Let the matrix \( A \) be:

\[
A = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \quad \quad (4)
\]

and the column vectors \( \mathbf{x} \) and \( \frac{d\mathbf{x}}{dt} \) be:

\[
\mathbf{x}^T = (x_1, x_2),
\]

\[
\frac{d\mathbf{x}^T}{dt} = \begin{pmatrix} \frac{dx_1}{dt} \\ \frac{dx_2}{dt} \end{pmatrix}.
\]

The linear system has the form:

\[
\frac{d\mathbf{x}}{dt} = A \cdot \mathbf{x}. \quad \quad (5)
\]

---

The origin, **\( \mathbf{o}^T = (0, 0) \)**, is an equilibrium (fixed) point of **(5)** because **\( A \cdot \mathbf{o} = \mathbf{o} \)**. One can examine the behavior (stability) of the solution vector:

\[
\mathbf{x}^T(t) = (x_1(t), x_2(t)),
\]

near the origin, **\( \mathbf{o} \)**, by analyzing the eigenvalues and eigenvectors of \( A \).

Click [here](http://www.egwald.ca/linearalgebra/lineardifferentialequations.php#classification) for a detailed classification of the equilibrium point at the origin.

---

The general \( 2 \times 2 \) matrix, \( A \), has:

\[
p = \text{trace}(A) = a + d, \quad q = \det(A) = a \cdot d - b \cdot c.
\]

Its characteristic equation is:

\[
f(\mu) = \mu^2 - p \cdot \mu + q.
\]

Factoring this quadratic equation yields the pair of eigenvalues, **\( \mu_1 \) and \( \mu_2 \)**, where:

\[
\mu_1 = \frac{p + \sqrt{p^2 - 4q}}{2}, \quad \mu_2 = \frac{p - \sqrt{p^2 - 4q}}{2}.
\]

Moreover:

\[
p = \mu_1 + \mu_2, \quad q = \mu_1 \cdot \mu_2.
\]

Designate the discriminant of the characteristic equation by:

\[
d = \text{disc}(A) = p^2 - 4q.
\]

### Classification of Fixed Points for Linear Systems

The following diagram classifies the fixed points (critical points) of the linear system (5) according to the values of \( p = \text{trace}(A) \), \( q = \det(A) \), and \( d = \text{disc}(A) \). The parabola, \( p^2 - 4q = 0 \), is the locus of points \((p, q)\) for which \( d = 0 \).

![Stability Diagram](php_images/twodflows_1.php)

In the region of the \((q, p)\) plane enclosed by the parabola, \( d = p^2 - 4q < 0 \). Consequently, the eigenvalues \( \mu_1 \) and \( \mu_2 \) are complex numbers. If \( p \neq 0 \), complex eigenvalues result in spiral trajectories. If \( p = 0 \), eigenvalues are purely imaginary, and trajectories enclose the fixed point in ellipses or circles.

- **Unstable fixed point**: If \( p > 0 \) and \( q > 0 \), both eigenvalues have positive real parts, and the fixed point is unstable. If \( p > 0 \) and \( q = 0 \), one eigenvalue is positive, and the other is zero, resulting in unstable lines.
- **Stable fixed point**: If \( p < 0 \) and \( q > 0 \), both eigenvalues have negative real parts, and the fixed point is stable. If \( p < 0 \) and \( q = 0 \), one eigenvalue is negative, and the other is zero, resulting in stable lines.
- **Saddle point**: If \( q < 0 \), one eigenvalue is positive, and the other is negative, leading to saddle point trajectories.

Finally, if \( p = 0 \) and \( q = 0 \):
- If \( A \) is the zero matrix, every vector \( \mathbf{x} \) is an equilibrium point.
- If \( A \) is not the zero matrix, there is a line of equilibrium points through the eigenvector corresponding to one zero eigenvalue. Other trajectories are parallel to this line, running in opposite directions on either side of it.

![Equilibrium Line Stability Diagram](php_images/twodflows_equline_points.php)

---

### Nonlinear Systems

The general form of a two-dimensional nonlinear system is:

\[
\frac{dx}{dt} = f(x, y), \quad \quad (6)
\]

\[
\frac{dy}{dt} = g(x, y), \quad \quad (7)
\]

\[
x(t_0) = x_0, \; y(t_0) = y_0. \quad \quad (8)
\]

---

### Fixed Points

The fixed points of the nonlinear system are numbers \( x^* \) and \( y^* \) such that:

\[
f(x^*, y^*) = 0, \quad \quad (9)
\]

\[
g(x^*, y^*) = 0. \quad \quad (10)
\]

Fixed points occur where the locus of points of equations (9) and (10) intersect.

---

### Example: (Strogatz 151-152)

The nonlinear system with functions \( f \) and \( g \) given by:

\[
\frac{dx}{dt} = f(x, y) = -x + x^3,
\]

\[
\frac{dy}{dt} = g(x, y) = -2y,
\]

has fixed points that satisfy:

\[
f(x, y) = -x + x^3 = 0,
\]

\[
g(x, y) = -2y = 0.
\]

In the diagram below, the fixed points occur at the intersections of the lines \( x = -1 \), \( x = 0 \), and \( x = 1 \) with the line \( y = 0 \) (the \( x \)-axis). These lines are called **nullclines**.

![Fixed Points and Nullclines](php_images/twodflows_3.php)

The fixed points are:

\[
(x_1^*, y_1^*) = (0, 0), \quad (x_2^*, y_2^*) = (-1, 0), \quad (x_3^*, y_3^*) = (1, 0).
\]

---

### Linearized Stability

The dynamics of a nonlinear system near a fixed point can be analyzed by [linearizing the system](https://www.egwald.ca/nonlineardynamics/mathappendix.php#linearization) about the fixed point, \( (x^*, y^*) \).

---

### Jacobian Matrix

The [Jacobian matrix](https://www.egwald.ca/nonlineardynamics/mathappendix.php#nonlinearjacobian) of the nonlinear system described by equations (6) and (7) at the fixed point \( (x^*, y^*) \) is the matrix of partial derivatives of the functions \( f \) and \( g \), evaluated at \( (x^*, y^*) \):

\[
J(x^*, y^*) =
\begin{pmatrix}
f_x(x^*, y^*) & f_y(x^*, y^*) \\
g_x(x^*, y^*) & g_y(x^*, y^*)
\end{pmatrix}. \quad \quad (11)
\]

### Jacobian Matrix and Fixed Point Dynamics

The Jacobian matrix of constant coefficients, \( J \), is identified with the matrix \( A \) of linear systems. Near a fixed point \( (x^*, y^*) \), the dynamics of the nonlinear system are qualitatively similar to the dynamics of the linear system associated with the \( J(x^*, y^*) \) matrix, provided the eigenvalues of the \( J \) matrix have non-zero real parts. Fixed points with a \( J \) matrix such that \( \text{Re}(\mu_{1, 2}) \neq 0 \) are called **hyperbolic fixed points**. Otherwise, fixed points are **non-hyperbolic fixed points**, whose stabilities must be determined directly.

---

### Classification of Fixed Points for Nonlinear Systems

Let the Jacobian matrix \( J \) evaluated at a fixed point \( (x^*, y^*) \) be:

\[
J = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
\]

For this matrix \( J \):

\[
p = \text{trace}(J) = a + d, \quad q = \det(J) = ad - bc.
\]

Its characteristic equation is:

\[
f(\mu) = \mu^2 - p \mu + q
\]

Factoring this quadratic equation yields the pair of eigenvalues, **\( \mu_1 \) and \( \mu_2 \)**:

\[
\mu_1 = \frac{p + \sqrt{p^2 - 4q}}{2}, \quad \mu_2 = \frac{p - \sqrt{p^2 - 4q}}{2}.
\]

Moreover:

\[
p = \mu_1 + \mu_2, \quad q = \mu_1 \cdot \mu_2.
\]

---

### Topological Classification

- **Hyperbolic Fixed Points**:
  - **Repellers (Sources)**: Unstable when \( p > 0, \, q > 0 \), and \( \text{Re}(\mu_{1, 2}) > 0 \).
  - **Attractors (Sinks)**: Stable when \( p < 0, \, q > 0 \), and \( \text{Re}(\mu_{1, 2}) < 0 \).
  - **Saddle Points**: Unstable when \( q < 0 \), with \( \text{Re}(\mu_1) < 0 \) and \( \text{Re}(\mu_2) > 0 \).

- **Non-Hyperbolic Fixed Points**:
  - **Marginal Case 1**: \( p = 0, \, q > 0 \), with \( \text{Re}(\mu_{1, 2}) = 0 \).
  - **Marginal Case 2**: \( p \neq 0, \, q = 0 \), with \( \mu_1 = 0 \) or \( \mu_2 = 0 \).
  - **Marginal Case 3**: \( p = 0, \, q = 0 \), with \( \mu_1 = 0 \) and \( \mu_2 = 0 \).

The classifications for the fixed points of a nonlinear system are summarized in the following table:

| Fixed Point Type            | Conditions                         | Stability                  |
|-----------------------------|-------------------------------------|----------------------------|
| **Repellers (Sources)**     | \( p > 0, q > 0 \), \( \text{Re}(\mu_{1, 2}) > 0 \) | Unstable                   |
| **Attractors (Sinks)**      | \( p < 0, q > 0 \), \( \text{Re}(\mu_{1, 2}) < 0 \) | Stable                     |
| **Saddle Points**           | \( q < 0 \), \( \text{Re}(\mu_1) < 0, \text{Re}(\mu_2) > 0 \) | Unstable                   |
| **Marginal Case 1**         | \( p = 0, q > 0 \), \( \text{Re}(\mu_{1, 2}) = 0 \) | Indeterminate              |
| **Marginal Case 2**         | \( p \neq 0, q = 0 \), \( \mu_1 = 0 \) or \( \mu_2 = 0 \) | Indeterminate              |
| **Marginal Case 3**         | \( p = 0, q = 0 \), \( \mu_1 = 0, \mu_2 = 0 \)       | Indeterminate              |

The classifications for the fixed points of a nonlinear system are visualized in the following diagram:

![Nonlinear Stability Diagram](php_images/twodflows_4.php)

---

### Example: Stability Analysis

The Jacobian matrix for the system is:

\[
J(x, y) = \begin{pmatrix} -1 + 3x^2 & 0 \\ 0 & -2 \end{pmatrix}
\]

#### Stability at \( (x_1^*, y_1^*) = (0, 0) \):

\[
J(0, 0) = \begin{pmatrix} -1 & 0 \\ 0 & -2 \end{pmatrix}, \quad p = -3, \quad q = 2
\]

\[
d = p^2 - 4q = 1, \quad \mu_1 = -1, \quad \mu_2 = -2
\]

The point \( (0, 0) \) is a **hyperbolic fixed point**. The system has a **stable node (attractor)** at \( (0, 0) \).

#### Stability at \( (x_2^*, y_2^*) = (-1, 0) \):

\[
J(-1, 0) = \begin{pmatrix} 2 & 0 \\ 0 & -2 \end{pmatrix}, \quad p = 0, \quad q = -4
\]

\[
d = p^2 - 4q = 16, \quad \mu_1 = 2, \quad \mu_2 = -2
\]

The point \( (-1, 0) \) is a **hyperbolic fixed point**. The system has a **saddle point** at \( (-1, 0) \).

#### Stability at \( (x_3^*, y_3^*) = (1, 0) \):

\[
J(1, 0) = \begin{pmatrix} 2 & 0 \\ 0 & -2 \end{pmatrix}, \quad p = 0, \quad q = -4
\]

\[
d = p^2 - 4q = 16, \quad \mu_1 = 2, \quad \mu_2 = -2
\]

The point \( (1, 0) \) is a **hyperbolic fixed point**. The system has a **saddle point** at \( (1, 0) \).

---

### Direction Field and Phase Portrait

The stability analysis for this example is verified by the following direction field and phase portrait of the nonlinear system:

| Direction Field                             | Phase Portrait                             |
|--------------------------------------------|--------------------------------------------|
| ![Direction Field](php_images/twodflows_2_1.php) | ![Phase Portrait](php_images/twodflows_2.php) |

### Example: (Boyce and DiPrima 487-488)

The nonlinear system with functions \( f \) and \( g \) given by:

\[
\frac{dx}{dt} = f(x, y) = y,
\]

\[
\frac{dy}{dt} = g(x, y) = -9 \sin(x) - \frac{1}{5} y,
\]

has fixed points that satisfy:

\[
f(x, y) = y = 0,
\]

\[
g(x, y) = -9 \sin(x) - \frac{1}{5} y = 0.
\]

The fixed points of this nonlinear system occur at the intersections of the **x-nullcline**, \( y = 0 \), and the **y-nullcline**, \( y = -45 \sin(x) \), as displayed in the diagram below:

![Fixed Points and Nullclines](php_images/twodflows_5.php)

#### Fixed Points

The fixed points are:

\[
(x^*, y^*) = (n\pi, 0), \quad \text{for } n = \ldots, -2, -1, 0, 1, 2, \ldots
\]

---

### Jacobian Matrix

The Jacobian matrix for the example is:

\[
J(x^*, y^*) =
\begin{pmatrix}
0 & 1 \\
-9 \cos(x) & -\frac{1}{5}
\end{pmatrix}
\]

---

### Stability Analysis

#### \( n = 0 \) or \( n \) even:
- \( p = -0.2 < 0 \), \( q = 9 > 0 \).
- The fixed points are **hyperbolic attractors**.

#### \( n \) odd:
- \( p = -0.2 < 0 \), \( q = -9 < 0 \).
- The fixed points are **hyperbolic saddle points**.

---

### Phase Portrait

The following phase portrait of the nonlinear system verifies the stability analysis:

![Nonlinear Phase Portrait](php_images/twodflows_6.php)

---

### Basin of Attraction

The basin of attraction of an attracting fixed point is the set of all initial points whose solution trajectories lead to the fixed point. In the diagram below, the yellow region represents the **basin of attraction** of the hyperbolic attractor at the origin:

![Basin of Attraction](php_images/twodflows_6_1.png)

---

### Homoclinic Orbits

Solution trajectories that begin and terminate at the same fixed point are called **homoclinic orbits**. An example is shown below, with the homoclinic orbits in red:

![Homoclinic Orbits](php_images/twodflows_14.php)

This nonlinear system has functions \( f \) and \( g \):

\[
\frac{dx}{dt} = f(x, y) = y,
\]

\[
\frac{dy}{dt} = g(x, y) = x - x^3,
\]

with a saddle point at \( (0, 0) \), and centers at \( (-1, 0) \) and \( (1, 0) \).

---

### Heteroclinic Orbits

Solution trajectories that begin and terminate at different saddle points are called **heteroclinic orbits**. An example is shown below, with the heteroclinic orbits in red:

![Heteroclinic Orbits](php_images/twodflows_12_1.php)

This nonlinear system has functions \( f \) and \( g \):

\[
\frac{dx}{dt} = f(x, y) = y,
\]

\[
\frac{dy}{dt} = g(x, y) = -\sin(x),
\]

The fixed points are:

\[
(x^*, y^*) = (n\pi, 0), \quad \text{for } n = \ldots, -2, -1, 0, 1, 2, \ldots
\]

- \( n = 0 \) or \( n \) even: The fixed points are **centers**.
- \( n \) odd: The fixed points are **hyperbolic saddle points**.

---

### Physical Interpretation: The Oscillating Pendulum (Boyce and DiPrima 476-477)

An object of mass \( m \) is suspended from a point \( O \) by a rigid, weightless rod of length \( L \). The angle of the rod with the vertical is \( \theta \), with the counterclockwise direction as positive. The rod can swing or rotate about \( O \). The **gravitational force** is \( F = mg \), while the **damping force** opposing the motion is \( c \left| \frac{d\theta}{dt} \right| \), where \( c > 0 \). The tangential gravitational force is \( F_1 = -mg\sin(\theta) \).

![Oscillating Pendulum](php_images/twodflows_7.php)

With the damping force, the equation of motion is:

\[
mL^2 \frac{d^2\theta}{dt^2} = -cL \frac{d\theta}{dt} - mgL\sin(\theta),
\]

or equivalently:

\[
\frac{d^2\theta}{dt^2} + \frac{c}{mL} \frac{d\theta}{dt} + \frac{g}{L}\sin(\theta) = 0.
\]

Letting \( \gamma = \frac{c}{mL} \) and \( \omega^2 = \frac{g}{L} \), the equation becomes:

\[
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega^2 \sin(\theta) = 0.
\]

This system can be rewritten as a two-dimensional nonlinear system:

\[
\frac{dx}{dt} = y, \quad \frac{dy}{dt} = -\omega^2 \sin(x) - \gamma y.
\]

For \( \omega^2 = 9 \) and \( \gamma = \frac{1}{5} \), the relevant phase portrait is shown for \( x \) between \( -\pi \) and \( \pi \).

![Phase Portrait](php_images/twodflows_6.php)

---

### Oscillating Pendulum Dynamics

The next graphic displays the motion of the pendulum with \( \omega^2 = 9 \) and \( \gamma = \frac{1}{5} \), starting from a position slightly displaced from the vertical (\( x = -3.04159 \) radians, \( y = 0.010000 \) radians/second):

![Oscillating Pendulum Dynamics](php_images/pendulum.gif)

### Lotka–Volterra Model: Decreasing and Increasing Returns

The Lotka–Volterra model is sensitive to modifications in the differential equations describing the dynamics of the nonlinear system. The following system represents a perturbation of the original model:

\[
\frac{dx}{dt} = f(x, y) = 3x - 2xy,
\]

\[
\frac{dy}{dt} = g(x, y) = -3y + 2xy - e y^2,
\]

where the parameter \( e \) is either \( -2 < e < 0 \) (increasing returns) or \( e > 0 \) (decreasing returns). The parameter \( e \) measures the returns available to the entity represented by \( y \).

---

### Fixed Points

The fixed points are:

\[
(x_1^*, y_1^*) = (0, 0),
\]

\[
(x_2^*, y_2^*) = \left( \frac{3}{2} + \frac{3}{4}e, \frac{3}{2} \right),
\]

where \( x_2^* > 0 \) requires \( e > -2 \).

---

### Jacobian Matrix

The Jacobian matrix for the system is:

\[
J(x^*, y^*) =
\begin{pmatrix}
3 - 2y & -2x \\
2y & -3 + 2x - 2ey
\end{pmatrix}
\]

---

### Stability Analysis

#### At \( (x_1^*, y_1^*) = (0, 0) \):
- \( p = \text{trace}(J) = 0 \),
- \( q = \det(J) = -9 \).

The fixed point is a **hyperbolic saddle point**.

#### At \( (x_2^*, y_2^*) = \left( \frac{3}{2} + \frac{3}{4}e, \frac{3}{2} \right) \):
- \( p = \text{trace}(J) = -\frac{3}{2}e \),
- \( q = \det(J) = \frac{9}{2}e + 9 \).

- For \( e > 0 \):
  - \( p < 0 \), \( q > 0 \),
  - The fixed point is a **hyperbolic attractor**.

- For \( -2 < e < 0 \):
  - \( p > 0 \), \( q > 0 \),
  - The fixed point is a **hyperbolic repeller**.

---

### Phase Portraits

The phase portraits below illustrate the behavior for both decreasing (\( e > 0 \)) and increasing (\( e < 0 \)) returns:

| ![Decreasing Returns](php_images/twodflows_9.php) | ![Increasing Returns](php_images/twodflows_9.php?e=-.25&nobs=1&sobs=0&lit=Increasing%20Returns) |
|:-------------------------------------------------:|:------------------------------------------------------------------------------------------:|
| \( e = 0.25 > 0 \)                                | \( e = -0.25 < 0 \)                                                                        |

