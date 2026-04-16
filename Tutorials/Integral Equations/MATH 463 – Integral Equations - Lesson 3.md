# MATH 463 - Integral Equations: Major Definitions & Concepts

## 1. Types of Kernels in Fredholm's Integral Equations
* **[span_0](start_span)Separable Kernel**: A kernel that can be expressed as the product of two functions, each depending on only one variable: $k(x,t)=g(x)h(t)$[span_0](end_span).
    * [span_1](start_span)The exact solution method involves substituting a constant $c=\int_{a}^{b}h(t)u(t)dt$ back into the integral equation[span_1](end_span).
* **[span_2](start_span)Degenerate Kernel**: A kernel that is expressed as a finite sum of separable kernels: $k(x,t)=\sum_{i=1}^{n}g_{i}(x)h_{i}(t)$[span_2](end_span).

## 2. Eigen Values of a Homogeneous Fredholm's Integral Equation
* [span_3](start_span)The base homogeneous equation is given by $u(x)=\lambda\int_{a}^{b}k(x,t)u(t)dt$[span_3](end_span).
* [span_4](start_span)If the substituted constant $c=0$, it results in the trivial solution[span_4](end_span).
* **[span_5](start_span)Eigen Values**: The specific values of $\lambda$ for which there exists a non-trivial solution where $u(x)\ne0$[span_5](end_span).

## 3. Method of Successive Approximation to the Free Term
* [span_6](start_span)This method approximates the solution as a power series in terms of $\lambda$: $y(x)=\phi_{0}(x)+\lambda^{1}\phi_{1}(x)+\lambda^{2}\phi_{2}(x)+.....+\lambda^{n}\phi_{n}(x)$[span_6](end_span).
* **[span_7](start_span)Base Case**: The initial term is set to the free term, $\phi_{0}(x)=f(x)$[span_7](end_span).
* **[span_8](start_span)Recursive Step**: Subsequent terms are found using $\phi_{n}(x)=\int_{a}^{b}k(x,t)\phi_{n-1}(t)dt$[span_8](end_span).
* **Conditions for Validity & Convergence**:
    * [span_9](start_span)The kernel $k(x,t)$ and the free term $f(x)$ must be bounded and continuous within the limits of integration[span_9](end_span).
    * [span_10](start_span)The series will converge if the absolute value of the common ratio is less than 1[span_10](end_span).

## 4. Method of Successive Approximation to the Kernel
* [span_11](start_span)[span_12](start_span)This approach builds the solution by iterating on the kernel itself rather than the free term[span_11](end_span)[span_12](end_span).
* **[span_13](start_span)Iterated Kernel Formula**: $k_{n}(x,t)=\int_{a}^{b}k(x,s)k_{n-1}(s,t)ds$[span_13](end_span).
* **[span_14](start_span)Resolvent Kernel ($\Gamma$)**: Defined as the sum of these iterated kernels: $\Gamma(x,t,\lambda)=\sum_{i=1}^{n}\lambda^{i-1}k_{i}(x,t)$[span_14](end_span).
* **[span_15](start_span)Final Solution Form**: The approximated solution is then written as $y(x)=f(x)+\lambda\int_{a}^{b}\Gamma(x,t,\lambda)f(t)dt$[span_15](end_span).
