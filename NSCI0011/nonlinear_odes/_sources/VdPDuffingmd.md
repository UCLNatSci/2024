# Week 3 - The Van der Pol Oscillator and Duffing Equation

The Van der Pol oscillator is a nonlinear dynamical system with broad applications in physics, biology, and engineering.  The Van der Pol oscillator was first proposed by Dutch engineer and physicist Balthasar van der Pol while working at Philips. He discovered stable oscillations, which he called relaxation oscillations (now identified as a type of limit cycle), in electrical circuits containing vacuum tubes. When these circuits were driven near the limit cycle, their current synchronized with the driving signal, a phenomenon known as entrainment. In 1927, Van der Pol and his colleague Van der Mark reported in Nature[1] that irregular noise was observed at specific drive frequencies, which was later understood to be deterministic chaos.

The Van der Pol equation has been widely applied in both physical and biological sciences. In biology, FitzHugh and Nagumo extended the equation to model neuron action potentials in a planar field. It has also been used in seismology to model the interaction of geological fault plates and in phonation research to describe oscillations of the vocal folds.

[1] Frequency Demultiplication" by Balth. van der Pol and J. van der Mark, published in Nature, Volume 120, pages 363–364, on September 10, 1927. 

---

## Mathematical Formulation

The Van der Pol oscillator is governed by the second-order nonlinear differential equation:

```{math}
\frac{\mathrm{d}^2x}{\mathrm{d}t^2} - \mu(1 - x^2)\frac{\mathrm{d}x}{\mathrm{d}t} + x = 0,
```

where:
- $x(t)$ is the state variable (e.g., displacement or voltage).
- $\mu > 0$ is the nonlinearity parameter, controlling the strength of damping and the nonlinearity.

This equation can also be written as a system of first-order ODEs:

```{math}
\begin{aligned}
    \frac{\mathrm{d}x}{\mathrm{d}t} &= y, \\
    \frac{\mathrm{d}y}{\mathrm{d}t} &= \mu(1 - x^2)y - x.
\end{aligned}
```

---

## Dynamics

- **Small $\mu$:** The system behaves like a harmonic oscillator with nearly sinusoidal solutions.
- **Large $\mu$:** The system exhibits nonlinear effects, with relaxation oscillations—periodic oscillations with sharp transitions and slow changes in amplitude.

We can see this in the phase-portrait of this system:

![Van der Pol Oscillator](vanderpol_plot.png)
---

There are some interesting features that we see in the Van der Pol system:

1. **Nonlinear Damping:**
   - When $|x| > 1$: The damping is positive (energy dissipation).
   - When $|x| < 1$: The damping is negative (energy is pumped into the system).
   
   This mechanism drives the system toward a limit cycle.

2. **Limit Cycle Oscillations:**
   - For $\mu > 0$, the system exhibits stable limit cycles regardless of initial conditions.
   - The amplitude of the limit cycle is approximately independent of $\mu$, but the shape becomes more pronounced with larger $\mu$.

3. **Self-Sustained Oscillations:**
   - Oscillations persist due to the balance between energy input (negative damping) and dissipation (positive damping).

---

There are a variety of systems where the VdP oscillator describes the dynamics:

- **Electrical Engineering:**  
  Modeling vacuum tube circuits and oscillators.

- **Biology:**  
  Describing heartbeat dynamics and neural oscillations.

- **Mechanical Systems:**  
  Modeling systems with non-linear damping.

- **Synchronization:**  
  The Van der Pol oscillator is often used to study synchronization phenomena in coupled systems.

---

# The Duffing Equation

The **Duffing equation** is a nonlinear second-order differential equation that models oscillators with a nonlinear restoring force. It is a standard example in nonlinear dynamics and chaos theory.
## Chaos

With both damping and forcing, the Duffing equation can exhibit **deterministic chaos**:

- Extreme sensitivity to initial conditions
- Strange attractors in phase space
- Period-doubling routes to chaos

The periodically forced Duffing oscillator, particularly in the double-well regime, is a textbook example of chaotic dynamics.

---


The Duffing equation appears in many real systems, including:

- Mechanical oscillators with large deflections
- Structural vibrations
- Nonlinear electrical circuits
- MEMS and NEMS resonators
- Models in climate dynamics and neuroscience

---

## 7. Key Takeaway

The Duffing equation demonstrates that adding a single cubic nonlinearity to a harmonic oscillator is enough to produce:

- Amplitude-dependent frequencies  
- Bistability  
- Hysteresis  
- Chaos  

It is one of the simplest systems that clearly illustrates how nonlinear dynamics departs from linear intuition.


---


The equation is typically written as

\[
\ddot{x} + \delta \dot{x} + \alpha x + \beta x^3 = \gamma \cos(\omega t),
\]

where:

- \(x(t)\): displacement  
- \(\ddot{x}\): acceleration (inertia)  
- \(\delta \dot{x}\): damping  
- \(\alpha x\): linear restoring force  
- \(\beta x^3\): **nonlinear stiffness term**  
- \(\gamma \cos(\omega t)\): external periodic forcing  

When \(\beta = 0\), the equation reduces to the linear driven, damped harmonic oscillator.

---

## Role of the Cubic Term

The cubic term \( \beta x^3 \) introduces nonlinearity and fundamentally changes the system’s behaviour.

### Hardening and softening springs

- **\(\beta > 0\)**: hardening spring  
  - Oscillation frequency increases with amplitude.
- **\(\beta < 0\)**: softening spring  
  - Oscillation frequency decreases with amplitude.

As a result, resonance becomes amplitude-dependent and superposition no longer applies.

---

## Unforced, Undamped Duffing Oscillator

Setting \(\delta = 0\) and \(\gamma = 0\) gives

\[
\ddot{x} + \alpha x + \beta x^3 = 0.
\]

This is a conservative system that can be analysed using the potential energy

\[
V(x) = \tfrac12 \alpha x^2 + \tfrac14 \beta x^4.
\]

### Equilibria

- \(\alpha > 0, \beta > 0\):  
  - Single stable equilibrium at \(x = 0\).
- \(\alpha < 0, \beta > 0\):  
  - Double-well potential with two stable equilibria and one unstable equilibrium at \(x = 0\).

The double-well case is especially important for understanding nonlinear transitions and chaos.

---

## Forced Duffing Oscillator

When periodic forcing is present (\(\gamma \neq 0\)):

- The resonance curve bends:
  - Rightward for hardening systems
  - Leftward for softening systems
- Multiple steady-state solutions may exist for the same parameters.
- Sudden jumps in oscillation amplitude can occur as parameters (e.g. driving frequency) are varied.

This leads to **hysteresis**, which does not occur in linear oscillators.

---



## Method of Multiple Scales

### Rationale

A simple example illustrating the need for an additional **super-slow time scale** is the **linearly damped oscillator**:

```{math}
\ddot{x} + 2\varepsilon \dot{x} + x = 0.
```

The solution is:

```{math}
x = e^{-\varepsilon t} \cos \left(\sqrt{1- \varepsilon^2} t\right)
```

In this case:
- The **amplitude** drifts on the time scale $ O(\varepsilon^{-1}) $.
- The **phase** drifts on the longer time scale $ O(\varepsilon^{-2}) $.

By the time the phase has shifted significantly, the amplitude has already decayed substantially. In general when working to $\mathcal{O}(\varepsilon^k)$ on a time scale $\mathcal{O}(\varepsilon^{k-n})$ one must expect to have a hierarchy of $n$ slow time scales. Some of these may be essential to the system, representing genuinely different processes. 


### Non-linear Pendulum

For the non-linear pendulum, $\ddot{\theta} + \sin(\theta) = 0$ we examined perturbatie solutions last week.  The perturbation series that we derived for $ \theta(t) $ had a secular term (proportional to $ t $) that causes it to lose validity at large times, even for small $ \varepsilon $. The physical cause of this problem was a slow phase drift of the true solution away from the unperturbed solution due to the nonlinear correction to the pendulum period. It would be nice to devise a perturbation series approach that remained valid at long time by accounting for such slow drifts to avoid secular terms. The method of multiple scales accomplishes this goal.


The idea, as applied to the nonlinear pendulum problem,

```{math}
\frac{d^2\theta}{dt^2} + \sin\theta = 0, \quad \theta(0) = \varepsilon \ll1, \quad \frac{d\theta}{dt}(0) = 0.
```

is to make $ \theta(t) $ formally a function of multiple time scales that capture the fast and slow time variability of the solution. Since the first nonlinear correction to the solution is of order $ \varepsilon^2 $ compared to the unperturbed solution, we introduce the timescales

```{math}
t_0 = t, \quad t_2 = \varepsilon^2 t, \dots
```

and (to the order of accuracy needed for our purposes)

```{math}
\theta(t) = \varepsilon \theta_1(t_0, t_2) + \varepsilon^3 \theta_3(t_0, t_2) + \dots
```

Having multiple variables to describe the time dependence is redundant, but this redundancy can be exploited to develop a perturbation series with no secular terms that is uniformly valid for all small $ \varepsilon $.

Turning to the equation, note that

```{math}
\frac{d\theta_k}{dt} = \frac{\partial \theta_k}{\partial t_0} + \varepsilon^2 \frac{\partial \theta_k}{\partial t_2}
```

so that

```{math}
\frac{d^2\theta_k}{dt^2} = \left( \frac{\partial}{\partial t_0} + \varepsilon^2 \frac{\partial}{\partial t_2} \right)^2 \theta_k = \frac{\partial^2 \theta_k}{\partial t_0^2} + 2\varepsilon^2 \frac{\partial^2 \theta_k}{\partial t_0 \partial t_2} + \dots
```

while

```{math}
\sin \theta = \varepsilon \theta_1 + \varepsilon^3 (\theta_3 - \frac{\theta_1^3}{6}) + \dots
```

Substituting these series into the nonlinear pendulum equation and sorting by increasing powers of $ \varepsilon $, we get:

#### $ \mathcal{O}\left(\varepsilon^1\right) Order $:

```{math}
0 = \frac{\partial^2 \theta_1}{\partial t_0^2} + \theta_1, \quad \theta_1(t_0 = 0, t_2 = 0) = 1, \quad \frac{\partial \theta_1}{\partial t_0}(t_0 = 0, t_2 = 0) = 0.
```

Solving this,

```{math}
\theta_1(t) = A(t_2) \cos t_0 + B(t_2) \sin t_0, \quad A(0) = 1, \quad B(0) = 0.
```

The formal dependence on the slow time $ t_2 $ allows the leading-order solution to be more general than in our original perturbation series solution. This is how the method accounts for the slow phase shift of the perturbed solution.

#### $ \mathcal{O}\left(\varepsilon^3\right) $ Order:

```{math}
\frac{\partial^2 \theta_3}{\partial t_0^2} + 2 \frac{\partial^2 \theta_1}{\partial t_0 \partial t_2} + \theta_3 - \frac{\theta_1^3}{6} = 0.
```

Using the known form of $ \theta_1 $, we deduce:

```{math}
\frac{\partial^2 \theta_3}{\partial t_0^2} + \theta_3 = -2 \frac{dA}{dt_2} \sin t_0 + 2 \frac{dB}{dt_2} \cos t_0 + \frac{1}{6} (A \cos t_0 + B \sin t_0)^3.
```

To suppress secular terms, the coefficient of $ e^{it} $ and $ e^{-it} $ must be zero:

```{math}
0 = -\frac{dB}{dt_2} + i \frac{dA}{dt_2} + \frac{3}{48} (A - iB)^2 (A + iB).
```

Separating into real and imaginary parts,

```{math}
\frac{dB}{dt_2} = \frac{1}{16} A(A^2 + B^2), \quad \frac{dA}{dt_2} = -\frac{1}{16} B(A^2 + B^2).
```

This pair of coupled ODEs determines the slow evolution of the leading-order solution. Noting that

```{math}
\frac{d}{dt_2} (A^2 + B^2) = 0 \Rightarrow A^2 + B^2 = 1.
```

Thus, the ODEs simplify to:

```{math}
\frac{dB}{dt_2} = \frac{1}{16} A, \quad \frac{dA}{dt_2} = -\frac{1}{16} B.
```

Solving these,

```{math}
A(t_2) = \cos \frac{t_2}{16}, \quad B(t_2) = \sin \frac{t_2}{16}.
```

Thus, the slow-time behavior of the leading-order solution is:

```{math}
\theta_1(t) = \cos \frac{t_2}{16} \cos t_0 + \sin \frac{t_2}{16} \sin t_0 = \cos \left( t_0 - \frac{t_2}{16} \right) = \cos t \left( 1 - \frac{\varepsilon^2}{16} \right).
```

The corresponding period is:

```{math}
T = 2\pi \left( 1 - \frac{\varepsilon^2}{16} \right) \approx 2\pi \left( 1 + \frac{\varepsilon^2}{16} \right),
```

which matches the result derived from previous methods.

#### $ \theta_3(t_0, t_2) $ Correction Term

Solving for the correction term,

```{math}
\frac{\partial^2 \theta_3}{\partial t_0^2} + \theta_3 = \frac{1}{48} \left( [A - iB]^3 e^{3it_0} + [A + iB]^3 e^{-3it_0} \right).
```

By solving for $ \theta_3 $, we find:

```{math}
\theta_3(t_0, t_2) = -\frac{1}{192} \left( \cos^3 (t_0 - t_2/16) + A_3(t_2) \cos t_0 + B_3(t_2) \sin t_0 \right).
```

Matching initial conditions,

```{math}
A_3(t_2) = \frac{1}{192}, \quad B_3(0) = 0.
```

Thus,

```{math}
\theta_3(t_0, t_2) = \frac{1}{192} \left( \cos (t_0 - t_2/16) - \cos^3 (t_0 - t_2/16) \right),
```

which is consistent with the regular perturbation series - but without the secular terms!

We can see the difference in a plot, against the numerical solutions:
![method of multiple scales against numerical solutions](nonlinearpmms.png)

### Van der Pol Application
Applying this method to the Van der Pol oscillator,


```{math}
\ddot{x} + \varepsilon (x^2 - 1) \dot{x} + x = 0, \quad t > 0, \quad \text{with } \varepsilon \ll 0
```

subject to:

```{math}
x(0) = 1, \quad \dot{x}(0) = 0.
```

Treating the problem as a regular one yields the approximation:

```{math}
x(t, \varepsilon) \approx \cos t + \varepsilon \left[ \frac{3}{8} \left(t \cos t - \sin t\right) - \frac{1}{32} \left(\sin 3t - 3 \sin t\right) \right].
```

This expansion is asymptotic for fixed $ t $ as $ \varepsilon \to 0 $, but breaks down when $ t = \mathcal{O}\left(\varepsilon^{-1}\right) $. (It is, however, possible to prove that the expansion converges!)

The problem with the naive approximation is that the $ \varepsilon $-damping changes the amplitude of the oscillation on a time scale $ \mathcal{O}\left(\varepsilon^{-1}\right) $ due to the slow accumulation of small effects. Thus, the oscillator has two processes acting on their own time scales:

1. The basic oscillation on the time scale of $ \mathcal{O}\left(1\right) $ due to inertia causing the restoring force to overshoot the equilibrium position.
2. The slow drift in the amplitude (and possibly the phase) on the time scale $ \mathcal{O}\left(\varepsilon^{-1}\right) $ due to small friction.

We recognize these two time scales by introducing two time variables:

```{math}
\tau = t \quad \text{(the fast time of the oscillation)}
```
```{math}
T = \varepsilon t \quad \text{(the slow time of the amplitude drift)}
```

The slowly changing features will then be combined into factors that are functions of $ T $, while the rapidly changing features will be combined into factors that are functions of $ \tau $. Thus, we look for a solution of the form:

```{math}
x(t; \varepsilon) = X(T, \tau; \varepsilon).
```

As real time $ t $ increases, the fast time $ \tau $ increases at the same rate, while the slow time $ T $ increases slowly. Thus,

```{math}
\frac{d}{dt} = \frac{\partial}{\partial \tau} + \varepsilon \frac{\partial}{\partial T}.
```

We now seek an asymptotic approximation for $ x $ allowing for changes over the long time scale. Thus, we pose:

```{math}
x(t; \varepsilon) \approx X_0(T, \tau) + \varepsilon X_1(T, \tau)
```

with the requirement that the expansion be asymptotic for $ T = O(1) $. Substituting into the governing equation and comparing coefficients of $ \varepsilon^n $, we find a sequence of problems.

#### $ \mathcal{O}\left(\varepsilon^0\right) $ order:

```{math}
\frac{\partial^2 X_0}{\partial \tau^2} + X_0 = 0, \quad t > 0
```

with initial conditions:

```{math}
X_0(0) = 1, \quad \frac{\partial X_0}{\partial \tau}(0) = 0.
```

Integrating with respect to $ \tau $, treating $ T $ as an independent variable held constant, we obtain the general solution:

```{math}
X_0 = R(T) \cos (\tau + \theta(T)),
```

where $ R $ and $ \theta $ are constant as far as the rapid $ \tau $ variations are concerned but are allowed to vary over the long $ T $ time scale. The initial conditions give:

```{math}
R(0) = 1, \quad \theta(0) = 0.
```

Except for this information, $ R $ and $ \theta $ are unknown in the leading order analysis. Knowing that the amplitude is controlled by the action of the small friction over a long time, we must proceed to the next order.

#### $ \mathcal{O}\left(\varepsilon^1\right) $ Order:

```{math}
\frac{\partial^2 X_1}{\partial \tau^2} + X_1 = -(X_0^3 - X_0).
```

Substituting the leading order solution:

```{math}
2 R \frac{d\theta}{dT} \cos (\tau + \theta) + \left( 2 \frac{dR}{dT} + \frac{3}{4} R^3 - R \right) \sin (\tau + \theta) + \frac{1}{4} R^3 \sin 3(\tau + \theta) = 0.
```

To maintain the asymptotic validity of the expansion, we must eliminate secular terms that grow unboundedly. This leads to the solvability conditions:

```{math}
\frac{d\theta}{dT} = 0, \quad \frac{dR}{dT} = \frac{1}{8} R (4 -  R^2).
```

Using the initial conditions:

```{math}
\theta = 0, \quad R = 2(1 + 3e^{-T})^{-1/2}.
```

Thus, eventually, the amplitude of the oscillator drifts to 2. Note that the amplitude and phase of the leading order term are fully determined in the next order problem by ensuring that the correction term does not break the asymptotic validity; it is not necessary to explicitly find the correction term.

However, the correction term can still be found and is given by:

```{math}
X_1 = -\frac{1}{32} R^3 \sin 3\tau + S(T) \sin (\tau + \theta(T)),
```

where $ S(T) $ and $ \theta(T) $ are new unknown amplitude and phase functions. 

The amplitude drifts on the time scale $ \mathcal{O}\left(1\right) $, while the phase drifts on the longer time scale $ O(\varepsilon^{-2}) $. In this example, by the time the phase has shifted significantly, the amplitude has already decayed considerably.

In general, when working at $ \mathcal{O}\left(k\right) $ on a time scale $ \mathcal{O}\left(\varepsilon^{-n}\right) $, one must expect a **hierarchy of $ n $ slow time scales**. Some of these slow time scales represent genuinely different physical processes, while others may simply be **adjustments to a previous process**, such as frequency corrections, which are often better handled using coordinate straining.

#### Initial Conditions

The unknown functions $ S(T) $ and $ \theta(T) $ satisfy the initial conditions:

```{math}
S(0) = -\frac{9}{32}, \quad \theta(0) = 0.
```

These new amplitude and phase functions will ultimately be determined by the **secularity condition** in the $ O(\varepsilon) $ problem.

#### Breakdown of Asymptotics at Higher Orders

At higher orders, resonant forcing may become **unavoidable** due to insufficient freedom in the undetermined functions. This leads to a **loss of asymptotic validity**. 

This is precisely what occurs in the **Van der Pol oscillator** when attempting to determine $ X_2 $ at $ O(\varepsilon) $ for $ t = O(\varepsilon^{-1}) $. The issue can be resolved by introducing an **additional slow time scale**:

```{math}
T_2 = \varepsilon^2 t.
```



---



## Exercises 

````{admonition} Exercises with ODE solvers
1\. Get some numerical solutions out of Python, what does the time series for the Van der Pol Oscillator look like?

2\. Get a phase portrait out and look at small $\mu$ (where daqmped oscillator solutions are valid) and large $\mu$ results (damped oscillator solutions are not valid) - what conclusions can we draw?

3\. The forced Van der Pol oscillator includes an external driving term:

```{math}
\frac{\mathrm{d}^2x}{\mathrm{d}t^2} - \mu(1 - x^2)\frac{\mathrm{d}x}{\mathrm{d}t} + x = F\cos(\Omega t),
```

where $F$ is the forcing amplitude and $\Omega$ is the forcing frequency. 

How does adding in a forcing term change the dynamics of this system? Add this to your code and compare.

4\. Compare your numerical results to the method of multiple scales results.

5\. Start solving the Duffing equatoin in Python, can we find any sorts of solutions with stable limit cycles.



