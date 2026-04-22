- A set E is said to be finite provided either it is empty or there is a natural number n for which E is equipotent to {1,...,n}
- We say that, E is countably infinite provided E is equipotent to the set N of natural numbers.
- A set that is either finite or countably infinite is said to be countable.
- If a set is equipotent to a countable set, then it is countable
-


---
tags:
  - mathematics
  - real-functions
  - exams
  - proofs
title: Real Functions I - Exam Questions and Solutions
---

# Real Functions I: Concept Archive

[cite_start]This note compiles definitions, theorems, and proofs from the Real Functions I course materials[cite: 30, 55, 89]. 

## 1. Core Definitions

* [cite_start]**Open Set**: A set $S$ of real numbers is said to be an open set provided for each $x \in S$, the interval $(a, b)$ is contained in $S$[cite: 117, 118, 122].
* [cite_start]**Closed Set**: A set $P$ is said to be closed if and only if the complement of $P$, which is $R \setminus P$, is open[cite: 127, 128, 129, 130].
* [cite_start]**Borel Set**: A Borel set is a set that can be constructed by repeatedly taking countable unions and intersections of closed or open sets[cite: 131, 136, 137, 138].
* [cite_start]**Outer Measure**: The outer measure $m^*(A)$ of a set $A$ is the infimum of all the set sums such that the sets cover $A$[cite: 141, 142, 145]. 

---

## 2. Fundamental Proofs in Measure Theory

### Monotonicity of Outer Measure
[cite_start]**Question:** If $A \subset B$, show that $m^*(A) \le m^*(B)$[cite: 21, 58, 100].

**Proof:**
* [cite_start]We have to show that $B = A \cup (B \setminus A)$[cite: 121].
* [cite_start]Therefore, $m^*(B) = m^*(A) + m^*(B \setminus A)$[cite: 121].
* [cite_start]Because measure is non-negative, this implies that $m^*(B) \ge m^*(A)$[cite: 121].
* [cite_start]Alternatively, if $A \subset U$, then $m^*(A) \le m^*(U)$[cite: 531].

### Measurability of Sets with Zero Measure
[cite_start]**Question:** Given that $E \subset R$ and $m^*(E) = 0$, show that $E$ is measurable[cite: 22, 101].

**Proof:**
* [cite_start]For any arbitrary set $A \subset R$ and $E \subset R$, the subadditivity of outer measure states $m^*(A) \le m^*(A \cap E) + m^*(A \cap \overline{E})$[cite: 125, 126, 133].
* [cite_start]Since $A \cap E \subset E$ and $m^*(E) = 0$, it implies that $m^*(A \cap E) = 0$[cite: 127].
* [cite_start]Substituting this yields $m^*(A) \ge 0 + m^*(A \cap \overline{E})$, which simplifies to $m^*(A) \ge m^*(A \cap \overline{E})$[cite: 134, 135].
* [cite_start]Hence, the set $E$ is measurable[cite: 136].

### Additivity over Disjoint Measurable Sets
**Question:** Let $A, B \in R$ with $B$ measurable and $A \cap B = \emptyset$. [cite_start]Show that $m^*(A \cup B) = m^*(A) + m^*(B)$[cite: 65, 66, 102, 103, 288, 289].

**Proof:**
* [cite_start]We can express the union as $A \cup B = ((A \cup B) \cap B) \cup ((A \cup B) \cap \overline{B})$[cite: 291].
* [cite_start]By applying outer measure, $m^*(A \cup B) = m^*((A \cup B) \cap B) + m^*((A \cup B) \cap \overline{B})$[cite: 292].
* [cite_start]Since the sets are disjoint, this evaluates to $m^*(B) + m^*(A)$[cite: 293].
* [cite_start]Therefore, $m^*(A \cup B) = m^*(A) + m^*(B)$[cite: 294].

### Translation Invariance
**Question:** Show that if $E$ is a measurable set, then each translate $E+y$ of $E$ is also measurable[cite: 37, 105, 315].

**Proof:**
* [cite_start]Let $E$ be a measurable set, $A$ be any set, and $y$ be any real number[cite: 321].
* [cite_start]Using the translation invariance of outer measure, $m^*(A) = m^*(A-y) = m^*((A-y) \cap E) + m^*((A-y) \cap \overline{E})$[cite: 323].
* [cite_start]This expression is equivalent to $m^*(A \cap (E+y)) + m^*(A \cap (E+y)^c)$[cite: 323].
* [cite_start]Hence, $E+y$ is measurable[cite: 324].

---

## 3. Functions and Integration

### Simple Functions
[cite_start]**Question:** Show that the sum and product of two simple functions are simple[cite: 44, 108, 349, 353].

**Proof Setup:**
* [cite_start]Let $A_1 = \sum_{i=1}^{N_1} a_i \chi_{F_i}$ and $A_2 = \sum_{j=1}^{N_2} b_j \chi_{F_j}$ be two simple functions[cite: 352, 354].
* [cite_start]Let $G_{ij} = F_i \cap F_j$, where $G_{ij}$ forms a disjoint family of measurable sets[cite: 354, 358, 359].
* [cite_start]**Sum:** $A_1 + A_2 = \sum_{i=1}^{N_1} \sum_{j=1}^{N_2} (a_i + b_j)\chi_{G_{ij}}$[cite: 361, 363].
* [cite_start]**Product:** $A_1 \cdot A_2 = \sum_{i=1}^{N_1} \sum_{j=1}^{N_2} a_i b_j \chi_{G_{ij}}$[cite: 364].

### Limits and Step Functions
[cite_start]**Question:** Prove that $\lim_{n \rightarrow \infty} \int_{-\infty}^{\infty} f(x) \cos(nx) dx = 0$ for every step function $f$[cite: 48, 69, 83, 112, 428, 429].

**Proof:**
* [cite_start]Consider the integral over an interval $[a, b]$: $\int_a^b \cos(nx) dx = \frac{1}{n} \sin(nx) |_a^b$[cite: 163, 443].
* [cite_start]Evaluating the bounds gives $\frac{1}{n}[\sin(nb) - \sin(na)]$[cite: 165, 444].
* [cite_start]As $n \rightarrow \infty$, this expression goes to $0$[cite: 167, 168, 180, 445].

---

## 4. Major Convergence Theorems

### Bounded Convergence Theorem
[cite_start]**Statement:** Let $\{f_n\}$ be a sequence of measurable functions on a set of finite measure $E$[cite: 225]. Suppose there is a real number $M$ such that $|f_n(x)| [cite_start]\le M$ on $E$[cite: 225]. [cite_start]If $f_n \rightarrow f$ pointwise on $E$, then $\int_E f = \lim \int_E f_n$[cite: 226, 227].


**Proof (via Littlewood's Third Principle):**
* By Littlewood's third principle, if $\{f_n\}$ converges to $f$ pointwise on a set of finite measure, it converges nearly uniformly. 
* Given $\epsilon > 0$, there exists a subset $A$ of $E$ such that $m(A) < \frac{\epsilon}{4M}$ and $f_n \to f$ uniformly on $E \setminus A$.
* We can bound the integral: $\int_E |f_n - f| = \int_A |f_n - f| + \int_{E \setminus A} |f_n - f|$.
* On $A$, $|f_n - f| \le |f_n| + |f| \le 2M$. So, $\int_A |f_n - f| \le 2M \cdot m(A) < 2M(\frac{\epsilon}{4M}) = \frac{\epsilon}{2}$.
* On $E \setminus A$, $f_n \to f$ uniformly, so for large $n$, $|f_n - f| < \frac{\epsilon}{2 \cdot m(E)}$.
* Thus, $\int_E |f_n - f| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon$. As $\epsilon \to 0$, $\int_E f_n \to \int_E f$.

### Fatou's Lemma
**Statement:** Let $\{f_n\}$ be a sequence of non-negative measurable functions. If $f_n \to f$ pointwise almost everywhere on $E$, then:
$$\int_E f \le \liminf_{n \rightarrow \infty} \int_E f_n$$

### Monotone Convergence Theorem (MCT)
**Statement:** Let $\{f_n\}$ be an increasing sequence of non-negative measurable functions on $E$. If $f_n \to f$ pointwise almost everywhere on $E$, then:
$$\int_E f = \lim_{n \rightarrow \infty} \int_E f_n$$

*(Note: MCT and Fatou's Lemma can be used to prove one another, and both are foundational for evaluating the convergence of integrals of sequences of functions).*

### Egoroff's Theorem
**Statement:** If a sequence of measurable functions $\{f_n\}$ converges to a real-valued function $f$ almost everywhere on a measurable set $E$ of finite measure, then given $\eta > 0$, there exists a subset $A \subset E$ with $m(A) < \eta$ such that $f_n$ converges to $f$ uniformly on $E \setminus A$.

---

## 5. Properties of Countable Sets and Unions

### Outer Measure of Countable Sets
**Question:** If $A$ is a countable set, prove that $m^*(A) = 0$.

**Proof:**
* Let $A$ be a countable set. We can enumerate its elements as $A = \{x_1, x_2, x_3, \dots\}$.
* For any $\epsilon > 0$, we can cover each point $x_n$ with an open interval $I_n = (x_n - \frac{\epsilon}{2^{n+1}}, x_n + \frac{\epsilon}{2^{n+1}})$.
* The length of each interval $I_n$ is $l(I_n) = \frac{\epsilon}{2^n}$.
* The total outer measure is bounded by the sum of the lengths of these intervals: $m^*(A) \le \sum_{n=1}^\infty l(I_n) = \sum_{n=1}^\infty \frac{\epsilon}{2^n} = \epsilon$.
* Since $\epsilon$ is arbitrarily small, it follows that $m^*(A) = 0$.

### Countable Additivity of Measurable Sets
**Question:** Show that if $\{E_i\}$ is a countable disjoint collection of measurable sets, then $m(\bigcup_{n=1}^\infty E_n) = \sum_{n=1}^\infty m(E_n)$.

**Proof Outline:**
* By countable subadditivity of outer measure, $m(\bigcup_{n=1}^\infty E_n) \le \sum_{n=1}^\infty m(E_n)$.
* Conversely, since $\bigcup_{n=1}^\infty E_n$ contains any finite union $\bigcup_{n=1}^k E_n$, by monotonicity, $m(\bigcup_{n=1}^\infty E_n) \ge m(\bigcup_{n=1}^k E_n)$.
* For finite disjoint measurable sets, $m(\bigcup_{n=1}^k E_n) = \sum_{n=1}^k m(E_n)$.
* Taking the limit as $k \to \infty$, $m(\bigcup_{n=1}^\infty E_n) \ge \sum_{n=1}^\infty m(E_n)$.
* Combining both inequalities yields equality.

---

## 6. Characteristic Functions and Specific Integrals

### Properties of Characteristic (Indicator) Functions
* **Intersection:** $\chi_{A \cap B} = \chi_A \cdot \chi_B$
* **Union:** $\chi_{A \cup B} = \chi_A + \chi_B - \chi_A \cdot \chi_B$
    * *Proof for Union:* $\chi_{A \cup B} = \chi_{A \setminus B} + \chi_{B \setminus A} + \chi_{A \cap B}$. Expanding this using set differences leads back to $\chi_A + \chi_B - \chi_{A \cap B}$.

### Evaluating specific limit integrals
**Question:** Find $\lim_{n \rightarrow \infty} \int_{-\infty}^{\infty} e^{-x^2} \sin^2(nx) dx$. It is known that $\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$.

**Solution:**
* Use the trigonometric identity: $\sin^2(nx) = \frac{1}{2}(1 - \cos(2nx))$.
* Substitute this into the integral: $\lim_{n \rightarrow \infty} \frac{1}{2} \int_{-\infty}^{\infty} e^{-x^2} (1 - \cos(2nx)) dx$.
* Split the integral: $\frac{1}{2} \int_{-\infty}^{\infty} e^{-x^2} dx - \frac{1}{2} \lim_{n \rightarrow \infty} \int_{-\infty}^{\infty} e^{-x^2} \cos(2nx) dx$.
* The first part evaluates to $\frac{1}{2} \sqrt{\pi}$.
* The second part evaluates to $0$ (similar to the Riemann-Lebesgue lemma for integrable functions).
* Therefore, the final answer is $\frac{\sqrt{\pi}}{2}$.

---

## 7. Littlewood's Three Principles
According to Littlewood, real analysis is grounded in three main principles:
1. Every measurable set is nearly a finite disjoint union of intervals.
2. Every measurable function is nearly continuous.
3. Every convergent sequence of measurable functions is nearly uniformly convergent.