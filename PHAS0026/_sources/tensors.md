# Cartesian Tensors

## Definitions

Physical properties are described using one or several independent variables. For example, volume $ V $ of a cake (see Fig. 2.1a) is described using only one variable. Such properties are called **scalars**. Three independent variables are needed to describe the velocity of the champagne cork (Fig. 2.1b). Such properties are called **vectors**. We can use $ v $ or $ (v_x, v_y, v_z) $ or $ x_1, x_2, x_3 $ to represent the vector of velocity.

How many independent variables are needed to describe the response of a solid to external stress? This property should reflect the direction and magnitude of the force applied to each point, and the direction and magnitude of the displacement of each point. Hence, nine independent variables are needed. Thus, in general, physical properties are described using $ N $ independent variables.

In this chapter, we will consider how representation of these properties changes upon transformation from one coordinate system to another. We will consider real variables only and focus on three-dimensional Euclidean space. Some of the definitions will be given for $ N $-dimensional space.

---

## N-dimensional space

Consider a set of $ N $ real independent variables $ x_1, x_2, \dots, x_i, \dots, x_N $. These values will be called coordinates of a point. All the points corresponding to all the possible values of the coordinates form the **N-dimensional space**. This space will be denoted as $ V_N $.

Note the difference between a coordinate system defined by $ x_1, x_2, \dots, x_i, \dots, x_N $ and a point given by a specific realization of the coordinates $ x_1, x_2, \dots, x_i, \dots, x_N $.

---

### Curve in N-dimensional space

If there are $ N $ equations $ x_i = f_i(u) $, where $ i = 1, 2, \dots, N $, and $ u $ is a parameter and $ f_i(u) $ are functions of $ u $, the collection of points which satisfy these equations defines a curve in $ V_N $.

---

### Subspace in N-dimensional space

In general, if there are $ N $ equations

```{math}
x_i = f_i(u_1, u_2, \dots, u_M), \quad \text{where} \, i = 1, 2, \dots, N \, \text{and} \, M < N
```

where $ u_1, u_2, \dots, u_M $ are parameters and $ f_i(u_1, \dots, u_M) $ are functions of these parameters, the collection of all points which satisfy these equations defines an $ M $-dimensional subspace $ V_M $ in $ V_N $. If $ M = N - 1 $, the subspace $ V_M $ is called a **hypersurface** of $ V_N $.

---

### Kronecker delta ($ \delta $) symbol

```{math}
\delta_{ij} = 
\begin{cases}
1 & \text{if} \, i = j \\
0 & \text{if} \, i \neq j
\end{cases}
```

---

### Summation convention

In order to simplify equations, we will use two conventions regarding the indices.

1. Indices will take all values from 1 to $ N $, unless otherwise stated explicitly.
2. If an index appears twice in any single term, a summation with respect to this index is implied. The summation goes over the range from 1 to $ N $ (convention 1).

For example, in 3D space ($ N = 3 $):

```{math}
a_i x_i = a_1 x_1 + a_2 x_2 + a_3 x_3
```

```{math}
a_{ij} b_{jk} = a_{i1} b_{1k} + a_{i2} b_{2k} + a_{i3} b_{3k} \quad \text{(the sum depends on $ i $ and $ k $)}
```

Similarly, in $ N $-dimensional space:

```{math}
a_{ij} b_{jk} c_{kmn} = \sum_{i=1}^{N} \sum_{j=1}^{N} a_{ij} b_{jk} c_{kmn}
```

```{math}
\frac{\partial^2 \delta}{\partial x_i^2} = \frac{\partial^2 \delta}{\partial x_1^2} + \frac{\partial^2 \delta}{\partial x_2^2} + \frac{\partial^2 \delta}{\partial x_3^2}
```

```{math}
\sum_{i=1}^{N} a_i x_i + \sum_{j=1}^{N} b_j x_j = a_i x_i + b_j x_j
```

Note that no summation is implied in
```{math} 
a_i + x_i + b_j + x_j. 
```
The summation index is called a dummy index; it can be replaced by any other index as long as it does not conflict with other indices used in equations. For example, if $ x_i $ is defined by the function $ \varphi_i $ as

```{math} 
x_i = \varphi_i(x_1, x_2, \dots, x_N), 
```

then the differential of $ x_i $ can be written as

```{math}
dx_i = \sum_{j=1}^{N} \frac{\partial \varphi_i}{\partial x_j} dx_j = \frac{\partial \varphi_i}{\partial x_j} dx_j = \frac{\partial \varphi_i}{\partial x_r} dx_r.
```

In order to avoid confusion, the same index should not be used more than twice in one term. For example,

```{math}
\frac{dx_j}{\partial x_i} = \frac{\partial \varphi_j}{\partial x_i} \quad \text{but not} \quad \frac{dx_j}{\partial x_j}.
```

To demonstrate the effect of the Kronecker symbol:

```{math}
a_i x_i = (a_i x_i)^2 = (a_i x_i)(a_j x_j) = a_i a_j x_i x_j,
```

```{math}
b_j \delta_{ij} = b_i,
```

but not $ a_i x_i a_i x_i $.

### Exercise

Show that

```{math}
a_{ij} \delta_{jk} = a_{ik}, \quad a_{ij} b_{jk} \delta_{ki} = a_{ij} b_{ji} = a_{kj} b_{jk}.
```

```{math}
\delta_{ij} \delta_{jk} = \delta_{ik}, \quad \delta_{ii} = N.
```

---

## Change of Basis

### Transformation of coordinates in 3-dimensional space

Let us introduce a set of independent basis vectors in a 3D space: $ e_1, e_2, e_3 $. Then, any vector $ x $ can be represented as

```{math}
x = x_1 e_1 + x_2 e_2 + x_3 e_3 = x_k e_k,
```

where $ x_1, x_2, x_3 $ are called components of the vector $ x $. Consider a new basis set $ e'_1, e'_2, e'_3 $ related to the old one by:

```{math}
e'_1 = S_{11} e_1 + S_{21} e_2 + S_{31} e_3 = S_{k1} e_k,
```

```{math}
e'_2 = S_{12} e_1 + S_{22} e_2 + S_{32} e_3 = S_{k2} e_k,
```

```{math}
e'_3 = S_{13} e_1 + S_{23} e_2 + S_{33} e_3 = S_{k3} e_k,
```

where $ S_{ij} $ are elements of a matrix $ S $. In the new basis set, vector $ x $ can be written as:

```{math}
x = x'_1 e'_1 + x'_2 e'_2 + x'_3 e'_3 = x'_k e'_k.
```

Substituting the expressions for $ e'_1, e'_2, e'_3 $ into this equation gives:

```{math}
x = x'_1 (S_{k1} e_k) + x'_2 (S_{k2} e_k) + x'_3 (S_{k3} e_k)
= x'_j (S_{kj} e_k).
```

Hence, the components of the vector $ x $ in the old and new basis sets are related. The components of the transformation matrix $ S $ are given by:

```{math}
\frac{\partial x_i}{\partial x'_k} = S_{ik}.
```

---

#### Transformation of coordinates in N-dimensional space

Consider a space $ V_N $ and a coordinate system $ x_1, x_2, \dots, x_N $. If there are $ N $ equations

```{math}
x'_i = \varphi_i(x_1, x_2, \dots, x_N) \quad (i = 1, 2, \dots, N),
```

where $ \varphi_i $ are independent single-valued continuous and differentiable functions of coordinates, these equations define the transformation of coordinate system $ x_1, x_2, \dots, x_N $ into a new coordinate system $ x'_1, x'_2, \dots, x'_N $.

A necessary and sufficient condition for the independence of the functions $ \varphi_i $ is that the determinant of the $ N \times N $ matrix formed by the derivatives

```{math}
\frac{\partial x'_i}{\partial x_j} = \frac{\partial \varphi_i(x_1, \dots, x_N)}{\partial x_j} \quad (i, j \in 1, \dots, N),
```

denoted as $ S $, is not equal to zero:

```{math}
\det([S_{ji}]) = \det \left( \frac{\partial \varphi_i(x_1, \dots, x_N)}{\partial x_j} \right) \neq 0.
```

Under this condition, the above equations can be solved with respect to $ x_i $, i.e., one can find functions $ \psi_i $ which express old coordinates $ x_i $ in terms of new coordinates $ x'_j $:

```{math}
x_i = \psi_i(x'_1, x'_2, \dots, x'_N) \quad (i = 1, 2, \dots, N).
```

### Rotations of Cartesian coordinate systems

Investigate how components of a vector are changed by a rotation of the Cartesian coordinate system. For convenience, introduce transformation matrix $ L = S^{-1} $, where matrix $ S $ defines the rotation of the basis set vectors. Then,

```{math}
x'^{i} = L^{i}_{j} x^{j}, \quad x^{i} = L^{j}_{i} x'^{j}
```
(orthogonality of rows) (orthogonality of columns).

Orthogonality of $ L $ means that

```{math}
L^{ik} L^{jk} = \delta^{ij}, \quad L_{ki} L_{kj} = \delta^{ij}
```

(In the following we always assume that matrix $ L $ is orthogonal.)

Since we defined new basis $ e'_j $ ($ j = 1, 2, 3 $) as

```{math}
e'_j = S_{ij} e_i = (L^{-1})_{ij} e_i,
```

For orthonormal vectors $ e_k $ ($ k = 1, 2, 3 $) and rotation $ L $:

```{math}
e_k \cdot e'_j = S_{ij} e_k \cdot e_i = S_{ij} \delta_{ki} = S_{kj} = (L^{-1})_{kj} = (L^{T})_{kj} = L_{jk},
```

i.e., elements of the transformation matrix $ L $ are defined by the scalar products of the old and new basis vectors.

**Exercise:** Show that the transformation matrix $ L $ for a rotation of the coordinate system by an angle $ \theta $ about the $ e_3 $ axis is

```{math}
L = 
\begin{pmatrix}
\cos \theta & \sin \theta & 0 \\
-\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{pmatrix}
```

---

![Rotation of Cartesian axes by an angle α about the x3 axis.](image_url)

**Figure 2.2:** Rotation of Cartesian axes by an angle $ \alpha $ about the $ x_3 $ axis. Note that the rotation of the axes changes components of the vector $ x $ but not the vector itself.

**Exercise:** Show that two consecutive rotations of the coordinate system by an angle $ \theta $ about the $ e_3 $ axis is also a rotation with the value of the rotation angle of $ 2\theta $.

In general, the product of two rotations is also a rotation, i.e., if

```{math}
x'^{i} = L^{i}_{j} x^{j}
```

and then

```{math}
x''^{i} = M^{i}_{j} x'^{j},
```

```{math}
x'' = M x' = M (L x) = (M L) x = (ML) x.
```

---

### Transformation of vectors

Consider a set of quantities $ v_i $ ($ i = 1, \dots, N; N = 3 $), which are functions of coordinates $ x_j $ ($ j = 1, \dots, N; N = 3 $), i.e.,

```{math}
v_i = v_i(x_1, x_2, x_3),
```

and investigate how their values are changed by a rotation of the Cartesian axes. We already know that coordinates transform as

```{math}
x'^{i} = L^{i}_{j} x^{j}.
```

If a set of new quantities $ v'^{i} $ can be obtained from the set of $ v_i $ by the same transformation:

```{math}
v'^{i} = L^{i}_{j} v^{j},
```

then $ v_i $ form the components of a vector or 1st-order Cartesian tensor. According to this definition:

```{math}
v'_k e'_k = (L_{kj} v_j)(S_{nk} e_n) = (S_{nk} L_{kj}) v_j e_n = S_{nk}(S^{-1})_{kj} v_j e_n = \delta_{nj} v_j e_n = v_n e_n,
```

i.e.,

```{math}
v = v_i e_i = v'_j e'_j.
```

---

Review:

1. **N-dimensional space:** variables $ x_1, x_2, \dots, x_N $ ($ x_i \in \mathbb{R} $).
2. **The summation convention:** $ a_i b_i = a_i b_i $.
3. **Basis set $ e_i $, rotation of the coordinate system:** $ e'_j = S_{ij} e_i $ and the corresponding transformation of coordinates $ x'_i = (S^{-1})_{ij} x_j $.
4. **1st-order Cartesian tensors $ v = (v_1, v_2, v_3) $:** $ v'_i = (S^{-1})_{ij} v_j = L_{ij} v_j $.

Clearly (by definition), $ v $ is a vector if

```{math}
v_1 = x_1, \quad v_2 = x_2, \quad v_3 = x_3,
```

i.e., $ v = (x_1, x_2, x_3) $. Consider other sets of $ v_i $ in 2D space. Which of these functions are scalars, vectors, or neither?

- $ v(x_1, x_2) = v_1 = x_1 + x_2 $
- $ v(x_1, x_2) = v_1 = x_1^2 + x_2^2 $
- $ v(x_1, x_2) = (v_1, v_2) = (x_1, x_2) $
- $ v(x_1, x_2) = (v_1, v_2) = (x_2, -x_1) $
- $ v(x_1, x_2) = (v_1, v_2) = (x_2, x_1) $

### Exercise
For the case of a two-dimensional space, show that $ v = (x_2, -x_1) $ transforms as a vector under rotation of the coordinate system and $ v = (x_2, x_1) $ does not.

## Transformation of Scalars
Scalars or 0th order tensors have only one component, which is invariant with respect to the rotation of the coordinate system. Are $ x_1^2 + x_2^2 $ and $ x_1^2 + x_2^2 + x_3^2 $ scalars in the three-dimensional Cartesian space?

Examples of scalars include $ \mathbf{F} \cdot d\mathbf{r}, \mathbf{E} \cdot d\mathbf{r}, \mathbf{B} \cdot \mathbf{B} $, and many others.

**Exercise**  
Show that the scalar product of vectors $ \mathbf{a} $ and $ \mathbf{b} $ is, indeed, a scalar, then demonstrate it for $ \mathbf{r} \cdot \mathbf{v} $, where $ \mathbf{v} $ is a vector.

**Example**  
Let $ \phi(x_1, x_2, x_3) $ be a scalar and derive $ \mathbf{E} $ as:

```{math}
\mathbf{E}(x_1, x_2, x_3) = \nabla \phi(x_1, x_2, x_3) = \frac{\partial \phi}{\partial x_1} \mathbf{e}_1 + \frac{\partial \phi}{\partial x_2} \mathbf{e}_2 + \frac{\partial \phi}{\partial x_3} \mathbf{e}_3.
```

```{math}
\begin{aligned}
\mathbf{v} &= (x_2, -x_1) \\
\mathbf{v} &= (x_1, x_2)
\end{aligned}
```

![Examples of functions in 2D](Figure 2.3)

Examples of functions in the 2D case:
- (a) $ \mathbf{v}(x_1, x_2) = x_1 \mathbf{e}_1 + x_2 \mathbf{e}_2 $
- (b) $ \mathbf{v}(x_1, x_2) = x_2 \mathbf{e}_1 - x_1 \mathbf{e}_2 $
- (c) $ \mathbf{v}(x_1, x_2) = x_2 \mathbf{e}_1 + x_1 \mathbf{e}_2 $

### Is $ \mathbf{E} $ a vector?
Components $ E_i' $ in a new basis are given by:

```{math}
E_i' = - \frac{\partial \phi'}{\partial x_i'} = - \frac{\partial \phi}{\partial x_j} \frac{\partial x_j}{\partial x_i'} = L_{ij} E_j,
```

i.e., they satisfy the transformation condition for the 1st order tensors. Thus, $ \mathbf{E} $ is a vector.

## 2nd- and Higher-Order Tensors

Many physical properties of materials are described using the language of tensors. For example, deformation, dielectric and magnetic permittivities, magnetoelectric effect, and conductivity are described using 2nd order tensors.

### Example:
Spin Hamiltonian used to model electron paramagnetic resonance (EPR) spectra for a system of $ N_{\text{atm}} $ atoms with nuclear spins $ I_k $:

```{math}
A = a_{\text{iso}} I + T
```

These properties are related to the atomistic structure of materials, e.g., the conductivity tensor of crystals with cubic symmetry is isotropic. In this section, we describe basic operations with tensors.

## Components of a 2nd-Order Tensor
Quantities $ T_{ij} $ are components of a 2nd-order tensor if they transform according to

```{math}
T' = L L T_{ij} L_{ik} L_{jl}
```

upon rotation of the coordinate system. Then, components of the tensor $ T_{ij} $ in the old basis are expressed via components $ T_{k'0l} $ in the new basis as

```{math}
T_{ij} = L_{ki} L_{lj} T_{k'0l}
```

In general, components of the order $ N $ tensor should transform as:

```{math}
T' = L L \dots L T_{i_1i_2 \dots i_N}
```

where $ T_{i_1i_2 \dots i_N} $ is the tensor with $ N $-th order, and $ L_{ \alpha_1i_1} L_{ \alpha_2i_2} \dots L_{ \alpha_Ni_N} $ are the transformation matrices.

### Example:
```{math}
H = \mu_B B g S + \dots
```
where $ g $ and $ A $ are 2nd order tensors. $ A_k $ is the hyperfine interaction tensor for atom $ k $; it is usually decomposed into isotropic and anisotropic parts.

```{math}
A_k = \sum_{k=1}^{N_{\text{atm}}}
```

### Outer Product
The outer product of vectors $ \mathbf{a} $ and $ \mathbf{b} $ is defined as:

```{math}
A_{ij} = a_i b_j
```

and is denoted as:

```{math}
A = \mathbf{a} \otimes \mathbf{b}
```

(Note the difference from $ A = \mathbf{a} \times \mathbf{b} $.) Consider transformation of the outer product components upon rotation of the coordinate system:

```{math}
A'_{ij} = a'_i b'_j = L_{ik} a_k L_{jl} b_l = L_{ik} L_{jl} A_{kl}
```

Thus, components of the outer products of two vectors transform in the same way as components of a 2nd-order tensor.

Since $ \mathbf{a} = a_i e_i $ and $ \mathbf{b} = b_j e_j $, the tensor formed by the outer product of $ \mathbf{a} $ and $ \mathbf{b} $ can be written as:

```{math}
T = \mathbf{a} \otimes \mathbf{b} = T' e' \otimes e'
```

### Contraction
Contraction of a tensor assumes:
1. Equating two subscripts
2. Summing over all possible values of these subscripts.

In the case of the 2nd-order tensor, contraction of $ T $ gives the sum of its diagonal elements:

```{math}
T_{ii} = \text{Tr}(T)
```

which gives a zero-order tensor. In general, contraction of a tensor of order $ N $ produces another tensor and its order is $ N - 2 $. For the order $ N $ tensor:

```{math}
T' = L L \dots L T_{i_1i_2 \dots i_N}
```

For the contracted tensor, it follows:

```{math}
T' = L \dots L \dots L \dots L T_{i_1 \dots i_p \dots i_N}
```

The contraction operation is not defined for vectors. However, one can first generate a 2nd-order tensor as the outer product of two vectors $ T_{ij} = a_i b_j $ and then apply the contraction operation, which gives a scalar product of the vectors $ a_i b_i $.

### Inner Product
Operations of multiplication and contraction can be combined to produce new tensors. For example, if $ A $ is a 3rd-order tensor and $ B $ is a 4th-order tensor, then new tensors $ C_{ijmnt} $, $ C_{kln} $, and $ C_m $ of 5th, 3rd, and 1st order can be constructed as follows:

```{math}
C_{ijmnt} = A_{ijk} B_{kmnt}
```
```{math}
C_{kln} = A_{ijk} B_{linj}
```
```{math}
C_m = A_{ijk} B_{kmji}
```

This process is called inner multiplication and the resulting tensors are called inner products. To prove that inner products are tensors, consider transformations of their components. For example:

```{math}
C_{kn} = A_{ki} B_{ni}
```

in a rotated coordinate system:

```{math}
C'_{kn} = A'_{ki} B'_{ni} = (L_{kp} L_{iq} A_{pq})(L_{nr} L_{is} B_{rs}) = L_{kp} L_{nr} (L_{iq} L_{is}) A_{pq} B_{rs}
```

Thus, $ C $ is a tensor.

### Gradient of a Vector
If $ \mathbf{v} $ is a vector, then quantities $ T_{ij} = \frac{\partial v_i}{\partial x_j} $ form components of a 2nd-order tensor. To prove it, consider these quantities in a rotated coordinate system:

```{math}
T'_{ij} = \frac{\partial v'_i}{\partial x'_j} = L_{ik} \frac{\partial v_k}{\partial x_l} L_{jl}
```

Tensor $ T = \nabla \mathbf{v} $ can be considered as the gradient of a vector.

### Example
Demonstrate that matrix $ T $ represents a 2nd-order tensor:

```{math}
T = \begin{pmatrix} x_2 - x_1 & x_2 \\ -x_1 & x_2 \end{pmatrix}
```

## Summation of Tensors
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

## Symmetric Tensors
A 2nd-order tensor is called symmetric if its components are related as:

```{math}
T_{ij} = T_{ji}
```

for all values of $ i $ and $ j $. In the case of an $ N $-th order tensor, if:

```{math}
T_{i_1 \dots i_N} = T_{i_1 \dots i_m \dots i_n \dots i_N}
```

this tensor is said to be symmetric with respect to the $ n $-th and $ m $-th subscripts.

### Example - Stress and strain tensors.

Stress Tensor – Force $ F $ Acting on a Small Surface Element $ S $:

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

![Figure 2.4: Stress in a Loaded Deformable Body (Wiki)](figure2.4.png)

---

### Maxwell Stress Tensor:

```{math}
\sigma_{ij} = \epsilon_0 E_i E_j + \mu_1 B_i B_j - \frac{1}{2} \left( \epsilon_0 E^2 + \mu_1 B^2 \right) \delta_{ij}
```

---

## Antisymmetric Tensors:

If:

```{math}
T_{i_1 i_2 \dots i_N} = -T_{i_1 \dots i_m \dots i_N}
```

Then the tensor is said to be **antisymmetric**. 

Examples: **Levi-Civita Tensor**, **Electromagnetic Tensor**.

### Electromagnetic Tensor:

```{math}
F^{\mu \nu} =
\begin{pmatrix}
0 & \frac{E_x}{c} & \frac{E_y}{c} & \frac{E_z}{c} \\
-\frac{E_x}{c} & 0 & -B_z & B_y \\
-\frac{E_y}{c} & B_z & 0 & -B_x \\
-\frac{E_z}{c} & -B_y & B_x & 0
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

## Decomposition into Symmetric and Antisymmetric Parts:

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

## Tensors $ \delta_{ij} $ and $ \epsilon_{ijk} $:

### Permutation Symbol and Permutation Tensor:

The permutation symbol $ \epsilon_{ijk} $ is a three-index object defined as:

```{math}
\epsilon_{ijk} = \begin{cases} 
+1 & \text{if } (i,j,k) \text{ is an even permutation of } (1,2,3), (2,3,1), (3,1,2) \\
-1 & \text{if } (i,j,k) \text{ is an odd permutation of } (1,3,2), (3,2,1), (2,1,3) \\
0 & \text{if } i = j \text{ or } i = k \text{ or } j = k 
\end{cases}
```

The permutation symbol satisfies the following relations:

```{math}
\epsilon_{ij} \epsilon_{ijk} = \epsilon_{ijk} \epsilon_{ijk} = \epsilon_{ijk} \epsilon_{pqr} = \delta_{ij} \delta_{ip} \delta_{jq} \delta_{kr}
```

In the new coordinate system:

```{math}
\epsilon_{ijk}' = L_{li} L_{mj} L_{nk} \epsilon_{lmn}
```

---

### Applications of $ \epsilon_{ijk} $:

**Example 1: Vector Product of $ a $ and $ b $:**

```{math}
\mathbf{c} = a \times b = 
\begin{pmatrix}
C_{11} & C_{12} & C_{13} \\
C_{21} & C_{22} & C_{23} \\
C_{31} & C_{32} & C_{33}
\end{pmatrix}
```

```{math}
c = \epsilon_{ijk} a_i b_j = \epsilon_{klm} b_l c_m
```

**Example 2: Double Vector Product:**

```{math}
d = [a \times (b \times c)] = \epsilon_{ijk} a_i (b \times c)_k
```

Using:

```{math}
\epsilon_{ijk} \epsilon_{klm} = \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl}
```

We can find:

```{math}
d = a \times (b \times c) = (a \cdot c)b - (a \cdot b)c
```

**Exercise:** Find an explicit expression for the $ i $-th component of $ \mathbf{r} \times (\mathbf{r} \times \mathbf{a}) $ using the properties of the tensor $ \epsilon_{ijk} $.

---

## Isotropic Tensor:

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

### Proof of the Quotient Law for $ N = M = 2 $

Assume that

```{math}
A_{jk} B_{ik} = C_{ji}
```

holds for all rotated coordinate systems and for any second-order tensor $ B $. Consider the transformation in a new coordinate system:

```{math}
A'_{jk} B'_{ik} = L_{jp} L_{iq} C_{pq} = L_{jp} L_{iq} A_{pr} B_{rq} = L_{jp} L_{iq} A_{pr} L_{uq} L_{vr} B'_{uv} = L_{jp} (L_{iq} L_{uq}) L_{vr} A_{pr} B'_{uv} = L_{jp} ( \cdots) \cdots
```

Comparing the left and right sides:

```{math}
A'_{jk} B'_{ik} - L_{jp} L_{vr} A_{pr} B'_{uv} = 0
```

and note that subscripts $ k $ and $ v $ are dummy subscripts. Hence, the above equality can be rewritten as:

```{math}
(A'_{jk} - L_{jp} L_{kr} A_{pr}) B'_{ik} = 0
```

Since we assumed that $ B $ is arbitrary, we conclude that:

```{math}
A'_{jk} = L_{jp} L_{kr} A_{pr}
```

Thus, the components $ A_{pr} $ transform as components of a tensor.

### Exercise

Show that if

```{math}
A_{ik} B_{k} = C_{i}
```

holds for any vector $ B $ and for a vector $ C $, then $ A $ is a second-order tensor.

---

## Physical Applications of Tensors

### Tensor or Inertia

Consider a collection of interconnected points $ \alpha $ with masses $ m_\alpha $ (neglecting the masses of the connectors). The orbital momentum of this system is defined as:

```{math}
L = \sum_\alpha \left( \mathbf{r}_\alpha \times \mathbf{p}_\alpha \right) = \sum_\alpha m_\alpha \left( \mathbf{r}_\alpha \times \left( \boldsymbol{\omega} \times \mathbf{r}_\alpha \right) \right)
```

For continuous bodies, substitute the summation over $ \alpha $ with integration over $ dm $. Find the explicit expression for the $ i $-th component of $ L $:

```{math}
\sum_\alpha m_\alpha \left( \epsilon_{ijk} x_{\alpha j} (\boldsymbol{\omega} \times \mathbf{r}_\alpha)_k \right)
= \sum_\alpha m_\alpha \left( \epsilon_{ijk} \epsilon_{klm} x_{\alpha j} \boldsymbol{\omega}_l x_{\alpha m} \right)
= \sum_\alpha m_\alpha \left( -\epsilon_{ilm} x_{\alpha j} x_{\alpha m} \right) \boldsymbol{\omega}_l
= I_{il} \boldsymbol{\omega}_l
```

where the components $ I_{ij} $ are called the components of the tensor of inertia. Since $ L $ and $ \boldsymbol{\omega} $ are vectors, $ I_{ij} $ are components of a true second-order tensor. By construction, $ I_{ij} $ is a symmetric tensor.

### Kinetic Energy of a Rotating System

For a fixed rotation axis, the kinetic energy is given by:

```{math}
T = \frac{1}{2} \int \rho \mathbf{v}^2 \, dV = \frac{1}{2} \int I_{ij} \omega_i \omega_j \, dm
```

---

### Strain Tensor

In the case of deformation, consider a small element of an elastic body subjected to deformation. Let the distance between two points before and after deformation be given by:

```{math}
d\ell = \sqrt{dx_1^2 + dx_2^2 + dx_3^2}, \quad d\ell' = \sqrt{(dx_1')^2 + (dx_2')^2 + (dx_3')^2}
```

The relationship between the two can be expressed as:

```{math}
(d\ell')^2 = (d\ell)^2 + 2 u_{ik} dx_i dx_k
```

where $ u_{ik} $ is the strain or deformation tensor.

---

### Stress Tensor

Stress is defined as the average force per unit area of a surface within a deformable body. The ith component of the total force acting on a volume $ V $ is given by:

```{math}
F_i = \int F_i \, dV
```

The stress tensor $ \sigma_{ik} $ relates the force to the strain:

```{math}
\sigma_{ik} = -p \delta_{ik}
```

where $ p $ is the pressure applied to the body.

---

### Elastic Constants

The stress and strain tensors are related by:

```{math}
\sigma_{ij} = c_{ijkl} \, u_{kl}
```

The 4th-order tensor $ c_{ijkl} $ is called the stiffness tensor or elastic tensor, and its components are the elastic constants. The stiffness tensor has 81 components, but only 21 independent components are needed due to symmetry considerations.
