---
axis: A
position: algebra_constraint
static_dynamic: static
connected_to:
  - A.algebra_analysis
  - A.algebra_group
  - B.crystal
  - B.fx
  - C.scaling
  - L.number_theory
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-10
runtime_summary:
  what: Conductor = constraint codim count vector (NOT factor count). Scope = global/axial/zonal/partial. §1-5 crystal/FX, §6 数論版 (Dirichlet/Artin conductor)
  when: conductor 計算 / N_constraint / b₁(G) / centering vs glide vs screw / Dirichlet 指標導手 / Artin ramification / L(s,ρ) functional equation の導手因子
  provides: [conductor_vector, T1_centering_extinction, T2_FX_constraint, T5_first_betti, T6_codimension, codim_glide_1, codim_screw_2, dirichlet_conductor, artin_conductor, artin_conductor_codim_sum, unramified_codim_0, tame_ramification_codim_1, wild_ramification_codim_ge_2, L_function_conductor_factor, artin_induction, brauer_decomposition, isotypic_idempotent]
  consumes: [c_group_theory.md, c_phase_complex.md, c_spectral.md, nt_relative_units.md, nt_frobenius_schur.md]
  axis: [A]
  residual_types: [R-comp, R-gauge]
  key_theorems:
    - {id: T1, statement: "abs_centering = 1 - 1/n_centering"}
    - {id: T2, statement: "N_constraint = C(n,2) - (n-1) for n-currency FX"}
    - {id: T5, statement: "N_eff = b₁(G) = K - M + 1 for observation graph"}
    - {id: T6, statement: "glide → codim 1 (1/h), screw → codim 2 (1/h²)"}
    - {id: S8_artin_conductor_codim_identity, statement: "f_p(ρ) = Σ_i (|I_i|/|I_0|) codim(V^{I_i}) — Artin conductor は ramification filtration 重み付き codimension 和", derived_in: "§6.2", status: established, cross_refs: [c_spectral.md §8, research/stark_projection_v0.md]}
  cost: large
  status: established
  one_screen: |
    §1 Conductor = constraint vector, not scalar. Scope = global/axial/zonal/partial.
    §2 Composition: additive (FX) vs multiplicative (crystal).
    §3 n_eff = 1/(1-abs_total) で heterogeneous 吸収.
    §4 FX: T5 b₁(G) = K-M+1 for partial observation.
    §5 T6: glide codim 1 (1/h), screw codim 2 (1/h²). ρ_cross = |C₂/C₁| entanglement.
    §6 Number theory 拡張: Dirichlet conductor = 指標の最小周期; Artin conductor f_p(ρ) = Σ_i (|I_i|/|I_0|) codim(V^{I_i}).
       unramified=codim 0, tame=codim 1, wild=codim≥2. 全て conductor_count rule の同一テンプレート (constraint codim 和).
       c_spectral.md §8 の √|d_K| = Artin conductor of trivial char. Stark e_χ = conductor → K(χ) → w_{K(χ)} downstream.
       §6.9: Induction/Restriction/Brauer 分解. L(s, Ind σ) = L(s, σ). Brauer: all Artin L = ℤ-product of Hecke L.
       Tier 1: L = ζ_F/ζ_ℚ. Tier 2: L = ζ_{F₁}/ζ_{F₂}. Tier √: L² = ζ/ζ (square-root obstruction).
       Isotypic idempotent e_χ = (dim χ/|G|)Σ χ⁻¹(σ)σ cuts χ-component from unit lattice.
---

# Conductor

## 1. Definition

Conductor measures the strength of algebraic constraints in a system. It is fundamentally a **vector quantity**:

    conductor = (c_global, c_local, ...)

where each component corresponds to a distinct class of constraints with different scope.

### 1.1 Scalar reduction

A scalar conductor suffices when all constraints are homogeneous (same type, same scope). This is the case for:
- **FX**: all constraints are triangular arbitrage (same type, global scope) -> scalar N_constraint = C(n,2) - (n-1)
- **Simple crystals with P lattice**: no centering constraints -> scalar = 0

Scalar conductor FAILS when constraints are heterogeneous:
- **Crystal with centering + glide**: centering operates globally (kills fraction 1-1/n of ALL hkl), glide operates locally (kills fraction delta of SPECIAL hkl). These have different scope and cannot be combined into a single number.

### 1.2 Constraint scope

Each constraint has a **scope** = fraction of the observable space it affects.

| Constraint type | Scope | Example |
|---|---|---|
| Centering translation | Global (all hkl) | F centering: kills 75% of all reflections |
| Screw axis | Axial (00l only) | 6_3 screw: kills 50% of ~12 reflections |
| Glide plane | Zonal (h0l, 0kl) | c-glide: kills 50% of ~168 reflections |
| Wyckoff z+1/2 pairing | Partial (l-odd, h-k=0 mod 3) | Graphite: kills 100% of 342 reflections |

**Key result**: N_constraint (simple count) has R^2 = 0.000 as predictor of absence. Constraint TYPE and SCOPE matter, not count.

## 2. Constraint Composition Laws

### 2.1 FX: Additive with redundancy (alpha < 1)

Each new triangular arbitrage adds a linear constraint to the system. But constraints overlap — the 21st arbitrage is a linear combination of previous ones. This redundancy makes amp grow sub-linearly with N_constraint.

### 2.2 Crystal: Multiplicative (alpha > 1, or exact exponential)

Each independent centering translation halves the surviving reflections. n independent translations give survival rate 1/n. This is multiplicative composition, giving an exact exponential (not a power law).

### 2.3 General principle

The composition law of constraints determines the functional form of the scaling:
- Additive (with redundancy) -> power law regime of sigmoid
- Multiplicative (independent) -> exponential / discrete sigmoid
- The sigmoid is the general envelope

## 3. Effective conductor for heterogeneous systems

For a system with both global and local constraints:

    abs_total = abs_global + delta_local

where abs_global = 1 - 1/n_centering (exact), and delta_local is structure-specific.

The effective centering multiplicity:

    n_eff = 1 / (1 - abs_total)

gives a real-valued "conductor" that absorbs both contributions. Examples:
- BCC Fe (I centering, no glide): n_eff = 2.000 (integer, clean)
- Graphite (P + z+1/2 pairing): n_eff = 1.184 (fractional, "partial centering")
- Diamond (F + d-glide): n_eff = 5.682 (exceeds n_centering=4, glide adds)

## 4. FX conductor

FX conductor = N_constraint = C(n_ccy, 2) - (n_ccy - 1) = number of independent triangular arbitrage constraints.

| n_currencies | N_pairs | N_signal | N_constraint |
|---|---|---|---|
| 3 | 3 | 2 | 1 |
| 4 | 6 | 3 | 3 |
| 5 | 10 | 4 | 6 |
| 6 | 15 | 5 | 10 |
| 7 | 21 | 6 | 15 |
| 8 | 28 | 7 | 21 |

**Universe dependence**: N_constraint depends on the closed universe of currencies. Taking a subset changes the conductor definition.

### 4.1 Partial observation formula (Theorem T5)

For K observed pairs forming a connected graph G on M currencies:

    N_eff = b₁(G) = K - M + 1

where b₁ is the first Betti number (= number of independent cycles = cyclomatic number).

Physical meaning: the spanning tree of M currencies requires M-1 edges to identify
all M-1 independent factors. Each additional edge closes one cycle, creating one
triangular arbitrage constraint. b₁ counts these independent cycle closures.

**Verification** (fx_dict_partial_conductor.py + fx_dict_residual_10pct.py):
- 12-pair subset (8 ccy): b₁ = 12 - 8 + 1 = 5. Sigmoid(5) = 5.0. Observed: 4.5.
- Raw residual: +10%. After Wishart baseline correction (N/T effect): **+0.4%**.
- The 10% is NOT a conductor error — it's a Wishart(12,T) vs Wishart(10,T) baseline mismatch.

**Residual decomposition**:
- H1 (sigmoid fit uncertainty): ~4%
- H2 (cycle correlation / hub topology): ~2%
- H3 (Wishart N/T baseline): **~9%** (dominant source, correctable)

**Note**: The formula recovers full-observation as a special case:
K = C(n,2), M = n -> b₁ = C(n,2) - n + 1 = T2.

## 5. Codimension structure of constraints (Theorem T6)

### 5.1 Bulk-boundary decomposition

For crystal systems observed at finite resolution h_max:

    abs_total(h) = abs_centering + C₁/h + C₂/h² + O(1/h³)

where:
- `abs_centering` = bulk (codim 0, h-independent topological invariant)
- `C₁/h` = leading boundary term from **glide planes** (codim 1 in reciprocal space)
- `C₂/h²` = subleading term from **screw axes** (codim 2) AND **glide plane intersections**

### 5.2 Codimension determines convergence rate

Each non-symmorphic symmetry element s has a codimension:

    codim_s = 3 - dim(extinction zone of s in reciprocal space)

- Glide plane: extinction zone = plane (dim 2) → codim = 1 → O(1/h)
- Screw axis: extinction zone = line (dim 1) → codim = 2 → O(1/h²)
- Symmorphic elements: no extinction zone → delta = 0 exactly

Running alpha analysis (h_max=4..32) confirms convergence to integer codim:
- Glide-dominant: alpha_eff → 0.96-0.98 at [20-32], extrapolates to 1
- Screw-dominant: alpha_eff → 1.94-1.98 at [20-32], extrapolates to 2
- P6₁: alpha = 1.975, essentially exactly 2

### 5.3 Cross-term ratio ρ_cross

    ρ_cross = |C₂/C₁|

This quantity encodes the **entanglement** between symmetry elements:

| System | ρ_cross | Interpretation |
|---|---|---|
| P2₁/c (1 glide) | 0.48 | C₂ ≈ C₁/2, pure finite-size correction |
| Pc (1 glide) | 0.79 | Slightly higher, edge effects in triclinic |
| R-3c (R + c-glide) | 1.19 | Centering-glide entanglement amplifies C₂ |
| Pnma (n + 2₁) | 0.63 | Glide-screw interaction, moderate |
| Pn-3n (3 × n-glide) | 1.30 | Inclusion-exclusion from 3 intersecting planes |

**General rule**: ρ_cross ~ (measure of codim-2 intersections) / (measure of codim-1 zones).

For k intersecting glide planes in a cubic lattice, the inclusion-exclusion gives:

    delta ≈ k·C_plane/h - C(k,2)·C_intersection/h² + ...

### 5.4 Centering-glide orthogonality

**Leading order**: centering and non-symmorphic elements are orthogonal.
T6 decomposes abs_total = abs_centering + delta_glide, and abs_centering is
exactly 1 - 1/n regardless of glide/screw content. The leading codim (alpha → integer)
is determined purely by the non-symmorphic element type, independent of centering.

**Subleading order**: centering and non-symmorphic elements entangle.
R-3c has C₂ = -30 (vs Pc's -19.5) because R-centering's 1/3 selection interacts
with the c-glide extinction zone. This entanglement enters at the C₂ level,
not C₁. The leading-subleading hierarchy is:

    C₁: type of non-symmorphic element (codim, independent of centering)
    C₂: geometry of centering × non-symmorphic interaction (lattice-dependent)

This two-layer structure — leading orthogonal, subleading entangled — is a
concrete instance of the L0 axiom A1 (structured error decomposition).

### 5.5 FX instance of bulk-boundary decomposition (T8)

The crystal bulk-boundary structure has a direct FX translation:

    Crystal: abs(h) = abs_centering + C_1/h + C_2/h^2 + ...
    FX:      amp_FX/W = A * (cluster bulk) - B * (signal boundary) + ...

with A/B = exp(c_s^2) = sqrt(e), where c_s^2 = 1/2 is the FX centering coherence
(T1 corollary). The Boltzmann-like factor exp(-c_s^2 * codim) is the FX analogue
of the 1/h^codim decay in crystals -- in both cases, higher-codimension
contributions are suppressed by a universal factor determined by the
bulk coherence amplitude.

This establishes T6 and T8 as two faces of the same mechanism (the L0 axiom A1,
structured error decomposition), applied to discrete (crystal) and continuous
(FX) constraint algebras respectively.

**Reverse prediction (C8)**: If T8 is genuinely the continuous limit of T6, then
crystal systems should also show sqrt(e) in an appropriately defined
bulk/glide amplitude ratio. The rho_cross values (0.48, 0.79, 1.19, 0.63, 1.30)
do not directly equal sqrt(e) = 1.649, but rho_cross measures C_2/C_1 (not A/B).
The correct test is to define an FX-analogous ratio for crystals and check.
See C8 in c_theorems_master.md.

---

## 6. Number theory 拡張: Dirichlet / Artin conductor

### §6.0 動機 — conductor_count rule の数論版

`conductor_count` rule (ROUTING.yaml, bond/conductor = constraint 数) の crystal (T1, T6) と FX (T2, T5) 版が §1-5 で確立した。§6 は同じ structural template の **数論版**を追加する: Dirichlet 指標の conductor と Artin 表現の conductor は、いずれも **ramification filtration 重み付き codimension 和**として記述され、T6 の glide/screw codim 階層と **同一の constraint-counting 構造**を共有する。

これは dictionary 内で conductor 概念が `{crystal, FX, number theory}` の 3 domain で既存 entry となる最初の整理である。

### §6.1 Dirichlet conductor

**定義**: Dirichlet 指標 χ mod N に対し、**conductor** f_χ は χ が factor through する最小の正整数 m。すなわち χ が mod m の指標 χ′ から χ(n) = χ′(n mod m) で誘導される最小の m。χ が **primitive** ⟺ f_χ = N。

**例**:
- trivial χ₀ mod N: f = 1 (mod 1 指標から誘導)
- non-trivial χ mod 4 (order 2): f = 4
- order-4 χ mod 5: f = 5
- 任意 χ mod 12: f ∈ {1, 3, 4, 12} (12 の divisor で χ が factor する最小)

**ΣΦ 読み**: f_χ は **指標の最小周期** であり、χ が「動作する最小のスケール」を定める。crystal で「extinction pattern を達成する最小の space group」と同じ意味で、f_χ は「指標を定義する最小の modulus」。scalar conductor としては **scope = global** (全 mod N 指標の空間における制約位置)。

### §6.2 Artin conductor と conductor_count rule の完全同形

**一般設定**: 体の有限拡大 K/k と Galois 表現 ρ: Gal(K̄/k) → GL_n(ℂ) が与えられる。各素点 p (of k) に対し、**局所 Artin conductor 指数**:

    f_p(ρ) = Σ_{i=0}^∞ (|I_i| / |I_0|) · codim(V^{I_i})

ここで I_i は p における higher ramification subgroup (lower numbering)、V は表現空間、V^{I_i} は I_i の不動部分空間、codim は V 内の codimension。

**大域 Artin conductor** は ideal ∏_p p^{f_p(ρ)} ⊂ O_k。

**ΣΦ 読み (§6 の中心主張)**:

> f_p(ρ) = Σ_i (|I_i|/|I_0|) · codim(V^{I_i})
> は **constraint codim sum** と **完全に同形** である。

対応:

| Artin conductor | ΣΦ conductor_count (T6) |
|---|---|
| 各 ramification subgroup I_i | 各 non-symmorphic 対称要素 (glide, screw, ...) |
| codim(V^{I_i}) = I_i に「動かされる」方向数 | codim(extinction zone) = 対称要素が制約する方向数 |
| 重み \|I_i\|/\|I_0\| (wild ramification の higher order 処理) | composition law (multiplicative for centering, additive for glide) |
| 総和 f_p(ρ) = 局所制約の全 codim 計 | 総 N_constraint = 全対称要素の制約 codim 計 |

両者は **同じ constraint-counting template** を異なる domain (ramification theory vs 空間群幾何) で実装したもの。これは S8 (c_theorems_master.md) に登録される structural identity。

### §6.3 Unramified / tame / wild の階層 = T6 の codim 階層

Artin conductor 内部の ramification 階層は T6 の codim 階層と **1 対 1 対応**する:

| Ramification type | f_p(ρ) への寄与 | ΣΦ codim | crystal 類比 |
|---|---|---|---|
| unramified (I_0 自明作用) | 0 (V^{I_0} = V, codim 0) | codim 0 | symmorphic 要素 (extinction なし) |
| tamely ramified (I_0 非自明、I_1 自明) | codim(V^{I_0}) (1 項のみ) | codim ≥ 1 主 | glide 面 (1/h, codim 1) |
| wildly ramified (I_1 以降非自明) | Σ 複数項 | codim ≥ 2 主 | screw 軸 (1/h², codim 2) |

**対応の詳細**:

- **Unramified**: ρ は Frobenius のみで決まり、inertia が自明に作用する。`f_p(ρ) = 0` ⟺ 制約なし ⟺ crystal の symmorphic 対称要素に対応。
- **Tame**: 素数 p が ρ の表現空間の一部方向 (= codim(V^{I_0}) 次元) を「動かす」。重みは (|I_0|/|I_0|)=1 で単一項。これが T6 の「codim 1 主」と同じ「1 次構造」。
- **Wild**: I_1, I_2, ... が追加に寄与。higher filtration が重みを膨らませ、T6 の「codim 2 以上」の高次補正と対応。

この対応は **表層的類推ではなく構造的同一性**: 両方とも「対称性の filtration に沿って codimension を積算する」という同じ algorithm を実装する。

### §6.4 Functional equation と √|d_K| の Artin conductor 再解釈

完備化 L-function Λ(s, ρ) の functional equation:

    Λ(s, ρ) = N(ρ)^{s/2} · Γ_∞(s, ρ) · L(s, ρ)
    Λ(s, ρ) = ε(ρ) · Λ(1-s, ρ̄)

ここで **N(ρ) = 大域 Artin conductor の絶対ノルム** (k = ℚ の場合はそのまま整数)。ε(ρ) は符号因子。

**c_spectral.md §8 との接続**:

ρ = trivial 1-次元表現 (= Dedekind ζ_K の場合) では:

    N(trivial) = |d_K|   (数体 K の絶対 discriminant)

つまり **`√|d_K|` (c_spectral.md §8.3 の 6-gauge 分解の {mult, anal} 因子) は「自明表現の Artin conductor の平方根」である**。

一般の Artin L(s, ρ) では:
- √|d_K| が √N(ρ) に一般化される
- Class number formula の 6-gauge 分解の {mult, anal} 因子は **conductor 因子**として統一表示される

これにより **c_spectral.md §8.3 の {mult, anal} 署名の「素」は nt_conductor.md §6 で名指される** — c_spectral.md は「discriminant」と書き、nt_conductor.md は「Artin conductor of trivial char」と書く。両者は同じ object だが dictionary 的 residence は nt_conductor.md (T6 の自然な拡張として)。

### §6.5 Stark rank 1 の e_χ は conductor の下流

research/stark_projection_v0.md §2.2 の rank-1 abelian Stark:

    L'(0, χ) = -(1/e_χ) · Σ_{σ ∈ Gal(K/k)} χ(σ⁻¹) · log |σ(ε_χ)|

の正規化因子 `e_χ` は、**conductor から派生する downstream invariant**:

```
χ (Dirichlet or Artin character)
  ↓ [§6.1-6.2] conductor f_χ を持つ
K(χ) ⊆ ℚ(ζ_{f_χ})    (Kronecker-Weber: Dirichlet 指標は cyclotomic 拡大で実現)
  ↓ [Galois 対応] χ の kernel の固定体
w_{K(χ)} = |μ(K(χ))|   (H-stark-4 territory, c_spectral.md §8.3 の w_K)
  ↓ [Stark 正規化]
e_χ = w_{K(χ)}
```

**帰結**: Stark 公式の 3 つの非自明構造要素 {χ, ε_χ, e_χ} のうち **χ と e_χ は両方とも nt_conductor.md §6 に住む** (χ は §6.1-6.2 で直接定義、e_χ は §6.5 で導出)。残る ε_χ (Stark 単元) のみが **L2 数論辞書**側の未作成 entry (G4)。

これで nt_conductor.md は research/stark_projection_v0.md の rank-1 Stark 表示に **2/3 の構成要素** を供給する primary L1 entry となる。

### §6.6 Scope と非包含項目

**§6 が提供するもの**:
- Dirichlet conductor と Artin conductor の name-only 定義
- `conductor_count` rule の数論版 (§6.2 の formula-level 同形)
- unramified/tame/wild の ΣΦ codim 階層対応 (§6.3)
- √|d_K| の conductor 再解釈 (§6.4, c_spectral.md §8 との bridge)
- Stark e_χ の upstream 定位 (§6.5)

**§6 が提供しないもの** (scope 外):
- Artin conductor の具体計算 (個別表現に対する詳細は標準文献参照)
- 非 abelian Galois 表現の conductor (Langlands 対応領域、辞書 scope 外)
- local Langlands の epsilon factor ε(ρ) の詳細 (§6.4 で name のみ)
- p-adic Artin conductor / Swan conductor の分離 (p-adic gauge 未導入、OQ 候補)

§6 は **name-only + structural bridge** 層である。本体的拡張が必要になった段階で §6.7 以降に具体例を追加する。

### §6.7 検証スクリプト

- (未実装) `dirichlet_conductor_verify.py`: 小さな mod で χ の conductor を手計算と照合 (mod 12 の 4 指標、mod 15 の 8 指標など)
- (未実装) `artin_trivial_char_disc_verify.py`: ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5) で自明表現の Artin conductor = |d_K| を直接確認 (c_spectral.md §8.5 の 5 ケースと整合)
- §6.2 の structural identity は closed-form proof、script 不要

### §6.8 他辞書との接続

- **c_spectral.md §8** (class number formula): √|d_K| = Artin conductor of trivial char. §6.4 で明示。
- **c_phase_complex.md §4** (ℂ での L-function 合流): Dirichlet 指標が住む場所、§6.1 の上流。
- **identity_asymmetry.md §3.4** (L(χ₀) pole): 自明指標 ⟺ conductor f=1 ⟺ unramified. §6.3 の最小ケース。
- **omega/Paper_Omega_Origination.md §2.5** (L関数型 signature): Catalan G = L(2, χ₄) の conductor は 4; L関数型 signature 署名の例は §6.1 の primitive character で parameterize される。
- **research/stark_projection_v0.md §2.2, H-stark-3**: §6.5 経由で e_χ を供給。
- **nt_relative_units.md**: §6.9 の relative regulator が nt_relative_units.md §3 と双方向接続。
- **nt_frobenius_schur.md**: §6.9.4 の pairing type が nt_frobenius_schur.md §3 と接続。

### §6.9 Artin L-function の Induction / Restriction / Brauer 分解

#### §6.9.0 動機

§6.2 は Artin conductor を **定義**した。本 §6.9 は Artin L-function を **分解する** 道具立てを辞書化する。OQ-NT-7/8 の Tier 分類理論は「どの intermediate field で L-function が落ちるか」を核としており、その文法が **induction (Ind)** と **Brauer 分解**。number_theory_dictionary_v0.md §5.3.14 で $S_3$ ケースに使われ、research/brauer_closure_galois_classification_v0.md §11-12 で $A_4, D_4$ に拡張済だが、L1 辞書に住処がなかった。

#### §6.9.1 Induction と Restriction

**Setting**: $H \leq G$ は部分群、$\rho : G \to GL(V)$ は $G$ の表現、$\sigma : H \to GL(W)$ は $H$ の表現。

**Restriction** $\mathrm{Res}^G_H \rho$: $\rho$ を $H$ に制限。$V$ は同じだが $G$-作用を $H$-作用に縮小。

**Induction** $\mathrm{Ind}^G_H \sigma$: $W$ から $G$-表現を構成。$\dim(\mathrm{Ind}^G_H \sigma) = [G:H] \cdot \dim \sigma$。

**Frobenius 相互律** (名前 duality):

$$\langle \mathrm{Ind}^G_H \sigma, \rho \rangle_G = \langle \sigma, \mathrm{Res}^G_H \rho \rangle_H$$

**Artin L-function への帰結**:

$$L(s, \mathrm{Ind}^G_H \sigma) = L(s, \sigma)$$

(Artin の induction invariance)。つまり **大きな群 $G$ の表現としての L-function は、小さな群 $H$ の表現としての L-function と等しい**。

#### §6.9.2 Brauer 分解定理

**Brauer の定理**: 任意の $G$ の character $\chi$ は、$G$ の **elementary subgroups** (= cyclic × $p$-group) $H_i$ 上の **1 次元** characters $\sigma_i$ の induced characters の $\mathbb{Z}$-linear combination で書ける:

$$\chi = \sum_i n_i \cdot \mathrm{Ind}^G_{H_i} \sigma_i, \quad n_i \in \mathbb{Z}$$

**L-function への帰結**:

$$L(s, \chi) = \prod_i L(s, \sigma_i)^{n_i}$$

右辺は Hecke L-functions (1 次元 character の L-function) の有理的べき乗積。**全ての Artin L-function は Hecke L-function の比 (有理的積) で書ける**。

#### §6.9.3 Tier 理論との接続 — 具体例

§6.2 の Artin conductor + 本 §6.9 の induction/Brauer 分解で、OQ-NT-7 の Tier 分類が L1 語彙で記述可能になる。

**Tier 1 (strict closure)**:

$$L(s, \rho) = \frac{\zeta_F(s)}{\zeta_{\mathbb{Q}}(s)} \quad \text{(単一中間体 } F = H^{\ker\rho}\text{ で完結)}$$

例: $S_3$ の $\rho_2$ → $L(s, \rho_2) = \zeta_{\mathbb{Q}(\alpha)} / \zeta_{\mathbb{Q}}$ (number_theory_dictionary_v0.md §5.3.14.2)

**Tier 2 (relaxed closure)**:

$$L(s, \rho) = \frac{\zeta_{F_1}(s)}{\zeta_{F_2}(s)} \quad \text{(2 つの中間体の比)}$$

**必要十分条件**: $\exists$ subgroups $H_1 \subsetneq H_2 \leq G$ s.t. $\langle \rho|_{H_1}, \mathbf{1}\rangle - \langle \rho|_{H_2}, \mathbf{1}\rangle = 1$ and $\forall \psi \neq \rho$: $\langle \psi|_{H_1}, \mathbf{1}\rangle = \langle \psi|_{H_2}, \mathbf{1}\rangle$. (Frobenius 相互律で $\zeta_{F_1}/\zeta_{F_2}$ の irrep 寄与を計算すると、$\rho$ のみ指数 1 で残り全消去。)

例: $D_4$ の 2-dim irrep → $L(s, \rho) = \zeta_{F_1} / \zeta_{F_2}$, $F_2 \neq \mathbb{Q}$ (research/brauer_closure_galois_classification_v0.md §12)

**Tier √ (impossible closure)**:

$$L(s, \rho)^2 = \frac{\zeta_{F_1}(s)}{\zeta_{F_2}(s)} \quad \text{(べき乗が必要、} L \text{ 自体は整数べきでは捕獲不可)}$$

例: $Q_8$ の 2-dim irrep → $L(s, \rho)^2 = \zeta_{F_1} / \zeta_{\mathbb{Q}}$ (research/brauer_closure_failure_taxonomy_v0.md)

**Tier 分類は induction/Brauer の具体形に還元される**: $\rho$ が $\zeta$ 比で何乗まで捕獲可能かが tier を決める。

#### §6.9.4 Isotypic projection $e_\chi$ (名前定義)

$G/N$ ($N \trianglelefteq G$) の character $\chi$ に対し、群環 $\mathbb{C}[G/N]$ 内の **isotypic idempotent**:

$$e_\chi = \frac{\dim \chi}{|G/N|} \sum_{\sigma \in G/N} \chi^{-1}(\sigma) \cdot \sigma$$

性質:
- $e_\chi^2 = e_\chi$ (idempotent)
- $e_\chi \cdot e_\psi = 0$ ($\chi \neq \psi$ のとき直交)
- $\sum_\chi e_\chi = 1$ (完全分解)
- $e_\chi \cdot V = V_\chi$ ($V$ の $\chi$-isotypic component を切り出す)

**nt_relative_units.md §4.3 との接続**: Stark unit の $\chi$-成分は $e_\chi \cdot \lambda(\varepsilon)$ で抽出される。number_theory_dictionary_v0.md §5.3.7 の計算 $P_\chi(v(\alpha))_0 = 0.2812$ は $e_\chi$ の具体的適用。

**Tier 2 での使い方**: $e_{\chi_0}$ (trivial idempotent) で射影した成分 = $O_{F_2}^\times \otimes \mathbb{Q}$ (nt_relative_units.md §4.2)。sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ は $(1 - e_{\chi_0})$ で切り出される complementary space。

#### §6.9.5 §6.9 の scope

**提供するもの**:
- Induction / Restriction の name-only 定義と Frobenius 相互律 (§6.9.1)
- Brauer 分解定理 (§6.9.2)
- Tier 理論への具体的接続 (§6.9.3)
- Isotypic idempotent $e_\chi$ の定義 (§6.9.4)

**提供しないもの** (scope 外):
- Brauer 分解の constructive algorithm (elementary subgroup の具体的構成)
- Mackey の公式 / double coset decomposition
- Artin holomorphy 予想 (OQ-NT-3)
- Modular representation theory ($\mathrm{char}(k) | |G|$)

### §6.10 NT carry conductor (OQ-P2-1, Paper N2 §2)

#### §6.10.0 動機

§6.1 (Dirichlet conductor) と §6.2 (Artin conductor) は **L 関数側** の conductor を定義した。本 §6.10 は Paper 2 の **carry rate** という別側面で生じる **arithmetic combinatorial conductor** を辞書化する。これは OQ-P2-1 (RESOLVED 2026-04-22, `research/oq_p2_1_carry_closed_form.md`) で得られた閉形式の conductor 構造であり、Paper N2 (`papers/publication/nt/N2_paper2_structural_ja.md` §2) の主結果 M1 として展開された。

#### §6.10.1 Carry rate と admissible set

**Setting**: $X \geq 2$, $Y \geq 1$, $L = XY$, $\gcd(M, L) = 1$, prime gap $g \geq 2$。Paper 2 の核心写像 $u(n) = M \cdot x + y \pmod{L}$ における **carry 率** $c(g, X)$ は、prime pair $(p, p+g)$ の residue 対が境界 $X$ を跨ぐ漸近確率。

**Admissible set**:

$$
S_g(X) := \{a \in \mathbb{Z}/X\mathbb{Z} : \gcd(a, X) = \gcd(a + g, X) = 1\}
$$

これは $(p \bmod X, (p+g) \bmod X)$ の Hardy-Littlewood 一様分布における support。

#### §6.10.2 Closed form (OQ-P2-1 RESOLVED)

**Theorem (carry rate closed form, OQ-P2-1 RESOLVED 2026-04-22)**:

$$
c(g, X) \;=\; \frac{N_g(X)}{|S_g(X)|}
$$

ここで $|S_g(X)|$ は X を割る素数上の **有限 Euler 積**:

$$
|S_g(X)| \;=\; X \prod_{p \mid X}\!\Bigl(1 - \frac{\nu_g(p)}{p}\Bigr),
\qquad
\nu_g(p) \;=\;
\begin{cases}
2 & p \nmid g \\
1 & p \mid g
\end{cases}
$$

$N_g(X)$ は短 finite sum ($r = g \bmod X$):

$$
N_g(X) \;=\; \#\{b \in \{1, \ldots, r-1\} : \gcd(b, X) = 1, \gcd(r-b, X) = 1\}
$$

$c(g, X)$ は $g$ に対して $r = g \bmod X$ と $X$ の各素因子に対する $g$ の整除性のみに依存する。

#### §6.10.3 Conductor 次元 = $\omega(X)$

**主張 (NT carry conductor の dimension)**:

$$
\dim(\text{conductor}_\text{carry}) \;=\; \omega(X)
$$

ここで $\omega(X)$ = $X$ の異なる素因子の個数。

**根拠**: $c(g, X)$ は 2 つの scope-distinct constraint
- (a) starting residue $x_1 = p \bmod X$ の $X$-coprimality
- (b) shifted residue $x_1 + r$ の $X$-coprimality

に依存する。両者は同じ scope ($\mathbb{Z}/X\mathbb{Z}$) 上の異なる位置における制約で **jointly factorizable でない** (従来「次元 2」と推測されていた)。

しかし $|S_g(X)|$ の Euler 積分解 $\prod_{p \mid X}$ は **conductor を 1 prime ずつの constraint の積として表す** ため、effective conductor 次元は $\omega(X)$。具体例: $X = 396 = 2^2 \cdot 3^2 \cdot 11$ で $\omega(X) = 3$、Euler 積は 3 因子。

**Paper 2 §C.2 訂正**: Paper 2 §C.2 の「carry 率に解析的公式がある（→ $\varphi(X)$ の residue 構造に依存し、closed form は未導出）」は本 §6.10.2 の閉形式により訂正される。conductor 次元は $\omega(X)$ であって 2 ではない。

#### §6.10.4 Zero-carry の代数的説明 (Paper 2 Remark 2.5)

$c(g, X) = 0 \iff N_g(X) = 0$。$X = 396$ では $g = 4, 16$ で該当 (全 $b \in [1, r-1]$ で $\gcd(b, 396) > 1$ または $\gcd(r-b, 396) > 1$)。これらは閉形式の **代数的帰結** であり、経験的偶然ではない。

#### §6.10.5 Paper N1 / N2 framework での位置付け

**T-AAS instance** (Paper N1 §5.2, Paper N2 §2.5): NT carry conductor は T-AAS の clean instance を与える:
- **f_torsion = 0**: 閉形式が Q-gauge 経由で構造的に消える
- **f_rational = $\omega(X)$**: gauge invariant conductor (X-dependent)

**S15 Structural 層** (Paper N1 §3.3): $\omega(X)$, $|S_g(X)|$, $N_g(X)$ の 3 観測量はいずれも parameter-free integer invariant として Structural 層に住む。

**Arrow 1 instance** (Paper N1 §4.1): Paper 2 観測対象 $F_{g,k}(s)$ の input spec のうち X 軸 (gauge $L = XY$ の周期) が Structural observable $\omega(X)$ を encode。$c(g, X)$ closed form は Arrow 1 mapping の **代数的閉鎖** の数論的 instance。

**Observation-optimal gauge theorem instance** (`c_observation_optimal_gauge.md §5 Path 3`): Paper 2 carry split (Information balance $X = 6$ vs Structural balance $\{X = 2g\}$ locus) の Structural balance 側は **carry conductor の Euler product structure** に直接依存する。詳細は §c_observation_optimal_gauge.md §5.5 + Paper N2 §6.3 を参照。

#### §6.10.6 Dirichlet / Artin conductor との対比

NT carry conductor は §6.1 / §6.2 の Dirichlet / Artin conductor と **異なる起源** で発生する:

| 種類 | 起源 | Conductor 次元 | 主応用 |
|---|---|---|---|
| **Dirichlet conductor** ($f_\chi$, §6.1) | 指標の最小周期 | 1 (各 $\chi$ で integer) | $L(s, \chi)$ functional eq |
| **Artin conductor** ($f_p(\rho)$, §6.2) | Galois rep の ramification filtration | $\Sigma$ codim · weight (T6 同型) | $L(s, \rho)$ functional eq |
| **NT carry conductor** ($\omega(X)$, §6.10) | Combinatorial admissible set $S_g(X)$ | $\omega(X)$ (X 素因子個数) | Paper 2 carry rate, OQ-P2-1 RESOLVED |

3 conductor は **L 関数解析側 (§6.1/§6.2) vs combinatorial 側 (§6.10)** の 2 極を form し、本辞書 entry が NT 観測量の conductor 概念を拡張する。

#### §6.10.7 Scope と検証

**提供するもの**:
- Carry rate $c(g, X)$ の closed form definition (§6.10.2)
- Conductor 次元 $\omega(X)$ の同定 (§6.10.3)
- Paper 2 §C.2 訂正 (Paper N2 §2.5 transfer)
- Paper N1/N2 framework での position (§6.10.5)
- Dirichlet / Artin conductor との対比 (§6.10.6)

**提供しないもの** (scope 外、Paper N2 §2-§3 で展開):
- Carry rate の数値検証データ (Paper N2 §2.3 + `experiments/core/oq_p2_1_carry_closed_form.py`)
- D_floor 放物型公式 + RH 翻訳 (Paper N2 §3 / `c_recursive_floor_principle.md §6.8` D_floor universality row)
- $\gamma_1$ dip detection (Paper N2 §3.5)

**Status**: ESTABLISHED 2026-04-22 (OQ-P2-1 RESOLVED, 30+ 設定で empirical 一致 $|d| < 1.5$pp)、本 §6.10 は Paper N2 v0.2 (2026-04-26) の dictionary residence。

**Ref**:
- `research/oq_p2_1_carry_closed_form.md` (OQ-P2-1 RESOLVED 主体)
- `papers/publication/nt/N2_paper2_structural_ja.md` §2 (Paper N2 main result M1)
- `papers/publication/nt/N1_observation_theory_nt_ja.md` §3.3, §4.1, §5.2 (framework header positions)
- `c_observation_optimal_gauge.md §5.5` (Path 3 arithmetic mod-n clause expansion, Paper N2 §6.3 transfer)
