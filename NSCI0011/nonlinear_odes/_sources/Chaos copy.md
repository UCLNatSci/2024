# Weeks 6 - 10 - Investigating Chaos

## Hallmarks of Chaotic Behaviour in a Dynamical System

A dynamical system is typically considered **chaotic** if it exhibits the following core features:

### Sensitive Dependence on Initial Conditions

A defining feature of chaos is **sensitive dependence on initial conditions**:  
arbitrarily small differences in initial states grow exponentially with time.

Consider two nearby initial conditions in phase space:

\[
\mathbf{x}_0
\quad \text{and} \quad
\mathbf{x}_0 + \delta \mathbf{x}_0 .
\]

Under the system dynamics, their separation evolves approximately as

\[
\|\delta \mathbf{x}(t)\| 
\approx 
\|\delta \mathbf{x}_0\| e^{\lambda t},
\]

where:

- $\|\delta \mathbf{x}(t)\|$ is the distance between trajectories at time $t$,
- $\lambda$ is the **Lyapunov exponent**,
- $\lambda > 0$ implies exponential divergence.



#### Lyapunov Exponent (Formal Definition)

The largest Lyapunov exponent is defined by

\[
\lambda
=
\lim_{t \to \infty}
\frac{1}{t}
\ln
\left(
\frac{\|\delta \mathbf{x}(t)\|}
     {\|\delta \mathbf{x}_0\|}
\right).
\]

Interpretation:

- $ \lambda > 0 $ → chaos (exponential divergence)  
- $ \lambda < 0 $ → trajectories converge  
- $ \lambda = 0 $ → neutral stability (e.g. quasi-periodic motion)

In an $n$-dimensional system there exists a full **Lyapunov spectrum**

\[
\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_n,
\]

and chaos requires at least one positive exponent.



#### Predictability Horizon (Lyapunov Time)

If errors grow as

\[
\|\delta \mathbf{x}(t)\|
\approx
\|\delta \mathbf{x}_0\| e^{\lambda t},
\]

then the time at which the error becomes $ \mathcal{O}(1) $ is approximately

\[
t_{\text{predict}}
\approx
\frac{1}{\lambda}
\ln
\left(
\frac{1}{\|\delta \mathbf{x}_0\|}
\right).
\]

The characteristic timescale

\[
\tau_L = \frac{1}{\lambda}
\]

is called the **Lyapunov time**.

### Deterministic Dynamics

Chaos occurs in systems governed by **deterministic evolution laws**.  
There is no stochastic forcing, no random noise, and no probabilistic rule in the dynamics itself.

A continuous-time dynamical system is typically written as

\[
\frac{d\mathbf{x}}{dt} = \mathbf{f}(\mathbf{x}),
\]

where:

- $\mathbf{x} \in \mathbb{R}^n$ is the state vector,
- $\mathbf{f} : \mathbb{R}^n \to \mathbb{R}^n$ is a deterministic nonlinear function.

Given an initial condition $\mathbf{x}(0) = \mathbf{x}_0$, the solution $\mathbf{x}(t)$ is uniquely determined (assuming standard existence and uniqueness conditions).



#### Discrete-Time Systems

Similarly, a discrete dynamical system (map) takes the form

\[
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n).
\]

Again, once $\mathbf{x}_0$ is specified, the entire future sequence

\[
\{\mathbf{x}_1, \mathbf{x}_2, \mathbf{x}_3, \dots\}
\]

is completely determined.

Example (logistic map):

\[
x_{n+1} = r x_n (1 - x_n),
\]

which is entirely deterministic — yet chaotic for certain parameter values.


#### Determinism vs Randomness

It is crucial to distinguish:

- **Chaotic dynamics** (deterministic but unpredictable)
- **Stochastic dynamics** (intrinsically random)

In a chaotic system:

- The governing equations contain no random variables.
- Identical initial conditions produce identical trajectories.
- Unpredictability arises from exponential amplification of microscopic uncertainty.

In contrast, stochastic systems include explicit noise terms, e.g.

\[
\frac{d\mathbf{x}}{dt}
=
\mathbf{f}(\mathbf{x})
+
\boldsymbol{\eta}(t),
\]

where $\boldsymbol{\eta}(t)$ is a random process.



#### Role of Nonlinearity

Determinism alone is not sufficient for chaos.

Linear systems of the form

\[
\frac{d\mathbf{x}}{dt} = A\mathbf{x}
\]

cannot exhibit chaos. Their solutions are combinations of exponentials and cannot produce:

- Stretching-and-folding dynamics  
- Strange attractors  
- Sensitive dependence with bounded motion  

Chaos requires **nonlinearity**, which allows trajectories to be stretched, folded, and reinjected into bounded regions of phase space.



#### Key Insight

Chaos is not a failure of determinism.

Rather, it reveals that:

\[
\text{Deterministic laws} \;\not\Rightarrow\; \text{Long-term predictability}.
\]

The equations are exact — but finite precision in initial data leads to unavoidable practical unpredictability.


### Aperiodic Long-Term Behaviour

A chaotic system exhibits **aperiodic long-term motion**: trajectories do not settle to fixed points or periodic orbits, and they never exactly repeat.

Importantly, the motion remains **bounded**, yet non-repeating.



#### Fixed Points and Periodic Orbits

A **fixed point** $\mathbf{x}^*$ satisfies

\[
\mathbf{f}(\mathbf{x}^*) = 0
\quad \text{(continuous time)},
\]

or

\[
\mathbf{F}(\mathbf{x}^*) = \mathbf{x}^*
\quad \text{(discrete time)}.
\]

A **periodic orbit** of period $T$ (continuous time) satisfies

\[
\mathbf{x}(t + T) = \mathbf{x}(t)
\quad \forall t,
\]

while for a discrete map, a period-$k$ orbit satisfies

\[
\mathbf{F}^k(\mathbf{x}) = \mathbf{x}.
\]

In chaotic systems, typical trajectories do **not** converge to stable fixed points or stable periodic orbits.



#### Non-Periodicity

For chaotic motion,

\[
\mathbf{x}(t + T) \neq \mathbf{x}(t)
\quad \text{for all finite } T > 0.
\]

There is no finite recurrence time for which the trajectory exactly repeats.

However, trajectories may return arbitrarily close to previous states (Poincaré recurrence), without ever becoming periodic.



#### Bounded but Non-Repeating Motion

A key feature of dissipative chaotic systems is that trajectories remain confined to a bounded region of phase space:

\[
\|\mathbf{x}(t)\| < C
\quad \text{for all } t \ge 0,
\]

for some constant $C$.

Yet within this bounded region, the trajectory wanders forever in a complex, non-repeating way.

This distinguishes chaos from:

- Unbounded exponential growth  
- Simple periodic motion  
- Quasi-periodic motion on invariant tori  



#### Contrast with Quasi-Periodic Motion

Quasi-periodic motion (e.g. on a torus) has the form

\[
\mathbf{x}(t)
=
\mathbf{g}(\omega_1 t, \omega_2 t, \dots),
\]

where the frequencies $\omega_i$ are incommensurate.

Such motion:

- Never exactly repeats,
- But does **not** exhibit sensitive dependence on initial conditions,
- And has zero largest Lyapunov exponent.

Thus, aperiodicity alone does not imply chaos — it must occur together with exponential instability.



#### Long-Term Behaviour and Attractors

In dissipative chaotic systems, trajectories approach a **chaotic attractor**:

\[
\lim_{t \to \infty} \text{dist}(\mathbf{x}(t), \mathcal{A}) = 0,
\]

where $\mathcal{A}$ is:

- Invariant,
- Bounded,
- Fractal in structure.

The motion on this attractor is:

- Deterministic,
- Bounded,
- Aperiodic,
- Sensitive to initial conditions.



Aperiodic long-term behaviour means that the system never settles into simple repeating dynamics, yet remains confined to a structured region of phase space — a defining qualitative signature of chaos.

### Topological Mixing

A central structural property of chaotic systems is **topological mixing**.

Informally, mixing means that the system eventually spreads any small region of phase space throughout the entire accessible region.



#### Formal Definition (Continuous Time)

Let $\mathcal{A}$ be an invariant set (e.g. an attractor), and let
$\phi^t : \mathcal{A} \to \mathcal{A}$ denote the flow of the system.

The system is **topologically mixing** on $\mathcal{A}$ if for any two nonempty open sets
$U, V \subset \mathcal{A}$, there exists a time $T > 0$ such that

\[
\phi^t(U) \cap V \neq \varnothing
\quad \text{for all } t > T.
\]

That is, after sufficient time, the evolved image of $U$ overlaps with $V$.



#### Discrete-Time Version

For a map $\mathbf{F} : \mathcal{A} \to \mathcal{A}$, mixing means:

For any two nonempty open sets $U, V \subset \mathcal{A}$, there exists an integer $N$ such that

\[
\mathbf{F}^n(U) \cap V \neq \varnothing
\quad \text{for all } n \ge N.
\]



#### Geometric Interpretation: Stretching and Folding

Topological mixing arises from two competing mechanisms:

1. **Stretching**  
   Nearby trajectories separate exponentially along unstable directions
   (positive Lyapunov exponent).

2. **Folding**  
   The system remains bounded, so stretched regions must fold back into
   phase space.

This repeated stretching-and-folding process creates intricate filamentary
structures and fractal geometry.

A classic analogy is kneading dough:

- Stretch  
- Fold  
- Repeat  

Eventually, any small patch becomes intertwined with the whole.



#### Mixing vs Ergodicity

Mixing is stronger than ergodicity.

- **Ergodic:** time averages equal space averages for almost all initial conditions.
- **Mixing:** correlations between sets decay over time.

In measure-theoretic terms, mixing implies that for measurable sets
$U, V$,

\[
\lim_{t \to \infty}
\mu(\phi^t(U) \cap V)
=
\mu(U)\mu(V),
\]

where $\mu$ is an invariant measure.

This expresses statistical independence at long times.



#### Physical Meaning

Topological mixing implies:

- Long-term loss of memory of initial regions,
- Irreversible-looking macroscopic behaviour,
- Statistical structure emerging from deterministic laws.

Although the system is deterministic, the continual mixing of phase space
produces behaviour that resembles random evolution at large scales.



Topological mixing ensures that chaotic dynamics are not merely unstable,
but globally intertwined — every region of phase space eventually
interacts with every other region.


### Dense Periodic Orbits

A defining structural property of chaotic systems is the existence of
**dense periodic orbits**.

This means that although typical trajectories are aperiodic, periodic
orbits are embedded throughout the chaotic set and lie arbitrarily
close to any point on it.



#### Periodic Orbits

For a discrete map $\mathbf{F}$, a point $\mathbf{x}$ is periodic of period $k$ if

\[
\mathbf{F}^k(\mathbf{x}) = \mathbf{x},
\]

where $k \in \mathbb{N}$ is the smallest such integer.

For continuous-time systems with flow $\phi^t$, a periodic orbit
of period $T > 0$ satisfies

\[
\phi^T(\mathbf{x}) = \mathbf{x}.
\]



#### Density

Let $\mathcal{A}$ be a chaotic invariant set (e.g. an attractor).

Periodic orbits are **dense** in $\mathcal{A}$ if:

For every point $\mathbf{x} \in \mathcal{A}$ and every neighborhood
$U$ of $\mathbf{x}$,

\[
U \cap \{\text{periodic points}\} \neq \varnothing.
\]

In other words, periodic points lie arbitrarily close to every point in
the chaotic set.



#### Unstable Nature of Periodic Orbits

In chaotic systems, these periodic orbits are typically **unstable**.

If $\mathbf{x}^*$ is a periodic point, then the Jacobian of the
$k$-fold map,

\[
D\mathbf{F}^k(\mathbf{x}^*),
\]

has at least one eigenvalue with magnitude greater than 1:

\[
|\lambda_i| > 1.
\]

Thus nearby trajectories diverge from the periodic orbit
exponentially.

This instability explains why:

- Periodic motion exists mathematically,
- But is not observed for generic initial conditions.



#### Structural Importance

Although unstable, periodic orbits form the "skeleton" of chaotic dynamics.

Many properties of chaotic systems can be expressed in terms of sums over periodic orbits, for example:

- Topological entropy
- Lyapunov exponents
- Natural invariant measures

This is the foundation of **periodic orbit theory**.



#### Conceptual Significance

Dense periodic orbits imply that chaotic dynamics are not random.

Instead, chaos consists of:

- Infinitely many unstable periodic motions,
- Interwoven densely throughout phase space,
- With trajectories continually shadowing different periodic orbits.

Thus, chaos contains an intricate hidden order:
aperiodic motion built from an infinity of unstable periodic structures.

### Strange Attractors (Dissipative Systems)

In dissipative chaotic systems, long-term trajectories approach a
geometrically complex invariant set known as a **strange attractor**.

A strange attractor is characterized by:

- Invariance under the dynamics,
- Attraction of nearby trajectories,
- Fractal (non-integer) dimension,
- Sensitive dependence on initial conditions.



#### Attractors

Let $\phi^t$ denote the flow of a continuous-time system.

A set $\mathcal{A} \subset \mathbb{R}^n$ is an **attractor** if:

1. **Invariance**
\[
\phi^t(\mathcal{A}) = \mathcal{A}
\quad \text{for all } t \ge 0.
\]

2. **Attraction**
There exists a neighborhood $U$ of $\mathcal{A}$ such that
\[
\lim_{t \to \infty}
\text{dist}(\phi^t(\mathbf{x}), \mathcal{A}) = 0
\quad \text{for all } \mathbf{x} \in U.
\]

3. **Minimality**
$\mathcal{A}$ contains no proper subset with these properties.



#### Dissipation and Volume Contraction

Strange attractors arise in **dissipative systems**, where phase-space
volume contracts.

For a system

\[
\frac{d\mathbf{x}}{dt} = \mathbf{f}(\mathbf{x}),
\]

volume contraction occurs if

\[
\nabla \cdot \mathbf{f} < 0.
\]

The divergence determines the rate of change of an infinitesimal
volume element $V(t)$:

\[
\frac{dV}{dt}
=
(\nabla \cdot \mathbf{f}) V.
\]

If the divergence is negative on average, volumes shrink, forcing
trajectories onto a lower-dimensional set.



#### Fractal Geometry

A strange attractor has **non-integer dimension**.

One commonly used notion is the box-counting dimension:

\[
D_B
=
\lim_{\varepsilon \to 0}
\frac{\log N(\varepsilon)}
     {\log(1/\varepsilon)},
\]

where $N(\varepsilon)$ is the number of boxes of size
$\varepsilon$ required to cover the attractor.

For strange attractors:

\[
\text{integer dimension} > D_B > \text{topological dimension}.
\]

This fractal structure results from repeated stretching and folding.



#### Lyapunov Spectrum and Dimension

In dissipative chaotic systems:

- At least one Lyapunov exponent is positive,
- The sum of exponents is negative (volume contraction).

The **Kaplan–Yorke (Lyapunov) dimension** is often used:

\[
D_{KY}
=
j
+
\frac{\lambda_1 + \cdots + \lambda_j}
     {|\lambda_{j+1}|},
\]

where $j$ is the largest integer such that

\[
\sum_{i=1}^{j} \lambda_i \ge 0.
\]

This provides an estimate of the attractor’s fractal dimension.



#### Example: The Lorenz Attractor

The Lorenz system:

\[
\begin{aligned}
\dot{x} &= \sigma (y - x), \\
\dot{y} &= x(\rho - z) - y, \\
\dot{z} &= xy - \beta z,
\end{aligned}
\]

for suitable parameter values, produces a strange attractor that is:

- Bounded,
- Fractal,
- Chaotic,
- Structurally stable over parameter ranges.



#### Conceptual Significance

Strange attractors represent the long-term state of dissipative chaotic systems.

They combine:

- Deterministic laws,
- Exponential instability,
- Global boundedness,
- Fractal geometric structure.

Thus, chaotic motion is not wandering arbitrarily through phase space,
but is confined to a highly organized yet infinitely intricate set.


## Quantitative Diagnostics of Chaos

### Positive Lyapunov Exponent

The most practical and widely used quantitative signature of chaos is the
existence of a **positive Lyapunov exponent**.

While earlier sections introduced the concept qualitatively, here we
formalize its role as a diagnostic criterion.



#### Linearised Dynamics

Consider a continuous-time dynamical system

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\]

and let $\mathbf{x}(t)$ be a trajectory.

The evolution of an infinitesimal perturbation
$\delta \mathbf{x}(t)$ is governed by the linearised system:

\[
\frac{d}{dt}\delta \mathbf{x}
=
D\mathbf{f}(\mathbf{x}(t))
\, \delta \mathbf{x},
\]

where $D\mathbf{f}$ is the Jacobian matrix evaluated along the trajectory.

This equation describes the dynamics in the tangent space.



#### Definition of Lyapunov Exponents

The Lyapunov exponent associated with a perturbation direction is

\[
\lambda
=
\lim_{t \to \infty}
\frac{1}{t}
\ln
\frac{\|\delta \mathbf{x}(t)\|}
     {\|\delta \mathbf{x}(0)\|}.
\]

More generally, an $n$-dimensional system has a full
**Lyapunov spectrum**

\[
\lambda_1 \ge \lambda_2 \ge \cdots \ge \lambda_n.
\]



#### Criterion for Chaos

A system is chaotic if

\[
\lambda_1 > 0,
\]

i.e. the largest Lyapunov exponent is positive.

This guarantees exponential divergence of nearby trajectories:

\[
\|\delta \mathbf{x}(t)\|
\sim
e^{\lambda_1 t}.
\]



#### Discrete-Time Systems

For a discrete map

\[
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n),
\]

perturbations evolve according to

\[
\delta \mathbf{x}_{n+1}
=
D\mathbf{F}(\mathbf{x}_n)
\, \delta \mathbf{x}_n.
\]

The Lyapunov exponent is then

\[
\lambda
=
\lim_{n \to \infty}
\frac{1}{n}
\ln
\frac{\|\delta \mathbf{x}_n\|}
     {\|\delta \mathbf{x}_0\|}.
\]



#### Physical Interpretation

A positive Lyapunov exponent implies:

- Exponential loss of information about initial conditions,
- Finite predictability time,
- Practical irreversibility despite deterministic laws.

If measurement precision is $\epsilon$, then the predictability horizon is

\[
t_{\text{predict}}
\approx
\frac{1}{\lambda_1}
\ln\!\left(\frac{1}{\epsilon}\right).
\]



#### Relation to Volume Evolution

The sum of Lyapunov exponents determines volume behaviour:

\[
\sum_{i=1}^n \lambda_i
=
\lim_{t \to \infty}
\frac{1}{t}
\ln \left(\frac{V(t)}{V(0)}\right).
\]

- Positive sum → volume expansion (Hamiltonian-type systems)
- Negative sum → volume contraction (dissipative systems)

In dissipative chaos:

\[
\lambda_1 > 0
\quad \text{but} \quad
\sum_{i=1}^n \lambda_i < 0.
\]

This combination produces strange attractors.



The largest Lyapunov exponent provides a concrete, computable,
and experimentally measurable test for chaos, making it the most
operational definition used in practice.


### Fractal (Non-Integer) Dimension

A key geometric signature of chaotic attractors is that they possess
**non-integer (fractal) dimension**.

Unlike smooth manifolds (lines, surfaces, volumes), strange attractors
occupy a set whose effective dimension lies between integers.



#### Why Fractal Structure Appears

Chaotic dynamics involve repeated:

- Stretching (due to positive Lyapunov exponents),
- Folding (to remain bounded),
- Dissipation (phase-space volume contraction).

This infinite repetition produces structures with detail at all scales.

The result is a geometrically intricate set that is:

- Bounded,
- Self-similar (often statistically),
- Non-smooth,
- Non-integer dimensional.



#### Box-Counting Dimension

One practical definition is the **box-counting dimension**.

Cover the attractor with boxes of side length $\varepsilon$.  
Let $N(\varepsilon)$ be the number of boxes required.

The box-counting dimension is defined as

\[
D_B
=
\lim_{\varepsilon \to 0}
\frac{\log N(\varepsilon)}
     {\log (1/\varepsilon)}.
\]

For smooth objects:

- Line → $D = 1$  
- Surface → $D = 2$  
- Volume → $D = 3$

For strange attractors:

\[
1 < D_B < 2
\quad \text{(typically, in 3D systems)}
\]

or more generally,

\[
\text{topological dimension} < D_B < \text{embedding dimension}.
\]



#### Correlation Dimension

In experimental data, the **correlation dimension** is often used.

Define the correlation sum

\[
C(\varepsilon)
=
\frac{1}{N^2}
\sum_{i,j}
\Theta
\big(
\varepsilon - \|\mathbf{x}_i - \mathbf{x}_j\|
\big),
\]

where:

- $\Theta$ is the Heaviside step function,
- $\{\mathbf{x}_i\}$ are sampled trajectory points.

The correlation dimension is

\[
D_2
=
\lim_{\varepsilon \to 0}
\frac{\log C(\varepsilon)}
     {\log \varepsilon}.
\]

For chaotic attractors, $D_2$ is typically non-integer.



#### Kaplan–Yorke (Lyapunov) Dimension

The fractal dimension can also be estimated from the Lyapunov spectrum.

Let

\[
\lambda_1 \ge \lambda_2 \ge \cdots \ge \lambda_n
\]

be the ordered Lyapunov exponents.

Define $j$ as the largest integer such that

\[
\sum_{i=1}^{j} \lambda_i \ge 0.
\]

The **Kaplan–Yorke dimension** is

\[
D_{KY}
=
j
+
\frac{\sum_{i=1}^{j} \lambda_i}
     {|\lambda_{j+1}|}.
\]

This links geometric complexity directly to dynamical instability.



#### Physical Interpretation

Fractal dimension reflects:

- Partial contraction of phase-space volume,
- Competition between expansion and dissipation,
- Infinite geometric refinement.

It quantifies how densely trajectories fill phase space.

In dissipative chaotic systems:

\[
\lambda_1 > 0,
\quad
\sum_i \lambda_i < 0,
\quad
D_{KY} \notin \mathbb{Z}.
\]

Thus, strange attractors are geometrically intermediate between smooth
manifolds of different integer dimensions.



Non-integer dimension is therefore a geometric fingerprint of chaotic
attractors — revealing that the long-term state of the system is neither
a simple curve nor a surface, but a fractal object.



### Broadband Power Spectrum

Another practical diagnostic of chaos is the presence of a
**broadband power spectrum**.

While periodic systems exhibit discrete spectral lines,
chaotic systems typically display a continuous frequency distribution.



#### Time Series and Fourier Transform

Consider an observable $x(t)$ generated by a dynamical system.

Its Fourier transform is defined as

\[
\hat{x}(\omega)
=
\int_{-\infty}^{\infty}
x(t) e^{-i \omega t} \, dt.
\]

The **power spectral density (PSD)** is

\[
S(\omega)
=
\lim_{T \to \infty}
\frac{1}{2T}
\left|
\int_{-T}^{T}
x(t) e^{-i \omega t} \, dt
\right|^2.
\]

The PSD measures how signal energy is distributed across frequencies.



#### Spectral Signatures of Different Dynamics

1. **Periodic Motion**

If

\[
x(t) = A \cos(\omega_0 t),
\]

then

\[
S(\omega)
\propto
\delta(\omega - \omega_0)
+
\delta(\omega + \omega_0),
\]

i.e. sharp spectral lines.



2. **Quasi-Periodic Motion**

For motion with incommensurate frequencies,

\[
x(t) = \sum_k A_k \cos(\omega_k t),
\]

the spectrum consists of a countable set of discrete peaks.



3. **Chaotic Motion**

For chaotic dynamics, the spectrum becomes continuous:

\[
S(\omega)
\text{ is broadband and smooth.}
\]

There are no isolated delta-function peaks dominating the signal.

This reflects the aperiodic, non-repeating nature of the motion.



#### Relation to Correlation Decay

The power spectrum is related to the autocorrelation function

\[
R(\tau)
=
\lim_{T \to \infty}
\frac{1}{2T}
\int_{-T}^{T}
x(t)x(t+\tau)\, dt.
\]

By the Wiener–Khinchin theorem,

\[
S(\omega)
=
\int_{-\infty}^{\infty}
R(\tau) e^{-i \omega \tau} \, d\tau.
\]

In chaotic systems, correlations typically decay:

\[
R(\tau) \to 0
\quad \text{as} \quad \tau \to \infty.
\]

Decay of correlations produces a continuous spectrum.



#### Important Distinction

A broadband spectrum alone does not prove chaos.

Stochastic noise can also produce continuous spectra.

Therefore, spectral analysis should be combined with:

- Lyapunov exponent calculations,
- Phase-space reconstruction,
- Fractal dimension estimation.



#### Physical Interpretation

A broadband spectrum indicates:

- No dominant repeating frequency,
- Loss of long-term phase coherence,
- Mixing of timescales due to nonlinear interactions.

It provides an experimentally accessible indicator of chaotic dynamics,
especially in physical and laboratory systems.


## What Chaos Is Not

To properly understand chaos, it is equally important to clarify
what chaos does *not* mean.

Chaos is frequently confused with randomness, noise, or mere complexity.
These are fundamentally different concepts.



### Not Randomness

A chaotic system is governed by deterministic equations:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x})
\quad \text{or} \quad
\mathbf{x}_{n+1} = \mathbf{F}(\mathbf{x}_n).
\]

Given an exact initial condition $\mathbf{x}_0$,
the future trajectory is uniquely determined.

In contrast, a stochastic system includes explicit randomness:

\[
\dot{\mathbf{x}}
=
\mathbf{f}(\mathbf{x})
+
\boldsymbol{\eta}(t),
\]

where $\boldsymbol{\eta}(t)$ is a random process.

Key distinction:

- **Chaos:** unpredictability from exponential sensitivity.
- **Randomness:** unpredictability from intrinsic probabilistic forcing.



### Not Noise

Experimental signals from chaotic systems often resemble noise.
However, chaotic time series:

- Possess finite-dimensional attractors,
- Have deterministic structure,
- Exhibit positive Lyapunov exponents.

Noise-driven systems generally:

- Lack a finite-dimensional deterministic structure,
- Do not admit a Lyapunov spectrum in the same sense,
- Often produce stochastic diffusion rather than bounded strange attractors.

Phase-space reconstruction can distinguish the two.



### Not Mere Nonlinearity

Nonlinearity is necessary for chaos, but not sufficient.

For example:

\[
\dot{x} = -x + x^3
\]

is nonlinear but not chaotic.

Similarly, many nonlinear systems exhibit:

- Stable fixed points,
- Stable periodic orbits,
- Quasi-periodic tori.

Thus:

\[
\text{Nonlinearity} \;\not\Rightarrow\; \text{Chaos}.
\]

Additional ingredients such as stretching, folding, and recurrence are required.



### Not Simple Complexity

A system may appear complicated but still be regular.

Examples:

- Quasi-periodic motion on a torus,
- High-frequency but periodic oscillations,
- Large systems of coupled linear oscillators.

Visual complexity alone does not imply:

- Positive Lyapunov exponents,
- Topological mixing,
- Fractal attractors.

Chaos is defined by precise dynamical properties, not aesthetic irregularity.



### Not Unbounded Instability

Exponential growth alone is not chaos.

For example:

\[
\dot{x} = x
\quad \Rightarrow \quad
x(t) = x_0 e^{t}.
\]

This system has exponential divergence but:

- No bounded attractor,
- No stretching-and-folding mechanism,
- No complex invariant set.

Chaos requires bounded motion combined with instability.

Chaos is therefore:

- Deterministic but unpredictable,
- Structured but aperiodic,
- Bounded but unstable,
- Geometrically fractal but dynamically lawful.

Understanding what chaos is *not* prevents conflating it with noise,
disorder, or mere complication.


## Finding Chaos in the Logistic Map

The logistic map is one of the simplest dynamical systems that exhibits
chaos. Despite its algebraic simplicity, it displays the full sequence
from stability to periodic motion to chaos.

---

### Definition of the Logistic Map

The logistic map is a one-dimensional discrete dynamical system:

\[
x_{n+1} = f(x_n) = r x_n (1 - x_n),
\]

where:

- $x_n \in [0,1]$,
- $r \in [0,4]$ is a control parameter.

For a given initial condition $x_0$, the sequence
$\{x_1, x_2, x_3, \dots\}$ is completely deterministic.

---

## Step 1: Fixed Points and Stability

Fixed points satisfy

\[
x^* = r x^* (1 - x^*).
\]

Solving gives:

\[
x^*_1 = 0,
\qquad
x^*_2 = 1 - \frac{1}{r}.
\]

To determine stability, compute

\[
f'(x) = r(1 - 2x).
\]

A fixed point is stable if

\[
|f'(x^*)| < 1.
\]

Results:

- For $0 < r < 1$: $x^* = 0$ is stable.
- For $1 < r < 3$: $x^* = 1 - \frac{1}{r}$ is stable.
- At $r = 3$: stability is lost.

This marks the first bifurcation.

---

## Step 2: Period-Doubling Cascade

At $r = 3$, a **period-doubling bifurcation** occurs:

- The fixed point becomes unstable.
- A stable period-2 orbit emerges.

As $r$ increases further:

- Period-2 becomes unstable.
- Period-4 orbit appears.
- Then period-8.
- Then period-16.
- And so on.

This sequence accumulates at

\[
r_\infty \approx 3.56995.
\]

The spacing between bifurcation values shrinks geometrically:

\[
\delta
=
\lim_{n \to \infty}
\frac{r_{n-1} - r_{n-2}}
     {r_n - r_{n-1}}
\approx 4.669,
\]

where $\delta$ is the **Feigenbaum constant**.

This universal constant appears in many nonlinear systems.

---

## Step 3: Onset of Chaos

For

\[
r > r_\infty,
\]

the system becomes chaotic.

Characteristics:

- No stable periodic orbit (for most $r$),
- Aperiodic long-term behaviour,
- Sensitive dependence on initial conditions.

However, small periodic windows still exist
(e.g. the period-3 window near $r \approx 3.83$).

---

## Step 4: Lyapunov Exponent

For one-dimensional maps, the Lyapunov exponent is

\[
\lambda
=
\lim_{N \to \infty}
\frac{1}{N}
\sum_{n=0}^{N-1}
\ln |f'(x_n)|.
\]

For the logistic map:

\[
\lambda
=
\lim_{N \to \infty}
\frac{1}{N}
\sum_{n=0}^{N-1}
\ln |r(1 - 2x_n)|.
\]

- If $\lambda < 0$: periodic behaviour.
- If $\lambda > 0$: chaos.

At $r = 4$,

\[
\lambda = \ln 2,
\]

indicating strong exponential sensitivity.

---

## Step 5: Bifurcation Diagram

Plotting long-term values of $x_n$ versus $r$ produces the
**bifurcation diagram**:

- Single branch (stable fixed point),
- Split into two,
- Then four,
- Then a dense chaotic band.

The diagram visually demonstrates:

- Period-doubling cascade,
- Self-similarity,
- Fractal structure,
- Windows of periodicity within chaos.

---

## Step 6: Fractal Attractor

In the chaotic regime, iterates of the logistic map
accumulate on a fractal subset of $[0,1]$.

The invariant density for $r = 4$ is

\[
\rho(x)
=
\frac{1}{\pi \sqrt{x(1-x)}},
\]

which is singular at the boundaries.

This non-uniform invariant measure reflects mixing
and stretching dynamics.

---

## Period Three Implies Chaos

A fundamental result (Li & Yorke, 1975):

If a continuous one-dimensional map has a period-3 orbit,
then it has periodic orbits of every period and exhibits chaotic behaviour.

Thus, the existence of period-3 in the logistic map
guarantees chaos.

---

## Why the Logistic Map Is Important

The logistic map demonstrates that:

- Chaos does not require high dimension,
- Chaos does not require complicated equations,
- Nonlinearity plus feedback is sufficient.

It provides a complete route to chaos via:

\[
\text{Fixed point}
\rightarrow
\text{Period doubling}
\rightarrow
\text{Chaos}.
\]

---

The logistic map stands as one of the clearest and most studied
examples of deterministic chaos, encapsulating the essential
mechanisms of nonlinear instability, universality, and fractal
structure in a single quadratic equation.

\]`{admonition} ODE code using odeint
:class: dropdown

\]python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
r_min, r_max = 2.5, 4.0
n_r = 5000
n_iter = 1000
n_transient = 500

# r values
r = np.linspace(r_min, r_max, n_r)

# Initial condition
x = np.ones(n_r) * 0.5

# Storage for Lyapunov exponents
lyapunov = np.zeros(n_r)

# Prepare figure
plt.figure(figsize=(10, 7))

for i in range(n_iter):
    x = r * x * (1 - x)
    
    # Accumulate Lyapunov exponent
    lyapunov += np.log(np.abs(r * (1 - 2*x)))
    
    # Plot after transients die out
    if i >= n_transient:
        plt.plot(r, x, ',k', alpha=0.25)

plt.title("Logistic Map Bifurcation Diagram")
plt.xlabel("r")
plt.ylabel("x")
plt.show()

# Compute average Lyapunov exponent
lyapunov /= n_iter

# Plot Lyapunov exponent
plt.figure(figsize=(10, 4))
plt.plot(r, lyapunov, 'k')
plt.axhline(0, color='red', linestyle='--')
plt.title("Lyapunov Exponent of Logistic Map")
plt.xlabel("r")
plt.ylabel("λ")
plt.show()
\]
\]`

## Finding Chaos in Continuous-Time Dynamical Systems

Unlike discrete maps (e.g. the logistic map), continuous-time systems
are governed by ordinary differential equations:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}, t).
\]

Detecting chaos in such systems requires a combination of dynamical,
geometric, and numerical diagnostics.

---

# 1. Dimensional Requirement

Before attempting to detect chaos in a continuous-time system,
one must verify that chaos is *structurally possible*.

Not all dynamical systems can exhibit chaos.

---

## 1.1 Autonomous Systems

Consider an autonomous system

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\qquad \mathbf{x} \in \mathbb{R}^n.
\]

The dimension \(n\) of phase space plays a fundamental role.

### Key Theorem: Poincaré–Bendixson

For a smooth **two-dimensional autonomous system**, long-term bounded trajectories can only approach:

- A fixed point,
- A periodic orbit,
- A set of fixed points connected by trajectories.

They cannot form strange attractors.

Therefore:

\[
\textbf{2D autonomous systems cannot exhibit chaos.}
\]

---

## 1.2 Why 2D Is Too Simple

Chaos requires:

- Exponential stretching,
- Folding to maintain boundedness,
- Recurrence.

In two dimensions:

- Stretching in one direction must be compensated by contraction in another.
- There is insufficient geometric freedom to fold trajectories into fractal structures.
- Limit sets must be simple (fixed points or periodic orbits).

The topology of the plane restricts complexity.

---

## 1.3 Minimum Dimension for Continuous Chaos

Continuous-time chaos requires:

\[
n \ge 3.
\]

Examples:

- Lorenz system (3D) → chaotic.
- Rössler system (3D) → chaotic.
- Unforced Duffing (2D autonomous) → not chaotic.

---

## 1.4 Time-Dependent Forcing

A periodically forced 2D system behaves differently.

Example: forced Duffing

\[
\ddot{x} + \delta \dot{x} + \alpha x + \beta x^3 = \gamma \cos(\omega t).
\]

Although the physical state is \((x, \dot{x})\),
the system is explicitly time-dependent.

Introduce a new variable:

\[
\dot{\theta} = \omega.
\]

Now the system becomes:

\[
\dot{x} = v,
\]
\[
\dot{v} = -\delta v - \alpha x - \beta x^3 + \gamma \cos \theta,
\]
\[
\dot{\theta} = \omega.
\]

This is a **3D autonomous system**.

Thus, chaos becomes possible.

---

## 1.5 Geometric Intuition

Chaos requires a mechanism analogous to kneading dough:

1. Stretch phase space locally.
2. Fold it globally.
3. Repeat indefinitely.

In 2D autonomous systems:

- Folding without intersections of trajectories is severely restricted.
- Stable and unstable manifolds cannot form the complex transverse intersections required for homoclinic tangles.

In 3D:

- Manifolds can intersect transversely.
- Homoclinic and heteroclinic tangles can form.
- Strange attractors become possible.

---

## 1.6 Hamiltonian vs Dissipative Systems

Even in 3D, additional structure matters.

- Hamiltonian systems conserve phase-space volume.
- Dissipative systems contract volume.

Continuous-time dissipative chaos typically requires:

\[
\sum_{i=1}^n \lambda_i < 0,
\quad \text{and} \quad
\lambda_1 > 0.
\]

This combination produces strange attractors.

---

## 1.7 Practical Rule

Before searching for chaos:

1. Determine whether the system is autonomous.
2. Determine its phase-space dimension.
3. If autonomous and \(n \le 2\), chaos is impossible.
4. If \(n \ge 3\) (or time-forced), chaos is possible — proceed to diagnostics.

---

## 1.8 Summary

Continuous-time chaos requires sufficient dimensionality to support:

- Exponential instability,
- Recurrence,
- Topological complexity.

Without at least three effective dimensions,
the geometry of phase space forbids chaotic attractors.

---

# 2. Largest Lyapunov Exponent

The most definitive diagnostic of chaos in continuous-time systems
is the **largest Lyapunov exponent**.

It quantifies the average exponential rate at which nearby trajectories diverge.

---

## 2.1 Linearisation Along a Trajectory

Consider an autonomous system:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\qquad \mathbf{x} \in \mathbb{R}^n.
\]

Let \(\mathbf{x}(t)\) be a solution trajectory.

Introduce a small perturbation:

\[
\mathbf{x}(t) + \delta \mathbf{x}(t).
\]

Linearising gives the **variational equation**:

\[
\dot{\delta \mathbf{x}}
=
D\mathbf{f}(\mathbf{x}(t)) \, \delta \mathbf{x},
\]

where \(D\mathbf{f}\) is the Jacobian matrix evaluated along the trajectory.

This describes the evolution of perturbations in tangent space.

---

## 2.2 Definition of the Largest Lyapunov Exponent

The largest Lyapunov exponent is:

\[
\lambda_1
=
\lim_{t \to \infty}
\frac{1}{t}
\ln
\frac{\|\delta \mathbf{x}(t)\|}
     {\|\delta \mathbf{x}(0)\|}.
\]

If nearby trajectories diverge exponentially,

\[
\|\delta \mathbf{x}(t)\|
\sim
e^{\lambda_1 t}.
\]

---

## 2.3 Interpretation of the Sign

- \( \lambda_1 < 0 \) → perturbations decay → stable fixed point
- \( \lambda_1 = 0 \) → neutral direction (e.g. periodic orbit)
- \( \lambda_1 > 0 \) → exponential divergence → chaos

In continuous-time systems:

- One exponent is always zero (flow direction).
- Chaos requires at least one positive exponent.

---

## 2.4 Full Lyapunov Spectrum

An \(n\)-dimensional system has \(n\) Lyapunov exponents:

\[
\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_n.
\]

Their sum determines phase-space volume evolution:

\[
\sum_{i=1}^n \lambda_i
=
\lim_{t\to\infty}
\frac{1}{t}
\ln \frac{V(t)}{V(0)}.
\]

- Positive sum → volume expansion
- Negative sum → dissipation

In dissipative chaotic systems:

\[
\lambda_1 > 0,
\quad
\sum_{i=1}^n \lambda_i < 0.
\]

This produces strange attractors.

---

## 2.5 Numerical Computation (Benettin Method)

In practice, the limit is approximated by:

1. Integrating the original system.
2. Simultaneously integrating the variational equation.
3. Periodically renormalising the perturbation vector.
4. Averaging logarithmic growth.

If renormalisations occur at times \(t_k\), then:

\[
\lambda_1
\approx
\frac{1}{T}
\sum_{k}
\ln \frac{\|\delta \mathbf{x}(t_k)\|}
           {\|\delta \mathbf{x}(t_{k-1})\|},
\]

where \(T\) is total elapsed time.

Renormalisation prevents overflow and keeps perturbations infinitesimal.

---

## 2.6 Geometric Meaning

The largest Lyapunov exponent measures:

- Local stretching rate,
- Information loss rate,
- Predictability horizon.

Predictability time:

\[
t_{\text{predict}}
\approx
\frac{1}{\lambda_1}
\ln\!\left(\frac{1}{\epsilon}\right),
\]

where \(\epsilon\) is measurement precision.

---

## 2.7 Example: Forced Duffing

For the forced Duffing oscillator:

\[
\ddot{x} + \delta \dot{x} + \alpha x + \beta x^3 = \gamma \cos(\omega t),
\]

the Jacobian is:

\[
J(t)
=
\begin{pmatrix}
0 & 1 \\
-\alpha - 3\beta x^2 & -\delta
\end{pmatrix}.
\]

Integrating the tangent dynamics reveals whether
\(\lambda_1 > 0\).

If so, the Duffing system is chaotic.

---

## 2.8 Why This Is the Definitive Test

Other diagnostics (Poincaré sections, spectra, fractal dimension)
can strongly suggest chaos.

But:

\[
\boxed{\lambda_1 > 0}
\]

is the clearest quantitative criterion.

It directly measures exponential instability —
the core dynamical signature of chaos.


# 3. Poincaré Section

A **Poincaré section** is one of the most powerful tools for detecting
and visualising chaos in continuous-time systems, especially when the
system is periodically forced (e.g. the Duffing oscillator).

It reduces a continuous flow to a discrete map, making chaotic structure
much easier to classify.

---

## 3.1 Motivation: From Continuous Flow to a Discrete Map

For a continuous-time system

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}, t),
\]

trajectories are curves in phase space, which can be difficult to interpret.

A Poincaré section samples the trajectory at specific times or crossings
to produce a sequence of points:

\[
\mathbf{x}_0, \mathbf{x}_1, \mathbf{x}_2, \dots
\]

This converts the flow into an **iterated map**, allowing classification
using the geometry of discrete-time dynamics.

---

## 3.2 Periodically Forced Systems (Stroboscopic Section)

If the system is forced with period

\[
T = \frac{2\pi}{\omega},
\]

a natural choice is a **stroboscopic Poincaré section**, defined by sampling
once every forcing period:

\[
\mathbf{x}_n = \mathbf{x}(nT).
\]

For the forced Duffing oscillator, one records

\[
(x(nT), \dot{x}(nT)).
\]

This produces a discrete map

\[
\mathbf{x}_{n+1} = \mathcal{P}(\mathbf{x}_n),
\]

called the **Poincaré map**, where \(\mathcal{P}\) advances the solution by one period.

---

## 3.3 Autonomous Systems (Surface of Section)

For an autonomous \(n\)-dimensional system

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\]

a Poincaré section is defined by choosing a hypersurface

\[
\Sigma = \{\mathbf{x} \in \mathbb{R}^n : g(\mathbf{x}) = 0\},
\]

such that trajectories intersect \(\Sigma\) transversely:

\[
\nabla g(\mathbf{x}) \cdot \mathbf{f}(\mathbf{x}) \neq 0
\quad \text{on intersections}.
\]

Each time the trajectory crosses \(\Sigma\), record the intersection point.
This again defines a Poincaré map:

\[
\mathbf{x}_{k+1} = \mathcal{P}(\mathbf{x}_k).
\]

Dimensional reduction:
- Original flow in \(n\) dimensions
- Poincaré map acts on \((n-1)\)-dimensional section

This reduction is a key reason Poincaré sections reveal structure so clearly.

---

## 3.4 How to Classify the Motion from the Section

The geometry of points on the section determines the regime:

### (a) Periodic Motion

A periodic orbit in continuous time intersects the section at a finite number of points.

- Period-1 orbit → one point
- Period-\(k\) orbit → \(k\) distinct points

\[
\{\mathbf{x}_1, \dots, \mathbf{x}_k\}.
\]

### (b) Quasi-Periodic Motion

Quasi-periodic motion lies on an invariant torus.
Its intersection with the section forms a smooth closed curve:

\[
\text{closed invariant loop on } \Sigma.
\]

### (c) Chaotic Motion

Chaotic trajectories produce an aperiodic sequence of intersections.
The points fill a complicated set with fine structure.

Typical signature:

- A scattered, filamentary, fractal-looking “cloud”
- Self-similar structure under magnification

This is the cross-section of a strange attractor.

---

## 3.5 Why Chaos Looks Fractal in a Poincaré Section

For dissipative chaos:

- Phase-space volume contracts,
- Trajectories collapse onto an attractor,
- Stretching and folding create fractal geometry.

The attractor \(\mathcal{A}\) has non-integer dimension.
Its intersection with \(\Sigma\) inherits this complexity.

Thus, a Poincaré section can reveal fractality even when the full
phase-space attractor is difficult to view.

---

## 3.6 Practical Procedure (Forced Duffing Example)

1. Simulate long enough to remove transients.
2. Compute the forcing period \(T = 2\pi/\omega\).
3. Sample \((x(t), \dot{x}(t))\) at \(t = nT\).
4. Plot the points in the \((x,\dot{x})\) plane.

Then classify:

- Point(s) → periodic
- Closed loop → quasi-periodic
- Fractal cloud → chaotic

---

## 3.7 Limitations and Best Practice

- A finite simulation may hide very long transients.
- Periodic windows exist inside chaotic regimes.
- Noise can blur the fractal structure.

Therefore, Poincaré sections should be combined with:

- Largest Lyapunov exponent (\(\lambda_1 > 0\)),
- Power spectrum,
- Bifurcation scans.

---

## 3.8 Summary

A Poincaré section converts a continuous-time system into a discrete map
whose geometry provides a direct visual classification:

\[
\text{periodic} \rightarrow \text{finite points},\quad
\text{quasi-periodic} \rightarrow \text{closed curve},\quad
\text{chaotic} \rightarrow \text{fractal set}.
\]

For forced oscillators such as Duffing,
the stroboscopic Poincaré section is one of the clearest ways to detect chaos.

# 4. Phase-Space Structure and Strange Attractors

Beyond numerical indicators such as Lyapunov exponents,
chaos in continuous-time systems can often be recognised directly
from the **geometry of phase space**.

Examining long-term trajectories reveals whether the system
settles into simple motion or onto a strange attractor.

---

## 4.1 Phase Space Representation

For a system

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\]

the **phase space** is the space of all possible states \(\mathbf{x}\).

A trajectory is a curve:

\[
\mathbf{x}(t)
\subset \mathbb{R}^n.
\]

Long-term behaviour corresponds to the limit set:

\[
\omega(\mathbf{x}_0)
=
\left\{
\mathbf{y} :
\mathbf{x}(t_k) \to \mathbf{y}
\text{ for some } t_k \to \infty
\right\}.
\]

Understanding this limit set is central to classifying chaos.

---

## 4.2 Regular Motion in Phase Space

### (a) Fixed Points

Trajectories converge to:

\[
\mathbf{x}(t) \to \mathbf{x}^*.
\]

The phase portrait shows all trajectories spiralling
or flowing toward a single point.

---

### (b) Periodic Orbits

Trajectories approach a closed curve:

\[
\mathbf{x}(t+T) = \mathbf{x}(t).
\]

In phase space, this appears as a stable limit cycle.

---

### (c) Quasi-Periodic Motion

Trajectories lie on invariant tori.
In 3D phase space, this forms a smooth toroidal surface.

The motion never repeats but remains geometrically smooth.

---

## 4.3 Chaotic Motion

In chaotic regimes:

- Motion remains bounded,
- Trajectories never close,
- The limit set is neither a point nor a smooth surface.

Instead, trajectories accumulate on a **strange attractor**.

Characteristics:

- Fractal geometry,
- Sensitive dependence on initial conditions,
- Non-integer dimension,
- Dense unstable periodic orbits embedded within.

---

## 4.4 Stretching and Folding Mechanism

The geometric origin of strange attractors is:

1. **Local stretching**  
   Exponential separation of nearby trajectories.

2. **Global folding**  
   Dissipation keeps motion bounded.

This repeated process creates:

- Filamentary structure,
- Self-similarity,
- Fractal geometry.

A useful analogy is repeatedly stretching and folding dough.

---

## 4.5 Dissipation and Volume Contraction

For a continuous system:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}),
\]

the divergence

\[
\nabla \cdot \mathbf{f}
\]

determines phase-space volume evolution.

If

\[
\nabla \cdot \mathbf{f} < 0,
\]

then volumes contract:

\[
\frac{dV}{dt}
=
(\nabla \cdot \mathbf{f}) V.
\]

Volume contraction combined with instability
forces trajectories onto lower-dimensional attractors.

---

## 4.6 Example: Lorenz Attractor

The Lorenz system:

\[
\begin{aligned}
\dot{x} &= \sigma (y - x), \\
\dot{y} &= x(\rho - z) - y, \\
\dot{z} &= xy - \beta z,
\end{aligned}
\]

produces a bounded, butterfly-shaped attractor.

Properties:

- \(\lambda_1 > 0\),
- Fractal dimension \( \approx 2.06 \),
- Dissipative (volume contracting).

The attractor is neither surface nor volume,
but a fractal subset of \(\mathbb{R}^3\).

---

## 4.7 Practical Identification

To classify chaos via phase space:

1. Simulate long enough to remove transients.
2. Plot trajectories in full phase space.
3. Check for:
   - Boundedness,
   - Non-closure,
   - Apparent fractal structure,
   - No smooth invariant surface.

If trajectories densely fill a complex,
structured region without forming smooth manifolds,
the system is likely chaotic.

---

## 4.8 Summary

Phase-space analysis distinguishes regimes:

- Fixed point → single point attractor.
- Periodic → closed curve.
- Quasi-periodic → smooth torus.
- Chaotic → strange attractor with fractal geometry.

Continuous-time chaos is therefore visible not only
through numerical diagnostics,
but directly in the geometric structure of phase space.

# 5. Power Spectrum and Frequency Analysis

Another practical way to detect chaos in continuous-time systems
is through **frequency-domain analysis** of a time series.

While Lyapunov exponents measure instability directly,
the power spectrum reveals the temporal structure of the motion.

---

## 5.1 From Time Series to Frequency Spectrum

Suppose we observe a scalar variable \(x(t)\)
from a dynamical system:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}).
\]

The Fourier transform of \(x(t)\) is

\[
\hat{x}(\omega)
=
\int_{-\infty}^{\infty}
x(t) e^{-i \omega t} \, dt.
\]

The **power spectral density (PSD)** is

\[
S(\omega)
=
\lim_{T \to \infty}
\frac{1}{2T}
\left|
\int_{-T}^{T}
x(t) e^{-i \omega t} \, dt
\right|^2.
\]

It describes how energy is distributed across frequencies.

---

## 5.2 Spectral Signatures of Different Dynamical Regimes

### (a) Periodic Motion

If

\[
x(t) = A \cos(\omega_0 t),
\]

then

\[
S(\omega)
\propto
\delta(\omega - \omega_0)
+
\delta(\omega + \omega_0).
\]

The spectrum consists of sharp discrete peaks.

---

### (b) Quasi-Periodic Motion

If motion contains incommensurate frequencies,

\[
x(t)
=
\sum_k A_k \cos(\omega_k t),
\]

the spectrum contains multiple discrete peaks,
but still remains countable and sharp.

---

### (c) Chaotic Motion

For chaotic systems:

- Motion is aperiodic,
- Correlations decay,
- No finite set of frequencies dominates.

The spectrum becomes **broadband and continuous**:

\[
S(\omega)
\text{ is smooth over a range of frequencies.}
\]

This reflects the mixing of many timescales.

---

## 5.3 Relation to Autocorrelation

Define the autocorrelation function:

\[
R(\tau)
=
\lim_{T\to\infty}
\frac{1}{T}
\int_0^T x(t)x(t+\tau)\,dt.
\]

The Wiener–Khinchin theorem gives:

\[
S(\omega)
=
\int_{-\infty}^{\infty}
R(\tau) e^{-i\omega\tau}\,d\tau.
\]

In chaotic systems:

\[
R(\tau) \to 0
\quad \text{as} \quad \tau \to \infty.
\]

Decay of correlations leads to a continuous spectrum.

---

## 5.4 Practical Computation

In numerical simulations:

1. Simulate long enough to remove transients.
2. Record \(x(t)\) over a long time window.
3. Compute the discrete Fourier transform (FFT).
4. Plot the magnitude squared.

Interpretation:

- Isolated sharp peaks → periodic.
- Several sharp peaks → quasi-periodic.
- Dense continuous band → chaotic.

---

## 5.5 Limitations

A broadband spectrum alone does **not** prove chaos.

Stochastic noise also produces continuous spectra.

Therefore, spectral analysis must be combined with:

- Largest Lyapunov exponent,
- Poincaré section,
- Phase-space structure.

---

## 5.6 Example: Forced Duffing Oscillator

In the chaotic regime:

- The time series appears irregular.
- The power spectrum shows a continuous band.
- Small remnants of forcing frequency may still appear,
  but without dominant discrete harmonics.

---

## 5.7 Summary

Frequency-domain classification:

\[
\text{Periodic} \rightarrow \text{Discrete spectrum}
\]
\[
\text{Quasi-periodic} \rightarrow \text{Discrete multi-peak spectrum}
\]
\[
\text{Chaotic} \rightarrow \text{Broadband continuous spectrum}
\]

Power spectrum analysis provides a practical,
experimentally accessible method for detecting
continuous-time chaos.

# 6. Bifurcation Analysis and Routes to Chaos

Chaos in continuous-time systems typically does not appear abruptly.
Instead, it emerges as a system parameter is varied through a sequence
of qualitative changes called **bifurcations**.

Studying these transitions provides both structural insight and
a practical method for locating chaotic regimes.

---

## 6.1 Control Parameters

Consider a parametrised system:

\[
\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x}; \mu),
\]

where \(\mu\) is a control parameter
(e.g. forcing amplitude, damping, frequency).

As \(\mu\) varies, the qualitative nature of solutions may change.

These qualitative changes are called **bifurcations**.

---

## 6.2 Local Bifurcations

Before chaos appears, systems often undergo
simpler local bifurcations.

### (a) Saddle–Node Bifurcation

Two fixed points collide and annihilate.

---

### (b) Hopf Bifurcation

A fixed point loses stability and a limit cycle emerges.

In 3D systems, this may lead to quasi-periodic motion on a torus.

---

## 6.3 Period-Doubling Route to Chaos

One of the most common routes to chaos is the
**period-doubling cascade**.

As parameter \(\mu\) increases:

\[
\text{period-1}
\rightarrow
\text{period-2}
\rightarrow
\text{period-4}
\rightarrow
\text{period-8}
\rightarrow
\cdots
\rightarrow
\text{chaos}.
\]

The intervals between bifurcations shrink geometrically,
often following Feigenbaum scaling.

This route occurs in:

- Forced Duffing oscillator,
- Many nonlinear oscillators,
- Fluid convection models.

---

## 6.4 Quasi-Periodic Route (Torus Breakdown)

Another common route:

1. Hopf bifurcation produces a limit cycle.
2. A second frequency appears.
3. Motion lies on a torus.
4. The torus becomes unstable and breaks down.
5. Chaos emerges.

This is called **torus breakdown**.

---

## 6.5 Intermittency

In intermittency:

- Motion alternates between nearly periodic behaviour
  and chaotic bursts.
- As parameter changes, chaotic intervals grow longer.

This route is common near crisis bifurcations.

---

## 6.6 Crisis-Induced Chaos

A **crisis** occurs when a chaotic attractor
suddenly changes size or disappears due to
collision with an unstable invariant set.

This can cause:

- Sudden onset of chaos,
- Sudden expansion of attractor,
- Sudden destruction of chaos.

---

## 6.7 Constructing a Bifurcation Diagram

To visualise routes to chaos:

1. Choose a parameter \(\mu\).
2. Simulate long-term dynamics for many values of \(\mu\).
3. Remove transients.
4. Record local maxima of \(x(t)\)
   or Poincaré section points.
5. Plot these values versus \(\mu\).

Interpretation:

- Single branch → periodic.
- Multiple branches → period-k.
- Dense band → chaos.
- Gaps → periodic windows.

---

## 6.8 Example: Forced Duffing

As forcing amplitude \(\gamma\) increases:

- Stable periodic oscillation,
- Period-doubling cascade,
- Chaotic attractor,
- Periodic windows embedded in chaos.

The bifurcation diagram reveals the structure
of chaotic regions.

---

## 6.9 Why Bifurcation Analysis Is Important

Bifurcation analysis:

- Locates chaotic parameter regions,
- Explains how chaos emerges,
- Reveals universal scaling behaviour,
- Connects continuous-time chaos to discrete-map theory.

---

## 6.10 Summary

Chaos in continuous-time systems typically arises through
well-defined routes:

\[
\text{Periodic}
\rightarrow
\text{Period-doubling / Torus breakdown / Intermittency}
\rightarrow
\text{Chaos}.
\]

Bifurcation diagrams provide a global structural view of
how nonlinear instability develops as system parameters vary.


# 7. Fractal Dimension

For dissipative systems, compute dimension of the attractor:

- Box-counting dimension
- Correlation dimension
- Kaplan–Yorke dimension from Lyapunov spectrum

Non-integer dimension is strong evidence of strange attractors.

---

# 8. Decay of Correlations

Compute the autocorrelation function:

\[
R(\tau) =
\lim_{T\to\infty}
\frac{1}{T}
\int_0^T x(t)x(t+\tau)\,dt.
\]

Chaotic systems typically show decay of correlations,
indicating mixing.

---

# 9. Analytical Prediction (Advanced)

In some systems (e.g. forced Duffing),
the **Melnikov method** can predict transversal
intersection of stable and unstable manifolds,
which implies chaos.

This provides analytical evidence of homoclinic tangles.

---

# Practical Workflow for Continuous-Time Chaos

1. Verify sufficient dimensionality.
2. Simulate long-time dynamics.
3. Remove transients.
4. Compute largest Lyapunov exponent.
5. Construct Poincaré section.
6. Check power spectrum.
7. (Optional) Estimate fractal dimension.

If:
- Motion is bounded,
- Aperiodic,
- Largest Lyapunov exponent > 0,
- Poincaré section is fractal,

then the system is chaotic.

---

# Conceptual Insight

Continuous-time chaos arises from:

\[
\text{Nonlinearity}
+
\text{Instability}
+
\text{Recurrence (boundedness)}.
\]

Stretching generates exponential divergence,
while folding (due to bounded phase space)
creates fractal structure.

Chaos is therefore structured instability,
not randomness.
