# Cartesian Tensors

## Definitions

Physical properties are described using one or several independent variables. For example, volume $ V $ of a cake (see figure below a) is described using only one variable. Such properties are called **scalars**. Three independent variables are needed to describe the velocity of the champagne cork (see figure below b). Such properties are called **vectors**. We can use $ v $ or $ (v_x, v_y, v_z) $ or $ x_1, x_2, x_3 $ to represent the vector of velocity.

How many independent variables are needed to describe the response of a solid to external stress? This property should reflect the direction and magnitude of the force applied to each point, and the direction and magnitude of the displacement of each point. Hence, nine independent variables are needed. Thus, in general, physical properties are described using $ N $ independent variables.

In this chapter, we will consider how representation of these properties changes upon transformation from one coordinate system to another. We will consider real variables only and focus on three-dimensional Euclidean space. Some of the definitions will be given for $ N $-dimensional space.


```{figure} tensors_fig1.png
---
name: fig:tensors_fig1
---
Examples of (a) *scalar* - volume of a cake; (b) *vector* - velocity of a champaign cork; (c) relation between directions of forces and displacements of each point in a solid; (d) metric of Minkowski space.
```


### N-dimensional space

Consider a set of $ N $ real independent variables $ x_1, x_2, \dots, x_i, \dots, x_N $. These values will be called coordinates of a point. All the points corresponding to all the possible values of the coordinates form the **N-dimensional space**. This space will be denoted as $ V_N $.

Note the difference between a coordinate system defined by $ x_1, x_2, \dots, x_i, \dots, x_N $ and a point given by a specific realization of the coordinates $ x_1, x_2, \dots, x_i, \dots, x_N $.

---

### Curves in N-dimensional space

If there are $ N $ equations:
```{math}
x_i = f_i(u), \quad (i = 1, 2, \dots, N)
```
and $ u $ is a parameter and $ f_i(u) $ are functions of $ u $, the collection of points which satisfy these equations defines a curve in $ V_N $.

---

### Subspace in N-dimensional space

In general, if there are $ N $ equations

```{math}
x_i = f_i(u_1, u_2, \dots, u_M), \quad \text{where} \, i = 1, 2, \dots, N \, \text{and} \, M < N
```

where $ u_1, u_2, \dots, u_M $ are parameters and $ f_i(u_1, \dots, u_M) $ are functions of these parameters, the collection of all points which satisfy these equations defines an $ M $-dimensional *subspace* $ V_M $ in $ V_N $. If $ M = N - 1 $, the subspace $ V_M $ is called a *hypersurface* of $ V_N $.

---

### Kronecker delta ($ \delta $) symbol

We can define the Kronecker delta symbol through:

```{math}
\delta_{ij} = 
\begin{cases}
1 & \text{if} \, i = j \\
0 & \text{if} \, i \neq j
\end{cases}
```

In matrix language, this is nothing more than the identity matrix!

---

### Summation convention

In order to simplify equations, we will use two conventions regarding the indices.

1. Indices will take *all values* from 1 to $ N $, unless otherwise stated explicitly.
2. If an index appears *twice* in any single term, a summation with respect to this index is implied. The summation goes over the range from 1 to $ N $ (convention 1).

For example, in 3D space ($ N = 3 $):

```{math}
a_i x_i &= a_1 x_1 + a_2 x_2 + a_3 x_3 \\
a_{ij} b_{jk} &= a_{i1} b_{1k} + a_{i2} b_{2k} + a_{i3} b_{3k} \quad \text{(the sum depends on $ i $ and $ k $)}\\
a_{ij}\,b_{jk}\,C_{kan} &= \sum_{j=1}^3\,\sum_{k=1}^3 a_{ij}\,b_{jk}\,C_{kmn} \quad \text{(the sum depends on $ i, m $ and $ n $)} \\
\frac{\partial^2 \phi}{\partial x_i^2} &= \frac{\partial^2 \phi}{\partial x_1^2} + \frac{\partial^2 \phi}{\partial x_2^2} + \frac{\partial^2 \phi}{\partial x_3^2}
```

Similarly, in $ N $-dimensional space:

```{math}
\sum_{i=1}^{N} a_i x_i + \sum_{j=1}^{N} b_j x_j = a_i x_i + b_j x_j
```

Note that no summation is implied in
```{math} 
a_i + x_i + b_j + x_j. 
```
The summation index is called a *dummy index*; it can be replaced by any other index as long as it does not conflict with other indices used in equations. For example, if $ \bar{x}_i $ is defined by the function $ \phi_i $ as

```{math} 
\bar{x}_i = \phi_i(x_1, x_2, \dots, x_N), 
```

then the differential of $ \bar{x}_i $ can be written as

```{math}
d\bar{x}_i = \sum_{j=1}^{N} \frac{\partial \phi_i}{\partial x_j} \mathrm{d}x_j = \frac{\partial \phi_i}{\partial x_j} \mathrm{d}x_j = \frac{\partial \phi_i}{\partial x_r} \mathrm{d}x_r.
```

In order to avoid confusion, the same index should not be used more than twice in one term. For example,

```{math}
\frac{d\bar{x}_j}{\partial x_i} = \frac{\partial \phi_j}{\partial x_i} \quad \text{but not} \quad \frac{d\bar{x}_j}{\partial x_j}.
```
and
```{math}
\left( \sum_{i=1}^N a_i\,x_i\right)^2 = (a_x\,x_i)^2 = (a_i\,x_i)(a_j\,x_j) = a_i\,a_j\,x_i\,x_j \quad \text{but not} \quad a_i\,x_i\,a_i\,x_i
```

To demonstrate the effect of the Kronecker symbol:

```{math}
b_j\,\delta_{ij} &= b_i \\
a_{ij}\,\delta_{jk} &= a_{ik} \\
a_{ij}\,b_{jk}\,\delta_{kl} &= a_{ki}\,b_{ji} = a_{kj}\,b_{jk}

```

*Exercise:* Show that

```{math}
\delta_{ij} \delta_{jk} &= \delta_{ik}\\
\delta_{ii} &= N
```

---

## Change of Basis

### Transformation of coordinates in 3-dimensional space

Let us introduce a set of independent basis vectors in a 3D space: $ \mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3 $. Then, any vector $ x $ can be represented as

```{math}
x = x_1 \mathbf{e}_1 + x_2 \mathbf{e}_2 + x_3 \mathbf{e}_3 = x_k \mathbf{e}_k,
```

where $ x_1, x_2, x_3 $ are called components of the vector $ x $. Consider a new basis set $ e'_1, e'_2, e'_3 $ related to the old one by:

```{math}
\mathbf{e}'_1 &= S_{11} \mathbf{e}_1 + S_{21} \mathbf{e}_2 + S_{31} \mathbf{e}_3 = S_{k1} \mathbf{e}_k\\
\mathbf{e}'_2 &= S_{12} \mathbf{e}_1 + S_{22} \mathbf{e}_2 + S_{32} \mathbf{e}_3 = S_{k2} \mathbf{e}_k\\
\mathbf{e}'_3 &= S_{13} \mathbf{e}_1 + S_{23} \mathbf{e}_2 + S_{33} \mathbf{e}_3 = S_{k3} \mathbf{e}_k
```
or
```{math}
\mathbf{e}_j' = S_{jk}\,\mathbf{e}_k
``` 
where $ S_{ij} $ are elements of a matrix $ S $. In the new basis set, vector $ \mathbf{x} $ can be written as:

```{math}
\mathbf{x} = x'_1 \mathbf{e}'_1 + x'_2 \mathbf{e}'_2 + x'_3 \mathbf{e}'_3 = x'_k \mathbf{e}'_k.
```

Substituting the expressions for $ e'_1, e'_2, e'_3 $ into this equation gives:

```{math}
\mathbf{x} = x'_1 (S_{k1} \mathbf{e}_k) + x'_2 (S_{k2} \mathbf{e}_k) + x'_3 (S_{k3} \mathbf{e}_k)
= x'_j (S_{kj} \mathbf{e}_k).
```

Substitution of the expressions for $ \mathbf{e}_{1}, \mathbf{e}_{2}, \mathbf{e}_{3} $ into this equation gives:

```{math}
\mathbf{x} &= x'_{1} (S_{11} \mathbf{e}_1 + S_{21} \mathbf{e}_2 + S_{31} \mathbf{e}_3) \\
&+ x'_{2} (S_{12} \mathbf{e}_1 + S_{22} \mathbf{e}_2 + S_{32} \mathbf{e}_3) \\
&+ x'_{3} (S_{13} \mathbf{e}_1 + S_{23} \mathbf{e}_2 + S_{33} \mathbf{e}_3) \\
&= x'_{1} (S_{k1} \mathbf{e}_k) + x'_{2} (S_{k2} \mathbf{e}_k) + x'_{3} (S_{k3} \mathbf{e}_k) \\
&= x'_{j} (S_{k_j} \mathbf{e}_k).
```


Hence, the components of the vector $ x $ in the old and new basis sets are related as

```{math}
x_1 &= S_{11} x'_{1} + S_{12} x'_{2} + S_{13} x'_{3} = S_{1k} x'_{k}\\
x_2 &= S_{21} x'_{1} + S_{22} x'_{2} + S_{23} x'_{3} = S_{2k} x'_{k}\\
x_3 &= S_{31} x'_{1} + S_{32} x'_{2} + S_{33} x'_{3} = S_{3k} x'_{k}
```
Or
```{math}
x_i = S_{ik}\,x'_{k}
```
i.e. $x_i$ are *functions* of $x'_i$ and components of the transformation matrix $ S $ are given by:

```{math}
S_{ik} = \frac{\partial x_i}{\partial x'_k}
```

The system of equations $x_i = S_{ij} x_{0j}$ can be resolved with respect to $ x'_{I} $ if $ \det(S) \neq 0 $. In this case, it is possible to define the inverse of the matrix $ S $, which transforms components of $ \mathbf{x} $ from the old basis to the new one:

```{math}
x'_{I} = (S^{-1})_{ij} x_j.
```

### Rotation 

If the transformation defined by the matrix $ S $ is a *rotation*, i.e., $ S $ is orthogonal ($ S^{-1} = S^T $), then

```{math}
x'_{I} = (S^T)_{ij} x_j = S_{ji} x_j.
```


---

### Transformation of coordinates in N-dimensional space

Consider a space $ V_N $ and a coordinate system $ x_1, x_2, \dots, x_N $. If there are $ N $ equations

```{math}
x'_i = \phi_i(x_1, x_2, \dots, x_N) \quad (i = 1, 2, \dots, N),
```

where $ \phi_i $ are independent single-valued continuous and differentiable functions of coordinates, these equations define the *transformation* of coordinate system $ x_1, x_2, \dots, x_N $ into a new coordinate system $ x'_1, x'_2, \dots, x'_N $.

A necessary and sufficient condition for the independence of the functions $ \phi_i $ is that the determinant of the $ N \times N $ matrix formed by the derivatives

```{math}
\frac{\partial x'_i}{\partial x_j} = \frac{\partial \phi_i(x_1, \dots, x_N)}{\partial x_j} \quad (i, j \in 1, \dots, N),
```

denoted as $ S $, is not equal to zero:

```{math}
\det([S_{ji}]) = \det \left( \frac{\partial \phi_i(x_1, \dots, x_N)}{\partial x_j} \right) \neq 0.
```

Under this condition, the above equations can be solved with respect to $ x_i $, i.e., one can find functions $ \psi_i $ which express old coordinates $ x_i $ in terms of new coordinates $ x'_j $:

```{math}
x_i = \psi_i(x'_1, x'_2, \dots, x'_N) \quad (i = 1, 2, \dots, N).
```

## Rotations of Cartesian coordinate systems

Lets investigate how components of a vector are changed by a rotation of the Cartesian coordinate system. For convenience, introduce transformation matrix $ L = S^{-1} $, where matrix $ S $ defines the rotation of the basis set vectors. Then,

```{math}
x'_{i} &= L_{ij} x_{j}\\
x_{i} &= L_{ij} x'_{j}
```

Orthogonality of $ L $ means that

```{math}
L_{ik} L_{jk} &= \delta_{ij} \quad \text{(orthogonality of rows)}\\
L_{ki} L_{kj} &= \delta_{ij}  \quad \text{(orthogonality of columns)}
```

(In the following we always assume that matrix $ L $ is orthogonal.)

Since we defined new basis $ e'_j $ ($ j = 1, 2, 3 $) as

```{math}
e'_j = S_{ij} \mathbf{e}_i = (L^{-1})_{ij} \mathbf{e}_i,
```

For orthonormal vectors $ \mathbf{e}_k $ ($ k = 1, 2, 3 $) and rotation $ L $:

```{math}
\mathbf{e}_k \cdot e'_j = S_{ij} \mathbf{e}_k \cdot \mathbf{e}_i = S_{ij} \delta_{ki} = S_{kj} = (L^{-1})_{kj} = (L^{T})_{kj} = L_{jk},
```

i.e., elements of the transformation matrix $ L $ are *defined* by the scalar products of the old and new basis vectors.

*Exercise:* Show that the transformation matrix $ L $ for a rotation of the coordinate system by an angle $ \theta $ about the $ \mathbf{e}_3 $ axis is

```{math}
L = 
\begin{pmatrix}
\cos \theta & \sin \theta & 0 \\
-\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{pmatrix}
```


```{figure} tensors_fig2.png
---
name: fig:tensors_fig2
---
Rotation of Cartesian axes by an angle $ \alpha $ about the $ x_3 $ axis. Note that the rotation of the axes changes components of the vector $ x $ but not the vector itself.
```

*Exercise:* Show that two consecutive rotations of the coordinate system by an angle $ \theta $ about the $ \mathbf{e}_3 $ axis is also a rotation with the value of the rotation angle of $ 2\theta $.

In general, the product of two rotations is also a rotation, i.e., if

```{math}
x'_{i} = L_{ij} x_{j}
```

and 

```{math}
x''_{i} = M_{ij} x'_{j},
```
then

```{math}
x''_i = M_{ij} x'_j = M_{ij} (L_{jk} x_k) = (M_{ik} L_{jk}) x_k = (ML)_{ik} x_k.
```

---

### Transformation of vectors

Consider a set of quantities $ v_i $ ($ i = 1, \dots, N; N = 3 $), which are *functions* of coordinates $ x_j $ ($ j = 1, \dots, N; N = 3 $), i.e.,

```{math}
v_i = v_i(x_1, x_2, x_3),
```

and investigate how their values are changed by a rotation of the Cartesian axes. We already know that coordinates transform as

```{math}
x'_{i} = L_{ij} x_{j}.
```

If a set of new quantities $ v'^{i} $ can be obtained from the set of $ v_i $ by the same transformation:

```{math}
v'_{i} = L_{ij} v_{j},
```

then $ v_i $ form the components of a vector or *$1^{st}$-order Cartesian tensor*. According to this definition:

```{math}
v'_k e'_k = (L_{kj} v_j)(S_{nk} \mathbf{e}_n) = (S_{nk} L_{kj}) v_j \mathbf{e}_n = S_{nk}(S^{-1})_{kj} v_j \mathbf{e}_n = \delta_{nj} v_j \mathbf{e}_n = v_n \mathbf{e}_n,
```

i.e.,

```{math}
\mathbf{v} = v_i \mathbf{e}_i = v'_j \mathbf{e}'_j.
```

---

Review:

1. N-dimensional space: variables $ x_1, x_2, \dots, x_N $ ($ x_i \in \mathbb{R} $).
2. The summation convention: $ a_i b_i = a_i b_i $.
3. Basis set $ \mathbf{e}_i $, rotation of the coordinate system: $ e'_j = S_{ij} \mathbf{e}_i $ and the corresponding transformation of coordinates $ x'_i = (S^{-1})_{ij} x_j $.
4. 1st-order Cartesian tensors $ v = (v_1, v_2, v_3) $: $ v'_i = (S^{-1})_{ij} v_j = L_{ij} v_j $.

*Exercise:* Clearly (by definition), $ \mathbf{v} $ is a vector if

```{math}
v_1 = x_1, \quad v_2 = x_2, \quad v_3 = x_3,
```

i.e., $ v = (x_1, x_2, x_3) $. Consider other sets of $ v_i $ in 2D space. Which of these functions are scalars, vectors, or neither?

```{math}
\mathbf{v}(x_1, x_2) &= v_1 = x_1 + x_2 \\
\mathbf{v}(x_1, x_2) &= v_1 = x_1^2 + x_2^2 \\
\mathbf{v}(x_1, x_2) &= (v_1, v_2) = (x_1, x_2) \\
\mathbf{v}(x_1, x_2) &= (v_1, v_2) = (x_2, -x_1) \\
\mathbf{v}(x_1, x_2) &= (v_1, v_2) = (x_2, x_1) 
```

```{figure} tensors_fig3.png
---
name: fig:tensors_fig3
---
Examples of functions in the 2D case: (a) $\mathbf{v}(x_1, x_2) = x_1 \mathbf{e}_1 + x_2 \mathbf{e}_2$; (b) $\mathbf{v}(x_1, x_2) = x_2 \mathbf{e}_1 - x_1 \mathbf{e}_2$;(c) $\mathbf{v}(x_1, x_2) = x_2 \mathbf{e}_1 + x_1 \mathbf{e}_2$.
```


*Exercise*: For the case of a two-dimensional space, show that $ \mathbf{v} = (x_2, -x_1) $ transforms as a vector under rotation of the coordinate system and $ \mathbf{v} = (x_2, x_1) $ does not.

### Transformation of scalars
Scalars or *$0^{th}$ order tensors* have only one component, which is invariant with respect to the rotation of the coordinate system. 

Are $ x_1^2 + x_2^2 $ and $ x_1^2 + x_2^2 + x_3^2 $ scalars in the three-dimensional Cartesian space?

Examples of scalars include $ \mathbf{F} \cdot d\mathbf{r}, e\mathbf{E} \cdot d\mathbf{r}, \mathbf{B} \cdot \mathbf{B} $, and many others.

*Exercise:* Show that the scalar product of vectors $ \mathbf{a} $ and $ \mathbf{b} $ is, indeed, a scalar, then demonstrate it for $ \nabla \cdot \mathbf{v} $, where $ \mathbf{v} $ is a vector.

*Example:*  Let $ \phi(x_1, x_2, x_3) $ be a scalar and derive $ \mathbf{E} $ as:

```{math}
\mathbf{E}(x_1, x_2, x_3) = -\nabla \phi(x_1, x_2, x_3) = -\frac{\partial \phi}{\partial x_1} \mathbf{e}_1 - \frac{\partial \phi}{\partial x_2} \mathbf{e}_2 - \frac{\partial \phi}{\partial x_3} \mathbf{e}_3.
```
Is $\mathbf{E}$ a vector? Components $E'_i$ in a new basis are given by

```{math}
E_i' = - \frac{\partial \phi'}{\partial x_i'} = - \frac{\partial \phi}{\partial x_j} \frac{\partial x_j}{\partial x_i'} = L_{ij} E_j,
```

i.e., they satisfy the transformation condition for the $1^{st}$ order tensors. Thus, $ \mathbf{E} $ is a vector.

## $2^{nd}$ and Higher-Order Tensors

Many physical properties of materials are described using the language of tensors. For example, *deformation*, *dielectric* and *magnetic permittivities*, *magnetoelectric* effect, and *conductivity* are described using $2^{nd}$ order tensors.

*Example:* Spin Hamiltonian used to model electron paramagnetic resonance (EPR) spectra for a system of $ N_{\text{atm}} $ atoms with nuclear spins $ I_k $:

```{math}
H = \mu_B\mathbf{B\,g\,S} + \sum_{k=1}^{N_{atm}} \mathbf{S\,A}_k\mathbf{I}_k
```
Where $\mathbf{g}$ and $\mathbf{A}$ are $2^{nd}$ order tensors.  $\mathbf{A}_k$ is the hyperfine interaction tensor for atom $k$; it is decomposed into isotropic and anisotropic parts:
```{math}
\mathbf{A} = a_{\text{iso}} \mathbf{I} + \mathbf{T}
```

These properties are related to the atomistic structure of materials, e.g., the conductivity tensor of crystals with cubic symmetry is isotropic. In this section, we describe basic operations with tensors.

Quantities $ T_{ij} $ are components of a 2nd-order tensor if they transform according to

```{math}
T'_{ij} = L_{ik} L_{jl} T_{kl}
```

upon rotation of the coordinate system. Then, components of the tensor $ T_{ij} $ in the old basis are expressed via components $ T_{k'l} $ in the new basis as

```{math}
T_{ij} = L_{ki} L_{lj} T'_{kl}.
```

In general, components of an order $ N $ tensor should transform as

```{math}
T'_{i_1 i_2 \ldots i_N} = L_{i_1 \alpha_1} L_{i_2 \alpha_2} \ldots L_{i_N \alpha_N} T_{\alpha_1 \alpha_2 \ldots \alpha_N}.
```

And

```{math}
T_{i_1 i_2 \ldots i_N} = L_{\alpha_1 i_1} L_{\alpha_2 i_2} \ldots L_{\alpha_N i_N} T'_{\alpha_1 \alpha_2 \ldots \alpha_N}.
```

An $N$-th order Cartesian tensor has $ 3^N $ components. Components of 2nd-order tensors are conveniently represented using matrices with elements $ T_{ij} $, where $ i $ refers to the row number and $ j $ refers to the column number.


### Outer Product
The *outer product* of vectors $ \mathbf{a} $ and $ \mathbf{b} $ is defined as:

```{math}
A_{ij} = a_i b_j
```

and is denoted as:

```{math}
\mathbf{A} = \mathbf{a} \otimes \mathbf{b}
```

Note the difference from $ \mathbf{A} = \mathbf{a} \times \mathbf{b} $!

Consider transformation of the outer product components upon rotation of the coordinate system:

```{math}
A'_{ij} = a'_i b'_j = L_{ik} a_k L_{jl} b_l = L_{ik} L_{jl} A_{kl}
```

Thus, components of the outer products of two vectors transform in the same way as components of a 2nd-order tensor.

Since $ \mathbf{a} = a_i \mathbf{e}_i $ and $ \mathbf{b} = b_j \mathbf{e}_j $, the tensor formed by the outer product of $ \mathbf{a} $ and $ \mathbf{b} $ can be written as:

```{math}
\mathbf{T} = \mathbf{a} \otimes \mathbf{b} = a_i\,b_j\, \mathbf{e}_i \otimes \mathbf{e}_j = = T_{ij}'  \mathbf{e}_i' \otimes \mathbf{e}_j'
```

Note that while components of the tensor $ T $ depend on the coordinate system, it is the *same* tensor in both coordinate systems.

The outer product operation can be applied to arbitrary tensors $ \mathbf{A} $ and $ \mathbf{B} $ of orders $ N $ and $ M $, respectively; the resulting tensor has order $ N + M $:

```{math}
\mathbf{T} = A \otimes B.
```

Components of the outer product tensor are

```{math}
T_{i_1 i_2 \ldots i_N j_1 j_2 \ldots j_M} = A_{i_1 i_2 \ldots i_N} B_{j_1 j_2 \ldots j_M}.
```


### Contraction
Contraction of a tensor assumes:
1. Equating two subscripts
2. Summing over all possible values of these subscripts.

In the case of the 2nd-order tensor, contraction of $ \mathbf{T}1 $ gives the sum of its diagonal elements:

```{math}
T_{ii} = \text{Tr}(T)
```

which gives a zero-order tensor. 

In general, contraction of a tensor of order $ N $:

1. Produces another tensor, and
2. Reduces its order to $ N - 2 $.

To show this, we need to investigate the transformation of the entity formed by contraction. (In anticipation that it is a tensor, we call it $ T $).

For an order $ N $ tensor:

```{math}
T'_{i_1 i_2 \ldots i_N} = L_{i_1 j_1} L_{i_2 j_2} \ldots L_{i_N j_N} T_{j_1 j_2 \ldots j_N}.
```

For the contracted tensor (using the orthogonality of $ L $):

```{math}
T'_{i_1 \ldots i_p \ldots i_p \ldots i_N} &= L_{i_1 j_1} \ldots L_{i_p j_p} \ldots L_{i_p j_q} \ldots L_{i_N j_N} T_{j_1 \ldots j_p \ldots j_q \ldots j_N}\\
&= L_{i_1 j_1} \ldots L_{i_p j_p} \, \delta_{j_p j_q} \ldots L_{i_N j_N} T_{j_1 \ldots j_p \ldots j_q \ldots j_N} \\
&= (L_{i_1 j_1} \ldots L_{i_{p-1} j_{p-1}})(L_{i_{p+1} j_{p+1}} \ldots L_{i_{q-1} j_{q-1}})(L_{i_{q+1} j_{q+1}} \ldots L_{i_N j_N}) T_{j_1 \ldots j_q \ldots j_N}.
```


The contraction operation is not defined for vectors. However, one can first generate a 2nd-order tensor as the outer product of two vectors 
```{math}
T_{ij} = a_i b_j
```

and then apply the contraction operation, which gives a scalar product of the vectors
```{math}
a_i b_i
```

### Inner Product
Operations of multiplication and contraction can be combined to produce new tensors. For example, if $ \mathbf{A} $ is a 3rd-order tensor and $ \mathbf{B} $ is a 4th-order tensor, then new tensors $ C_{ijmnt} $, $ C_{kln} $, and $ C_m $ of 5th, 3rd, and 1st order can be constructed as follows:

```{math}
C_{ijmnt} &= A_{ijk} B_{kmnt}\\
C_{kln} &= A_{ijk} B_{linj} \\
C_m &= A_{ijk} B_{kmji}
```

This process is called *inner multiplication* and the resulting tensors are called *inner products*. To prove that inner products are tensors, consider transformations of their components. For example:

```{math}
C_{kn} = A_{ki} B_{ni}
```

in a rotated coordinate system:

```{math}
C_{k' n} &= A'_{k i} B'_{n i} \\
&= (L_{k p} L_{i q} A_{p q})(L_{n r} L_{i s} B_{r s})\\
&= L_{k p} L_{n r} (L_{i q} L_{i s}) A_{p q} B_{r s}\\
&= L_{k p} L_{n r} (\delta_{q s}) A_{p q} B_{r s}\\
&= L_{k p} L_{n r} A_{p q} B_{r q}\\
&= L_{k p} L_{n r} C_{p r}.
```

Thus, $ \mathbf{C} $ is a tensor.

### Gradient of a Vector
If $ \mathbf{v} $ is a vector, then quantities
```{math}
T_{ij} = \frac{\partial v_i}{\partial x_j}
```
form components of a 2nd-order tensor. To prove it, consider these quantities in a rotated coordinate system:

```{math}
T'_{ij} = \frac{\partial v'_i}{\partial x'_j} = L_{ik} \frac{\partial v_k}{\partial x_l} L_{jl}
```

Tensor $ \mathbf{T} = \nabla \mathbf{v} $ can be considered as the gradient of a vector.

*Exercise:* Demonstrate that matrix $ T $ represents a 2nd-order tensor:

```{math}
T = \begin{pmatrix} {x_2}^2 & - x_1\,x_2 \\ -x_1 \,x_2 & {x_1}^2 \end{pmatrix}
```

### Summation of Tensors
If $ A_{i_1i_2 \dots i_N} $ and $ B_{j_1j_2 \dots j_N} $ are components of two tensors of the same order in the same coordinate system, then their sum and difference are defined as:

```{math}
S_{k_1k_2 \dots k_N} = A_{k_1k_2 \dots k_N} + B_{k_1k_2 \dots k_N}
```
```{math}
D_{k_1k_2 \dots k_N} = A_{k_1k_2 \dots k_N} - B_{k_1k_2 \dots k_N}
```

To prove that $ S_{k_1k_2 \dots k_N} $ are components of a tensor, show that they transform as:

```{math}
S'_{k_1 k_2 \dots k_N} = L_{k_1n_1} L_{k_2n_2} \dots L_{k_Nn_N} S_{n_1n_2 \dots n_N}
```
upon rotation of the coordinate system.

### Symmetric Tensors
A 2nd-order tensor is called *symmetric* if its components are related as:

```{math}
T_{ij} = T_{ji}
```

for all values of $ i $ and $ j $. In the case of an $ N $-th order tensor, if:

```{math}
T_{i_1 \dots i_N} = T_{i_1 \dots i_m \dots i_n \dots i_N}
```

this tensor is said to be symmetric with respect to the $ n $-th and $ m $-th subscripts.

Examples include Stress and strain tensors.

### Stress Tensor – Force $ \mathbf{F} $ acting on a small surface element $ \mathbf{S} $:

```{math}
\begin{pmatrix}
\sigma_{11} & \sigma_{12} & \sigma_{13} \\
\sigma_{21} & \sigma_{22} & \sigma_{23} \\
\sigma_{31} & \sigma_{32} & \sigma_{33}
\end{pmatrix}
=
\begin{pmatrix}
\tau_{xx} & \tau_{xy} & \tau_{xz} \\
\tau_{yx} & \tau_{yy} & \tau_{yz} \\
\tau_{zx} & \tau_{zy} & \tau_{zz}
\end{pmatrix}
```

Where:

```{math}
T_{ij} = T_{ji}
```

```{figure} tensors_fig4.png
---
name: fig:tensors_fig4
---
Stress in a loaded deformable body.
```


---

### Maxwell Stress Tensor:

```{math}
\sigma_{ij} = \epsilon_0 \mathbf{e}_i \mathbf{e}_j + \mu_1 B_i B_j - \frac{1}{2} \left( \epsilon_0 E^2 + \mu_1 B^2 \right) \delta_{ij}
```

---

## Antisymmetric Tensors:

If:

```{math}
T_{i_1 i_2 \dots i_N} = -T_{i_1 \dots i_m \dots i_N}
```

Then the tensor is said to be **antisymmetric**. 

Examples include that *Levi-Civita* Tensor and *Electromagnetic* (or *Faraday*) Tensor.

### Electromagnetic Tensor:

```{math}
F^{\mu \nu} =
\begin{pmatrix}
0 & \frac{\mathbf{e}_x}{c} & \frac{\mathbf{e}_y}{c} & \frac{\mathbf{e}_z}{c} \\
-\frac{\mathbf{e}_x}{c} & 0 & -B_z & B_y \\
-\frac{\mathbf{e}_y}{c} & B_z & 0 & -B_x \\
-\frac{\mathbf{e}_z}{c} & -B_y & B_x & 0
\end{pmatrix}
```

Where:

```{math}
B = \nabla \times A
```

```{math}
E = - \frac{\partial A}{\partial t} - \nabla \Phi
```

---

### Decomposing a Tensor into Symmetric and Antisymmetric Parts
An arbitrary tensor can be written as a sum of a symmetric and antisymmetric tensors. 

For 2nd order tensors:

```{math}
T_{ij} = \frac{1}{2} (T_{ij} + T_{ji}) + \frac{1}{2} (T_{ij} - T_{ji}) = S_{ij} + A_{ij}
```

Where $ S_{ij} $ is symmetric and $ A_{ij} $ is antisymmetric.

For Nth order tensor:

```{math}
S_{i_1 \dots i_N} = \frac{1}{2} \left( T_{i_1 \dots i_N} + T_{i_1 \dots i_m \dots i_N} \right)
```

```{math}
A_{i_1 \dots i_N} = \frac{1}{2} \left( T_{i_1 \dots i_N} - T_{i_1 \dots i_m \dots i_N} \right)
```

---

## The identity and permutation tensors

### Permutation Symbol and Permutation Tensor $ \epsilon_{ijk} $

The permutation symbol $ \epsilon_{ijk} $ is a three-index object defined as:

```{math}
\epsilon_{ijk} = \begin{cases} 
+1 & \text{if } (i,j,k) \text{ is an even permutation of } (1,2,3), (2,3,1), (3,1,2) \\
-1 & \text{if } (i,j,k) \text{ is an odd permutation of } (1,3,2), (3,2,1), (2,1,3) \\
0 & \text{if } i = j \text{ or } i = k \text{ or } j = k 
\end{cases}
```
This is also called the *Levi-Civita symbol*, *Levi-Civita density*, *alternating* tensor, and *signature*. Notations $\varepsilon_{ijk}$ and $e_{ijk}$ are also used in literature.

In matrix and vector language the $\epsilon$ tensor is used for the cross product $\mathbf{C} = \mathbf{A} \times \mathbf{B} \Rightarrow C_k = \epsilon_{ijk}\,A_i\,B_j$

The permutation symbol satisfies the following relations:

```{math}
\delta_{ij} \,\epsilon_{ijk} &= 0 \\
\epsilon_{ipq}\,\epsilon_{jpq} &= 2\delta_{ij} \\
\epsilon_{ijk}\,\epsilon_{ijk} &= 6 \\
\epsilon_{ijk}\epsilon_{pqk} &= \delta_{ip} \,\delta_{jq}  - \delta_{iq} \,\delta_{jp} 
```

and, in general,

```{math}
\epsilon_{ijk} \epsilon_{pqr} = \begin{vmatrix}
  \delta_{ip} & \delta_{iq} & \delta_{ir} \\
  \delta_{jp} & \delta_{jq} & \delta_{jr} \\
  \delta_{kp} & \delta_{kq} & \delta_{kr}
\end{vmatrix}
```

### Proving that $ \delta_{ij} $ and $ \epsilon_{ijk} $ are tensors

Even if neither $ \delta_{ij} $ nor $ \epsilon_{ijk} $ depend on coordinates, we can formally consider the transformation of their components with respect to the rotation of the coordinate system. Note that $ \delta_{ij} $ has two subscripts and $ \epsilon_{ijk} $ has three subscripts. Hence, in the new coordinate system:

```{math}
\delta_{i'j} = L_{ik} L_{jl} \delta_{kl}.
```

Using the properties of $ \delta_{ij} $ and the orthogonality of the transformation matrix $ L $:

```{math}
\delta_{i'j} = L_{ik} L_{jl} \delta_{kl} = L_{ik} L_{jk} = \delta_{ij}.
```
Similarly, transformation of $\epsilon_{ijk}$ is given by:

```{math}
\epsilon_{ijk}' = L_{il} L_{jm} L_{kn} \epsilon_{lmn}.
```

First notice that $ \epsilon_{ijk} $ can be used to calculate determinants of $ 3 \times 3 $ matrices:

```{math}
\text{det}(A) \epsilon_{ijk} = A_{il} A_{jm} A_{kn} \epsilon_{lmn}.
```
Hence, for the transformation matrix $ L $:

```{math}
\text{det}(L) \epsilon_{ijk} = L_{il} L_{jm} L_{kn} \epsilon_{lmn} = \epsilon'_{ijk}.
```

Using the orthogonality of $ L $ ($\text{det}(L) = 1$),

```{math}
\epsilon'_{ijk} = \epsilon_{ijk},
```

i.e., the properties of $ \epsilon_{ijk} $ do not change under orthogonal transformation, and the subscripts change as they should for the third-order tensor.

### $4^{th}$ Order $ \epsilon_{ijkl} $

The components of the rank 4 permutation tensor can be defined as:

```{math}
\epsilon_{ijkl} =
\begin{cases}
+1 & \text{if } (i,j,k,l) \text{ is an even permutation of } (1,2,3,4) \\
-1 & \text{if } (i,j,k,l) \text{ is an odd permutation of } (1,2,3,4) \\
0 & \text{for all other combinations of } (i,j,k,l)
\end{cases}
```

---

### Applications of $ \epsilon_{ijk} $:

*Example 1:* Vector Product of $ a $ and $ b $:

```{math}
\mathbf{c} = \mathbf{a} \times \mathbf{b} = 
\begin{vmatrix}
\mathbf{e}_1 & \mathbf{e}_2 & \mathbf{e}_3 \\
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3 
\end{vmatrix}
= 
\begin{vmatrix}
C_{11} & C_{12} & C_{13} \\
C_{21} & C_{22} & C_{23} \\
C_{31} & C_{32} & C_{33}
\end{vmatrix}
```
Since

```{math}
\text{det}(A) \epsilon_{ijk} &= A_{il} A_{jm} A_{kn} \epsilon_{lmn}\\
c \epsilon_{ijk} &= C_{il} C_{jm} C_{kn} \epsilon_{lmn}
```

Setting $ i=1, j=2, k=3 $ gives ($ \epsilon_{123}=1 $):

```{math}
c = C_{1l} C_{2m} C_{3n} \epsilon_{lmn}.
```

Since $ C_{1l} = e_l $, $ C_{2m} = a_m $, and $ C_{3n} = b_n $, we obtain:

```{math}
c = e_l a_m b_n \epsilon_{lmn}
```

The $l$-th component of $\mathbf{c}$ is given by:

```{math}
c_l = \epsilon_{lmn} a_m b_n.
```

*Example 2:* Double Vector Product:

In the case of a double vector product

```{math}
\mathbf{d} = [\mathbf{a} \times (\mathbf{b} \times \mathbf{c})],
```

the $ i $-th component of $ \mathbf{d} $ is 

```{math}
d_i = \epsilon_{ijk} a_j (b \times c)_k
```

and the $ k $-th component of $ b \times c $ is 

```{math}
(b \times c)_k = \epsilon_{klm} b_l c_m.
```

Thus, we have 

```{math}
d_i = \epsilon_{ijk} \epsilon_{klm} a_j b_l c_m.
```

Using the identity 

```{math}
\epsilon_{ijk} \epsilon_{klm} = \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl},
```

we find that

```{math}
d_i &= \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl}a_jb_lc_m\\
&= \delta_{il}a_m b_lc_m - \delta_{im} a_lb_lc_m\\
&= (a_m c_m) b_i - (a_l b_l) c_i.
```

In vector form, this is expressed as 

```{math}
\mathbf{d} = \mathbf{a} \times (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c}.
```

*Example:* Double cross products are used in solving geometrical problems. It is also used as an order parameter in complex dipolar structures in mag- nets and ferroelectrics 

```{figure} tensors_fig5.png
---
name: fig:tensors_fig5
---
Predicted hysteresis loops in asymmetric ferromagnetic ring. [S. Prosandeev and L. Bellaiche, Phys. Rev. B, 77 060101(R) (2008).]
```


*Exercise:* Find an explicit expression for the $ i $-th component of 
```{math}
\nabla \times (\mathbf{r} \times \mathbf{a})
```
using the properties of the tensor $ \epsilon_{ijk} $.

---

### Isotropic Tensors

An isotropic tensor has components that remain the same in all rotated coordinate systems.

All rank-0 tensors (scalars) are isotropic, but no rank-1 tensors (vectors) are isotropic. Both $ \delta_{ij} $ and $ \epsilon_{ijk} $ are isotropic tensors. They are the unique isotropic tensors of the 2nd and 3rd orders, respectively.


## The Quotient Theorem

The quotient theorem states that if

```{math}
A_{i_1 \dots \alpha \dots i_N} B_{j_1 \dots \alpha \dots j_M} = C_{i_1 i_2 \dots i_N j_1 j_2 \dots j_M}
```

in all coordinate systems rotated with respect to each other, and $ B $ is an arbitrary order $ M $ tensor, and $ C $ is an order $ N + M - 2 $ tensor, then quantities

```{math}
A_{i_1 i_2 \dots i_N}
```

are components of a tensor of the order $ N $.

We will prove the Quotient Law for $ N = M = 2 $.  Assume that:

```{math}
A_{jk} B_{ik} = C_{ji}
```

holds for all rotated coordinate systems and for any second-order tensor $ B $. Consider the transformation in a new coordinate system:

```{math}
A'_{jk} B'_{ik} &= C'_{ji} \\
&= L_{jp} L_{iq} C_{pq} \\
&= L_{jp} L_{iq} A_{pr} B_{rq} \\
&= L_{jp} L_{iq} A_{pr} L_{uq} L_{vr} B'_{uv} \\
&= L_{jp} (L_{iq} L_{uq}) L_{vr} A_{pr} B'_{uv} \\
&= L_{jp} L_{vr} A_{pr} B'_{iv}
```

Comparing the left and right sides:

```{math}
A'_{jk} B'_{ik} - L_{jp} L_{vr} A_{pr} B'_{uv} = 0
```

and note that subscripts $ k $ and $ v $ are dummy subscripts. Hence, the above equality can be rewritten as:

```{math}
(A'_{jk} - L_{jp} L_{kr} A_{pr}) B'_{ik} = 0
```

Since we assumed that $ \mathbf{B} $ is arbitrary, we conclude that:

```{math}
A'_{jk} = L_{jp} L_{kr} A_{pr}
```

Thus, the components $ A_{pr} $ transform as components of a tensor:
```{math}
A'_{jk} = L_{jp} L_{kr} A_{pr}
```


*Exercise:* Show that if

```{math}
A_{ik} B_{k} = C_{i}
```

holds for any vector $ \mathbf{B} $ and for a vector $ \mathbf{C} $, then $ \mathbf{A} $ is a second-order tensor.

---

## Physical Applications of Tensors

### Tensor of Inertia

Consider a collection of interconnected points $ \alpha $ with masses $ m_\alpha $ (neglecting the masses of the connectors). The orbital momentum of this system is defined as:

```{math}
L = \sum_\alpha \left( \mathbf{r}_\alpha \times \mathbf{p}_\alpha \right) = \sum_\alpha m_\alpha \left( \mathbf{r}_\alpha \times \left( \boldsymbol{\omega} \times \mathbf{r}_\alpha \right) \right)
```

For continuous bodies, substitute the summation over $ \alpha $ with integration over $ \mathrm{d}m $. Find the explicit expression for the $ i $-th component of $ \mathbf{L} $:

```{math}
L_i &= \sum_\alpha m_\alpha \left( \epsilon_{ijk} x'_{\alpha j} (\boldsymbol{\omega} \times \mathbf{r}_\alpha)_k \right) = \sum_\alpha m_\alpha \left[ \epsilon_{ijk} \epsilon_{klm} x^{\alpha}_{j} \omega_l x^{\alpha}_{m} \right]\\
&= \sum_\alpha m_\alpha \left[ \left(\delta_{il}\delta_{jm} - \delta_{im}\delta_{jl}\right) x^{\alpha}_{j} x^{\alpha}_{m} \right]\omega_l\\
&= \sum_\alpha m_\alpha \left[ \delta_{il}x^{\alpha}_{j} x^{\alpha}_{j} - x^{\alpha}_{i} x^{\alpha}_{l}  \right]\omega_l\\
&= I_{il} \omega_l
```

where the components $ I_{ij} $ are called the components of the tensor of inertia. Since $ \mathbf{L} $ and $ \boldsymbol{\omega} $ are vectors, $ I_{ij} $ are components of a true second-order tensor. 

We see that by construction, $ I_{ij} $ is a symmetric tensor.

### Kinetic Energy of a Rotating System

For a fixed rotation axis, the kinetic energy is given by:

```{math}
T &= \frac{1}{2} \int v^2 \, \mathrm{d}m = \frac{1}{2} \int (\boldsymbol{\omega} \times \mathbf{r})^2 \, \mathrm{d}m\\
&= \frac{1}{2} \int \omega^2 r^2 \, \mathrm{d}m\\
&= \frac{1}{2} I \omega^2
```
In a general case:

```{math}
T &=  \frac{1}{2} \int\frac{\mathrm{d}\mathbf{r}}{\mathrm{d}t} \cdot \frac{\mathrm{d}\mathbf{r}}{\mathrm{d}t}\, \mathrm{d}m \\
&= \frac{1}{2} \int (\boldsymbol{\omega} \times \mathbf{r}) \cdot (\boldsymbol{\omega} \times \mathbf{r}) \, \mathrm{d}m \\
&= \frac{1}{2} \int (\boldsymbol{\omega} \times \mathbf{r})_{i} (\boldsymbol{\omega} \times \mathbf{r})_{i} \, \mathrm{d}m \\
&= \frac{1}{2} \int(\epsilon_{ijk} \omega_{j} x_{k})(\epsilon_{imn} \omega_{m} x_{n}) \, \mathrm{d}m\\
&= \frac{1}{2} \int \left( \delta_{jm} \delta_{kn} - \delta_{jn} \delta_{km} \right) x_{k} x_{n} \omega_{j} \omega_{m} \, \mathrm{d}m \\
&= \frac{1}{2} \int \left(\left[ \delta{jm} x_{k} x_{k} - x_{j} x_{m}\right]\omega_{j}
\omega_{m} \right) \, \mathrm{d}m \\
&= \frac{1}{2} I_{jm} \omega_{j} \omega_{m}.
```


---

### Strain Tensor

In the case of deformation, consider a small element of an elastic body subjected to deformation (see our earlier figure for stress tensor). Let us define deformation-induced dis- placement of a point as:
```{math}
\mathbf{u} = \mathbf{r}' - \mathbf{r}
```

Here $\mathbf{r} = (x_1,\, x_2,\, x_3)$ are coordinates of a point before deformation, $\mathbf{r}' = (x'_1,\, x'_2,\, x'_3)$ are coordinates of the same point after the deformation and $\mathbf{u}$ is *deformation vector*. Note that coordinates $x'_i$ are functions of the coordinates $x_k$.

Let the distance between two points before and after deformation be given by:

```{math}
d\ell = \sqrt{\mathrm{d}x_1^2 + \mathrm{d}x_2^2 + \mathrm{d}x_3^2}, \quad d\ell' = \sqrt{(\mathrm{d}x_1')^2 + (\mathrm{d}x_2')^2 + (\mathrm{d}x_3')^2}
```

The relationship between the two can be expressed as:

```{math}
(d\ell)^2 &= (\mathrm{d}x_1)^2 + (\mathrm{d}x_2)^2 + (\mathrm{d}x_3)^2 = \mathrm{d}x_i \mathrm{d}x_i \\
(d\ell')^2 &= (\mathrm{d}x'_1)^2 + (\mathrm{d}x'_2)^2 + (\mathrm{d}x'_3)^2 \\
&= \mathrm{d}x'_i \mathrm{d}x'_i \\
&= (\mathrm{d}x_i + \mathrm{d}u_i)(\mathrm{d}x_i + \mathrm{d}u_i)\\
&= \mathrm{d}x_i \,\mathrm{d}x_i + 2\mathrm{d}x_i \,\mathrm{d}u_i + \mathrm{d}u_i\, \mathrm{d}u_i\\
&= (\mathrm{d}\ell)^2 + 2\mathrm{d}x_i \,\mathrm{d}u_i + \mathrm{d}u_i\, \mathrm{d}u_i
```

Since components of the deformation vector $u_i$ are functions of $x_k$, we have  
```{math}
\mathrm{d}u_i = \frac{\partial u_i}{\partial x_k} \mathrm{d}x_k.
```
Thus,
```{math}
(\mathrm{d}\ell^0)^2 = (\mathrm{d}\ell)^2 + 2\frac{\partial u_i}{\partial x_k} \mathrm{d}x_i \mathrm{d}x_k + \frac{\partial u_i}{\partial x_k} \frac{\partial u_j}{\partial x_n} \mathrm{d}x_k \mathrm{d}x_n,
```
which can also be written as
```{math}
(\mathrm{d}\ell^0)^2 = (\mathrm{d}\ell)^2 + \frac{\partial u_i}{\partial x_k} \mathrm{d}x_i \mathrm{d}x_k + \frac{\partial u_k}{\partial x_i} \mathrm{d}x_i \mathrm{d}x_k + \frac{\partial u_m}{\partial x_n} \mathrm{d}x_i \mathrm{d}x_k,
```
or
```{math}
(\mathrm{d}\ell')^2 = (\mathrm{d}\ell)^2 + 2u_{ik} \mathrm{d}x_i\, \mathrm{d}x_k
```
 
where $u_{ik}$ is the *deformation* or *strain* tensor:

```{math}
u_{ik} = \frac{1}{2}\left(\frac{\partial u_i}{\partial x_k} + \frac{\partial u_k}{\partial x_i} + \frac{\partial u_m}{\partial x_i}\frac{\partial u_m}{\partial x_i} \right)\simeq \frac{1}{2}\left(\frac{\partial u_i}{\partial x_k} + \frac{\partial u_k}{\partial x_i}\right).
```

---

### Stress Tensor

Stress is defined as the average force per unit area of a surface within a deformable body:
```{math}
\sigma = \frac{F}{S}
```
![Components of the stress tensor](tensors_fig6.png)

Components of the stress tensor

Consider a small volume shown in the above figure. The $i^{th}$ component of the total force acting on a volume $ V $ is given by:

```{math}
F_i = \int F_i \, \mathrm{d}V
```
where $\mathrm{F}_i$ is the $i^{th}$ component of the force $\mathrm{F}$ acting on a unit of volume $\mathrm{d}V$.

This volume integral can be converted to a surface integral if $ F_i $ has a form of $ \frac{\partial \sigma_{ik}}{\partial x_k} $. In addition, $ \sigma $ has to be a tensor: if $ \sigma_{ik} $ are components of a tensor, then $ \frac{\partial \sigma_{ik}}{\partial x_k} $ are components of a vector. Then,
```{math}
\int F_i \, \mathrm{d}V = \int \frac{\partial \sigma_{ik}}{\partial x_k} \, \mathrm{d}V = \oint \sigma_{ik} \,\mathrm{d}S_k,
```
and $ \sigma_{ik} $ has the dimension of strain. Here we used the divergence theorem:
```{math}
\int_V (\nabla\cdot a) \, \mathrm{d}V = \int_S a \cdot\mathrm{d}S,
```
where the *surface $ S $ encloses the volume $ V $.*

The moment acting on a “small” volume $ \mathrm{d}V $ is 
```{math}
m_{ik} = (F_i x_k - F_k x_i) \, \mathrm{d}V.
```
Thus, the total moment acting on a body is 
```{math}
M_{ik} = \int (F_i x_k - F_k x_i) \, \mathrm{d}V = \int \left( \frac{\partial \sigma_{im}}{\partial x_k} - \frac{\partial \sigma_{km}}{\partial x_i} \right) \, \mathrm{d}V,
```
which can be re-written as
```{math}
M = \int \frac{\partial}{\partial x_m} (\sigma_{im} x_k - \sigma_{km} x_i) \, \mathrm{d}V - \int \left( \sigma_{ik} \frac{\partial}{\partial x_i} \right) \, \mathrm{d}V.
```

Rewriting the first term as a surface integral and use $ \frac{\partial x_k}{\partial x_m} = \delta_{km} $ and $ \frac{\partial x_i}{\partial x_m} = \delta_{im} $ in the second term:
```{math}
M_{ik} = \oint (\sigma_{im} x_k - \sigma_{km} x_i) \,\mathrm{d}S_m + \int (\sigma_{ki} - \sigma_{ik}) \, \mathrm{d}V.
```

For a body in equilibrium, the momentum should not contain the contribution due to the integral over the volume. You may wish to think about why this is!

The integral over volume in this equation vanishes if:

```{math}
\sigma_{ik} = \sigma_{ki}
```
i.e., the stress tensor is symmetric.

For a homogeneously compressed body, pressure $p$ is applied to every point of its surface and the force applied to a surface element $\mathrm{d}\mathbf{S}$ is $\mathbf{F} = -p\mathrm{d}\mathbf{S}$, i.e., components of the force are $F_i = -p\mathrm{d}S_i$.

At the same time, components of the force are equal to 
```{math}
F_i = \sigma_{ik} \mathrm{d}S_k
```
Thus, the stress tensor in this case is:

```{math}
\sigma_{ik} = -p \delta_{ik}.
```


---

### Elastic Constants

The stress and strain tensors are related by:

```{math}
\sigma_{ij} = c_{ijkl} \, u_{kl}
```

The 4th-order tensor $ c_{ijkl} $ is called the *stiffness* tensor or *elastic* tensor, and its components are the *elastic* constants. The stiffness tensor has 81 components ($3 \times 3 \times 3 \times 3$), but only 21 independent components are needed due to symmetry considerations.
