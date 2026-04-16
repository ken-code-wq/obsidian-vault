
---

## 1. Fredholm's Integral Equation with a Separable Kernel

**Definition:** An integral equation where the kernel $k(x,t)$ can be separated into a product of two functions, each depending on a single variable:

$$k(x,t) = g(x)h(t)$$

**Method for Exact Solution:**
Given the equation $u(x) = f(x) + \lambda\int_{a}^{b} k(x,t)\, u(t)\, dt$:
1. Substitute the separable kernel: $u(x) = f(x) + \lambda\int_{a}^{b} g(x)h(t)\, u(t)\, dt$.
2. Factor out $g(x)$ from the integral: $u(x) = f(x) + \lambda g(x)\int_{a}^{b} h(t)\, u(t)\, dt$.
3. Since the integral has constant limits, it evaluates to a constant $c$:
   $$c = \int_{a}^{b} h(t)\, u(t)\, dt$$
4. Express the solution as: $u(x) = f(x) + \lambda g(x)c$.
5. Find $c$ by substituting $u(t) = f(t) + \lambda g(t)c$ into the definition of $c$:
   $$c = \int_{a}^{b} h(t)\left[f(t) + \lambda g(t)c\right] dt$$

---

## 2. Fredholm's Integral Equation with a Degenerate Kernel

**Definition:** A kernel that can be expressed as a finite sum of separable kernels:

$$k(x,t) = \sum_{i=1}^{n} g_{i}(x)h_{i}(t)$$

**Method for Exact Solution:**
1. Substitute the expanded sum into the integral:
   $$u(x) = f(x) + \lambda\int_{a}^{b} \left[g_{1}(x)h_{1}(t) + \dots + g_{n}(x)h_{n}(t)\right] u(t)\, dt$$
2. Break into separate integrals and let $c_{i} = \int_{a}^{b} h_{i}(t)\, u(t)\, dt$.
3. Form the general solution:
   $$u(x) = f(x) + \lambda g_{1}(x)c_{1} + \lambda g_{2}(x)c_{2} + \dots + \lambda g_{n}(x)c_{n}$$
4. Substitute $u(t)$ back into each $c_{i}$ integral to create a system of algebraic equations, solve for all $c_{i}$, and plug them back to complete the solution.

---

## 3. Eigen Values of a Homogeneous Fredholm's Integral Equation

**Definition:** For a homogeneous equation $u(x) = \lambda\int_{a}^{b} k(x,t)\, u(t)\, dt$, solving it yields a constant $c = \int_{a}^{b} h(t)\, u(t)\, dt$. If $c = 0$, it gives rise to the trivial solution.

> **Eigen Value Condition:** The eigen values are the specific values of $\lambda$ for which $u(x) \neq 0$.

---

## 4. Method of Successive Approximation to the Free Term

**Method:** Approximates the solution as a series expansion in terms of $\lambda$:
$$y(x) = \phi_{0}(x) + \lambda^{1}\phi_{1}(x) + \lambda^{2}\phi_{2}(x) + \dots + \lambda^{n}\phi_{n}(x)$$

**Iterative Steps:**
* **Base Term:** $\phi_{0}(x) = f(x)$
* **1st Approximation:** $\phi_{1}(x) = \int_{a}^{b} k(x,t)\phi_{0}(t)\, dt$
* **$n$-th Approximation:** $\phi_{n}(x) = \int_{a}^{b} k(x,t)\phi_{n-1}(t)\, dt$

> **Requirements for Validity:**
> * Both the kernel $k(x,t)$ and the free term $f(x)$ must be continuous and bounded within the limits of integration.
> * For the resulting series to converge, the absolute value of the common ratio must be less than 1 ($|r| < 1$).

---

## 5. Method of Successive Approximation to the Kernel

**Method:** Iterates on the kernel function instead of the free term, leading to the creation of a "Resolvent Kernel".

**Iterative Steps for Kernels:**
* **Base Kernel:** $k_{1}(x,t) = k(x,t)$ 
* **$n$-th Kernel:** $k_{n}(x,t) = \int_{a}^{b} k(x,s)k_{n-1}(s,t)\, ds$

**The Resolvent Kernel ($\Gamma$):**
$$\Gamma(x,t,\lambda) = \sum_{i=1}^{n} \lambda^{i-1}k_{i}(x,t)$$

**Final Solution Form:**
$$y(x) = f(x) + \lambda\int_{a}^{b} \Gamma(x,t,\lambda)\, f(t)\, dt$$

---

## Key Terms Glossary

| Term | Meaning |
|---|---|
| **Separable Kernel** | A kernel $k(x,t)$ that can be factored into $g(x)h(t)$. |
| **Degenerate Kernel** | A kernel represented as a sum of separable kernels. |
| **Trivial Solution** | Occurs when the integral constant $c = 0$, leading to $u(x)=0$. |
| **Resolvent Kernel** | Denoted as $\Gamma(x,t,\lambda)$, it is an infinite series of iterated kernels used to directly solve the integral equation. |
| **Common Ratio ($r$)** | In successive approximations, the series converges if $|r| < 1$. |

---

## Tags
#math463 #integral-equations #fredholm #eigen-values #resolvent-kernel #KNUST
