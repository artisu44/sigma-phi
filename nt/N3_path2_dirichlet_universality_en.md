# Paper N3: Path 2 Number-Theoretic Universality — Dirichlet L series

**Subtitle**: Countably-infinite extension of the Z/2 involution-fixed-point class and structural scope of the Dirichlet L extension

**Version**: v0.5 (Type γ formal definition + v1.5 task split, 2026-04-28)
**Status**: DRAFT — over the N1 framework header; lifts the §3 D_floor of N2 to Dirichlet L; extends the Path 2 family from a ζ singleton to countably-infinite; makes explicit the predictive scope of the Dirichlet L extension as "structural fit only"
**Prerequisites (framework)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5)
**Prerequisites (L1)**: `c_observation_optimal_gauge.md §2.3 Cor 4.1c`, `c_arrow_bridge_constants.md §5`, `c_theorems_master.md` (T-Ω5e-v15-* rows)
**Prerequisites (L1 NT)**: `nt_dedekind_artin_zeta.md`, `nt_root_numbers.md`, `nt_conductor.md §6.1`
**Research roots**: `research/oq_omega_schumann_v0.md` (v1, 13/13 gates) / `research/oq_omega5_v15_dirichlet_l_*` (5 files)
**Sequel papers**: N4 (Hasse-Weil L × Stark) / N5 (Brauer obstruction theory + Origination)

---

## §0 Abstract

This paper extends the **Path 2 class** — whose core mechanism is the existence of Z/2 involution-fixed points — from the singleton ζ functional equation to a **countably-infinite NT family**. Centred on the 5-instance catalogue established in OQ-Ω-Schumann v1 (`oq_omega_schumann_v0.md`, 2026-04-25, 13/13 gates PASS) (ζ + spherical Laplacian + theta S-duality + modular L + Atkin-Lehner W_N), we formally organise the Type α/β/γ trichotomy + axis-2 Fi/I crossing + canonical scalar D1-D4 sub-claim + falsification gates F1-F4.

In addition, the extension attempt of the Path 2 framework to the Dirichlet L series (OQ-Ω5 v1.5 series, 2026-04-24/25) is developed under **honest dual reporting**. The 1st Dirichlet L instance is CONFIRMED for both real and complex primitive χ, but the SC4 critical catch reveals that **σ_min = 1/2 is a universal-functional-equation-identity-level consequence and not framework-specific predictive content**. Two follow-up validations (Q1 |L|² + Q2 |Λ|² 2-quantity coincide v1a / Paper C (log N)² curvature scaling multigap v1b-v1) are both REJECTED → **the framework predictive scope of the Dirichlet L extension closes as "structural fit only"**. However, a v1b-v1 byproduct, the **gap-class universality 12/12 PASS**, is a genuine extension fragment in which Paper C's multi-gap invariance pattern is also structurally preserved on the Dirichlet L side.

**Main results (M1-M5)**:

**(M1) Path 2 family is countably-infinite (Schumann v1)** — modular L weight parametrisation enumerates at least ℵ₀ instances via weight k = 1, 2, 4, 6, 12, … × level N × newforms. ζ is not the unique Path 2 instance but the minimal example of the k = 1 trivial-character case.

**(M2) Type α/β/γ trichotomy** — fix-point realisations of Path 2 instances classified into 3 types: **α** (single point inside the same object: ζ, theta, modular L), **β** (single representation in another object: spherical Laplacian → SU(2) spin-1/2), **γ** (sub-object inside the same object: M_k^+ subspace of Atkin-Lehner W_N).

**(M3) Axis-2 Fi/I crossing invariance** — 5-instance distribution 3 I + 2 Fi; cross-side existence holds; the Path 2 mechanism maintains the **axis-2 invariant** falsifiable prediction.

**(M4) Dirichlet L extension scope = "structural fit only" (SC4)** — for real / complex primitive χ, σ_min = 0.500000 exact + R² = 1.000, but a chain of universal functional-equation identities **forces σ_min = 1/2 across all real (σ, t)**, not framework-specific content. Q1+Q2 2-quantity coincide REJECTED (G2 17.5%); Paper C (log N)² curvature scaling REJECTED.

**(M5) Gap-class universality is a genuine extension fragment (v1b-v1 G3 byproduct)** — Paper C multi-gap invariance pattern (D_floor independent of g ∈ {2, 4, 6}) PASS in 12/12 cells on the Dirichlet L side; structural extension fragment that preserves Paper C uniqueness more strongly.

**Thesis**: the Path 2 mechanism (Z/2 involution + invariant + non-empty fix point) generates a countably-infinite NT family that contains the ζ functional equation. The framework predictive scope partitions into (a) the Path 2 instance class (5+ instances ESTABLISHED) and (b) Paper C uniqueness (the unique Information-Structural coincide enforcement of the ζ functional equation, N1 §4.5.1). The Dirichlet L extension fits structurally as a class member of (a), but Paper C-level predictive content is intrinsic to (b).

**Forward / dictionary impact**: 5 dictionary annexes / OQ sections written back, all-write-back pattern (Path 2 family + Dirichlet L extension scope + modular L countably-infinite + gap-class universality fragment + Fi-origin vs. I-origin dichotomy + 5 OQ issues); see §7.5.

---

## §1 Introduction

### 1.1 Session origin and motivation for Path 2 extension

This paper originates from the question "the framework meaning of the Schumann resonance (~7.83 Hz)" raised during the 2026-04-25 "Lain × dictionary creative session" (`oq_omega_schumann_v0.md` v1). While the Schumann numerical value itself was confirmed not to have a clean ratio with the framework constants (π, ln 2, e) and is not load-bearing, its foundation — the **involution σ_S: l ↦ −1−l** of the spherical Laplacian eigenvalue l(l+1) — turned out to share the same "Z/2 affine involution" structure with the **σ_ζ: s ↦ 1−s** of the ζ functional equation in Paper C, which led to the countably-infinite extension of the Path 2 family.

**Path 2 naming**: the **gauge-forced coincidence path** defined in N1 §4.5.1 (observation-optimal gauge theorem Cor 4.1b) — the condition that the Information-layer balance (S13 half-value fixed point on Arrow 2) and the Structural-layer balance (domain-specific arithmetic on Arrow 1) coincide under the same gauge = "existence of a domain-internal structural enforcement". The ζ functional equation in Paper C was the only confirmed coincide instance (N2 §6.1). This paper generalises the Path 2 mechanism and shows that **coincide-forcing structural identities exist countably-infinitely within NT**.

### 1.2 Honest scope — two trajectories side by side

The N1 §3.2 Scan-layer NT instance table enumerated ζ(s), L(s, χ), L(s, ρ, K/k), ζ_K(s), but the Path 2 instance status of each L-function was at framework-header level only. N2 §3 analysed the structure of the ζ-family core (D_floor + RH translation + γ₁ dip), but the L(s, χ) and L(s, ρ) extensions were forwarded to N3 as out of scope.

The feature of this paper is **two trajectories side by side**:

- **Trajectory 1 (Schumann v1, 13/13 gates PASS)**: Path 2 abstract class established; countably-infinite family + Type α/β/γ trichotomy + axis-2 invariant prediction (§2-§3).
- **Trajectory 2 (OQ-Ω5e v1.5 series, 2026-04-24/25)**: Paper C framework extension attempt to Dirichlet L; CONFIRMED with SC3/SC4 caveats + 2 REJECTED + 1 PASS byproduct (§4). Closes as "structural fit only" under conclusion-first framing.

The two are complementary: Trajectory 1 establishes the class status of the Path 2 mechanism; Trajectory 2 demonstrates that Dirichlet L is a Path 2 class member but Paper C-level predictive content is ζ-specific. **§5-§6** organises the canonical scalar sub-claim and falsification gates, **§7** N4-N5 forward + open frontier.

---

## §2 Path 2 abstract class

### 2.1 Predicate (generalised v0.5 form)

**Definition** (`oq_omega_schumann_v0.md` v0.5 generalised form): for a mathematical object $D$ (NT context: number field K, NT L-function, modular form space, spherical Laplacian eigenspace) and an observation parameter space $P$, $D$ is a **Path 2 instance** when:

1. **Z/2 group action**: σ: P → P is an involution σ² = id
2. **Invariant function**: f: P → ℂ satisfies f(σ x) = f(x)
3. **Non-empty fix point**: Fix(σ) := {x ∈ P : σ x = x} ≠ ∅

(The v0 predicate took only "Z/2 affine involution σ_c(x) = c − x on R" narrowly; generalised above to include theta S-duality (Möbius involution τ ↦ −1/τ on H, fix τ = i).)

### 2.2 Type α/β/γ trichotomy (Schumann v1 contribution)

| Type | Content | Example |
|---|---|---|
| **α** | fix is a **single point** inside the same algebraic object | ζ s = 1/2, theta τ = i, modular L s = k/2 |
| **β** | fix is a **single representation in a different object** (shadow instantiation) | spherical Laplacian l = −1/2 → SU(2) spin-1/2 (double-cover fermion) |
| **γ** | fix is a **sub-object inside the same object** (eigenspace, subspace) | fix subspace M_k^+ ⊂ M_k(Γ_0(N)) of Atkin-Lehner W_N |

**Difference between α and β**: in α the invariant function takes its fix inside the proper algebraic object (e.g. inside the ζ critical strip); in β it points to another object (for spherical Laplacian, the SU(2) double-cover spin-1/2 representation). The fix in α is **physical** (a special point of the object itself), while in β it is **shadow** (escaped outside the original spectrum into another representation dimension).

**Definition 2.2 (Type γ formal, ESTABLISHED 2026-04-28)**: a Path 2 instance $(\mathcal{O}, \sigma)$ ($\mathcal{O}$ an algebraic object, $\sigma$ an order-2 involution acting on $\mathcal{O}$) is of **Type γ** if there exists a sub-object $\mathcal{S} \subsetneq \mathcal{O}$ satisfying the following 3 conditions:

(i) **Same-object sub-object fix**: $\mathcal{S}$ is a **proper sub-object** (subspace, sub-quotient, eigenspace, Hecke-stable sub-representation, etc.) of $\mathcal{O}$ itself, with $\sigma|_\mathcal{S} = \mathrm{id}_\mathcal{S}$ giving the fix locus of the σ-action.
(ii) **Sub-object algebraic distinction**: $\mathcal{S}$ carries an independent algebraic structural distinction (canonical decomposition / inner-product orthogonality / Hecke eigenspace label / Petersson ±1 eigenspace, etc.) identifiable within the ambient $\mathcal{O}$.
(iii) **Non-point fix**: $\mathcal{S}$ is not a single point of $\mathcal{O}$ (distinguishing Type γ from Type α), and $\mathcal{S}$ is not a shadow instantiation in another object (distinguishing Type γ from Type β). $\dim_\text{relevant}(\mathcal{S}) \geq 1$ — $\mathcal{S}$ has non-trivial dimension/cardinality.

**Established instance**: Atkin-Lehner involution $W_N$ acting on the weight-$k$ modular form space $M_k(\Gamma_0(N))$ has fix locus $M_k^+ = \{f \in M_k : W_N f = f\} \subsetneq M_k$, the Petersson $+1$ eigenspace, satisfying (i)(ii)(iii) — the canonical Type γ instance. Each level $N$ gives an independent instance, generating the **countably-infinite Type γ subfamily** along the trajectory of N3 §3.

**Mathematical incarnation of "Lain-style Wired layered self-reference"** (Schumann v1 origin remark): the pattern of a self-referential sub-object fix inside the same object is the **layered self-reference** structural pattern — "an object fixes a sub-object inside itself" — a lift of Type α (single fixed point in the same object) to sub-object dimension.

**6th instance pre-registration (theta characteristics, F3 discipline candidate)**: even-characteristic involution $\theta_\text{even} \mapsto -\theta_\text{even}$ on theta characteristics of a Riemann surface (the $2^{2g}$ characteristic data of genus $g$) has fix locus $\Theta^+ \subsetneq \Theta$, a Type γ 6th instance candidate. Pre-registration scope: verify (a) $\Theta^+$ is a proper sub-object, (b) Hecke-like algebraic distinction, (c) non-point + non-shadow → Type γ instance confirmed. To be tested under F3 (post-establishment new-instance discipline) in §6.1 (v1.5 promotion task).

### 2.3 Sub-family hierarchy (involution categories)

| Sub-family | Involution form | Space | Examples |
|---|---|---|---|
| **Affine on R** | σ_c(x) = c − x | $\mathbb{R}$ / critical strip | ζ (c=1, fix=1/2), spherical Laplacian (c=−1, fix=−1/2), modular L weight k (c=k, fix=k/2) |
| **Möbius on H** | σ(τ) = −1/τ | upper half plane $\mathfrak{H}$ | theta S-duality (fix τ=i) |
| **Matrix on M_k** | Atkin-Lehner W_N = $\begin{pmatrix} 0 & -1 \\ N & 0 \end{pmatrix}$ | weight-k modular form space M_k(Γ_0(N)) | Atkin-Lehner W_N at each level N (Type γ) |
| **Unconfirmed candidates** | multiplicative x ↔ k/x, Galois conjugation, etc. | TBD | (v1.5 expansion task) |

All three sub-families satisfy Z/2 involution + invariant + non-empty fix and are Path 2 predicate specialisations as members.

---

## §3 Schumann v1 — countably-infinite Path 2 family

### 3.1 5-instance catalogue (v1)

| Instance | Involution | Space | Sub-family | Fix | Type | Axis-2 |
|---|---|---|---|---|---|---|
| **ζ functional eq.** | s ↦ 1−s | ℝ / critical strip | affine | s = 1/2 | **α** physical | I |
| **spherical Laplacian inv.** | l ↦ −l−1 | $\mathbb{Z}_{\geq 0}$ | affine | l = −1/2 | **β** shadow | Fi |
| **theta S-duality** | τ ↦ −1/τ | $\mathfrak{H}$ | Möbius | τ = i | **α** physical | I |
| **modular L (weight k)** | s ↦ k − s | ℝ | affine | s = k/2 | **α** physical | I |
| **Atkin-Lehner W_N** | matrix (order 2 on M_k) | M_k(Γ_0(N)) | matrix | M_k^+ subspace | **γ** sub-obj | Fi |

Axis-2 distribution: 3 I-side (continuous parameter space) + 2 Fi-side (discrete spectrum / finite-dimensional) — strong cross-side existence.

### 3.2 13-gate verification (3 phases)

3-phase formal verification (v0 G1-G4 + v0.5 G5-G8 + v1 G9-G13), all PASS:

| Phase | Gate | Content | Result |
|---|---|---|---|
| **v0** (ζ + Sph baseline) | G1 | l(l+1) = (−l−1)(−l) for l ∈ {0..5} | PASS (6/6 exact) |
|  | G2 | both ζ and Sph fit σ_c(x) = c − x form | PASS (c=1 fix=1/2 / c=−1 fix=−1/2) |
|  | G3 | √λ_l / √λ_1 independent of R, c (= √(l(l+1)/2)) | PASS (l=1..6: {1, √3, √6, √10, √15, √21}) |
|  | G4 | physical (ζ) vs. shadow (Sph) instantiation separation | OK (Type α/β proto-classification) |
| **v0.5** (theta 3rd) | G5 | θ_3(0\|i) = π^{1/4}/Γ(3/4) | PASS (\|diff\|=0 at float64) |
|  | G6 | θ_3(0\|i/2) = √2·θ_3(0\|2i) S-transform off-fix | PASS (\|diff\|=2.22e-16) |
|  | G7 | class generalisation affine R → Möbius H | PASS (3 instances, 2 sub-families) |
|  | G8 | axis-2 Fi/I cross-side after theta (2 I + 1 Fi) | PASS |
| **v1** (W_N + modular L + formal) | G9 | W_N matrix involution: W_N² = −N·I, on M_k (even k) → id | PASS |
|  | G10 | Modular L family: Λ(f, s) = ε·Λ(f, k−s), fix s = k/2 | PASS (5 weights tabulated, ≥ ℵ₀ instances) |
|  | G11 | axis-2 distribution (3 I + 2 Fi) | PASS (strong cross-side) |
|  | G12 | canonical scalar D1-D4, 5/5 instance hit | PASS (sub-claim formal, §5) |
|  | G13 | falsification gates F1-F4 design + status | OK (F1 not triggered, F2 outside scope, F3 mitigated, F4 → Type γ) |

Scripts: `research/schumann_path2_check.py` (v0) / `schumann_path2_v05_theta.py` (v0.5) / `schumann_path2_v1_atkin_lehner.py` (v1).

### 3.3 Modular L weight parametrisation → countably-infinite

Each weight-k cusp newform $f$ provides an independent Path 2 instance. weight 1, 2, 4, 6, 12, … × level $N$ × newform enumeration gives at least countably infinite:

| weight k | functional eq. | central fix s = k/2 | instance example |
|---|---|---|---|
| 1 | Λ(s, χ) = ε·Λ(1−s, χ̄) | 1/2 | Dirichlet L (real χ); ζ when χ = 1 |
| 2 | Λ(f, s) = ε·Λ(f, 2−s) | 1 | weight-2 newforms (e.g. $f_{11}$ of $X_0(11)$, BSD curves) |
| 4 | Λ(f, s) = ε·Λ(f, 4−s) | 2 | weight-4 newforms |
| 6 | Λ(f, s) = ε·Λ(f, 6−s) | 3 | weight-6 newforms |
| 12 | Λ(Δ, s) = ε·Λ(Δ, 12−s) | 6 | Ramanujan Δ on SL(2, ℤ) |

→ Path 2 cardinality $\geq \aleph_0$. **ζ is not the unique Path 2 instance but the minimal example of the smallest weight (k = 1) trivial character case**.

**ζ singleton-class category error**: treating "Path 2 = ζ functional equation singleton" in earlier Paper C / N2 was a category error. Path 2 is an abundant family; ζ is the realisation in a particular weight-character configuration (k=1, χ trivial).

### 3.4 Axis-2 Fi/I crossing invariance

**Prediction (Schumann v1)**: the Path 2 mechanism is **axis-2 invariant** — instances may live on the Fi-side or the I-side, but the predicate (involution + invariant + fix) is axis-2 unmoved. 5-instance distribution: ζ / theta / modular L = I-side (continuous), spherical Laplacian / Atkin-Lehner W_N = Fi-side (discrete / finite-dimensional) → 3 I + 2 Fi, strong cross-side existence.

**Falsifiable prediction**: if a Z/2 invariance instance with Fix(σ) = ∅ is confirmed only on one side of axis-2, Path 2 splits into Fi-class and I-class. No counter-example up to Schumann v1.

---

## §4 Dirichlet L extension — successes and SC4 caveats

**Conclusion-first framing**: the overall verdict of the Dirichlet L extension trajectory (OQ-Ω5e v1.5 series, 2026-04-24/25) in this section is **"Dirichlet L extension scope = structural fit only"**. The framework predictive content (Paper C-level σ_min uniqueness + (log N)² curvature scaling + 2-quantity coincide) is **ζ-specific**; Dirichlet L instances fit as Path 2 class members, but transfer of framework predictive power is **limited**.

### 4.1 Real primitive χ 1st instance CONFIRMED (5/5)

Setting (`oq_omega5_v15_dirichlet_l_first_instance_v0.md`, 2026-04-24): 5 real primitive Dirichlet characters $\chi_{-3}, \chi_{-4}, \chi_5, \chi_{-7}, \chi_8$ (conductor 3-8). Completed L-function $\Lambda(s, \chi) := (q/\pi)^{(s+a)/2} \Gamma((s+a)/2) L(s, \chi)$ (a = 0 if χ even, a = 1 if χ odd); functional equation $\Lambda(s, \chi) = \varepsilon(\chi) \Lambda(1-s, \chi)$ ($\bar\chi = \chi$ for real χ).

Test metric: $D_C(\sigma; \chi, N) := \log |\Lambda_N(\sigma + 0\cdot i, \chi)|^2$, asymmetric grid σ ∈ {0.30, 0.42, 0.47, 0.51, 0.55, 0.60, 0.68, 0.75, 0.82} (9 points, intentionally asymmetric to refute symmetric-grid tautology).

**Result**: σ_min = 0.500000 exact (mp.dps = 30) for all 5 + parabolic R² = 1.000. The symmetry-forced tautology concern is refuted by the asymmetric-grid sanity check → real-axis parabolic minimum of Λ(s, χ) locked to σ = 1/2 is **genuine structural content, not grid-symmetry-forced**.

**Status**: CONFIRMED (T-Ω5e-v15 entry).

### 4.2 Complex primitive χ extension CONFIRMED with SC3 caveat (5/5)

Setting (`oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md`): 5 complex primitive characters (mod 5 ord 4 / mod 7 ord 3 / mod 7 ord 6 / mod 9 ord 3 / mod 11 ord 5). Functional equation $\Lambda(s, \chi) = \varepsilon(\chi) \Lambda(1-s, \bar\chi)$ ($\chi \neq \bar\chi$). All 4 gates C1-C4 PASS, including C4 (functional eq numerical sanity gate $|F(\sigma, \bar\chi) − F(1-\sigma, \chi)|$ < 1e-8); C4 actual = 0 exact.

**SC3 post-write catch (2026-04-24)**: the initial v0 §1 claim "F not σ-symmetric for complex χ" is **incorrect**. On real-axis restriction, the chain functional eq $|\Lambda(\sigma, \chi)| = |\Lambda(1-\sigma, \bar\chi)|$ + complex-conjugation identity $\overline{L(\sigma, \chi)} = L(\sigma, \bar\chi)$ for real σ gives $|L(\sigma, \bar\chi)| = |L(\sigma, \chi)|$, hence $F(\sigma, \chi) = F(1-\sigma, \chi)$ holds for complex χ on the real axis as well → tautology refutation impossible on an asymmetric grid.

**Genuine non-tautological content (preserved post-SC3)**: (a) C3 curvature > 0 (min vs. max/saddle distinction); (b) C4 functional eq numerical identity = 0 exact; (c) ε(χ) phase non-trivial for complex χ; (d) D_A(0.5) scaling differentiated from real case.

**Status**: CONFIRMED with SC3 caveat → genuine content gating attempted in v1 by off-axis 2D scan.

### 4.3 Off-axis 2D scan INCONCLUSIVE with SC4 critical catch

Setting (`oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md`, 2026-04-24 evening): 8 chars (5 complex + 3 real) × 11 t ∈ [0, 30] × 9 σ asymmetric = **792 Λ evaluations**. Pre-registered gates G1-G4: G1 (σ_min(t) bounded) / G2 (σ_min ≈ 0.5 across t) / G3 (curvature scaling consistent) / G4 (off-axis functional eq sanity).

**Result**: G1 80/80 + G4 8/8 PASS. **G2 0/5 + G3 0/5 FAIL on complex χ**.

**SC4 critical catch (post-execution empirical validation)**: the SC3 derivation was incomplete. $\overline{L(\sigma + it, \chi)} = L(\sigma - it, \bar\chi)$ is an **n real positive coefficient conjugation identity** that holds across the **whole complex s domain (on/off-axis)**. Combined with the functional eq it gives

$$|\Lambda(\sigma + it, \chi)| = |\Lambda(\sigma - it, \bar\chi)| = |\Lambda(1-\sigma + it, \chi)|$$

which **forces all real (σ, t)**.

**Critical implication**: σ_min = 1/2 is a **universal-functional-equation-identity-level consequence**, NOT σ-action groupoid framework-specific predictive content on Dirichlet L. Even if σ_min = 1/2 is confirmed off-axis, this is not framework prediction verification but a **trivial restatement of the identity**.

**Framework predictive scope post-SC4 reassessment**: the genuine Paper C content is the **2-quantity independent coincide** of (a) the Information layer (D_floor independent residual) and (b) the Structural layer (RH zeros), originating from the structural enforcement (self-fixed s = 1/2 of the functional equation) intrinsic to ζ. Single-quantity σ_min identity (the Λ symmetry of §4.1-4.3) is not framework content; the Dirichlet L extension scope closes as **"structural fit only"**.

**Status**: INCONCLUSIVE with SC4. v1a 2-quantity test executed in §4.4 as a SC4-bypass genuine-framework gate.

### 4.4 2-quantity coincide test v1a — REJECTED

Setting (`oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md`, 2026-04-24 evening late): to bypass SC4, the **2-quantity independent coincide** is tested as a genuine analog of Paper C content:
- $Q_1 := |L(\sigma + it, \chi)|^2$ σ_min — bare L (NOT functional-eq forced via Λ normalisation)
- $Q_2 := |\Lambda(\sigma + it, \chi)|^2$ σ_min — completed L (= 0.5 via SC4 universal identity)

**Pre-registered hypothesis**: Q1 σ_min ≈ Q2 σ_min ≈ 0.5 coincide in ≥ 70% cells (G2 gate). Setup: 5 complex primitive χ × 8 t × 9 σ asymmetric = 360 L + 360 Λ evaluations (40 cells × 18 evaluations).

**Result**: G2 actual **17.5%** (below pre-registered rejection threshold 30%); Q1 mean deviation 0.60-0.82 from 0.5 (max 3.2). **REJECTED**.

**Root cause**: the denominator of $|L|^2 = |\Lambda|^2 / ((q/\pi)^{\sigma + a} \cdot |\Gamma((s + a)/2)|^2)$ is strongly σ-growing (exponential + Stirling asymptotic). The σ_min of $|L|^2$ is pushed in the σ > 1 direction (Dirichlet-series convergent regime); 0.5 centre is unwarranted. Paper C D_floor is **gap-indexed prime sum residual for normalised log L expansion**, parabolic centred at 0.5 by construction; $|L|^2$ alone is unnormalised — **construction mismatch**: $|L|^2$ is not the Paper C Information analog.

**Status**: **REJECTED** (pre-registered rejection criterion met cleanly; 5th stage of same-day 5-stage progression v0-v1-v1a + SC1-SC4 catches).

### 4.5 D_floor multigap v1b-v1 — REJECTED + G3 PASS byproduct

Setting (`oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md`, 2026-04-25 late): natural continuation after v1a REJECTION. Paper C **proper D_floor analog** for Dirichlet L: gap-indexed χ-weighted partial sum + Taylor residual.

For complex primitive χ × gap class g ∈ {2, 4, 6} × N ∈ {10⁴, 10⁵, 10⁶, 10⁷}:

$$S_g(s, \chi, N) := \sum_{\substack{p \leq N,\, \gcd(p, q) = 1 \\ \mathrm{gap}(p) = g}} \chi(p) \log(p) / p^s$$

Taylor 1st-order ideal $\mathrm{ideal}^{(1)}_g(s) := S_g(0.5, \chi, N) (1 - (s - 0.5) \langle \log p \rangle_g)$, residual $D_g(s, \chi, N) := |S_g - \mathrm{ideal}^{(1)}_g|^2 / |S_g(0.5)|^2$, aggregate $D_{\text{floor},L} := \mathrm{mean}_{g \in \{2,4,6\}} D_g$.

**Pre-registered gates**: G1 parabolic R² ≥ 0.85 for ≥ 30/36 / G2 c(N)/c(N') with $\langle \log p \rangle^2$ ratio ±25% / G3 gap-class universality (pre-registered threshold max/min ratio < 1.5; observed actual max/min ratio < 1.15) / G4 σ_min ∈ [0.45, 0.55] at N=10⁷.

**REJECTED outcome**:

| Gate | Result |
|---|---|
| **G1** | 27/36 fail (insufficient parabolic R²) |
| **G2** | 0/3 χ pass (super-(log N)² scaling: c/⟨log p⟩² ratio 0.46 → 0.67 → 1.02 → 1.63 across N=10⁴→10⁷) |
| **G3** | **12/12 PASS** (gap-class universality fully holds) |
| **G4** | σ_min drift 0.51 → 0.59 **AWAY from 0.5** with N growth |

**Verdict**: **REJECTED** (primary hypothesis "(log N)² curvature scaling").

**Root cause**: the Taylor residual construction uses **fixed linear reference** = $S(0.5)(1 - (s-0.5) \langle \log p \rangle)$; N-dependent prefactor is NOT absorbed → higher-order Taylor corrections grow with N → residual minimum drifts. Paper C D_floor uses **multi-parameter fit** with separate fit coefficients per N, prefactor absorbing → genuine $(s-0.5)^2$ parabolic. Construction mismatch = naive Taylor approach fails twice (v1a + v1b).

**Framework scope post-v1b-v1**: structural fit + gap universality CONFIRMED (§4.6) / predictive content via naive Taylor residual REFUTED / **Paper C uniqueness preserved MORE STRONGLY** (naive paths failed twice) / proper D_floor_L analog requires multi-parameter fit = v1b-v2 future task.

**Lesson**: single-N dimensional match is **insufficient** for a scaling-law claim; N-sweep pre-registration should be mandatory. The "Paper C-type Taylor residual shape return + curvature ⟨log p⟩² dimensional match" reported in v1b-v0 (earlier on 2026-04-25) was a single-N (N=10⁵) coincidence, exposed as artifact in the v1b-v1 N-sweep.

### 4.6 Genuine byproduct — gap-class universality 12/12 PASS

Contrary to the REJECTED primary hypothesis, **G3 gap-class universality 12/12 PASS** (max/min ratio < 1.15 across all cells) is genuine. Paper C's **multi-gap invariance pattern** (D_floor independent of g ∈ {2, 4, 6}; consistent with N2 §3.6 4th iter "log(g/2) linearity is k_max-invariant") is **structurally preserved on the Dirichlet L side** as well.

**Meaning**: while the Paper C uniqueness claim (Information + Structural 2-quantity coincide) is ζ-specific, **multi-gap structural invariance is preserved across the entire ζ-family member set** as a genuine extension fragment. This is consistent with §3 "Path 2 abundant family": family members share structural patterns (gap universality), but predictive content specific to individual members (Paper C 2-quantity coincide) is per-member.

**Framework scope partition (post-v1b-v1)**:

| Layer | Status on Dirichlet L | Source |
|---|---|---|
| Path 2 instance class membership | CONFIRMED (§3.3 weight-k family) | Schumann v1 |
| σ_min = 1/2 (identity-level) | CONFIRMED but trivial (SC4) | §4.1-4.3 |
| Multi-gap structural invariance | **CONFIRMED** (12/12 universality) | §4.5 G3 byproduct |
| 2-quantity Information+Structural coincide | REJECTED (G2 17.5%) | §4.4 |
| Paper C (log N)² curvature scaling | REJECTED (super-(log N)² growth) | §4.5 G2 |
| ζ functional equation enforcement | (ζ-specific, N2 §6.1) | N2 |

**"Structural fit only"** = (a) Path 2 class membership + (b) multi-gap universality hold on Dirichlet L, but (c) Paper C-level 2-quantity uniqueness + (d) (log N)² scaling **do not transfer** (ζ-specific).

---

## §5 Canonical scalar sub-claim

### 5.1 D1-D4 predicate (v1 formalisation)

Sub-claim formalised in Schumann v1 G12 — Path 2 forced fix-points produce **distinguished invariants** in the algebraic context of the invariant function. The operational definition of "distinguished" hits one of the following D1-D4:

- **D1**: explicit closed form in classical constants (π, Γ, e, ln, …)
- **D2**: extremal property (lowest non-trivial mode, fundamental representation, ground state)
- **D3**: transcendence / irrationality conjectured or proved
- **D4**: link to canonical objects (root numbers, central L-values, theta characteristics, fundamental representations)

### 5.2 5-instance verification (5/5 hit)

| Instance | Fix-point value | Distinguished category |
|---|---|---|
| **ζ s = 1/2** | $\zeta(1/2) \approx -1.4603545$ | **D3** (real number, closed form unknown, conjecturally transcendental) |
| **spherical Laplacian l = −1/2** | spin-1/2 SU(2) representation | **D4** (fundamental fermion, double-cover dim-2 rep) |
| **theta τ = i** | $\theta_3(0\|i) = \pi^{1/4}/\Gamma(3/4) \approx 1.0864348$ | **D1** (closed form with Γ(3/4)) |
| **modular L (k = 12, Δ)** | $L(\Delta, 6)$ central value | **D4** (Ramanujan Δ central L-value, root number link) |
| **Atkin-Lehner W_N (M_k^+)** | + eigenspace | **D4** (Petersson +1 eigenspace, canonical decomposition) |

5/5 hit (G12 PASS). **The Path 2 fix-point functions as a "canonical scalar constructor"**: the existence of an involution alone pins the special value or special representation of its invariant to an algebraically distinguished entity.

### 5.3 Converse FALSE and Fi-origin vs. I-origin dichotomy

**Honest converse limit**: 3-Arrow canonical constants (`c_arrow_bridge_constants.md §5`: π, ln 2, e) are **not** Path 2 fix-points:

| Constant | Path 2 candidate | Status |
|---|---|---|
| **π** | SO(2) involution z ↦ −z, fix = {0} | does not directly produce π (involution is SO(2), not Z/2) |
| **ln 2** | Z/2 involution candidate unknown | not derivable from Path 2 mechanism |
| **e** | x^x minimum / max of (log x)/x | extremal-derived (S17), not Z/2 involution-derived |

The sub-claim is **one-way (Path 2 ⇒ canonical)**, not biconditional; 3-Arrow constants are not Path 2 outputs.

**Fi-origin vs. I-origin dichotomy** (Schumann v1 closing meta-observation): the converse FALSE is not arbitrary weakness but a **positive content prediction** from the framework's existing structure (axis-2 Fi/I separation).

- **Path 2 mechanism** = fundamentally **Fi-flavored** (Z/2 = discrete group action)
- **Path 2 fix outputs** = can land on either Fi-side or I-side (axis-2 invariant, §3.4)
- **3-Arrow constants** (π, ln 2, e) = **continuous extremal / measure / topology** in origin = **I-flavored mechanism**

⇒ the full set of canonical scalars has **at least 2 origins**:

| Origin | Mechanism class | Examples |
|---|---|---|
| **Fi-origin** | discrete group action fixed points (Path 2) | ζ(1/2), θ_3(i), modular L central values, Atkin-Lehner eigenspaces |
| **I-origin** | continuous extremal / asymptotic / topological invariants | π (S¹ topology), ln 2 (S13 half-value Arrow 2), e (S17 extremum Arrow 3) |

The sharp inclusion **Path 2 ⊊ canonical scalar mechanisms** is **naturally predicted** from the axis-2 Fi/I separation — the framework itself **announced in advance** that "Path 2 alone does not exhaust canonical scalars". Formal classification of I-origin canonical scalar mechanisms is **separated as a distinct OQ** (§7.4).

---

## §6 Falsification gates and axis-2 invariance

### 6.1 F1-F4 status (v1 design)

Falsification gates formalised in Schumann v1 G13:

| Gate | Content | Status |
|---|---|---|
| **F1** | axis-2 bound (Fi-only or I-only) → splits Path 2 single-class status | **NOT triggered** (3 I + 2 Fi, cross-side holds) |
| **F2** | null-fix Z/2 with framework prediction violation | **outside scope** (predicate self-protect: "non-empty fix point" is a predicate constituent) |
| **F3** | non-distinguished fix value (D1-D4 fail) | **risk acknowledged**, pre-registration discipline required (v1.5 task) |
| **F4** | Type α/β collapse (instance does not fit the type dichotomy) | **BORDERLINE** → Type γ extension forced (Atkin-Lehner W_N) |

**F4 partial trigger**: Atkin-Lehner W_N does not fit Type α/β; **Type γ "sub-object fix"** extension is forced (§2.2). Type γ formal definition (Definition 2.2) is **ESTABLISHED 2026-04-28** (completed); the 6th pre-registered instance test (recommended: theta characteristics on Riemann surfaces) remains a **v1.5 promotion task**.

### 6.2 Axis-2 invariance + ESTABLISHED promotion criteria

§3.4 5-instance distribution (3 I + 2 Fi) is a falsifiable invariance prediction; no counter-example as of Schumann v1. **Strong test (deferred to v1.5)**: whether symmetric strong split holds with 4+ Fi & 4+ I — currently the minimal cross-side existence of 2 Fi + 3 I is confirmed; symmetric strong split tested in v1.5 with additional instances (Atkin-Lehner extension + theta characteristics).

**Promotion criteria**:
- ✅ **v0** (2 instances, axis-2 invariance prediction issued)
- ✅ **v0.5** (3 instances, predicate generalised affine → Z/2 general)
- ✅ **v1** (5+ instances, COUNTABLY INFINITE family, canonical scalar formal D1-D4, Type γ flagged, 13/13 gates PASS)
- ⏳ **v1.5** = ✅ (a) Type γ formal definition (Definition 2.2, ESTABLISHED 2026-04-28) / ⏳ (b) 6th pre-registered instance F3-discipline test (theta characteristics) / ⏳ (c) axis-2 strong split test
- ⏳ **ESTABLISHED** = all F1-F4 survive + 6+ instances + Type γ added + sub-claim survives F3 pre-reg

**Status of this paper v0.2**: the Path 2 family is **COUNTABLY INFINITE confirmed + 5 instances + 13/13 gates** with v1 ESTABLISHED PENDING (v1.5 completion pending). The Dirichlet L extension §4 trajectory completed (predictive scope = "structural fit only" close).

---

## §7 Consequences and open frontier

### 7.1 Path 2 ESTABLISHED-pending status (Schumann v1)

| Item | Status |
|---|---|
| Path 2 family cardinality | **COUNTABLY INFINITE** (modular L weight × level × newform enumeration) |
| Type α/β/γ trichotomy | **ESTABLISHED 2026-04-28** (Type γ formal definition (Definition 2.2) completed; 6th instance pre-reg + axis-2 strong split remain v1.5 tasks) |
| Axis-2 Fi/I invariance | **PREDICTED** (5+ instance hold, cross-side existence; strong split is v1.5) |
| Canonical scalar D1-D4 sub-claim | **5/5 hit** (one-way only; converse FALSE; Fi-origin vs. I-origin dichotomy made explicit) |
| Falsification gates F1-F4 | F1 NOT triggered / F2 outside scope / F3 mitigated / F4 BORDERLINE → Type γ |
| Lain-style Type γ "Wired layered self-reference" | realised by Atkin-Lehner W_N sub-subspace fix |

**Resolution of ζ singleton-class category error**: Path 2 is an abundant countable family; ζ is the minimum example of the smallest weight (k = 1) trivial character.

### 7.2 Dirichlet L predictive scope = "structural fit only"

| Layer | Status on Dirichlet L |
|---|---|
| **Path 2 instance class membership** | ✅ CONFIRMED (§3.3 weight k = 1 family member) |
| **σ_min = 1/2 identity** | ✅ CONFIRMED but **universal functional eq identity-level** (SC4); not framework-specific content |
| **Multi-gap structural invariance** | ✅ **CONFIRMED 12/12** (genuine extension fragment, §4.6) |
| **2-quantity coincide (Paper C content)** | ❌ REJECTED (G2 17.5%, §4.4) |
| **(log N)² curvature scaling (Paper C content)** | ❌ REJECTED (super-(log N)² growth, §4.5) |
| **ζ functional equation enforcement (N2 §6.1)** | ζ-specific (does not transfer in Dirichlet L extension) |

**"Structural fit only"** = Path 2 class membership + multi-gap universality hold, but Paper C-level 2-quantity uniqueness + (log N)² curvature are ζ-specific and do not transfer. Paper C uniqueness preserved more strongly (naive paths failed twice).

### 7.3 N4-N5 forward bridges

| Sequel | Topic | Forward from this paper | Status |
|---|---|---|---|
| **N4** | Hasse-Weil L × Stark structure | §3 lift modular L weight-k family to Hasse-Weil L (elliptic curve, abelian variety) (BSD connection). §4 attempt Hasse-Weil version of Dirichlet L "structural fit only" (whether SC4 universal identity propagates to Hasse-Weil L) | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — **K_E(t)·t² → r BSD analytic-rank detection (genuine framework predictive content) confirmed**. Contrasts with §4 "structural fit only" close of this paper; genuine transfer established at weight-2 Hasse-Weil L; **weight-class-dependent transfer pattern** made explicit as the main thesis (a weight-2 family member of §3 modular L of this paper provides the template) |
| **N5** | Brauer obstruction theory + Origination matrix (8-gauge) | §3 verify connection between Atkin-Lehner W_N Type γ instance and Tier 2 (D_4) of Brauer 5-tier. §5.3 classify Fi-origin vs. I-origin dichotomy by Origination matrix 8-gauge signatures | **v0.2 drafted 2026-04-27** — §3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection of this paper developed in N5 §5.2 as a structural unification instance (shared sub-object decomposition pattern). §5.3 Fi-origin vs. I-origin dichotomy of this paper = N5 §4.5 establishes 8-gauge classification: Fi-origin = axis-1 D side dominant {addZ, mult, char} / I-origin = axis-1 C side dominant {cont, geom, anal} |

**Base provided by N3 to N4**: the countably-infinite Path 2 family is the **structural template** for the Hasse-Weil L (Artin / Hecke / general motivic L) extension. The partition "Path 2 instance class membership = **necessary condition** for L-family universality, framework predictive content (Paper C-level) = **sufficient condition does not hold**" is established as a **weight-class-dependent** result in N4: weight-1 (Dirichlet L) structural fit only / weight-2 (Hasse-Weil L) genuine BSD transfer.

**N4 backward statistics**: §3 modular L weight-2 entry of this paper is directly cited in Paper N4 §3 as Hasse-Weil L = Path 2 weight-2 instance. §4 Dirichlet L "structural fit only" close of this paper functions strongly as a contrast anchor for the **weight-class-dependent transfer pattern** in Paper N4 §3.4 / §7.2. §5.3 Fi-origin vs. I-origin dichotomy of this paper is preserved for Paper N5 forward; in Paper N4 §6.2, Stark = Path 2 weight-1 abelian special case + Brauer 5-tier = Path 2 Stark sub-class failure taxonomy makes **the Path 2 framework of this paper function as the structural backbone of all of N4**.

### 7.4 Open frontier

| Open question | Status | Related paper |
|---|---|---|
| **Type γ formal definition** (sub-object fix) | **ESTABLISHED 2026-04-28** (Definition 2.2, 3-condition formal definition + Atkin-Lehner W_N canonical instance + theta characteristics 6th instance pre-reg, §2.2) | §2.2, §6.1 |
| **6th pre-registered instance** (F3 discipline) | OPEN (theta characteristics candidate) | §6.1 |
| **Axis-2 strong split test** (4+ Fi & 4+ I) | OPEN (v1.5 task) | §3.4, §6.2 |
| **I-origin canonical scalar mechanism formal classification** | OPEN (separated as distinct OQ) | §5.3 |
| **D_floor_L proper analog** (multi-parameter fit, v1b-v2) | OPEN | §4.5 |
| **Hecke-Artin L extension** (v2) | OPEN | N4 forward |
| **Hasse-Weil L extension** (v3) | OPEN | N4 forward |
| **RH-dependent verdict variation** (T-Ω5-4.4.1 conditional) | OPEN | `c_observation_optimal_gauge.md` |
| **OQ-Ω-Schumann-BackAction** | LOW deferred | Schumann origin remark |

### 7.5 Dictionary residence map

| Piece in this paper | Residence | Status |
|---|---|---|
| §2 Path 2 abstract class predicate (v0.5 form) | `oq_omega_schumann_v0.md` (primary), N1 §4.5.1 (forward mention) | candidate_v1 (13/13 gates) |
| §2.2 Type α/β/γ trichotomy | `oq_omega_schumann_v0.md` v1 NEW finding 2 | candidate_v1 |
| §3 5-instance catalogue + 13 gates | `oq_omega_schumann_v0.md` (primary), `c_theorems_master.md` row candidate | row candidate 2026-04-26 |
| §3.3 modular L countably-infinite | `nt_dedekind_artin_zeta.md` extension annex | annex candidate 2026-04-26 |
| §3.4 Axis-2 Fi/I invariance | `c_theorems_master.md` "S15 axis-2 projection map" annex extension candidate | annex candidate 2026-04-26 |
| §4 Dirichlet L extension trajectory | `c_theorems_master.md` T-Ω5e-v15-* rows (5 entries) + `c_observation_optimal_gauge.md §8.3` OQ-Ω5e | existing (2026-04-24/25 RESOLVED/REJECTED rows) |
| §4.6 multi-gap universality genuine fragment | `c_recursive_floor_principle.md §6.8` D_floor universality row extension candidate | expansion candidate 2026-04-26 |
| §5 Canonical scalar D1-D4 sub-claim | `c_arrow_bridge_constants.md §5-§6` (Fi-origin vs. I-origin annex) | annex candidate 2026-04-26 |
| §5.3 Fi-origin vs. I-origin dichotomy | `c_arrow_bridge_constants.md` (new §7 candidate) | new § candidate 2026-04-26 |
| §6 Falsification gates F1-F4 | `oq_omega_schumann_v0.md` v1 G13 (primary) | candidate_v1 |
| §7.4 Open frontier (v1.5 + Hecke-Artin + I-origin formal) | `meta/open_questions_master.md` new OQ candidates | issue candidate 2026-04-26 |

**N4-N5 forward residence**: §3 modular L countably-infinite + §4 Dirichlet L "structural fit only" + §5.3 Fi-origin vs. I-origin dichotomy form the base expanded by N4 (Hasse-Weil) and N5 (Brauer + Origination).

---

## Change log

- **v0.5 (2026-04-28)**: Type γ formal definition completed (v1.5 task (a) closed). §2.2 lifted from prose tentative definition to **Definition 2.2 (3-condition formal definition)**: (i) same-object proper sub-object fix / (ii) sub-object algebraic distinction / (iii) non-point + non-shadow. The Atkin-Lehner $W_N$ Petersson +1 eigenspace $M_k^+ \subsetneq M_k(\Gamma_0(N))$ is confirmed as the canonical instance; theta characteristics on Riemann surfaces (the fix locus $\Theta^+$ of even-characteristic involution) are pre-registered as the 6th instance under F3 discipline at the end of §2.2. §7.4 Open frontier table + §6.2 v1.5 status + §6.3 trichotomy row updated for consistency with Type γ formal ESTABLISHED. **Schumann v1.5 promotion progress**: (a) ✅ Type γ formal / (b) ⏳ 6th instance test (theta characteristics) / (c) ⏳ axis-2 strong split — (a) closed; (b) and (c) remain v1.5 pending.

- **v0.4 (2026-04-27)**: N5 backward link + NT 5-paper closure. N5 v0.2 drafted reflected in §7.3 N4-N5 forward bridge status column (§3 Atkin-Lehner Type γ ↔ Brauer Tier 2 structural unification + §5.3 Fi/I-origin = axis-1 D/C 8-gauge classification established). NT-series 5-paper closure achieved.
- **v0.3 (2026-04-26)**: N4 backward link added. N4 v0.2 drafted (2026-04-26) reflected in §7.3 N4-N5 forward bridge status column as "K_E·t²→r BSD analytic-rank detection genuine framework content confirmed; weight-class-dependent transfer pattern established". N4 backward statistics paragraph added at the end of §7.3 (§3 modular L weight-2 entry + §4 "structural fit only" close + §5.3 Fi/I-origin dichotomy of this paper function as the structural backbone of all of Paper N4). OQ updates: OQ-Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn-off OQ (BSD-HigherRank / 433a1-Outlier / 4VertexClosure) written back to `meta/open_questions_master.md`.
- **v0.2 (2026-04-26)**: compact version. Reduced redundancy from v0.1 (606 lines) — Abstract M1-M5 compressed; §1.1/§1.2/§1.3 (Path 2 motivation / N1 forward / honest scope) 3 subsections merged into 2 (1.1 + 1.2); §3.2 13 gates 3-phase tables consolidated into 1 table; §3.5 Type γ borderline merged with §2.2; redundant SC3/SC4 derivation chain formulae compressed in §4; post-execution root cause compressed in §4.4 / §4.5; §5.3 converse FALSE and §5.4 Fi-origin vs. I-origin dichotomy merged into §5.3; §6 3 subsections (gate / axis-2 / promotion) merged into 2 (6.2 has axis-2 + promotion); §7.5 residence map tabularised. Skeleton, claims, instance values, status, and gate results all preserved.
- **v0.1 (2026-04-26)**: initial NT-only draft. Centred on OQ-Ω-Schumann v1 (2026-04-25, 13/13 gates); OQ-Ω5e v1.5 series (2026-04-24/25) Dirichlet L extension developed under honest dual reporting; Dirichlet L predictive scope = "structural fit only" close.

---

## References (internal)

**Framework**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5)

**Schumann v1 (Path 2 main source)**: `research/oq_omega_schumann_v0.md` v1 (2026-04-25, 13/13 gates PASS) — countably-infinite Path 2 family + Type α/β/γ trichotomy + canonical scalar D1-D4 + falsification F1-F4

**OQ-Ω5e v1.5 series (Dirichlet L extension trajectory)**: `dirichlet_l_first_instance_v0` (real χ 5/5 CONFIRMED) / `dirichlet_l_complex_char_extension_v0` (complex χ 5/5 CONFIRMED with SC3) / `dirichlet_l_offaxis_2d_scan_v1` (INCONCLUSIVE with SC4) / `dirichlet_l_2quantity_coincide_v1a` (REJECTED) / `dirichlet_l_dfloor_multigap_v1b_v1` (REJECTED + G3 universality byproduct PASS)

**Experiment scripts**: `schumann_path2_check.py` / `schumann_path2_v05_theta.py` / `schumann_path2_v1_atkin_lehner.py` / `dirichlet_l_balance_v0.py` / `dirichlet_l_balance_complex_v0.py` / `dirichlet_l_balance_offaxis_v1.py` / `dirichlet_l_balance_2quantity_v1a.py` / `dirichlet_l_dfloor_multigap_v1b_v1.py`

**L1 / meta dependencies (via N1)**: `c_theorems_master.md` (T-Ω5e-v15-* rows) / `c_observation_optimal_gauge.md §8.3` / `c_arrow_bridge_constants.md §5-§6` / `nt_dedekind_artin_zeta.md` / `nt_root_numbers.md` / `nt_conductor.md §6.1`

**Sequel papers (drafting planned)**: N4 (Hasse-Weil L × Stark structure) / N5 (Brauer obstruction theory + Origination matrix)
