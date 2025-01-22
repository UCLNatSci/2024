# Looking at Numerical Solutions to ODEs

## Using odeint

We can look at a code that solves a simple harmonic system for a mass on a spring, $m \ddot{x} + k x = 0$:

````{admonition} ODE code using odeint
:class: dropdown

```python
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

# Simple Harmonic Motion (SHM) system ODE
def shm_system(y, t, m, k):
    x, v = y
    dxdt = v
    dvdt = -(k/m) * x
    return [dxdt, dvdt]

# Initial conditions
initial_conditions = [1.0, 0.0]  # initial displacement and velocity

# Parameters
m = 1.0  # Mass
k = 10.0  # Spring constant

# Time span
t_span = np.linspace(0, 10, 1000)

# Solve the ODE using odeint
solution = odeint(
    shm_system,
    initial_conditions,
    t_span,
    args=(m, k)
)

# Extract displacement and velocity from the solution
displacement, velocity = solution.T

# Plot the results
plt.figure(figsize=(10, 4))
plt.plot(t_span, displacement, label='Displacement (x)')
plt.plot(t_span, velocity, label='Velocity (v)')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()
plt.title('Simple Harmonic Motion (SHM) System')
plt.grid(True)
plt.show()
```
````

As we see this solves the system and produces an output for $x(t)$ and also $v(t) = \dot{x}(t)$.

```{figure} ./run1.png
---
name: run1
---
```

How did we get this into the form that python can then solve it?

Firstly lets look at what `odeint` requires, we need the equations in the form of a coupled system of first order equations (rather than as a second order system), so we can turn
```{math}
m\ddot{x} + k x = 0 \Rightarrow \ddot{x} + \frac{k}{m}x = 0
```

into a new system, where we define the velocity intermediate variable $v = \dot{x}$ and so rewrite as:
```{math}
\dot{x} &= v \\
\dot{v} &= -\frac{k}{m} x
```

which we can recognise as the two lines in the function `shm_system`.
```python 
# Simple Harmonic Motion (SHM) system ODE
def shm_system(y, t, m, k):
    x, v = y
    dxdt = v
    dvdt = -(k/m) * x
    return [dxdt, dvdt]
```

We also need to put in some initial conditions - as we are solving a second order system, we need two of these and they're represent $x(t=0)$ and $\dot{x}(t=0)$.  
```python
initial_conditions = [1.0, 0.0] 
```

We set up a range of $t$ values for the solution in the `t_span` which is an array of 1000 linearly spaced points from $0 \leq t \leq 10$.
```python
t_span = np.linspace(0, 10, 1000)
```

We also pass the paramters `mass` and `spring_constant` to `odeint`, 
```python
solution = odeint(
    shm_system,
    initial_conditions,
    t_span,
    args=(mass, spring_constant)
)
```

The output is an array which we transpose and the first column here is $x(t)$ and the second $\dot{x}(t)$, which will be the same length as `t_span`, 

```python
displacement, velocity = solution.T
```

and finally we plot the results.

We can look up all the parameters of `odeint` [here](https://docs.scipy.org/doc/scipy/reference/generated/scipy.integrate.OdeSolver.html#scipy.integrate.OdeSolver).  

## Using solve_ivp

It turns out that python has *other* ODE packages - `odeint` is problably the most widespread one, but it only has one sort of solver, but there is a more versatile package - `solve_ivp`.

````{admonition} ODE code in solve_ivp
:class: dropdown
```python
import numpy as np
from scipy.integrate import solve_ivp
import matplotlib.pyplot as plt

# Define the differential equation for the mass-spring system
def mass_spring_system(t, y, k, m):
    x, v = y
    dxdt = v
    dvdt = -k / m * x
    return [dxdt, dvdt]

# Set up initial conditions and parameters
initial_conditions = [1.0, 0.0]  # Initial displacement and velocity
m = 1.0  # Mass
k = 10.0  # Spring constant


# Set up time range
t_span = (0, 10)

# Solve the differential equation using solve_ivp
solution = solve_ivp(
    mass_spring_system, 
    t_span, 
    initial_conditions, 
    args=(k, m), 
    dense_output=True)

# Evaluate the solution at specific time points
t_eval = np.linspace(0, 10, 1000)
y_eval = solution.sol(t_eval)

# Extract displacement and velocity from the solution
x, v = y_eval

# Plot the results
plt.figure(figsize=(10, 4))
plt.plot(t_eval, x, label='Displacement (x)')
plt.plot(t_eval, v, label='Velocity (v)')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()
plt.title('Simple Harmonic Motion (SHM) System')
plt.grid(True)
plt.show()
```
````
The parameters for `solve_ivp` are 
`scipy.integrate.solve_ivp(fun, t_span, y0, method='RK45', t_eval=None, dense_output=False, events=None, vectorized=False, args=None, **options)`  and the method can be changed here.  We can look up these parameters [here](https://docs.scipy.org/doc/scipy/reference/generated/scipy.integrate.solve_ivp.html), but the default method is usually fine.



## Phase Portrait Analysis of ODEs

Phase portrait analysis is a powerful visual tool for understanding the qualitative behavior of solutions to ordinary differential equations (ODEs). It involves plotting the trajectories of the system in the phase space, which captures how the state variables evolve over time.


### Phase Space
- A graphical representation where each point corresponds to a unique state of the system.
- For a second-order ODE, the phase space is two-dimensional with axes typically representing the state variable ($x$) and its derivative ($\dot{x}$).

### Trajectories
- The curves in the phase space represent the solutions of the ODE as time progresses.
- The direction of motion along the curves is determined by the system's dynamics.

### Fixed Points (Equilibria)
- Points in the phase space where the system remains stationary ($\dot{x} = 0, \ddot{x} = 0$).
- Fixed points are classified as:
  - **Attractors (Stable)**: Trajectories converge toward the fixed point.
  - **Repellers (Unstable)**: Trajectories diverge from the fixed point.
  - **Saddle Points**: Fixed points that attract along one direction and repel along another.

### Limit Cycles
- Closed trajectories representing periodic solutions of the system.
- Limit cycles can be:
  - **Stable** (attracting): Trajectories spiral toward the limit cycle.
  - **Unstable** (repelling): Trajectories spiral away from the limit cycle.

### Attractors
- Sets (e.g., fixed points, limit cycles) to which the system evolves after a long time, regardless of initial conditions within a specific region.

### Repellers
- States or regions from which trajectories are pushed away.

---

### Basic Example: Simple Harmonic Motion (SHM)

The equation for SHM is:

```{math}
\ddot{x} + \omega^2 x = 0
```

- Introducing $v = \dot{x}$, the equation can be rewritten as a first-order system:

```{math}
\dot{x} = v, \quad \dot{v} = -\omega^2 x
```

- The phase portrait for this system is a set of concentric circles centered at the origin ($x = 0, v = 0$):
  - **Fixed Point**: $(x, v) = (0, 0)$ (center, neutrally stable).
  - Trajectories represent oscillations with constant amplitude and period.

---

Below is Python code to generate phase portraits for a simple harmonic motion system.

````{admonition} Phase Portraits
:class: dropdown

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Define the SHM system
def shm_system(t, z, omega):
    x, v = z
    dxdt = v
    dvdt = -omega**2 * x
    return [dxdt, dvdt]

# Parameters
omega = 1.0  # Angular frequency
t_span = [0, 20]  # Time range for simulation
initial_conditions = [
    [1.0, 0.0],
    [0.0, 1.0],
    [0.5, 0.5],
    [-1.0, -1.0],
    [1.5, -0.5]
]  # Various initial conditions

# Generate and plot the phase portraits
plt.figure(figsize=(8, 8))
for ic in initial_conditions:
    sol = solve_ivp(shm_system, t_span, ic, args=(omega,), t_eval=np.linspace(t_span[0], t_span[1], 500))
    plt.plot(sol.y[0], sol.y[1], label=f'IC: x0={ic[0]}, v0={ic[1]}')

# Add labels and formatting
plt.title("Phase Portrait of Simple Harmonic Motion")
plt.xlabel("x (Position)")
plt.ylabel("v (Velocity)")
plt.axhline(0, color='gray', linewidth=0.5)
plt.axvline(0, color='gray', linewidth=0.5)
plt.grid()
plt.legend()
plt.show()
````

## Vector Field Flows in Phase Portrait Diagrams

A **vector field** in a phase portrait represents the direction and rate of change of the system's state variables at each point in the phase space. It provides a comprehensive view of how the system evolves over time, independent of specific initial conditions.

Key Features of Vector Field Flows

### Direction
- The direction of the arrows in the vector field indicates the instantaneous rate of change of the system's variables.
- For a two-dimensional system, this corresponds to the derivatives $\dot{x}$ and $\dot{v}$ (or $\dot{y}$, depending on the system).

### Magnitude
- The length of the arrows reflects the speed at which the system evolves at that point in the phase space.
- Arrows in regions where the system changes slowly are shorter, while those in rapidly changing regions are longer.

### Normalization
- In many visualizations, the arrows are normalized to emphasize direction rather than magnitude. This ensures that the flow patterns remain visible even when the system has regions with drastically different speeds.

### Interpretation
- The vector field provides a "map" of the system's dynamics, showing how trajectories flow toward, away from, or around features like fixed points and limit cycles.
- Arrows pointing toward a fixed point suggest it is an **attractor**, while arrows pointing away indicate a **repeller**.

---

Importance in Phase Portraits

### Trajectories
- By integrating the vector field, we obtain the trajectories of the system for given initial conditions. These trajectories describe the actual paths followed in the phase space.

### Qualitative Behavior
- The vector field reveals qualitative behavior, such as oscillations, divergence, or convergence, without requiring explicit solutions to the ODE.

### Stability Analysis
- The flow around fixed points can help determine their stability. For example:
  - Spiraling arrows indicate a **spiral point** (stable or unstable).
  - Radial arrows indicate **nodes** (converging for attractors, diverging for repellers).
  - Saddle points show arrows converging along one direction and diverging along another.

---

### Example: Simple Harmonic Motion (SHM)

In the case of SHM ($\ddot{x} + \omega^2 x = 0$):
- The vector field is defined by:
  ```{math}
  \dot{x} = v, \quad \dot{v} = -\omega^2 x
  ```
- The flow is circular around the origin, reflecting the periodic nature of SHM.
- The origin ($x = 0, v = 0$) is a **neutrally stable fixed point**, with no damping or driving forces altering the energy of the system.

---


Below is Python code to generate a phase portrait for a simple harmonic motion system, complete with arrows to indicate the flow of solutions.

````{admonition} Vector Flow Phase Portrait
:class: dropdown

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Define the SHM system
def shm_system(t, z, omega):
    x, v = z
    dxdt = v
    dvdt = -omega**2 * x
    return [dxdt, dvdt]

# Parameters
omega = 1.0  # Angular frequency
t_span = [0, 20]  # Time range for simulation
initial_conditions = [
    [1.0, 0.0],
    [0.0, 1.0],
    [0.5, 0.5],
    [-1.0, -1.0],
    [1.5, -0.5]
]  # Various initial conditions

# Create grid for vector field
x = np.linspace(-2, 2, 20)
v = np.linspace(-2, 2, 20)
X, V = np.meshgrid(x, v)
dX = V
dV = -omega**2 * X

# Normalize vectors for consistent arrow lengths
magnitude = np.sqrt(dX**2 + dV**2)
dX_normalized = dX / magnitude
dV_normalized = dV / magnitude

# Plot phase portraits
plt.figure(figsize=(8, 8))
for ic in initial_conditions:
    sol = solve_ivp(shm_system, t_span, ic, args=(omega,), t_eval=np.linspace(t_span[0], t_span[1], 500))
    plt.plot(sol.y[0], sol.y[1], label=f'IC: x0={ic[0]}, v0={ic[1]}', lw=1.5)

# Add arrows to show the vector field
plt.quiver(X, V, dX_normalized, dV_normalized, color='blue', alpha=0.6, scale=25)

# Add labels and formatting
plt.title("Phase Portrait of Simple Harmonic Motion with Flow Arrows")
plt.xlabel("x (Position)")
plt.ylabel("v (Velocity)")
plt.axhline(0, color='black', linewidth=0.8, linestyle='--')
plt.axvline(0, color='black', linewidth=0.8, linestyle='--')
plt.grid(color='gray', linestyle='--', linewidth=0.5, alpha=0.7)
plt.legend()
plt.tight_layout()
plt.show()
````

## Exercises 

````{admonition} Exercises with ODE solvers

1\. Write a code to solve a damped harmonic oscillator:
```{math}
\ddot{x} + 2 \omega_0 \zeta \dot{x} + \omega_0^2 x = 0
```
where $\omega_0^2 = k/m$ and the damping ratio $\zeta$ can take different values.  

2\. Plot solutions for $\zeta = 0,\, \zeta = 0.5, \zeta = 1, \zeta = 2$ and pick sensible values of other parameters, plotting a time series $x(t)$ vs $t$.

Also try plotting a phase portrait here, $x(t)$ vs $\dot{x}(t)$.

3\. Add a source term to the ODE:
```{math}
\ddot{x} + 2 \omega_0 \zeta \dot{x} + \omega_0^2 x = F_0\,\cos(\Omega t)
```
where we can add in an oscilating term with amplitude $F_0$ and frequency $\Omega$ and repeat your analysis.

````
