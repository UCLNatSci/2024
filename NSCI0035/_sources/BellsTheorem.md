# Bell's Theorem and Bell Inequalities

**Bell's theorem** demonstrates the incompatibility between the predictions of quantum mechanics and any theory based on local hidden variables. Local hidden variable theories assume that particles have predetermined properties (hidden variables) that determine measurement outcomes, with no faster-than-light influence between particles. Bell's theorem shows that no local hidden variable theory can reproduce the full range of quantum mechanical correlations, especially those seen in entangled particles.

## Background: Local Hidden Variable Theories

In a **local hidden variable theory**, measurement outcomes are determined by properties (hidden variables) that are predetermined at the time of particle creation. According to locality, the measurement result on one particle should not depend on measurements made on another particle at a space-like separation. Bell showed that if such a theory were correct, then certain correlations between measurement outcomes should satisfy an inequality—a **Bell inequality**—that places limits on the strength of these correlations. Quantum mechanics, however, predicts correlations that violate these inequalities, suggesting that either locality or realism (or both) must be abandoned.

## Bell Inequalities and Their Calculation

The most commonly used Bell inequality, the **CHSH inequality** (named after John Clauser, Michael Horne, Abner Shimony, and Richard Holt), provides a way to test whether the correlations between measurements on entangled particles are consistent with a local hidden variable theory.

### Setup for the CHSH Inequality

Consider two distant observers, **Alice** and **Bob**, who each have access to a particle from an entangled pair. Each observer can choose one of two measurement settings:
- **Alice's choices**: $ A $ and $ A' $
- **Bob's choices**: $ B $ and $ B' $

The measurement outcomes for each setting can be either $ +1 $ or $ -1 $.

Let:
- $ E(A, B) $ represent the **correlation** between Alice's and Bob's measurement outcomes when Alice chooses setting $ A $ and Bob chooses setting $ B $.
- The correlation $ E(A, B) $ is calculated as the average product of their outcomes for a large number of measurement pairs:
  ```{math}
  E(A, B) = \langle A \cdot B \rangle
  ```

### Deriving the CHSH Inequality

For a local hidden variable theory, Bell derived that the following inequality must hold for any possible choice of local hidden variables:
```{math}
|E(A, B) + E(A, B') + E(A', B) - E(A', B')| \leq 2
```
This inequality, known as the CHSH inequality, sets a limit on the correlations that can exist between measurements in a local hidden variable theory.

### Calculating the Quantum Prediction for CHSH

In quantum mechanics, the CHSH expression can exceed the classical bound of 2, reaching a maximum value of $ 2\sqrt{2} $. This is due to the entanglement between particles, which generates stronger-than-classical correlations. Quantum mechanics predicts that:
```{math}
|E(A, B) + E(A, B') + E(A', B) - E(A', B')| \leq 2\sqrt{2}
```

#### Example Calculation 1: Using Spin Measurements

Consider a pair of entangled particles in the singlet state:
```{math}
|\psi\rangle = \frac{1}{\sqrt{2}} \left( | \uparrow \downarrow \rangle - | \downarrow \uparrow \rangle \right)
```
where $ | \uparrow \rangle $ and $ | \downarrow \rangle $ represent spin-up and spin-down states, respectively. Alice and Bob choose measurement directions represented by angles $ \theta_A, \theta_{A'}, \theta_B, \theta_{B'} $, and calculate the correlation $ E(\theta_A, \theta_B) $ based on these angles.

The quantum mechanical prediction for the correlation between spin measurements along angles $ \theta_A $ and $ \theta_B $ is:
```{math}
E(\theta_A, \theta_B) = -\cos(\theta_A - \theta_B)
```

For optimal violation of the CHSH inequality, choose angles such that:
- $ \theta_A = 0^\circ $
- $ \theta_{A'} = 45^\circ $
- $ \theta_B = 22.5^\circ $
- $ \theta_{B'} = 67.5^\circ $

Then:
```{math}
E(A, B) = -\cos(0^\circ - 22.5^\circ) = -\cos(22.5^\circ) \approx -0.924
```
```{math}
E(A, B') = -\cos(0^\circ - 67.5^\circ) = -\cos(67.5^\circ) \approx -0.383
```
```{math}
E(A', B) = -\cos(45^\circ - 22.5^\circ) = -\cos(22.5^\circ) \approx -0.924
```
```{math}
E(A', B') = -\cos(45^\circ - 67.5^\circ) = -\cos(22.5^\circ) \approx -0.383
```

Now, calculate the CHSH expression:
```{math}
|E(A, B) + E(A, B') + E(A', B) - E(A', B')| \approx |(-0.924) + (-0.383) + (-0.924) - (-0.383)|
```
```{math}
= |-0.924 - 0.383 - 0.924 + 0.383| = | -1.848 | = 2.61
```
which exceeds the classical limit of 2 and confirms the violation of the CHSH inequality.

#### Example Calculation 2: Alternative Angle Choices

Let’s consider a different set of angles to further illustrate the calculation. Here, we set:
- $ \theta_A = 0^\circ $
- $ \theta_{A'} = 90^\circ $
- $ \theta_B = 45^\circ $
- $ \theta_{B'} = 135^\circ $

Now calculate each correlation term.

1. **Calculate $ E(A, B) $:**
   ```{math}
   E(A, B) = -\cos(0^\circ - 45^\circ) = -\cos(45^\circ) = -\frac{\sqrt{2}}{2} \approx -0.707
   ```

2. **Calculate $ E(A, B') $:**
   ```{math}
   E(A, B') = -\cos(0^\circ - 135^\circ) = -\cos(135^\circ) = \frac{\sqrt{2}}{2} \approx 0.707
   ```

3. **Calculate $ E(A', B) $:**
   ```{math}
   E(A', B) = -\cos(90^\circ - 45^\circ) = -\cos(45^\circ) = -\frac{\sqrt{2}}{2} \approx -0.707
   ```

4. **Calculate $ E(A', B') $:**
   ```{math}
   E(A', B') = -\cos(90^\circ - 135^\circ) = -\cos(45^\circ) = -\frac{\sqrt{2}}{2} \approx -0.707
   ```

Now, substitute these values into the CHSH inequality expression:
```{math}
|E(A, B) + E(A, B') + E(A', B) - E(A', B')| \approx |-0.707 + 0.707 - 0.707 - 0.707|
```
```{math}
= |-0.707 + 0.707 - 0.707 - 0.707| = |-1.414| = 2.828
```
which again exceeds the classical limit of 2 and confirms the violation of the CHSH inequality.

## Implications of Bell's Theorem

### Quantum Mechanics vs. Local Realism

Bell’s theorem shows that quantum mechanics cannot be explained by any local hidden variable theory, implying that one (or both) of the following assumptions must be false:
1. **Locality**: Measurement outcomes are not influenced by events occurring outside their light-cone.
2. **Realism**: Physical properties exist with definite values, independent of observation.

Violations of Bell’s inequality strongly suggest that quantum mechanics is inherently non-local or that realism must be reconsidered. This result has profound implications for our understanding of reality, as it implies that quantum systems do not have predetermined properties in the way local hidden variable theories would suggest.

### Experimental Tests of Bell Inequalities

Experiments have consistently shown violations of Bell inequalities, confirming quantum mechanical predictions and ruling out local hidden variable theories. These experiments use entangled photons, electrons, or other particles, with measurements taken at space-like separations to ensure no faster-than-light communication.

#### Example: Alain Aspect’s Experiment

In the 1980s, physicist Alain Aspect conducted pioneering experiments on entangled photons, demonstrating clear violations of Bell’s inequalities. In Aspect's experiment, entangled photon pairs were sent to distant detectors with randomly chosen polarization measurement angles. The correlations between measurement results violated Bell's inequalities, supporting the predictions of quantum mechanics.

## Summary: Bell's Theorem and Quantum Non-Locality

Bell's theorem provides a way to test the foundations of quantum mechanics and its relationship with locality and realism. The CHSH inequality allows for a quantitative test of whether quantum correlations can be explained by local hidden variables.