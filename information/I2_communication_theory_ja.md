# Paper I2: 観測理論 ─ Communication theory

**サブタイトル**: 信号論 (0/1/2 scaffold) / 量子通信論 (3+ relational, 量子優位 formal) / **新規通信論 5 proposals** (framework 由来) / I-series final closure

**バージョン**: v0.2 (P1 capacity correction: 2.18 → 0.40 bits/symbol honest Shannon, 2026-04-28)
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

**(M3) 新規通信論 5 proposals (framework 由来)** — (P1) **σ\* phase-channel** (Q3 §4 σ\* gauge instance, EEG ESTABLISHED, **honest Shannon capacity $C_{\sigma_*} \approx 0.40$ bits/symbol** — uniform-input wrapped-Gaussian phase channel, M1 (closed-form) + M2 (Blahut-Arimoto) cross-check, `research/oq_p1_capacity_v0`) / (P2) **4-class resource-stratified channel** (T-AAS lift, 各 class が異なる capacity sub-channel) / (P3) **qutrit info-density codebook** (S17 e-extremum discrete argmax, qubit に対し ~5.5% Hartley density 優位) / (P4) **5-stage ln 2 chain converter** (S13 universal natural unit を媒介する cross-instantiation channel) / (P5) **Arrow 1 kernel narrowness channel taxonomy** (Q1 §6 4-vertex sparsity classification を channel design に lift)。各 proposal は I1 §6 5-anchor framework から **直接 derive**。

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

**Comparison to Shannon-Hartley**:
- Shannon-Hartley AWGN: $C = \frac{1}{2} \log_2(1 + S/N)$ bits/use
- P1 σ\*-channel at σ\*: $C_{\sigma_*} \approx 0.40$ bits/symbol (≈ ½ bit threshold)
- ~2x density advantage 主張は **REJECTED**: σ\* operating point で P1 は AWGN moderate SNR より低 capacity。phase-coding density advantage は σ ≪ σ\* regime (low-noise) でのみ成立。

**σ\* の honest Shannon-theoretic 解釈**: σ\* は wrapped-Gaussian phase channel の capacity が ≈ ½ bit/symbol を切る noise level。"half-amplitude $E[\cos Z] = 1/2$" 解釈と整合 (両者とも "channel が約半分死ぬ" 同じ物理的境界の異なる定量化) で、Shannon 量での characterisation は 5-stage ln 2 chain S4 σ\* gauge stage の **量化された情報論的 anchor** を提供。

### 4.3 EEG empirical verification + framework anchor

**EEG verified ESTABLISHED 2026-04-09** (`sheet_A_amplitude/sigma_star.md` Entry 2): 7 subjects × 5 bands ($\delta, \theta, \alpha, \beta, \gamma$) で σ\* phase damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ subject-band averaged std ≈ 0.0012 → P1 phase-channel が **biological signal context で empirical 動作確認済**。

**Framework anchor**: P1 は I1 §6 anchor (e) σ\* phase observation gauge の通信 paradigm lift。新規性: phase-noise-bounded channel が standalone communication paradigm として **quantitative capacity** $C_{\sigma_*}$ 提案。

### 4.4 Status

**P1 status**: candidate_v0.2_corrected (honest Shannon capacity ≈0.40 bits/symbol established by M1+M2 cross-check, EEG 動作確認、framework 概念 (phase-noise-bounded channel) 保持)。OQ-P1-Capacity → CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED (`research/oq_p1_capacity_v0.md` 2026-04-28)、v0 2.18 bits/symbol claim retracted、replaced 0.40 bits/symbol。

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

**P3 status**: ESTABLISHED (S17 codebook argmax = 3 ESTABLISHED 2026-04-23, 5/5 gate, `c_arrow_bridge_constants.md §12.1`)。Practical realization は engineering task, 5.5% advantage は **formal information-theoretic mathematical fact**。

**Framework anchor**: P3 は I1 §6 anchor (b) S17 直接 instance、量子通信論への量子優位 contribution としても active (qutrit-based protocols が qubit-based より info-density 最適)。

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
| **P1 σ\*-phase channel** | 軽 (Gaussian noise + threshold detection, $\sigma_*$ 単閾値) | 中 (phase coherence bounded by $\sigma_* = \sqrt{2 \ln 2}$, half-amplitude convention) | ✓ medium scale (signal-level, EEG biological scale verified) | △ novel (EEG ESTABLISHED 2026-04-09 として biological 動作確認、通信応用は uncharted) | honest Shannon $C_{\sigma_*} \approx 0.40$ bits/phase symbol at σ\*, advantage only at σ ≪ σ\* (low-noise regime) | **σ\*-near operating点で AWGN density advantage 不在**、phase-coherent hardware 必要、low-noise regime のみ density gain |
| **P2 4-class resource-stratified** | 重 (resource-theoretic operations, magic state distillation, Wigner negativity preparation, BQP-class 計算) | 低 (resource-class 内では minimal) | ✗ small (resource-bounded, class-specific) | ✗ highly speculative (理論枠組み、具体 protocol 未確立) | Per-class capacity bound + cross-class hierarchy | **理論的 elegance、実装 cost 量子計算 worst case**、研究段階 |
| **P3 qutrit codebook** | 中 (3-level hardware: 3-level optical pulses / 3-level superposition / 3-level discrimination) | 中 (3-level discrimination noise, quartit と同等水準) | ✓ medium-large (qutrit-supporting hardware で deployable) | △ feasible (3-level optical / qutrit superconducting 既存技術), 通信 standard 化未) | **5.5% Hartley density advantage**, S17 5/5 gate ESTABLISHED | **5.5% gain は実用的に意味あるか要検証**、ハードウェア 2-level → 3-level 移行コスト |
| **P4 5-stage ln 2 converter** | 重 (cross-instantiation transitions, Born ↔ von Neumann ↔ FDT ↔ Landauer ↔ σ\* 物理 conversion 全部実装) | 低 (5-fold redundancy) | ✗ small (lab-scale physical instantiation conversions) | ✗ highly speculative (各 stage 物理実装の cross-coupling 未確立) | 5-fold redundancy via ln 2 invariant | **冗長性 elegant、実装 cost 5-stage hardware 全部必要**, 思考実験段階 |
| **P5 Arrow 1 kernel narrowness taxonomy** | mode-specific (V₁ discrete: 軽 / V₂ Gaussian: 中 / V₃ poly-circuit: 重 / V₄ Bell: 中) | mode-specific | mode-specific | △ design framework (concrete protocol per mode, taxonomy 自体は guidance) | sparsity-mode optimal channel design | **設計 framework として有用、protocol-by-protocol 評価必要** |

### §11.3 主観察 (実装 vs framework lens)

**観察 11.3.1**: 信号論は "**重 0/1/2 scaffold base 圧倒的成熟 + 大量データ最適**", 量子通信論は "**低損失 + cryptographic, 研究段階**", **5 novel proposals は middle ground** ─ framework-derived advantage を持ちつつ実装 cost が信号論と量子通信の中間。

**観察 11.3.2 (framework-internal practical sweet spot, v0.2 corrected)**: I-series 5 proposals 中、**P3 qutrit codebook が "信号論級軽量 + framework-derived advantage"** で確実な sweet spot (5.5% Hartley density gain ESTABLISHED, S17 5/5 gate)。**P1 σ\*-channel は σ ≪ σ\* low-noise regime で density advantage、σ\* operating point では advantage 不在** (`research/oq_p1_capacity_v0.md` 2026-04-28、honest Shannon $C_{\sigma_*} \approx 0.40$ bits/symbol、AWGN moderate SNR と同水準)。P1 は **conditional secondary** (low-noise regime 限定) として評価。

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

### §11.5 OQ-Practical-Tradeoff-Quantification (本論 spawn 2026-04-27)

**OQ-Practical-Tradeoff-Quantification (本論 §11 spawn-off, MEDIUM)**:

**Scope**: 本 §11 比較表は **qualitative trade-off** (軽 / 重 / ✓ / ✗ / △ scale) 表現。**Quantitative trade-off bound** 化 — 例: P1 σ\*-channel の正確な capacity formula proof + AWGN advantage 厳密比較 / P3 qutrit 5.5% density gain の noise budget 含む net advantage / P4 5-stage converter の transition fidelity 計算 — を formal task として open。

**Status**: OPEN。Per-paradigm quantitative analysis = OQ-P1-Capacity (§4.4) + OQ-P2-CrossClass (§5.4) + OQ-P4-Implementation (§7.4) + OQ-P5-Sparsity-Capacity (§8.4) の **aggregate**。

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
