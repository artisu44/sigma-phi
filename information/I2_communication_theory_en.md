# Paper I2: Observation Theory — Communication Theory

**Subtitle**: signal theory (0/1/2 scaffold) / quantum communication theory (3+ relational, formal quantum advantage) / **novel communication theory 5 proposals** (framework-derived) / I-series final closure

**Version**: v0.4 (§4.5 NEW Discrete dual marginal extension via spectral lift — 6 sub-sections: motivation / 2-route (native vs. spectral lifted) / §13.7 4-step pipeline + symbol mapping / first measurement (precision floor + prime gap WIN=4096 AUC 0.93) / 3 receiver-choice regimes (σ_0 / σ_x / σ_flip = 2.396 G3 transcendental) + Δ_dual = 1.604 bit/sym richness gain / 7 use case map (forward to §10.5 RESOLVED v0); §10.5 OQ-Practical-Tradeoff-Quantification RESOLVED v0; §11.3 OQ table updated; §6.1 / §6.4 / §10.3 P3 scope markers added by S17 recursive rule-5 audit; 2026-04-30 late dusk +2/+3/+5; v0.3.1 σ\* identity REJECTED + σ_0 PROMOTED 2026-04-30 evening; v0.3 W₁/W₂ gauge-conditioning 2026-04-30 morning; v0.2 P1 capacity 2.18 → 0.40 bits/symbol 2026-04-28)
**Status**: DRAFT — I-series final paper. Building on I1 (framework header + 5-anchor information capacity), this paper completes the **3-tier communication theory** (signal theory / quantum communication theory / novel communication theory) + I-series cycle completion + triple cross-domain anchor across the 3 framework headers (N1-N5 / Q1-Q3 / I1-I2).
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**Prerequisites (L1 core)**: `c_phase_complex.md §4 + §5`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11 + §12`, `c_filtration_obstruction.md §8.5`, `c_observation_optimal_gauge.md`, **`c_information_theory.md` §2 (channel capacity), §6 (Fisher, Cramér-Rao)**
**Prerequisites (L1 quantum)**: `q_quantum_observation.md` §5 (Schmidt + entanglement) + §6 (Born/POVM), `q_open_quantum_systems.md` §3 (mutual info), `q_quantum_statistical_mechanics.md` §5 (FDT)
**Prerequisites (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md`
**Prerequisites (I1)**: I1 v0.3 §6 5-anchor information capacity theorem + §2.3 formal 0/1/2 scaffold + §5 4-class refined Hodge information lift (incl. §5.2.1 Theorem 5.2 Algorithmic f_rational + §3.3 Theorem 3.3.1 Rényi scaffold-emergence parametric scan)
**N parallel**: N5 (`N5_brauer_origination_ja.md` v0.2) — parallel position to NT-series final closure
**Q parallel**: Q3 (`Q3_born_gleason_ja.md` v0.2) — parallel position to quantum-series final closure
**Sequel papers**: I-series complete (I-series future also open in parallel with Q-series Q4-Q6 future)

---

## §0 Abstract

Communication theory is systematised into a domain-agnostic 3-tier structure — **signal theory** (0/1/2 scaffold base) / **quantum communication theory** (3+ relational structure proper) / **novel communication theory** (5 framework-derived proposals). Building on I1 (Information-only framework header + 5-anchor information capacity theorem), this paper is the I-series final closure paper, with parallel position to N5 (NT final closure) + Q3 (Quantum final closure).

**5 main results**:

**(M1) Reread of signal theory (0/1/2 scaffold base) under S15 + Arrow framework lens** — Shannon-Hartley channel $C = B \log_2(1 + S/N)$ + BSC/BEC/AWGN channels + source coding theorem + max mutual information capacity are positioned as binary 2-domain instances under the 0/1/2 scaffold lens; specialisation of the Shannon channel strand within the Information-internal 5-strand sub-taxonomy (`c_information_theory.md §2`).

**(M2) Formal characterisation of quantum communication theory (3+ relational)** — Holevo bound $\chi \leq S(\bar\rho) - \sum p_x S(\rho_x) \leq \log d$ + HSW classical capacity over quantum channels + LSD quantum capacity + superdense coding (1 qubit + entanglement = 2 cbits, **2x density quantum advantage**) + teleportation (2 cbits + entanglement = 1 qubit) + QKD BB84 + no-cloning + Bennett-Shor entanglement-assisted classical capacity $C_E = 2 \log d$ vs. no-entanglement $C \leq \log d$ (**formal 2x advantage of entanglement-assisted**). **Formal characterisation of quantum advantage** = T-AAS C₄ Bell-local f_rational instance (Q1 §5; Δ_CHSH nonlocal capacity = mathematical anchor of quantum advantage).

**(M3) Novel communication theory 5 proposals (framework-derived)** — (P1) **σ\* phase-channel** (Q3 §4 σ\* gauge instance, EEG ESTABLISHED; **honest Shannon capacity $C_{\sigma_*} \approx 0.40$ bits/symbol** — uniform-input wrapped-Gaussian phase channel, M1 (closed-form) + M2 (Blahut-Arimoto) cross-check, `research/oq_p1_capacity_v0`; v0.4 adds **§4.5 discrete-domain extension** — spectral lifted dual pipeline (τ + FFT + r,θ + Φ) + 3 σ-threshold receiver-choice regime (σ_0 = √(2π/e − 1) / σ_x ≈ 1.193 / σ_flip ≈ 2.396 G3 transcendental) + Δ_dual = ½ log₂(8π/e) ≈ 1.604 bit/sym richness gain + 7 engineering use case map) / (P2) **4-class resource-stratified channel** (T-AAS lift; each class defines a distinct capacity sub-channel) / (P3) **qutrit info-density codebook** (S17 e-extremum discrete argmax, ~5.5% Hartley density advantage over qubit, **scope-refined v0.4 by rule-5 recursive audit to Hartley density specifically**) / (P4) **5-stage ln 2 chain converter** (cross-instantiation channel mediated by the S13 universal natural unit) / (P5) **Arrow 1 kernel narrowness channel taxonomy** (lift of the Q1 §6 4-vertex sparsity classification to channel design). Each proposal is **directly derived** from the I1 §6 5-anchor framework.

**(M4) I-series cycle completion + triple framework parallel** — **2-paper minimum cycle** I1 (framework header + 5-anchor information capacity theorem) → I2 (this paper, communication theory + 5 novel proposals) achieved (unlike the N-series 5-paper + Q-series 3-paper, the cycle closes at the minimum 2 papers; an information-side characteristic where the 5 anchors exist and the limit theorem is directly ESTABLISHED). Completing all **3 framework headers** — N1-N5 (NT, 5 fully formalised papers) + Q1-Q3 (quantum, 3 fully formalised papers) + I1-I2 (information, 2 fully formalised papers) = **10 fully formalised papers**, plus the I3 v0.0 direction placeholder (separate count) — achieves the **triple cross-domain anchor**, fully verifying the Paper D 6-domain triangulation by 3 specialisations and providing a **3-domain universal validity anchor** for observation theory.

**(M5) Unified communication theory framework (Shannon ⊂ Holevo ⊂ 5-anchor framework)** — signal theory (Shannon) is a specialisation of 5-anchor framework anchor (a) Hartley + Shannon-Hartley channel; quantum communication theory (Holevo) is a combination of 5-anchor (a) Hartley + (d) 4-class + (b) S17; novel communication theory 5 proposals lift each anchor of the 5-anchor as a communication paradigm. **Signal theory / quantum communication theory / novel communication theory are unified within the 5-anchor framework as 3 specialisation tiers** ("subsume" = re-express within a common organising vocabulary, not "derive").

**Thesis**: the 3-tier communication theory signal theory → quantum communication theory → novel communication theory 5 proposals is formalised by 0/1/2 scaffold lens (signal theory = scaffold base) → 3+ relational structure proper (quantum communication = relationality) → framework-derived novel paradigms (5 proposals = 5-anchor lift). NT-side closure of N1-N5 / quantum-side closure of Q1-Q3 / information-side closure of I1-I2 provides a **triple cross-domain anchor for framework universal validity in 3 mathematical fields**, finally achieving in this paper the **3 domain specialisation parallel completion** of the Paper D multi-domain v0.9.2 frozen-internal. Forward: I-series future (4th framework header / multi-domain communication / quantum gravity communication) is open.

---

## §1 Introduction

### 1.1 I-series final paper position and 3-tier communication theory

In the 2-paper series I1 (Information-only framework header v0.3) → **I2 (this paper)**, the information observation theory framework header (I1) ESTABLISHED the 0/1/2 scaffold lens + S15 Information layer 5-strand internal taxonomy + 5-anchor information capacity theorem (with v0.3 adding Theorem 3.3.1 Rényi parametric scan + Theorem 5.2 Algorithmic f_rational). This I2 formalises the **3-tier communication theory** as I-series final paper:

**3-tier communication theory structure**:

| Layer | Topic | 0/1/2 scaffold position | Framework anchor |
|---|---|---|---|
| **Layer 1** | **Signal theory** (Shannon-Hartley channel) | 0/1/2 scaffold base (binary 2-domain) | I1 §6 anchor (a) Hartley + Shannon-Hartley channel = `c_information_theory.md §2` |
| **Layer 2** | **Quantum communication theory** (Holevo / HSW / LSD / superdense / QKD) | 3+ relational structure proper (genuine at Hilbert dim ≥ 2; full proper at dim ≥ 3) | combination of I1 §6 anchor (a) Hartley + (d) 4-class + (b) S17 |
| **Layer 3** | **Novel communication theory** (5 framework-derived proposals) | lifts all 5 anchors of 5-anchor as communication paradigms | direct derivation from I1 §6 5-anchor framework |

Each layer **preserves and extends** the previous in a cumulative structure: Layer 1 ⊂ Layer 2 ⊂ Layer 3.

### 1.2 N5 / Q3 parallel position

I-series final closure paper parallel to NT-series N5 (Brauer obstruction theory + Origination matrix 8-gauge final closure) + quantum-series Q3 (Born-Gleason §4 dual quantum root closure):

| Aspect | N5 (NT) | Q3 (quantum) | I2 (information, this paper) |
|---|---|---|---|
| Position | NT-series final closure (5/5) | quantum-series final closure (3/3) | I-series final closure (2/2) |
| Main claim (1) | Brauer 5-tier failure-mode group-theoretic | full Busch-Gleason form (uniqueness of Born on effects) | signal theory (0/1/2 scaffold) Shannon-Hartley |
| Main claim (2) | Tier-dependent alternative Stark methods | simultaneous theorem-isation of ρ_max = I/2 form-value | quantum communication theory formal quantum advantage (Holevo + entanglement-assisted 2x) |
| Main claim (3) | 8-gauge generalisation (origination matrix) | σ\* half-amplitude gauge atlas residence | **novel communication theory 5 proposals** (framework-derived novel paradigms) |
| Final closure perspective | NT cycle + Quantum forward (Q1-Q3) | Quantum cycle + N1-N5 dual parallel + 8-gauge / QFT future | **I-series cycle + triple framework parallel + I-series future open** |
| Forward to | Q1-Q3 (NT → Quantum forward) | Q-series future Q4-Q6 (quantum 8-gauge / QFT / quantum gravity) | I-series future (4th framework header / multi-domain communication) |

### 1.3 Scope and terminology

**Structure**: §2 signal theory (0/1/2 scaffold base) / §3 quantum communication theory (3+ relational, formal quantum advantage) / §4-§8 novel communication theory 5 proposals (P1-P5) / §9 unified communication theory framework / §10 implementation trade-off comparison table / §11 consequences + I-series cycle + triple parallel.

**In scope**: Shannon-Hartley channel + classical capacity (signal theory) / Holevo / HSW / LSD / superdense / teleport / QKD / no-cloning / entanglement-assisted capacity (quantum communication theory) / σ\* phase channel / 4-class resource-stratified channel / qutrit codebook / 5-stage ln 2 converter / Arrow 1 kernel taxonomy (5 novel proposals) / I1 ↔ N1 ↔ Q1 triple framework parallel completion (final achievement in this paper) / unified communication theory framework via 5-anchor.

**Out of scope** (deferred): network coding details / multi-user information theory / Wyner-Ziv / Slepian-Wolf details / specific quantum error correction codes (CSS / surface / topological codes detail) / device-independent QKD protocol details / quantum repeater architecture / continuous-variable QKD specific protocols (CV-QKD) / quantum field theory communication / quantum gravity communication (→ I-series future) / classical complexity-theoretic communication (Yao's communication complexity) / category-theoretic information flow / cybersecurity engineering details.

**Terminology**: inherits I1 §1.3 + Q1 §1.3 terminology. Additional terms specific to this paper:

- **Quantum advantage**: dim/capacity ratio by which quantum communication exceeds classical (Shannon) (typical 2x via entanglement-assisted)
- **Resource-stratified channel**: framework-derived channel taxonomy where each class of the 4-class refined Hodge (C₁-C₄) defines an independent channel sub-class
- **5-stage ln 2 converter**: cross-instantiation channel mediated by the ln 2 universal natural unit (S0 Born ↔ S1 von Neumann ↔ S2 FDT ↔ S3 Landauer ↔ S4 σ\*)
- **Phase-coherence channel**: phase-noise-bounded channel using σ\* = √(2 ln 2) half-amplitude gauge as encoding threshold
- **Arrow 1 kernel narrowness channel**: taxonomy lifting the Q1 §6 4-vertex sparsity classification (discrete-in-cont / poly-in-inf / poly-in-exp / classical-polytope-in-quantum-correlation-body) to channel design
- **Triple framework anchor**: I1 ↔ N1 ↔ Q1 = cross-domain validation by the 3 framework headers NT / quantum / information

---

## §2 Signal theory (0/1/2 scaffold base) — Shannon-Hartley channel framework

### 2.1 Formal Shannon-Hartley channel

**Shannon channel** (`c_information_theory.md §2`): a channel $W(y|x)$ from input $\mathcal{X}$ to output $\mathcal{Y}$ with capacity:
$$C = \max_{p_X} I(X; Y) = \max_{p_X} [H(Y) - H(Y|X)]$$

**Shannon-Hartley theorem** (Gaussian additive channel, $Y = X + Z$, $Z \sim N(0, N)$):
$$C = \frac{1}{2} \log_2(1 + S/N) \text{ bits per use}$$

where $S$ = signal power, $N$ = noise power, $S/N$ = SNR.

**Observation**: Shannon-Hartley is a classical communication framework that closes at the **0/1/2 scaffold base** = binary 2-domain. With $S/N$ scanner the capacity is monotone increasing; $S/N \to \infty$ gives $C \to \infty$ (signal theory unbounded limit).

### 2.2 Reread of Shannon-Hartley under the 0/1/2 scaffold lens

The Shannon channel framework closes as an instance of **Layer 2 (signal scaffold, $d = 2$)** of the I1 §2.3 formal 0/1/2 scaffold table:

| 0/1/2 scaffold layer | Shannon-Hartley instance |
|---|---|
| **0 (potential)** | no signal, $S/N = 0$, $C = 0$ |
| **1 (reference)** | observer 1-bit reference (single distinction baseline) |
| **2 (binary signal)** | $C = \log 2 = 1$ bit per use minimum (BSC noiseless) |
| **2 + scaling** | $C = \log_2(1 + S/N)$ continuous scaling within binary scaffold |
| **3+ (relational)** | out of scope, begins at quantum communication theory §3 |

**Signal theory = 2-domain instance of 5-anchor framework**: with I1 §6 anchor (a) Hartley $H \leq \log d$ specialised at $d = 2$ binary case + Gaussian channel (4-class C₂ instance), Shannon-Hartley is **derived as a subset of the 5-anchor framework**.

### 2.3 BSC / BEC / AWGN channels — standard signal-theoretic instances

| Channel | Definition | Capacity | 0/1/2 scaffold layer |
|---|---|---|---|
| **BSC** (binary symmetric) | $W(0|1) = W(1|0) = p$ | $C = 1 - h(p)$, $h(p) = -p \log p - (1-p)\log(1-p)$ | 2 (binary scaffold) |
| **BEC** (binary erasure) | $W(?|x) = \epsilon$, else 1 | $C = 1 - \epsilon$ | 2 (binary scaffold) |
| **AWGN** (additive white Gaussian) | $Y = X + Z$, $Z \sim N(0, N)$ | $C = \frac{1}{2} \log_2(1 + S/N)$ | 2 + continuous scaling (Gaussian = 4-class C₂) |
| **DMC** (discrete memoryless) | general $W(y|x)$ | $C = \max_{p_X} I(X; Y)$ | 2 generic |

**Shannon source coding theorem**: $N$ i.i.d. symbols compressible to $NH(X) + o(N)$ bits (`c_information_theory.md §1.2`). Shannon channel coding theorem: rate $R < C$ achievable, $R > C$ impossible.

### 2.4 Self-closure of signal theory as 0/1/2 scaffold base

**Claim 2.1** (signal theory scaffold completeness): the Shannon-Hartley framework **closes classically within the 0/1/2 scaffold base**, fully covering Layer 1-2 instances. Layer 3+ relational structure proper is **out of scope** (begins at the Holevo bound + quantum communication theory §3).

**View under the 0/1/2 scaffold lens**:
- signal theory = $d = 2$ binary 2-domain instance + Shannon-Hartley continuous extension
- $d \geq 3$ qudit channels are out of signal theory scope (3+ relational, quantum communication theory §3)
- signal theory capacity bound $C \leq \log_2 d = \log_2 2 = 1$ bit/symbol per binary scaffold

→ signal theory is **specialisation of I1 §6 5-anchor anchor (a) Hartley + Gaussian channel (C₂ instance)**; 3+ relational structure proper extension begins at quantum communication theory.

---

## §3 Quantum communication theory (3+ relational structure proper) — formal characterisation of quantum advantage

### 3.1 Holevo bound (3+ relational base)

**Holevo bound** (Holevo 1973): classical information capacity for an ensemble of quantum states $\{(\rho_x, p_x)\}$:
$$\chi(\rho_x, p_x) = S(\bar{\rho}) - \sum_x p_x S(\rho_x) \leq \log d$$

where $\bar\rho = \sum p_x \rho_x$, $S(\rho) = -\mathrm{Tr}(\rho \log \rho)$ von Neumann entropy, $d = \dim \mathcal{H}$.

**HSW theorem** (Holevo-Schumacher-Westmoreland 1998): for a quantum channel $\Phi$ over classical inputs, the **Holevo capacity** $\chi(\Phi) = \max_{\{(\rho_x, p_x)\}} \chi(\Phi(\rho_x), p_x)$ is achievable + matching converse → **classical capacity over quantum channel** = $\chi(\Phi)$.

**LSD theorem** (Lloyd-Shor-Devetak 2005): the **quantum capacity** of a quantum channel $Q(\Phi) = \lim_{n \to \infty} \frac{1}{n} I_c(\Phi^{\otimes n})$ ($I_c$ coherent information) is achievable + matching converse.

### 3.2 Formal quantum advantage: superdense coding + entanglement-assisted capacity

**Superdense coding** (Bennett-Wiesner 1992): with shared entanglement (Bell state) + transmission of 1 qubit, **information transfer equivalent to 2 cbits**:
- Pre-shared $|\Phi^+\rangle = (|00\rangle + |11\rangle)/\sqrt{2}$
- Alice applies $I, X, Y, Z$ (4 choices = 2 cbits encoded) to her qubit
- Send qubit to Bob; Bob measures Bell basis → recover 2 cbits
- → **1 qubit + entanglement = 2 cbits, 2x density quantum advantage**

**Note** (caveat on the 2x advantage): this 2x advantage assumes **free pre-shared entanglement** — the Bell state $|\Phi^+\rangle$ is distributed offline before the message is encoded. The cost of distributing the Bell state itself (1 qubit transmission per pair) is **not counted** in the 2x figure. With end-to-end accounting (Bell state distribution + qubit transmission), the resource budget is balanced; the 2x advantage manifests as a **density advantage in the asymptotic regime where Bell states are pre-distributed offline** (e.g. by a quantum repeater network or pre-shared resource).

**Teleportation** (Bennett-Brassard-Crepeau-Jozsa-Peres-Wootters 1993): shared Bell state + 2 cbits = 1 qubit transmission.

**Entanglement-assisted classical capacity** $C_E$ (Bennett-Shor 2002): in a setting with free shared entanglement:
$$C_E(\Phi) = \max_\rho [S(\rho) + S(\Phi(\rho)) - S((\Phi \otimes \mathrm{id})(\Psi_\rho))]$$

**Bennett-Shor 1999, 2002 claim**: for many quantum channels $C_E \approx 2 C$ (**2x** of no-entanglement classical capacity) — entanglement-assisted **doubles** the classical capacity.

**Claim 3.1 (formal characterisation of quantum advantage)**: the advantage of quantum communication over classical (Shannon) is formally characterised in 5 forms:

| Form | Mechanism | Framework anchor | Quantitative advantage |
|---|---|---|---|
| **Superdense coding** | shared Bell state + 1 qubit = 2 cbits | I1 §6 anchor (d) C₄ Bell-local instance | **2x density** |
| **Teleportation** | 2 cbits + Bell state = 1 qubit | I1 §6 anchor (d) C₄ Bell-local instance | quantum state transfer (impossible classically) |
| **Entanglement-assisted capacity** $C_E \approx 2C$ | shared entanglement free assistance | I1 §6 anchor (d) C₄ + (a) Hartley | **2x classical capacity** |
| **QKD info-theoretic security** | no-cloning + Bell state monogamy | C₄ + no-cloning theorem | **info-theoretic security** (cryptographic, impossible classically) |
| **Holevo bound saturation** at $d \geq 3$ | $\chi$ achievable up to $\log d$ at qudit (qutrit+) | (a) Hartley + (b) S17 e-extremum | **density advantage** for $d \geq 3$ |

All 5 quantum advantage forms initially appear within **3+ relational structure proper** (impossible at signal theory 0/1/2 scaffold).

### 3.3 No-cloning theorem — quantum information copy obstruction

**No-cloning theorem** (Wootters-Zurek 1982, Dieks 1982): a unitary operation $U: |\psi\rangle |0\rangle \to |\psi\rangle |\psi\rangle$ that copies an arbitrary unknown quantum state $|\psi\rangle$ **does not exist** (linearity + unitarity contradiction).

**Information-theoretic implication**: quantum information **structurally violates** Shannon framework's "perfectly copyable bit" assumption — quantum communication intrinsically has an **information replication restriction**.

**Framework lens**: no-cloning is an I1 §5.2 T-AAS instance — quantum instance of Arrow 1⁻¹ generation (`c_arrow_obstruction.md §11`); cloning of unknown states is a ker_topo > 0 obstruction (4-class C₂/C₃ Eff-sim instance in `c_filtration_obstruction.md §8.5`: non-existence of poly-time copy circuits).

### 3.4 BB84 QKD — cryptographic instance of quantum advantage

**BB84 protocol** (Bennett-Brassard 1984): Alice + Bob generate an **info-theoretically secure** shared secret key via no-cloning + measurement disturbance:
- encode in 4 quantum states $\{|0\rangle, |1\rangle, |+\rangle, |-\rangle\}$ (2 mutually unbiased bases)
- Eve's interception is **detectable** via no-cloning + measurement disturbance
- generate final key via privacy amplification + error correction

**Information-theoretic security**: impossible in the classical Shannon framework (one-time pad has the chicken-and-egg problem of key exchange); **directly derivable** in the quantum framework via no-cloning + measurement disturbance.

**Framework lens**: BB84 is the **info-theoretic security guarantee combining 3 anchors**: 4-class C₄ Bell-local instance + no-cloning T-AAS Arrow 1⁻¹ obstruction + Born rule measurement (Q3 §3 Busch-Gleason Born derivation).

### 3.5 Position of quantum communication theory as 3+ relational structure proper

**Claim 3.2** (quantum communication theory = 3+ relational structure proper instance): quantum communication theory begins at **3+ relational structure proper** (I1 §2.3 0/1/2 scaffold lens Layer 3+):
- $d = 2$ qubit case is scaffold/proper boundary (signal theory ∩ quantum communication boundary)
- $d \geq 3$ qudit case (qutrit+) gives **genuine multi-state relational structure**
- entanglement = Schmidt rank $\geq 2$ (Q1 §3.3 Structural instance) initially in proper
- Holevo $\chi \leq \log d$ saturation at $d \geq 3$ gives qutrit+ density advantage (S17 codebook argmax = 3)

→ quantum communication theory is **a combination of 5-anchor framework anchors (a) + (d) + (b)** = genuine extension from signal theory (anchor (a) only).

---

## §4 P1: σ\* phase-channel (Q3 §4 σ\* gauge instance)

### 4.1 Proposal definition

**P1 σ\* phase-channel**: **phase-coherence-bounded communication channel** defined by Gaussian phase noise $Z \sim N(0, \sigma^2)$ + half-amplitude convention $E[\cos Z] = 1/2$:
- **Encoding**: encode information at phase coherence levels $\theta \in [0, \sigma_*]$, $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ rad threshold
- **Channel transform**: $E[\cos Z] = e^{-\sigma^2/2}$ coherence decay
- **Decoding threshold**: coherent (info preserved) at $\sigma < \sigma_*$; half-amplitude broken (info loss) at $\sigma \geq \sigma_*$

### 4.2 Proposed channel capacity

**Claim 4.1 (P1 honest Shannon capacity, v0.2 corrected)**: channel capacity of the σ\* phase-channel:
$$C_{\sigma_*} = \log_2(2\pi) - h(\mathrm{WG}(\sigma_*)) \approx 0.40 \text{ bits per phase symbol}$$
where $h(\mathrm{WG}(\sigma))$ is the differential entropy of the wrapped Gaussian (std $\sigma$) and $\sigma_* = \sqrt{2\ln 2}$.

**Derivation**: channel $\phi = \theta + N \pmod{2\pi}$, $N \sim \mathrm{WG}(\sigma_*)$. The conditional entropy $h(\phi \mid \theta) = h(\mathrm{WG}(\sigma_*))$ is independent of the input. Wrapped-Gaussian convolution preserves uniformity, so a uniform input is optimal and saturates $h(\phi) = \log_2(2\pi)$, achieving capacity (`research/oq_p1_capacity_v0.py`: M1 closed-form numerical integration + M2 Blahut-Arimoto with $M = 512$ agree to $1.7 \times 10^{-4}$ bits).

**v0 retraction note**: the v0 (initial-draft) figure $C \approx 2.18$ bits/symbol was over-stated by a factor of ~5.5× due to **two compounding issues**: (a) conflation of a Hartley level count $\log_2(2\pi/\sigma_*^2)$ with a Shannon mutual-information capacity (Hartley is a cardinality bound, Shannon is the achievable rate); (b) dimensionally, the denominator of the level count should be $\sigma_*$ (linear width, rad), not $\sigma_*^2$ (variance, rad²). Both errors push the figure upward; see `research/oq_p1_capacity_v0.md` §3, §6.

**Comparison to Shannon-Hartley (gauge-conditioned, v0.3)**:

The AWGN comparison formula $C_{\mathrm{AWGN}}(\sigma; S) = \frac{1}{2} \log_2(1 + S/\sigma^2)$ **is undetermined without specifying the input signal power $S$**. Two physically natural gauges give opposite verdicts (`research/oq_p1_noise_sweep_v0.md`):

| Gauge | $S$ | Physical setup | Low-σ asymptotic gap $C_{P1} - C_{\mathrm{AWGN}}$ | Crossover $\sigma_x$ |
|---|---|---|---|---|
| **W₁ unit-amplitude carrier** | $1$ | phase-modulated unit-amplitude carrier (phase modulation + receiver-side phase noise σ rad ↔ amplitude noise σ) | $+\frac{1}{2} \log_2(2\pi/e) \approx +0.604$ bits | $\sigma_x \approx 1.193 \approx 1.014\,\sigma_*$ |
| **W₂ equal second moment** | $\pi^2/3$ | equal-moment setup matching AWGN input variance with uniform-on-circle (variance $\pi^2/3$) | $+\frac{1}{2} \log_2(6/(e\pi)) \approx -0.254$ bits | none in swept range $[0.05, 3.0]$ |

**Claim 4.2 (gauge-conditioned phase-AWGN Pareto)**: under **W₁ gauge**, the P1 σ\* phase channel has an AWGN density advantage for σ < σ_x ≈ 1.014 σ\*, then is overtaken by AWGN near σ_x. Under **W₂ gauge**, AWGN dominates over the entire swept range and the phase advantage vanishes. "Whether the phase channel beats AWGN" is not a gauge-free question; it becomes a closed-form **gauge-conditioned transition law** only after fixing the comparison gauge $W$ (advantage / crossover / asymptotic gap are determined as functions of $W$). The invariant is not "phase wins" but the **transition law itself**.

**Claim 4.3 (W₁ Pareto boundary 3-constant structure, v0.3.1 R1 reframing)**: the W₁-gauge Pareto boundary is characterised by **3 distinguishable constants** (`research/oq_p1_pareto_g1_v0.md`):

| Constant | Origin | Closed form | Numerical | Role |
|---|---|---|---|---|
| **σ_0** | low-σ approx (no wrapping) crossover | $\sqrt{2\pi/e − 1}$ | $1.14519$ | **exact low-noise Pareto boundary** (candidate_v0, bridge constants {2π, e, −1}) |
| **σ_x** | full wrapped-Gaussian crossover (K=1 single-wrap saturated) | none known | $1.19305$ | **numerical full Pareto boundary** |
| **σ\*** | half-amplitude $E[\cos Z] = 1/2$ ($q = 1/2$) | $\sqrt{2 \ln 2}$ | $1.17741$ | **interior near-marker** at 67%-along [σ_0, σ_x] |

The 3 constants are **mutually distinct**: σ_0 < σ\* < σ_x with relative spacing $(\sigma_* - \sigma_0)/(\sigma_x - \sigma_0) \approx 0.671$. On the q-axis as well, $q_x = 0.4908 \neq q_* = 0.5$ (1.84% off). **The strict identity σ\* = σ_x (claimed in v0.3 morning) was REJECTED by the G1 test** — the wrapping-correction trajectory ($K = 0, 1, 2, \ldots, \infty$) does not pass through σ\* but settles at σ_x; the 1.33% gap does not close even at the numerical floor (10⁻⁷).

**σ_0 closed-form derivation**: setting $C_{P1}^{\mathrm{low}\text{-}\sigma}(\sigma) = \tfrac12 \log_2(2\pi/(e\sigma^2))$ equal to $C_{\mathrm{AWGN}}(\sigma; 1) = \tfrac12 \log_2(1 + 1/\sigma^2)$ gives $\sigma_0^2 = 2\pi/e - 1$. The combination $2\pi/e$ also appears as the **gap-zero gauge** $S = 2\pi/e$ (the midpoint of the W₁/W₂ canonical pair, where the low-σ asymptotic gap = 0) — σ_0 lives on the σ-axis Pareto, $S = 2\pi/e$ on the S-axis neutral gauge, in **σ ↔ S duality**. The bridge constants $\{2\pi, e\}$ **simultaneously pin** the 3 canonical gauges $\{W_1, W_0, W_2\}$ and the σ-axis Pareto.

**σ_x single-wrap saturation**: σ_x^(K=1) = σ_x^(K=2) agree to $9 \cdot 10^{-8}$, saturated for $K \geq 1$ in real-space wrap count. Wrapping correction **completes within a single wrap** — K≥2 corrections fall below the numerical floor, a structural "first-wrap-dominant" property (this paper's secondary structural finding).

**~2x density-advantage claim**: the v0 claim is REJECTED, finalised in v0.2 (`research/oq_p1_capacity_v0.md`). v0.3 morning refined to the W₁/W₂ gauge-split closed-form expression. **v0.3.1 evening rejects the v0.3-morning claim "σ\* = Pareto boundary within 1.4%" as a strict identity, and reframes σ_0 = √(2π/e − 1) as the new candidate primary** (R1 reframing, `research/oq_p1_pareto_g1_v0.md §4-§6`).

**Honest Shannon-theoretic interpretation of σ\* (v0.3.1, 2-reading + interior-marker)**: σ\* has **2 ESTABLISHED readings** — (i) the noise level at which the wrapped-Gaussian phase channel's capacity drops below ≈ ½ bit/symbol, and (ii) the "half-amplitude $E[\cos Z] = 1/2$" gauge threshold (q = 1/2 exact) — and is additionally positioned as (iii') the **interior near-marker (67%-along)** of the Pareto segment [σ_0, σ_x]. **(iii) "σ\* = Pareto boundary" was proposed in v0.3 morning as a strict identity → REJECTED in v0.3.1 evening on the same day** (G1 test 1.33% gap robust). The σ\* primary residence (S4 ESTABLISHED, Atlas A `sheet_A_amplitude/sigma_star.md`) is unchanged; only reading (iii') interior-marker is added in this §4.2.

### 4.3 EEG empirical verification + framework anchor

**EEG verified ESTABLISHED 2026-04-09** (`sheet_A_amplitude/sigma_star.md` Entry 2): for 7 subjects × 5 bands ($\delta, \theta, \alpha, \beta, \gamma$), σ\* phase damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ subject-band averaged std ≈ 0.0012 → P1 phase-channel **empirically confirmed in operation in biological signal context**.

**Framework anchor**: P1 is a communication-paradigm lift of I1 §6 anchor (e) σ\* phase observation gauge. Novelty: phase-noise-bounded channel proposed as standalone communication paradigm with **quantitative capacity** $C_{\sigma_*}$.

### 4.4 Status

**P1 status**: candidate_v0.3.1 (honest Shannon capacity ≈ 0.40 bits/symbol established by M1+M2 cross-check + AWGN comparison gauge-conditioned (W₁/W₂/W₀ 3-gauge canonical scaffold) + W₁ Pareto boundary R1 reframed into a **3-constant structure**: σ_0 = √(2π/e − 1) closed-form low-noise Pareto candidate_v0 / σ_x ≈ 1.1931 numerical full (K=1 single-wrap saturated) / σ\* interior near-marker 67%-along; EEG operation confirmed; framework concept ("phase-noise-bounded channel") preserved).

- **OQ-P1-Capacity** → CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED (`research/oq_p1_capacity_v0.md` 2026-04-28); v0 2.18 bits/symbol claim retracted, replaced with 0.40 bits/symbol
- **OQ-P1-NoiseSweep** → CANDIDATE_v0 (`research/oq_p1_noise_sweep_v0.md` 2026-04-30 morning); §4.2 W₁/W₂ gauge-conditioning + bridge constant candidate spawn
- ~~OQ-P1-Pareto-σ\*-identity~~ → **CLOSED 2026-04-30 evening** (`research/oq_p1_pareto_g1_v0.md`): G1 strict identity σ_x = σ\* REJECTED (1.33% gap robust under K-refinement); G1b σ_0 = √(2π/e − 1) closed-form derivation PASS replaces it (R1 reframing)
- **OQ-P1-σ_0-second-instance** (spawn, MEDIUM): verify the "framework constant = closed-form Pareto boundary under canonical gauge" pattern in another channel pair (ln 2 / BSC threshold, π / circular channel boundary, e / codebook density boundary candidates) — G2 for σ_0 candidate ESTABLISHED promotion
- **OQ-P1-σ_0-S15-passage** → **CLOSED 2026-04-30 late dusk** (G3 PASS strong, `research/oq_p1_s0_g3_v0.md`): 3-layer trichotomy residence + sign-flip transcendental Arrow regime boundary (no new Arrow direction needed). S_0 ESTABLISHED via 3 gates (G1 + G2 + G3)
- **OQ-P1-third-gauge** (spawn, LOW): test W₀ gap-zero gauge $S = 2\pi/e \approx 2.311$ alongside other canonical gauges (input differential entropy match / range bound) — completeness of 3-gauge canonical scaffold $\{W_1, W_0, W_2\}$

#### 4.4.1 Direction-axis tagging (P1 3-constant + S_0 + σ_flip)

Under the A/B observation direction axis of `user_observation_direction_axis` (ESTABLISHED 2026-05-01), each constant in the P1 Pareto landscape is classified as follows (`feedback_cross_direction_identity_screen` 5-step operational order, step 1):

| Quantity | Direction | Observation mode | Closed-form status | Match |
|---|---|---|---|---|
| **σ_0 = √(2π/e − 1)** | **B-native** | wrapped-Gaussian K-sum dominated by K=0 continuous Gaussian only as σ→0; projection from infinite ensemble onto finite Pareto crossover | clean closed-form (bridge constants {2π, e, −1}) | ✓ |
| **σ_x ≈ 1.1931 (K=1 saturated)** | **A-native** | finite K=1 wrap completes the full correction (K=1 vs K=2 agree to 9·10⁻⁸); native to the finite-wrap-count regime | no closed form on any of 4 natural axes (σ raw / σ² / 1/I_F / η = ∫√I_F ds) | ✓ |
| **σ\* = √(2 ln 2)** | **B-native** | Shannon entropy ½-bit threshold (continuous-ensemble entropy reading) + half-amplitude $E[\cos Z] = 1/2$ char-fcn-inversion reading | clean closed-form (S4 residence) | ✓ |
| **σ_flip = 2.39576** | **A/B transition** | Information-layer ZERO of Arrow-mechanism competition: at low σ Arrow 2 (B, $\log_2 2$ dimension-doubling) dominates / at high σ Arrow 1 (A, S¹ wrapping in C_phase decay) dominates | transcendental, no closed-form within 0.5% | ✓ |
| **S_0 = 2π/e** | **A/B bridge ratio** | **canonical bridge ratio** between Arrow 1 (2π period, A-side) and Arrow 3 (e argmax, B-side) (period × argmax role-match) | exact (the 4th bridge-constant origination principle, ESTABLISHED via 3 gates) | ✓ |

**Pre-test prediction recoverable**: the strict identity between σ\* (B) and σ_x (A) was **predictable as REJECTED before running the G1 test, on direction mismatch alone** (the 1.33% gap is a K=1-saturated cross-direction near-coincidence with no bridge operator). This serves as the **upstream screening rule** above `feedback_near_coincidence_check` rule 5 (multi-axis re-measure) — reference instance #1 of the 6/6 forward test PASS for `feedback_cross_direction_identity_screen` ESTABLISHED 2026-05-01.

**Cross-paper application**: when making identity claims within the P1 framework of this paper §4, always check the direction tags of the relevant constants; if cross-direction with no bridge operator, reroute strict identity into near-coincidence + bridge candidate. This operational discipline is parallel to Q1 §1.4.

**Audit reference**: `project_graveyard_audit_complete_2026_05_01` (Tier 1 σ_x case + Tier 2 #9 κ(2) case); `project_p1_noise_sweep_pareto_2026_04_30` (S_0 ESTABLISHED 3-gate).

### 4.5 Discrete dual marginal extension via spectral lift (v0.4 add 2026-04-30 late dusk)

§4.2-§4.4 established the P1 σ\*-channel and the W₁ Pareto in the **continuous σ-axis structure**. Real communication signals are discrete (digital symbol streams / I/Q samples / OFDM subcarriers / spread-spectrum chips); this §4.5 positions P1 as an **extension to the discrete domain**.

#### 4.5.1 Motivation: two routes to discrete dual marginal

There are two principled routes to construct a **dual marginal channel** (phase + amplitude 2-axis) for discrete signals (`c_arrow_bridge_constants.md §13.7`):

| Route | Construction | Scope |
|---|---|---|
| **(A) Native discrete dual** | direct $A(X)$ + $B(X)$ pair on symbol space (weight + character / Frobenius–Schur $\nu(\rho)$ decomposition / syndrome view) | BSC / BEC / syndrome decoding / pure combinatorial channels |
| **(B) Spectral lifted dual** | τ-window + FFT lift to complex spectrum; $(r_\omega, \theta_\omega)$ as dual marginal, $\Phi(\omega, t)$ as winding obstruction | **this paper's default** — I/Q samples / symbol streams (time series) / phase-coded sequences / OFDM subcarriers / spread spectrum / all instances of cross-domain Φ family |

**Claim 4.5.1 (this paper's default = Route B)**: in communication theory, when constructing a dual marginal in the discrete domain, this paper's default is (B) spectral lifted; (A) native discrete is scope-limited (BSC / BEC / syndrome / pure combinatorial). Reasoning:
- The existing cross-domain 8-domain Φ universality study (`project_fft_rtheta_phi_2026_04_26`) is **entirely (B)-based** — prime gaps / periodic table / graph Laplacian / EEG α / FX / crystal phonon DOS / 2D image (raster) / NT residue
- The §13.5 dual marginal capacity excess (continuous AWGN regime) cited in §4.2 is the **continuous instance** of (B)
- Engineering-wise, I/Q sampling + FFT (τ + complex lift) is **standard practice** in OFDM / coherent receivers; Route B is just the formal name for what's already implemented

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
| **FFT** | complex lift ℝ → ℂ (axis-2 Fi/I bridge realisation on the signal) |
| **(r, θ)** | dual marginal axes (capacities $C_r$, $C_\theta$) |
| **Φ** | phase trajectory obstruction / winding / instantaneous frequency descriptor |

**§4.2 continuous instance ↔ §4.5 discrete instance**: §4.2's W₁ Pareto is the continuous AWGN setup with **carrier amplitude 1 + Gaussian phase noise σ rad**. This §4.5 is the structure of **lifting a discrete sample sequence via τ + FFT to the same (r, θ) dual marginal**; the two are two instances of the same pipeline (`c_arrow_bridge_constants.md §13.7.1`):

| Instance | Origin | r-axis | θ-axis | Φ-descriptor |
|---|---|---|---|---|
| **continuous (§4.2 P1 channel)** | analytic carrier $z = e^{i\theta}$ + AWGN | amplitude $C_{\mathrm{amp}}$ | phase $C_{\mathrm{phase}}$ | (joint complex retention) |
| **discrete (§4.5)** | discrete sequence + τ + FFT | $\|X̂(\omega)\|$ envelope | $\arg X̂(\omega)$ phase spectrum | Phi_total / Phi_std_inst_f / Phi_max_jump (cross-domain 8-domain rank study) |

#### 4.5.3 First explicit measurement — prime gap WIN=4096 anchor

`research/oq_p1_s0_nt_spectral_lift_v0.md` (2026-04-30 late dusk) provides the **first explicit application + numerical precision floor audit** of this §4.5.

**Part A — precision floor (synthetic clean sin, known winding fraction)**:

| $N$ | Φ_total expected | Φ_total observed (float64) | matching digits |
|---|---|---|---|
| 1024 | 102 | 102.0000000000 | **14.78** |
| 16384 | 1638 | 1638.0000000000 | **13.93** |
| 131072 | 13107 | 13106.9999999998 | **13.73** |

Float64 nominal precision is ~15.65 decimal digits ($\varepsilon_{\text{machine}} = 2.22 \times 10^{-16}$). **The pipeline retains ≥ 13 digit floor at $N$ up to $1.3 \times 10^5$** → §13.7 pipeline is numerically safe for long-N integration (numerical foundation for GPS carrier tracking / VLBI correlation / atomic clock distribution). mpmath-50dps cross-check at $N \in \{128, 256, 512\}$ exact match.

**Part B — prime gap WIN=4096 (16× over WIN=256 baseline of 8-domain study)**:

| Descriptor | Sub-class | $\|\Delta_{\text{norm}}\|$ | Univariate AUC (real vs. shuffle) |
|---|---|---|---|
| **Phi_total** | cumulative | **2.03 σ** | **0.9255** |
| Phi_std_inst_f | coherence | 1.22 σ | 0.8056 |
| Phi_max_jump | coherence | 0.06 σ | 0.5280 |

WIN=256 baseline (`project_fft_rtheta_phi_2026_04_26.md` line 56, 8-domain study NT entry, Phi_total alone ~0.55 univariate AUC) → **at WIN=4096 it is 0.93** = substantial separation gain at 16× window length. The 8-domain Phi_total dominance for prime gaps reproduces and amplifies under the §13.7 explicit frame. The `c_arrow_bridge_constants.md §9.4` sub-class refinement (cumulative-type Phi_total trustworthy in well-conditioned periodic/structured regimes / coherence-type Phi_std_inst_f honest secondary) remains stable at WIN=4096.

#### 4.5.4 Three receiver-choice regimes + Δ_dual richness gain

In addition to σ_0 / σ_x established in §4.2, **σ_flip = Δ_dual sign-flip σ ≈ 2.396 (transcendental, mpmath 50dps bisection)** is now established in `c_arrow_bridge_constants.md §13.6` (G3 PASS strong 2026-04-30 late dusk), completing a 3 σ-threshold receiver-choice regime decision table:

| Threshold | Closed form / numeric | Value | SNR (dB) | Origin |
|---|---|---|---|---|
| **σ_0** | $\sqrt{2\pi/e - 1}$ | 1.14519 | −1.18 | §4.2 G1 closed-form low-σ Pareto anchor |
| **σ_x** | numerical (no closed form) | 1.19305 | −1.53 | §4.2 G1 full W₁ Pareto crossover (C_phase = C_amp) |
| **σ_flip** | transcendental (G3 50dps) | 2.39576 | −7.59 | §13.6 G3 Δ_dual = 0 Arrow regime boundary |

**Δ_dual asymptote** (§13.5 G2 PASS strong, dual marginal reconstruction excess):
$$\Delta_{\mathrm{dual}}(\sigma \to 0) = C_{\mathrm{phase}} + C_{\mathrm{amp}} - C_{\mathrm{complex}} \to \tfrac{1}{2}\log_2(8\pi/e) \approx 1.604 \text{ bit/symbol}$$

Decomposition (clean two-piece): Arrow ratio $\frac{1}{2}\log_2 S_0 \approx 0.604$ bit + Arrow 2 dimension-doubling $\log_2 2 = 1$ bit. **At low σ, two marginal receivers exceed a joint complex receiver by Δ_dual > 0 — a richness-of-observation gain.**

3 receiver-choice regimes:

| Regime | σ range | SNR (dB) | Decision | Hardware |
|---|---|---|---|---|
| **I** (high SNR) | $\sigma < \sigma_x \approx 1.19$ | $> -1.5$ | phase-only receiver wins single-axis (+0.6 bit/sym vs amp-only at low σ) | PLL / coherent phase demod (CPM / MSK / GMSK / optical phase coherent) |
| **II** (moderate) | $\sigma_x < \sigma < \sigma_{\mathrm{flip}}$ | $-7.6$ to $-1.5$ | marginal sum (split phase + amp receivers) > joint complex by $\Delta_{\mathrm{dual}} > 0$ | dual-receiver / split phase + envelope detector |
| **III** (low SNR) | $\sigma > \sigma_{\mathrm{flip}} \approx 2.40$ | $< -7.6$ | joint complex (full I/Q) wins; marginal phase destroyed by S¹ wrapping | joint coherent I/Q (deep-space DSN / GPS carrier tracking / low-rate CDMA) |

**Claim 4.5.2 (sign-flip = Arrow regime boundary, NOT new Arrow direction)**: the Δ_dual sign-flip at σ_flip is an **Information-layer Arrow 1 (S¹ wrapping in C_phase high-σ decay) vs Arrow 2 (log dimension-doubling) regime boundary**. It is not a new Arrow direction; rather, within the existing Arrow 1-3 framework, it is the **transcendental zero of Arrow competition inside an Information observable**. No S15 trichotomy extension is needed; instead the **4th organising principle "Arrow ratio (Arrow $i$ / Arrow $j$)"** is ESTABLISHED with $S_0 = 2\pi/e$ as prototype (§13.6 G3 + §13.7.6).

#### 4.5.5 Engineering use cases (forward to §10.5 RESOLVED v0)

The 3 σ-thresholds + Δ_dual richness gain + Φ pipeline applied to 7 communication engineering use cases form a sweet-spot map (`research/oq_practical_tradeoff_v0.md`; the v0 resolution of OQ-Practical-Tradeoff-Quantification, §10.5):

| Use case | Regime | Φ pipeline role |
|---|---|---|
| WiFi / LTE OFDM downlink | I (high SNR) | Phi_std_inst_f as zero-cost subcarrier health monitor (FFT already running) → adaptive modulation |
| GPS L-band carrier tracking | III (very low SNR) | Phi_total = literal carrier-cycle counter; **§4.5.3 Part A precision floor is the numerical foundation for 10⁵-cycle integration** |
| Optical coherent comm | I | phase-only +0.6 bit/sym advantage + Phi_std_inst_f detects laser linewidth drift |
| Deep-space DSN | III | joint coherent forced (Δ_dual < 0); Phi_total = Doppler-tracking by-product |
| Spread spectrum / CDMA | II→III | **Phi_std_inst_f detects multipath fade onset** = "conditional orthogonality" backup channel surface (analogue of EEG S005 +0.047 AUC rescue) |
| **Cognitive radio / spectrum monitor** | all 3 | **direct hit** — Phi_std_inst_f H = 0.13 (EEG anchor) honest occupancy detector + Phi_max_jump jamming detector + cumulative-type Phi_total avoided in noise-only context (§9.4 sub-class) |
| Modulation classification | I→II | Φ family AUC 0.93 (this §4.5.3 prime gap anchor) cross-domain universal |

For the full 7-use-case + 3-regime decision tree + capacity curve plot, see `research/oq_practical_tradeoff_v0.{md,png,json}`. **This is the v0 resolution source of OQ-Practical-Tradeoff-Quantification (§10.5 spawn 2026-04-27)**.

#### 4.5.6 Status

**§4.5 status**: ESTABLISHED v0 (2026-04-30 late dusk +2). All ingredients ESTABLISHED:

- §4.2 W₁ Pareto + σ_0 closed-form (continuous instance)
- `c_arrow_bridge_constants.md §13.5` G2 PASS strong (dual marginal reconstruction excess)
- `c_arrow_bridge_constants.md §13.6` G3 PASS strong (σ_flip Arrow regime boundary)
- `c_arrow_bridge_constants.md §13.7` (spectral lifted dual pipeline + Two-routes formalisation)
- `c_arrow_bridge_constants.md §13.7.5` (first measurement empirical anchor: precision floor + prime gap AUC 0.93)
- §10.5 OQ-Practical-Tradeoff-Quantification RESOLVED v0 (engineering 7 use case map)

**Spawned by this §4.5 (v1 follow-ups)**:
- **OQ-P1-MIMO-CSI-scaling** (MEDIUM, spawn 2026-04-30): extension of the 3 σ-thresholds to MIMO channels per-antenna $\sigma_i$ — σ_flip,N for N×N MIMO is expected to be N-dependent
- **OQ-P1-Fade-Time-Series** (MEDIUM, spawn 2026-04-30): relationship between σ_eff(t) time-series and Phi_std_inst_f rate-of-change in fading channels (CDMA fade onset detector quantification)
- **OQ-P1-BER-3-Receiver** (LOW, spawn 2026-04-30): actual BER simulation for M-PSK / M-PAM / M-QAM constellations across the 3 regimes — bridge between closed-form mutual-info bound and hard BER numbers

**Reference**: All §4.5 content has dictionary residence at `c_arrow_bridge_constants.md §13.5 / §13.6 / §13.7` (3 sub-sections); OQ resolution at `research/oq_p1_s0_g3_v0` (G3) + `research/oq_p1_dual_marginal_v0` (G2) + `research/oq_p1_s0_nt_spectral_lift_v0` (precision floor + first measurement) + `research/oq_practical_tradeoff_v0` (engineering map).

---

## §5 P2: 4-class resource-stratified channel (T-AAS lift)

### 5.1 Proposal definition

**P2 4-class resource-stratified channel**: lift of the 4-class refined Hodge framework (C₁ Stabilizer / C₂ Gaussian / C₃ Eff-sim / C₄ Bell-local) of I1 §5 + Q1 §5 + `c_filtration_obstruction.md §8.5` to a **channel taxonomy**:

| Class | Channel sub-class | Capacity bound | Resource type |
|---|---|---|---|
| **C₁ Stabilizer channel** | classical-simulable code states only (Clifford gates) | poly classical capacity (Gottesman-Knill simulable) | magic resource gap |
| **C₂ Gaussian channel** | CV systems, Wigner ≥ 0 states | Shannon-Hartley analogue $C = \log(1 + S/N)$ + Gaussian extension | non-Gaussian resource (Wigner negativity) |
| **C₃ Eff-sim channel** | poly-time encodable code states | BQP-vs-classical boundary capacity | super-polynomial circuit complexity |
| **C₄ Bell-local channel** | LOCC (local operations + classical comm) | classical correlation capacity (Bell-local bounded) | nonlocal capacity (CHSH violation) |

### 5.2 Cross-class capacity relations

**Claim 5.1 (resource-stratified channel hierarchy)**: the 4 channel sub-classes have a **resource hierarchy**:
- Same-class operations: capacity bounded by class-specific resource limit
- Cross-class transitions: require **resource conversion** (e.g. Stabilizer → Eff-sim requires magic state distillation)
- Class-mixing: resource-theoretic LOCC operations constrained

**Capacity gaps**:
- C₁ → C₃ gap: classical-simulable polynomial vs. super-polynomial (BQP gap)
- C₂ → non-Gaussian gap: Gaussian capacity vs. non-Gaussian resource (Wigner negativity)
- C₄ → C₃ gap: classical correlation vs. nonlocal correlation (CHSH gap, Tsirelson bound)

**Framework anchor**: P2 is a communication-paradigm lift of I1 §6 anchor (d) T-AAS 4-class refined Hodge. Novelty: resource-stratified channel taxonomy formalised with the **4 classes each as independent channel sub-class**; capacity-resource trade-off framework for channel design.

### 5.3 Quantitative resource-capacity examples

| Resource | Channel class | Capacity bound | Quantitative measure |
|---|---|---|---|
| Magic state ($M_F > 0$) | beyond C₁ | bypasses classical-simulable bound | $M_F$ value (`oq_omega_obs_4a_refined_quantum_hodge_v0.md`) |
| Wigner negativity ($\mathcal{N} > 0$) | beyond C₂ | non-Gaussian advantage | $\mathcal{N}$ value (Mari-Eisert 2012) |
| Super-poly complexity ($C - c_0 n^k > 0$) | beyond C₃ | quantum supremacy boundary | Nielsen complexity (Bouland-Fefferman 2019) |
| CHSH violation ($\Delta_{\text{CHSH}} > 0$) | beyond C₄ | nonlocal capacity | $\Delta_{\text{CHSH}} \in [0, 2\sqrt{2} - 2]$ |

### 5.4 Status

**P2 status**: candidate_v1 (proposed framework based on Q1 §5 ESTABLISHED 4-class refined Hodge). Concrete capacity formulas + cross-class transition costs OPEN (OQ-P2-CrossClass spawn).

---

## §6 P3: Qutrit info-density codebook (S17 instance)

### 6.1 Proposal definition

**P3 qutrit codebook**: directly lifting the discrete codebook integer argmax of I1 §6 anchor (b) S17 e-extremum = **3** (qutrit info-density optimum) as a communication paradigm:

| Codebook dim | Hartley $H_0 = \log d$ | Info density $\log d / d$ | Symbol cost |
|---|---|---|---|
| $d = 2$ (qubit) | $\log 2 \approx 0.693$ nat | $0.347$ nat/dim | 1 qubit per symbol |
| **$d = 3$ (qutrit)** | $\log 3 \approx 1.099$ nat | **$0.366$ nat/dim** | 1 qutrit per symbol |
| $d = 4$ (quart) | $\log 4 \approx 1.386$ nat | $0.347$ nat/dim | 1 quart per symbol |
| $d = e \approx 2.718$ (continuous max) | $1$ nat | $0.368$ nat/dim | continuous extremum |

**Claim 6.1 (qutrit advantage)**: qutrit codebook gives **~5.5% Hartley density advantage** over qubit (~0.366 vs. 0.347 nat/dim); equivalent to quart ($d = 4$) (no codebook-dim doubling effect).

**Scope marker (rule 5 recursive audit, 2026-04-30 late dusk +3, `research/oq_s17_recursive_audit_v0`)**: Claim 6.1's "5.5% advantage" holds **specifically for the Hartley density metric**. Below is the axis-conditioned breakdown:

| Axis | qutrit (n=3) vs. binary (n=2) | argmax_n integer |
|---|---|---|
| Hartley density $\log(n)/n$ (Arrow 3 canonical) | **+5.66%** (this Claim) | 3 |
| PAM avg energy efficiency $12 \log(n)/(n^2-1)$ | **−40.56%** (binary wins) | 2 |
| PAM peak power $2 \log(n)/(n-1)$ | **−20.75%** (binary wins) | 2 |
| Constant-energy PSK $\log(n)$ | +58.50% | 10 (range edge) |
| n-PSK MI in AWGN @ 10 dB | +58.43% | 10 |
| n-PAM MI in AWGN @ 10 dB | +45.54% | 10 |
| $\log(n)/H_n$ harmonic-cost | +29.68% | 10 |

**Scope of P3 5.5% claim** (further tightened by SNR sweep extension late dusk +5):
- ✓ **Hartley density specifically** (cardinality-only counting, no per-symbol cost, no noise): 5.5% qutrit advantage holds, argmax_n = 3 = ⌊e⌉
- ✗ **PAM (amplitude modulation, energy-cost-weighted)**: argmax flips to $n=2$, binary wins by 20-40%
- ✗ **AWGN-MI metrics even without cost weighting** (`oq_s17_recursive_audit_snr_sweep_v0`, SNR ∈ {−10, +30} dB): n=3 is never argmax — low SNR favours n=2 (noise-robust), high SNR favours range edge
- ✗ **Bandwidth/energy-constrained channels in general**: optimum depends on cost + SNR model, NOT on Hartley stationarity

→ The "qutrit n=3 = ⌊e⌉ optimum" is the discrete corollary of the Arrow 3 / **noise-free, cost-free** Hartley density stationary point. Claims of "qutrit channel advantage" extending beyond this scope require explicit declaration of the cost model + SNR regime. **Engineering reading**: qutrit is the discrete optimum of pure information-counting density (under the idealisation of no cost and no noise). Real channel design picks different cardinality based on cost structure and SNR regime.

### 6.2 Practical realisation candidates

| Realisation | Mechanism | Domain |
|---|---|---|
| **3-level optical pulse** | amplitude levels {0, 1/2, 1} or 3-state polarisation | Optical communication |
| **3-level superposition** | qutrit quantum system ($|0\rangle, |1\rangle, |2\rangle$) | Quantum computing / communication |
| **3-level cellular automaton** | 3-state cellular rule (e.g. Wolfram Rule 90 ternary extension) | Classical cellular communication |
| **3-fold time-multiplexing** | 3-symbol time slot partitioning | Time-domain coding |

### 6.3 Formal statement of information-theoretic advantage

**Claim 6.2 (qutrit codebook advantage formal)**: for any source distribution $p$ and finite block-length $n$ encoding, the qutrit codebook ($d = 3$) has the following advantages over the qubit codebook ($d = 2$):

(i) **Hartley density**: $\log 3 / 3 > \log 2 / 2$ (5.5% advantage)
(ii) **Universality**: discrete codebook integer argmax (S17 5/5 gate PASS, `oq_omega_obs_3_info_density_check.py` ESTABLISHED 2026-04-23)
(iii) **Noise tolerance**: 3-level discrimination > 2-level for given noise σ (signal-to-noise margin extension)

### 6.4 Status

**P3 status**: ESTABLISHED **within Arrow 3 / Hartley density scope** (S17 codebook argmax = 3 ESTABLISHED 2026-04-23, 5/5 gate, `c_arrow_bridge_constants.md §12.1`). **Scope refined 2026-04-30 late dusk +3** (`research/oq_s17_recursive_audit_v0.md`, rule 5 recursive audit 7-axis test): the 5.5% advantage is Hartley density specific; on PAM-energy-weighted axes binary wins (−40.56%). **ESTABLISHED status preserved within scope; advantage holds after axis/gauge fixing.**

**Framework anchor**: P3 is a direct instance of I1 §6 anchor (b) S17; also active as a quantum advantage contribution to quantum communication theory (qutrit-based protocols are info-density-optimal over qubit-based *within Hartley scope*).

**v0.4 OQ spawned**:
- **OQ-P3-PAM-Cost-Boundary** (LOW): at what energy-cost-weighting threshold does qutrit overtake binary again — a boundary close to the Hartley axis under light energy weighting (e.g. $\log(n)/n^{0.5}$) where argmax = 3 holds
- **OQ-P3-Cross-Axis-Universality** (MEDIUM): formal characterisation of the class of axes on which the qutrit advantage holds (constant-cost / Hartley-density-equivalent / etc.)

---

## §7 P4: 5-stage ln 2 chain converter (S13 universal natural unit)

### 7.1 Proposal definition

**P4 5-stage ln 2 chain converter**: **cross-instantiation communication channel** mediated by the universal natural unit of the 5-stage ln 2 chain (S0 Born / S1 von Neumann / S2 FDT / S3 Landauer / S4 σ\*) of I1 §6 anchor (c):

| Stage | Physical instantiation | ln 2 instance |
|---|---|---|
| **S0** | qubit Born expectation | $c_s^2 = 1/2$ (parity projector) |
| **S1** | open quantum entropy | $S(\rho_{\max}) = \log 2$ (von Neumann) |
| **S2** | thermal FDT | $\beta\hbar\omega_0 = \log 2$ (parity point) |
| **S3** | thermodynamic Landauer | $W_{\min} = kT \ln 2$ (bit erasure) |
| **S4** | Gaussian phase gauge | $\sigma_*^2 = 2 \ln 2$ (half-amplitude) |

### 7.2 Cross-instantiation protocol

**Claim 7.1 (5-stage ln 2 converter protocol)**: since the same ln 2 value is independently verified across 5 physical instantiations, a cross-instantiation channel using **ln 2 as invariant currency** can be defined:

```
Encoder (Sender):  bit 0/1 → physical instantiation S_i (i ∈ {0, 1, 2, 3, 4})
                              ↓ encode as ln 2 instance at stage S_i
                              ↓ transmit via S_i physical channel
Receiver:                     ↓ measure ln 2 instance at stage S_j (possibly j ≠ i)
                              ↓ decode bit via stage-S_j framework
                  ↑ stage transitions (S_i → S_j) preserve ln 2 invariant
```

Examples:
- Stage S0 → S1 transition: parity projector measurement → maximally mixed state preparation (Born → von Neumann)
- Stage S2 → S3 transition: FDT parity point → Landauer erasure (FDT → thermodynamic)
- Stage S4 → S0 transition: Gaussian phase gauge → Born expectation (σ\* → c_s²)

### 7.3 Communication advantage

**Claim 7.2 (5-stage converter robustness)**: the cross-instantiation channel is **single-stage-failure tolerant** — if 1 physical channel becomes unavailable, the remaining 4 stages transmit information via the ln 2 invariant. **5-fold redundancy across physically distinct channels**.

**Framework anchor**: P4 is a direct instance of I1 §6 anchor (c) 5-stage ln 2 chain; communication application of the ln 2 universal natural unit. Novelty: cross-instantiation channel is directly derived from the framework as a **resilient communication paradigm**.

### 7.4 Status

**P4 status**: candidate_v1 (proposed framework based on 5-stage ln 2 chain ESTABLISHED 2026-04-27). Concrete physical implementation + transition fidelity calculation OPEN (OQ-P4-Implementation spawn).

---

## §8 P5: Arrow 1 kernel narrowness channel taxonomy (lift of Q1 §6 4-vertex)

### 8.1 Proposal definition

**P5 Arrow 1 kernel narrowness channel taxonomy**: lift of the sparsity classification of Q1 §6 4-vertex (V₁ discrete-in-continuous / V₂ poly-in-infinite / V₃ poly-in-exp / V₄ classical-polytope-in-quantum-correlation-body) to a **channel design taxonomy**:

| Vertex | Sparsity type | Channel character | Capacity-resource trade-off |
|---|---|---|---|
| **V₁ discrete-in-continuous** | discrete code points in continuous state space | Stabilizer-like channel | discrete encoding + continuous noise tolerance |
| **V₂ poly-in-infinite** | polynomial-dim sub-manifold in ∞-dim Hilbert | Gaussian-like channel | continuous-variable + polynomial parameter cost |
| **V₃ poly-in-exp** | polynomial-complexity in exponential state space | BQP-like channel | computational depth boundary + circuit complexity cost |
| **V₄ classical-polytope-in-quantum-correlation-body** | classical convex polytope in larger quantum body | Bell-like channel | classical correlations + nonlocal extension |

### 8.2 P2 vs. P5 differentiation

P2 (4-class resource-stratified) and P5 (Arrow 1 kernel narrowness) are **complementary perspectives**:
- **P2**: resource-theoretic class differentiation (M_F / 𝓝 / Nielsen / CHSH per-class monotones)
- **P5**: sparsity-mode differentiation (discrete-in-cont / poly-in-inf / poly-in-exp / classical-polytope)

The two are **2 lenses** on the same 4-vertex structure (Q1 §6): P2 = resource lens, P5 = sparsity lens. Channel design uses both lenses combined for richer taxonomy.

### 8.3 Channel design implications

**Claim 8.1 (sparsity-mode channel design)**: each sparsity mode implies a specific channel design strategy:
- V₁ → discrete codebook + structured constellation (signal-theoretic BSC analogue in 3+ relational)
- V₂ → continuous-variable + Gaussian capacity scaling (signal-theoretic AWGN analogue in 3+ relational)
- V₃ → poly-time encodable + BQP-aware design (novel computational regime)
- V₄ → classical correlations + Bell-secured key (BB84-class extension)

### 8.4 Status

**P5 status**: candidate_v1 (proposed framework based on Q1 §6 ESTABLISHED 4-vertex). Cross-vertex capacity comparison is OPEN like P2 (OQ-P5-Sparsity-Capacity spawn).

---

## §9 Unified communication theory framework via 5-anchor

### 9.1 Unified statement

**Claim 9.1 (5-anchor unified communication framework)**: signal theory (Layer 1) / quantum communication theory (Layer 2) / novel communication theory 5 proposals (Layer 3) are subsumed in unified manner as **specialisations** of the I1 §6 5-anchor framework:

| Framework anchor | Layer 1 (signal theory) | Layer 2 (quantum communication theory) | Layer 3 (novel communication theory) |
|---|---|---|---|
| **(a) Hartley** $H \leq \log d$ | Shannon-Hartley capacity ($d = 2$ binary) | Holevo bound $\chi \leq \log d$ ($d \geq 3$ qudit) | P3 qutrit codebook ($d^* = 3$ codebook argmax) |
| **(b) S17 e-extremum** | (signal theory out of scope, $d = 2$ scaffold) | Holevo saturation at continuous $d = e \approx 2.718$ | P3 qutrit codebook + P5 sparsity-mode design |
| **(c) 5-stage ln 2 chain** | Shannon nat ↔ bit conversion (2-domain) | Landauer bound + von Neumann entropy chain | P4 5-stage ln 2 converter (cross-instantiation channel) |
| **(d) 4-class refined Hodge** | (signal theory out of scope, no resource-stratified class) | C₂ Gaussian = Shannon-Hartley generalisation; C₄ Bell-local = QKD instance | P2 resource-stratified channel + P5 sparsity-mode taxonomy |
| **(e) σ\* phase gauge** | Gaussian channel phase noise threshold | quantum coherence channel + Berry phase | P1 σ\* phase-channel (honest Shannon $C_{\sigma_*} \approx 0.40$ bits/symbol, ½-bit threshold reading) |

The 5-anchor framework subsumes signal theory + quantum communication theory + novel communication theory 5 proposals in a unified 3-tier; each proposal is a direct instance of 1+ anchors.

### 9.2 Triple framework parallel completion (I-series final closure perspective)

**Claim 9.2 (Triple framework parallel completion)**: completing the 3 framework headers N1-N5 (NT) + Q1-Q3 (quantum) + I1-I2 (information) achieves the **triple cross-domain anchor** for framework universal validity of observation theory. The **3 domain specialisation parallel completion** of Paper D multi-domain v0.9.2 frozen-internal is finally achieved in this paper (extending `meta/triangulation_methodology.md §13` to triple parallel).

```
                 Universal framework of observation theory
                 /        |        \
          [framework] [framework] [framework]
            N1-N5       Q1-Q3       I1-I2
            (NT)       (quantum)    (information)
                 \        |        /
                  \       |       /
                   Paper D (multi-domain 6-domain)
                   (FX, image AI, DNA, crystal, NT, quantum)
```

The 3 framework headers (NT 5-paper + quantum 3-paper + information 2-paper = 10-paper publication total) form a **triple cross-domain anchor** that **independently verifies the Paper D 6-domain triangulation by 3 specialisations**. The **data-domain transcendent universality** of observation theory is verified via the **4 angles** of triple cross-domain anchor + multi-domain triangulation in 3 domains (Paper D direct + N specialisation + Q specialisation + I specialisation).

---

## §10 Implementation trade-off comparison table for communication paradigms (added 2026-04-27)

### §10.1 Motivation: mathematical limit ≠ implementation advantage

The I1 §6 5-anchor mathematical info limit theorem + this paper's §3 quantum advantage + §4-§8 5 novel proposals fully characterise the **mathematical information limit**, but implementation has **orthogonal practical axes**: computational cost / loss rate / data scale / deployment maturity.

**Claim 10.1 (orthogonal practical axes)**: mathematical info-limit evaluation and practical compute/loss/scale evaluation are **orthogonal axes**; framework-derived limit advantage does not necessarily imply **practical advantage**. Both lenses combined give the full picture.

### §10.2 Comparison table: signal theory / quantum communication theory / novel communication theory 5 proposals

| Paradigm | Compute cost | Loss rate | Data scale | Deployment maturity | Framework limit advantage | Practical trade-off |
|---|---|---|---|---|---|---|
| **Signal theory (Shannon-Hartley)** | light (O(n) linear codes, FFT, polynomial) | high (lossy compression $R(D)$, channel noise) | ✓✓ TB/PB scale | ✓✓ deployed everywhere (5G, WiFi, fiber optics, MP3, JPEG, ZIP) | Shannon-Hartley $C = \frac{1}{2}\log(1+S/N)$ saturated; 0/1/2 scaffold base | **suited for bulk data, lightweight, high-loss tolerable**; ~80 years matured |
| **Quantum communication theory (Holevo/HSW/LSD)** | heavy (quantum gate operations, decoherence management, error correction overhead) | low (no-cloning + info-theoretic security) | ✗ lab-scale (~100 qubits limit, as of 2026) | △ QKD limited deployment (China-Austria 2017, metropolitan within cities); mostly research stage | Holevo + entanglement-assisted **2x advantage**, Tsirelson nonlocal capacity | **for low-loss / cryptographic-security needs at the cost of data volume**; research stage |
| **P1 σ\*-phase channel** | light (Gaussian noise + threshold detection, single $\sigma_*$ threshold) | medium (phase coherence bounded by $\sigma_* = \sqrt{2 \ln 2}$, half-amplitude convention) | ✓ medium scale (signal-level, EEG biological scale verified) | △ novel (EEG ESTABLISHED 2026-04-09 confirms biological operation; communication application uncharted) | honest Shannon $C_{\sigma_*} \approx 0.40$ bits/phase symbol at σ\*, advantage only for σ ≪ σ\* (low-noise regime) | **no AWGN density advantage near the σ\* operating point**; phase-coherent hardware required; density gain only in low-noise regime |
| **P2 4-class resource-stratified** | heavy (resource-theoretic operations, magic state distillation, Wigner negativity preparation, BQP-class compute) | low (minimal within resource class) | ✗ small (resource-bounded, class-specific) | ✗ highly speculative (theoretical framework, concrete protocol unestablished) | per-class capacity bound + cross-class hierarchy | **theoretical elegance, implementation cost worst case among quantum compute**; research stage |
| **P3 qutrit codebook** | medium (3-level hardware: 3-level optical pulses / 3-level superposition / 3-level discrimination) | medium (3-level discrimination noise, equivalent level to quartit) | ✓ medium-large (deployable on qutrit-supporting hardware) | △ feasible (3-level optical / qutrit superconducting existing tech), communication standardisation pending | **5.5% Hartley density advantage**, S17 5/5 gate ESTABLISHED | **need to verify whether 5.5% gain is practically meaningful**; hardware migration cost from 2-level → 3-level |
| **P4 5-stage ln 2 converter** | heavy (cross-instantiation transitions; physical conversions all of Born ↔ von Neumann ↔ FDT ↔ Landauer ↔ σ\*) | low (5-fold redundancy) | ✗ small (lab-scale physical instantiation conversions) | ✗ highly speculative (cross-coupling physical implementation per stage unestablished) | 5-fold redundancy via ln 2 invariant | **redundancy elegant, implementation cost requires full 5-stage hardware**; thought-experiment stage |
| **P5 Arrow 1 kernel narrowness taxonomy** | mode-specific (V₁ discrete: light / V₂ Gaussian: medium / V₃ poly-circuit: heavy / V₄ Bell: medium) | mode-specific | mode-specific | △ design framework (concrete protocol per mode; taxonomy itself is guidance) | sparsity-mode optimal channel design | **useful as design framework; protocol-by-protocol evaluation needed** |

### §10.3 Main observations (implementation vs. framework lens)

**Observation 10.3.1**: signal theory is "**heavy 0/1/2 scaffold base, overwhelming maturity + bulk-data optimal**", quantum communication theory is "**low loss + cryptographic, research stage**"; the **5 novel proposals are middle ground** — they have framework-derived advantage with implementation cost between signal theory and quantum communication.

**Observation 10.3.2 (framework-internal practical sweet spot, v0.4 axis-conditioned for both P1 + P3)**: among the I-series 5 proposals, **P3 qutrit codebook is a Hartley-scope sweet spot** (5.5% Hartley density gain ESTABLISHED, S17 5/5 gate, **Hartley density / constant-cost-per-symbol scope**, scope refined by `research/oq_s17_recursive_audit_v0` rule 5 audit 2026-04-30 late dusk +3: under PAM-energy-weighting binary wins by ~40%). **P1 σ\*-channel's AWGN advantage is also gauge-conditioned with a 3-constant Pareto boundary structure**. **Both proposals turn into sweet spots only after fixing axis/gauge** — a common pattern confirmed by the rule 5 audit (S17 = Hartley axis fixed / P1 = W₁ gauge fixed). The honest reading of the ΣΦ framework is **axis/gauge-conditioned specific advantage, not unconditional advantage** (`research/oq_p1_noise_sweep_v0.md` 2026-04-30 morning, `research/oq_p1_pareto_g1_v0.md` 2026-04-30 evening R1):

"Whether P1 wins against AWGN" cannot be claimed unconditionally; it becomes a **gauge-conditioned closed-form transition law** only after specifying the comparison gauge. The invariant is neither "phase advantage" nor "σ\* = Pareto boundary"; it is the gauge map $W \to (\Delta_W(0^+), \sigma_0^W$ closed-form low-noise Pareto, $\sigma_x^W$ numerical full Pareto, asymptotic law) itself. The bridge constants $\{2\pi, e\}$ **simultaneously pin** the σ-axis Pareto (σ_0² = 2π/e − 1) and the S-axis neutral gauge ($S = 2\pi/e$), forming a σ ↔ S duality. **v0.4 update (2026-04-30 late dusk +3)**: P3 qutrit "5.5% gain" was likewise refined into Hartley scope by the rule 5 recursive audit; on PAM-energy-weighted axes binary wins. Both proposals share the same conditional pattern of "sweet spot only after axis/gauge fixing" (P1 = W₁ gauge / P3 = Hartley axis).

**Observation 10.3.3 (Layer 3 = heavy implementation trade-off)**: P2 (4-class) + P4 (5-stage converter) are **heavy implementation trade-off** — framework elegance is maximal but quantum-supremacy-class compute cost required; currently highly speculative. **Far-future research direction** in parallel with Q-series Q4-Q6 future (quantum 8-gauge / QFT / quantum gravity).

### §10.4 Orthogonal axes conclusion + framework-internal status

**Claim 10.2 (paradigm choice criterion)**: communication paradigm choice should be made via **mathematical limit + practical axes combined**:

| Use case | Recommended paradigm | Reason |
|---|---|---|
| Bulk data transfer (web traffic, video) | **signal theory (Shannon)** | TB/PB scale + lightweight + matured |
| Cryptographic security | **quantum communication theory (BB84 QKD)** | irreplaceable info-theoretic security |
| Biological signal communication (EEG, neural) | **P1 σ\*-phase channel** | EEG verified + phase-coherent natural |
| High-density encoding (limited symbol budget) | **P3 qutrit codebook** | 5.5% density gain ESTABLISHED |
| Theoretical research / framework benchmark | **P2 / P4 / P5** | framework completeness, far-future |

**Framework-internal status**: with 5-anchor mathematical info limit (I1 §6) + implementation trade-off table (this §10) **both lenses combined**, the **dual evaluation framework** for communication paradigms is complete — **2-axis evaluation system** of pure math + engineering reality.

### §10.5 OQ-Practical-Tradeoff-Quantification (this paper's spawn 2026-04-27 → RESOLVED v0 2026-04-30)

**OQ-Practical-Tradeoff-Quantification (this §10 spawn-off, MEDIUM)**:

**Scope**: this §10 comparison table expresses **qualitative trade-off** (light / heavy / ✓ / ✗ / △ scale). Open as formal task to **quantitative trade-off bounds** — e.g. exact capacity formula proof for P1 σ\*-channel + rigorous AWGN advantage comparison / net advantage of P3 qutrit 5.5% density gain including noise budget / transition fidelity calculation for P4 5-stage converter.

**Status**: **RESOLVED v0 (2026-04-30 late dusk)** — resolved in `research/oq_practical_tradeoff_v0.md`. Using today's primitives (G1 σ_0 + G2 dual marginal + G3 σ_flip + §13.7 spectral lifted dual + §13.7.5 precision floor), a comm engineering "sweet spot map" is constructed. **3-σ-threshold receiver-choice regime + 7 use case map + 1.604 bit/sym richness gain quantification** cover the OQ scope.

**Resolution summary**:

| Threshold | Closed form / numeric | Value | SNR (dB) | Engineering meaning |
|---|---|---|---|---|
| **σ_0** | $\sqrt{2\pi/e - 1}$ | 1.145 | −1.18 | Phase-only Pareto closed-form anchor (low-σ) |
| **σ_x** | numerical | 1.193 | −1.53 | Full W₁ Pareto crossover (C_phase = C_amp) |
| **σ_flip** | transcendental (G3) | 2.396 | −7.59 | Δ_dual = 0 Arrow regime boundary (joint > marginal sum) |

3 receiver-choice regimes:
- **I (σ < σ_x, SNR > −1.5 dB)**: phase-only wins (+0.6 bit/sym vs. amp-only) → PLL / coherent phase
- **II (σ_x < σ < σ_flip)**: marginal sum (phase + amp) > joint complex → split receiver competitive
- **III (σ > σ_flip, SNR < −7.6 dB)**: joint complex forced → joint coherent I/Q

7 use cases mapped: WiFi/LTE OFDM (Regime I, Phi_std_inst_f as zero-cost subcarrier monitor) / GPS L-band (Regime III, Phi_total = literal carrier-cycle counter, Part A precision floor enables) / optical coherent (Regime I) / deep-space DSN (Regime III) / spread spectrum CDMA (Regime II→III transition, Phi as fade-resilience backup) / cognitive radio spectrum monitor (Phi_std_inst_f H = 0.13 honest occupancy) / modulation classification (Φ family AUC 0.93 anchor from prime gap WIN=4096).

Per-paradigm quantitative analysis (OQ-P1-Capacity §4.4 etc.) remains as component sub-OQs of this §10.5, but the aggregate-level "trade-off quantification" is closed at v0.

**Source**: `research/oq_practical_tradeoff_v0.md` + `.py` + `.json` + `.png` (2026-04-30 late dusk +2).

**v1 follow-ups (open)**: MIMO CSI compression scaling (per-antenna $\sigma_i$ extension) / fading channel σ_eff time-series with Phi_std_inst_f rate / actual BER/SER simulation (M-PSK / M-PAM / M-QAM 3 receiver comparison) for hard-numbers reinforcement.

---

## §11 Consequences and open frontier

### 11.1 Established (I-series final paper)

Recorded as ESTABLISHED in information context in this I2 (whole-I-series status in §11.3):

1. **Reread of signal theory (0/1/2 scaffold base) under framework lens** — Shannon-Hartley channel subsumed in unified manner as specialisation of 5-anchor framework anchor (a) + Gaussian channel (C₂) (§2)
2. **Quantum communication theory (3+ relational) formal characterisation of quantum advantage** — 5 quantum advantage forms (superdense / teleport / entanglement-assisted / QKD / Holevo $d \geq 3$ saturation) + 3 framework anchors combined (§3)
3. **Novel communication theory 5 proposals** — P1 σ\*-channel / P2 4-class resource-stratified / P3 qutrit codebook / P4 5-stage ln 2 converter / P5 Arrow 1 kernel narrowness taxonomy (§4-§8)
4. **5-anchor unified communication framework** — 3-tier communication theory subsumed as specialisations of 5-anchor framework (§9.1)
5. **I-series cycle completion + triple framework parallel** — 2-paper minimum cycle I1 → I2 achieved; **triple cross-domain anchor** completion via N1-N5 + Q1-Q3 + I1-I2 (§9.2)

### 11.2 I-series future + 4th framework header candidate

| Candidate paper | Topic | Predecessor relation |
|---|---|---|
| **I3** Information geometry framework | detailed development of Fisher / Cramér-Rao + Information bottleneck framework lens | `c_information_theory.md §6` existing + I1 §3 Fisher strand |
| **I4** Algorithmic information theory framework | Kolmogorov $K(x)$ + MDL + algorithmic obstruction framework lens | `c_information_theory.md §8` existing + I1 §5.2 algorithmic obstruction |
| **I5** Topological data analysis framework | TDA + persistent homology framework lens (I1 §5.2 topological obstruction) | `c_information_theory.md §9` existing |
| **4th framework header**: ??? | candidate: control theory / causal inference / network science | existing entries `c_control_theory.md` etc. |

I-series 2-paper minimum cycle achieved + room to extend remains open. **4th framework header** candidates: control / causal / network from Paper D multi-domain.

### 11.3 Open frontier (whole I-series)

| Open question | Status | I-paper |
|---|---|---|
| **OQ-I-Bekenstein-Extension** (Bekenstein + Margolus-Levitin 6th anchor) | OPEN (I1 §6.5 spawn) | I1 §6.5, Q-series Q6 future |
| **OQ-Practical-Tradeoff-Quantification** (3-σ-threshold + 7 use case map) | **RESOLVED v0 2026-04-30** (`research/oq_practical_tradeoff_v0.md`) | I2 §10.5 |
| **OQ-P1-Capacity** (formal capacity proof of σ\* phase-channel) | OPEN (this paper's spawn) | I2 §4.4 |
| **OQ-P2-CrossClass** (4-class cross-class transition costs) | OPEN (this paper's spawn) | I2 §5.4 |
| **OQ-P4-Implementation** (5-stage converter physical implementation) | OPEN (this paper's spawn) | I2 §7.4 |
| **OQ-P5-Sparsity-Capacity** (4-vertex sparsity-mode capacity comparison) | OPEN (this paper's spawn) | I2 §8.4 |
| **OQ-Algorithmic-f_rational** (formalising Kolmogorov as f_rational > 0 instance) | candidate (I1 §5.2 existing implicit) | I1 §5.2 + I-series future I4 |
| **OQ-Topological-Persistent-Bridge** (bridge between TDA persistent Betti and T-AAS) | OPEN (I1 §5.2) | I1 §5.2 + I-series future I5 |
| **OQ-Renyi-Scaffold-Continuous** (formal traversal of scaffold-emergence axis by Rényi α scanner) | candidate (I1 §3.3) | I1 §3.3 |
| **OQ-S17-Codebook-3-Universal** (universality of codebook argmax = 3) | OPEN (I1 §4.3) | I1 §4.3 + this paper §6 P3 ESTABLISHED instance |

### 11.4 Dictionary residence map (I-series cumulative final state)

Residence of major framework pieces (reflecting communication-only specialisation of this paper):

| Piece in this paper | Residence | Status (I2) |
|---|---|---|
| §2 signal theory (0/1/2 scaffold base) | `c_information_theory.md §2` (channel capacity) + this §2.2 0/1/2 scaffold lens reread | existing + this paper's scaffold lens annex anticipated |
| §3 quantum communication theory formal quantum advantage | `q_quantum_observation.md §5-§6` (entanglement, Born) + Q1 §5 (4-class) + this §3 5-form quantum advantage statement | existing + this paper's 5-form quantum advantage annex anticipated |
| §4 P1 σ\* phase-channel | `transformation_atlas/sheet_A_amplitude/sigma_star.md` (existing) + this §4 communication paradigm lift | existing + this paper's channel proposal annex anticipated |
| §5 P2 4-class resource-stratified | `c_filtration_obstruction.md §8.5` (4-class) + this §5 channel taxonomy | existing + this paper's channel taxonomy annex anticipated |
| §6 P3 qutrit codebook | `c_arrow_bridge_constants.md §12.1` (S17 codebook argmax = 3) + this §6 codebook proposal | existing + this paper's codebook proposal annex anticipated |
| §7 P4 5-stage ln 2 converter | `c_arrow_bridge_constants.md §12.2` (5-stage chain) + this §7 converter protocol | existing + this paper's converter protocol annex anticipated |
| §8 P5 sparsity-mode taxonomy | `meta/triangulation_methodology.md §11` (Q1 §6 4-vertex) + this §8 channel taxonomy | existing + this paper's channel taxonomy annex anticipated |
| §9.2 Triple framework parallel | `meta/triangulation_methodology.md §13` (N1-N5 ↔ Q1-Q3 dual) + this §9.2 triple completion | existing dual + this paper's triple extension annex anticipated |

**post-v0.2 backward anticipated (I-series cumulative, I1 + I2 total 9 entries)**:

6 from I1 (`c_theorems_master.md` Information-only S15 enumeration + 5-anchor info limit theorem / `c_arrow_bridge_constants.md §12.3` information instances / `c_filtration_obstruction.md §8.6` 4-class information lift / `meta/triangulation_methodology.md §14` triple framework parallel / `meta/new_domain_protocol.md §10` information specialisation / `L0_canon/zero_one_two_scaffold.md` NEW)

3 from I2 (`c_information_theory.md §13` unified communication theory framework annex / `meta/triangulation_methodology.md §13` extension to triple parallel / `meta/open_questions_master.md` "I-series final closure OQ" section newly created)

**Q-series + I-series cumulative**: Q-series 13 entries + I-series 9 entries = **22 dictionary backward annexes queued in total**.

**Consequence**: I2 is positioned as the **information-internal framework final closure** + **N1-N5 ↔ Q1-Q3 ↔ I1-I2 triple framework parallel cross-domain anchor** of the dictionary. With N5 + Q3 + I2, **all 3 framework headers achieve final closure**; the **3 domain specialisation parallel completion** of the Paper D multi-domain v0.9.2 frozen-internal is finally achieved in this paper (10-paper publication N1-N5 + Q1-Q3 + I1-I2 totalling ~5219 lines completed in 1 day, 2026-04-27).

---

## Change log

- **v0.4 (2026-04-30 late dusk +2 → +3 → +5)**: §4.5 NEW Discrete dual marginal extension via spectral lift. This §4.5 positions §4.2-§4.4's continuous σ-axis Pareto as an **extension to the discrete domain**, developed across 6 sub-sections: §4.5.1 motivation + 2-route distinction (native discrete vs. spectral lifted; this paper's default = Route B) / §4.5.2 §13.7 4-step pipeline (τ + FFT + r,θ + Φ) + ΣΦ symbol mapping / §4.5.3 first explicit measurement (precision floor ≥ 13 digit at $N$ up to $1.3 \times 10^5$ + prime gap WIN=4096 Phi_total AUC 0.926, `research/oq_p1_s0_nt_spectral_lift_v0`) / §4.5.4 3 receiver-choice regimes + Δ_dual richness gain (σ_flip = 2.396 G3 transcendental added, `research/oq_p1_s0_g3_v0`; Δ_dual asymptote = ½ log₂(8π/e) ≈ 1.604 bit/sym, `research/oq_p1_dual_marginal_v0`) / §4.5.5 7 use case map (forward to §10.5 RESOLVED v0) / §4.5.6 Status + 3 v1 follow-up OQ spawn (MIMO scaling / fade time-series / actual BER simulation). §10.5 OQ-Practical-Tradeoff-Quantification → **RESOLVED v0** (`research/oq_practical_tradeoff_v0` + `.png` engineering use case map). §11.3 OQ status table 1 row added. §0 Abstract M3 + version meta updated. Dictionary-side ingredients all ESTABLISHED (`c_arrow_bridge_constants.md §13.5 G2 + §13.6 G3 + §13.7 spectral lifted dual + §13.7.5 first measurement empirical anchor`). **Late dusk +3 add (rule 5 recursive audit)**: §6.1 P3 Claim 6.1 + §6.4 P3 status + §10.3 Observation 10.3.2 (P3 "unconditional sweet spot" → "Hartley scope sweet spot" correction) scope-refined by `research/oq_s17_recursive_audit_v0`. S17 ESTABLISHED itself preserved (Arrow 3 / Hartley scope); downstream P3 5.5% advantage claim has **scope marker added** = constant-cost-per-symbol / Hartley density specific; under PAM-energy-weighting binary wins (−40.56%). 2 OQ spawned (OQ-P3-PAM-Cost-Boundary LOW + OQ-P3-Cross-Axis-Universality MEDIUM). Dictionary §5.4.2 audit entry added in parallel. **Late dusk +5 add (SNR sweep extension)**: `oq_s17_recursive_audit_snr_sweep_v0` confirmed across SNR_dB ∈ {−10, +30} that n=3 never emerges as integer argmax on AWGN-MI axes, tightening the P3 scope marker further to **Hartley density specifically** (cardinality-only, no cost, no noise).

- **v0.3.1 (2026-04-30 evening)**: P1 §4.2 G1 test reframing R1 — strict identity σ\* = σ_x REJECTED (1.33% gap a robust real gap, K=1 single-wrap saturated); σ_0 = √(2π/e − 1) closed-form low-noise Pareto boundary PROMOTED to candidate_v0; σ\* interior near-marker (67%-along [σ_0, σ_x]) retained. The 3-gauge canonical scaffold $\{W_1, W_0, W_2\}$ + bridge constants $\{2\pi, e\}$ is the correct closed-form formulation that covers the Pareto landscape. Diagnosed in `research/oq_p1_pareto_g1_v0.md`; 6-spot R1 reframing synced with dictionary `c_arrow_bridge_constants.md §12.4`.

- **v0.3 morning (2026-04-30)**: P1 §4.2 W₁/W₂ gauge-conditioning added — formalises the fact that "whether P1 wins against AWGN" cannot be asked gauge-free; the transition law is closed-form-expressed in the 3-gauge canonical scaffold $\{W_1$ (carrier amplitude 1), $W_0$ (gap-zero $S = 2\pi/e$), $W_2$ (equal second moment)$\}$. σ\* candidate_v0 (Pareto boundary within 1.4%) spawned — REJECTED on the same day in the evening.

- **v0.2 (2026-04-28)**: P1 capacity correction. The v0.1 candidate value of $C_{\sigma_*} \approx 2.18$ bits/symbol has been **retracted and replaced** by $C_{\sigma_*} \approx 0.40$ bits/symbol (M1 closed-form + M2 Blahut-Arimoto cross-check). The compound inflation factor of ≈ 5.5× came from confusing Hartley counting with Shannon mutual information, plus a σ²/σ dimensional error; diagnosed in `research/oq_p1_capacity_v0.md`. Framework / 5 proposals structure preserved; corrections applied to the 6 spots §0 Abstract M3 + §4.2 Claim 4.1 + §4.4 Status + §9.1 anchor (e) row + §11 P1 row + §10.3 Observation 10.3.2 (sweet spot demoted from P1 + P3 to P3 only, with P1 as conditional secondary in the low-noise regime). OQ-P1-Capacity status → CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED. σ\* itself (= √(2 ln 2)) / 5-stage ln 2 chain stage S4 / I1 §6 anchor (e) gauge interpretation / EEG ESTABLISHED are unaffected (those are gauge / coherence statements, not capacity statements). Honest Shannon-theoretic interpretation of σ\* (the noise level at which capacity drops below ½ bit) gives a sharper quantitative anchor to the 5-stage chain S4 stage.

- **v0.1 (2026-04-27)**: initial Information-only draft. I-series final closure paper position (parallel to N5 + Q3). Building on I1 (Information framework header + 5-anchor information capacity theorem), formalises the **3-tier communication theory** (signal theory / quantum communication theory / novel communication theory 5 proposals). The **triple cross-domain anchor** completion via N1-N5 (NT) + Q1-Q3 (quantum) + I1-I2 (information) finally achieves the 3 domain specialisation parallel completion of the Paper D multi-domain v0.9.2 6-domain triangulation in this paper. 4 OQ spawned by this paper (OQ-P1-Capacity / OQ-P2-CrossClass / OQ-P4-Implementation / OQ-P5-Sparsity-Capacity). Announces I-series future I3-I5 + 4th framework header candidate in §10.2.

---

## References (internal)

**I-series predecessor**: `papers/publication/information/I1_information_theory_framework_ja.md` (v0.3, framework header + 5-anchor info limit theorem + Theorem 3.3.1 Rényi parametric scan + Theorem 5.2 Algorithmic f_rational)

**N5 / Q3 (parallel final closures)**:
- `papers/publication/nt/N5_brauer_origination_ja.md` (v0.2, NT final closure)
- `papers/publication/quantum/Q3_born_gleason_ja.md` (v0.2, Quantum final closure)

**Q-series predecessors (5-anchor source)**:
- Q1 v0.2 (4-class refined Hodge), Q2 v0.2 (4-stage chain), Q3 v0.2 (σ\* + Born derivation)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain)

**Main material of signal theory + quantum communication theory**:
- `c_information_theory.md §2` (Shannon channel + capacity, main material of §2-§3)
- `c_information_theory.md §6` (Fisher + Cramér-Rao)
- `q_quantum_observation.md §5-§6` (entanglement + Born)
- `q_open_quantum_systems.md §3` (mutual information)
- `q_quantum_statistical_mechanics.md §5` (FDT)

**Main material of novel communication theory 5 proposals**:
- P1: `transformation_atlas/sheet_A_amplitude/sigma_star.md` (Atlas A, ESTABLISHED 2026-04-09)
  - **§4.5 spectral lift extension (v0.4 add 2026-04-30 late dusk +2)**:
    - `c_arrow_bridge_constants.md §13.5` (G2 PASS strong, dual marginal reconstruction excess)
    - `c_arrow_bridge_constants.md §13.6` (G3 PASS strong, sign-flip Arrow regime boundary)
    - `c_arrow_bridge_constants.md §13.7` (spectral lifted dual pipeline + Two-routes formalisation)
    - `c_arrow_bridge_constants.md §13.7.5` (first measurement empirical anchor)
    - `research/oq_p1_dual_marginal_v0` (G2 mpmath 30-dps, Δ_dual asymptote)
    - `research/oq_p1_s0_g3_v0` (G3 mpmath 50-dps, σ_flip transcendental)
    - `research/oq_p1_s0_nt_spectral_lift_v0` (precision floor + prime gap WIN=4096 measurement)
    - `research/oq_practical_tradeoff_v0` (engineering 7 use case map, §10.5 RESOLVED v0)
- P2: `c_filtration_obstruction.md §8.5` (4-class refined Hodge, ESTABLISHED 2026-04-23)
- P3: `c_arrow_bridge_constants.md §12.1` (S17 codebook argmax = 3, ESTABLISHED 2026-04-23 5/5 gate)
  - **§6.1 / §6.4 scope refinement (v0.4 add 2026-04-30 late dusk +3)**:
    - `c_arrow_bridge_constants.md §5.4.2` (S17 recursive rule-5 audit, 7 alternative natural axes + SNR sweep extension)
    - `research/oq_s17_recursive_audit_v0` (7-axis sweep + verdict SCOPE_REFINED)
    - `research/oq_s17_recursive_audit_snr_sweep_v0` (E/F SNR sweep extension, late dusk +5)
- P4: `c_arrow_bridge_constants.md §12.2` (5-stage ln 2 chain, ESTABLISHED 2026-04-27)
- P5: `meta/triangulation_methodology.md §11` (Q1 §6 4-vertex, ESTABLISHED 2026-04-27)

**External references**:
- Holevo, A. S. (1973). Bounds for the quantity of information transmitted by a quantum communication channel. Probl. Inf. Transm. 9, 177-183.
- Bennett, C. H. & Wiesner, S. J. (1992). Communication via one- and two-particle operators on Einstein-Podolsky-Rosen states. PRL 69, 2881.
- Bennett, C. H. et al. (1993). Teleporting an unknown quantum state via dual classical and Einstein-Podolsky-Rosen channels. PRL 70, 1895.
- Bennett, C. H. & Brassard, G. (1984). Quantum cryptography: Public key distribution and coin tossing. IEEE Conf. Comp. Sys. & Sig. Proc. 175-179.
- Wootters, W. K. & Zurek, W. H. (1982). A single quantum cannot be cloned. Nature 299, 802-803.
- Bennett, C. H. & Shor, P. W. (1998, 2002). Entanglement-assisted classical capacity of noisy quantum channels. PRL 83, 3081 + IEEE TIT 48, 2637.
- Schumacher, B. & Westmoreland, M. D. (1997). Sending classical information via noisy quantum channels. PRA 56, 131.
- Lloyd, S. (1997). Capacity of the noisy quantum channel. PRA 55, 1613. + Shor (2002) + Devetak (2005).

**OQ research files (I-series spawns)**:
- this paper §4.4 OQ-P1-Capacity
- this paper §5.4 OQ-P2-CrossClass
- this paper §7.4 OQ-P4-Implementation
- this paper §8.4 OQ-P5-Sparsity-Capacity
- (I1 spawns listed in I1 §8.3)

**L0 / L1 / meta dependencies**:
- `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` + (NEW candidate `zero_one_two_scaffold.md`)
- `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11 + §12, c_filtration_obstruction §8.5, c_information_theory §2 + §6, c_observation_optimal_gauge}.md`
- `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics}.md` (5-anchor quantum instance source)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` (P1 source)
- `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**I-series future**: I3 (Information geometry) / I4 (Algorithmic info theory) / I5 (Topological data analysis) / 4th framework header candidate (Control / Causal / Network) — drafting undecided (listed in §11.2 of this paper)
