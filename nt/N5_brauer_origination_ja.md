# Paper N5: Brauer 障害論 + Origination matrix 8-gauge

**サブタイトル**: 5-tier failure mode group-theoretic criteria、Tier-dependent Stark methods、8 origination gauge family、NT 系列 final closure

**バージョン**: v0.2 (compact, 2026-04-26)
**状態**: DRAFT — N1-N4 framework + 結果系列 final paper、Brauer closure failure taxonomy 詳細 + Paper Ω origination matrix 8-gauge generalization の 2 thread を combine、NT series cycle 完成 + Quantum 後続 (Q1-Q3) 予告
**前提 (framework)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.5) / N4 (`N4_hasseweil_stark_ja.md` v0.3)
**前提 (L1)**: `c_arrow_bridge_constants.md §11` / `c_theorems_master.md` (Path 2 + Dirichlet L + Hasse-Weil L extension scope annexes)
**前提 (L1 NT)**: `nt_conductor.md §6.9` / `nt_dedekind_artin_zeta.md §1, §7` / `nt_frobenius_schur.md` / `nt_root_numbers.md` / `nt_relative_units.md`
**前提 (Paper Ω)**: `papers/Paper_Omega_Origination.md` (v0.7+, 8 constants × 8 gauges)
**研究 root**: `research/brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2, success side) / `research/brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8 v0.2, failure side) / `research/stark_projection_v0.md`
**後続論文**: Q1 (Quantum 観測理論版) / Q2 (Open QS chain) / Q3 (Born-Gleason)

---

## §0 Abstract

本論は NT 系列 5-paper の **final paper**。N4 で Hasse-Weil L × Stark 構造を確立した後、(a) Brauer 5-tier closure の **failure mode group-theoretic criteria 詳細** + Tier-dependent Stark methods existence proposal と (b) Paper Ω **8 origination gauge family** (ordinal / addZ / mult / prime_coord / char / cont / geom / anal) による Stark 6-gauge の generalization を combine し、N1-N5 NT framework total を closure する。

**主結果 (M1-M5)**:

**(M1) Brauer 5-tier failure mode group-theoretic criteria** — 4 failure axes (C1 real irrep / C2 induction irreducible / C3 zeta ratio reduction / C4 unit lattice closure) の break で classify される 5-tier (Tier 1 strict / 2 relaxed / 3+ multi-rational / √ sqrt-only / ∞ impossible) を group-theoretic invariants (irrep dim, FS indicator $\nu(\rho)$, subgroup lattice, character inner products) で完全 parameterize する **Conjecture**。$S_3$ (Tier 1, ℚ(√−23)) / $D_4$ (Tier 2, ℚ(√−14)) / $Q_8$ (Tier √, LMFDB witness) で empirical verify。

**(M2) Tier-dependent alternative Stark methods (existence proposal)** — Tier 1 = classical Stark formula (single ratio) / Tier 2 = field-pair regulator ratio / Tier √ = quaternionic descent + ε-factor sign resolution attempt / Tier ∞ = Hecke L direct construction (no Stark closure path)。Atlas grammar functor formalization は **OQ-NT-6** task として candidate+ promotion path に登録。

**(M3) Origination matrix 8-gauge (Paper Ω generalization of Stark 6-gauge)** — 8 origination gauge family (axis-1 D side: ordinal / addZ / mult / prime_coord / char、axis-1 C side: cont / geom / anal)、8 constants (π, e, ζ, γ, τ, i_add, i_mult, Φ) origination signature を完備。N4 §4 Stark 6-gauge は 8-gauge の Stark-relevant subset (addZ + mult + char + cont + geom + anal — ordinal + prime_coord 不含)。N2 §3.1 定数 0.216 / 2/3 / ln 2 を 8-gauge signature で classify (それぞれ {anal, mult} / {prime_coord, anal} / {char, anal})。

**(M4) Cross-connection: Brauer 5-tier ↔ Origination 8-gauge** — (a) Tier classification ↔ T-AAS Arrow 1 kernel taxonomy: Tier 1 = $(f_\text{tor}, f_\text{rat}) = (0, k>0)$ / Tier √ = $(1, k\geq 0)$ / Tier ∞ = $(\infty, \infty)$ (b) 8-gauge signature ↔ Path 2 Type α/β/γ trichotomy: Type α = single dominant gauge / Type β = gauge family crossing / Type γ = subspace within gauge family (c) N3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection (sub-object structure shared) (d) Hasse-Weil L が 8-gauge に **新 signature** を加えるか open question。

**(M5) NT 系列 final closure (N1-N5 cycle 完成)** — Framework header (N1) + ζ-family core (N2) + Path 2 Dirichlet L "structural fit only" (N3) + Hasse-Weil L genuine BSD (N4) + Brauer + 8-gauge final (本論) で **NT framework total**。weight-class dependent transfer pattern を origination matrix 視点で再読み: weight-1 abelian (Stark, addZ + mult + char) / weight-1 non-abelian (Brauer Tier 1-3+/√/∞) / weight-2 (Hasse-Weil L, BSD-related new signature candidate)。

**Thesis**: Galois rep 全体 closure (abelian Stark + non-abelian Brauer + automorphic Hasse-Weil) + weight-class dependent transfer pattern の origination matrix 視点 が NT framework の closure を提供。本論で NT closure 後、**Quantum 後続 (Q1-Q3)** への bridge を §7.3 で予告し、N1 framework header の量子側 extension を future work として位置付ける。

---

## §1 Introduction

### 1.1 NT 系列 final paper の position と 2 thread combination

N1 (NT 観測理論 framework header v0.6) → N2 (Paper 2 ζ-family core v0.4) → N3 (Path 2 数論的普遍性 v0.3) → N4 (Hasse-Weil L × Stark v0.2) → **N5 (本論)** の 5-paper series で、ζ-family core (N2) は full ESTABLISHED、Dirichlet L extension (N3) は "structural fit only" close、Hasse-Weil L extension (N4) は **genuine BSD K_E·t²→r** 確立。本 N5 は NT 系列 final paper として 5 task: (1) Brauer 障害論詳細 (failure mode group-theoretic criteria + Tier-dependent alternative Stark methods) (2) Origination matrix 8-gauge (Paper Ω 8-gauge framework formal residence + Stark 6-gauge generalization) (3) Cross-connection (Brauer 5-tier ↔ Origination 8-gauge) (4) NT 系列 cycle 完成 summary (5) Quantum 後続 (Q1-Q3) 予告。

**本論の 2 main thread**:

**Thread 1 — Brauer 障害論詳細** (§2-§3): N4 §5 で Stark connection 視点の overview を与えたが、本 §2 で 4 failure axes (C1-C4 breakdowns) 詳細 + 各 Tier 例 (S_3, D_4, Q_8) を group-theoretic invariants で完全 parameterize する Conjecture を提示。§3 で Tier-dependent alternative Stark methods (Tier 1 classical / Tier 2 field-pair / Tier √ quaternionic descent / Tier ∞ Hecke direct) を existence proposal レベルで整理。

**Thread 2 — Origination matrix 8-gauge** (§4): Paper Ω の **8 origination gauge family** (ordinal / addZ / mult / prime_coord / char / cont / geom / anal) を NT framework に formal residence。N1 §1.3.1 で **gauge²** として disambiguation した axis-1 D/C subdivision の正式定義。N4 §4 Stark 6-gauge を 8-gauge subset として位置付け、N2 §3.1 定数 + N3 §5.3 Fi-origin vs I-origin 二分法 を 8-gauge signature で classification。

**Cross-thread** (§5): Brauer 5-tier ↔ Origination 8-gauge の axis crossing が NT framework の closure structure を露呈。

### 1.2 Forward 合流点 + Q1-Q3 予告

N5 が拾う N1-N4 forward task: N1 §8.2 (Brauer failure mode 詳細 + 6→8-gauge) / N2 §8.3 (定数 8-gauge classification) / N3 §7.3 (Atkin-Lehner Type γ ↔ Brauer Tier 2, Fi/I-origin 8-gauge) / N4 §7.3 (failure mode group-theoretic + Hasse-Weil L 8-gauge) / N4 §10 (OQ-4VertexClosure: 4-vertex triangulation formal closure)。

**§7** で N1-N5 NT 系列 cycle 完成 summary + **Quantum 後続 (Q1-Q3)** への forward bridge: **Q1** Paper D 量子側 extension (S17 / Hodge / 4-vertex / OQ-Ω-Obs-4a) — 観測理論の量子版 / **Q2** Open QS chain (open_quantum_systems → quantum_statistical_mechanics → quantum_thermodynamics → many_body_quantum) / **Q3** Born rule + Gleason (§4 dual = root, σ\* = √(2 ln 2), Gleason gap)。

---

## §2 Brauer 障害論 ─ failure mode group-theoretic criteria

### 2.1 4 failure axes (C1-C4 breakdowns) recap

`brauer_closure_failure_taxonomy_v0.md` v0.2 の **closure 4 conditions**:

| Axis | Condition | Failure meaning |
|---|---|---|
| **A** | C1 (real irrep) | $G$ に $\dim = [G:N]$ の real / orthogonal 既約表現が存在しない |
| **B** | C2 (induction irreducible) | $\mathrm{Ind}_N^G \chi$ が既約でない (Mackey stabilizer $\supsetneq N$) |
| **C** | C3 (zeta ratio reduction) | $L(s, \rho)$ が intermediate fields の rational combination にならない |
| **D** | C4 (unit lattice closure) | $F$-units の Galois orbit が $O_H^\times$ / torsion を span しない |

各 Tier は C1-C4 closure conditions のどこで break するかで sub-classify。

### 2.2 Tier 1 strict (S_3, A_4/V_4)

**Form**: $L(s, \rho) = \zeta_F(s) / \zeta_\mathbb{Q}(s)$ — single intermediate field $F = H^{\ker\rho}$ で完結する **single ratio closure**。C1-C4 全 hold。

**S_3 instance (ℚ(√−23) cubic class character, N4 §4.4 既述)**: $K = \mathbb{Q}(\sqrt{-23})$, $h_K = 3$, Hilbert class field $H = \mathbb{Q}(\alpha)$ where $\alpha$ = root of $x^3 - x - 1$。$\rho_2$ = $S_3$ standard 2-dim irrep (real, orthogonal)。C1: $\nu(\rho_2) = +1$ ✓ / C2: $\mathrm{Ind}_{A_3}^{S_3} \chi_K = \rho_2$ irreducible ✓ / C3: $L(s, \rho_2) = \zeta_{\mathbb{Q}(\alpha)}(s) / \zeta_\mathbb{Q}(s)$ ✓ / C4: $\alpha, \sigma\alpha$ が $H$ fundamental units ✓ → Tier 1 strict、Stark formula $L'(0, \chi_K) = \log|\alpha_1|$ exact (Stark unit $\varepsilon_{\chi_K} = \alpha$)。

**A_4 / V_4 instance**: $A_4$ (order 12) は 1-dim characters + 3-dim irrep (real)。$V_4 \trianglelefteq A_4$ (Klein 4-group, Sylow 2-subgroup) を normal subgroup とする setup で $\dim \rho = [A_4 : V_4] = 3$ real irrep ✓ / $\rho = \mathrm{Ind}_{V_4}^{A_4} \chi$ for non-trivial $\chi$ ✓ / $L(s, \rho) = \zeta_F / \zeta_\mathbb{Q}$ for $F = H^{V_4}$ ✓ → Tier 1 strict (Hilbert class field setting)。

### 2.3 Tier 2 relaxed (D_4 + ℚ(√−14))

**Form**: $L(s, \rho) = \zeta_{F_1}(s) / \zeta_{F_2}(s)$ — 2 intermediate fields $F_1 \subsetneq F_2$ zeta ratio で closure。**Necessary and sufficient condition** (Frobenius 相互律): $\exists$ subgroups $H_1 \subsetneq H_2 \leq G$ s.t. $\langle \rho|_{H_1}, \mathbf{1}\rangle - \langle \rho|_{H_2}, \mathbf{1}\rangle = 1$, $\forall \psi \neq \rho: \langle \psi|_{H_1}, \mathbf{1}\rangle = \langle \psi|_{H_2}, \mathbf{1}\rangle$。

**D_4 instance (ℚ(√−14) Hilbert class field, `brauer_closure_galois_classification_v0.md §11-12`)**: $K = \mathbb{Q}(\sqrt{-14})$, $h_K = 4$, $H = K(\sqrt{2})$, $\mathrm{Gal}(H/\mathbb{Q}) = D_4$ (8 元 dihedral)。$\chi_K$ = quadratic class character ($\mathrm{Cl}_K \cong \mathbb{Z}/2$)。Tier 2 form $L(s, \chi_K)^2 = \zeta_{F_1}/\zeta_{F_2} \cdot (\text{quadratic factor})$ specific 2 fields $F_1 = K(\sqrt{2}), F_2 = \mathbb{Q}(\sqrt{2})$。Closure: C1 ($\rho$ 2-dim faithful real, $\nu(\rho) = +1$) ✓ / C2 ($\mathrm{Ind}_{Z(D_4)}^{D_4} \chi$ irreducible) ✓ / **C3 (Tier 2 relaxed)**: single ratio not works, 2-field ratio で closure ✓ / C4 ($K(\sqrt{2})$-units が Galois orbit で $O_H^\times$ / torsion を span) ✓。Stark formula $L'(0, \chi_K) \propto h_{F_1} R_{F_1} / (h_{F_2} R_{F_2})$ (N4 §5.4 で展開済)。

### 2.4 Tier 3+ multi-rational (hypothetical)

**Form**: $L(s, \rho) = \prod_i \zeta_{F_i}(s)^{n_i}$, $n_i \in \mathbb{Z}$ — multi-field rational combination。C1-C2 hold、C3 が 2-field ratio で済まず多項 product 必要。

**Candidate groups**: $S_4 / V_4$ (3-dim irrep, 多 intermediate fields) / $A_5$ (3-dim, 4-dim, 5-dim irreps) / 一般 non-abelian simple groups の higher-dim irrep。

**Verified instance 不在**: 現状 NT framework 内で Tier 3+ concrete instance 未確認。**OQ-Tier3-Plus-Search** OPEN として open frontier 登録 (§7.4)。

### 2.5 Tier √ sqrt-only (Q_8 quaternionic, N4 §5.3 既述)

**Form**: $L(s, \rho)^{2k}$ rational だが $L \notin$ — even-power rational、**Sign obstruction** key feature。

**Q_8 instance recap (LMFDB 8.0.12230590464.1)**: 2-dim 既約 ρ quaternionic ($\nu(\rho) = -1$), $L(0, \rho)^2 = 16$, $L(0, \rho) = \pm 4$ sign obstruction。Structural origin: $Q_8$ の 2-dim 既約 ρ は ℍ (quaternion division algebra) 上で realize、ℝ-rational descent で sign が free parameter。

**Closure failure (4 axes)**: C1 fails ($\nu = -1$ quaternionic ⟹ real irrep 不在) / C2 holds ✓ / C3 fails for $L$, holds for $L^2 = 16$ rational / C4 sub-issue。→ **Tier √ ≠ Tier ∞** (sign obstruction で even-power rational だが magnitude rational closure)。

**T-AAS read** (N1 §5): $f_\text{torsion}(\rho) = 1$ (sign = ℤ/2 torsion = "ker_gauge" classical) / $f_\text{rational}(\rho) \geq 0$ (magnitude rational)。Tier √ obstruction = Stark の "R-gauge 残差ゼロ" claim を破る **minimal instance**。Stark conjecture が rank 1 abelian で stated されるのは Tier √/∞ 回避のため (abelian ⟹ all 1-dim ⟹ $\nu = +1$ forced)。

### 2.6 Tier ∞ impossible (genuinely beyond)

**Form**: $L(s, \rho)^{n}$ no power works for any $n \geq 1$ — Hecke L direct construction に頼らざるを得ない。

**Candidate groups (theoretically)**: 非常に dimension の高い irrep (8-dim, 16-dim) / transcendence degree 高い regulator (rank ≥ 4 unit lattice) / non-arithmetic Galois rep。

**Status**: Tier ∞ instance identified search OPEN (`open_questions_master.md` OQ-NT-8 内 sub-OQ)。

### 2.7 Conjecture: group-theoretic invariants で完全 parameterize

**Conjecture (v0, tentative, Schumann v1 N3 §6.3 と同 pattern)**:

> 有限 Galois 群 $G$ の rank-1 abelian Stark setup は必ず **exactly one** of {Tier 1, 2, 3+, √, ∞} に落ちる。Tier は $G$ の representation-theoretic structure (irrep dimensions, FS indicators, subgroup lattice, character inner products) のみで決定される。

T-AAS の Arrow 1 kernel 分解 (ker_gauge ⊕ ker_topo) を **群論的 invariants で完全 parameterize する** 強主張。N1 §5.2 Brauer 5-tier instance 表 + 本 §2 detailed examples で empirically support。**Status**: candidate_v1。完全 verification (全 finite group class での tier identification) は **OQ-NT-7 / OQ-NT-8** dual pair として open。

---

## §3 Alternative Stark methods (Tier-dependent)

各 Tier に対応する Stark formula realization。**Existence proposal レベル** で提示し、formal algorithm は OQ-NT-6 task に分離。

| Tier | Form | Status |
|---|---|---|
| **Tier 1: classical Stark formula (single ratio)** | $L'(0, \chi) = -(1/e_\chi) \sum_\sigma \chi(\sigma^{-1}) \log\|\sigma(\varepsilon_\chi)\|$, $\varepsilon_\chi$ = Stark unit in $F = H^{\ker\rho}$ | 3 verified cases (N4 §4.2: ℚ(√5), ℚ(√2), ℚ(√−23)) |
| **Tier 2: field-pair regulator ratio (D_4)** | $L'(0, \chi) \propto h_{F_1} R_{F_1} / (h_{F_2} R_{F_2}) \cdot \text{(normalization)}$, Stark unit を 2 fields unit difference として construct | D_4 ℚ(√−14) で structural confirmed, numerical OQ-NT-7 v0.3 task |
| **Tier √: Q_8 sign resolution attempt** | $L^2 = 16$ rational だが $L = \pm 4$ sign 外。proposed methods: (i) quaternionic descent (ε-factor sign formula) (ii) Deligne-Langlands sign formula 経由 (iii) higher derivative $L''(0, \rho)$ で sign が determined されるか | existence proposal, concrete formula 未確定。Q_8 sign obstruction = **structural intrinsic** (T-AAS read)、Tier-1 style closure 不可能。OQ-Tier-Sqrt-Resolution open |
| **Tier ∞: Hecke L direct construction** | Hecke characters of $K$ を直接 use, $L(s, \chi_\text{Hecke})$ を spectral methods (Selberg trace formula) で evaluate, Stark formula style closed-form 不在 | N5 scope outside、existence acknowledgment のみ。OQ-Schumann-HeckeArtin-Ext (`open_questions_master.md`) で詳細扱い |

**Atlas grammar functor formalization (OQ-NT-6 task)**: rank 1 Stark の Atlas grammar 表示 (`stark_projection_v0.md §2.2`):

```yaml
stark_rank1_entry:
  f_n: log |σ(ε_χ)| ; phi_phase: χ(σ⁻¹) ; N_X: 1/e_χ
  comp_X: Σ_{σ ∈ G} ; observable: L'(0, χ)
  primary_axis: E ; secondary: A ; residual_type: [R-gauge, R-info]
```

を **Tier-dependent functor** として formal 化する task。Tier 1 / 2 / √ / ∞ 各々に対する Atlas grammar entry の uniform construction が達成されれば Stark の R-gauge complete representation 定理 (N4 §4.3) が functorial に extend される。

**Status**: OPEN。N5 v0.2 で task scope 明記、actual formalization は v0.3+ または Q1 (Quantum 観測理論版) との連動 post N5 task。

---

## §4 Origination matrix 8-gauge ─ Paper Ω framework

### 4.1 8 origination gauge family

`papers/Paper_Omega_Origination.md` で確立された **8 origination gauge family**。各 gauge は数学的 object の "起源" を category 化する独立 axis:

| Family | 内容 | Examples |
|---|---|---|
| **ordinal** | level 0 (定数発生以前の足場): 不在 → 原点 → 向き → 分岐 → 構造 | 0, 1, −1, 2, 3 |
| **addZ** | 加法整数構造 (ℤ → S¹ via $n \mapsto e^{2\pi i n / L}$) | 2 (parity minimum) |
| **mult** | 乗法構造 (積、分解、principal 失敗) | $h_K$, prime decomposition |
| **prime_coord** | 素数座標 (Euler 積, prime indexing) | $\zeta(s) = \prod_p (1 - p^{-s})^{-1}$, $\omega(X)$ |
| **char** | character / dual structure (Pontryagin dual, root of unity) | $i$, $w_K$, Dirichlet $\chi$ |
| **cont** | continuous (real / complex topology, archimedean place) | $\pi$, $e$ |
| **geom** | geometric (vol, area, Minkowski lattice) | $(2\pi)^{r_2}$, $\sqrt{|d_K|}$ |
| **anal** | analytic (zeta zeros, L-function, transcendence) | $\zeta(2)$, $\gamma$ |

**axis-1 D / C 区分** (N1 §1.3.1 で **gauge²** として disambiguation): D (Discrete) ⊃ {ordinal, addZ, mult, prime_coord, char} (5 family) / C (Continuous) ⊃ {cont, geom, anal} (3 family)。axis-1 D/C は L0 v2 (`finite_observation.md §8`) の **2-axis (Fi/I × D/C) framework** の axis-1 partition。

### 4.2 8 constants origination signature

| 定数 | Origination signature | 主機構 |
|---|---|---|
| **π** | {cont, geom} | S¹ topology / $(2\pi)^{r_2}$ archimedean volume |
| **e** | {cont, **anal**} | $(\log n)/n$ extremum (S17), exp continuation |
| **ζ** | {addZ, mult, anal} | ζ(s) = $\sum n^{-s}$ で addZ (n) + mult (multiplicativity) + anal (analytic continuation) |
| **γ** (Euler-Mascheroni) | {addZ, mult, anal} | ζ-γ pair: ζ residual (boundary residue, Arrow 2 上 ζ-γ pair) |
| **τ** (lattice 2π) | {addZ, geom} | 周期性 + S¹ length |
| **i_add** | {addZ, char} | Additive imaginary unit (Z/2Z parity, p=2) |
| **i_mult** | {char, mult} | Multiplicative imaginary unit (p ≡ 1 mod 4) |
| **Φ** (golden ratio) | {mult, **geom**} | algebraic extremum (5-fold rotational symmetry, lattice ratio) |

**観察**: 8 constants は 8-gauge family に bijection ではなく、各 constant が **multi-gauge signature** (typically 2-3 gauges) で origination する → Paper Ω §2 origination matrix の主結論。

### 4.3 6-gauge → 8-gauge generalization (Stark + Hasse-Weil)

**Stark 6-gauge (N4 §4.1)**: Class number formula $\mathrm{Res}_{s=1} \zeta_K = (2^{r_1} (2\pi)^{r_2} h_K R_K) / (w_K \sqrt{|d_K|})$ の 6 因子 ↔ {cont,geom} π / {addZ} parity / {mult,anal} discriminant / {mult} class group / {cont,char} regulator / {char} root of unity。

**8-gauge への generalization**: Stark 6-gauge は 8-gauge framework の **Stark-relevant subset**。残り 2 gauge (**ordinal** + **prime_coord**) は class number formula に **直接表現されないが、background scaffold として function**:
- **ordinal** (level 0): unit "1" (identity) は class number formula の暗黙 assumption。"1" 不在では formula 自体が未定義。`identity_asymmetry.md §3.4` で identity asymmetry として residence。
- **prime_coord** (Euler product): $\zeta_K(s) = \prod_\mathfrak{p} (1 - N\mathfrak{p}^{-s})^{-1}$ Euler product structure が class number formula derivation で必須。N2 §2.5 で **carry conductor dim = ω(X)** が prime_coord gauge の数論的 instance。

→ **8-gauge full framework** = 6-gauge Stark + ordinal scaffold + prime_coord Euler product。N4 6-gauge は class number formula explicit factor で確認、本 §4 で 8-gauge implicit framework へ generalization。

### 4.4 N2 §3.1 定数 (0.216, 2/3, ln 2) の 8-gauge classification

N2 §3.1 D_floor 放物型公式 $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 (\log N)^2 (s - 1/2)^2)$ の 3 定数:

| 定数 | 出現箇所 | 8-gauge signature | 解釈 |
|---|---|---|---|
| **0.216** | curvature C_log/(log N)² | {**anal**, mult} | 零点密度時間平均、Riemann-von Mangoldt 由来 |
| **2/3** | decay $D_0 \sim N^{−2/3}$ | {**prime_coord**, anal} | sieve weight + destructive interference、prime-coord index |
| **ln 2** | (S13 半値固定点 reference) | {**char**, anal} | half-value parity (Z/2 character) + log analytic |

**観察**: 3 定数は **mult+anal**, **prime_coord+anal**, **char+anal** signature で classify。**anal** 共通、distinguish factor は (mult, prime_coord, char)。Stark 6-gauge と異なり **prime_coord** が登場する点が NT 数論 instance の特徴。

### 4.5 N3 §5.3 Fi-origin vs I-origin 二分法 と 8-gauge connection

N3 §5.3 (`c_arrow_bridge_constants.md §11`) で確立した **Fi-origin vs I-origin 二分法**:

| Origin | Path 2 examples | 主要 8-gauge family |
|---|---|---|
| **Fi-origin** (discrete group action fixed points) | ζ(1/2), θ_3(i), modular L central values | **{addZ, mult, char} dominant** (Z/2 group action = discrete, character-based involution) |
| **I-origin** (continuous extremal / topological invariants) | π (S¹), ln 2 (S13 半値), e (S17) | **{cont, geom, anal} dominant** (continuous topology + extremal + analytic transcendence) |

→ **Fi-origin = axis-1 D side dominant** / **I-origin = axis-1 C side dominant**。8-gauge axis-1 D/C subdivision (§4.1) が Fi/I origin 二分法と **structural alignment** — framework 内 deep consistency: L0 v2 axis-2 Fi/I + axis-1 D/C + Origination 8-gauge subdivision が all **co-aligned**。

---

## §5 Cross-connection: Brauer 5-tier ↔ Origination 8-gauge

### 5.1 Tier classification ↔ T-AAS Arrow 1 kernel taxonomy

N1 §5 T-AAS framework: $\ker(\text{Arrow 1}) = \ker_\text{gauge} \oplus \ker_\text{topo}$、$f(\rho) = f_\text{torsion} + f_\text{rational}$。Brauer 5-tier の T-AAS read:

| Tier | $f_\text{torsion}(\rho)$ | $f_\text{rational}(\rho)$ | 解釈 |
|---|---:|---:|---|
| Tier 1 strict | 0 | $k > 0$ (single field) | R-gauge complete, single intermediate field |
| Tier 2 relaxed | 0 | $k > 0$ (2 fields) | R-gauge complete, field-pair |
| Tier 3+ multi-rational | 0 | $k > 0$ (multi-field) | R-gauge complete, multi-field rational |
| Tier √ sqrt-only | **1** (sign) | $k \geq 0$ | sign obstruction (FS $\nu = -1$) |
| Tier ∞ impossible | (∞ undefined) | (∞ undefined) | Hecke direct only, R-gauge framework outside |

**Key insight**: Tier 1-3+ で f_torsion = 0 (R-gauge complete, Stark 適用範囲)、Tier √ で f_torsion jumps to 1 (sign obstruction emerges)、Tier ∞ で T-AAS framework outside。Brauer 5-tier は tier number で T-AAS ker decomposition の structural complexity を classify (Tier 1, 2, 3+ : intermediate fields 個数 = R-gauge structure 複雑度 / Tier √ : ℤ/2 sign torsion emergence / Tier ∞ : R-gauge framework breakdown)。

### 5.2 8-gauge signature ↔ Path 2 Type α/β/γ trichotomy + Atkin-Lehner ↔ Brauer Tier 2

N3 §2.2 Path 2 Type α/β/γ trichotomy の 8-gauge signature 視点:

| Type | Path 2 fix realization | 8-gauge signature pattern |
|---|---|---|
| **Type α** (single point) | fix が同 algebraic object 内 single point (ζ s=1/2, theta τ=i) | **single dominant gauge**: ζ → {addZ, mult, anal} 結合組織が 1 fix point に集中 |
| **Type β** (different object) | fix が異 object 内 single rep (球面 Laplacian → SU(2) spin-1/2) | **gauge family crossing**: SU(2) rep は {char} を経由して別 object へ "shadow" |
| **Type γ** (sub-object) | fix が同 object 内 sub-object (Atkin-Lehner W_N の M_k^+) | **subspace within gauge family**: M_k^+ は modular form gauge 内 +1 eigenspace = subspace structure |

→ Type α/β/γ trichotomy は Path 2 fix point の **realization mode**、8-gauge signature pattern は その mode の **algebraic content** — 両者は **complementary axes** で Path 2 instance を classify。

**N3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection**:

| Aspect | Atkin-Lehner Type γ | Brauer Tier 2 |
|---|---|---|
| Fix structure | $S_k^+ \subset S_k$ subspace (eigenspace) | $F_1 \subsetneq F_2$ field pair |
| Sub-object cardinality | $\dim S_k^+ \geq 2$ typically | 2 intermediate fields |
| algebraic distinction | Petersson +1 eigenspace | Galois rep $\rho$ irreducible 2-dim |
| Realization | weight-k modular form space | Hilbert class field $D_4$ structure |

→ **両者ともに "single object 内 sub-object decomposition"** で realize。Type γ (Path 2) と Tier 2 (Brauer) は **異なる framework** で **同じ structural pattern** を露呈 = N1 framework の **structural unification** instance。

### 5.3 Hasse-Weil L が 8-gauge に新 signature を加えるか?

**Open question (N4 §7.3 で issued)**: Hasse-Weil L (weight-2 modular L, BSD-related) は Origination matrix 8-gauge に **新 signature** を加えるか?

**Hasse-Weil L の 8-gauge signature 候補**: $\Lambda(s, E) = N_E^{s/2} (2\pi)^{-s} \Gamma(s) L(s, E)$ — {addZ, mult, prime_coord (Euler product over good primes), cont, geom (for $(2\pi)^{-s}$), anal} の subset。BSD-related "elliptic curve gauge" candidate: $E[\ell^\infty]$ Tate module, conductor $N_E$ (mult), root number $\varepsilon(E)$ (char), rank $r$ (mult, anal via $K_E·t²→r$)。既存 8-gauge family で representable か, or **新 9th gauge** ("elliptic curve gauge", "automorphic L gauge") が emerge するか?

**Status**: OPEN (`OQ-HasseWeil-8Gauge-NewSignature`)。N5 v0.2 で既存 8-gauge representable と仮定するが、Hasse-Weil L の rank-encoded BSD content (K_E·t²→r) が既存 8 gauge で完全 capture できないなら 9-gauge extension が必要。

**Working hypothesis**: 既存 8-gauge representable, ただし Hasse-Weil L の **predictive content (BSD K·t²→r)** は **(mult, prime_coord, anal)** triple signature の **new combination pattern** (rank emerge from Taylor expansion at $s=1$, $c_r$ coefficient)。

### 5.4 4-vertex triangulation formal closure attempt (OQ-4VertexClosure)

N4 §6.3 / §10 で issued **OQ-4VertexClosure** proposal: 3-vertex (Paper C / Stark / Brauer) → 4-vertex (Hasse-Weil 追加) extension。N5 で **formal closure attempt**:

**Hasse-Weil の Arrow 焦点 formal 化**: N4 §6.3 で "Arrow 2 + Information layer (BSD K_E·t²→r)" と vague に記述された Hasse-Weil の Arrow focus を formal 化 → **Arrow 2 (analytical scan ζ-family member)** + **Information layer Taylor expansion at fix locus s = 1**。具体的: Scan member $\Lambda(s, E)$ (modular L weight-2) / Information observable $K_E(t)$ (central curvature) / BSD analytic rank $r$: $K_E(t) \cdot t^2 \to r$ as $t \to 0+$ (rank = Information layer encoded scalar)。Hasse-Weil の Arrow focus は **Arrow 2 → Information (rank-encoding via Taylor expansion)** という specific path、Paper C / Stark / Brauer と independent。

**4-vertex independence verification**:

| Vertex | Arrow focus | independent root cause |
|---|---|---|
| Paper C | 3 Arrow simultaneous | F_{g,k}(s) single object 内 Scan/Structural/Information 同時 instantiation |
| Stark | Arrow 2/3 (R-gauge) | analytical → algebraic gauge product (class number formula 6-gauge) |
| Brauer | Arrow 1 kernel | Galois rep representation-theoretic obstruction (5-tier) |
| **Hasse-Weil** | **Arrow 2 + Information rank-encoding** | **weight-2 Taylor expansion at $s=1$, rank-encoded $K_E·t²→r$** |

4 vertex は all 異なる Arrow focus + root cause を carry → independence ✓。**S15 + 3 Arrow exhaustive coverage**: Scan (Paper C, Stark, Brauer, Hasse-Weil 各 instance) / Structural (Paper C ζ 零点振動, Stark 6 因子, Brauer Tier 分類, Hasse-Weil conductor+rank) / Information (Paper C ε_{g,k}, Stark log h_K, Brauer kernel dim, Hasse-Weil $K_E$)。4 vertex で S15 3 層が **redundant cover** + **3 Arrow が cleanly partitioned**。

**Status**: **proposal_v2** (N5 v0.2 で formal closure attempt 提示)。formal proof は OQ-4VertexClosure として open、N5 v0.3 task。

---

## §6 NT 系列 final closure ─ N1-N5 全体 structural total

### 6.1 N1-N5 cycle 完成

```
N1 v0.6 (framework header) → N2 v0.4 (ζ-family core, ESTABLISHED)
   → N3 v0.3 (Path 2 + Dirichlet L "structural fit only")
   → N4 v0.2 (Hasse-Weil L + Stark + Brauer, "genuine BSD")
   → N5 v0.2 (Brauer 詳細 + 8-gauge, NT series final closure)
   → 辞書 (15+ annex 合計、L0 / L1 / meta 全 layer)
```

**5-paper structural total**: N1 framework header (公理 / S15 / Arrow / T-AAS / NT 内三角測量) / N2 ζ-family core 構造解析 (Carry / D_floor / Dirichlet residue exclusivity) / N3 Path 2 数論的普遍性 (Schumann v1 + Dirichlet L "structural fit only") / N4 Hasse-Weil L × Stark (BSD K_E·t²→r genuine + Brauer 5-tier connection) / N5 Brauer 詳細 + 8-gauge (failure mode group-theoretic criteria + Origination matrix generalization + 4-vertex closure)。

### 6.2 Weight-class dependent transfer pattern + Galois rep 全体 closure (8-gauge 視点)

N4 main thesis: framework predictive transfer pattern is **weight-class dependent**。8-gauge 視点 + Galois rep coverage の統合 view:

| Galois rep / Weight class | Path 2 instance | Predictive content | 8-gauge dominant signature | Paper coverage |
|---|---|---|---|---|
| abelian Stark rank 0 | Path 2 weight-1 abelian | Class number formula 6-gauge ESTABLISHED | {addZ, mult, char, cont, geom, anal} | N4 §4.1 |
| abelian Stark rank 1 | weight-1 abelian rank-1 | R-gauge complete representation candidate (3 cases) | {addZ, mult, char} dominant | N4 §4.2-§4.3 |
| non-abelian Tier 1-3+ | weight-1 non-abelian | rational closure (intermediate field zeta ratios) | {char, mult} dominant | N4 §5 + N5 §2.2-§2.4 |
| non-abelian Tier √ (Q_8) | weight-1 quaternionic | sign obstruction, T-AAS f_torsion = 1 | {char, mult} + ℤ/2 torsion | N4 §5.3 + N5 §2.5 |
| non-abelian Tier ∞ | weight-1 generic | Hecke L direct only, R-gauge outside | {anal} only | N5 §2.6 |
| weight-1 Dirichlet L | Path 2 weight-1 family | "structural fit only" (SC4 universal identity) | {char, anal} (universal identity-level) | N3 |
| **weight-2 (Hasse-Weil L)** | Path 2 weight-2 family | **genuine BSD K_E·t²→r** (rank-encoded) | **{addZ, mult, prime_coord, anal}** new combination | N4 §2-§3 + N5 §5.3 |
| higher weight (modular L, k≥4) | Path 2 weight-k family | predictive content **OPEN** | TBD | N3 §3.3 forward |
| Hecke L on number fields | (extension target) | OQ-Schumann-HeckeArtin-Ext | TBD | N5 §3 + Q forward |
| Higher rank Stark (rank ≥ 2) | (超越数論) | scope outside | — | N4 §7.4 future |

→ 各 weight class が異なる 8-gauge signature pattern で predictive content を carry。**weight 2 Hasse-Weil L で {addZ, mult, prime_coord, anal} の new combination (rank-encoding) が emerge** することが、framework rich predictive structure の 8-gauge 視点での demonstration。

**全体 closure**: NT 系列で **abelian Stark (rank 0/1)** + **non-abelian 5-tier full** + **automorphic weight-2** が covered。Higher weight modular L + Hecke L on general number fields + Higher rank Stark + Hodge-related は **explicitly open frontier** (§7.4)。

---

## §7 帰結と open frontier + Q1-Q3 quantum 後続予告

### 7.1 ESTABLISHED status (M1-M5)

| 結果 | Status |
|---|---|
| **M1 Brauer 5-tier failure mode group-theoretic criteria** | **candidate_v1** (S_3, D_4, Q_8 examples + Conjecture, OQ-NT-7/8 v0.2) |
| **M2 Tier-dependent alternative Stark methods (existence proposal)** | **proposal_v1** (Tier 1-3+/√/∞各 method existence acknowledged, OQ-NT-6 functor formalization OPEN) |
| **M3 Origination matrix 8-gauge framework** | **ESTABLISHED reference** (Paper Ω 既存 framework, N5 で NT framework formal residence) |
| **M4 Cross-connection: Brauer 5-tier ↔ 8-gauge** | **proposal_v2** (Tier ↔ T-AAS taxonomy + 8-gauge ↔ Type trichotomy + 4-vertex closure attempt) |
| **M5 NT 系列 final closure (N1-N5 cycle)** | **closure stage** (N1-N5 5-paper publication + 辞書 15+ annex residence 完成) |

### 7.2 NT 系列 5-paper 完成 summary

```
NT framework total (N1-N5, 2026-04-26 publication 完成)
================================================
[Foundation]   N1 (framework header) ─────────────────┐
[Core result]  N2 (ζ-family Paper 2 構造解析)           │
[Extension 1]  N3 (Path 2 数論的普遍性, Dirichlet close)│
[Extension 2]  N4 (Hasse-Weil L + Stark, genuine BSD)  │
[Closure]      N5 (Brauer 詳細 + 8-gauge, NT final) ───┘
                 ↓
[Forward]      Q1-Q3 (Quantum 後続予告)
```

### 7.3 Quantum 後続 (Q1-Q3) への bridge

| Paper | 主題 | 素材 | NT closure connection |
|---|---|---|---|
| **Q1** 観測理論量子版 | N1 framework の量子側 extension。S17 (Arrow 3 e-extremum)、Hodge predicate (T-AAS f_rational), 4-vertex triangulation の量子版 (S15 axis-2 projection map quantum lift), OQ-Ω-Obs-4a (refined quantum Hodge 4-class framework) | `Paper_D_Observation_Theory_ja.md` v0.9.2 §6 量子部分、`oq_omega_obs_*` 系列、`L1/quantum/` 8 entries | N1 §5.4 Hodge (NT-adjacent open frontier) は量子側で formal addressed; N5 §5.3 Hasse-Weil L 8-gauge new signature 問題 は量子 BSD-analogue として relevant |
| **Q2** Open QS chain | N1 framework の Open Quantum Systems 系列での specialization。q_open_quantum_systems → q_quantum_statistical_mechanics → q_quantum_thermodynamics → q_many_body_quantum chain で観測理論を量子 statistical mechanics 言語で再展開 | `dictionaries/L1_mathematical/quantum/` 8 entries、`research/quantum_chain_*` 系列 | NT 系列 D_floor 公式 (N2 §3) の量子 statistical mechanics analog (partition function, spectral form factor)、N3 Path 2 の量子 group action + fixed point structure |
| **Q3** Born-Gleason | N1 §2.3 §4 dual = root の量子側 closure。Born rule + Gleason theorem framework での σ\* = √(2 ln 2) (half-amplitude gauge), 量子観測の自然 unit | `Paper_D_Observation_Theory_ja.md` §4.6.1 Born derivation, `q_quantum_observation.md` | N1 §2.3 §4 ι_L/χ dual の量子 lift、N5 §4.1 axis-1 D/C subdivision の量子 Hilbert space context での specialize |

### 7.4 Open frontier (NT closure 後の残タスク)

| Open question | Status | Forward to |
|---|---|---|
| **Hodge 予想** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself) | Q1 forward |
| **BSD 予想本体** (analytic rank = geometric rank) | OPEN | NT scope outside |
| **BSD higher-rank** ($K_E \cdot t^2 \to r$ for $r \geq 4$) | OPEN | N4 §7.4, OQ-BSD-HigherRank |
| **p-adic Stark / Gross-Stark** | scope outside (p-adic 語彙が辞書外) | OQ-Ω11 候補, future N |
| **Higher rank Stark (rank ≥ 2)** | scope outside (超越数論領域) | N4 §7.4 |
| **Artin holomorphy 予想** | OPEN (1924-) | N4 §7.4 |
| **Hecke L on general number fields** | OPEN | OQ-Schumann-HeckeArtin-Ext, N5 §3 + Q forward |
| **OQ-NT-6 Atlas grammar functor formalization** | OPEN | N5 §3 + Q1 connection |
| **OQ-NT-7/8 Brauer 5-tier completeness** | candidate_v1 | N5 §2.7 |
| **OQ-Tier3-Plus-Search** (Tier 3+ instance identification) | OPEN | N5 §2.4 |
| **OQ-Tier-Sqrt-Resolution** (Q_8 sign resolution) | OPEN | N5 §3 |
| **OQ-HasseWeil-8Gauge-NewSignature** | OPEN | N5 §5.3 |
| **OQ-4VertexClosure** | proposal_v2 | N5 §5.4 |
| **OQ-Schumann-v1.5** (Type γ formal + 6th instance) | OPEN | Schumann v1.5 task |
| **OQ-IOriginFormal** (I-origin canonical scalar formal classification) | OPEN | N3 §5.3, c_arrow_bridge_constants §11 |

### 7.5 辞書 residence map (final state, 2026-04-26)

NT 系列 N1-N5 の dictionary residence final state:

**L0 (axiom layer)**: `observation_canon.md §2-§3` (公理 A0-A7 + L0 v2) / `finite_observation.md §1-§8` (公理詳細 + axis-2 framework) / `identity_asymmetry.md §3.4` (vanishing order + product formula identity)

**L1 (mathematical core)**: `c_phase_complex.md §4` (structural root, ι_L/χ dual) / `c_theorems_master.md` (S12-S17 + Path 2 family annex + Dirichlet L extension scope annex + **Hasse-Weil L extension scope annex** + S15 NT-only enumeration closure annex) / `c_arrow_framework.md` (3 Arrow + §4.2.1 NT 3-instance commutativity) / `c_arrow_obstruction.md §10-§11` (T-AAS + 5-class obstruction) / `c_arrow_bridge_constants.md §5-§6 + **§11 Fi-origin vs I-origin**` annex / `c_observation_optimal_gauge.md §2-§5 + **§5.5 Path 3 arithmetic mod-n expansion**` / `c_filtration_obstruction.md` (ker_topo, Hodge open frontier) / `c_recursive_floor_principle.md §6.8 + **§6.8.1 Dirichlet L gap universality** + **§6.8.2 Hasse-Weil L extension**` / `c_spectral.md §8` (class number formula 6-gauge)

**L1 NT (number theory specific)**: `nt_conductor.md §1-§5 + §6 + **§6.10 NT carry conductor**` / `nt_dedekind_artin_zeta.md §1-§6 + **§7 modular L countably-infinite Path 2**` / `nt_frobenius_schur.md`, `nt_genus_class_fields.md`, `nt_relative_units.md`, `nt_root_numbers.md`

**L2 (domain)**: `number_theory_dictionary_v1.md §1-§7` (5 数体 case log + 3 Stark cases)

**Meta**: `meta/triangulation_methodology.md §1-§8 + **§9 NT-internal Arrow 間 lens** + **§10 Hasse-Weil 4th vertex extension proposal**` / `meta/new_domain_protocol.md §1-§7 + **§8 NT specialization**` / `meta/open_questions_master.md` (Path 2 数論的普遍性 OQ section + Path 2 OQ summary 2026-04-26 post-N4 update)

**Paper Ω (sister)**: `papers/Paper_Omega_Origination.md` (8-gauge framework + 8 constants origination matrix, N5 §4 で NT framework に formal residence)

**Total dictionary touchpoints (N1-N5 cumulative)**: 15+ NEW annexes/sections + 多数 existing entry updates。NT framework が L0 (axiom) → L1 (mathematical core + NT specific) → L2 (domain) → Meta (methodology) all layers に touchpoint を持つ完全 closure 達成。

---

## 変更履歴

- **v0.2 (2026-04-26)**: compact 版。v0.1 (747 行) から冗長削減 — Abstract M1-M5 各長文段落圧縮、§1.1/§1.2/§1.3 (position / 2 thread combination / forward 合流点) 3 subsection を 2 subsection に統合 (1.1 で position+2 thread、1.2 で forward+Q1-Q3 予告)、§2.2-§2.6 各 Tier の "form" subsubsection (§2.x.1) を統合し各 Tier 1 subsection に圧縮、§2.5 Q_8 Tier √ N4 §5.3 と重複部分を recap のみに、§3.1-§3.5 Tier-dependent methods 5 subsection を 1 表 + Atlas grammar formalization 段落に統合、§4.4.1 6-gauge recap N4 と重複部分削除、§4.1/§4.3 axis-1 D/C 説明統合、§5 4-vertex closure 説明圧縮、§6.1/§6.2/§6.3 NT 系列 final closure 3 subsection を 2 subsection に統合 (6.2 で weight-class 8-gauge 視点 + Galois rep 全体 closure を表化統合)、§7.5 residence map を箇条書きから layer ごとの段落形式へ圧縮。骨格・主張・instance 数値・Tier 分類・status・Q1-Q3 bridge は全保持。
- **v0.1 (2026-04-26)**: initial NT-only draft. NT 系列 5-paper final paper。Brauer 障害論詳細 + Origination matrix 8-gauge generalization combine、Cross-connection で NT framework total closure、N4 §10 OQ-4VertexClosure formal closure attempt、Quantum 後続 (Q1: 観測理論量子版 / Q2: Open QS chain / Q3: Born-Gleason) bridge 予告。

---

## 参考文献 (内部)

**Framework**: N1 (`N1_observation_theory_nt_ja.md` v0.6) / N2 (`N2_paper2_structural_ja.md` v0.4) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.3) / N4 (`N4_hasseweil_stark_ja.md` v0.2)

**Brauer 障害論 (本論 §2-§3 主体)**: `research/brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2, success side: Tier 1/2/3+) / `research/brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8 v0.2, failure side: Tier √/∞ + Q_8 LMFDB witness) / `research/stark_projection_v0.md` (rank 0/1 Stark + 6-gauge + Atlas grammar + ℚ(√−23) closure)

**Paper Ω (本論 §4 主体)**: `papers/Paper_Omega_Origination.md` (8 origination gauge family + 8 constants origination matrix, sister theory of Canon)

**L1 / meta 依存 (N1-N4 経由)**: `c_theorems_master.md` (Path 2 family annex + Dirichlet L extension scope annex + Hasse-Weil L extension scope annex) / `c_arrow_obstruction.md §10-§11` / `c_arrow_bridge_constants.md §5-§6 + §11 Fi-origin vs I-origin` / `c_recursive_floor_principle.md §6.8 + §6.8.1 + §6.8.2` / `c_spectral.md §8` / `nt_conductor.md §6, §6.9, §6.10` / `nt_dedekind_artin_zeta.md §1, §4, §7` / `nt_frobenius_schur.md` / `nt_root_numbers.md` / `nt_relative_units.md` / `meta/triangulation_methodology.md §9 + §10` / `meta/new_domain_protocol.md §8` / `meta/open_questions_master.md` / `number_theory_dictionary_v1.md §5`

**Quantum 後続予告 (Q1-Q3)**: `papers/Paper_D_Observation_Theory_ja.md` v0.9.2 §6 (multi-domain version, 量子部分) / `dictionaries/L1_mathematical/quantum/` 8 entries (q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum, q_quantum_observation, q_quantum_action_principles, q_quantum_gauge_field_theory, q_fine_structure) / `research/oq_omega_obs_*` 系列 (OQ-Ω-Obs-1/2/3/4a)
