# Paper I2: 観測理論 ─ Communication theory

**サブタイトル**: 信号論 (0/1/2 scaffold) / 量子通信論 (3+ relational, 量子優位 formal) / **新規通信論 5 proposals** (framework 由来) / I-series final closure

**バージョン**: v0.4 (§4.5 NEW Discrete dual marginal extension via spectral lift — 6 sub-section: 動機 / 2-route (native vs spectral lifted) / §13.7 4-step pipeline + symbol mapping / first measurement (precision floor + prime gap WIN=4096 AUC 0.93) / 3 receiver-choice regimes (σ_0 / σ_x / σ_flip = 2.396 G3 transcendental) + Δ_dual = 1.604 bit/sym richness gain / 7 use case map (forward to §11.5 RESOLVED v0); §11.5 OQ-Practical-Tradeoff-Quantification RESOLVED v0; §10.3 OQ table updated. 2026-04-30 late dusk +2; v0.3.1 σ\* identity REJECTED + σ_0 PROMOTED 2026-04-30 evening; v0.3 W₁/W₂ gauge-conditioning 2026-04-30 朝; v0.2 P1 capacity 2.18 → 0.40 bits/symbol 2026-04-28)
**状態**: DRAFT — I-series final paper、I1 (framework header + 5-anchor 情報量限界) を踏まえた **通信論 3 階層** (信号論 / 量子通信論 / 新規通信論) + I-series cycle 完成 + 3 framework header (N1-N5 / Q1-Q3 / I1-I2) triple cross-domain anchor 完備
**前提 (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**前提 (L1 core)**: `c_phase_complex.md §4 + §5`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11 + §12`, `c_filtration_obstruction.md §8.5`, `c_observation_optimal_gauge.md`, **`c_information_theory.md` §2 (channel capacity), §6 (Fisher, Cramér-Rao)**
**前提 (L1 quantum)**: `q_quantum_observation.md` §5 (Schmidt + entanglement) + §6 (Born/POVM), `q_open_quantum_systems.md` §3 (mutual info), `q_quantum_statistical_mechanics.md` §5 (FDT)
**前提 (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md`
**前提 (I1)**: I1 v0.3 §6 5-anchor 情報量限界 theorem + §2.3 0/1/2 scaffold formal + §5 4-class refined Hodge 情報 lift (incl. §3.3 定理 3.3.1 Renyi parametric scan + §5.2.1 定理 5.2 Algorithmic f_rational)
**N parallel**: N5 (`N5_brauer_origination_ja.md` v0.2) — NT 系列 final closure と parallel position
**Q parallel**: Q3 (`Q3_born_gleason_ja.md` v0.2) — 量子系列 final closure と parallel position
**後続論文**: I-series 完結 (Q-series Q4-Q6 future と並行で I-series future も open)

---

## §0 Abstract

通信論 (communication theory) はドメイン無関係な 3 階層構造 ─ **信号論** (0/1/2 scaffold base) / **量子通信論** (3+ relational structure proper) / **新規通信論** (framework 由来 5 proposals) ─ で系統化される。本論は I1 (Information-only framework header + 5-anchor 情報量限界 theorem) を踏まえた I-series final closure paper、N5 (NT final closure) + Q3 (Quantum final closure) と parallel position。

**主結果 5 件**:

**(M1) 信号論 (0/1/2 scaffold base) S15 + Arrow framework lens 再読み** — Shannon-Hartley channel $C = B \log_2(1 + S/N)$ + BSC/BEC/AWGN channels + source coding theorem + max mutual information capacity を 0/1/2 scaffold lens で binary 2-domain instance として位置付け、Information-internal 5-strand sub-taxonomy (`c_information_theory.md §2`) 内 Shannon channel strand specialization。

**(M2) 量子通信論 (3+ relational) formal characterization** — Holevo bound $\chi \leq S(\bar\rho) - \sum p_x S(\rho_x) \leq \log d$ + HSW classical capacity over quantum channels + LSD quantum capacity + superdense coding (1 qubit + entanglement = 2 cbits, **2x density 量子優位**) + teleportation (2 cbits + entanglement = 1 qubit) + QKD BB84 + no-cloning + Bennett-Shor entanglement-assisted classical capacity $C_E = 2 \log d$ vs no-entanglement $C \leq \log d$ (entanglement-assisted **2x advantage formal**)。**量子優位 formal characterization** = T-AAS C₄ Bell-local f_rational instance (Q1 §5, Δ_CHSH nonlocal capacity = 量子優位 mathematical anchor)。

**(M3) 新規通信論 5 proposals (framework 由来)** — (P1) **σ\* phase-channel** (Q3 §4 σ\* gauge instance, EEG ESTABLISHED, **honest Shannon capacity $C_{\sigma_*} \approx 0.40$ bits/symbol** — uniform-input wrapped-Gaussian phase channel, M1 (closed-form) + M2 (Blahut-Arimoto) cross-check, `research/oq_p1_capacity_v0`; v0.4 で **§4.5 discrete-domain extension** 追加 — spectral lifted dual pipeline (τ + FFT + r,θ + Φ) + 3 σ-threshold receiver-choice regime (σ_0 = √(2π/e − 1) / σ_x ≈ 1.193 / σ_flip ≈ 2.396 G3 transcendental) + Δ_dual = ½ log₂(8π/e) ≈ 1.604 bit/sym richness gain + 7 engineering use case map) / (P2) **4-class resource-stratified channel** (T-AAS lift, 各 class が異なる capacity sub-channel) / (P3) **qutrit info-density codebook** (S17 e-extremum discrete argmax, qubit に対し ~5.5% Hartley density 優位) / (P4) **5-stage ln 2 chain converter** (S13 universal natural unit を媒介する cross-instantiation channel) / (P5) **Arrow 1 kernel narrowness channel taxonomy** (Q1 §6 4-vertex sparsity classification を channel design に lift)。各 proposal は I1 §6 5-anchor framework から **直接 derive**。

**(M4) I-series cycle 完成 + Triple framework parallel** — I1 (framework header + 5-anchor 情報量限界 theorem) → I2 (本論 communication theory + 5 novel proposals) の **2-paper minimum cycle** 達成 (N-series 5-paper + Q-series 3-paper と異なり最小 2-paper closure、5-anchor 既存で limit theorem 直接 ESTABLISHED な情報側特性)。N1-N5 (NT) + Q1-Q3 (量子) + I1-I2 (情報) の **3 framework header complete = triple cross-domain anchor** 完備、Paper D 6-domain triangulation を 3 specialization fully verify する **観測理論 3-domain universal validity anchor** 達成。

**(M5) 通信論 unified framework (Shannon ⊂ Holevo ⊂ 5-anchor framework)** — 信号論 (Shannon) は 5-anchor framework anchor (a) Hartley + Shannon-Hartley channel の specialization、量子通信論 (Holevo) は 5-anchor (a) Hartley + (d) 4-class + (b) S17 の combination、新規通信論 5 proposals は 5-anchor 各 anchor を通信 paradigm として lift。**5-anchor framework が信号論 / 量子通信論 / 新規通信論 を unified に subsume** する。

**Thesis**: 信号論 → 量子通信論 → 新規通信論 5 proposals の 3 階層通信論は 0/1/2 scaffold lens (信号論 = scaffold base) → 3+ relational structure proper (量子通信論 = 関係性) → framework-derived novel paradigm (5 proposals = 5-anchor lift) で formal 化される。N1-N5 NT 系列の数論側 closure / Q1-Q3 量子系列の量子側 closure / I1-I2 情報系列の情報側 closure が **3 数学領域での framework universal validity の triple cross-domain anchor** を提供、Paper D 多領域版 v0.9.2 frozen-internal の **3 domain specialization parallel completion** を本論で final 達成。Forward: I-series future (4th framework header / 多域 communication / 量子重力 communication) は open。

---

## §1 Introduction

### 1.1 I-series final paper position と 3 階層通信論

I1 (Information-only framework header v0.1, 558 行) → **I2 (本論)** の 2-paper series で、情報観測理論 framework header (I1) は 0/1/2 scaffold lens + S15 Information layer 5-strand internal taxonomy + 5-anchor 情報量限界 theorem が ESTABLISHED。本 I2 は I-series final paper として **3 階層通信論** を formal 化:

**3 階層通信論 structure**:

| Layer | 主題 | 0/1/2 scaffold position | framework anchor |
|---|---|---|---|
| **Layer 1** | **信号論** (Shannon-Hartley channel) | 0/1/2 scaffold base (binary 2-domain) | I1 §6 anchor (a) Hartley + Shannon-Hartley channel = `c_information_theory.md §2` |
| **Layer 2** | **量子通信論** (Holevo / HSW / LSD / superdense / QKD) | 3+ relational structure proper (Hilbert dim ≥ 2 で genuine, dim ≥ 3 で full proper) | I1 §6 anchor (a) Hartley + (d) 4-class + (b) S17 combination |
| **Layer 3** | **新規通信論** (5 framework-derived proposals) | 5-anchor 全 5 anchor を通信 paradigm として lift | I1 §6 5-anchor framework 直接 derive |

各 Layer は前 Layer を **保存 + 拡張** する cumulative structure: Layer 1 ⊂ Layer 2 ⊂ Layer 3。

### 1.2 N5 / Q3 parallel position

NT 系列 N5 (Brauer 障害論 + Origination matrix 8-gauge final closure) + 量子系列 Q3 (Born-Gleason §4 dual quantum root closure) と parallel I-series final closure paper:

| 観点 | N5 (NT) | Q3 (量子) | I2 (情報, 本論) |
|---|---|---|---|
| Position | NT 系列 final closure (5/5) | 量子系列 final closure (3/3) | I-series final closure (2/2) |
| 主主張 (1) | Brauer 5-tier failure mode group-theoretic | Busch-Gleason 完全形 (effects Born 一意化) | 信号論 (0/1/2 scaffold) Shannon-Hartley |
| 主主張 (2) | Tier-dependent alternative Stark methods | ρ_max = I/2 form-value 同時定理化 | 量子通信論 量子優位 formal (Holevo + entanglement-assisted 2x) |
| 主主張 (3) | 8-gauge generalization (origination matrix) | σ\* half-amplitude gauge atlas residence | **新規通信論 5 proposals** (framework 由来 novel paradigms) |
| Final closure 視点 | NT cycle + Quantum forward (Q1-Q3) | Quantum cycle + N1-N5 dual parallel + 8-gauge / QFT future | **I-series cycle + Triple framework parallel + I-series future open** |
| Forward to | Q1-Q3 (NT → Quantum forward) | Q-series future Q4-Q6 (Quantum 8-gauge / QFT / 量子重力) | I-series future (4th framework header / 多域 communication) |

### 1.3 本論の範囲 + 用語

**構成**: §2 信号論 (0/1/2 scaffold base) / §3 量子通信論 (3+ relational, 量子優位 formal) / §4-§8 新規通信論 5 proposals (P1-P5) / §9 通信論 unified framework / §10 帰結 + I-series cycle + triple parallel。

**Scope 内**: Shannon-Hartley channel + classical capacity (信号論) / Holevo / HSW / LSD / superdense / teleport / QKD / no-cloning / entanglement-assisted capacity (量子通信論) / σ\* phase channel / 4-class resource-stratified channel / qutrit codebook / 5-stage ln 2 converter / Arrow 1 kernel taxonomy (5 novel proposals) / I1 ↔ N1 ↔ Q1 triple framework parallel completion (本論で final 達成) / 通信論 unified framework via 5-anchor。

**Scope 外** (本論で扱わない): network coding 詳細 / multi-user information theory / Wyner-Ziv / Slepian-Wolf 詳細 / specific quantum error correction codes (CSS / surface / topological codes detail) / device-independent QKD protocol details / quantum repeater architecture / continuous-variable QKD specific protocols (CV-QKD) / 量子場論 communication / 量子重力 communication (→ I-series future) / classical complexity-theoretic communication (Yao's communication complexity) / category-theoretic information flow / cybersecurity engineering details。

**用語**: I1 §1.3 + Q1 §1.3 用語継承。本論固有の追加用語:

- **Quantum advantage**: 量子通信が classical (Shannon) を超える dim/capacity ratio (典型 2x via entanglement-assisted)
- **Resource-stratified channel**: 4-class refined Hodge (C₁-C₄) 各 class が独立 channel sub-class を定義する framework-derived channel taxonomy
- **5-stage ln 2 converter**: ln 2 universal natural unit を媒介とする cross-instantiation channel (S0 Born ↔ S1 von Neumann ↔ S2 FDT ↔ S3 Landauer ↔ S4 σ\*)
- **Phase-coherence channel**: σ\* = √(2 ln 2) half-amplitude gauge を encoding threshold とする phase-noise-bounded channel
- **Arrow 1 kernel narrowness channel**: Q1 §6 4-vertex sparsity classification (discrete-in-cont / poly-in-inf / poly-in-exp / classical-polytope-in-quantum-correlation-body) を channel design に lift した taxonomy
- **Triple framework anchor**: I1 ↔ N1 ↔ Q1 = NT / 量子 / 情報 3 framework header の cross-domain validation

---

## §2 信号論 (0/1/2 scaffold base) ─ Shannon-Hartley channel framework

### 2.1 Shannon-Hartley channel formal

**Shannon channel** (`c_information_theory.md §2`): A channel $W(y|x)$ from input $\mathcal{X}$ to output $\mathcal{Y}$ with capacity:
$$C = \max_{p_X} I(X; Y) = \max_{p_X} [H(Y) - H(Y|X)]$$

**Shannon-Hartley theorem** (Gaussian additive channel, $Y = X + Z$, $Z \sim N(0, N)$):
$$C = \frac{1}{2} \log_2(1 + S/N) \text{ bits per use}$$

ここで $S$ = signal power, $N$ = noise power, $S/N$ = SNR。

**観察**: Shannon-Hartley は **0/1/2 scaffold base** = binary 2-domain で完結する classical communication framework。$S/N$ scanner で capacity が monotone increase、$S/N \to \infty$ で $C \to \infty$ (信号論 unbounded limit)。

### 2.2 0/1/2 scaffold lens で Shannon-Hartley を再読み

I1 §2.3 0/1/2 scaffold formal table の **Layer 2 (signal scaffold, $d = 2$)** instance として Shannon channel framework が完結:

| 0/1/2 scaffold layer | Shannon-Hartley instance |
|---|---|
| **0 (potential)** | no signal, $S/N = 0$, $C = 0$ |
| **1 (reference)** | observer 1-bit reference (single distinction baseline) |
| **2 (binary signal)** | $C = \log 2 = 1$ bit per use minimum (BSC noiseless) |
| **2 + scaling** | $C = \log_2(1 + S/N)$ continuous scaling within binary scaffold |
| **3+ (relational)** | scope 外、量子通信論 §3 で開始 |

**信号論 = 2-domain instance of 5-anchor framework**: I1 §6 anchor (a) Hartley $H \leq \log d$ で $d = 2$ binary case + Gaussian channel (4-class C₂ instance) で Shannon-Hartley が **5-anchor framework subset** として derive される。

### 2.3 BSC / BEC / AWGN channels ─ 信号論 standard instances

| Channel | Definition | Capacity | 0/1/2 scaffold layer |
|---|---|---|---|
| **BSC** (binary symmetric) | $W(0|1) = W(1|0) = p$ | $C = 1 - h(p)$, $h(p) = -p \log p - (1-p)\log(1-p)$ | 2 (binary scaffold) |
| **BEC** (binary erasure) | $W(?|x) = \epsilon$, else 1 | $C = 1 - \epsilon$ | 2 (binary scaffold) |
| **AWGN** (additive white Gaussian) | $Y = X + Z$, $Z \sim N(0, N)$ | $C = \frac{1}{2} \log_2(1 + S/N)$ | 2 + continuous scaling (Gaussian = 4-class C₂) |
| **DMC** (discrete memoryless) | general $W(y|x)$ | $C = \max_{p_X} I(X; Y)$ | 2 generic |

**Shannon source coding theorem**: $N$ i.i.d. symbols compressible to $NH(X) + o(N)$ bits (`c_information_theory.md §1.2`)。Shannon channel coding theorem: rate $R < C$ achievable, $R > C$ impossible。

### 2.4 信号論 の 0/1/2 scaffold base としての完結性

**主張 2.1** (信号論 scaffold completeness): Shannon-Hartley framework は **0/1/2 scaffold base 内で classical 完結**、Layer 1-2 instance を full closure で覆う。Layer 3+ relational structure proper は **scope 外** (Holevo bound + 量子通信論 §3 で開始)。

**0/1/2 scaffold lens で view**:
- 信号論 = $d = 2$ binary 2-domain instance + Shannon-Hartley continuous extension
- $d \geq 3$ qudit channels は 信号論 scope 外 (3+ relational, 量子通信論 §3)
- 信号論 capacity bound $C \leq \log_2 d = \log_2 2 = 1$ bit/symbol per binary scaffold

→ 信号論は I1 §6 5-anchor の **anchor (a) Hartley + Gaussian channel (C₂ instance) の specialization**、量子通信論で 3+ relational structure proper extension が始まる。

---

## §3 量子通信論 (3+ relational structure proper) ─ 量子優位 formal characterization

### 3.1 Holevo bound (3+ relational base)

**Holevo bound** (Holevo 1973): 量子状態 $\{(\rho_x, p_x)\}$ ensemble に対する classical information capacity:
$$\chi(\rho_x, p_x) = S(\bar{\rho}) - \sum_x p_x S(\rho_x) \leq \log d$$

ここで $\bar\rho = \sum p_x \rho_x$, $S(\rho) = -\mathrm{Tr}(\rho \log \rho)$ von Neumann entropy, $d = \dim \mathcal{H}$。

**HSW theorem** (Holevo-Schumacher-Westmoreland 1998): 量子 channel $\Phi$ over classical inputs の **Holevo capacity** $\chi(\Phi) = \max_{\{(\rho_x, p_x)\}} \chi(\Phi(\rho_x), p_x)$ achievable + matching converse → **classical capacity over quantum channel** = $\chi(\Phi)$。

**LSD theorem** (Lloyd-Shor-Devetak 2005): 量子 channel の **quantum capacity** $Q(\Phi) = \lim_{n \to \infty} \frac{1}{n} I_c(\Phi^{\otimes n})$, $I_c$ coherent information, achievable + matching converse。

### 3.2 量子優位 formal: superdense coding + entanglement-assisted capacity

**Superdense coding** (Bennett-Wiesner 1992): 共有 entanglement (Bell state) + 1 qubit transmission で **2 cbits 相当 information transfer**:
- Pre-shared $|\Phi^+\rangle = (|00\rangle + |11\rangle)/\sqrt{2}$
- Alice applies $I, X, Y, Z$ (4 choices = 2 cbits encoded) to her qubit
- Send qubit to Bob, Bob measures Bell basis → recover 2 cbits
- → **1 qubit + entanglement = 2 cbits, 2x density 量子優位**

**Teleportation** (Bennett-Brassard-Crepeau-Jozsa-Peres-Wootters 1993): 共有 Bell state + 2 cbits = 1 qubit transmission。

**Entanglement-assisted classical capacity** $C_E$ (Bennett-Shor 2002): 共有 entanglement free な setting で:
$$C_E(\Phi) = \max_\rho [S(\rho) + S(\Phi(\rho)) - S((\Phi \otimes \mathrm{id})(\Psi_\rho))]$$

**Bennett-Shor 1999, 2002 主張**: 多くの quantum channels で $C_E \approx 2 C$ (no-entanglement classical capacity の **2x**) ─ entanglement-assisted で classical capacity が **doubled**。

**主張 3.1 (量子優位 formal characterization)**: 量子通信の classical (Shannon) に対する優位は以下 5 form で formal characterize される:

| Form | Mechanism | Framework anchor | Quantitative advantage |
|---|---|---|---|
| **Superdense coding** | 共有 Bell state + 1 qubit = 2 cbits | I1 §6 anchor (d) C₄ Bell-local instance | **2x density** |
| **Teleportation** | 2 cbits + Bell state = 1 qubit | I1 §6 anchor (d) C₄ Bell-local instance | quantum state transfer (classical impossible) |
| **Entanglement-assisted capacity** $C_E \approx 2C$ | shared entanglement free assistance | I1 §6 anchor (d) C₄ + (a) Hartley | **2x classical capacity** |
| **QKD info-theoretic security** | no-cloning + Bell state monogamy | C₄ + no-cloning theorem | **info-theoretic security** (cryptographic, classical impossible) |
| **Holevo bound saturation** at $d \geq 3$ | qudit (qutrit+) で $\chi$ achievable up to $\log d$ | (a) Hartley + (b) S17 e-extremum | **density 優位** for $d \geq 3$ |

5 量子優位 form は全て **3+ relational structure proper** 内で initially 出現 (信号論 0/1/2 scaffold では impossible)。

### 3.3 No-cloning theorem ─ 量子情報 copy obstruction

**No-cloning theorem** (Wootters-Zurek 1982, Dieks 1982): 任意 unknown 量子状態 $|\psi\rangle$ を copy する unitary operation $U: |\psi\rangle |0\rangle \to |\psi\rangle |\psi\rangle$ は **存在しない** (linearity + unitarity 矛盾)。

**Information-theoretic implication**: 量子情報は Shannon framework の "perfectly copyable bit" assumption を **structurally violate** ─ 量子通信は **information replication restriction** を内在的に持つ。

**Framework lens**: no-cloning は I1 §5.2 T-AAS instance ─ Arrow 1⁻¹ generation (`c_arrow_obstruction.md §11`) の量子 instance、unknown 状態の cloning が ker_topo > 0 obstruction (`c_filtration_obstruction.md §8.5` 4-class C₂/C₃ Eff-sim instance: poly-time copy circuit non-existence)。

### 3.4 BB84 QKD ─ 量子優位 cryptographic instance

**BB84 protocol** (Bennett-Brassard 1984): Alice + Bob 共有 secret key を no-cloning + measurement disturbance で **info-theoretically secure** に generate:
- 4 量子 states $\{|0\rangle, |1\rangle, |+\rangle, |-\rangle\}$ (2 mutually unbiased bases) で encode
- Eve の interception は no-cloning + measurement disturbance で **detectable**
- Privacy amplification + error correction で final key 生成

**Information-theoretic security**: classical Shannon framework で impossible (one-time pad は key exchange の chicken-and-egg)、量子 framework で no-cloning + measurement disturbance により **直接 derive**。

**Framework lens**: BB84 は 4-class C₄ Bell-local instance + no-cloning T-AAS Arrow 1⁻¹ obstruction + Born rule measurement (Q3 §3 Busch-Gleason Born derivation) の **3 anchor combined info-theoretic security guarantee**。

### 3.5 量子通信論の 3+ relational structure proper としての position

**主張 3.2** (量子通信論 = 3+ relational structure proper instance): 量子通信論は **3+ relational structure proper** (I1 §2.3 0/1/2 scaffold lens Layer 3+) で始まる:
- $d = 2$ qubit case は scaffold/proper boundary (信号論 ∩ 量子通信 boundary)
- $d \geq 3$ qudit case (qutrit+) で **genuine multi-state relational structure**
- entanglement = Schmidt rank $\geq 2$ (Q1 §3.3 Structural instance) で initially proper
- Holevo $\chi \leq \log d$ saturation at $d \geq 3$ で qutrit+ density 優位 (S17 codebook argmax = 3)

→ 量子通信論は **5-anchor framework anchor (a) + (d) + (b) combination** = 信号論 (anchor (a) only) からの genuine extension。

---

## §4 P1: σ\* phase-channel (Q3 §4 σ\* gauge instance)

### 4.1 Proposal definition

**P1 σ\* phase-channel**: Gaussian phase noise $Z \sim N(0, \sigma^2)$ + half-amplitude convention $E[\cos Z] = 1/2$ で定義される **phase-coherence-bounded communication channel**:
- **Encoding**: information を phase coherence levels $\theta \in [0, \sigma_*]$ で encode、$\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ rad threshold
- **Channel transform**: $E[\cos Z] = e^{-\sigma^2/2}$ で coherence decay
- **Decoding threshold**: $\sigma < \sigma_*$ で coherent (info preserved), $\sigma \geq \sigma_*$ で half-amplitude broken (info loss)

### 4.2 提案 channel capacity

**主張 4.1 (P1 honest Shannon capacity, v0.2 corrected)**: σ\* phase-channel の channel capacity:
$$C_{\sigma_*} = \log_2(2\pi) - h(\mathrm{WG}(\sigma_*)) \approx 0.40 \text{ bits per phase symbol}$$
ここで $h(\mathrm{WG}(\sigma))$ は wrapped Gaussian (std $\sigma$) の differential entropy、$\sigma_* = \sqrt{2\ln 2}$。

**Derivation**: channel $\phi = \theta + N \pmod{2\pi}$, $N \sim \mathrm{WG}(\sigma_*)$。$h(\phi|\theta) = h(\mathrm{WG}(\sigma_*))$ は input 非依存。Wrapped-Gaussian convolution が uniform を保つため uniform input が optimal、$h(\phi) = \log_2(2\pi)$ saturation で capacity 達成 (`research/oq_p1_capacity_v0.py` M1 closed-form + M2 Blahut-Arimoto cross-check, M=512 で 1.7e-4 bits agreement)。

**v0 retraction note**: v0 (本論 initial draft) で記載した $C \approx 2.18$ bits/symbol は **2 issues** で over-stated だった: (a) Hartley level count $\log_2(2\pi/\sigma_*^2)$ を Shannon mutual-info capacity と取り違え (Hartley は cardinality bound, Shannon は achievable rate)、(b) "level count" の denominator が dimensional に $\sigma_*$ (linear width, rad) であるべきところで $\sigma_*^2$ (variance, rad²) を使用。両 error が compound して inflation ratio ≈ 5.5× (`research/oq_p1_capacity_v0.md` §3, §6)。

**Comparison to Shannon-Hartley (gauge-conditioned, v0.3)**:

AWGN 比較式 $C_{\mathrm{AWGN}}(\sigma; S) = \frac{1}{2} \log_2(1 + S/\sigma^2)$ は **入力信号 power $S$ を指定しないと答えが定まらない**。物理的に自然な 2 gauge は反対方向の verdict を与える (`research/oq_p1_noise_sweep_v0.md`):

| Gauge | $S$ | 物理 setup | 低-σ asymptotic gap $C_{P1} - C_{\mathrm{AWGN}}$ | crossover $\sigma_x$ |
|---|---|---|---|---|
| **W₁ unit-amplitude carrier** | $1$ | 振幅固定 1 の phase-modulated carrier (位相変調 + 受信側で位相雑音 σ rad ↔ 振幅雑音 σ) | $+\frac{1}{2} \log_2(2\pi/e) \approx +0.604$ bits | $\sigma_x \approx 1.193 \approx 1.014\,\sigma_*$ |
| **W₂ equal second moment** | $\pi^2/3$ | AWGN 入力分散を uniform-on-circle (variance $\pi^2/3$) と整合させた equal-moment setup | $+\frac{1}{2} \log_2(6/(e\pi)) \approx -0.254$ bits | sweep 範囲 $[0.05, 3.0]$ で無し |

**主張 4.2 (gauge-conditioned phase-AWGN Pareto)**: P1 σ\* phase channel は **W₁ gauge の下で** σ < σ_x ≈ 1.014 σ\* で AWGN density advantage を持ち、σ_x 近傍で AWGN に追い越される。**W₂ gauge の下では** AWGN が swept 範囲全体で dominant、phase advantage は消失する。"phase channel が AWGN に勝つか" は gauge-free の問いではなく、**比較 gauge $W$ を fix して初めて closed-form で決まる gauge-conditioned transition law** (advantage / crossover / asymptotic gap が $W$ の関数として determined)。invariant は "phase が勝つ" ではなく **transition law それ自体**。

**主張 4.3 (W₁ Pareto boundary 3-constant 構造、v0.3.1 R1 reframing)**: W₁ gauge での Pareto boundary は **3 distinguishable constants** で characterize される (`research/oq_p1_pareto_g1_v0.md`):

| Constant | Origin | Closed form | Numerical | Role |
|---|---|---|---|---|
| **σ_0** | Low-σ approx (no wrapping) crossover | $\sqrt{2\pi/e − 1}$ | $1.14519$ | **exact low-noise Pareto boundary** (candidate_v0, bridge constants {2π, e, −1}) |
| **σ_x** | Full wrapped-Gaussian crossover (K=1 single-wrap saturated) | none known | $1.19305$ | **numerical full Pareto boundary** |
| **σ\*** | Half-amplitude $E[\cos Z] = 1/2$ ($q = 1/2$) | $\sqrt{2 \ln 2}$ | $1.17741$ | **interior near-marker** at 67%-along [σ_0, σ_x] |

3 constants は **互いに不一致**: σ_0 < σ\* < σ_x、relative spacing $(\sigma_* - \sigma_0)/(\sigma_x - \sigma_0) \approx 0.671$。q-axis でも $q_x = 0.4908 \neq q_* = 0.5$ (1.84% off)。**σ\* = σ_x strict identity (v0.3 朝の主張) は G1 test で REJECTED** — wrapping correction trajectory (K = 0, 1, 2, …, ∞) は σ\* を pass through せず σ_x で settle、numerical floor (10⁻⁷) でも closed しない real gap 1.33%。

**σ_0 closed-form derivation**: $C_{P1}^{\mathrm{low}\text{-}\sigma}(\sigma) = \tfrac12 \log_2(2\pi/(e\sigma^2))$ と $C_{\mathrm{AWGN}}(\sigma; 1) = \tfrac12 \log_2(1 + 1/\sigma^2)$ を等置すると $\sigma_0^2 = 2\pi/e - 1$。combination $2\pi/e$ は同時に **gap-zero gauge** $S = 2\pi/e$ (W₁/W₂ canonical pair の中点、低-σ asymptotic gap = 0) としても登場 — σ_0 は σ-axis Pareto, $S = 2\pi/e$ は S-axis neutral gauge の **σ ↔ S 双対**。bridge constants $\{2\pi, e\}$ が 3 canonical gauge $\{W_1, W_0, W_2\}$ と σ-axis Pareto を **同時に pin** する。

**σ_x single-wrap saturation**: σ_x^(K=1) = σ_x^(K=2) を 9·10⁻⁸ で agree、real-space wrap count $K \geq 1$ で saturated。wrapping correction が **single wrap で完了** — K≥2 corrections は numerical floor 以下、構造的 "first-wrap-dominant" property (本論 secondary structural finding)。

**~2x density advantage 主張**: 旧 (v0) 主張 REJECTED は v0.2 で確定 (`research/oq_p1_capacity_v0.md`)。v0.3 朝は W₁/W₂ gauge-split closed-form 表現に refine。**v0.3.1 evening は v0.3 朝の "σ\* = Pareto boundary 1.4% 内一致" claim を strict identity 棄却 + σ_0 = √(2π/e − 1) を新主役 candidate に reframe** (R1 reframing、`research/oq_p1_pareto_g1_v0.md §4-§6`)。

**σ\* の honest Shannon-theoretic 解釈 (v0.3.1、2-reading + interior-marker)**: σ\* は (i) wrapped-Gaussian phase channel の capacity が ≈ ½ bit/symbol を切る noise level + (ii) "half-amplitude $E[\cos Z] = 1/2$" gauge threshold (q = 1/2 exact) の **2 ESTABLISHED reading** を持ち、加えて (iii') Pareto segment [σ_0, σ_x] の **interior near-marker (67%-along)** として位置付けられる。**(iii) "σ\* = Pareto boundary" strict identity は v0.3 朝 で提唱 → 同日 v0.3.1 evening で REJECTED** (G1 test 1.33% gap robust)。σ\* primary residence (S4 ESTABLISHED, Atlas A `sheet_A_amplitude/sigma_star.md`) は不変、本 §4.2 で追加 reading は (iii') interior-marker のみ。

### 4.3 EEG empirical verification + framework anchor

**EEG verified ESTABLISHED 2026-04-09** (`sheet_A_amplitude/sigma_star.md` Entry 2): 7 subjects × 5 bands ($\delta, \theta, \alpha, \beta, \gamma$) で σ\* phase damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ subject-band averaged std ≈ 0.0012 → P1 phase-channel が **biological signal context で empirical 動作確認済**。

**Framework anchor**: P1 は I1 §6 anchor (e) σ\* phase observation gauge の通信 paradigm lift。新規性: phase-noise-bounded channel が standalone communication paradigm として **quantitative capacity** $C_{\sigma_*}$ 提案。

### 4.4 Status

**P1 status**: candidate_v0.3.1 (honest Shannon capacity ≈0.40 bits/symbol established by M1+M2 cross-check + AWGN 比較 gauge-conditioned (W₁/W₂/W₀ 3-gauge canonical scaffold) + W₁ Pareto boundary が **3-constant 構造** に R1 reframed: σ_0 = √(2π/e − 1) closed-form low-noise Pareto candidate_v0 / σ_x ≈ 1.1931 numerical full (K=1 single-wrap saturated) / σ\* interior near-marker 67%-along、EEG 動作確認、framework 概念 (phase-noise-bounded channel) 保持)。

- **OQ-P1-Capacity** → CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED (`research/oq_p1_capacity_v0.md` 2026-04-28)、v0 2.18 bits/symbol claim retracted、replaced 0.40 bits/symbol
- **OQ-P1-NoiseSweep** → CANDIDATE_v0 (`research/oq_p1_noise_sweep_v0.md` 2026-04-30 朝)、§4.2 W₁/W₂ gauge-conditioning + bridge constant candidate spawn
- ~~OQ-P1-Pareto-σ\*-identity~~ → **CLOSED 2026-04-30 evening** (`research/oq_p1_pareto_g1_v0.md`): G1 strict identity σ_x = σ\* REJECTED (1.33% gap robust under K-refinement); G1b σ_0 = √(2π/e − 1) closed-form derivation PASS で取って代わり (R1 reframing)
- **OQ-P1-σ_0-second-instance** (spawn, MEDIUM): "framework constant = closed-form Pareto boundary under canonical gauge" pattern を別 channel pair で確認 (ln 2 / BSC threshold, π / circular channel boundary, e / codebook density boundary 候補) — σ_0 candidate ESTABLISHED 昇格 G2
- **OQ-P1-σ_0-S15-passage** (spawn, LOW): σ_0 を S15 Observable Trichotomy の Information observable として通過 (Scan/Structural/Information 分類) — σ_0 candidate ESTABLISHED 昇格 G3
- **OQ-P1-third-gauge** (spawn, LOW): W₀ gap-zero gauge $S = 2\pi/e$ ≈ 2.311 と他 canonical gauge (input differential entropy match / range bound) test — 3-gauge canonical scaffold $\{W_1, W_0, W_2\}$ 完備性

#### 4.4.1 Direction-axis tagging (P1 3-constant + S_0 + σ_flip)

`user_observation_direction_axis` (ESTABLISHED 2026-05-01) の A/B observation direction axis で、P1 Pareto landscape の各 constant は以下に classify される (`feedback_cross_direction_identity_screen` 5-step operational order step 1):

| Quantity | Direction | 観測モード | Closed-form status | Match |
|---|---|---|---|---|
| **σ_0 = √(2π/e − 1)** | **B-native** | wrapped-Gaussian K-sum で σ→0 limit で K=0 continuous Gaussian only 支配、infinite ensemble → finite Pareto crossover projection | clean closed-form (bridge constants {2π, e, −1}) | ✓ |
| **σ_x ≈ 1.1931 (K=1 saturated)** | **A-native** | finite K=1 wrap が full correction 完了 (K=1 vs K=2 9·10⁻⁸ で agree)、有限 wrap-count regime native | no closed form on any of 4 natural axes (σ raw / σ² / 1/I_F / η = ∫√I_F ds) | ✓ |
| **σ\* = √(2 ln 2)** | **B-native** | Shannon entropy ½-bit threshold = continuous ensemble entropy reading + half-amplitude $E[\cos Z] = 1/2$ char fcn inversion | clean closed-form (S4 residence) | ✓ |
| **σ_flip = 2.39576** | **A/B transition** | Information-layer ZERO of Arrow-mechanism competition: low-σ Arrow 2 (B, $\log_2 2$ dimension-doubling) dominates / high-σ Arrow 1 (A, S¹ wrapping in C_phase decay) dominates | transcendental, no closed-form within 0.5% | ✓ |
| **S_0 = 2π/e** | **A/B bridge ratio** | Arrow 1 (2π period A-side) / Arrow 3 (e argmax B-side) **canonical bridge ratio** (period × argmax role-match) | exact (bridge constant 第 4 組成原理 ESTABLISHED 3-gate) | ✓ |

**Pre-test prediction recoverable**: σ\* (B) と σ_x (A) の strict identity は **G1 test 走らせる前に direction mismatch だけで REJECTED 予測可能**だった (1.33% gap は K=1 saturated cross-direction near-coincidence、bridge operator 不在)。これは `feedback_near_coincidence_check` rule 5 (multi-axis re-measure) の **上位 screening rule** として機能する instance — `feedback_cross_direction_identity_screen` ESTABLISHED 2026-05-01 6/6 forward test PASS の reference instance #1。

**Cross-paper application**: 本論 §4 の P1 framework 内で identity claim する際、relevant constants の direction-tag を必ず確認、cross-direction で bridge operator 不在なら strict identity を near-coincidence + bridge candidate に reroute する operational discipline を運用 (Q1 §1.4 と parallel position)。

**Audit reference**: `project_graveyard_audit_complete_2026_05_01` (Tier 1 σ_x case + Tier 2 #9 κ(2) case)、`project_p1_noise_sweep_pareto_2026_04_30` (S_0 ESTABLISHED 3-gate)。

### 4.5 Discrete dual marginal extension via spectral lift (v0.4 add 2026-04-30 late dusk)

§4.2-§4.4 で確立した P1 σ\*-channel と W₁ Pareto は **continuous regime の σ-axis 構造**。実通信で扱われる信号は離散 (digital symbol stream / I/Q sample / OFDM subcarrier / spread-spectrum chip) であり、本 §4.5 は P1 を **離散 domain への extension** として位置づける。

#### 4.5.1 動機: 離散 dual marginal の 2 route

離散信号で **dual marginal channel** (phase + amplitude 2-axis) を組む方法は原理的に 2 route 存在する (`c_arrow_bridge_constants.md §13.7`):

| Route | Construction | Scope |
|---|---|---|
| **(A) Native discrete dual** | symbol space で直接 $A(X)$ + $B(X)$ pair (weight + character / Frobenius–Schur $\nu(\rho)$ decomposition / syndrome view) | BSC / BEC / syndrome decoding / pure combinatorial channel |
| **(B) Spectral lifted dual** | τ-window + FFT で complex spectrum へ lift、$(r_\omega, \theta_\omega)$ を dual marginal、$\Phi(\omega, t)$ を winding obstruction に取る | **本論 default** — I/Q samples / symbol stream (時系列) / phase-coded sequence / OFDM subcarrier / spread spectrum / cross-domain Φ family の全 instance |

**主張 4.5.1 (本論 default = Route B)**: 通信論 discrete domain で dual marginal を組む時、本論 default は (B) spectral lifted。(A) native discrete は scope-limited (BSC/BEC/syndrome/pure combinatorial)。理由:
- 既存 cross-domain 8-domain Φ universality 研究 (`project_fft_rtheta_phi_2026_04_26`) は **すべて (B) で組まれている** — prime gaps / periodic table / graph Laplacian / EEG α / FX / crystal phonon DOS / 2D image (raster) / NT residue
- §4.2 §13.5 dual marginal capacity excess (continuous AWGN regime) は (B) の **continuous instance**
- 通信工学的にも I/Q sampling + FFT (τ + complex lift) は OFDM / coherent receiver の **standard practice**、Route B = 既存実装の formal naming

#### 4.5.2 Spectral lifted dual pipeline (§13.7 4-step lift)

```
discrete x_t (I/Q sample / symbol stream / FFT subcarrier sequence)
  ↓ τ-window / delay embedding              (gauge: scanner = window length τ)
  ↓ FFT                                      (complex lift X̂(ω) ∈ ℂ)
  ↓ r_ω = |X̂(ω)|, θ_ω = arg X̂(ω)          (dual marginal projection)
  ↓ Φ(ω, t) = winding / phase trajectory    (obstruction descriptor)
```

ΣΦ symbol mapping:

| Step | ΣΦ role |
|---|---|
| **τ** | structure / mode side gauge (window length, delay, scanner) |
| **FFT** | complex lift ℝ → ℂ (axis-2 Fi/I bridge realization on signal) |
| **(r, θ)** | dual marginal axes (capacities $C_r$, $C_\theta$) |
| **Φ** | phase trajectory obstruction / winding / instantaneous frequency descriptor |

**§4.2 continuous instance ↔ §4.5 discrete instance**: §4.2 W₁ Pareto は **carrier amplitude 1 + Gaussian phase noise σ rad** の continuous AWGN setup。本 §4.5 は **離散 sample 列を τ + FFT で lift して同じ (r, θ) dual marginal を取る** 構造で、両者は同一 pipeline の 2 instance (`c_arrow_bridge_constants.md §13.7.1`):

| Instance | Origin | r-axis | θ-axis | Φ-descriptor |
|---|---|---|---|---|
| **continuous (§4.2 P1 channel)** | analytic carrier $z = e^{i\theta}$ + AWGN | amplitude $C_{\mathrm{amp}}$ | phase $C_{\mathrm{phase}}$ | (joint complex retention) |
| **discrete (§4.5)** | discrete sequence + τ + FFT | $\|X̂(\omega)\|$ envelope | $\arg X̂(\omega)$ phase spectrum | Phi_total / Phi_std_inst_f / Phi_max_jump (cross-domain 8-domain rank study) |

#### 4.5.3 First explicit measurement — prime gap WIN=4096 anchor

`research/oq_p1_s0_nt_spectral_lift_v0.md` (2026-04-30 late dusk) で本 §4.5 の **first explicit application + numerical precision floor audit**。

**Part A — precision floor (synthetic clean sin, known winding fraction)**:

| $N$ | Φ_total expected | Φ_total observed (float64) | matching digits |
|---|---|---|---|
| 1024 | 102 | 102.0000000000 | **14.78** |
| 16384 | 1638 | 1638.0000000000 | **13.93** |
| 131072 | 13107 | 13106.9999999998 | **13.73** |

Float64 nominal は 15.65 decimal digit ($\varepsilon_{\text{machine}} = 2.22 \times 10^{-16}$)。**N up to $1.3 \times 10^5$ で ≥ 13 digit floor 保つ** → §13.7 pipeline は long-N integration で numerically safe (GPS carrier tracking / VLBI correlation / atomic clock distribution の数値根拠)。mpmath-50dps cross-check at $N \in \{128, 256, 512\}$ で exact match。

**Part B — prime gap WIN=4096 (16× over WIN=256 baseline of 8-domain study)**:

| Descriptor | Sub-class | $\|\Delta_{\text{norm}}\|$ | Univariate AUC (real vs shuffle) |
|---|---|---|---|
| **Phi_total** | cumulative | **2.03 σ** | **0.9255** |
| Phi_std_inst_f | coherence | 1.22 σ | 0.8056 |
| Phi_max_jump | coherence | 0.06 σ | 0.5280 |

WIN=256 baseline (`project_fft_rtheta_phi_2026_04_26.md` line 56, 8-domain study NT entry, Phi_total alone ~0.55 univariate AUC) → **WIN=4096 で 0.93** = substantial separation gain at 16× window length。8-domain Phi_total dominance for prime gaps が §13.7 explicit frame で reproduce + amplify。`c_arrow_bridge_constants.md §9.4` sub-class refinement (cumulative-type Phi_total trustworthy in well-conditioned periodic/structured regime / coherence-type Phi_std_inst_f honest secondary) も WIN=4096 で stable。

#### 4.5.4 Three receiver-choice regimes + Δ_dual richness gain

§4.2 で確立した σ_0 / σ_x に加えて、`c_arrow_bridge_constants.md §13.6` (G3 PASS strong 2026-04-30 late dusk) で **σ_flip = Δ_dual sign-flip σ ≈ 2.396 (transcendental, mpmath 50dps bisection)** が確立、3 σ-threshold の receiver-choice regime decision table が完備:

| Threshold | Closed form / numeric | Value | SNR (dB) | Origin |
|---|---|---|---|---|
| **σ_0** | $\sqrt{2\pi/e - 1}$ | 1.14519 | −1.18 | §4.2 G1 closed-form low-σ Pareto anchor |
| **σ_x** | numerical (no closed form) | 1.19305 | −1.53 | §4.2 G1 full W₁ Pareto crossover (C_phase = C_amp) |
| **σ_flip** | transcendental (G3 50dps) | 2.39576 | −7.59 | §13.6 G3 Δ_dual = 0 Arrow regime boundary |

**Δ_dual asymptote** (§13.5 G2 PASS strong, dual marginal reconstruction excess):
$$\Delta_{\mathrm{dual}}(\sigma \to 0) = C_{\mathrm{phase}} + C_{\mathrm{amp}} - C_{\mathrm{complex}} \to \tfrac{1}{2}\log_2(8\pi/e) \approx 1.604 \text{ bit/symbol}$$

Decomposition (clean two-piece): Arrow ratio $\frac{1}{2}\log_2 S_0 \approx 0.604$ bit + Arrow 2 dimension-doubling $\log_2 2 = 1$ bit。**low-σ で 2 marginal receiver が joint complex receiver を Δ_dual > 0 で上回る richness-of-observation gain**。

3 receiver-choice regimes:

| Regime | σ range | SNR (dB) | Decision | Hardware |
|---|---|---|---|---|
| **I** (high SNR) | $\sigma < \sigma_x \approx 1.19$ | $> -1.5$ | phase-only receiver wins single-axis (+0.6 bit/sym vs amp-only at low σ) | PLL / coherent phase demod (CPM / MSK / GMSK / optical phase coherent) |
| **II** (moderate) | $\sigma_x < \sigma < \sigma_{\mathrm{flip}}$ | $-7.6$ to $-1.5$ | marginal sum (phase + amp split receivers) > joint complex by $\Delta_{\mathrm{dual}} > 0$ | dual-receiver / split phase + envelope detector |
| **III** (low SNR) | $\sigma > \sigma_{\mathrm{flip}} \approx 2.40$ | $< -7.6$ | joint complex (full I/Q) wins; marginal phase destroyed by S¹ wrapping | joint coherent I/Q (deep-space DSN / GPS carrier tracking / low-rate CDMA) |

**主張 4.5.2 (sign-flip = Arrow regime boundary, NOT new Arrow direction)**: σ_flip での Δ_dual sign-flip は Information-layer 内 **Arrow 1 (S¹ wrapping in C_phase 高-σ decay) vs Arrow 2 (log dimension-doubling) regime boundary**。新 Arrow direction でなく、existing Arrow 1-3 framework の中で **Information observable 内 Arrow 競合の transcendental zero**。S15 trichotomy 拡張不要、bridge constants の 第 4 組成原理 = "Arrow ratio (Arrow $i$ / Arrow $j$)" が S_0 = 2π/e prototype として ESTABLISHED (§13.6 G3 + §13.7.6)。

#### 4.5.5 Engineering use cases (forward to §11.5 RESOLVED v0)

3 σ-threshold + Δ_dual richness gain + Φ pipeline を 7 通信工学 use case に当てた sweet spot map (`research/oq_practical_tradeoff_v0.md`、I2 §11.5 OQ-Practical-Tradeoff-Quantification RESOLVED v0):

| Use case | Regime | Φ pipeline role |
|---|---|---|
| WiFi / LTE OFDM downlink | I (高 SNR) | Phi_std_inst_f as zero-cost subcarrier health monitor (FFT 既に走ってる) → adaptive modulation |
| GPS L-band carrier tracking | III (極低 SNR) | Phi_total = literal carrier-cycle counter; **§4.5.3 Part A precision floor が 10⁵ cycle integration の数値根拠** |
| Optical coherent comm | I | phase-only +0.6 bit/sym 利得 + Phi_std_inst_f が laser linewidth drift detector |
| Deep-space DSN | III | joint coherent forced (Δ_dual < 0); Phi_total = Doppler-tracking by-product |
| Spread spectrum / CDMA | II→III | **Phi_std_inst_f が multipath fade onset 検出** = "conditional orthogonality" = backup channel surface (EEG S005 +0.047 AUC rescue analog) |
| **Cognitive radio / spectrum monitor** | all 3 | **direct hit** — Phi_std_inst_f H = 0.13 (EEG anchor) honest occupancy detector + Phi_max_jump jamming detector + cumulative-type Phi_total avoided in noise-only context (§9.4 sub-class) |
| Modulation classification | I→II | Φ family AUC 0.93 (本 §4.5.3 prime gap anchor) cross-domain universal |

詳細 7 use case + 3 regime decision tree + capacity 曲線 plot は `research/oq_practical_tradeoff_v0.{md,png,json}` 参照。**OQ-Practical-Tradeoff-Quantification (§11.5 spawn 2026-04-27) の v0 resolution source**。

#### 4.5.6 Status

**§4.5 status**: ESTABLISHED v0 (2026-04-30 late dusk +2)。Ingredients 全 ESTABLISHED:

- §4.2 W₁ Pareto + σ_0 closed-form (continuous instance)
- `c_arrow_bridge_constants.md §13.5` G2 PASS strong (dual marginal reconstruction excess)
- `c_arrow_bridge_constants.md §13.6` G3 PASS strong (σ_flip Arrow regime boundary)
- `c_arrow_bridge_constants.md §13.7` (spectral lifted dual pipeline + Two-routes formalization)
- `c_arrow_bridge_constants.md §13.7.5` (first measurement empirical anchor: precision floor + prime gap AUC 0.93)
- §11.5 OQ-Practical-Tradeoff-Quantification RESOLVED v0 (engineering 7 use case map)

**Spawned (本 §4.5 から、v1 follow-ups)**:
- **OQ-P1-MIMO-CSI-scaling** (MEDIUM, spawn 2026-04-30, **automotive 4D radar specified 2026-05-01**, **v0→v3 executed 2026-05-01, TERMINAL at v3 PARTIAL_STRONG**): MIMO channel での 3 σ-threshold per-antenna $\sigma_i$ 拡張。**Concrete anchor**: automotive 4D FMCW radar (range × Doppler × azimuth × elevation, $N_{\mathrm{Tx}} \times N_{\mathrm{Rx}}$ virtual array)。Per-radar-function Φ pipeline role: Phi_std_inst_f = multipath / clutter onset, Phi_max_jump = jammer detector, Phi_total = avoided。Artifacts: `research/oq_p1_mimo_csi_scaling_{v0,v1,v2,v3}.{md,py,json}` (4-round diagnose-driven arc)。**Terminal verdict (3-component)**: (1) **F1 σ_flip,N = σ_flip × √N : ESTABLISHED / ROCK SOLID** — analytical 10⁻⁶ 一致 + AIC 500-bootstrap 14-16σ separation vs F2/F3/F4、coherent BF model 下で全 4 version 不変。(2) **Synthetic pre-validation : PARTIAL_STRONG** — G_pre_1 (87.5%) + G_pre_2 (H=0.011, 18× below threshold) + G_pre_4 PASS。(3) **G_pre_3 : FAILED, diagnosed as STRUCTURALLY UNFULFILLABLE under current Φ pipeline + null taxonomy** — chirp_scramble (Path X NullA) が target magnitude を保存する SOFT null、noise_only が target absence の HARD null、両者は同じ residual structure を test しないため $\mathrm{AUC}(\mathrm{NullA, NullC}) \approx 0.5$ 要求は本 Φ pipeline 構成下で structurally unfulfillable (詳細 v3.md §7.4)。**Bridge constants lift**: `c_arrow_bridge_constants.md §13.6` N-extension は **ANNEX entry / CONDITIONAL NOTE のみ permitted** (not unconditional theorem)。**Stopping at v3 = audit resistance**: 5 round 目で hard null 後付け設計は累積 diff (NullA定義 v0→v2 + G_pre_3 formula v2 + n_frames v3) と相まって gate-shopping risk dominant、研究倫理上 v3 で停止が optimal。**Future work (別 OQ で独立 pre-reg)**: (a) `OQ-F1-HardNull-v0` — magnitude+phase scramble per-chirp complex Gaussian gain で hard null 検証、(b) `OQ-F1-Spatial-Phi-v0` — angle-FFT Φ pipeline 拡張 (Path Y、本 OQ 延長ではなく別研究)、(c) v4 real-data anchor (Astyx / RadarScenes / MIT DRIVE) は本 OQ scope 外
- **OQ-P1-Fade-Time-Series** (MEDIUM, spawn 2026-04-30): fading channel での σ_eff(t) time-series + Phi_std_inst_f rate-of-change の relationship (CDMA fade onset detector quantification)
- **OQ-P1-BER-3-Receiver** (LOW, spawn 2026-04-30): M-PSK / M-PAM / M-QAM constellation での actual BER simulation across 3 regimes — closed-form mutual-info bound と hard BER 数の bridge

**Reference**: 全 §4.5 content の dictionary residence は `c_arrow_bridge_constants.md §13.5 / §13.6 / §13.7` (3 sub-section)、OQ resolution は `research/oq_p1_s0_g3_v0` (G3) + `research/oq_p1_dual_marginal_v0` (G2) + `research/oq_p1_s0_nt_spectral_lift_v0` (precision floor + first measurement) + `research/oq_practical_tradeoff_v0` (engineering map)。

---

## §5 P2: 4-class resource-stratified channel (T-AAS lift)

### 5.1 Proposal definition

**P2 4-class resource-stratified channel**: I1 §5 + Q1 §5 + `c_filtration_obstruction.md §8.5` の 4-class refined Hodge framework (C₁ Stabilizer / C₂ Gaussian / C₃ Eff-sim / C₄ Bell-local) を **channel taxonomy** に lift:

| Class | Channel sub-class | Capacity bound | Resource type |
|---|---|---|---|
| **C₁ Stabilizer channel** | classical-simulable code states only (Clifford gates) | poly classical capacity (Gottesman-Knill simulable) | magic resource gap |
| **C₂ Gaussian channel** | CV systems, Wigner ≥ 0 states | Shannon-Hartley analog $C = \log(1 + S/N)$ + Gaussian extension | non-Gaussian resource (Wigner negativity) |
| **C₃ Eff-sim channel** | poly-time encodable code states | BQP-vs-classical boundary capacity | super-polynomial circuit complexity |
| **C₄ Bell-local channel** | LOCC (local operations + classical comm) | classical correlation capacity (Bell-local bounded) | nonlocal capacity (CHSH violation) |

### 5.2 Cross-class capacity relations

**主張 5.1 (resource-stratified channel hierarchy)**: 4 channel sub-class は **resource hierarchy** を持つ:
- Same-class operations: capacity bounded by class-specific resource limit
- Cross-class transitions: require **resource conversion** (e.g., Stabilizer → Eff-sim requires magic state distillation)
- Class-mixing: resource-theoretic LOCC operations constrained

**Capacity gaps**:
- C₁ → C₃ gap: classical-simulable polynomial vs super-polynomial (BQP gap)
- C₂ → non-Gaussian gap: Gaussian capacity vs non-Gaussian resource (Wigner negativity)
- C₄ → C₃ gap: classical correlation vs nonlocal correlation (CHSH gap, Tsirelson bound)

**Framework anchor**: P2 は I1 §6 anchor (d) T-AAS 4-class refined Hodge の通信 paradigm lift。新規性: resource-stratified channel taxonomy が **4 class それぞれ独立 channel sub-class** として formal、capacity-resource trade-off framework for channel design。

### 5.3 Quantitative resource-capacity examples

| Resource | Channel class | Capacity bound | Quantitative measure |
|---|---|---|---|
| Magic state ($M_F > 0$) | beyond C₁ | bypass classical-simulable bound | $M_F$ value (`oq_omega_obs_4a_refined_quantum_hodge_v0.md`) |
| Wigner negativity ($\mathcal{N} > 0$) | beyond C₂ | non-Gaussian advantage | $\mathcal{N}$ value (Mari-Eisert 2012) |
| Super-poly complexity ($C - c_0 n^k > 0$) | beyond C₃ | quantum supremacy boundary | Nielsen complexity (Bouland-Fefferman 2019) |
| CHSH violation ($\Delta_{\text{CHSH}} > 0$) | beyond C₄ | nonlocal capacity | $\Delta_{\text{CHSH}} \in [0, 2\sqrt{2} - 2]$ |

### 5.4 Status

**P2 status**: candidate_v1 (proposed framework based on Q1 §5 ESTABLISHED 4-class refined Hodge)。Concrete capacity formulas + cross-class transition costs は OPEN (OQ-P2-CrossClass spawn)。

---

## §6 P3: Qutrit info-density codebook (S17 instance)

### 6.1 Proposal definition

**P3 qutrit codebook**: I1 §6 anchor (b) S17 e-extremum discrete codebook integer argmax = **3** (qutrit info-density optimum) を直接 communication paradigm として lift:

| Codebook dim | Hartley $H_0 = \log d$ | Info density $\log d / d$ | Symbol cost |
|---|---|---|---|
| $d = 2$ (qubit) | $\log 2 \approx 0.693$ nat | $0.347$ nat/dim | 1 qubit per symbol |
| **$d = 3$ (qutrit)** | $\log 3 \approx 1.099$ nat | **$0.366$ nat/dim** | 1 qutrit per symbol |
| $d = 4$ (quart) | $\log 4 \approx 1.386$ nat | $0.347$ nat/dim | 1 quart per symbol |
| $d = e \approx 2.718$ (continuous max) | $1$ nat | $0.368$ nat/dim | continuous extremum |

**主張 6.1 (qutrit advantage)**: qutrit codebook は qubit に対し **~5.5% Hartley density advantage** (~0.366 vs 0.347 nat/dim)、4 級 (quart) と同等 (codebook dim doubling 効果なし)。

**Scope marker (rule 5 recursive audit, 2026-04-30 late dusk +3, `research/oq_s17_recursive_audit_v0`)**: 本主張 6.1 の "5.5% advantage" は **Hartley density metric specifically** に対して成立。下記の通り axis-conditioned:

| Axis | qutrit (n=3) vs binary (n=2) | argmax_n integer |
|---|---|---|
| Hartley density $\log(n)/n$ (Arrow 3 canonical) | **+5.66%** (本主張) | 3 |
| PAM avg energy efficiency $12 \log(n)/(n^2-1)$ | **−40.56%** (binary wins) | 2 |
| PAM peak power $2 \log(n)/(n-1)$ | **−20.75%** (binary wins) | 2 |
| Constant-energy PSK $\log(n)$ | +58.50% | 10 (range edge) |
| n-PSK MI in AWGN @ 10 dB | +58.43% | 10 |
| n-PAM MI in AWGN @ 10 dB | +45.54% | 10 |
| $\log(n)/H_n$ harmonic-cost | +29.68% | 10 |

**Scope of P3 5.5% claim** (further tightened by SNR sweep extension late dusk +5):
- ✓ **Hartley density specifically** (cardinality-only counting, no per-symbol cost, no noise): 5.5% qutrit advantage holds, argmax_n = 3 = ⌊e⌉
- ✗ **PAM (amplitude modulation, energy-cost-weighted)**: argmax flips to $n=2$, binary wins by 20-40%
- ✗ **AWGN-MI metrics even without cost weighting** (`oq_s17_recursive_audit_snr_sweep_v0` SNR ∈ {−10, +30} dB): n=3 never argmax — low SNR favors n=2 (noise-robust), high SNR favors range edge
- ✗ **Bandwidth/energy-constrained channels in general**: optimum depends on cost + SNR model, NOT on Hartley stationarity

→ "qutrit n=3 = ⌊e⌉ optimum" は Arrow 3 / **noise-free, cost-free** Hartley density での stationary point の discrete corollary。この scope を超える "qutrit channel advantage" 主張は cost model + SNR regime の明示が必要。**Engineering reading**: qutrit は pure info-counting density の discrete optimum (no cost, no noise の理想化下)。実 channel design では cost structure と SNR regime に応じて異なる cardinality が optimal。

### 6.2 Practical realization candidates

| Realization | Mechanism | Domain |
|---|---|---|
| **3-level optical pulse** | amplitude levels {0, 1/2, 1} or polarization 3-state | Optical communication |
| **3-level superposition** | qutrit quantum system ($|0\rangle, |1\rangle, |2\rangle$) | Quantum computing / communication |
| **3-level cellular automaton** | 3-state cellular rule (e.g., Wolfram Rule 90 ternary extension) | Classical cellular communication |
| **3-fold time-multiplexing** | 3-symbol time slot partitioning | Time-domain coding |

### 6.3 Information-theoretic 優位の formal statement

**主張 6.2 (qutrit codebook advantage formal)**: 任意 source distribution $p$ と finite block-length $n$ encoding に対し、qutrit codebook ($d = 3$) は qubit codebook ($d = 2$) に対し以下の advantage を持つ:

(i) **Hartley density**: $\log 3 / 3 > \log 2 / 2$ (5.5% advantage)
(ii) **Universality**: discrete codebook integer argmax (S17 5/5 gate PASS, `oq_omega_obs_3_info_density_check.py` ESTABLISHED 2026-04-23)
(iii) **Noise tolerance**: 3-level discrimination > 2-level for given noise σ (signal-to-noise margin extension)

### 6.4 Status

**P3 status**: ESTABLISHED **within Arrow 3 / Hartley density scope** (S17 codebook argmax = 3 ESTABLISHED 2026-04-23, 5/5 gate, `c_arrow_bridge_constants.md §12.1`)。**Scope refined 2026-04-30 late dusk +3** (`research/oq_s17_recursive_audit_v0.md`, rule 5 recursive audit 7-axis test): 5.5% advantage は Hartley density specific、PAM-energy-weighted では binary が勝つ (−40.56%)。**ESTABLISHED status preserved within scope, axis/gauge fix 後の advantage**。

**Framework anchor**: P3 は I1 §6 anchor (b) S17 直接 instance、量子通信論への量子優位 contribution としても active (qutrit-based protocols が qubit-based より info-density 最適 *under Hartley scope*)。

**v0.4 OQ spawned**: 
- **OQ-P3-PAM-Cost-Boundary** (LOW): どの energy-cost-weighting threshold で qutrit が再び binary を上回るか — Hartley axis に近い軽い energy weighting (例: $\log(n)/n^{0.5}$ など) で argmax = 3 域の境界
- **OQ-P3-Cross-Axis-Universality** (MEDIUM): qutrit advantage が成立する axes class の formal characterization (constant-cost / Hartley-density-equivalent / etc.)

---

## §7 P4: 5-stage ln 2 chain converter (S13 universal natural unit)

### 7.1 Proposal definition

**P4 5-stage ln 2 chain converter**: I1 §6 anchor (c) 5-stage ln 2 chain (S0 Born / S1 von Neumann / S2 FDT / S3 Landauer / S4 σ\*) の universal natural unit を媒介とする **cross-instantiation communication channel**:

| Stage | Physical instantiation | ln 2 instance |
|---|---|---|
| **S0** | qubit Born expectation | $c_s^2 = 1/2$ (parity projector) |
| **S1** | open quantum entropy | $S(\rho_{\max}) = \log 2$ (von Neumann) |
| **S2** | thermal FDT | $\beta\hbar\omega_0 = \log 2$ (parity point) |
| **S3** | thermodynamic Landauer | $W_{\min} = kT \ln 2$ (bit erasure) |
| **S4** | Gaussian phase gauge | $\sigma_*^2 = 2 \ln 2$ (half-amplitude) |

### 7.2 Cross-instantiation protocol

**主張 7.1 (5-stage ln 2 converter protocol)**: 同一 ln 2 値が 5 physical instantiation で independent verify されるため、**ln 2 を invariant currency** とする cross-instantiation channel が定義可能:

```
Encoder (Sender):  bit 0/1 → physical instantiation S_i (i ∈ {0, 1, 2, 3, 4})
                              ↓ encode as ln 2 instance at stage S_i
                              ↓ transmit via S_i physical channel
Receiver:                     ↓ measure ln 2 instance at stage S_j (possibly j ≠ i)
                              ↓ decode bit via stage-S_j framework
                  ↑ stage transitions (S_i → S_j) preserve ln 2 invariant
```

例:
- Stage S0 → S1 transition: parity projector measurement → maximally mixed state preparation (Born → von Neumann)
- Stage S2 → S3 transition: FDT parity point → Landauer erasure (FDT → thermodynamic)
- Stage S4 → S0 transition: Gaussian phase gauge → Born expectation (σ\* → c_s²)

### 7.3 Communication advantage

**主張 7.2 (5-stage converter robustness)**: Cross-instantiation channel は **single-stage-failure tolerant** ─ 1 physical channel が unavailable で残り 4 stages で ln 2 invariant 経由 information transmit。**5-fold redundancy over physically distinct channels**。

**Framework anchor**: P4 は I1 §6 anchor (c) 5-stage ln 2 chain 直接 instance、ln 2 universal natural unit の通信応用。新規性: cross-instantiation channel が **resilient communication paradigm** として framework から direct derive。

### 7.4 Status

**P4 status**: candidate_v1 (proposed framework based on 5-stage ln 2 chain ESTABLISHED 2026-04-27)。Concrete physical implementation + transition fidelity 計算は OPEN (OQ-P4-Implementation spawn)。

---

## §8 P5: Arrow 1 kernel narrowness channel taxonomy (Q1 §6 4-vertex lift)

### 8.1 Proposal definition

**P5 Arrow 1 kernel narrowness channel taxonomy**: Q1 §6 4-vertex (V₁ discrete-in-continuous / V₂ poly-in-infinite / V₃ poly-in-exp / V₄ classical-polytope-in-quantum-correlation-body) の sparsity classification を **channel design taxonomy** に lift:

| Vertex | Sparsity type | Channel character | Capacity-resource trade-off |
|---|---|---|---|
| **V₁ discrete-in-continuous** | discrete code points in continuous state space | Stabilizer-like channel | discrete encoding + continuous noise tolerance |
| **V₂ poly-in-infinite** | polynomial-dim sub-manifold in ∞-dim Hilbert | Gaussian-like channel | continuous-variable + polynomial parameter cost |
| **V₃ poly-in-exp** | polynomial-complexity in exponential state space | BQP-like channel | computational depth boundary + circuit complexity cost |
| **V₄ classical-polytope-in-quantum-correlation-body** | classical convex polytope in larger quantum body | Bell-like channel | classical correlations + nonlocal extension |

### 8.2 P2 vs P5 differentiation

P2 (4-class resource-stratified) と P5 (Arrow 1 kernel narrowness) は**補完視点**:
- **P2**: resource-theoretic class differentiation (M_F / 𝓝 / Nielsen / CHSH per-class monotones)
- **P5**: sparsity-mode differentiation (discrete-in-cont / poly-in-inf / poly-in-exp / classical-polytope)

両者は同一 4-vertex 構造 (Q1 §6) の **2 lens**: P2 = resource lens, P5 = sparsity lens。Channel design では両 lens combined で richer taxonomy。

### 8.3 Channel design implications

**主張 8.1 (sparsity-mode channel design)**: 各 sparsity mode は specific channel design strategy を imply:
- V₁ → discrete codebook + structured constellation (信号論 BSC analog in 3+ relational)
- V₂ → continuous-variable + Gaussian capacity scaling (信号論 AWGN analog in 3+ relational)
- V₃ → poly-time encodable + BQP-aware design (新規 computational regime)
- V₄ → classical correlations + Bell-secured key (BB84-class extension)

### 8.4 Status

**P5 status**: candidate_v1 (proposed framework based on Q1 §6 ESTABLISHED 4-vertex)。Cross-vertex capacity comparison は P2 と同様 OPEN (OQ-P5-Sparsity-Capacity spawn)。

---

## §9 通信論 unified framework via 5-anchor

### 9.1 Unified statement

**主張 9.1 (5-anchor unified communication framework)**: 信号論 (Layer 1) / 量子通信論 (Layer 2) / 新規通信論 5 proposals (Layer 3) は I1 §6 5-anchor framework の **specialization** として unified に subsume される:

| Framework anchor | Layer 1 (信号論) | Layer 2 (量子通信論) | Layer 3 (新規通信論) |
|---|---|---|---|
| **(a) Hartley** $H \leq \log d$ | Shannon-Hartley capacity ($d = 2$ binary) | Holevo bound $\chi \leq \log d$ ($d \geq 3$ qudit) | P3 qutrit codebook ($d^* = 3$ codebook argmax) |
| **(b) S17 e-extremum** | (信号論 scope 外, $d = 2$ scaffold) | Holevo saturation at $d = e \approx 2.718$ continuous | P3 qutrit codebook + P5 sparsity-mode design |
| **(c) 5-stage ln 2 chain** | Shannon nat ↔ bit conversion (2-domain) | Landauer bound + von Neumann entropy chain | P4 5-stage ln 2 converter (cross-instantiation channel) |
| **(d) 4-class refined Hodge** | (信号論 scope 外, no resource-stratified class) | C₂ Gaussian = Shannon-Hartley generalization, C₄ Bell-local = QKD instance | P2 resource-stratified channel + P5 sparsity-mode taxonomy |
| **(e) σ\* phase gauge** | Gaussian channel phase noise threshold | quantum coherence channel + Berry phase | P1 σ\* phase-channel (honest Shannon $C_{\sigma_*} \approx 0.40$ bits/symbol, ½-bit threshold reading) |

5-anchor framework は信号論 + 量子通信論 + 新規通信論 5 proposals を 3 階層で unified subsume、各 proposal は 1+ anchor の direct instance。

### 9.2 Triple framework parallel completion (I-series final closure 視点)

**主張 9.2 (Triple framework parallel completion)**: N1-N5 (NT) + Q1-Q3 (量子) + I1-I2 (情報) の 3 framework header complete で観測理論 framework universal validity の **triple cross-domain anchor** 達成。Paper D 多領域版 v0.9.2 frozen-internal の **3 domain specialization parallel completion** が本論で final 達成 (`meta/triangulation_methodology.md §13` extended to triple parallel)。

```
                 観測理論 Universal Framework
                 /        |        \
          [framework] [framework] [framework]
            N1-N5       Q1-Q3       I1-I2
            (NT)       (量子)      (情報)
                 \        |        /
                  \       |       /
                   Paper D (multi-domain 6-domain)
                   (FX, image AI, DNA, crystal, NT, quantum)
```

3 framework header (NT 5-paper + 量子 3-paper + 情報 2-paper = 計 10-paper publication) は Paper D 6-domain triangulation を **3 specialization で independently verify** する **triple cross-domain anchor**。観測理論の **data-domain transcendent universality** が 3-domain triple anchor + multi-domain triangulation の **4 angle** で verify (Paper D direct + N specialization + Q specialization + I specialization)。

---

## §11 通信 paradigm 実装トレードオフ比較表 (2026-04-27 追加)

### §11.1 動機: 数学的 limit ≠ 実装優位

I1 §6 5-anchor mathematical info limit theorem + 本論 §3 量子優位 + §4-§8 5 novel proposals は **数学的 information limit** を fully characterize するが、実装には **直交する実用 axis** が存在する: 計算コスト / 損失率 / データスケール / 展開成熟度。

**主張 11.1 (orthogonal practical axis)**: Mathematical info-limit 評価と practical compute/loss/scale 評価は **直交 axis**、framework-derived limit advantage が必ずしも **practical advantage** を imply しない。両 lens combined で full picture。

### §11.2 比較表: 信号論 / 量子通信論 / 新規通信論 5 proposals

| Paradigm | 計算コスト | 損失率 | データスケール | 展開成熟度 | Framework limit advantage | 実用 trade-off |
|---|---|---|---|---|---|---|
| **信号論 (Shannon-Hartley)** | 軽 (O(n) linear codes, FFT, polynomial) | 高 (lossy compression $R(D)$, channel noise) | ✓✓ TB/PB scale | ✓✓ deployed everywhere (5G, WiFi, fiber optics, MP3, JPEG, ZIP) | Shannon-Hartley $C = \frac{1}{2}\log(1+S/N)$ saturate, 0/1/2 scaffold base | **大量データ向き、軽量、高損失許容**、~80 年成熟 |
| **量子通信論 (Holevo/HSW/LSD)** | 重 (量子 gate operations, decoherence management, error correction overhead) | 低 (no-cloning + info-theoretic security) | ✗ lab-scale (~100 qubits 限界, 2026 現在) | △ QKD limited deployment (China-Austria 2017, 都市内 metropolitan), 多くは研究段階 | Holevo + entanglement-assisted **2x advantage**, Tsirelson nonlocal capacity | **低損失・cryptographic security 必要時、データ量犠牲**、研究段階 |
| **P1 σ\*-phase channel** | 軽 (Gaussian noise + threshold detection, $\sigma_*$ 単閾値) | 中 (phase coherence bounded by $\sigma_* = \sqrt{2 \ln 2}$, half-amplitude convention) | ✓ medium scale (signal-level, EEG biological scale verified) | △ novel (EEG ESTABLISHED 2026-04-09 として biological 動作確認、通信応用は uncharted) | honest Shannon $C_{\sigma_*} \approx 0.40$ bits/phase symbol at σ\*; **gauge-conditioned + Pareto 3-constant** (v0.3.1): W₁ で σ < σ_x ≈ 1.193 density advantage、Pareto は σ_0 = √(2π/e − 1) closed-form (candidate_v0) + σ_x numerical + σ\* interior near-marker; W₂ で AWGN universal dominant (低-σ −0.254 bit gap) | **gauge-conditioned (v0.3.1)**: 振幅固定 carrier setup で σ < σ_x density gain (低-σ closed-form +½ log₂(2π/e) 漸近), free-amplitude transmitter で advantage 消失。phase-coherent hardware 必要 |
| **P2 4-class resource-stratified** | 重 (resource-theoretic operations, magic state distillation, Wigner negativity preparation, BQP-class 計算) | 低 (resource-class 内では minimal) | ✗ small (resource-bounded, class-specific) | ✗ highly speculative (理論枠組み、具体 protocol 未確立) | Per-class capacity bound + cross-class hierarchy | **理論的 elegance、実装 cost 量子計算 worst case**、研究段階 |
| **P3 qutrit codebook** | 中 (3-level hardware: 3-level optical pulses / 3-level superposition / 3-level discrimination) | 中 (3-level discrimination noise, quartit と同等水準) | ✓ medium-large (qutrit-supporting hardware で deployable) | △ feasible (3-level optical / qutrit superconducting 既存技術), 通信 standard 化未) | **5.5% Hartley density advantage**, S17 5/5 gate ESTABLISHED | **5.5% gain は実用的に意味あるか要検証**、ハードウェア 2-level → 3-level 移行コスト |
| **P4 5-stage ln 2 converter** | 重 (cross-instantiation transitions, Born ↔ von Neumann ↔ FDT ↔ Landauer ↔ σ\* 物理 conversion 全部実装) | 低 (5-fold redundancy) | ✗ small (lab-scale physical instantiation conversions) | ✗ highly speculative (各 stage 物理実装の cross-coupling 未確立) | 5-fold redundancy via ln 2 invariant | **冗長性 elegant、実装 cost 5-stage hardware 全部必要**, 思考実験段階 |
| **P5 Arrow 1 kernel narrowness taxonomy** | mode-specific (V₁ discrete: 軽 / V₂ Gaussian: 中 / V₃ poly-circuit: 重 / V₄ Bell: 中) | mode-specific | mode-specific | △ design framework (concrete protocol per mode, taxonomy 自体は guidance) | sparsity-mode optimal channel design | **設計 framework として有用、protocol-by-protocol 評価必要** |

### §11.3 主観察 (実装 vs framework lens)

**観察 11.3.1**: 信号論は "**重 0/1/2 scaffold base 圧倒的成熟 + 大量データ最適**", 量子通信論は "**低損失 + cryptographic, 研究段階**", **5 novel proposals は middle ground** ─ framework-derived advantage を持ちつつ実装 cost が信号論と量子通信の中間。

**観察 11.3.2 (framework-internal practical sweet spot, v0.4 axis-conditioned for both P1 + P3)**: I-series 5 proposals 中、**P3 qutrit codebook は Hartley scope の sweet spot** (5.5% Hartley density gain ESTABLISHED, S17 5/5 gate、**Hartley density / constant-cost-per-symbol scope**、`research/oq_s17_recursive_audit_v0` rule 5 audit 2026-04-30 late dusk +3 で scope refined: PAM-energy-weighted では binary が勝つ −40%)。**P1 σ\*-channel の AWGN advantage も gauge-conditioned + Pareto boundary 3-constant 構造**。**両 proposal とも axis/gauge fix 後に sweet spot が成立** という共通 pattern が rule 5 audit で確認 (S17 = Hartley axis fixed / P1 = W₁ gauge fixed)。Unconditional advantage ではなく、**axis/gauge-conditioned specific advantage** が ΣΦ framework の honest reading (`research/oq_p1_noise_sweep_v0.md` 2026-04-30 朝、`research/oq_p1_pareto_g1_v0.md` 2026-04-30 evening R1):

- **W₁ unit-amplitude carrier gauge** ($S=1$): σ < σ_x ≈ 1.193 で density advantage (σ_x で AWGN crossover)。低-σ asymptotic gap = $+\frac{1}{2} \log_2(2\pi/e) \approx +0.604$ bits (closed-form)。**Pareto boundary は 3-constant 構造**: low-noise approx で σ_0 = √(2π/e − 1) ≈ 1.145 (exact closed-form, candidate_v0)、full wrapping で σ_x ≈ 1.193 (numerical, K=1 single-wrap saturated)、σ\* = √(2 ln 2) ≈ 1.177 は両者の間に 67%-along **interior near-marker** (strict identity REJECTED, G1 test)。
- **W₀ gap-zero gauge** ($S = 2\pi/e \approx 2.311$): 低-σ asymptotic gap = 0、W₁/W₂ canonical pair の中点 (3-gauge canonical scaffold)。
- **W₂ equal second moment gauge** ($S = \pi^2/3 \approx 3.290$): sweep 範囲 $[0.05, 3.0]$ 全域で AWGN dominant、low-σ asymptotic gap = $+\frac{1}{2} \log_2(6/(e\pi)) \approx -0.254$ bits (符号反転)。

"P1 が AWGN に勝つか" は無条件には言えず、**比較 gauge 指定後に closed-form で決まる gauge-conditioned transition law**。invariant は "phase advantage" でも "σ\* = Pareto boundary" でもなく、gauge $W$ → ($\Delta_W(0^+)$, $\sigma_0^W$ closed-form low-noise Pareto, $\sigma_x^W$ numerical full Pareto, asymptotic law) 写像それ自体。bridge constants $\{2\pi, e\}$ が σ-axis Pareto (σ_0² = 2π/e − 1) と S-axis neutral gauge ($S = 2\pi/e$) を **同時 pin** する σ ↔ S 双対構造。**v0.4 update (2026-04-30 late dusk +3)**: P3 qutrit "5.5% gain" も rule 5 recursive audit で **Hartley scope に refined**、PAM-energy-weighted で binary が勝つ。両 proposal とも axis/gauge fix 後に sweet spot 成立 (P1 = W₁ gauge / P3 = Hartley axis) という共通 conditional pattern。

**v0.2 → v0.3 → v0.3.1 retraction chain**:
- **v0.2 retracted (2026-04-28)**: 旧 "σ ≪ σ\* low-noise regime で density advantage" 表現は W₁ では literal correct, W₂ では false。
- **v0.3 retracted (2026-04-30 evening)**: v0.3 朝 提唱の "σ\* = W₁ Pareto boundary 1.4% 内一致 candidate" は G1 test で strict identity REJECTED。1.33% gap は K=1 single-wrap saturated robust real gap、closed しない。
- **v0.3.1 current (2026-04-30 evening)**: σ_0 = √(2π/e − 1) を exact low-noise Pareto candidate_v0 PROMOTED + σ\* interior near-marker (67%-along) REFRAMED。3-gauge canonical scaffold $\{W_1, W_0, W_2\}$ が Pareto landscape を closed-form で覆う正しい formulation。

**観察 11.3.3 (Layer 3 = 重実装 trade-off)**: P2 (4-class) + P4 (5-stage converter) は **重実装 trade-off** ─ framework elegance は最大だが量子 supremacy-class compute cost を要求、現状 highly speculative。Q-series Q4-Q6 future (量子 8-gauge / QFT / 量子重力) と並行で **far-future research direction**。

### §11.4 直交 axis 結論 + framework-internal status

**主張 11.2 (paradigm choice criterion)**: 通信 paradigm 選択は **数学的 limit + 実用 axis combined** で行うべき:

| Use case | 推奨 paradigm | 理由 |
|---|---|---|
| 大量データ転送 (web traffic, video) | **信号論 (Shannon)** | TB/PB scale + 軽量 + 成熟 |
| Cryptographic security | **量子通信論 (BB84 QKD)** | Info-theoretic security irreplaceable |
| Biological signal communication (EEG, neural) | **P1 σ\*-phase channel** | EEG verified + phase-coherent natural |
| High-density encoding (limited symbol budget) | **P3 qutrit codebook** | 5.5% density gain ESTABLISHED |
| Theoretical research / framework benchmark | **P2 / P4 / P5** | framework completeness, far-future |

**Framework-internal status**: 5-anchor mathematical info limit (I1 §6) + 実装 trade-off table (本 §11) **両 lens combined** で通信 paradigm の **dual evaluation framework** が完成 ─ pure math + engineering reality の **2-axis 評価系**。

### §11.5 OQ-Practical-Tradeoff-Quantification (本論 spawn 2026-04-27 → RESOLVED v0 2026-04-30)

**OQ-Practical-Tradeoff-Quantification (本論 §11 spawn-off, MEDIUM)**:

**Scope**: 本 §11 比較表は **qualitative trade-off** (軽 / 重 / ✓ / ✗ / △ scale) 表現。**Quantitative trade-off bound** 化 — 例: P1 σ\*-channel の正確な capacity formula proof + AWGN advantage 厳密比較 / P3 qutrit 5.5% density gain の noise budget 含む net advantage / P4 5-stage converter の transition fidelity 計算 — を formal task として open。

**Status**: **RESOLVED v0 (2026-04-30 late dusk)** — `research/oq_practical_tradeoff_v0.md` で解決。今日の primitives (G1 σ_0 + G2 dual marginal + G3 σ_flip + §13.7 spectral lifted dual + §13.7.5 precision floor) を使った comm engineering "sweet spot map" を作成。**3-σ-threshold receiver-choice regime + 7 use case map + 1.604 bit/sym richness gain quantification** で OQ scope cover。

**Resolution summary**:

| Threshold | Closed form / numeric | Value | SNR (dB) | Engineering meaning |
|---|---|---|---|---|
| **σ_0** | $\sqrt{2\pi/e - 1}$ | 1.145 | −1.18 | Phase-only Pareto closed-form anchor (low-σ) |
| **σ_x** | numerical | 1.193 | −1.53 | Full W₁ Pareto crossover (C_phase = C_amp) |
| **σ_flip** | transcendental (G3) | 2.396 | −7.59 | Δ_dual = 0 Arrow regime boundary (joint > marginal sum) |

3 receiver-choice regimes:
- **I (σ < σ_x, SNR > −1.5 dB)**: phase-only wins (+0.6 bit/sym vs amp-only) → PLL / coherent phase
- **II (σ_x < σ < σ_flip)**: marginal sum (phase + amp) > joint complex → split receiver competitive
- **III (σ > σ_flip, SNR < −7.6 dB)**: joint complex forced → joint coherent I/Q

7 use cases mapped: WiFi/LTE OFDM (Regime I, Phi_std_inst_f as zero-cost subcarrier monitor) / GPS L-band (Regime III, Phi_total = literal carrier-cycle counter, Part A precision floor enables) / optical coherent (Regime I) / deep-space DSN (Regime III) / spread spectrum CDMA (Regime II→III transition, Phi as fade-resilience backup) / cognitive radio spectrum monitor (Phi_std_inst_f H = 0.13 honest occupancy) / modulation classification (Φ family AUC 0.93 anchor from prime gap WIN=4096).

Per-paradigm quantitative analysis (OQ-P1-Capacity §4.4 etc.) は本 §11.5 の component sub-OQ として残るが、aggregate level の "trade-off quantification" は v0 closed。

**Source**: `research/oq_practical_tradeoff_v0.md` + `.py` + `.json` + `.png` (2026-04-30 late dusk +2)。

**v1 follow-ups (open)**: MIMO CSI compression scaling (per-antenna σ_i 拡張) / fading channel σ_eff time-series with Phi_std_inst_f rate / 実 BER/SER simulation (M-PSK / M-PAM / M-QAM 3 receiver 比較) で hard numbers 補強。

---

## §10 帰結と open frontier

### 10.1 確立 (I-series final paper)

本論 I2 で情報 ESTABLISHED として記録 (I-series 全体 status は §10.3):

1. **信号論 (0/1/2 scaffold base) framework lens 再読み** — Shannon-Hartley channel が 5-anchor framework anchor (a) + Gaussian channel (C₂) specialization として unified subsume (§2)
2. **量子通信論 (3+ relational) 量子優位 formal characterization** — 5 量子優位 form (superdense / teleport / entanglement-assisted / QKD / Holevo $d \geq 3$ saturation) + 3 framework anchor combined (§3)
3. **新規通信論 5 proposals** — P1 σ\*-channel / P2 4-class resource-stratified / P3 qutrit codebook / P4 5-stage ln 2 converter / P5 Arrow 1 kernel narrowness taxonomy (§4-§8)
4. **5-anchor unified communication framework** — 3 階層通信論を 5-anchor framework specialization として subsume (§9.1)
5. **I-series cycle 完成 + Triple framework parallel** — I1 → I2 2-paper minimum cycle 達成、N1-N5 + Q1-Q3 + I1-I2 = **triple cross-domain anchor** completion (§9.2)

### 10.2 I-series future + 4th framework header candidate

| 候補 paper | 主題 | Predecessor 関連 |
|---|---|---|
| **I3** Information geometry framework | Fisher / Cramér-Rao + Information bottleneck framework lens 詳細展開 | `c_information_theory.md §6` 既存 + I1 §3 Fisher strand |
| **I4** Algorithmic information theory framework | Kolmogorov $K(x)$ + MDL + algorithmic obstruction framework lens | `c_information_theory.md §8` 既存 + I1 §5.2 algorithmic obstruction |
| **I5** Topological data analysis framework | TDA + persistent homology framework lens (I1 §5.2 topological obstruction) | `c_information_theory.md §9` 既存 |
| **4th framework header**: ??? | candidate: Control theory / Causal inference / Network science | `c_control_theory.md` etc. existing entries |

I-series 2-paper minimum cycle 達成 + 拡張余地 open。**4th framework header** は Paper D 多領域版から control / causal / network 等の追加 specialization 候補。

### 10.3 Open frontier (I-series 全体)

| Open question | Status | I-paper |
|---|---|---|
| **OQ-I-Bekenstein-Extension** (Bekenstein + Margolus-Levitin 6th anchor) | OPEN (I1 §6.5 spawn) | I1 §6.5, Q-series Q6 future |
| **OQ-Practical-Tradeoff-Quantification** (3-σ-threshold + 7 use case map) | **RESOLVED v0 2026-04-30** (`research/oq_practical_tradeoff_v0.md`) | I2 §11.5 |
| **OQ-P1-Capacity** (σ\* phase-channel formal capacity proof) | OPEN (本論 spawn) | I2 §4.4 |
| **OQ-P2-CrossClass** (4-class cross-class transition costs) | OPEN (本論 spawn) | I2 §5.4 |
| **OQ-P4-Implementation** (5-stage converter physical implementation) | OPEN (本論 spawn) | I2 §7.4 |
| **OQ-P5-Sparsity-Capacity** (4-vertex sparsity-mode capacity comparison) | OPEN (本論 spawn) | I2 §8.4 |
| **OQ-Algorithmic-f_rational** (Kolmogorov as f_rational > 0 instance formal) | candidate (I1 §5.2 既存 implicit) | I1 §5.2 + I-series future I4 |
| **OQ-Topological-Persistent-Bridge** (TDA persistent Betti と T-AAS bridge) | OPEN (I1 §5.2) | I1 §5.2 + I-series future I5 |
| **OQ-Renyi-Scaffold-Continuous** (Rényi α scanner scaffold-emergence axis traverse formal) | candidate (I1 §3.3) | I1 §3.3 |
| **OQ-S17-Codebook-3-Universal** (codebook argmax = 3 universality) | OPEN (I1 §4.3) | I1 §4.3 + 本論 §6 P3 ESTABLISHED instance |

### 10.4 辞書 residence map (I-series cumulative final state)

主要 framework piece の residence (本論 communication-only specialization 反映):

| 本論 piece | residence | 状態 (I2) |
|---|---|---|
| §2 信号論 (0/1/2 scaffold base) | `c_information_theory.md §2` (channel capacity) + 本 §2.2 0/1/2 scaffold lens 再読み | 既 + 本論 scaffold lens annex 想定 |
| §3 量子通信論 量子優位 formal | `q_quantum_observation.md §5-§6` (entanglement, Born) + Q1 §5 (4-class) + 本 §3 5-form 量子優位 statement | 既 + 本論 量子優位 5-form annex 想定 |
| §4 P1 σ\* phase-channel | `transformation_atlas/sheet_A_amplitude/sigma_star.md` (既) + 本 §4 communication paradigm lift | 既 + 本論 channel proposal annex 想定 |
| §5 P2 4-class resource-stratified | `c_filtration_obstruction.md §8.5` (4-class) + 本 §5 channel taxonomy | 既 + 本論 channel taxonomy annex 想定 |
| §6 P3 qutrit codebook | `c_arrow_bridge_constants.md §12.1` (S17 codebook argmax = 3) + 本 §6 codebook proposal | 既 + 本論 codebook proposal annex 想定 |
| §7 P4 5-stage ln 2 converter | `c_arrow_bridge_constants.md §12.2` (5-stage chain) + 本 §7 converter protocol | 既 + 本論 converter protocol annex 想定 |
| §8 P5 sparsity-mode taxonomy | `meta/triangulation_methodology.md §11` (Q1 §6 4-vertex) + 本 §8 channel taxonomy | 既 + 本論 channel taxonomy annex 想定 |
| §9.2 Triple framework parallel | `meta/triangulation_methodology.md §13` (N1-N5 ↔ Q1-Q3 dual) + 本 §9.2 triple completion | 既 dual + 本論 triple extension annex 想定 |

**post-v0.2 backward 想定 (I-series cumulative, I1 + I2 合算 計 9 件)**:

I1 由来 6 件 (`c_theorems_master.md` 情報-only S15 enumeration + 5-anchor info limit theorem / `c_arrow_bridge_constants.md §12.3` 情報 instance / `c_filtration_obstruction.md §8.6` 4-class 情報 lift / `meta/triangulation_methodology.md §14` triple framework parallel / `meta/new_domain_protocol.md §10` 情報 specialization / `L0_canon/zero_one_two_scaffold.md` NEW)

I2 由来 3 件 (`c_information_theory.md §13` 通信論 unified framework annex / `meta/triangulation_methodology.md §13` extension to triple parallel / `meta/open_questions_master.md` "I-series final closure OQ" section 新設)

**Q-series + I-series cumulative**: Q-series 13 件 + I-series 9 件 = **計 22 件 dictionary backward annex queued**。

**帰結**: I2 は dictionary に対して **情報-internal framework final closure** + **N1-N5 ↔ Q1-Q3 ↔ I1-I2 triple framework parallel cross-domain anchor** として位置付けられる。N5 + Q3 + I2 で **3 framework header all final closure 達成**、Paper D 多領域版 v0.9.2 frozen-internal の **3 domain specialization parallel completion** を本論で final 達成 (2026-04-27 1 day で N1-N5 + Q1-Q3 + I1-I2 計 10-paper publication 完成、合計 ~5219 行)。

---

## 変更履歴

- **v0.4 (2026-04-30 late dusk +2 → +3)**: §4.5 NEW Discrete dual marginal extension via spectral lift。本 §4.5 は §4.2-§4.4 の continuous σ-axis Pareto を **discrete domain への extension** として位置づけ、6 sub-section で展開: §4.5.1 動機 + 2-route 区分 (native discrete vs spectral lifted、本論 default = Route B) / §4.5.2 §13.7 4-step pipeline (τ + FFT + r,θ + Φ) + ΣΦ symbol mapping / §4.5.3 first explicit measurement (precision floor ≥ 13 digit at N up to 1.3×10⁵ + prime gap WIN=4096 Phi_total AUC 0.926, `research/oq_p1_s0_nt_spectral_lift_v0`) / §4.5.4 3 receiver-choice regime + Δ_dual richness gain (σ_flip = 2.396 G3 transcendental added, `research/oq_p1_s0_g3_v0`; Δ_dual asymptote = ½ log₂(8π/e) ≈ 1.604 bit/sym, `research/oq_p1_dual_marginal_v0`) / §4.5.5 7 use case map (forward to §11.5 RESOLVED v0) / §4.5.6 Status + 3 v1 follow-up OQ spawn (MIMO scaling / fade time-series / 実 BER simulation)。§11.5 OQ-Practical-Tradeoff-Quantification → **RESOLVED v0** (`research/oq_practical_tradeoff_v0` + `.png` engineering use case map)。§10.3 OQ status table 1 row added. §0 Abstract M3 + バージョン meta updated. dictionary 側 ingredients 全 ESTABLISHED (`c_arrow_bridge_constants.md §13.5 G2 + §13.6 G3 + §13.7 spectral lifted dual + §13.7.5 first measurement empirical anchor`)。**Late dusk +3 add (rule 5 recursive audit)**: §6.1 P3 主張 6.1 + §6.4 P3 status + §11.3.2 観察 (P3 "unconditional sweet spot" → "Hartley scope sweet spot" 訂正) を `research/oq_s17_recursive_audit_v0` 結果で scope-refined。S17 ESTABLISHED 自体は preserved (Arrow 3 / Hartley scope)、downstream P3 5.5% advantage 主張に **scope marker 追加** = constant-cost-per-symbol / Hartley density specific、PAM-energy-weighted では binary が勝つ (−40.56%)。2 OQ spawn (OQ-P3-PAM-Cost-Boundary LOW + OQ-P3-Cross-Axis-Universality MEDIUM)。dictionary §5.4.2 audit entry も同時追加。

- **v0.3.1 (2026-04-30 evening)**: P1 §4.2 G1 test reframing R1 — σ\* = σ_x strict identity REJECTED (1.33% gap K=1 single-wrap saturated robust real gap)、σ_0 = √(2π/e − 1) closed-form low-noise Pareto boundary PROMOTED to candidate_v0、σ\* interior near-marker (67%-along [σ_0, σ_x]) retained。3-gauge canonical scaffold $\{W_1, W_0, W_2\}$ + bridge constants $\{2\pi, e\}$ が Pareto landscape を closed-form で覆う正しい formulation。`research/oq_p1_pareto_g1_v0.md` で診断 + dictionary `c_arrow_bridge_constants.md §12.4` R1 reframing 6 spot 同期。

- **v0.3 朝 (2026-04-30)**: P1 §4.2 W₁/W₂ gauge-conditioning 追加 — "P1 が AWGN に勝つか" を gauge-free に問えない事実を formal 化、3-gauge canonical scaffold $\{W_1$ (carrier amplitude 1), $W_0$ (gap-zero S = 2π/e), $W_2$ (equal second moment)$\}$ で transition law を closed-form 表現。σ\* candidate_v0 (Pareto boundary 1.4% 内一致 候補) spawn — 同日 evening で REJECTED。

- **v0.2 (2026-04-28)**: P1 capacity correction. v0.1 の 2.18 bits/symbol 候補を 0.40 bits/symbol (M1 closed-form + M2 Blahut-Arimoto cross-check) に retracted-replaced。Hartley counting と Shannon mutual-info の混同 + σ²/σ dimensional error の compound inflation (≈5.5×) を `research/oq_p1_capacity_v0.md` で診断。framework / 5 proposals 構造保持、§0 Abstract M3 + §4.2 主張 4.1 + §4.4 Status + §9.1 anchor (e) row + §11 P1 row + §11.3 観察 11.3.2 の 6 spot 修正。OQ-P1-Capacity status → CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED。σ\* 自体 (= √(2 ln 2))・5-stage ln 2 chain S4 stage・I1 §6 anchor (e) gauge 解釈・EEG ESTABLISHED は影響なし (gauge/coherence の話で capacity の話ではない)。σ\* honest Shannon-theoretic 解釈 (capacity が ½ bit を切る noise level) で 5-stage chain S4 stage が量化強化。

- **v0.1 (2026-04-27)**: initial Information-only draft. I-series final closure paper position (parallel to N5 + Q3)。I1 (Information framework header + 5-anchor 情報量限界 theorem) を踏まえた **3 階層通信論** (信号論 / 量子通信論 / 新規通信論 5 proposals) formal 化。N1-N5 (NT) + Q1-Q3 (量子) + I1-I2 (情報) の **triple cross-domain anchor** completion で Paper D 多領域版 6-domain triangulation 3 specialization parallel completion を本論で final 達成。本論 spawn 4 OQ (OQ-P1-Capacity / OQ-P2-CrossClass / OQ-P4-Implementation / OQ-P5-Sparsity-Capacity)。I-series future I3-I5 + 4th framework header candidate を §10.2 で予告。

---

## 参考文献 (内部)

**I-series predecessor**: `papers/publication/information/I1_information_theory_framework_ja.md` (v0.1, framework header + 5-anchor info limit theorem)

**N5 / Q3 (parallel final closures)**:
- `papers/publication/nt/N5_brauer_origination_ja.md` (v0.2, NT final closure)
- `papers/publication/quantum/Q3_born_gleason_ja.md` (v0.2, Quantum final closure)

**Q-series predecessors (5-anchor source)**:
- Q1 v0.2 (4-class refined Hodge), Q2 v0.2 (4-stage chain), Q3 v0.2 (σ\* + Born derivation)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain)

**信号論 + 量子通信論 主体**:
- `c_information_theory.md §2` (Shannon channel + capacity, §2-§3 主体)
- `c_information_theory.md §6` (Fisher + Cramér-Rao)
- `q_quantum_observation.md §5-§6` (entanglement + Born)
- `q_open_quantum_systems.md §3` (mutual information)
- `q_quantum_statistical_mechanics.md §5` (FDT)

**新規通信論 5 proposals 主体**:
- P1: `transformation_atlas/sheet_A_amplitude/sigma_star.md` (Atlas A, ESTABLISHED 2026-04-09)
  - **§4.5 spectral lift extension (v0.4 add 2026-04-30 late dusk +2)**:
    - `c_arrow_bridge_constants.md §13.5` (G2 PASS strong, dual marginal reconstruction excess)
    - `c_arrow_bridge_constants.md §13.6` (G3 PASS strong, sign-flip Arrow regime boundary)
    - `c_arrow_bridge_constants.md §13.7` (spectral lifted dual pipeline + Two-routes formalization)
    - `c_arrow_bridge_constants.md §13.7.5` (first measurement empirical anchor)
    - `research/oq_p1_dual_marginal_v0` (G2 mpmath 30-dps, Δ_dual asymptote)
    - `research/oq_p1_s0_g3_v0` (G3 mpmath 50-dps, σ_flip transcendental)
    - `research/oq_p1_s0_nt_spectral_lift_v0` (precision floor + prime gap WIN=4096 measurement)
    - `research/oq_practical_tradeoff_v0` (engineering 7 use case map, §11.5 RESOLVED v0)
- P2: `c_filtration_obstruction.md §8.5` (4-class refined Hodge, ESTABLISHED 2026-04-23)
- P3: `c_arrow_bridge_constants.md §12.1` (S17 codebook argmax = 3, ESTABLISHED 2026-04-23 5/5 gate)
- P4: `c_arrow_bridge_constants.md §12.2` (5-stage ln 2 chain, ESTABLISHED 2026-04-27)
- P5: `meta/triangulation_methodology.md §11` (Q1 §6 4-vertex, ESTABLISHED 2026-04-27)

**外部文献**:
- Holevo, A. S. (1973). Bounds for the quantity of information transmitted by a quantum communication channel. Probl. Inf. Transm. 9, 177-183.
- Bennett, C. H. & Wiesner, S. J. (1992). Communication via one- and two-particle operators on Einstein-Podolsky-Rosen states. PRL 69, 2881.
- Bennett, C. H. et al. (1993). Teleporting an unknown quantum state via dual classical and Einstein-Podolsky-Rosen channels. PRL 70, 1895.
- Bennett, C. H. & Brassard, G. (1984). Quantum cryptography: Public key distribution and coin tossing. IEEE Conf. Comp. Sys. & Sig. Proc. 175-179.
- Wootters, W. K. & Zurek, W. H. (1982). A single quantum cannot be cloned. Nature 299, 802-803.
- Bennett, C. H. & Shor, P. W. (1998, 2002). Entanglement-assisted classical capacity of noisy quantum channels. PRL 83, 3081 + IEEE TIT 48, 2637.
- Schumacher, B. & Westmoreland, M. D. (1997). Sending classical information via noisy quantum channels. PRA 56, 131.
- Lloyd, S. (1997). Capacity of the noisy quantum channel. PRA 55, 1613. + Shor (2002) + Devetak (2005).

**OQ research files (I-series spawn)**:
- 本論 §4.4 OQ-P1-Capacity
- 本論 §5.4 OQ-P2-CrossClass
- 本論 §7.4 OQ-P4-Implementation
- 本論 §8.4 OQ-P5-Sparsity-Capacity
- (I1 spawn は I1 §8.3 listed)

**L0 / L1 / meta 依存**:
- `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` + (NEW candidate `zero_one_two_scaffold.md`)
- `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11 + §12, c_filtration_obstruction §8.5, c_information_theory §2 + §6, c_observation_optimal_gauge}.md`
- `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics}.md` (5-anchor 量子 instance source)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` (P1 source)
- `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**I-series future**: I3 (Information geometry) / I4 (Algorithmic info theory) / I5 (Topological data analysis) / 4th framework header candidate (Control / Causal / Network) — 起草未定 (本論 §10.2 で listing)
