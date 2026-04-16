- A matrix with 0 as its determinant is a singular matrix and non-singular otherwise

### Condition of a Matrix
> The condition of a matrix is a measure of how sensitive its solutions are to changes in its input data.
> 
> For example, consider the quadratic form $Q(x) = x^T A^{−1}x$. If small changes in x produce large changes in Q(x), then matrix A is said to be ill-conditioned.
> 
> $Condition Number = \frac{\lambda_{max}}{\lambda_{min}}$

- To make a non-symmetric square matrix $Q$ to be symmetric we use $\frac{1}{2}(Q+Q^T)$ 

### Quadratic Form to Symmetric Matrix Formula
 - For a general quadratic form:
$$f(\mathbf{X}) = a x_1^2 + b x_2^2 + c x_3^2 + 2d x_1 x_2 + 2e x_1 x_3 + 2f x_2 x_3$$

 - The corresponding symmetric matrix $A$ is:
$$A = \begin{bmatrix} a & d & e \\ d & b & f \\ e & f & c \end{bmatrix}$$

### Definitions of Matrix Definiteness
* **Positive Definite:** $X^T QX > 0$ for all $x \neq 0$
  * Example: $Q = \begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}$

* **Positive Semi-definite:** $x^T Qx \ge 0$ for all $x$, and there exists $x \neq 0$ such that $x^T Qx = 0$
  * Example: $Q = \begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}$

* **Negative Definite:** $x^T Qx < 0$ for all $x \neq 0$
  * Example: $Q = \begin{bmatrix} -2 & 1 \\ 1 & -2 \end{bmatrix}$

* **Negative Semi-definite:** $-Q$ is positive semi-definite
  * Example: $Q = \begin{bmatrix} -1 & 1 \\ 1 & -1 \end{bmatrix}$

* **Indefinite:** When $x^T Qx < 0$ for some $x$ and $x^T Qx > 0$ for some other $x$
  * Example: $Q = \begin{bmatrix} 1 & 1 \\ 1 & -1 \end{bmatrix}$



### Principal Minors
- A matrix is positive definite if all of its leading principal determinants are strictly positive.
- You can immediately identify an indefinite matrix if at least two of its diagonal elements have opposite signs (e.g., one is positive and one is negative).
* **Principal Minor:** A principal minor of order $k$ of an $n \times n$ matrix $Q$ is a sub-matrix obtained by deleting any $n-k$ rows and their corresponding columns.
* **Principal Determinant:** The determinant of a principal minor. There are $2^n - 1$ principal determinants for an $n \times n$ matrix.
* **Leading Principal Minor:** Obtained specifically by deleting the *last* $n-k$ rows and their corresponding columns.
* **Leading Principal Count:** The total number of leading principal determinants of an $n \times n$ matrix is $n$.
---
* **Positive Definite:** All diagonal elements $> 0$. All leading principal determinants $> 0$.
* **Positive Semi-definite:** All diagonal elements $\ge 0$. All principal determinants $\ge 0$.
* **Negative Definite:** Test $-Q$ for positive definiteness. (Leading principal determinants of $Q$ will alternate signs, starting with negative: $-, +, -, + \dots$)
* **Negative Semi-definite:** Test $-Q$ for positive semi-definiteness.
* **Indefinite:** At least two diagonal elements have opposite signs.



## Convex Sets
- A set S is convex if for any two points in the set, the line joining those two points is also entirely within the set.
- A set S is convex if for any two vectors x and y in S, the vector $x = λx + (1−λ)y$ is also in S for any λ between 0 and 1.
- An extreme point of a convex set is a point that cannot be expressed as a convex combination of any other two points in the set.


### Theorems
- The necessary condition for the continuous function $f(x)$ to have an extreme point at $x = x_0$ is that the gradient $\nabla f(x) = 0$. That is:
$$\frac{\partial f(x_0)}{\partial x_1} = \frac{\partial f(x_0)}{\partial x_2} = \cdots = \frac{\partial f(x_0)}{\partial x_n} = 0$$
- A sufficient condition for a stationary point $x_0$ to be an extreme point is that the Hessian matrix $H(x)$, evaluated at $x_0$, is:
	1. Positive definite when $x_0$ is a minimum point, and
	2. Negative definite when $x_0$ is a maximum point.