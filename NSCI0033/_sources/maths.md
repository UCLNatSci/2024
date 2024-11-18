# Mathematical Preliminaries

## Ordinary Differential Equations
One area we need to confident in is solving second-order ordinary differential equations (ODEs), both homogeneous and inhomogeneous.

### Second-Order Homogeneous ODEs

A second-order homogeneous ODE has the form:
```{math}
a x'' + b x' + c x = 0
```
where $ a $, $ b $, and $ c $ are constants.

*Steps to Solve:*
1. Write the Characteristic Equation:
   Substitute $ x = e^{\lambda t} $ into the equation, which leads to the characteristic equation:
   ```{math}
   a \lambda^2 + b \lambda + c = 0
   ```

2. Solve for $\lambda$:
   Use the quadratic formula to find the roots, $\lambda_1$ and $\lambda_2$:
   ```{math}
   \lambda = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
   ```

3. Determine the Solution Based on the Roots:
   - Distinct Real Roots ($\lambda_1 \neq \lambda_2$): The solution is
     ```{math}
     x(t) = C_1 e^{\lambda_1 t} + C_2 e^{\lambda_2 t}
     ```
   - Repeated Real Roots ($\lambda_1 = \lambda_2$): The solution is
     ```{math}
     x(t) = (C_1 + C_2 t) e^{\lambda t}
     ```
   - Complex Roots ($\lambda = \alpha \pm \beta i$): The solution is
     ```{math}
     x(t) = e^{\alpha t} (C_1 \cos(\beta t) + C_2 \sin(\beta t))
     ```

*Example*
For $ x'' - 5x' + 6x = 0 $:
   - Characteristic equation: $\lambda^2 - 5\lambda + 6 = 0$
   - Roots: $\lambda_1 = 2$, $\lambda_2 = 3$
   - Solution: $ x(t) = C_1 e^{2t} + C_2 e^{3t} $

### Second-Order Inhomogeneous ODEs

A second-order inhomogeneous ODE has the form:
```{math}
a x'' + b x' + c x = g(t)
```
where $ g(t) $ is a non-zero function, known as the forcing function or inhomogeneous term.

*Steps to Solve:*
1. Find the Complementary Solution ($x_c$):
   Solve the associated homogeneous equation (as above), which gives the complementary solution $ x_c $.

2. Find the Particular Solution ($x_p$):
   Use an appropriate method to find a particular solution $ x_p $ that satisfies the full equation.

   Methods for Finding $x_p$:
   - Method of Undetermined Coefficients:
     If $ g(t) $ is a polynomial, exponential, sine, or cosine function, guess a form for $ x_p $ and determine the coefficients by substitution.
   - Variation of Parameters:
     If $ g(t) $ is more complicated, use variation of parameters to express $ x_p $ in terms of integrals involving $ x_c $.

3. Write the General Solution:
   The general solution to the inhomogeneous ODE is the sum of the complementary and particular solutions:
   ```{math}
   x(t) = x_c(t) + x_p(t)
   ```
### Forcing Terms and Particular Solutions

The method of undetermined coefficients is often used to find $ x_p(t) $ based on the type of forcing function $ g(t) $. Here are common types of forcing terms and the typical forms to try for $ x_p $.

*Polynomial Forcing Term*
If $ g(t) = P_n(t) $, a polynomial of degree $ n $ (e.g., $ g(t) = t^2 + 3t + 4 $), then assume
```{math}
x_p(t) = A_n t^n + A_{n-1} t^{n-1} + \dots + A_0
```
where $ A_n, A_{n-1}, \dots, A_0 $ are constants to be determined.

*Exponential Forcing Term*
If $ g(t) = e^{\alpha t} $:
   - If $ e^{\alpha t} $ is **not** part of $ x_c $, assume
     ```{math}
     x_p(t) = A e^{\alpha t}
     ```
   - If $ e^{\alpha t} $ **is** part of $ x_c $, multiply by $ t $:
     ```{math}
     x_p(t) = A t e^{\alpha t}
     ```
   - If $ e^{\alpha t} $ appears in $ x_c $ with multiplicity $ m $, multiply by $ t^m $:
     ```{math}
     x_p(t) = A t^m e^{\alpha t}
     ```

*Trigonometric Forcing Term*
If $ g(t) = \cos(\beta t) $ or $ g(t) = \sin(\beta t) $:
   - If neither $ \cos(\beta t) $ nor $ \sin(\beta t) $ is part of $ x_c $, assume
     ```{math}
     x_p(t) = A \cos(\beta t) + B \sin(\beta t)
     ```
   - If $ \cos(\beta t) $ or $ \sin(\beta t) $ is part of $ x_c $, multiply by $ t $:
     ```{math}
     x_p(t) = (A t) \cos(\beta t) + (B t) \sin(\beta t)
     ```


*Example*
For $ x'' - 5x' + 6x = e^{3t} $:
   - Complementary Solution $ x_c $: Solve $ x'' - 5x' + 6x = 0 $ (as done in the homogeneous example above), giving $ x_c = C_1 e^{2t} + C_2 e^{3t} $.
   - Particular Solution $ x_p $: Try $ x_p = A t e^{3t} $ (since $ e^{3t} $ is part of $ x_c $), substitute and solve for $ A $.
   - General Solution: Combine both solutions:
     ```{math}
     x(t) = x_c(t) + x_p(t) = C_1 e^{2t} + C_2 e^{3t} + A t e^{3t}
     ```
## Coordinate Systems

### Spherical Coordinates Overview

In spherical coordinates, a point in three-dimensional space is represented by three values: $ r $, $ \theta $, and $ \phi $, where:
- $ r $: the radial distance from the origin to the point.
- $ \theta $: the polar angle, measured from the positive $ z $-axis.
- $ \phi $: the azimuthal angle, measured from the positive $ x $-axis in the $ x $-$ y $ plane.

The coordinates $ (r, \theta, \phi) $ provide a way to describe positions in terms of distance and angles rather than Cartesian $ (x, y, z) $ coordinates.

### Coordinate Definitions and Conversion

#### Definition of Spherical Coordinates:
- **Radial distance** $ r $: The distance from the origin to the point.
- **Polar angle** $ \theta $: The angle between the point and the positive $ z $-axis.
- **Azimuthal angle** $ \phi $: The angle between the projection of the point onto the $ x $-$ y $ plane and the positive $ x $-axis.

#### Conversions from Cartesian to Spherical:
Given a point in Cartesian coordinates $ (x, y, z) $:
```{math}
r = \sqrt{x^2 + y^2 + z^2}
```
```{math}
\theta = \arccos\left(\frac{z}{r}\right)
```
```{math}
\phi = \arctan\left(\frac{y}{x}\right)
```

#### Conversions from Spherical to Cartesian:
Given a point in spherical coordinates $ (r, \theta, \phi) $:
```{math}
x = r \sin \theta \cos \phi
```
```{math}
y = r \sin \theta \sin \phi
```
```{math}
z = r \cos \theta
```

Here are notes on the unit vectors in the spherical coordinate system, using the physicist's convention.

### Unit Vectors in Spherical Coordinates

In spherical coordinates, the position of a point is given by the coordinates $ (r, \theta, \phi) $. The associated unit vectors $ \hat{r} $, $ \hat{\theta} $, and $ \hat{\phi} $ point in the directions of increasing $ r $, $ \theta $, and $ \phi $, respectively.

#### Radial Unit Vector $ \hat{r} $
- Points directly away from the origin, in the direction of increasing $ r $.
- In Cartesian coordinates, it is given by:
  ```{math}
  \hat{r} = \sin \theta \cos \phi \, \hat{x} + \sin \theta \sin \phi \, \hat{y} + \cos \theta \, \hat{z}
  ```

#### Polar Unit Vector $ \hat{\theta} $
- Points in the direction of increasing $ \theta $, which is perpendicular to $ \hat{r} $.
- Lies in the plane defined by $ r $ and $ z $ (or $ r $ and $ \theta $), pointing downward from the $ z $-axis for increasing $ \theta $.
- In Cartesian coordinates, it is given by:
  ```{math}
  \hat{\theta} = \cos \theta \cos \phi \, \hat{x} + \cos \theta \sin \phi \, \hat{y} - \sin \theta \, \hat{z}
  ```

#### Azimuthal Unit Vector $ \hat{\phi} $
- Points in the direction of increasing $ \phi $, perpendicular to both $ \hat{r} $ and $ \hat{\theta} $.
- Lies in the $ x $-$ y $ plane, tangent to the circle of constant $ r $ and $ \theta $ and oriented counterclockwise when looking down the $ z $-axis.
- In Cartesian coordinates, it is given by:
  ```{math}
  \hat{\phi} = -\sin \phi \, \hat{x} + \cos \phi \, \hat{y}
  ```

### Non-Constant Nature of Spherical Unit Vectors

Unlike Cartesian unit vectors, the spherical unit vectors $ \hat{r} $, $ \hat{\theta} $, and $ \hat{\phi} $ vary with position, meaning they depend on $ \theta $ and $ \phi $:
- $ \hat{r} $, $ \hat{\theta} $, and $ \hat{\phi} $ change direction as the point moves, even if $ r $, $ \theta $, or $ \phi $ remain constant.

###  Derivatives of Spherical Unit Vectors

Because the unit vectors change with $ \theta $ and $ \phi $, their derivatives are non-zero, which is important in computing derivatives of vector fields.

#### Derivatives with Respect to $ \theta $
```{math}
\frac{\partial \hat{r}}{\partial \theta} = \hat{\theta}
```
```{math}
\frac{\partial \hat{\theta}}{\partial \theta} = -\hat{r}
```
```{math}
\frac{\partial \hat{\phi}}{\partial \theta} = 0
```

#### Derivatives with Respect to $ \phi $
```{math}
\frac{\partial \hat{r}}{\partial \phi} = \sin \theta \, \hat{\phi}
```
```{math}
\frac{\partial \hat{\theta}}{\partial \phi} = \cos \theta \, \hat{\phi}
```
```{math}
\frac{\partial \hat{\phi}}{\partial \phi} = -\sin \theta \, \hat{r} - \cos \theta \, \hat{\theta}
```

### Expressing a Vector in Spherical Coordinates

A vector $ \vec{A} $ in spherical coordinates can be expressed as:
```{math}
\vec{A} = A_r \hat{r} + A_\theta \hat{\theta} + A_\phi \hat{\phi}
```
where $ A_r $, $ A_\theta $, and $ A_\phi $ are the components of $ \vec{A} $ in the directions of $ \hat{r} $, $ \hat{\theta} $, and $ \hat{\phi} $, respectively.

- $ A_r $: the component along $ \hat{r} $.
- $ A_\theta $: the component along $ \hat{\theta} $, associated with changes in $ \theta $.
- $ A_\phi $: the component along $ \hat{\phi} $, associated with changes in $ \phi $.

### Velocity Vector in Spherical Coordinates

To derive the velocity vector in spherical coordinates, we start with a position vector expressed in terms of spherical coordinates and then differentiate it with respect to time. Here are the steps:

#### Position Vector in Spherical Coordinates

In spherical coordinates, the position vector $ \vec{r} $ is given by:
```{math}
\vec{r} = r \hat{r}
```
where $ r $ is the radial distance from the origin to the point.

#### Differentiating the Position Vector

The velocity vector $ \vec{v} $ is the time derivative of the position vector:
```{math}
\vec{v} = \frac{\mathrm{d}\vec{r}}{\mathrm{d}t} = \frac{\mathrm{d}}{\mathrm{d}t} (r \hat{r})
```
Applying the product rule:
```{math}
\vec{v} = \frac{\mathrm{d}r}{\mathrm{d}t} \hat{r} + r \frac{\mathrm{d}\hat{r}}{\mathrm{d}t}
```
The term $ \frac{\mathrm{d}r}{\mathrm{d}t} $ is simply the radial component of the velocity, which we can call $ \dot{r} $ (where $ \dot{r} $ denotes the time derivative of $ r $). So:
```{math}
\vec{v} = \dot{r} \hat{r} + r \frac{\mathrm{d}\hat{r}}{\mathrm{d}t}
```

#### Finding $ \frac{\mathrm{d}\hat{r}}{\mathrm{d}t} $

To evaluate $ \frac{\mathrm{d}\hat{r}}{\mathrm{d}t} $, we need to express it in terms of changes in $ \theta $ and $ \phi $, since $ \hat{r} $ depends on these angles. Using the chain rule:
```{math}
\frac{\mathrm{d}\hat{r}}{\mathrm{d}t} = \frac{\partial \hat{r}}{\partial \theta} \frac{\mathrm{d}\theta}{\mathrm{d}t} + \frac{\partial \hat{r}}{\partial \phi} \frac{\mathrm{d}\phi}{\mathrm{d}t}
```
From the spherical coordinate unit vector derivatives, we have:
```{math}
\frac{\partial \hat{r}}{\partial \theta} = \hat{\theta} \quad \text{and} \quad \frac{\partial \hat{r}}{\partial \phi} = \sin \theta \, \hat{\phi}
```
Substituting these:
```{math}
\frac{\mathrm{d}\hat{r}}{\mathrm{d}t} = \hat{\theta} \frac{\mathrm{d}\theta}{\mathrm{d}t} + \sin \theta \, \hat{\phi} \frac{\mathrm{d}\phi}{\mathrm{d}t}
```
Define $ \dot{\theta} = \frac{\mathrm{d}\theta}{\mathrm{d}t} $ and $ \dot{\phi} = \frac{\mathrm{d}\phi}{\mathrm{d}t} $, which are the rates of change of the angles. Then:
```{math}
\frac{\mathrm{d}\hat{r}}{\mathrm{d}t} = \dot{\theta} \, \hat{\theta} + \sin \theta \, \dot{\phi} \, \hat{\phi}
```

####  Substitute Back into the Velocity Expression

Substituting $ \frac{\mathrm{d}\hat{r}}{\mathrm{d}t} $ back into the expression for $ \vec{v} $:
```{math}
\vec{v} = \dot{r} \hat{r} + r (\dot{\theta} \, \hat{\theta} + \sin \theta \, \dot{\phi} \, \hat{\phi})
```
Distribute $ r $ to get:
```{math}
\vec{v} = \dot{r} \hat{r} + r \dot{\theta} \, \hat{\theta} + r \sin \theta \, \dot{\phi} \, \hat{\phi}
```

#### Final Expression for the Velocity Vector

Thus, the velocity vector $ \vec{v} $ in spherical coordinates is:
```{math}
\vec{v} = \dot{r} \hat{r} + r \dot{\theta} \, \hat{\theta} + r \sin \theta \, \dot{\phi} \, \hat{\phi}
```
where:
- $ \dot{r} = \frac{\mathrm{d}r}{\mathrm{d}t} $ is the radial component of velocity.
- $ r \dot{\theta} $ is the polar component of velocity.
- $ r \sin \theta \, \dot{\phi} $ is the azimuthal component of velocity.

This breakdown of the velocity vector is essential in many physical applications, such as analyzing the motion of particles in fields with spherical symmetry.



### Volume Element in Spherical Coordinates

In spherical coordinates, the volume element $ \mathrm{d}V $ is:
```{math}
\mathrm{d}V = r^2 \sin \theta \, \mathrm{d}r \, \mathrm{d}\theta \, \mathrm{d}\phi
```
This expression is useful when setting up integrals in spherical coordinates, especially in problems with spherical symmetry.

### Surface Elements in Spherical Coordinates

The surface elements on a sphere of radius $ r $ are often useful in physical applications:
- *Radial surface element* (on a sphere of radius $ r $):
  ```{math}
  \mathrm{d}A = r^2 \sin \theta \, \mathrm{d}\theta \, \mathrm{d}\phi
  ```
- *Polar surface element* (on a cone of constant $ \theta $):
  ```{math}
  \mathrm{d}A = r \sin \theta \, \mathrm{d}r \, \mathrm{d}\phi
  ```
- **Azimuthal surface element** (on a plane of constant $ \phi $):
  ```{math}
  \mathrm{d}A = r \, \mathrm{d}r \, \mathrm{d}\theta
  ```

### Gradient, Divergence, and Curl in Spherical Coordinates

#### Gradient
The gradient of a scalar field $ f(r, \theta, \phi) $ in spherical coordinates is:
```{math}
\nabla f = \frac{\partial f}{\partial r} \hat{r} + \frac{1}{r} \frac{\partial f}{\partial \theta} \hat{\theta} + \frac{1}{r \sin \theta} \frac{\partial f}{\partial \phi} \hat{\phi}
```

#### Divergence
The divergence of a vector field $ \vec{A} = A_r \hat{r} + A_\theta \hat{\theta} + A_\phi \hat{\phi} $ in spherical coordinates is:
```{math}
\nabla \cdot \vec{A} = \frac{1}{r^2} \frac{\partial}{\partial r} (r^2 A_r) + \frac{1}{r \sin \theta} \frac{\partial}{\partial \theta} (\sin \theta A_\theta) + \frac{1}{r \sin \theta} \frac{\partial A_\phi}{\partial \phi}
```

#### Curl
The curl of a vector field $ \vec{A} = A_r \hat{r} + A_\theta \hat{\theta} + A_\phi \hat{\phi} $ in spherical coordinates is:
```{math}
\nabla \times \vec{A} = \frac{1}{r \sin \theta} \left( \frac{\partial}{\partial \theta} (A_\phi \sin \theta) - \frac{\partial A_\theta}{\partial \phi} \right) \hat{r} + \frac{1}{r} \left( \frac{1}{\sin \theta} \frac{\partial A_r}{\partial \phi} - \frac{\partial}{\partial r} (r A_\phi) \right) \hat{\theta} + \frac{1}{r} \left( \frac{\partial}{\partial r} (r A_\theta) - \frac{\partial A_r}{\partial \theta} \right) \hat{\phi}
```




## Flux
Lets think about a house pipe, as depicted in {numref}`HosePipe` with water of density $\rho$, moving through a hose pipe of cross sectional 
area $A$ with a velocity of $\bf v$,
```{figure} ./figures/HoseFlux2.png
---
name: HosePipe
---
Flux of water passing through a hose pipe, with cross sectional area $A$
```
We can see that the cross sectional area is perpendicular to the velocity in this case, so we define:
```{math}
{\bf A} = A\,\hat{\bf n}
```
where $\hat{\bf n}$ is a unit vector normal to the surface area $A$.  We can find the rate of mass flowing through the pipe, which is sometimes 
called the <b>Mass Current</b> $I_m$ of the water flow, with units of $[\textrm{mass}][\textrm{time}]^{-1}$:
```{math}
I_m = \rho {\bf v} \cdot {\bf A}
```
and so we can find the <b>Mass Flux</b> $\Phi_m$, with units of $[\textrm{mass}][\textrm{length}]^{-2}[\textrm{time}]^{-1}$
```{math}
\Phi_m = \rho {\bf v}
```
If we increase or decrease the size of the hose, we can figure out the flow rate of the resulting water flow using this mass flux, as we illustrate 
in {numref}`Flux`. 
```{figure} ./figures/flux.png
---
name: Flux
---
<b>Left panel,</b> flux changes with increase to flow; 
<b>Middle panel</b>, flux changes with increase to area; 
<b>Right panel</b>, distorting the area can change the flux through it.
```
If we increase the size of $A$, the resulting mass current is smaller (water would flow slower out of hose) and likewise if we 
decrease $A$, then the mass current would be larger (water would flower faster out of the hose).  We notice that in this hose pipe example, the water 
flows the cross sectional area $A$ which is perpendicular to the direction of fluid flow, this may not necessarily be true in other systems. 
```{figure} ./figures/Flux3DdA.png
---
name: flux3DdA
---
Depiction of some 3D surface area $A$ decomposed into area elements $\mathrm{d} A$, with some vector field $\bf F$ shown in the red. The flux of the vector 
field is shown in blue as the components of $\bf F$ in the direction of the normal vectors $\bf n$ in $\mathrm{d} A$.
```
Consider the system shown in {numref}`flux3DdA`, where some vector field $\bf F(x)$ is passing through a surface with area $A$.  We can split up 
the area into smaller surface elements $\mathrm{d} A$ and consider the flux $\Phi$ passing through each of these.  In each surface element, 
we can define a surface normal $\bf n$ and then just resolve $\bf F$ into $\bf F_\parallel$ and $\bf F_\perp$ components, as shown in {numref}`flux3D`. 
```{figure} ./figures/flux3D.png
---
name: flux3D
---
A vector $\bf F$ passes through some surface (depicted in the green), <b>Left panel,</b> the situation for a flat surface, <b>Right panel</b> the situation for a curved surface.
Notice that in each case the setting up a surface normal vector at each position and resolving the vector $\bf F$ into parallel $\bf F_\parallel$ and 
perpendicular $\bf F_\perp$ components. 
```
Thus we will have the flux for each surface element $\mathrm{d} A$ as:
```{math}
\mathrm{d} \Phi = {\bf F} \cdot {\bf n}
```
and so the total flux will be described by summing up all of these components over the surface, which we can do with a closed surface integral:
```{math}
\Phi = \iint_A \left({\bf F} \cdot {\bf n}\right) \,\mathrm{d} A = \iint_A {\bf F} \cdot \mathrm{d} {\bf A}
```
## Divergence and Stokes Theorems
- For a vector field $\bf F$ within some volume $V$, bounded by a surface area $A$ with surface normal $\bf n$, as depicted in 
{numref}`divergencetheorem`, then we can relate:
```{math}
\iiint _{V}\left(\nabla\cdot {\bf F} \right)\,\mathrm{d} V = \iint_A {\bf F} \cdot \mathrm{d} {\bf A}
```
```{figure} ./figures/DivergenceTheorem2.png
---
name: divergencetheorem
---
A pictorial look at flux of a vector field $\bf F$ crossing a bounding area $A$ which can be related to a divergence $\nabla \cdot {\bf F}$ within the volume $V$.
```

- For a vector field $\bf F$ within boundary $\ell$ of a surface area $A$ with surface normal $\bf n$, as depicted in {numref}`stokestheorem`, then we can relate:
```{math}
\int _{\ell}\,{\bf F}\cdot\mathrm{d} \ell = \iint_A (\nabla \times {\bf F}) \cdot \mathrm{d}  {\bf A}
```
```{figure} ./figures/StokesTheorem.png
---
name: stokestheorem
---
A pictorial look at a vector ${\bf F}$ on the boundary $\ell$ which can be related to the curl $\nabla \times {\bf F}$ within the area $A$.
```

##  Helmholtz Decomposition
The Helmholtz decomposition, shown in Equation {eq}`HelmholtzDecomp` states that a suitably smooth vector field $\bf F$ can, in general, be decomposed 
into two components:
```{math}
:label: HelmholtzDecomp
{\bf F} = -\nabla \phi + \nabla \times {\bf A}
```
where $\phi$ is a scalar field, also called the <b>Scalar Potential</b>, and $\bf A$ is a vector field, also called the <b>Vector Potential</b>.
