# Newton's Laws of Motion

<img src="Figs/newtonlawillus.jpeg" width="400">

*Image Credit: Encyclopedia Britannica*

Classical mechanics uses these Laws of Motion as a starting point:

1. A body remains at rest </mark>or in a state of uniform motion</mark> (non-accelerating) </mark>unless acted on by an external force</mark>.
2. A force $ \mathbf{F} $ can be quantitatively defined as the rate of change of momentum $ \mathbf{p} $ it causes on the object upon which it is acting:
   ```{math}
   \mathbf{F} = \frac{\mathrm{d}\mathbf{p}}{\mathrm{d}t}.
   ```
3. To every force (action) there is an </mark>equal but opposite reaction</mark>.

These laws are only valid for an observer who is using a reference frame that is </mark>inertial</mark> (i.e., not undergoing acceleration, which excludes frames with rotating coordinate axes).

Consider the simple example of two bodies, with masses $ m_1 $ and $ m_2 $, which move while in contact with each other under the influence of an external force $ \mathbf{F} $. The total force on the combined system (see {numref}`fig:newton2`) is $ \mathbf{F} + \mathbf{F}_{12} + \mathbf{F}_{21} $, where the notation $ \mathbf{F}_{ij} $ denotes the force, due to contact, of body $ j $ on body $ i $.

Newton's Second Law tells us that the external force on the system is the total mass multiplied by the acceleration of the co-moving bodies:
```{math}
\mathbf{F} = (m_1 + m_2) \mathbf{a}.
```

On the other hand, Newton's Law must also be valid for the two bodies individually, and the total external force acting upon them individually:
```{math}
\mathbf{F} + \mathbf{F}_{12} = m_1 \mathbf{a}, \\
\mathbf{F}_{21} = m_2 \mathbf{a}.
```

We can see, by comparing the above equations, that we require $ \mathbf{F} = \mathbf{F} + \mathbf{F}_{12} + \mathbf{F}_{21} $, or more simply $ \mathbf{F}_{12} = -\mathbf{F}_{21} $. The contact force on the first body due to the second is equal in magnitude but opposite in direction to that of the second body on the first.

When we sit inside a room in everyday life, we are clearly *not* accelerating (we ignore the Earth's rotation for this example). Hence, the total vector force on us must be zero. It follows that the action or force </mark>downwards</mark> on us due to the Earth's gravitation must be exactly balanced by the force </mark>upwards</mark> on us due to contact with the object we are sitting on. (If we </mark>did</mark> include the effects of the Earth's rotation, the total force on us would have to be equal to our mass multiplied by the centripetal acceleration we undergo in order to "co-rotate" with the Earth).

```{figure} Figs/fig-newton2.png
---
name: fig:newton2
---
Diagram of two bodies, with masses $ m_1 $ and $ m_2 $, accelerating to the right. The bodies remain in contact during the motion - thus they exert equal and opposite contact forces upon each other. An external force $ \mathbf{F} $ is applied to the leftmost body, which initiates the motion (see text).
```


We shall see that, in general, Newton's Second Law above leads us to descriptions of motion which involve having to solve second-order differential equations for the position of the moving body, or bodies, which comprise the system we are studying. We can start with the simple example of motion under the influence of a constant acceleration.

## Motion Under Constant Acceleration

Recalling that momentum is the product of mass $ m $ and velocity $ \mathbf{v} $, we can write Newton's Second Law for this case as:

```{math}
\mathbf{F} = m \frac{\mathrm{d}\mathbf{v}}{\mathrm{d}t} = m \mathbf{a},   
```
where $ \mathbf{a} $ denotes the constant vector acceleration of the moving body.

This differential equation can be integrated, between some initial time $ 0 $ and some final time $ t $, to give velocity as:
```{math}
\mathbf{v}(t) = \mathbf{v}(0) + \mathbf{a}\,t.   
```

Since, by definition, vector velocity is the derivative of vector position, we can integrate again to acquire an expression for the body's position as a function of time:
```{math}
\mathbf{r}(t) = \mathbf{r}(0) + \mathbf{v}(0)\,t + \frac{1}{2}\,\mathbf{a}\,t^2.
```

These equations are simply generalizations to vector quantities of the familiar equations of motion in one dimension.

A specific, important example of motion under constant acceleration is that of a block of mass $ m $ sliding down an inclined plane under the influence of gravity (see {numref}`fig:inclinedplane`).
In this problem, the gravitational force on the block is $ mg $ in the vertically downwards direction, where $ g $ is the magnitude of the local acceleration due to the Earth's gravity.
However, since the block is only free to move in the $ x $ direction along the plane, we must consider only the component of the force in that direction, which will be $ mg \sin \theta $, where $ \theta $ in the Figure is the angle of tilt of the plane with respect to the horizontal.

```{figure} Figs/inclinedplane.png
---
name: fig:inclinedplane
---
Inclined Plane: (a) Block sliding down inclined plane; (b) Force diagram; (c) Force diagram including friction (from the book by Fowles and Cassiday).
```

Hence, the equation of motion for the block is:
```{math}
m \ddot{x} = m g \sin \theta.
```
Using this equation and assuming that the block is released from rest at time zero, integration once with respect to time reveals the behavior of the velocity:
```{math}
\dot{x}(t_f) - 0 = \int_{t=0}^{t_f} \ddot{x}\,\mathrm{d}t =  g \sin \theta\,t_f. 
```
Integration again gives the behavior of the position coordinate $ x $, during the time interval that the block is moving down the plane, starting at initial position $ x = x_0 $:
```{math}
x(t_f) - x_0 = \int_{t=0}^{t_f} \dot{x}(t)\,\mathrm{d}t =  \frac{1}{2}\,g\,\sin\theta\,t_f^2. 
```

Now, in the time taken for the block to move from initial position $ x(0) = x_0 $ to final position $ x(t_{end}) = x_0 + \frac{h}{\sin \theta} $ (where $ h $ is the vertical displacement of the block during this motion), its velocity will have increased from zero (rest) to a final value $ v = \dot{x}(t_{end}) $ (just before it strikes the horizontal plane). We can calculate this final velocity by noting that:
```{math}
x(t_{end}) - x_0 = \frac{1}{2}\,g\,\sin\theta\,t_{end}^2 = \frac{v^2}{2g\,\sin\theta} \\
\Rightarrow v = \sqrt{2g \sin \theta (x(t_{end}) - x_0)} = \sqrt{2gh}.
```

In practice, a body experiencing this kind of motion can also experience a retarding force due to friction. The frictional force is often expressed as $ \mu_k mg \cos \theta $, where $ \mu_k $ is the </mark>coefficient of friction</mark> and $ mg \cos \theta $ is the component of the gravitational force which acts normally to the inclined plane - which is equal and opposite to the reaction force exerted by the plane on the block. Including friction thus gives an equation of motion:

```{math}
m \ddot{x} = m g \sin \theta - \mu_k m g \cos \theta.
```

Interestingly, we can see that if the angle of tilt satisfies </mark>$ \tan \theta = \mu_k $</mark>, the total acceleration will be zero and a block initially at rest will remain at rest, or, if pushed into motion, will continue to move down the plane at a constant speed.

## Concepts of Kinetic and Potential Energy

For some situations, the force experienced by a moving body depends explicitly only on spatial position. For example, a body moving under the influence of Earth's gravity feels a force based on its position relative to the Earth. Similarly, a body moving under an electrostatic field produced by a stationary charge or collection of charges experiences a position-dependent force. For these cases, where force $ \mathbf{F} $ may be expressed as a function of particle position $ \mathbf{r} $, we can write a general equation of motion for a particle of mass $ m $ as:
```{math}
:label: eq:maeqf
m \ddot{\mathbf{r}} = \mathbf{F}(\mathbf{r}).  
```

Suppose our particle moves under this force from a position $ \mathbf{r_i} $ at time $ t_i $ to a position $ \mathbf{r_f} $ at time $ t_f $. If we take the line integral along this path of the left-hand side of Equation (1), we obtain:
```{math}
\int_{\mathbf{r_i}}^{\mathbf{r_f}} m \ddot{\mathbf{r}} \cdot \mathrm{d}\mathbf{r} = \int_{t_i}^{t_f} m \ddot{\mathbf{r}} \cdot \frac{\mathrm{d}\mathbf{r}}{\mathrm{d}t} \, \mathrm{d}t = \int_{t_i}^{t_f} m \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{1}{2} \dot{\mathbf{r}} \cdot \dot{\mathbf{r}}\right) \, \mathrm{d}t.
```
If we define the <mark>kinetic energy</mark> of our particle as $ T = \frac{1}{2} m \dot{\mathbf{r}} \cdot \dot{\mathbf{r}} $, this integral represents the change in kinetic energy $ T_f - T_i $ between the endpoints.

Now, let's line-integrate the right-hand side of {eq}`eq:maeqf`. We obtain:
```{math}
T_f - T_i = \int_{\mathbf{r_i}}^{\mathbf{r_f}} \mathbf{F}(\mathbf{r}) \cdot \mathrm{d}\mathbf{r}.
```
The right-hand side represents the <mark>work done by the force</mark> during the particle's motion along its path. If this work is positive, it shows up as an <mark>increase in kinetic energy</mark>. Conversely, if the work integral is negative, the kinetic energy of the body decreases. We can rearrange the equation as:
```{math}
(T_f - T_i) - \int_{\mathbf{r_i}}^{\mathbf{r_f}} \mathbf{F}(\mathbf{r}) \cdot \mathrm{d}\mathbf{r} = 0.
```
If we can define a function $ V $, known as <mark>potential energy</mark>, such that $ \mathbf{F} = -\nabla V $, this becomes:
```{math}
(T_f - T_i) + (V_f - V_i) = 0,
```
or, in other words, the <mark>total (kinetic plus potential) energy $ T + V $ is conserved during motion</mark>. If the particle moves from any initial point around a closed path back to that point, no net work will have been done on it by the force field. Forces that can be expressed as gradients of scalar functions are known as <mark>conservative forces</mark> (the scalar function is usually known as <mark>potential energy</mark>, or <mark>potential</mark> if referring to energy per unit mass).

### Example: Variation of Gravity with Height

Consider a small body of mass $ m $ falling vertically towards Earth. A single coordinate $ x $ can describe its position above Earth's surface, where $ R_E + x $ (with $ R_E $ as Earth's radius) is the distance between the body and Earth's center.

The force on the body due to Earth's gravitational field has magnitude $ \frac{G M_E m}{(R_E + x)^2} $, where $ M_E $ is Earth's mass, directed radially inwards. The equation of motion for purely radial motion becomes:
```{math}
m \ddot{x} = -\frac{G M_E m}{(R_E + x)^2}.
```
Let's integrate the left-hand side by setting:
```{math}
\ddot{x} = \frac{\mathrm{d}}{\mathrm{d}t} \left( \frac{\mathrm{d}x}{\mathrm{d}t} \right) = \frac{\mathrm{d}x}{\mathrm{d}t} \frac{\mathrm{d}}{\mathrm{d}x} \left( \frac{\mathrm{d}x}{\mathrm{d}t} \right) = v \frac{\mathrm{d}v}{\mathrm{d}x} = \frac{\mathrm{d}}{\mathrm{d}x} \left( \frac{1}{2} v^2 \right).
```
Dropping $ m $ from both sides, we get:
```{math}
\int_{x=x_0}^{x_f} \frac{\mathrm{d}}{\mathrm{d}x} \left( \frac{1}{2} v^2 \right) \, \mathrm{d}x = \int_{x=x_0}^{x_f} -\frac{G M_E}{(R_E + x)^2} \, \mathrm{d}x,
```
```{math}
\Rightarrow \frac{1}{2} (v_f^2 - v_0^2) = \left[ \frac{G M_E}{R_E + x} \right]_{x_0}^{x_f},
```
```{math}
\Rightarrow \frac{1}{2} (v_f^2 - v_0^2) = - \left( -\frac{G M_E}{R_E + x_f} - -\frac{G M_E}{R_E + x_0} \right).
```

This is another form of the energy equation, where we identify the gravitational potential as $ U(x) = -\frac{G M_E}{R_E + x} $. As the body falls, kinetic energy increases (becomes more positive) at the cost of potential energy, which decreases (becomes more negative).

Since gravitational acceleration $ g $ at Earth's surface is $ g = \frac{G M_E}{R_E^2} $, we can also write the potential function as:
```{math}
U(x) = -\frac{g R_E}{1 + \frac{x}{R_E}}.
```
For a body thrown vertically upward from the surface ($ x = 0 $), with initial speed $ v_0 $, we have:
```{math}
:label: eq:vfsqrd
v_f^2 &= v_0^2 -2\,g\,R_E\,(-1/(1+x_f/R_E) + 1/(1+0/R_E))  \\ 
&= v_0^2 -2\,g\,R_E\,(1-1/(1+x_f/R_E)) \\
&= v_0^2 -2\,g\,x_f/(1+x_f/R_E).
```

This equation lets us explore aspects of the trajectory. The <mark>maximum height</mark> $ x_{max} $ reached by the body, where $ v_f = 0 $, is given by:
```{math}
:label: eq:xmax
x_f = x_{max} = \frac{v_0^2}{2g} \left( 1 - \frac{v_0^2}{2 g R_E} \right)^{-1}.
\tag{3}
```

If $ x \ll R_E $, {eq}`eq:vfsqrd` approximates to $ v_f^2 \approx v_0^2 - 2 g x_f $, familiar from cases with close-to-constant downward acceleration $ g $.

Similarly, for $v_0^2 \ll 2gR_E$, {eq}`eq:xmax` reduces to $x_{max} \approx v_0^2/(2g)$.

From the exact expression {eq}`eq:xmax`, we see that for $ x_{max} \to \infty $, the <mark>escape velocity</mark> can be found by setting $ v_0^2 = v_{esc}^2 = 2 g R_E $. For $ g = 9.8 \, \mathrm{m \cdot s^{-2}} $ and $ R_E = 6400 \, \mathrm{km} $, we find $ v_{esc} \approx 11 \, \mathrm{km \cdot s^{-1}} $. Similar values apply for other planets with different masses and radii.

## Fluid Resistance: Terminal Velocity

For a body falling through a fluid that resists its motion (such as through viscous drag), we can examine an equation of motion as follows:
```{math}
m \frac{\mathrm{d}v}{\mathrm{d}t} = -mg - cv,    
```
where $ c > 0 $ is a constant, and $ g $ is the local gravitational acceleration, assumed constant here. This setup includes a "resisting" term proportional to the velocity $ v $. Rearranging and integrating from time zero to a final time $ t_f $:
```{math}
\int_{v_0}^{v(t_f)} \frac{-1}{g + \frac{cv}{m}} \, \mathrm{d}v &= \int_0^{t_f} \mathrm{d}t,\\
\Rightarrow \left(-\frac{m}{c}\right) \ln\left(\frac{g + \frac{cv(t_f)}{m}}{g + \frac{cv_0}{m}}\right) &= t_f,\\
\Rightarrow v(t_f) &= -\frac{gm}{c} + \exp\left(-\frac{ct_f}{m}\right)\left(\frac{mg}{c} + v_0\right).
```

As $ t_f \gg \frac{m}{c} $, the magnitude of $ v $ approaches the </mark>terminal speed</mark> $ v_t = \frac{gm}{c} $. Setting the characteristic time scale $ \tau = \frac{m}{c} $, we can rewrite $ v(t_f) $ as:
```{math}
v(t_f) = -v_t \left(1 - \exp\left(-\frac{t_f}{\tau}\right)\right) + v_0 \exp\left(-\frac{t_f}{\tau}\right).
```

This form clarifies that terminal velocity is approached </mark>exponentially</mark> over time, while the initial motion $ v_0 $ </mark>fades exponentially</mark>. The time scale for both processes, $ \tau $, is shorter for larger values of $ c $, corresponding to a more viscous fluid.

## Centrifugal Force and Rotating Frames of Reference

In investigating equations of motion, it's important to note how the chosen coordinate frame affects their form. Here, we compare a fixed coordinate system $ S $ with axes $ (x, y, z) $ to a rotating system $ S^{\prime} $ with axes $ (x^{\prime}, y^{\prime}, z^{\prime}) $ that share the same origin as $ S $ and rotate about a direction given by unit vector $ \mathbf{n} $ (see {numref}`fig:rotnaxes`). The angular velocity vector of the primed axes, as seen in frame $ P $, is $ \mathbf{\omega} = \omega \mathbf{n} $. The direction of $ \mathbf{n} $ follows a right-handed sense with respect to the rotation.


```{figure} Figs/rotnaxes.png
---
name: fig:rotnaxes
---
The angular velocity vector $\vec{\omega}$ describes the rotation of the primed axes / frame, $S'$, as observed in the unprimed frame $S$.  From Fowles and Cassiday.
```

At any time, the coordinates of a point in space can be described by either $ (x, y, z) $ or $ (x', y', z') $, depending on the frame chosen. The full position vector must be equivalent between frames:
```{math}
\mathbf{r} = \mathbf{i} x + \mathbf{j} y + \mathbf{k} z = \mathbf{i'} x' + \mathbf{j'} y' + \mathbf{k'} z'.
```

To examine the velocity in both frames, we differentiate with respect to time. The unit vectors in $ S' $ rotate over time, while those in $ S $ remain fixed:
```{math}
\mathbf{i} \frac{\mathrm{d}x}{\mathrm{d}t} + \mathbf{j} \frac{\mathrm{d}y}{\mathrm{d}t} + \mathbf{k} \frac{\mathrm{d}z}{\mathrm{d}t} = \mathbf{i'} \frac{\mathrm{d}x'}{\mathrm{d}t} + \mathbf{j'} \frac{\mathrm{d}y'}{\mathrm{d}t} + \mathbf{k'} \frac{\mathrm{d}z'}{\mathrm{d}t} + x' \frac{\mathrm{d}\mathbf{i'}}{\mathrm{d}t} + y' \frac{\mathrm{d}\mathbf{j'}}{\mathrm{d}t} + z' \frac{\mathrm{d}\mathbf{k'}}{\mathrm{d}t}.
```

A corotating observer in $ S' $ sees a velocity with components $ \left( \frac{\mathrm{d}x'}{\mathrm{d}t}, \frac{\mathrm{d}y'}{\mathrm{d}t}, \frac{\mathrm{d}z'}{\mathrm{d}t} \right) $. Defining this velocity vector as $ \mathbf{v'} $, the velocity relation between frames is:
```{math}
\mathbf{v} = \mathbf{v'} + x' \frac{\mathrm{d}\mathbf{i'}}{\mathrm{d}t} + y' \frac{\mathrm{d}\mathbf{j'}}{\mathrm{d}t} + z' \frac{\mathrm{d}\mathbf{k'}}{\mathrm{d}t}.
```

For any vector $ \mathbf{p'} $ of fixed magnitude rotating about a fixed axis with angular velocity $ \mathbf{\omega} $, the rate of change is:
```{math}
\frac{\mathrm{d}\mathbf{p'}}{\mathrm{d}t} = \mathbf{\omega} \times \mathbf{p'}.
```
To understand this, we note that, in a small time increment $\delta t$, the change in the vector will point along the local direction of its rotation, which is the direction of the corresponding cross product $\mathbf{\omega} \times \mathbf{p'}\,\delta t$. Thus for our general velocity relation, we can write:
```{math}
:label: eq:vdefn
\mathbf{v} = \mathbf{v'} + x' (\mathbf{\omega} \times \mathbf{i'}) + y' (\mathbf{\omega} \times \mathbf{j'}) + z' (\mathbf{\omega} \times \mathbf{k'}) = \mathbf{v'} + \mathbf{\omega} \times \mathbf{r'}.
```

### Acceleration Relation
To find a relation between acceleration vectors, we use the definition of $ \mathbf{v'} $:
```{math}
\frac{\mathrm{d}\mathbf{v'}}{\mathrm{d}t} = \ddot{x'} \mathbf{i'} + \ddot{y'} \mathbf{j'} + \ddot{z'} \mathbf{k'} + \dot{x'} \mathbf{\omega} \times \mathbf{i'} + \dot{y'} \mathbf{\omega} \times \mathbf{j'} + \dot{z'} \mathbf{\omega} \times \mathbf{k'} = \mathbf{a'} + \mathbf{\omega} \times \mathbf{v'}.
```
Here, the components of the vector $\mathbf{a'}$ are the same acceleration components that would be perceived by the co-rotating observer. In a similar manner to how we derived
$\frac{\mathrm{d}\mathbf{v'}}{\mathrm{d}t}$ above, we could also show that:

```{math}
\frac{\mathrm{d}\mathbf{r'}}{\mathrm{d}t} = \mathbf{v'} + \mathbf{\omega} \times \mathbf{r'}.
```
Returning now to {eq}`eq:vdefn`, we can differentiate both sides, making use of the above expressions for both $\frac{\mathrm{d}\mathbf{v'}}{\mathrm{d}t}$ and $\frac{\mathrm{d}\mathbf{r'}}{\mathrm{d}t}$:
```{math}
\mathbf{a} = \frac{\mathrm{d}\mathbf{v}}{\mathrm{d}t} = \frac{\mathrm{d}\mathbf{v'}}{\mathrm{d}t} + \dot{\mathbf{\omega}} \times \mathbf{r'} + \mathbf{\omega} \times \frac{\mathrm{d}\mathbf{r'}}{\mathrm{d}t},
```
```{math}
= \mathbf{a'} + \mathbf{\omega} \times \mathbf{v'} + \dot{\mathbf{\omega}} \times \mathbf{r'} + \mathbf{\omega} \times (\mathbf{v'} + \mathbf{\omega} \times \mathbf{r'}).
```
Simplifying gives:
```{math}
\mathbf{a} = \mathbf{a'} + 2 \mathbf{\omega} \times \mathbf{v'} + \dot{\mathbf{\omega}} \times \mathbf{r'} + \mathbf{\omega} \times (\mathbf{\omega} \times \mathbf{r'}).
```

This expression relates actual acceleration $ \mathbf{a} $ to apparent acceleration $ \mathbf{a'} $, where the terms on the right include position and velocity in the rotating frame. Rearranging for $ \mathbf{a'} $ reveals that:
- $ -2 \mathbf{\omega} \times \mathbf{v'} $: </mark>Coriolis acceleration</mark>
- $ -\mathbf{\omega} \times (\mathbf{\omega} \times \mathbf{r'}) $: </mark>Centrifugal acceleration</mark>
- $ -\dot{\mathbf{\omega}} \times \mathbf{r'} $: </mark>Transverse acceleration</mark>

In frame $ S $, the equation of motion for a particle of mass $ m $ is $ \mathbf{F} = m \mathbf{a} $. Replacing $ \mathbf{a} $ with the above, the analogous equation in $ S' $ becomes:
```{math}
:label: eq:eomrot
m \mathbf{a'} = \mathbf{F} - 2 m \mathbf{\omega} \times \mathbf{v'} - m \mathbf{\omega} \times (\mathbf{\omega} \times \mathbf{r'}) - m \dot{\mathbf{\omega}} \times \mathbf{r'}.
```

Here, the observer in $ S' $ includes these </mark>inertial forces</mark> to determine the motion in their frame. The right-hand side terms represent the real force, Coriolis force, centrifugal force, and transverse force.

The Coriolis force deflects moving particles at right angles to their motion. It affects airflow around pressure systems in Earth's atmosphere. The centrifugal force, always directed outward from the rotation axis, has magnitude $ m r' \sin \theta \, \omega^2 $, where $ r' \sin \theta $ is the distance between the particle and the rotation axis.

## Example: Motion in the Earth's Corotating Frame

### The Local Vertical

Let's start by considering what we are really measuring when we use a hanging weight (often known as a plumb bob) to define the local vertical direction at its location on the surface of the rotating Earth. Because the Earth is rotating, the plumb direction (the direction of the string from which the weight hangs) generally does not point exactly towards the Earth's centre (in fact, the surface of the Earth is not perfectly spherical). The exception is if it is situated along the Earth's equator or at either rotational pole.

To understand why, let's consider a frame of reference where the weight, or plumb bob, is at the origin (see {numref}`fig:plumbbobaxes`). As the Earth rotates, it carries this local reference frame around. Thus, the axes rotate, and they also undergo a translational motion—illustrated by the origin tracing a circle of radius $ R_E \cos \lambda $ once per planetary rotation, where $ R_E $ is the radius of the Earth and $ \lambda $ is the geocentric latitude of the weight.


```{figure} Figs/plumbbobaxes.png
---
name: fig:plumbbobaxes
---
Forces on a plumb bob hanging just above a location of longitude $ \lambda $ on the Earth's surface. The primed axes shown form a rotating reference frame in which the bob appears stationary. From Fowles and Cassiday.
```

Let us now think about each of the terms in {eq}`eq:eomrot` and the form they take for our simple example of a hanging bob at rest in this frame of reference. Firstly, the bob is stationary and not accelerating in this frame, hence $ \mathbf{a'} = 0 $. The centrifugal force on the bob, since we have placed it at the origin position $ \mathbf{r'} = 0 $, must also be zero. There is no transverse force as we are assuming the Earth rotates at a steady rate and so $ \dot{\omega} = 0 $. Because the bob is at rest in this frame, $ \mathbf{v'} = 0 $, which means the Coriolis force is zero. Thus, the only surviving term is $ \mathbf{F} $, the sum of the real forces on the bob. There is another term we have to include, which was not derived in the work leading to {eq}`eq:eomrot`. Since our coordinate axes are rotating about a particular direction, _as well as their origin undergoing a translational motion_, we need to add an apparent force of the form $ -m \mathbf{A_0} $, linked to the acceleration associated with the translational part of the motion. Hence, in our reference frame, the equation of motion for the bob is equivalent to

```{math}
\mathbf{F} - m \mathbf{A_0} = 0.
```

The acceleration $ \mathbf{A_0} $ is simply the acceleration associated with the translational motion of the frame origin as the Earth rotates. Thus, it has magnitude $ R_E \omega^2 \cos \lambda $, where $ \omega $ is the Earth's angular velocity. Clearly, it takes on its maximum value at the equator $ \lambda = 0 $ (it is always directed towards the Earth's axis of rotation) and falls to zero at the poles. At the equator, its presence accounts for a small, but finite $ \sim 1\% $ correction that must be applied to the real acceleration due to gravity in order to obtain the correct magnitude and direction of the local acceleration along the local vertical direction (defined by the direction of the vector $ \mathbf{F} - m \mathbf{A_0} $ — see {numref}`fig:plumbbobdirn`).


```{figure} Figs/plumbbobdirn.png
---
name: fig:plumbbobdirn
---
Forces on the plumb bob; Forces which define the weight of the plumb bob, $ m \mathbf{g} $. From Fowles and Cassiday.
```


The "effective" force $ m \mathbf{g} $ on the plumb bob, which we usually define as the local force due to gravity in our corotating frame, is thus actually the real force due to gravity $ m \mathbf{g_0} $, plus the inertial force $ -m \mathbf{A_0} $, due to acceleration of our frame of reference. This is illustrated in {numref}`fig:plumbbobdirn`, which shows that the presence of the inertial force deflects the bob away from the direction of $ \mathbf{g_0} $ by a small angle $ \epsilon $. Applying the law of sines to the triangle of forces shown gives us:

```{math}
\frac{\sin \epsilon}{m \omega^2 R_E \cos \lambda} = \frac{\sin \lambda}{mg}.
```

Since $ \epsilon $ is small, we can make the approximation $ \sin \epsilon \approx \epsilon $ and rearrange to obtain:

```{math}
\sin \epsilon \approx \epsilon = \frac{\omega^2 R_E}{g} \cos \lambda \sin \lambda = \frac{\omega^2 R_E}{2g} \sin (2 \lambda).
```

The angle $ \epsilon $, as expected, vanishes at the equator and the poles, and takes on its maximum value at $ \lambda = 45^{\circ} $, which is only $ 0.1^{\circ} $. It is important to note that, in this analysis, we have implicitly assumed that the actual gravitational acceleration $ \mathbf{g_0} $ is constant and directed towards the Earth's centre. This is not strictly valid — the Earth's ellipsoid shape plus local topography make the exact calculation difficult; however, corrections due to such effects will generally be small.

### Projectile Motion

We will now make use of the results and symbols from the last section to write a more general equation of motion for a projectile moving near the Earth's surface, whose motion is described in a similar, corotating frame illustrated in {numref}`fig:projaxes`. The origin lies at a fixed latitude and longitude. The axes are oriented such that the $ z' $ axis is along the upward vertical direction (as defined by the direction of the string from which a static weight hangs), $ y' $ points locally northward and $ x' $ points locally eastward. Our equation of motion in this frame of reference is thus:

```{math}
m \frac{\mathrm{d}^2 \mathbf{r'}}{\mathrm{d}t^2} = \mathbf{F} + m \mathbf{g} - 2m \mathbf{\omega} \times \frac{\mathrm{d} \mathbf{r'}}{\mathrm{d}t} - m \mathbf{\omega} \times (\mathbf{\omega} \times \mathbf{r'}),
```

where $ \mathbf{F} $ is any actual applied force, other than gravity, $ \mathbf{g} = \mathbf{g_0} - \mathbf{A_0} $, and we have added the Coriolis and centrifugal terms since our projectile is moving.

```{figure} Figs/projaxes.png
---
name: fig:projaxes
---
Axes for analysing projectile motion (Fowles and Cassiday).
```

Let us simplify the problem by ignoring forces such as air resistance and setting $ \mathbf{F} = 0 $. We will also ignore the centrifugal force, since it is usually very small compared with the other terms, in practice. Thus:

```{math}
m \frac{\mathrm{d}^2 \mathbf{r'}}{\mathrm{d}t^2} = m \mathbf{g} - 2m \mathbf{\omega} \times \frac{\mathrm{d} \mathbf{r'}}{\mathrm{d}t}.
```

With the axes we have chosen, we can define unit vectors $ \mathbf{i'}, \mathbf{j'}, \mathbf{k'} $ along the respective $ x', y', z' $ directions. Hence we can write $ \mathbf{g} = -g \mathbf{k'} $ and $ \mathbf{\omega} = \omega \cos \lambda \mathbf{j'} + \omega \sin \lambda \mathbf{k'} $. With some vector algebra, we can show that:

```{math}
\mathbf{\omega} \times \frac{\mathrm{d} \mathbf{r'}}{\mathrm{d}t} = \mathbf{i'} (\omega \dot{z'} \cos \lambda - \omega \dot{y'} \sin \lambda) + \mathbf{j'} (\omega \dot{x'} \sin \lambda) + \mathbf{k'} (-\omega \dot{x'} \cos \lambda).
```

Using this result, the components of the equation of motion now read as:

```{math}
:label: eq:accelwcoriol
\ddot{x'} = -2 \omega (\dot{z'} \cos \lambda - \dot{y'} \sin \lambda), \quad \ddot{y'} = -2 \omega (\dot{x'} \sin \lambda), \quad \ddot{z'} = -g + 2 \omega \dot{x'} \cos \lambda.
```

To finish this section, we will use these equations to analyse how the position of the projectile behaves with time, and investigate the effect of the Coriolis force which arises because of the rotating coordinate frame which we are using to describe the motion.


Assuming our projectile commences its journey at the origin with initial velocity
$(\dot{x'}_0,\dot{y'}_0,\dot{z'}_0)$ at time zero, we can integrate the equations above once with respect to time and obtain descriptions of how the velocity components evolve as functions of time:
```{math}
:label: eq:velwcoriol
    \dot{x'}(t) &= \dot{x'}_0 -2\omega\,({z'(t)}\,\cos\lambda - {y'(t)}\,\sin\lambda), \notag \\
    \dot{y'}(t) &= \dot{y'}_0 -2\omega\,({x'(t)}\,\sin\lambda), \notag \\
    \dot{z'}(t) &= \dot{z'}_0 - gt + 2\omega\,{x'(t)}\,\cos\lambda.
```
We can now substitute the above forms for $\dot{y'}$ and $\dot{z'}$ into the original
equation of motion along the $x'$ direction (first of {eq}`eq:accelwcoriol`).
We obtain:
```{math}
    \ddot{x'} = 2\omega g t \, \cos\lambda - 2\omega \,(\dot{z'}_0\,\cos\lambda
                - \dot{y'}_0\,\sin\lambda),
```
where we have ignored the terms of order $\omega^2$. Integrating again (which is easier now, since the right-hand side is just a linear function of time) gives us a velocity component of the projectile:
```{math}
    \dot{x'}(t) = \dot{x'}_0 + \omega g t^2 \, \cos\lambda 
    - 2\omega t \,(\dot{z'}_0\,\cos\lambda
                - \dot{y'}_0\,\sin\lambda).
```
Now the right-hand side of the equation above is quadratic in time, and comparatively straightforward to integrate once more to acquire position coordinate $x'$ versus time:
```{math}
    {x'}(t) = \dot{x'}_0\,t + \frac{1}{3} \omega g t^3 \, \cos\lambda
              - \omega t^2 \,(\dot{z'}_0\,\cos\lambda
                - \dot{y'}_0\,\sin\lambda).
```
If we substitute the preceding expression for $x'$ into the final two equations of {eq}`eq:velwcoriol`, and then integrate those, we obtain these equations for the evolution of $y'$ and $z'$:
```{math}
    {y'}(t) &= \dot{y'}_0 t - \omega \dot{x'}_0 t^2 \, \sin\lambda,  \\
    {z'}(t) &= \dfrac{-1}{2} g t^2 + \dot{z'}_0 t + \omega\,\dot{x'}_0 t^2 \cos\lambda.
```
The terms involving $\omega$ in the expressions for projectile position coordinates represent the effect of the Earth's rotation, and describing the motion in a coordinate system fixed to the Earth itself. Note that if we omit these terms, we retrieve the familiar parabolic trajectory in a single plane for problems where the only acceleration
comes from a uniform downwards gravitational term, $-g\vec{k'}$.

