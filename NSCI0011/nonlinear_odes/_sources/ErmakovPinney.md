# The Ermakov-Pinney Equation

The **Ermakov-Pinney equation** is a nonlinear second-order differential equation of the form:

```{math}
\frac{d^2 y}{dt^2} + \omega^2(t) y = \frac{\lambda}{y^3}
```

where $ y = y(t) $ is the unknown function, $ \omega(t) $ is a given function of time (often related to an oscillator), and $ \lambda $ is a constant.

## Background and Origins
- The equation was originally studied by **Vladimir Ermakov** in 1880 in the context of nonlinear differential equations.
- Later, **Edward Pinney** (1950) independently rediscovered it while studying solutions to the **time-dependent harmonic oscillator**.
- The Ermakov-Pinney equation appears naturally in problems involving **parametric oscillators** and **quantum mechanics**.

## Connection to the Linear Oscillator
- The general solution of the **linear** equation 

  ```{math}
  \frac{d^2 x}{dt^2} + \omega^2(t) x = 0
  ```

  provides a basis for solving the **Ermakov-Pinney equation**. If $ x_1(t) $ and $ x_2(t) $ are two linearly independent solutions of this equation, then the solution to the Ermakov-Pinney equation is given by:

  ```{math}
  y(t) = \sqrt{A x_1^2 + B x_1 x_2 + C x_2^2}
  ```

  where $ A, B, C $ are constants satisfying $ 4AC - B^2 = \lambda $.

## Forms of $ \omega(t) $ and $ \lambda(t) $
### Constant $ \omega $ and $ \lambda $
- $ \omega(t) = \omega_0 $, $ \lambda = \lambda_0 $ (simple harmonic case)
- $ \omega(t) = i \gamma $, $ \lambda = \lambda_0 $ (damped system)

### Variable $ \omega(t) $ with Constant $ \lambda $
- **Adiabatic variation**: $ \omega(t) = \omega_0 (1 + \epsilon t) $
- **Parametric modulation**: $ \omega(t) = \omega_0 + \alpha \cos(\Omega t) $
- **Power-law variation**: $ \omega(t) = \frac{\omega_0}{t} $

### Constant $ \omega $ with Variable $ \lambda(t) $
- **Decaying nonlinearity**: $ \lambda(t) = \lambda_0 e^{- \beta t} $
- **Oscillatory nonlinearity**: $ \lambda(t) = \lambda_0 \cos(\nu t) $

## Solutions for Adiabatically Varying Frequency
For an **adiabatic variation** of frequency:

```{math}
\omega(t) = \omega_0 (1 + \epsilon t)
```

we numerically solve the Ermakov-Pinney equation:

```{math}
\frac{d^2 y}{dt^2} + (\omega_0 (1 + \epsilon t))^2 y = \frac{\lambda}{y^3}
```

where $ \lambda = 1.0 $, $ \omega_0 = 1.0 $, and different values of $ \epsilon $ are considered.

