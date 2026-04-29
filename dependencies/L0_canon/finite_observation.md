---
axis: [A, B]
position: L0_root
static_dynamic: both
connected_to:
  - B.L1_base
  - B.L1_fiber
  - A.algebra
  - A.harmonic_analysis
arrow_status:
  upstream: none
  downstream: done
updated: 2026-04-23
---

# Finite Observation Theory

## 0. Thesis

All observation is finite. All structure lives in the infinite limit. The art is extracting one from the other.

Every L1 theorem, L2 measurement, L3 correspondence, and L4 error ultimately derives from a single fact: **the observer sees a finite window of an infinite object, and the window itself determines what algebra is visible.**

---

## 1. The Finite Window

### 1.1 Definition

An observation is a triple (S, W, m) where:
- S = the infinite structure (prime distribution, crystal lattice, eigenvalue spectrum, ...)
- W = the finite window (Z_L, hkl grid, rolling window, ...)
- m = the measurement (counting, diffraction, spectral statistics, ...)

The observed value m(S|_W) depends on both S and W. Theorems describe m(S). Experiments measure m(S|_W). The gap m(S) - m(S|_W) is the **finite observation error**.

### 1.2 The window determines the visible algebra

- **Number theory**: Observer chooses gauge M, sees Z_L = Z_{XY}. Low M -> few Nyquist modes (coarse algebra). High M -> more modes (finer algebra). The algebra Z_X x Z_Y is a PROJECTION ARTIFACT of the window Z_L. [Paper 0, §1: "All observation limits derive from omega = ord_L(M)"]

- **Crystal**: Observer chooses h_max, sees hkl in [-h_max, h_max]^3. Small h_max -> centering absences dominate (global algebra). Large h_max -> glide/screw absences become resolvable (local algebra). [This session: h_max=6 gives 74.6% vs 75.0% theory]

- **FX**: Observer chooses rolling window T, currency set n. Small n -> few constraints visible (gas phase). Large n -> full triangular closure visible (solid phase). [FX dictionary: 8 currencies -> 21 constraints]

### 1.3 Nyquist principle (discrete)

The highest resolvable frequency in a periodic series of period omega is k_N = floor(omega/2). [Paper 0, Claim B]

This is the discrete sampling theorem: the window sets the maximum resolution. Below this frequency, structure is observable. Above it, aliasing occurs. The Nyquist limit is NOT a property of the object S — it is a property of the window W.

**Cross-domain instances**:
- Number theory: k_N = floor(omega/2) Fourier modes resolvable in gauge M
- Crystal: h_max determines maximum |k| resolvable
- FX: T (window length) determines minimum frequency resolvable in spectrum

---

## 2. The Uncertainty Principle

### 2.1 Resolution-channel tradeoff

R(omega, N) * rank(omega) ~ const(N)

where R = observation quality (mixing + sampling), rank = number of independent information channels. [Paper 0, Theorem 0.2]

**Interpretation**: You cannot simultaneously have high resolution (large R) AND many channels (large rank). More constraints -> more channels -> each channel is noisier. Fewer constraints -> fewer channels -> each channel is cleaner.

### 2.2 Non-commutativity of limits

Different orders of taking limits yield different structures: [Paper VII, Thm 5.1]

    lim_{T->inf} lim_{B->inf} =/= lim_{B->inf} lim_{T->inf}

where T = observation time, B = resolution. The order matters because:
- T -> inf first: arbitrarily small signals become detectable (no threshold)
- B -> inf first: system appears reversible (precision erases irreversibility)
- Constant T/B: a third, distinct limiting behavior emerges

**Cross-domain instances**:
- Number theory: lim_{N->inf} lim_{L->inf} vs lim_{L->inf} lim_{N->inf} give different prime distribution statistics
- Crystal: lim_{h_max->inf} lim_{T->0K} (perfect crystal) vs lim_{T->0K} lim_{h_max->inf} (Debye-Waller persists)
- FX: lim_{T->inf} lim_{N_ccy->inf} vs lim_{N_ccy->inf} lim_{T->inf} (regime structure vs market size)

---

## 3. Convergence Rates as Observables

### 3.1 The rate encodes the controlling structure

How fast m(S|_W) -> m(S) as W expands tells you WHICH part of S controls the approach. [Projection Dictionary, Phase 3-4]

| Observable | Rate alpha | Controlling structure |
|---|---|---|
| Prime counting pi(N) | N^{-1/2} | GRH / PNT |
| Leading SV sigma_1(N) | N^{-0.14} | zeta zeros (gamma_1 ~ 14.13) |
| Second SV sigma_2(N) | N^{-0.08} | L-function zeros (gamma_1 ~ 8.04) |
| Crystal centering absence (h_max) | ~ h_max^{-2} | Grid boundary effects |
| FX amp/Wishart (T window) | ~ T^{-1/2} | Central limit theorem |

### 3.2 Fast convergence = simple structure, slow convergence = deep structure

When an observable converges fast (alpha ~ 0.5), it is controlled by the leading term of the asymptotic expansion. When it converges slowly (alpha ~ 0.08), deeper structure (subleading zeros, secondary corrections) controls the rate.

**Implication for L4**: An error that persists across window sizes is NOT noise — it is deep structure converging slowly. The Debye-Waller factor (ERR-C1) is an example: it doesn't vanish with larger h_max because it is physical, not a truncation artifact.

---

## 4. Gauge Invariance and Gauge Dependence

### 4.1 Amplitude is gauge-invariant; phase is gauge-dependent

|c_chi(M)|^2 = |tau(chi-bar)|^2 / phi(L)^2 [Paper 0, Theorem 0.3]

The squared amplitude (energy allocation across characters) does NOT depend on M (the observer's gauge choice). Only the phase depends on M.

**Translation**: What you CAN know (amplitude) vs what DEPENDS ON HOW you look (phase).

### 4.2 Cross-domain interpretation

- **Crystal**: |F(hkl)|^2 is the observable (amplitude squared). The phase of F(hkl) requires additional information (anomalous dispersion, direct methods). This is the "phase problem" of crystallography — same dichotomy.
- **FX**: Eigenvalue magnitude spectrum is stable across windows (gauge-invariant). Eigenvector orientation depends on window choice (gauge-dependent).
- **General**: Any system has gauge-invariant observables (what to measure) and gauge-dependent artifacts (how the measurement was set up). L4 errors often come from mistaking gauge-dependent quantities for gauge-invariant ones.

---

## 5. The Finite Observation Error Decomposition

### 5.1 Three-component structure

Every finite observation error decomposes as: [Paper 0, §5.1]

    error = error_arithmetic + error_projection + error_noise

- **error_arithmetic** (~26%): inherent to the object S (e.g., primes != uniform mod 6). Cannot be reduced by better observation.
- **error_projection** (~60-70%): depends on window choice W (gauge M, h_max, rolling window T). Reducible by better gauge selection.
- **error_noise** (~5-10%): finite-N sampling variance. Reducible by N^{-1/2}.

### 5.2 Cross-domain instances

| Component | Number theory | Crystal | FX |
|---|---|---|---|
| Arithmetic | Prime irregularity mod L | Atom-specific form factors | Currency-specific volatility |
| Projection | Gauge M image coverage | h_max truncation, DW contamination | Window T, pair subset selection |
| Noise | Finite prime count | Counting statistics | Finite sample returns |

### 5.3 Floor deviation

D_floor > 0 is an unavoidable observation error in any finite gauge L. It vanishes only as phi(L) -> infinity. [Paper 0, Definition 5a.2]

**Formal definition** (c_distortion_floor.md S2.4):

    D_floor(S, W) := inf_{g in G(W)} d( m(S), m_g(S|_W) )

where G(W) is the set of gauge transformations on W, and d is the domain-appropriate
distortion measure. D_floor decomposes as D_arith + D_proj_irr (noise is excluded
because it vanishes at N -> infinity). See c_distortion_floor.md for the unified
type signature, 5 domain instances, and the common structure theorem (P1-P4).

**Cross-domain**: Every finite system has a floor deviation. Crystal at h_max=6: D_floor ~ 0.4%. FX at N_ccy=8: D_floor ~ 26% (distance from sigmoid saturation).

---

## 6. Effective Participation and Saturation

### 6.1 phi_eff as finite-window observable

phi_eff(L) / phi(L) ~ C_inf / log(p_omega) as omega -> infinity [Paper 0, Theorem 0.4-0.5]

The effective participation ratio measures what fraction of the theoretical capacity is actually realized in finite observation. It decays logarithmically — more capacity is always wasted than used.

### 6.2 Saturation as the infinite-N prediction

The sigmoid saturation level A is the predicted value of amp at infinite conductor:

    amp(conductor -> inf) = A

This is the L0 interpretation of the L1 sigmoid formula. At finite conductor, we measure amp < A. The ratio amp/A = 1 - base^(-conductor) tells us how close to the infinite limit we are.

| Domain | A | Current amp/A | Interpretation |
|---|---|---|---|
| Crystal (F lattice) | 1.0 | 0.75 | 75% of maximum extinction |
| FX (8 currencies) | 18.2 | 0.74 | 74% of sigmoid saturation |
| Number theory | C_inf/log(p_omega) | varies | Logarithmic approach |

---

## 7. Axioms

### A0 (Finite observation) [umbrella]
All observables are measured in finite windows. The window determines the visible algebra.

The following sub-axioms make A0 precise for the Born rule derivation (Paper I §4). Existing references to "A0" remain valid as the umbrella.

#### A0a (Finiteness)
The observer's Hilbert space is finite-dimensional: dim(H) = L < ∞. All sums are finite, all spectra are discrete, all algebras are matrix algebras. The infinite-dimensional limit L → ∞ is a mathematical idealization that the observer never reaches.

**Consequence for additivity**: For a finite observer, only finite decompositions are operationally accessible. Hence finite additivity is the primitive requirement; σ-additivity enters only as an idealized infinite-limit completion. The measure-theoretic debate over σ-additivity does not arise at the operational level of finite observation.

#### A0b (Partial access)
For any observable A = Σ λ_j P_j, the observer obtains exactly one outcome λ_j per measurement. The observer cannot simultaneously access all components of the state. This is the irreducible cost of finiteness: the window shows one face of the structure, not all faces at once.

**Operational content**: Given an orthogonal decomposition I = P₁ + P₂ + ... + P_L, the observer's single measurement yields one index j ∈ {1, ..., L}. To characterize the full state, repeated measurements on identically prepared systems are required.

#### A0c (Multi-window compatibility)
When the same state is measured with respect to different orthogonal decompositions (different "windows"), the probability assignments must be consistent on shared subspaces. Specifically:

If decomposition D₁ contains projection P and decomposition D₂ also contains P (or a refinement of P), the probability assigned to P must be the same regardless of which decomposition is used.

**From A0b + A0c to frame function** (via two lemmas):

**Lemma L0.1 (Outcome weights)** [from A0b]:
Each orthogonal decomposition {P_j} induces a weight assignment v(P_j) satisfying:
(i) v(P_j) ≥ 0 (each outcome either occurs or does not),
(ii) Σ_j v(P_j) = 1 (exactly one outcome per measurement).
This follows from A0b: the observer obtains one result from mutually exclusive alternatives, so a non-negative normalized assignment is operationally necessary for prediction.

**Lemma L0.2 (Context consistency)** [from A0c]:
If projection P appears in two different orthogonal decompositions D₁ and D₂, then v_{D₁}(P) = v_{D₂}(P). That is, the weight assigned to a shared subspace is independent of the decomposition context. This is A0c applied to the weight assignments of L0.1.

**Corollary L0.3 (Frame function)**:
L0.1 + L0.2 together define a frame function: a decomposition-independent, non-negative, normalized assignment on projections. The frame function is not assumed as a primitive but assembled from the outcome structure (A0b) and the compatibility constraint (A0c).

### Theorem T0d (Operational fuzziness) [derived from A0a]

**Statement**: A finite observer's operationally realizable measurements are naturally described by effects (POVMs). Sharp projections (PVMs) remain mathematically well-defined but represent an idealized limit.

**Proof sketch**: A sharp projection P_j = |e_j⟩⟨e_j| assigns outcome j if and only if the state is exactly in the eigenspace of P_j. This requires infinite precision in distinguishing eigenvalues — the observer must resolve λ_j from λ_k with zero error. But A0a (finiteness) implies the observer's measurement apparatus has finite resolution. Any realistic implementation of P_j is therefore an effect E_j with 0 ≤ E_j ≤ I and Σ E_j = I, where E_j approximates P_j but E_j² ≠ E_j in general (fuzzy measurement). Sharp projections are recovered in the idealized limit of infinite measurement precision.

**Consequence**: The operationally natural domain of the frame function (Corollary L0.3) is effects E(H), not projections Proj(H). This is precisely the domain where Busch-Gleason (q_quantum_observation.md §6) guarantees v(E) = Tr(ρE) for ALL dimensions, including dim = 2. PVMs are not excluded but are special cases within the broader POVM framework.

### Born rule derivation chain (Paper I §4 reference)

```
A0a (finiteness: dim < ∞)
  ├──→ T0d (operational fuzziness: effects as natural domain)
  └──→ A0b (partial access: one outcome per measurement)
          │
          ↓
        Lemma L0.1: v(P_j) ≥ 0, Σ v(P_j) = 1
        (outcome weights from A0b)
          │
          ↓ + A0c (multi-window compatibility)
          │
          ↓
        Lemma L0.2: v(P) context-independent
          │
          ↓
        Corollary L0.3: frame function on Proj(H)
          │
          ↓ + T0d (extend domain to effects E(H))
          │
          ↓ + Busch-Gleason (q_quantum_observation.md §6)
          │
          ↓
        v(E) = Tr(ρ · E)  for all E ∈ E(H)
        = Born rule (全 dim, dim=2 含む)
```

**Residue** (what this chain does NOT derive):
1. **Preferred basis**: Which decomposition does nature "choose"? (Decoherence gives partial answer; L0 does not resolve this.)
2. **Single outcome**: Why does one j occur rather than all? (Measurement problem hard core; no known resolution.)

### A0-ID (Identity asymmetry) [see L0/identity_asymmetry.md]
The identity element (1, χ₀, k=0, trivial representation) breaks the symmetry that all other elements enjoy. Summing with symmetry produces a constant offset from the identity, not noise. Instance: (1+ζ(2τ)) in c-matrix covariance (c_spectral.md §7).

### A1 (Structured error)
The gap between finite observation and infinite theorem is not noise but structure. Errors decompose into arithmetic + projection + noise components.

### A2 (Convergence as observable)
The rate at which finite observations approach infinite limits is itself an observable. The rate encodes which part of the infinite structure controls the approach.

### A3 (Gauge invariance)
Amplitudes (energies) are gauge-invariant. Phases (directions) are gauge-dependent. Mistaking one for the other is a category error.

### A4 (Non-commutative limits)
The order of taking multiple limits to infinity affects the result. There is no canonical "infinite limit" — only limits along specified paths.

### A5 (Saturation)
In systems with finite constraint counts, power laws observed over limited ranges are local approximations of underlying sigmoid saturation curves. The saturation level A is the infinite-conductor limit of the observable.

**Scope limitation**: A5 applies to systems with FINITE constraint counts (FX: 21, crystal: 4 centering types). It does NOT apply to scale-free systems with infinite constraint hierarchies (critical phenomena, Brownian self-similarity). Critical exponents in scale-invariant systems arise from a different mechanism (renormalization group fixed points) where constraint count is not finite but self-similar across scales. The boundary: if the system has a well-defined maximum conductor, A5 applies; if constraints form an infinite hierarchy, A5 does not.

### A6 (Non-commutative path dependence)
The saturation level A and the path to it depend on WHICH sequence of limits is taken (A4). For FX: fixing N_ccy=8 and extending T does NOT approach A=18.2 (only refines the spectral estimate at fixed conductor). Approaching A requires increasing N_ccy (increasing conductor). The "infinite limit" must specify the path.

### A7 (Scanner hierarchy) [2026-04-23, from Paper D §2.1 axiom 3]

Scan observables (S12 family) are parametrized by one or more scanner variables σ that live in the L-3 evaluation axis. Fixing σ yields a single observable; sweeping σ yields a parametric family. Every Scan member admits the canonical form

    O(σ; D, f) = Σ_{d ∈ D} f(d) · exp( a(σ) · b(d) )

with D = data space, f = arithmetic/geometric weight. The pair (D, f) is the **input specification** read by Arrow 1, and σ is the dimension along which Arrows 2 / 3 evaluate (Arrow 2 = −∂/∂σ log G, Arrow 3 = log |D| at the σ → extreme limit). A0+A3+A7 jointly determine the S15 partition (Scan / Structural / Information).

**Cross-domain instances**:
- ζ(s): σ = s, D = ℤ_{>0}, f = 1, a(s) = −s, b(n) = log n
- Z(β): σ = β, D = energy levels, f = degeneracy, a(β) = −β, b(E) = E
- K(τ): σ = τ, D = unfolded eigenvalues, f = 1, a(τ) = 2πi, b(x) = x
- F(h): σ = h, D = atomic positions, f = atomic factor, a(h) = 2πi, b(r) = h·r
- U(t): σ = t, D = spectral support of A, f = projector weight, a(t) = i, b(λ) = λ

**Source**: Paper D §2.1 axiom 3, c_arrow_framework.md §1 (Arrow 1 selector).

---

## 8. Axis-2 (Finite / Infinite) framework [2026-04-23, L0 v2]

### 8.1 Two-axis refinement of A0

A0 (finite observation) is restated under a 2-axis lens that orthogonalizes
the original "finite vs infinite" content from the "discrete vs continuous"
content.

| Axis | Pole | Pole | Role |
|---|---|---|---|
| **axis-1** | **D** (Discrete) | **C** (Continuous) | Algebraic texture (S15 Trichotomy partition) |
| **axis-2** | **Fi** (Finite) | **I** (Infinite) | Reachability by the observer |

Observer is constitutively on the **Fi side of axis-2**. The I side is an
ideal (mathematical idealization) that the observer never reaches. Observation
is the one-way traversal **I → Fi** of axis-2; the reverse (Fi → I lifting)
is the unbridgeable gap that creates kernel.

### 8.2 L0 v2 reformulation

Rephrasing A0 under the 2-axis lens (Paper D §2.3.1):

- **(a')** [perfect observation impossible] Observer lives on Fi. The Fi → I
  Arrow does not exist. Perfect observation is well-defined as an I-side ideal
  but unreachable.
- **(b')** [kernel as boundary phenomenon] Whenever an Arrow crosses the
  Fi/I boundary on axis-2, kernel (obstruction) develops on the boundary.
  This is the axis-2 cause of "every observation has a kernel".
- **(c')** [kernel admits axis-2 decomposition] T-AAS kernel decomposition
  reads as an axis-2 split:
  - **(c'-1) Fi-side artifact** (ker_gauge family): observer's finite basis
    choice; removable by another Fi gauge. f_torsion contribution.
  - **(c'-2) I-side residue** (ker_topo family): observer-unreachable I-side
    structure leaving an image on Fi; not removable by any Fi gauge.
    f_rational contribution.
  - **(c'-3) Fi → Fi internal irreversibility** (ker_backaction): collapse-
    direction-specific information loss; lives on process-space rather than
    state-space. Independent layer.
- **(d')** [one-line characterization] Observation theory = **classification
  of axis-2 Fi/I boundary phenomena**. Axis-1 D/C supplies the texture of
  this boundary (kernel class internal structure, S15 3-class partition).

### 8.3 Conservative extension (v1 ↔ v2 relation)

L0 v2 is a **conservative extension** of L0 v1 (the umbrella A0 + sub-axioms
A0a/b/c above), not a re-derivation:

- v1 (a) ≡ v2 (a') under translation "perfect observation = Fi → I unreachable"
- v1 (b) ≡ v2 (b') under translation "kernel = Fi/I boundary crossing"
- v1 (c) ⊂ v2 (c'-1, 2, 3): v1's "kernel structure governed by T-AAS"
  is preserved; v2 refines the binary T-AAS split (ker_gauge ⊕ ker_topo)
  into a 3-part axis-2 decomposition by promoting ker_backaction to an
  independent layer.
- v2 (d') is **new content** in v2 (the meta-claim about what observation
  theory itself is).

The extension is conservative: every v1 statement is recoverable from v2
under the translation. v2 adds (d') and refines (c) without invalidating
v1; existing L1 / L2 derivations from v1 remain valid.

### 8.4 Existing framework projections

Each existing piece of the framework projects onto axis-2:

| Framework piece | Axis-2 reading |
|---|---|
| **S15 Trichotomy** (Scan / Structural / Information) | axis-1 partition; each class has both Fi (truncated, observer-reachable) and I (idealized, unreachable) realization (c_theorems_master.md S15 axis-2 projection map) |
| **3 Arrow** (Paper D §4) | every Arrow has an I → Fi axis-2 component; Arrow 2 alone is pure Fi↔Fi / I↔I bridge with no axis-2 traversal |
| **T-AAS** (c_arrow_obstruction.md §10) | ker_gauge = Fi-artifact, ker_topo = I-residue, ker_backaction = Fi→Fi irreversibility; axis-2 unification in §10.0 |
| **S13 / S17** (Arrow 2 / 3 stationary points) | residence axis-2 positioning controls value-fixed (S13) vs derivative-fixed (S17) format shift |
| **Meta-theorem coincide / split** (Paper D §4.5.1) | axis-2 Fi/I commutator = 0 / ≠ 0 (functional-equation enforcement = the rare instance that forces commutativity) |
| **OQ-Ω-Obs-1 classical vs quantum asymmetry** | classical Hodge: Fi/I gap not yet observed (open) vs quantum Schmidt rank: Fi/I gap non-zero by theorem; visible on axis-2 |

**One-line summary**: ΣΦ observation theory = **classification of axis-2 Fi/I boundary phenomena**.

**Source**: Paper D §2.3.1 (L0 v2), c_theorems_master.md §"S15 axis-2 projection map" annex, c_arrow_obstruction.md §10.0 (2-axis lens), research/oq_l0_refinement_finite_infinite_2axis_v0.md.

---

## 9. Corollaries (derived from axioms, verified in L2)

### Corollary of A2: Ratio invariance (2026-04-08, from T8 resolution)

When a quantity is constructed as a ratio of two observer-dependent
measurements, the observer-intrinsic factors can cancel exactly, leaving
only the object-intrinsic structure. This is the mechanism by which
T8's A/B = sqrt(e) remains universal even though A and B individually
drift with K (observation window size).

**General principle**: ratios are object-intrinsic; absolute values are
observer-intrinsic. More precisely:
- c_s = 1/sqrt(2) is object-intrinsic (T1, independent of observation)
- A/B = exp(c_s^2) = sqrt(e) is object-intrinsic (ratio cancels c_W)
- A = B * sqrt(e) is exact, but A and B individually depend on c_W(K)
- c_W(K) is observer-intrinsic (depends on K, see below)

This generalizes: the 5-constant dichotomy of Paper Omega can be partially
reformulated as "what cancels in ratios" vs "what survives only in
absolute values".

### Corollary of A0+A1+A2: Crossover exponents are non-universal (2026-04-08)

The Wishart fluctuation c_W exhibits crossover scaling K^{-0.76} rather than
the naive bulk K^{-1/2}. This follows from A0+A1+A2:

    c_W(K) = c_W^{bulk}(K) + c_W^{edge}(K)
           ~ K^{-1/2} + K^{-2/3} * w(K)

A1 decomposes c_W into bulk (Marchenko-Pastur CLT, codim 0) and edge
(Tracy-Widom soft edge, codim 1). A2 says the convergence rate is itself
observable, so the effective exponent depends on K. A0 says neither
K -> infinity nor K -> N can be reached, so observation is always in the
mixed regime.

For K in [10, 20] (FX measurement range), destructive interference between
bulk and edge drives the effective exponent above the naive additive value:

    alpha_eff ≈ 0.5 + (1/6) * w_eff ≈ 0.76

(Measured: 0.76. Predicted range: [0.5, 0.83]. See c_scaling_laws.md §1.4.)

**Consequence**: The 2% residual in A = 18.2 vs B*sqrt(e) = 17.81 is NOT
a correction to be eliminated. It is an observation axiom signature:
the principled non-universality that A0+A1+A2 require for any quantity
measured in a finite window.

### Corollary of A0+A3 (定数の gauge 射影性, 2026-04-09)

L0 の有限窓テーゼ (A0) と gauge 不変/依存の区別 (A3) は数学定数にも適用される。同一定数が異なる gauge で異なる intrinsic 度を持つ (origination matrix)。離散整数 gauge と連続位相 gauge のどちらも「真」とは主張できず、両者は定数の射影を与える。

具体例: 虚数単位 i は二つの独立な起源を持つ。加法指標としての i (4|L, p=2 起源) と乗法指標としての i (4|φ(L), p≡1 mod 4 起源) は独立条件で発生し、同じ定数 i = √-1 に合流する。定数が「一つ」であることは起源が「一つ」であることを意味しない。

旧 5 定数 dichotomy {φ,π,i} vs {e,γ} は origination matrix で棄却された。Φ は離散 gauge (multiplicative) にのみ intrinsic、π は連続 gauge にのみ intrinsic であり、同じ族を形成しない。新しい分類は離散↔連続のスペクトルとして記述される。

詳細: Paper Ω (Origination)。検証スクリプト: arithmetic_quartet.py, constants_origin.py, gamma_origin.py。
