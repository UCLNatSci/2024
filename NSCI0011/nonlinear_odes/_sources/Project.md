# Project Submission Information

## Protype Submission

Your protype should include the 

### Python Code

- **Complete and Functional Code**: Provide the full Python script that performs the following tasks:
  
1. Solves the specified ordinary differential equation (ODE).
2. Generates a time series plot.
3. Generates a phase portrait plot.

- **Code Comments**: Include clear and concise comments within your code to explain:
4. Initial conditions setup.
5. ODE formulation and integration method.
6. Plotting functions and any other significant code segments.

*Example*:

```python
    import numpy as np
    import matplotlib.pyplot as plt
    from scipy.integrate import solve_ivp

    # Define the system of ODEs
    def system(t, y):
        dydt = [...]
        return dydt

    # Initial conditions
    y0 = [...]

    # Time span for the solution
    t_span = [...]

    # Solve the ODE
    solution = solve_ivp(system, t_span, y0, ...)

    # Plotting the time series
    plt.figure()
    plt.plot(solution.t, solution.y[0], label='Variable 1')
    plt.plot(solution.t, solution.y[1], label='Variable 2')
    plt.xlabel('Time')
    plt.ylabel('Variables')
    plt.title('Time Series Plot')
    plt.legend()
    plt.show()

```

### Plots

- **Time Series Plot**: Illustrate how the system's variables evolve over time.

- **Phase Portrait Plot**: Depict the trajectories of the system in the phase plane.

*Note*: Choose initial conditions that highlight interesting behaviors in the system. Exploring a variety of initial conditions can reveal a range of dynamics.

### Description Document
- **Length**: Limit to one page maximum.

- **Content**:
  - **Analysis of Plots**: Discuss very brieflt the behaviors observed in your plots.
  - **Code Explanation**:
    - Describe how the ODE was transformed into a coupled system for numerical solving.
    - Specify the initial conditions used and the rationale behind their selection.
    - Briefly explain the numerical methods or solvers employed.

*Example*:

In the time series plot, Variable 1 exhibits damped oscillations, converging to a steady state, while Variable 2 shows a monotonic decrease. The phase portrait reveals a spiral trajectory indicating a stable focus at the origin. The ODE was decomposed into a system of first-order equations to facilitate the use of the `solve_ivp` solver from SciPy. Initial conditions were selected to demonstrate the system's response to perturbations from equilibrium.
