# Energy in an Electric Field
We can see that if we have charges that are free to move in space and some are at rest, the presence of a moving 
charge or uniform electric field will cause a force to act on these free charges to move, pick up kinetic energy 
and have non-zero momentum.  Therefore an electric field carries <b>Electric Potential Energy</b>.  The work done 
$\mathrm{d} W$ on a charge $Q$ in the presence of an electric field $\bf E$ moving a distance $\bf \mathrm{\bf d} r$ in the 
field would be given by:
```{math}
\mathrm{d} W = Q\,\mathbf{E}\,\cdot \mathrm{d} \mathbf{r}
```
and therefore the change in electric potential energy $\mathrm{d} U$ is found to be:
```{math}
:label: elecpotenergy
\mathrm{d} U = - Q\,\mathbf{E}\,\cdot \mathrm{d} \mathbf{r} \Rightarrow U = -\int_{\mathcal{C}} Q\,\mathbf{E}\,\cdot \mathrm{d} \mathbf{r}
```
For a point charge $Q$, centered on the origin, producing an electric field, then a charge moving in from $r \rightarrow \infty$ 
up to a distance $r_0$, the potential energy is:
```{math}
U = -\,\frac{Q\,Q_s}{4\pi\,\epsilon_0}\int_{\infty}^{r_0} \frac{\mathbf{e_r}}{r^2}\,\cdot \mathrm{d} \mathbf{r} = 
\frac{Q\,Q_s}{4\pi\,\epsilon_0}\frac{1}{r_0}
```
This gives rise to the idea of <b> Electric Potential </b> $\phi$,
```{math}
:label: EFieldpotential
\phi({\bf r}) = -\int_c {\bf E} \cdot \mathrm{\bf d} \mathbf{r}
```
Here $\phi$ is amount of energy per unit charge given to $Q$ when moving on some path $C$ through an electric field from a point with 
zero potential to position $\bf r$.  As the Helmholtz decomposition theorem in Equation {eq}`HelmholtzDecomp` shows, $\bf E$ would
in general have divergence and curl components, however if $\bf E$ is curl free, then we can write:
```{math}
:label: Efieldgradpotential
{\bf E} = -\nabla \phi 
```
We can also see that $\phi$ is related to the potential energy $U$, 
```{math}
U = Q\,\phi
``` 
For a point charge $Q_S$ producing an electric field, the electrical potential is given by:
```{math}
\phi = -\frac{Q_S}{4\pi\,\epsilon_0}\int_{\infty}^{r_0}\frac{\mathbf{e_r}}{r^2}\cdot\mathrm{d}\mathbf{r} 
= -\frac{Q_S}{4\pi\,\epsilon_0}\int_{\infty}^{r}\frac{\mathrm{d}r}{r^2} = \frac{Q_S}{4\pi\,\epsilon_0}\frac{1}{r_0}
```
The term <b>Potential Difference</b> is given to the difference between the electric potentials $\Delta \phi$ between 
two points $({\bf r_1,\, r_2} )$ in an electrostatic system:
```{math}
\Delta \phi = {\phi}_2 - {\phi}_1 &= -\int_{\infty}^{r_2} {\bf E} \cdot \mathrm{d} \mathbf{r} - 
\left (- \int_{\infty}^{r_1} {\bf E} \cdot \mathrm{d} \mathbf{r}\right) 
= \int_{r_2}^{\infty} {\bf E} \cdot \mathrm{d} \mathbf{r}+ \int_{\infty}^{r_1} {\bf E} \cdot \mathrm{d} \mathbf{r}\\ 
&= \int_{r_2}^{r_1} {\bf E} \cdot \mathrm{d} \mathbf{r}= -\int_{r_1}^{r_2} {\bf E} \cdot \mathrm{d} \mathbf{r}
```
Suppose we have a system of two charges, how does $U$ change?  $Q_1$ and $Q_2$ will each produce an 
electrostatic field which a test charge $Q$ coming in from $r \rightarrow \infty$ will feel and therefore $U$ has the form:
```{math}
U = \frac{Q}{4 \pi\,\epsilon_0}\left(\frac{Q_1}{r_1} + \frac{Q_2}{r_2}\right)
```
where $r_1,\, r_2$ are the distances between the charges $Q_1,\, Q_2$ and the test charge.  We can generalise this for $N$ point charges 
$Q_1, \,Q_2, \, \dots,\, Q_N$:
```{math}
U = \frac{Q}{4 \pi\,\epsilon_0}\left(\frac{Q_1}{r_1} + \frac{Q_2}{r_2} + \dots + \frac{Q_N}{r_N}\right) = 
\frac{Q}{4 \pi\,\epsilon_0}\,\sum_{i=1}^N \frac{Q_i}{r_i}
```
We should notice however that this is the potential energy that is a result of a charge $Q$ being introduced into the system, 
but clearly if there two or more charges already in the system, they too possess electric potential energies because there are 
also pairs of charges mutually interacting:
```{math}
U = \frac{1}{4\pi\,\epsilon_0}\frac{Q_1\,Q_2}{|r_1-r_2|}
```
We can also think about this in terms of potentials, e.g. $\phi({\bf r_1})$ is as a result of charge $Q_1({\bf r_1})$, therefore here:
```{math} 
U = \frac{1}{2}\bigg[Q_2\,{\phi}_1(r_2) + Q_1\,{\phi}_2(r_1)\bigg] 
```
where the $1/2$ factor is to avoid the over counting of the interaction field $Q_1 \rightarrow Q_2$ and $Q_2 \rightarrow Q_1$.  These 
expressions can be generalised for $N$ point charges:
```{math}
:label: intrinsicelecpotenergy
U &= \,\frac{1}{2}\sum_{i=1}^N Q_i\,{\phi}({\bf r}_i)  \\ 
&=  \,\frac{1}{2}\left(\frac{1}{4\pi\,\epsilon_0}\right)\sum_{i=1}^N Q_i\, \sum_{j=1}^{N(j \neq i)} \frac{Q_j}{|r_i-r_j|}
```
