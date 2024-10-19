# Integral Transforms

We have already introduced the Laplace integral transform and used it in order to solve ordinary differential equations. In this chapter, we will use Laplace and Fourier integral transforms to solve partial differential equations (PDE). The strategy of the integral transform method is to reduce the number of variables in a PDE and to convert it to a simpler PDE or to an ordinary differential equation.

## Laplace Transform

Laplace transforms are a natural method of choice if the problem concerns a process where at least one of the variables can have values from zero to infinity. We will demonstrate the application of integral transforms to solving PDEs using particular examples.

### Example

Consider a semi-infinite tube filled initially with pure water and brought into contact with a salt solution maintained at a fixed concentration. Find the total amount of salt diffused into the tube by the time $ t $ if the diffusion constant is $ k $.

The semi-infinite tube is a one-dimensional system. Therefore, the concentration of salt in the tube $ u $ can be described using two variables only: $ x $ – the distance from the salt container and $ t $ – the duration of the contact. Hence, $ u = u(x, t) $.

The diffusion process is described by the equation:

```{math}
k \frac{\partial^2 u(x,t)}{\partial x^2} = \frac{\partial u(x,t)}{\partial t}
```

and the following conditions:

- $ u(0, t) = u_0 $, i.e., the concentration of the salt solution "at the source" is the same at all times.
- $ u(x, 0) = 0 $, i.e., the tube contained pure water prior to being brought into contact with the salt reservoir at $ t = 0 $.
- $ u(1,t) = 0 $, i.e., salt will never reach the far end of the semi-infinite tube.
- $ u(x,t) $ is finite for all $ x $ and all $ t $.

Our strategy is to convert this PDE into an ODE by eliminating the dependence on one of the variables.

Taking the Laplace transform from both sides with respect to $ t $ gives:

```{math}
\int_0^\infty \frac{\partial^2 u(x,t)}{\partial x^2} e^{-st} dt = \int_0^\infty \frac{\partial u(x,t)}{\partial t} e^{-st} dt
```

Swapping the order of the derivatives and integrals:

```{math}
\frac{\partial^2}{\partial x^2} \left( \int_0^\infty e^{-st} u(x,t) dt \right) = \int_0^\infty \frac{\partial}{\partial t} e^{-st} u(x,t) dt
```

This gives:

```{math}
k \frac{\partial^2 U(x,s)}{\partial x^2} = s U(x,s)
```

where $ U(x,s) $ is the Laplace transform of $ u(x,t) $. Integrating the right-hand side by parts, as done previously:

```{math}
\int_0^\infty u e^{-st} dt = u(x,t) e^{-st} \big|_0^\infty + s \int_0^\infty u(x,t) e^{-st} dt = s U(x,s) - u(x,0)
```

Taking into account the boundary condition $ u(x, 0) = 0 $, becomes:

```{math}
k \frac{\partial^2 U(x,s)}{\partial x^2} = s U(x,s)
```

which is an ordinary differential equation with respect to $ U(x,s) $.

The solution to this equation is given by:

```{math}
U(x, s) = A(s) e^{\sqrt{\frac{s}{k}} x} + B(s) e^{-\sqrt{\frac{s}{k}} x}
```

where $ A(s) $ and $ B(s) $ are, in general, functions of $ s $. Only one of the terms here is physically meaningful in the context of this problem. Indeed, assuming that $ u(1, t) = 0 $, i.e., salt never reaches the far end of the semi-infinite tube, we have:

```{math}
U(x, s) = B(s) e^{-\sqrt{\frac{s}{k}} x}
```

The function $ B(s) $ can be determined from the boundary conditions by calculating the Laplace transform of $ u(0, t) = u_0 $:

```{math}
U(0,s) = \int_0^\infty u_0 e^{-st} dt = u_0 \int_0^\infty e^{-st} dt = \frac{u_0}{s}
```

Hence:

```{math}
B(s) = \frac{u_0}{\sqrt{\frac{k}{s}}}
```

Thus, $ U(x, s) = \frac{u_0}{\sqrt{k}} e^{-\sqrt{\frac{s}{k}} x} $.

Now, to find the total amount of salt diffused into the tube, we need to calculate:

```{math}
w(t) = \int_0^\infty u(x,t) dx
```

However, since the problem requires only $ w(t) $, we do not need to find $ u(x,t) $ explicitly.

To find $ w(t) $, we consider the Laplace transform of $ w(t) $:

```{math}
W(s) = \int_0^\infty w(t) e^{-st} dt = \int_0^\infty \left( \int_0^\infty u(x,t) dx \right) e^{-st} dt
```

The inner integral is the Laplace transform of $ u(x,t) $, and hence:

```{math}
W(s) = \int_0^\infty U(x,s) dx
```

Substituting $ U(x, s) $, the integral can be evaluated:

```{math}
W(s) = \frac{u_0}{\sqrt{k}} \int_0^\infty e^{-\sqrt{\frac{s}{k}} x} dx = \frac{u_0}{\sqrt{k}} \cdot \frac{1}{\sqrt{s}}
```

Thus:

```{math}
W(s) = \frac{u_0}{\sqrt{k s}}
```

Finally, $ w(t) $ can be found by consulting a table of Laplace transforms:

```{math}
w(t) = \frac{u_0 \sqrt{k}}{\sqrt{\pi}} t^{-1/2}
```

### Exercise

A semi-infinite metal bar has an initial temperature $ T = 0 \, \text{K} $ everywhere along the bar. At time $ t = 0 $, one end of the bar is brought into contact with a constant temperature heat reservoir at $ T = 100 \, \text{K} $. Find the temperature distribution along the bar after time $ t $.

## Inverse Laplace Transform

Consider a 2nd-order ODE

```{math}
A y''(t) + B y'(t) + C y(t) = f(t),
```

where the boundary conditions imposed on the function $ y $ are $ y(0) = y'(0) = 0 $, $ t \geq 0 $, and $ A $, $ B $, $ C $ are constant coefficients.

The Laplace transform of this equation gives

```{math}
A p^2 Y(p) + B p Y(p) + C Y(p) = F(p),
```

where $ Y(p) $ is the Laplace transform of $ y(t) $ and $ F(p) $ is the transform of $ f(t) $. From here, we find

```{math}
Y(p) = \frac{F(p)}{A p^2 + B p + C} = \frac{F(p)}{A(p + a)(p + b)},
```

where $ a $ and $ b $ are constants.

We already know the inverse Laplace transform of $ F(p) $ (it is given to us as $ f(t) $) and we can always find the inverse transform of

```{math}
\frac{1}{A(p + a)(p + b)}
```

by inspecting the table of Laplace transforms. Can we find the inverse transform of $ Y(p) $?

More generally, assume that inverse Laplace transforms of $ H(p) $ and $ G(p) $ are known functions $ h(t) $ and $ g(t) $, respectively. How do we find the inverse Laplace transform of $ H(p) G(p) $?

### Convolution

Consider the product $ H(p) G(p) $, where $ H(p) $ and $ G(p) $ are Laplace transforms of $ h(t) $ and $ g(t) $, respectively.

```{math}
H(p) G(p) = \int_0^\infty h(s) e^{-ps} ds \int_0^\infty g(t) e^{-pt} dt = \int_0^\infty \int_0^\infty h(s) g(t) e^{-p(s + t)} ds dt.
```

Introduce a new variable $ r = s + t $ for any fixed $ t $. Then, $ s = r - t $ and $ ds = dr $. To define the limits of integration with respect to $ dr $, we notice that $ r = t $ if $ s = 0 $ and $ r = \infty $ if $ s = \infty $. Therefore,

```{math}
H(p) G(p) = \int_0^\infty \left( \int_t^\infty h(r - t) g(t) e^{-pr} dr \right) dt.
```

The diagram below shows schematically the order of integration in this equation: each horizontal line corresponds to the inner integration from $ r = t $ to $ r = \infty $; all lines together cover one half of the first quadrilateral, which corresponds to the outer integral for $ 0 \leq t < \infty $.

![Convolution Integration](convolution_integration.png)

(a) Inner integral (over $ r $): $ t \leq r < 1 $, outer integral (over $ t $): $ 0 \leq t < 1 $;  
(b) Inner integral (over $ t $): $ 0 \leq t < r $, outer integral (over $ r $): $ 0 \leq r < 1 $.


We can change the order of integration with respect to $ t $ and $ r $ in the equation, as illustrated in Fig. 6.1(b), so as

```{math}
H(p) G(p) = \int_0^\infty \left( \int_0^r g(r - t) h(t) e^{-pr} dt \right) dr.
```

This inner integral is called the convolution of functions $ g(x) $ and $ h(x) $. (Do not confuse the symbol $ \ast $ indicating the convolution operation with that indicating the multiplication operation.)

Thus, Equation (6.5) can be written as

```{math}
H(p) G(p) = \int_0^\infty [h \ast g] e^{-pr} dr,
```

i.e., the Laplace transform of a convolution of functions $ h(x) $ and $ g(x) $ equals the product of the Laplace transforms of these functions. In other words, $ g \ast h $ is the inverse Laplace transform of $ H(p) G(p) $.

---

### Example

Find the solution of the equation

```{math}
y'' + 3y' + 2y = e^{-t} \quad \text{with} \quad y(0) = y'(0) = 0
```

using the convolution method. After Laplace transform:

```{math}
p^2 Y(p) + 3p Y(p) + 2 Y(p) = \mathcal{L}(e^{-t}),
```

which gives

```{math}
Y(p) = \frac{1}{(p^2 + 3p + 2)} = \frac{1}{(p+1)(p+2)}.
```

The inverse Laplace transform of $ L(e^{-t}) $ is $ e^{-t} $. Therefore,

```{math}
Y(p) = \mathcal{L}(e^{-t} - e^{-2t}).
```

To find $ y(t) $, we need to calculate the convolution of $ e^{-t} - e^{-2t} $ and $ e^{-t} $:

```{math}
y(t) = \int_0^t \left[ e^{-t} - e^{-2t} \right] e^{-(t - \tau)} d\tau.
```

This simplifies to:

```{math}
y(t) = t e^{-t} + e^{-2t} - e^{-t}.
```

## Convolution theorem.

Let us consider two functions $ f(x) $ and $ g(x) $. Their Fourier transforms can be defined as

```{math}
F(k) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{+\infty} f(x)e^{-ikx} dx
```

and

```{math}
G(k) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{+\infty} g(x)e^{-ikx} dx.
```

Note that other definitions of the Fourier transform may use a different factor in front of the integral.

Is it possible to give meaning to the product $ F(k)G(k) $? Rewrite $ F(k)G(k) $ as:

For any fixed $ t $, we can introduce a new variable $ p = s+t $. Then, $ s = p - t $ and $ ds = dp $. Rewrite the integral in terms of variables $ p $ and $ t $. Note that the integration limits remain unchanged:

```{math}
F(k)G(k) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(p-t)g(t) e^{-ikp} dp dt.
```

Change the order of integration with respect to $ dt $ and $ dp $ and multiply both parts of the equation by $ p^{2\pi} $:

```{math}
\frac{1}{2\pi} F(k)G(k) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(p-t) g(t) e^{-ikp} dp dt.
```

The integral in square parenthesis is called the convolution (note that the integration limits are different from those defined for the case of the Laplace transform):

```{math}
\int_{-\infty}^{+\infty} f(p-t)g(t) dt.
```

Thus the equation states that the product of the Fourier transforms of functions $ f(x) $ and $ g(x) $ is proportional to the Fourier transform of a convolution of these functions. This statement is called the **convolution theorem**.

### Exercise
Demonstrate that

```{math}
\int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(p-t)g(t) dt = \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(t-p)g(t) dt.
```

## Temperature distribution in an infinite bar

An infinite metal bar has the initial temperature distribution along the bar $ f(x) $. Find the temperature distribution after time $ t $.

Let $ u(x,t) $ be the temperature at a point $ x $ along the bar at the time $ t $. Assume that the far ends of the bar remain cold, i.e.

```{math}
u(\pm 1, t) = \frac{\partial u(x, t)}{\partial x} \Big|_{x=\pm 1} = 0.
```

The temperature along the bar is described by the heat flow equation

```{math}
\frac{\partial^2 u}{\partial x^2} = \frac{\partial u}{\partial t}.
```

Natural boundary conditions for this problem are:
- The far ends of the bar remain cold: $ u(x,t) \to 0 $ for $ x \to \pm 1 $.
- The temperature does not change at the ends of the bar: $ \frac{\partial u(x, t)}{\partial x} \to 0 $ for $ x \to \pm 1 $.

Apply the Fourier transform to both parts of the equation:

```{math}
\frac{1}{2\pi} \int_{-\infty}^{+\infty} \frac{\partial^2 u}{\partial x^2} e^{-ikx} dx = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \frac{\partial u}{\partial t} e^{-ikx} dx.
```

The LHS can be integrated by parts:

```{math}
\int_{-\infty}^{+\infty} \frac{\partial^2 u}{\partial x^2} e^{-ikx} dx = -k^2 \int_{-\infty}^{+\infty} u(x,t) e^{-ikx} dx,
```

while in the RHS, $ \frac{\partial}{\partial t} $ can be moved outside of the integration. Thus, the PDE is transformed into:

```{math}
-k^2 U(k,t) = \frac{\partial U(k,t)}{\partial t}.
```

The latter equation has a solution of the form:

```{math}
U(k,t) = U(k,0) e^{-k^2 \alpha t}.
```

Function $ U(k,0) $ is defined from the initial condition at the time $ t = 0 $:

```{math}
U(k,0) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} u(x,0) e^{-ikx} dx = F(k),
```

i.e. $ U(k,0) $ is given by the Fourier transform of the function $ f(x) $.

Thus,

```{math}
U(k,t) = 2\pi F(k) G(k,t),
```

where we introduced the function $ G(k,t) $ defined as:

```{math}
G(k,t) = e^{-k^2 \alpha t}.
```

Function $ G(k,t) $ can be considered as a Fourier transform of some function $ g(x,t) $. Since $ U(k,t) $ is represented as a product of two Fourier transforms, we can apply the convolution theorem to find $ u(x,t) $:

```{math}
u(x,t) = \int_{-\infty}^{+\infty} g(x-s,t) f(s) ds.
```

In other words, the problem will be solved if we find function $ g(x,t) $ explicitly. Function $ g(x,t) $ can be found by the inverse Fourier transform of $ G(k,t) $:

```{math}
g(x,t) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{-k^2 \alpha t} e^{ikx} dk.
```

To take this integral, first complete the square:

```{math}
g(x,t) = \frac{1}{\sqrt{4\pi \alpha t}} \int_{-\infty}^{+\infty} e^{-\frac{(k-ix)^2}{4\alpha t}} dk.
```

Now, using the fact that:

```{math}
\int_{-\infty}^{+\infty} e^{-a s^2} ds = \sqrt{\frac{\pi}{a}},
```

we obtain:

```{math}
g(x,t) = \frac{1}{\sqrt{4\pi \alpha t}} e^{-\frac{x^2}{4\alpha t}}.
```

Finally, the temperature distribution at time $ t $ can be calculated, using function $ g(x,t) $ and the initial temperature distribution $ f(x) $.
