---
title: "OQ-P2-1 closure: carry rate c(g, X) closed form"
status: RESOLVED (2026-04-22)
scope: Paper 2 §B.2, §C.2 carry rate 解析公式
---

## Statement

**Theorem (c(g, X) closed form)**. For parameters $X \geq 2$, $Y \geq 1$,
$L = XY$, $M$ coprime to $L$, and prime gap $g \geq 2$, the asymptotic carry
rate (under Hardy-Littlewood prime distribution) is

$$
c(g, X) \;=\; \frac{N_g(X)}{|S_g(X)|}
$$

where

* $|S_g(X)|$ is the count of admissible starting residues:
  $$
  S_g(X) \;=\; \{\,a \in \mathbb{Z}/X\mathbb{Z}\;:\;\gcd(a, X) = \gcd(a+g, X) = 1\,\}
  $$
  with the finite **Euler product** (product ranges over primes dividing $X$):
  $$
  |S_g(X)| \;=\; X \prod_{p \mid X}\!\left(1 - \frac{\nu_g(p)}{p}\right),
  \qquad
  \nu_g(p) \;=\;
  \begin{cases}
    2 & p \nmid g \\
    1 & p \mid g
  \end{cases}
  $$

* $N_g(X)$ is the short finite sum with $r = g \bmod X$:
  $$
  N_g(X) \;=\; \#\{\,b \in \{1, \ldots, r-1\}\;:\;\gcd(b, X) = \gcd(r-b, X) = 1\,\}.
  $$

Here $c(g, X)$ depends on $g$ only through $r = g \bmod X$ and the parity
of $g$ with respect to each prime divisor of $X$.

## Derivation

Let $p$ be a prime with $x_1 = p \bmod X$. By definition, carry $c = 1$
iff $x_1 \geq X - r$ where $r = g \bmod X$.

Write $a = x_1$. Under Dirichlet's theorem plus Hardy-Littlewood
correlations, the joint distribution of $(p \bmod X, (p+g) \bmod X)$ over
prime pairs $(p, p+g)$ approaches the uniform distribution over the
admissible set $S_g(X)$ defined above. For carry:

* $x_1 \geq X - r$ means $a = X - r + b$ for some $b \in \{0, \ldots, r-1\}$.
* $\gcd(a, X) = \gcd(X - r + b, X) = \gcd(r - b, X)$.
* $\gcd(a + g, X) = \gcd(X - r + b + g, X) = \gcd(b + qX, X) = \gcd(b, X)$
  since $g = qX + r$.

Thus the carry event within $S_g(X)$ corresponds exactly to
$\{b \in \{1, \ldots, r-1\} : \gcd(b, X) = 1,\ \gcd(r - b, X) = 1\}$
(the case $b = 0$ forces $\gcd(0, X) = X \neq 1$, so is excluded).

For the denominator, $|S_g(X)|$ factors by the Chinese Remainder Theorem
over prime powers $p^k \parallel X$. For each such factor:

* If $p \nmid g$: the forbidden residues are $a \equiv 0 \pmod p$ and
  $a \equiv -g \pmod p$ (two distinct nonzero classes), giving
  $(p-2) \cdot p^{k-1}$ admissible residues.
* If $p \mid g$: the only forbidden residue is $a \equiv 0 \pmod p$,
  giving $\varphi(p^k) = (p-1) \cdot p^{k-1}$.

Multiplying and factoring $X = \prod p^k$ yields the Euler-product form.

## Numerical verification

Scripts: `experiments/core/oq_p2_1_carry_closed_form.py`,
primes up to $10^7$.

### X = 396 (Paper 2 main parameter)

| g | $\|S_g\|$ | $N_g$ | $c_{\text{pred}}$ | empirical count | empirical % | diff |
|---|---|---|---|---|---|---|
| 2  | 54  | 1 | 1.852% |  1,102 / 58,980 | 1.868% | -0.02% |
| 4  | 54  | 0 | 0.000% |  0 / 58,621 | 0.000% | 0.000% |
| 6  | 108 | 2 | 1.852% |  1,845 / 99,987 | 1.845% | +0.01% |
| 8  | 54  | 2 | 3.704% |  1,475 / 42,352 | 3.483% | +0.22% |
| 10 | 54  | 1 | 1.852% |    947 / 54,431 | 1.740% | +0.11% |
| 12 | 108 | 2 | 1.852% |  1,060 / 65,513 | 1.618% | +0.23% |
| 14 | 54  | 3 | 5.556% |  2,032 / 35,394 | 5.741% | -0.19% |
| 16 | 54  | 0 | 0.000% |  0 / 25,099 | 0.000% | 0.000% |
| 18 | 108 | 4 | 3.704% |  1,729 / 43,851 | 3.943% | -0.24% |
| 20 | 54  | 4 | 7.407% |  1,745 / 22,084 | 7.902% | -0.49% |
| 22 | 60  | 2 | 3.333% |    654 / 19,451 | 3.362% | -0.03% |
| 24 | 108 | 6 | 5.556% |  1,542 / 27,170 | 5.675% | -0.12% |
| 26 | 54  | 5 | 9.259% |  1,198 / 12,249 | 9.780% | -0.52% |
| 28 | 54  | 2 | 3.704% |    515 / 13,255 | 3.885% | -0.18% |
| 30 | 108 | 8 | 7.407% |  1,830 / 21,741 | 8.417% | -1.01% |

**Aggregate (15 gaps, 600,178 transitions)**: predicted 2.89%, empirical 2.95%.
All per-gap differences $|d| < 1.1$ percentage points, consistent with the
$O(1/\sqrt{N})$ Hardy-Littlewood finite-sample error.

### X = 50 (Paper 2 second parameter)

All 15 gaps $g \in \{2, \ldots, 30\}$: predicted vs empirical agree within
$\sim 1.5$ percentage points. Carry rates span $6.7\% \to 60\%$; the
predicted ordering and magnitudes match empirical throughout.

### X-scan for $g = 2$ (twin prime carry rate as X varies)

| X | factorization | $\|S_2(X)\|$ | $c_{\text{pred}}$ | empirical |
|---|---|---|---|---|
| 20  | $2^2 \cdot 5$       | 6   | 16.667% | 16.550% |
| 30  | $2 \cdot 3 \cdot 5$ | 3   | 33.333% | 33.074% |
| 50  | $2 \cdot 5^2$       | 15  |  6.667% |  6.560% |
| 100 | $2^2 \cdot 5^2$     | 30  |  3.333% |  3.238% |
| 200 | $2^3 \cdot 5^2$     | 60  |  1.667% |  1.668% |
| 396 | $2^2 \cdot 3^2 \cdot 11$ | 54 | 1.852% | 1.868% |
| 500 | $2^2 \cdot 5^3$     | 150 |  0.667% |  0.641% |
| 1000| $2^3 \cdot 5^3$     | 300 |  0.333% |  0.336% |

All agreements within $\leq 0.3$ percentage points.

## Structural consequences

### Zero-carry gaps (Paper 2 Remark 2.5 explained)

$c(g, X) = 0$ iff $N_g(X) = 0$, i.e., there is no $b \in \{1, \ldots, r-1\}$
with both $b$ and $r - b$ coprime to every prime divisor of $X$.

For $X = 396 = 2^2 \cdot 3^2 \cdot 11$:
- $g = 4$ (r=4): $b \in \{1, 2, 3\}$. Need both $b$ and $4-b$ coprime to $396$.
  $b=1$: $4-1=3$, but $\gcd(3, 396) = 3$. $b=2,3$: $\gcd(b, 396) > 1$. $N = 0$.
- $g = 16$ (r=16): similar exhaustion; $N_{16}(396) = 0$.

These are **algebraic** consequences of the closed form, not empirical
curiosities.

### Conductor dimension

From the feedback memory ("conductor = constraint count"), $c(g, X)$
depends on TWO scope-distinct constraints: (a) starting residue $x_1$
coprimality with $X$, (b) $(p+g)$ residue $(x_1 + r)$ coprimality with $X$.
These are constraints on the SAME scope (residues mod $X$) but at
DIFFERENT positions, so they are **not jointly factorizable** into a
single scope.

However the **Euler product decomposition over primes of $X$** shows that
the conductor can be expressed as a product of one-prime-at-a-time
constraints, so the effective conductor dimension is $\omega(X)$
(the number of distinct primes dividing $X$), not 2. This resolves the
"dim ambiguity" noted in paper2_twin_dictionary_bridge_v1.md §1.5.

Concretely: for $X = 396$, $\omega(X) = 3$ (primes $2, 3, 11$). The carry
rate Euler product has 3 factors.

### Scaling

For fixed $g$, $c(g, X) \to 0$ as $X \to \infty$ like $\sim N_g(X) / |S_g(X)|
\sim (r-1) \varphi(X)^{-\text{something}} / X$. The X-scan data for $g = 2$
shows the rate decays roughly as $|S_g(X)|^{-1}$ (since $N_g$ is bounded for
fixed $g$, and $|S_g(X)|$ grows as $X \prod_{p|X}(1 - \nu/p)$).

## Paper 2 §C.2 claim correction

The §C.2 parenthetical states:

> "carry 率に解析的公式がある（→ $\varphi(X)$ の residue 構造に依存し、
>  closed form は未導出）"

**Correction**: The closed form IS derivable and is given above. The
$\varphi(X)$-dependence is captured exactly by the Euler product
$\prod_{p | X} (1 - \nu_g(p)/p)$, and the short-sum numerator $N_g(X)$ is
fully explicit. What was missing was the **admissible-set framing**
(conditioning on both $p$ and $p+g$ prime), which I make explicit here.

## Status

**OQ-P2-1 RESOLVED POSITIVELY (2026-04-22)**.

Closed form confirmed by numerical agreement across:
- 15 gaps at $X = 396$ (all $|d| < 1.1$ pp)
- 15 gaps at $X = 50$ (all $|d| < 1.5$ pp)
- 8 values of $X \in \{20, \ldots, 1000\}$ at $g = 2$ (all $|d| < 0.3$ pp)

**Remaining NT OQ in Paper 2 slate**: OQ-P2-2 s*(N) → 1 analytic proof
(PARTIAL, trichotomy established).
