# Gravitation and Central Forces

<img src="Figs/gravimag.jpeg" width="700">

*Image Credit: NASA / CC BY*

## Newton's Law of Universal Gravitation
Every particle in the universe attracts every other particle with a force whose magnitude is proportional to the product of the masses of the two particles and inversely proportional to the square of the distance between them. The direction of the force lies along the straight line connecting the two particles.

We can represent this statement mathematically by using vectors, as follows:

```{math}
:label: eq:gravlaw
\mathbf{F}_{ij} = \dfrac{G m_i m_j}{r_{ij}^2} \dfrac{\mathbf{r}_{ij}}{r_{ij}}.
```

In {eq}`eq:gravlaw`, $\mathbf{F}_{ij}$ is the attractive force on a point mass $m_i$ due to another mass $m_j$, which is situated at a distance $r_{ij}$ from $m_i$. The vector $\mathbf{r}_{ij}$ is a vector running from the position of $m_i$ to that of $m_j$ (we can write $\mathbf{r}_{ij} = \mathbf{r}_j - \mathbf{r}_i$). In accordance with Newton's law of action and reaction, we can see that $\mathbf{F}_{ij} = -\mathbf{F}_{ji}$.

The value of $G$, the <mark>universal constant of gravitation</mark>, is $(6.67259 \pm 0.00085) \times 10^{-11} \, \mathrm{N \cdot m^2 \cdot kg^2}$. Gravitational force is an example of a <mark>central force</mark>—these are forces whose lines of action emerge from, or terminate on, a single point or center. It is also an <mark>isotropic force</mark>, since its magnitude does not depend on the direction along which it acts. If we approximate the Earth as a body with perfect spherical symmetry, the gravitational force due to the Earth acting upon any mass $m$ on its surface would be:

```{math}
\frac{G M_E m}{R_E^2},
```

with $M_E$ and $R_E$ denoting the Earth's mass and radius. According to Newton's second law, this force must also be equal to $m g$, where $g$ is the acceleration upon the mass $m$ due to gravity. Hence, $g = \frac{G M_E}{R_E^2}$ is the acceleration due to the Earth's gravitational force at its surface, and is independent of the mass of the body upon which it acts.

## Gravitational Force between a Uniform Sphere and a Particle
Consider a thin spherical shell of radius $R$, as shown in Figure 1, which carries a uniform mass per unit area of $\sigma$ (often known as surface mass density). Now let's calculate the gravitational field due to the shell at some particle $P$, of mass $m$, which is situated outside the shell, at a distance $r$ from its center. In a convenient set of coordinates, the $z$-axis can be chosen so that it contains both the center of the shell (which we choose to be the origin $O$) and the point $P$.

```{figure} Figs/gshell.png
---
name: fig:gshell
---
Diagram for calculating the gravitational field at a point $P$ outside a thin spherical shell of uniform surface density.
```

To do the calculation, we divide the shell up into many rings, or circular strips, which are symmetrical about the $z$-axis and of infinitesimal thickness $R \, \Delta \theta$, where $\theta$ is the angle between the direction $OP$ and the position of any element on a ring with respect to the origin. The radius of the rings is $R \sin \theta$. Hence, any ring will have a surface area $\Delta S = 2\pi R \sin \theta \, \Delta \theta$, and thus have a mass $\Delta M = \sigma \, \Delta S$.

The Figure shows that any element $Q$ of the ring will exert a force on $P$ given by $\mathbf{\Delta F}_Q$, which points from $P$ to $Q$. We can resolve this force into components parallel and perpendicular to the $z$-axis (i.e., the direction $OP$). From the symmetry of the problem, we see that as we travel around the ring, the sum of all the perpendicular components will add to zero, and only the parallel component is important. This component for any of the rings has a magnitude given by:

```{math}
:label: eq:dfring
\Delta F_{\text{ring}} = G \dfrac{m \, \Delta M}{s^2} \cos \phi
= G \dfrac{m 2 \pi \sigma R^2 \sin \theta \cos \phi}{s^2} \Delta \theta.
```

To add together the force due to all of the rings which make up the shell, it seems we have to integrate with respect to the variable angle $\theta$, whose value varies between 0 and $\pi$. We can make the calculation a little easier by firstly noting, from the geometry of the triangle in the figure, that $s^2 = r^2 + R^2 - 2 r R \cos \theta$ (cosine rule for triangles). Noting that $r$ and $R$ are fixed values, but that $s$ and $\theta$ are variable, the differential of this expression gives:

```{math}
s \, ds = r R \, \sin \theta \, d \theta.
```

Similarly, the angle $\phi$ is related to the triangle's side lengths according to:

```{math}
R^2 = s^2 + r^2 - 2 r s \cos \phi \quad \rightarrow \quad \cos \phi = \frac{s^2 + r^2 - R^2}{2 r s}.
```

We can now eliminate factors involving $\theta$ and $\phi$ from our expression for $\Delta F_{\text{ring}}$ in {eq}`eq:dfring`:

```{math}
:label: eq:dfringupd
\Delta F_{\text{ring}} &= G \dfrac{m 2 \pi \sigma R^2}{s^2} \dfrac{s}{rR} \dfrac{s^2 + r^2 - R^2}{2 r s} \Delta s \\
&= \dfrac{G m \pi \sigma R}{r^2} \left(1 + \dfrac{r^2 - R^2}{s^2}\right) \Delta s.
```

We can now integrate this expression with respect to $s$, whose value ranges between $r - R$ and $r + R$ in order to cover the sphere. We obtain:

```{math}
    F &= \dfrac{G m\pi\sigma R} {r^2} \, 
        \int_{s=r-R}^{r+R}\left(1 + \dfrac{r^2 - R^2}{s^2}\right)\, ds \\
        &= \dfrac{G m\pi\sigma R} {r^2} \, 
        \left(2R -(r^2 - R^2)\left[\dfrac{1}{s}\right]_{r-R}^{r+R}\right)
        \\
        &= \dfrac{G m\pi\sigma R} {r^2} \, 
        \left(2R -(r^2 - R^2)\dfrac{((r-R)-(r+R))}{(r+R)(r-R)}\right)
        \\
        & = \dfrac{G m 4\pi \sigma R^2}{r^2} = G M_s m / r^2. 
```

Here, $M_s$ is the mass of the sphere.

This is a very important result—it shows that the gravitational field due to the spherical shell, at any point outside that shell, is equivalent to the field produced by a point mass at the center of the sphere, containing all of the mass of the sphere. It is easy to see that this idea can be extended to <mark>any spherically symmetric body</mark>, whose density is a function of radial distance only. Such a body is essentially a superposition of many spherical shells, and so the same result holds true. Interestingly, the <mark>total force at any point inside the shell is zero</mark>, which can be proven with an analysis similar to that shown above.

## Kepler's Laws of Planetary Motion
From a detailed analysis of planetary motions in our Solar System, Johannes Kepler (1571-1630) was able to deduce three important aspects of this motion. His laws also played an important role in Newton's development of the law of gravitation. In this section, we'll investigate how Kepler's laws are a consequence of the planets being subject to a central force -- namely, the gravitational force.

<div id="sec:angmomkep"></div>

### Angular Momentum and Kepler's Second Law 

<mark>Kepler's second law</mark> may be stated: </mark>A line drawn between the Sun and the planet sweeps out equal areas in equal times as the planet orbits the Sun.</mark> What underpins this behaviour is a constant of the motion known as the planet's <mark>angular momentum</mark>. The mathematical definition of angular momentum is:
```{math}
\mathbf{L} = \mathbf{r} \times \mathbf{p},
```
where $ \mathbf{r} $ is the position vector of the centre of the planet with respect to the centre of the Sun, and $ \mathbf{p} $ is the planet's momentum (the usual product, $ m \mathbf{v} $, of its mass and velocity). To prove that the angular momentum $ \mathbf{L} $ stays constant during the motion of the planet under the gravitational influence of the Sun, we may investigate the derivative with respect to time:
```{math}
\dfrac{\mathrm{d}\mathbf{L}}{\mathrm{d}t} = \dot{\mathbf{r}} \times \mathbf{p} + \mathbf{r} \times \dot{\mathbf{p}} 
= \mathbf{v} \times (m \mathbf{v}) + m \mathbf{r} \times \dot{\mathbf{v}}.
```
Now the first term on the right-hand side is zero, since it involves the cross product of a vector with itself. The second term involves the cross product of $ \mathbf{r} $ and the acceleration $ \dot{\mathbf{v}} $. But according to Newton's second law, the acceleration is proportional to the force acting on the body. The gravitational force of the Sun on the planet acts in the direction from the planet to the Sun, i.e. along the direction $ -\mathbf{r} $. Hence the second term in the equation above is also zero and $ \mathbf{L} $ is a constant of the motion as the planet orbits the Sun. Since $ \mathbf{L} $ is always perpendicular to the plane defined by the vectors $ \mathbf{r} $ and $ \mathbf{p} $, it follows that this plane remains fixed in its orientation and thus the problem of orbital motion, in our example, is essentially a two-dimensional problem.

Taking this idea further, let's specify the position of the planet with two coordinates: its radial distance $ r $ from the Sun and the angle $ \theta $ made between its position vector and some convenient reference direction lying in the plane of its orbit about the Sun. This reference direction passes through the origin, which is chosen to be the Sun's location (see {numref}`fig:sweepda`).
We can thus define the planet's velocity as <mark>$ \mathbf{v} = \dot{r} \mathbf{e}_{r} + r \dot{\theta} \mathbf{e}_{\theta} $</mark>, where the vectors $ \mathbf{e}_j $ are appropriate unit vectors in the radial and meridional directions.

```{figure} Figs/sweepda.png
---
name: fig:sweepda
---
Motion of a particle in a single plane. (a) Components of velocity; n(b) Area swept out during an infinitesimal time increment. (from the book by Fowles and Cassiday)
```

Using this definition, the angular momentum magnitude becomes 
```{math}
L = |m \mathbf{r}\times \mathbf{v}| = |m r^2 \dot{\theta} \, \mathbf{e}_r \times \mathbf{e}_{\theta}|.
```
Since $ |\mathbf{e}_r \times \mathbf{e}_{\theta}| = 1 $ (these unit vectors are always orthogonal), 
```{math}
L = m r^2 \dot{\theta}.
```
Hence the conservation of angular momentum implies that $ \dot{\theta} \propto 1/r^2 $.

The angular momentum is also related to the rate of change of the area swept out by the position vector of the planet as it orbits. Figure below shows that in an infinitesimal time $ \mathrm{d}t $, the area swept out is that of a triangle, and given by 
```{math}
\mathrm{d}A= \frac{1}{2} |\mathbf{r}\times\mathbf{\mathrm{d}r}| = \frac{1}{2} |\mathbf{r}\times\mathbf{v} \mathrm{d}t|.
```
Thus:
```{math}
:label: eq:dareadt
\dfrac{\mathrm{d}A}{\mathrm{d}t} = \frac{1}{2} |\mathbf{r}\times\mathbf{v}| = \dfrac{L}{2m}.
```
Since we know $ L $ is a constant of the motion, we conclude that so too (as Kepler's observations showed) is the rate at which a planet's position vector (with respect to the Sun) sweeps out area as it moves.

### Kepler's First Law and Orbital Geometry
Kepler's first law is a relationship between the size of a planet's orbit and its orbital period. To derive this relationship, we will set up the equation of motion of an orbiting planet, of mass $ m $, and solve it. The equation itself may be written in the form:
```{math}
m\,\ddot{\mathbf{r}} = f(r)\,\mathbf{e}_r.
```
This equation emphasises that the gravitational force experienced by the planet, due to the Sun, is collinear with the unit vector $ \mathbf{e}_r $, which points along the Sun-planet direction.

We can decompose this vector equation into its radial ($ r $) and meridional ($ \theta $) components by using the expressions from the </mark>Particle Dynamics</mark> unit for the corresponding components of the acceleration:

```{math}
:label: eq:eomcompr
m (\ddot{r} - r \dot{\theta}^2) = f(r),
```
```{math}
:label: eq:eomcomp
m (2 \dot{r} \dot{\theta} + r \ddot{\theta}) = 0. 
```

It is straightforward to show that the second equation implies
```{math}
\dfrac{\mathrm{d}}{\mathrm{d}t} (r^2 \dot{\theta}) = 0.
```
This condition is equivalent to the statement that the angular momentum is conserved. The quantity $ l = r^2 \dot{\theta} $ is equal to (see section on [angular momentum](#sec:angmomkep)) the angular momentum per unit mass of the planet. This is often referred to as the <mark>specific angular momentum</mark>.

In order to investigate the shape of an orbital trajectory for a planet (or indeed any particle moving under the influence of a central force) it is convenient to work with the variable $ u = 1/r $. The variation in $ u $ as a function of $ \theta $ is what we are seeking to understand.

We note that we can transform $ \dot{r} $ in terms of $ u $ as follows:

```{math}
\dot{r} = \dfrac{\mathrm{d}}{\mathrm{d}t}(1/u) = (-1/u^2)\,\dot{u} = \dfrac{-1}{u^2}\,\dot{\theta}\,\dfrac{\mathrm{d}u}{\mathrm{d}\theta} = -l \, \dfrac{\mathrm{d}u}{\mathrm{d}\theta}.
```
The final step above makes use of the definition $ l = r^2 \dot{\theta} $.

Differentiating a second time to obtain an expression for $ \ddot{r} $, we get:
```{math}
\ddot{r} = -l \, \dfrac{\mathrm{d}}{\mathrm{d}t} \left(\dfrac{\mathrm{d}u}{\mathrm{d}\theta}\right) = -l \dot{\theta} \dfrac{\mathrm{d}^2u}{\mathrm{d}\theta^2}.
```

If we now substitute our expressions for $ \dot{r} $, $ \dot{\theta} $, and $ \ddot{r} $ into {eq}`eq:eomcompr`, we obtain the following differential equation for $ u $ as a function of $ \theta $:

```{math}
:label: eq:uorbit
l \left( \frac{l}{r^2} \right) \dfrac{\mathrm{d}^2u}{\mathrm{d}\theta^2} + r \left( \frac{l^2}{r^4} \right) &= -\frac{f(r)}{m}, \\
\rightarrow \dfrac{\mathrm{d}^2u}{\mathrm{d}\theta^2} + u &= \dfrac{-f\left({1}/{u}\right)}{ml^2 \, u^2} 
```
This equation allows us to determine the shape of an orbit ($ u(\theta) $), given the nature of the force function $ f(r) $ (a function of radial distance only). Conversely, given the function $ u(\theta) $, one can, in principle, determine the force function $ f(r) $, which then gives insight as to the nature of the central force producing the given orbital trajectory.

Let's now look for solutions of {eq}`eq:uorbit` corresponding to the orbit of a planet of mass $ m $ around the Sun of mass $ M $. We will assume that $ m \ll M $ so that the Sun stays fixed at the origin of our coordinate system (i.e.\ its position is unperturbed by the presence of any planet). For this case, the function $ f(r)= -k/r^2 $, where the constant
$ k = GMm $. Our equation for the orbit then becomes:
```{math}
\dfrac{\mathrm{d}^2u}{\mathrm{d}\theta^2} + u = \dfrac{ku^2}{ml^2} = \dfrac{GM}{l^2}.
```
Fortunately, we have encountered this type of differential equation already, in the unit on 'Oscillations'. The general solution can be written:
```{math}
u(\theta) = A \cos(\theta - \theta_0) + \dfrac{GM}{l^2},
```
where $ A $ and $ \theta_0 $ are constants. It follows that we can obtain $ r $ through:
```{math}
r(\theta) = \dfrac{1}{u} = \dfrac{1}{A \cos(\theta - \theta_0) + \dfrac{GM}{l^2}}.
```
Without loss of generality, we can adopt a convention where we set $ \theta_0 = 0 $ and thus define the direction $ \theta = 0 $ to correspond to the minimum value of $ r $. Hence:
```{math}
:label: eq:rvsthetaorb
r(\theta) = \dfrac{1}{A \cos\theta + \dfrac{GM}{l^2}} = \dfrac{l^2/GM}{1 + \left(\dfrac{Al^2}{GM}\right)\cos\theta}. 
```

Now, this solution $ r(\theta) $ for the orbital shape looks very much like the well-known formula that corresponds to the shapes known as <mark>conic sections</mark>. This formula can be written:
```{math}
:label: eq:conicsecn
r(\theta) = \dfrac{a(1 - \epsilon^2)}{1 + \epsilon \cos\theta}, 
```
where $ \epsilon $ is a parameter known as the <mark>eccentricity</mark>, and the point of closest approach to the origin (minimum $ r $) occurs at a distance $ a(1 - \epsilon) $. 

The three broad classes of conic section / orbit shape can be classified according to the value of $ \epsilon $ as follows:
1. <mark>Ellipse</mark> ($ 0 \leq \epsilon < 1 $): An elliptical shape can be formed by considering the general intersection of a plane and a cone (see {numref}`fig:conicsecn`). When the angle of tilt $ \xi $ between the plane and the cone axis lies in the interval $ (\beta, \pi/2) $, where $ \beta $ is the cone's generating angle (angle between its axis and its slant height). For the special case where $ \epsilon = 0 $ ($ \xi = \pi/2 $), the shape becomes a circle defined by $ r = a $, a figure of constant radial distance from the origin.
2. <mark>Parabola</mark> ($ \epsilon = 1 $): In this case, to keep the product $ a(1 - \epsilon^2) $ finite as $ \epsilon \rightarrow 1 $, we require $ a \rightarrow \infty $. The angle between the intersecting plane and cone (see {numref}`fig:conicsecn`) becomes equal to $ \beta $.
3. <mark>Hyperbola</mark> ($ \epsilon > 1 $): Here, the angle of tilt between the intersecting plane and cone lies in the interval $ [0, \beta) $. Like the parabola, the hyperbola represents an open conic section with unbounded values of $ r $. The ellipse is a closed conic section.



```{figure} Figs/conicsecn.png
---
name: fig:conicsecn
---
(a) Circle, $ \epsilon = 0 $; (b) Ellipse, $ 0 < \epsilon < 1 $; (c) Parabola, $ \epsilon = 1 $; (d) Hyperbola, $ \epsilon > 1 $; (e) Family of conic sections which describe orbits. (from the book by Fowles and Cassiday)
```

{eq}`eq:conicsecn` shows that the points of closest approach and farthest distance on the elliptical orbit of a planet around the Sun, referred to as its <mark>perihelion</mark> and <mark>apohelion</mark>, occur when $ \theta = 0, \pi $ and thus $ r_{min} = a(1 - \epsilon) $, $ r_{max} = a(1 + \epsilon) $. The Earth's moon, since it orbits the Earth, has a <mark>perigee</mark> and <mark>apogee</mark> during its orbital motion.

Generally speaking, the planets of the Solar System have small orbital eccentricities. The highest value is that of Mercury, for which $ \epsilon \approx 0.206 $. The Earth's orbit is much closer to circular, having $ \epsilon \approx 0.017 $. For the Earth, $ r_{min} \approx 146 \, \text{million km} $ and $ r_{max} \approx 153 \, \text{million km} $. By contrast, Halley's comet has a highly eccentric orbit, $ \epsilon \approx 0.967 $ with a perihelion of only $ r_{min} \approx 89 \, \text{million km} $ and an apohelion beyond the orbit of Neptune. Non-recurring comets are on parabolic or hyperbolic orbits.

### Periodic Orbital Motion and Kepler's Third Law
Kepler's third law relates the orbital period of a planet to its distance from the Sun. In this section, we will demonstrate how it can be derived using Newton's laws of motion. We start with Kepler's second law, as summarised by {eq}`eq:dareadt`; the rate at which the position vector of the orbiting planet sweeps out area is proportional to its constant angular momentum:
```{math}
\dfrac{\mathrm{d}A}{\mathrm{d}t} = \dfrac{L}{2m}.
```
Now if we integrate both sides of this equation over one full orbital period $ \tau $, the left-hand side will become the area enclosed by the planet's elliptical orbit. This is equal to $ \pi a b $, where $ a $ and $ b $ are the lengths of the semi-major and semi-minor axes of the ellipse. The right-hand side will simply integrate, since it is a constant with time:
```{math}
    \pi a b = \dfrac{L}{2m} \tau.
```
Since $ b = a\,\sqrt{1-\epsilon^2} $, where $ \epsilon $ is the eccentricity of the ellipse:
```{math}
    \pi a^2 \, \sqrt{1-\epsilon^2}\,\dfrac{2m}{L} = \dfrac{L}{2m} \tau.
```
Squaring both sides:
```{math}
    4\pi^2 a^4 \, (1-\epsilon^2)\,\dfrac{m^2}{L^2} &= \tau^2 \\
    \rightarrow 4\pi^2 a^4 \, (1-\epsilon^2)\,\dfrac{1}{l^2} &= \tau^2,
```
where $ l $ is the angular momentum per unit mass, or </mark>specific angular momentum</mark>.  
Now, by comparing {eq}`eq:rvsthetaorb` and {eq}`eq:conicsecn`, we can make the identification $ a\,(1-\epsilon^2) = l^2/(GM) $. Thus we can replace a factor $ a\,(1-\epsilon^2) $ in the equation above with the constant $ l^2/(GM) $:
```{math}
    4\pi^2 a^3 \, \dfrac{l^2}{GM}\,\dfrac{1}{l^2} &= \tau^2, \\
    \rightarrow \dfrac{4\pi^2}{GM_{\odot}}\, a^3  &= \tau^2.
```
Thus the square of the orbital period for any planet or body orbiting the Sun (of mass $ M_{\odot} $) is proportional to the cube of the semimajor axis length of its elliptical orbit. The equation above tells us that if we measure $ a $ in units of the </mark>astronomical unit or AU</mark>, where $ 1 \, \text{AU} \approx 1.5 \times 10^8 \, \text{km} $ is the Earth's orbital semimajor axis, and we measure $ \tau $ in units of years (where one year is the Earth's orbital period), the relation simplifies to
```{math}
a^3 = \tau^2.
```

## Gravitational Potential
Consider a static body of mass $ M $ at the origin of a convenient coordinate system. This body exerts a gravitational force $ \mathbf{F} $, as we have studied, on another, moving particle of mass $ m $. We remind ourselves that:
```{math}
    \mathbf{F} = \dfrac{-GMm}{r^2}\,\mathbf{e}_r,
```
where symbols have their usual meaning and the radial unit vector $ \mathbf{e}_r $ points from the origin towards the position of the mass $ m $.

Let's now consider the work we need to do <mark>against</mark> the gravitational force in order to displace the mass $ m $ by a small vector displacement $ \mathbf{\mathrm{d}r} $. If we don't wish to accelerate the particle, we can apply a force $ -\mathbf{F} $ which is equal and opposite to the gravitational force. The corresponding increment of work done is thus:
```{math}
    dW = -\mathbf{F}\cdot\mathbf{\mathrm{d}r} = \dfrac{GMm}{r^2}\,\mathbf{e}_r\cdot\mathbf{\mathrm{d}r}.
```
Note that $ \mathbf{e}_r\cdot\mathbf{\mathrm{d}r} = dr $, the amount by which the radial distance of the particle changes. Thus it is only the radial component of a larger, finite displacement which contributes to the work done. To verify this, let's integrate both sides of the differential equation above between some initial and final vector positions:
```{math}
    W = \int_{r_i}^{r_f} \frac{GMm}{r^2}\,dr = \frac{-GMm}{r_f}-\frac{-GMm}{r_i}.
```
This is an important result - it tells us that the work done is <mark>independent of the path taken</mark> between the initial and final positions of the particle. Stated another way, a central force which obeys the inverse square law is said to be a <mark>conservative force</mark>.

Let's develop this further by introducing a physical definition of the gravitational potential energy of a test particle of mass $ m $ due to a stationary body of mass $ M $. We define this potential energy to be the work done in moving the particle from an infinite distance, where we take its potential energy to be zero, to a point with radial distance $ r $ from the origin (location of spherically symmetric mass $ M $). Using the above relation, we obtain the following expression for potential energy $ V $ at the particle's location at radial distance $ r $:
```{math}
    V(r) = \frac{-GMm}{r}-\lim_{r_i\rightarrow\infty} \frac{-GMm}{r_i} = \frac{-GMm}{r}.
```
Note that for finite separation $ r $, the gravitational potential energy of our system of two masses is algebraically negative.

We can go on to generally define the <mark>gravitational potential $ \Phi $</mark> as the <mark>potential energy per unit mass</mark> of a small test particle of mass $ m $ (in the presence of other masses) in the limit as $ m $ becomes vanishingly small. We define potential in this way to ensure that the presence of the mass $ m $ does not significantly change the total potential energy of the whole system. Hence:
```{math}
\Phi(\mathbf{r}) = \lim_{m\rightarrow 0} V(\mathbf{r})/m.
```
and the potential due to a point mass $ M $, at a distance $ r $, is simply $ \Phi(r) = -GM/r $.

Now consider a collection of source point masses $ M_j $ placed at corresponding positions $ \mathbf{r}_j $. Since the gravitational force at any point in space is just the vector sum of the force due to the individual masses, it follows that the total potential is just given by the sum:
```{math}
    \Phi(\mathbf{r}) = \sum_j -GM_j/|\mathbf{r}-\mathbf{r}_j|.
```

The force on a small test particle, of mass $ m $, at a given point in such a system is related to the gradient in the potential energy, according to <mark>$ {\mathbf{F}} = -\nabla V $</mark>. Similarly <mark>$ {\mathbf{g}} = -\nabla \Phi $</mark>, where $ \mathbf{F} = m\mathbf{g} $ -- that is, $ \mathbf{g} $ has dimensions of acceleration.

Note that the action of the gradient operator on a scalar function takes a simple form in Cartesian coordinates:
```{math}
    \nabla f(x,y,z) = \dfrac{\partial f}{\partial x}\,\mathbf{e}_x + \dfrac{\partial f}{\partial y}\,\mathbf{e}_y + \dfrac{\partial f}{\partial z}\,\mathbf{e}_z.
```
We will encounter the formula for the same vector, $ \nabla f $, in different coordinate systems during the problem solving classes. By definition, the small increment in value of some function $ f(x,y,z) $ when moving from some initial position $ \mathbf{r} $ to some nearby position $ \mathbf{r} + \mathbf{\mathrm{d}r} $ is given to a good approximation by $ df \approx (\nabla f)\cdot\mathbf{\mathrm{d}r} $.

Note that if some field of force $ \mathbf{F}(\mathbf{r}) $ is conservative, it means that zero work is done in moving a test particle around a closed path in space. In other words:
```{math}
    \oint \mathbf{F}\cdot\mathbf{\mathrm{d}r} = 0.
```
From our previous work on vector calculus, we know that the integral on the left-hand side, through Stokes' Theorem, is related to the surface integral of the curl of $ \mathbf{F} $ (usually written as $ \nabla \times \mathbf{F} $). Thus it follows that if the spatial dependence of a field of force satisfies $ \nabla \times \mathbf{F}

## Energy of Orbits in a Central Field

Because a central force is conservative, the total potential-plus-kinetic energy $T+V$ of a test particle will be conserved, according to:

```{math}
:label: eq:energygen
E = \frac{1}{2} m (\dot{r}^2 + r^2 \dot{\theta}^2) + V(r) = \text{constant},
```

where we once again use polar coordinates $r$ and $\theta$ to describe motion in a single plane containing the origin.

For a general central force, this equation can be written, using the auxiliary variable $u = 1/r$, as:

```{math}
E = \frac{1}{2} m l^2 \left[ \left(\frac{\mathrm{d} u}{\mathrm{d} \theta}\right)^2 + u^2\right] + V(1/u),
```

where $l$ again represents specific angular momentum.

For the specific case of a field of force which has an inverse-square dependence on distance, the potential energy is $V(r) = -k/r = -ku$, with $k$ an appropriate constant. Hence the energy equation becomes:

```{math}
E = \frac{1}{2} m l^2 \left[ \left(\frac{\mathrm{d} u}{\mathrm{d} \theta}\right)^2 + u^2\right] - ku.
```

To see how orbital parameters relate to this energy $E$, we can rearrange the above equality in order to relate increments along the orbit in $\theta$ and in $u$:

```{math}
d\theta = du \left( \frac{2E}{ml^2} + \frac{2ku}{ml^2} - u^2 \right)^{-1/2}.
```

Now defining the constants $a = -1$, $b = \frac{2k}{ml^2}$, and $c = \frac{2E}{ml^2}$, we can apply a standard integral identity:

```{math}
\theta - \theta_0 = \int du \left( c + bu + au^2 \right)^{-1/2} = \frac{1}{\sqrt{-a}} \cos^{-1} \left( \frac{b + 2au}{-\sqrt{b^2 - 4ac}} \right).
```

Now let's rearrange to get $u$ in terms of $\theta$ and the other parameters:

```{math}
u = \frac{\sqrt{b^2 - 4ac}}{-2a} \cos(-a(\theta - \theta_0)) + \frac{b}{-2a}.
```

Finally, replacing $u$ with $1/r$ and re-inserting the constant definitions gives:

```{math}
:label: eq:rvsthetaenergy
r = \frac{ml^2/k}{1 + \sqrt{1 + 2Eml^2/k^2} \cos(\theta - \theta_0)}.
```

Now compare this to the equivalent orbital trajectory given by equations {eq}`eq:conicsecn` and {eq}`eq:uorbit` (as before we can set $\theta_0 = 0$ to be the angle corresponding to the periapsis of the orbit). We observe that the eccentricity is given by:

```{math}
\epsilon = \sqrt{1 + \frac{2Eml^2}{k^2}}.
```

We also note, from the numerator of {eq}`eq:rvsthetaenergy`, that we can identify:

```{math}
a(1 - \epsilon^2) = \frac{ml^2}{k}, \\
\rightarrow a \left( \frac{-2E m l^2}{k^2} \right) = \frac{ml^2}{k}, \\
\rightarrow E = -\frac{k}{2a}.
```

This important relation tells us that for closed (elliptical) orbits, which will have algebraically negative energy $E$, the semimajor axis $a$ of the ellipse will be determined by that energy. More generally, the sign of the energy determines which type of eccentricity, and thus conic section, the orbital trajectory will follow:

- $E < 0$, $\epsilon < 1$ (closed/bound orbit: elliptical/circular)
- $E = 0$, $\epsilon = 1$ (parabolic orbit)
- $E > 0$, $\epsilon > 1$ (hyperbolic orbit)

Since $E = T + V$, closed orbits arise for the case $T < |V|$, while open orbits arise when $T \geq |V|$.

For the case of the Sun's gravitational field of force, $k = G M_{\odot} m$, and so

```{math}
E = \frac{1}{2} m v^2 - \frac{G M_{\odot} m}{r}.
```

Hence for bound orbits about the Sun, $v^2$ cannot equal or exceed the value $2 G M_{\odot} / r$.

## The Limits of Radial Motion

Since the angular momentum of a particle moving under the influence of a central field of force is a constant of the motion, we can rewrite {eq}`eq:energygen` as follows (using $\dot{\theta} = l/r^2$):

```{math}
:label: eq:energygen2
E = \frac{1}{2} m \dot{r}^2 + \left( V(r) + \frac{ml^2}{2r^2} \right) = \text{constant},
```

The grouping of the terms introduces the <mark>effective potential</mark>,  
$U(r) = V(r) + \frac{ml^2}{2r^2}$, which, in particular, contains the term $\frac{ml^2}{2r^2}$, known as the <mark>centrifugal potential</mark>. Written in this way, the energy equation tells us that the radial motion of our particle can be described by a one-dimensional equation (i.e. depending only on the radial coordinate and its time derivative, which is the radial velocity).

As for the case of simple harmonic motion, we can explore the limiting values of radial distance by setting $\dot{r} = 0$ in the energy equation, thus seeking solutions of:

```{math}
V(r) + \frac{m l^2}{2 r^2} = E.
```

A further constraint is provided by $U(r) \leq E$, since $\dot{r}^2$ is positive or zero.

If we use the central (gravitation-like) potential $V(r) = -k/r$, then this condition becomes:

```{math}
-\frac{k}{r} + \frac{m l^2}{2 r^2} = E \quad \rightarrow \quad E r^2 + k r - \frac{1}{2} m l^2 = 0.
```

The solutions of this quadratic equation in $r$ are:

```{math}
r_{\text{min}, \text{max}} = \frac{k \pm \sqrt{k^2 + 2 E m l^2}}{-2E}.
```

For a bound orbit, $E < 0$ and the two roots are both positive, representing the points of closest and furthest approach of the orbit (also known as <mark>periapsis and apoapsis</mark>, or <mark>pericentre and apocentre</mark>). In fact, the roots of the equation $U(r) = E$ can be geometrically interpreted as the points of intersection between two lines in the coordinate plane defined by radial distance and energy (see {numref}`fig:effpotplots`).

```{figure} Figs/effpotplots.jpeg
---
name: fig:effpotplots
---
A plot of the radial distance dependence of the effective potential $U$, along with some examples of total orbital energies. Axes are dimensionless, and scaled as indicated (see text).
```

As the figure shows, when $E$ (a constant of the motion) takes on its minimum possible value, $E_{\text{min}} = \frac{-k^2}{2 m l^2}$, there is just one point of intersection and just one solution to $U(r) = E$, representing a circular orbit, for which radial distance remains at a single value. For the case $E_{\text{min}} < E < 0$, there will be two points of intersection. This corresponds to a bound, elliptical orbit for which radial distance varies between a lower (periapsis) and upper (apoapsis) limit. Finally, for the case $E \geq 0$, the orbit is open (parabolic or hyperbolic) and only one point of intersection is obtained (the single periapsis, with no accompanying apoapsis).

An important point we can note from our study of planetary orbits is that orbital parameters such as semimajor axis and eccentricity are independent of the mass of the orbiting planet (recall that we are assuming a stationary Sun, with the planet mass negligible by comparison).
