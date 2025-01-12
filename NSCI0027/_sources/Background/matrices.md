# Matrix Methods

## Linear Simultaneous Equations

Lets consider a system of linear simultaneous equations, beginning with two unknowns and two equations:

```{math}
:label: 2ndorderlinerSE
a x + by &= c \\
d x + ey &= f 
```

In order to solve this system, lets think about the standard steps:

1. Rearrange to make one variable the subject of one of the equations, e.g.:
```{math}
x = \frac{c-by}{a}
```

2. Substitute into the second equation, e.g.:
```{math}
d\left( \frac{c-by}{a}\right) + ey = f
```

3. Rearrange to find value of one variable, e.g.:
```{math}
cd - bdy + aey = af \Rightarrow y = \frac{af - cd}{ae - bd}
```

4. Back substitute to find the value of the other variable. e.g.:
```{math}
x = \frac{c-by}{a} = \frac{c - b\left(\frac{af - cd}{ae - bd}\right)}{a} = \frac{ace - bcd - abf + bcd}{a(ae - bd)} \Rightarrow x= \frac{ce - bf}{ae-bd}
```

We see that there is a common quantity $ae - bd$ appearing in both solutions.  

We can use this simple example to set up a new system for organising the information stored in simultaneous equations, lets call this object $\mathbf{A}$ and write it down as:

```{math}
\mathbf{A} = \begin{pmatrix} a & b \\ d & c\end{pmatrix}
```

We notice that it looks a bit like a column vector but it now has two columns! We call this array of numbers **a matrix**.  

We can see that $\mathbf{A}$ encodes the left hand side coefficients of {eq}`2ndorderlinerSE`, it would also be good to encode the inputs to these equations:
```{math}
\mathbf{b} = \begin{pmatrix} x \\ y \end{pmatrix}
```

and the outputs to these equations:
```{math}
\mathbf{c} = \begin{pmatrix} c \\ f \end{pmatrix}
```
which we have encoded as regular column vectors.  We can now aim to encode the full set of equations using $\mathbf{A}\,\mathbf{b} = \mathbf{c}$ which would look like:
```{math}
\begin{pmatrix} a & b \\ d & c\end{pmatrix}\, \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} c \\ f \end{pmatrix}\Longleftrightarrow \begin{cases} a x + by = c \\
d x + ey = f \end{cases}
```

We see that this sort of equation can work, if we accept that the manner in which we perform the multiplication of these sorts of objects looks a little different (c.f. vector algebra and multiplication is also a little different to regular number algebra and multiplication).



## An Introduction to Matrices


A matrix <b>(plural: matrices)</b> is essentially just an array of values, arranged in rows and columns. 

Two example matrices are given below

```{math}
:label: square_matrix
\left( \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right) \qquad \left[ \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right]
```

It is important that you do not use commas to separate the elements, which is incorrect notation.

Either square or round brackets can be used to denote a matrix - but you should avoid mixing notation. Other types of brackets cannot be used, so none of the expressions below are matrices. In fact, the third expression has a special meaning, as we will see later.

\begin{align}\begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \qquad \left\{ \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right\} \qquad \left| \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right|	\end{align}

### Terminology

The matrix featured in {eq}`square_matrix` is referred to as a square matrix because it has the same number of rows and columns. We also can say that it is a (2x2) matrix, because it has two rows and two columns.

The number of rows must be given first:

$ \left( \begin{matrix} 1 & -3 & 5\\ 2 & -1 & 7\end{matrix} \right) $  is a (2 x 3) matrix, $ \left( \begin{matrix} 1 & -3 \\ 2 & -1 \\ 5 & 7\end{matrix} \right) $ is a (3 x 2) matrix.

This measurement is properly referred to as the **order** of a matrix, but is also often referred to as the **size**.

The individual values in a matrix are called **elements**, so in the matrix $ M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) $ we can say that the element in the $2^{nd}$ row and $3^{rd}$ column is the number 6. Subscripts can be used to refer to the elements, by writing $ M_{2,3} = 6$ for example.

The **transpose** of a matrix, written with a superscript letter T, means that we swap the rows and columns, as in the example given below:

$ M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) \Rightarrow M^T = \left( \begin{matrix} 1 & 4 \\ 2 & 5  \\ 3 & 6\end{matrix} \right)$

In element notation, for any matrix $X$, we can write that $\left(X^T\right)_{i,j} = X_{j,i}$.

That is, the element in the $i^{th}$ row and $j^{th}$ column of $X$ becomes the element in the $j^{th}$ row and $i^{th}$ column of $X^T$.

The order of a matrix is reversed when it it transposed.

In a square matrix, two diagonals are called the **main diagonal** (top-left two bottom right), and the **anti-diagonal** (bottom-left to top-right). Square matrices for which $A_{i,j}=A_{j,i}$ are called **symmetric matrices**.

An **upper-triangular matrix** is a square matrix in which the elements below the main diagonal are all zero, and a **lower-triangular matrix** is one where the elements above the main diagonal are all zero.

A **diagonal matrix** is one in which all of the elements are zero apart from those on the main diagonal. These type of matrices are very special, since they have "nice" properties for the purpose of matrix algebra.    

```{exercise}
:label: q_matrix_definitions

1\. What is the order of each of the matrices shown?

$A=\left(\begin{array}{cc}0 & -1 \\2 & 3 \\-1 & 0 \\\end{array}\right)$,   $b=\left(\begin{array}{c}1 \\2 \\3 \\\end{array}\right)$,   $c=0$.

2\. Given the matrix $X=\left(\begin{array}{ccc}-3 & 4 & 0 \\1 & 1 & 2 \\7 & -4 & 3 \\\end{array}\right)$, what element is represented by $(X^T)_{2,3}$ ?

3\. Which of the following matrices is an upper-triangular matrix?

$A=\left(\begin{array}{cccc}2&8&-1&0\\0&2&2&2\\0&0&1&-5\\0&0&0&3\end{array}\right)$, $B=\left(\begin{array}{cccc}1&-2&5&2\\3&6&-2&0\\8&2&0&0\\-2&0&0&0\end{array}\right)$, $C=\left(\begin{array}{ccc}6&0&0\\-3&-4&0\\2&7&7\end{array}\right)$.

```

## Matrix algebra

We will look at how real number algebra, such as addition and multiplication, can be extended to work with matrices. These are entirely human constructs, and you may be easily forgiven for asking why do we do it this way?

However, the best way to appreciate the practicalities is by tackling some problems, and so the definitions will first be introduced without much explanation. From a mathematical perspective, we simply note that the definitions must be consistent and well-determined (unambiguous).

### Multiplication by a scalar

Let $\lambda$ be a scalar (a single number) and $M$ be a matrix. Then $\lambda M$ means that every element in matrix $M$ is multiplied by $\lambda$. This can be written in element notation as follows:

$$ (\lambda M)_{i,j} = \lambda M_{i,j}$$

For example, $ -3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) = \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right) $.

### Addition

Let $A$ and $B$ be two matrices of the same order. Then,

$$\left(A + B\right)_{i,j} = A_{i,j} + B_{i,j}$$

The expression states that to add two matrices, we add together the corresponding elements. This type of operation on two matrices can be referred to as an element-wise operation.

For example, $ \left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) + \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right) = \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right) $.


The element-wise property means that only matrices of the same order can be added, and the expressions below are both meaningless:

$$ \left( \begin{matrix} 1 & 2 \end{matrix} \right) + \left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right) $$

$$\left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right) + 1 $$

Matrix addition can be combined with multiplication by a scalar to add multiples of one matrix to another.

For example, $ \left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) - 3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) = \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right) $.

```{exercise}
:label: q_matrix_arithmetic

Given the matrices $A=\left(\begin{array}{cc}1 & 2 \\-1 & 0 \\3 & 1 \\\end{array}\right)$, $B=\left(\begin{array}{cc}-4 & 1 \\1 & 2 \\-2 & 3 \\\end{array}\right)$, $C=\left(\begin{array}{cc}0 & 3 \\4 & 2 \\1 & 1 \\\end{array}\right)$, $D=\left(\begin{array}{cc}5 & 1 \\3 & 2 \\\end{array}\right)$, what will be the result of the following expressions?

1. $\left(A+B\right)+C$
2. $(C+B)+A$
3. $A-2B+\frac{1}{2}C$
4. $A+D$

```

### Matrix multiplication

To multiply two matrices together, their inner dimensions must be the same. That is, to calculate $ AB $, the number of columns in $A$ must be the same as the number of rows in $B$. The order of the product matrix is given by the outer dimensions of the two matrices. We can represent this result visually:

![The (i,j)th element in the product AB is given by the product sum of row i from matrix A with column j of matrix B](../Figures/matrixordermultiplication.png)


```{admonition} Matrix Multiplication

Given a $(p × r)$ matrix $A$ and a $(r × q)$ matrix $B$, the matrix product $AB$ defines a $(p × q)$ matrix,

<div style="width:25%; margin: auto;">

![Two matrices A,B can be multiplied if their inner dimensions agree. The dimensions of the result is given by the outer dimensions of AB](../Figures/MatrixDimensions.png)

</div>

whose elements are given by:

$$ \left(A B\right)_{i,j} = \sum_k  A_{i,k} B_{k,j} $$


```

To perform matrix multiplication, we must take elements in a row on the left hand side matrix and multiply with elements in a column on the right hand side matrix. The process is illustrate graphically here for a (2 x 2 ) example:

![The (i,j)th element in the product AB is given by the product sum of row i from matrix A with column j of matrix B](../Figures/MatrixMultiplicationExpanded.png)


```{exercise}
:label: q_matrix_multiplication

Given that

$A=\left(\begin{array}{ccc}3 & 1 & -2 \\0 & 2 & 4 \\\end{array}\right)$,   $B=\left(\begin{array}{cc}2 & 3 \\-3 & 0 \\1 & 1 \\\end{array}\right)$,   $C=\left(\begin{array}{cccc}1 & -8 & 2 & 11 \\0 & 4 & -3 & -7 \\6 & 1 & 8 & 1 \\\end{array}\right)$,    $D=\left(\begin{array}{ccc}1 & 2 & 3 \\1 & 1 & 1 \\2 & 0 & 1 \end{array}\right)$,

1. Calculate $AB$ and $BA$. Are these results the same?
2. Explain why the result $A\left(\begin{array}{c}1\\2\end{array}\right)$ cannot be calculated.
3. What will be the order of the matrix $A C$?
4. Calculate the element in the second row and third column of $AC$
5. Calculate the result $D^2$ (this question is a bit boring, but good practice!)
```

```{admonition} Example: Walk Lengths
:class: dropdown

Consider the connected graph below, in which the vertices have been numbered 1-4:

![A graph with 4 connected vertices](../Figures/network1.png)

The graph can be represented by an adjacency matrix $A$ in which element $A_{i,j}$ is either 1 or 0 identifying if  vertex $i$ is or is not connected to vertex $j$. For this graph we have:

$$A=\left(\begin{array}{cccc}0 & 1 & 1 & 0 \\1 & 0 & 1 & 1 \\1 & 1 & 0 & 1 \\0 & 1 & 1 & 0 \\\end{array}\right)$$

It can be proved by induction that the result $S^N$ tells us how many $N$-step paths there are between each pair of vertices (see inductive step outline below). Therefore, if we want the number of 3-step paths between each pair of vertices, we can compute

$$M^3=\left(\begin{array}{cccc}2 & 5 & 5 & 2 \\5 & 4 & 5 & 5 \\5 & 5 & 4 & 5 \\2 & 5 & 5 & 2 \\\end{array}\right)$$

For instance, there are 5 walks of length 3 between vertices 1 and 2. Can you find them all?

**Inductive step outline:**

If $S^{N-1}$ gives all walks of length $N-1$ between pairs of vertices, then the following result gives the number of paths starting at node $i$ and ending at vertex $j$, obtained by taking one extra step from each connected vertex:

$$S^N_{i,j}=S^{N-1}_{i,1}S_{1,j}+S^{N-1}_{i,2}S_{2,j}+S^{N-1}_{i,3}S_{3,j}+S^{N-1}_{i,4}S_{4,j}$$
```

### Properties of Matrix Multiplication

Matrix multiplication is **associative**, that is

$$A (B C)\equiv (A B)C$$

This can be proved by showing that the left and right hand sides are the same order, and that $(A(B C))_{i,j}=((A B)C)_{i,j}$.

Matrix multiplication is **NOT commutative**, that is

$$\begin{array}{c}A B\neq B A \end{array}$$

(although the  $AB$ and $BA$ may be equal in some special cases).

```{warning}
For two matrices $A$ and $B$, in general $AB \neq BA$.

Forgetting the matrix multiplication is non-commutative leads to disaster!
```

```{admonition} Example
:class: tip, dropdown
**Worked example illustrating non-commutative property**

$$\left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right) \left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right)=\left(\begin{array}{cc}1\ 2+2\ 1 & 1\ 1+2\ 2 \\0\ 1-3\ 2 & 0\ 2-3\ 1\end{array}\right)=\left(\begin{array}{cc}4 & 5 \\-6 & -3 \\\end{array}\right)$$

$$\left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right) \left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right)=\left(\begin{array}{cc}2\ 1+1 (-3) & 2\ 2+1\ 0 \\1\ 1+2 (-3) & 1\ 2+2\ 0 \end{array}\right)=\left(\begin{array}{cc}-1 & 4 \\-5 & 2 \\\end{array}\right)$$
```


## Matrix Inverses

Since a matrix represents a linear transformation, which is a function, we can consider if a matrix has an inverse. For example, consider the $(2 \times 2)$ matrix $R_{\pi/2}$ which represents a $\pi/2$ anticlockwise rotation about the origin:

$$R_{\pi/2} = \begin{pmatrix}0 & -1 \\1 & 0\end{pmatrix}.$$

Its inverse is a $\pi/2$ *clockwise* rotation about the origin, represented by the following matrix:

$$R_{3\pi/2} = \begin{pmatrix}0 & 1 \\-1 & 0\end{pmatrix}.$$


```{figure} ../Figures/linear_transformations_8_0.png
---
width: 600px
name: inverse_transformation
---
If the matrix $A = R_{\pi/2}$ is a $\pi/2$ anticlockwise rotation about the origin then its inverse $A^{-1} = R_{3\pi/2}$ is a $\pi/2$ clockwise rotation about the origin. The matrix $A^{-1}A = I$ represents the identity transformation.
```

In general, if $A$ is an $n \times n$ matrix and $B$ is its inverse, then $B$ is also an $(n \times n)$ matrix which satisfies

$$ABx = x$$

for all $x \in \mathbb{R}^n$.

In other words, $AB$ is a matrix which leaves $x$ unchanged. The only matrix which leaves $x$ unchanged is the identity matrix $I$, and so we have the following definition of the inverse matrix.

```{admonition} Definition

Let $A$ be an $(n \times n)$ square matrix. If there is an $(n \times n)$ matrix $B$ such that

$$AB = BA = I_n$$

then $A$ is **invertible** and $B$ is the **inverse** of A.

We write $B = A^{-1}$.
```


```{exercise}
:label: q_matrix_inverse_1

1. Show that $R_{3\pi/2}$ is the inverse of $R_{\pi/2}$.
2. What is the inverse of the matrix $R_{\theta}$ representing an anticlockwise rotation about the origin by $\theta$? Calculate $R_{\theta}R_{\theta}^{-1}$ and show that it equals the identity matrix.
3. Given that $C X D = E$, write down the solution for $X$ explicitly in terms of inverse matrices $C^{-1}$ and $D^{-1}$.
```

## Solving Matrix Equations

Suppose that we are given the definitions below and asked to compute the result for $B$ :

$$A=\left(\begin{array}{cc}1 & 2 \\2 & 1 \end{array}\right), \quad A B=\left(\begin{array}{cc}5 & 3 \\4 & 3 \end{array}\right)$$ (a_ab)

If this was ordinary scalar algebra, then $B$ would be given by $\frac{AB}{A}$, but we have not defined the concept of division for matrices. Indeed, we should recognise a difficulty in doing so, since matrix multiplication is not commutative. The problems $Q X = P$ and $X Q=P$ do not generally have the same solution, and so the expression $X=\frac{P}{Q}$ would be ambiguous.

The difficulty could be addressed by introducing separate concepts of "left-division" and "right-division", and some authors have done exactly this. However, a more fundamental approach is to abandon the idea of division for matrices altogether, and consider what it means for matrix multiplication to be invertible.

To illustrate the use of the inverse matrix, we multiply each side of the equation for $A B$ in {eq}`a_ab` by $A^{-1}$ as follows:

$$A^{-1}(AB)=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right)$$ (a_inverse_ab)

It is very important to recognise that we must do exactly the same thing to both sides of the equation. Since we pre-multiply (left multiply) the left-hand side by $A^{-1}$, we must also pre-multiply the right-hand side by $A^{-1}$.

Due to the non-commutative nature of matrix multiplication, the result $A^{-1}(A B)$ is not the same as the result $(A B)A^{-1}$.

Now, since matrix multiplication is associative, the left hand side of {eq}`a_inverse_ab` can be rewritten as $(A^{-1} A)B$, and by the definitions of the inverse and identity matrix, we can write $(A^{-1} A)B=I B=B$ in order to obtain

$$B=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right)$$

Thus, the result for $B$ can be determined by performing a matrix multiplication, provided that we can find $A^{-1}$.

```{admonition} Solving $AX=B$ and $XA=B$

Let $A$ be an invertible $(n \times n)$ square matrix and $B$ an ($n \times m)$ matrix. Then

$A X = B$ has solution $X=A^{-1}B $

$X A = B$ has solution $X=B A^{-1}$.
```

## Calculating the (2x2) inverse

The (2x2) matrix that satisfies the definition $A A^{-1} = A^{-1}A=I$ is outlined in the box below. In section 3.6 we will examine how the result may be derived from first principles, but for now you may simply verify the claim by checking the result of the products $A A^{-1}$ and $A^{-1}A$.

```{admonition} The inverse of a (2x2) matrix

The inverse of a (2x2) matrix $A=\left(\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right)$ is given by

$$A^{-1}=\frac{1}{\mathrm{det}(A)}\mathrm{adj}(A)$$

where

$$\mathrm{det}(A)=\left|\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right|=a_{11} a_{22}-a_{12} a_{21}$$

and

$$\mathrm{adj}(A)=\left(\begin{array}{cc}a_{22} & -a_{12} \\-a_{21} & a_{11} \end{array}\right)$$

Note that $\text{det}(A)$ is a scalar quantity.

$\text{det}(A)$ s referred to as the **determinant** of $A$. For a (2x2) matrix, the determinant is given by subtracting the product of the anti-diagonal elements from the product of the leading diagonal elements.  

$\text{adj}(A)$ is known as the **adjugate matrix**. For a (2x2) matrix, the adjugate is given by swapping the diagonal elements and multiplying the anti-diagonal elements by -1.

Notice the special notation $|A|$ that is used to denote the determinant of $A$.
```

```{exercise}
:label: q_twobytwo_inverse

1\. 	Calculate the determinant of the matrix $M=\left(\begin{array}{cc}2 & -1 \\3 & 4 \end{array}\right)$.

2\. 	Write the equations below in the form $Ax=b$:
\begin{align*}
2x-3y&=1\\
3x-2y&=2
\end{align*}

Calculate the coefficient matrix $A$ and hence obtain the solution for $x$

3\.	Solve the problem given in {eq}`a_ab` to find B.

```

