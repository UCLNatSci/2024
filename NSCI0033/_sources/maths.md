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


## Cylindrical Coordinates

An illustration of cylindrical coordinates and associated, locally defined unit vectors is shown in {numref}`fig:cylcoords`. The three coordinates are: $ R $ (cylindrical radial distance), which is the perpendicular distance of the point of interest from some reference axis (here chosen to be the Cartesian $ z $-axis); $ \phi $, the azimuthal angle between the $ x $-axis and the projection of the position vector onto the $ xy $-plane; and $ z $, which is identical to the usual Cartesian $ z $-coordinate.

```{figure} /classicalmechanics/Figs/cylcoords.png
---
name: fig:cylcoords
---
Illustration of cylindrical coordinates and unit vectors (from the book by Fowles and Cassiday).
```

Now, the position vector of any moving particle with respect to the origin can be expressed, using the corresponding (locally defined) unit vectors in this system, as:

```{math}
\mathbf{r}(t) = R\,\mathbf{e_R} + z\,\mathbf{e_z}.
```

The unit vector $ \mathbf{e_R} $ will change direction as the particle moves, since it is parallel to the direction from the closest point on the $ z $-axis to the position of the particle itself. On the other hand, the unit vector $ \mathbf{e_z} $ will not change with the particle motion.

We can thus use similar calculations as were done in the previous section to prove that:

```{math}
\frac{\mathrm{d}\mathbf{e_R}}{\mathrm{d}t} = \dot{\phi}\,\mathbf{e_{\phi}},
```

where we have used the 'overdot' notation to denote time derivative, $ \dot{\phi} = \frac{\mathrm{d}\phi}{\mathrm{d}t} $.

Using this same notation now to calculate the velocity in cylindrical coordinates:

```{math}
\dot{\mathbf{r}} = \dot{R}\,\mathbf{e_R} + R\,\frac{\mathrm{d}\mathbf{e_R}}{\mathrm{d}t} + \dot{z}\,\mathbf{e_z}
            = \dot{R}\,\mathbf{e_R} + R\,\dot{\phi}\,\mathbf{e_{\phi}} + \dot{z}\,\mathbf{e_z}.
```

The cylindrical components of the above equation represent the cylindrical radial velocity, the azimuthal velocity (equivalent to a local rotational component of motion about the $ z $-axis), and the axial velocity.

Differentiating the azimuthal unit vector $ \mathbf{e_{\phi}} $ with respect to time, using similar reasoning as for equation $ \frac{\mathrm{d}\mathbf{e_{\phi}}}{\mathrm{d}t} $, gives us:

```{math}
\mathbf{e_{\phi}}'(t) = -\dot{\phi}\,\mathbf{e_R}.
```

If we now use this result and the equation for $ \frac{\mathrm{d}\mathbf{e_R}}{\mathrm{d}t} $ when we differentiate velocity (equation $ \dot{\mathbf{r}} $) to get acceleration, we arrive at (proof is left for the reader as an exercise):

```{math}
\ddot{\mathbf{r}} = (\ddot{R}-R\,\dot{\phi}^2)\,\mathbf{e_R} + (R\,\ddot{\phi} + 2\dot{R}\dot{\phi})\,\mathbf{e_{\phi}} + \ddot{z}\,\mathbf{e_z}.
```

We can identify the term $ -R\,\dot{\phi}^2\,\mathbf{e_R} $ in this expression as the centripetal acceleration associated with that component of the motion which represents rotation about the $ z $-axis.

## Spherical Coordinates

In this section, we repeat the same general strategy for deriving formulas for velocity and acceleration in the <mark>spherical polar coordinates</mark> for three-dimensional space. We remind ourselves, from the previous section, that this strategy involves expressing the local unit vectors of our coordinate system in a form that is relatively straightforward to differentiate — the Cartesian form of these vectors is a good choice here. Differentiation then allows us to express the time derivatives of each of our local unit vectors in terms of other unit vectors in the triad, which in turn allows us to make final derivations of the spherical polar implementations of velocity and acceleration of a moving particle. Note that the vectors which we obtain for a particle's velocity and acceleration ultimately must have the same final magnitude and direction in all coordinate systems. However, the different orientations of unit coordinate vectors in these different systems mean that the individual <mark>components</mark> of acceleration and velocity are indeed dependent on our choice of coordinates.

```{figure} /classicalmechanics/Figs/spherecoords.png
---
name: fig:spherecoords
---
Illustration of spherical coordinates and unit vectors (from the book by Fowles and Cassiday).
```

With these concepts in mind, we now turn to the spherical polar coordinate system, whose position coordinates and local unit vectors are illustrated in {numref}`fig:spherecoords`. We see that in this system, the three quantities which now specify a particle's position are: $r$, its radial distance from the origin; $\theta$, the polar angle which is the angle between the $z$-Cartesian axis and the position vector of the particle; $\phi$, the azimuthal angle, which is the angle between the $x$-axis and the projection of the position vector onto the $xy$-plane. If we express these unit vectors in the Cartesian components, we obtain:

```{math}
\mathbf{e_{r}} &= \sin\theta \cos\phi\,\mathbf{e_x} + \sin\theta \sin\phi\,\mathbf{e_y} + \cos\theta\,\mathbf{e_z}
\\
\mathbf{e_{\theta}} &= \cos\theta \cos\phi\,\mathbf{e_x} + \cos\theta \sin\phi\,\mathbf{e_y} - \sin\theta\,\mathbf{e_z}
\\
\mathbf{e_{\phi}} &= -\sin\phi\,\mathbf{e_x} + \cos\phi\,\mathbf{e_y}
```

As usual, these unit vectors point along the local direction of maximum increase of the corresponding position coordinate.

Taking the general time derivative of the radial unit vector (assuming that both $\theta$ and $\phi$ are functions of time along the particle trajectory):

```{math}
:label: eq:duvecrdt
\frac{\mathrm{d}\mathbf{e_r}}{\mathrm{d}t} &= \frac{\partial \mathbf{e_r}}{\partial \theta}\,\dot{\theta} + \frac{\partial \mathbf{e_r}}{\partial \phi}\,\dot{\phi} \\
&= \cos\theta \cos\phi\,\dot{\theta}\,\mathbf{e_x} + \cos\theta \sin\phi\,\dot{\theta}\,\mathbf{e_y} - \sin\theta\,\dot{\theta}\,\mathbf{e_z}
\\
&- \sin\theta \sin\phi\,\dot{\phi}\,\mathbf{e_x} + \sin\theta \cos\phi\,\dot{\phi}\,\mathbf{e_y}
\\
&= \dot{\theta}\,\mathbf{e_{\theta}} + \sin\theta\,\dot{\phi}\,\mathbf{e_{\phi}}.
```

Note that these expressions have geometrical meaning. For example, if a particle moves such that its $\phi$ coordinate does not change, and it only increases its coordinate $\theta$, following a circular path of constant radial distance $r$, then in a time $\delta t$, the incremental change in the radial unit vector `carried along' with the particle would be of magnitude $\dot{\theta}\,\delta t$ and of direction parallel to the maximum-rate direction of increasing $\theta$, i.e., parallel to $\mathbf{e_{\theta}}$.

We now have enough information to evaluate all the terms (scalar and vector derivatives) needed in the definition of velocity:

```{math}
:label: eq:dvecrdt
\dfrac{\mathrm{d}(r\mathbf{e_r})}{\mathrm{d}t} &= \dot{r}\,\mathbf{e_r} + r\,\dfrac{\mathrm{d}\mathbf{e_r}}{\mathrm{d}t}
\\
&= \dot{r}\,\mathbf{e_r} + r\,\dot{\theta}\,\mathbf{e_{\theta}} + r\,\sin\theta\,\dot{\phi}\,\mathbf{e_{\phi}}.
```

Similar calculations to those which led to Equation {eq}`eq:duvecrdt`, for the other unit vectors (proof is left to the reader), give:

```{math}
:label: eq:duvecthetadt
\frac{\mathrm{d}\mathbf{e_{\theta}}}{\mathrm{d}t} = -\dot{\theta}\,\mathbf{e_{r}} + \cos\theta\,\dot{\phi}\,\mathbf{e_{\phi}},
```
```{math}
:label: eq:duvecphidtsp
\frac{\mathrm{d}\mathbf{e_{\phi}}}{\mathrm{d}t} = -\sin\theta\,\dot{\phi}\,\mathbf{e_{r}} - \cos\theta\,\dot{\phi}\,\mathbf{e_{\theta}}.
```

Finally, we can obtain the spherical polar components of acceleration by differentiating Equation {eq}`eq:dvecrdt`, and using the unit vector results from Equations
{eq}`eq:duvecrdt`, {eq}`eq:duvecthetadt` and {eq}`eq:duvecphidtsp`:

```{math}
:label: eq:accelsph
\mathbf{a} = \dfrac{\mathrm{d}^2(r\mathbf{e_r})}{\mathrm{d}t^2} &= \ddot{r}\,\mathbf{e_r} + \dot{r}\,\dot{\theta}\mathbf{e_{\theta}} + 
+ r\,\ddot{\theta}\,\mathbf{e_{\theta}}  \\
&+ \dot{r}\,\sin\theta\,\dot{\phi}\,\mathbf{e_{\phi}} 
 + r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,\mathbf{e_{\phi}} 
 + r\,\sin\theta\,\ddot{\phi}\,\mathbf{e_{\phi}}  \\
 & + \dot{r}\dfrac{\mathrm{d}\mathbf{e_r}}{\mathrm{d}t}
 + r\,\dot{\theta}\dfrac{\mathrm{d}\mathbf{e_{\theta}}}{\mathrm{d}t}
 + r\,\sin\theta\,\dot{\phi}\dfrac{\mathrm{d}\mathbf{e_{\phi}}}{\mathrm{d}t} \notag \\
 &= \ddot{r}\,\mathbf{e_r} + \dot{r}\,\dot{\theta}\mathbf{e_{\theta}} + 
+ r\,\ddot{\theta}\,\mathbf{e_{\theta}}  \\
&+ \dot{r}\,\sin\theta\,\dot{\phi}\,\mathbf{e_{\phi}} 
 + r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,\mathbf{e_{\phi}} 
 + r\,\sin\theta\,\ddot{\phi}\,\mathbf{e_{\phi}}  \\
 & + \dot{r}\,\dot{\theta}\,\mathbf{{e}_{\theta}} + \dot{r}\,\sin\theta\,\dot{\phi}\,\mathbf{{e}_{\phi}}
 -r\,\dot{\theta}^2\,\mathbf{{e}_{r}} +
r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,\mathbf{{e}_{\phi}} \notag \\
 & -r\,\sin^2\theta\,\dot{\phi}^2\,\mathbf{{e}_{r}} -
r\,\sin\theta\,\cos\theta\,\dot{\phi}^2\,\mathbf{{e}_{\theta}}. 
```

Collecting terms corresponding to each component of the acceleration vector, this expression simplifies to:

```{math}
\mathbf{a} =& (\ddot{r}-r \dot{\theta}^2-r\, {\sin^2\theta} \, \dot{\phi}^2)\,\mathbf{e_r} \\
& (r \ddot{\theta} + 2 \dot{r} \dot{\theta} -r\,\sin\theta\,\cos\theta\,\dot{\phi}^2) \, \mathbf{e_{\theta}}  \\
& (r\,\sin\theta\,\ddot{\phi} + 2\sin\theta\,\dot{r}\dot{\phi}
+ 2 r\,\cos\theta\,\dot{\theta}\dot{\phi})\,\mathbf{e_{\phi}}.
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
