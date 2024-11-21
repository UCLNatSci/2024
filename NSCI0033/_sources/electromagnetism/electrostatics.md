# Electrostatics

## Coulombs Law

Lets start with the basics, Coulombs law in Equation {eq}`CoulombsLaw`, tells us that a repulsive force between two 
charges $Q_i$, $Q_1$ at the origin and $Q_2$ at distance $r$:
```{math}
:label: CoulombsLaw
F_c = \frac{Q_1\,Q_2}{4\,\pi\,\epsilon_0}\frac{1}{r^2}
```
Obviously we can shift the charges, so that in general  $(Q_1(\mathbf{r}_1), \, Q_2(\mathbf{r}_2))$.  Also $\mathbf{F}_c$ is a vector quantity, 

so we can write the force acting on $Q_2(\mathbf{r}_2)$ due to $Q_1(\mathbf{r}_1)$ as:
```{math}
\mathbf{F}_{12} = \frac{Q_1\,Q_2}{4\,\pi\,\epsilon_0}\frac{1}{|\mathbf{r}_2 - \mathbf{r}_1|^2}\,\mathbf{\hat{r}}_{12}
``` 
where $\mathbf{\hat{r}}_{12}$ is a normalised vector that points from $Q_1(\mathbf{r}_1) \rightarrow Q_2(\mathbf{r}_2)$:

```{math}
\mathbf{\hat{r}}_{12} = \frac{\mathbf{r}_2 - \mathbf{r}_1}{|\mathbf{r}_2 - \mathbf{r}_1|}
```

This force $\mathbf{F}_{12}$ is related directly to the size of the charges and to the inverse square of the distance between them.  We can define the <mark>Electric Field</mark> $\mathbf{E}$ as the <mark>force per unit charge</mark>, in this case we can find the electric field due to the charge $Q_1$ measured at $\mathbf{r}_2$ as:
```{math}
:label: EFieldCharge
\mathbf{E} = \frac{\mathbf{F}_c}{Q_2} = \frac{Q_1}{4\,\pi\,\epsilon_0}\frac{1}{|\mathbf{r}_2-\mathbf{r}_1|^2}\,\mathbf{\hat{r}}_{12}
```

This expression has $Q_1$ taking the role of a <mark>source charge</mark>.

The direction of $ \mathbf{E} $ depends on the sign of the charges, positive sources have $ \mathbf{E} $ pointing <mark>away</mark> from the charge, negative sources have $ \mathbf{E} $ pointing <mark>towards</mark> the charge.  We can see this from an electric field diagram, such
as shown in {numref}`PositiveChargeEField`.
```{figure} ../figures/PositiveChargeEField.png
---
name: PositiveChargeEField
---
Electric fields lines from a positive charge
```

Our field lines radiate outwards radially, depending only on the distance from a point to the charge (here we are just assuming a point charge) and in the direction a positive charge would follow (here outwards as like charges repel).  

These are all very sound ideas that we have no doubt learnt before, the question is whilst Coulombs law is a very effective tool to empirically describe electric fields from point charges, where does is arrive from? Will it work in more complicated situations?  


## Superposition of charges

The net electric field at a point due to multiple charges is the <mark>vector sum</mark> of the electric fields produced by each charge individually.  This principle applies because electric fields obey the laws of vector addition.  This means we can break down (in principle) a complicated system (or distribution of charges) into its component charge parts.

In a given electrostatic system, we can aim to identify all charges and their positions, calculate the electric field vector $ \mathbf{E}_i $ at the point of interest due to each charge $ q_i $ and then add the vectors:

```{math}
\mathbf{E}_{\text{net}} = \sum_i \mathbf{E}_i
```

For charges distributed in 2D or 3D, we can break each electric field into components:

```{math}
\mathbf{E}_i = E_{i,x} \hat{\mathbf{i}} + E_{i,y} \hat{\mathbf{j}} + E_{i,z} \hat{\mathbf{k}}
```

And then sum the components along each axis:

```{math}
\mathbf{E}_{\text{net},x} = \sum_i E_{i,x}, \quad \mathbf{E}_{\text{net},y} = \sum_i E_{i,y}, \quad \mathbf{E}_{\text{net},z} = \sum_i E_{i,z}
```

We can use this method to calculate fields in systems with multiple discrete charges (or in the case of *continuous* charge distributions with integration to find the total charge).

Symmetry can often be exploited to simplify calculations (e.g., fields cancel out along certain axes).


### Example Problem: Superposition of Electric Fields


Two point charges, $ q_1 $ and $ q_2 $, are placed in a 2D coordinate plane:
- $ q_1 = +2 \, \mu\mathrm{C} $ is located at $ \mathbf{r}_1 = (0, 0) \, \mathrm{m} $ (origin).
- $ q_2 = -3 \, \mu\mathrm{C} $ is located at $ \mathbf{r}_2 = (4, 0) \, \mathrm{m} $ (along the x-axis).
- Find the net electric field $ \mathbf{E}_{\text{net}} $ at point $ P $ located at $ (2, 3) \, \mathrm{m} $.

---

### Step 1: Electric Field Contributions
The electric field $ \mathbf{E}_i $ due to a point charge $ q_i $ is:

```{math}
\mathbf{E}_i = \frac{1}{4\pi\epsilon_0} \frac{|q_i|}{r_i^2} \hat{\mathbf{r}}_i
```

where $ r_i $ is the distance between the charge $ q_i $ and point $ P $, and $ \hat{\mathbf{r}}_i $ is the unit vector from $ q_i $ to $ P $.

1. **Distance from $ q_1 $ to $ P $:**

```{math}
r_1 = \sqrt{(2 - 0)^2 + (3 - 0)^2} = \sqrt{4 + 9} = 3 \, \mathrm{m}
```

2. **Distance from $ q_2 $ to $ P $:**

```{math}
r_2 = \sqrt{(2 - 4)^2 + (3 - 0)^2} = \sqrt{(-2)^2 + 3^2} = \sqrt{4 + 9} = 3 \, \mathrm{m}
```

---

### Step 2: Electric Field Magnitudes
Using $ \frac{1}{4\pi\epsilon_0} \approx 9 \times 10^9 \, \mathrm{N \cdot m^2 / C^2} $:

1. **Electric field from $ q_1 $:**

```{math}
E_1 = \frac{9 \times 10^9 \cdot 2 \times 10^{-6}}{3^2} = \frac{18 \times 10^3}{9} = 2 \times 10^3 \, \mathrm{N/C}
```

2. **Electric field from $ q_2 $:**

```{math}
E_2 = \frac{9 \times 10^9 \cdot 3 \times 10^{-6}}{3^2} = \frac{27 \times 10^3}{9} = 3 \times 10^3 \, \mathrm{N/C}
```

---

### Step 3: Direction of Electric Fields
1. **Direction of $ \mathbf{E}_1 $:**
   - $ q_1 > 0 $, so $ \mathbf{E}_1 $ points away from $ q_1 $:
   ```{math}
   \hat{\mathbf{r}}_1 = \frac{\mathbf{r}_P - \mathbf{r}_1}{r_1} = \frac{(2, 3) - (0, 0)}{3} = \left(\frac{2}{3}, 1\right)
   ```
   ```{math}
   \mathbf{E}_1 = E_1 \hat{\mathbf{r}}_1 = 2 \times 10^3 \left(\frac{2}{3} \hat{\mathbf{i}} + \hat{\mathbf{j}}\right) = \left(1333 \hat{\mathbf{i}} + 2000 \hat{\mathbf{j}}\right) \, \mathrm{N/C}
   ```

2. **Direction of $ \mathbf{E}_2 $:**
   - $ q_2 < 0 $, so $ \mathbf{E}_2 $ points toward $ q_2 $:
   ```{math}
   \hat{\mathbf{r}}_2 = \frac{\mathbf{r}_P - \mathbf{r}_2}{r_2} = \frac{(2, 3) - (4, 0)}{3} = \left(\frac{-2}{3}, 1\right)
   ```
   ```{math}
   \mathbf{E}_2 = E_2 \hat{\mathbf{r}}_2 = 3 \times 10^3 \left(\frac{-2}{3} \hat{\mathbf{i}} + \hat{\mathbf{j}}\right) = \left(-2000 \hat{\mathbf{i}} + 3000 \hat{\mathbf{j}}\right) \, \mathrm{N/C}
   ```

---

### Step 4: Net Electric Field
Add $ \mathbf{E}_1 $ and $ \mathbf{E}_2 $ component-wise:

1. $ x $-component:
   ```{math}
   E_{\text{net},x} = 1333 - 2000 = -667 \, \mathrm{N/C}
   ```

2. $ y $-component:
   ```{math}
   E_{\text{net},y} = 2000 + 3000 = 5000 \, \mathrm{N/C}
   ```

Thus:

```{math}
\mathbf{E}_{\text{net}} = -667 \hat{\mathbf{i}} + 5000 \hat{\mathbf{j}} \, \mathrm{N/C}
```

---

### Step 5: Magnitude and Direction
1. **Magnitude**:
   ```{math}
   |\mathbf{E}_{\text{net}}| = \sqrt{(-667)^2 + 5000^2} = \sqrt{445889 + 25000000} \approx 5022 \, \mathrm{N/C}
   ```

2. **Angle (relative to $ x $-axis)**:
   ```{math}
   \theta = \tan^{-1}\left(\frac{E_{\text{net},y}}{E_{\text{net},x}}\right) = \tan^{-1}\left(\frac{5000}{-667}\right) \approx -83.4^\circ
   ```

   (or $ 96.6^\circ $ counterclockwise from the positive $ x $-axis).

---

### Final Answer:
```{math}
\mathbf{E}_{\text{net}} = 5022 \, \mathrm{N/C} \, \text{at an angle of } 96.6^\circ \, \text{counterclockwise from the } x\text{-axis.}
```


## Infinitesimal Coulombs law
Lets start with a simpler problem first though, a semicircular arc of charge, as depicted in {numref}`SemiCircularArcofCharge`
```{figure} ../figures/SemiCircularArcofCharge.png
---
name: SemiCircularArcofCharge
---
An finite line of charges, with charge density $\lambda$, arranged in a semicircular arc of length $L$ and centered on the origin.
```
What are the symmetries of this semicircular system? Well if we consider a section of the arc, it will carry a charge $\mathrm{d} Q$ which we can rewrite as 
$\mathrm{d} Q = \lambda \mathrm{d} \ell$.  Given that for a circular arc $\ell = r \theta$ and since $L = \pi r$, therefore 
```{math}
\mathrm{d} Q = \frac{\lambda\,L}{\pi} \mathrm{d} \theta
```
where $\theta$ is an angle that moves round the arc, as we define in {numref}`AngularArcofCharge`.
```{figure} ../figures/SemiCircularArcofCharge2.png
---
name: AngularArcofCharge
---
Semicircular arc of charges, centered on the origin, with charge element $\mathrm{d} Q$, length $L$, radius $r$ and angle $\theta$.
```
Clearly now we want to integrate over all the charges $\mathrm{d}Q$ which will involve integrating over all angles $\mathrm{d} \theta$.  Since we are treating 
these infitesimal charge elements as point charges, the magnitude of the electric field has the form:
```{math}
\mathrm{d} E = \frac{\mathrm{d}Q}{4 \pi\,\epsilon_0\,r^2} = \frac{\pi \,\mathrm{d}Q}{4\,\epsilon_0\,L^2}
```
The direction of the field components however will change depending on whereabouts along the ring we are, clearly are $\theta = 0$, the field is directed along the $x$-axis only:
```{math}
\mathrm{d}\mathbf{E}_{\theta = 0} = \frac{\pi \,\mathrm{d}Q}{4\,\epsilon_0\,L^2} \,\mathbf{\hat{i}} + 0 \,\mathbf{\hat{j}}
```
Whilst if we examine the field at $\theta = -\pi/2$ and $\theta = \pi/2$, we notice that the electric field will be aligned in the positive and negative $y$-axis directions (respectively):
```{math}
\mathrm{d}\mathbf{E}_{\theta = -\pi/2} &=&\, 0 \,\mathbf{\hat{i}} + \frac{\pi \,\mathrm{d}Q}{4\,\epsilon_0\,L^2} \,\mathbf{\hat{j}} \\
\mathrm{d}\mathbf{E}_{\theta =\pi/2} &=&\, 0 \,\mathbf{\hat{i}} - \frac{\pi \,\mathrm{d}Q}{4\,\epsilon_0\,L^2} \,\mathbf{\hat{j}} 
```
In fact we see that there will always be a cancellation of the $y$ components of the electric field from the arc, we can always pair up the components over 
$-\pi/2 \leq \theta \leq \pi/2$, this leaves just the $x$ components:
```{math}
\mathrm{d}\mathbf{E}_{\theta} &=&\, \frac{\pi \,\mathrm{d}Q}{4\,\epsilon_0\,L^2} \Big[ \cos(\theta) \,\mathbf{\hat{i}} + \sin(\theta) \,\mathbf{\hat{j}} \Big] \\
\int_0^\mathbf{E} \mathrm{d}\mathbf{E}_{\theta} &=&\,  \frac{\pi}{4\,\epsilon_0\,L^2} \frac{\lambda\,L}{\pi} \int_{-\pi/2}^{\pi/2} \Big(\cos(\theta)\,\mathbf{\hat{i}} + 
\sin(\theta)\,\mathbf{\hat{j}} \Big)\,\mathrm{d} \theta\\
\mathbf{E} &=&\,  \frac{\lambda}{4\,\epsilon_0\,L}  \Big[\sin(\theta)\,\mathbf{\hat{i}} - \cos(\theta)\,\mathbf{\hat{j}}\Big]_{-\pi/2}^{\pi/2} = \frac{\lambda}{2\,\epsilon_0\,L} \,\mathbf{\hat{i}} + 0\,\mathbf{\hat{j}}
```
### Rectilinear Rod
Lets return to the rod in {numref}`Finitelineofcharge`, we can set this system up in {numref}`Finitelineofcharge2`, trying to make the rod as symmetric as possible:

```{figure} ../figures/FiniteLineOfCharges3.png
---
name: Finitelineofcharge2
---
An finite line of charges, with charge density $\lambda$, with length $L$, symmetrically aligned over the $x$ axis. We pick out an element of charge indicated 
in red, so here $\mathrm{d} Q = \lambda \,\mathrm{d} x$.
```
With a line of charge, of length $L$, aligned along the $x$ axis, we can look at a point at a distance $R$ away, aligned halfway along the rod.  Once again we can break up this 
line of charge into infinitesimal chunks, each contributing $\mathrm{d} Q$ charge and then the overall electric field will be found by superposition.  The magnitude of the electric 
field at a distance $R$ from the rod appears to be given by:
```{math}
\mathrm{d} E = \frac{\mathrm{d}Q}{4\pi \,\epsilon_0\,r^2}
```
where the length $r$ can take values between $R \leq r \leq \sqrt{R^2 + L^2 / 4}$. 

In this system, we find that at $x = 0$, the electric field is only aligned in the $y$ direction:
```{math}
\mathrm{d} \mathbf{E}_{x = L/2} = 0\,\mathbf{\hat{i}} + \frac{\mathrm{d}Q}{4\pi \,\epsilon_0\,R^2}\,\mathbf{\hat{j}}
```
whereas the $x$ components of the electric field for all the lengths at $-L/2 \leq x < 0$ and $0 > x \leq L/2$ will pair up, to cancel out, leaving only the $y$ components:
```{math}
\mathrm{d} \mathbf{E} &=&\, \frac{\mathrm{d}Q}{4\pi \,\epsilon_0\,r^2} \Big (\sin(\theta)\,\mathbf{\hat{i}} + \cos(\theta)\,\mathbf{\hat{j}}\Big)\\
\int_0^\mathbf{E} \mathrm{d} \mathbf{E}' &=&\, \frac{\lambda }{4\pi \,\epsilon_0} \int_{-L/2}^{L/2}\Big (\frac{x}{r^3}\,\mathbf{\hat{i}} + \frac{R}{r^3}\,\mathbf{\hat{j}}\Big)\,\mathrm{d} x\\
\mathbf{E} &=&\, \frac{\lambda}{4\pi \,\epsilon_0} \int_{-L/2}^{L/2}\Bigg(\frac{x}{(x^2 + R^2)^{3/2}}\,\mathbf{\hat{i}} + \frac{R}{(x^2 + R^2)^{3/2}}\,\mathbf{\hat{j}}\Bigg)\,\mathrm{d} x 
```
Where we have used the substitutions $\sin(\theta) = x/r = x / \sqrt{x^2 + R^2},\, \cos(\theta) = R / r = R / \sqrt{x^2 + R^2}$.  We can also use the substitution 
$x = R\,\tan(\theta) \Rightarrow \mathrm{d}x = R\,\sec^2(\theta)$ to find:
```{math}
\mathbf{E} &=&\, \frac{\lambda}{4\pi \,\epsilon_0} \int_{x = -L/2}^{x = L/2}\Big (\frac{R \,\tan(\theta)}{R^3\,\sec^3(\theta)}\,\mathbf{\hat{i}} + 
\frac{R}{R^3\,\sec^3(\theta)}\,\mathbf{\hat{j}}\Big) R\,\sec^2(\theta)\,\mathrm{d} \theta \\
 &=&\,\frac{\lambda}{4\pi \,\epsilon_0\,R} \int_{x = -L/2}^{x = L/2}\Bigg(\sin(\theta)\,\mathbf{\hat{i}} + \cos(\theta)\,\mathbf{\hat{j}}\Bigg)\,\mathrm{d} \theta \\
 &=&\,\frac{\lambda}{4\pi \,\epsilon_0\,R} \Big[ -\cos(\theta)\,\mathbf{\hat{i}} + \sin(\theta)\,\mathbf{\hat{j}}\Big]_{x = -L/2}^{x = L/2} \\
 &=&\,\frac{\lambda}{4\pi \,\epsilon_0\,R} \Big[ -\frac{R}{(x^2 + R^2)^{1/2}}\,\mathbf{\hat{i}} + \frac{x}{(x^2 + R^2)^{1/2}}\,\mathbf{\hat{j}}\Big]_{-L/2}^{L/2} \\
 &=&\,\frac{\lambda}{4\pi \,\epsilon_0\,R} \Big( 0 \,\mathbf{\hat{i}} + \frac{L}{(L^2/4 + R^2)^{1/2}}\,\mathbf{\hat{j}}\Big) 
```
Which results in:
```{math}
\mathbf{E} = \frac{\lambda\,L }{4\pi \,\epsilon_0\,R\,\sqrt{L^2/4 + R^2}}\,\mathbf{\hat{j}}
```
Notice that in the limit of $L \gg 1$, this would look like:
```{math}
\mathbf{E} \rightarrow \frac{\lambda}{2\pi \,\epsilon_0\,R}\,\mathbf{\hat{j}}
```
which is essentially the result for the infinite line of charge in Equation {eq}`InfiniteChargeLineEField`.

We note therefore that the relevant expression for the magnitude of the electric field at a distance $R$ from the rod is found from just the $y$ component:
```{math}
:label: EFieldWire
\mathrm{d} E &=&\, \frac{\mathrm{d}Q}{4\pi \,\epsilon_0\,r^2}\,\cos(\theta) = \frac{\mathrm{d}Q\,R}{4\pi \,\epsilon_0\,r^3}\\
\Rightarrow E &=&\,  \frac{\lambda}{4\pi \,\epsilon_0}\int_{rod} \frac{R}{r^3}\,\mathrm{d}x = \frac{\lambda}{4\pi \,\epsilon_0\,R} \Bigg[\frac{x}{\sqrt{x^2+R^2}}\Bigg]_{rod}
```

## Gauss's law
Lets now look at electric fields from the point of view of an a containing surface and flux crossing the surface boundary.  Starting with a charge 
$Q$, we can surround this in three dimensions by a sphere, as seen in Figure {numref}`EFieldFlux`.
```{figure} ../figures/EFieldFlux2.png
---
name: EFieldFlux
---
Flux of the electric field from a point charge $+q$ passing through a spherical surface.
```

Now we have field lines perpendicular to the surface, here a sphere, so a similar situation to hose pipe and the water.  But now we have 
to think about <em>how close</em> the field lines get over the spheres surface - they should really be thought of as infinitesimally small, so we use 
an area integral summing up the flux crossing the bounding surface area $A$:  
```{math}
\Phi_E = \iint_A \mathbf{E}\cdot \mathrm{d}\mathbf{A}
```
What will this flux we related to? Well imagine us increasing the size of the charge at the centre of the sphere, clearly the size of the Coulombic 
force between this and another charge will increase and so the magnitude of the electric field will increase.  As the flux is counting however much 
of the electric field is crossing the spherical boundary here, clearly the flux will increased, so we can make the statement:
```{math}
\iint \mathbf{E}\cdot \mathrm{d} \mathbf{A} \propto Q
```
This makes sense because both flux and charge are scalar quantities and because the flux only seems to change with the charge linearly 
(we saw this in Equation {eq}`EFieldCharge`).  Lets just assign a constant $k$ to make this an equation
```{math}
\iint \mathbf{E}\cdot \mathrm{d} \mathbf{A} = k\,Q
```
and we will aim to find the value of $k$ later.  One thing we can find straightforwardly is what units $k$ should have
```{math}
[\textrm{k}] = [\rho][\mathbf{v}][\textrm{Q}]^{-2} = \textrm{kg}\,\textrm{m}^{-3}\,\textrm{m}\,\textrm{s}^{-1}\,\textrm{C}^{-2} 
= \textrm{kg}\,\textrm{m}^{-2}\,\textrm{s}^{-1}\,\textrm{C}^{-2}
```
We can aim to use this flux law to get to Coulombs law, as the two results must agree, so starting with the spherical surface area $A$ 
around the charge $Q$ we find that the area normal vector is $\mathbf{A} = A_r\,\mathbf{\hat{r}}$.  The surface integral term therefore reduces to:
```{math}
\iint \mathbf{E}\cdot \mathrm{d} \mathbf{A} = \iint E_r \,\mathrm{d} A_r
``` 
where we decomposed the electric field $\bf E$ in to components:
```{math}
\mathbf{E} = E_r \mathbf{\hat{r}} + E_\theta \mathbf{\hat{\theta}} + E_\phi \mathbf{\hat{\phi}}
```
By symmetry therefore the electric field does not have an angular $(\theta,\, \phi)$ dependence - this makes sense physically because 
whether a charge is on our left or right hand side does not charge the force felt if it is at the same fixed distance.  

Calculating $\iint \mathbf{E}\cdot \mathrm{d} \mathbf{A}$ is straightforward on a sphere:
```{math}
\iint E_r\, \mathrm{d} A_r = \iint E_r \,r^2 \,\sin \theta\, \mathrm{d} \theta \,\mathrm{d} \phi
```
Since $E_r$ only has $r$ dependence, we can factorise this out of the integral:
```{math}
E_r \iint  \,r^2 \,\sin \theta\, \mathrm{d} \theta \,\mathrm{d} \phi = E_r(4 \pi\,r^2) &=&\, kQ \\
\Rightarrow E_r &=&\, \frac{kQ}{4\pi\,r^2}
```
Finally we can write this in vector form:
```{math}
\mathbf{E} = \,E_r \,\mathbf{\hat{r}} = \frac{k Q}{4\pi\,r^2} \,\mathbf{\hat{r}}
```
Comparing this result with Coulomb's law in Equation {eq}`CoulombsLaw`, we find we can fix $k = 1/\epsilon_0$ (which also has the required units, check 
this for yourself!).  So our final expression, which is known as <mark>Gauss's Law</mark>, can be written as:
```{math}
:label: GaussLaw
\iint_A \mathbf{E} \cdot \mathrm{d} \mathbf{A} = \frac{Q}{\epsilon_0} 
```
The charge $Q$ here should be carefully explained, central to the discussion of the flux were the field lines from the 
charge cutting the bounding surface area $A$, so we really mean to write the $Q$ as one enclosed by the area $A$ and so 
we should really write Gauss's law as:
```{math}
\iint_A \mathbf{E} \cdot \mathrm{d} \mathbf{A} = \frac{Q_{enclosed}}{\epsilon_0}
```

## Gravitational Analogue
One of the grand goals of physics is to understand nature through the same equations but on different scales - so called <mark>universality</mark>.  We
find that the equations in electrostatics can be used to discuss Newton's law of gravitation.  We notice that the equations are essentially just a 
redefinition of fields and constants:
```{math}
F_C = \frac{1}{4\pi \epsilon_0}\frac{Q_1\,Q_2}{r^2} \Longleftrightarrow F_G = -G\frac{\,M_1\,M_2}{r^2}
```
where $F_G$ is negative as it is only an attractive force, these suggest that by analogy:  
```{math}
\frac{1}{\epsilon_0} \Longleftrightarrow -4\pi\, G, \quad \quad Q_i \Longleftrightarrow M_i
```
Our electric field here $\mathbf{E}$ has a direct analogue in the gravitational field $\mathbf{g}$:
```{math}
\mathbf{E} = \frac{\mathbf{F}_E}{Q} \Longleftrightarrow \mathbf{g} = \frac{\mathbf{F}_N}{M}
```
and therefore we could examine Gauss's law for gravitational fields:
```{math}
:label: gravfieldGauss
\iint \mathbf{g} \cdot \mathrm{d} \mathbf{A} = -4\pi\,G\,M_{enclosed}
```
An application of this is understanding the interior gravitational field of a large uniform astrophysical body (e.g. the Earth), 
which we find results in the analogue of {numref}`electricfieldsphere`.  
