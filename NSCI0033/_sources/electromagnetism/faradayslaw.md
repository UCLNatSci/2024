# Faraday's Law
Our discussion of both the Biot-Savart and Ampère's laws tells us that moving charges (currents) produce magnetic fields.  Since these currents 
are pushed by potential difference - driven by electric fields, these result in a magnetic field.  The next question is can we start with a magnetic 
field and finish with an electric field - Faraday's law tells us yes!  

Thinking again about the link between moving charges and magnetic fields:
```{math}
Q\,{\bf v} \propto {\bf B}
```
As we mentioned previously, we can think of $Q\,{\bf v}$ is a <b>current momentum</b>, therefore taking the time derivative should produce a <b>current force</b>:
```{math}
\frac{\partial {\bf B}}{\partial t}  \propto \frac{\partial}{\partial t}\left(Q\,{\bf v} \right)
```
and we call this the electromotive force (EMF), denoted by $\mathcal{E}$.  

One potential question here is, as we saw in {numref}`BiotSavart`, an element of current carrying wire $I\,\mathrm{\bf d} \ell$ produces a whole plane of magnetic 
field.  Therefore to calculate the total contribution to the EMF, we need to find the magnetic flux $\Phi_B$, giving us the form of Faraday's law:
```{math}
:label: FaradaysLaw
\mathcal{E}  = -\frac{\partial \Phi_B}{\partial t} = - \frac{\partial}{\partial t} \iint_A {\bf B}\cdot\mathrm{d}{\bf A}
```

A charge $ q $ moving with velocity $ \mathbf{v} $ in electromagnetic fields experiences the Lorentz force
```{math}
\mathbf{F} = q(\mathbf{E} + \mathbf{v} \times \mathbf{B}).
```

In a purely magnetic field ($ \mathbf{E} = 0 $), the force is always perpendicular to the velocity. As a result magnetic fields can change the *direction* of motion of a charge, but they do **no work** on a free charge in uniform motion.

This raises an important question - **how can a magnetic field produce a voltage in a circuit?**

Consider a magnet moving past a stationary conductor or loop.

- In the **rest frame of the magnet**, the magnetic field is static, but charges in the conductor are moving.
  They experience a magnetic force $ q(\mathbf{v} \times \mathbf{B}) $.
- In the **rest frame of the conductor**, charges may initially be at rest, yet a force still acts on them and a current is induced.

In this frame, the effect of the moving magnetic field is described as an **induced electric field** acting around the loop.

**Key idea:**

> A changing magnetic flux can be viewed as producing an effective electric field that drives charges around a closed path.

This motivates the definition of emf as a loop integral rather than as a conservative potential difference.

Consider a straight conducting rod of length $ L $ moving with speed $ v $ through a uniform magnetic field $ \mathbf{B} $, with
$ \mathbf{v} \perp \mathbf{B} $.

A charge in the rod experiences a magnetic force
```{math}
F = qvB.
```

Charge separation continues until an electric field $ \mathbf{E} $ builds up such that
```{math}
qE = qvB \quad \Rightarrow \quad E = vB.
```

The potential difference across the rod is
```{math}
\Delta V = \int \mathbf{E}\cdot d\mathbf{l} = EL = vBL.
```

Hence the motional emf is
```{math}
\mathcal{E} = BLv.
```

Now place the moving rod into a rectangular circuit so that the area enclosed by the loop changes with time.

If the rod moves a distance $ x(t) $,
```{math}
A(t) = Lx(t).
```

For a uniform magnetic field perpendicular to the loop,
```{math}
\Phi_B(t) = BA(t) = BLx(t).
```

Differentiating,
```{math}
\frac{d\Phi_B}{dt} = BL\frac{dx}{dt} = BLv.
```

Therefore,
```{math}
\mathcal{E} = -\frac{d\Phi_B}{dt}
```
where the minus sign encodes Lenz’s law.

This shows that Faraday’s law captures both, an emf due to a **time-varying magnetic field**, and an emf due to **motion of conductors through a magnetic field**.

If we have a coil of wire, with $N$ turns of wire, each of which cuts through magnetic field lines, as we see in {numref}`MagnetInACoil`. 
Faraday's law applies to each turn, it acts like a series circuit across the field and so the EMF induced becomes an additive process, and so we have:
```{math}
\mathcal{E} = -N\,\frac{\partial \Phi_B}{\partial t}
```
Note that the two sides of Equation {eq}`FaradaysLaw` differ by a sign, this is known as <b>Lenz's law</b>.  This is here to ensure that we do not 
violate conservation of energy - the direction of an induced current which is pushed by the EMF $\mathcal{E}$ is always such as to oppose the change in the magnetic 
field that produces it.  This means that if we push a permanent magnet into a coil of wire, as we see in {numref}`MagnetInACoil`, the EMF which will push a 
current such that the magnetic field that Amp\`eres law predicts would be created will oppose the magnetic field of the permanent magnet.  If the current flowed in 
then opposite direction, it would cause the magnet to be dragged into coil faster and faster, creating a flow of limitless energy (which is clearly impossible).

```{figure} ../figures/MagnetInACoil1.png
---
name: MagnetInACoil
---
Direction of induced EMF from a moving magnetic into a coil, <b> Left</b> - North pole moving into coil, <b> Right </b> - North pole moving out of coil.
```

## Electrical Transformers
We can apply Faraday's law to investigate the flow of magnetic fields and EMF's in a transformer, as depicted in {numref}`Transformer`, where an initial 
voltage $V_p$ typically pushes an initially large current $I_p$ in the primary circuit and through the primary coil.
```{figure} ../figures/Transformer.png
---
name: Transformer
--- 
Flow of magnetic flux in a transformer - we denote the left hand coil the Primary and right hand coil the Secondary, each carries a current $I_{p,s}$ and EMF $V_{p,s}$.
```
The alternating voltage in the primary circuit, say:
```{math} 
V_p(t) = V_0\cos(\omega \,t)
``` 
with some ohmic resistance $R_p$, which pushes 
a current 
```{math} I_p = \frac{V_p}{R_p} = \frac{V_0}{R_p}\cos(\omega\,t) 
``` 
through the primary coil.  The total input energy in the primary coil therefore is: 
```{math} 
P_{in} = V_p\,I_p = \frac{{V_0}^2}{R_p}\cos^2(\omega\,t)
``` 
and this is related to the output energy $P_{out} = V_s\,I_s$, with $P_{in} = P_{out}$.  By Ampère's law, we can see the time varying current creates a 
time varying magnetic field $\Phi_B(t)$ in the primary coil.  Then by Faraday's law, the changing flux is related to the induced EMF $\mathcal{E}$ in each coil as:
```{math}
V_p &=&\, -N_p\,\frac{\mathrm{d}\Phi_B(t)}{\mathrm{d} t}\\
V_s &=&\, -N_s\,\frac{\mathrm{d}\Phi_B(t)}{\mathrm{d} t}
```
Since the magnetic flux moves through the iron core (and ignoring any losses), then we can combine the equations to find:
```{math}
-\frac{\mathrm{d} \Phi_B(t)}{\mathrm{d} t} = \frac{V_p}{N_p} = \frac{V_s}{N_s} \Longrightarrow \frac{V_p}{V_s} = \frac{N_p}{N_s} = a
```
where $a$ is the so called turns ratio.  Combining with the energy conservation condition $V_p\,I_p = V_s\,I_s$, we find different situations based on ratios of $N_p,\,N_s$:
```{math}
N_p < N_s &\Rightarrow&\, a < 1\,\, \textrm{step up}\\
N_p > N_s &\Rightarrow&\, a > 1\,\, \textrm{step down}
```

