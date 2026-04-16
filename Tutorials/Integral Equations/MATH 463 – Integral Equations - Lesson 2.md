
## Converting Integral Equations

---

## 1. Volterra Integral Equation – 1st Kind

**Definition:** An integral equation of the form

$$f(x) = \int_0^x k(x,t)\, u(t)\, dt$$

where $u(x)$ is the unknown function, $k(x,t)$ is the kernel, and $f(x)$ is a known function. The unknown $u(x)$ appears *only inside* the integral.

---

## 2. Volterra Integral Equation – 2nd Kind

**Definition:** An integral equation of the form

$$F(x) = u(x) + \int_0^x K(x,t)\, u(t)\, dt$$

where the unknown $u(x)$ appears *both outside and inside* the integral.

---

## 3. Converting 1st Kind → 2nd Kind

**Method:** Differentiate both sides using the **Leibniz Integral Rule**.

$$\frac{d}{dx}\left\{ f(x) = \int_0^x k(x,t)\,u(t)\,dt \right\}$$

$$f'(x) = k(x,x)\,u(x) + \int_0^x k'(x,t)\,u(t)\,dt$$

Dividing through by $k(x,x)$:

$$\underbrace{\frac{f'(x)}{k(x,x)}}_{F(x)} = u(x) + \int_0^x \underbrace{\frac{k'(x,t)}{k(x,x)}}_{K(x,t)} u(t)\,dt$$

> **Requirement:** $k(x,x) \neq 0$

---

## 4. Converting Volterra IE → Ordinary Differential Equation (ODE)

**Method:** Apply the Leibniz rule repeatedly until the integral sign is fully removed. Initial conditions are recovered by substituting $x = 0$ into the integral equation.

**Leibniz Integral Rule (general form):**

$$\frac{d}{dx}\int_{\alpha(x)}^{\beta(x)} K(x,t)\,\mu(t)\,dt = K(x,\beta)\,\beta'(x) - K(x,\alpha)\,\alpha'(x) + \int_{\alpha(x)}^{\beta(x)} \frac{\partial K}{\partial x}\,\mu(t)\,dt$$

---

## 5. Converting Initial Value Problem (IVP) → Volterra IE

**Key Reduction Formula** (collapses $n$-fold nested integrals into one):

$$\int_0^x\int_0^{x_1}\cdots\int_0^{x_{n-1}} f(x_n)\,dx_n\cdots dx_1 = \frac{1}{(n-1)!}\int_0^x (x-t)^{n-1} f(t)\,dt$$

**Special cases:**

| Nested integral | Single integral |
|---|---|
| $\int_0^x\int_0^x f(t)\,dt\,dt$ | $\int_0^x (x-t)\,f(t)\,dt$ |
| $\int_0^x\int_0^x\int_0^x f(t)\,dt\,dt\,dt$ | $\dfrac{1}{2}\int_0^x (x-t)^2 f(t)\,dt$ |

---

## 6. General Procedure: IVP (3rd Order)→ Volterra IE 

Given: $y''' + p(x)y'' + q(x)y' + r(x)y = g(x)$, with $y(0)=\alpha,\ y'(0)=\beta,\ y''(0)=\gamma$

**Step 1:** Set $y'''(x) = u(x)$

**Step 2:** Integrate successively to express $y'', y', y$ in terms of $u(x)$:

$$y''(x) = \gamma + \int_0^x u(t)\,dt$$

$$y'(x) = \beta + \gamma x + \int_0^x (x-t)\,u(t)\,dt$$

$$y(x) = \alpha + \beta x + \frac{\gamma x^2}{2} + \frac{1}{2}\int_0^x (x-t)^2 u(t)\,dt$$

**Step 3:** Substitute into the ODE → Volterra IE of the 2nd kind:

$$u(x) = f(x) + \int_0^x k(x,t)\,u(t)\,dt$$

where:

$$k(x,t) = -\left[p(x) + q(x)(x-t) + \frac{r(x)}{2}(x-t)^2\right]$$

$$f(x) = g(x) - \left[\gamma p(x) + \beta q(x) + \alpha r(x) + \gamma x\, q(x) + r(x)\!\left(\beta x + \frac{\gamma x^2}{2}\right)\right]$$

---

## Key Terms Glossary

| Term | Meaning |
|---|---|
| **Kernel** $k(x,t)$ | The function inside the integral that weights $u(t)$ |
| **1st kind Volterra IE** | Unknown $u$ appears only inside the integral |
| **2nd kind Volterra IE** | Unknown $u$ appears both inside and outside the integral |
| **Leibniz Rule** | Rule for differentiating under the integral sign |
| **Reduction formula** | Converts $n$ nested integrals into one single integral |

---

## Tags
#math463 #integral-equations #volterra #ODE #IVP #leibniz-rule #KNUST