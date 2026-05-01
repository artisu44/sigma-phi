# Paper Q1: 観測理論 ─ 量子版

**サブタイトル**: 非可換 §4 dual・S15 量子内 enumeration・T-AAS 4-class refined Hodge・量子内 Arrow 間 triangulation

**バージョン**: v0.2 (compact, 2026-04-27)
**状態**: DRAFT — Paper D (multi-domain v0.9.2) からの 量子-only 再構成、N1 (NT-only) と parallel framework header
**前提 (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**前提 (L1)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11`, `c_filtration_obstruction.md`, `c_observation_optimal_gauge.md`
**前提 (L1 量子)**: `q_quantum_observation.md`, `q_action_principles.md`, `q_gauge_field_theory.md`, `q_fine_structure.md` (4 entries; Open QS chain 4 entries は Q2 主体)
**前提 (NT 並行)**: N1 (`N1_observation_theory_nt_ja.md` v0.7)
**後続論文**: Q2 (Open QS chain) / Q3 (Born-Gleason)

---

## §0 Abstract

量子観測量はドメイン無関係な 3 層構造 **S15 Observable Trichotomy** (Scan / Structural / Information) に排他的かつ網羅的に分類され、層間 3 Arrow の可換性が ユニタリ発展 / spectral 構造 / von Neumann entropy 系の翻訳を保証する。Arrow 1 kernel は **T-AAS** で ker_gauge ⊕ ker_topo に直和分解、conductor は f_torsion + f_rational に分裂する。

本論は Paper D (multi-domain v0.9.2) の量子専用 reformulation。multi-domain triangulation を strip し、**量子内 4 instance** (Stabilizer / Gaussian / Eff-sim / Bell-local — OQ-Ω-Obs-4a 4-class refined Hodge framework) による **Arrow 1 kernel taxonomy 4-vertex triangulation** で再構築。N1 (NT-only) と parallel structure を持つが、量子側固有の 2 特徴 — (a) §4 dual の **非可換 lift** (ι_L → Stone unitary group, χ → unitary representation) と (b) Born-Gleason による Arrow 2-3 の **single-object 同時 instanciation** — を重点記述。

**主結果 6 件**:

1. **S15 量子-only restatement** — 3 層 enumeration (Scan 7 / Structural 12 / Information 9) + L1 量子 8 entries 網羅 → 量子内網羅性閉鎖
2. **Arrow 構造の量子内検証** — 3 量子 instance (β→0 thermal limit, t→0 trivial unitary, T→∞ classical limit) で extreme limit commutativity verify
3. **T-AAS 4-class refined Hodge (ESTABLISHED 2026-04-23)** — Stabilizer / Gaussian / Eff-sim / Bell-local の 4 narrower class で f_rational > 0 instance formal、Theorem 4a.1 (unified f_rational via class infidelity, log₂-bit 統一 4-monotone) で 4 monotone (M_F / 𝓝 / Nielsen C / Δ_CHSH) を class-fidelity F_C(ρ) で統合
4. **量子内 Arrow 1 kernel narrowness 4-vertex triangulation** — 4 instance が異なる sparsity 様式主担当 (C₁ discrete-in-continuous / C₂ poly-in-infinite / C₃ poly-in-exp / C₄ classical-polytope-in-quantum-correlation-body)。N1 cross-Arrow 3-vertex を補完する intra-Arrow taxonomy 4-vertex 視点
5. **Born-Gleason as §4 dual 量子 root** (Q3 forward) — Busch-Gleason 定理 (PRL 2003) による Born 則 form (Tr(ρE)) と value (ρ_max = I/2) の同時定理化、dim=2 Gleason 例外の有限観測者条件下解消
6. **新量子ドメイン Protocol (6-step) + Q2-Q3 forward** — Open QS chain (Q2) 4-stage residence + Born-Gleason closure (Q3) 明示 forward

**Thesis**: 量子観測量はドメイン外 instance を要さずに観測理論の全骨格を独立に支える。N1 (NT) と Q1 (量子) の **2 parallel framework header** が S15 / T-AAS / Arrow framework の **ドメイン非依存普遍性** を 2 数学領域で同時 verify。本論は Q2-Q3 の理論基盤として機能。

---

## §1 Introduction

### 1.1 なぜ「量子観測理論」か

量子力学の中心問題 — 観測者は重ね合わせ状態をどう「読む」のか — は Born 則 (Prob = |⟨φ|ψ⟩|² = Tr(ρ P_φ)) で operational に閉じているが、その **生成原理** は Bohr-Heisenberg 以来開かれた question。ΣΦ 辞書はこれを「§4 dual の非可換 lift 上で観測がどの層に住むか」と捉え直し、量子観測量が共通 **観測三分類 S15** に住むことを 2026-04-08 以来蓄積で確認 (`q_quantum_observation.md`)。

S12 → S13 → S14 → S15 → S17 chain が露呈させた結論:

> **量子観測量は加法 ⇔ 乗法の双対の異なる射影であり、その射影は排他的・網羅的に 3 層に分類される。古典との差異は §4 dual の非可換 lift の有無に局所化される。**

Paper D (multi-domain) の triangulation で観測理論の普遍性は確立済だが、本論は **量子内自閉性** に焦点を絞り Q2-Q3 の理論基盤として機能。N1 が NT 内自閉性で同様の framework header を提供するのと parallel position。

### 1.2 本論の範囲

**構成**: §2 公理 / §3 S15 / §4 Arrow / §5 T-AAS / §6 三角測量 / §7 Protocol / §8 帰結。

**Scope 内**: §4 dual の非可換 lift (Stone 定理, ユニタリ表現, スペクトル定理) / S15 量子 enumeration + 各層 quantum instance / T-AAS 4-class refined Hodge (OQ-Ω-Obs-4a ESTABLISHED 2026-04-23, 6/6 gate, 3/4 empirical) / 量子内 Arrow 間 triangulation (4-vertex algebraic class) / 6-step protocol 量子 specialization / N1 parallel structure 視点。

**Scope 外** (本論で扱わない): multi-domain triangulation (→ Paper D) / NT 内 instance 詳細 (→ N1-N5) / Open QS chain 4-stage 詳細 (→ Q2) / Born 則 derivation 完全形 / Gleason gap dim=2 解消の完全証明 / σ* = √(2 ln 2) half-amplitude gauge (→ Q3) / 量子場論 / QFT / 量子重力 / 弦理論 (本論 scope 外、L1 量子 8 entries 範囲限定)。

### 1.3 用語と "gauge" disambiguation

**基本用語**: Observable = 量子観測量 (自己共役作用素 A, または POVM Effect E) / Scanner = Scan に付随する外部パラメタ (t 時間, β 逆温度, τ unfolded time) / **§4 dual** = ι_L (加法 ℤ → S¹) と χ (乗法指標) の対 — 量子版では **Stone unitary group {U(t)}** (連続 ι_L lift) と **unitary representation π: G → U(H)** (非可換 χ lift) / Arrow = S15 3 層を繋ぐ写像 / T-AAS = Arrow 1 kernel 分解定理 / Triangulation = 独立 instance による偶然性排除。

**"gauge" の 3 用法** (混同回避、N1 §1.3 と同義):

| 記号 | 名称 | 意味 | 本論での使用範囲 |
|---|---|---|---|
| **gauge¹** | §4 dual gauge | ι_L / χ の選択 = 観測の structural root (量子 lift 含む) | §2-§5 全体 |
| **gauge²** | Origination 8-gauge | 定数発生場の 8 種 family | §6 + §8.2 forward のみ |
| **gauge³** | Arrow 3 base-of-log gauge | log の base 選択 (b > 0, b ≠ 1) | §4.5 S17 base 非依存性のみ |

T-AAS の "ker_gauge" は **gauge¹** family (量子: class-stabilizing unitary 群、e.g., Clifford for C₁, symplectic for C₂)。

**追加用語 (量子-specific)**: **Class-stabilizing gauge** = 4 algebraic class C 各々を保つ unitary 群 (C₁ Clifford / C₂ Gaussian symplectic / C₃ poly-depth circuit / C₄ local unitaries U_A ⊗ U_B) / **Class-fidelity F_C** = $F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$, Theorem 4a.1 (§5.3) で unified monotone $-\log_2 F_C$ の base を提供。

### 1.4 Direction-axis position (Q-framework = B-primary native)

`user_observation_direction_axis` (ESTABLISHED 2026-05-01) の A/B observation direction axis において、本論 Quantum framework は **B-direction primary native** に位置する:

| Side | Direction | 観測モード | 量子側 instance |
|---|---|---|---|
| 加法/離散/NT | **A (有限→無限)** | 有限観測 → 無限 outer extrapolation | (本論 scope 外、N1 framework が担当) |
| **乗法/連続/量子** | **B (無限→有限)** | **無限 ontology → 有限 inner projection** | **本論主領域** |

**B-direction native 構造の量子側 instance**:
- **Born rule** (§3 Information layer / Q3 forward): 無限次元 Hilbert ensemble (state space) → 有限 measurement outcome の projection postulate
- **Stone unitary group** (§1.3): 連続 ι_L lift = 無限 ontology の continuous parametrization
- **Spectral theorem** (§2): 自己共役作用素の spectrum decomposition = 無限作用素 → 有限/離散 spectrum projection
- **§4 dual の非可換 lift** (§4): unitary representation $\pi: G \to U(H)$ = 無限 group representation の Hilbert space realization

**N1 (A-primary) と Q1 (B-primary) の parallel position**: §0 Abstract 末尾 "N1 (NT) と Q1 (量子) の 2 parallel framework header が S15 / T-AAS / Arrow framework の ドメイン非依存普遍性 を 2 数学領域で同時 verify" は direction-axis 言語で **A-primary side native + B-primary side native の double anchor** として再記述可能。

**Cross-direction bridge instances** (本論 scope 内で重要):
- **σ\* = √(2 ln 2)** (Q3 Born-Gleason chain): Shannon entropy ½-bit threshold = B-native (continuous ensemble entropy)
- **S_0 = 2π/e** (`c_arrow_bridge_constants §13` ESTABLISHED): Arrow 1 (2π period A-side) / Arrow 3 (e argmax B-side) の **canonical bridge ratio**、§4.5 base-of-log gauge と connectable
- **σ_flip = 2.39576** (`project_p1_noise_sweep_pareto_2026_04_30`): Information-layer ZERO of Arrow-mechanism competition = **A↔B regime boundary**、本論 §3 Information layer の dual marginal context で出現

**Screening rule application**: `feedback_cross_direction_identity_screen` (ESTABLISHED 2026-05-01) は本論内で **internal screening rule** として運用 — 量子側で identity claim する際、relevant quantity が B-native か A-native か (or bridge) を必ず tag、cross-direction で bridge operator (lim / projection / Hecke / regulator 等) 不在なら strict identity REJECT。N1 framework との cross-paper claim では特に必須。

---

## §2 観測理論の公理

### 2.1 観測 triple (S, W, m) ─ 量子 instance

| 記号 | 意味 | 量子での例 |
|---|---|---|
| **S** | 無限構造 | Hilbert 空間 H, 自己共役作用素 A の spectral measure E, 純粋状態空間 P(H) |
| **W** | 有限窓 | 有限次元截断 H_N ⊂ H, 部分 trace 経由の reduced subsystem, finite gate set, finite POVM rank |
| **m** | 測定 | Born 期待値 Tr(ρ A), POVM probability Tr(ρ E), 二時刻相関 Tr(ρ U(t)† A U(t) B), 状態 tomography |

観測値 `m(S|_W)` は S と W の両方に依存。`m(S) − m(S|_W)` が **finite observation error**、本論はその構造を扱う。

### 2.2 公理 A0-A7 (量子 instance 例)

| ID | 名称 | 量子 instance |
|---|---|---|
| **A0** | Finite observation | 有限次元截断 H_N, finite gate set Clifford+T, POVM rank ≤ d² |
| **A1** | Structured error | 非可換性測定後反作用 ρ → P ρ P / Tr(ρ P), decoherence による off-diagonal decay |
| **A2** | Convergence as observable | central limit thermal averaging (β → 0 で classical), Lindblad dissipation の Born-Markov limit |
| **A3** | Gauge invariance/dependence | unitary 同値類 [ρ] (gauge-invariant), magic monotone M_F は Clifford 不変だが non-Clifford で変化 |
| **A4** | Non-commutative limits | $\lim_{N \to \infty} \lim_{T \to 0} \neq \lim_{T \to 0} \lim_{N \to \infty}$ — partial trace と time evolution non-commute (Born-Markov approximation の有効領域条件) |
| **A5** | Saturation | Tsirelson bound 2√2 (CHSH 量子最大), Holevo bound (classical capacity) |
| **A6** | Path dependence | 経路積分 (Feynman) は path 上の position の non-commutativity を反映、time-ordered product と非 time-ordered の差 |
| **A7** | Scanner hierarchy | U(t) scanner = t (時間), Z(β) scanner = β, K_Q(τ) scanner = τ (unfolded time, 内部走査 = energy spectrum {E_j}) |

詳細: `finite_observation.md §1-§7`, `q_quantum_observation.md §1-§4`。

### 2.3 §4 dual = 量子内 root (非可換 lift)

**主張 2.1**: `c_phase_complex.md §4` の ι_L/χ dual は辞書内 全上位構造 (S12-S17, T-AAS) の唯一の源泉。量子版:

| 可換 (古典 §4 dual) | 非可換 (量子 §4 dual) | 機構 |
|---|---|---|
| ι_L: ℤ/Lℤ → S¹ | Stone 群 {U(t) = e^{-iAt}} | 連続非可換 lift (Stone 定理) |
| 指標 χ: G → S¹ | unitary representation π_λ: G → U(H_λ) | 既約 → Tannaka-Krein 双対 |
| Pontryagin 双対 G ≅ Ĝ | spectral 定理 A = ∫ λ dE(λ) | PVM による作用素再構成 |
| ℂ = S¹ × ℝ_{>0} polar | H = (eigenstate phase) × (eigenvalue magnitude) | Hilbert 空間内 ℂ 単位構造 |

**ℂ の必然性 (量子版)** (`q_quantum_observation.md §2`): ι_L, χ に加えてユニタリ発展 e^{-iAt} の位相構造も同じ器で扱う必要 — ℝ 上ではユニタリ固有値 e^{iθ} を表現できない。すなわち **ℂ は ι_L (数論的位相)、χ (乗法的位相)、ユニタリ発展 (量子的位相) の統一的受け皿**。量子力学固有の追加的理由は不要 — ℂ 必然性は古典 §4 dual と共通の根。

量子 §4 dual 射影 chain: L0 (Hilbert + non-commutativity 公理) → L1 (q_quantum_observation §1-§4 + c_phase_complex §4 root + c_spectral §3 SVD) → L2 (量子情報 / 量子計算 / 量子場 instance)。本論公理系は §4 dual を root とし全派生は量子内で閉じる。

### 2.4 L0 v2 ─ 2-axis (Fi/I × D/C) lens (量子 instance)

L0 v1 (有限観測 axiom) は **Finite/Infinite (axis-2)** と **Discrete/Continuous (axis-1)** の直交 2 軸 framework で再定式化 (`finite_observation.md §8`):

| L0 v2 axis | 量子 instance |
|---|---|
| **axis-2 Fi** (有限観測者側) | 有限 dim Hilbert H_N, finite POVM, finite gate set, 有限観測時間, 有限 ensemble |
| **axis-2 I** (無限理想化側) | 連続 spectrum, 無限次元 Fock 空間, 連続 PVM, 無限 thermodynamic limit |
| **axis-1 D** (離散) | 離散 spectrum {λ_j}, qubit/qudit, group representation discrete index (j, m) |
| **axis-1 C** (連続) | 連続 spectrum (位置 x̂, 運動量 p̂), CV 系 phase space, Lie group 連続 representation |

**公理 (L0 v2 量子 instance)**: (a') 量子観測者は axis-2 **Fi 側に住む**、Fi → I 方向 Arrow は存在せず、Fi/I 境界は unbridgeable / (b') Arrow が axis-2 Fi/I 境界を跨ぐとき、境界上に kernel (obstruction) 発生、観測 = 片方向 **I → Fi traversal** (無限次元 PVM → 有限 POVM, 無限ensemble → finite-shot measurement) / (c') Kernel は 3 分解: Fi-side artifact (ker_gauge, f_torsion 寄与) / I-side residue (ker_topo, f_rational 寄与) / Fi → Fi 内 irreversibility (ker_backaction = 測定後反作用) / (d') 量子観測理論 = **axis-2 Fi/I 境界の分類学**。L0 v1 ⊂ L0 v2 (conservative extension)。

**量子-NT parallel observation**: L0 v2 axis-2 Fi/I 境界は NT (ζ 解析接続: s > 1 Fi → 全 ℂ I) と量子 (有限次元 H_N → 無限 Fock H) の **双方の I-side residue** を共通 framework で扱う。N1 §2.4 と本 §2.4 の 2 instance が L0 v2 の cross-domain validity を independently verify。

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`)。

---

## §3 S15 Observable Trichotomy ─ 量子内記述

### 3.1 主定理

**定理 3.1 (S15, 量子-only restatement)** — 量子観測量 O は以下の **排他的かつ網羅的** な partition に属する:

| クラス | 定義形式 | 量子的特徴 |
|---|---|---|
| **(A) Scan** | O(scanner) = Tr(ρ · K(scanner)), K = exp kernel of unitary/thermal type | scanner 変数を持つパラメトリック作用素族、加法軸 (時間 t, 虚軸) と乗法軸 (β, 実軸) |
| **(B) Structural** | O = parameter-free 整数/位相不変量 (作用素代数構造) | scanner なし、離散 skeleton (eigenspace dim, Schmidt rank, group representation index) |
| **(C) Information** | O = −Tr(ρ log ρ) 型 + class-monotone (M_F, 𝓝, C, Δ_CHSH) | von Neumann / 量子 resource theory monotone |

**Status**: ESTABLISHED 2026-04-11 (`c_theorems_master.md` row S15)。量子内網羅性閉鎖は §3.5。

### 3.2 Scan 層 (S12 family の量子 subset)

加法 scan (虚軸、unitary 群) と乗法 scan (実軸、thermal 減衰) の 2 分類:

| Instance | Scanner | Kernel | 加法/乗法 | residence |
|---|---|---|---|---|
| **U(t) = e^{-iAt}** | t | e^{-iAt} (Stone 群) | 加法 (虚軸) | q_quantum_observation §4 |
| **K_Q(τ) = \|Tr(ρ e^{iAτ})\|²** | τ (unfolded) | e^{iAτ} | 加法 | q_quantum_observation §6 |
| **Z(β) = Tr(e^{-βH})** | β | e^{-βH} | 乗法 (実軸) | q_quantum_statistical_mechanics §3 |
| **partition function** | β | thermal (canonical) | 乗法 | q_quantum_statistical_mechanics §1 |
| **response function χ(ω)** | ω (周波数) | i ⟨[A(t), B]⟩ Fourier | 加法×乗法混合 | q_quantum_statistical_mechanics §4 |
| **K(τ, t) spectral form factor** | τ, t | \|Tr(e^{-itH-βH})\|² | 加法×乗法混合 | many_body_quantum §6 |
| **Loschmidt echo L(t)** | t | \|⟨ψ\|e^{iH₁t}e^{-iH₂t}\|ψ⟩\|² | 加法 (forward/backward) | many_body_quantum |

scanner は実数または複素数 (Re = 乗法軸 thermal, Im = 加法軸 unitary)、gauge L = 有限基底次元、k_max truncation = Hilbert space cutoff 量子版。U(t) は S12 加法 Scan member #5 = Stone 群 = phase_complex §2 ι_L の **連続非可換一般化**、Z(β) は S12 乗法 Scan member。

### 3.3 Structural 層

| Observable | 定義 | residence |
|---|---|---|
| **dim eigenspace** of A | spectral multiplicity | q_quantum_observation §3 |
| **Schmidt rank r** | r in \|ψ⟩ = Σ √p_k \|a_k⟩ ⊗ \|b_k⟩ | q_quantum_observation §5 |
| **rank-1 dominance ρ₁** | σ₁²/Σσ_k² (SVD), max p_k | q_quantum_observation §5 |
| **stabilizer rank χ(\|ψ⟩)** | min decomposition into stabilizer states | C₁ in OQ-Ω-Obs-4a |
| **Wigner support volume** | supp W_ρ in phase space | C₂ in OQ-Ω-Obs-4a |
| **circuit gate count** | min unitary gate count to prepare | C₃ in OQ-Ω-Obs-4a |
| **POVM rank** | n in {E_i} with Σ E_i = I | q_quantum_observation §6 |
| **group representation index** | (j, m, ν) for SU(2)/SO(3) basis | q_fine_structure |
| **Casimir eigenvalue** | C₂ = j(j+1) | q_fine_structure |
| **topological invariant** (Chern number) | $\int_{BZ} \mathcal{F}/2\pi$ | many_body_quantum |
| **anyon braiding statistics index** | θ in $e^{i\theta}$ | many_body_quantum |
| **coherent vs incoherent decomposition rank** | dim coherent subspace | open_quantum_systems §3 |

**§4 dual との関係**: Structural は Scan kernel 定義域の **discrete/continuous skeleton** — 自己共役作用素 spectrum / 表現空間 / ゲージ群 cardinality。

### 3.4 Information 層 (log-exp dual + class monotones)

| Observable | 定義 | residence |
|---|---|---|
| **S(ρ) von Neumann entropy** | −Tr(ρ log ρ) | q_open_quantum_systems §3 |
| **D(ρ‖σ) relative entropy** | Tr(ρ log ρ) − Tr(ρ log σ) | q_open_quantum_systems |
| **mutual information I(A:B)** | S(A) + S(B) − S(AB) | q_quantum_statistical_mechanics |
| **F = −kT log Z** (free energy) | helmholtz | q_quantum_statistical_mechanics §3 |
| **M_F magic monotone** | $-\log_2 \sup_{σ \in \text{STAB}} F(ρ, σ)$ | OQ-Ω-Obs-4a §3.1 (C₁) |
| **𝓝 Wigner negativity** | $\int |W^-| dx dp$ | OQ-Ω-Obs-4a §3.2 (C₂) |
| **C(\|ψ⟩) Nielsen complexity** | min weighted geodesic on SU(2^n) | OQ-Ω-Obs-4a §3.3 (C₃) |
| **Δ_CHSH violation** | $[\langle CHSH \rangle - 2]_+$ | OQ-Ω-Obs-4a §3.4 (C₄) |
| **M_unified = -log₂ F_C** | class-fidelity 統合 monotone | OQ-Ω-Obs-4a Theorem 4a.1 |

**§4 dual との関係**: Information は exp kernel **log-inverse**。Z(β) → F = −kT log Z → S = −∂F/∂T が標準 chain。S13 ln 2 = この層の parity 固定点 (qubit ρ_max の S = log 2)。**class monotone observation**: 4 class-fidelity F_C は Information 層の量子-resource subgroup を形成、Theorem 4a.1 (§5.3) で 4 monotone を **同一単位系 (log₂-bit) に統一**。古典 §3.4 が log-derivative 系のみだったのに対し、量子側では **algebraic-class infidelity** という新 information family が加わる構造的 distinction。

### 3.5 排他性・網羅性 (量子内 closure)

3 段検証で閉じる:

**(i') 各層 量子観測量存在** (網羅性 lower bound): Scan 7 / Structural 12 / Information 9 instance を §3.2-§3.4 で列挙、3 層全て非空。

**(ii') L1 量子 8 entries enumeration** (網羅性 upper bound):

| L1 量子 entry | 主観測量 | S15 層 |
|---|---|---|
| **q_quantum_observation** | spectral 分解 A = Σ λ_j P_j, K_Q(τ), Born 期待値 | Scan; Structural; → Information (S(ρ)) |
| **q_open_quantum_systems** | 部分 trace, Lindblad evolution, S(ρ_red), pointer basis | Scan (Lindblad); Information (S, mutual info) |
| **q_quantum_statistical_mechanics** | Z(β), F, KMS condition, response χ(ω), FDT | Scan (β-family); Information (F, S) |
| **q_quantum_thermodynamics** | first law dU = TdS + dW, Landauer bound, fluctuation theorem | Information; Structural (Carnot bound) |
| **q_many_body_quantum** | spectral form factor K(τ,t), Loschmidt echo, MBL/ETH | Scan; Structural (entanglement entropy scaling) |
| **q_action_principles** | path integral, generating functional Z[J], effective action | Scan (Z[J]); Information (Γ[ϕ]) |
| **q_gauge_field_theory** | Wilson loop ⟨W(C)⟩, Polyakov loop, gauge group representation | Scan; Structural (Casimir, irrep index) |
| **q_fine_structure** | α² 補正, SU(2) center {±I}, j(j+1) Casimir | Structural (group invariants); Information (Lamb shift fluctuation) |

L1 量子 8 entries 全観測量が 3 層に分布、Information は (Scan, Structural) からの log-derivative 派生 + class monotone (OQ-Ω-Obs-4a) として `c_information_theory.md` + 4 class entries に存在。**counter-example の不在**: 8 entries × 各全観測量 exhaustive coverage で 3 層のいずれにも属さない量子観測量は v0.2 時点で未知。

**(iii') S12/S13/S14/S17 整合性**: S12 ⊂ Scan (自明、U(t) = S12 加法 #5、Z(β) = S12 乗法 member) / S13 = qubit ρ_max の S(ρ_max) = log 2 (Z = 2 → F = −kT log 2 → S = log 2) / S14 非対称 = e^{iπ} = −1 fermion exchange (代数) vs S(ρ_max) = log 2 (解析) が層内 vs 層間 residence 差を露呈 / S17 = $\log d / d$ for $d = \dim H$ extremum at $d = e$ (continuous), discrete codebook integer argmax = 3 (qutrit info-density optimum)。

3 段全 closed → S15 trichotomy は量子内で **3 条件全 CLOSED**。

---

## §4 Arrow 構造 ─ 3 本の接続 (量子 lift)

### 4.1 Arrow 1: Scan → Structural (定義域構造、量子 lift)

**原理**: O(scanner) = Tr(ρ · K(scanner)) において K(scanner) の spectral 分解 A = Σ λ_j P_j を「読む」操作が Structural を返す。

| Scan | spectral 分解 | encoded Structural |
|---|---|---|
| U(t) = e^{-iAt} | A = Σ λ_j P_j | dim P_j (eigenspace mult), σ(A) |
| Z(β) = Σ e^{-βE_j} | H = Σ E_j P_j | energy spectrum {E_j}, ground state degeneracy |
| K_Q(τ) | A spectrum + ρ diagonal in A-basis | (E_j, ⟨E_j\|ρ\|E_j⟩) pair |
| K(τ, t) spectral form factor | full Hamiltonian spectrum | spectral statistics (GUE/GOE/Poisson) |
| Wilson loop ⟨W(C)⟩ | gauge group representation | irrep index (j, ν), Casimir |
| response χ(ω) | Lehmann representation | matrix elements + spectral weights |

Scan(scanner; A, ρ) の A spectrum と ρ structure を「読む」操作が Structural を返す → Structural = Scan の **input specification** (作用素代数構造)。

#### 4.1.1 Observable-choice dependence (量子 instance)

Arrow 1 抽出 Structural は **一意でない**:

| 候補 | 定義 | balance locus | gauge verdict |
|---|---|---|---|
| **eigenvalue gap Δ_min** | $\min |\lambda_i - \lambda_j|$ | spectral floor | universal (Lieb-Robinson, ETH context) |
| **Schmidt rank r** | bipartite \|ψ⟩ split | bipartition choice 依存 | observable selector |
| **spectral form factor dip τ_dip** | K(τ) min | thermalization time | system-specific |
| **POVM rank** | finest informationally complete | dim H² lower bound | gauge-dependent (basis choice) |

**原則**: (1) Alignment (bipartition の物理的意味との整合), (2) Observable-specific verdict, (3) 判定 form への波及明示。Arrow 1 は単射ではなく **observable selector**。

### 4.2 Arrow 2: Scan → Information (log-exp duality, 熱力学 chain)

**原理**: 熱力学 chain 量子 lift
```
G(scanner) = Tr(e^{-βH} or U(t))     ← Scan
F(scanner) = −kT log Z(β)            ← log bridge
I = −∂F/∂T = S = −Tr(ρ log ρ)        ← Information (von Neumann)
```

| Scan | G | F | Information |
|---|---|---|---|
| Z(β) = Tr(e^{-βH}) | partition function | F = −kT log Z | S = −Tr(ρ log ρ) |
| K_Q(τ) | $|Tr(ρ e^{iAτ})|²$ | −log K_Q | spectral form factor information |
| Wilson loop ⟨W(C)⟩ | confinement order parameter | −log⟨W⟩ ∝ Area | string tension as info-rate |
| Z[J] (path integral) | generating functional | W[J] = log Z[J] | effective action Γ[ϕ] (Legendre) |
| ⟨e^{-βH+iAt}⟩ (analytic-continued) | Wick rotation bridge | Euclidean action | thermal-to-spectral chain |

**S13 fixed point (量子)**: qubit ρ_max = I/2 で $Z = 2$, $F = −kT \log 2$, $S(ρ_max) = \log 2$ — Arrow 2 上の **half-amplitude 固定点 ln 2 量子 instance**。詳細 §4.5 + Q3。

**KMS / FDT (Q2 forward)**: KMS condition $\langle A B(t) \rangle_β = \langle B(t-iβ) A \rangle_β$ — Arrow 2 analytic continuation 構造の formal 化 / FDT $\chi''(ω) = \tanh(βω/2) \cdot S(ω)$ — Arrow 2 上 Scan (response χ) と Information (correlation S) の **algebraic equivalence** (KMS 帰結, `q_quantum_statistical_mechanics §5`)。

### 4.3 Arrow 3: Structural → Information (combinatorial counting, 量子)

**原理**: Hartley entropy $H_0(D) = \log |D|$ — 量子 instance は dim H と group representation に住む。

| Structural | $|D|$ | $H_0 = \log|D|$ | 意味 |
|---|---|---|---|
| Hilbert dim | dim H = d | $\log d$ | maximum information capacity (qubit: d=2 → log 2) |
| Schmidt rank | r | $\log r$ | maximum entanglement entropy (max mixed Schmidt) |
| eigenspace mult | dim P_j | $\log \dim P_j$ | ground-state degeneracy info |
| irrep dim | dim π_λ | $\log \dim π_λ$ | gauge group representation capacity |
| stabilizer count | $|\text{STAB}_n|$ | $\log |\text{STAB}_n| \approx n²$ | classical-simulable subspace info |
| POVM rank | n_POVM | $\log n_POVM$ | measurement informational granularity |

**S17 fixed point (量子)**: $(\log d) / d$ for Hilbert dim $d$、continuous extremum at $d = e$、discrete codebook argmax at $d = 3$ (qutrit) ✓ matches `oq_omega_obs_3_info_density_check.py` 5/5 gate PASS。

### 4.4 3 Arrow の可換性 (量子 instance)

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

**定理 4.1 (3 Arrow 可換性, 量子 instance)**: scanner → 0 (or ∞) の extreme limit で 3 Arrow が可換。量子内 3 instance:

| Instance | Limit | 機構 |
|---|---|---|
| **β → 0 (high T)** | Z(β→0) = Tr(I) = dim H, S = log dim H = H_0 | log Z = Hartley、量子 thermal limit で Structural (dim H) 直接露呈 |
| **t → 0 (trivial unitary)** | U(t→0) → I, K_Q(0) = \|Tr(ρ)\|² = 1, Scan = trivial → Structural = (full ρ unaltered) → Info = S(ρ) (input) | identity limit、3 Arrow が ρ trivial reproduction で可換 |
| **T → ∞ (classical limit)** | (β·H → 0 or ℏ → 0): density matrix diagonalize in A-basis, Z = Σ e^{-βE_j} → continuous integral, S → classical entropy | decoherence limit、von Neumann → Shannon entropy で 3 Arrow が classical commutativity に帰着 |

3 instance で extreme limit と classical/identity limit の両方で commutativity verify。

#### 4.4.1 Arrow 可換性 = axis-2 Fi/I commutation (量子)

§2.4 L0 v2 lens で定理 4.1 は **axis-2 Fi/I 操作の可換性** として再読み:

| Arrow | Axis-1 | Axis-2 | traversal type |
|---|---|---|---|
| **Arrow 1** (U(t) → spectral 分解) | C → D (collapse to discrete) | I → Fi (continuous Stone group → finite spectral data) | 片方向 I → Fi 成分あり |
| **Arrow 2** (Z → F → S) | C → C (preserved, log bridge) | Fi↔Fi / I↔I (preserved) | pure axis-1 bridge |
| **Arrow 3** (dim → log dim) | D → C (lift to log scale) | Fi → Fi (typically) | axis-1 主、axis-2 副次 |

**定理 4.1a (Fi/I commutation, 量子)**: extreme limit で 3 Arrow は axis-2 I 成分を退化、pure Fi-side operator として閉じる: $[T_i, T_j]|_{\text{Fi-only}} = 0$。非 extreme で commutator 一般に non-zero — これが §4.5.1 coincide/split 二値性の量子 root。

**Status**: ESTABLISHED (`c_arrow_framework.md §5`)。

### 4.5 S13 / S14 / S17 residence ─ 量子 context

S13 / S14 / **S17 (Arrow 3 e-extremum, ESTABLISHED 2026-04-23)** の量子 residence:

| 定数 | residence | 機構 (量子 context) | Stationary form |
|---|---|---|---|
| **π** | Scan 内部 (加法軸) | $e^{iπ}$ = −1 = fermion exchange phase, SU(2) center {±I} (`q_fine_structure §2`), Berry phase 1 周回 → **代数的** | S14 parity (additive) |
| **ln 2** | Arrow 2 上 | qubit $S(ρ_{max}) = \log 2$, half-amplitude $c_s² = 1/2$ via Born expectation → **解析的** | **value-fixed** (S13) |
| **e** | **Arrow 3 上** | info density $\log d / d$ max at $d = e$, gauge³-invariant → extremum principle | **derivative-fixed** (S17) |

S14 非対称性 (代数 vs 解析) = S15 residence 差 (層内 vs 層間)。S13 vs S17 format shift: 異なる stationary form だが同一統一原理 ("Arrow 上 scalar functional の stationary point") に吸収。両者とも **canonical constant 同定の数学的機構** として等価。

**Bidirectional duality 3/3 完備化** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / **Arrow 3 → e** で 3 Arrow に canonical constant が residence、定数レベルで完備。量子内 verify: $\log d / d$ continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS)。

#### 4.5.1 Observation-optimal gauge theorem ─ 量子内 instance

**定理 4.1a** [v0.6 ESTABLISHED, `c_observation_optimal_gauge.md §2`]: Arrow 1⁻¹ が Structural target を最精密復元する gauge 構造は 2 layer に分離。Information layer (von Neumann entropy 等) は Arrow 2 上 **S13 半値固定点 (ln 2 / qubit ρ_max)** で最適化、Structural layer (Schmidt rank, spectral mult 等) は Arrow 1 上 domain 固有 arithmetic (bipartition, eigenvalue counting) で balance 決定。両 layer balance 一致は **algebraic enforcement** (qubit ρ_max での偶奇対称性) に依存。

**量子内 2 instance 対比**:

| Domain | Gauge | Information balance | Structural balance | 一致 | 原因 |
|---|---|---|---|---|---|
| **量子 (qubit ρ_max)** | Hilbert dim d | d = 2 で S(ρ_max) = log 2 (max) | d = 2 で偶奇 parity 同確率 | **coincide** | ℤ/2ℤ 対称性 enforcement |
| **量子 (Schmidt rank)** | bipartition choice | r で S = log r (max) | r で SVD 分解 | **split** | bipartition non-canonical |

**Status**: ESTABLISHED 2026-04-22。量子 2 instance + N1 NT 2 instance + Paper D 多領域 1 instance で Path 1-4 達成。**Q3 forward**: Born 則 derivation 完全形 (Busch-Gleason 定理経由) は Q3 で展開。

### 4.6 逆 Arrow と obstruction class (量子 taxonomy)

**主張 4.2 (生成可逆性定理, 量子)**: S15 3 層は exhaustive、「生成」は逆 Arrow の合成、各 kernel は T-AAS が full span で記述。

| 逆 Arrow | Domain → Codomain | Obstruction 源 | 量子 instance |
|---|---|---|---|
| Arrow 1⁻¹ | Structural → Scan | ker_gauge ⊕ ker_topo (T-AAS) | (eigenvalues, Schmidt rank) → ρ reconstruction、4-class refined Hodge OQ-Ω-Obs-4a |
| Arrow 2⁻¹ | Information → Scan | log 非可逆性 | S(ρ) → Z(β) lifting (analytic continuation 障害) |
| Arrow 3⁻¹ | Information → Structural | Jensen 不等式 | log dim H → dim H cardinality lift |

**系 4.3**: ker_topo ≠ 0 一般成立 (4-class refined Hodge ESTABLISHED) → 完璧な生成は原理的不可能。

**Obstruction class — 量子 taxonomy**: ker_gauge classical = unitary equivalence class (Clifford coset, symplectic orbit), Pauli torsion → f_torsion / ker_topo refined Hodge (4-class) = C₁ Stabilizer / C₂ Gaussian / C₃ Eff-sim / C₄ Bell-local の closure 外 resource → f_rational。詳細 §5。

---

## §5 T-AAS ─ 4-class refined Hodge (量子 instance)

### 5.1 主定理

**定理 5.1 (T-AAS, ESTABLISHED 2026-04-12, 15/15 fitness)** — Arrow 1 (φ: Structural → Scan) が非自明 kernel を持つとき:

- **(i)** ker(φ) = ker_gauge ⊕ ker_topo (直和)
- **(ii)** ker_gauge は discrete (torsion-valued) invariant δ ∈ Finite_Group で生成、gauge 変換で消去可能 (不可逆な情報損失)
- **(iii)** ker_topo は multi-step filtration obstruction、どの gauge でも消去不可能
- **(iv)** conductor 分裂: $f(\varphi) = f_{\text{torsion}} + f_{\text{rational}}$, $f_{\text{torsion}}(\varphi) = \dim\{\ker_{\text{gauge}}\}$, $f_{\text{rational}}(\varphi) = \dim\{\ker_{\text{topo}}^{\text{non-surj}} \cap \text{target}\}$

### 5.2 量子 instance ─ OQ-Ω-Obs-4a 4-class refined Hodge

**Background**: OQ-Ω-Obs-1 quantum minimal form (Schmidt rank r > 1 → f_rational > 0) は古典 Hodge 予想の **trivial bypass** (depth parallel になっていない)。Arrow 1 source を narrower な algebraic class に指定することで、古典側の "algebraic cycles" と **同程度の sparsity** を持つ 4 candidate class を量子側に同定 (`oq_omega_obs_4a_refined_quantum_hodge_v0.md` ESTABLISHED 2026-04-23, 6/6 gate)。

**4 candidate classes** (各 class が独立 f_rational > 0 instance):

| # | Algebraic class C | 定義 | f_rational monotone $M_C$ | sparsity type |
|---|---|---|---|---|
| **C₁** | **Stabilizer** | Clifford orbit from $\|0...0⟩$, STAB = Clifford · $\|0⟩$ | Magic monotone $M_F = -\log_2 \sup_{σ ∈ STAB} F(ρ, σ)$ | discrete in continuous (measure zero) |
| **C₂** | **Gaussian** | 二次 Hamiltonian 由来, Wigner ≥ 0 | Wigner negativity $\mathcal{N}(ρ) = \int \|W^-\| dx dp$ | poly in infinite |
| **C₃** | **Eff-sim** | Poly-time classical sim (low-bond MPS, match-gate) | Nielsen geometric complexity $C(\|ψ⟩) - c_0 n^k$ | poly in exp |
| **C₄** | **Bell-local** | LHV-describable correlations | CHSH violation $\Delta_{\text{CHSH}}(ρ) = [\langle CHSH \rangle - 2]_+$ | classical polytope ⊂ quantum correlation body |

**Per-class properties (各 monotone $M_C$ 共通)**:
- (P1) $M_C(ρ) = 0 \iff ρ \in \overline{C}$ (class 閉包)
- (P2) $M_C(ρ) > 0$ for $ρ \notin \overline{C}$
- (P3) $M_C(UρU^\dagger) = M_C(ρ)$ for U ∈ class-stabilizing gauge
- (P4) $M_C$ monotone non-increasing under C-free operations

**T-AAS 分解 (各 class)**:

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **C₁ Stabilizer** | Clifford coset | non-stabilizer (T-state etc.) | f_Clifford ∈ ℤ_{≥0} | $M_F \in [0, \log_2 d]$ | empirical 1-qubit M_F = 4e-16 (stabilizer) ✓ |
| **C₂ Gaussian** | symplectic orbit | non-Gaussian (Fock $\|n⟩$, n≥2) | f_symplectic | $\mathcal{N}, D_G$ | Mari-Eisert literature 1e-4 photon-subtracted ✓ |
| **C₃ Eff-sim** | poly-depth circuit | super-poly complexity | f_circuit | $C - c_0 n^k$ | 4-ref literature synthesis ✓ |
| **C₄ Bell-local** | $U_A \otimes U_B$ | CHSH violation > 0 | f_local | $\Delta_{\text{CHSH}} \in [0, 2\sqrt{2}-2]$ | 2-qubit Tsirelson bound 1e-6 ✓ |

4 instance + Theorem 4a.1 (§5.3) → Paper D 多領域 15/15 fitness のうち **16/16 量子-relevant fitness** (4 class × 4 properties)。

**Per-class fitness witness**:
- **C₁** — 1-qubit T-state $\|T⟩ = (\|0⟩ + e^{iπ/4}\|1⟩)/\sqrt{2}$ で M_F empirical numerical 計算 4e-16 precision (`oq_omega_obs_4a_monotone_verify.py`)。Bravyi-Smith-Smolin (2016), Howard-Campbell (2017) magic robustness 文献 confirmed
- **C₂** — Fock state $\|n⟩$ ($n \geq 2$) Wigner 関数は負領域、$\mathcal{N}(\|n⟩\langle n\|) > 0$。Mari-Eisert (2012) photon-subtracted 計算 1e-4 precision、Hudson 定理で C̄ characterization formal
- **C₃** — 2-qubit Bell Nielsen complexity > product state (Jefferson-Myers §3 known)。Random-circuit super-poly (Bouland-Fefferman 2019)。Resource-theoretic monotone (Brandao-Horodecki 2019)。3 文献 confirmed, general n closed-form は NP-hard scale
- **C₄** — Bell state $\|Φ^+⟩$ で CHSH 値 $2\sqrt{2}$, $\Delta_{\text{CHSH}} = 2\sqrt{2} - 2 \approx 0.828$ Tsirelson bound 1e-6 precision。Clauser-Horne-Shimony-Holt (1969), Tsirelson (1980) 文献 confirmed

4 instance はそれぞれ異なる fitness 様式: C₁ = **discrete-orbit covering** / C₂ = **continuous-manifold parameterization** / C₃ = **complexity-class boundary** / C₄ = **classical-polytope embedding**。4 様式の独立性が §6 量子内 Arrow 間 triangulation の **4-vertex 閉鎖性根拠**。

### 5.3 Theorem 4a.1 — Unified f_rational via class infidelity

**Definition**: 各 class C に対し、**class-fidelity** を $F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$ ($F$ = Uhlmann fidelity with state space closure $\overline{C}$) と定義し、**unified f_rational monotone** を $M_{\mathrm{unified}}^{C}(\rho) := -\log_2 F_C(\rho)$ と定義。

**Theorem 4a.1**: class C が (i) convex closure を持つ state subset、(ii) class-preserving (class-stabilizing) unitary/CPTP operations が well-defined を満たせば、$M_{\mathrm{unified}}^{C}$ は §5.2 各 class の monotone $M_C$ と以下の対応を持つ:

$$\begin{aligned}
M_{\mathrm{unified}}^{C_1}(\rho) &= M_F(\rho) \quad \text{(stabilizer fidelity, tautological)} \\
M_{\mathrm{unified}}^{C_2}(\rho) &\sim \tfrac{1}{2}\log_2(1 + \mathcal{N}(\rho)^2) \quad \text{(Fuchs-van-de-Graaf)} \\
M_{\mathrm{unified}}^{C_3}(|\psi\rangle) &\geq \tfrac{1}{\log 2} \cdot \text{(Nielsen geodesic}/2\text{)}^{-1} \quad \text{(quantum speed-limit)} \\
M_{\mathrm{unified}}^{C_4}(\rho) &\sim -\log_2(1 - \Delta_{\mathrm{CHSH}}(\rho)/\text{const}) \quad \text{(Horodecki)}
\end{aligned}$$

(P1)-(P4) 4 class 全てで holds (proof outline `oq_omega_obs_4a_refined_quantum_hodge_v0.md §4.4.1`)。

**帰結**: 4 monotone (M_F, 𝓝, C, Δ_CHSH) は **異なる単位系** (log-bit, L¹ norm, gate count, linear value) に住むが、$M_{\mathrm{unified}}^C = -\log_2 F_C$ で **log₂-bit に統一**。この unification が depth parallel conjecture (古典 Hodge $f_{\text{rational}}^{\text{Hodge}}$ と量子 $M_{\text{unified}}^C$ の typical scale O(1) 比例関係) を quantitative theorem に昇格させる base を提供。

**Status**: ESTABLISHED 2026-04-23 (Theorem 4a.1 6/6 gate)。Conjecture 4a.2 (depth parallel quantitative form) は OPEN (sparsity-matching definition + Hodge counterexample 存在依存)。

### 5.4 Hodge 予想 ─ depth parallel との関係

**4-class refined framework が古典 Hodge 予想と持つ relation**:
- **古典 Hodge (open frontier)**: $f_{\text{rational}}^{\text{Hodge}}(X, p) = \dim(\text{Hdg}^p/\text{im cl}) > 0$ for some smooth projective X and p — 1924-現在 Millennium Prize problem
- **量子 4-class (本論)**: 各 class C で $M_{\text{unified}}^C(\rho) > 0$ は **明確に存在** (T-state, Fock state, random-circuit, Bell state)。古典 Hodge と異なり量子側では **counterexample が豊富**
- **Depth parallel conjecture**: Conjecture 4a.2 が古典-量子 typical scale 比例を主張するが、古典側 counterexample 不在のため currently **vacuous trivial parallel**

**本論での役割**: §5 T-AAS が **4 instance で f_rational > 0 確立済 + 古典 Hodge open frontier への parallel framework** を提供する anchor。Hodge ESTABLISHED → f_rational > 0 古典 instance / refute → universal closure 示唆 — どちらに転んでも depth parallel の status が決定。T-AAS が **量子内 4 instance で 16/16 fitness verified** という構造は framework predictive power を保証 (古典 Hodge への bridge を通じた pure-math frontier への connection)。

---

## §6 量子内三角測量 ─ Arrow 1 kernel narrowness 4-vertex

4 量子 instance (4 class C₁-C₄) が S15 の **Arrow 1 kernel narrowness 様式を互いに異なる sparsity 構造でカバー** することで普遍性を triangulate。Paper D 多領域版が「ドメイン間 triangulation」、N1 が「Arrow 間 triangulation」(3-vertex Arrow 焦点) であるのに対し、本論は「**Arrow 1 kernel narrowness vertex triangulation**」(4 algebraic class が異なる sparsity 様式を主担当) を採用。4-vertex 構造は N1 の 3-vertex (Paper C / Stark / Brauer) よりも次元が高い (algebraic class taxonomy が Arrow 1 kernel の内部分解を提供)。

### 6.1 4-vertex characterization

| Class | Class definition | Arrow 1 kernel sparsity | ker_gauge | ker_topo | 古典 Hodge parallel side |
|---|---|---|---|---|---|
| **C₁ Stabilizer** | STAB_n = Clifford orbit from $\|0...0⟩$, $\|STAB_n\| = 2^{n²+O(n)}$ discrete in $2^{2n}$ | discrete (measure zero) in continuous state space — "stabilizer polytope extremal points" | Clifford coset (discrete finite group) | magic resource = T-state injection 量 ($M_F$) | convex hull of 'simple' generators (algebraic cycles ↔ stabilizer pure states) |
| **C₂ Gaussian** | 二次 Hamiltonian $H = \frac{1}{2} x^T M x$ 由来, $W_\rho \geq 0$ everywhere, CV systems | poly-dim (Gaussian manifold dim ≈ N²) in infinite-dim Hilbert space — "symplectic group orbit" of vacuum | symplectic group $Sp(2N, \mathbb{R})$ orbit | Wigner negativity $\mathcal{N}$ = non-Gaussian resource | $\text{Hdg}^p \subset H^{p,p} \cap H^{2p}(X, \mathbb{Q})$ analytic ∩ rational 交差 — analytic submanifold |
| **C₃ Eff-sim** | poly-time classical simulable (low-bond MPS, match-gate, stabilizer union), Nielsen $C = O(\text{poly}(n))$ | polynomial-parameter family in exp-dim state space — "BQP-vs-classical simulation frontier" | poly-depth circuit composition | super-polynomial complexity = quantum supremacy resource | "Hodge conjecture is computationally hard" (Millennium-open) — computational depth |
| **C₄ Bell-local** | LHV-describable correlations, CHSH ≤ 2 (classical), Bell polytope | classical convex polytope embedded in larger quantum correlation body (Tsirelson bound $2\sqrt{2}$) | local unitaries $U_A \otimes U_B$ (pair-wise) | CHSH violation $\Delta_{\text{CHSH}}$ = nonlocal capacity | "algebraic cycles ↔ classical means" — classical correlation gap |

**主担当 Arrow (全 vertex 共通)**: **Arrow 1 kernel** (T-AAS 分解 sparsity 様式)。各 monotone (M_F, 𝓝, C, Δ_CHSH) は **Arrow 3 上 information layer** に分類されるが、本 vertex では Arrow 1 kernel sparsity 様式が主役。

### 6.2 4-vertex triangulation の閉鎖性

**閉鎖性の主張**:
- **層レベル**: 各 class が独立 f_rational > 0 instance 提供 → 単一 class 偶然性排除
- **Arrow レベル**: 4 instance が異なる Arrow 1 kernel sparsity 様式 → T-AAS Arrow 1 kernel taxonomy 全体が独立 verify (4 narrowness 様式が古典 Hodge の 4 parallel 方向に対応)
- **障害レベル**: C₁ discrete-orbit covering / C₂ continuous-manifold parameterization / C₃ complexity-class boundary / C₄ classical-polytope embedding — 4 様式の独立性が量子内 Arrow 間 triangulation の閉鎖性根拠

**視点変換 (3-vertex → 4-vertex)**: N1 では 3 NT instance が異なる Arrow を主担当 (Paper C 3 Arrow simultaneous / Stark Arrow 2-3 / Brauer Arrow 1 kernel)。本論では 4 量子 instance が **同一 Arrow (Arrow 1 kernel) の異なる sparsity 様式** を主担当 — これは Arrow 1 kernel の **内部分解** に着目する量子側固有の triangulation 視点。N1 = cross-Arrow triangulation、Q1 = intra-Arrow taxonomy triangulation で、両者は補完的視点。

4 量子 instance のいずれも他の 3 instance を前提とせずに Arrow 1 kernel の特定 sparsity 様式を露呈 — この独立性が量子内普遍性の証拠。

### 6.3 N1 ↔ Q1 parallel observation (cross-paper)

| 観点 | N1 (NT) | Q1 (量子) |
|---|---|---|
| Triangulation 視点 | Arrow 間 (3-vertex) | Arrow 1 kernel narrowness (4-vertex) |
| 主担当 instance | Paper C / Stark / Brauer | C₁ / C₂ / C₃ / C₄ |
| f_rational > 0 status | 1 open (Hodge NT-adjacent) + 3 instance ESTABLISHED | 4 ESTABLISHED instance + Hodge depth parallel conjecture |
| §4 dual lift | 古典 (ι_L, χ commutative) | 非可換 (Stone group, unitary representation) |
| Forward to | N2-N5 (NT 系列 final closure) | Q2-Q3 (Open QS chain + Born-Gleason) |

**Cross-validation**: N1 と Q1 が **同一 framework (S15 / 3 Arrow / T-AAS)** を 2 独立数学領域 (NT, 量子) で independently verify する → framework の **ドメイン非依存普遍性** が 2-domain triangulation で確認。N1 + Q1 = framework の universal validity の cross-domain anchor。

---

## §7 新量子ドメイン検討 Protocol (6-step)

新量子ドメイン (新 Hilbert 空間, 新 unitary 表現クラス, 新 algebraic class, 新 quantum resource theory) への検討手順 (`meta/new_domain_protocol.md` 量子 specialization):

| Step | 内容 |
|---|---|
| **0** | §4 dual 射影同定 (量子 lift) — 加法 (Stone 群 {U(t)}, S¹ subgroup), 乗法 (unitary representation π: G → U(H), spectral decomposition), Bridge (Hilbert 空間, ℂ unit) |
| **1** | Scan observable 同定 — exp kernel が書けるか? 加法 scan ($e^{-iHt}$) / 乗法 scan ($e^{-βH}$)? S12 6+1 member 対応? |
| **2** | Structural observable 同定 — parameter-free 整数/位相不変量、dim H, Schmidt rank, irrep index, group-theoretic invariants, topological invariants |
| **3** | Information observable 同定 — log-derivative chain ($-\partial_T F = S$), Hartley $\log \dim H$, von Neumann $S(\rho)$, class-monotone (M_F / 𝓝 / C / Δ_CHSH) |
| **4** | 3 Arrow 検証 — Arrow 1 (A spectrum, ρ structure が Structural encode), Arrow 2 ($Z \to F \to S$ thermodynamic chain), Arrow 3 (extreme limit で Scan が log dim H に退化?) |
| **5** | T-AAS 分解確認 — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? 4-class refined Hodge 内 residence (C₁/C₂/C₃/C₄ どれに最も近いか)? |
| **6** | 辞書 residence 決定 — L1 量子 8 entries 内 residence、必要なら新 entry 提案、Q2 Open QS chain との接続点同定 |

**検証済 application**: 4 algebraic class で各々 fitness verify、3/4 empirical (C₁ M_F 4e-16, C₂ Mari-Eisert 1e-4, C₄ Tsirelson 1e-6) + C₃ literature synthesis 4-ref。

**次候補 5 件**: 量子コヒーレンス theory (Baumgratz-Cramer-Plenio 2014: incoherent in fixed basis = free states) / Quantum reference frame (G-invariance, asymmetric state resource) / Topological order (anyon braiding, Chern-Simons level) / Quantum error correction code states (stabilizer code subspace) / Quantum field theory states (CFT vacuum, Jefferson-Myers 2017 Nielsen complexity 文献で C₃ extension 候補)。

---

## §8 帰結と open frontier

### 8.1 確立 (量子-only restatement)

1. **S15 Observable Trichotomy** — 3 段で網羅性閉鎖 (§3.5)
2. **Arrow 構造 (3 本) と可換性** — 3 量子 instance (β→0 thermal limit, t→0 trivial unitary, T→∞ classical limit) で commutativity verify (§4.4)
3. **T-AAS 4-class refined Hodge** — Stabilizer/Gaussian/Eff-sim/Bell-local で 16/16 量子-relevant fitness、Theorem 4a.1 unified via class infidelity (§5.2-§5.3)
4. **量子内 Arrow 1 kernel narrowness 4-vertex triangulation** — 4 instance が異なる sparsity 様式主担当、N1 cross-Arrow triangulation を補完する intra-Arrow taxonomy 視点 (§6)
5. **S13/S14/S17 量子内 residence** — π/ln 2/e の Arrow 上 canonical constant、3 Arrow base 完備 (§4.5)
6. **Observation-optimal gauge theorem (量子 2 instance 対比)** — qubit ρ_max coincide vs Schmidt rank split を本論で statement のみ (§4.5.1)
7. **N1 ↔ Q1 framework parallel** — 同一 framework を 2 独立数学領域で independently verify、framework の **ドメイン非依存普遍性** 2-domain anchor (§6.3)

### 8.2 Q2-Q3 forward bridge

| 後続 | 主題 | 本論からの forward |
|---|---|---|
| **Q2** Open QS chain | open_quantum_systems → quantum_statistical_mechanics → quantum_thermodynamics → many_body_quantum 4-stage chain で観測理論を量子 statistical mechanics 言語で再展開 | §3.2 Scan family (Z(β) / response χ(ω) / KMS / FDT) 詳細展開、§4.2 Arrow 2 上 KMS-FDT 等価性 (Tomita-Takesaki modular 理論経由)、§5 T-AAS 分解の Lindblad evolution + decoherence + pointer basis Einselection 視点、N3 Path 2 の量子 group action analog (KMS 軌道) |
| **Q3** Born-Gleason | §4 dual = root の量子 closure、Born rule + Gleason theorem framework で σ\* = √(2 ln 2) (half-amplitude gauge), 量子観測の自然 unit | §2.3 §4 dual 量子 root の Busch-Gleason derivation 完全形 (PRL 2003, dim=2 解消)、§4.5 S13 ln 2 量子 residence の half-amplitude gauge σ\* closure、§5 Born 則 form (Tr(ρE)) と value (ρ_max = I/2) の同時定理化 |

**8-gauge forward (N5 parallel)**: 本論は §1.3 で gauge² を明示 listing のみ。Origination matrix 8 gauge family の量子 instance (e.g., π Berry phase, ln 2 qubit S, e info-density, ζ partition function regularization) の formal residence は Q-paper 系列 final closure (将来 Q4-Q5 候補) で検討。

### 8.3 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **Conjecture 4a.2** (depth parallel quantitative form) | OPEN (sparsity-matching definition + Hodge counterexample 存在依存) | §5.4, Q1 future |
| **古典 Hodge 予想** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself, 1924-) | §5.4, NT-adjacent |
| **Quantum Reference Frame G-invariance** as 5th class candidate | OPEN | §7 next candidate |
| **Topological order (anyons) 5th class candidate** | OPEN | §7 next candidate |
| **OQ-Ω-Obs-1 minimal form と 4a refined form の関係** | RESOLVED (4a is depth-matching extension) | OQ-Ω-Obs-4a §1 |
| **OQ-Ω-Obs-3 e-extremum** (Arrow 3 e residence) | ESTABLISHED 2026-04-23, 5/5 gate | §4.5 |
| **OQ-Ω-Obs-2 Arrow 1⁻¹ generation** | PARTIAL_CLOSED 2026-04-22 | §4.6, future |
| **σ\* = √(2 ln 2) half-amplitude gauge** | candidate (Q3 forward) | Q3 |
| **dim=2 Gleason gap full closure** (Busch-Gleason 完全形) | ESTABLISHED 2003 (Busch PRL) | §6.1 (主担当 Arrow), Q3 |
| **量子 8-gauge origination matrix** | OPEN (Q-series future) | §8.2 |
| **quantum field theory + CFT への extension** | scope 外 (本論 L1 量子 8 entries 限定) | future Q-series |

### 8.4 辞書 residence map

| 本論 piece | residence | 状態 (Q1) |
|---|---|---|
| §2.1 公理 1 (Dual receptacle 量子 lift) | `c_phase_complex.md §4` + `q_quantum_observation.md §1-§2` | 既存 reuse |
| §2.2 公理 A0-A7 (量子 instance) | `finite_observation.md §1-§7` + `observation_canon.md §2` + 本 §2.2 NEW 量子 instance 例 | 既存 + 本論 expansion |
| §2.4 L0 v1 + L0 v2 (量子 instance) | `finite_observation.md §8` + `observation_canon.md §3` + 本 §2.4 NEW 量子 instance 例 | 2026-04-23 ESTABLISHED + 本論 expansion |
| §3 S15 + 量子 enumeration 閉鎖 | `c_theorems_master.md` row S15 + 本 §3.5 量子-only annex (NEW) | annex 実装予定 (post-v0.2 backward) |
| §3.2-§3.4 Scan/Structural/Information family | `c_theorems_master.md` + `q_quantum_observation §3-§6` + `q_quantum_statistical_mechanics §3-§4` + `q_fine_structure` + `q_gauge_field_theory` | 既存 reuse |
| §4 3 Arrow framework (量子 lift) | `c_arrow_framework.md` | 2026-04-23 既存 L1 entry |
| §4.4 Arrow 可換性 (3 量子 instance) | `c_arrow_framework.md §4.2.1` + 本 §4.4 NEW 量子 instance annex | annex 実装予定 |
| §4.5 / §4.5.1 S13/S14/S17 residence + 量子 instance | `c_arrow_bridge_constants.md §5-§6` + §11 (既 N3 由来) + 本 §4.5 量子 expansion | 既 + 量子 expansion 実装予定 |
| §4.6 逆 Arrow + obstruction (量子 限定) | `c_arrow_obstruction.md §11` + 量子 subset filter | 既 + 本論 量子 scope filter |
| §5 T-AAS 4-class | `c_arrow_obstruction.md §10` (T-AAS) + `oq_omega_obs_4a_refined_quantum_hodge_v0.md` (4-class formal) | 既 + research file integration |
| §5.3 Theorem 4a.1 unified | `c_filtration_obstruction.md` (T-AAS f_rational instance, 4-class quantum lift annex NEW) | annex 実装予定 |
| §5.4 Hodge depth parallel | `c_filtration_obstruction.md` Hodge open + 本 §5.4 量子 4-instance closure annex (NEW) | annex 実装予定 |
| §6 量子内 4-vertex triangulation | NEW `meta/triangulation_methodology.md §11` 量子-internal Arrow 1 kernel narrowness annex | annex 実装予定 |
| §7 6-step protocol (量子 specialize) | NEW `meta/new_domain_protocol.md §9` 量子 specialization annex | annex 実装予定 |
| §6.3 N1 ↔ Q1 parallel | NEW `meta/triangulation_methodology.md §12` cross-paper framework parallel annex | annex 実装予定 |

**post-v0.2 backward 統計**: Q1 起草後想定 7 件 dictionary annex 書き戻し: c_theorems_master 量子-only S15 enumeration / c_arrow_framework §4.2.2 量子 Arrow 可換性 / c_arrow_bridge_constants §12 量子 instance expansion (S13 qubit, S17 qubit/qutrit info-density) / c_filtration_obstruction 4-class quantum lift annex (Theorem 4a.1) / meta/triangulation_methodology §11 (4-vertex) + §12 (N1 ↔ Q1 parallel) / meta/new_domain_protocol §9 量子 specialization。

**帰結**: 本論は dictionary に対して **量子-internal framework header** として位置付けられ、theorem / definition は L0 / L1 量子 / meta entry に formal residence。Q2 (Open QS chain 4-stage) + Q3 (Born-Gleason closure) 起草後、framework header → 結果論文 → 辞書 backward の **3 層 link が完成** (N1-N5 系列と並行)。

---

## 変更履歴

- **v0.2 (2026-04-27)**: compact 版。v0.1 (733 行) から冗長削減 — Abstract 6 主結果を凝縮、§1.1/§1.2/§1.3 構成を簡素化、§2.3 §4 dual 説明を表 + 1 段落に集約 (ℂ 必然性引用文を 1 段落圧縮)、§2.4 L0 v2 公理 (a')-(d') を 1 段落化、§3 各層解説をテーブル化 + 結論段落のみ、§3.5 closure 3 段検証を簡素化、§4.4 Arrow 可換性は表保持・解説圧縮、§4.4.1 Fi/I は表保持、§4.5/§4.5.1 S13/S14/S17 + Observation-optimal を簡素化、§5 T-AAS § 内冗長部分削減 (4-class 表 + per-class fitness witness は核心保持)、§5.3 Theorem 4a.1 数式は完全保持、§5.4 Hodge depth parallel を圧縮、§6.1-§6.4 各 class subsection (4 subsections) を 1 統合表に圧縮、§6.5 closure 主張 + §6.6 N1↔Q1 parallel を §6.2/§6.3 にリネーム + 圧縮、§7 protocol 表は保持、§8.4 residence map 説明圧縮 + post-v0.2 backward 統計を 1 段落に。骨格・主張・instance 数値・status 表記は全保持。
- **v0.1 (2026-04-27)**: initial Q-only draft. Paper D v0.9.2 (multi-domain frozen-internal) からの 量子 specialization。N1 (NT-only) と parallel framework header position。4 量子 instance (C₁/C₄ OQ-Ω-Obs-4a 4-class refined Hodge) による Arrow 1 kernel narrowness 4-vertex triangulation で再構築。

---

## 参考文献 (内部)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**N1 系列 (parallel framework header)**: `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.7, NT-only restatement)

**本論で展開される結果の出典**:
- `research/oq_omega_obs_4a_refined_quantum_hodge_v0.md` (ESTABLISHED 2026-04-23, 6/6 gate) — §5.2 4-class formal + §5.3 Theorem 4a.1
- `research/oq_omega_obs_4a_monotone_verify.py` — §5.2 empirical verification (C₁ M_F 4e-16, C₄ CHSH 1e-6)
- `research/oq_omega_obs_1_ker_entangle_frational_path_v0.md` (CONFIRMED 2026-04-22) — §4.6 minimal form (Schmidt rank → f_rational, depth-deficient)
- `research/oq_omega_obs_3_e_arrow3_v0.md` (ESTABLISHED 2026-04-23) + `oq_omega_obs_3_info_density_check.py` (5/5 gate) — §4.5 S17 量子 e-extremum
- `research/oq_omega_obs_4_noncommutative_scan_v0.md` (parent OQ for 4a)
- `research/oq_l0_refinement_finite_infinite_2axis_v0.md` (ESTABLISHED 2026-04-23) — §2.4 L0 v2 量子 instance
- `research/bidirectional_duality_v0.md` — §2.3 §4 dual root + §3.2 量子 S15 接続

**L0 / L1 / meta 依存**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11, c_filtration_obstruction, c_observation_optimal_gauge, c_spectral §3}.md` / `L1_mathematical/quantum/{q_quantum_observation §1-§9, q_action_principles, q_gauge_field_theory, q_fine_structure}.md` (本論主体) / `L1_mathematical/quantum/{q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum}.md` (Q2 forward 主体) / `meta/{triangulation_methodology, new_domain_protocol}.md`

**後続論文**: Q2 (Open QS chain 4-stage) / Q3 (Born-Gleason + dim=2 closure + σ\* gauge) — 起草予定
