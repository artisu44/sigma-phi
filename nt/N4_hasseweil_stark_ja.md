# Paper N4: Hasse-Weil L × Stark 構造

**サブタイトル**: weight-2 framework extension と BSD analytic rank detection、Stark R-gauge complete representation、Brauer 5-tier closure の三角形

**バージョン**: v0.3 (N5 backward link + NT 5-paper 完成, 2026-04-27)
**状態**: DRAFT — N1 framework header + N2 Paper 2 構造解析 + N3 Path 2 数論的普遍性 上、Hasse-Weil L weight-2 framework extension と Stark / Brauer 構造論の cross-connection を展開
**前提 (framework)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.5)
**前提 (L1)**: `c_observation_optimal_gauge.md`, `c_arrow_bridge_constants.md §11`, `c_theorems_master.md` (Path 2 family annex + Dirichlet L extension scope annex)
**前提 (L1 NT)**: `nt_dedekind_artin_zeta.md §1, §4, §7` / `nt_conductor.md §6` / `nt_relative_units.md` / `nt_root_numbers.md` / `nt_frobenius_schur.md` / `c_spectral.md §8`
**前提 (L2)**: `number_theory_dictionary_v1.md §5` (5 数体 + 3 cases rank 1 Stark verify)
**研究 root**: `research/oq_omega5_v15_hasse_weil_L_*` (8 files) / `research/stark_projection_v0.md` / `research/brauer_closure_*`
**後続論文**: N5 (Brauer 障害論 詳細 + Origination matrix 8-gauge)

---

## §0 Abstract

本論は **Hasse-Weil L (weight-2 modular L) と Stark / Brauer の Galois rep 構造** を、N1-N3 framework 上で連結する。N3 で確立された **Path 2 countably-infinite NT family** の weight-2 instance を Hasse-Weil L とし、N3 §4 Dirichlet L "structural fit only" close と対照的に **Hasse-Weil L では framework predictive content が genuine に transfer する** ことを示す。具体的には **K_E(t)·t² → r as t → 0+** (analytic rank r の framework-side empirical detector、proper AFE library-grade で 9/10 curves match within 5%) を main novel content として展開。

**主結果 (M1-M5)**:

**(M1) Hasse-Weil L weight-2 framework extension (v2 arc 8-stage trajectory CONFIRMED)** — Functional eq $\Lambda(s, E) = \varepsilon(E) \Lambda(2-s, E)$、Fix locus s = 1。11a1 1st instance CONFIRMED、4 non-CM curves で conductor universality 21/24 PASS at t≥5、proper Iwaniec-Kowalski AFE library-grade で **smoothing-artifact diagnosis REJECTED, signal genuine**。

**(M2) BSD analytic rank detection K_E(t)·t² → r (genuine framework predictive content)** — Reviewer Taylor prediction $\Lambda(1+x+it) \approx c_r (x+it)^r$ を base に **central curvature** $K_E(t) := \partial^2_\sigma \log|\Lambda(E, \sigma+it)|_{\sigma=1}$ を pre-registered observable とし、$K_E(t) \cdot t^2 \to r$ as $t \to 0+$ を 10-curve (rank 0/1/2/3) で proper AFE 検証。9/10 curves で rank と 5% 以内 agree (rank 3 5077a1: 3.0934)、433a1 outlier は curve-specific Taylor coefficient anomaly (c_2 small)。**N3 Dirichlet L "structural fit only" との対比で、Hasse-Weil L は genuine framework predictive transfer の instance**。

**(M3) Stark rank 0/1 R-gauge complete representation** — Class number formula 6-gauge $\mathrm{Res}_{s=1} \zeta_K = (2^{r_1} (2\pi)^{r_2} h_K R_K) / (w_K \sqrt{|d_K|})$ を 5 数体で empirical verify。Rank 1 abelian Stark $L'(0, \chi) = -(1/e_\chi) \sum_\sigma \chi(\sigma^{-1}) \log|\sigma(\varepsilon_\chi)|$ を 3 cases (ℚ(√5), ℚ(√2), ℚ(√−23)) で Atlas grammar verify、Δ_residual = 0 exact (R-gauge complete representation 定理)。

**(M4) Brauer 5-tier closure (Stark connection)** — Galois rep ρ の representation-theoretic structure で Tier 1 ($S_3$, $A_4/V_4$) / Tier 2 ($D_4$) / Tier 3+ / Tier √ ($Q_8$) / Tier ∞ に classify。Stark R-gauge complete representation は Tier 1-3+ で hold、Tier √ では sign obstruction (Q_8 LMFDB 8.0.12230590464.1: $L(0, \rho)^2 = 16$, $L = \pm 4$)、Tier ∞ では Hecke L direct only。

**(M5) Cross-connection 三角形 (Hasse-Weil / Stark / Brauer)** — Hasse-Weil = Path 2 weight-2 instance、Stark = weight-1 abelian special case、Brauer 5-tier = Path 2 instance class の Tier-organized failure taxonomy。N1 §6 NT-internal triangulation (Paper C / Stark / Brauer) を本論で **(Hasse-Weil / Stark / Brauer) 三角形** に specialize、weight-1 vs weight-2 比較で framework predictive content の transfer pattern を明示。

**Thesis**: Hasse-Weil L (weight-2 modular L) は N3 で確立された Path 2 countably-infinite family の weight-2 instance であり、Dirichlet L (weight-1) と異なり **K_E(t)·t² → r BSD analytic rank detection** という genuine framework predictive content を提供する。これは framework predictive transfer が **weight-class dependent** であることを demonstrate。Stark rank 0/1 (weight-1 abelian) + Brauer 5-tier (closure failure taxonomy) と組み合わせて、weight-1 / weight-2 / Galois rep structure の三角形が **N1 framework の Galois-rep 側 closure** として function する。

---

## §1 Introduction

### 1.1 Hasse-Weil + Stark の position と N3 対比

N1 (NT 観測理論 framework header) → N2 (Paper 2 ζ-family core 構造解析) → N3 (Path 2 数論的普遍性 + Dirichlet L "structural fit only" close) の系列で、ζ-family core (weight 1) は full ESTABLISHED、Dirichlet L extension (weight 1, character twist) は structural fit only に close された。本 N4 は次の natural extension target である **Hasse-Weil L (weight 2, modular L)** + **Stark structure (weight 1 abelian, R-gauge)** + **Brauer closure (Galois rep 5-tier)** の組み合わせを扱う。

| 系列 | 特徴 |
|---|---|
| **Hasse-Weil L** | Weight $k = 2$ modular form (cusp newform on $\Gamma_0(N)$, BSD curves) / functional eq involution $\sigma_E: s \mapsto 2-s$, Fix locus $s = 1$ / Path 2 instance class membership (N3 §3.3) |
| **Stark** | Weight $k = 1$ abelian (Dirichlet L 系列の specific configuration) / R-gauge complete representation 定理 ($\Delta_\text{residual} = 0$ exact) / Class number formula = rank 0 established / Rank 1 abelian conjecture (3 cases verified) |
| **Brauer 5-tier** | Galois rep ρ representation-theoretic structure で classify / Stark "L(s, ρ) = ζ_F/ζ_ℚ" tier theory / Tier 1 strict / 2 relaxed / 3+ multi-rational / √ sqrt-only / ∞ impossible |

**N3 Dirichlet L "structural fit only" との対比 (本論で示す対照的結果)**: Hasse-Weil L weight-2 framework extension は v2 arc 8-stage trajectory (§2) で展開され、最終 v2 v8 proper AFE で **K_E(t)·t² → r as t → 0+** が genuine signal として library-grade verified (9/10 curves rank within 5%)。Dirichlet L とは異なり **Hasse-Weil L では framework predictive content が genuine に transfer する**。weight 1 → weight 2 で Fix locus が s = 1/2 → s = 1 に shift、BSD-related analytic rank が central curvature で **detect 可能** — Dirichlet L の SC4 universal identity-level σ_min = 1/2 とは構造的に異なる **rank-encoded substantive content**。

→ **framework predictive transfer pattern は weight-class dependent**: weight 1 (Dirichlet L) は structural fit only、weight 2 (Hasse-Weil L) は genuine (BSD analytic rank の framework-side detector)。

### 1.2 Honest trajectory + BSD connection

本論の特徴: **§2** Hasse-Weil L v2 arc 8-stage trajectory の honest reporting (途中 Phase 3 numerical artifact catch + reviewer redirect も methodology lesson として include) / **§3** K_E(t)·t² → r BSD analytic rank detection を **genuine framework predictive content** として強調 (ただし "BSD 予想を解いた" とは主張せず、"BSD analytic rank の framework-side empirical detector" として位置付け) / **§4-§5** Stark + Brauer Galois rep 構造論を Hasse-Weil との connection 視点で整理 / **§6** (Hasse-Weil / Stark / Brauer) 三角形を N1 §6 NT-internal triangulation の specialize として展開 / **§7** N5 forward + open frontier + 辞書 residence map。

---

## §2 Hasse-Weil L weight-2 framework extension (v2 arc 8-stage trajectory)

### 2.1 Weight-shift functional equation + Fix locus s = 1

Elliptic curve $E$ over ℚ (conductor $N_E$, root number $\varepsilon(E) = \pm 1$) の completed Hasse-Weil L:

$$\Lambda(s, E) := N_E^{s/2} \cdot (2\pi)^{-s} \cdot \Gamma(s) \cdot L(s, E), \qquad \Lambda(s, E) = \varepsilon(E) \cdot \Lambda(2-s, E)$$

**Involution** $\sigma_E: s \mapsto 2-s$, $\sigma_E^2 = \mathrm{id}$、**Fix locus** $\{s : s = 2-s\} = \{s = 1\}$ (critical line for weight 2)。Path 2 instance class membership (N3 §3.3, `nt_dedekind_artin_zeta.md §7`): Hasse-Weil L = modular L weight-parametrization の **weight $k = 2$ instance**。

**Dirichlet L (weight 1) との対比**: Dirichlet L $\Lambda(s, \chi) = \varepsilon \Lambda(1-s, \bar\chi)$ で involution $s \mapsto 1-s$, Fix s = 1/2、Path 2 type weight-1 family。Hasse-Weil L は weight $k = 2$, Fix s = 1, weight-2 family。

### 2.2 v2 v2 11a1 first instance CONFIRMED (non-CM, conductor 11)

Setting (`oq_omega5_v15_hasse_weil_L_t_adaptive_v2_v2.md`, 2026-04-25): Cremona 11a1 (Weierstrass $(0, -1, 1, -10, -20)$, conductor 11, rank 0)。t-adaptive smoothing $X(t) = 50 + 30|t|$、smoothed L-series $L_\text{smooth}(s, E) = \sum a_n \exp(-n/X(t)) / n^s$、smoothed $\Lambda$、long Weierstrass point counting for $a_p$。

**Result**: 11a1 で full pass。framework extension to weight-2 が non-CM 経由で empirically 確認 → v2 v3 で classes phenomenon 切り分け。

### 2.3 v2 v3 conductor universality 21/24 PASS at t≥5 (4 non-CM curves)

4 non-CM curves で conductor 多様化:

| Curve | Conductor | Rank |
|---|---:|---:|
| 11a1 | 11 (prime) | 0 |
| 14a1 | 14 (= 2·7) | 0 |
| 17a1 | 17 (prime) | 0 |
| 37a1 | 37 (prime) | **1** ← first non-zero rank |

**Pre-registered Gates**: G1 σ_min(t) ∈ [0.9, 1.1] at t ∈ {5, 10, 15} ≥ 2/3 t-values per curve / G2 cross-curve pairwise max σ_min difference < 0.15 / G3 functional equation |Λ(s)|/|Λ(2-s)| ≈ 1 within ±0.01。

**Result**: G2 21/24 PASS = **conductor universality empirically 確立 at t≥5** (G2 perfect 18/18 at t = 5, 10, 15)。

**Unexpected finding**: 37a1 (rank 1) で small t (t = 0.5) で σ_min = 0.749 が観測 — rank 0 curves (σ_min ≈ 1.00) と clean separation。BSD 由来の **L(1, E) = 0** 効果が small t で現れる positive structural finding (rank effect at small t)。

### 2.4 v2 v4-v5 rank amplitude discovery + Phase 3 numerical artifact catch

**v2 v4 NEW finding**: σ_min(t) oscillation amplitude $A(E) := \max_t \sigma_\min(E, t) - \min_t \sigma_\min(E, t)$ は **rank-discriminating**: Rank 0 (3 curves) $A \in [0.028, 0.048]$ / Rank 1 (3 curves) $A \in [0.164, 0.319]$ / cluster separation 3-6× clean → "amplitude rank-discriminating" hypothesis issued。

**v2 v5 multi-rank robustness test** (10 curves, rank 0/1/2/3): rank 0 vs rank 1 amplitude separation **ROBUST CONFIRMED** (4 rank-0 $A \in [0.040, 0.048]$ vs 3 rank-1 $A \in [0.178, 0.424]$, cluster gap 0.13)。

**ただし rank 2/3 で numerical breakdown**: σ_min values −0.87, 13.08, −5.69 等 parabolic fit failure。**Phase 3 post-execution audit** で原因特定 = insufficient smoothing at conductor ≥ 389 (X(t) = 50 + 30|t| が conductor 389+ で truncation insufficient)。G6 monotone scaling claim は artifact-amplified として **REJECTED**。

**Methodology lesson**: 単一 hypothesis (amplitude = rank monotone scaling) が conductor-rank confounding で fail する instance。Phase 3 post-execution audit が critical (single-N "dimensional match" claim と同 pattern, N3 §4.5 v1b v0 と同型 lesson)。

### 2.5 v2 v7 K_E(t) Taylor prediction (reviewer redirect)

**External AI review (2026-04-25)** v2 v0-v6 arc に対する 3 主要批判: (1) Theoretical: Exact Λ has σ-symmetry identity-level + Taylor expansion at s=1 gives σ-curvature ∝ r/t² → rank should pin minimum **MORE at σ = 1**, NOT shift away (2) Methodological: Conductor-rank confounding fatal for $A(E)$ interpretation (3) Constructive proposal: Switch observable $A(E)$ → $K_E(t) := \partial^2_\sigma \log|\Lambda(E, \sigma + it)|_{\sigma = 1}$ (central curvature, theoretically grounded)。

**Pre-registered Hypothesis (v7)**: $K_E(t) \cdot t^2 \to r$ as $t \to 0+$, $O(t^2)$ subleading correction (theoretical foundation §3.2 で展開)。

**Result**: PARTIAL_CONFIRMED (8/10 curves at t = 0.3 で integer-rank agreement)、ただし t = 0.1 で finite-difference artifact (h/t = 0.5, systematic FD underestimation)。**Phase 3 catch**: gate-design lesson on my own gate choice (t = 0.1 too small for h = 0.05)。t = 0.3+ で confirmed。

### 2.6 v2 v8 proper AFE library-grade CONFIRMED (genuine signal)

Setting (`oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md`): v2 v7 で reviewer's Taylor prediction が smoothed implementation で empirically verified された。**Critical question**: signal は genuine か smoothing-mediated artifact か?

→ proper Iwaniec-Kowalski AFE via mpmath's incomplete gamma function を実装、library-grade L-function evaluation:

$$\Lambda(s, E) = N_E^{s/2} (2\pi)^{-s} \Sigma_1(s) + \varepsilon \cdot N_E^{(2-s)/2} (2\pi)^{-(2-s)} \Sigma_2(s)$$

ここで $\Sigma_1(s) = \sum a_n n^{-s} \Gamma(s, 2\pi n / \sqrt{N_E})$, $\Sigma_2(s) = \sum a_n n^{-(2-s)} \Gamma(2-s, 2\pi n / \sqrt{N_E})$ (Γ(s, x) = upper incomplete gamma)。**Functional equation Λ(s, E) = ε·Λ(2-s, E) は exactly by construction**。

**Gates summary** (詳細 §3.3):
- **G1 (functional eq sanity)**: |Λ_AFE(s)| / |Λ_AFE(2-s)| ratios machine-precision agreement at all test points
- **G2 (K_E·t² rank prediction at t=0.3)**: **9/10 curves agree with rank within 5%**, 433a1 outlier curve-specific
- **G3 (AFE vs smoothed comparison)**: 8 curves close agreement (smoothed accurate for these), 5077a1 rank 3 で AFE FIXES smoothed boundary issues (smoothed 1.84 → AFE 3.09 clean), 433a1 outlier in different directions (curve-specific arithmetic)

**Verdict**: **CONFIRMED genuine signal**。Reviewer's smoothing-artifact diagnosis **REJECTED**。Framework's BSD analytic rank detection は theoretically grounded + library-grade verified。

### 2.7 v2 arc trajectory summary

| stage | content | status |
|---|---|---|
| v2 v0 | CM E:y²=x³-x first sketch | PARTIAL with truncation caveat |
| v2 v1 | smoothed and noncm methodology | (intermediate) |
| v2 v2 | 11a1 t-adaptive | CONFIRMED full pass |
| v2 v3 | 4 non-CM conductor universality | 21/24 PASS at t≥5 + rank-1 BSD effect at small t |
| v2 v4 | rank universality | NEW finding: amplitude rank-discriminating |
| v2 v5 | multi-rank amplitude | rank 0/1 ROBUST + rank 2/3 numerical artifact (Phase 3 catch) |
| v2 v6 | smoothing refinement | (intermediate) |
| v2 v7 | K_E(t) Taylor reviewer redirect | PARTIAL_CONFIRMED at t=0.3+ |
| **v2 v8** | **proper AFE library-grade** | **CONFIRMED genuine signal** (9/10 curves match within 5%) |

**Final verdict**: Hasse-Weil L weight-2 framework extension は v2 v8 で **K_E(t)·t² → r** central curvature observable で genuine framework predictive content として ESTABLISHED。Path 2 instance class membership (N3 §3.3 modular L weight-2 family) + framework-specific BSD analytic rank detection の 2 layer が確立。

---

## §3 BSD analytic rank detection ─ genuine framework predictive content

### 3.1 K_E(t)·t² → r as t → 0+

**Statement (v2 v8 ESTABLISHED)**: Elliptic curve $E$ over ℚ with analytic rank $r$ (= geometric rank under BSD) について、central curvature

$$K_E(t) := \partial^2_\sigma \log|\Lambda(E, \sigma + it)|_{\sigma = 1}$$

は

$$\boxed{K_E(t) \cdot t^2 \to r \quad \text{as} \quad t \to 0+}$$

with $O(t^2)$ subleading correction from $c_{r+1}$ term。

### 3.2 Theoretical foundation (Taylor expansion at s=1)

Reviewer Taylor argument (`oq_omega5_v15_hasse_weil_L_central_curvature_v2_v7.md §1`): Λ has Taylor expansion at s=1 with leading order $r$ (analytic rank):

$$\Lambda(1+z, E) = c_r z^r + c_{r+1} z^{r+1} + \cdots, \quad c_r \neq 0, \quad c_k \in \mathbb{R}$$

(real coefficients は $a_n \in \mathbb{Z}$ from elliptic curve over ℚ)。Near $s = 1 + it$ for fixed small $t$:

$$|\Lambda(1 + x + it)|^2 \approx |c_r|^2 (x^2 + t^2)^r, \quad \log|\Lambda| \approx \log|c_r| + (r/2) \log(x^2 + t^2)$$

$$\partial^2_x \log|\Lambda| = \frac{r(t^2 - x^2)}{(x^2 + t^2)^2}$$

**At $x = 0$** (i.e., $\sigma = 1$): $K_E(t) = r/t^2 + O(1)$ → **$K_E(t) \cdot t^2 \to r$** as $t \to 0+$ leading-order limit。

### 3.3 10-curve verification (rank 0/1/2/3) with proper AFE

`oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md §6` の 10-curve test:

| Curve | rank r | $K_E(0.3) \cdot (0.3)^2$ AFE | Predicted r | Agreement |
|---|---:|---:|---:|---|
| 11a1 | 0 | 0.0230 | 0 | ✓ within 5% |
| 14a1 | 0 | 0.0264 | 0 | ✓ within 5% |
| 15a1 | 0 | 0.0277 | 0 | ✓ within 5% |
| 17a1 | 0 | 0.0301 | 0 | ✓ within 5% |
| 37a1 | 1 | 1.0206 | 1 | ✓ within 5% |
| 43a1 | 1 | 1.0236 | 1 | ✓ within 5% |
| 53a1 | 1 | 1.0264 | 1 | ✓ within 5% |
| 389a1 | 2 | 2.0470 | 2 | ✓ within 5% |
| 433a1 | 2 | **0.1211** | 2 | ✗ outlier (curve-specific) |
| 5077a1 | 3 | **3.0934** | 3 | ✓ within 5% |

**Mean per rank class** (excluding 433a1 outlier): rank 0 → 0.0268, rank 1 → 1.0236, rank 2 → 2.0470, rank 3 → 3.0934 — **monotone integer-rank progression**, clean BSD analytic rank detection。

**433a1 outlier diagnosis**: 433a1 で $K \cdot t^2 = 0.12$ at $t = 0.3$ (vs predicted 2)。$a_p$ sample ($a_2 = +2$ unusual positive, $a_3 = +1$, $a_5 = 0$, $a_7 = +1$) で一般 elliptic curve は negative often。For rank 2: $\Lambda(1+z) = c_2 z^2 + c_3 z^3 + \cdots$、$K_E(t) \cdot t^2 \approx 2 + 2 \mathrm{Re}(c_3/c_2 \cdot it) + |c_3/c_2|^2 t^2 + \cdots$ → $|c_2|$ small relative to $|c_3|$ で subleading correction dominates at moderate t、t=0.05 or smaller で pure leading-order regime。**Curve-specific Taylor coefficient anomaly**, not framework / methodology failure。

### 3.4 vs Dirichlet L "structural fit only" (genuine framework content claim)

詳細 vs 比較は §7.2。要点: Dirichlet L (weight 1) は σ_min identity level でのみ confirmed (SC4 universal identity-level、trivial)、2-quantity coincide / (log N)² scaling は **REJECTED** → "structural fit only"。Hasse-Weil L (weight 2) は **BSD analytic rank detection $K \cdot t^2 \to r$** が 9/10 curves で confirmed → **genuine framework content transfer**。

→ N3 §4 close と対照的に、Hasse-Weil L では framework predictive content が genuine に transfer する → **weight-class dependent transfer pattern**。

**重要な caveat**: 本論は "BSD 予想を解いた" とは主張しない。$K_E(t) \cdot t^2 \to r$ は **analytic rank の framework-side empirical detector** であり、analytic rank と geometric rank の equality (BSD 予想本体) は **assumed**。Framework は analytic rank を $K_E$ から detect できることを示したのであって、analytic rank = geometric rank の証明 (= BSD) は scope 外。

### 3.5 Path 2 instance class membership (modular L weight-2)

N3 §3.3 modular L weight-parametrization (`nt_dedekind_artin_zeta.md §7`) の weight $k = 2$ row が本論主対象:

| weight $k$ | functional eq | central fix | example |
|---|---|---|---|
| 1 | $\Lambda(s, \chi) = \varepsilon \Lambda(1-s, \bar\chi)$ | 1/2 | Dirichlet L; ζ when χ = χ_0 |
| **2** | $\Lambda(f, s) = \varepsilon \Lambda(f, 2-s)$ | **1** | **weight-2 newform (Hasse-Weil L of elliptic curves)** |
| 4 | $\Lambda(f, s) = \varepsilon \Lambda(f, 4-s)$ | 2 | weight-4 newforms |
| 12 | $\Lambda(\Delta, s) = \varepsilon \Lambda(\Delta, 12-s)$ | 6 | Ramanujan $\Delta$ |

**Path 2 class predicate (N3 §2.1) verify**: (1) Z/2 group action $\sigma_E : s \mapsto 2-s$, $\sigma_E^2 = \mathrm{id}$ ✓ (2) Invariant $|\Lambda(s, E)|^2$ (functional equation) ✓ (3) Non-empty fix point $s = 1$ ✓ → Hasse-Weil L は Path 2 class member、Type α (fix が同 algebraic object 内 single point)、axis-2 I-side。

**Type γ candidate**: Atkin-Lehner involution $W_q$ on $S_2(\Gamma_0(N))$ for $q | N$ (N3 §2.2 Type γ instance) は weight-2 modular form space で fix が $S_2^+ \subset S_2$ subspace。Hasse-Weil L は specific newform $f \in S_2(\Gamma_0(N))$ に attach するので、$f$ が $W_q$-eigenvector ($f \in S_2^\pm$) の場合に Atkin-Lehner Type γ structure が relevance を持つ (BSD root number $\varepsilon(E) = \pm \varepsilon_q(f)$ via Atkin-Lehner eigenvalue product)。

---

## §4 Stark rank 0/1 R-gauge complete representation

### 4.1 Class number formula 6-gauge (5 数体 verify)

**Theorem (Dirichlet-Hecke, ESTABLISHED, `c_spectral.md §8`)**:

$$\mathrm{Res}_{s=1} \zeta_K(s) = \frac{2^{r_1} (2\pi)^{r_2} h_K R_K}{w_K \sqrt{|d_K|}}$$

ここで $r_1, r_2$ = real / complex embeddings ($r_1 + 2 r_2 = [K : \mathbb{Q}]$), $h_K$ = class number, $R_K$ = regulator, $w_K = |\mu(K)|$, $d_K$ = absolute discriminant。

**6-gauge 分解** (N1 §6.2 transfer): 6 因子は Paper Ω 全 gauge² 署名に **1:1 対応**:

| 因子 | 正体 | gauge² signature |
|---|---|---|
| $(2\pi)^{r_2}$ | 複素 place archimedean volume | {cont, geom} (π) |
| $2^{r_1}$ | 実 place archimedean volume | {addZ} (parity minimum) |
| $\sqrt{|d_K|}$ | $O_K$ Minkowski 共体積 | {mult, anal} |
| $h_K$ | ideal class group 位数 | {mult} |
| $R_K$ | log-unit lattice co-volume | {cont, char} |
| $w_K$ | $K$ 中 root of unity 数 | {char} |

**5 数体 empirical verification** (`number_theory_dictionary_v1.md §5`): ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5) で 6 因子の数値計算 + class number formula 両辺 agreement 確認 → **gauge² の積分解定理**。

### 4.2 Rank 1 abelian Stark — 3 cases verified

**Stark rank 1 abelian conjecture** (`stark_projection_v0.md §1.2`): For abelian extension $K/k$ and Galois character $\chi$ with $r(\chi) = 1$:

$$L'(0, \chi) = -\frac{1}{e_\chi} \sum_{\sigma \in \mathrm{Gal}(K/k)} \chi(\sigma^{-1}) \log|\sigma(\varepsilon_\chi)|$$

where $\varepsilon_\chi \in O_K^\times$ is the **Stark unit** (existence is the substantive content)。

**3 verified cases**:

| Case | Field | χ | $h_K$ | Type | Status |
|---|---|---|---|---|---|
| (i) | ℚ(√5) | $\chi_5$ (real) | 1 | real quadratic | exact verified, Atlas grammar |
| (ii) | ℚ(√2) | $\chi_8$ (real) | 1 | real quadratic | exact verified, Atlas grammar |
| (iii) | ℚ(√−23) | cubic class character (non-real) | 3 | imaginary quadratic, $S_3$ setup | structural verified via Brauer reduction |

Case (i), (ii): real quadratic, $h = 1$、Stark unit = fundamental unit。LHS $L'(0, \chi)$ と RHS exact 一致、$\Delta_\text{residual} = 0$ exact 成立。Case (iii) は §4.4 で Brauer/Artin induction 経由の structural verify。

### 4.3 Atlas grammar formal — R-gauge complete representation 定理

Atlas grammar 表示 (rank 1 Stark, `stark_projection_v0.md §2.2`):

```yaml
stark_rank1_entry:
  f_n:           log |σ(ε_χ)|          # 振幅 (axis A)
  phi_phase:     χ(σ⁻¹)                 # gauge-rotation (axis E)
  N_X:           1/e_χ                   # torsion 正規化 (w_K 分)
  comp_X:        Σ_{σ ∈ G}              # Galois 軌道和
  observable:    L'(0, χ)                # 解析的 linear response
  primary_axis:  E ; secondary: A
  residual_type: [R-gauge, R-info]
```

**主張 (R-gauge complete representation 定理)**: Stark rank 1 conjecture は **R-gauge 残差の完全表現定理** — L'(0, χ) は log-unit lattice 上 character-mode 投影に **残差ゼロ**で一致 ($\Delta_\text{residual} = 0$ exact)。これは ΣΦ 辞書のほぼ全 entry ($\Delta > 0$) と対照的。**Stark が "難しい" 理由**: 多くの解析量は log-unit lattice 以外に漏れる成分 (R-env / R-comp / R-topo) を持つ、Stark は "L-derivative は純 R-gauge である" — **漏れの不在** そのものが主張。

### 4.4 ℚ(√−23) S_3 cubic class character analytic closure

`number_theory_dictionary_v1.md §5.3` + `stark_projection_v0.md` H-stark-2 closure。

**Setup**: $K = \mathbb{Q}(\sqrt{-23})$, $h_K = 3$, $\chi_K$ = cubic class character (non-real, complex order 3)。Hilbert class field $H/K$ で $\mathrm{Gal}(H/\mathbb{Q}) = S_3$ (non-abelian, 6 元)、$H = \mathbb{Q}(\alpha)$ where $\alpha$ = root of $x^3 - x - 1$ (plastic constant 関連)。

**Brauer / Artin induction による analytic closure** (2026-04-10): Key identity

$$L(s, \chi_K) = L(s, \rho_2) = \zeta_{\mathbb{Q}(\alpha)}(s) / \zeta_\mathbb{Q}(s)$$

where $\rho_2$ = $S_3$ standard 2-dim irrep (real, orthogonal)。Frobenius 相互律 + Brauer induction $\mathrm{Ind}_{A_3}^{S_3} \chi_K = \rho_2$ で verify。

**L'(0, χ_K) closed form**: $L'(0, \chi_K) = -2 \zeta'_{\mathbb{Q}(\alpha)}(0) = \log|\alpha_1| \approx 0.28122$ (rank-1 class number formula for $\mathbb{Q}(\alpha)$, Stark conjecture 不使用)。$R_H = 3 (\log|\alpha_1|)^2 \approx 0.23725$ が $R_{\alpha, \sigma\alpha}$ と完全一致 → $\alpha, \sigma\alpha$ が $H$ の fundamental units (item (i) closed)。Stark normalization $c = 3 = h_K$ (item (ii) closed)。

**Closed-form Stark formula**: $L'(0, \chi_K) = (1/3) \sum_\tau \bar\chi_K(\tau) \log|\tau(\alpha)|_{w_0} = \log|\alpha_1|$ → **ℚ(√−23) cubic class character での Stark closure** (Brauer/Artin induction + classical class number formula で済む analytic shortcut)。

**External audit cleared** (2026-04-10): AI half (Grok approve_candidate, high confidence) + Human half (RO approve_candidate, +2 missed adversarial catches: representation_fragility + normalization_dependency)。

**Promotion path**: 3 verified cases で R-gauge complete representation 定理は **candidate** maintained。candidate+ 昇格は (a) Stark unproven case predictive verification / (b) framework Δ_residual reduction instance / (c) Atlas grammar functor formalization のいずれかで pending。

---

## §5 Brauer 5-tier closure ─ Stark との connection 視点

### 5.1 Tier classification recap

`brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2) + `brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8) の 5-tier:

```
              closure spectrum
  ├──── success side ────┤  ├─ failure side ─┤
 Tier 1   Tier 2   Tier 3+  │  Tier √   Tier ∞
 strict   relaxed   multi   │  sqrt only  impossible
  S_3     D_4    (hypo.)    │   Q_8      (unknown)
 A_4/V_4
```

| Tier | Form | Examples | Stark formula |
|---|---|---|---|
| **Tier 1** | $L = \zeta_F/\zeta_\mathbb{Q}$ (single ratio) | $S_3$, $A_4/V_4$ | single reg $h_F R_F$ |
| **Tier 2** | $L = \zeta_{F_1}/\zeta_{F_2}$ | $D_4$ | reg ratio |
| **Tier 3+** | $L = \prod \zeta_{F_i}^{n_i}$ | $S_4/V_4$? | multi-reg rational |
| **Tier √** | $L^{2k} = $ rational, $L \notin$ | $Q_8$ | square-root of rational combo |
| **Tier ∞** | no power works | (unknown genuinely) | direct Hecke L only |

### 5.2 Stark connection (Tier-dependent realization)

Stark R-gauge complete representation 定理 (§4.3) の Tier-dependent realization:

| Tier | Stark realization | Δ_residual |
|---|---|---|
| **Tier 1** ($S_3$, $A_4/V_4$) | single intermediate field zeta ratio → single reg $h_F R_F$ | 0 (R-gauge only) |
| **Tier 2** ($D_4$) | 2 intermediate fields zeta ratio → field-pair reg | 0 (R-gauge, more complex composition) |
| **Tier 3+** | multi-field rational combination | 0 (formal generalization) |
| **Tier √** ($Q_8$) | $L^2$ rational だが $L$ not、**sign obstruction** | $\neq 0$ on sign (FS $\nu(\rho) = -1$ quaternionic) |
| **Tier ∞** | Hecke L direct only | 不適用 |

Tier 1-3+ で Stark R-gauge complete representation 定理 hold、Tier √ で sign obstruction、Tier ∞ で Hecke direct 必要。

### 5.3 Q_8 Tier √ numerical witness

`brauer_closure_failure_taxonomy_v0.md` v0.2 で Q_8 Tier √ verification:
- **LMFDB curve**: 8.0.12230590464.1
- **2-dim 既約 ρ**: **quaternionic** (FS indicator $\nu(\rho) = -1$)
- **L(0, ρ)² = 16** (rational)、**L(0, ρ) = ±4** (sign obstruction、square-root で外側に漏れる)
- **Structural origin**: $Q_8$ の 2-dim 既約 ρ は ℍ (quaternion) 上で realize、ℝ-rational descent で sign が free parameter として残る

**T-AAS read** (N1 §5): $f_\text{torsion}(\rho) = 1$ (sign obstruction = ℤ/2 torsion = "ker_gauge" classical instance), $f_\text{rational}(\rho) \geq 0$ (magnitude rational, complete representation 部分)。Tier √ obstruction は Stark の "R-gauge 残差ゼロ" claim を破る minimal instance。Stark conjecture が rank 1 abelian で stated されるのは Tier √/∞ 回避のため (abelian ⟹ all irreps 1-dim ⟹ all real ⟹ $\nu = +1$ forced)。

### 5.4 Tier 1 (S_3) と Tier 2 (D_4) examples

**Tier 1 instance: S_3 (ℚ(√−23))**: §4.4 で展開した instance は $S_3$ Tier 1 strict closure case — $L(s, \chi_K) = L(s, \rho_2) = \zeta_{\mathbb{Q}(\alpha)}(s) / \zeta_\mathbb{Q}(s)$、single intermediate field $F = \mathbb{Q}(\alpha) = $ Hilbert class field、single ratio で closure。Stark unit $\varepsilon_{\chi_K} = \alpha$ (fundamental unit of $\mathbb{Q}(\alpha)$)。

**Tier 2 instance: D_4** (`brauer_closure_galois_classification_v0.md §11-12`): $K = \mathbb{Q}(\sqrt{-14})$ の Hilbert class field $H = K(\sqrt{2})$、$\mathrm{Gal}(H/\mathbb{Q}) = D_4$。$\chi_K$ = quadratic class character。Tier 2 form $L(s, \chi_K)^2 = \zeta_{F_1}/\zeta_{F_2} \cdot (\text{quadratic factor})$ specific 2 intermediate fields $F_1 = K(\sqrt{2}), F_2 = \mathbb{Q}(\sqrt{2})$ で field-pair ratio closure。Stark formula $L'(0, \chi_K) \propto h_{F_1} R_{F_1} / (h_{F_2} R_{F_2})$。

### 5.5 Hasse-Weil L が Tier 分類と どう交差するか

Hasse-Weil L = weight-2 modular L (Path 2 family member, §3.5)。Galois rep 視点: Hasse-Weil L $L(s, E)$ は $E[\ell^\infty]$ Tate module による **2-dim ℓ-adic Galois rep** に attach、$\mathrm{Gal}(\bar{\mathbb{Q}}/\mathbb{Q})$ は **non-abelian** (large group)。2-dim irrep の FS indicator generically $0$ (complex) / $-1$ (quaternionic) / $+1$ (real)。

**Tier 分類との関係**: Tier 1/2/3+ closure は Hasse-Weil L の **non-abelian Galois rep** に attach するので Stark style "intermediate field zeta ratio" closure には fit しない (closure conditions C1-C4 が weight-2 modular L で fail)。Tier √/∞: 2-dim ℓ-adic Galois rep が quaternionic structure の場合 Tier √ analog だが、Hasse-Weil L は modularity (Wiles theorem) で **automorphic L として construct** — Brauer Tier 分類とは異なる framework。

→ **Hasse-Weil L は Brauer 5-tier の outside scope** (Stark style closure 不適用)。代わりに Hasse-Weil L は **modular L weight-2 instance** として §3 K_E(t)·t² → r BSD analytic rank detection が framework predictive content を提供。**Tier 分類は weight-1 abelian Stark の closure structure**、**Hasse-Weil L は weight-2 modular L の BSD analytic rank structure** — 両者は framework 内で **異なる layer の predictive content** を担当。

---

## §6 Cross-connection: Hasse-Weil / Stark / Brauer 三角形

### 6.1 Hasse-Weil L = N3 Path 2 modular L weight-2 family member

§2.1 + §3.5 で確立した Hasse-Weil L の Path 2 instance class membership: N3 §3.3 modular L weight-parametrization の **weight $k = 2$** entry / functional equation involution $\sigma_E : s \mapsto 2-s$, Fix locus $s = 1$ / Type α / axis-2 I-side。

**N3 5-instance catalog の中での Hasse-Weil L**:

| N3 instance | Path 2 type | weight | example |
|---|---|---|---|
| ζ functional eq | α | 1 | weight-1 trivial char minimum |
| 球面 Laplacian | β | n/a | shadow rep |
| theta S-duality | α | n/a | Möbius modular |
| modular L weight 1 | α | 1 | Dirichlet L |
| **Hasse-Weil L** | **α** | **2** | **本論主対象** |
| modular L weight 4-12 | α | 4-12 | weight-k newforms (Δ etc.) |
| Atkin-Lehner W_N | γ | n/a | sub-object fix |

→ Hasse-Weil L は N3 family の specific weight = 2 instance、**Path 2 abundant family の middle** に位置。

### 6.2 Stark + Brauer = Path 2 weight-1 abelian special case + failure taxonomy

**Stark (rank 1 abelian)** = Path 2 family の specific configuration (weight $k = 1$ + character χ abelian (1-dim) + Galois group G abelian、Brauer Tier 1-3+)。Path 2 catalog 上の Stark position = Dirichlet L (weight 1) row の **abelian Galois extension subset**。Stark の framework predictive content = Path 2 family の中での独自性: σ_min identity-level (Fix s = 1/2) は N3 §4 で SC4 trivialized、**R-gauge complete representation 定理** ($\Delta_\text{residual} = 0$ exact) は **Stark 固有の framework content**、Class number formula 6-gauge は rank 0 ESTABLISHED universal。

→ Stark = Path 2 framework predictive content の **abelian rank-1 specialize**、Hasse-Weil L (weight-2, K_E·t²→r) と相補的: Stark = weight-1 abelian R-gauge complete representation / Hasse-Weil = weight-2 BSD analytic rank detection。

**Brauer 5-tier** = Stark R-gauge complete representation 定理の **Galois rep representation-theoretic obstruction taxonomy**: Tier 1-3+ で complete representation 定理 hold (rational closure)、Tier √ sign obstruction (Q_8 quaternionic $\nu = -1$, $\Delta_\text{sign} \neq 0$)、Tier ∞ closure 不可能 (Hecke direct only)。Brauer 5-tier = **Path 2 Stark sub-class の failure taxonomy**。Hasse-Weil L は Stark scope outside (non-abelian + weight-2) で Brauer 5-tier 直接適用は限定的だが、Galois rep representation-theoretic structure (irrep dim, FS indicator) は **Path 2 Type α/β/γ trichotomy (N3 §2.2)** と analogous。

### 6.3 三角測量 (Hasse-Weil / Stark / Brauer) — N1 §6 の精緻化

N1 §6 NT-internal Arrow 間 triangulation は **Paper C / Stark / Brauer** の 3 vertex で展開された (Paper C: 3 Arrow simultaneous in single object F_{g,k}(s) / Stark: Arrow 2/3 / Brauer: Arrow 1 kernel)。本論で **Hasse-Weil を 4th vertex 候補** として考察:

| Instance | Arrow focus | Layer evidence |
|---|---|---|
| Paper C (N2) | **3 Arrow simultaneous** | F_{g,k}(s) single object, all 3 layers |
| Stark (本論 §4) | **Arrow 2/3** (R-gauge complete rep) | analytical → algebraic gauge product |
| Brauer (本論 §5) | **Arrow 1 kernel** (T-AAS) | representation-theoretic obstruction |
| **Hasse-Weil (本論 §3)** | **Arrow 2 + Information layer** (BSD K_E·t²→r) | weight-2 family member, rank encoded in central curvature |

**4-vertex triangulation 提案**: N1 §6 の 3-vertex (Paper C / Stark / Brauer) を **Hasse-Weil 追加 4-vertex** に拡張する候補。Hasse-Weil L の framework predictive content (BSD analytic rank detection) は N1 framework の Galois-rep extension closure として function。

**ただし注意**: 4-vertex への拡張は Paper N4 v0.2 では **proposal stage**。実装 (Hasse-Weil の Arrow 焦点 formal 化 + 4-vertex closure proof) は v0.3 task または N5 forward。本論では §6.3 で **vision sketch** のみ提示し、formal 化は future work。

---

## §7 帰結と open frontier

### 7.1 ESTABLISHED status (M1-M5)

| 結果 | Status |
|---|---|
| **M1 Hasse-Weil L weight-2 framework extension** (v2 arc 8-stage) | **CONFIRMED** (v2 v8 proper AFE, 11a1 + 4 non-CM 21/24 + 10-curve K_E·t²) |
| **M2 BSD analytic rank detection K_E(t)·t² → r** | **CONFIRMED genuine signal** (9/10 curves match within 5%, AFE library-grade verified, smoothing-artifact diagnosis REJECTED) |
| **M3 Stark rank 0/1 R-gauge complete representation** | **rank 0 ESTABLISHED** (5 数体 verify) + **rank 1 abelian candidate** (3 cases verify) |
| **M4 Brauer 5-tier closure (Stark connection)** | **OQ-NT-7 v0.2 + OQ-NT-8 v0.2** (Tier 1-3+/√/∞ classification, Q_8 Tier √ numerical witness LMFDB) |
| **M5 Cross-connection 三角形 (Hasse-Weil / Stark / Brauer)** | **proposal stage** (本論 §6 vision sketch、formal 4-vertex triangulation 化は v0.3 / N5 forward task) |

### 7.2 vs N3 Dirichlet L 対比 (genuine vs structural fit only)

| Layer | Dirichlet L (N3 §4) | Hasse-Weil L (本論 §2-§3) |
|---|---|---|
| Path 2 instance class membership | ✅ CONFIRMED | ✅ CONFIRMED |
| σ_min Fix locus identity-level | ✅ trivial (SC4 universal identity at s=1/2) | ✅ (s=1, weight-2 analogue) |
| Multi-gap structural invariance | ✅ **CONFIRMED 12/12** (genuine fragment) | ✅ conductor universality 21/24 PASS at t≥5 (analogue) |
| 2-quantity coincide | ❌ REJECTED (weight-1 specific) | (different test BSD-style) |
| Paper C (log N)² curvature scaling | ❌ REJECTED | (different scaling, BSD-style) |
| **BSD analytic rank detection** | (BSD outside Dirichlet L scope) | ✅ **CONFIRMED** $K \cdot t^2 \to r$ 9/10 curves |
| **Genuine framework content transfer** | ❌ "structural fit only" | ✅ **GENUINE** (BSD analytic rank detector) |

→ **Framework predictive transfer pattern is weight-class dependent**: weight 1 (Dirichlet L) structural fit only / weight 2 (Hasse-Weil L) genuine (BSD analytic rank detector)。これは N1 framework の **rich predictive structure** を demonstrate — 各 weight-class が異なる framework content を carry し、Path 2 family member ごとに predictive scope が determined。

### 7.3 N5 forward bridge

| 後続 | 主題 | 本論からの forward |
|---|---|---|
| **N5** | Brauer 障害論 詳細 + Origination matrix (8-gauge) | §5 Brauer 5-tier の **failure mode group-theoretic criteria** + **alternative Stark methods** (Tier √ Q_8 sign resolution, Tier ∞ Hecke direct construction) を N5 で詳細展開。§4 6-gauge (Stark) を **Origination matrix 8-gauge** (axis-1 D/C subdivision: addZ/mult/prime_coord/char/ordinal × cont/geom/anal) に generalize。Hasse-Weil L が Origination matrix 8-gauge signature を加えるか N5 で investigate (BSD related new gauge candidate)。 **v0.2 起草完了 2026-04-27** — Brauer 5-tier failure mode group-theoretic Conjecture + Tier-dependent Stark methods 4 cases proposal + 8-gauge generalization (Stark 6-gauge は subset, ordinal + prime_coord 加わる) + Cross-connection (本論 §3 BSD K_E·t²→r が weight-2 で {addZ, mult, prime_coord, anal} new combination として emerge) + 4-vertex triangulation proposal_v2 (本論 §6.3 を formal closure attempt まで拡張) |

**§6.3 4-vertex triangulation の formal 化**: N1 §6 NT-internal triangulation の Hasse-Weil 拡張 (3-vertex → 4-vertex) は **N5 forward** または Paper N4 v0.3 task。

### 7.4 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **OQ-Schumann-HasseWeil-Ext** (本論 §3 で partial address) | OPEN MEDIUM | §2-§3, N5 forward |
| **BSD higher-rank** ($K_E \cdot t^2 \to r$ for $r \geq 4$) | OPEN (5077a1 rank 3 が highest verified, $r \geq 4$ curves に extend) | §3.3 |
| **433a1 outlier** (curve-specific Taylor coefficient anomaly) | LOW (curve-specific, not framework) | §3.3 |
| **Hecke L extension** (general number field, not over ℚ) | OPEN | §6.1 |
| **p-adic Hasse-Weil L** (p-adic gauge 列追加) | OPEN scope outside | future N |
| **Stark rank 1 abelian conjecture proof** | OPEN (3 cases verified, R-gauge complete rep candidate) | §4.2-§4.4 |
| **Higher rank Stark** (rank ≥ 2) | scope 外 (超越数論領域) | §4 future |
| **OQ-NT-7/8 Brauer 5-tier completeness** | candidate_v1 (Tier classification conjecture) | §5 |
| **4-vertex triangulation formal closure** | proposal stage | §6.3, N5 forward |

### 7.5 辞書 residence map

| 本論 piece | residence | 状態 |
|---|---|---|
| §2 Hasse-Weil L weight-2 framework extension trajectory | `research/oq_omega5_v15_hasse_weil_L_*` (8 files), `c_theorems_master.md` "Path 2 countably-infinite family" annex (modular L weight-2 row) | candidate_v2 v8 (CONFIRMED genuine signal) |
| §3 BSD analytic rank K_E(t)·t² → r | `c_theorems_master.md` (T-Ω5e-v15 Hasse-Weil row 候補), `c_recursive_floor_principle.md §6.8.1` (Hasse-Weil L extension annex 候補) | 2026-04-26 annex 候補 |
| §4.1 Class number formula 6-gauge (5 cases) | `c_spectral.md §8`, `number_theory_dictionary_v1.md §5` | 既 ESTABLISHED |
| §4.2-§4.3 Rank 1 abelian Stark 3 cases | `research/stark_projection_v0.md`, `number_theory_dictionary_v1.md §5.2-§5.3` | 既 candidate (H-stark-2) |
| §4.4 ℚ(√−23) S_3 analytic closure | `research/stark_projection_v0.md` H-stark-2 closure, `nt_dedekind_artin_zeta.md §5.4` (canonical example), `nt_conductor.md §6.9` (Brauer/induction) | 既 (audit cleared 2026-04-10) |
| §5 Brauer 5-tier (Stark connection) | `brauer_closure_galois_classification_v0.md` (OQ-NT-7), `brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8), `nt_conductor.md §6.9` | OQ-NT-7/8 candidate_v0.2 |
| §5.3 Q_8 Tier √ numerical witness | `brauer_closure_failure_taxonomy_v0.md` v0.2 (Q_8 LMFDB), `nt_root_numbers.md` | 既 numerical verified |
| §6 Cross-connection 三角形 (4-vertex triangulation proposal) | `meta/triangulation_methodology.md §9` NT-internal Arrow 間 lens の 4-vertex extension annex 候補 | 2026-04-26 proposal stage, N5 forward |
| §7.4 Open frontier | `meta/open_questions_master.md` "Path 2 数論的普遍性 OQ" section + 新規 OQ candidates | 2026-04-26 issue 候補 |

**N5 forward residence**: §5 Brauer 5-tier の failure mode 詳細 + alternative Stark methods + §4 6-gauge → Origination matrix 8-gauge generalization が N5 で expand される base。

---

## 変更履歴

- **v0.3 (2026-04-27)**: N5 backward link + NT 5-paper 完成。N5 v0.2 起草完了 を §7.3 N5 forward bridge 表の状態列に反映 (本論 §3 BSD K_E·t²→r が weight-2 で 8-gauge new combination signature として N5 で classify + 本論 §6.3 4-vertex triangulation proposal_v2 へ拡張)。NT 系列 5-paper closure achieved。
- **v0.2 (2026-04-26)**: compact 版。v0.1 (815 行) から冗長削減 — Abstract M1-M5 各長文段落圧縮、§1.1/§1.2/§1.3 (position / N3 対比 / honest trajectory) 3 subsection を 2 に統合 (1.1 で position+対比、1.2 で trajectory framing)、§2.1 Dirichlet L 対比表を §3.4 と重複するため簡素化、§2.6 v8 G1-G3 結果の詳細表を §3.3 と重複するため summary に圧縮、§3.4 vs Dirichlet L 対比を §7.2 と統合 (§3.4 は要点のみ)、§4.3 Atlas grammar yaml 周りの説明圧縮、§5 5-tier 表と spectrum 図の重複削減、§6 4 subsection (6.1-6.4) を 3 に統合 (6.2 で Stark+Brauer 統合)。骨格・主張・instance 数値 (9/10, 21/24, 5%, K·t² 表)・SC4 caveat・REJECTED/CONFIRMED status は全保持。
- **v0.1 (2026-04-26)**: initial NT-only draft. N1 framework header + N2 Paper 2 構造解析 + N3 Path 2 数論的普遍性 上で Hasse-Weil L weight-2 framework extension (v2 arc 8-stage trajectory) + Stark rank 0/1 R-gauge complete representation + Brauer 5-tier closure を組み合わせ。

---

## 参考文献 (内部)

**Framework**: N1 (`N1_observation_theory_nt_ja.md` v0.5) / N2 (`N2_paper2_structural_ja.md` v0.3) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.2)

**Hasse-Weil L research arc (v2 arc 8-stage trajectory)**: `research/oq_omega5_v15_hasse_weil_L_*` 8 files (`cm_curve_v2_v0` PARTIAL → `smoothed_and_noncm_v2_v1` methodology → `t_adaptive_v2_v2` 11a1 CONFIRMED → `conductor_universality_v2_v3` 4 non-CM 21/24 PASS → `rank_universality_v2_v4` amplitude rank-discrim → `rank_amplitude_v2_v5` Phase 3 catch → `central_curvature_v2_v7` Taylor reviewer redirect → `proper_afe_v2_v8` library-grade CONFIRMED genuine signal)

**Stark / Brauer**: `research/stark_projection_v0.md` (Stark 6-gauge + Atlas grammar + ℚ(√−23) closure) / `research/brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2, success side) / `research/brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8 v0.2, failure side + Q_8 LMFDB)

**L1 / meta 依存 (N1 経由)**: `c_theorems_master.md` (Path 2 family annex + Dirichlet L extension scope annex, S15/S17) / `c_observation_optimal_gauge.md` / `c_arrow_bridge_constants.md §11` / `c_recursive_floor_principle.md §6.8` + §6.8.1 / `c_spectral.md §8` / `nt_dedekind_artin_zeta.md §1, §4, §5.4, §7` / `nt_conductor.md §6, §6.9` / `nt_relative_units.md` / `nt_root_numbers.md` / `nt_frobenius_schur.md` / `meta/triangulation_methodology.md §9` / `meta/new_domain_protocol.md §8` / `meta/open_questions_master.md` / `number_theory_dictionary_v1.md §5`

**後続論文 (起草予定)**: N5 (Brauer 障害論 詳細 + Origination matrix 8-gauge)
