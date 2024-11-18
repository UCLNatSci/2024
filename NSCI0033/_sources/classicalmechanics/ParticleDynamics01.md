# Particle Dynamics

![image](Figs/particlemotionillust.jpg)

*Image Credit: J. Barker*

## Vector Functions describing Velocity and Acceleration of a Moving Particle

In this unit, we wish to quantify the motion of a particle, or a group
of particles, which move in response to different types of
[forces]{.mark}. To do this, we will use vector functions to represent
the position, velocity and acceleration of particles in different
coordinate systems. We start with the case of [Cartesian]{.mark}
coordinates, the simplest case. The vector position of our particle with
respect to the origin, at some time $t$, can be written (using bold
typeface convention for vector quantity):

```{math}
:label: posnveccartdefn
\mathbf{r}(t) = x(t)\,\hat{\mathbf{x}} + y(t)\,\hat{\mathbf{y}} + z(t)\,\hat{\mathbf{z}}
``` 
where the vectors
${\bf{\hat{x}}}$, ${\bf{\hat{y}}}$, ${\bf{\hat{z}}}$
are unit vectors aligned with the axes of the coordinate system.

The <mark>velocity</mark>, ${\bf{v}}(t)$, of the particle is the
rate of change of its vector position with time. To calculate this, we
simply differentiate all the individual components in our general
expression:

```{math}
\mathbf{v}(t) = \mathbf{r}'(t) = x'(t)\,\hat{\mathbf{x}} + y'(t)\,\hat{\mathbf{y}} + z'(t)\,\hat{\mathbf{z}},
``` 
where the prime notation ($'$) indicates taking a
derivative of the functions $x(t), y(t), z(t)$ with respect to time.

What about acceleration? By definition, <mark>acceleration</mark>
${\bf{a}}(t)$ is the rate of change of velocity, so:
```{math}
\mathbf{a}(t) = \mathbf{v}'(t) = \mathbf{r}''(t) = x''(t)\,\hat{\mathbf{x}} + y''(t)\,\hat{\mathbf{y}} + z''(t)\,\hat{\mathbf{z}}.
```

These definitions give very simple expressions for motion under constant acceleration. For example a vertically falling body close enough to the surface of the Earth experiences a constant downward acceleration, $g \approx 9.8\,\mathrm{m\cdot s^{-2}}$. 

If we take the downward vertical direction as $-z$, then ${\bf{a}} = -g\,{\bf{\hat{z}}}$. Using subscript notation to indicate vector component, $a_z = -g$. If the body is initially at rest (zero velocity) at a height $h$ above the ground, then dropped, we can integrate the definition of acceleration, to find how its velocity evolves with time: 
```{math}
v_z(t_f)-v_z(0) &= \int_{0}^{t_f} a_z(t)\,dt =  -g\,(t_f-0) \notag \\
\rightarrow v_z(t_f) &= -g\,t_f.
``` 
Thus the particle's velocity increases linearly with time during its fall. To work out how far it falls in the same time interval $t=0\rightarrow t_f$, we integrate the expression for velocity:
```{math}
z(t_f)-z(0) &= \int_{0}^{t_f} v_z(t)\,dt =  \int_{0}^{t_f} -g\,t\,dt \\
\rightarrow z(t_f) -h &= -\frac{1}{2}\,g\,t_f^2 \\
\rightarrow z(t_f) &= h-\frac{1}{2}\,g\,t_f^2
``` 

The particle's journey 'finishes' when it strikes the
ground at $z=0$, at which the corresponding time $t_{\mathrm{end}}$ will
satisfy $0 = h-\frac{1}{2}\,g\,t_{\mathrm{end}} ^2$. Solving this
equality, we obtain $t_{\mathrm{end}} = \sqrt{2h/g}$.

### Example: Circular Motion

Of course, the Cartesian coordinate system is not our only choice for
describing particle motion. Other coordinate systems also follow the
basic definitions of velocity and acceleration, however the
corresponding expressions may look a little different in coordinate
systems where the unit vectors are locally defined -- in other words,
where the coordinate unit vectors may change direction as the particle
moves.

A simple example of this is a particle executing <mark>circular
motion</mark> in the Cartesian $x-y$ plane. If the particle moves on a
circular path of constant radius $b$, then we may specify its position
using two Cartesian coordinates which are themselves functions of time:
```{math}
x = b\,\cos(\omega\,t), \hspace{1cm} y = b\,\sin(\omega\,t),
``` 
where the constant $\omega$ is the <mark>angular velocity</mark>of the particle. 
$\omega = 2\pi/T$, where $T$ is the period of the motion. 
Figure [1](#fig:circmotion){reference-type="ref"
reference="fig:circmotion"} illustrates this type of motion.

<figure id="fig:circmotion">
<div class="center">
<embed src="Figs/circmotion.pdf" style="width:8cm" />
</div>
<figcaption>Diagram of particle executing circular motion, showing
direction of position and velocity vectors at time <span
class="math inline">\(t\)</span>, when angular coordinate is <span
class="math inline">\(\phi\)</span> (see text).</figcaption>
</figure>

Equivalently, we could use the single angular coordinate
$\phi = \omega\,t$ to trace the particle position. In a general polar
coordinate system, $\phi$ is the angle between the particle's position
vector and the $x$ axis; and the radial distance $r$ from the origin
specifies the second coordinate needed to specify any position in the
two-dimensional plane. In this simple example, $r$ is held constant at
value $b$.

The polar coordinate unit vectors point locally in the direction of
maximum increase in those coordinates. Thus, unit vector
${\bf{\hat{r}}}$ points radially outwards from the origin at
the position of our particle; while unit vector
${\bf{\hat{\phi}}}$ points along the local direction of
rotation of the particle, at the particle's position. Both of these unit
vectors execute one full rotation for one period of the motion -- that
is, a time interval of duration $T=2\pi/\omega$, during which $\phi$
changes value by $2\pi$.

If we choose to use these unit vectors for calculating velocity and
acceleration in polar coordinates, we commence with the position of the
particle, which, by definition, is: ```{math}
\mathbf{r}(t) = b\,{\mbox{${\bf{\hat{r}}}$}}(t).
``` We have to differentiate the full vector function
${\bf{r}}(t)$ to get the velocity. $b$ is constant with time,
but the radial unit vector is not -  it changes direction, according to:
```{math}
{\mbox{${\bf{\hat{r}}}$}}'(t) &= \frac{d}{dt}\,(\cos(\omega\,t)\,\hat{\mathbf{x}} + \sin(\omega\,t)\,\hat{\mathbf{y}}) \notag \\
                        &=\omega\,(-\sin(\omega\,t)\,\hat{\mathbf{x}} + \cos(\omega\,t)\,\hat{\mathbf{y}})  \notag \\
                        &=\omega\,{\mbox{${\bf{\hat{\phi}}}$}}.
``` We introduce the unit vector
${\bf{\hat{\phi}}}$ in the final step, as we identify it with
the unit vector in the previous line, which is always orthogonal to
${\bf{\hat{r}}}$ and which always points along the direction
of motion of the particle. Thus we have: ```{math}
\mathbf{r}'(t) = b\,{\mbox{${\bf{\hat{r}}}$}}'(t) = b\omega\,{\mbox{${\bf{\hat{\phi}}}$}}(t).
``` Furthermore, for the acceleration, we see that we need
to differentiate ${\bf{\hat{\phi}}}(t)$ with respect to time,
as follows: ```{math}
{\mbox{${\bf{\hat{\phi}}}$}}'(t) &= \frac{d}{dt}\,(-\sin(\omega\,t)\,\hat{\mathbf{x}} + \cos(\omega\,t)\,\hat{\mathbf{y}}) \notag \\
                        &=\omega\,(-\cos(\omega\,t)\,\hat{\mathbf{x}} - \sin(\omega\,t)\,\hat{\mathbf{y}})  \notag \\
                        &=-\omega\,{\mbox{${\bf{\hat{r}}}$}}.
\label{eq:duvecphidt}
``` And so, our expression for acceleration becomes:
```{math}
\mathbf{r}''(t) = b\omega\,{\mbox{${\bf{\hat{\phi}}}$}}'(t) = -b\omega^2\,{\mbox{${\bf{\hat{r}}}$}},
``` which always points towards the centre of the rotation
(i.e. the origin, in this example), and has a magnitude
$b\omega^2 = v_{\phi}^2/b$, where the uniform rotational speed
$v_{\phi}=b\omega$. This type of acceleration, associated with
rotational motion, is known as [centripetal acceleration]{.mark}.
Because it acts perpendicularly to the direction of motion, it changes
the particle's direction, but not its speed.

### Example: Rolling Wheel

Consider a point on the moving rim of a rolling wheel of radius $b$. Let
the position of this point be at a height $2b$ above the ground
(i.e. uppermost point on the rim) at time zero. As time proceeds, the
position of the centre of the wheel can be described by:
```{math}
\mathbf{r}_{w}(t) = b\,\omega\,t\,\hat{\mathbf{x}} + b\,\hat{\mathbf{y}},
``` where the centre of the wheel moves in the $x$ direction
at a speed given by one wheel circumference unrolling along the ground
per rotational period, or $2\pi\,b/(2\pi/\omega)=b\,\omega$. We have
assumed that the wheel lies in the $xy$ plane during its motion. Figure
[2](#fig:wheel){reference-type="ref" reference="fig:wheel"} illustrates
the motion of this point.

<figure id="fig:wheel">
<div class="center">
<embed src="./Figs/wheel.pdf" style="width:12cm" />
</div>
<figcaption>Cycloidal trajectory (solid blue curve with arrows) of a
moving point on rim of rolling wheel (see text). Black semi-circle
indicates the right side of the wheel at time zero.</figcaption>
</figure>

Our moving point, in a frame of reference where the wheel centre is
stationary, has a position at time $t$, relative to the wheel centre,
given by: ```{math}
\mathbf{r}_{p}(t) = b\,\sin(\omega\,t)\,\hat{\mathbf{x}} + b\,\cos(\omega\,t)\,\hat{\mathbf{y}}.
```

The complete position vector of our 'rolling point' is thus:
```{math}
\mathbf{r}_{w}(t) + \mathbf{r}_{p}(t) = b\,(\omega\,t+\sin(\omega\,t))\,\hat{\mathbf{x}} + b\,(1+\cos(\omega\,t))\,\hat{\mathbf{y}}.
``` Differentiating once with respect to time gives the
velocity of the moving point: ```{math}
\mathbf{v}(t) = b\,(\omega+\omega\,\cos(\omega\,t))\,\hat{\mathbf{x}} + -\omega\,b\,\sin(\omega\,t)\,\hat{\mathbf{y}}.
``` Note that, for times when
$\omega t = 0, 2\pi, 4\pi, 6\pi, ...$, when the point is at the
uppermost location on the wheel, the velocity is of magnitude
$2\omega b$ in the $x$ direction -- that is, the point is
instantaneously moving at twice the velocity of the moving centre of the
wheel.

On the other hand, for times when $\omega t = \pi, 3\pi, 5\pi, ...$,
when the point is in contact with the ground, its instantaneous velocity
is zero.

Differentiating again with respect to time gives the acceleration of the
moving point: ```{math}
\mathbf{a}(t) = \mathbf{v}'(t)= -b\,\omega^2\,\sin(\omega\,t))\,\hat{\mathbf{x}} + -b\,\omega^2\,\cos(\omega\,t)\,\hat{\mathbf{y}} = -\omega^2\,\mathbf{r}_p(t).
``` We recognize that this acceleration is always directed
from the moving point towards the centre of the wheel at all times, and
is of magnitude $b\omega^2$.

## Velocity and Acceleration with Three-Dimensional Spatial Coordinates

When we consider particle motion in three dimensions, logically we need
three coordinates to specify vector quantities such as position,
velocity and acceleration. The general relationships still hold -- for
example, velocity is the rate of change of position with respect to
time. In this section, we extend some of the ideas from the previous
section to derive appropriate formulae for these quantities in the
[cylindrical]{.mark} and [spherical]{.mark} coordinate systems for
three-dimensional space.

### Cylindrical Coordinates

An illustration of cylindrical coordinates and associated, locally
defined unit vectors is shown in Figure
[3](#fig:cylcoords){reference-type="ref" reference="fig:cylcoords"}. The
three coordinates are: $R$ (cylindrical radial distance), which is the
perpendicular distance of the point of interest from some reference axis
(here chosen to be the Cartesian $z$ axis); $\phi$, the azimuthal angle
between the $x$ axis and the projection of the position vector onto the
$xy$ plane; and $z$, which is identical to the usual Cartesian $z$
coordinate.

<figure id="fig:cylcoords">
<div class="center">
<embed src="./Figs/cylcoords.pdf" style="width:6cm" />
</div>
<figcaption>Illustration of cylindrical coordinates and unit vectors
(from the book by Fowles and Cassiday).</figcaption>
</figure>

Now, the position vector of any moving particle with respect to the
origin can be expressed, using the corresponding (locally defined) unit
vectors in this system, as: ```{math}
\mathbf{r}(t) = R\,{\mbox{${\bf{{e}_R}}$}} + z\,{\mbox{${\bf{{e}_z}}$}}.
``` The unit vector ${\bf{{e}_R}}$ will change
direction as the particle moves, since it is parallel to the direction
from the closest point on the $z$ axis to the position of the particle
itself. On the other hand, the unit vector ${\bf{{e}_z}}$
will not change with the particle motion.

We can thus use similar calculations as were done in the previous
section to prove that: ```{math}
\frac{d{\mbox{${\bf{{e}_R}}$}}}{dt} = \dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}},
\label{eq:duvecRdt}
``` where we have used the 'overdot' notation to denote time
derivative, $\dot{\phi} = \frac{d\phi}{dt}$.

Using this same notation now to calculate the velocity in cylindrical
coordinates: ```{math}
\dot{\mathbf{r}} &= \dot{R}\,{\mbox{${\bf{{e}_R}}$}} + R\,\dfrac{d{{\mbox{${\bf{{e}_R}}$}}}}{dt} + \dot{z}\,{\mbox{${\bf{{e}_z}}$}} \notag \\
            &= \dot{R}\,{\mbox{${\bf{{e}_R}}$}} + R\,\dot{\phi}\,{{\mbox{${\bf{{e}_{\phi}}}$}}} + \dot{z}\,{\mbox{${\bf{{e}_z}}$}}.
\label{eq:rdotcyl}
``` The cylindrical components of the above equation
represent the cylindrical radial velocity, the azimuthal velocity
(equivalent to a local rotational component of motion about the $z$
axis), and the axial velocity.

Differentiating the azimuthal unit vector ${\bf{{e}_{\phi}}}$
with respect to time, using similar reasoning as for equation
[\[eq:duvecphidt\]](#eq:duvecphidt){reference-type="ref"
reference="eq:duvecphidt"}, gives us: ```{math}
{\mbox{${\bf{{e}_{\phi}}}$}}'(t) = -\dot{\phi}\,{\mbox{${\bf{{e}_{R}}}$}}.
```

If we now use this result and equation
[\[eq:duvecRdt\]](#eq:duvecRdt){reference-type="ref"
reference="eq:duvecRdt"} when we differentiate velocity (equation
[\[eq:rdotcyl\]](#eq:rdotcyl){reference-type="ref"
reference="eq:rdotcyl"}) to get acceleration, we arrive at (proof is
left for the reader as an exercise): ```{math}
\ddot{\mathbf{r}} &= (\ddot{R}-R\,\dot{\phi}^2)\,{\mbox{${\bf{{e}_R}}$}} + (R\,\ddot{\phi} + 2\dot{R}\dot{\phi})\,{\mbox{${\bf{{e}_{\phi}}}$}} + \ddot{z}\,{\mbox{${\bf{{e}_{z}}}$}}. 
\label{eq:rdotdotcyl}
``` We can identify the term
$-R\,\,{\phi}^2\,{\bf{{e}_R}}$ in this expression as the
centripetal acceleration associated with that component of the motion
which represents rotation about the $z$ axis.

### Spherical Coordinates

In this section, we repeat the same general strategy for deriving
formulae for velocity and acceleration in the [spherical polar
coordinates]{.mark} for three-dimensional space. We remind ourselves,
from the previous section, that this strategy involves expressing the
local unit vectors of our coordinate system in a form which is
relatively straightforward to differentiate - the Cartesian form of
these vectors is a good choice here. Differentiation then allows us to
express the time derivatives of each of our local unit vectors in terms
of other unit vectors in the triad, which in turn allows us to make
final derivations of the spherical polar implementations of velocity and
acceleration of a moving particle. Note that the vectors which we obtain
for a particle's velocity and acceleration ultimately must have the same
final magnitude and direction in all coordinate systems - however, the
different orientations of unit coordinate vectors in these different
systems mean that the individual *components* of acceleration and
velocity are indeed dependent on our choice of coordinates.

<figure id="fig:spherecoords">
<div class="center">
<embed src="./Figs/spherecoords.pdf" style="width:6cm" />
</div>
<figcaption>Illustration of spherical coordinates and unit vectors (from
the book by Fowles and Cassiday).</figcaption>
</figure>

With these concepts in mind, we now turn to the spherical polar
coordinate system, whose position coordinates and local unit vectors are
illustrated in Figure [4](#fig:spherecoords){reference-type="ref"
reference="fig:spherecoords"}. We see that in this system, the three
quantities which now specify a particle's position are: $r$, its radial
distance from the origin; $\theta$, the polar angle which is the angle
between the $z$ Cartesian axis and the position vector of the particle;
$\phi$, the azimuthal angle which is the angle between the $x$ axis and
the projection of the position vector onto the $xy$ plane. If we express
these unit vectors in the Cartesian components, we obtain:
```{math}
{\mbox{${\bf{{e}_{r}}}$}} &= \sin\theta\,\cos\phi\,{\mbox{${\bf{{e}_x}}$}} + \sin\theta\,\sin\phi\,{\mbox{${\bf{{e}_y}}$}} + \cos\theta\,{\mbox{${\bf{{e}_z}}$}}, \notag \\
{\mbox{${\bf{{e}_{\theta}}}$}} &= \cos\theta\,\cos\phi\,{\mbox{${\bf{{e}_x}}$}} + \cos\theta\,\sin\phi\,{\mbox{${\bf{{e}_y}}$}} - \sin\theta\,{\mbox{${\bf{{e}_z}}$}}, \notag \\
{\mbox{${\bf{{e}_{\phi}}}$}} &= -\sin\phi\,{\mbox{${\bf{{e}_x}}$}} + \cos\phi\,{\mbox{${\bf{{e}_y}}$}}. 
``` As usual, these unit vectors point along the local
direction of maximum increase of the corresponding position coordinate.

Taking the general time derivative of the radial unit vector (assuming
that both $\theta$ and $\phi$ are functions of time along the particle
trajectory): ```{math}
\frac{d{\mbox{${\bf{{e}_r}}$}}}{dt} &= 
\frac{\partial {\mbox{${\bf{{e}_r}}$}}}{\partial \theta}\,\dot{\theta} +
\frac{\partial {\mbox{${\bf{{e}_r}}$}}}{\partial \phi}\,\dot{\phi}  \notag \\
&=\cos\theta\,\cos\phi\,\dot{\theta}\,{\mbox{${\bf{{e}_x}}$}} + \cos\theta\,\sin\phi\,\dot{\theta}\,{\mbox{${\bf{{e}_y}}$}} - \sin\theta\,\dot{\theta}\,{\mbox{${\bf{{e}_z}}$}}  \notag \\
&-\sin\theta\,\sin\phi\,\dot{\phi}\,{\mbox{${\bf{{e}_x}}$}} + \sin\theta\,\cos\phi\,\dot{\phi}\,{\mbox{${\bf{{e}_y}}$}} \notag \\
&= \dot{\theta}\,{\mbox{${\bf{{e}_{\theta}}}$}} + \sin\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}}.
\label{eq:duvecrdt}
``` Note that these expressions have geometrical meaning.
For example, if a particle moves such that its $\phi$ coordinate does
not change, and it only increases its coordinate $\theta$, following a
circular path of constant radial distance $r$, then in a time
$\delta t$, the incremental change in the radial unit vector 'carried
along' with the particle would be of magnitude $\dot{\theta}\,\delta t$
and of direction parallel to the maximum-rate direction of increasing
$\theta$, i.e. parallel to ${\mbox{${\bf{{e}_{\theta}}}$}}$.

We now have enough information to evaluate all the terms (scalar and
vector derivatives) needed in the definition of velocity:
```{math}
\dfrac{d(r{\mbox{${\bf{e_r}}$}})}{dt} &= \dot{r}\,{\mbox{${\bf{e_r}}$}} + r\,\dfrac{d{\mbox{${\bf{e_r}}$}}}{dt} \notag \\
&= \dot{r}\,{\mbox{${\bf{e_r}}$}} + r\,\dot{\theta}\,{\mbox{${\bf{{e}_{\theta}}}$}} + r\,\sin\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}}
\label{eq:dvecrdt}
```

Similar calculations to those which led to equation
[\[eq:duvecrdt\]](#eq:duvecrdt){reference-type="ref"
reference="eq:duvecrdt"}, for the other unit vectors (proof is left to
the reader), give: ```{math}
\frac{d{\mbox{${\bf{{e}_{\theta}}}$}}}{dt} &= -\dot{\theta}\,{\mbox{${\bf{{e}_{r}}}$}} +
\cos\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}}, 
\label{eq:duvecthetadt}
``` ```{math}
\frac{d{\mbox{${\bf{{e}_{\phi}}}$}}}{dt} &=  -\sin\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{r}}}$}} -
\cos\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{\theta}}}$}}.
\label{eq:duvecphidtsp}
```

Finally, we can obtain the spherical polar components of acceleration by
differentiating equation
[\[eq:dvecrdt\]](#eq:dvecrdt){reference-type="ref"
reference="eq:dvecrdt"}, and using the unit vector results from
equations [\[eq:duvecrdt\]](#eq:duvecrdt){reference-type="ref"
reference="eq:duvecrdt"},
[\[eq:duvecthetadt\]](#eq:duvecthetadt){reference-type="ref"
reference="eq:duvecthetadt"},
[\[eq:duvecphidtsp\]](#eq:duvecphidtsp){reference-type="ref"
reference="eq:duvecphidtsp"}:

```{math}
\mathbf{a} = \dfrac{d^2(r{\mbox{${\bf{e_r}}$}})}{dt^2} &= \ddot{r}\,{\mbox{${\bf{e_r}}$}} + \dot{r}\,\dot{\theta}{\mbox{${\bf{e_{\theta}}}$}} + 
+ r\,\ddot{\theta}\,{\mbox{${\bf{e_{\theta}}}$}} + \notag \\
&+ \dot{r}\,\sin\theta\,\dot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} 
 + r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} 
 + r\,\sin\theta\,\ddot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} + \notag \\
 & + \dot{r}\dfrac{d{\mbox{${\bf{e_r}}$}}}{dt}
 + r\,\dot{\theta}\dfrac{d{\mbox{${\bf{e_{\theta}}}$}}}{dt}
 + r\,\sin\theta\,\dot{\phi}\dfrac{d{\mbox{${\bf{e_{\phi}}}$}}}{dt} \notag \\
 &= \ddot{r}\,{\mbox{${\bf{e_r}}$}} + \dot{r}\,\dot{\theta}{\mbox{${\bf{e_{\theta}}}$}} + 
+ r\,\ddot{\theta}\,{\mbox{${\bf{e_{\theta}}}$}} + \notag \\
&+ \dot{r}\,\sin\theta\,\dot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} 
 + r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} 
 + r\,\sin\theta\,\ddot{\phi}\,{\mbox{${\bf{e_{\phi}}}$}} + \notag \\
 & + \dot{r}\,\dot{\theta}\,{\mbox{${\bf{{e}_{\theta}}}$}} + \dot{r}\,\sin\theta\,\dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}}
 -r\,\dot{\theta}^2\,{\mbox{${\bf{{e}_{r}}}$}} +
r\,\cos\theta\,\dot{\theta}\,\dot{\phi}\,{\mbox{${\bf{{e}_{\phi}}}$}} \notag \\
 & -r\,\sin^2\theta\,\dot{\phi}^2\,{\mbox{${\bf{{e}_{r}}}$}} -
r\,\sin\theta\,\cos\theta\,\dot{\phi}^2\,{\mbox{${\bf{{e}_{\theta}}}$}}. 
\label{eq:accelsph}
```

Collecting terms corresponding to each component of the acceleration
vector, this expression simplifies to: ```{math}
\mathbf{a} =& (\ddot{r}-r \dot{\theta}^2-r\, {\sin^2\theta} \, \dot{\phi}^2)\,{\mbox{${\bf{e_r}}$}}     + \notag \\
& (r \ddot{\theta} + 2 \dot{r} \dot{\theta} -r\,\sin\theta\,\cos\theta\,\dot{\phi}^2) \, {\mbox{${\bf{e_{\theta}}}$}} + \notag \\
& (r\,\sin\theta\,\ddot{\phi} + 2\sin\theta\,\dot{r}\dot{\phi}
+ 2 r\,\cos\theta\,\dot{\theta}\dot{\phi})\,{\mbox{${\bf{e_{\phi}}}$}}.
```\
**Example 1 - Circular Orbital Motion** We may consider the following
simple example of describing motion in spherical coordinates. A particle
of mass $m$ follows a circular orbit of constant radius $r_0$ with
respect to the centre of a spherically symmetric planet of mass $M$. For
simplicity, we consider part of such an orbit where $\phi$ is constant.
The only force on the orbiting particle is in the radial direction
towards the planet centre, and has magnitude $GMm/r_0^2$ where $G$ is
the classical gravitational constant. In vector notation, the force is
${\mbox{${\bf{F}}$}}=-(GMm/r_0^2)\,{\mbox{${\bf{e_r}}$}}$ and so the
acceleration is
$\mathbf{a} = {\mbox{${\bf{F}}$}}/m = -(GM/r_0^2)\,{\mbox{${\bf{e_r}}$}}$.
But we know from our general acceleration formula that the radial
acceleration must also be equal to
$a_r = \ddot{r} - r\dot{\theta}^2 = -r_0\,\dot{\theta}^2$. Hence:
```{math}
r_0\,\dot{\theta}^2 = GM/r_0^2 \rightarrow \dot{\theta}=\pm\sqrt{GM/r_0^3},
%a_{\theta} = \r_0\,\ddot{\theta} = 0 \rightarrow \theta
``` which means the particle has constant angular velocity,
and completes one orbit in a time given by $T = 2\pi/|\dot{\theta}|
=\sqrt{4\pi^2/(GM)}\,r_0^{3/2}$. This is a simple example of one of
Kepler's laws of gravitational motion. Note that the conditions of
constant $\dot{\theta}$ and constant $\phi$ for this simple example
confirm that $a_{\theta}$ and $a_{\phi}$ do indeed evaluate to zero, as
required.\
**Example 2 - Elliptical Motion** This problem comes from Chapter 1 in
the book by Fowles and Cassiday. A small ball is fastened to a long
rubber band and twirled around in such a way that the ball moves in an
elliptical path, given by the equation: ```{math}
\mathbf{r}(t) = {\mbox{${\bf{e_x}}$}}\,b\,\cos(\omega t) + {\mbox{${\bf{e_y}}$}}\,2b\,\sin(\omega t), \notag
``` where $b$ and $\omega$ are constants.

To find the speed $v$ (velocity magnitude) of the ball, we simply
differentiate once with respect to time, noting that the Cartesian unit
vectors stay constant with time along the particle trajectory described:
```{math}
\mathbf{r}'(t) = -{\mbox{${\bf{e_x}}$}}\,b\,\omega\,\sin(\omega t) + {\mbox{${\bf{e_y}}$}}\,2b\,\omega\,\cos(\omega t), \notag
```

Hence
$v(t) = |\mathbf{r}'(t)| = b\omega\,\sqrt{\sin^2(\omega t) + 4\cos^2(\omega t)} = b\omega\,\sqrt{1 + 3\cos^2(\omega t)}$.

Now, if we wish to calculate the distance of the ball from the origin as
a function of time, this is simply the magnitude $r(t)$ of the given
vector function $\mathbf{r}(t)$, which is
$r(t) = b\,\sqrt{1+3\sin^2(\omega t)}$. We note that
$\frac{dr}{dt} \propto \sin{\omega t}\,\cos{\omega t}$, which means that
$\frac{dr}{dt} = 0$ at times $t=0$ and $t=\pi/(2\omega)$. These times
therefore represent two instants when the ball is at its minimum and
maximum distance from the origin, respectively.

We note that, for $t=0$ (minimum distance from origin, $r_{min}=b$),
$v = 2\omega b$. And for $t=\pi/(2\omega)$ (maximum distance from
origin, $r_{max} = 2b$), $v = \omega b$. Speed declines with increasing
distance.

Further exercises and problems based on the material in this unit will
be attempted and discussed in the problem-solving tutorials.
