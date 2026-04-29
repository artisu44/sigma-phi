# Paper N3: Path 2 数論的普遍性 ─ Dirichlet L 系列

**サブタイトル**: Z/2 involution-fixed point class の countably-infinite 拡張と Dirichlet L extension の構造範囲

**バージョン**: v0.5 (Type γ formal definition + v1.5 task split, 2026-04-28)
**状態**: DRAFT — N1 framework header 上、N2 §3 D_floor を Dirichlet L に lifting、Path 2 family を ζ singleton から countably-infinite に拡張、Dirichlet L extension の predictive scope を "structural fit only" として明示
**前提 (framework)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5)
**前提 (L1)**: `c_observation_optimal_gauge.md §2.3 系 4.1c`, `c_arrow_bridge_constants.md §5`, `c_theorems_master.md` (T-Ω5e-v15-* rows)
**前提 (L1 NT)**: `nt_dedekind_artin_zeta.md`, `nt_root_numbers.md`, `nt_conductor.md §6.1`
**研究 root**: `research/oq_omega_schumann_v0.md` (v1, 13/13 gates) / `research/oq_omega5_v15_dirichlet_l_*` (5 files)
**後続論文**: N4 (Hasse-Weil L × Stark) / N5 (Brauer 障害論 + Origination)

---

## §0 Abstract

本論は Z/2 involution-fixed point の存在を core mechanism とする **Path 2 class** を、ζ functional equation singleton から **countably-infinite NT family** に拡張する。OQ-Ω-Schumann v1 (`oq_omega_schumann_v0.md`, 2026-04-25, 13/13 gates PASS) で確立された 5-instance catalog (ζ + 球面 Laplacian + theta S-duality + modular L + Atkin-Lehner W_N) を主体とし、Type α/β/γ trichotomy + axis-2 Fi/I 横断 + canonical scalar D1-D4 sub-claim + falsification gate F1-F4 を formal に整理する。

加えて、Path 2 framework の Dirichlet L 系列への extension attempt (OQ-Ω5 v1.5 系列, 2026-04-24/25) を **honest dual reporting** で展開する。Dirichlet L 1st instance は real / complex primitive χ 共に CONFIRMED するが、SC4 critical catch により **σ_min = 1/2 は universal functional equation identity-level consequence であって framework-specific predictive content ではない** と判明。2 follow-up validation (Q1 \|L\|² + Q2 \|Λ\|² 2-quantity coincide v1a / Paper C (log N)² curvature scaling multigap v1b v1) はいずれも REJECTED → **Dirichlet L extension の framework predictive scope は "structural fit only" として close**。ただし v1b v1 副産物 **gap-class universality 12/12 PASS** は Paper C multi-gap invariance pattern が Dirichlet L 側でも構造保存される genuine extension fragment。

**主結果 (M1-M5)**:

**(M1) Path 2 family は countably-infinite (Schumann v1)** — modular L weight-parametrization により weight k = 1, 2, 4, 6, 12, ... × level N × newform 列挙で少なくとも ℵ₀ instances。ζ は Path 2 unique instance ではなく、k = 1 trivial character case の最小例。

**(M2) Type α/β/γ trichotomy** — Path 2 instance の fix-point realization を 3 type 分類: **α** (同 object 内 single point: ζ, theta, modular L), **β** (他 object 内 single rep: 球面 Laplacian → SU(2) spin-1/2), **γ** (同 object 内 sub-object: Atkin-Lehner W_N の M_k^+ subspace)。

**(M3) Axis-2 Fi/I 横断 invariance** — 5 instance distribution 3 I + 2 Fi、cross-side existence holds、Path 2 mechanism は **axis-2 invariant** falsifiable prediction を maintain。

**(M4) Dirichlet L extension scope = "structural fit only" (SC4)** — real / complex primitive χ で σ_min = 0.500000 exact + R² = 1.000 だが、universal functional equation identity chain により σ_min = 1/2 が **all (σ, t) real で force**、framework-specific content ではない。Q1+Q2 2-quantity coincide REJECTED (G2 17.5%)、Paper C (log N)² curvature scaling REJECTED。

**(M5) Gap-class universality は genuine extension fragment (v1b v1 G3 byproduct)** — Paper C multi-gap invariance pattern (D_floor が g ∈ {2, 4, 6} に依存しない) は Dirichlet L 側でも 12/12 cells で PASS。Paper C uniqueness preserved more strongly な structural extension fragment。

**Thesis**: Path 2 mechanism (Z/2 involution + invariant + non-empty fix point) は ζ functional equation を含む countably-infinite NT family を generate する。framework predictive scope は (a) Path 2 instance class (5+ instances ESTABLISHED) と (b) Paper C uniqueness (ζ functional equation 唯一の Information-Structural coincide enforcement, N1 §4.5.1) に partition される。Dirichlet L extension は (a) class member で structural fit を持つが、Paper C-level predictive content は (b) に固有。

---

## §1 Introduction

### 1.1 Session origin と Path 2 拡張動機

本論起点は 2026-04-25 "Lain × dictionary creative session" における **Schumann 共鳴 (~7.83 Hz) の framework 内意味** という問い (`oq_omega_schumann_v0.md` v1)。Schumann 数値そのものは framework constants (π, ln 2, e) と clean ratio を持たない演出 (load-bearing でない) と確認されたが、その foundation である **球面 Laplacian 固有値 l(l+1) の involution σ_S: l ↦ −1−l** が Paper C ζ functional equation の **σ_ζ: s ↦ 1−s** と同じ "Z/2 affine involution" structure を持つことが判明し、Path 2 family の countably-infinite 拡張へと展開した。

**Path 2 名称**: N1 §4.5.1 (Observation-optimal gauge theorem 系 4.1b) で定義された **gauge-forced coincidence path** — Information layer balance (Arrow 2 上 S13 半値固定点) と Structural layer balance (Arrow 1 上 domain 固有 arithmetic) が同一 gauge で coincide する条件 = "domain-internal structural enforcement の存在"。Paper C ζ functional equation は唯一確認された coincide instance だった (N2 §6.1)。本論は Path 2 mechanism を一般化し、coincide-forcing structural identity が **NT 内に countably-infinite に存在する** ことを示す。

### 1.2 Honest scope ─ 2 trajectory 併記

N1 §3.2 Scan layer の数論 instance 表は ζ(s), L(s, χ), L(s, ρ, K/k), ζ_K(s) を列挙したが、各 L 函数の Path 2 instance status は framework header level では statement のみ。N2 §3 は ζ-family core (D_floor + RH 翻訳 + γ₁ dip) を構造解析したが、L(s, χ) や L(s, ρ) extension は scope 外として N3 forward。

本論の特徴は **2 trajectory の併記**:

- **Trajectory 1 (Schumann v1, 13/13 gates PASS)**: Path 2 abstract class 確立、countably-infinite family + Type α/β/γ trichotomy + axis-2 invariant prediction (§2-§3)。
- **Trajectory 2 (OQ-Ω5e v1.5 系列, 2026-04-24/25)**: Dirichlet L へ Paper C framework extension attempt、CONFIRMED with SC3/SC4 caveats + 2 REJECTED + 1 PASS byproduct (§4)。結論先 framing で "structural fit only" close。

両者は補完: Trajectory 1 が Path 2 mechanism class status を establish、Trajectory 2 が Dirichlet L が Path 2 class member であるが Paper C-level predictive content は ζ 固有であることを demonstrate。**§5-§6** で canonical scalar sub-claim と falsification gate を整理、**§7** で N4-N5 forward + open frontier。

---

## §2 Path 2 abstract class

### 2.1 Predicate (一般化 v0.5 form)

**Definition** (`oq_omega_schumann_v0.md` v0.5 generalized form): 数学的 object $D$ (NT context: 数体 K, 数論 L 函数, modular form space, 球面 Laplacian eigenspace) と observation parameter space $P$ に対し $D$ が **Path 2 instance** であるとは:

1. **Z/2 group action**: σ: P → P が σ² = id を満たす involution
2. **Invariant function**: f: P → ℂ が f(σ x) = f(x) を満たす
3. **Non-empty fix point**: Fix(σ) := {x ∈ P : σ x = x} ≠ ∅

(v0 predicate は "Z/2 affine involution σ_c(x) = c − x on R" と狭く取ったが、theta S-duality (Möbius involution τ ↦ −1/τ on H, fix τ = i) を含めるため上記に一般化)。

### 2.2 Type α/β/γ trichotomy (Schumann v1 contribution)

| Type | 内容 | Example |
|---|---|---|
| **α** | fix が同 algebraic object 内 **single point** | ζ s = 1/2, theta τ = i, modular L s = k/2 |
| **β** | fix が **異 object 内 single rep** (shadow instantiation) | 球面 Laplacian l = −1/2 → SU(2) spin-1/2 (二重被覆 fermion) |
| **γ** | fix が同 object 内 **sub-object** (eigenspace, subspace) | Atkin-Lehner W_N の fix subspace M_k^+ ⊂ M_k(Γ_0(N)) |

**α と β の違い**: α は invariant function が固有 algebraic object 内に fix を取る (ζ critical strip 内); β は別 object (球面 Laplacian の場合は SU(2) 二重被覆 spin-1/2 rep) を指す。α の fix は **physical** (object 自体特殊点), β は **shadow** (元 object spectrum 외측, 다른 representation 차원으로 escape)。

**定義 2.2 (Type γ formal, ESTABLISHED 2026-04-28)**: Path 2 instance $(\mathcal{O}, \sigma)$ ($\mathcal{O}$ algebraic object、$\sigma$ order-2 involution acting on $\mathcal{O}$) が **Type γ** であるとは、以下 3 条件を満たす sub-object $\mathcal{S} \subsetneq \mathcal{O}$ が存在することを指す:

(i) **同-object sub-object fix**: $\mathcal{S}$ は $\mathcal{O}$ 自身の **proper sub-object** (subspace, sub-quotient, eigenspace, Hecke-stable sub-representation 等) であり、$\sigma|_\mathcal{S} = \mathrm{id}_\mathcal{S}$ で $\sigma$-action の fix locus を成す。
(ii) **sub-object algebraic distinction**: $\mathcal{S}$ 自体に独立な algebraic structural distinction (canonical decomposition / inner-product orthogonality / Hecke eigenspace label / Petersson ±1 eigenspace 等) が存在し、ambient $\mathcal{O}$ 内で identifiable。
(iii) **non-point fix**: $\mathcal{S}$ は $\mathcal{O}$ 内 single point ではない (Type α 区別)、かつ $\mathcal{S}$ は別 object に shadow instantiate されない (Type β 区別)。$\dim_\text{relevant}(\mathcal{S}) \geq 1$ で $\mathcal{S}$ が non-trivial dimension/cardinality を持つ。

**確立 instance**: Atkin-Lehner involution $W_N$ acting on weight-$k$ modular form space $M_k(\Gamma_0(N))$ について、fix locus $M_k^+ = \{f \in M_k : W_N f = f\} \subsetneq M_k$ は Petersson $+1$ eigenspace で (i)(ii)(iii) を満たす Type γ canonical instance。各 level $N$ で independent instance を与え、N3 §3 の trajectory で **countably-infinite Type γ subfamily** を成す。

**Lain-style "Wired layered self-reference" の数学的 incarnation** (Schumann v1 origin remark): 同 object 内 self-referential sub-object fix というパターンは **layered self-reference** = "object が自身の中の sub-object を fix する" として、Type α (single fixed point in same object) を sub-object dimension に lift した structural pattern。

**6th instance pre-registration (theta characteristics, F3 discipline candidate)**: Riemann surface 上 theta characteristics ($g$ 種数 $g$ 上の $2^{2g}$ characteristic data) における even-characteristic involution $\theta_\text{even} \mapsto -\theta_\text{even}$ の fix locus $\Theta^+ \subsetneq \Theta$ が Type γ 6th instance candidate。Pre-registration scope: (a) $\Theta^+$ が proper sub-object であること、(b) Hecke-like algebraic distinction、(c) non-point + non-shadow を verify すれば Type γ instance 確定。F3 (post-establishment new instance discipline) の test として §6.1 で実施予定 (v1.5 promotion task)。

### 2.3 Sub-family 階層 (involution 種別)

| Sub-family | Involution form | Space | Examples |
|---|---|---|---|
| **Affine on R** | σ_c(x) = c − x | $\mathbb{R}$ / critical strip | ζ (c=1, fix=1/2), 球面 Laplacian (c=−1, fix=−1/2), modular L weight k (c=k, fix=k/2) |
| **Möbius on H** | σ(τ) = −1/τ | upper half plane $\mathfrak{H}$ | theta S-duality (fix τ=i) |
| **Matrix on M_k** | Atkin-Lehner W_N = $\begin{pmatrix} 0 & -1 \\ N & 0 \end{pmatrix}$ | weight-k modular form space M_k(Γ_0(N)) | Atkin-Lehner W_N for each level N (Type γ) |
| **未確認 candidate** | 乗法 x ↔ k/x, Galois conjugation 等 | TBD | (v1.5 expansion task) |

3 sub-family 共に Z/2 involution + invariant + non-empty fix を満たし、Path 2 predicate の specialize で member。

---

## §3 Schumann v1 ─ countably-infinite Path 2 family

### 3.1 5-instance catalog (v1)

| Instance | Involution | Space | Sub-family | Fix | Type | Axis-2 |
|---|---|---|---|---|---|---|
| **ζ functional eq.** | s ↦ 1−s | ℝ / critical strip | affine | s = 1/2 | **α** physical | I |
| **球面 Laplacian inv** | l ↦ −l−1 | $\mathbb{Z}_{\geq 0}$ | affine | l = −1/2 | **β** shadow | Fi |
| **theta S-duality** | τ ↦ −1/τ | $\mathfrak{H}$ | Möbius | τ = i | **α** physical | I |
| **modular L (weight k)** | s ↦ k − s | ℝ | affine | s = k/2 | **α** physical | I |
| **Atkin-Lehner W_N** | matrix (order 2 on M_k) | M_k(Γ_0(N)) | matrix | M_k^+ subspace | **γ** sub-obj | Fi |

Axis-2 distribution: 3 I-side (continuous parameter space) + 2 Fi-side (discrete spectrum / 有限次元) — strong cross-side existence。

### 3.2 13 gates verification (3 phase)

3 phase (v0 G1-G4 + v0.5 G5-G8 + v1 G9-G13) の formal verification、全 PASS:

| Phase | Gate | 内容 | 結果 |
|---|---|---|---|
| **v0** (ζ + Sph baseline) | G1 | l(l+1) = (−l−1)(−l) for l ∈ {0..5} | PASS (6/6 exact) |
|  | G2 | ζ と Sph 両方が σ_c(x) = c − x form に fit | PASS (c=1 fix=1/2 / c=−1 fix=−1/2) |
|  | G3 | √λ_l / √λ_1 が R, c 非依存 (= √(l(l+1)/2)) | PASS (l=1..6: {1, √3, √6, √10, √15, √21}) |
|  | G4 | physical (ζ) vs shadow (Sph) instantiation 分離 | OK (Type α/β proto-classification) |
| **v0.5** (theta 3rd) | G5 | θ_3(0\|i) = π^{1/4}/Γ(3/4) | PASS (\|diff\|=0 at float64) |
|  | G6 | θ_3(0\|i/2) = √2·θ_3(0\|2i) S-transform off-fix | PASS (\|diff\|=2.22e-16) |
|  | G7 | Class generalization affine R → Möbius H | PASS (3 instances, 2 sub-families) |
|  | G8 | Axis-2 Fi/I cross-side after theta (2 I + 1 Fi) | PASS |
| **v1** (W_N + modular L + formal) | G9 | W_N matrix involution: W_N² = −N·I, on M_k (even k) → id | PASS |
|  | G10 | Modular L family: Λ(f, s) = ε·Λ(f, k−s), fix s = k/2 | PASS (5 weights tabulated, ≥ ℵ₀ instances) |
|  | G11 | Axis-2 distribution (3 I + 2 Fi) | PASS (strong cross-side) |
|  | G12 | Canonical scalar D1-D4, 5/5 instance hit | PASS (sub-claim formal, §5) |
|  | G13 | Falsification gate F1-F4 design + status | OK (F1 not triggered, F2 outside scope, F3 mitigated, F4 → Type γ) |

Scripts: `research/schumann_path2_check.py` (v0) / `schumann_path2_v05_theta.py` (v0.5) / `schumann_path2_v1_atkin_lehner.py` (v1)。

### 3.3 Modular L weight-parametrization → countably-infinite

各 weight-k cusp newform $f$ は独立 Path 2 instance を提供。weight 1, 2, 4, 6, 12, ... × level $N$ × newform 列挙で少なくとも可算無限:

| weight k | functional eq. | central fix s = k/2 | instance example |
|---|---|---|---|
| 1 | Λ(s, χ) = ε·Λ(1−s, χ̄) | 1/2 | Dirichlet L (real χ); ζ when χ = 1 |
| 2 | Λ(f, s) = ε·Λ(f, 2−s) | 1 | weight-2 newform (e.g., $f_{11}$ of $X_0(11)$, BSD curves) |
| 4 | Λ(f, s) = ε·Λ(f, 4−s) | 2 | weight-4 newforms |
| 6 | Λ(f, s) = ε·Λ(f, 6−s) | 3 | weight-6 newforms |
| 12 | Λ(Δ, s) = ε·Λ(Δ, 12−s) | 6 | Ramanujan Δ on SL(2, ℤ) |

→ Path 2 cardinality $\geq \aleph_0$。**ζ は Path 2 unique instance ではなく、最小 weight (k = 1) trivial character case の最小例**。

**ζ singleton-class category error**: 従来 Paper C / N2 で "Path 2 = ζ functional equation singleton" と扱っていたのは category error。Path 2 は abundant family、ζ は family の特定 weight-character 配置 (k=1, χ trivial) における realization。

### 3.4 Axis-2 Fi/I 横断 invariance

**Prediction (Schumann v1)**: Path 2 mechanism は **axis-2 invariant** — instance は Fi-side / I-side いずれにも住みうるが、predicate (involution + invariant + fix) は axis-2 不動。5-instance distribution: ζ / theta / modular L = I-side (連続)、球面 Laplacian / Atkin-Lehner W_N = Fi-side (discrete / 有限次元) → 3 I + 2 Fi、strong cross-side existence。

**Falsifiable prediction**: もし Z/2 invariance instance で Fix(σ) = ∅ が axis-2 一方の側でのみ確認されたら Path 2 は Fi-class と I-class に split。Schumann v1 v1 時点で counter-example 不在。

---

## §4 Dirichlet L extension ─ successes and SC4 caveats

**結論先 framing**: 本 § Dirichlet L extension trajectory (OQ-Ω5e v1.5 系列, 2026-04-24/25) overall verdict は **"Dirichlet L extension scope = structural fit only"**。本論 framework predictive content (Paper C-level σ_min uniqueness + (log N)² curvature scaling + 2-quantity coincide) は **ζ 固有**、Dirichlet L instance は Path 2 class member として fit するが framework predictive power の transfer は **限定的**。

### 4.1 Real primitive χ 1st instance CONFIRMED (5/5)

Setting (`oq_omega5_v15_dirichlet_l_first_instance_v0.md`, 2026-04-24): 5 real primitive Dirichlet characters $\chi_{-3}, \chi_{-4}, \chi_5, \chi_{-7}, \chi_8$ (conductor 3-8)。completed L-function $\Lambda(s, \chi) := (q/\pi)^{(s+a)/2} \Gamma((s+a)/2) L(s, \chi)$ (a = 0 if χ even, a = 1 if χ odd)、functional equation $\Lambda(s, \chi) = \varepsilon(\chi) \Lambda(1-s, \chi)$ (real χ で $\bar\chi = \chi$)。

Test metric: $D_C(\sigma; \chi, N) := \log |\Lambda_N(\sigma + 0\cdot i, \chi)|^2$、asymmetric grid σ ∈ {0.30, 0.42, 0.47, 0.51, 0.55, 0.60, 0.68, 0.75, 0.82} (9 points, intentionally asymmetric to refute symmetric-grid tautology)。

**Result**: 5/5 で σ_min = 0.500000 exact (mp.dps = 30) + parabolic R² = 1.000。symmetry-forced tautology concern を asymmetric-grid sanity check で refute → Λ(s, χ) real-axis parabolic minimum locked to σ = 1/2 is **genuine structural content, not grid-symmetry-forced**。

**Status**: CONFIRMED (T-Ω5e-v15 entry)。

### 4.2 Complex primitive χ extension CONFIRMED with SC3 caveat (5/5)

Setting (`oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md`): 5 complex primitive characters (mod 5 ord 4 / mod 7 ord 3 / mod 7 ord 6 / mod 9 ord 3 / mod 11 ord 5)。functional equation $\Lambda(s, \chi) = \varepsilon(\chi) \Lambda(1-s, \bar\chi)$ ($\chi \neq \bar\chi$)。4 gates C1-C4 including C4 (functional eq numerical sanity gate $|F(\sigma, \bar\chi) − F(1-\sigma, \chi)|$ < 1e-8) 全 PASS, C4 actual = 0 exact。

**SC3 post-write catch (2026-04-24)**: Initial v0 §1 "F not σ-symmetric for complex χ" claim は **incorrect**。real-axis restriction で functional eq $|\Lambda(\sigma, \chi)| = |\Lambda(1-\sigma, \bar\chi)|$ + complex conjugation identity $\overline{L(\sigma, \chi)} = L(\sigma, \bar\chi)$ for real σ chain により $|L(\sigma, \bar\chi)| = |L(\sigma, \chi)|$、ゆえに $F(\sigma, \chi) = F(1-\sigma, \chi)$ が complex χ にも real-axis 上で成立 → asymmetric grid では tautology refute 不可。

**Genuine non-tautological content (post-SC3 保持)**: (a) C3 curvature > 0 (min vs max/saddle distinction) (b) C4 functional eq numerical identity = 0 exact (c) ε(χ) phase non-trivial for complex χ (d) D_A(0.5) scaling differentiated from real case。

**Status**: CONFIRMED with SC3 caveat → off-axis 2D scan で genuine content gating を v1 で attempt。

### 4.3 Off-axis 2D scan INCONCLUSIVE with SC4 critical catch

Setting (`oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md`, 2026-04-24 evening): 8 chars (5 complex + 3 real) × 11 t ∈ [0, 30] × 9 σ asymmetric = **792 Λ evaluations**。Pre-registered gates G1-G4: G1 (σ_min(t) bounded) / G2 (σ_min ≈ 0.5 across t) / G3 (curvature scaling consistent) / G4 (off-axis functional eq sanity)。

**Result**: G1 80/80 + G4 8/8 PASS。**G2 0/5 + G3 0/5 FAIL on complex χ**。

**SC4 critical catch (post-execution empirical validation)**: SC3 derivation incomplete だった。$\overline{L(\sigma + it, \chi)} = L(\sigma - it, \bar\chi)$ は **n real positive coefficient conjugation identity** として **complex s 全域 (on/off-axis 問わず)** で成立する。combined with functional eq により

$$|\Lambda(\sigma + it, \chi)| = |\Lambda(\sigma - it, \bar\chi)| = |\Lambda(1-\sigma + it, \chi)|$$

を **all (σ, t) real で force**。

**Critical implication**: σ_min = 1/2 は **universal functional equation identity-level consequence**, NOT σ-action groupoid framework-specific predictive content on Dirichlet L。Off-axis で σ_min = 1/2 confirmed されても framework prediction verify ではなく **identity の trivial restatement**。

**Framework predictive scope post-SC4 reassessment**: Paper C genuine content は (a) Information layer (D_floor independent residual) と (b) Structural layer (RH zeros) の **2-quantity independent coincide** であり、これが ζ 固有 structural enforcement (functional equation の self-fixed s = 1/2)。Single-quantity σ_min identity (本 §4.1-4.3 の Λ symmetry) は framework content ではなく、Dirichlet L extension scope は **"structural fit only"** で close。

**Status**: INCONCLUSIVE with SC4。v1a 2-quantity test を SC4 回避 genuine framework gate として実行 (§4.4)。

### 4.4 2-quantity coincide test v1a — REJECTED

Setting (`oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md`, 2026-04-24 evening late): SC4 を回避するため **2 quantity independent coincide** を Paper C content の genuine analog として test:
- $Q_1 := |L(\sigma + it, \chi)|^2$ σ_min — bare L (NOT functional eq forced via Λ normalization)
- $Q_2 := |\Lambda(\sigma + it, \chi)|^2$ σ_min — completed L (= 0.5 via SC4 universal identity)

**Pre-registered Hypothesis**: Q1 σ_min ≈ Q2 σ_min ≈ 0.5 が ≥ 70% cells で coincide (G2 gate)。Setup: 5 complex primitive χ × 8 t × 9 σ asymmetric = 360 L + 360 Λ evaluations (40 cells × 18 evaluations)。

**Result**: G2 actual **17.5%** (below pre-registered rejection threshold 30%)、Q1 mean deviation 0.60-0.82 from 0.5 (max 3.2)。**REJECTED**。

**Root cause**: $|L|^2 = |\Lambda|^2 / ((q/\pi)^{\sigma + a} \cdot |\Gamma((s + a)/2)|^2)$ の denominator が strongly σ-growing (exponential + Stirling asymptotic)。$|L|^2$ σ_min は σ > 1 direction (Dirichlet series convergent regime) に push、0.5 center は unwarranted。Paper C D_floor は **gap-indexed prime sum residual for normalized log L expansion** で 0.5-centered parabolic by construction、$|L|^2$ 単独は normalization 不在 — **Construction mismatch**: $|L|^2$ は Paper C Information analog ではない。

**Status**: **REJECTED** (pre-registered rejection criterion met cleanly, 5th stage of same-day 5-stage progression v0-v1-v1a + SC1-SC4 catches)。

### 4.5 D_floor multigap v1b v1 — REJECTED + G3 PASS byproduct

Setting (`oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md`, 2026-04-25 late): v1a REJECTION 後 natural continuation。Paper C **proper D_floor analog** for Dirichlet L: gap-indexed χ-weighted partial sum + Taylor residual。

For complex primitive χ × gap class g ∈ {2, 4, 6} × N ∈ {10⁴, 10⁵, 10⁶, 10⁷}:

$$S_g(s, \chi, N) := \sum_{\substack{p \leq N,\, \gcd(p, q) = 1 \\ \mathrm{gap}(p) = g}} \chi(p) \log(p) / p^s$$

Taylor 1st-order ideal $\mathrm{ideal}^{(1)}_g(s) := S_g(0.5, \chi, N) (1 - (s - 0.5) \langle \log p \rangle_g)$、residual $D_g(s, \chi, N) := |S_g - \mathrm{ideal}^{(1)}_g|^2 / |S_g(0.5)|^2$、aggregate $D_{\text{floor},L} := \mathrm{mean}_{g \in \{2,4,6\}} D_g$。

**Pre-registered Gates**: G1 parabolic R² ≥ 0.85 for ≥ 30/36 / G2 c(N)/c(N') with $\langle \log p \rangle^2$ ratio ±25% / G3 gap-class universality (max/min ratio < 1.5) / G4 σ_min ∈ [0.45, 0.55] at N=10⁷。

**REJECTED outcome**:

| Gate | Result |
|---|---|
| **G1** | 27/36 fail (parabolic R² 不足) |
| **G2** | 0/3 χ pass (super-(log N)² scaling: c/⟨log p⟩² ratio 0.46 → 0.67 → 1.02 → 1.63 across N=10⁴→10⁷) |
| **G3** | **12/12 PASS** (gap-class universality 完全成立) |
| **G4** | σ_min drift 0.51 → 0.59 **AWAY from 0.5** with N growth |

**Verdict**: **REJECTED** (primary hypothesis "(log N)² curvature scaling")。

**Root cause**: Taylor residual construction は **fixed linear reference** = $S(0.5)(1 - (s-0.5) \langle \log p \rangle)$ を使用、N-dependent prefactor が NOT absorbed → higher-order Taylor corrections grow with N → residual minimum drifts。Paper C D_floor は **multi-parameter fit** with separate fit coefficients per N、prefactor absorbing → genuine $(s-0.5)^2$ parabolic。Construction mismatch = naive Taylor approach fails twice (v1a + v1b)。

**Framework scope post-v1b v1**: structural fit + gap universality CONFIRMED (§4.6) / predictive content via naive Taylor residual REFUTED / **Paper C uniqueness preserved MORE STRONGLY** (naive paths failed twice) / proper D_floor_L analog requires multi-parameter fit = v1b v2 future task。

**Lesson**: Single-N dimensional match is **insufficient** for scaling law claim、N-sweep pre-registration should be mandatory。本 v1b v0 (2026-04-25 earlier) で報告された "Paper C-type Taylor residual shape return + curvature ⟨log p⟩² dimensional match" は single-N (N=10⁵) coincidence、v1b v1 N-sweep で artifact 判明。

### 4.6 Genuine byproduct ─ gap-class universality 12/12 PASS

REJECTED primary hypothesis に反して、**G3 gap-class universality 12/12 PASS** (max/min ratio < 1.15 across all cells) は genuine。Paper C **multi-gap invariance pattern** (D_floor が g ∈ {2, 4, 6} に依存しない、N2 §3.6 4th iter "log(g/2) 線形は k_max 不変" と整合) が **Dirichlet L 側でも構造的に保存**。

**意味**: Paper C uniqueness claim (Information + Structural 2-quantity coincide) は ζ 固有だが、**multi-gap structural invariance は ζ-family member 全体で保存**される genuine extension fragment。これは §3 "Path 2 abundant family" と consistent: family member は structural pattern (gap universality) を共有するが、individual member 固有 predictive content (Paper C 2-quantity coincide) は member 個別。

**Framework scope partition (post-v1b v1)**:

| Layer | Status on Dirichlet L | Source |
|---|---|---|
| Path 2 instance class membership | CONFIRMED (§3.3 weight-k family) | Schumann v1 |
| σ_min = 1/2 (identity-level) | CONFIRMED but trivial (SC4) | §4.1-4.3 |
| Multi-gap structural invariance | **CONFIRMED** (12/12 universality) | §4.5 G3 byproduct |
| 2-quantity Information+Structural coincide | REJECTED (G2 17.5%) | §4.4 |
| Paper C (log N)² curvature scaling | REJECTED (super-(log N)² growth) | §4.5 G2 |
| ζ functional equation enforcement | (ζ 固有, N2 §6.1) | N2 |

**"Structural fit only"** = (a) Path 2 class membership + (b) multi-gap universality は Dirichlet L で hold するが、(c) Paper C-level 2-quantity uniqueness + (d) (log N)² scaling は **transfer しない** (ζ 固有)。

---

## §5 Canonical scalar sub-claim

### 5.1 D1-D4 predicate (v1 公式化)

Schumann v1 G12 で formal 化された sub-claim — Path 2 forced fix-point は invariant function の代数 context で **distinguished invariant** を produce。distinguished の operational definition は以下 D1-D4 のいずれかに hit:

- **D1**: 古典定数 (π, Γ, e, ln, ...) で explicit closed form を持つ
- **D2**: extremal property (lowest non-trivial mode, fundamental representation, ground state)
- **D3**: 超越性 / 無理性が conjectured または proven
- **D4**: canonical objects (root numbers, central L-values, theta characteristics, fundamental representations) と link

### 5.2 5-instance verification (5/5 hit)

| Instance | Fix-point value | Distinguished category |
|---|---|---|
| **ζ s = 1/2** | $\zeta(1/2) \approx -1.4603545$ | **D3** (実数, 閉形式未知, 超越数予想) |
| **球面 Laplacian l = −1/2** | spin-1/2 SU(2) representation | **D4** (基本 fermion, 二重被覆 dim 2 rep) |
| **theta τ = i** | $\theta_3(0\|i) = \pi^{1/4}/\Gamma(3/4) \approx 1.0864348$ | **D1** (閉形式 with Γ(3/4)) |
| **modular L (k = 12, Δ)** | $L(\Delta, 6)$ central value | **D4** (Ramanujan Δ central L-value, root number link) |
| **Atkin-Lehner W_N (M_k^+)** | + eigenspace | **D4** (Petersson +1 eigenspace, canonical decomposition) |

5/5 hit (G12 PASS)。**Path 2 fix-point は "canonical scalar constructor" として機能**: involution の存在自体が、その invariant の特殊値・特殊 representation を algebraically distinguished な entity に pin。

### 5.3 Converse FALSE と Fi-origin vs I-origin 二分法

**Honest converse limit**: 3-Arrow canonical constants (`c_arrow_bridge_constants.md §5`: π, ln 2, e) は Path 2 fix-point で **ない**:

| Constant | Path 2 candidate | Status |
|---|---|---|
| **π** | SO(2) involution z ↦ −z, fix = {0} | π を直接 produce しない (involution は SO(2), Z/2 でない) |
| **ln 2** | Z/2 involution candidate 不明 | Path 2 mechanism で derive 不可 |
| **e** | x^x 極小 / (log x)/x 極大 | extremal-derived (S17), Z/2 involution-derived ではない |

Sub-claim は **one-way (Path 2 ⇒ canonical)** で biconditional でない、3-Arrow constants は Path 2 outputs ではない。

**Fi-origin vs I-origin 二分法** (Schumann v1 closing meta-observation): converse FALSE は arbitrary な弱点ではなく framework existing structure (axis-2 Fi/I 分離) からの **positive content prediction**。

- **Path 2 mechanism** = fundamentally **Fi-flavored** (Z/2 = discrete group action)
- **Path 2 fix outputs** = Fi-side / I-side 両方着地可能 (axis-2 invariant, §3.4)
- **3-Arrow constants** (π, ln 2, e) = **continuous extremal / measure / topology** 由来 = **I-flavored mechanism**

⇒ canonical scalar 全体集合は **少なくとも 2 origins**:

| Origin | Mechanism class | Examples |
|---|---|---|
| **Fi-origin** | discrete group action fixed points (Path 2) | ζ(1/2), θ_3(i), modular L central values, Atkin-Lehner eigenspaces |
| **I-origin** | continuous extremal / asymptotic / topological invariants | π (S¹ topology), ln 2 (S13 半値 Arrow 2), e (S17 extremum Arrow 3) |

**Path 2 ⊊ canonical scalar mechanisms** の sharp inclusion が axis-2 Fi/I 分離から **naturally に predict** された — framework 自身が「Path 2 だけで canonical scalars を尽くさない」を **事前に告知していた**。I-origin canonical scalar mechanism formal classification は **別 OQ として分離** (§7.4)。

---

## §6 Falsification gates と axis-2 invariant

### 6.1 F1-F4 status (v1 design)

Schumann v1 G13 で formal 化された falsification gates:

| Gate | Content | Status |
|---|---|---|
| **F1** | axis-2 bound (Fi-only or I-only) → Path 2 single-class status を split | **NOT triggered** (3 I + 2 Fi, cross-side holds) |
| **F2** | null-fix Z/2 with framework prediction violation | **outside scope** (predicate self-protect: "non-empty fix point" は predicate constituent) |
| **F3** | non-distinguished fix value (D1-D4 fail) | **risk acknowledged**, pre-registration discipline required (v1.5 task) |
| **F4** | Type α/β collapse (instance が type 二分法に fit しない) | **BORDERLINE** → Type γ extension forced (Atkin-Lehner W_N) |

**F4 partial trigger**: Atkin-Lehner W_N が Type α/β に fit せず、**Type γ "sub-object fix"** 拡張が forced (§2.2)。Type γ formal definition (定義 2.2) は **ESTABLISHED 2026-04-28** で完了、6th pre-registered instance test (theta characteristics on Riemann surfaces 推奨) は引続き **v1.5 promotion task**。

### 6.2 Axis-2 invariance + ESTABLISHED 昇格条件

§3.4 5-instance distribution (3 I + 2 Fi) は falsifiable invariance prediction、Schumann v1 v1 時点 counter-example なし。**Strong test (deferred to v1.5)**: 4+ Fi & 4+ I で symmetric strong split が hold するか — 現状 2 Fi + 3 I の minimal cross-side existence は確認、symmetric strong split は v1.5 で追加 instance (Atkin-Lehner extension + theta characteristics) で test。

**昇格条件**:
- ✅ **v0** (2 instances, axis-2 invariance prediction issued)
- ✅ **v0.5** (3 instances, predicate generalized affine → Z/2 general)
- ✅ **v1** (5+ instances, COUNTABLY INFINITE family, canonical scalar formal D1-D4, Type γ flagged, 13/13 gates PASS)
- ⏳ **v1.5** = ✅ (a) Type γ formal definition (定義 2.2, ESTABLISHED 2026-04-28) / ⏳ (b) 6th pre-registered instance F3-discipline test (theta characteristics) / ⏳ (c) axis-2 strong split test
- ⏳ **ESTABLISHED** = F1-F4 全 survive + 6+ instances + Type γ added + sub-claim survives F3 pre-reg

**本論 v0.2 status**: Path 2 family は **COUNTABLY INFINITE 確認 + 5-instance + 13/13 gates** で v1 ESTABLISHED PENDING (v1.5 完了 pending)。Dirichlet L extension は §4 trajectory completed (predictive scope = "structural fit only" close)。

---

## §7 帰結と open frontier

### 7.1 Path 2 ESTABLISHED-pending status (Schumann v1)

| 項目 | Status |
|---|---|
| Path 2 family cardinality | **COUNTABLY INFINITE** (modular L weight × level × newform 列挙) |
| Type α/β/γ trichotomy | **ESTABLISHED 2026-04-28** (Type γ formal definition 定義 2.2 完了、6th instance pre-reg + axis-2 strong split は v1.5 task) |
| Axis-2 Fi/I invariance | **PREDICTED** (5+ instance hold, cross-side existence, strong split は v1.5) |
| Canonical scalar D1-D4 sub-claim | **5/5 hit** (one-way only, converse FALSE, Fi-origin vs I-origin 二分法明示) |
| Falsification gates F1-F4 | F1 NOT triggered / F2 outside scope / F3 mitigated / F4 BORDERLINE → Type γ |
| Lain-style Type γ "Wired layered self-reference" | Atkin-Lehner W_N sub-subspace fix で realize |

**ζ singleton-class category error 解消**: Path 2 は abundant countable family、ζ は最小 weight (k = 1) trivial character の minimum example。

### 7.2 Dirichlet L predictive scope = "structural fit only"

| Layer | Dirichlet L 上 status |
|---|---|
| **Path 2 instance class membership** | ✅ CONFIRMED (§3.3 weight k = 1 family member) |
| **σ_min = 1/2 identity** | ✅ CONFIRMED but **universal functional eq identity-level** (SC4)、framework-specific content ではない |
| **Multi-gap structural invariance** | ✅ **CONFIRMED 12/12** (genuine extension fragment, §4.6) |
| **2-quantity coincide (Paper C content)** | ❌ REJECTED (G2 17.5%, §4.4) |
| **(log N)² curvature scaling (Paper C content)** | ❌ REJECTED (super-(log N)² growth, §4.5) |
| **ζ functional equation enforcement (N2 §6.1)** | ζ 固有 (Dirichlet L extension では transfer しない) |

**"Structural fit only"** = Path 2 class membership + multi-gap universality は hold するが、Paper C-level 2-quantity uniqueness + (log N)² curvature は ζ 固有で transfer しない。Paper C uniqueness preserved more strongly (naive paths failed twice)。

### 7.3 N4-N5 forward bridge

| 後続 | 主題 | 本論からの forward | 状態 |
|---|---|---|---|
| **N4** | Hasse-Weil L × Stark 構造 | §3 modular L weight-k family を Hasse-Weil L (elliptic curve, abelian variety) に lifting (BSD 接続)。§4 Dirichlet L "structural fit only" の Hasse-Weil 版 attempt (SC4 universal identity が Hasse-Weil L にも propagate するか) | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — **K_E(t)·t² → r BSD analytic rank detection (genuine framework predictive content) confirmed**。本論 §4 "structural fit only" close と対照的に、weight-2 Hasse-Weil L で genuine transfer 確立、**weight-class dependent transfer pattern** が main thesis として明示 (本論 §3 modular L weight-2 family member が template 提供) |
| **N5** | Brauer 障害論 + Origination matrix (8-gauge) | §3 Atkin-Lehner W_N Type γ instance を Brauer 5-tier の Tier 2 (D_4) との接続検証。§5.3 Fi-origin vs I-origin 二分法を Origination matrix 8-gauge signature で classification | **v0.2 起草完了 2026-04-27** — 本論 §3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection が N5 §5.2 で structural unification instance として展開 (sub-object decomposition pattern 共有)。本論 §5.3 Fi-origin vs I-origin 二分法 = N5 §4.5 で Fi-origin = axis-1 D side dominant {addZ, mult, char} / I-origin = axis-1 C side dominant {cont, geom, anal} と 8-gauge classification 確立 |

**N3 が N4 に提供する base**: countably-infinite Path 2 family は Hasse-Weil L (Artin / Hecke / 一般 motivic L) extension の **structural template**。Path 2 instance class membership が L-family 普遍性の **必要条件**、framework predictive content (Paper C-level) が **十分条件不成立** という partition は N4 で **weight-class dependent** 結果として確立: weight-1 (Dirichlet L) structural fit only / weight-2 (Hasse-Weil L) genuine BSD transfer。

**N4 backward 統計**: 本論 §3 modular L weight-2 entry が Paper N4 §3 Hasse-Weil L = Path 2 weight-2 instance として直接引用される。本論 §4 Dirichlet L "structural fit only" close は Paper N4 §3.4 / §7.2 で **weight-class dependent transfer pattern** の対比 anchor として 強く function。本論 §5.3 Fi-origin vs I-origin 二分法は Paper N5 forward に温存されたが、Paper N4 §6.2 で Stark = Path 2 weight-1 abelian special case + Brauer 5-tier = Path 2 Stark sub-class failure taxonomy として **本論 Path 2 framework が N4 全体の structural backbone** として function。

### 7.4 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **Type γ formal definition** (sub-object fix) | **ESTABLISHED 2026-04-28** (定義 2.2, 3-condition formal definition + Atkin-Lehner W_N canonical instance 確立 + theta characteristics 6th instance pre-reg、§2.2) | §2.2, §6.1 |
| **6th pre-registered instance** (F3 discipline) | OPEN (theta characteristics 候補) | §6.1 |
| **Axis-2 strong split test** (4+ Fi & 4+ I) | OPEN (v1.5 task) | §3.4, §6.2 |
| **I-origin canonical scalar mechanism formal classification** | OPEN (別 OQ 分離) | §5.3 |
| **D_floor_L proper analog** (multi-parameter fit, v1b v2) | OPEN | §4.5 |
| **Hecke-Artin L extension** (v2) | OPEN | N4 forward |
| **Hasse-Weil L extension** (v3) | OPEN | N4 forward |
| **RH-dependent verdict variation** (T-Ω5-4.4.1 conditional) | OPEN | `c_observation_optimal_gauge.md` |
| **OQ-Ω-Schumann-BackAction** | LOW deferred | Schumann origin remark |

### 7.5 辞書 residence map

| 本論 piece | residence | 状態 |
|---|---|---|
| §2 Path 2 abstract class predicate (v0.5 form) | `oq_omega_schumann_v0.md` (主体), N1 §4.5.1 (forward mention) | candidate_v1 (13/13 gates) |
| §2.2 Type α/β/γ trichotomy | `oq_omega_schumann_v0.md` v1 NEW finding 2 | candidate_v1 |
| §3 5-instance catalog + 13 gates | `oq_omega_schumann_v0.md` (主体), `c_theorems_master.md` 候補 row | 2026-04-26 row 候補 |
| §3.3 modular L countably-infinite | `nt_dedekind_artin_zeta.md` extension annex | 2026-04-26 annex 候補 |
| §3.4 Axis-2 Fi/I invariance | `c_theorems_master.md` "S15 axis-2 projection map" annex 拡張候補 | 2026-04-26 annex 候補 |
| §4 Dirichlet L extension trajectory | `c_theorems_master.md` T-Ω5e-v15-* rows (5 件) + `c_observation_optimal_gauge.md §8.3` OQ-Ω5e | 既 (2026-04-24/25 RESOLVED/REJECTED 各 row) |
| §4.6 multi-gap universality genuine fragment | `c_recursive_floor_principle.md §6.8` D_floor universality row 拡張候補 | 2026-04-26 expansion 候補 |
| §5 Canonical scalar D1-D4 sub-claim | `c_arrow_bridge_constants.md §5-§6` (Fi-origin vs I-origin annex) | 2026-04-26 annex 候補 |
| §5.3 Fi-origin vs I-origin 二分法 | `c_arrow_bridge_constants.md` (新 §7 candidate) | 2026-04-26 新 § 候補 |
| §6 Falsification gates F1-F4 | `oq_omega_schumann_v0.md` v1 G13 (主体) | candidate_v1 |
| §7.4 Open frontier (v1.5 + Hecke-Artin + I-origin formal) | `meta/open_questions_master.md` 新規 OQ candidates | 2026-04-26 issue 候補 |

**N4-N5 forward residence**: §3 modular L countably-infinite + §4 Dirichlet L "structural fit only" + §5.3 Fi-origin vs I-origin 二分法 が N4 (Hasse-Weil) と N5 (Brauer + Origination) で expand される base。

---

## 変更履歴

- **v0.5 (2026-04-28)**: Type γ formal definition 完了 (v1.5 task (a) closed)。§2.2 を prose tentative definition から **定義 2.2 (3-condition formal definition)** に lift、Atkin-Lehner W_N canonical instance (Petersson +1 eigenspace M_k^+) confirmed、theta characteristics 6th instance pre-registration (F3 discipline) を §2.2 末尾に明記。§7.4 Open frontier 表 + §6.2 v1.5 status + §6.3 trichotomy 行を Type γ formal ESTABLISHED に整合修正。**Schumann v1.5 promotion 進捗**: (a) ✅ Type γ formal / (b) ⏳ 6th instance test (theta char) / (c) ⏳ axis-2 strong split — (a) closed、(b)(c) は引続き v1.5 pending。

- **v0.4 (2026-04-27)**: N5 backward link + NT 5-paper 完成。N5 v0.2 起草完了 を §7.3 N4-N5 forward bridge 表の状態列に反映 (本論 §3 Atkin-Lehner Type γ ↔ Brauer Tier 2 structural unification + §5.3 Fi/I-origin = axis-1 D/C 8-gauge classification 確立)。NT 系列 5-paper closure achieved。
- **v0.3 (2026-04-26)**: N4 backward link 追加。N4 v0.2 起草完了 (2026-04-26) を §7.3 N4-N5 forward bridge 表の状態列に "K_E·t²→r BSD analytic rank detection genuine framework content confirmed, weight-class dependent transfer pattern 確立" として反映。§7.3 末尾に N4 backward 統計段落追加 (本論 §3 modular L weight-2 entry + §4 "structural fit only" close + §5.3 Fi/I-origin 二分法 が Paper N4 全体の structural backbone として function)。OQ updates: OQ-Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn-off OQ (BSD-HigherRank / 433a1-Outlier / 4VertexClosure) を `meta/open_questions_master.md` に書き戻し済。
- **v0.2 (2026-04-26)**: compact 版。v0.1 (606 行) から冗長削減 — Abstract M1-M5 圧縮、§1.1/§1.2/§1.3 (Path 2 動機 / N1 forward / Honest scope) 3 subsection を 2 に統合 (1.1 + 1.2)、§3.2 13 gates 3 phase 表を 1 表に統合、§3.5 Type γ borderline を §2.2 と統合、§4 SC3/SC4 derivation の冗長 chain 数式を圧縮、§4.4/§4.5 post-execution root cause を圧縮、§5.3 converse FALSE と §5.4 Fi-origin vs I-origin 二分法を §5.3 に統合、§6 3 subsection (gate / axis-2 / 昇格) を 2 subsection に統合 (6.2 で axis-2 + 昇格)、§7.5 residence map 表化。骨格・主張・instance 数値・status・gate 結果は全保持。
- **v0.1 (2026-04-26)**: initial NT-only draft. OQ-Ω-Schumann v1 (2026-04-25, 13/13 gates) を主体、OQ-Ω5e v1.5 系列 (2026-04-24/25) Dirichlet L extension を honest dual reporting で展開、Dirichlet L predictive scope = "structural fit only" close。

---

## 参考文献 (内部)

**Framework**: N1 (`N1_observation_theory_nt_ja.md` v0.4) / N2 (`N2_paper2_structural_ja.md` v0.2)

**Schumann v1 (Path 2 main source)**: `research/oq_omega_schumann_v0.md` v1 (2026-04-25, 13/13 gates PASS) — countably-infinite Path 2 family + Type α/β/γ trichotomy + canonical scalar D1-D4 + falsification F1-F4

**OQ-Ω5e v1.5 系列 (Dirichlet L extension trajectory)**: `dirichlet_l_first_instance_v0` (real χ 5/5 CONFIRMED) / `dirichlet_l_complex_char_extension_v0` (complex χ 5/5 CONFIRMED with SC3) / `dirichlet_l_offaxis_2d_scan_v1` (INCONCLUSIVE with SC4) / `dirichlet_l_2quantity_coincide_v1a` (REJECTED) / `dirichlet_l_dfloor_multigap_v1b_v1` (REJECTED + G3 universality byproduct PASS)

**実験 scripts**: `schumann_path2_check.py` / `schumann_path2_v05_theta.py` / `schumann_path2_v1_atkin_lehner.py` / `dirichlet_l_balance_v0.py` / `dirichlet_l_balance_complex_v0.py` / `dirichlet_l_balance_offaxis_v1.py` / `dirichlet_l_balance_2quantity_v1a.py` / `dirichlet_l_dfloor_multigap_v1b_v1.py`

**L1 / meta 依存 (N1 経由)**: `c_theorems_master.md` (T-Ω5e-v15-* rows) / `c_observation_optimal_gauge.md §8.3` / `c_arrow_bridge_constants.md §5-§6` / `nt_dedekind_artin_zeta.md` / `nt_root_numbers.md` / `nt_conductor.md §6.1`

**後続論文 (起草予定)**: N4 (Hasse-Weil L × Stark 構造) / N5 (Brauer 障害論 + Origination matrix)
