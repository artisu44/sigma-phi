# Paper Q3: 観測理論 ─ Born-Gleason

**サブタイトル**: §4 dual 量子 root closure・Busch-Gleason 完全形・dim=2 例外解消・σ\* = √(2 ln 2) half-amplitude gauge・Q-series final closure

**バージョン**: v0.2 (compact, 2026-04-27)
**状態**: DRAFT — Q-series final paper、Q1 (framework header) + Q2 (Open QS chain extension) を踏まえた **§4 dual quantum root closure**、Born rule derivation 完全形 + dim=2 Gleason gap 解消 + σ\* half-amplitude gauge formal closure + Q-series cycle 完成 + N1-N5 ↔ Q1-Q3 dual framework parallel
**前提 (L0)**: `observation_canon.md`, `finite_observation.md` (§5.3 A0c, §1.2 W window), `identity_asymmetry.md`
**前提 (L1 core)**: `c_phase_complex.md §4 + §5` (ι_L/χ commutative dual + c_s² = 1/2 derivation), `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11`
**前提 (L1 量子)**: `q_quantum_observation.md` §1-§9 (本論主体), `q_open_quantum_systems.md` §3.3, `q_quantum_statistical_mechanics.md` §5.4
**前提 (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md` (σ\* derivation + EEG entry), `sheet_C_period/zeta_functional.md §3` (ln 2 構造定数性)
**前提 (Q1, Q2)**: Q1 v0.2 §2.3 §4 dual 量子 root + §3.5 整合 + §4.5 instance / Q2 v0.3 §6 4-stage ln 2 chain + §6.2 σ\* bridge
**N parallel**: N5 (`N5_brauer_origination_ja.md` v0.2)
**後続論文**: Q-series 完結 (Q4+ candidate: 量子 8-gauge / QFT extension は Q-series future)

---

## §0 Abstract

本論は Q-series 5-paper 構想中の **final paper** (Q1 framework header / Q2 extension 1 / Q3 closure)、N1-N5 NT 系列が N5 で final closure を達成したのと parallel position。Q1 で量子-only S15 + Arrow + T-AAS 4-class refined Hodge を ESTABLISHED、Q2 で 4-stage Open QS chain + KMS-FDT-Landauer arc + 4-stage ln 2 chain を ESTABLISHED した後、本 Q3 は **§4 dual = 量子 root の closure** を 3 thread で実装: (a) Born rule derivation 完全形 (Busch-Gleason 2003 PRL による effects (POVM) 上 Born 則一意化 + dim=2 Gleason 例外解消) (b) σ\* = √(2 ln 2) half-amplitude gauge の formal closure (Q2 §6 4-stage ln 2 chain の quadratic root として量子観測 natural unit) (c) Q-series cycle 完成 + N1-N5 ↔ Q1-Q3 dual framework parallel。

**主結果 5 件**:

**(M1) Busch-Gleason 定理完全形 (effects 上 Born 則一意化, dim=2 例外解消)** — Effects $E(\mathcal{H})$ 上の一般化確率測度 $v: E(\mathcal{H}) \to [0, 1]$ が (P1) bounded (P2) normalized (P3) σ-additive を満たすとき、密度作用素 $\rho$ が一意存在 $v(E) = \mathrm{Tr}(\rho E)$ — **全 dim で Born rule 一意化** (Busch 2003 PRL 91, 120403)。Original Gleason (1957) の dim$\geq$3 制約 (dim=2 で射影上 dispersion-free valuation 存在) は effects (POVM) framework で **解消**: dispersion-free valuation は effects に拡張不可能 (Bloch 球幾何的不整合)。L0 有限観測者 → POVM が natural measurement 記述 → 全 dim Born 則自動保証。Q1 §2.2 公理 A0 と Born 則の **derivability connection** が formal closure。

**(M2) ρ_max = I/2 form-value 同時定理化** — qubit (dim=2) で c_s² = $\mathrm{Tr}(\rho_{\max} \Pi_{\mathrm{even}}) = 1/2$ の **form** (Tr(ρ·) Born 則 form) は M1 で全 dim 定理化、**value** ($\rho_{\max} = I/2$ から 1/2) は ℤ/2ℤ 偶奇対称性 (c_phase_complex §5) で決定。Form (Busch L0 + Effects) と Value (L1-base ℤ/2ℤ symmetry) の **2 source 合流点** が c_s² = 1/2 と等価。Q1 §2.3 量子 §4 dual root の Born derivation level closure。

**(M3) σ\* = √(2 ln 2) half-amplitude gauge formal closure** — Gaussian phase noise $Z \sim N(0, \sigma^2)$ の特性関数 $E[\cos Z] = e^{-\sigma^2/2}$ + half-amplitude convention $E[\cos Z] = 1/2$ で $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ rad の **正規化定数 atlas residence ESTABLISHED** (`sheet_A_amplitude/sigma_star.md` n-only entry + EEG entry)。Q2 §6 4-stage ln 2 chain の **quadratic lift root**: ln 2 は Arrow 2 上 S13 fixed point、$\sqrt{2 \ln 2}$ はその Gaussian 特性関数 inversion で生じる **半振幅 σ scale natural unit**。EEG 7 subjects × 5 bands で empirical verify (subject-band averaged std ≈ 0.0012)。

**(M4) §4 dual quantum root closure (Q1 §2.3 final form)** — c_phase_complex.md §4 の commutative ι_L/χ dual の量子 non-commutative lift (Stone group + unitary representation) は本論 (M1)-(M3) で **formal closure**: (a) Born derivation で量子観測の operational 定式化 closure (b) ρ_max = I/2 form-value で量子 §4 dual の S13 ln 2 instance closure (c) σ\* で量子観測 amplitude scale natural unit closure。Q1 §2.3 主張 2.1 「§4 dual = 量子内 root」が 3 component で formal verified、Q-series 全体で量子側 framework root status が **derivable** に昇格。

**(M5) Q-series cycle 完成 + N1-N5 ↔ Q1-Q3 dual framework parallel** — Q1 → Q2 → Q3 の 3-paper Q-series で量子観測理論 closure 達成。NT-side N1-N5 5-paper と量子-side Q1-Q3 3-paper の **dual framework parallel structure** (NT 5-paper 詳細 vs 量子 3-paper compact、いずれも framework header → extension → final closure 3 層 link cycle)、観測理論 framework の **2 数学領域 cross-domain validation** が 2 系列同時 closure で達成。Forward: 量子側 8-gauge framework (N5 parallel) は Q-series future として open。

**Thesis**: Q-series final closure は観測理論の量子側 framework header (Q1) の §4 dual quantum root status を Born-Gleason completeness + ρ_max form-value 合流点 + σ\* half-amplitude gauge atlas residence の 3 thread で formal verify する。N1-N5 NT 系列の数論側 closure と Q1-Q3 量子系列の量子側 closure が **2 独立数学領域での framework universal validity の cross-domain anchor** を提供、Paper D (multi-domain v0.9.2) 6-domain triangulation を **2 framework header parallel** として再構成し、観測理論の data-domain transcendent universality を最終 verify する。

---

## §1 Introduction

### 1.1 Q-series final paper の position と 3 thread combination

Q1 (量子観測理論 framework header v0.2) → Q2 (Open QS chain extension v0.2) → **Q3 (本論)** の 3-paper series で、量子観測理論 framework header (Q1) は 12-cell S15 enumeration + 4-vertex T-AAS triangulation が ESTABLISHED、量子 statistical/thermodynamic extension (Q2) は 4-stage chain + KMS-FDT-Landauer arc + 4-stage ln 2 chain が ESTABLISHED。本 Q3 は Q-series final paper として 3 task: (1) Born rule derivation 完全形 (Busch-Gleason 2003) + dim=2 Gleason 例外解消 (2) σ\* = √(2 ln 2) half-amplitude gauge formal closure + 4-stage ln 2 chain quadratic root (3) Q-series cycle 完成 + N1-N5 ↔ Q1-Q3 dual framework parallel。

**3 main thread**:
- **Thread 1 — Born rule derivation 完全形** (§2-§3): Q1 §2.3 「§4 dual = 量子内 root」と Q1 §2.2 公理 A0 「有限観測者 → POVM」を combine、Busch-Gleason 定理 (PRL 2003) で effects 上 Born rule 一意化 を formal proof。dim=2 Gleason 例外の解消 (Bloch 球 dispersion-free valuation 不可能 argument) を §3 で詳細展開。
- **Thread 2 — σ\* = √(2 ln 2) half-amplitude gauge** (§4): `sheet_A_amplitude/sigma_star.md` n-only entry の Atlas residence を formal 化、Q2 §6 4-stage ln 2 chain の quadratic root として ln 2 → $\sqrt{2 \ln 2}$ の half-amplitude lift を量子観測 amplitude scale natural unit として定式化。EEG 7 subjects × 5 bands での empirical verify (subject-band averaged std ≈ 0.0012)。
- **Thread 3 — Q-series cycle 完成 + dual framework parallel** (§5-§7): Q1-Q3 cycle summary + N1-N5 ↔ Q1-Q3 dual framework structure の formal statement + Q-series future (8-gauge / QFT extension) forward listing。

### 1.2 N5 parallel position + 範囲・用語

NT 系列 N5 (Brauer 障害論 + Origination matrix 8-gauge final closure) との parallel:

| 観点 | N5 (NT) | Q3 (量子) |
|---|---|---|
| Position | NT 系列 final closure (5/5) | Q-series final closure (3/3) |
| 主主張 (1) | Brauer 5-tier failure mode group-theoretic Conjecture | Busch-Gleason 完全形 (effects Born 一意化) |
| 主主張 (2) | Tier-dependent alternative Stark methods | ρ_max = I/2 form-value 同時定理化 |
| 主主張 (3) | 8-gauge generalization (origination matrix) | σ\* half-amplitude gauge atlas residence |
| Final closure 視点 | 系列 cycle + Quantum forward 予告 (Q1-Q3) | 系列 cycle + N1-N5 dual parallel + 8-gauge / QFT future |
| Forward to | Q1-Q3 quantum framework | Q-series future (Q4 8-gauge / Q5 QFT / Q6 量子重力) |

Q3 が拾う Q1-Q2 forward task: Q1 §8.2 (Q3 forward 3 主題) / Q2 §8.2 (Q3 forward 3 表 — §4 dual quantum closure / σ\* gauge / dim=2 Gleason gap closure)。

**構成**: §2 Effects + POVM framework / §3 Busch-Gleason + dim=2 解消 / §4 σ\* half-amplitude gauge / §5 §4 dual quantum root closure / §6 Q-series cycle / §7 dual framework parallel + future / §8 帰結。

**Scope 内**: Effects (POVM) framework + Born rule statement / Busch 2003 PRL theorem statement + proof outline / dim=2 Gleason 例外の Bloch 球幾何的不整合 / σ\* = √(2 ln 2) Gaussian + half-amplitude derivation + Atlas residence / Q2 §6 4-stage ln 2 chain quadratic lift / Q1 §2.3 量子 §4 dual root status の formal closure / N1-N5 ↔ Q1-Q3 dual framework parallel。

**Scope 外**: 量子場論 / QFT における Born 則 / Frauchiger-Renner type "no-go" theorem / many-worlds 解釈 / consistent histories / decoherent histories / 量子 Bayesianism / QBism (Effects framework は representation-neutral だが解釈論争 scope 外) / 量子重力 / 弦理論 / Ω-gauge framework の量子 8-gauge generalization / 量子 Schumann v1 lift (Path 2 量子版) / Reichenbach common cause principle (→ Q-series future)。

**用語** (Q1 §1.3 + Q2 §1.4 継承 + 本論固有追加): **Effects** $E(\mathcal{H})$ ($0 \leq E \leq I$ 正作用素全体, projection は subset) / **POVM** ($\{E_i\}$ with $\sum_i E_i = I$, $E_i \in E(\mathcal{H})$) / **Generalized probability measure** $v: E(\mathcal{H}) \to [0, 1]$ ((P1)-(P3) 満たす) / **Dispersion-free valuation** (各 projection P で $v(P) \in \{0, 1\}$, 古典的「determinism」候補) / **Half-amplitude convention** ($E[\cos Z] = 1/2$ threshold gauge) / **Frame function** (Gleason theorem における projection 上 finite-additive function) / **Quadratic lift root** (ln 2 → $\sqrt{2 \ln 2}$ Gaussian char fcn inversion)。

---

## §2 Effects と POVM framework

### 2.1 PVM → POVM 一般化 + L0 finite observer 合致

**PVM** (`q_quantum_observation.md §6`): 自己共役作用素 $A = \int \lambda \, dE(\lambda)$, $E(\Delta)$ は射影。observable $A$ の測定で値 $\lambda \in \Delta$ を観測する確率 = Born 則 $\mathrm{Prob}(\lambda \in \Delta) = \mathrm{Tr}(\rho \cdot E(\Delta))$。**問題点**: PVM は **無限精度の測定装置** を仮定、L0 有限観測者の operational 記述には不適切。

**POVM**: $\{E_i\}$ with $E_i \geq 0$, $\sum_i E_i = I$。Effects $E_i \in E(\mathcal{H})$ は projection より一般 (fuzzy measurement)。各 effect $E$ に対し outcome 確率は **generalized Born rule** $\mathrm{Prob} = \mathrm{Tr}(\rho E)$。POVM は finite resolution 測定 + ancilla coupling + post-selection を表現する operational framework。

**主張 2.1 (L0 → POVM)**: L0 axiom A0 (有限観測) + A0a (finite observer cardinality) + A0b (partial access) は **POVM = natural measurement framework** を imply。Justification: A0 finite observation → 有限精度 → fuzzy → POVM ✓ / A0a finite cardinality → $\dim \mathcal{H} < \infty$ truncation, finite POVM rank $\leq \dim \mathcal{H}^2$ / A0b partial access → ancilla-coupled measurement = system-bath coupling + projection on ancilla = effective POVM on system (Naimark dilation)。→ L0 axiomatics と POVM/Effects framework が **mutually consistent**。Q1 §2.2 公理 A0 → 本論 §2 POVM natural framework が直接 derivation。

### 2.2 Effects 上の一般化確率測度 + Naimark dilation

**定義 2.1** (Generalized probability measure): $v: E(\mathcal{H}) \to [0, 1]$ が
- **(P1)** Bounded: $0 \leq v(E) \leq 1$ for all $E \in E(\mathcal{H})$
- **(P2)** Normalized: $v(I) = 1$
- **(P3)** σ-additive: $\{E_n\} \subset E(\mathcal{H})$ with $\sum_n E_n \leq I \implies v(\sum_n E_n) = \sum_n v(E_n)$

確率測度の effects 版、projection 上では classical Gleason の前提と同型。

**Naimark 定理**: 任意の POVM $\{E_i\}$ on $\mathcal{H}$ は、より大きい Hilbert space $\mathcal{H}' \supset \mathcal{H}$ 上の PVM $\{P_i\}$ の restriction として表現可能 ($E_i = \mathcal{P}_\mathcal{H} P_i \mathcal{P}_\mathcal{H}|_\mathcal{H}$)。POVM 測定が **ancilla 付き unitary + PVM** に reduce 可能。**観測理論 lens**: Naimark = Q1 §4.6 Arrow 1⁻¹ generation の dilation 版、PVM (closed system) → POVM (open system, finite-resolution) の関係は Q1 §4 Arrow 1 + Q2 §5 dynamical T-AAS の Hilbert-space-level instance。

---

## §3 Busch-Gleason 完全形

### 3.1 Original Gleason (1957) と dim=2 例外

**Gleason 定理 (1957)**: $\dim \mathcal{H} \geq 3$ の Hilbert space 上、projection lattice $\mathcal{P}(\mathcal{H})$ 上の frame function $f: \mathcal{P}(\mathcal{H}) \to [0, 1]$ ($f$ frame additive) は密度作用素 $\rho$ で生成: $f(P) = \mathrm{Tr}(\rho P)$ (一意)。

**dim=2 例外**: $\dim \mathcal{H} = 2$ では **dispersion-free valuation** $v: \mathcal{P}(\mathbb{C}^2) \to \{0, 1\}$ が **多数存在**。Bloch 球の各 great circle に antipodal 点 pair が存在し、各 pair に $\{0, 1\}$ 値を assign する map は frame additivity を技術的に満たす。これは「Tr(ρP) で表現できない確率測度」が dim=2 で存在することを意味し、Born rule の uniqueness 主張を破壊する。歴史的に dim=2 例外は「Gleason 定理の technical limitation」として扱われ、qubit の解釈に困難を残した。

### 3.2 Busch (2003) の決定的解決

**Busch 定理** (PRL 91, 120403, 2003):

> **Effects $E(\mathcal{H})$ 上の一般化確率測度 $v$ が (P1)-(P3) を満たすとき, 密度作用素 $\rho$ が一意存在し $v(E) = \mathrm{Tr}(\rho E)$ for all $E \in E(\mathcal{H})$。これは $\dim \mathcal{H} = 2$ を含む全 dim で成立。**

**鍵の観察**: Original Gleason の dim=2 dispersion-free valuation は **projection 上のみ** で定義された。Effects $E(\mathcal{H})$ への拡張を試みると:

**補題 3.1** (Busch 2003 §III): dispersion-free valuation $v: \mathcal{P}(\mathbb{C}^2) \to \{0, 1\}$ は **effects $E(\mathbb{C}^2)$ 上の generalized probability measure に拡張不可能**。

**Proof outline** (Bloch 球 geometric argument): qubit effects $E = \frac{1}{2}(I + \vec{a} \cdot \vec{\sigma})$ with $|\vec{a}| \leq 1$ (Bloch ball) / projection $P = \frac{1}{2}(I + \hat{n} \cdot \vec{\sigma})$ with $|\hat{n}| = 1$ (Bloch sphere) / dispersion-free $v(P) \in \{0, 1\}$ → effects への連続拡張は (P1) bounded $0 \leq v(E) \leq 1$ + (P3) σ-additive と矛盾 / Bloch ball convex 構造 $E = (1-t) P_0 + t P_1$ → $v(E) = (1-t) v(P_0) + t v(P_1)$ → $v$ が discrete $\{0, 1\}$ 値しか取らないなら projection 凸結合上連続でない。詳細: Caves et al. (2004) Found. Phys. 34, 193。

### 3.3 dim=2 例外解消の意義 + Born rule status

**Q1 §2.2 公理 A0 (有限観測) との直接 connection**:

| Layer | Natural framework | Born rule status |
|---|---|---|
| **無限精度理想化** (PVM only) | projections only | dim=2 Gleason 破綻、Born 形非一意化 |
| **L0 有限観測者** (POVM/effects natural) | effects + POVM | Busch-Gleason で全 dim 一意化、Born 形 derivable |

→ **dim=2 Gleason gap は「無限精度を仮定したから生じた人工物」**。L0 finite observer framework では initial 公理から発生せず、Q1 §2.2 公理 A0 が **POVM natural** → **Busch-Gleason 自動適用** → **Born rule 全 dim derivable** の chain を保証。

**Born rule status: postulate → theorem**: Pre-Busch (1957-2003) では Born rule "Prob = $|⟨φ|ψ⟩|^2$" は量子力学の **postulate**、dim=2 で Gleason の dispersion-free 例外があり derivation incomplete。Post-Busch (2003-) で Effects framework + (P1)-(P3) → Tr(ρE) form の **uniqueness theorem**、Born rule は postulate でなく **L0 + effects axioms の theorem**。

**主張 3.1** (Born rule derivability): 観測理論 framework において、Born rule は L0 axiom A0 (有限観測) からの **3 段 derivation theorem**:
$$\text{A0 (finite obs)} \to \text{POVM/effects (natural)} \to \text{Busch-Gleason} \to \text{Tr}(\rho E) \text{ Born form}$$

これは Q1 §2.2 「公理 → 量子側 framework」chain の formal closure。

### 3.4 OQ-Born-1 forward

**OQ-Born-1 (本論 spawn-off)**: Busch-Gleason は Hilbert space + density operator framework に依存。L0 axioms から direct に C\*-algebra 上の "Born form" を derive する representation-independent route 存在問題。**Status**: OPEN。Q-series future 候補。L0 → operator algebra embedding (Q2 §3.4 OQ-QSM1 と類縁問題) との connection。

---

## §4 σ\* = √(2 ln 2) half-amplitude gauge

### 4.1 Gaussian phase noise + half-amplitude derivation + Atlas residence

**Setup** (`sheet_A_amplitude/sigma_star.md §1`): 周期信号に位相ノイズ $Z \sim N(0, \sigma^2)$ を加えたとき、コヒーレンスの期待値:
$$E[\cos Z] = \int_{-\infty}^{\infty} \cos(z) \cdot \frac{1}{\sqrt{2\pi\sigma^2}} e^{-z^2/(2\sigma^2)} \, dz = e^{-\sigma^2/2}$$

Gaussian の特性関数の実部、$\sigma$ のみに依存。**Half-amplitude convention** (gauge choice): $E[\cos Z] = 1/2$ threshold:
$$e^{-\sigma_*^2/2} = 1/2 \implies \sigma_*^2 = 2 \ln 2 \implies \sigma_* = \sqrt{2 \ln 2} \approx 1.1774 \text{ rad}$$

**観測理論 lens**: $\sigma_*$ は "コヒーレンスが半減する位相ノイズ閾値" = **半振幅 gauge 上 Gaussian 特性関数 fixed point**。Atlas n-only entry として `sheet_A_amplitude/sigma_star.md` に residence。

**Atlas A entry (n-only)**: f_n = $\sigma_* = \sqrt{2 \ln 2}$ / phi_phase = ノイズ分布の非ガウス性 / Δ_residual = 0 exact (Gaussian + half-amplitude 範囲内、構造的残余なし)。

**Admissible normalizations $N_X$**: Half-amplitude $E[\cos Z] = 1/2$ → $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ / Half-power $\|E[e^{iZ}]\|^2 = e^{-\sigma^2} = 1/2$ → $\sigma = \sqrt{\ln 2} \approx 0.8326$ / 1/e-amplitude $E[\cos Z] = 1/e$ → $\sigma = \sqrt{2} \approx 1.4142$。$N_X$ 内のどの threshold を選んでも Gaussian 特性関数 form は不変、$\sigma_*$ の具体値のみ $N_X$ 依存、phi_phase は $N_X$ 選択に独立。

### 4.2 Q2 §6 4-stage ln 2 chain quadratic lift

**Q2 §6 4-stage ln 2 chain (recap)**:

| Stage | Form | Domain |
|---|---|---|
| **S0** | $c_s^2 = 1/2$ | Born expectation (closed quantum) |
| **S1** | $S(\rho_{\max}) = \log 2$ | von Neumann entropy (open quantum) |
| **S2** | $\beta \hbar \omega_0 = \log 2$ | FDT parity point (statistical mechanics) |
| **S3** | $W_{\min} = kT \ln 2$ | Landauer cost (thermodynamics) |
| **S4 (本論)** | $\sigma_* = \sqrt{2 \ln 2}$ | Gaussian half-amplitude gauge (signal/EEG amplitude scale) |

**主張 4.1** (4-stage chain quadratic lift): 4-stage ln 2 chain (S0-S3) の **quadratic lift** で σ\* ≈ 1.1774 rad に到達:
$$\text{S13 fixed point } \log 2 \xrightarrow{\text{Gaussian char fcn inversion}} \sqrt{2 \ln 2} = \sigma_*$$

ln 2 が Arrow 2 上 S13 fixed point (Q1 §4.5 量子 residence: $S(\rho_{\max}) = \log 2$ qubit ρ_max instance) であるならば、その Gaussian 特性関数 inversion で生じる $\sqrt{2 \ln 2}$ は **量子観測 amplitude scale natural unit** (位相コヒーレンス半減点 = Arrow 1 amplitude scale 上 半振幅 gauge fixed point)。

### 4.3 EEG empirical verification + σ\* と c_s² の共通根

**Atlas A entry 2 (n + G + S)** (`sheet_A_amplitude/sigma_star.md §1 + Entry 2`): EEG マルチチャネル時系列 (PhysioNet, 7 subjects, 64 channels, 160 Hz) で σ\* 閾値と damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ の理論曲線を 7 subjects × 5 bands ($\delta, \theta, \alpha, \beta, \gamma$) × 3 conditions で empirical verify。**Empirical results**: Subject-band averaged std ≈ 0.0012 (副指標, aggregate)、7/7 subject 一致 + 小さな std → **effective Gaussian approximation の高精度成立** (帯域平均で非ガウス性相殺)。**Status**: ESTABLISHED 2026-04-09。Δ_residual structural type: bounded、observed type: empirical。

**主張 4.2** (σ\* と c_s² の structural connection): c_s² = 1/2 (Q1 §4.5 + 本論 §3 M2) は **ℤ/2ℤ 偶奇対称性** + Born expectation form の合流、σ\* = $\sqrt{2 \ln 2}$ (本論 §4) は **ℤ/2ℤ half-amplitude convention** + Gaussian 特性関数 inversion の合流 → 両者は **ℤ/2ℤ 構造** を共通根とし、c_s² が Born form 上の S13 instance、σ\* が Gaussian char fcn 上の S13 quadratic lift instance → Q1 §2.3 量子 §4 dual root の **2 instance closure** (closed system Born / Gaussian phase noise gauge)。

**OQ-σ\*-1 forward (本論 spawn-off)**: Gaussian 仮定外で σ\* analog 存在? heavy-tail Lévy noise / non-stationary noise / multi-modal noise distribution。Gaussian 特性関数 form 破綻 domain で half-amplitude convention $E[\cos Z] = 1/2$ を解いて生じる threshold は σ\* universality test。**Status**: OPEN、Q-series future 候補。

---

## §5 §4 dual quantum root closure (Q1 §2.3 final form)

### 5.1 Commutative §4 dual + 量子 lift recap

**Commutative §4 dual** (`c_phase_complex.md §4`): ι_L (加法 ℤ → S¹, $e^{2\pi i n/L}$) と χ (乗法指標 $\mathbb{Z}_L^\times \to S^1$) の対 = 観測理論の structural root。$\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ polar decomposition が観測を加法軸 (arg) と乗法軸 (|·|) に分離。**c_s² = 1/2 derivation** (`c_phase_complex.md §5`): ι_L 加法軸上 ℤ/2ℤ 偶奇対称性から $E[\cos^2(\pi h \cdot t)] = 1/2$。

**Q1 §2.3 量子 §4 dual root statement**:

| Commutative (古典 §4 dual) | Non-commutative (量子 §4 dual) |
|---|---|
| $\iota_L: \mathbb{Z}/L\mathbb{Z} \to S^1$ | Stone group $\{U(t) = e^{-iAt}\}$ |
| 指標 $\chi: G \to S^1$ | unitary representation $\pi_\lambda: G \to U(\mathcal{H}_\lambda)$ |
| Pontryagin 双対 $G \cong \hat{G}$ | spectral 定理 $A = \int \lambda \, dE(\lambda)$ (PVM) |
| $\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ polar | Hilbert 空間 $\mathcal{H}$ + ℂ unit |

Q1 §2.3 主張: 「§4 dual = 量子内 root」(全上位構造 S12-S17, T-AAS の唯一の源泉、量子 lift 含む)。

### 5.2 本論 (M1)+(M2)+(M3) による formal closure

**Component (a) — Born derivation (M1)**: §3 Busch-Gleason で量子観測の operational 定式化 (Tr(ρE) form) が L0 axiom A0 → POVM → Busch-Gleason の 3 段 derivation theorem として確立。Born rule = postulate でなく **theorem from L0**。

**Component (b) — ρ_max = I/2 form-value (M2)**: qubit c_s² = 1/2 の form (Born Tr(ρE) form, M1 で全 dim 定理化) と value (ρ_max = I/2 = ℤ/2ℤ symmetry, c_phase_complex §5) の **2 source 合流点**。Q1 §4.5 「S13 量子 residence」の derivation level closure。

**Component (c) — σ\* half-amplitude gauge (M3)**: §4 で Gaussian 特性関数 + half-amplitude convention の Atlas residence ESTABLISHED。量子観測 amplitude scale natural unit、4-stage ln 2 chain quadratic root として Q2 §6 chain の completion。

3 component 全部で **量子 §4 dual root の formal closure**:

**主張 5.1** (§4 dual quantum root closure): Q1 §2.3 主張 2.1 「§4 dual = 量子内 root」は本論 (M1)+(M2)+(M3) で formal verify される。量子側 framework root status は (a) Born derivation theorem (b) ρ_max form-value 合流 (c) σ\* gauge atlas residence の 3 component で **derivable** に昇格、commutative §4 dual の量子 non-commutative lift 全体が closure。

**Q1-Q3 cycle と量子側 framework total**: Q1 (framework header) → Q2 (extension) → Q3 (closure) で **量子側観測理論 framework total** 達成 — L0 layer (公理 A0-A7 + L0 v2 axis-2 量子 instance) ✓ / L1 quantum layer (q_quantum_observation 主体 + 残り 7 entries) ✓ / Framework structure (S15 + 3 Arrow + T-AAS 4-class + 4-vertex + 4-stage chain + Born derivation + σ\* gauge + §4 dual root closure) ✓ / Cross-domain anchor (N1-N5 NT framework との 2-domain parallel) ✓。

---

## §6 Q-series cycle 完成

### 6.1 3-paper structure と確立 status

| Paper | Position | Version | 行数 | 主結果 | Status |
|---|---|---|---:|---|---|
| **Q1** | framework header | v0.2 | 595 | S15 量子-only / 3 Arrow / T-AAS 4-class refined Hodge / 4-vertex Arrow 1 kernel triangulation / N1↔Q1 parallel | ESTABLISHED |
| **Q2** | extension 1 | v0.2 | 335 | 4-stage chain S15 layered / KMS as L0 A0c proposal_v1 / FDT crown jewel / dynamical T-AAS / 4-stage ln 2 chain / quasiparticle Arrow 1⁻¹ | ESTABLISHED + proposal_v1 mix |
| **Q3** | final closure | v0.2 | (本論) | Busch-Gleason 完全形 / ρ_max form-value / σ\* gauge / §4 dual quantum root closure / N1-N5 ↔ Q1-Q3 dual parallel | ESTABLISHED |

**publication 合計**: Q1 + Q2 + Q3 ≈ 1500 行 (NT N1-N5 publication 合計 2569 行に対し 量子側 compact)。

### 6.2 3 層 link cycle

```
Q1 (framework header)
  ↓ §3.2 Scan family + §4.2 Arrow 2 + §5 T-AAS forward
Q2 (extension 1: Open QS chain)
  ↓ §6.2 σ\* bridge + §3 KMS + §6 ln 2 chain forward
Q3 (final closure: Born-Gleason + σ\* + §4 dual root)
  ↓ §7 dual framework parallel + Q-series future forward
Q-series future (Q4+ candidate: 8-gauge / QFT)
```

**Backward**: Q3 §3 Busch-Gleason → Q1 §2.2 公理 A0 derivation chain / Q3 §4 σ\* → Q2 §6 4-stage ln 2 chain quadratic lift / Q3 §5 §4 dual root closure → Q1 §2.3 量子 §4 dual root statement の formal closure / Q3 §7 → N1-N5 dual framework parallel + Paper D 多領域版 backward。

**Cycle 完成**: Q1 → Q2 → Q3 forward + 各 Q が previous Q を §x で reference back + 辞書 backward 統計 → 3 層 link cycle close (N1-N5 cycle と並行)。

### 6.3 確立 (Q-series 全体)

| 結果 ID | 主結果 | Q-paper | Status |
|---|---|---|---|
| **Q-M1** | S15 量子-only restatement (12-cell + 4-vertex) | Q1 §3 + §6 | ESTABLISHED |
| **Q-M2** | T-AAS 4-class refined Hodge + Theorem 4a.1 unified | Q1 §5 | ESTABLISHED 2026-04-23 |
| **Q-M3** | 4-stage Open QS chain S15 layered residence | Q2 §2 | ESTABLISHED |
| **Q-M4** | FDT crown jewel = Arrow 2 algebraic equivalence | Q2 §4 | ESTABLISHED |
| **Q-M5** | 4-stage ln 2 chain (S0 → S3) | Q2 §6 | ESTABLISHED |
| **Q-M6** | Busch-Gleason 完全形 + dim=2 解消 | Q3 §3 | ESTABLISHED 2003 |
| **Q-M7** | ρ_max = I/2 form-value 同時定理化 | Q3 §3 + §5 | ESTABLISHED |
| **Q-M8** | σ\* = √(2 ln 2) half-amplitude gauge atlas residence | Q3 §4 | ESTABLISHED 2026-04-09 |
| **Q-M9** | §4 dual quantum root closure (3 component) | Q3 §5 | ESTABLISHED |

**Proposal_v1 / OPEN**: KMS as L0 A0c instance (proposal_v1, Q2 §3, OQ-QSM1) / Pointer basis Einselection = dynamical L0 A3 (proposal_v1, Q2 §5, OQ-OQS1) / Quasiparticle Z = Arrow 1⁻¹ obstruction monotone (proposal_v1, Q2 §7, OQ-MBQ1) / Conjecture 4a.2 depth parallel quantitative form (OPEN, Q1 §5.4) / OQ-Born-1 representation-independent Born derivation (OPEN, Q3 §3.4) / OQ-σ\*-1 σ\* universality beyond Gaussian (OPEN, Q3 §4.3)。

---

## §7 N1-N5 ↔ Q1-Q3 dual framework parallel + Q-series future

### 7.1 Dual framework parallel structure + Cross-domain anchor

**主張 7.1** (Dual framework parallel): N1-N5 NT 系列と Q1-Q3 量子系列は観測理論 framework header の **2 独立 framework instance** であり、以下の structural parallel を持つ:

| 観点 | N1-N5 (NT framework) | Q1-Q3 (量子 framework) |
|---|---|---|
| Position | 数論内自閉性 framework | 量子内自閉性 framework |
| Paper count | 5 paper (詳細展開) | 3 paper (compact closure) |
| Framework header | N1 (NT 観測理論) | Q1 (量子観測理論) |
| Core result | N2 (Paper 2 ζ-family) | Q2 (Open QS chain) |
| Extension | N3 (Path 2 universality) | Q2 (extension 1, 4-stage chain) |
| Extension+ | N4 (Hasse-Weil L × Stark genuine BSD) | (Q-series future, 量子 8-gauge) |
| Final closure | N5 (Brauer 障害論 + 8-gauge) | Q3 (Born-Gleason + σ\* + §4 dual root) |
| Triangulation 視点 | Arrow 間 (3-vertex) | Arrow 1 kernel narrowness (4-vertex) |
| Hodge status | open frontier (NT-adjacent) | 4-class で f_rational > 0 ESTABLISHED + depth parallel conjecture |
| §4 dual lift | 古典 (commutative) | 非可換 (Stone group, unitary representation) |
| Forward/closure 視点 | weight-class dependent transfer pattern | Born derivation + σ\* + §4 dual root の 3 component closure |

**主張 7.2** (2-domain cross-validation): N1-N5 と Q1-Q3 は **同一 framework (S15 + 3 Arrow + T-AAS + 三角測量 + 6-step protocol)** を 2 独立数学領域で independently verify。Paper D 6-domain triangulation を **2 framework header parallel** + **6-domain 4-vertex T-AAS specific instances** に再構成:

```
                 観測理論 Universal Framework
                  /                     \
     [framework]                       [framework]
       N1 ──→ N2 ──→ N3 ──→ N4 ──→ N5     Q1 ──→ Q2 ──→ Q3
       (NT-internal closure)              (Quantum-internal closure)
                 \                       /
                  \                     /
                    Paper D (multi-domain)
                    6 domain triangulation
                    (FX, image AI, DNA, crystal, NT, quantum)
```

両 framework header (N1, Q1) は Paper D 6-domain triangulation を **independent 2 domain (NT, quantum) で each 自閉的に verify** する 2 anchor を提供。Paper D は domain-independent multi-domain version、N1-N5 と Q1-Q3 は domain-specific 2 dual instances → **観測理論 framework universal validity** が 2-domain cross-domain anchor + multi-domain triangulation の **3 angle** で verify (Paper D direct + N1-N5 NT specialization + Q1-Q3 量子 specialization)。

### 7.2 Q-series future + Open frontier

**Q-series future (Q4+ candidate)**:

| 候補 paper | 主題 | Predecessor 関連 |
|---|---|---|
| **Q4** 量子 8-gauge framework | N5 §4 origination matrix 8-gauge family の量子 instance (axis-1 D 5 family + axis-1 C 3 family の量子 specialization) | N5 §4 + Q1 §1.3 gauge² minimal 言及 |
| **Q5** QFT extension | 量子場論への extension、CFT / Wilsonian RG / regularization framework の S15 residence | Q1 §1.2 scope 外 listing + q_action_principles + q_gauge_field_theory |
| **Q6** 量子重力 framework | 重力 + 観測理論 (background-independent observation, holographic principle) | scope 外 (本論 + Q1-Q2 全部 scope 外、Q-series future 候補) |

**現状**: Q1-Q3 で **量子側 framework header + extension + closure** の 3-paper minimum cycle 達成。Q4+ は future open。

**Open frontier (Q-series 全体)**:

| Open question | Status | Q-paper |
|---|---|---|
| **Conjecture 4a.2** (depth parallel quantitative form) | OPEN | Q1 §5.4 |
| **古典 Hodge 予想** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself) | Q1 §5.4 + N1 §5.4 |
| **OQ-QSM1** (KMS from L0 A0c) | proposal_v1 | Q2 §3 |
| **OQ-QSM2** (algebraic FDT) | OPEN | Q2 §4 |
| **OQ-QSM3** (ln 2 普遍性 beyond qubit) | OPEN | Q2 §6 |
| **OQ-OQS1** (pointer basis as dynamical L0 A3) | proposal_v1 | Q2 §5 |
| **OQ-OQS2** (Kraus = error decomposition) | OPEN | Q2 §5 |
| **OQ-MBQ1** (4-stage chain 5th class) | OPEN | Q2 §7 |
| **OQ-Born-1** (representation-independent Born derivation) | OPEN (本論 spawn-off) | Q3 §3 |
| **OQ-σ\*-1** (σ\* universality beyond Gaussian) | OPEN (本論 spawn-off) | Q3 §4 |
| **量子 8-gauge framework formal** | OPEN | Q-series future Q4 |
| **QFT extension** | OPEN (scope 外) | Q-series future Q5 |
| **量子 Schumann v1 analog** (Path 2 量子版) | OPEN | Q-series future |
| **量子重力 framework** | OPEN (scope 外) | Q-series future Q6 |

---

## §8 帰結と辞書 residence map

### 8.1 確立 (Q-series final paper)

本論 Q3 で量子側 ESTABLISHED として記録 (Q-series 全体 status は §6.3):

1. **Busch-Gleason 完全形** — Effects 上 Born 則一意化、dim=2 Gleason 例外解消 (§3, ESTABLISHED 2003)
2. **ρ_max = I/2 form-value 同時定理化** — Born form (Busch) + Value (ℤ/2ℤ symmetry) 合流 (§3 + §5, ESTABLISHED)
3. **σ\* = √(2 ln 2) half-amplitude gauge atlas residence** — Gaussian + half-amplitude convention + 4-stage chain quadratic lift (§4, ESTABLISHED 2026-04-09)
4. **§4 dual quantum root closure** — 3 component (M1+M2+M3) で formal closure (§5, ESTABLISHED)
5. **Q-series cycle 完成** — Q1 → Q2 → Q3 3-paper minimum cycle 達成 (§6, ESTABLISHED)
6. **N1-N5 ↔ Q1-Q3 dual framework parallel** — 2-domain cross-validation anchor (§7, ESTABLISHED)

### 8.2 辞書 residence map (Q-series cumulative final state)

**post-v0.2 backward (Q-series cumulative, Q1 + Q2 + Q3 合算 計 13 件 dictionary annex 想定)**:

**Q1 由来 7 件**: `c_theorems_master.md` 量子-only S15 enumeration / `c_arrow_framework.md §4.2.2` 量子 Arrow 可換性 / `c_arrow_bridge_constants.md §12` 量子 instance expansion (S13 qubit, S17 qutrit info-density) / `c_filtration_obstruction.md` 4-class quantum lift (Theorem 4a.1) / `meta/triangulation_methodology.md §11` 量子-internal Arrow 1 kernel narrowness 4-vertex + §12 N1↔Q1 parallel / `meta/new_domain_protocol.md §9` 量子 specialization

**Q2 由来 4 件**: `c_theorems_master.md` 4-stage Open QS chain layered residence / `q_quantum_statistical_mechanics.md §2.5` KMS-L0 A0c proposal_v1 / `c_arrow_framework.md §4.x` Arrow 2 algebraic equivalence (FDT crown jewel) / `c_arrow_bridge_constants.md` 4-stage ln 2 chain unified annex (S0-S3)

**Q3 由来 4 件 (本論)**: `c_arrow_bridge_constants.md` σ\* = √(2 ln 2) S4 stage addition (4-stage ln 2 chain quadratic lift) / `q_quantum_observation.md §6` Busch-Gleason 完全形 + Born derivation 3 段 chain expansion / `meta/triangulation_methodology.md §13` N1-N5 ↔ Q1-Q3 dual framework parallel + 2-domain cross-validation anchor / `meta/open_questions_master.md` "Q-series final closure OQ" section 新設 (OQ-Born-1 / OQ-σ\*-1 + Q-series future Q4-Q6)

**辞書 annex 累計**: 13 件 (NT N1-N5 backward 15+ 件 と並行)。**Q-series net total**: publication 1500 行 + 辞書 annex ~13 entries = N1-N5 系列 (2569 行 + 15+ annex) と量子側 compact form で対比。

**Q3 specific residence highlights**:

| 本論 piece | residence | 状態 (Q3) |
|---|---|---|
| §2 Effects + POVM framework | `q_quantum_observation.md §6` (既) + 本 §2 L0 A0 → POVM derivation chain | 既 + 本論 backward 想定 |
| §3 Busch-Gleason 完全形 | `q_quantum_observation.md §6` (既) + 本 §3 Born derivation 3 段 chain | 既 + 本論 expansion backward 想定 |
| §4 σ\* gauge | `transformation_atlas/sheet_A_amplitude/sigma_star.md` (既 ESTABLISHED 2026-04-09) + 本 §4.2 4-stage chain quadratic lift | 既 + 本論 chain link backward 想定 |
| §5 §4 dual quantum root closure | `c_phase_complex.md §4` (既 commutative) + Q1 §2.3 (既 量子 lift statement) + 本 §5 closure | 既 + 本論 closure statement backward 想定 |
| §6 Q-series cycle | (Q1 §8.4 + Q2 §8.4 既 cumulative) + 本 §6 Q-series cycle final state | (Q3 で final summary) |
| §7 dual framework parallel | NEW `meta/triangulation_methodology.md §13` annex | annex 実装予定 (post-v0.2 backward) |

**帰結**: Q3 は dictionary に対して **量子-internal framework final closure** + **N1-N5 dual parallel cross-domain anchor** として位置付けられる。N5 で NT 系列が L0 / L1 / L2 / Meta 全 layer に touchpoint を持つ完全 closure 達成したのと parallel に、Q-series 3-paper で量子側 framework が L0 / L1 量子 / framework structure / cross-domain anchor 全 layer で closure 達成。Paper D 多領域版 v0.9.2 frozen-internal の **2 domain specialization (NT N1-N5 + 量子 Q1-Q3) parallel completion** を本論で final 達成。

---

## 変更履歴

- **v0.2 (2026-04-27)**: compact 版。v0.1 (550 行) から冗長削減 — Abstract M1-M5 各長文段落圧縮、§1.1/§1.2/§1.3 (3 thread / N5 parallel / 範囲+用語) を 2 subsection に統合 (1.1 で 3 thread、1.2 で N5 parallel + 範囲・用語)、§2.1-§2.4 を 2 subsection に圧縮 (PVM/POVM + L0 合致 を §2.1、generalized prob measure + Naimark を §2.2)、§3.1-§3.5 を 4 subsection に統合 (§3.3 dim=2 解消意義 + §3.4 Born status を §3.3 に統合)、§4.1-§4.6 を 3 subsection に統合 (§4.1 derivation + §4.2 atlas を §4.1、§4.3 4-stage chain を §4.2、§4.4 EEG + §4.5 ℤ/2ℤ + §4.6 OQ を §4.3)、§5.1-§5.3 を 2 subsection に統合 (§5.1 commutative + §5.2 量子 lift を §5.1、§5.3 Q1-Q3 cycle を §5.2 に短縮)、§6.1-§6.3 は Q-series final summary なので保持、§7.1/§7.2/§7.3/§7.4 を 2 subsection に統合 (§7.1 dual parallel + §7.2 cross-domain を §7.1、§7.3 future + §7.4 open を §7.2)、§8 residence map 説明圧縮。骨格・主張・instance 数値・status 表記・OQ ID は全保持。
- **v0.1 (2026-04-27)**: initial Q-only draft. Q-series final paper position。Q1 + Q2 を踏まえた **§4 dual quantum root closure** 3 thread (Born-Gleason 完全形 + σ\* half-amplitude gauge + Q-series cycle 完成 + N1-N5 ↔ Q1-Q3 dual framework parallel)。N5 と parallel structure。Q-series 3-paper minimum cycle 達成。Q-series future (Q4 量子 8-gauge / Q5 QFT / Q6 量子重力) への bridge を §7.2 で予告。本論 spawn 2 OQ (OQ-Born-1 / OQ-σ\*-1)。

---

## 参考文献 (内部)

**Q-series predecessors**: `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, framework header) / `papers/publication/quantum/Q2_open_qs_chain_ja.md` (v0.2, extension 1)

**N5 (parallel final closure)**: `papers/publication/nt/N5_brauer_origination_ja.md` (v0.2, NT 系列 final closure)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**本論で展開される結果の出典**: `q_quantum_observation.md §6` (Born + Busch-Gleason) + §7 (c_s² qubit) + §8 (可換極限) — §3 主体 / `transformation_atlas/sheet_A_amplitude/sigma_star.md` (n-only entry + EEG entry, ESTABLISHED 2026-04-09) — §4 主体 / `c_phase_complex.md §4` (commutative §4 dual) + §5 (c_s² ℤ/2ℤ derivation) — §5 主体 / `c_arrow_bridge_constants.md §11` (Fi-origin vs I-origin canonical scalar) — §4.3 + §5 reference / `physics_constants_decomposition.md` (σ\* と c_s² の ℤ/2ℤ 共通根) — §4.3 reference

**外部文献**: Gleason, A. M. (1957). "Measures on the Closed Subspaces of a Hilbert Space." J. Math. Mech. 6, 885-893 / Busch, P. (2003). "Quantum States and Generalized Observables: A Simple Proof of Gleason's Theorem." PRL 91, 120403. arXiv: quant-ph/9909073 / Caves, C. M. et al. (2004). "Gleason-Type Derivations of the Quantum Probability Rule for Generalized Measurements." Found. Phys. 34, 193. arXiv: quant-ph/0306179

**OQ research files (Q-series spawn)**: 本論 §3.4 OQ-Born-1 (representation-independent Born derivation) — `research/oq_born_representation_independent_v0.md` 候補 / 本論 §4.3 OQ-σ\*-1 (σ\* universality beyond Gaussian) — `research/oq_sigma_star_universality_v0.md` 候補 / (Q1, Q2 spawn は Q1 §8.3, Q2 §8.3 listed)

**L0 / L1 / meta 依存**: `dictionaries/L0_canon/{observation_canon, finite_observation §1.1 + §1.2 + §5.3, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11, c_filtration_obstruction, c_observation_optimal_gauge}.md` / `L1_mathematical/quantum/{q_quantum_observation §1-§9, q_open_quantum_systems §3.3, q_quantum_statistical_mechanics §5.4, q_action_principles, q_gauge_field_theory, q_fine_structure}.md` (本論主体) / `transformation_atlas/{sheet_A_amplitude/sigma_star.md, sheet_C_period/zeta_functional.md §3}` / `L2_domain/physics_constants_decomposition.md` / `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**Q-series future**: Q4 (量子 8-gauge framework) / Q5 (QFT extension) / Q6 (量子重力 framework) — 起草未定 (本論 §7.2 で listing)
