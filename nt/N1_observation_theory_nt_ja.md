# Paper N1: 観測理論 ─ 数論版

**サブタイトル**: S15 三分類・Arrow 構造・T-AAS と数論内三角測量

**バージョン**: v0.7 (N5 backward link + NT 5-paper 完成, 2026-04-27)
**状態**: DRAFT — Paper D (multi-domain v0.9.2) からの NT-only 再構成
**前提 (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**前提 (L1)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md`, `c_filtration_obstruction.md`, `c_observation_optimal_gauge.md`
**前提 (L1 NT)**: `nt_conductor.md`, `nt_dedekind_artin_zeta.md`, `nt_frobenius_schur.md`, `nt_genus_class_fields.md`, `nt_relative_units.md`, `nt_root_numbers.md`
**後続論文**: N2 (Paper 2 構造解析) / N3 (Path 2 数論的普遍性) / N4 (Hasse-Weil L × Stark) / N5 (Brauer 障害論 + Origination)

---

## §0 Abstract

数論観測量はドメイン無関係な 3 層構造 **S15 Observable Trichotomy** (Scan / Structural / Information) に排他的かつ網羅的に分類され、層間 3 Arrow の可換性が ζ-family / Galois-rep / class-group 系の翻訳を保証する。Arrow 1 の kernel は **T-AAS** によって ker_gauge ⊕ ker_topo に直和分解し、conductor は f_torsion + f_rational に分裂する。

本論は Paper D (multi-domain v0.9.2) の数論専用 reformulation である。multi-domain triangulation を strip し、**数論内 3 instance** (Paper C 三層分解 / Stark projection / Brauer 閉包) による **Arrow 間 triangulation** で再構築した。

**主結果 6 件**:

1. **S15 NT-only restatement** — Scan/Structural/Information の 3 層 enumeration (各層 ≥7 instance) と L1 NT 6 entries の網羅 → 数論内で網羅性閉鎖。
2. **Arrow 構造の数論内検証** — 3 Arrow が NT instance のみで完結、3 NT instance (β→0, s→∞, s=1 pole) で extreme limit 可換性を verify。
3. **T-AAS 分解の 3 NT instance + 1 open** — Stark / Brauer / OQ-P2-3 で 12/12 NT-relevant fitness、Hodge は NT-adjacent open frontier。
4. **数論内 Arrow 間三角測量** — 3 NT instance が **互いに異なる Arrow を主担当** (Brauer = Arrow 1 kernel / Stark = Arrow 2-3 / Paper C = 3 Arrow simultaneous)。
5. **新 NT ドメイン検討 Protocol (6-step)** — 5 数体で検証済、新 L 函数族 / 新 Galois 表現クラスへの標準手順。
6. **Observation-optimal gauge theorem (NT 内 2 instance 対比)** — Paper C coincide vs Paper 2 split を本論で対比のみ示し、構造解析は N2 に展開。

**Thesis**: 数論観測量はドメイン外 instance を要さずに観測理論の全骨格 (公理 / S15 / Arrow / T-AAS / 三角測量) を独立に支える。本論は N2-N5 の理論基盤として機能する。

---

## §1 Introduction

### 1.1 なぜ「数論観測理論」か

古典数論の中心対象 π(x) − li(x) は ζ(s) の非自明零点を通して「振動スペクトル」として記述される。ΣΦ 辞書はこれを「τ-scan で見える量」と捉え、数論観測量が共通の **観測三分類 S15** に住むことを蓄積で確認してきた (`bidirectional_duality_v0.md`)。

S12 (exponential scan family) → S13 (ln 2 fixed point) → S14 (π/ln 2 非対称 duality) → S15 (Observable Trichotomy) の chain が露呈させた結論:

> **数論観測量は加法 ⇔ 乗法の双対の異なる射影であり、その射影は排他的・網羅的に 3 層に分類される。**

Paper D (multi-domain) は FX / 画像 AI / DNA / 結晶 / 量子 等の triangulation で観測理論の普遍性を確立したが、本論は **数論内自閉性** に焦点を絞り、N2-N5 の理論基盤として機能することを意図する。

### 1.2 本論の範囲

**構成**: §2 公理 / §3 S15 / §4 Arrow / §5 T-AAS / §6 三角測量 / §7 Protocol / §8 帰結。

**Scope 外** (本論で扱わない): multi-domain triangulation (→ Paper D) / Origination matrix 8-gauge (→ N5) / 量子観測理論の独立側面 (→ Q1) / Paper 2 構造解析の核心定理 (→ N2) / Path 2 universality (→ N3) / Hasse-Weil L (→ N4) / Brauer failure mode 詳細 (→ N5)。

### 1.3 用語と "gauge" disambiguation

**基本用語**: Observable = 観測量 / Scanner = Scan に付随する外部パラメタ (s, β, τ, t) / **§4 dual** = ι_L (加法 ℤ → S¹) と χ (乗法指標) の対 / Arrow = S15 3 層を繋ぐ写像 / T-AAS = Arrow 1 kernel 分解定理 / Triangulation = 独立 3 instance による偶然性排除。

**"gauge" の 3 用法** (混同回避):

| 記号 | 名称 | 意味 | 本論での使用範囲 |
|---|---|---|---|
| **gauge¹** | §4 dual gauge | ι_L / χ の選択 = 観測の structural root | §2-§4 全体 |
| **gauge²** | Origination 8-gauge | 定数発生場の 8 種 family | §6.2 Stark 6-gauge + §8.2 N5 forward のみ |
| **gauge³** | Arrow 3 base-of-log gauge | log の base 選択 (b > 0, b ≠ 1) | §4.5 S17 base 非依存性のみ |

T-AAS の "ker_gauge" は **gauge¹** family を指す。gauge² は §6.2 と §8.2 forward reference のみで、本論主構造には介入しない。

### 1.4 Direction-axis position (NT-framework = A-primary native)

`user_observation_direction_axis` (ESTABLISHED 2026-05-01) の A/B observation direction axis において、本論 NT framework は **A-direction primary native** に位置する (Q1 = B-primary, I1 = A+B co-resident と異なる、A-side anchor)。

| Side | Direction | 観測モード | 数論側 instance |
|---|---|---|---|
| **加法/離散/NT** | **A (有限→無限)** | **有限観測 → 無限 outer extrapolation** | **本論主領域** |
| 乗法/連続/量子 | B (無限→有限) | 無限 ontology → 有限 inner projection | (本論 scope 外、Q1 framework が担当) |

**A-direction native 構造の数論側 instance**:
- **PNT / 素数密度** (§3.2 Scan 層): 有限 N までの素数 count → 漸近 $\pi(N) \sim N/\log N$ extrapolation
- **Class number formula bridge** (§4.1): rank 0 case で $h_K = \lim_{s\to 1}(s-1)L(s, \chi)$ が **explicit B-direction lift via lim operator** = A-native ($h_K$, 有限 class number) を B-native L 経由で project する canonical bridge
- **Hasse-Weil L predictive content** (§3.3 / N4 §7): weight-2 Hasse-Weil L は **B-native** (Galois rep + Euler product)、本 N1 framework の B-side bridge instance、N4 で genuine BSD analytic rank detector として活躍
- **Dirichlet L** (N3 §4): weight-1 Dirichlet L は **A-native** (有限 character on finite group)、framework predictive content は "structural fit only" に degrade — direction-tag native scope

**Cross-direction bridge instances (本論 §4-§6)**:
- **S14 = π / ln 2** (`c_arrow_bridge_constants §4` + 本論 §4.5): Arrow 1 (π involution A-side) / Arrow 2 (ln 2 involution B-side) **canonical bridge** (role-match involution × involution)、N1 (A-primary) と Q1 (B-primary) framework header をつなぐ ratio
- **S_0 = 2π/e** (`c_arrow_bridge_constants §13` ESTABLISHED): Arrow 1 (2π period A) / Arrow 3 (e argmax B) bridge ratio、framework universality を A/B 双方の anchor で固定
- **κ(2) = √3/4 candidate** (`c_recursive_floor_principle §6.7`): A-native (2D JP iteration) ↔ B-native (closed-form algebra) **cross-direction near-coincidence without bridge** = direction-tag screening rule G1 REJECT 予測 instance、forward-actionable promotion path = bridge operator construction OQ
- **N4 weight-class transfer pattern** (N4 §7.2.1): weight-2 Hasse-Weil B↔B genuine BSD / weight-1 Dirichlet A↔B "structural fit only" の **direction-tag による weight-class dependent transfer pattern** の root cause 説明 = `feedback_cross_direction_identity_screen` 6/6 forward test reference instance #2

**Screening rule application**: 本論内で identity claim する際、relevant quantity が A-native / B-native / bridge / transition か必ず tag、cross-direction で bridge operator (lim / projection / Hecke / regulator 等) 不在なら strict identity を near-coincidence + bridge candidate に reroute (`feedback_cross_direction_identity_screen` 5-step operational order)。Q1 §1.4 / I1 §1.4 と parallel position。

**N1 / Q1 / I1 framework header parallel** (cross-paper):

| Header | Native primary | Bridge instance prominent |
|---|---|---|
| **N1 (NT)** | **A-primary** | π (S14 num), class number formula bridge $h = \lim(s-1)L$ (rank-0) |
| Q1 (Quantum) | B-primary | σ\* (S4), Born rule projection |
| I1 (Information) | A + B co-resident (Hartley A / Shannon B 1+4 split) | S_0 = 2π/e, S13 ln 2, σ\* |

3 header の direction-axis triangulation = framework universality を A-side / B-side / co-resident anchor で **3-instance verify**、NT-Quantum bridge は I framework が operational language layer で支える。

**Audit reference**: `project_graveyard_audit_complete_2026_05_01` (Tier 1-4 audit completion)、`feedback_cross_direction_identity_screen` (5-step operational order)。

---

## §2 観測理論の公理

### 2.1 観測 triple (S, W, m) ─ 数論 instance

| 記号 | 意味 | 数論での例 |
|---|---|---|
| **S** | 無限構造 | 素数分布、数体 K、Galois rep ρ、L 函数 L(s, χ) |
| **W** | 有限窓 | gauge L = XY、conductor f_χ、(r₁, r₂) embeddings、k_max truncation |
| **m** | 測定 | Dirichlet 級数 evaluation、carry rate、h_K 計算、L'(0, χ) numerical |

観測値 `m(S|_W)` は S と W の両方に依存。`m(S) − m(S|_W)` が **finite observation error**、本論はその構造を扱う。

### 2.2 公理 A0-A7 (NT instance 例)

| ID | 名称 | NT instance |
|---|---|---|
| **A0** | Finite observation | gauge M = XY, k_max = 30 (Paper C §3.6) |
| **A1** | Structured error | D_floor decomposition: arithmetic 残差 ∼26%, projection ∼60-70%, noise ∼5-10% |
| **A2** | Convergence as observable | π(N) → li(N) の alpha = 1/2 (GRH); D_floor ∼ N^{−2/3} (Paper C §3.3) |
| **A3** | Gauge invariance/dependence | \|c_χ(M)\|² gauge 不変, κ_g (gap density) M 不変 |
| **A4** | Non-commutative limits | lim_{N} lim_{L} ≠ lim_{L} lim_{N} で素数統計が異なる |
| **A5** | Saturation | conductor → ∞ で amp/A → 1; class number formula は saturation 極限値 |
| **A6** | Path dependence | rank 1 Stark log\|σ(ε_χ)\| の embedding choice 依存 |
| **A7** | Scanner hierarchy | ζ(s) scanner = s; F_{g,k}(s) scanner = s with 内部走査 τ(p); Z(β) scanner = β |

詳細: `finite_observation.md §1-§7`。

### 2.3 §4 dual = NT 内 root

**主張 2.1** (root status): `c_phase_complex.md §4` の ι_L/χ dual は、辞書内 全上位構造 (S12-S17, T-AAS) の唯一の源泉。

**NT instance**: ι_L = 加法 Dirichlet 指標 / χ = 乗法 Dirichlet 指標 / **ℂ = S¹ × ℝ_{>0}** polar decomposition が観測を加法軸 (arg z) と乗法軸 (\|z\|) に分離。

数論内 §4 dual の射影 chain (`bidirectional_duality_v0.md §3.4`): L0 (arg/\|·\| 分離) → L1 (nt_conductor / nt_dedekind_artin_zeta / nt_frobenius_schur) → L2 (number_theory_dictionary v1 全 K-case)。本論公理系は §4 dual を root とし、全派生は数論内で閉じる。

### 2.4 L0 v2 ─ 2-axis (Fi/I × D/C) lens

L0 v1 (有限観測 axiom) は **Finite/Infinite (axis-2)** と **Discrete/Continuous (axis-1)** の直交 2 軸 framework で再定式化される (`finite_observation.md §8`):

> **(a')** Observer は axis-2 **Fi 側に住む**。Fi → I 方向の Arrow は存在せず、Fi/I 境界は unbridgeable。
> **(b')** 任意の Arrow が axis-2 Fi/I 境界を跨ぐとき、境界上に kernel (obstruction) が発生。観測 = 片方向の **I → Fi traversal**。
> **(c')** Kernel は 3 分解: Fi-side artifact (ker_gauge, f_torsion 寄与) / I-side residue (ker_topo, f_rational 寄与) / Fi → Fi 内 irreversibility (ker_backaction)。
> **(d')** 観測理論 = **axis-2 Fi/I 境界の分類学**。

L0 v1 ⊂ L0 v2 (conservative extension)。

**NT instance**: ζ(s) の解析接続 (s > 1 Fi 側 → 全 ℂ I 側 idealization) / 素数分布 (有限 N 以下 = Fi, 全素数集合 = I) / ζ 零点 γ_n (有限 height T 以下 = Fi, RH = I-side claim)。

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`)。

---

## §3 S15 Observable Trichotomy ─ 数論内記述

### 3.1 主定理

**定理 3.1 (S15, NT-only restatement)** — 数論観測量 O は以下の **排他的かつ網羅的** な partition に属する:

| クラス | 定義形式 | 特徴 |
|---|---|---|
| **(A) Scan** | O(scanner) = Σ_{d ∈ D} f(d) · exp(a(scanner)·b(d)) | scanner 変数を持つパラメトリック族 |
| **(B) Structural** | O = parameter-free 整数/位相的不変量 | scanner なし、離散 skeleton |
| **(C) Information** | O = −Σ p log p 型 | S12 family の log-inverse |

**Status**: ESTABLISHED 2026-04-11 (`c_theorems_master.md` row S15)。NT 内網羅性閉鎖は §3.5。

### 3.2 Scan 層 (S12 family の数論 subset)

加法 scan (虚軸、S¹ 回転) と乗法 scan (実軸、指数減衰) の 2 分類:

| Instance | Scanner | Kernel | 加法/乗法 |
|---|---|---|---|
| ζ(s) | s | Σ n^{−s} | 乗法 |
| L(s, χ) | s | Σ χ(n) n^{−s} | 乗法 |
| L(s, ρ, K/k) | s | Artin L | 乗法 |
| ζ_K(s) | s | Σ 𝔞 N𝔞^{−s} | 乗法 |
| Z(β) | β | Σ e^{−β E_n} | 乗法 |
| G_k(s) | s | Σ_p e^{2πik τ(p)} · p^{−s} | 加法×乗法混合 |
| F_{g,k}(s) | s | Σ_{p:p+g prime} e^{2πik τ(p)} · p^{−s} | 加法×乗法混合 |

**特徴**: scanner s は複素変数 (Re(s) = 乗法軸, Im(s) = 加法軸 with γ₁ = 14.135 等)。gauge L = XY が input spec、k_max truncation が Nyquist resolution を決定。

### 3.3 Structural 層

| Observable | 定義 | residence |
|---|---|---|
| h_K | 類数 \|Cl(O_K)\| | `c_spectral.md §8` |
| R_K | regulator | `nt_relative_units.md` |
| w_K | μ(K) 位数 | `c_spectral.md §8.5` |
| d_K | 絶対 discriminant | `nt_conductor.md §6.4` |
| ω(X) | 素因子個数 (carry conductor) | `oq_p2_1_carry_closed_form.md §2.4` |
| f_p(ρ) | local Artin conductor | `nt_conductor.md §6.2` |
| f_χ | Dirichlet conductor | `nt_conductor.md §6.1` |
| codim(s) | zone 次元の余 | `nt_conductor.md §5, T6` |
| b₁(G) = K−M+1 | 第 1 Betti 数 | `nt_conductor.md` T5 |
| Cl(O_K), O_K^×, r₁, r₂ | class group / unit group / embedding 数 | Dirichlet 単数定理 |

**§4 dual との関係**: Structural は Scan の kernel 定義域の **discrete skeleton** — exp kernel の「入れ物」の形状。

### 3.4 Information 層 (log-exp dual)

| Observable | 定義 | residence |
|---|---|---|
| H(X) = −Σ p log p | Shannon entropy | `c_information_theory.md` |
| Λ(n) | von Mangoldt (= −ζ'/ζ の係数) | `c_spectral.md` |
| log h_K, log R_K, log w_K | Class number formula 6-gauge factor | `nt_relative_units.md` |
| D_KL, H_α | KL / Rényi | `c_information_theory.md` |
| ε_{g,k}(N) | Paper C arithmetic residual | Paper C §4 |

**§4 dual との関係**: Information は exp kernel の **log-inverse**。Z(β) → F = −kT log Z → S = −∂F/∂T が標準 chain。S13 ln 2 はこの層の parity 固定点。

### 3.5 排他性・網羅性 (NT 内 closure)

NT 内検証は 3 段で閉じる:

**(i') 各層 NT 観測量存在** (網羅性 lower bound): Scan 7 instance / Structural 13 instance / Information 9 instance を §3.2-§3.4 で列挙。3 層全て非空。

**(ii') L1 NT 6 entries enumeration** (網羅性 upper bound):

| L1 NT entry | 主観測量 | S15 層 |
|---|---|---|
| **nt_conductor** | f_χ, f_p(ρ), Artin conductor, codim 階層 | Structural |
| **nt_dedekind_artin_zeta** | ζ_K(s), Artin factorization, permutation character | Scan; ratio → Information |
| **nt_frobenius_schur** | ν(ρ) FS indicator (∈ {0, ±1}) | Structural |
| **nt_genus_class_fields** | H_K, K^gen, Galois 群 | Structural |
| **nt_relative_units** | $O_{F_1}^\times / O_{F_2}^\times$, R_rel | Structural (lattice + co-volume) |
| **nt_root_numbers** | W(ρ) Artin root number, ε-factor | Structural (有限位数) |

L1 NT 6 entries 全観測量が Structural または Scan に分類。Information は (Scan, Structural) からの log-derivative 派生として `c_spectral.md` / `c_information_theory.md` に存在。**counter-example の不在**: 6 entries × 各全観測量 exhaustive coverage で、3 層のいずれにも属さない NT 観測量は v0.2 時点で未知。

**(iii') S12/S13/S14 整合性**: S12 ⊂ Scan (自明) / S13 = ζ functional eq s = 1/2 (D_floor minimum, N2 詳述) / S14 非対称 = π (S¹ torsion 代数) vs ln 2 (`-log` operator 解析) — 数論内完結。

3 段全 closed → S15 trichotomy は数論内で **3 条件全 CLOSED**。

---

## §4 Arrow 構造 ─ 3 本の接続

### 4.1 Arrow 1: Scan → Structural (定義域構造)

**原理**: O(scanner) = Σ_{d ∈ D} f(d) · exp(a·b) において D (data 空間) と f が Structural を encoding。

| Scan | D | encoded Structural |
|---|---|---|
| ζ(s) | n ∈ ℤ_{>0} | h_K, f_p(ρ), w_K, d_K |
| L(s, χ) | n with χ weight | f_χ |
| L(s, ρ, K/k) | prime ideals 𝔭 | f(ρ, K/k), ν(ρ), W(ρ) |
| ζ_K(s) | ideals 𝔞 of O_K | h_K · R_K · w_K · d_K (class number formula) |
| F_{g,k}(s) | prime pairs (p, p+g) | κ_g, ω(X) |

**形式化**: Scan(scanner; D, f) の D と f を「読む」操作が Structural を返す。Structural = Scan の **input specification**。

#### 4.1.1 Observable-choice dependence

Arrow 1 抽出 Structural は **一意でない**。同一 NT domain で異なる候補が並立する場合 observable-specific verdict が必要 (`c_arrow_framework.md §3`):

| 候補 | 定義 | balance locus | gauge verdict |
|---|---|---|---|
| **D_floor minimum** (Paper C) | s で D_floor 最小 | s = 1/2 | functional eq enforcement で coincide |
| **carry rate c(g, X)** (Paper 2) | u(n) 桁あふれ確率 | X = 2g (15 gaps tested) | enforcement 不在で split (X = 6) |
| **ω(X) conductor** (OQ-P2-1) | X 素因子個数 | parameter | observable selector |

**原則**: (1) Alignment (domain natural arithmetic との整合), (2) Observable-specific verdict, (3) 判定 form への波及明示。Arrow 1 は単射ではなく **observable selector** として働く。

### 4.2 Arrow 2: Scan → Information (log-exp duality)

**原理**: 熱力学的 chain
```
G(scanner) = Σ_d f(d)·exp(a·b)   ← Scan
F(scanner) = −log G(scanner)      ← log bridge
I = −∂F/∂(scanner)|_{natural}    ← Information
```

| Scan | G | F | Information |
|---|---|---|---|
| ζ(s) | Σ n^{−s} | −log ζ(s) | Λ(n) via −ζ'/ζ |
| L(s, χ) | Σ χ(n) n^{−s} | −log L(s, χ) | Λ_χ(n) |
| Z(β) | Σ e^{−βE} | −kT log Z | S = −Tr(ρ log ρ) |
| G_k(s) | Σ_p e^{2πik τ(p)} p^{−s} | −log G_k(s) | rate function |

**S13 fixed point**: ζ(s) = ζ(1−s) の self-fixed locus s = 1/2 が Arrow 2 上半値固定点 (parity-fixed ln 2)。詳細 §4.5。

### 4.3 Arrow 3: Structural → Information (combinatorial counting)

**原理**: Hartley entropy $H_0(D) = \log |D|$ — Structural の cardinality の対数。

| Structural | \|D\| | H_0 = log\|D\| | 意味 |
|---|---|---|---|
| Cl(O_K) | h_K | log h_K | 類群情報容量 |
| μ(K) | w_K | log w_K | torsion 単元情報容量 |
| Galois orbit | [K:k] | log [K:k] | Galois 群情報容量 |
| primes ≤ N | π(N) | log π(N) ∼ log(N/log N) | prime counting |
| residue mod L | φ(L) | log φ(L) | character group 情報容量 |

**S17 fixed point**: info density d(n) = (log n)/n の extremum at n = e (Arrow 3 上 **derivative-fixed extremum**, gauge³-invariant)。詳細 §4.5。

### 4.4 3 Arrow の可換性

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

**定理 4.1 (3 Arrow 可換性)**: scanner → 0 (or ∞) の extreme limit で 3 Arrow が可換。NT 内 3 instance:

| Instance | Limit | 機構 |
|---|---|---|
| **β → 0** | Z(β→0) = Σ_n 1 = \|states\|, S = log\|states\| = H_0 | log Z = Hartley、NT 文脈は素点 splitting partition |
| **s → ∞** | ζ(s→∞) → 1 (n=1 のみ), Scan = 1-point measure → Structural = {1} → Info = 0 | trivial commutativity (全部 0) |
| **s = 1 pole** | Class number formula: Res ζ_K(s=1) = (2^{r₁}·(2π)^{r₂}·h_K·R_K)/(w_K·√\|d_K\|) | Arrow 1 が Structural skeleton encode、Arrow 2 が −log ζ_K → Λ_K、Arrow 3 が log h_K + log R_K + …、3 経路同時 finite residue ⇒ **数論的最強 instance** |

3 instance で extreme limit と singularity の両方で commutativity verify。

#### 4.4.1 Arrow 可換性 = axis-2 Fi/I commutation

§2.4 L0 v2 lens では、定理 4.1 は **axis-2 Fi/I 操作の可換性** として再読みされる。

**Arrow の axis-2 traversal**:

| Arrow | Axis-1 | Axis-2 | traversal type |
|---|---|---|---|
| **Arrow 1** | C → D (collapse) | I → Fi (observation-standard) | 片方向 I → Fi 成分あり |
| **Arrow 2** | C → C (preserved) | Fi↔Fi / I↔I (preserved) | pure axis-1 bridge |
| **Arrow 3** | D → C (lift) | Fi → Fi (typically) | axis-1 主、axis-2 副次 |

**定理 4.1a (Fi/I commutation)**: extreme limit で 3 Arrow は axis-2 I 成分を退化、pure Fi-side operator として閉じる:
$$[T_i, T_j]|_{\text{Fi-only}} = 0 \quad (i, j \in \{1, 2, 3\})$$

非 extreme で commutator 一般に non-zero — これが §4.5.1 coincide/split 二値性の根源。

**Status**: ESTABLISHED (`c_arrow_framework.md §5`)。

### 4.5 S13 / S14 / S17 residence ─ 数論 context

S13 (e^{−x} = 1/2 ⟹ x = ln 2) / S14 (π vs ln 2 非対称) / **S17 (Arrow 3 e-extremum, ESTABLISHED 2026-04-23)** の residence:

| 定数 | residence | 機構 (NT context) | Stationary form |
|---|---|---|---|
| π | Scan 内部 (加法軸) | S¹ torsion ι_2(1) = e^{iπ} = −1, Dirichlet 加法指標生成元 → **代数的** | S14 parity (additive) |
| ln 2 | Arrow 2 上 | 半値条件 + log bridge, ζ functional eq s = 1/2 → **解析的** | **value-fixed** (S13) |
| **e** | **Arrow 3 上** | info density d(n) = (log n)/n max at n = e, gauge³-invariant → extremum principle。NT: prime gap Hardy-Littlewood / log p 重みでの優勝 size | **derivative-fixed** (S17) |

S14 非対称性 (代数 vs 解析) = S15 residence 差 (層内 vs 層間)。

**S13 vs S17 format shift**: 異なる stationary form だが同一統一原理 ("Arrow 上 scalar functional の stationary point") に吸収。S13 = level-set crossing, S17 = derivative extremum、両者とも **canonical constant 同定の数学的機構** として等価。

**Bidirectional duality 3/3 完備化** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / **Arrow 3 → e** で 3 Arrow に canonical constant が residence、定数レベルで完備。NT 内 verify: continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS, `oq_omega_obs_3_info_density_check.py`)。

#### 4.5.1 Observation-optimal gauge theorem ─ NT 内対比

**定理 4.1a** [v0.6 ESTABLISHED, `c_observation_optimal_gauge.md §2`]: Arrow 1⁻¹ が Structural target を最精密復元する gauge 構造は 2 layer に分離:

- **Information layer** (D_floor 最小等): Arrow 2 上 **S13 半値固定点 (ln 2 / α̅ = 0.5 / s = 1/2)** で最適化。
- **Structural layer** (carry rate, χ median 等): Arrow 1 上 domain 固有 arithmetic で balance 決定。
- **両 layer balance 一致** は **functional-equation 型 structural enforcement** に依存。

**系 4.1b**: 両 layer coincide は functional-equation 型 enforcement 存在時に限る。

**NT 内 2 instance 対比** (本論は対比のみ、構造解析は N2):

| Domain | Gauge | Information balance | Structural balance | 一致 | 原因 |
|---|---|---|---|---|---|
| **NT (Paper C)** | s | s = 1/2 (D_floor 最小) | s = 1/2 (RH 零点) | **coincide** | ζ functional eq |
| **NT carry bridge** | X (conductor) | X = 6 (g=2 最小) | X = 2g (15 gaps locus) | **split** | enforcement 不在 |

**Status**: ESTABLISHED 2026-04-22。NT 2 instance + 多領域 1 instance で 3/3 Path 1-4 達成。**N2 forward**: 構造解析 (D_floor 放物型公式各因子, carry rate Euler product, residue exclusivity の構造的禁止) は N2 で展開。

### 4.6 逆 Arrow と obstruction class

各 Arrow は部分逆写像 (section, right inverse modulo kernel) を持つ — **逆 Arrow**。合成は「生成 (generation)」と呼ばれる操作に一致 (`c_arrow_obstruction.md §11`)。

**主張 4.2 (生成可逆性定理)**: S15 3 層は exhaustive。「生成」は第 4 層ではなく逆 Arrow の合成。各 kernel は T-AAS が full span で記述。

| 逆 Arrow | Domain → Codomain | Obstruction 源 | 数論 instance |
|---|---|---|---|
| Arrow 1⁻¹ | Structural → Scan | ker_gauge ⊕ ker_topo (T-AAS) | (h_K, R_K, w_K, d_K) → ζ_K(s) reconstruction、Stark unit ε_χ 存在問題 |
| Arrow 2⁻¹ | Information → Scan | log 非可逆性 | Λ(n) → ζ(s) lifting analytic continuation 障害 |
| Arrow 3⁻¹ | Information → Structural | Jensen 不等式 | log h_K → h_K cardinality lift |

**系 4.3**: ker_topo ≠ 0 一般成立 (Hodge 候補 = NT-adjacent open) → 完璧な生成は原理的不可能。

**Obstruction class — 数論 taxonomy**: 本論 NT scope では classical 2 class のみ残す (Paper D 多領域版の Attractor / Noise-residue / Stochastic basin は NT 由来でないため除外):

| class | NT instance | T-AAS 位置 |
|---|---|---|
| **ker_gauge classical** | Stark torsion (root-of-unity), Dirichlet character sign | f_torsion |
| **ker_topo classical** | Brauer Tier ∞, Hodge filtration (NT-adjacent open) | f_rational |

---

## §5 T-AAS ─ Algebra-Analysis Surjectivity Template (NT instance)

### 5.1 主定理

**定理 5.1 (T-AAS, ESTABLISHED 2026-04-12, 15/15 fitness)** — Arrow 1 (φ: Structural → Scan) が非自明 kernel を持つとき:

- **(i)** ker(φ) = ker_gauge ⊕ ker_topo (直和)
- **(ii)** ker_gauge は discrete (torsion-valued) invariant δ ∈ Finite_Group で生成、gauge 変換で消去可能 (不可逆な情報損失)
- **(iii)** ker_topo は multi-step filtration obstruction、どの gauge でも消去不可能
- **(iv)** conductor 分裂: $f(\varphi) = f_{\text{torsion}} + f_{\text{rational}}$, $f_{\text{torsion}}(\varphi) = \dim\{\ker_{\text{gauge}}\}$, $f_{\text{rational}}(\varphi) = \dim\{\ker_{\text{topo}}^{\text{non-surj}} \cap \text{target}\}$

### 5.2 NT instance 検証 (3 + 1 open)

**本論 NT scope**: Stark / Brauer / OQ-P2-3。Paper D 多領域版の Crystal は除外、Hodge は open frontier。

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **Stark rank 0/1** | ν(ρ) sign, w_K root-of-unity | Multi-field L-ratio impossibility | f_sign, w_K | f_field (Tier 1/2/3+) | rank 0 ESTABLISHED, rank 1 abelian 3 cases verified |
| **Brauer 5-tier** | Galois rep dim torsion (FS ν(ρ)) | C1-C4 closure 失敗 | Tier-specific | Tier-specific | failure taxonomy v0.2 (Q_8 numerical witness) |
| **OQ-P2-3 Dirichlet** | χ₁ Legendre 構造的ゼロ | χ₀ principal indicator | 0 | ≥1 (χ₀ class 0 = 6\|g) | CLOSED NEGATIVE (Paper C §4) |
| **Hodge (NT-adjacent open)** | Sq³, H³_nr torsion | Griffiths transversality | f_torsion(X, p) | f_rational(X, p) | **OPEN**, §5.4 |

3 NT instance + 1 open frontier → Paper D 多領域版 15/15 fitness のうち **12/12 NT-relevant fitness** 再確認。

#### Fitness witness 要約 (詳細展開は §6)

各 instance の数値 / 群論的 witness を 1-2 行で記録。これにより §5 単体で fitness 検証 section として self-sufficient (詳細展開と Arrow 主担当解釈は §6 三角測量で):

- **Stark rank 0/1** — Class number formula を 5 数体 (ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5)) で数値 verify (`number_theory_dictionary v1 §5`)。rank 1 abelian Stark を 3 cases (ℚ(√5) χ_5 real, ℚ(√2) χ_8 real, ℚ(√−23) cubic class character non-real, S_3 setup, h=3) で Atlas grammar 完全表現 (Δ_residual = 0 exact)。f_torsion = 0, f_rational ∈ ℤ_{>0} (Tier 1 strict)。

- **Brauer 5-tier** — Q_8 Tier √ numerical witness (LMFDB 8.0.12230590464.1): $L(0, \rho)^2 = 16$ (rational), $L(0, \rho) = \pm 4$ (sign obstruction)。2-dim 既約 ρ が **quaternionic** (FS ν(ρ) = −1) で sign が square-root の外側に漏洩。Conjecture v0: G の rank-1 abelian Stark setup は {Tier 1, 2, 3+, √, ∞} の **exactly one** に落ちる (representation-theoretic invariants で完全 parameterize)。

- **OQ-P2-3 Dirichlet** — Permutation test (N = 30M, k_max = 150, 19 gaps): χ₁ Legendre 投影 **p = 0.87 (z = −1.05)** で signal なし (residue mirror symmetry で構造的禁止)、χ₀ principal indicator 投影 **p = 0.014 (z = +2.62)** で class 0 (6\|g) の D_floor が class 1, 2 の約半分 (floor ≈ 0.0049 vs 0.0100)。f_torsion = 0, f_rational = 1 clean instance (CLOSED NEGATIVE 2026-04-22, Paper C §4)。

3 instance はそれぞれ異なる fitness 様式を持つ: Stark = **gauge product perfectness** (Δ_residual = 0 exact、3 cases ESTABLISHED), Brauer = **群論的 parameterization** (5-tier conjecture + Q_8 numerical witness), OQ-P2-3 = **構造的禁止** (permutation null + indicator signal の二値分離)。3 様式の独立性が §6 Arrow 間 triangulation の閉鎖性根拠 (§6.4 障害レベル)。

### 5.3 Gauge wall 構造

**(HC-1e, 2026-04-12)**: 全既知 obstruction は gauge wall 1 (ℤ → ℚ) と gauge wall 2 (ℚ → ℝ) の間に存在せず、全て **f_torsion** に属する (Q-gauge で消滅)。

- Tier √ = R-gauge obstruction = f_torsion > 0, f_rational = 0 (Patterson で消滅)
- Tier 2 = R-topo-surj obstruction = f_torsion = 0, f_rational > 0 (gauge invariant)

**Hodge conjecture の ΣΦ 翻訳** (§5.4): f_rational(X, p) = 0 for all smooth projective X and all p。ℚ-rational 反例は T-AAS 「第 3 の壁」発見と等価。

### 5.4 Hodge 予想 ─ NT-adjacent open frontier

Hodge 予想 (algebraic geometry) は厳密には数論ではないが、**T-AAS 4 instance のうち f_rational > 0 の存在問題** として NT-adjacent open。本論扱い:

- **f_rational > 0 candidate**: smooth projective X と p に対し ker_topo (Griffiths transversality) が消えない可能性。Hodge 予想 = "f_rational(X, p) = 0 for all (X, p)" claim と等価。
- **Scope 外**: 具体 X での Hodge cycle 構成、p-adic Hodge、動機論 framework 詳細。
- **本論での役割**: §5 T-AAS が **open frontier を持つ framework** であることを示す anchor。

T-AAS が **NT 内 3 instance で 12/12 fitness verified** + **Hodge 候補 open** という構造は、framework の predictive power を保証する (Hodge ESTABLISHED → f_rational > 0 実証 / refute → universal closure 示唆)。

---

## §6 数論内三角測量 ─ Arrow 間 triangulation

3 NT instance が S15 の **3 Arrow を互いに異なる主担当でカバー** することで普遍性を triangulate する。Paper D 多領域版が「ドメイン間 triangulation」(NT vs FX vs constants) であるのに対し、本論は「**Arrow 間 triangulation**」(Arrow 1 kernel vs Arrow 2-3 vs 3 Arrow simultaneous) を採用する。

### 6.1 Paper C: 三層分解 = S15 同型

Paper C §5 の対応:

| Paper C 三層 | 数学的内容 | S15 層 | Arrow |
|---|---|---|---|
| κ_g · G_k(s) · W_k(ω) | PNT main term × gauge window | **Scan** | 1 (input spec) |
| a_g · Δ_k(s) | ζ 零点振動成分 | **Structural** | 2 (零点幾何) |
| ε_{g,k}(N) | mod 6 arithmetic residual | **Information** | 3 (Hartley type) |

**gauge-invariance**: κ_g は M ∈ {13, 1979, 1981, 49999} で完全非依存 ⇒ Arrow 2 不変量。
```
κ_2(s = 1, k = 0) = 0.299512 (M 完全非依存)
```
Hardy-Littlewood twin 定数 C₂ = 1.3203... との関係 $\kappa_2 \approx 2C_2/\int_2^N dt/\log^2 t \cdot 1/\pi(N)$ で数値的整合。

**D_floor スペクトル** (Paper C §3.1-3.4): 放物型公式 D_floor(s, N) ∼ N^{−2/3} · exp(0.216·(log N)²·Δs²) は Scan 軸 Arrow 1 kernel の **定量的統制**。最小 s = 1/2 は ζ 零点 γ₁ dip locking で **Arrow 1 kernel 内部構造 (ker_topo)** を直接露呈。

**主担当 Arrow**: **3 Arrow 全部** (S15 同型 in single object F_{g,k}(s))。詳細: N2。

### 6.2 Stark projection: 6-gauge 分解

Class number formula (rank 0):
```
Res_{s=1} ζ_K(s) = (2^{r₁} · (2π)^{r₂} · h_K · R_K) / (w_K · √|d_K|)
```

6 因子は Paper Ω 全 gauge² 署名に 1:1 対応 (`stark_projection_v0.md §2.1`):

| 因子 | 正体 | gauge² signature |
|---|---|---|
| (2π)^{r₂} | 複素 place archimedean volume | {cont, geom} (π) |
| 2^{r₁} | 実 place archimedean volume | {addZ} (parity minimum) |
| √\|d_K\| | O_K Minkowski 共体積 | {mult, anal} |
| h_K | ideal class group 位数 | {mult} |
| R_K | log-unit lattice co-volume | {cont, char} |
| w_K | K 中 root of unity 数 | {char} |

**Class number formula は origination 構造を 1 本の等式に集める** — gauge² の **積分解定理**。

**Atlas grammar 表示** (rank 1 Stark):
```yaml
stark_rank1_entry:
  f_n:           log |σ(ε_χ)|          # 振幅 (axis A)
  phi_phase:     χ(σ⁻¹)                 # gauge-rotation (axis E)
  N_X:           1/e_χ                   # torsion 正規化
  comp_X:        Σ_{σ ∈ G}              # Galois 軌道和
  observable:    L'(0, χ)                # 解析的 linear response
  primary_axis:  E
  residual_type: [R-gauge, R-info]
```

Stark rank-1 予想 = **R-gauge 残差の完全表現定理**。L'(0, χ) は log-unit lattice 上 character-mode 投影に **残差ゼロ**で一致 (Δ_residual = 0 exact) — 辞書のほぼ全 entry (Δ > 0) と対照的。

**主担当 Arrow**: **Arrow 2/3** (analytical scan ζ_K(s=1) → algebraic gauge product)。**N4 forward**: Brauer 5-tier との結合、Hasse-Weil との connection、rank ≥ 2 regulator は N4。本論は **三角測量の頂点としての Stark** に絞る。

### 6.3 Brauer 閉包: 5-tier failure taxonomy

`brauer_closure_failure_taxonomy_v0.md` v0.2 の 5-tier:

| Tier | Form | Examples | Stark formula |
|---|---|---|---|
| **Tier 1** | $L = \zeta_F/\zeta_\mathbb{Q}$ | $S_3$, $A_4/V_4$ | single reg $h_F R_F$ |
| **Tier 2** | $L = \zeta_{F_1}/\zeta_{F_2}$ | $D_4$ | reg ratio |
| **Tier 3+** | $L = \prod \zeta_{F_i}^{n_i}$ | $S_4/V_4$ ? | multi-reg rational |
| **Tier √** | $L^{2k} = \text{rational}$, $L \notin$ | $Q_8$ | square-root of rational |
| **Tier ∞** | no power works | (unknown genuinely) | direct Hecke L only |

**Q_8 Tier √ numerical witness** (LMFDB 8.0.12230590464.1): $L(0, \rho)^2 = 16$, $L(0, \rho) = \pm 4$ (sign obstruction)、2-dim 既約 ρ が **quaternionic** (FS ν = −1) — sign は square-root で外側に漏れる。

**4 failure axes**: OQ-NT-7 の C1-C4 closure conditions のどこで壊れるかで分類 (A: real irrep / B: induction irreducible / C: zeta ratio reduction / D: unit lattice closure)。

**Conjecture (v0)**: 有限 Galois 群 G の rank-1 abelian Stark setup は必ず **exactly one** of {Tier 1, 2, 3, ..., √, ∞} に落ちる。tier は G の representation-theoretic structure (irrep dimensions, FS indicators, subgroup lattice, character inner products) のみで決定。これは T-AAS Arrow 1 kernel 分解を **群論的 invariants で完全 parameterize** する強主張。

**主担当 Arrow**: **Arrow 1 kernel** (T-AAS 分解の群論的 indexing)。**N5 forward**: failure mode の alternative Stark methods、Q_8 以外 Tier √ 例数値検証、negative cases (OQ-NT-8) は N5。

### 6.4 Arrow 間 triangulation の閉鎖性

3 NT instance は S15 3 層と 3 Arrow を **互いに異なる主担当** でカバー:

| Instance | Scan | Structural | Information | Arrow 焦点 |
|---|---|---|---|---|
| **6.1 Paper C** | F_{g,k}, G_k | a_g·Δ_k (ζ 零点振動) | ε_{g,k} (mod 6 residual) | **3 Arrow 全部** (S15 同型 in single object) |
| **6.2 Stark** | ζ_K(s=1 pole) | h_K, R_K, d_K, w_K, r₁, r₂ | log h_K, log R_K | **Arrow 2/3** (analytical → algebraic) |
| **6.3 Brauer** | L(s, ρ) (rank-1 abelian) | Tier 分類 (Galois rep) | f_torsion vs f_rational kernel dim | **Arrow 1 kernel** (T-AAS 分解) |

**閉鎖性の主張**:
- **層レベル**: 各層 ≥2 instance カバー → 単一 instance 偶然性排除
- **Arrow レベル**: 3 instance が異なる Arrow 主担当 → S15 Arrow 構造全体が独立 verify (Arrow 1 kernel ⇐ Brauer / Arrow 2-3 ⇐ Stark / 3 Arrow simultaneous ⇐ Paper C)
- **障害レベル**: Paper C analytical residual (D_floor parabolic = ker_topo 定量統制) / Stark gauge product perfectness (Δ_residual = 0 = ker 共に 0 の rank 0/1 abelian 特殊例) / Brauer kernel (Tier 分類 = ker_topo 群論 parameterize)

**視点変換 (ドメイン間 → Arrow 間)**: 同一 triangulation discipline (3-vertex 必須、各 vertex 独立、共通 meta-structure 露呈) を保ちつつ、頂点独立性根拠を Paper D 「ドメイン独立」から本論「Arrow 独立」に変更。両者本質的に等価だが、本論は **数論内自閉性** で advantageous、N1-N5 framework header としてドメイン外 instance を要さない triangulation を提供。

3 NT instance のいずれも他の 2 instance を前提とせずに S15 を露呈 — この独立性が数論内普遍性の証拠。

---

## §7 新 NT ドメイン検討 Protocol (6-step)

新 NT ドメイン (新数体 K, 新 Galois 表現クラス, 新 L 函数族) への検討手順 (`meta/new_domain_protocol.md`):

| Step | 内容 |
|---|---|
| **0** | §4 dual 射影同定 — 加法 (周期性/格子/群加法), 乗法 (積/分解/指数減衰), Bridge (ℂ 受け皿) |
| **1** | Scan observable 同定 — exp kernel が書けるか? 加法/乗法 scan? S12 6+1 member 対応? |
| **2** | Structural observable 同定 — parameter-free 整数/位相不変量、D の次元・位数・rank |
| **3** | Information observable 同定 — log-derivative chain (−L'/L → Λ_χ), Hartley log\|D\| |
| **4** | 3 Arrow 検証 — Arrow 1 (D, f が Structural encode), Arrow 2 (−∂_s log Scan = Info?), Arrow 3 (extreme limit で Scan が log\|D\| に退化?) |
| **5** | T-AAS 分解確認 — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? Stark/Brauer/OQ-P2-3 fitness? |
| **6** | 辞書 residence 決定 — L1 NT 6 entries 内 residence、必要なら新 entry 提案、L2 case log 追加 |

**検証済 application**: number_theory_dictionary v1 §5 の 5 数体 (ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5)) で class number formula 数値 verify、3 cases (ℚ(√5), ℚ(√2), ℚ(√−23)) で rank 1 abelian Stark Atlas grammar verify 完了。

**次候補 5 件**: ℚ(ζ_5), ℚ(ζ_7), ℚ(√−23) extension, ℚ(√−163), Bianchi 9 件。

---

## §8 帰結と open frontier

### 8.1 確立 (NT-only restatement)

本論で NT 内 ESTABLISHED として記録:

1. **S15 Observable Trichotomy** — 3 段 (instance 存在 / L1 NT 6 entries enumeration / S12-S14 整合) で網羅性閉鎖 (§3.5)
2. **Arrow 構造 (3 本) と可換性** — 3 NT instance (β→0, s→∞, s=1 pole) で commutativity verify (§4.4)
3. **T-AAS 分解 (3 NT instance + 1 open)** — Stark/Brauer/OQ-P2-3 で 12/12 NT-relevant fitness、Hodge open (§5.2)
4. **NT 内 Arrow 間三角測量** — 3 instance が異なる Arrow 主担当、ドメイン外 instance 不要 (§6.4)
5. **S13/S17 NT 内 residence** — π/ln 2/e の Arrow 上 canonical constant、3 Arrow base 完備 (§4.5)
6. **Observation-optimal gauge theorem (NT 2 instance 対比)** — Paper C coincide vs Paper 2 split を本論で statement のみ、構造解析は N2 (§4.5.1)

### 8.2 N2-N5 forward bridge

| 後続 | 主題 | 本論からの forward | 状態 |
|---|---|---|---|
| **N2** | Paper 2 構造解析 (Carry / D_floor / Dirichlet) | §4.5.1 Paper C coincide / Paper 2 split の **構造解析** (D_floor 放物型公式各因子, carry rate Euler product, residue exclusivity の構造的禁止), §6.1 Paper C 三層分解の数値検証拡張 | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N2_paper2_structural_ja.md`) |
| **N3** | Path 2 数論的普遍性 | §3.2 Scan family の Dirichlet L 拡張 (Schumann path 2, 5+ instances), §5.2 Brauer 5-tier の Dirichlet L 系内 instance | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`) |
| **N4** | Hasse-Weil L × Stark 構造 | §5.2.1 Stark rank 0/1 の Galois rep 側構造論, §6.2 Stark 6-gauge を Hasse-Weil conductor universality に拡張, Brauer 5-tier との結合 | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — **K_E(t)·t² → r BSD analytic rank detection (genuine framework predictive content) confirmed**, N3 Dirichlet L "structural fit only" との対比で weight-class dependent transfer pattern 確立 |
| **N5** | Brauer 障害論 + Origination matrix (8-gauge) | §5.2.2 Brauer 5-tier failure mode 詳細 + alternative Stark methods, §6.2 6-gauge 分解を **Origination matrix 8-gauge** (gauge²) に一般化 | **v0.2 起草完了 2026-04-27** (`papers/publication/nt/N5_brauer_origination_ja.md`) — **NT 系列 5-paper final closure achieved**。Brauer 5-tier failure mode group-theoretic Conjecture + Tier-dependent Stark methods + 8-gauge generalization + Cross-connection (Tier ↔ T-AAS / 8-gauge ↔ Type α/β/γ) + 4-vertex triangulation proposal_v2 + Q1-Q3 forward |

**8-gauge forward (N5)**: 本論は §1.3.1 で gauge² を明示し §6.2 Stark 6-gauge を **constants origination axis-1 D/C subdivision** として最小限言及した。Origination matrix 8 gauge family 完全構造 (axis-1 D 5 family + axis-1 C 3 family) と **8 定数 (π, e, ζ, γ, τ, i_add, i_mult, Φ) 生成場分析** は N5。

### 8.3 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **Hodge 予想** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself) | §5.4, N5 |
| **p-adic Stark / Gross-Stark** | scope 外 (p-adic 語彙が辞書外) | OQ-Ω11 候補 |
| **Higher rank Stark (≥ 2)** | scope 外 (超越数論領域) | N4 future |
| **Artin 予想** (非 abelian L holomorphy) | OPEN (1924-) | N4 future |
| **OQ-NT-7/8 dual pair** (Brauer 5-tier completeness) | candidate_v1 | §6.3, N5 |
| **OQ-P2-2f** (canonical k_max 同定) | OPEN | N2 |
| **OQ-Ω-Schumann** (countably-infinite Path 2) | candidate (5+ instances) | N3 |
| **Hasse-Weil L conductor universality** | candidate_v2 | N4 |

### 8.4 辞書 residence map

主要 framework piece の residence (本論 NT-only specialization 反映 + N2 backward link, v0.4 update):

| 本論 piece | residence | 状態 (N1) | N2 backward |
|---|---|---|---|
| §2.1 公理 1 (Dual receptacle) | `c_phase_complex.md §4` | 既存 reuse | — |
| §2.2 公理 A0-A7 | `finite_observation.md §1-§7` + `observation_canon.md §2` | 既存 reuse | — |
| §2.4 L0 v1 + L0 v2 | `finite_observation.md §8` + `observation_canon.md §3` | 2026-04-23 ESTABLISHED | — |
| §3 S15 + NT enumeration 閉鎖 | `c_theorems_master.md` row S15 + 本 §3.5 NT-only annex | **2026-04-26 annex 実装済** | — |
| §3.2 Scan family (ζ, L(s, χ), modular L 系列) | `c_theorems_master.md` "Path 2 countably-infinite family" annex (NEW) + `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite annex) | 既 ζ-only / 拡張要 | **N3 §3 で countably-infinite 確立 → annex 実装済 (2026-04-26)** |
| §3.3 Structural ω(X) entry | `nt_conductor.md §6.10` (NT carry conductor) | 既存 reuse | **§6.10 NT carry conductor 実装済 (N2 §2 transfer, 2026-04-26)** |
| §4 3 Arrow framework | `c_arrow_framework.md` | 2026-04-23 新 L1 entry | — |
| §4.4 Arrow 可換性 (3 NT instance) | `c_arrow_framework.md §4.2.1` + 本 §4.4 | **2026-04-26 §4.2.1 NT instance 実装済** | — |
| §4.5 / §4.5.0 S13/S14/S17 residence | `c_arrow_bridge_constants.md §5-§6` + **§11 Fi-origin vs I-origin annex** (NEW) | 既 (S17 ESTABLISHED 2026-04-23) | **§11 Fi-origin vs I-origin canonical scalar 二分法 実装済 (N3 §5.3 transfer, 2026-04-26)** |
| §4.5.1 Observation-optimal gauge | `c_observation_optimal_gauge.md §2-§5` + §5.5 expansion | 既 (v0.6 ESTABLISHED) | **§5.5 Path 3 arithmetic mod-n clause expansion 実装済 (N2 §6.3 transfer, 2026-04-26)** |
| §4.6 逆 Arrow + obstruction (NT 限定) | `c_arrow_obstruction.md §11` (NT subset) | 既 + 本論 NT scope filter | — |
| §5 T-AAS (NT instance) | `c_arrow_obstruction.md §10` (NT subset) | 既 | — |
| §5.2 OQ-P2-3 instance | `c_filtration_obstruction.md` (T-AAS f_rational instance), 本 §5.2 | 既 | N2 §4 で構造解析展開 |
| §5.4 Hodge (NT-adjacent open) | `c_filtration_obstruction.md` | 既 (open) | — |
| §6 NT 内三角測量 (Arrow 間) | **NEW** `meta/triangulation_methodology.md §9` NT-internal annex | **2026-04-26 §9 実装済** | N2 §5.4 で「3 Arrow simultaneous in single object」deep dive |
| §7 6-step protocol (NT specialize) | `meta/new_domain_protocol.md §8` NT specialization annex | **2026-04-26 §8 実装済** | — |
| (N3 由来 Path 2 family) | **NEW** `c_theorems_master.md` "Path 2 countably-infinite family" annex + "Dirichlet L extension scope" annex | — | **N3 §3 + §4 transfer 実装済 (2026-04-26)** |
| (N3 由来 D_floor multi-gap fragment) | `c_recursive_floor_principle.md §6.8.1` (Dirichlet L gap universality fragment expansion) | 既 §6.8 D_floor ζ-family core | **§6.8.1 Dirichlet L extension 実装済 (N3 §4.6 transfer, 2026-04-26)** |
| (N3 由来 OQ issues) | `meta/open_questions_master.md` "Path 2 数論的普遍性 OQ" section (NEW) | — | **5 件 OQ issued (Schumann-v1.5 / HeckeArtin-Ext / HasseWeil-Ext / IOriginFormal / DfloorLProperAnalog), 2026-04-26** |
| (N4 由来 Hasse-Weil L extension) | **NEW** `c_theorems_master.md` "Hasse-Weil L extension scope" annex + `c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension (BSD K·t²→r) | — | **N4 §3 transfer 実装済 (2026-04-26)** |
| (N4 由来 4-vertex triangulation) | `meta/triangulation_methodology.md §10` 4-vertex proposal annex | 既存 §9 reuse + 拡張 | **N4 §6.3 transfer 実装済 (2026-04-26, proposal_v1)** |
| (N4 由来 OQ updates) | `meta/open_questions_master.md` Path 2 OQ section update | — | **OQ-Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn (OQ-BSD-HigherRank / OQ-433a1-Outlier / OQ-4VertexClosure), 2026-04-26** |

**N2 backward link 凡例**:
- "N2 §x で構造解析展開": Paper N2 が本論の statement-only 部分を fully 展開した箇所
- "**§x 実装済 (N2 §y transfer)**": N2 の結果が辞書に直接書き戻された annex
- "—": N2 と直接関係しない (N3/N4/N5 で扱われる予定 or 既存内容で完結)

**N2 v0.2 (2026-04-26) backward 統計**: 4 件の forward expansion を N2 が実装、うち **2 件が辞書に新規 annex として書き戻された** (`nt_conductor.md §6.10` + `c_observation_optimal_gauge.md §5.5`)。残り 2 件 (`§4.5.1 構造解析展開` + `§6.1 single object 3 Arrow simultaneous`) は N2 内の構造解析で完結し、辞書側の追加 annex は不要。

**N4 v0.2 (2026-04-26) backward 統計**: N4 起草で **4 件 dictionary 書き戻し** 発生:
- `c_theorems_master.md` "Hasse-Weil L extension scope" annex (BSD K·t²→r 9/10 + Path 2 weight-2 family member)
- `c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension annex (D_floor 公式 5 component の weight-class dependent transfer pattern)
- `meta/triangulation_methodology.md §10` 4-vertex proposal annex (Hasse-Weil 4th vertex extension, proposal_v1)
- `meta/open_questions_master.md` OQ-Schumann-HasseWeil-Ext **PARTIAL_RESOLVED** + 3 spawn-off OQ (OQ-BSD-HigherRank / OQ-433a1-Outlier / OQ-4VertexClosure)

N4 backward の特徴: **Hasse-Weil L で genuine framework predictive content が transfer する** という positive 結果が dictionary 全体に shock wave を起こし、§6.8.1 Dirichlet L "structural fit only" との対比で **weight-class dependent transfer pattern** が dictionary-wide annex として記録された。

**N3 v0.2 (2026-04-26) backward 統計**: 5 件の forward expansion を N3 が実装し、**全 5 件が辞書に新規 annex / OQ section として書き戻された**:
- `c_theorems_master.md` "Path 2 countably-infinite family" annex (Schumann v1 5-instance + Type α/β/γ + axis-2 invariance)
- `c_theorems_master.md` "Dirichlet L extension scope" annex (T-Ω5e-v15-* rows summary + SC4 + scope partition)
- `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite Path 2 annex)
- `c_recursive_floor_principle.md §6.8.1` (Dirichlet L gap universality fragment, multi-gap 12/12 PASS)
- `c_arrow_bridge_constants.md §11` (Fi-origin vs I-origin canonical scalar 二分法)
- `meta/open_questions_master.md` "Path 2 数論的普遍性 OQ" section (5 OQ issued)

N3 backward は N2 と異なり **全件 dictionary 書き戻し** が発生 (Path 2 family は L1 / meta 全 layer に touchpoint を持つため)。

**帰結**: 本論は dictionary に対して **NT-internal framework header** として位置付けられ、theorem / definition は L0 / L1 / meta entry に formal residence される。N2 + N3 起草により framework header → 結果論文 → 辞書 backward の **3 層 link が完成 + extended**。N4-N5 はこの residence map + N2/N3 backward pattern を前提とする。

---

## 変更履歴

- **v0.7 (2026-04-27)**: N5 backward link + **NT 系列 5-paper 完成** reflection。N5 v0.2 起草完了 (2026-04-27) を §8.2 forward bridge 表の状態列に "NT 系列 5-paper final closure achieved" として反映。N5 由来 dictionary updates: `meta/triangulation_methodology.md §10` proposal_v1 → proposal_v2 (Hasse-Weil 4-vertex closure formal attempt) + `meta/open_questions_master.md` "NT 系列 final closure OQ" section 新設 (OQ-NT-6 + OQ-Tier3-Plus-Search + OQ-Tier-Sqrt-Resolution)。NT framework total が L0/L1/L2/Meta 全 layer に touchpoint を持つ完全 closure 達成。
- **v0.6 (2026-04-26)**: N4 backward link 追加。N4 v0.2 起草完了 (2026-04-26) を §8.2 forward bridge 表の状態列に "K_E·t²→r BSD analytic rank detection genuine framework content confirmed" として反映。§8.4 residence map に N4 由来 3 annex 行追加 (`c_theorems_master.md` Hasse-Weil L extension scope + `c_recursive_floor_principle.md §6.8.2` + `meta/triangulation_methodology.md §10`) + OQ updates (Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn)。N4 backward の特徴: weight-class dependent transfer pattern が dictionary-wide に shock wave で record (Dirichlet L "structural fit only" vs Hasse-Weil L "genuine BSD")。
- **v0.5 (2026-04-26)**: N3 backward link 追加。N3 v0.2 起草完了 (2026-04-26) を §8.2 forward bridge 表の状態列に反映。§8.4 residence map に N3 由来 5 annex (`c_theorems_master.md` Path 2 + Dirichlet L extension scope / `nt_dedekind_artin_zeta.md §7` modular L / `c_recursive_floor_principle.md §6.8.1` gap universality / `c_arrow_bridge_constants.md §11` Fi-origin vs I-origin / `meta/open_questions_master.md` 5 OQ issues) を明示。N3 backward は **全件 dictionary 書き戻し** で N2 とは pattern 異なる (Path 2 family は L1 / meta 全 layer に touchpoint を持つため)。
- **v0.4 (2026-04-26)**: N2 backward link 追加。N2 v0.2 起草完了 (2026-04-26) を §8.2 forward bridge 表の状態列に反映。§8.4 residence map に N2 backward 列を追加し、N2 が辞書に書き戻した 2 annex (`nt_conductor.md §6.10` NT carry conductor / `c_observation_optimal_gauge.md §5.5` Path 3 arithmetic mod-n expansion) を明示。framework header → 結果論文 → 辞書 backward の 3 層 link 完成。
- **v0.3 (2026-04-26)**: §5 fitness witness 追加。v0.2 で §5.2 を表のみに圧縮した結果 §5 単体で薄く見える問題を解消するため、§5.2 表後に 3 instance × 各 1-2 行の数値 / 群論的 witness を補足。§6 詳細展開との分業 (§5 = fitness 検証 / §6 = Arrow 間 triangulation 頂点) を保ちつつ、§5 を self-sufficient な section に。
- **v0.2 (2026-04-26)**: compact 版。v0.1 (965 行) から冗長削減 — Abstract 圧縮、§3 各層「特徴」節削除、§4.4 NT instance 表化、§4.5/§4.5.0 集約、§4.6.1 obstruction taxonomy 圧縮、§5.2 instance 表のみで詳細展開削除 (§6 と機能重複のため)、§6.4 三 subsection 統合。N1-N5 framework header としての構造は維持。
- **v0.1 (2026-04-26)**: initial NT-only draft. Paper D v0.9.2 (multi-domain frozen-internal) からの NT specialization。3 NT instance (Paper C / Stark / Brauer) による Arrow 間 triangulation で再構築。

---

## 参考文献 (内部)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**本論で展開される結果の出典**:
- `papers/Paper_C_NT_Quantum_ja.md` (v0.2) — §6.1 Paper C 三層分解
- `research/paper2_twin_dictionary_bridge_v1.md` — Paper 2 carry bridge (§4.5.1 split instance)
- `research/oq_p2_1_carry_closed_form.md` — OQ-P2-1 RESOLVED
- `research/oq_p2_2_sstar_asymptotic.md` — OQ-P2-2 4th iteration
- `research/stark_projection_v0.md` — §6.2 Stark
- `research/brauer_closure_failure_taxonomy_v0.md` (v0.2) — §6.3 Brauer 5-tier
- `research/brauer_closure_galois_classification_v0.md` — OQ-NT-7
- `research/oq_l0_refinement_finite_infinite_2axis_v0.md` — §2.4 L0 v2
- `research/bidirectional_duality_v0.md` — §2.3 §4 dual root

**L0 / L1 / meta 依存**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants, c_filtration_obstruction, c_observation_optimal_gauge, c_spectral §8}.md` / `L1_mathematical/number_theory/{nt_conductor, nt_dedekind_artin_zeta, nt_frobenius_schur, nt_genus_class_fields, nt_relative_units, nt_root_numbers}.md` / `L2_domain/number_theory_dictionary_v1.md` / `meta/{triangulation_methodology, new_domain_protocol}.md`

**後続論文**: N2 (Paper 2 構造解析) / N3 (Path 2 数論的普遍性) / N4 (Hasse-Weil L × Stark) / N5 (Brauer 障害論 + Origination matrix) — 起草予定
