# Trigonometry

## The Basics
Trigonometry is the study of triangles, lengths, and angles. Typically, we use trigonometry to examine right-angled triangles, where Pythagoras's theorem applies:  
```{math} 
a^2 + b^2 = c^2 
```

![Right-Angled Triangle](RightAngledTriangle.png)

We can label the sides opposite and adjacent to angle $ \theta $ and define the three basic trigonometric functions:

![Triangle](TriangleAdjOppHyp3.png)

If we look at Pythagoras's theorem again:
```{math} 
\text{opposite}^2 + \text{adjacent}^2 = \text{hypotenuse}^2 \Rightarrow \frac{\text{opposite}^2}{\text{hypotenuse}^2} + \frac{\text{adjacent}^2}{\text{hypotenuse}^2} = 1 
``` 
```{math}
\Rightarrow \sin^2(\theta) + \cos^2(\theta) = 1
```
which is a very useful relation between $ \sin $ and $ \cos $. We can also define reciprocal functions for each of the trigonometric functions:
```{math}
\sin(\theta) \Rightarrow \text{cosec}(\theta) = \frac{1}{\sin(\theta)}
```
```{math}
\cos(\theta) \Rightarrow \sec(\theta) = \frac{1}{\cos(\theta)}
```
```{math}
\tan(\theta) \Rightarrow \cot(\theta) = \frac{1}{\tan(\theta)}
```

There are some angles which produce special results:

![Special Angles](sin30sin45sin60.png)

It is also common to write angles in **Radians** instead of **Degrees**, and we can convert between them using:
```{math}
\text{Radians} = \text{Degrees} \times \frac{2\pi}{360} \Longleftrightarrow \text{Degrees} = \text{Radians} \times \frac{360}{2\pi}
```

Using radians is quite common in mathematics, so we will use them throughout from now on. We can extend these trigonometric definitions from triangles to circles, and plot graphs over the range $ 0 \leq \theta < 2 \pi $:

![Trig Circles](TrigCircles.png)
![Sine and Cosine](SineCosine.png)

Notice that since $ \sin(\theta) < 0, \, \pi < \theta < 2\pi $ and $ \cos(\theta) < 0, \, \frac{\pi}{2} < \theta < \frac{3\pi}{2} $, the circle can be broken up into quadrants with different behaviors:

![Four Quadrants](Four-quadrants-circle.jpg)

Using trigonometry, we can find some interesting identities. Start with a triangle and draw a right-angled bisector from apex $B$ down to side $b$:

![Any Triangle](AnyTriangle.png)

## Trigonometric Rules
### Sine Area Rule 
Since Area $= \frac{1}{2}bh$, using trigonometry:

```{math}
\sin(C) = \frac{h}{a} \Rightarrow h = a \sin(C)
```

and hence for *any* triangle:

```{math}
\text{Area} = \frac{1}{2}a\,b\,\sin(C)
```

which we can extend to any two sides of a triangle and the angle between them:

```{math}
\text{Area} = \frac{1}{2}a\,b\,\sin(C) = \frac{1}{2}a\,c\,\sin(B) = \frac{1}{2}b\,c\,\sin(A)
```

### Sine Rule
Using trigonometry:

```{math}
\sin(A) &= \frac{h}{c} \Rightarrow h = c \sin(A) \\
\sin(C) &= \frac{h}{a} \Rightarrow h = a \sin(C) \Rightarrow \frac{\sin(A)}{a} = \frac{\sin(C)}{c}
```

We could equally bisect the line $a$ at right angles from apex $A$, and find that:

```{math}
\frac{\sin(A)}{a} = \frac{\sin(C)}{c}
```

which means for *any* triangle:

```{math}
\frac{\sin(A)}{a} =  \frac{\sin(B)}{b}= \frac{\sin(C)}{c}
```

### Cosine Rule 
Performing Pythagoras's theorem on the sides opposite to $h$:

```{math}
a^2 &= h^2 + (b_2)^2 \\
c^2 &= h^2 - (b_1)^2 \Rightarrow (b_1)^2 = c^2 - h^2
```

Looking at the side $b$, which is broken up into $b_1, b_2$:

```{math}
b = b_1 + b_2 \Rightarrow b_2 = b - b_1
```

and now putting these together:

```{math}
a^2 &= h^2 + (b_2)^2 = h^2 + b^2 - 2bb_1 + (b_1)^2 \\
a^2 &= b^2 + c^2 -2bb_1
```

Using trigonometry on the side $b_1$:

```{math}
\cos(A) &= \frac{b_1}{c} \Rightarrow b_1 = c \cos(A) \\
\Rightarrow a^2 &= b^2 + c^2 - 2bc\cos(A)
```

This reduces to Pythagoras's theorem for $A = \frac{\pi}{2}$, but holds true for *any* triangle. We can also write different versions based on the angles involved:

```{math}
a^2 &= b^2 + c^2 - 2bc\cos(A) \\
b^2 &= a^2 + c^2 - 2ac\cos(B) \\
c^2 &= a^2 + b^2 - 2ab\cos(C)
```

These are useful formulae for calculating a triangle's angles when we know all the side lengths, OR to find a third side if we know one angle and two lengths of a triangle.

## Trigonometric Identities
Using our trigonometric definitions, we can start to develop more complicated identities. Two of the most useful are the compound angle identities for $ \sin(\theta) $ and $ \cos(\theta) $, which can be proven geometrically:

![Angle Addition Diagram for Sine](AngleAdditionDiagramSine.png)

where we have used the odd function properties of $ \sin(\theta) $ and even function properties of $ \cos(\theta) $ in the final set of identities. Equally, for $ \tan(\theta) $, we find:

```{math}
\tan(\alpha \pm \beta) = \frac{\sin(\alpha \pm \beta)}{\cos(\alpha \pm \beta)} = \frac{\sin(\alpha)\cos(\beta) \pm \cos(\alpha)\sin(\beta)}{\cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta)} = \frac{\tan(\alpha) \pm \tan(\beta)}{1 \mp \tan(\alpha)\tan(\beta)}
```

### Double Angle Identities
Using these identities, for the case of double angles:

```{math}
\sin(2\theta) &= 2 \sin(\theta)\,\cos(\theta) \\
\cos(2\theta) &= 2 \cos^2(\theta) - \sin^2(\theta)
&= 2 \cos^2(\theta) - 1 \\
&= 1 - 2\sin^2(\theta)
```

where for these last two identities we have made use of the trigonometric version of Pythagoras's theorem, $ \cos^2(\theta) + \sin^2(\theta) = 1 $. Likewise for $ \tan(\theta) $:

```{math}
\tan(2\theta) = \frac{2 \tan(\theta)}{1 - \tan^2(\theta)}
```

## Inverse Trigonometric Functions
As well as knowing the trigonometric functions and their reciprocal functions, it is possible to define their inverse functions. To ensure that we have 1-to-1 mappings, we need to restrict the domain of the functions before finding the inverse, which means there can be different co-domains for each function:

```{math}
\begin{array}{clccc}
\sin(x), & x \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right] & \Rightarrow & \arcsin(x), & x \in \left[-1,1\right] \\
\cos(x), & x \in \left[0,\pi\right] & \Rightarrow & \arccos(x), & x \in \left[-1,1\right] \\
\tan(x), & x \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right] & \Rightarrow & \arctan(x), & x \in \left(-\infty,\infty\right)
\end{array}
```

We can visualize all of these graphically:

![Inverse Trigonometric Functions](ArcSinCos3.png)

We notice that for $ \tan(x),\, \arctan(x) $, the function asymptotes to positive/negative infinity, whereas $ \sin(x), \,\cos(x) $, etc., are all in closed intervals.

## Hyperbolic Functions*
Recall that there are both **odd** and **even** functions which satisfy:

```{math}
\begin{array}{lcl}
f(-x) = -f(x) & \text{(odd)} \\
f(-x) = f(x) & \text{(even)}
\end{array}
```

We do also know functions which fit into neither of these categories, such as the exponential function $ f(x) = e^x $.

We can define the **Hyperbolic** functions:

![Hyperbolic Functions](Sinh_cosh_tanh2.png)

From the definitions, we find the following useful relation:

```{math}
\cosh^2(\theta) - \sinh^2(\theta) \equiv 1
```

Likewise, it is possible to construct reciprocal functions:

![Reciprocal Functions](Csch_sech_coth2.png)

Which allow us to construct further useful relations:

```{math}
1 - \tanh^2(\theta) \equiv \text{sech}^2(\theta) \quad \text{and} \quad \text{coth}^2(\theta) - 1 \equiv \text{cosech}^2(\theta)
```
