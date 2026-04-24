---
layout: post
title: Learn Exam P - Probability
date: 2025-08-04 19:09 -0700
description: Exam P Study Guide
authors: [khoa_pham]
categories: [Programming Hub, Skill Tracks]
tags: [actuarial]
pin: false
math: true
mermaid: true
toc: true
comments: true
---


## A. Discrete Probability

### 1. Fundamentals of Probability
#### 1) Fundamentals of Probability

For any two events $$A$$ and $$B$$:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

#### 2) Complements

The complement of event $$A$$, written as $$A'$$, is the event that $$A$$ does not occur.

$$
P(A') = 1 - P(A)
$$

#### 3) Venn Diagrams

If $$A$$ and $$B$$ are mutually exclusive, then they cannot occur at the same time:

$$
P(A \cap B) = 0
$$

So:

$$
P(A \cup B) = P(A) + P(B) - 0
$$

or simply:

$$
P(A \cup B) = P(A) + P(B)
$$

#### 4) De Morgan's Laws

The complement of $$A \cup B$$ means neither $$A$$ nor $$B$$ occurs:

$$
(A \cup B)' = A' \cap B'
$$

The complement of $$A \cap B$$ means at least one of $$A$$ or $$B$$ does not occur:

$$
(A \cap B)' = A' \cup B'
$$

#### 5) Inclusion-Exclusion

For three events $$A$$, $$B$$, and $$C$$:

$$
P(A \cup B \cup C)
= P(A) + P(B) + P(C)
- P(A \cap B) - P(A \cap C) - P(B \cap C)
+ P(A \cap B \cap C)
$$

### 2. Conditional Probability

#### 1) Conditional Probability

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

So:

$$
P(A \cap B) = P(B)P(A \mid B) = P(A)P(B \mid A)
$$

#### 2) Independence

For two events $$A$$ and $$B$$:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

If $$A$$ and $$B$$ are independent, then:

$$
P(A \cap B) = P(A)P(B)
$$

Also, if independent:

$$
P(B) = P(B \mid A)
$$

#### 3) Sequence of Events

#### 4) Bayes' Theorem and Law of Total Probability

If $$A_i$$ represents a case:

$$
P(A_1 \mid B) =
\frac{P(B \mid A_1)P(A_1)}
{\sum_i P(B \mid A_i)P(A_i)}
$$

### 3. Discrete Moments

#### 1) Mode and Median

A median $$m$$ satisfies:

$$
F(m) = P(X \le m) \ge \frac{1}{2}
$$

#### 3) Mean and Law of Total Expectation

For a discrete random variable $$X$$:

$$
E(X) = \sum_x xP(X = x)
$$

For a function $$g(X)$$:

$$
E[g(X)] = \sum_x g(x)P(X = x)
$$

Linearity of expectation:

$$
E(aX + b) = aE(X) + b
$$

Law of total expectation:

$$
E(X) = \sum_i E(X \mid A_i)P(A_i)
$$

#### 5) Survival Approach

For a nonnegative integer-valued random variable $$X$$:

$$
E(X) = \sum_{x=0}^{\infty} P(X > x)
= \sum_{x=1}^{\infty} P(X \ge x)
$$

where $$x \ge 0$$.

#### 7) Variance

Variance formulas:

$$
\operatorname{Var}(X) = E(X^2) - E(X)^2
= E[(X - \mu)^2]
$$

Linear transformation:

$$
\operatorname{Var}(aX + b) = a^2\operatorname{Var}(X)
$$

Coefficient of variation:

$$
CV(X) = \frac{SD(X)}{E(X)} = \frac{\sigma}{\mu}
$$

Standard deviation:

$$
\sigma = SD(X) = \sqrt{\operatorname{Var}(X)}
$$

#### 8) Discrete Uniform

For a discrete uniform random variable $$N$$ on the integers from $$a$$ to $$b$$:

$$
P(N = n) = \frac{1}{b - a + 1}
$$

where $$b - a + 1$$ is the ***number of possible values***.

$$
E(N) = \frac{a + b}{2}
$$

$$
\operatorname{Var}(N) =
\frac{(\text{# possible values})^2 - 1}{12}
$$

### 4. Combinatorics

#### 1) Permutations and Combinations

Permutations:

$$
{}_nP_r = \frac{n!}{(n - r)!}
$$

where order is important.

Combinations:

$$
{}_nC_r = \frac{n!}{r!(n - r)!}
= \binom{n}{r}
= \binom{n}{n-r}
$$

where order is *not* important.

#### 3) Binomial Distribution

For $$N \sim \operatorname{Binomial}(n, p)$$:

$$
P(N = k) = \binom{n}{k}p^k(1 - p)^{n-k}
$$

$$
E(N) = np
$$

$$
\operatorname{Var}(N) = np(1 - p)
$$

#### 4) Multinomial Distribution

$$
P(N_1 = k_1, N_2 = k_2, N_3 = k_3)
=
\frac{n!}{k_1!k_2!k_3!}
p_1^{k_1}p_2^{k_2}p_3^{k_3}
$$

#### 5) Hypergeometric Distribution

With replacement, trials are independent, so the distribution is binomial:

$$
P(g) =
\binom{n}{g}
\left(\frac{G}{N}\right)^g
\left(\frac{N - G}{N}\right)^{n-g}
$$

Without replacement, the distribution is hypergeometric:

$$
P(g) =
\frac{
\binom{G}{g}
\binom{N - G}{n - g}
}{
\binom{N}{n}
}
$$

### 5. Key Discrete Distributions

#### 1) Geometric Distribution

There are two common versions of the geometric distribution.

**At 1: trials until first success**

$$
P(N = n) = (1 - p)^{n - 1}p
$$

$$
E(N) = \frac{1}{p}
$$

$$
\operatorname{Var}(N) = \frac{1 - p}{p^2}
$$

Survival probabilities:

$$
P(N > n) = (1 - p)^n
$$

$$
P(N \ge n) = (1 - p)^{n - 1}
$$

**At 0: failures before first success**

$$
P(N = n) = (1 - p)^n p
$$

$$
E(N) = \frac{1 - p}{p}
$$

$$
\operatorname{Var}(N) = \frac{1 - p}{p^2}
$$

Survival probabilities:

$$
P(N \ge n) = (1 - p)^n
$$

$$
P(N > n) = (1 - p)^{n + 1}
$$

#### 2) Memoryless Property

For a geometric random variable $$N$$:

$$
P(N > n + k \mid N > n) = P(N > k) = (1 - p)^k
$$

Expectation memoryless property:

$$
E(X - s \mid X > s) = E(X)
$$

So:

$$
E(X \mid X > s) = s + E(X)
$$

Variance memoryless property:

$$
\operatorname{Var}(X - s \mid X > s) = \operatorname{Var}(X)
$$

So:

$$
\operatorname{Var}(X \mid X > s) = \operatorname{Var}(X)
$$

#### 3) Negative Binomial Distribution

The $$r^{\text{th}}$$ success occurs on trial $$n$$:

$$
P(N = n) =
\binom{n - 1}{r - 1}
p^r(1 - p)^{n - r}
$$

The number of failures $$k$$ before the $$r^{\text{th}}$$ success:

$$
P(X = k) =
\binom{r + k - 1}{k}
p^r(1 - p)^k
$$

Example: for $$\operatorname{NegBin}(p = 0.6, r = 4)$$,

$$
P(N = 5)
= \binom{4}{3}(0.6)^3(0.4)^1(0.6)
$$

or:

$$
P(X = 1)
= \binom{4}{1}(0.4)^1(0.6)^3(0.6)
$$


<div style="max-width: 320px; margin: 1rem auto;">
  <svg viewBox="0 0 320 220" width="100%" role="img" aria-label="Fourth success occurs at A">
    <rect width="320" height="220" fill="#f8f7ec"/>

    <!-- grid -->
    <g stroke="#d8d8d8" stroke-width="2">
      <line x1="40" y1="0" x2="40" y2="220"/>
      <line x1="120" y1="0" x2="120" y2="220"/>
      <line x1="200" y1="0" x2="200" y2="220"/>
      <line x1="280" y1="0" x2="280" y2="220"/>

      <line x1="0" y1="40" x2="320" y2="40"/>
      <line x1="0" y1="120" x2="320" y2="120"/>
      <line x1="0" y1="200" x2="320" y2="200"/>
    </g>

    <!-- dashed timeline -->
    <line
      x1="35"
      y1="120"
      x2="185"
      y2="120"
      stroke="#8a2a96"
      stroke-width="5"
      stroke-linecap="round"
      stroke-dasharray="16 16"
    />

    <!-- label -->
    <text x="153" y="65" fill="#8a2a96" font-size="28" font-weight="700">
      4th
    </text>

    <!-- point A -->
    <text x="162" y="120" fill="#8a2a96" font-size="32" font-weight="700">
      A
    </text>
  </svg>
</div>


Mean and variance:

$$
E(X) = r\frac{1 - p}{p}
$$

$$
\operatorname{Var}(X) = r\frac{1 - p}{p^2}
$$

#### 4) Poisson Distribution

For $$N \sim \operatorname{Poisson}(\lambda)$$:

$$
P(N = n) = e^{-\lambda}\frac{\lambda^n}{n!}
$$

$$
E(N) = \operatorname{Var}(N) = \lambda
$$

#### 5) Sum of Poisson Variables

If $$X_1 \sim \operatorname{Poisson}(\lambda_1)$$ and $$X_2 \sim \operatorname{Poisson}(\lambda_2)$$, then:

$$
X_1 + X_2 \sim \operatorname{Poisson}(\lambda_1 + \lambda_2)
$$

So:

$$
P[\operatorname{Poisson}(\lambda_1 + \lambda_2) = k]
=
e^{-(\lambda_1 + \lambda_2)}
\frac{(\lambda_1 + \lambda_2)^k}{k!}
$$

### 6. Deductibles and Policy Limits

Total cost/loss:

$$
\text{Total cost/loss}
=
\text{Insurance Payment (covered)}
+
\text{Company Cost (uncovered)}
$$

$$
E(X) = E(Y) + E(U)
$$

#### Ordinary Deductible

For a deductible $$d$$, the insurance payment $$Y$$ is:

$$
Y =
\begin{cases}
0, & X \le d \\
X - d, & X > d
\end{cases}
$$

The uncovered cost $$U$$ is:

$$
U =
\begin{cases}
X, & X < d \\
d, & X \ge d
\end{cases}
$$

#### Policy Limit

For a policy limit $$B$$, the insurance payment $$Y$$ is:

$$
Y =
\begin{cases}
X, & X < B \\
B, & X \ge B
\end{cases}
$$

#### Deductible with Policy Limit

For a deductible $$d$$ and policy limit $$B$$, the insurance payment $$Y$$ is:

$$
Y =
\begin{cases}
0, & X \le d \\
X - d, & d < X < d + B \\
B, & X \ge d + B
\end{cases}
$$


## B. Continuous Probability

### 0. Calculus Review

#### Derivatives

$$
(x^n)' = nx^{n - 1}
$$

$$
(\ln x)' = \frac{1}{x}
$$

$$
(e^x)' = e^x
$$

$$
[c f(x)]' = c f'(x)
$$

$$
[f(u)]' = f'(u)u'
$$

$$
(uv)' = u'v + uv'
$$

$$
\left(\frac{u}{v}\right)'
=
\frac{u'v - uv'}{v^2}
$$

#### Integrals

$$
\int a \, dx = ax
$$

$$
\int x^n \, dx = \frac{1}{n + 1}x^{n + 1}
$$

$$
\int \frac{1}{x} \, dx = \ln x
$$

$$
\int e^{bx} \, dx = \frac{1}{b}e^{bx}
$$

$$
\int a^x \, dx = \frac{1}{\ln a}a^x
$$

#### Integration by Parts

$$
\int u \, dv = uv - \int v \, du
$$

#### Example

Find:

$$
\int x^2 e^{2x} \, dx
$$


<div style="max-width: 620px; margin: 1rem auto;">
  <svg viewBox="0 0 620 440" width="100%" role="img" aria-label="Integration by parts table">
    <rect width="620" height="440" fill="#f8f7ec"/>

    <!-- grid -->
    <g stroke="#d8d8d8" stroke-width="2">
      <line x1="72" y1="0" x2="72" y2="440"/>
      <line x1="162" y1="0" x2="162" y2="440"/>
      <line x1="252" y1="0" x2="252" y2="440"/>
      <line x1="342" y1="0" x2="342" y2="440"/>
      <line x1="432" y1="0" x2="432" y2="440"/>
      <line x1="522" y1="0" x2="522" y2="440"/>

      <line x1="0" y1="78" x2="620" y2="78"/>
      <line x1="0" y1="168" x2="620" y2="168"/>
      <line x1="0" y1="258" x2="620" y2="258"/>
      <line x1="0" y1="348" x2="620" y2="348"/>
    </g>

    <!-- purple writing -->
    <g fill="#8a2a96" font-family="Comic Sans MS, Chalkboard SE, Marker Felt, cursive" font-weight="700">
      <!-- left column -->
      <text x="84" y="82" font-size="42">x²</text>
      <text x="84" y="172" font-size="42">2x</text>
      <text x="88" y="260" font-size="42">2</text>
      <text x="88" y="350" font-size="42">0</text>

      <!-- signs -->
      <text x="252" y="86" font-size="42">+</text>
      <text x="252" y="176" font-size="42">−</text>
      <text x="252" y="266" font-size="42">+</text>
      <text x="252" y="356" font-size="42">−</text>

      <!-- right column -->
      <text x="370" y="82" font-size="42">e²ˣ</text>
      <text x="360" y="162" font-size="42">(1/2)e²ˣ</text>
      <text x="360" y="252" font-size="42">(1/4)e²ˣ</text>
      <text x="360" y="342" font-size="42">(1/8)e²ˣ</text>
    </g>

    <!-- diagonal arrows/lines -->
    <g stroke="#8a2a96" stroke-width="6" stroke-linecap="round">
      <line x1="172" y1="64" x2="350" y2="142"/>
      <line x1="172" y1="158" x2="350" y2="236"/>
      <line x1="172" y1="246" x2="350" y2="326"/>
      <line x1="172" y1="335" x2="350" y2="414"/>
    </g>
  </svg>
</div>


This tabular integration-by-parts setup gives:

$$
\int x^2 e^{2x} \, dx
=
x^2\left(\frac{1}{2}\right)e^{2x}
-
2x\left(\frac{1}{4}\right)e^{2x}
+
2\left(\frac{1}{8}\right)e^{2x}
-
0
$$

So:

$$
\int x^2 e^{2x} \, dx
=
\frac{x^2}{2}e^{2x}
-
\frac{x}{2}e^{2x}
+
\frac{1}{4}e^{2x}
+ C
$$


### 1. Densities and CDFs

#### 2) Densities and CDFs

For a continuous random variable $$X$$:

$$
P(a < X \le b)
=
\int_a^b f(x) \, dx
=
F(b) - F(a)
$$

The survival function is:

$$
P(X > t) = S(t) = \int_t^\infty f(x) \, dx
$$

#### 3) Mixed Distributions

For a mixed distribution with a point mass at $$x$$:

$$
P(X = x)
=
F(x) - \lim_{t \uparrow x} F(t)
$$

### 2. Continuous Moments

#### 1) Moments of Continuous Distributions

For a continuous random variable $$X$$:

$$
E(X) = \int x f(x) \, dx
$$

For a function $$g(X)$$:

$$
E[g(X)] = \int g(x) f(x) \, dx
$$

#### 2) Moments of Mixed Distributions

For a mixed random variable $$X$$:

$$
E(X)
=
\int x f(x) \, dx
+
\sum_x x P(X = x)
$$

#### 3) Survival Function Approach

For a nonnegative continuous random variable $$X$$:

$$
E(X)
=
\int_0^\infty P(X > x) \, dx
$$

### 3. Key Continuous Distributions

#### 1) Continuous Uniform

For $$X \sim \operatorname{Uniform}(a, b)$$:

$$
f(x) = \frac{1}{b - a}
$$

$$
F(x) = P(X \le x) = \frac{x - a}{b - a}
$$

$$
E(X) = \frac{b + a}{2}
$$

$$
\operatorname{Var}(X) = \frac{(b - a)^2}{12}
$$

#### 3) Exponential Random Variables

For $$X \sim \operatorname{Exponential}(\theta)$$:

$$
f(x) = \frac{1}{\theta}e^{-x/\theta}
$$

$$
F(x) = 1 - e^{-x/\theta}
$$

$$
S(x) = e^{-x/\theta}
$$

$$
E(X) = \theta = \frac{1}{\lambda}
$$

$$
\operatorname{Var}(X) = \theta^2
$$

Memoryless property:

$$
E(T - s \mid T > s) = \theta
$$

So:

$$
E(T \mid T > s) = s + \theta
$$

#### 4) Gamma, Exponential, and Poisson

For $$X \sim \operatorname{Gamma}(\alpha, \theta)$$:

$$
f(x) =
\frac{x^{\alpha - 1}}{\Gamma(\alpha)\theta^\alpha}
e^{-x/\theta}
$$

When $$\alpha = 2$$, this becomes:

$$
f(x) =
\frac{x}{\theta^2}e^{-x/\theta}
$$

$$
F(x)
=
1 - e^{-x/\theta}
-
\frac{x}{\theta}e^{-x/\theta}
$$

$$
E(X) = \alpha\theta
$$

$$
\operatorname{Var}(X) = \alpha\theta^2
$$

#### 5) Beta and Pareto

### 4. Normal Approximations

#### 1) Normal Distribution

For $$Z \sim N(0, 1)$$:

$$
P\left(Z \le \frac{x - \mu}{\sigma}\right) = \Phi(z)
$$

where:

$$
z = \frac{x - \mu}{\sigma}
$$

Symmetry:

$$
P(Z > z) = P(Z \le -z)
$$

$$
1 - \Phi(z) = \Phi(-z)
$$

Common values:

$$
\Phi(z) = 0.95
$$

$$
z = \Phi^{-1}(0.95) = 1.6449
$$

$$
\Phi(z) = 0.75
$$

$$
z = \Phi^{-1}(0.75) = 0.6745
$$

#### 2) Linear Interpolation

Example 1:

$$
\Phi(0.87) = 0.8078
$$

$$
\Phi(0.88) = 0.8106
$$

Interpolating for $$0.81$$:

$$
\Phi^{-1}(0.81)
=
0.87
+
\frac{0.81 - 0.8078}{0.8106 - 0.8078}
(0.88 - 0.87)
=
0.8779
$$

Example 2:

$$
\Phi(1.31) = 0.9049
$$

$$
\Phi(1.32) = 0.9066
$$

Interpolating for $$1.3168$$:

$$
\Phi(1.3168)
=
0.9049
+
\frac{1.3168 - 1.31}{1.32 - 1.31}
(0.9066 - 0.9049)
=
0.906056
$$


#### 3) Central Limit Theorem

For a sum $$S$$ of $$n$$ independent and identically distributed random variables:

$$
E(S) = n\mu
$$

$$
\operatorname{Var}(S) = n\sigma^2
$$

For the sample mean $$\bar{X}$$:

$$
E(\bar{X}) = \frac{1}{n}n\mu = \mu
$$

$$
\operatorname{Var}(\bar{X})
=
\frac{1}{n^2}n\sigma^2
=
\frac{\sigma^2}{n}
$$

#### 4) Continuity Correction

When approximating a discrete random variable with a continuous normal distribution:

$$
P(X \ge k) \approx P(X > k - 0.5) \quad \text{"At least"}
$$

$$
P(X > k) \approx P(X > k + 0.5) \quad \text{"Greater than"}
$$

$$
P(X \le k) \approx P(X < k + 0.5) \quad \text{"At most"}
$$

$$
P(X < k) \approx P(X < k - 0.5) \quad \text{"Less than"}
$$


#### 5) Lognormal Random Variables

### 5. Deductibles with Continuous


## C. Multivariate Probability

### 1. Joint Distributions

#### 1) Joint Distributions

#### 2) Marginal and Conditional Distributions

### 2. Joint Moments

#### 1) Means of Multivariate Distributions

For discrete random variables $$X$$ and $$Y$$:

$$
E[g(X, Y)]
=
\sum_x \sum_y g(x, y)P(X = x, Y = y)
$$

For $$E(X)$$:

$$
E(X)
=
\sum_x \sum_y xP(X = x, Y = y)
=
\sum_y \sum_x xP(X = x, Y = y)
$$

#### 2) Covariances and Correlations

Variance of a linear combination:

$$
\operatorname{Var}(aX + bY)
=
a^2\operatorname{Var}(X)
+
b^2\operatorname{Var}(Y)
+
2ab\operatorname{Cov}(X, Y)
$$

Covariance:

$$
\operatorname{Cov}(X, Y)
=
E(XY) - E(X)E(Y)
$$

Covariance and correlation:

$$
\operatorname{Cov}(X, Y)
=
\operatorname{Corr}(X, Y)SD(X)SD(Y)
$$

For a sum $$S = X_1 + X_2 + \cdots + X_n$$:

$$
\operatorname{Var}(S)
=
n\operatorname{Var}(X_i)
+
2\sum_{i < j}\operatorname{Cov}(X_i, X_j)
$$

#### 3) Conditional Moments

Law of total expectation:

$$
E(X) = E[E(X \mid Y)]
$$

Law of total variance:

$$
\operatorname{Var}(X)
=
E[\operatorname{Var}(X \mid Y)]
+
\operatorname{Var}[E(X \mid Y)]
$$

### 3. Order Statistics

#### 1) Order Statistics

For the maximum order statistic $$Y = \max(X_1, X_2, \dots, X_k)$$:

$$
P(Y \le y)
=
P(\text{all } X_i \le y)
=
[F(y)]^k
$$

For the minimum order statistic $$Y = \min(X_1, X_2, \dots, X_k)$$:

$$
P(Y > y)
=
P(\text{all } X_i > y)
=
[1 - F(y)]^k
$$

<!-- $$
P(Y \le y)
=
1 - P(Y > y)
=
1 - [1 - F(y)]^k
$$ -->

$$
P(Y \le y)
=
1 - P(\text{all } X_i > y)
=
1 - [1 - F(y)]^k
$$

Law of total probability for $$Y$$:

$$
P(A)
=
\int P(A \mid Y = y) f_Y(y) \, dy
\quad \text{continuous}
$$

$$
P(A)
=
\sum_y P(A \mid Y = y)P(Y = y)
\quad \text{discrete}
$$

#### 2) General Order Stats
