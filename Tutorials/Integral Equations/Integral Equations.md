## Definition
An **integral equation** is an equation in which an unknown function appears under one or more integral signs.

---

## General Form

$$
\mu(x) = f(x) + \lambda \int_{\alpha(x)}^{\beta(x)} K(x,t)\,\mu(t)\,dt
$$

### Components

- $\mu(x)$ → unknown function (solution to be determined)  
- $f(x)$ → free term / forcing function (known and continuous)  
- $\lambda$ → parameter (controls variation of the solution)  
- $\alpha(x), \beta(x)$ → limits of integration (constants or functions)  
- $K(x,t)$ → kernel (known and continuous function)  

---

## Kernel

A **kernel** is a known function $K(x,t)$ defined on a region in the $(x,t)$-plane.

### Types of Kernels

- **Separable Kernel**
  $$
  K(x,t) = g(x)h(t)
  $$

- **Degenerate Kernel**
  $$
  K(x,t) = \sum_{i=1}^{n} g_i(x) h_i(t)
  $$

- **Symmetric Kernel**
  $$
  K(x,t) = K(t,x)
  $$

### Properties of Symmetric Kernels

- Eigen values are real  
- Eigen functions corresponding to distinct eigenvalues are orthogonal  

---

## Classification of Integral Equations

### 1. Structure

- **Volterra Integral Equation**  
  Limits depend on $x$
  $$
  \int_{a(x)}^{b(x)} ...
  $$

- **Fredholm Integral Equation**  
  Limits are constants
  $$
  \int_{a}^{b} ...
  $$

---

### 2. Kind

- **First Kind**  
  Unknown function appears only inside the integral
  $$
  f(x) = \int K(x,t)\mu(t)\,dt
  $$

- **Second Kind**  
  Unknown function appears both inside and outside
  $$
  \mu(x) = f(x) + \int K(x,t)\mu(t)\,dt
  $$

---

### 3. Linearity

- **Linear**
  - $\mu(t)$ appears to power 1
  - No nonlinear operations

- **Nonlinear**
  - $\mu(t)^2$, $\sin(\mu(t))$, etc.

---

### 4. Singularity

- **Singular**
  - Improper integral (e.g., infinite limits)
  - $$
\int_{-1}^{1}\frac{\phi(s)}{s-t}\,ds = f(t),\qquad -1<t<1
$$

- **Non-Singular**
  - Proper integral

---

### 5. Homogeneity

- **Homogeneous**
  $$
  f(x) = 0
  $$

- **Non-Homogeneous**
  $$
  f(x) \neq 0
  $$

---

## Solution of an Integral Equation

A **solution** is a function that satisfies the equation when substituted into it, producing an identity.

---

## Leibniz Integral Rule (Differentiation Under the Integral Sign)

For
$$
\int_{a(x)}^{b(x)} f(x,t)\,dt
$$

$$
\frac{d}{dx} \left( \int_{a(x)}^{b(x)} f(x,t)\,dt \right)
=
f(x,b(x)) \cdot b'(x)
-
f(x,a(x)) \cdot a'(x)
+
\int_{a(x)}^{b(x)} \frac{\partial f(x,t)}{\partial x}\,dt
$$