# Weeks 6–10 — Investigating Chaos

## Introduction

Chaos is a phenomenon in deterministic dynamical systems in which
long-term behaviour becomes practically unpredictable despite the
governing laws being exact and non-random.

A dynamical system describes how a state evolves in time.  
It can be written either as:

*Continuous-time system (flow)*

```{math}
\frac{d\mathbf{x}}{dt} = \mathbf{f}(\mathbf{x}),
```

where:

- $\mathbf{x}(t) \in \mathbb{R}^n$ is the state vector,
- $\mathbf{f}$ is a deterministic nonlinear function.

*Discrete-time system (map)*

```{math}
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n),
```

where:

- $\mathbf{x}_n$ is the state at step $n$,
- $\mathbf{F}$ is a deterministic update rule.

In both cases:

- There is **no randomness** in the equations.
- Once an initial condition is specified, the entire future trajectory is uniquely determined (assuming standard existence and uniqueness conditions).



### Determinism Does Not Imply Predictability

A central insight of chaos theory is:

```{math}
\text{Deterministic laws} \;\not\Rightarrow\; \text{Long-term predictability}.
```

Even when equations are perfectly known, arbitrarily small uncertainties
in the initial condition can grow exponentially with time.
Because real measurements always have finite precision, this leads to
practical unpredictability.

Thus, chaos represents a breakdown of long-term prediction —
not a breakdown of determinism.

### Discrete vs Continuous-Time Chaos

Chaos can occur in both:

*Discrete-Time Systems (Maps)*

- Often lower-dimensional.
- Can exhibit chaos even in one dimension.
- Example: the logistic map

```{math}
x_{n+1} = r x_n (1 - x_n).
```

*Continuous-Time Systems (Flows)*

- Governed by differential equations.
- Require sufficient phase-space dimension.
- Autonomous systems in two dimensions cannot exhibit chaos
  (Poincaré–Bendixson theorem).
- Chaos typically requires:
  - At least three dimensions, or
  - Explicit time-dependent forcing.

Example: the Lorenz system

```{math}
\begin{aligned}
\dot{x} &= \sigma (y - x), \\
\dot{y} &= x(\rho - z) - y, \\
\dot{z} &= xy - \beta z.
\end{aligned}
```



### What Makes Chaos Special?

Chaotic systems are characterised by a combination of:

- Deterministic evolution,
- Exponential sensitivity to initial conditions,
- Bounded yet aperiodic motion,
- Complex geometric structure in phase space.

They are neither random nor simply complicated —
they are structured, lawful systems exhibiting instability and recurrence.

The following sections formalise these properties,
introduce quantitative diagnostics,
and demonstrate how chaos is identified in both
discrete and continuous-time systems.

## Hallmarks of Chaotic Behaviour

Chaos is not defined by visual irregularity or mere complexity,
but by a specific combination of dynamical and geometric properties.

The following features characterise chaotic systems at a conceptual level.
Precise quantitative tests are introduced later.


### Sensitive Dependence on Initial Conditions

A defining property of chaos is **sensitive dependence on initial conditions**.

If two trajectories begin arbitrarily close in phase space,

```{math}
\mathbf{x}_0
\quad \text{and} \quad
\mathbf{x}_0 + \delta \mathbf{x}_0,
```

then their separation typically grows exponentially:

```{math}
\|\delta \mathbf{x}(t)\|
\approx
\|\delta \mathbf{x}_0\| e^{\lambda t},
```

where:

- $\|\delta \mathbf{x}(t)\|$ is the distance between trajectories,
- $\lambda > 0$ represents an exponential growth rate.

This phenomenon is often called the **butterfly effect**.

Because real measurements have finite precision,
exponential growth of errors leads to practical unpredictability,
even though the equations themselves are deterministic.

(Exponential growth rates are quantified using Lyapunov exponents,
introduced in Section 3.)

### Aperiodic but Bounded Long-Term Behaviour

Chaotic trajectories:

- Do not converge to stable fixed points,
- Do not settle into stable periodic orbits,
- Never exactly repeat.

Formally, there is no finite $T > 0$ such that

```{math}
\mathbf{x}(t + T) = \mathbf{x}(t)
\quad \text{for all } t.
```

However, chaotic motion is typically **bounded**:

```{math}
\|\mathbf{x}(t)\| < C
\quad \text{for all } t \ge 0,
```

for some constant $C$.

Thus chaos combines:

- Instability,
- Non-periodicity,
- Long-term confinement to a structured region of phase space.

This distinguishes chaos from:

- Simple periodic oscillation,
- Quasi-periodic motion on invariant tori,
- Unbounded exponential growth.

### Topological Mixing

Chaos is not only locally unstable but also globally intertwined.

A system is **topologically mixing** on an invariant set $\mathcal{A}$
if, for any two nonempty open sets $U, V \subset \mathcal{A}$,
there exists a time $T$ such that

```{math}
\phi^t(U) \cap V \neq \varnothing
\quad \text{for all } t > T,
```

where $\phi^t$ denotes the flow (or iterated map).

Intuitively:

- Any small region of phase space eventually spreads throughout the accessible region.
- The system continually redistributes trajectories.

Mixing implies long-term loss of information about
where trajectories originated.



### Dense Periodic Orbits

Although typical chaotic trajectories are aperiodic,
periodic orbits are densely embedded within the chaotic set.

Let $\mathcal{A}$ be an invariant chaotic set.
Periodic orbits are **dense** in $\mathcal{A}$ if:

For every point $\mathbf{x} \in \mathcal{A}$
and every neighbourhood $U$ of $\mathbf{x}$,

```{math}
U \cap \{\text{periodic points}\} \neq \varnothing.
```

Thus:

- Infinitely many periodic motions exist,
- They lie arbitrarily close to every chaotic trajectory,
- They are typically unstable.

Chaotic motion can be viewed as trajectories
continually shadowing different unstable periodic orbits.



### Strange Attractors (Dissipative Systems)

In dissipative systems, chaotic motion often occurs on a
**strange attractor**.

An attractor $\mathcal{A}$ satisfies:

1. **Invariance**
   ```{math}
   \phi^t(\mathcal{A}) = \mathcal{A}
   \quad \text{for all } t \ge 0.
   ```

2. **Attraction**
   Nearby trajectories converge toward $\mathcal{A}$.

A strange attractor additionally exhibits:

- Sensitive dependence on initial conditions,
- Complex geometric structure,
- Typically fractal (non-integer) dimension.

Such attractors arise from repeated stretching
(exponential instability)
combined with folding and dissipation
(which keep trajectories bounded).

The Lorenz attractor is a classical example.

## Quantitative Diagnostics of Chaos

The hallmarks of chaos describe qualitative behaviour.
To determine whether a system is chaotic in practice,
we require **quantitative diagnostics**.

This section develops the main mathematical tools used
to detect and measure chaos.



### Lyapunov Exponents and Predictability Time

The most fundamental quantitative signature of chaos
is the existence of a **positive Lyapunov exponent**.



### Linearised Dynamics (Continuous Time)

Consider

```{math}
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
```

and let $\mathbf{x}(t)$ be a trajectory.

A small perturbation evolves according to the linearised equation

```{math}
\frac{d}{dt}\delta \mathbf{x}
=
D\mathbf{f}(\mathbf{x}(t))\, \delta \mathbf{x},
```

where $D\mathbf{f}$ is the **Jacobian matrix** of $\mathbf{f}$ with respect to the state $\mathbf{x}$.

Let $\mathbf{f} : \mathbb{R}^n \to \mathbb{R}^n$ with components
```{math}
\mathbf{f}(\mathbf{x}) = (f_1(\mathbf{x}), f_2(\mathbf{x}), \dots, f_n(\mathbf{x}))^\top,
\quad
\mathbf{x} = (x_1, x_2, \dots, x_n)^\top.
```

Then the Jacobian evaluated along the trajectory $\mathbf{x}(t)$ is the $n\times n$ matrix
```{math}
D\mathbf{f}(\mathbf{x}(t))
=
\left[
\frac{\partial f_i}{\partial x_j}\big(\mathbf{x}(t)\big)
\right]_{i,j=1}^n
=
\begin{pmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_n}{\partial x_1} & \frac{\partial f_n}{\partial x_2} & \cdots & \frac{\partial f_n}{\partial x_n}
\end{pmatrix}_{\mathbf{x}=\mathbf{x}(t)}.
```

Equivalently, $D\mathbf{f}(\mathbf{x})$ is the linear map that gives the first-order Taylor expansion
```{math}
\mathbf{f}(\mathbf{x} + \delta\mathbf{x})
\approx
\mathbf{f}(\mathbf{x}) + D\mathbf{f}(\mathbf{x})\,\delta\mathbf{x}.
```



### Definition

The Lyapunov exponent associated with a perturbation direction is

```{math}
\lambda
=
\lim_{t \to \infty}
\frac{1}{t}
\ln
\frac{\|\delta \mathbf{x}(t)\|}
     {\|\delta \mathbf{x}(0)\|}.
```

An $n$-dimensional system has a full **Lyapunov spectrum**

```{math}
\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_n.
```


### Criterion for Chaos

```{math}
\boxed{\lambda_1 > 0}
```

A positive largest exponent guarantees exponential divergence:

```{math}
\|\delta \mathbf{x}(t)\|
\sim
e^{\lambda_1 t}.
```

In continuous-time systems:

- One exponent is always zero (flow direction).
- Dissipative chaos typically satisfies
  ```{math}
  \lambda_1 > 0,
  \qquad
  \sum_{i=1}^n \lambda_i < 0.
  ```

We can think of two trajectories in phase space, nearby:
```{figure} ./Orbital_instability.png
---
name: Orbital_instability
---
Explanations of the Lyapunov exponent from phase space.
```


### Discrete-Time Systems

For a map

```{math}
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n),
```

the Lyapunov exponent is

```{math}
\lambda
=
\lim_{N \to \infty}
\frac{1}{N}
\sum_{n=0}^{N-1}
\ln \|D\mathbf{F}(\mathbf{x}_n)\|.
```



### Predictability Time (Lyapunov Time)

If initial uncertainty is $\epsilon$, then

```{math}
t_{\text{predict}}
\approx
\frac{1}{\lambda_1}
\ln\!\left(\frac{1}{\epsilon}\right).
```

The characteristic timescale

```{math}
\tau_L = \frac{1}{\lambda_1}
```

is called the **Lyapunov time**.

It measures how quickly predictability is lost.


### Bifurcations and Routes to Chaos

Chaos typically emerges through parameter variation.

Consider

```{math}
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}; \mu).
```

As $\mu$ changes, qualitative transitions occur.



### Common Routes to Chaos

*Period-Doubling Cascade*

```{math}
\text{period-1}
\rightarrow
\text{period-2}
\rightarrow
\text{period-4}
\rightarrow
\cdots
\rightarrow
\text{chaos}.
```

*Intermittency*

Alternation between near-periodic behaviour and chaotic bursts.

*Crisis*

Sudden change in chaotic attractor size or existence.

*Bifurcation Diagram*

To visualise:

1. Vary parameter $\mu$.
2. Remove transients.
3. Plot long-term values (e.g. maxima or Poincaré points).
4. Identify branches, cascades, and chaotic bands.



### Summary of Diagnostics

Chaos is strongly supported if:

- Largest Lyapunov exponent $ \lambda_1 > 0 $,
- Motion is bounded,
- Attractor has non-integer dimension,
- Power spectrum is broadband,
- Bifurcation structure exhibits known routes to chaos.

These tools provide a rigorous, measurable framework
for identifying chaotic dynamics.

## What Chaos Is Not

Understanding chaos requires distinguishing it from several
commonly confused concepts. Chaos is subtle: it combines
determinism, instability, and geometric structure — but it is
neither randomness nor mere complexity.

Clarifying what chaos is *not* prevents conceptual mistakes.



### Not Randomness

A chaotic system is governed by deterministic equations:

```{math}
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x})
\quad \text{or} \quad
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n).
```

Given an exact initial condition $\mathbf{x}_0$,
the future trajectory is uniquely determined.

In contrast, a stochastic system includes intrinsic randomness:

```{math}
\dot{\mathbf{x}}
=
\mathbf{f}(\mathbf{x})
+
\boldsymbol{\eta}(t),
```

where $\boldsymbol{\eta}(t)$ is a random process.

**Key distinction:**

- Chaos → unpredictability from exponential sensitivity.
- Randomness → unpredictability from probabilistic forcing.

Identical initial conditions in a chaotic system always produce identical trajectories. This is not true in a stochastic system.



### Not Noise

Chaotic signals often *look* noisy in time series plots.
However, chaotic dynamics have:

- Finite-dimensional deterministic structure,
- A well-defined Lyapunov spectrum,
- An invariant attractor.

Noise-driven systems:

- Do not evolve on a finite-dimensional attractor,
- Do not have deterministic stretching-and-folding geometry,
- Often exhibit diffusion rather than bounded structure.

Phase-space reconstruction techniques can distinguish
low-dimensional chaos from high-dimensional noise.



### Not Mere Nonlinearity

Nonlinearity is necessary for chaos — but not sufficient.

For example:

```{math}
\dot{x} = -x + x^3
```

is nonlinear but does not exhibit chaos.

Similarly, many nonlinear systems display:

- Stable fixed points,
- Stable periodic orbits,
- Quasi-periodic motion on invariant tori.

Thus,

```{math}
\text{Nonlinearity} \;\not\Rightarrow\; \text{Chaos}.
```

Additional ingredients are required:
instability, recurrence, and global phase-space structure.



### Not Simple Visual Complexity

A system may appear complicated but still be regular.

Examples:

- Multi-frequency quasi-periodic oscillations,
- High-frequency periodic motion,
- Large linear systems with many oscillatory modes.

Visual irregularity alone does not imply:

- Positive Lyapunov exponent,
- Topological mixing,
- Fractal attractor.

Chaos is defined by precise dynamical properties,
not aesthetic irregularity.



### Not Unbounded Instability

Exponential growth alone is not chaos.

Consider:

```{math}
\dot{x} = x
\quad \Rightarrow \quad
x(t) = x_0 e^t.
```

This system has exponential divergence but:

- No bounded attractor,
- No recurrence,
- No stretching-and-folding mechanism.

Chaos requires bounded motion combined with instability.



### Not Complete Disorder

Although chaotic trajectories are aperiodic and unpredictable
in detail, they are not structureless.

Chaotic systems contain:

- Dense unstable periodic orbits,
- Invariant measures,
- Fractal attractors,
- Statistical regularities.

Chaos is therefore structured instability —
not total disorder.



## Case Study: The Logistic Map

The logistic map is one of the simplest dynamical systems that exhibits
the full transition from stability to chaos.

Despite being a one-dimensional discrete map, it displays:

- Fixed points,
- Period-doubling cascades,
- Chaotic attractors,
- Positive Lyapunov exponents,
- Fractal invariant sets,
- Universal scaling laws.

It is therefore a canonical example of deterministic chaos.



### Definition of the Logistic Map

The logistic map is defined by

```{math}
x_{n+1} = f(x_n) = r x_n (1 - x_n),
```

where:

- $x_n \in [0,1]$,
- $r \in [0,4]$ is a control parameter.

Given an initial value $x_0$, the entire sequence
$\{x_1, x_2, \dots\}$ is completely deterministic.



### Fixed Points and Stability

Fixed points satisfy

```{math}
x^* = r x^*(1 - x^*).
```

Solving gives

```{math}
x_1^* = 0,
\qquad
x_2^* = 1 - \frac{1}{r}.
```

To determine stability, compute

```{math}
f'(x) = r(1 - 2x).
```

A fixed point is stable if

```{math}
|f'(x^*)| < 1.
```

Results:

- $0 < r < 1$: $x^* = 0$ is stable.
- $1 < r < 3$: $x^* = 1 - \frac{1}{r}$ is stable.
- At $r = 3$: the fixed point loses stability.

This marks the first bifurcation.



### Period-Doubling Route to Chaos

At $r = 3$, a **period-doubling bifurcation** occurs:

- The fixed point becomes unstable.
- A stable period-2 orbit emerges.

As $r$ increases:

```{math}
\text{period-2}
\rightarrow
\text{period-4}
\rightarrow
\text{period-8}
\rightarrow
\cdots
```

The bifurcation values accumulate at

```{math}
r_\infty \approx 3.56995.
```

The spacing between successive bifurcations shrinks geometrically:

```{math}
\delta
=
\lim_{n\to\infty}
\frac{r_{n-1}-r_{n-2}}
     {r_n - r_{n-1}}
\approx 4.669,
```

where $\delta$ is the **Feigenbaum constant**.

This constant appears universally in many nonlinear systems
undergoing period-doubling cascades.



### Onset of Chaos

For

```{math}
r > r_\infty,
```

the logistic map becomes chaotic (for most values of $r$).

Characteristics:

- Aperiodic long-term behaviour,
- Sensitive dependence on initial conditions,
- Irregular iterates within a bounded interval.

However, periodic windows still exist,
for example the period-3 window near $r \approx 3.83$.



### Lyapunov Exponent of the Logistic Map

For one-dimensional maps, the Lyapunov exponent is

```{math}
\lambda
=
\lim_{N \to \infty}
\frac{1}{N}
\sum_{n=0}^{N-1}
\ln |f'(x_n)|.
```

For the logistic map:

```{math}
\lambda
=
\lim_{N \to \infty}
\frac{1}{N}
\sum_{n=0}^{N-1}
\ln |r(1 - 2x_n)|.
```

Interpretation:

- $\lambda < 0$ → periodic behaviour,
- $\lambda = 0$ → bifurcation point,
- $\lambda > 0$ → chaos.

At $r = 4$,

```{math}
\lambda = \ln 2,
```

indicating strong exponential sensitivity.



### Bifurcation Diagram

Plotting long-term values of $x_n$ versus $r$
produces the **bifurcation diagram**:

- Single branch → stable fixed point,
- Two branches → period-2,
- Four branches → period-4,
- Dense band → chaotic regime.

The diagram reveals:

- Period-doubling cascade,
- Self-similarity,
- Fractal structure,
- Periodic windows embedded in chaos.



### Invariant Measure (r = 4)

At $r = 4$, the logistic map has invariant density

```{math}
\rho(x)
=
\frac{1}{\pi \sqrt{x(1-x)}}.
```

This distribution is non-uniform and singular at the boundaries,
reflecting the stretching and folding dynamics.



### Period Three Implies Chaos

A fundamental theorem (Li & Yorke, 1975):

If a continuous one-dimensional map has a period-3 orbit,
then it has periodic orbits of every period and exhibits chaotic behaviour.

Thus the presence of period-3 implies chaos.



### Numerical Exploration (Python Example)

Below is a minimal example computing both
the bifurcation diagram and Lyapunov exponent.

```python
import numpy as np
import matplotlib.pyplot as plt

r_min, r_max = 2.5, 4.0
n_r = 4000
n_iter = 1000
n_transient = 500

r = np.linspace(r_min, r_max, n_r)
x = np.ones(n_r) * 0.5
lyap = np.zeros(n_r)

plt.figure(figsize=(10,7))

for i in range(n_iter):
    x = r * x * (1 - x)
    lyap += np.log(np.abs(r * (1 - 2*x)))
    
    if i >= n_transient:
        plt.plot(r, x, ',k', alpha=0.2)

plt.xlabel("r")
plt.ylabel("x")
plt.title("Logistic Map Bifurcation Diagram")
plt.show()

lyap /= n_iter

plt.figure(figsize=(10,4))
plt.plot(r, lyap, 'k')
plt.axhline(0, color='red', linestyle='--')
plt.xlabel("r")
plt.ylabel("Lyapunov Exponent")
plt.title("Lyapunov Exponent vs r")
plt.show()
```

This results in a bifurcation diagram:

```{figure} ./bifurcation_diagram.png
---
name: bifurcation_diagram
---
Bifurcation diagram of the logistic map $x_{n+1} = r x_n (1 - x_n)$, 
showing long-term values of $x_n$ as the parameter $r$ varies from 2.5 to 4.0. 

For $r < 3$, the system converges to a stable fixed point.  
At $r = 3$, a period-doubling bifurcation occurs, followed by a cascade of further doublings accumulating at $r_\infty \approx 3.56995$.  
Beyond this value, chaotic behaviour emerges, visible as dense bands of aperiodic iterates.  
Embedded within the chaotic region are periodic windows (e.g. near $r \approx 3.83$), illustrating the intricate self-similar structure of the route to chaos.
```


## Case Study: The Duffing Oscillator (Continuous-Time Chaos)

The Duffing oscillator is a classical nonlinear system that exhibits
chaos when periodically forced.

It provides a canonical example of **continuous-time chaos** and
illustrates how the diagnostics developed earlier are applied to flows.



### The Duffing Equation

The forced, damped Duffing equation is

```{math}
\ddot{x}
+
\delta \dot{x}
+
\alpha x
+
\beta x^3
=
\gamma \cos(\omega t),
```

where:

- $\delta$ = damping,
- $\alpha, \beta$ = linear and nonlinear stiffness,
- $\gamma$ = forcing amplitude,
- $\omega$ = forcing frequency.

This is a nonlinear second-order ODE.



### Why Chaos Is Possible Here

*Autonomous vs Forced Systems*

The unforced Duffing equation (no $\cos(\omega t)$) is
a 2D autonomous system:

```{math}
\dot{x} = v,
\qquad
\dot{v} = -\delta v - \alpha x - \beta x^3.
```

By the **Poincaré–Bendixson theorem**, 2D autonomous systems
cannot exhibit chaos.

*Time-Dependent Forcing Adds a Dimension*

Introduce

```{math}
\dot{\theta} = \omega.
```

The system becomes

```{math}
\dot{x} = v,
```
```{math}
\dot{v} = -\delta v - \alpha x - \beta x^3 + \gamma \cos \theta,
```
```{math}
\dot{\theta} = \omega.
```

This is a **3D autonomous system**, making chaos possible.

Thus, periodic forcing effectively increases the phase-space dimension.



### Poincaré Section (Stroboscopic Map)

Because the forcing is periodic with period

```{math}
T = \frac{2\pi}{\omega},
```

we construct a **stroboscopic Poincaré section**:

```{math}
(x(nT), \dot{x}(nT)).
```

This reduces the continuous flow to a discrete map.

Classification:

- Single point → periodic motion
- Finite set of points → period-$k$
- Closed curve → quasi-periodic
- Fractal cloud → chaotic attractor

A fractal Poincaré section strongly indicates chaos.



### Largest Lyapunov Exponent

To confirm chaos quantitatively, compute
the largest Lyapunov exponent $\lambda_1$.

For the Duffing system, the Jacobian matrix is

```{math}
J(t)
=
\begin{pmatrix}
0 & 1 \\
-\alpha - 3\beta x^2 & -\delta
\end{pmatrix}.
```

Integrating the variational equation

```{math}
\dot{\delta \mathbf{x}} = J(t)\,\delta \mathbf{x}
```

alongside the original system allows numerical estimation
of $\lambda_1$.

Criterion:

```{math}
\lambda_1 > 0
\quad \Rightarrow \quad
\text{chaos}.
```



### Bifurcation Structure

Varying the forcing amplitude $\gamma$
reveals a rich bifurcation structure:

```{math}
\text{periodic}
\rightarrow
\text{period-doubling}
\rightarrow
\text{chaos}.
```

Features include:

- Period-doubling cascades,
- Periodic windows within chaos,
- Crisis transitions.

Plotting Poincaré points or maxima of $x(t)$
versus $\gamma$ produces a bifurcation diagram.



### Phase-Space Structure

In chaotic regimes, trajectories:

- Remain bounded,
- Never repeat,
- Accumulate on a strange attractor.

The attractor exhibits:

- Stretching and folding geometry,
- Fractal structure,
- Embedded unstable periodic orbits.





### Summary of Continuous-Time Diagnostics

To establish chaos in the Duffing oscillator:

1. Confirm sufficient dimensionality (effective 3D system).
2. Construct a Poincaré section.
3. Compute largest Lyapunov exponent.
4. Examine bifurcation structure.
5. Inspect power spectrum.

If:

- Motion is bounded,
- Aperiodic,
- $\lambda_1 > 0$,
- Poincaré section is fractal,

then the Duffing system is chaotic.



The Duffing oscillator demonstrates that
continuous-time chaos arises from
nonlinearity combined with forcing and dissipation,
producing structured yet unpredictable dynamics.
