# Dynamics of Systems of Particles

<img src="Figs/nasagal.jpg" width="700">

*Image Credit: NASA / ESA*


In this unit, we will develop some general physical principles which we can use to study the behaviour of systems for which we wish to describe the motion of two or more particles. Then we will apply these general rules to specific examples of such systems.

## Centre of Mass and Linear Momentum

We begin with some definitions. In general, we are considering a system of $N$ particles, each of mass $m_j$ ($j=1,2,...,N$), situated at vector positions $\mathbf{r}_j$. Using this notation, the <mark>center of mass</mark> of the system is the point with position:

```{math}
\mathbf{r}_{cm} = \dfrac{\sum_{j=1}^N m_j\,\mathbf{r}_j}{\sum_{j=1}^N m_j}.
```

Thus implies that the $x$ coordinate (in a Cartesian frame) of the centre of mass is given by:
```{math}
x_{cm}=\frac{\sum_{j=1}^N m_j\,x_j}{\sum_{j=1}^N m_j}
```
with analogous expressions for $y_{cm}$ and $z_{cm}$.

The total linear momentum of our ensemble of particles is just the sum of all the individual momenta:

```{math}
\mathbf{p} = \sum_j \mathbf{p}_j = \sum_j m_j\,\mathbf{v}_j.
```

By definition, $\mathbf{v}_j = \dot{\mathbf{r}}_j$. Hence:

```{math}
\mathbf{p} = \sum_j m_j\,\dot{\mathbf{r}}_j = M\,\dot{\mathbf{r}}_{cm},
```

where $M=\sum_j m_j$ is the total mass, and the velocity of the centre of mass is $\mathbf{v}_{cm} = \dot{\mathbf{r}}_{cm}$. Thus the total linear momentum of our system of moving particles is equivalent to their total mass multiplied by the velocity of their centre of mass, as defined above.

Let's keep to a general treatment for the moment, and imagine that any particle with integer label $i$ is subject to two types of force. The first is purely external (i.e., arises from a source completely outside the system), which we shall denote $\mathbf{F}_i$. The second type of force is the force which may be exerted on particle $i$ by any or all of the other particles in the system (for example, gravitational force). We represent this as the force on particle $i$ due to particle $j$, $\mathbf{F}_{ij}$, with, of course, $\mathbf{F}_{ii}=0$. The equation of motion for particle $i$ thus becomes:

```{math}
m_i\,\dot{\mathbf{v}}_i = \dot{\mathbf{p}}_i = \mathbf{F}_i + \sum_{j=1}^N \mathbf{F}_{ij}.
```

Now, we can in fact write $N$ versions of the above equation, for each possible value of $i$. If we added all of these together, we would obtain:

```{math}
\sum_{i=1}^N \dot{\mathbf{p}}_i = \sum_{i=1}^N \mathbf{F}_i + \sum_{i=1}^N \sum_{j=1}^N \mathbf{F}_{ij}.
```

Now in the double summation, we would expect $\mathbf{F}_{ij} = -\mathbf{F}_{ji}$ (for every action, there is an equal and opposite reaction). Hence the summed terms cancel and the double summation reduces to zero. We are left with:

```{math}
\sum_{i=1}^N \dot{\mathbf{p}}_i = \dot{\mathbf{p}} = \sum_{i=1}^N \mathbf{F}_i,
```

where by definition $\dot{\mathbf{p}}$ is equal to $M\mathbf{a}_{cm}$, the total mass of the system multiplied by the acceleration of the centre of mass.

Thus, the acceleration of the centre of mass of our system of particles is <mark>equivalent to the acceleration of a single particle of mass $M$ being acted on by the sum of all the external forces.</mark>  For the case where all the particles are moving in a region of uniform gravitational acceleration $\mathbf{g}$, this implies that $M\mathbf{a}_{cm} = M\mathbf{g}$. In other words, if a projectile moving in a region of uniform $\mathbf{g}$ were to explode during flight, the <mark>centre of mass of the pieces would follow the same path as the projectile would have followed, had it not exploded.</mark>

For the case of a system which is not acted on by *any* external forces, we would have $\dot{\mathbf{p}} = 0$ -- that is, <mark>the total linear momentum of the system is conserved in the absence of external forces.</mark>  This statement is otherwise known as the <mark>principle of conservation of linear momentum.</mark>

### Example Problem

At some point in its trajectory, a ballistic missile of mass $m$ breaks up into three fragments of mass $m/3$ each. One of the fragments continues on with an initial velocity of one-half the original velocity $\mathbf{v_0}$ of the missile just before breakup. The other two pieces go off at right angles to each other with equal speeds. Find the initial speeds of the later two fragments in terms of $\mathbf{v_0}$.

Conservation of momentum implies for the fragments (labelled $1,2,3$):

```{math}
\frac{m}{3} (\mathbf{v_1} + \mathbf{v_2} + \mathbf{v_3}) = m\mathbf{v_0}
```

Since we are given $\mathbf{v_1} = \frac{\mathbf{v_0}}{2}$, this becomes:

```{math}
\mathbf{v_2} + \mathbf{v_3} = 3 \mathbf{v_0} - \frac{\mathbf{v_0}}{2} = \frac{5}{2} \mathbf{v_0}
```

Taking the scalar product of both sides with itself, and noting that $\mathbf{v_2}\cdot\mathbf{v_3}=0$:

```{math}
v_2^2 + v_3^2 = 2v_2^2 = \left(\frac{5}{2}\right)^2 v_0^2
```

```{math}
\rightarrow v_2 = v_3 = \frac{5}{2\sqrt{2}}\,v_0 \approx 1.77 v_0.
```

## Angular Momentum and Kinetic Energy of a System

It seems logical to assign the total angular momentum, $ \mathbf{L} $, of our system as the sum of the individual angular momenta of its constituent particles:

```{math}
\mathbf{L} = \sum_i m_i\,\mathbf{r}_i \times \mathbf{v}_i.
```

To check whether or not total angular momentum is conserved, let's calculate its time derivative:

```{math}
\frac{\mathrm{d}\mathbf{L}}{\mathrm{d}t} = \sum_i m_i\,\dot{\mathbf{r}}_i \times \mathbf{v}_i + \sum_i m_i\,\mathbf{r}_i \times \dot{\mathbf{v}}_i.
```

The first summation on the right-hand side vanishes, since, by definition, $ \mathbf{v}_i = \dot{\mathbf{r}}_i $. We can rewrite the second summation as follows, noting that the vector $ m_i\,\dot{\mathbf{v}}_i $, through Newton's second law, is equal to the sum of all the forces acting on the particle with label $ i $:

```{math}
\frac{\mathrm{d}\mathbf{L}}{\mathrm{d}t} = \sum_i \mathbf{r}_i \times (\mathbf{F}_i + \sum_j \mathbf{F}_{ij}).
```

Now consider a pair of distinct particles with labels $ i $ and $ j $. The sum of the two corresponding terms in the double summation, involving their mutual internal forces, is $ \mathbf{r}_i \times \mathbf{F}_{ij} + \mathbf{r}_j \times \mathbf{F}_{ji} $. Since $ \mathbf{F}_{ij} = -\mathbf{F}_{ji} $, this is equal to $ (\mathbf{r}_i - \mathbf{r}_j) \times \mathbf{F}_{ij} $. Now, the difference $ (\mathbf{r}_i - \mathbf{r}_j) $ is simply the vector directed from the location of particle $ j $ to particle $ i $. If the internal forces are of a central nature, i.e., collinear with the vector separations between the pairs of particles in our system, then this cross product vanishes. Hence, we are left with:

```{math}
:label: eq:dangmom
\frac{\mathrm{d}\mathbf{L}}{\mathrm{d}t} = \sum_i \mathbf{r}_i \times \mathbf{F}_i.
```

Therefore, <mark>in the absence of external forces, the total angular momentum of the system is conserved</mark>, as well as its total linear momentum.

When the external forces are non-zero, Equation {eq}`eq:dangmom` indicates that the total angular momentum will change with time, and its rate of change is given by the total moment of force, or <mark>torque</mark>, acting on the system.

The concept of the centre of mass can help us gain a little more insight into the nature of the individual motions which comprise the total angular momentum. We can rewrite the position of each particle as the sum of the position of the centre of mass plus the position of the particle relative to the centre of mass:

```{math}
\mathbf{r}_i = \mathbf{r}_{cm} + \overline{\mathbf{r}}_i.
```

Taking the derivative with time of both sides of this equation reveals that, as expected, the velocity of each particle is the sum of the centre-of-mass velocity plus the velocity of the particle relative to the centre of mass:

```{math}
\mathbf{v}_i = \mathbf{v}_{cm} + \overline{\mathbf{v}}_i.
```

Using this notation, the total angular momentum becomes:

```{math}
\mathbf{L} &= \sum_{i=1}^N m_i\,(\mathbf{r}_{cm} + \overline{\mathbf{r}}_i) \times (\mathbf{v}_{cm} + \overline{\mathbf{v}}_i) \\
&= \sum_{i=1}^N m_i\,(\mathbf{r}_{cm} \times \mathbf{v}_{cm}) + \sum_{i=1}^N m_i\,(\mathbf{r}_{cm} \times \overline{\mathbf{v}}_i) \\
&+ \sum_{i=1}^N m_i\,(\overline{\mathbf{r}}_{i} \times {\mathbf{v}}_{cm}) + \sum_{i=1}^N m_i\,(\overline{\mathbf{r}}_{i} \times \overline{\mathbf{v}}_i).
```

Let us now analyse each of the four final summations in the equation above:

- The first summation equals $ \left(\sum_{i=1}^N m_i\right)\,(\mathbf{r}_{cm} \times \mathbf{v}_{cm}) $, and is the <mark>angular momentum associated with a particle of mass equal to the total mass of the system, which moves coincidentally with the centre of mass of the system.</mark>

- The second summation equals $ \mathbf{r}_{cm} \times \sum_{i=1}^N m_i\,\overline{\mathbf{v}}_i $. Since, by definition $ \overline{\mathbf{v}}_i = \mathbf{v}_i - \mathbf{v}_{cm} $, the factor $ \sum_{i=1}^N m_i\,\overline{\mathbf{v}}_i = \mathbf{p} - M \mathbf{v}_{cm} $, where $ \mathbf{p} $ is the total linear momentum of the system, and $ M $ the total mass. But by definition $ \mathbf{p} = M \mathbf{v}_{cm} $, and thus the second summation in the expansion for total angular momentum is zero.

- The third summation equals $ \left(\sum_{i=1}^N m_i\,\overline{\mathbf{r}}_{i}\right) \times {\mathbf{v}}_{cm} $. Since $ \overline{\mathbf{r}}_{i} = \mathbf{r}_i - \mathbf{r}_{cm} $, this can be written as $ \left(\sum_{i=1}^N m_i\,(\mathbf{r}_i - \mathbf{r}_{cm})\right) \times {\mathbf{v}}_{cm} $. But since by definition $ \sum_{i=1}^N m_i\,\mathbf{r}_i = M \mathbf{r}_{cm} $, the third summation also evaluates to zero.

- The fourth and final summation equals $ \sum_{i=1}^N m_i\,(\overline{\mathbf{r}}_{i} \times \overline{\mathbf{v}}_i) $, which can be thought of as the <mark>angular momentum carried by the motion of all the particles relative to the motion of the centre of mass.</mark>

We can summarise the results above with the statement that the total angular momentum of a system can be expressed as the sum of two terms. The first is the angular momentum of a fictitious particle with mass equal to the total mass of the system whose position and velocity coincide with the actual centre of mass. This component of the total angular momentum is sometimes referred to as `orbital angular momentum'.

The second component of a system's total angular momentum, as stated above, is the angular momentum carried by the motions of the particles relative to that of the centre of mass. This component of the total angular momentum is sometimes referred to as 'spin angular momentum'.

We will now consider an appropriate definition of the <mark>total kinetic energy</mark> of our system of particles. Again, it seems logical to adopt a definition of the sum of the individual kinetic energies of all the constituent particles:

```{math}
T = \sum_{i=1}^N \frac{1}{2} m_i v_i^2 = \sum_{i=1}^N \frac{1}{2} m_i \mathbf{v}_i \cdot \mathbf{v}_i.
```

As for the case of angular momentum, we can express the system's total kinetic energy as the sum of two energy terms as follows (proof is fairly straightforward using the definition of $ \overline{v}_i $, and is left to the reader):

```{math}
T = \frac{1}{2} M v_{cm}^2 + \sum_{i} \frac{1}{2} m_i \overline{v}_i^2.
```

The first term is the kinetic energy of translation of the whole system, and the second is the kinetic energy of motion relative to the centre of mass.

<div id="sec:2bodyp"></div>

## The Two-Body Problem and Reduced Mass

```{figure} Figs/twobody.png
---
name: fig:twobody
---
A system of two bodies with masses $m_1$ and $m_2$, with respective positions $\overline{\mathbf{r}}_1$ and $\overline{\mathbf{r}}_2$ relative to the centre of mass.
```

Consider a system consisting of two bodies of masses $m_1$ and $m_2$, as shown in {numref}`fig:twobody`. Using our previous notation, we can assign these masses with positions $\overline{\mathbf{r}}_1$ and $\overline{\mathbf{r}}_2$ relative to the centre of mass of the system, which we take to be at the origin for convenience. The position of the centre of mass lies somewhere on the line connecting the two bodies, since we must satisfy the definition of the centre of mass position:

```{math}
  \dfrac{m_1}{m_1+m_2}\,\overline{\mathbf{r}}_1 + \dfrac{m_2}{m_1+m_2}\,\overline{\mathbf{r}}_2 = \mathbf{0} \quad \Rightarrow \quad m_1\,\overline{\mathbf{r}}_1 = - m_2 \, \overline{\mathbf{r}}_2.
```

Now, if the two bodies exert a gravitational force on each other, the equation of motion for bodies 1 and 2 can be written as:

```{math}
:label: eq:accelind
    m_1\,\dfrac{\mathrm{d}^2\overline{\mathbf{r}}_1}{\mathrm{d}t^2} = \mathbf{F}_{12} = -\dfrac{G m_1 m_2}{R^3} \mathbf{R}, \quad
    m_2\,\dfrac{\mathrm{d}^2\overline{\mathbf{r}}_2}{\mathrm{d}t^2} = \mathbf{F}_{21} =  \dfrac{G m_1 m_2}{R^3} \mathbf{R}
```

where $\mathbf{R}=\overline{\mathbf{r}}_1-\overline{\mathbf{r}}_2$ is the vector going from $m_2$ to $m_1$, as shown.

It is interesting to consider the dynamical evolution of the system by calculating the acceleration of the vector separation $\mathbf{R}$, which is equal to $\ddot{\mathbf{R}} = \dfrac{\mathrm{d}^2\overline{\mathbf{r}}_1}{\mathrm{d}t^2}-\dfrac{\mathrm{d}^2\overline{\mathbf{r}}_2}{\mathrm{d}t^2}$. Using the equations above, we find that this expression is equivalent to:

```{math}
    \ddot{\mathbf{R}} = -\dfrac{G m_1 m_2}{R^3}\mathbf{R} \left(\dfrac{1}{m_1} + \dfrac{1}{m_2}\right).
```

If we now define the <mark>reduced mass $\mu$</mark> of the system through $\dfrac{1}{\mu} = \dfrac{1}{m_1} + \dfrac{1}{m_2}$, or equivalently $\mu = \dfrac{m_1 m_2}{m_1 + m_2}$, we obtain:

```{math}
    \mu\,\ddot{\mathbf{R}} = -\dfrac{G m_1 m_2}{R^2}\mathbf{e}_R,
```

where the unit vector $\mathbf{e}_R = \mathbf{R}/|\mathbf{R}|$. This equation tells us that when we consider the motion of either body </mark>relative to the other</mark>, as represented by the behaviour of the vector $\mathbf{R}$, the acceleration is always radially inwards towards the centre of mass and has magnitude $\dfrac{G m_1 m_2}{\mu R^2} = \dfrac{G M}{R^2}$, where $M = m_1 + m_2$.

Therefore, for the simple case where $R$ is constant, the angular velocity $\Omega$ with which both bodies rotate about the centre of mass (whose acceleration must be zero) must satisfy:

```{math}
    R \Omega^2 = \dfrac{G M}{R^2},
```

implying that the period of rotation is $P = \dfrac{2\pi}{\Omega} = \sqrt{\dfrac{4\pi^2}{GM}R^3}$.

Previously, when considering the orbits of planets about the Sun, we assumed that the Sun was fixed in its position. This is equivalent to assuming that the orbiting body has a mass very small compared to the Sun, or, in the present context, that the reduced mass of the Sun-planet system is approximately equal to $M_{\odot}$, since $m \ll M_{\odot}$. The above equation shows us that there is a small correction to the orbital period when one more accurately considers the motion of the planet about the actual centre of mass of the Sun-planet system. If we express $M$ in units of Solar mass, and orbital radius $a$ in units of astronomical units (AU, the mean distance from the Earth to the Sun), we obtain a formula for the orbital period in units of years:

```{math}
    P/\mathrm{yr} = \left(\dfrac{M}{M_{\odot}}\right)^{-1/2} \left(\dfrac{a}{\mathrm{AU}}\right)^{3/2}.
```

For most planets in the Solar System, the added mass term in this formula for orbital period makes very little difference – for example, the Earth-to-Sun mass ratio is only $\sim 1/330000$. For the most massive planet, Jupiter, this ratio is $\sim 1/1000$, which changes the ‘fixed Sun’ value for Jupiter's orbital period by about $0.05\%$. One can note, however, that for systems where the masses of the two bodies are more comparable, this correction would be much more important to take into account.

### Binary Star Systems

Half of all the stars in our galaxy are actually two-body systems, in which two stars revolve about their common centre of mass. The distances between the component stars can vary widely. The star Sirius is actually a binary system consisting of the luminous star known as Sirius, of mass $\sim 2.1\,M_{\odot}$; and a much fainter white dwarf star, of mass $\sim 1.05\,M_{\odot}$, which is situated at distances $\sim 20\,\mathrm{AU}$ from its bright companion. The corresponding orbital period of the system is $\sim 50 \,\mathrm{yr}$.

The X-ray source Cygnus X-1 is a binary system consisting of a $\sim20\,M_{\odot}$ star whose companion is a black hole of similar mass. Their distance of separation is a comparatively small ~$0.2\,\mathrm{AU}$. Matter from the outer layers of the larger `regular' star in this system is being accreted by the black hole. As the material falls towards the black hole, it forms an accretion disc. As the matter in this disc orbits the black hole, it can lose energy by frictional heating and crash down into it, heating to temperatures exceeding tens of millions of degrees which makes the hot gas radiate strongly in the X-ray waveband.


```{figure} Figs/Cygnus_X-1.png
---
name: Cygnus_X-1
---
Artist's impression of Cygnus X-1 (Credit: ESA/HST)
```

## Dynamics of Collisions

When two bodies collide, the forces they exert on each other during the time of contact can be considered internal forces in the system consisting of the two bodies alone. Thus total linear momentum must be conserved and the total vector momentum of the bodies before and after the collision must be equal:

```{math}
m_1\,\mathbf{v}_1 + m_2\,\mathbf{v}_2 = m_1\,\mathbf{v'}_1 + m_2\,\mathbf{v'}_2.
```

In terms of the energy balance of the system, we can write:

```{math}
\dfrac{1}{2} m_1 v_1^2 + \dfrac{1}{2} m_2 v_2^2 = \dfrac{1}{2} m_1 {v'_1}^2 + \dfrac{1}{2} m_2 v_2'^2 + Q,
```

where $Q$ indicates that part of the initial total kinetic energy which is dissipated as, for example, heat energy during the collision. If $Q=0$, no energy loss occurs and the collision is said to be </mark>elastic</mark>. The cases $Q>0$ and $Q<0$ respectively represent </mark>exoergic</mark> and </mark>endoergic</mark> collisions.

#### Direct Collisions (Single Axis of Motion)

If our two colliding particles are constrained to move back and forth along only one coordinate axis -- let us call it the $x$ axis -- the momentum conservation reads:

```{math}
:label: eq:momcons1d
m_1\,\dot{x}_1 + m_2\,\dot{x}_2 = m_1\,\dot{x}'_1 + m_2\,\dot{x}'_2.
```
  
In principle, we can calculate the velocities after the collision (the primed quantities) if we know the velocities before the collision and if we also know something about the energy difference $Q$. It is convenient to define a </mark>coefficient of restitution $\epsilon$</mark>, which is the ratio of the speed at which the bodies approach each other before collision to the speed at which they recede from each other after the collision:

```{math}
\epsilon = \dfrac{|\dot{x}'_2-\dot{x}'_1|}{|\dot{x}_2-\dot{x}_1|} = \dfrac{v'}{v}.
```

For elastic collisions ($Q=0$), $\epsilon=1$.

For <mark>totally inelastic collisions</mark>, the bodies stick together after colliding and so $\epsilon=0$. More generally, of course, $\epsilon$ will lie somewhere between $0$ and $1$.

From the momentum conservation equation, we obtain:

```{math}
\dot{x}'_2 = \dfrac{(m_1/m_2)\,(\dot{x}_1-\dot{x}'_1) + \dot{x}_2}.
```

Substituting this into the definition of $\epsilon^2$, we get:

```{math}
\epsilon^2\,(\dot{x}_2-\dot{x}_1)^2 &= (\dot{x}'_2-\dot{x}'_1)^2 \\
\rightarrow \epsilon^2\,(\dot{x}_2-\dot{x}_1)^2 &= ((m_1/m_2)\,(\dot{x}_1-\dot{x}'_1) + \dot{x}_2 -\dot{x}'_1)^2  \\
\rightarrow \epsilon^2\,(\dot{x}_2-\dot{x}_1)^2 &= ((m_1/m_2 + 1)\,(\dot{x}_1-\dot{x}'_1) + (\dot{x}_2 -\dot{x}_1))^2  \\
\rightarrow 0  &= (m_1/m_2 + 1)^2\,(\dot{x}_1-\dot{x}'_1)^2 +  \\
    & 2 (m_1/m_2 + 1)\,(\dot{x}_2 -\dot{x}_1)\,(\dot{x}_1-\dot{x}'_1) +  (1-\epsilon^2)\,(\dot{x}_2-\dot{x}_1)^2 
```

Solving this quadratic equation in $(\dot{x}_1-\dot{x}'_1)$, we find the velocity after collision. It is appropriate to choose the more physically meaningful solution which corresponds to:

```{math}
:label: eq:solx1pdot
\dot{x}'_1 = \dfrac{(m_1-\epsilon m_2)\,\dot{x_1} + (m_2 + \epsilon m_2)\,\dot{x_2}}{m_1+m_2}.
```

This is an appropriate choice because, for the case $\epsilon=1,m_1=m_2,\dot{x}_2 = -\dot{x}_1$, it correctly predicts that the bodies will rebound after collision, and change direction ($\dot{x}'_1 = -\dot{x}_1$). The solution for $\dot{x}'_2$ that accompanies Equation {eq}`eq:solx1pdot` is:

```{math}
:label: eq:solx2pdot
\dot{x}'_2 = \dfrac{(m_1 + \epsilon m_1)\,\dot{x_1} + (m_2 - \epsilon m_1)\,\dot{x_2}}{m_1+m_2}.
```

For an elastic collisions with $\epsilon=0$, where the bodies stick together after collision, we find that the post-collision velocities agree, $\dot{x}'_2 = \dot{x}'_1$, as expected. For the elastic case $\epsilon=1, m_1=m_2$, the bodies simply exchange velocities after collision -- $\dot{x}'_1 = \dot{x}_2, \dot{x}'_2 = \dot{x}_1$.

#### Impulse

The concept of impulse is usually associated with forces which act for relatively short times, such as the forces between colliding bodies. If the bodies are in contact for an interval of time $t_1\rightarrow t_1 + \Delta t$, and the force acting on one body is $\mathbf{F}$, then the corresponding change in its momentum is:

```{math}
\Delta({m\mathbf{v}}) =\int_{t_1}^{t_1 + \Delta t} \mathbf{F}\,dt.
```

The time integral of force in this equation is known as the </mark>impulse</mark>, and has units of momentum.

#### Oblique Collisions

In this section, we consider the more general case of collisions where the motion of the colliding bodies is not confined to a straight line. We start by considering the case of a particle of mass $m_1$ with initial velocity $\mathbf{v}_1$ which strikes a particle of mass $m_2$ which is initially at rest. The conservation of total momentum must still apply, provided we use the vector sum of momenta.

```{math}
m_1\,\mathbf{v}_1 = m_1\,\mathbf{v}'_1 + m_2\,\mathbf{v}'_2.
```

The energy balance may be written:

```{math}
\frac{1}{2} m_1 v_1^2 = \frac{1}{2} m_1\,{v}'^2_1 + \frac{1}{2} m_2\,{v}'^2_2 + Q,
```

where we again use the symbol $Q$ to denote total energy loss or gain.

For the special case $m_1 = m_2 = m$, the energy balance condition may be written (now using symbols for momenta $\mathbf{p} = m \mathbf{v}$, with magnitude $p = m v$):

```{math}
p_1^2 = {p}'^2_1 + {p}'^2_2 + 2 m Q.
```

Since $\mathbf{p}_1 = \mathbf{p}'_1 + \mathbf{p}'_2$, $p_1^2$ is also equal to:

```{math}
\mathbf{p}_1 \cdot \mathbf{p}_1 = (\mathbf{p}'_1 + \mathbf{p}'_2)\cdot(\mathbf{p}'_1 + \mathbf{p}'_2)
= {{p}'_1}^2 + {{p}'_2}^2 + 2 \mathbf{p}'_1 \cdot \mathbf{p}'_2.
```

Comparing the last two equations shows that $\mathbf{p}'_1 \cdot \mathbf{p}'_2 = m Q$. Thus for elastic collisions where $Q=0$, the final directions of motion of the incident and the target particle are orthogonal.

### Centre Of Mass Coordinates

{numref}`fig:cofmcoord` shows the same collision between two particles in two different coordinate frames. In the so-called laboratory frame, we observe an incident particle of mass $ m_1 $ and velocity $ \mathbf{v}_1 $ striking a stationary target particle of mass $ m_2 $. After the collision, both particles are in motion and their velocities make angles $ \phi_1 $ and $ \phi_2 $ with the direction of the incident velocity.


```{figure} Figs/cofmcoord.png
---
name: fig:cofmcoord
---
The same collision viewed in laboratory (left) and centre-of-mass (right) coordinates.
```


Now, if we consider the same collision in the centre-of-mass coordinates, in which the centre of mass is stationary, the picture changes. We recall that for a system such as this, with two particles and no external forces, the centre of mass does not accelerate and remains situated on the line connecting the two particles. In the frame of reference where the centre of mass is stationary, the total momentum before collision and after collision must be zero. Thus, in the centre-of-mass frame, the particles move in opposite directions before the collision, both approaching the stationary centre of mass. And after the collision, their velocities make the same angle $ \theta $ with their initial directions of motion.

The momentum conservation and energy balance in the centre-of-mass coordinates can be written:

```{math}
\overline{\mathbf{p}}_1 + \overline{\mathbf{p}}_2 = 0 = \overline{\mathbf{p}}_1' + \overline{\mathbf{p}}_2',
```

```{math}
\dfrac{\overline{{{p}}_1}^2}{2 m_1} + 
\dfrac{\overline{{{p}}_2}^2}{2 m_2} = 
\dfrac{\overline{{{p}}'_1}^2}{2 m_1} + 
\dfrac{\overline{{{p}}'_2}^2}{2 m_2} + Q.
```

Since the first equation implies the momentum magnitude relations
```{math}
\overline{{p}_1}^2 = \overline{{p}_2}^2, \quad \overline{{p}'_1}^2 = \overline{{p}'_2}^2,
```
the energy balance becomes:

```{math}
\dfrac{\overline{{{p}}_1}^2}{2\mu} 
= 
\dfrac{\overline{{{p}}'_1}^2}{2 \mu} + 
Q,
```
where we use the usual definition of reduced mass $ \mu $, introduced in section on [two-body](#sec:2bodyp) methods.

```{figure} Figs/labcmvels.png
---
name: fig:labcmvels
---
The relation between velocity in the laboratory and centre-of-mass frames.
```

Let us now consider the relationship between the velocity in the laboratory and the centre-of-mass frames of reference.  {numref}`fig:labcmvels` illustrates the definition of the post-collision velocity in these two frames:

```{math}
\overline{\mathbf{v}}'_1 = \mathbf{v}'_1 - \mathbf{v}_{cm} = \mathbf{v}'_1 - \dfrac{m_1 \mathbf{v}_1}{m_1 + m_2}
```

The diagram shows, using the orientation angles indicated, that:

```{math}
v'_1 \, \sin{\phi_1} = \overline{v'}_1 \, \sin\theta, \quad
v'_1 \, \cos{\phi_1} = \overline{v'}_1\, \cos\theta + v_{cm}
```

Dividing these equations gives us a reasonably simple relation between the scattering angles in the two frames:

```{math}
\tan{\phi_1} = \dfrac{\sin\theta}{\cos\theta + \gamma},
```
where $ \gamma = v_{cm}/\overline{v'}_1 = \dfrac{m_1 {v}_1/\overline{v'}_1}{m_1 + m_2} $.

For the special case of elastic collision where $ Q = 0 $, the energy conservation equation tells us that, in the centre-of-mass frame, $ \overline{p}_1 = \overline{p'}_1 $ — that is, $ \overline{v}_1 = \overline{v'}_1 $. It follows that:

```{math}
\overline{v'}_1 = \overline{v}_1 = v_1 - v_{cm} = \dfrac{m_2 v_1}{m_1 + m_2}.
```

We then obtain:

```{math}
\gamma = \dfrac{m_1 {v}_1}{m_1 + m_2} \dfrac{m_1 + m_2}{m_2 v_1} = \dfrac{m_1}{m_2}.
```

This value of $ \gamma $ for the elastic collision case indicates that, for the case where the target mass $ m_2 $ is extremely large compared to the mass $ m_1 $ of the incident particle, $ \gamma \rightarrow 1 $ and the two angles $ \theta $ and $ \phi $ approach equal value. For the case where these masses are equal, $ \gamma = 1 $ and

```{math}
\tan\phi_1 = \tan\left(\dfrac{\theta}{2}\right),
```
i.e., the scattering angle in the centre-of-mass frame is twice the value it has in the lab frame. Similar reasoning applied to the target particle shows that it has a scattering angle of $ (\pi-\theta)/2 $ in the laboratory system. Therefore, when an incident particle strikes a target of equal mass in the lab frame, the post-collision velocities are perpendicular to each other.

## Rotation of Rigid Bodies

A rigid body may be considered a system of particles (mass elements) whose positions relative to each other remain fixed. In this section, we consider the properties of rotational motion of a rigid body, for the case where the axis of rotation maintains a fixed direction in space.

### Centre of Mass of a Rigid Body

Our previous definition of the centre of mass of a system of discrete particles can be generalized by an integral definition for a rigid, extended body. Using Cartesian coordinates, the position of the centre of mass thus becomes:

```{math}
x_{cm} = \dfrac{\int_{\mathcal{V}} \rho\,x\,d\mathcal{V}}
                   {\int_{\mathcal{V}} \rho\,d\mathcal{V}}, \quad
y_{cm} = \dfrac{\int_{\mathcal{V}} \rho\,y\,d\mathcal{V}}
                   {\int_{\mathcal{V}} \rho\,d\mathcal{V}}, \quad
z_{cm} = \dfrac{\int_{\mathcal{V}} \rho\,z\,d\mathcal{V}}
                   {\int_{\mathcal{V}} \rho\,d\mathcal{V}},
```

where $\rho$ is the local density of the body and $d\mathcal{V}$ is an infinitesimal volume element.

For the case of a body which takes the form of a thin shell, we could replace the mass element in the above definitions by $\rho_S\,dS$ where $\rho_S$ is a surface density (mass per unit area) and $dS$ is a surface element.  
For the case of a body which takes the form of a thin wire, we could replace the mass element in the above definitions by $\rho_{\ell}\,d\ell$ where $\rho_{\ell}$ is a linear density (mass per unit length) and $d{\ell}$ is a length element.

If a rigid body has a mass distribution which is symmetric about a plane, then its centre of symmetry will lie in that same plane. To demonstrate this, we can consider a body which is symmetric about the $xy$-plane. We can divide the body up into pairs of equal mass elements, $dM_i$ and $dM_i'$, which have equal and opposite $z$-coordinates, $z_i$ and $z_i' = -z_i$. The $z$-coordinate of its centre of mass will thus be:

```{math}
z_{cm} = \dfrac{\int (z_i\,dM_i + z_i'\,dM_i')}{\int (dM_i + dM_i')} = 0.
```

A similar result applies for a body which has an axis or a line of symmetry.

#### Solid Homogeneous Hemisphere

A body which has the form of a solid half-sphere with a uniform density $\rho$ will have symmetry about the radius which is perpendicular to its plane face. Hence its centre of mass will lie on this line, which we will adopt as the $z$-axis.

```{figure} Figs/hemisphere.png
---
name: fig:hemisphere
---
Coordinates for calculating the centre of mass of a solid hemisphere.
```

Now we can divide the hemisphere into a series of thin circular discs (see {numref}`fig:hemisphere`) of infinitesimal thickness $ dz $ and variable radius $ r = \sqrt{a^2 - z^2} $, where $ a $ is the radius of the hemisphere and $ z $ is the axial coordinate of the disc. The mass of a disc will thus be:
```{math}
dM = \pi \rho \, r^2 \,dz.
```
Integrating to obtain the specific axial location of the centre of mass gives:
```{math}
z_{cm} = \dfrac{\int_{z=0}^a z\,\pi \rho \, {(a^2 - z^2)} \,dz}
    {\int_{z=0}^a \pi \rho \, {(a^2 - z^2)} \,dz} \notag
    = \dfrac{\pi \rho \, {(a^2 \,\dfrac{1}{2} a^2 - \dfrac{1}{4} a^4)}}
    {\pi \rho \, {(a^2 a - \dfrac{1}{3} a^3)}} = \dfrac{3}{8} a.
```

#### Thin Hemispherical Shell

For the case of a thin hemispherical shell, we use the angular coordinate $ \theta $ (see {numref}`fig:hemisphere`) to divide the shell's surface into circular strips of mass $ \rho_S \, dS = 2\pi \rho_S a\, \cos\theta\, a\, d\theta $.

Note that $ \cos\theta\,d\theta = d(\sin\theta) $. Since 
$\sin\theta = z/a$, then $ d(\sin\theta) = dz/a $. Therefore:
```{math}
z_{cm} = \dfrac{\int_{z=0}^a \, 2\pi \rho_S a\, z\, dz}
                   {\int_{z=0}^a \, 2\pi \rho_S a\, dz} = \dfrac{1}{2} a.
```

#### Thin Semicircular Lamina

A <mark>lamina</mark> is a body that has the form of a thin layer or plate. Consider a semicircular lamina of uniform density $ \rho $ which occupies the following points in Cartesian space:
```{math}
x = R \cos{\phi}, ~~ z = R \sin{\phi}, ~~ -\Delta y/2 \leq y \leq \Delta y/2,
```
where the cylindrical coordinates satisfy $ 0 \leq R \leq a $, where $ a $ is the radius of the semicircle, and $ 0 \leq \phi \leq \pi $. Using the cylindrical coordinates, we can calculate the $ z $-coordinate of the centre of mass as follows:
```{math}
z_{cm} = \dfrac{\int_{R=0}^a \int_{\phi=0}^\pi \, z \rho \, R \, dR \, d\phi}{\int_{R=0}^a \int_{\phi=0}^\pi \, \rho \, R \, dR \, d\phi} \notag
    = \dfrac{\int_{R=0}^a \, R^2\, dR \, \int_{\phi=0}^\pi \, \sin{\phi} \, d\phi}{\int_{R=0}^a R\, dR \, \int_{\phi=0}^\pi \, d\phi} \notag
    = \dfrac{\frac{1}{3}\,a^3\cdot 2}{\frac{1}{2}\,a^2\cdot \pi}
    = \dfrac{4a}{3\pi}.
```

### Moment of Inertia

Consider now the rotation of a rigid body about a fixed axis, which we shall refer to as the $ z $-axis. The path of a single point in the moving body may be described by coordinates $ (x_i, y_i, z_i) $ where $ z_i $ remains fixed and the other coordinates describe a circular path $ x_i^2 + y_i^2 = r_i^2 $, where $ r_i $ is the constant perpendicular distance of the point from the axis of rotation.

The speed of the element of mass $ m_i $ located at this point will be
```{math}
v_i = r_i\, \omega,
```
where $ \omega $ is the magnitude of the angular velocity of rotation. The individual velocity components of $ m_i $ are:
```{math}
\dot{x}_i = -v_i\, \sin\phi_i, ~~~ \dot{y}_i = v_i\, \cos\phi, ~~~ \dot{z}_i = 0.
```
Here the azimuthal angle $ \phi_i $ is defined by $ x_i = r_i\, \cos\phi_i, y_i = r_i\, \sin\phi_i $.

These velocity components can also be calculated by using the vector identity:
```{math}
\mathbf{v}_i = \mathbf{\omega} \times \mathbf{r}_i,
```
with $ \mathbf{\omega} = \omega\, \mathbf{e_z} $.

Using these definitions, we can now calculate the <mark>total kinetic energy of rotation</mark> for the rigid body:
```{math}
T_{rot} = \sum_i \, \frac{1}{2} m_i v_i^2 \notag
            = \frac{1}{2}\, (\sum_i \, m_i r_i^2) \, \omega^2 \notag
            = \frac{1}{2}\, I_z \, \omega^2,
```
where $ I_z = \sum_i \, m_i r_i^2 $ is known as the body's <mark>moment of inertia</mark> about its axis of rotation.

The angular momentum of a single mass element is
$ \mathbf{r}_i \times m_i \mathbf{v}_i $. The $ z $-component of this cross product is
```{math}
m_i (x_i \dot{y}_i - y_i \dot{x}_i) = m_i (x_i^2 + y_i^2) \omega
= m_i r_i^2 \omega.
```
The total $ z $-component of the angular momentum, is thus:
```{math}
L_z = \sum_i m_i r_i^2 \omega = I_z \omega.
```
Since the body in question is constrained to rotate about the $ z $-axis, the rate of change of its angular momentum component in the $ z $-direction is equal to the corresponding component of the moment of any external forces in that direction:
```{math}
N_z = \dfrac{\mathrm{d}L_z}{\mathrm{d}t} = \dfrac{\mathrm{d}(I_z \omega)}{\mathrm{d}t}.
```
For a rigid body, $ I_z $ is constant, so $ N_z = I_z\, \dfrac{\mathrm{d}\omega}{\mathrm{d}t} $.

We can therefore consider physical quantities defined for translational motion alongside their counterparts for rotational motion:

| Quantity         | Linear Expression                 | Rotational Expression                  |
|------------------|-----------------------------------|-----------------------------------------|
| Momentum         | $p_x = m v_x$                     | $L_z = I_z \omega$                      |
| Force            | $F_x = m \dot{v}_x$               | $N_z = I_z \dot{\omega}$                |
| Kinetic Energy   | $T = \dfrac{1}{2} m v^2$          | $T_{\text{rot}} = \dfrac{1}{2} I_z \omega^2$ |


For bodies which are extended or continuous (as opposed to collections of discrete particles), we can generalize the previous definition of the moment of inertia from a sum to an integral:
```{math}
I = \int R^2\,dM,
```
where $ dM = \rho \, \mathcal{V} $ is a mass element, whose volume is $ d\mathcal{V} $, at a location where the density is $ \rho $. Let us now consider some examples of how we calculate the moment of inertia of different bodies.

#### Moment of Inertia of a Thin Rod

```{figure} Figs/rodmoi.png
---
name: fig:rodmoi
---
oordinates for calculating the moment of inertia of a rod: (a) about one end and (b) about the centre of the rod.
```

{numref}`fig:rodmoi` shows appropriate coordinates for calculating the moment of inertia of a thin rod of total mass $m$ and length $a$. In the first example, the rod rotates about an axis perpendicular to itself which passes through one of its ends. The appropriate moment of inertia is thus:
```{math}
\int_{x=0}^a\,(m/a)\,x^2\,dx = ma^2/3.
```
In the second example, the axis of rotation passes through the midpoint of the rod, and the moment of inertia becomes:
```{math}
\int_{x=-a/2}^{a/2}\,(m/a)\,x^2\,dx = ma^2/12.
```

### Moment of Inertia of a Thin Spherical Shell

Consider a thin spherical shell rotating about the $z$ axis, which passes through the origin, taken to be the centre of the sphere. Using spherical coordinates and assuming the shell has a uniform surface density $\sigma$ and radius $a$, a surface element can be expressed as $dS = a^2\,\sin\theta\,d\theta\,d\phi$.

The shell can be divided into circular strips whose surface elements all have a constant value of the coordinate $z$, which equals
$a\,\cos\theta$. The perpendicular distance of any point on such a strip from the $z$ axis is $R=a\,\sin\theta=\sqrt{a^2-z^2}$. The mass of a strip is
$dM =  2\pi\sigma R \,a\,d\theta$. Hence the integrand
$R^2 dM = R^3\,(2\pi\sigma \,a\,d\theta) = (2\pi\sigma \,a^4\,\sin^3\theta\,d\theta)$.

The moment of inertia is thus:
```{math}
2\pi\sigma\,a^4\,\int_{\theta=0}^\pi   \sin^3\theta\,d\theta 
    = 2\pi\sigma\,a^4\,\int_{1}^{-1}   -(1-u^2)\,du,
```
using auxiliary variable $u=\cos\theta$. We finally obtain:
```{math}
2\pi\sigma\,a^4\,\int_{-1}^{1}   (1-u^2)\,du = 2\pi\sigma\,a^4\,(2 - \frac{1}{3}\cdot 2) = (8\pi/3)\,\sigma\,a^4.
```
This final evaluation can also be written as
$\frac{2}{3} M_s a^2$, where the mass of the shell is $M_s = 4\pi \sigma a^2$.

### The Parallel Axis Theorem
Consider the moment of inertia about the $z$ axis for a rigid body of arbitrary shape, which can be considered to be composed of mass elements $\delta m_i$:
```{math}
I_z = \sum_i \, \delta m_i\,(x_i^2 + y_i^2).
```
Using our previous `overbar' notation for coordinates relative to the body's centre of mass, we can write $x_i = x_{cm} + \overline{x}_i$, with a similar expression for the $y$ coordinate. Hence our moment of inertia becomes:
```{math}
I_z &= \sum_i \, \delta m_i\,((x_{cm} + \overline{x}_i)^2 +
     (y_{cm} + \overline{y}_i)^2) \notag \\
     &= \sum_i \, \delta m_i\,(\overline{x}_i^2 + \overline{y}_i^2) +
        \sum_i \, \delta m_i\,({x}_{cm}^2 + {y}_{cm}^2) \notag \\
     &+ 2 x_{cm}\,\sum_i \, \delta m_i\,\overline{x}_i
      + 2 y_{cm}\,\sum_i \, \delta m_i\,\overline{y}_i.
```
In the final expression above, the first summation is simply the moment of inertia taken about an axis -- let's label it $z'$ -- which is parallel to the $z$ axis and which passes through the body's own centre of mass. The second summation is the total mass of the body multiplied by the square of the perpendicular distance between the $z$ axis and the $z'$ axis.

For the final two summations, we can note that, according to the definition of the centre of mass, we would expect:
```{math}
    \sum_i \delta m_i\,\overline{x}_i = \sum_i \delta m_i\,\overline{y}_i = 0.
```
Hence, the expression for the moment of inertia reduces to:
```{math}
    I_z = \sum_i \, \delta m_i\,(\overline{x}_i^2 + \overline{y}_i^2) + M_d^2,
```
which expresses, in mathematical form, the <mark>Parallel Axis Theorem</mark> for moments of inertia: 
<mark>The moment of inertia of a rigid body taken about any axis is equal to the moment of inertia about a parallel axis passing through the centre of mass, plus the product of the mass of the body and the square of the perpendicular distance between the two axes.</mark>

## Towards Lagrangian Mechanics (Non-Examinable)

An elegant alternative formalism for investigating the time-dependent motion of a system of particles evolved from the work of Leibniz (1646-1716), Bernoulli (1667-1748), D'Alembert (1717-1783) and Lagrange (1736-1813). As an introduction to Lagrangian mechanics, we take the approach in this section of describing how Lagrange's equations can be derived from a variational principle developed by Hamilton (1805-1865), and consider a couple of simple applications.

#### Hamilton's Variational Principle

Defining the <mark>Lagrangian</mark> function $L = T - V$ as the difference between the potential and kinetic energy of a system of particles, Hamilton's principle is related to the evolution of the system between two times, $t_1$ and $t_2$. Out of the many possible ways that the positions and velocities of the constituent particles could evolve between these times, the *actual motion* is the 'trajectory' (evolution in time of positions and velocities) of the system which either maximizes or minimizes the integral:
```{math}
    J = \int_{t_1}^{t_2} L\,dt,
```
where we recognize that, generally, the Lagrangian will be a function of time. This condition is mathematically equivalent to the statement that a small increment or 'perturbation' in the value of $J$, taken with respect to its minimum or maximum value, must be zero:
```{math}
    \delta J = \delta \int_{t_1}^{t_2} L\,dt = 0.
```
This variation $\delta J$ corresponds to a path for the system where the particle positions and velocities are infinitesimally different from those which occur for the 'optimal' path — that is, the actual motion of the system for which $J$ takes on an extreme value. When calculating $\delta J$, however, all the parameters of the system are taken to be the same at the end times $t_1$, $t_2$ as they are for the optimal path.

Let's consider the simple example of a single particle moving under the influence of a uniform gravitational acceleration $g$ (for example close to the surface of the Earth). If the vertical coordinate above ground is denoted $y$, then the Lagrangian can be written simply as $L = \frac{m \dot{y}^2}{2} - m g y$. The corresponding variation in Hamilton's integral becomes:
```{math}
    \delta J = \int_{t_1}^{t_2} \delta\left( \frac{m \dot{y}^2}{2} - m g y \right) \, dt.
```

Now, $\delta y$ is a function of time which represents the small difference in $y$ between the actual motion of the particle and a conceptual trajectory which is infinitesimally different, at each time $t$, by an amount $\delta y$, and where $\delta y = 0$ at $t=t_1,t_2$. Since, according to this definition, the corresponding increment in velocity would be $\delta \dot{y} = \frac{\mathrm{d}}{\mathrm{d}t} (\delta y)$, we obtain:
```{math}
    \delta J = \int_{t_1}^{t_2} \left( m \dot{y}\,\delta \dot{y} - m g \, dy \right) \, dt,
```
where:
```{math}
    \int_{t_1}^{t_2} m \dot{y}\,\delta \dot{y} \, dt = \int_{t_1}^{t_2} m \dot{y}\,
    \frac{\mathrm{d}}{\mathrm{d}t}(\delta y) \, dt.
```
Integrating the final expression by parts gives:
```{math}
   \int_{t_1}^{t_2} m \dot{y}\,
    \frac{\mathrm{d}}{\mathrm{d}t}(\delta y) \, dt = \left[ m \dot{y} \, \delta y\right]_{t_1}^{t_2} -
    \int_{t_1}^{t_2} m \ddot{y}\,\delta y\,dt.
```
Now the first term on the right-hand side of the above equation vanishes, since 
$\delta y = 0$ at the endpoints of integration. Our original expression for 
$\delta J$ thus becomes:
```{math}
    \delta J = \int_{t_1}^{t_2} (-m \ddot{y} - m g)\,\delta y\,dt = 0.
```
Since this condition must hold for any conceptual path which is infinitesimally close to the actual motion, the only way it can be satisfied is if the integrand itself is zero for all times during the motion. That is:
```{math}
-m \ddot{y} - m g = 0,
```
which is equivalent to Newton's Second Law for a particle falling in a uniform gravitational field.

### Lagrange's Equations

We may repeat this kind of calculation for a more general case, where we have a system of particles whose positions can be described by a set of <mark>generalised</mark> coordinates $q_i$, each of which is some function of time. The $q_i$ are referred to as generalised because in this formalism they can be distances, angles, or some combination of these kinds of quantities. For each function $q_i$, there is of course a generalised velocity $\dot{q_i}$. Applying Hamilton's principle to these more general parameters, one can prove (we give the result here without proof) that the motion of the system is constrained by the following equations:
```{math}
:label: eq:lagrange
    \dfrac{\partial L}{\partial q_i} - \dfrac{\mathrm{d}}{\mathrm{d}t} \left( \dfrac{\partial L}{\partial \dot{q_i}} \right) = 0. 
```
These are the desired Lagrangian equations of motion for a system acting under conservative forces. If the equations are used to describe a motion where one or more particles are constrained in some sense (e.g., a particle constrained to move only on the surface of a sphere), then that constraint must be <mark>holonomic</mark>. In other words, it must be mathematically expressible by the condition that the value of some function $f$ is zero at all times, where $f$ can only be a function of the generalised coordinates and time.

We end this section by considering the motion of a single particle in a central field.

The potential energy of the particle, of mass $m$, in the gravitational field of the central body, of mass $M$ ($M >> m$, with $M$ stationary at the origin), is simply
```{math}
V = -\dfrac{G M m}{r},
```
where $r$ denotes radial distance from the origin. The kinetic energy is
```{math}
T = \frac{1}{2}\,m\,(\dot{r}^2 + r^2\,\dot{\theta}^2),
```
where $\theta$ is an angular coordinate. The particle is constrained to move in a single plane, as we have explored in the section "Gravity". The Lagrangian is:
```{math}
L = T - V = \frac{1}{2}\,m\,(\dot{r}^2 + r^2\,\dot{\theta}^2) + \dfrac{GMm}{r}.
```

Equation {eq}`eq:lagrange`, for the radial distance coordinate, reads:
```{math}
    \dfrac{\partial L}{\partial r} = \dfrac{\mathrm{d}}{\mathrm{d}t} \left( \dfrac{\partial L}{\partial \dot{r}}  \right)     \rightarrow 
    m r \,\dot{\theta}^2 -\dfrac{G M m}{r^2} = m \ddot{r} \rightarrow 
    -\dfrac{G M}{r^2} = \ddot{r} - r \,\dot{\theta}^2.
```

Equation {eq}`eq:lagrange`, for the angular coordinate, reads:
```{math}
    \dfrac{\partial L}{\partial \theta} = \dfrac{\mathrm{d}}{\mathrm{d}t} \left( \dfrac{\partial L}{\partial \dot{\theta}}  \right)     \rightarrow 
    0 = \dfrac{\mathrm{d}}{\mathrm{d}t} \left( m r^2 \dot{\theta} \right).
```

Thus, the treatment of the problem using Lagrange's formalism easily allows us to derive the radial equation of motion of the particle, as well as the mathematical expression of the conservation of its angular momentum.
