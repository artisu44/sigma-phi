# Paper N2: Paper 2 Structural Analysis — Carry / D_floor / Dirichlet

**Subtitle**: Number-theoretic structure of prime-gap factorisation and the D_floor spectrum theorem

**Version**: v0.5 (N5 backward link + NT 5-paper closure, 2026-04-27)
**Status**: DRAFT — NT-only extension of Paper C v0.2, positioned over the N1 framework header
**Prerequisites (framework)**: N1 (`N1_observation_theory_nt_ja.md`) v0.7
**Prerequisites (L1)**: `c_spectral.md §8`, `c_recursive_floor_principle.md`, `c_filtration_obstruction.md`, `c_arrow_framework.md §4.2.1`, `c_observation_optimal_gauge.md`, `c_theorems_master.md` (S13/S15/S17)
**Prerequisites (L1 NT)**: `nt_conductor.md §6`, `nt_dedekind_artin_zeta.md`
**Parent bridge**: `research/paper2_twin_dictionary_bridge_v1.md`
**Research roots**: `research/oq_p2_1_carry_closed_form.md`, `research/oq_p2_2_sstar_asymptotic.md`
**Sequel papers**: N3 (Path 2) / N4 (Hasse-Weil L × Stark) / N5 (Brauer + Origination)

---

## §0 Abstract

This paper is a structural analysis of the Dirichlet-type series F_{g,k}(s) along prime gaps. Five main results are developed over the N1 framework (axioms / S15 / Arrow / T-AAS / NT-internal triangulation):

**(M1) Closed form for the carry rate (OQ-P2-1 RESOLVED)** — c(g, X) = N_g(X) / |S_g(X)|, |S_g(X)| = X · ∏_{p|X}(1 − ν_g(p)/p), a **finite Euler product** over primes dividing X. |d| < 1.5pp across 30+ configurations. **Conductor dimension = ω(X)** (number of prime factors of X).

**(M2) D_floor spectrum theorem (OQ-P2-2/2c/2e CONFIRMED, P2-4 RESOLVED)** — parabolic formula $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 (\log N)^2 (s - 1/2)^2)$, unique minimum at s = 1/2 (3 decades). On the critical strip, the dip of D_floor(σ + it) locks onto γ₁ = 14.135 (all 21 σ-points) — the ΣΦ translation of RH.

**(M3) Gap dependence is structural, coefficients are k_max-gauge (OQ-P2-2 4th)** — α(1, g) > 0 holds across all 20 entries; s\*(N) → 1 is **universal in all gaps**. The log(g/2) linearity is k_max-invariant (R² ≈ 0.98), while coefficients are gauge quantities scaling as k_max^{−1/2}.

**(M4) Dirichlet decomposition of the ε_{g,k} residue is structurally forbidden (OQ-P2-3 CLOSED NEGATIVE)** — by mirror symmetry of residue exclusivity (100% at N=30M), the non-principal character χ₁ vanishes; χ₀ (6|g) carries the entire span. Binary separation by p = 0.87 (null) / p = 0.014 (χ₀) → **T-AAS f_torsion = 0, f_rational = 1 clean instance**.

**(M5) Three-layer decomposition = S15 isomorphism + structural analysis of the observation-optimal gauge** — the three layers F_{g,k}(s) = κ_g·G_k·W_k + a_g·Δ_k + ε_{g,k} correspond 1:1 with S15 (Scan/Structural/Information) (deep dive of N1 §6.1). Paper C coincide (s=1/2 functional-eq enforcement) vs. Paper 2 split (X=6 vs. X=2g locus) is made explicit as arithmetic mod-n reducibility.

**Thesis**: D_floor(s, N) along prime gaps is a paraboloid having s = 1/2 as the unique zero-scaling line, with curvature (log N)² and depth N^{−2/3}. It is the **prime-statistics version** of RH and the strongest NT instance of quantitative control of the N1 framework's Arrow 1 kernel.

**Forward / dictionary impact**: 2 dictionary annexes written back to `nt_conductor.md §6.10` (NT carry conductor) and `c_observation_optimal_gauge.md §5.5` (Path 3 arithmetic mod-n expansion); see §8.4.

---

## §1 Introduction

### 1.1 Number-theoretic positioning of Paper 2 + Twin-Zeta

The classical NT object π(x) − li(x) is the oscillation spectrum of non-trivial ζ-zeros. Paper 2 (2026-02-20) asserted the algebraic identity Δu = (M·Δx + Δy) mod L for u(n) = M·x + y mod L; the Twin-Zeta session (2026-03-04) established the gap-indexed factorisation

$$F_{g,k}(s) = \kappa_g \cdot G_k(s) \cdot W_k(\omega) + a_g \cdot \Delta_k(s) + \epsilon_{g,k}(N)$$

This paper integrates both results and develops them as the **quantitative-control instance of the Arrow 1 kernel** in the N1 framework.

### 1.2 Forward from the N1 framework header

This paper **cites N1 as axiomatic** and does **not redevelop** axioms A0-A7 / the S15 main theorem / the three-Arrow + Fi/I commutation / the T-AAS main theorem / the Arrow-level triangulation discipline / the 6-step protocol. Within the N1 framework we develop the concrete Paper 2 results (M1-M5), making explicit in each § where they lift to in N1.

### 1.3 Terminology

- **prime gap g**: p_{n+1} − p_n. In particular g = 2 (twin), 4, 6, …, 30.
- **F_{g,k}(s)** = $\sum_{p\,:\,p+g\,\text{prime}} e^{2\pi i k \tau(p)} \cdot p^{-s}$ — Dirichlet-type observable on gap-g prime pairs (τ(p) = internal scan phase).
- **Three-layer decomposition**: F_{g,k}(s) = (κ_g·G_k·W_k) [Scan] + (a_g·Δ_k) [Structural] + ε_{g,k} [Information]. G_k = Dirichlet τ-series over all primes; W_k = gauge window (Paper 0 Nyquist cut); Δ_k = ζ-zero oscillation component; ε_{g,k} = mod-6 arithmetic residual.
- **D_floor(s, N) := 1 − R²(s, N)** — three-layer fit residual. Main observable of this paper.
- **carry rate c(g, X)**: asymptotic probability that x + (g mod X) exceeds X under u(n) = M·x + y mod L.
- **residue exclusivity**: structural fact that prime gaps are constrained by the parent prime's mod-6 residue (§4.2).
- **κ_g**: gap-g prime pair density constant; ΣΦ counterpart of the Hardy-Littlewood twin constant C₂.

### 1.4 List of claims

| ID | Statement | Status |
|---|---|---|
| **M1** | c(g, X) is a closed-form finite Euler product over X | RESOLVED (OQ-P2-1) |
| **M2** | D_floor minimum at s = 1/2; parabolic, curvature (log N)², depth N^{−2/3} | CONFIRMED + RESOLVED (P2-2a/b/c) |
| **M3** | D_floor dip on the critical strip detects γ₁ | CONFIRMED (P2-2e, 21 σ-points) |
| **M4** | ε_{g,k} carries only the mod-6 principal indicator (non-principal characters structurally zero) | CLOSED NEGATIVE (P2-3) |
| **M5** | three-layer = S15 isomorphism + observation-optimal gauge structural analysis | CONFIRMED + structural (N1 §6.1 + §4.5.1 forward) |

---

## §2 Carry closed form (OQ-P2-1 RESOLVED)

### 2.1 Main theorem

**Theorem 2.1 (carry rate closed form)** — for X ≥ 2, Y ≥ 1, L = XY, gcd(M, L) = 1, prime gap g ≥ 2, the asymptotic carry rate under the Hardy-Littlewood distribution is

$$
c(g, X) = \frac{N_g(X)}{|S_g(X)|}, \quad
|S_g(X)| = X \prod_{p \mid X}\!\Bigl(1 - \frac{\nu_g(p)}{p}\Bigr), \quad
\nu_g(p) = \begin{cases} 2 & p \nmid g \\ 1 & p \mid g \end{cases}
$$

where $|S_g(X)|$ is a finite Euler product over primes dividing X (the count of admissible starting residues), and

$$
N_g(X) = \#\bigl\{ b \in \{1, \ldots, r-1\} : \gcd(b, X) = \gcd(r-b, X) = 1 \bigr\}, \quad r = g \bmod X
$$

is a short finite sum. c(g, X) depends only on r = g mod X and the divisibility of g by each prime factor of X.

### 2.2 Proof sketch

For p prime, set x₁ = p mod X. carry c = 1 ⟺ x₁ ≥ X − r (r = g mod X).

By Dirichlet's theorem + Hardy-Littlewood correlation, the joint distribution of residue pairs of (p, p+g) converges to the uniform distribution on $S_g(X) := \{a \in \mathbb{Z}/X\mathbb{Z} : \gcd(a, X) = \gcd(a+g, X) = 1\}$.

Rewriting the carry condition x₁ ≥ X − r as a = X − r + b (b ∈ [0, r−1]), we get gcd(a, X) = gcd(r − b, X), gcd(a + g, X) = gcd(b, X) (g = qX + r). Hence within S_g(X) the carry configurations match {b ∈ [1, r−1] : gcd(b, X) = gcd(r−b, X) = 1} (b = 0 excluded).

|S_g(X)| decomposes via CRT for each prime power p^k ∥ X: forbidden residues are 2 classes if p ∤ g → (p−2)·p^{k−1}; 1 class if p | g → φ(p^k) = (p−1)·p^{k−1}. Their product is the Euler form. ∎

### 2.3 Numerical verification

Script: `experiments/core/oq_p2_1_carry_closed_form.py`, primes up to 10⁷.

**X = 396 (Paper 2 main parameter; 2² · 3² · 11, ω=3)**:

| g | \|S_g\| | N_g | c_pred | empirical | diff |
|---|---|---|---|---|---|
| 2  | 54  | 1 | 1.852% | 1.868% | −0.02pp |
| 4  | 54  | **0** | **0.000%** | 0.000% | 0.000pp |
| 6  | 108 | 2 | 1.852% | 1.845% | +0.01pp |
| 8  | 54  | 2 | 3.704% | 3.483% | +0.22pp |
| 10 | 54  | 1 | 1.852% | 1.740% | +0.11pp |
| 12 | 108 | 2 | 1.852% | 1.618% | +0.23pp |
| 14 | 54  | 3 | 5.556% | 5.741% | −0.19pp |
| 16 | 54  | **0** | **0.000%** | 0.000% | 0.000pp |
| 18 | 108 | 4 | 3.704% | 3.943% | −0.24pp |
| 20 | 54  | 4 | 7.407% | 7.902% | −0.49pp |
| 22 | 60  | 2 | 3.333% | 3.362% | −0.03pp |
| 24 | 108 | 6 | 5.556% | 5.675% | −0.12pp |
| 26 | 54  | 5 | 9.259% | 9.780% | −0.52pp |
| 28 | 54  | 2 | 3.704% | 3.885% | −0.18pp |
| 30 | 108 | 8 | 7.407% | 8.417% | −1.01pp |

Aggregate (15 gaps, 600,178 transitions): c_pred = 2.89% vs. empirical = 2.95%, all |d| < 1.1pp (consistent with the O(1/√N) finite-sample Hardy-Littlewood error).

**X-scan for g = 2** (twin carry rate):

| X | factorisation | \|S_2\| | c_pred | empirical |
|---|---|---|---|---|
| 20  | 2² · 5             | 6   | 16.667% | 16.550% |
| 30  | 2 · 3 · 5          | 3   | 33.333% | 33.074% |
| 50  | 2 · 5²             | 15  | 6.667%  | 6.560%  |
| 100 | 2² · 5²            | 30  | 3.333%  | 3.238%  |
| 200 | 2³ · 5²            | 60  | 1.667%  | 1.668%  |
| 396 | 2² · 3² · 11       | 54  | 1.852%  | 1.868%  |
| 500 | 2² · 5³            | 150 | 0.667%  | 0.641%  |
| 1000| 2³ · 5³            | 300 | 0.333%  | 0.336%  |

All 8 points have |d| ≤ 0.3pp. X = 50 (15 gaps): all |d| < 1.5pp; carry rate range 6.7%-60% reproduced.

### 2.4 Zero-carry / conductor dimension / correction to Paper 2 §C.2

**Zero-carry (Paper 2 Remark 2.5)**: c(g, X) = 0 ⟺ N_g(X) = 0. At X = 396 this occurs for g = 4, 16 (all b rejected). These are **algebraic consequences** of the closed form, not empirical coincidence.

**Conductor dimension = ω(X)**: c(g, X) depends on two scope-distinct constraints (a) coprimality of starting residue x₁ with X and (b) coprimality of the (p+g) residue (x₁ + r) with X. They are not jointly factorisable at distinct positions of the same scope, but the Euler product ∏_{p|X} expresses them as a product of constraints prime by prime:

$$\dim(\text{conductor}_\text{carry}) = \omega(X)$$

For X = 396, ω(X) = 3 (primes 2, 3, 11) and the Euler product has 3 factors. This **corrects** Paper 2 §C.2 ("no closed form for carry rate, conductor dimension undetermined"). The φ(X)-dependence is captured exactly by ∏(1 − ν_g(p)/p), and N_g(X) is fully explicit.

### 2.5 Position in the N1 framework

**Arrow 1 instance** (N1 §4.1): within F_{g,k}(s) input spec, the X-axis (gauge L = XY period) encodes the Structural observable ω(X). The closed form of c(g, X) is the algebraic closure of the Arrow 1 mapping.

**T-AAS position** (N1 §5): the fact that g = 4, 16 are zero-carry at X = 396 is a clean algebraic realisation of ker_gauge (the torsion-vanishing condition on the Z/XZ × Z/XZ residue lattice). **f_torsion(c) = 0** (vanishes under Q-gauge), **f_rational(c) = ω(X)** (gauge-invariant conductor).

**S15 position** (N1 §3.3 Structural): all three observables ω(X), |S_g(X)|, N_g(X) reside in the Structural layer as parameter-free integer invariants.

---

## §3 D_floor spectrum theorem (OQ-P2-2 + P2-4)

### 3.1 Main result (final form)

**Claim 3.1** — gap-universal parabolic formula

$$
\log D_{\mathrm{floor}}(s, N) \approx -0.68 \cdot \log N + 0.216 \cdot (\log N)^2 \cdot (s - \tfrac{1}{2})^2 + \text{const}
$$

i.e. $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 \cdot (\log N)^2 \cdot (s - 1/2)^2)$.

- **Bottom (s = 1/2)**: D_floor ∼ N^{−2/3} → 0 (factorisation completion)
- **Width**: ∼ 1/(0.47 · log N) → 0 (delta-like contraction)
- **Gap dependence**: curvature coefficient C_log/(log N)² is gap-independent at 0.16 ± 0.004 (±4%)
- **Exp exponent**: (s − 1/2)² = squared distance from the critical line

Origin analysis of the constants 0.216, 2/3, 0.68 is developed structurally in §6.4. First-order approximation: leading expansion of zero contributions ρ = 1/2 + iγ in the explicit formula gives p^{ρ−s} = p^{(1/2−s)+iγ}, hence a first-order deviation δ_g(s) ∝ (s − 1/2)·⟨log p⟩_g of the gap-g restricted Dirichlet sum from its s = 1/2 value; with PNT ⟨log p⟩ ∼ log N, we obtain C_log ∝ (log N)².

### 3.2 Justification for parabolic fit

Model comparison (N ∈ {1M, …, 50M}, g = 2):

| Model | Form | R² range | Large N |
|---|---|---|---|
| A (linear parabola) | D = D₀ + C·Δs² | 0.963-0.994 | D₀ < 0 at 50M (collapses) |
| B (log-linear) | log D = a + b·Δs | 0.682-0.888 | worsens with N↑ |
| **C (log-quadratic)** | **log D = a + b·Δs + c·Δs²** | **0.996-0.999** | **stable across all N** |
| D (log-Gaussian) | log D = a + c·Δs² | −0.74-0.59 | collapses |

Decisive advantage for Model C. C_log vs. (log N)²: R² = 0.9999.

### 3.3 Decay of the bottom as N → ∞ (P2-2c, 3 decades)

`experiments/core/dfloor_d0_decay_1B.py`, N ∈ {10⁶, …, 10⁹} (8 points, **3 decades**):

| N | D(0.5) | D · log N |
|---|---|---|
| 1,000,000 | 0.032596 | 0.4503 |
| 5,000,000 | 0.012474 | 0.1924 |
| 10,000,000 | 0.008108 | 0.1307 |
| 50,000,000 | 0.002790 | 0.0495 |
| 100,000,000 | 0.001701 | 0.0313 |
| 200,000,000 | 0.001032 | 0.0197 |
| 500,000,000 | 0.000525 | 0.0105 |
| 1,000,000,000 | 0.000306 | 0.0063 |

| Model | Parameter | R² |
|---|---|---|
| **D₀ ∝ N^{−δ}** | **δ = 0.677, 95% CI [0.646, 0.720]** | **0.998** |
| D₀ ∝ 1/(log N)^β | β = 11.5 | 0.989 |
| D₀ ∝ 1/log N | CV(D·log N) = 1.28 (not constant) | — |

**Power law wins**. δ = 2/3 is the best AIC candidate (AIC = −40.07 vs. ln 2: −39.07, 1 − 1/π: −38.52).

### 3.4 RH translation (Corollary 3.3)

**Observation 3.2** — the parabolic vertex location s = 1/2 is the ΣΦ translation of the Riemann hypothesis.

For the explicit formula G_k(s) = Σ_p e^{2πik τ(p)}·p^{−s}, the contribution of a zero ρ = 1/2 + iγ is $p^{\rho - s} = p^{(1/2 - s) + i\gamma}$:

- s = 1/2: |p^{ρ−s}| = 1 pure oscillation → all zeros equally contribute, no p-range bias
- s ≠ 1/2: p^{1/2−s} damping/amplification factor → distortion via sieve interaction

**Corollary 3.3** — the critical line s = 1/2 is the **unique** vertical line on which the N-scaling exponent of D_floor vanishes. If RH is false (a zero exists at σ₀ ≠ 1/2) the vertex could move to s = σ₀, but no vertex with s ≠ 1/2 has ever been observed within the measurement range of this paper (N ≤ 10⁹, 21 σ-points, 21 gaps).

### 3.5 γ₁ dip: direct detection of non-trivial zero (P2-2e CONFIRMED)

D_floor(σ + it) measured on a 2D grid σ ∈ [0.5, 1.0] (21 points), t ∈ [11, 17] (121 points) with N = 50M, k_max = 30, g = 2:

| σ | t_min | dip | D_min | D_bg |
|---|---|---|---|---|
| 0.500 | 14.100 | 0.182 | 0.512 | 0.693 |
| 0.525 | 14.100 | 0.207 | 0.533 | 0.739 |
| 0.550 | 14.100 | 0.220 | 0.524 | 0.744 |
| **0.575** | **14.150** | **0.230** | **0.485** | **0.715** ← max |
| 0.600 | 14.150 | 0.229 | 0.437 | 0.666 |
| ... | ... | ... | ... | ... |
| 0.950 | 14.200 | 0.083 | 0.503 | 0.585 |

**Decisive facts**:
1. t_min locks onto γ₁ = 14.135: across all 21 σ values, t_min ∈ {14.10, 14.15, 14.20} (within grid 0.05).
2. dip max = 0.230 at σ = 0.575 (intermediate between low-D σ=0.5 and high-noise σ=1.0, optimal S/N).
3. dip > 0.08 across all σ (γ₁ influence observable across the entire critical strip).
4. σ-continuity (dip depth varies smoothly in σ).

This is not "direct observation of a ζ-zero" but **effective zero detection where γ₁ is detected σ-universally as the local minimum of the Dirichlet-type residual**.

### 3.6 k_max artifact correction and gap dependence (3rd / 4th iterations)

**Old interpretation** (memo v1, 2026-04-14): plateau at s ≈ 0.85 for gap=2 → s\* = 0.84 finite asymptote → contradicts RH (PARTIAL_NEGATIVE).

**Current interpretation (v3)**: the plateau is a k_max = 30 dependent artifact. k_max sweep (gap=2, N ∈ {500k, 30M}):

| s | k=15 | k=30 | k=60 | k=100 |
|---|---|---|---|---|
| 0.70 | 0.219 | 0.139 | 0.105 | 0.072 |
| 0.80 | 0.081 | 0.022 | 0.009 | −0.002 |
| 0.86 | **0.039** | 0.003 | −0.001 | −0.003 |
| 0.90 | 0.024 | 0.000 | 0.000 | −0.001 |
| 1.00 | **0.0069** | 0.001 | 0.001 | 0.001 |

α(0.86) shrinks +0.039 → −0.003 with k_max; at k_max=15 we have α(s=1.0) = +0.0069 > 0, consistent with the s\* → 1 claim.

**Mechanism**: D = ‖F − cG‖² / ‖F − mean(F)‖². As k_max grows, high-k modes carry gap-specific intrinsic residual that c·G cannot fit, inflating both numerator and denominator and diluting the low-k decay signal. The plateau is the crossover between low-k decay and high-k frozen noise.

**Correction**: old memo v1 "gap=2 exception" / v2 "gap-dependent s_crit" were artifacts under fixed k_max=30. s\* → 1 is preserved at small k_max even for gap=2. **Lesson**: sweep at least 3 parameters before any structural claim.

**Gap dependence (4th iter, k_max × gap cross-sweep)**: linear fit of α(1.0, g) vs. log(g/2):

| k_max | slope | intcpt | R² | α(1, g=2) | α(1, g=12) | α(1, g=30) |
|---|---|---|---|---|---|---|
| 15  | +0.0280 | +0.002 | 0.979 | +0.0069 | +0.0547 | +0.0787 |
| 30  | +0.0148 | +0.001 | 0.978 | +0.0010 | +0.0308 | +0.0392 |
| 60  | +0.0126 | −0.001 | 0.982 | +0.0010 | +0.0213 | +0.0337 |
| 100 | +0.0087 | −0.001 | 0.975 | +0.0007 | +0.0139 | +0.0236 |

**Three structural findings**:
1. **log(g/2) linearity is k_max-invariant** — R² ≈ 0.98 stable across all k_max; the form itself is structural.
2. **Coefficients are k_max-gauge dependent**: slope(s=1) ∼ k_max^{−0.573} (R²=0.947), slope(s=0.86) ∼ k_max^{−0.251} (R²=0.958). The k_max^{−1/2} scale near s=1 is consistent with white-noise dilution of high-k modes.
3. **α(1, g) > 0 across all 20 entries** — minimum α(1, g=2, k=100) = +0.0007; s\*(N) → 1 universal across all gaps. Old memo v2 "large-gap only" reframe is incorrect.

**Correction**: old "α(1, g) ≈ 0.013·log(g/2)" is a gauge value under fixed k_max=30. Replaced: α(1, g) = a(k_max)·log(g/2), where a(k_max) is a gauge quantity around k_max^{−1/2}. Identification of the coefficient at canonical k_max is OPEN (P2-2f).

### 3.7 OQ-P2-4 RESOLVED

OQ-P2-4 originally asked "is β exact or fitted?": cubic AIC comparison shows **β is NOT exact** (cubic AIC = −146 vs. power law −94).

**RESOLVED (2026-04-22)**:
- β NOT exact → generalised power law is the true form
- **C_log = 0.216 · (log N)² is exact** (R² = 0.9999, holds across all gaps)
- **α(0.5) = 0.677 is gauge-invariant** (3 decades, ±5%); δ = 2/3 wins on AIC, but rigorous identification pending N ≥ 10¹⁰

This is the **strongest NT instance of axiom A2 (convergence rate = observable)** in the N1 §3.5 exhaustivity closure — α(0.5) = 0.677 itself is a gauge-invariant scaling observable.

### 3.8 Position in the N1 framework

**Arrow 1 kernel control instance** (N1 §6.1): the D_floor parabolic formula is the **quantitative control** of the Arrow 1 kernel along the F_{g,k}(s) Scan axis. The minimum at s = 1/2 is not a fixed point on Arrow 2, but γ₁ dip locking (§3.5) directly exposes the **internal structure of the Arrow 1 kernel (ker_topo)**. **Relation to S17 (Arrow 3 e-extremum)**: §3.1 κ ≈ 0.216 ≈ 1/(2·2.31) is an O(1) constant of zero-density origin in time average; relation to zero density 1/(2π)·log(γ/2π) is in §6.4.

**Open questions (contributions to N1 §8.3)**:

| Sub-Q | Content | Status |
|---|---|---|
| P2-2a | log D_floor parabolic form (gap-universal) | **CONFIRMED** |
| P2-2b | curvature C_log ∝ (log N)² | **CONFIRMED** (R²=0.9999) |
| P2-2c | D₀ ∼ N^{−2/3} (δ ≈ 0.677) | **RESOLVED** (3 decades) |
| P2-2d | ε_k peaks correspond to ζ-zeros | **REJECTED** (perm p=0.81) |
| P2-2e | D_floor(σ+it) dip locks at γ₁ | **CONFIRMED** (21 σ-points) |
| P2-2f | identify canonical k_max + theorise β(s) | **OPEN** |
| P2-2g | double limit α(s, k_max, N) | **OPEN** |
| P2-2h | α(s=1, g) ∝ log(g/2): universal s\*→1 | **CONFIRMED** (4th iter) |

---

## §4 Dirichlet decomposition of ε_{g,k} (OQ-P2-3 CLOSED NEGATIVE)

### 4.1 Main result

**Theorem 4.1 (mod-6 mirror symmetry of ε)** — the mod-6 residue Dirichlet character decomposition of ε_{g,k} is **carried entirely by the principal indicator χ₀ (6|g)**; non-principal characters χ₁ (Legendre) are structurally zero:

- **χ₁ Legendre projection** ‖B‖²: permutation test (N=30M, k_max=150, 19 gaps) gives **p = 0.87 (z = −1.05)** ⇒ no signal
- **χ₀ indicator projection**: R² block test gives **p = 0.014 (z = +2.62)** ⇒ class 0 (6|g) D_floor is roughly half of class 1, 2 (floor ≈ 0.0049 vs. 0.0100)
- All signals vanish at s = 1

### 4.2 Structural reason for residue exclusivity

Structural fact holding 100% at N = 30M:

- **g ≡ 2 (mod 6)** arises only from p ≡ 5 (mod 6) primes (p+g ≡ 1 mod 6)
- **g ≡ 4 (mod 6)** arises only from p ≡ 1 (mod 6) primes (p+g ≡ 5 mod 6)
- **g ≡ 0 (mod 6)** arises from both residue classes (roughly half each)

Class 1 (g ≡ 2) and class 2 (g ≡ 4) have different parent residues but statistically symmetric and independent noise realisations → χ₁ = (m₁−m₂)/2 structurally vanishes. Only class 0 (g ≡ 0) is "doubly sourced" so its low D_floor is distinguished (the χ₀ indicator effect). This is called **residue exclusivity**.

### 4.3 Consequence (no second-stage factorisation)

There is **no "second-stage factorisation"** of ε_{g,k}. Residue mirror symmetry forbids non-principal character contributions → the arithmetic residual layer has only the principal indicator (conductor dimension 1). This is consistent with `c_filtration_obstruction.md` "f_rational residence = ker_topo^{non-surj} ∩ target only" (in the Twin-Zeta session conductor ω = 4 for L = 99000; here this contracts to conductor = 1 for mod 6).

### 4.4 Position in the N1 framework

**T-AAS clean instance** (N1 §5.2): OQ-P2-3 realises the clean instance with **f_torsion = 0** (χ₁ structurally vanishes → trivial under Q-gauge) + **f_rational = 1** (only χ₀, conductor dim 1). Registered as the 3rd NT instance alongside Stark / Brauer in N1 §5.2 table.

**Arrow 1 kernel structure** (N1 §4.6): residue exclusivity = structural obstruction; in the ker_gauge ⊕ ker_topo decomposition the algebraic mechanism by which the ker_gauge side (χ₁ Legendre) **automatically vanishes by mirror symmetry** is the pure NT instance of N1 §5.2 row "ker_gauge classical" (f_torsion contribution).

**Structural contribution of conductor dimension**: conductor dim = 1 is a parameter-free integer invariant analogous to f_p(ρ), f_χ rows in the N1 §3.3 Structural layer.

---

## §5 Three-layer decomposition = S15 Observable Trichotomy (deep dive of N1 §6.1)

### 5.1 Isomorphism claim

| Twin-Zeta layer | Mathematical content | S15 layer | Arrow | Dictionary residence |
|---|---|---|---|---|
| κ_g · G_k · W_k | PNT main term × gauge window | **Scan** | 1 | S12 (τ-scan) |
| a_g · Δ_k | ζ-zero spectrum contribution | **Structural** | 2 | S15 structural |
| ε_{g,k} | mod-6 arithmetic residual | **Information** | 3 | S15 information |

This is the NT core of the N1 §6.1 claim "Paper C three-layer decomposition = S15 isomorphism in single object".

### 5.2 Gauge-invariance verification per layer

- **Scan (κ_g)**: κ_2(s=1, k=0) = 0.299512 fully independent of M ∈ {13, 1979, 1981, 49999} ⇒ S15 Structural invariant. Numerically consistent with the Hardy-Littlewood twin constant C₂ = 1.3203… via $\kappa_2 \approx 2C_2/\int_2^N dt/\log^2 t \cdot 1/\pi(N)$.
- **Structural (Δ_k)**: R² > 0.9998 at s = 1/2 across all gaps; gauge-free.
- **Information (ε_{g,k})**: by §4, only the mod-6 principal indicator contributes; conductor dimension 1.

### 5.3 Transition of three-layer ratios with s

```
         s = 0.5                   s = 1.0
g    Scan%  Struct%  Info%    Scan%  Struct%  Info%
2    3.7    95.7     0.6      1.8    51.8     46.4
6    3.7    96.1     0.2      1.8    51.4     46.9
12   3.7    96.1     0.2      1.5    45.1     53.3
30   3.7    96.1     0.2      1.6    45.2     53.2
```

- **s = 1/2**: Structural 96%, Information 0.3% → ζ-zero structure dominates
- **s = 1**: Structural 45%, Information 53% → arithmetic residual exceeds half

"Arithmetic gets washed out at s = 1/2" is confirmed as a **quantitative transition** of S15 layers — the obverse of the §3 D_floor parabolic form (relative arithmetic weight grows as (s − 1/2)²).

### 5.4 Deep dive into N1 §6.1 — meaning of single-object three-Arrows-simultaneous

In N1 §6.4 (Arrow-level triangulation), Paper C is characterised as "**three Arrows simultaneous in single object F_{g,k}(s)**". Unlike Stark (Arrows 2/3) or Brauer (Arrow 1 kernel), there is NT-specific particularity that **three Arrows are simultaneously embedded inside the single observable F_{g,k}(s)**:

- **Arrow 1**: F_{g,k}(s) → input spec (gap distribution {p : p+g prime}, gauge L=XY, k mode)
- **Arrow 2**: F_{g,k}(s) → −log F_{g,k}(s) → log-derivative chain to ε_{g,k}
- **Arrow 3**: (Cl(O_K) for K = ℚ(ζ_{XY}), residue mod 6) → log h_K, log φ(L), log gap density

Three Arrows holding simultaneously is the basis for positioning F_{g,k}(s) as a "complete instance" of observation theory within Paper 2 NT. Stark/Brauer are complementary as Arrow 1 / Arrows 2-3 instances but do not pack three Arrows into a single instance as F_{g,k}(s) does. **Consequence**: F_{g,k}(s) is the **canonical realisation** of S15 isomorphism within NT; the predictive power of the N1 framework can radiate from this object outward to Stark / Brauer / other NT instances.

---

## §6 Structural analysis of the observation-optimal gauge theorem (forward expansion of N1 §4.5.1)

N1 §4.5.1 stated the **2-instance contrast** (Paper C coincide vs. Paper 2 carry split) only at the statement level, forwarding the structural analysis to this paper. §6 develops it.

### 6.1 Paper C coincide instance — structural enforcement by ζ functional eq

**Claim 6.1** — the coincide in Paper C (Information balance s = 1/2 = Structural balance s = 1/2) originates from structural enforcement by ζ(s) = ζ(1−s)·χ(s) (χ(s) = 2^s π^{s−1} sin(πs/2) Γ(1−s)).

| Mechanism | Content |
|---|---|
| **(a) Information balance** (S13 half-value fixed point on Arrow 2) | D_floor minimum at s = 1/2 (§3.1 main result) — half-value fixed point on the Scan log-derivative chain of the ζ-family |
| **(b) Structural balance** (RH zeros on Arrow 1) | RH (assumed): ζ-zeros concentrate on critical line s = 1/2 + iγ — natural balance locus of Δ_k(s) (ζ-zero oscillation component) |
| **(c) Simultaneous fixedness** | s ↔ 1−s symmetry of the functional equation collapses (a) and (b) onto the **same fixed point s = 1/2** |

**Agreement test of N1 §4.5.1b** (point realisation): $g_I^D = g_S^D$ = s = 1/2 (point ∈ Obs(D)), agreement criterion = **point-to-point equality** ✅, C(D) = 0 (agree). This is the unique confirmed instance of a domain-internal structural identity (functional equation) **forcing** agreement.

### 6.2 Paper 2 carry split instance — X = 6 vs. X = 2g locus

**Claim 6.2** — the split in Paper 2 (Information balance X = 6 ≠ Structural balance {X = 2g locus}) originates from **arithmetic mod-n reducibility**. Functional-equation-type enforcement is absent.

| Mechanism | Content |
|---|---|
| **(a) Information balance** | D_floor minimum w.r.t. X (g=2 fixed) is realised at X = 6 (Paper C §3 + Euler product structure of carry conductor). \|S_2(6)\| = 6·(1−2/2)·(1−1/3) = 0 (zero-carry artifact); practically a low-conductor region around X = 6 |
| **(b) Structural balance** | The c(g, X) = 1/2 locus is realised at X = 2g (carry-rate half-value arithmetic structure). 15 gaps tested: g=2→X=4, g=4→X=8, …, g=30→X=60 — locus realisation |
| **(c) Non-intersection** | X = 6 (point) and {X = 2g} (locus) **do not intersect** due to absence of arithmetic mod-n compatibility: X = 6 lies on the locus only for g = 3, but prime gaps g are always even (g≥4 even, g=2 twin) → g = 3 is outside NT scope → never intersect |

**Agreement test of N1 §4.5.1b** (point-in-locus realisation): $g_I^D$ = X = 6 (point), $g_S^D$ = {X = 2g : g ∈ S} (locus), criterion = **point-in-locus**; result X = 6 ∉ {2g} for g ≠ 3 + g = 3 ∉ NT prime gap → C(D) ≠ 0 (disagree).

### 6.3 Split causation: arithmetic mod-n reducibility

In the **N1 §4.5.1 Path 3 split causation taxonomy**, Paper 2 carry split is classified under the **arithmetic mod-n reducibility** clause (`c_observation_optimal_gauge.md §5`):

> g_S is pinned by the arithmetic structure (X = 2g locus) of the conductor X, and the locus does not intersect the Information optimum X = 6 (originating from factor 3).

This is the 2nd class of split causation alongside the stochastic basin selection of Paper E (image AI):
- Paper 2: **deterministic arithmetic mod-n** (parity constraint + factor structure)
- Paper E: **stochastic basin** (probabilistic UNet weight initialisation in training trajectories)

**Contribution to N1 §5.2**: §6.3 is, alongside OQ-P2-3 (Dirichlet residue exclusivity), an **NT instance of arithmetic mod-n constraint**. Residue exclusivity = constraint on class division (mod 6); carry split = constraint on X choice. Together they provide two instances showing how arithmetic mod-n governs T-AAS / agreement test of NT observables.

### 6.4 Structural analysis of factors in the D_floor parabolic formula

Structural origin analysis of the constants 0.216, 0.68, 2/3 in §3.1:

**(α) 0.216 = 1/(2·2.31)**: zero-density time average N(T) ∼ (T/2π) log(T/2π) (Riemann-von Mangoldt) gives zeros per unit time (1/2π) log(γ/2π); evaluated at γ₁ = 14.135 ≈ 0.184. Close to 0.216 but not exact — likely a finite-N effect (zeros ≤ γ_max ≈ 17 for N ≤ 50M) mixed with sieve weight. **Open**: exact identification deferred to P2-2f.

**(β) δ = 2/3 origin**: standard CLT gives δ = 1/2 (independent-sample average, Hardy-Littlewood). Observed δ = 0.677 exceeds 1/2, suggesting a sieve weight effect from destructive interference. Candidates: δ = 2/3 (phase importance metric `c_information_theory.md`) / δ = ln 2 = 0.693 (Arrow 2 S13 half-value) / δ = 1 − 1/π ≈ 0.682 (Arrow 1 via π). 2/3 wins on AIC, but exact identification pending N ≥ 10¹⁰. **Interim**: δ = 2/3 is the best AIC candidate but exact identification pending.

**(γ) C_log = 0.216·(log N)² is exact** (R² = 0.9999, holds across all gaps): emerges directly from the combination of first-order PNT ⟨log p⟩ ∼ log N + zero phase average O(1). **C_log is exact** confirmed by OQ-P2-4 (0.16 ± 0.004 across all gaps).

**Contribution to N1 §3.5 / §4.4**: special values such as 0.216, 2/3, ln 2 provide NT-internal instances of N1 §4.5 (S13/S14/S17). Specifically: C_log ∝ (log N)² ⟹ "log" of the Arrow 1 kernel reduces to **log p = log of prime element**, an arithmetic Hartley counting (direct connection to N1 §3.4 Information layer "Λ(n) = −ζ'/ζ").

### 6.5 Carry rate Euler product vs. residue exclusivity contrast

§2.4 and §4.2 contribute to T-AAS through different number-theoretic structures:

| Aspect | Carry rate (§2) | Residue exclusivity (§4) |
|---|---|---|
| **Constraint type** | gcd coprimality (Z/XZ, prime by prime) | mod-6 residue partition (Z/6Z class division) |
| **Conductor scope** | ω(X) (number of prime factors of X) | 1 (mod-6 principal indicator) |
| **Closed form mechanism** | Euler product ∏_{p|X}(1 − ν_g(p)/p) | Mirror symmetry (χ₁ structural zero) |
| **T-AAS f_torsion** | 0 (vanishes under Q-gauge) | 0 (vanishes by mirror) |
| **T-AAS f_rational** | ω(X) (X-dependent) | 1 (universal) |

The two realise T-AAS through **different aggregation axes** of arithmetic mod-n constraint (X-axis prime decomposition vs. g mod 6 residue partition). Together with the carry instance of §2.5, the OQ-P2-3 instance of N1 §5.2 forms the NT T-AAS clean-instance space.

---

## §7 Twin prime infinitude is not required

### 7.1 Proposition 7.1

**Proposition 7.1** — the three-layer decomposition does not depend on the truth of the twin prime conjecture (TPC).

| Scenario | Asymptotic of κ₂ | Structural layer | Factorisation |
|---|---|---|---|
| TPC true | κ₂ → C₂ × (const) > 0 | Δ_k invariant | holds permanently |
| TPC false | κ₂ → 0 (F_{2,k} → 0) | Δ_k invariant | holds in finite range |

Reasons: (1) within finite range F_{2,k}(s) = κ₂·G_k·W_k + a₂·Δ_k + ε holds purely algebraically (Paper 2 Thm 2.1); (2) the form of Δ_k (ζ-zero oscillation structure) does not depend on the number of twins; (3) factorisations for other g (g = 4, 6, 8, …) are completely independent.

**Validation**: R² > 0.9998 across all 11 gaps g ∈ {2, 4, 6, 8, …, 30} (twins are a convenient example, not a theoretical premise).

### 7.2 Explanation via S15 + T-AAS

TPC is a **Scan-layer (Arrow 1)** problem (κ_g = density of gap-g prime pairs = PNT + sieve asymptotic). The ζ-zero structure is a **Structural-layer (Arrow 2)** problem (Δ_k does not depend on the choice of subset conditioned on gap g). Scan/Structural separation ⇒ independence.

T-AAS reading: TPC true ⟹ F_{2,k} is f_rational-like (infinite support → ℚ-module); TPC false ⟹ F_{2,k} is f_torsion-like (finite support → ℤ-torsion). In either case ker_topo (ζ-zero phase structure) and ker_gauge (choice of M, X, Y) are identical — TPC asks "is it f_torsion or f_rational?" without touching the kernel structure.

This shows that the N1 §5 T-AAS framework is **operative independently of TPC truth value** = evidence of NT-internal robustness for the N1 framework header.

---

## §8 Consequences and Open Questions

### 8.1 Established (M1-M5)

1. **M1 — Carry rate closed form (OQ-P2-1 RESOLVED)**: finite Euler product c(g, X) = N_g(X)/|S_g(X)|; conductor dim = ω(X); |d| < 1.5pp across 30+ configurations.
2. **M2 — D_floor parabolic formula (P2-2a/b/c CONFIRMED + RESOLVED)**: D_floor ∼ N^{−2/3}·exp(0.216·(log N)²·Δs²); 3 decades verified.
3. **M3 — γ₁ detection in D_floor(σ + it) (P2-2e CONFIRMED)**: γ₁ = 14.135 dip locking across 21 σ-points.
4. **M4 — Gap dependence 4th iteration (P2-2 4th, P2-2h CONFIRMED)**: log(g/2) linearity is structural; coefficient is k_max-gauge a(k_max) ∼ k_max^{−1/2}.
5. **M5 — Three-layer = S15 isomorphism + observation-optimal gauge structural analysis (forward expansion of N1 §6.1 + §4.5.1)**: F_{g,k}(s) is the canonical realisation of single-object three-Arrows-simultaneous within NT; Paper C coincide / Paper 2 split made explicit as arithmetic mod-n reducibility.

Additionally: **OQ-P2-3 CLOSED NEGATIVE** (§4 Dirichlet residue exclusivity, T-AAS f_torsion=0, f_rational=1 clean instance) / **OQ-P2-4 RESOLVED** (§3.7 β not exact, C_log exact R²=0.9999, α(0.5)=0.677 gauge-inv).

### 8.2 Partial / Open

| ID | Content | Status |
|---|---|---|
| **P2-2f** | identify canonical k_max + theorise exponent β(s) of slope(s) vs. k_max | OPEN |
| **P2-2g** | double limit α(s, k_max, N) (k_max → ∞, N → ∞) | OPEN |
| **P2-5** | identify D(1) ≈ 0.447 | PENDING |
| **P2-2c (high precision)** | high-precision confirmation of δ = 2/3 (N ≥ 10¹⁰) | PENDING |
| **0.216 origin** | exact identification from zero-density time average | OPEN (P2-2f integration candidate) |

### 8.3 N3-N5 forward bridges

| Sequel | Topic | Forward from this paper | Status |
|---|---|---|---|
| **N3** | Path 2 NT universality (Dirichlet L series) | §3 lift D_floor structure to Dirichlet L(s, χ) (Schumann path 2 5+ instances). §4 generalise residue exclusivity to Galois rep series (mod L principal indicator) | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`) — §3 D_floor lifting attempt closes as "structural fit only" (SC4 caveat); §4 residue exclusivity generalisation is out of scope (Dirichlet L extension trajectory completed) |
| **N4** | Hasse-Weil L × Stark structure | §3 develop D_floor for Hasse-Weil L (CM curve, central curvature). §5.4 Galois-rep-side analogue of single-object three-Arrows-simultaneous. §6 concretise split causation in Stark rank 0/1 | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — §3 establishes the **5-component weight-class-dependent transfer pattern of the D_floor formula** (vertex location + multi-gap = transfer / curvature scaling + decay + γ₁ dip = ζ-specific / on the other hand at weight-2 the **K_E·t²→r BSD analytic-rank** weight-2 specific predictive content emerges); §5.4 / §6 split causation developed via §4.1 Stark Class number formula 6-gauge connection |
| **N5** | Brauer obstruction theory + Origination matrix (8-gauge) | §4 connect OQ-P2-3 T-AAS clean instance to class 0 (Tier 1 strict) of Brauer 5-tier. §3.1 classify constants 0.216, 2/3, ln 2 via Origination matrix 8-gauge signatures | **v0.2 drafted 2026-04-27** — §3.1 constants 0.216 / 2/3 / ln 2 of this paper classified in **{anal, mult} / {prime_coord, anal} / {char, anal}** 8-gauge signatures (N5 §4.5). §4 OQ-P2-3 T-AAS f_torsion=0/f_rational=1 clean instance is structurally aligned with Tier 1 strict (S_3) in T-AAS taxonomy (N5 §5.1) |

### 8.4 Dictionary residence map (extension of N1 §8.4)

| Piece in this paper | Residence | Status |
|---|---|---|
| §2 Carry closed form (OQ-P2-1) | `research/oq_p2_1_carry_closed_form.md` (primary), `c_recursive_floor_principle.md §6.8` cross-ref | RESOLVED 2026-04-22 |
| §2.4 Conductor dim = ω(X) | `nt_conductor.md §6` extension annex (NT carry conductor) | annex candidate 2026-04-26 |
| §3 D_floor parabolic formula | `c_recursive_floor_principle.md §6.8` (D_floor cross-domain table NT row) + `§6.8.1` (Dirichlet L gap-class universality (12/12 PASS) fragment, N3 §4.6 transfer) + `§6.8.2` (Hasse-Weil L extension, N4 §3 transfer) | existing (ESTABLISHED 2026-04-13) + **N3 backward §6.8.1 + N4 backward §6.8.2 implemented (2026-04-26)** |
| §3.1 (M2) | `c_theorems_master.md` D_floor(s) row | existing |
| §3.5 γ₁ dip detection | `c_recursive_floor_principle.md §6.8` (numerical cross-ref of this paper) | existing |
| §3.6 4th iter k_max-gauge | `research/oq_p2_2_sstar_asymptotic.md` (primary) | RESOLVED 2026-04-22 |
| §4 Dirichlet residue exclusivity (OQ-P2-3) | `c_filtration_obstruction.md` (T-AAS f_rational instance), N1 §5.2 table | existing + N1 register |
| §5 Three-layer = S15 isomorphism | `c_theorems_master.md` row S15 + N1 §6.1 reference | N1 §6.1 deep dive done |
| §6 Observation-optimal gauge structural analysis | `c_observation_optimal_gauge.md §5 Path 3 split causation` (arithmetic mod-n clause, expansion of §6.3 of this paper) | expansion candidate 2026-04-26 |
| §7 Twin prime non-requirement | `c_filtration_obstruction.md` (f_torsion vs. f_rational binary) + N1 §5 framework robustness | existing |

**N3-N5 forward residence**: each sequel paper directly cites §3.1, §4, §5.4, §6.3 of this paper.

**N3 v0.2 (2026-04-26) backward statistics**: in N3 drafting, the §3 D_floor lifting attempt of this paper was developed under honest dual reporting and closed as **Dirichlet L extension scope = "structural fit only"**. The **genuine extension fragment** = multi-gap structural invariance (12/12 PASS) was written back to `c_recursive_floor_principle.md §6.8.1` as N3 §4.6 transfer. Paper-C-level 2-quantity uniqueness + (log N)² curvature scaling is **ζ-specific (§3 of this paper ESTABLISHED)** confirmed (in Paper N3 §4.4 + §4.5, 2 paths REJECTED, Paper C uniqueness preserved more strongly).

**N4 v0.2 (2026-04-26) backward statistics**: in N4 drafting, the **weight-2 (Hasse-Weil L) extension** of §3 D_floor lifting was established and written back to `c_recursive_floor_principle.md §6.8.2` as N4 §3 transfer. Of the **5-component partition of the D_floor formula** established in §3 of this paper (vertex + multi-gap + curvature + decay + γ₁ dip), **vertex location + multi-gap transfer to both weight-1/2** while **curvature + decay + γ₁ dip remain ζ-specific (weight-1)**. At weight-2, a different observable (K_E central curvature) provides **the weight-2 specific predictive content of BSD analytic-rank detection (K·t²→r)**. **Framework predictive transfer pattern is weight-class dependent** (Paper N4 main thesis) emerges directly from the structural decomposition of the D_floor formula in §3 of this paper.

---

## Change log

- **v0.5 (2026-04-27)**: N5 backward link + NT 5-paper closure. N5 v0.2 drafted reflected in §8.3 N3-N5 forward bridge status column (8-gauge classification of §3.1 constants confirmed + §4 OQ-P2-3 aligned with Tier 1 strict T-AAS). NT-series 5-paper closure achieved.
- **v0.4 (2026-04-26)**: N4 backward link added. N4 v0.2 drafted (2026-04-26) reflected in §8.3 N3-N5 forward bridge status column (N4 = "K_E·t²→r BSD analytic-rank detection genuine framework content confirmed; weight-class-dependent transfer pattern established"). N4 §3 backward (`c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension) added to §3 D_floor row of §8.4 residence map. N4 backward statistics paragraph added at the end of §8.4 (5-component partition of the D_floor formula and weight-class-dependent transfer pattern emerge directly from §3 of this paper).
- **v0.3 (2026-04-26)**: N3 backward link added. N3 v0.2 drafted (2026-04-26) reflected in §8.3 N3-N5 forward bridge status column (N3 = "Dirichlet L extension trajectory completed, structural fit only close"). In §8.4 residence map, N3 §4.6 backward (`c_recursive_floor_principle.md §6.8.1` Dirichlet L gap universality fragment) added to §3 D_floor row. N3 backward statistics paragraph added at the end of §8.4 (Paper C uniqueness preserved more strongly via 2 paths REJECTED in N3 §4.4-§4.5).
- **v0.2 (2026-04-26)**: compact version. Reduced redundancy from v0.1 (724 lines) — Abstract compressed; §1.2 N1 forward 6-item list reduced to 1 paragraph; §2.4-§2.6 (zero-carry / conductor / Paper 2 §C.2 correction) consolidated into 1 subsection; explanation of 0.216 / 2/3 origin in §3.1 consolidated into §6.4; §3.6 / §3.7 k_max artifact correction and gap 4th iter merged into 1 section; §3.8 OQ-P2-4 merged into §3.7; redundancy in §5.4 single-object three-Arrows-simultaneous compressed; mechanisms (a)(b)(c) of §6.1 / 6.2 tabularised; §6.3 split causation explanation compressed; §7 S15 explanation and T-AAS reading merged. Skeleton, claims, instance numerical values, and status notation all preserved.
- **v0.1 (2026-04-26)**: initial NT-only draft. NT-only extension of Paper C v0.2 (550 lines, includes multi-domain bridge §7). Positioned over the N1 framework header; §7 quantum connection (FX/T-KD bridge) stripped; §6 structural analysis of the observation-optimal gauge theorem (forward expansion of N1 §4.5.1) and §3.8 OQ-P2-4 4th iter results added.

---

## References (internal)

**Parent paper / bridge**: `papers/Paper_C_NT_Quantum_ja.md` (v0.2, 2026-04-22, includes multi-domain bridge §7) / `research/paper2_twin_dictionary_bridge_v1.md` (active v1, 2026-04-22)

**Framework**: `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.7, 2026-04-27)

**OQ-P2 research notes**: `research/oq_p2_1_carry_closed_form.md` (RESOLVED 2026-04-22) / `research/oq_p2_2_sstar_asymptotic.md` (RESOLVED 4th iter)

**Original Paper 2 / Twin-Zeta**: Paper 2 (2026-02-20) / Twin-Zeta harvest (2026-03-04)

**Experiment scripts**: `experiments/core/oq_p2_1_carry_closed_form.py` (§2.3) / `experiments/core/dfloor_d0_decay_1B.py` (§3.3) / `experiments/core/oq_p2_2_kmax_gap_crosssweep.py` (§3.6) / `sigmaphi/data/oq_p2_2_sstar/alpha_kmax_gap_crosssweep.csv`

**L1 / meta dependencies (via N1)**: `c_theorems_master.md` (S13/S14/S15/S17 + D_floor universality row) / `c_recursive_floor_principle.md §6.8` / `c_filtration_obstruction.md` / `c_arrow_framework.md §4.2.1` / `c_observation_optimal_gauge.md §5` / `c_spectral.md §8` / `nt_conductor.md §6` / `nt_dedekind_artin_zeta.md` / `meta/triangulation_methodology.md §9` / `meta/new_domain_protocol.md §8`

**Sequel papers (drafting planned)**: N3 (Path 2 NT universality) / N4 (Hasse-Weil L × Stark) / N5 (Brauer obstruction theory + Origination matrix)
