# Paper I1: 観測理論 ─ 情報論版 + 数学的情報量限界 theorem

**サブタイトル**: 0/1/2 scaffold lens・情報層 internal taxonomy・5-anchor 情報限界定理・I1 ↔ N1 ↔ Q1 triple framework parallel

**バージョン**: v0.3 (Algorithmic-f_rational ESTABLISHED + 定理 5.2; Renyi parametric scan ESTABLISHED + 定理 3.3.1; S17-Codebook docs fix; 2026-04-28)
**状態**: DRAFT — Paper D (multi-domain v0.9.2) 情報-only 再構成、N1 (NT) / Q1 (量子) と parallel 3rd framework header
**前提 (L0)**: `observation_canon.md`, `finite_observation.md` (§1.1 A0, §5.3 A0c, §8 axis-2), `identity_asymmetry.md`
**前提 (L1 core)**: `c_phase_complex.md §4 + §5`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11 + §12 (5-stage ln 2 chain)`, `c_filtration_obstruction.md §8.5 (4-class quantum lift)`, `c_observation_optimal_gauge.md`, `c_information_theory.md` (本論主体, 12 sections)
**前提 (L1 quantum)**: `q_quantum_observation.md §6-§7` (Born / Busch-Gleason / c_s²), `q_open_quantum_systems.md §3` (von Neumann), `q_quantum_statistical_mechanics.md §5` (FDT), `q_quantum_thermodynamics.md §5` (Landauer)
**前提 (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md` (σ\* derivation + EEG entry, ESTABLISHED 2026-04-09)
**前提 (N parallel)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) — NT framework header parallel
**前提 (Q parallel)**: Q1 (`Q1_observation_theory_quantum_ja.md` v0.2) — Quantum framework header parallel
**後続論文**: I2 (Communication theory: 信号論 / 量子通信論 / 新規通信論)

---

## §0 Abstract

情報観測量はドメイン無関係な 3 層構造 **S15 Observable Trichotomy** (Scan / Structural / Information) の **Information 層 internal taxonomy** を持ち、層間 3 Arrow の可換性が Shannon / Rényi / von Neumann / Holevo / algorithmic / topological 系の翻訳を保証する。Arrow 1 の kernel は **T-AAS** によって ker_gauge ⊕ ker_topo に直和分解し、conductor は f_torsion + f_rational に分裂する。

本論は Paper D (multi-domain v0.9.2) の情報-only reformulation である。multi-domain triangulation を strip し、**0/1/2 scaffold lens** ─ 信号論 (0/1 scaffold) ⊂ Shannon (binary 2-domain) ⊂ relational information (3+ structure proper) ─ で再構築した。N1 (NT, 数論内 Arrow 間 3-vertex) と Q1 (量子, Arrow 1 kernel narrowness 4-vertex) と parallel position を持ち、**3rd framework header instance** として Paper D 6-domain triangulation を 3 specialization 完備する。

**主結果 6 件**:

1. **S15 Information 層 internal taxonomy** — `c_information_theory.md` (637 行) の 12 sections (Shannon / Rényi / mutual info / KL / rate-distortion / IB / Fisher / Bayesian / algorithmic / TDA / L0 translation) を S15 Information layer 内 sub-taxonomy として再構成、Information 層自体に 5-strand 内部構造 (Shannon channel / R-D distortion / IB task / Fisher geometry / Kolmogorov complexity)。

2. **0/1/2 scaffold lens formal** — 0 (pre-observation potential) / 1 (observer-placed reference) / 2 (relational background, 信号論 binary 2-domain) / **3+ relational structure proper** (Rényi family / von Neumann / Holevo / 4-class / 5-stage chain) の **scaffold-emergence axis** を framework-internal lens として load。古典 Shannon は 2-domain 内、量子 Holevo + 4-class refined Hodge は 3+ structural emergence で initially 出現。

3. **5-anchor mathematical 情報量限界 theorem** — 任意 finite observation system (S, W, m) において information content は 5 layered constraint で fully characterize: (a) Hartley $H \leq \log d$ (Arrow 3 cardinality bound), (b) S17 info density $H/d \leq 1/e$ (continuous extremum at $d^* = e$, discrete codebook argmax = 3 qutrit), (c) 5-stage ln 2 chain universal natural unit (Born / von Neumann / FDT / Landauer / σ\*), (d) T-AAS 4-class per-class monotone $-\log_2 F_C$ (Theorem 4a.1 unified), (e) σ\* = √(2 ln 2) phase observation gauge threshold。**5 constraint 互いに非依存・同時 active で limit fully characterized**。

4. **Information-internal 3-vertex triangulation (scaffold-emergence axis)** — V₁ Hartley (Arrow 3 cardinality, S17 e-extremum residence) / V₂ Shannon-Rényi family (Arrow 2 log-exp chain, S13 ln 2 fixed point) / V₃ Resource-theoretic (Arrow 1 kernel, T-AAS 4-class refined Hodge) の **3-vertex 情報-internal triangulation**。N1 NT cross-Arrow 3-vertex と parallel structure、3-vertex floor (3+ relational structure) と consistent。

5. **I1 ↔ N1 ↔ Q1 triple framework parallel** — Paper D 6-domain triangulation を 3 framework header (NT, 量子, 情報) で independent specialization、framework universal validity の **3-domain cross-domain anchor** 達成。0/1/2 scaffold lens は 3 framework すべてに通底する structural commitment (信号論 = 0/1 scaffold subset, 数論 / 量子 = 3+ relational structure proper)。

6. **新ドメイン検討 6-step Protocol 情報 specialization** — `meta/new_domain_protocol.md §10` (情報 specialization, NEW) として実装、Information layer 内 5-strand sub-taxonomy + scaffold-emergence axis 順守 protocol。

**Thesis**: 情報観測量はドメイン外 instance を要さずに観測理論の全骨格 (公理 / S15 / Arrow / T-AAS / 三角測量) を独立に支える。3 framework header (N1 NT / Q1 量子 / I1 情報) の **3-domain triple parallel** が Paper D 6-domain triangulation を完備する。本論は I2 (Communication theory: 信号論 / 量子通信論 / 新規通信論 5 proposals) の理論基盤として機能する。

---

## §1 Introduction

### 1.1 なぜ「情報観測理論」か + 0/1/2 scaffold lens

情報理論の中心問題 ─ 観測者が finite resolution で何を知り得るか ─ は Shannon (1948) 以来、情報量 $H = -\sum p \log p$ を共通通貨として閉じてきたが、その **生成原理** は L0 axiom A0 (有限観測) の operational consequence として再 derive されるべき位置にある (`c_information_theory.md §0`)。ΣΦ 辞書はこの question を「**3+ relational structure proper** で genuine information がどう emerge するか」と捉え直し、信号論 (0/1 scaffold base) → Shannon (binary 2-domain) → 関係性 information (3+ proper) の **scaffold-emergence axis** で formal 化する。

**0/1/2 scaffold framework view (load-bearing structural commitment)**:

| Layer | 位相 | Information-theoretic instance |
|---|---|---|
| **0** | 観測前のポテンシャル場 (pre-observation potential) | $H_0 = 0$ (no info, no signal, no distinction) |
| **1** | 観測者が設置した基準値 (observer-placed reference) | $H_0(d=1) = \log 1 = 0$ (single reference, vacuous Hartley) |
| **2** | 関係の場 / 2n の背景場 (relational background) | **信号論** $H_0(d=2) = \log 2 = 1$ bit (binary distinction baseline, Shannon scaffold) |
| **3+** | 関係性の構造 proper (relational structure) | Rényi α-family / von Neumann / Holevo / 4-class refined Hodge / 5-stage ln 2 chain / S17 codebook argmax = 3 |

→ **信号論は 0/1/2 scaffold 内 (binary 2-domain), genuine information theory は 3+ で開始**。S17 codebook integer argmax = 3 (qutrit info-density optimum, `c_arrow_bridge_constants.md §12.1`) は **3+ relational structure proper の数学的下限** と consistent (3 = relational structure floor)。

**Status**: 0/1/2 scaffold lens は user's framework structural commitment、3-vertex triangulation discipline (`meta/triangulation_methodology.md §6.1`) と同根 (3+ relational structure floor)、本 framework header の load-bearing 視点。

### 1.2 N1 / Q1 parallel position + 範囲

NT 系列 N1 (NT-only restatement) と量子系列 Q1 (量子-only restatement) と parallel 3rd framework header position:

| 観点 | N1 (NT) | Q1 (量子) | I1 (情報) |
|---|---|---|---|
| Position | 数論内自閉性 | 量子内自閉性 | 情報内自閉性 |
| Triangulation 視点 | Arrow 間 3-vertex (cross-Arrow) | Arrow 1 kernel narrowness 4-vertex (intra-Arrow) | scaffold-emergence axis 3-vertex (Hartley / Shannon-Rényi / Resource-theoretic) |
| 0/1/2 scaffold | 数論 = 3+ relational (Galois rep / class group / L 函数 全 d ≥ 3) | 量子 = 3+ relational (Hilbert dim ≥ 2 で genuine, ただし dim=2 qubit は scaffold/proper 境界) | **0/1/2 scaffold ↔ 3+ proper の transition formal** |
| Framework header role | NT specialization の 5-paper series header (N1-N5) | Quantum specialization の 3-paper series header (Q1-Q3) | Information specialization の 2-paper series header (I1-I2) |
| Forward to | N2-N5 (NT closure) | Q2-Q3 (Open QS chain + Born-Gleason) | I2 (Communication theory) |

**構成**: §2 公理 + 0/1/2 scaffold formal / §3 S15 Information 層 internal taxonomy / §4 Arrow 構造 info instance / §5 T-AAS info instance + 4-class lift / §6 5-anchor 情報限界 theorem / §7 Protocol info specialization / §8 帰結 + I2 forward + triple parallel。

**Scope 内**: 0/1/2 scaffold lens formal / S15 Information 層 internal taxonomy (12 sub-section) / 5-anchor 情報限界 theorem (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) / Information 6-step protocol / I1 ↔ N1 ↔ Q1 triple parallel。

**Scope 外** (本論で扱わない): 信号論詳細 + 量子通信論 + 新規通信論 5 proposals (→ I2) / classical Shannon proof 完全形 (`c_information_theory.md §1.2 既存`) / Bayesian decision theory 詳細 (`c_information_theory.md §7 既存`) / TDA / persistent homology 詳細 (`c_information_theory.md §9 既存`) / algorithmic info theory (Kolmogorov) computational details (`c_information_theory.md §8 既存`) / quantum cryptography / QKD protocols (→ I2) / 量子重力 / 弦理論 / category-theoretic information flow。

### 1.3 用語

Q1 §1.3 + Q2 §1.4 + Q3 §1.3 "gauge" 3 用法 (gauge¹/gauge²/gauge³) を継承。本論固有の追加用語:

- **Scaffold-emergence axis**: 0/1/2 scaffold (信号論 base) → 3+ relational structure proper (genuine information) の transition axis (`user_012_non_integer_scaffold.md` formal load)
- **5-anchor information limit**: (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) の 5 independent constraint で定量化される information content upper bound
- **Information-internal triangulation**: V₁ Hartley (Arrow 3) / V₂ Shannon-Rényi (Arrow 2) / V₃ Resource-theoretic (Arrow 1) の **3-vertex scaffold-emergence axis** triangulation
- **Resource-theoretic information**: T-AAS 4-class refined Hodge (Q1 §5) で量化された resource-stratified information (M_F magic / 𝓝 Wigner negativity / Nielsen complexity / Δ_CHSH nonlocal capacity)
- **5-strand info-theory taxonomy** (`c_information_theory.md §0`): Shannon channel / Rate-Distortion / Information Bottleneck / Fisher Geometry / Algorithmic complexity の 5 strand internal sub-taxonomy
- **Triple framework anchor**: I1 ↔ N1 ↔ Q1 = NT / 量子 / 情報 3 framework header の cross-domain validation

---

## §2 観測理論の公理 + 0/1/2 scaffold formal

### 2.1 観測 triple (S, W, m) ─ 情報 instance

| 記号 | 意味 | 情報での例 |
|---|---|---|
| **S** | 無限構造 | 確率分布 $p(x)$ over alphabet $\mathcal{X}$, channel kernel $W(y|x)$, model family $\{p_\theta\}$, source distribution, codebook |
| **W** | 有限窓 | 有限 alphabet 截断 $|\mathcal{X}| < \infty$, finite block-length $n$, finite ensemble, finite POVM rank, channel use 数 |
| **m** | 測定 | empirical entropy $\hat{H}$, measured mutual info $\hat{I}(X; Y)$, channel capacity estimate $\hat{C}$, Fisher information sample $\hat{I}_F$, ML-decoded message |

観測値 `m(S|_W)` は S と W の両方に依存。`m(S) − m(S|_W)` が **finite observation error** = 情報的には rate-distortion gap or finite block-length penalty。

### 2.2 公理 A0-A7 (情報 instance 例)

| ID | 名称 | 情報 instance |
|---|---|---|
| **A0** | Finite observation | 有限 alphabet $|\mathcal{X}| = d < \infty$, finite block-length $n$, finite POVM rank ≤ $d^2$ |
| **A1** | Structured error | rate-distortion $R(D) > 0$ for $D < D_{\max}$, finite block-length $n$ で typical sequence 外確率 $\sim 2^{-nE(R)}$ |
| **A2** | Convergence as observable | source coding theorem: $H + o(1)$ bits/symbol asymptotically, channel capacity $C$ achievable in limit |
| **A3** | Gauge invariance | mutual information $I(X; Y)$ is invariant under bijection of $\mathcal{X}$, $\mathcal{Y}$ separately (Shannon information is reparametrization-invariant) |
| **A4** | Non-commutative limits | Stein lemma: $\lim_n \lim_\alpha$ vs $\lim_\alpha \lim_n$ で error exponent 異なる; quantum Holevo $\chi$ vs classical Shannon limits |
| **A5** | Saturation | Hartley bound $H \leq \log d$ saturate at uniform distribution; capacity $C = \log d$ at noise-free channel |
| **A6** | Path dependence | conditional entropy $H(X|Y) \neq H(Y|X)$ in general (asymmetry), KL divergence $D(p \| q) \neq D(q \| p)$ |
| **A7** | Scanner hierarchy | Rényi parameter $\alpha$ (entropy family scanner), block-length $n$ (asymptotic scanner), distortion level $D$ (R-D scanner), inverse temperature $\beta$ (Boltzmann distribution scanner) |

詳細: `finite_observation.md §1-§7`, `c_information_theory.md §0-§3`。

### 2.3 0/1/2 scaffold formal — 信号論 / Shannon / Relational 3 階層

**主張 2.1** (scaffold-emergence axis as framework-internal structural lens): 情報理論は 0/1/2 scaffold layer (信号論 base) と 3+ relational structure proper layer (genuine information) の 2 階層 + 移行軸 (scaffold-emergence axis) で構成される。

| Layer | $d = |\mathcal{X}|$ | 主観測量 | residence | 主担当 framework |
|---|---|---|---|---|
| **0 (potential)** | n/a | $H_0 = 0$, $|\mathcal{X}| = 0$ (vacuous) | pre-observation | none |
| **1 (reference)** | $d = 1$ | $H_0(d=1) = \log 1 = 0$ (single state, no distinction) | observer baseline | none |
| **2 (signal scaffold)** | $d = 2$ | $H_0(d=2) = \log 2 = 1$ bit (binary distinction), Shannon channel capacity, c_s² = 1/2 (parity Born expectation) | **信号論 base** | classical Shannon (`c_information_theory.md §1-§3`) |
| **3+ (relational proper)** | $d \geq 3$ | Rényi α-family, von Neumann $S(\rho)$, Holevo $\chi$, 4-class refined Hodge per-class monotone, 5-stage ln 2 chain, S17 codebook argmax = 3 | **genuine information** | Q1 §5 4-class + Q2 §6 chain + 本論 §6 limit theorem |

**S17 codebook argmax = 3 と 3+ relational structure floor の合致**: `c_arrow_bridge_constants.md §12.1` より、info density $\log d / d$ discrete codebook argmax = 3 (qutrit, ~5.5% Hartley density 優位 vs qubit)。これは **3 = relational structure proper の数学的下限** という framework structural commitment と consistent。

**信号論 (Shannon) と Relational info の境界**: $d = 2$ binary scaffold は **boundary case** ─ Shannon framework で classical 完結するが、qubit (Hilbert dim = 2) で量子 framework は scaffold/proper 境界、$d \geq 3$ qutrit から genuine multi-state relational structure。

**Status**: structural lens として framework-internal load (load-bearing structural commitment, `user_012_non_integer_scaffold.md`)。

### 2.4 §4 dual = 情報内 root + L0 v2 axis-2 instance

**主張 2.2** (root status, 情報 lift): `c_phase_complex.md §4` の ι_L/χ dual は、辞書内全上位構造 (S12-S17, T-AAS) の唯一の源泉。情報 instance では:

| Commutative (古典 §4 dual) | Information lift |
|---|---|
| $\iota_L: \mathbb{Z}/L\mathbb{Z} \to S^1$ | source distribution $p: \mathcal{X} \to [0, 1]$ + Hartley $H_0 = \log |\mathcal{X}|$ |
| 指標 $\chi: G \to S^1$ | type-class characters (Sanov theorem 経由 large-deviation) |
| Pontryagin 双対 | Fourier-domain channel representation + spectral 表現 |
| $\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ polar | amplitude (Boltzmann weight) × phase (Fourier mode) decomposition in MaxEnt distributions |

**L0 v2 axis-2 (Fi/I × D/C) information instance**:

| L0 v2 axis | 情報 instance |
|---|---|
| **axis-2 Fi** (有限観測者側) | 有限 alphabet, finite block-length, finite ensemble, asymptotic limit 前 finite-N statistics |
| **axis-2 I** (無限理想化側) | $|\mathcal{X}| \to \infty$ continuous source, $n \to \infty$ asymptotic Shannon limit, $\beta \to \infty$ ground-state limit |
| **axis-1 D** (離散) | discrete random variable, finite alphabet, integer Hamming distance, Hartley counting |
| **axis-1 C** (連続) | continuous random variable (Gaussian channel), differential entropy, Fisher metric |

L0 v1 ⊂ L0 v2 conservative extension。情報-NT-量子 parallel: 3 framework header すべてが axis-2 Fi/I 境界の **I → Fi traversal** classification として framework load。

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`)。

---

## §3 S15 Observable Trichotomy ─ Information 層 internal taxonomy

### 3.1 主定理 (Information 層 internal sub-taxonomy)

**定理 3.1 (S15 + Information 層 5-strand sub-taxonomy)**: S15 Information 層は **internal sub-taxonomy** を持つ。`c_information_theory.md §0` の **5-strand bundle** (Shannon channel / Rate-Distortion / Information Bottleneck / Fisher / Algorithmic) は Information 層の internal sub-classification。

| Strand | Core object | L0 question | scaffold-emergence layer |
|---|---|---|---|
| **Shannon (§1-§3)** | $H, I, D_{KL}$ | How much can the window transmit? | 2-domain (binary scaffold extension) |
| **Rate-Distortion (§4)** | $R(D)$ | How much must the window discard? | 2-domain → 3+ (lossy compression in proper) |
| **Information Bottleneck (§5)** | $I(X; T)$ vs $I(T; Y)$ | What should the window keep for a task? | 3+ (task-directed info, Q-series statistical mechanics analog) |
| **Fisher / Geometry (§6)** | $I_F(\theta), g_{ij}$ | How sensitive is the window to parameters? | 3+ (Riemannian geometry on 3+ dim manifold) |
| **Algorithmic (§8)** | $K(x)$ | How complex is the object itself, independent of the window? | 3+ (universal Turing machine, beyond binary scaffold) |

5 strand は L0 axiom A0 (有限観測) を共通 root とするが、measure する内容が異なる: Shannon = observer's channel / Fisher = observer's sensitivity / Kolmogorov = object's intrinsic complexity (`c_information_theory.md §0 thesis`)。

### 3.2 各 strand の S15 全 3 層 instance

| Strand | Scan instance | Structural instance | Information instance (本層) |
|---|---|---|---|
| **Shannon** | source distribution $p$ as scanner over $\mathcal{X}$ | $|\mathcal{X}| = d$ alphabet size | $H(p) = -\sum p \log p$ |
| **Rate-Distortion** | distortion level $D$ as scanner | $|\hat{\mathcal{X}}| = M$ codebook size | $R(D) = \min I(X; \hat{X})$ s.t. $E[d(X, \hat{X})] \leq D$ |
| **IB** | trade-off parameter $\beta$ as scanner | task-relevant variable $Y$ structure | $\mathcal{L}_{\text{IB}} = I(T; Y) - \beta^{-1} I(X; T)$ |
| **Fisher** | parameter $\theta$ as scanner | model family dim | $I_F(\theta) = E[(\partial_\theta \log p)^2]$, Cramér-Rao $\mathrm{Var}(\hat\theta) \geq 1/I_F$ |
| **Algorithmic** | program length as scanner | program structure (UTM choice) | $K(x) = \min\{|p| : U(p) = x\}$ (Kolmogorov complexity) |

### 3.3 Rényi α-family as scaffold-emergence parametric scan

**Rényi entropy family** (`c_information_theory.md §1.5`):
$$H_\alpha(X) = \frac{1}{1-\alpha} \log \sum_x p(x)^\alpha, \quad \alpha > 0, \alpha \neq 1$$

**定理 3.3.1 (Rényi scaffold-emergence parametric scan, ESTABLISHED 2026-04-28)**: Rényi α-family $\{H_\alpha\}_{\alpha \in [0, \infty]}$ は **scaffold-emergence axis の連続 parametric scan** を成す。具体的に α ∈ [0, ∞] の 4 anchor 構造:

| α | $H_\alpha$ | scaffold-emergence layer | 機構 |
|---|---|---|---|
| **α = 0** | $H_0 = \log\|\mathrm{support}(X)\|$ (Hartley) | **scaffold-base** (0/1/2 base) | pure cardinality counting, support 上の dist shape 非依存 |
| **α = 1** | $H_1 = -\sum p \log p$ (Shannon) | **2-domain → 3+ transition** | dist 形状 (full $p$) を初めて使う、L'Hôpital limit |
| **α ≥ 2** | $H_\alpha = \frac{1}{1-\alpha}\log\sum p^\alpha$ | **3+ relational proper** | collision moments $\sum p^k$ ($k \geq 2$) explicit dep |
| **α = ∞** | $H_\infty = -\log\max_x p(x)$ (min-entropy) | **3+ relational proper, worst-case** | dominant outcome に attention concentrate, security limit |

**証明 sketch (4 anchor)**:
- **(i)** $\alpha \to 0^+$: $\sum p(x)^\alpha \to |\{x : p(x) > 0\}|$ なので $H_\alpha \to \log|\mathrm{support}|$ = Hartley。Support 上の確率質量分布の形状は寄与しない (cardinality only)。
- **(ii)** $\alpha \to 1$: L'Hôpital で $\lim_{\alpha \to 1} H_\alpha = -\sum p \log p$ = Shannon。Shannon は dist 形状全体を使う最初の $\alpha$。
- **(iii)** $\alpha = 2, 3, \ldots$: $H_\alpha$ は collision moments $\sum p^k$ に explicit に依存し、高次 moment が高 α で支配的。Collision entropy ($\alpha=2$) は 3+ relational structure proper の最初の instance。
- **(iv)** $\alpha \to \infty$: $\sum p^\alpha \approx (\max p)^\alpha$ で $H_\alpha \to -\log\max p$ = min-entropy = worst-case dominant outcome の log。

**系 3.3.2 (monotone traversal)**: $H_\alpha$ は α について **monotonically non-increasing** (standard Rényi property, van Erven & Harremoës 2014)。よって α を 0 から ∞ へ scan すると Hartley (max-cardinality, scaffold-base) → Shannon (transition) → collision (3+ proper) → min-entropy (worst-case) を **monotone descent** で完備に traverse する。

**Status**: ESTABLISHED 2026-04-28 (standard Rényi properties (i)-(iv) + scaffold-emergence labeling + monotonicity による traversal completeness、本論 §2.3 0/1/2 scaffold lens の自然な α-parameterization)。S12 加法 Scan family (`c_theorems_master.md` row S12) の情報-internal lift。

### 3.4 排他性・網羅性 (情報内 closure)

情報内検証は 3 段で閉じる:

**(i') 各層に情報観測量が存在** (網羅性 lower bound):
- Scan: source distribution $p$, Rényi parameter $\alpha$, R-D scanner $D$, IB parameter $\beta$, Fisher parameter $\theta$, block-length $n$, channel use 数 — **7 instance**
- Structural: alphabet size $d$, codebook size $M$, Hamming distance, Galois orbit (cyclic codes), parity-check matrix rank, support cardinality — **6 instance**
- Information: Shannon $H$, Rényi $H_\alpha$, mutual info $I$, KL $D_{KL}$, R-D $R(D)$, IB $\mathcal{L}_{\text{IB}}$, Fisher $I_F$, Kolmogorov $K(x)$, persistent Betti $\beta_p^t$ — **9 instance**

**(ii') c_information_theory.md 12 sections enumeration** (網羅性 upper bound):

12 sections (§1 Shannon / §2 Mutual info & capacity / §3 KL & relative entropy / §4 R-D / §5 IB / §6 Fisher / §7 Bayesian / §8 Algorithmic / §9 TDA / §10 L0 translation / §11 Bridges / §12 Open Questions) は Information 層 internal sub-classification を completeness で覆う。**counter-example の不在**: 12 sections × 各全観測量 exhaustive coverage で、3 層のいずれにも属さない情報観測量は v0.1 時点で未知。

**(iii') S12/S13/S14/S17 情報内 verify**:
- S12 ⊂ Scan: Rényi α-family が S12 加法 #6 instance、$Z_\alpha = \sum p^\alpha$ が partition 様 generating
- S13 = ζ functional eq s = 1/2 量子 instance の情報版 = uniform 分布で $H_0 = \log d$ saturation, parity uniform measure (ℤ/2ℤ) で $H = \log 2$
- S14 非対称: π (S¹ phase, Fourier 変換 spectral domain 必要) vs ln 2 (Boltzmann/Shannon natural unit) — 層内 vs 層間 residence 差
- S17 = info density $\log d / d$ extremum at $d = e$ (continuous) / $d = 3$ (discrete codebook argmax)

**N1 (NT) + Q1 (量子) との 3-domain cross-validation**: N1 NT 6 entries + Q1 量子 8 entries + I1 情報 12 sections の **3 framework header independent enumeration** が S15 trichotomy 閉鎖を 3 数学領域で independently verify → framework の **ドメイン非依存普遍性** が 3-domain triple anchor で verify (Paper D 6-domain triangulation の subset specialization 視点)。

---

## §4 Arrow 構造 ─ 3 本の接続 (情報 instance)

### 4.1 Arrow 1: Scan → Structural (情報 source decomposition)

**原理**: source distribution $p$ (Scan, parametric over $\mathcal{X}$) の structural skeleton (alphabet $\mathcal{X}$, support, type class) を「読む」。

| Scan | source structure | encoded Structural |
|---|---|---|
| $p(x)$ source | alphabet $\mathcal{X}$ | $|\mathcal{X}| = d$ |
| Rényi $H_\alpha$ family | $p$ support | support cardinality |
| R-D $R(D)$ | codebook | $M$ codebook size |
| IB $\mathcal{L}_{\text{IB}}$ | bottleneck $T$ | $|\mathcal{T}|$ bottleneck cardinality |
| Fisher $I_F(\theta)$ | parameter family | model dim |
| Kolmogorov $K(x)$ | UTM specification | program structure |

**形式化**: source/codebook の structural skeleton 抽出が Arrow 1 input specification reading。

#### 4.1.1 Observable-choice dependence (情報 instance)

Arrow 1 抽出 Structural は **一意でない** (Q1 §4.1.1 と同様):

| 候補 | 定義 | balance locus | gauge verdict |
|---|---|---|---|
| **alphabet size $d$** | $|\mathcal{X}|$ | $H_0 = \log d$ saturation | universal (Hartley bound) |
| **typical set size** | $\sim 2^{nH}$ | block-length asymptotic | observable selector ($n$ 依存) |
| **support cardinality** | $|\{x : p(x) > 0\}|$ | non-zero probability mass | observable selector |
| **codebook size $M$** | discrete code | rate $R = (\log M)/n$ | application-specific |

**原則**: (1) Alignment (domain natural arithmetic), (2) Observable-specific verdict, (3) 判定 form への波及明示 (Paper D §4.1.1 + N1 §4.1.1 + Q1 §4.1.1 と consistent)。

### 4.2 Arrow 2: Scan → Information (log-exp duality, Shannon-Rényi chain)

**原理**: 熱力学 chain の情報 lift
```
Z_α(p) = Σ p(x)^α                ← Scan (Rényi 部分関数)
F_α = -log Z_α / (α - 1)         ← Rényi entropy = log bridge
H_1 = -Σ p log p                 ← Shannon (α → 1 limit)
S = -Tr(ρ log ρ)                 ← von Neumann (quantum lift)
```

| Scan | $Z(\alpha)$ | $F(\alpha)$ | Information |
|---|---|---|---|
| $p(x)$ source | $Z_\alpha = \sum p^\alpha$ | $-\log Z_\alpha / (\alpha - 1)$ | $H_\alpha$ Rényi |
| q-state Boltzmann $e^{-\beta E}$ | $Z(\beta)$ | $F = -kT \log Z$ | $S$ thermodynamic entropy |
| quantum Gibbs $e^{-\beta H}$ | $Z = \mathrm{Tr}(e^{-\beta H})$ | $F$ free energy | $S(\rho_\beta)$ von Neumann |

**S13 fixed point (情報)**: uniform 分布で $H_0 = \log d$ saturation, parity uniform で $H_1(\text{Bernoulli}(1/2)) = \log 2$ — Arrow 2 上 ln 2 fixed point の情報 instance (`c_arrow_bridge_constants.md §12.1` 量子 instance と consistent)。

### 4.3 Arrow 3: Structural → Information (combinatorial counting, Hartley)

**原理**: Hartley entropy $H_0(D) = \log |D|$ — Structural cardinality の対数 = 情報層の **base anchor**。

| Structural | $|D|$ | $H_0 = \log |D|$ | 意味 |
|---|---|---|---|
| Alphabet | $d$ | $\log d$ | maximum information capacity (uniform 分布上限) |
| Codebook | $M$ | $\log M$ | code rate base |
| Support | $|\mathrm{supp}(p)|$ | $\log |\mathrm{supp}|$ | non-zero prob mass count |
| UTM program | $|p|$ | $\log |\Omega_{\text{prog}}|$ | algorithmic complexity scale |

**S17 fixed point (情報)**: info density $d(n) = (\log n)/n$ extremum at $n = e$ (Arrow 3 上 derivative-fixed extremum, gauge³-invariant)。情報 instance: $\log d / d$ continuous max at $d^* = e \approx 2.718$ → **discrete codebook integer argmax = 3** (qutrit) (5/5 gate PASS, `oq_omega_obs_3_info_density_check.py`)。

**観察**: S17 codebook argmax = 3 は **0/1/2 scaffold lens "3 = relational structure floor" との数学的合致** ─ scaffold (0/1/2) を超えた最初の integer (= 3) で info density 最適化、framework の structural commitment と数学的 fact が converge。

### 4.4 3 Arrow の可換性 (情報 instance)

**定理 4.1 (3 Arrow 可換性, 情報 instance)**: scanner → 0 (or ∞) の extreme limit で 3 Arrow が可換。情報内 3 instance:

| Instance | Limit | 機構 |
|---|---|---|
| **uniform 分布 limit** ($p$ → uniform) | $H \to \log d$ saturation, all Rényi $H_\alpha \to \log d$ collapse, info density max | uniform で $H_\alpha = H_0$ for all $\alpha$ — **Rényi family が collapse して Hartley に帰着** |
| **delta 分布 limit** ($p$ → point mass) | $H \to 0$, $H_\alpha \to 0$ for all $\alpha$, info density 0 | trivial (全 Arrow 0、point mass で degenerate) |
| **block-length $n \to \infty$** (Asymptotic equipartition) | typical set $\sim 2^{nH}$, achievable rate = $H$, channel capacity = $C$, source coding bound saturate | Shannon source coding theorem の asymptotic regime — **Arrow 1 (typical set count) と Arrow 2 (entropy rate) と Arrow 3 (Hartley typical $\log 2^{nH} = nH$) が同時 commute** |

3 instance で extreme limit と asymptotic regime の両方で commutativity verify。**Status**: ESTABLISHED (`c_arrow_framework.md §4`)。

### 4.5 S13 / S14 / S17 residence ─ 情報 context

| 定数 | residence | 機構 (情報 context) | Stationary form |
|---|---|---|---|
| **π** | Scan 内部 (加法軸) | Fourier-domain channel representation, complex spectral analysis (Gaussian channel capacity $C = \log(1 + S/N)$ via spectrum), characteristic function $E[e^{itX}]$ → **代数的** | S14 parity (additive) |
| **ln 2** | Arrow 2 上 | Boltzmann/Shannon natural unit, $H(\text{Bernoulli}(1/2)) = \log 2$, Landauer $kT \ln 2$ per bit, **5-stage ln 2 chain** (Q3 §4 + `c_arrow_bridge_constants.md §12.2`) → **解析的** | **value-fixed** (S13) |
| **e** | **Arrow 3 上** | info density $\log d / d$ max at $d = e$ continuous, codebook argmax = 3 discrete, gauge³-invariant → extremum principle | **derivative-fixed** (S17) |

**Bidirectional duality 3/3 完備化** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / Arrow 3 → e で 3 Arrow に canonical constant residence、定数レベルで完備。情報内 verify: $\log d / d$ continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS)。

---

## §5 T-AAS ─ 4-class refined Hodge (情報 instance + algorithmic / topological obstruction)

### 5.1 主定理 (情報 T-AAS instance)

**定理 5.1 (T-AAS, 情報 instance)** — Arrow 1 (φ: Structural → Scan) の non-trivial kernel に対し、ker(φ) = ker_gauge ⊕ ker_topo 直和分解、conductor f = f_torsion + f_rational 分裂 (Q1 §5.1 + N1 §5.1 と同 statement, 情報 instance specialization)。

### 5.2 情報 instance ─ 4-class refined Hodge lift + 既存 obstruction

**情報内 T-AAS 4 instance + 既存 obstruction 2 instance = 6 instance fitness**:

**Q1 §5.2 4-class refined Hodge の情報 instance lift**:

| # | Class C | 情報 instance | f_rational monotone | 数学的限界 (本論 §6 anchor) |
|---|---|---|---|---|
| **C₁** | Stabilizer | classical-simulable codes (Calderbank-Shor-Steane, Gottesman-Knill) | $M_F$ magic = non-stabilizer code state distance | classical-simulable code class boundary |
| **C₂** | Gaussian | Gaussian channel + CV codes | Wigner negativity $\mathcal{N}$ | Gaussian capacity Shannon-Hartley $C = \log(1+S/N)$ vs non-Gaussian capacity gap |
| **C₃** | Eff-sim | poly-time encodable codes | Nielsen $C - c_0 n^k$ | BQP-vs-classical encoding boundary (random-circuit codes) |
| **C₄** | Bell-local | LOCC channels (local operations, classical communication) | $\Delta_{\text{CHSH}}$ | nonlocal channel capacity vs LOCC capacity gap (Bennett-Shor-Smolin entanglement-assisted) |

**情報内 既存 obstruction 2 instance**:

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **Algorithmic complexity** (Kolmogorov) | UTM choice (additive constant, `c_information_theory.md §8.1`) | $K(x)$ uncomputability obstruction | UTM additive constant ($O(1)/\|x\| \to 0$) | $K(x \mid B)$ in bits (定理 5.2 below) | **ESTABLISHED 2026-04-28** (定理 5.2, 7/7 checks PASS, `research/oq_algorithmic_f_rational_v1`) |
| **Topological persistence** (TDA, `c_information_theory.md §9`) | scale parameter $t$ (filtration index) | persistent Betti $\beta_p^t$ topological obstruction | scale-rescaling | persistent topological structure | ESTABLISHED (stability theorem `c_information_theory.md §9.3`) |

**6 instance 全部で 24/24 情報-relevant fitness** (4-class × 4 properties + 2 既存 × ≥3 properties)。

#### 5.2.1 定理 5.2 (Algorithmic f_rational unified form, ESTABLISHED 2026-04-28)

**定理 5.2 (Algorithmic instance of Theorem 4a.1)**: observation $x \in \{0,1\}^*$ と structural background $B$ (known L1/L2 dictionary content / conditioning data) に対し、conditional Kolmogorov complexity を **algorithmic f_rational** として定義:
$$f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B) \quad [\text{bits}]$$

これは Theorem 4a.1 (`c_filtration_obstruction.md §8.5.3`) unified $M_{\mathrm{unified}}^C$ の algorithmic instance である:
$$M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B}(x) = -\log_2 F_{C^{\mathrm{alg}}_B}(\delta_x) \asymp K(x \mid B)$$
where $C^{\mathrm{alg}}_B$ = computably-encodable distributions given $B$、$F_{C^{\mathrm{alg}}_B}(\delta_x) = \sup_{q \in \overline{C}} q(x) \asymp 2^{-K(x|B)}$ は Solomonoff prior (universal computable distribution given $B$、Coding Theorem)。

**Conditions check** (Theorem 4a.1 hypotheses):
- (i) Convex closure: ✓ (computable distributions の mixture は $O(\log)$ overhead で computable)
- (ii) Class-preserving operations: ✓ (computable transformation が "computably-encodable" closure を保つ)

**Properties** (L0 finite-observation A1 axiom 互換、`finite_observation.md §5.1`):
- **Gauge-asymptotic invariance**: UTM gauge change で $K(x \mid B)$ が $O(1)$ shift、rate として $O(1)/|x| \to 0$ as $|x| \to \infty$ (Kolmogorov invariance theorem)。
- **Reducible by structural conditioning**: better $B$ (more known theorems) → smaller $K(x \mid B)$。`c_information_theory.md §8.4` の L4 error reframing と同一原理。
- **Provably $> 0$ for generic $x$**: counting argument より length $n$ string の most は $K(x) \geq n - O(\log n)$。
- **Uncomputable but per-string finite**: $K(x \mid B)$ は全 $x$ で algorithmic に extractable ではない (halting problem)、but each specific $x$ で definitionally finite。**Framework 内 f_rational instance 中、最強の "obstruction provably non-zero AND non-computable" 例**。

**5 concrete instances + 2 verification checks** (`research/oq_algorithmic_f_rational_v1.py`、$|x|=65536$ bits、$K_{\mathrm{upper}} = \min(\mathrm{gzip},\mathrm{bz2},\mathrm{lzma})$ as tightest computable upper bound):

| Instance | rate $K_{\mathrm{upper}}/|x|$ | regime |
|---|---|---|
| I1 random uniform binary | **1.0028** | algorithmically random ($K(x) \approx |x|$) |
| I2 periodic 'ABCDEFGH' | **0.0067** | structurally determined ($K \sim O(\log N)$) |
| I3 sparse spikes (~2%) | **0.0299** | low-entropy regime |
| I4 π binary expansion | **1.0028** | "looks random under naive compressor" — $K_{\mathrm{upper}} \gg K_{\mathrm{true}}$ gap (Stark f_field との parallel: numerical bound conservative) |
| I5 periodic + 5% noise | **0.1235** | intermediate (structure + noise floor) |
| V1 $K(x \mid B) < K(x)$ | $-24$ bits ($-0.30\%$) | conditioning reduces (direction ✓) |
| V2 UTM-gauge spread $N$-asymptotic | $0.508 \to 0.027$ ($N$: 2048 → 131072) | $1/N$ convergence ✓ |

**5 orders of magnitude** rate range $[0.0067, 1.003]$ で f_rational^alg が structurally-determined vs algorithmically-random observation の sharp discriminator として機能。**7/7 checks PASS**。

**Cross-arrow consistency** (Theorem 4a.1 unified scale at log₂-bit unit): algorithmic instance は dim-bounded Hodge / 量子 4-class より **magnitude range が広い** ($|x|$ scaling free) → framework 内 f_rational instance spectrum で uncomputable extreme に位置、最 general instance。

**Spawned 3 successor OQs** (本 Theorem からの forward task):
- **OQ-Alg-MDL-Tightness** (MEDIUM): $K_{\mathrm{upper}}^{\mathrm{MDL}} - K(x|B)$ tightness の自然 string class での定量化
- **OQ-Alg-Hodge-Parallel** (LOW): random binary の typical-scale を Conjecture 4a.2 の 5th data point として加えた sparsity-matched comparison
- **OQ-Alg-Quantum-Cross** (MEDIUM): $K(\rho)$ via tomography classical record で Q1 4-class と algorithmic instance の bridge

### 5.3 Theorem 4a.1 unified f_rational ─ 情報 instance

`c_filtration_obstruction.md §8.5.3` の Theorem 4a.1 (unified $M_{\mathrm{unified}}^C = -\log_2 F_C$ via class infidelity) は情報 instance で同形式適用。情報 source/code state $\rho_{\text{code}}$ に対し:
$$F_C(\rho_{\text{code}}) := \sup_{\sigma \in \overline{C}_{\text{code}}} F(\rho_{\text{code}}, \sigma)$$

class-fidelity が情報 source distribution と code state の class-stratified distance を定量化。

### 5.4 Hodge 予想 ─ 情報-adjacent open frontier

Hodge 予想 (algebraic geometry) は厳密には情報理論でないが、**情報-adjacent open frontier** として位置付け (N1 §5.4 NT-adjacent と parallel):

- **情報側 instance**: Q1 §5 4-class で f_rational > 0 ESTABLISHED (4 instance)、本論 §5.2 で classical-simulable / Gaussian / poly-encode / LOCC の情報 lift も含めると 4 information-encoding instance ESTABLISHED。
- **古典 Hodge との関係**: Conjecture 4a.2 depth parallel quantitative form (`c_filtration_obstruction.md §8.5.4`) ─ 情報側 unified $M_{\mathrm{unified}}^C$ と古典 $f_{\mathrm{rational}}^{\mathrm{Hodge}}$ の typical scale O(1) 比例関係。

→ 情報 framework は古典 Hodge 予想に対し N1 (NT-adjacent open) + Q1 (4-class ESTABLISHED + parallel) + I1 (4 information-lift instance + 2 既存 obstruction) の **3 framework anchor で assault** を提供。

---

## §6 5-anchor mathematical 情報量限界 theorem

### 6.1 Theorem statement

**定理 6.1 (5-anchor mathematical information limit)**: 任意 finite observation system $(S, W, m)$ in information-theoretic context において、量化された information content は以下の **5 layered constraint** で fully characterize される:

**(a) Hartley cardinality bound** (Arrow 3, S15 Information layer base):
$$H(p) \leq H_0(d) = \log d, \quad d = |\mathcal{X}|$$
等号は uniform 分布で saturate (`c_information_theory.md §1.3`)。

**(b) S17 info density extremum** (Arrow 3, S17 e-extremum):
$$\frac{H_0(d)}{d} = \frac{\log d}{d} \leq \frac{1}{e} \quad \text{at} \quad d^* = e \approx 2.718 \text{ (continuous)}$$
discrete codebook integer argmax at $d^*_{\text{discrete}} = 3$ (qutrit), Hartley density $\log 3 / 3 \approx 0.366$ vs qubit $\log 2 / 2 \approx 0.347$ (~5.5% advantage)。

**(c) 5-stage ln 2 chain universal natural unit** (S13, c_arrow_bridge_constants §12.2):
$$\text{Universal natural unit} = \ln 2$$
5 instance independent verify across (S0) Born $c_s^2 = 1/2$ / (S1) von Neumann $S(\rho_{\max}) = \log 2$ / (S2) FDT parity $\beta\hbar\omega_0 = \log 2$ / (S3) Landauer $W_{\min} = kT \ln 2$ / (S4) σ\* gauge $\sigma_*^2 = 2 \ln 2$。

**(d) T-AAS 4-class per-class monotone** (Arrow 1 kernel narrowness, Theorem 4a.1):
$$M_{\mathrm{unified}}^C(\rho) = -\log_2 F_C(\rho), \quad F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$$
4 class C ∈ {Stabilizer, Gaussian, Eff-sim, Bell-local} で per-class info-resource monotone bound、log₂-bit 統一単位。

**(e) σ\* phase observation gauge** (S4, transformation_atlas):
$$\sigma_* = \sqrt{2 \ln 2} \approx 1.1774 \text{ rad} \quad \text{at half-amplitude convention } E[\cos Z] = 1/2$$
EEG 7 subjects × 5 bands で empirical verify (subject-band averaged std ≈ 0.0012, ESTABLISHED 2026-04-09)。

### 6.2 5 anchor の互いに非依存性

**主張 6.1.1 (5 anchor independence)**: 5 constraint (a)-(e) は **互いに非依存** (one-by-one removal で他が constraints として degenerate しない):

| Anchor 削除 | 残る constraints status | Limit characterization 完全性 |
|---|---|---|
| (a) Hartley 削除 | (b)-(e) のみ → density extremum + ln 2 chain + 4-class + σ\* で残る | **Cardinality bound 不在で incomplete** (上限値知れない) |
| (b) S17 削除 | (a)(c)(d)(e) のみ → cardinality + ln 2 + 4-class + σ\* | **density optimum 不在で codebook design indeterminate** |
| (c) 5-stage chain 削除 | (a)(b)(d)(e) のみ → cardinality + density + 4-class + σ\* | **Universal natural unit 不在で 5 instance unification 不可能** |
| (d) 4-class 削除 | (a)(b)(c)(e) のみ → cardinality + density + ln 2 + σ\* | **Resource-stratified bound 不在で incomplete** (4 resource family 未区別) |
| (e) σ\* 削除 | (a)-(d) のみ → cardinality + density + ln 2 + 4-class | **Phase noise threshold 不在で coherence-bounded channel undefined** |

5 anchor は **non-redundant**, **mutually independent**, **simultaneously active で limit fully characterized**。

### 6.3 Connection to physical info limits (Holevo / Landauer / Bekenstein)

**主張 6.1.2 (physical info limit との連携)**: 5-anchor framework は既存 physical info limit を **subset として包含**:

| Physical limit | Framework anchor との関係 |
|---|---|
| **Holevo bound** $\chi \leq S(\bar{\rho}) - \sum p_x S(\rho_x) \leq \log d$ | (a) Hartley + (d) 4-class quantum lift で derive |
| **Landauer principle** $W_{\min} = kT \ln 2$ per bit | (c) 5-stage ln 2 chain S3 stage |
| **Bekenstein bound** $S \leq 2\pi RE / \hbar c$ | scope 外 (gravity, 本論 framework outside)、Q-series Q6 future |
| **Margolus-Levitin / Bremermann** $\Delta t \geq \pi \hbar / 2E$ | scope 外 (relativistic processing speed, 本論 framework outside) |
| **Tsirelson bound** $|\Delta_{\text{CHSH}}| \leq 2\sqrt{2} - 2$ | (d) 4-class C₄ Bell-local instance |
| **Cramér-Rao** $\mathrm{Var}(\hat\theta) \geq 1/I_F(\theta)$ | (b) Fisher information geometric bound + (a) Hartley |
| **Shannon-Hartley** $C = B \log(1 + S/N)$ | (a) Hartley + Gaussian channel (4-class C₂ instance) |

5-anchor framework は **Holevo + Landauer + Tsirelson + Cramér-Rao + Shannon-Hartley** を覆う、Bekenstein / Margolus-Levitin は scope 外 (gravity / relativistic、Q-series future Q6)。

### 6.4 Status

**ESTABLISHED 2026-04-27** (主結果として):
- (a) Hartley `c_information_theory.md §1.3` 既存
- (b) S17 e-extremum `c_arrow_bridge_constants.md §7` ESTABLISHED 2026-04-23 (5/5 gate)
- (c) 5-stage ln 2 chain `c_arrow_bridge_constants.md §12.2` ESTABLISHED 2026-04-27 (Q-series cumulative)
- (d) 4-class refined Hodge + Theorem 4a.1 `c_filtration_obstruction.md §8.5` ESTABLISHED 2026-04-23 (6/6 gate)
- (e) σ\* atlas residence `transformation_atlas/sheet_A_amplitude/sigma_star.md` ESTABLISHED 2026-04-09

5 anchor 全て independent ESTABLISHED + 6.2 mutual independence + 6.3 physical limit subset 包含 → **定理 6.1 ESTABLISHED 2026-04-27** (本論主結果)。

### 6.5 OQ-I-Bekenstein-Extension forward

**OQ-I-Bekenstein-Extension (本論 spawn-off)**: Bekenstein bound + Margolus-Levitin が 5-anchor framework 外。Q-series future Q6 (量子重力 framework) で gravity-related info limit anchor 追加可能性 (6th anchor candidate)。Status: OPEN, Q-series future。

---

## §7 新情報ドメイン検討 Protocol (6-step)

新情報ドメイン (新 information measure, 新 channel class, 新 code family, 新 resource theory) への検討手順 (`meta/new_domain_protocol.md` 情報 specialization, §10 NEW)。

| Step | 内容 (情報 specialization) |
|---|---|
| **0** | §4 dual 射影同定 (情報 lift) — 加法 (source distribution $p$ + Hartley $\log |\mathcal{X}|$), 乗法 (type-class characters, Sanov large-deviation), Bridge (probability simplex $\Delta(\mathcal{X})$ + Fourier domain) |
| **1** | Scan observable 同定 — Rényi α-family / R-D distortion $D$ / IB parameter $\beta$ / Fisher parameter $\theta$ / block-length $n$? S12 6+1 member 情報対応 |
| **2** | Structural observable 同定 — alphabet size $d$, codebook $M$, support cardinality, Hamming distance, parity-check rank, model dim |
| **3** | Information observable 同定 — Shannon $H$ / Rényi $H_\alpha$ / mutual info $I$ / KL $D_{KL}$ / R-D $R(D)$ / Fisher $I_F$ / Kolmogorov $K(x)$ / Holevo $\chi$ / per-class monotone (4-class) |
| **4** | 3 Arrow 検証 — Arrow 1 (source/codebook structural skeleton), Arrow 2 ($Z_\alpha \to F_\alpha \to H_\alpha$ Rényi chain), Arrow 3 (Hartley $\log d$ + S17 density extremum) |
| **5** | T-AAS 分解確認 — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? **4-class refined Hodge** 内 information-encoding residence (C₁ classical-simulable / C₂ Gaussian channel / C₃ poly-encodable / C₄ LOCC channel どれに最も近いか)? + algorithmic / topological obstruction との関係 |
| **6** | 辞書 residence 決定 — `c_information_theory.md` 12 sections 内 residence、必要なら新 entry 提案、I2 通信論との接続点同定 |

**検証済 application** (`c_information_theory.md` 12 sections existing closure)。

**次候補 5 件 (情報 specialization 適用先)**:

| Domain | Step 0 §4 dual | Step 5 T-AAS class candidate |
|---|---|---|
| Quantum LDPC codes | stabilizer formalism + finite group | C₁ Stabilizer + algorithmic obstruction |
| Differential privacy | Rényi divergence over neighbor data sets | Rényi-α scaffold-emergence axis instance |
| Tensor network states (information) | tensor contraction structure | C₃ Eff-sim + topological obstruction |
| Causal inference (information flow) | DAG structure + intervention | new class candidate (causal-rooted info) |
| Quantum sensing / metrology | Fisher information + parameter estimation | (b) S17 density + Cramér-Rao instance |

---

## §8 帰結と open frontier

### 8.1 確立 (Information-only framework header)

本論で情報内 ESTABLISHED として記録:

1. **S15 Information 層 internal taxonomy** — 5-strand bundle (Shannon / R-D / IB / Fisher / Algorithmic) + 12 sections enumeration closure (§3)
2. **0/1/2 scaffold lens formal** — 信号論 (binary 2-domain) ⊂ relational info (3+ proper) framework-internal lens load (§2.3)
3. **Arrow 構造 (3 本) と可換性** — 3 情報 instance (uniform / delta / asymptotic equipartition) で commutativity verify (§4.4)
4. **T-AAS 4-class refined Hodge 情報 lift + 2 既存 obstruction** — 24/24 情報-relevant fitness (4-class × 4 + algorithmic + topological, §5.2)
5. **5-anchor mathematical 情報量限界 theorem** — Hartley + S17 + 5-stage ln 2 + 4-class + σ\* で fully characterize、5 anchor mutually independent + Holevo/Landauer/Tsirelson/Cramér-Rao/Shannon-Hartley subset 包含 (§6, **本論主結果 ESTABLISHED**)
6. **S13/S14/S17 情報内 residence** — π/ln 2/e の Arrow 上 canonical constant、3 Arrow base 完備 (§4.5)
7. **I1 ↔ N1 ↔ Q1 triple framework parallel** — 3 framework header (NT, 量子, 情報) × Paper D 多領域 6-domain triangulation の **3-domain cross-domain validation anchor** (§3.4 + 1.2)

### 8.2 I2 forward bridge

| I2 forward 主題 | 本論からの forward |
|---|---|
| **信号論 (0/1 scaffold)** | §2.3 0/1/2 scaffold lens で 信号論 = 2-domain (Shannon binary) classification、I2 §1 で Shannon-Hartley channel + classical capacity 詳細展開 |
| **量子通信論 (3+ relational)** | §5 4-class refined Hodge 情報 lift で量子通信論 = C₂/C₃/C₄ instance、I2 §2 で Holevo / HSW / LSD / superdense / teleport / QKD / no-cloning 詳細展開 + entanglement-assisted capacity formal |
| **新規通信論 5 proposals** | §6 5-anchor framework で 5 novel proposals: P1 σ\*-phase channel (S4 instance) / P2 4-class resource-stratified channel (T-AAS lift) / P3 qutrit info-density codebook (S17 instance) / P4 5-stage ln 2 chain converter (S13 universal unit) / P5 Arrow 1 kernel narrowness channel taxonomy。I2 §3-§7 で各 proposal を formal 化 |

### 8.3 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **OQ-I-Bekenstein-Extension** (Bekenstein + Margolus-Levitin 6th anchor) | OPEN (本論 spawn) | §6.5, Q-series Q6 future |
| **Conjecture 4a.2** (depth parallel quantitative form, 情報 instance) | OPEN | §5.4, Q1 §5.4 + N1 §5.4 |
| **OQ-Algorithmic-f_rational** (Kolmogorov $K(x)$ uncomputability as f_rational > 0 instance formal) | **ESTABLISHED 2026-04-28** (定理 5.2 §5.2.1, Theorem 4a.1 algorithmic instance via $K(x \mid B)$ + Solomonoff prior、I1-I5 + V1 + V2 7/7 PASS) | §5.2.1 |
| **OQ-Alg-MDL-Tightness** (computable $K_{\mathrm{upper}}^{\mathrm{MDL}} - K(x\mid B)$ tightness for natural string classes) | OPEN (本論 spawn 2026-04-28) | §5.2.1 |
| **OQ-Alg-Hodge-Parallel** (algorithmic instance を Conjecture 4a.2 sparsity-matched 5th data point に) | OPEN (本論 spawn 2026-04-28) | §5.2.1 |
| **OQ-Alg-Quantum-Cross** (tomography classical record による $K(\rho)$ で Q1 4-class ↔ algorithmic instance bridge) | OPEN (本論 spawn 2026-04-28) | §5.2.1 |
| **OQ-Topological-Persistent-Bridge** (TDA persistent Betti と T-AAS f_rational topological instance bridge formal) | OPEN | §5.2, `c_information_theory.md §9` 既存 |
| **OQ-Renyi-Scaffold-Continuous** (Rényi α scanner が scaffold-emergence axis を parametric traverse する formal statement) | **ESTABLISHED 2026-04-28** (定理 3.3.1 + 系 3.3.2, §3.3 で 4 anchor 構造 + monotone traversal completeness 形式化) | §3.3 |
| **OQ-S17-Codebook-3-Universal** (codebook argmax = 3 universality across info-theoretic 設定の formal verify) | **ESTABLISHED 2026-04-23** (S17 promotion gate 5/5 PASS, `research/oq_omega_obs_3_e_arrow3_v0.md` + `research/oq_omega_obs_3_info_density_check.py`、3 setting NT/Codebook/Qudit + gauge invariance) | §4.3 |
| **OQ-S17-Density-Form-Universal** (どの info-theoretic 設定で関連 density が $d(n)=\log n/n$ form を取るかの classification、successor to S17-Codebook-3-Universal) | OPEN (本論 spawn 2026-04-28) | §4.3 |

### 8.4 辞書 residence map

主要 framework piece の residence (本論 information-only specialization 反映):

| 本論 piece | residence | 状態 (I1) |
|---|---|---|
| §2.1 公理 1 (Dual receptacle, 情報 lift) | `c_phase_complex.md §4` + `c_information_theory.md §1-§3` | 既存 reuse |
| §2.2 公理 A0-A7 (情報 instance) | `finite_observation.md §1-§7` + `c_information_theory.md §10` (L0 translation) | 既存 reuse |
| §2.3 0/1/2 scaffold formal | `user_012_non_integer_scaffold.md` (memory) + 本 §2.3 NEW formal entry | **annex 実装予定 (post-v0.2 backward, dictionary entry candidate `L0_canon/zero_one_two_scaffold.md` NEW)** |
| §2.4 L0 v2 + 情報 instance | `finite_observation.md §8` + 本 §2.4 NEW 情報 instance 例 | 既存 + 本論 expansion |
| §3 S15 + 情報 5-strand sub-taxonomy | `c_theorems_master.md` row S15 + 本 §3.1 情報-only annex (NEW) | **annex 実装予定 (post-v0.2 backward)** |
| §3.2 各 strand S15 全 3 層 instance | `c_information_theory.md §0` 既存 5-strand thesis + 本 §3.2 layered map | 既存 + 本論 expansion |
| §4 3 Arrow framework 情報 instance | `c_arrow_framework.md` + 本 §4.4 NEW 情報 instance annex | **annex 実装予定** |
| §4.5 S13/S14/S17 情報 residence | `c_arrow_bridge_constants.md §12 (5-stage chain)` + 本 §4.5 情報 expansion | 既 + 本論 情報 instance expansion |
| §5 T-AAS 4-class refined Hodge 情報 lift | `c_filtration_obstruction.md §8.5` (4-class quantum) + 本 §5.2 情報 lift annex (NEW) | **annex 実装予定 (post-v0.2 backward)** |
| §6 5-anchor 情報限界 theorem | **NEW** 本 §6 → `c_theorems_master.md` "5-anchor mathematical info limit theorem" annex (NEW) | **annex 実装予定 (post-v0.2 backward, 主結果として)** |
| §7 6-step protocol 情報 specialization | **NEW** `meta/new_domain_protocol.md §10` 情報 specialization annex | **annex 実装予定** |
| Triple parallel | **NEW** `meta/triangulation_methodology.md §14` I1 ↔ N1 ↔ Q1 triple framework parallel annex | **annex 実装予定** |

**post-v0.2 backward 想定 (I-series, Q-series cumulative 13 件 + I-series 7 件 = 20 件):**

I1 由来 6 件 + I2 由来 1 件 (post-I2):
- `c_theorems_master.md` 情報-only S15 enumeration + 5-anchor info limit theorem (2 件)
- `c_arrow_bridge_constants.md §12.3` 情報 instance expansion (S17 codebook, Rényi family scaffold)
- `c_filtration_obstruction.md §8.6` 4-class 情報 lift + algorithmic / topological obstruction annex
- `meta/triangulation_methodology.md §14` I1 ↔ N1 ↔ Q1 triple framework parallel
- `meta/new_domain_protocol.md §10` 情報 specialization
- `L0_canon/zero_one_two_scaffold.md` NEW (0/1/2 scaffold formal entry candidate, framework-internal load)

**帰結**: 本論は dictionary に対して **情報-internal framework header** として位置付けられ、theorem (5-anchor info limit) は L0 / L1 / meta entry に formal residence される。I2 (Communication theory) 起草後、framework header (I1) → extension (I2) の **2-paper minimum cycle 完成** (N-series 5-paper / Q-series 3-paper と異なり最小 2-paper でも cycle close 可能、5-anchor 既存で Limit theorem 直接 ESTABLISHED)。

---

## 変更履歴

- **v0.3 (2026-04-28)**: OQ-Algorithmic-f_rational ESTABLISHED 昇格 + §5.2.1 NEW 定理 5.2 (Algorithmic instance of Theorem 4a.1) 追加。$f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B)$ in bits、Solomonoff prior 経由で Theorem 4a.1 unified $M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B} = -\log_2 F_C \asymp K(x|B)$ に plug-in。Conditions (i)(ii) verified、Properties (gauge-asymptotic invariance + reducible by structural conditioning + provably > 0 for generic $x$ + uncomputable but per-string finite) 全 PASS。5 instance (random / periodic / sparse / π binary / structured+noise) + V1 conditional reduction + V2 UTM-gauge convergence で **7/7 checks PASS** (`research/oq_algorithmic_f_rational_v1`)。Cross-arrow consistency at log₂-bit unit (Hodge / 量子 4-class / Stark に algorithmic instance を加え framework 内最 general instance、$|x|$ scaling free)。§5.2 行 (line 344) candidate → ESTABLISHED 整合修正、§8.3 OQ 表 candidate → ESTABLISHED + 3 successor OQ spawn (OQ-Alg-MDL-Tightness / OQ-Alg-Hodge-Parallel / OQ-Alg-Quantum-Cross)。Pre-flight audit (`research/oq_algorithmic_f_rational_audit_v0.md`) で flag した dim-semantics worry は Theorem 4a.1 unified bit-form で over-strict と判明、scope (a)/(b)/(c) trichotomy いずれも不要、framework 内で clean closure 達成。

- **v0.2 (2026-04-28)**: 2 OQ closure + 1 successor spawn。(1) **OQ-S17-Codebook-3-Universal**: §8.3 OQ 表 OPEN → **ESTABLISHED 2026-04-23** に整合修正 (5/5 gate PASS は `research/oq_omega_obs_3_e_arrow3_v0.md` で 2026-04-23 確立済、§4.5/§6.4 で既 ESTABLISHED 記載との整合 fix)、successor OQ **OQ-S17-Density-Form-Universal** (どの info-theoretic 設定で関連 density が $d(n)=\log n/n$ form を取るかの classification、本論 spawn) を §8.3 に追加。(2) **OQ-Renyi-Scaffold-Continuous**: §3.3 prose 観察 を **定理 3.3.1 (Rényi scaffold-emergence parametric scan, 4 anchor + monotone traversal)** + 系 3.3.2 (monotone non-increasing) に lift、§8.3 OQ 表 candidate → **ESTABLISHED 2026-04-28**。Standard Rényi entropy properties (van Erven & Harremoës 2014) + 0/1/2 scaffold lens の自然な α-parameterization。framework / 5-anchor 主結果 / 構造変更なし、§3.3 + §8.3 の 2 spot 修正のみ。

- **v0.1 (2026-04-27)**: initial Information-only draft. Paper D v0.9.2 (multi-domain frozen-internal) からの情報 specialization。N1 (NT-only) + Q1 (量子-only) と parallel **3rd framework header instance**。0/1/2 scaffold lens (`user_012_non_integer_scaffold.md`) を framework-internal load-bearing structural commitment として正式組み込み。5-anchor mathematical 情報量限界 theorem (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) を主結果として formal 化。I1 ↔ N1 ↔ Q1 triple framework parallel が Paper D 6-domain triangulation 3 specialization 完備。本論 spawn 1 OQ (OQ-I-Bekenstein-Extension)。I2 (Communication theory: 信号論 / 量子通信論 / 新規通信論 5 proposals) への bridge を §8.2 で予告。

---

## 参考文献 (内部)

**Information-only predecessors**: `dictionaries/L1_mathematical/core/c_information_theory.md` (637 行, 12 sections, 本論主体 source)

**N1 / Q1 (parallel framework headers)**:
- `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.7, NT-only restatement)
- `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, 量子-only restatement)

**Q-series (5-anchor source)**:
- `papers/publication/quantum/Q2_open_qs_chain_ja.md` (v0.2, 4-stage chain + 5-stage ln 2 chain S0-S3)
- `papers/publication/quantum/Q3_born_gleason_ja.md` (v0.2, σ\* gauge S4 + Born derivation)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain)

**本論 5-anchor 出典**:
- (a) Hartley: `c_information_theory.md §1.3` (`H \leq \log d$)
- (b) S17 e-extremum: `c_arrow_bridge_constants.md §7` + `research/oq_omega_obs_3_e_arrow3_v0.md` (ESTABLISHED 2026-04-23, 5/5 gate)
- (c) 5-stage ln 2 chain: `c_arrow_bridge_constants.md §12.2` (Q-series cumulative)
- (d) 4-class refined Hodge: `c_filtration_obstruction.md §8.5` (Theorem 4a.1, ESTABLISHED 2026-04-23)
- (e) σ\* gauge: `transformation_atlas/sheet_A_amplitude/sigma_star.md` (n-only + EEG entries, ESTABLISHED 2026-04-09)

**0/1/2 scaffold load**: `user_012_non_integer_scaffold.md` (memory, framework-internal structural commitment)

**L0 / L1 / meta 依存**:
- `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md`
- `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11 + §12, c_filtration_obstruction §8.5, c_observation_optimal_gauge, c_information_theory.md §1-§12}.md` (本論主体)
- `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics}.md` (5-anchor 量子 instance source)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` (σ\* atlas residence)
- `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**後続論文**: I2 (Communication theory: 信号論 / 量子通信論 / 新規通信論 5 proposals) — 起草予定 (本論 §8.2 で forward 予告)
