# MATH 463 - Integral Equations: Fredholm Solutions

---

## 1. Fredholm's Integral Equation with a Separable Kernel

**Definition:** An integral equation where the kernel $k(x,t)$ can be separated into a product of two functions, each depending on a single variable:

[span_0](start_span)$$k(x,t) = g(x)h(t)$$[span_0](end_span)

**Method for Exact Solution:**
[span_1](start_span)Given the equation $u(x) = f(x) + \lambda\int_{a}^{b} k(x,t)\, u(t)\, dt$[span_1](end_span):
1. [span_2](start_span)Substitute the separable kernel: $u(x) = f(x) + \lambda\int_{a}^{b} g(x)h(t)\, u(t)\, dt$[span_2](end_span).
2. [span_3](start_span)Factor out $g(x)$ from the integral: $u(x) = f(x) + \lambda g(x)\int_{a}^{b} h(t)\, u(t)\, dt$[span_3](end_span).
3. Since the integral has constant limits, it evaluates to a constant $c$:
   [span_4](start_span)$$c = \int_{a}^{b} h(t)\, u(t)\, dt$$[span_4](end_span)
4. [span_5](start_span)Express the solution as: $u(x) = f(x) + \lambda g(x)c$[span_5](end_span).
5. [span_6](start_span)Find $c$ by substituting $u(t) = f(t) + \lambda g(t)c$ into the definition of $c$[span_6](end_span):
   [span_7](start_span)$$c = \int_{a}^{b} h(t)\left[f(t) + \lambda g(t)c\right] dt$$[span_7](end_span)

---

## 2. Fredholm's Integral Equation with a Degenerate Kernel

**[span_8](start_span)Definition:** A kernel that can be expressed as a finite sum of separable kernels[span_8](end_span):

[span_9](start_span)$$k(x,t) = \sum_{i=1}^{n} g_{i}(x)h_{i}(t)$$[span_9](end_span)

**Method for Exact Solution:**
1. Substitute the expanded sum into the integral:
   [span_10](start_span)$$u(x) = f(x) + \lambda\int_{a}^{b} \left[g_{1}(x)h_{1}(t) + \dots + g_{n}(x)h_{n}(t)\right] u(t)\, dt$$[span_10](end_span)
2. [span_11](start_span)Break into separate integrals and let $c_{i} = \int_{a}^{b} h_{i}(t)\, u(t)\, dt$[span_11](end_span).
3. Form the general solution:
   [span_12](start_span)$$u(x) = f(x) + \lambda g_{1}(x)c_{1} + \lambda g_{2}(x)c_{2} + \dots + \lambda g_{n}(x)c_{n}$$[span_12](end_span)
4. [span_13](start_span)Substitute $u(t)$ back into each $c_{i}$ integral to create a system of algebraic equations, solve for all $c_{i}$, and plug them back to complete the solution[span_13](end_span).

---

## 3. Eigen Values of a Homogeneous Fredholm's Integral Equation

**[span_14](start_span)Definition:** For a homogeneous equation $u(x) = \lambda\int_{a}^{b} k(x,t)\, u(t)\, dt$, solving it yields a constant $c = \int_{a}^{b} h(t)\, u(t)\, dt$[span_14](end_span). [span_15](start_span)If $c = 0$, it gives rise to the trivial solution[span_15](end_span).

> **[span_16](start_span)Eigen Value Condition:** The eigen values are the specific values of $\lambda$ for which $u(x) \neq 0$[span_16](end_span).

---

## 4. Method of Successive Approximation to the Free Term

**[span_17](start_span)Method:** Approximates the solution as a series expansion in terms of $\lambda$[span_17](end_span):
[span_18](start_span)$$y(x) = \phi_{0}(x) + \lambda^{1}\phi_{1}(x) + \lambda^{2}\phi_{2}(x) + \dots + \lambda^{n}\phi_{n}(x)$$[span_18](end_span)

**Iterative Steps:**
* **[span_19](start_span)Base Term:** $\phi_{0}(x) = f(x)$[span_19](end_span)
* **[span_20](start_span)1st Approximation:** $\phi_{1}(x) = \int_{a}^{b} k(x,t)\phi_{0}(t)\, dt$[span_20](end_span)
* **[span_21](start_span)$n$-th Approximation:** $\phi_{n}(x) = \int_{a}^{b} k(x,t)\phi_{n-1}(t)\, dt$[span_21](end_span)

> **Requirements for Validity:**
> * [span_22](start_span)Both the kernel $k(x,t)$ and the free term $f(x)$ must be continuous and bounded within the limits of integration[span_22](end_span).
> * [span_23](start_span)For the resulting series to converge, the absolute value of the common ratio must be less than 1 ($|r| < 1$)[span_23](end_span).

---

## 5. Method of Successive Approximation to the Kernel

**[span_24](start_span)Method:** Iterates on the kernel function instead of the free term, leading to the creation of a "Resolvent Kernel"[span_24](end_span).

**Iterative Steps for Kernels:**
* **[span_25](start_span)Base Kernel:** $k_{1}(x,t) = k(x,t)$ (Implied by standard notation)[span_25](end_span)
* **[span_26](start_span)$n$-th Kernel:** $k_{n}(x,t) = \int_{a}^{b} k(x,s)k_{n-1}(s,t)\, ds$[span_26](end_span)

**The Resolvent Kernel ($\Gamma$):**
[span_27](start_span)$$\Gamma(x,t,\lambda) = \sum_{i=1}^{n} \lambda^{i-1}k_{i}(x,t)$$[span_27](end_span)

**Final Solution Form:**
[span_28](start_span)$$y(x) = f(x) + \lambda\int_{a}^{b} \Gamma(x,t,\lambda)\, f(t)\, dt$$[span_28](end_span)

---

## Key Terms Glossary

| Term | Meaning |
|---|---|
| **Separable Kernel** | [span_29](start_span)A kernel $k(x,t)$ that can be factored into $g(x)h(t)$[span_29](end_span). |
| **Degenerate Kernel** | [span_30](start_span)A kernel represented as a sum of separable kernels[span_30](end_span). |
| **Trivial Solution** | [span_31](start_span)Occurs when the integral constant $c = 0$, leading to $u(x)=0$[span_31](end_span). |
| **Resolvent Kernel** | [span_32](start_span)Denoted as $\Gamma(x,t,\lambda)$, it is an infinite series of iterated kernels used to directly solve the integral equation[span_32](end_span). |
| **Common Ratio ($r$)** | In successive approximations, the series converges if $|r| [span_33](start_span)< 1$[span_33](end_span). |

---

## Tags
#math463 #integral-equations #fredholm #eigen-values #resolvent-kernel #KNUST
