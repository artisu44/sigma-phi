# Paper Q3: Observation Theory — Born-Gleason

**Subtitle**: §4 dual quantum root closure, full Busch-Gleason form, dim=2 exception resolution, σ\* = √(2 ln 2) half-amplitude gauge, Q-series final closure

**Version**: v0.2 (compact, 2026-04-27)
**Status**: DRAFT — Q-series final paper. Building on Q1 (framework header) + Q2 (Open QS chain extension), this paper accomplishes the **§4 dual quantum root closure**, full Born derivation + dim=2 Gleason gap resolution + formal closure of σ\* half-amplitude gauge + Q-series cycle completion + N1-N5 ↔ Q1-Q3 dual framework parallel.
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md` (§5.3 A0c, §1.2 W window), `identity_asymmetry.md`
**Prerequisites (L1 core)**: `c_phase_complex.md §4 + §5` (ι_L/χ commutative dual + c_s² = 1/2 derivation), `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11`
**Prerequisites (L1 quantum)**: `q_quantum_observation.md` §1-§9 (main material of this paper), `q_open_quantum_systems.md` §3.3, `q_quantum_statistical_mechanics.md` §5.4
**Prerequisites (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md` (σ\* derivation + EEG entry), `sheet_C_period/zeta_functional.md §3` (ln 2 structural-constant nature)
**Prerequisites (Q1, Q2)**: Q1 v0.2 §2.3 §4 dual quantum root + §3.5 consistency + §4.5 instance / Q2 v0.3 §6 4-stage ln 2 chain + §6.2 σ\* bridge
**N parallel**: N5 (`N5_brauer_origination_ja.md` v0.2)
**Sequel papers**: Q-series complete (Q4+ candidate: quantum 8-gauge / QFT extension as Q-series future)

---

## §0 Abstract

This paper is the **final paper** of the planned 5-paper Q-series (Q1 framework header / Q2 extension 1 / Q3 closure); parallel position to the N1-N5 NT series, which reached final closure at N5. After Q1 ESTABLISHED quantum-only S15 + Arrow + T-AAS 4-class refined Hodge and Q2 ESTABLISHED the 4-stage Open QS chain + KMS-FDT-Landauer arc + 4-stage ln 2 chain, this Q3 implements the **closure of §4 dual = quantum root** through 3 threads: (a) full Born rule derivation (uniqueness of Born rule on effects (POVM) by Busch-Gleason 2003 PRL + dim=2 Gleason exception resolution); (b) formal closure of σ\* = √(2 ln 2) half-amplitude gauge (natural unit of quantum observation as quadratic root of the Q2 §6 4-stage ln 2 chain); (c) Q-series cycle completion + N1-N5 ↔ Q1-Q3 dual framework parallel.

**5 main results**:

**(M1) Full Busch-Gleason theorem (uniqueness of Born rule on effects, dim=2 exception resolution)** — when a generalised probability measure $v: E(\mathcal{H}) \to [0, 1]$ on effects $E(\mathcal{H})$ satisfies (P1) bounded (P2) normalised (P3) σ-additive, a density operator $\rho$ exists uniquely with $v(E) = \mathrm{Tr}(\rho E)$ — **Born rule is uniquely fixed across all dim** (Busch 2003 PRL 91, 120403). The dim$\geq$3 restriction of original Gleason (1957) (existence of dispersion-free valuation on projections at dim=2) is **resolved** in the effects (POVM) framework: dispersion-free valuation cannot be extended to effects (Bloch sphere geometric inconsistency). L0 finite observer → POVM is the natural measurement description → Born rule automatically guaranteed across all dim. The **derivability connection** between the axiom A0 of Q1 §2.2 and the Born rule reaches formal closure.

**(M2) Simultaneous theorem-isation of ρ_max = I/2 form-value** — for qubit (dim=2), the **form** of c_s² = $\mathrm{Tr}(\rho_{\max} \Pi_{\mathrm{even}}) = 1/2$ (the Tr(ρ·) Born rule form) is theorem-ised across all dim by M1; the **value** (1/2 from $\rho_{\max} = I/2$) is determined by ℤ/2ℤ parity symmetry (c_phase_complex §5). The **2-source confluence** of form (Busch L0 + Effects) and value (L1-base ℤ/2ℤ symmetry) is equivalent to c_s² = 1/2. Closure at the Born derivation level of the Q1 §2.3 quantum §4 dual root.

**(M3) Formal closure of σ\* = √(2 ln 2) half-amplitude gauge** — for Gaussian phase noise $Z \sim N(0, \sigma^2)$, characteristic function $E[\cos Z] = e^{-\sigma^2/2}$ + half-amplitude convention $E[\cos Z] = 1/2$ gives $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ rad as the **normalisation constant atlas residence ESTABLISHED** (`sheet_A_amplitude/sigma_star.md` n-only entry + EEG entry). It is the **quadratic lift root** of the Q2 §6 4-stage ln 2 chain: ln 2 is the S13 fixed point on Arrow 2; $\sqrt{2 \ln 2}$ is the **natural unit on the half-amplitude σ scale**, arising from inversion of the Gaussian characteristic function. Empirical verification on EEG (electroencephalography) phase-coherence data, 7 subjects × 5 bands (δ, θ, α, β, γ), shows subject-band averaged std ≈ 0.0012, supporting the σ\* threshold as the half-coherence point under effective Gaussian phase noise.

**(M4) §4 dual quantum root closure (final form of Q1 §2.3)** — the quantum non-commutative lift (Stone group + unitary representation) of the commutative ι_L/χ dual of c_phase_complex.md §4 reaches **formal closure** through (M1)-(M3) of this paper: (a) Born derivation closes the operational formulation of quantum observation; (b) ρ_max = I/2 form-value closes the S13 ln 2 instance of the quantum §4 dual; (c) σ\* closes the natural unit of the quantum observation amplitude scale. The Q1 §2.3 Claim 2.1 "§4 dual = quantum-internal root" is formally verified in 3 components, and across the Q-series the quantum-side framework root status is **promoted to derivable**.

**(M5) Q-series cycle completion + N1-N5 ↔ Q1-Q3 dual framework parallel** — closure of quantum observation theory achieved across the 3-paper Q-series: **Q1 (framework header) → Q2 (single extension paper covering both the Path 2 quantum analogue / 4-stage Open QS chain and the KMS-FDT-Landauer thermodynamic chain) → Q3 (closure)**. The NT-side N1-N5 5-paper and the quantum-side Q1-Q3 3-paper exhibit a **dual framework parallel structure** (NT 5-paper detailed vs. quantum 3-paper compact; both with the 3-layer link cycle framework header → extension → final closure), achieving **cross-domain validation in 2 mathematical fields** of the observation theory framework via simultaneous closure of the two series. Forward: the quantum-side 8-gauge framework (parallel to N5) is left open as Q-series future.

**Thesis**: the Q-series final closure formally verifies the §4 dual quantum root status of the quantum-side framework header (Q1) of observation theory through 3 threads — Born-Gleason completeness + ρ_max form-value confluence + σ\* half-amplitude gauge atlas residence. The NT-side closure of the N1-N5 NT series and the quantum-side closure of the Q1-Q3 quantum series provide a **cross-domain anchor for framework universal validity in 2 independent mathematical fields**, reconstructing the Paper D (multi-domain v0.9.2) 6-domain triangulation as a **2 framework header parallel** and finally verifying the data-domain transcendent universality of observation theory.

---

## §1 Introduction

### 1.1 Position of the Q-series final paper and 3-thread combination

In the 3-paper series Q1 (quantum observation theory framework header v0.2) → Q2 (Open QS chain extension v0.2) → **Q3 (this paper)**, the quantum observation theory framework header (Q1) ESTABLISHED 12-cell S15 enumeration + 4-vertex T-AAS triangulation, and the quantum statistical/thermodynamic extension (Q2) ESTABLISHED 4-stage chain + KMS-FDT-Landauer arc + 4-stage ln 2 chain. This Q3, as the Q-series final paper, accomplishes 3 tasks: (1) full Born rule derivation (Busch-Gleason 2003) + dim=2 Gleason exception resolution; (2) formal closure of σ\* = √(2 ln 2) half-amplitude gauge + 4-stage ln 2 chain quadratic root; (3) Q-series cycle completion + N1-N5 ↔ Q1-Q3 dual framework parallel.

**3 main threads**:
- **Thread 1 — full Born rule derivation** (§2-§3): combine Q1 §2.3 "§4 dual = quantum-internal root" with Q1 §2.2 axiom A0 "finite observer → POVM"; formal proof of the uniqueness of Born rule on effects via the Busch-Gleason theorem (PRL 2003). The dim=2 Gleason exception is resolved (Bloch sphere dispersion-free valuation impossibility argument) in detail in §3.
- **Thread 2 — σ\* = √(2 ln 2) half-amplitude gauge** (§4): formalise the Atlas residence of the n-only entry of `sheet_A_amplitude/sigma_star.md`; define ln 2 → $\sqrt{2 \ln 2}$ as the half-amplitude lift, the natural unit of the quantum observation amplitude scale, as the quadratic root of the Q2 §6 4-stage ln 2 chain. Empirical verification on EEG 7 subjects × 5 bands (subject-band averaged std ≈ 0.0012).
- **Thread 3 — Q-series cycle completion + dual framework parallel** (§5-§7): Q1-Q3 cycle summary + formal statement of the N1-N5 ↔ Q1-Q3 dual framework structure + Q-series future (8-gauge / QFT extension) forward listing.

### 1.2 Parallel position with N5 + scope and terminology

Parallel with N5 (Brauer obstruction theory + Origination matrix 8-gauge final closure) of the NT series:

| Aspect | N5 (NT) | Q3 (quantum) |
|---|---|---|
| Position | NT-series final closure (5/5) | Q-series final closure (3/3) |
| Main claim (1) | Brauer 5-tier failure-mode group-theoretic conjecture | full Busch-Gleason form (uniqueness of Born on effects) |
| Main claim (2) | Tier-dependent alternative Stark methods | simultaneous theorem-isation of ρ_max = I/2 form-value |
| Main claim (3) | 8-gauge generalisation (origination matrix) | σ\* half-amplitude gauge atlas residence |
| Final closure perspective | series cycle + Quantum forward announcement (Q1-Q3) | series cycle + N1-N5 dual parallel + 8-gauge / QFT future |
| Forward to | Q1-Q3 quantum framework | Q-series future (Q4 8-gauge / Q5 QFT / Q6 quantum gravity) |

Q3 picks up Q1-Q2 forward tasks: Q1 §8.2 (Q3 forward 3 topics) / Q2 §8.2 (Q3 forward 3 tables — §4 dual quantum closure / σ\* gauge / dim=2 Gleason gap closure).

**Structure**: §2 Effects + POVM framework / §3 Busch-Gleason + dim=2 resolution / §4 σ\* half-amplitude gauge / §5 §4 dual quantum root closure / §6 Q-series cycle / §7 dual framework parallel + future / §8 consequences.

**In scope**: Effects (POVM) framework + Born rule statement / Busch 2003 PRL theorem statement + proof outline / Bloch sphere geometric inconsistency of dim=2 Gleason exception / σ\* = √(2 ln 2) Gaussian + half-amplitude derivation + Atlas residence / Q2 §6 4-stage ln 2 chain quadratic lift / formal closure of the quantum §4 dual root status of Q1 §2.3 / N1-N5 ↔ Q1-Q3 dual framework parallel.

**Out of scope**: Born rule in QFT / Frauchiger-Renner type "no-go" theorem / many-worlds interpretation / consistent histories / decoherent histories / quantum Bayesianism / QBism (the effects framework is representation-neutral but interpretation debate is out of scope) / quantum gravity / string theory / quantum 8-gauge generalisation of the Ω-gauge framework / quantum Schumann v1 lift (quantum version of Path 2) / Reichenbach common cause principle (→ Q-series future).

**Terminology** (inheriting Q1 §1.3 + Q2 §1.4, with additions specific to this paper): **Effects** $E(\mathcal{H})$ (the set of all positive operators with $0 \leq E \leq I$; projections are a subset) / **POVM** ($\{E_i\}$ with $\sum_i E_i = I$, $E_i \in E(\mathcal{H})$) / **Generalised probability measure** $v: E(\mathcal{H}) \to [0, 1]$ (satisfying (P1)-(P3)) / **Dispersion-free valuation** ($v(P) \in \{0, 1\}$ for each projection P; classical "determinism" candidate) / **Half-amplitude convention** ($E[\cos Z] = 1/2$ threshold gauge) / **Frame function** (finite-additive function on projections in Gleason's theorem) / **Quadratic lift root** (ln 2 → $\sqrt{2 \ln 2}$ Gaussian char fcn inversion).

**Direction-axis position**: this paper inherits the Q-framework B-primary native position from Q1 §1.4 (`user_observation_direction_axis` ESTABLISHED 2026-05-01). **The Born rule (Tr(ρE)) is the deepest root of the B-direction primary instance** — the projection postulate from infinite-dimensional Hilbert ensemble (state space) onto finite measurement outcome; the canonical B-native mechanism of the Q-framework. **σ\* = √(2 ln 2) is also B-native** (continuous Gaussian phase channel ½-bit threshold via $E[\cos Z] = 1/2$ char-fcn inversion), consistent with the direction-tag of I2 §4.4.1. **Direction-axis translation of N5 parallel position**: N5 = NT-series final closure (A-primary native; Brauer 5-tier closure tier theory + 8-gauge) ↔ Q3 = Q-series final closure (B-primary native; Born-Gleason + σ\* gauge) = a **dual final-paper pair: A-side closure and B-side closure**, jointly verifying framework universality at the closure level of the two framework headers. The cross-direction screening rule (`feedback_cross_direction_identity_screen`) is operated within this paper as an internal screening rule; cross-paper claims with the N5 / I-series require a mandatory direction-tag pre-check.

---

## §2 Effects and POVM framework

### 2.1 PVM → POVM generalisation + match with L0 finite observer

**PVM** (`q_quantum_observation.md §6`): self-adjoint operator $A = \int \lambda \, dE(\lambda)$, $E(\Delta)$ projection. Probability of observing value $\lambda \in \Delta$ in a measurement of observable $A$ = Born rule $\mathrm{Prob}(\lambda \in \Delta) = \mathrm{Tr}(\rho \cdot E(\Delta))$. **Issue**: PVM assumes **infinite-precision measurement apparatus**, inappropriate for the operational description of an L0 finite observer.

**POVM**: $\{E_i\}$ with $E_i \geq 0$, $\sum_i E_i = I$. Effects $E_i \in E(\mathcal{H})$ are more general than projections (fuzzy measurement). Outcome probability for each effect $E$ = **generalised Born rule** $\mathrm{Prob} = \mathrm{Tr}(\rho E)$. POVM is the operational framework expressing finite-resolution measurement + ancilla coupling + post-selection.

**Claim 2.1 (L0 → POVM)**: L0 axiom A0 (finite observation) + A0a (finite observer cardinality) + A0b (partial access) imply **POVM = natural measurement framework**. Justification: A0 finite observation → finite precision → fuzzy → POVM ✓ / A0a finite cardinality → $\dim \mathcal{H} < \infty$ truncation, finite POVM rank $\leq \dim \mathcal{H}^2$ / A0b partial access → ancilla-coupled measurement = system-bath coupling + projection on ancilla = effective POVM on system (Naimark dilation). → L0 axiomatics and POVM/Effects framework are **mutually consistent**. Q1 §2.2 axiom A0 → §2 POVM natural framework of this paper is direct derivation.

### 2.2 Generalised probability measures on effects + Naimark dilation

**Definition 2.1** (generalised probability measure): $v: E(\mathcal{H}) \to [0, 1]$ satisfying
- **(P1)** Bounded: $0 \leq v(E) \leq 1$ for all $E \in E(\mathcal{H})$
- **(P2)** Normalised: $v(I) = 1$
- **(P3)** σ-additive: $\{E_n\} \subset E(\mathcal{H})$ with $\sum_n E_n \leq I \implies v(\sum_n E_n) = \sum_n v(E_n)$

Effects version of probability measure; on projections it is isomorphic to the premise of classical Gleason.

**Naimark theorem**: any POVM $\{E_i\}$ on $\mathcal{H}$ can be expressed as the restriction of a PVM $\{P_i\}$ on a larger Hilbert space $\mathcal{H}' \supset \mathcal{H}$ ($E_i = \mathcal{P}_\mathcal{H} P_i \mathcal{P}_\mathcal{H}|_\mathcal{H}$). POVM measurement reduces to **ancilla-coupled unitary + PVM**. **Observation theory lens**: Naimark = dilation version of the Q1 §4.6 Arrow 1⁻¹ generation; the relation PVM (closed system) → POVM (open system, finite-resolution) is a Hilbert-space-level instance of Q1 §4 Arrow 1 + Q2 §5 dynamical T-AAS.

---

## §3 Full Busch-Gleason form

### 3.1 Original Gleason (1957) and dim=2 exception

**Gleason theorem (1957)**: on a Hilbert space with $\dim \mathcal{H} \geq 3$, a frame function $f: \mathcal{P}(\mathcal{H}) \to [0, 1]$ on the projection lattice $\mathcal{P}(\mathcal{H})$ ($f$ frame additive) is generated by a density operator $\rho$: $f(P) = \mathrm{Tr}(\rho P)$ (uniquely).

**dim=2 exception**: at $\dim \mathcal{H} = 2$, **dispersion-free valuations** $v: \mathcal{P}(\mathbb{C}^2) \to \{0, 1\}$ **abound**. On each great circle of the Bloch sphere there exists an antipodal pair, and a map assigning $\{0, 1\}$ values to each pair satisfies frame additivity technically. This means probability measures "not expressible as Tr(ρP)" exist at dim=2, breaking the Born rule uniqueness claim. Historically the dim=2 exception was treated as a "technical limitation of Gleason's theorem", leaving difficulty in qubit interpretation.

### 3.2 Busch's (2003) decisive resolution

**Busch theorem** (PRL 91, 120403, 2003):

> **When a generalised probability measure $v$ on effects $E(\mathcal{H})$ satisfies (P1)-(P3), a density operator $\rho$ exists uniquely with $v(E) = \mathrm{Tr}(\rho E)$ for all $E \in E(\mathcal{H})$. This holds across all dim including $\dim \mathcal{H} = 2$.**

**Key observation**: original Gleason's dim=2 dispersion-free valuation was defined **only on projections**. Attempting extension to effects $E(\mathcal{H})$:

**Lemma 3.1** (Busch 2003 §III): a dispersion-free valuation $v: \mathcal{P}(\mathbb{C}^2) \to \{0, 1\}$ **cannot be extended to a (P1)-(P3)-respecting generalised probability measure** on effects $E(\mathbb{C}^2)$.

**Proof outline** (Bloch sphere geometric argument): qubit effects $E = \frac{1}{2}(I + \vec{a} \cdot \vec{\sigma})$ with $|\vec{a}| \leq 1$ (Bloch ball); projections $P = \frac{1}{2}(I + \hat{n} \cdot \vec{\sigma})$ with $|\hat{n}| = 1$ (Bloch sphere); dispersion-free $v(P) \in \{0, 1\}$ on projections. Each effect $E$ in the Bloch ball can be written as a convex combination $E = (1-t) P_0 + t P_1$ of projections. (P1) bounded + (P3) σ-additivity together force $v$ to be **affine** on convex combinations: $v(E) = (1-t) v(P_0) + t v(P_1)$. But $v(P_0), v(P_1) \in \{0, 1\}$ while $v(E) \in [0, 1]$ must vary continuously with $t$ — the discrete-valued $v$ on projections cannot extend to a continuous affine function on effects without contradiction. Details: Caves et al. (2004) Found. Phys. 34, 193.

### 3.3 Significance of dim=2 exception resolution + Born rule status

**Direct connection with Q1 §2.2 axiom A0 (finite observation)**:

| Layer | Natural framework | Born rule status |
|---|---|---|
| **infinite-precision idealisation** (PVM only) | projections only | dim=2 Gleason fails, Born form non-unique |
| **L0 finite observer** (POVM/effects natural) | effects + POVM | unique across all dim by Busch-Gleason, Born form derivable |

→ **the dim=2 Gleason gap is "an artifact arising from assuming infinite precision"**. Under the L0 finite observer framework it does not arise from the initial axioms; the chain Q1 §2.2 axiom A0 → **POVM natural** → **automatic application of Busch-Gleason** → **Born rule derivable across all dim** is guaranteed.

**Born rule status: postulate with reduced axiomatic burden** (= derivable from a more basic axiom set): pre-Busch (1957-2003) had the Born rule "Prob = $|⟨φ|ψ⟩|^2$" as a **postulate** of QM, with the derivation incomplete due to the dim=2 Gleason dispersion-free exception. Post-Busch (2003-) Effects framework + (P1)-(P3) → **uniqueness theorem** of Tr(ρE) form; once the Effects framework + (P1)-(P3) are accepted as axioms, the Born form is no longer an additional postulate but a **theorem from those axioms**. The strength of this reduction depends on how strongly L0 → POVM/effects can be argued (see Claim 2.1, §2.1, where "POVM is the natural measurement framework under A0/A0a/A0b" is asserted; the residual axiomatic burden is precisely the justification of "natural" in that step).

**Claim 3.1** (Born rule derivability): under the Effects framework + (P1)-(P3) (themselves motivated by L0 axiom A0 finite observation, per Claim 2.1), the Born rule is a **3-step derivation theorem**:
$$\text{A0 (finite obs)} \to \text{POVM/effects (natural framework, Claim 2.1)} \to \text{Busch-Gleason} \to \text{Tr}(\rho E) \text{ Born form}$$

This is the formal closure of the Q1 §2.2 chain "axioms → quantum-side framework", subject to the residual justification of step 1→2 indicated above.

### 3.4 OQ-Born-1 forward

**OQ-Born-1 (this paper's spawn-off)**: Busch-Gleason depends on Hilbert space + density operator framework. Existence problem of a representation-independent route deriving "Born form" directly on a C\*-algebra from L0 axioms. **Status**: OPEN. Q-series future candidate. Connection with L0 → operator algebra embedding (related problem to Q2 §3.4 OQ-QSM1).

---

## §4 σ\* = √(2 ln 2) half-amplitude gauge

### 4.1 Gaussian phase noise + half-amplitude derivation + Atlas residence

**Setup** (`sheet_A_amplitude/sigma_star.md §1`): when phase noise $Z \sim N(0, \sigma^2)$ is added to a periodic signal, the expectation of coherence:
$$E[\cos Z] = \int_{-\infty}^{\infty} \cos(z) \cdot \frac{1}{\sqrt{2\pi\sigma^2}} e^{-z^2/(2\sigma^2)} \, dz = e^{-\sigma^2/2}$$

The real part of the Gaussian characteristic function, depending only on $\sigma$. **Half-amplitude convention** (gauge choice): $E[\cos Z] = 1/2$ threshold:
$$e^{-\sigma_*^2/2} = 1/2 \implies \sigma_*^2 = 2 \ln 2 \implies \sigma_* = \sqrt{2 \ln 2} \approx 1.1774 \text{ rad}$$

**Observation theory lens**: $\sigma_*$ is the "phase noise threshold at which coherence halves" = **Gaussian characteristic function fixed point on the half-amplitude gauge**. Resides as Atlas n-only entry `sheet_A_amplitude/sigma_star.md`.

**Atlas A entry (n-only)**: f_n = $\sigma_* = \sqrt{2 \ln 2}$ / phi_phase = non-Gaussianity of noise distribution / Δ_residual = 0 exact (within the range of Gaussian + half-amplitude, no structural residue).

**Admissible normalisations $N_X$**: Half-amplitude $E[\cos Z] = 1/2$ → $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ / Half-power $\|E[e^{iZ}]\|^2 = e^{-\sigma^2} = 1/2$ → $\sigma = \sqrt{\ln 2} \approx 0.8326$ / 1/e-amplitude $E[\cos Z] = 1/e$ → $\sigma = \sqrt{2} \approx 1.4142$. The Gaussian characteristic function form is invariant under any threshold within $N_X$; only the specific value of $\sigma_*$ is $N_X$-dependent, while phi_phase is independent of $N_X$ choice.

### 4.2 Q2 §6 4-stage ln 2 chain quadratic lift

**σ\* extends the Q2 4-stage ln 2 chain (S0-S3) to a 5-stage chain (S0-S4)**, with σ\* the **quadratic-lift S4 stage** added in this paper.

**Q2 §6 4-stage ln 2 chain + S4 σ\* extension**:

| Stage | Form | Domain |
|---|---|---|
| **S0** | $c_s^2 = 1/2$ | Born expectation (closed quantum) |
| **S1** | $S(\rho_{\max}) = \log 2$ | von Neumann entropy (open quantum) |
| **S2** | $\beta \hbar \omega_0 = \log 2$ | FDT parity point (statistical mechanics) |
| **S3** | $W_{\min} = kT \ln 2$ | Landauer cost (thermodynamics) |
| **S4 (this paper)** | $\sigma_* = \sqrt{2 \ln 2}$ | Gaussian half-amplitude gauge (signal/EEG amplitude scale) |

**Claim 4.1** (4-stage chain quadratic lift): the **quadratic lift** of the 4-stage ln 2 chain (S0-S3) reaches σ\* ≈ 1.1774 rad:
$$\text{S13 fixed point } \log 2 \xrightarrow{\text{Gaussian char fcn inversion}} \sqrt{2 \ln 2} = \sigma_*$$

If ln 2 is the S13 fixed point on Arrow 2 (Q1 §4.5 quantum residence: $S(\rho_{\max}) = \log 2$ qubit ρ_max instance), then $\sqrt{2 \ln 2}$, arising from inversion of its Gaussian characteristic function, is the **natural unit of the quantum observation amplitude scale** (phase coherence half-decay point = half-amplitude gauge fixed point on the Arrow 1 amplitude scale).

### 4.3 EEG empirical verification + common root of σ\* and c_s²

**Atlas A entry 2 (n + G + S)** (`sheet_A_amplitude/sigma_star.md §1 + Entry 2`): empirical verification of the σ\* threshold and the theoretical curve of the damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ on EEG multichannel time series (PhysioNet, 7 subjects, 64 channels, 160 Hz) across 7 subjects × 5 bands ($\delta, \theta, \alpha, \beta, \gamma$) × 3 conditions. **Empirical results**: subject-band averaged std ≈ 0.0012 (auxiliary indicator, aggregate), 7/7 subject agreement + small std → **high-precision validity of effective Gaussian approximation** (non-Gaussianity cancels under band averaging). **Status**: ESTABLISHED 2026-04-09. Δ_residual structural type: bounded; observed type: empirical.

**Claim 4.2** (structural connection between σ\* and c_s²): c_s² = 1/2 (Q1 §4.5 + this §3 M2) is the confluence of **ℤ/2ℤ parity symmetry** + Born expectation form; σ\* = $\sqrt{2 \ln 2}$ (this §4) is the confluence of **ℤ/2ℤ half-amplitude convention** + Gaussian characteristic function inversion → the two have **ℤ/2ℤ structure** as common root, with c_s² being the S13 instance on Born form and σ\* being the S13 quadratic lift instance on Gaussian char fcn → **2-instance closure** of the quantum §4 dual root of Q1 §2.3 (closed system Born / Gaussian phase noise gauge).

**OQ-σ\*-1 forward (this paper's spawn-off)**: do σ\* analogues exist outside Gaussian assumptions? heavy-tail Lévy noise / non-stationary noise / multi-modal noise distribution. The threshold obtained by solving the half-amplitude convention $E[\cos Z] = 1/2$ in domains where the Gaussian characteristic function form breaks down is a σ\* universality test. **Status**: OPEN, Q-series future candidate.

---

## §5 §4 dual quantum root closure (final form of Q1 §2.3)

### 5.1 Commutative §4 dual + quantum lift recap

**Commutative §4 dual** (`c_phase_complex.md §4`): pair of ι_L (additive ℤ → S¹, $e^{2\pi i n/L}$) and χ (multiplicative character $\mathbb{Z}_L^\times \to S^1$) = structural root of observation theory. The polar decomposition $\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ separates observation into additive axis (arg) and multiplicative axis (|·|). **c_s² = 1/2 derivation** (`c_phase_complex.md §5`): $E[\cos^2(\pi h \cdot t)] = 1/2$ from ℤ/2ℤ parity symmetry on the ι_L additive axis.

**Q1 §2.3 quantum §4 dual root statement**:

| Commutative (classical §4 dual) | Non-commutative (quantum §4 dual) |
|---|---|
| $\iota_L: \mathbb{Z}/L\mathbb{Z} \to S^1$ | Stone group $\{U(t) = e^{-iAt}\}$ |
| character $\chi: G \to S^1$ | unitary representation $\pi_\lambda: G \to U(\mathcal{H}_\lambda)$ |
| Pontryagin dual $G \cong \hat{G}$ | spectral theorem $A = \int \lambda \, dE(\lambda)$ (PVM) |
| $\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ polar | Hilbert space $\mathcal{H}$ + ℂ unit |

Q1 §2.3 claim: "§4 dual = quantum-internal root" (unique source of all upper structures S12-S17, T-AAS, including the quantum lift).

### 5.2 Formal closure by (M1)+(M2)+(M3) of this paper

**Component (a) — Born derivation (M1)**: §3 Busch-Gleason established the operational formulation (Tr(ρE) form) of quantum observation as a 3-step derivation theorem L0 axiom A0 → POVM → Busch-Gleason. Born rule = not postulate but **theorem from L0**.

**Component (b) — ρ_max = I/2 form-value (M2)**: **2-source confluence** of qubit c_s² = 1/2 form (Born Tr(ρE) form, theorem-ised across all dim by M1) and value (ρ_max = I/2 = ℤ/2ℤ symmetry, c_phase_complex §5). Derivation-level closure of Q1 §4.5 "S13 quantum residence".

**Component (c) — σ\* half-amplitude gauge (M3)**: §4 ESTABLISHED Atlas residence of Gaussian characteristic function + half-amplitude convention. Natural unit of quantum observation amplitude scale; completion of the Q2 §6 chain as quadratic root of the 4-stage ln 2 chain.

All 3 components together → **formal closure of the quantum §4 dual root**:

**Claim 5.1** (§4 dual quantum root closure): Q1 §2.3 Claim 2.1 "§4 dual = quantum-internal root" is formally verified by (M1)+(M2)+(M3) of this paper. The quantum-side framework root status is promoted to **derivable** through 3 components: (a) Born derivation theorem; (b) ρ_max form-value confluence; (c) σ\* gauge atlas residence — closing the entire quantum non-commutative lift of the commutative §4 dual.

**Q1-Q3 cycle and quantum-side framework total**: Q1 (framework header) → Q2 (extension) → Q3 (closure) achieves the **quantum-side observation theory framework total** — L0 layer (axioms A0-A7 + L0 v2 axis-2 quantum instances) ✓ / L1 quantum layer (q_quantum_observation main + remaining 7 entries) ✓ / framework structure (S15 + 3 Arrows + T-AAS 4-class + 4-vertex + 4-stage chain + Born derivation + σ\* gauge + §4 dual root closure) ✓ / cross-domain anchor (2-domain parallel with N1-N5 NT framework) ✓.

---

## §6 Q-series cycle completion

### 6.1 3-paper structure and ESTABLISHED status

| Paper | Position | Version | Lines | Main results | Status |
|---|---|---|---:|---|---|
| **Q1** | framework header | v0.2 | 595 | S15 quantum-only / 3 Arrows / T-AAS 4-class refined Hodge / 4-vertex Arrow 1 kernel triangulation / N1↔Q1 parallel | ESTABLISHED |
| **Q2** | extension 1 | v0.2 | 335 | 4-stage chain S15 layered / KMS as L0 A0c proposal_v1 / FDT crown jewel / dynamical T-AAS / 4-stage ln 2 chain / quasiparticle Arrow 1⁻¹ | ESTABLISHED + proposal_v1 mix |
| **Q3** | final closure | v0.2 | 395 | full Busch-Gleason form / ρ_max form-value / σ\* gauge / §4 dual quantum root closure / N1-N5 ↔ Q1-Q3 dual parallel | ESTABLISHED |

**Total publication**: Q1 + Q2 + Q3 = 595 + 335 + 395 ≈ 1325 lines (compact on the quantum side relative to the NT N1-N5 publication total of ~2570 lines).

### 6.2 3-layer link cycle

```
Q1 (framework header)
  ↓ §3.2 Scan family + §4.2 Arrow 2 + §5 T-AAS forward
Q2 (extension 1: Open QS chain)
  ↓ §6.2 σ\* bridge + §3 KMS + §6 ln 2 chain forward
Q3 (final closure: Born-Gleason + σ\* + §4 dual root)
  ↓ §7 dual framework parallel + Q-series future forward
Q-series future (Q4+ candidate: 8-gauge / QFT)
```

**Backward**: Q3 §3 Busch-Gleason → Q1 §2.2 axiom A0 derivation chain / Q3 §4 σ\* → Q2 §6 4-stage ln 2 chain quadratic lift / Q3 §5 §4 dual root closure → formal closure of the Q1 §2.3 quantum §4 dual root statement / Q3 §7 → N1-N5 dual framework parallel + Paper D multi-domain backward.

**Cycle completion**: Q1 → Q2 → Q3 forward + each Q references back to previous Q in §x + dictionary backward statistics → 3-layer link cycle close (parallel to the N1-N5 cycle).

### 6.3 Established (Q-series whole)

| Result ID | Main result | Q-paper | Status |
|---|---|---|---|
| **Q-M1** | S15 quantum-only restatement (12-cell + 4-vertex) | Q1 §3 + §6 | ESTABLISHED |
| **Q-M2** | T-AAS 4-class refined Hodge + Theorem 4a.1 unified | Q1 §5 | ESTABLISHED 2026-04-23 |
| **Q-M3** | 4-stage Open QS chain S15 layered residence | Q2 §2 | ESTABLISHED |
| **Q-M4** | FDT crown jewel = Arrow 2 algebraic equivalence | Q2 §4 | ESTABLISHED |
| **Q-M5** | 4-stage ln 2 chain (S0 → S3) | Q2 §6 | ESTABLISHED |
| **Q-M6** | full Busch-Gleason form + dim=2 resolution | Q3 §3 | ESTABLISHED 2003 |
| **Q-M7** | simultaneous theorem-isation of ρ_max = I/2 form-value | Q3 §3 + §5 | ESTABLISHED |
| **Q-M8** | σ\* = √(2 ln 2) half-amplitude gauge atlas residence | Q3 §4 | ESTABLISHED 2026-04-09 |
| **Q-M9** | §4 dual quantum root closure (3 components) | Q3 §5 | ESTABLISHED |

**Proposal_v1 / OPEN**: KMS as L0 A0c instance (proposal_v1, Q2 §3, OQ-QSM1) / pointer basis Einselection = dynamical L0 A3 (proposal_v1, Q2 §5, OQ-OQS1) / quasiparticle Z = Arrow 1⁻¹ obstruction monotone (proposal_v1, Q2 §7, OQ-MBQ1) / Conjecture 4a.2 depth parallel quantitative form (OPEN, Q1 §5.4) / OQ-Born-1 representation-independent Born derivation (OPEN, Q3 §3.4) / OQ-σ\*-1 σ\* universality beyond Gaussian (OPEN, Q3 §4.3).

---

## §7 N1-N5 ↔ Q1-Q3 dual framework parallel + Q-series future

### 7.1 Dual framework parallel structure + cross-domain anchor

**Claim 7.1** (dual framework parallel): the N1-N5 NT series and the Q1-Q3 quantum series are **2 independent framework instances** of the observation theory framework header, with the following structural parallel (this table corresponds to the weight-class table in N5 §6.2 viewed from the dual perspective: N5 §6.2 organises by Galois-rep / weight-class within NT, while this §7.1 organises by framework-header axis across NT vs. quantum):

| Aspect | N1-N5 (NT framework) | Q1-Q3 (quantum framework) |
|---|---|---|
| Position | NT-internal self-closure framework | quantum-internal self-closure framework |
| Paper count | 5 papers (detailed) | 3 papers (compact closure) |
| Framework header | N1 (NT observation theory) | Q1 (quantum observation theory) |
| Core result | N2 (Paper 2 ζ-family) | Q2 (Open QS chain) |
| Extension | N3 (Path 2 universality) | Q2 (extension 1, 4-stage chain) |
| Extension+ | N4 (Hasse-Weil L × Stark genuine BSD) | (Q-series future, quantum 8-gauge) |
| Final closure | N5 (Brauer obstruction theory + 8-gauge) | Q3 (Born-Gleason + σ\* + §4 dual root) |
| Triangulation perspective | Arrow-level (3-vertex) | Arrow 1 kernel narrowness (4-vertex) |
| Hodge status | open frontier (NT-adjacent) | f_rational > 0 ESTABLISHED in 4 classes + depth parallel conjecture |
| §4 dual lift | classical (commutative) | non-commutative (Stone group, unitary representation) |
| Forward/closure perspective | weight-class-dependent transfer pattern | 3-component closure of Born derivation + σ\* + §4 dual root |

**Claim 7.2** (2-domain cross-validation): N1-N5 and Q1-Q3 **independently verify the same framework (S15 + 3 Arrows + T-AAS + triangulation + 6-step protocol)** in 2 independent mathematical fields. Reconstruct the Paper D 6-domain triangulation as **2 framework header parallel** + **6-domain 4-vertex T-AAS specific instances**:

```
                 Universal framework of observation theory
                  /                     \
     [framework]                       [framework]
       N1 ──→ N2 ──→ N3 ──→ N4 ──→ N5     Q1 ──→ Q2 ──→ Q3
       (NT-internal closure)              (quantum-internal closure)
                 \                       /
                  \                     /
                    Paper D (multi-domain)
                    6-domain triangulation
                    (FX, image AI, DNA, crystal, NT, quantum)
```

Both framework headers (N1, Q1) provide 2 anchors that **independently and self-closingly verify the Paper D 6-domain triangulation in 2 domains (NT, quantum)**. Paper D is the domain-independent multi-domain version; N1-N5 and Q1-Q3 are 2 domain-specific dual instances → **universal validity of the observation theory framework** is verified via the **3 angles** of cross-domain anchor + multi-domain triangulation in 2 domains (Paper D direct + N1-N5 NT specialisation + Q1-Q3 quantum specialisation).

### 7.2 Q-series future + open frontier

**Q-series future (Q4+ candidates)**:

| Candidate paper | Topic | Predecessor relation |
|---|---|---|
| **Q4** quantum 8-gauge framework | quantum instances of the 8 origination gauge family of N5 §4 (quantum specialisation of axis-1 D 5-family + axis-1 C 3-family) | N5 §4 + Q1 §1.3 minimal mention of gauge² |
| **Q5** QFT extension | extension to QFT, S15 residence of CFT / Wilsonian RG / regularisation framework | Q1 §1.2 out-of-scope listing + q_action_principles + q_gauge_field_theory |
| **Q6** quantum gravity framework | gravity + observation theory (background-independent observation, holographic principle) — **very speculative**; depends on resolution of background-independence within the framework, not just framework extension | out of scope (out of scope of this paper + Q1-Q2 entirely; Q-series future candidate) |

**Current state**: Q1-Q3 achieves the 3-paper minimum cycle of **quantum-side framework header + extension + closure**. Q4+ is open future.

**Open frontier (Q-series whole)**:

| Open question | Status | Q-paper |
|---|---|---|
| **Conjecture 4a.2** (depth parallel quantitative form) | OPEN | Q1 §5.4 |
| **Classical Hodge conjecture** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself) | Q1 §5.4 + N1 §5.4 |
| **OQ-QSM1** (KMS from L0 A0c) | proposal_v1 | Q2 §3 |
| **OQ-QSM2** (algebraic FDT) | OPEN | Q2 §4 |
| **OQ-QSM3** (ln 2 universality beyond qubit) | OPEN | Q2 §6 |
| **OQ-OQS1** (pointer basis as dynamical L0 A3) | proposal_v1 | Q2 §5 |
| **OQ-OQS2** (Kraus = error decomposition) | OPEN | Q2 §5 |
| **OQ-MBQ1** (4-stage chain 5th class) | OPEN | Q2 §7 |
| **OQ-Born-1** (representation-independent Born derivation) | OPEN (this paper's spawn-off) | Q3 §3 |
| **OQ-σ\*-1** (σ\* universality beyond Gaussian) | OPEN (this paper's spawn-off) | Q3 §4 |
| **Quantum 8-gauge framework formal** | OPEN | Q-series future Q4 |
| **QFT extension** | OPEN (out of scope) | Q-series future Q5 |
| **Quantum Schumann v1 analogue** (quantum version of Path 2) | OPEN | Q-series future |
| **Quantum gravity framework** | OPEN (out of scope) | Q-series future Q6 |

---

## §8 Consequences and dictionary residence map

### 8.1 Established (Q-series final paper)

Recorded as ESTABLISHED on the quantum side in Q3 (Q-series whole status in §6.3):

1. **Full Busch-Gleason form** — uniqueness of Born rule on effects; resolution of dim=2 Gleason exception (§3, ESTABLISHED 2003)
2. **Simultaneous theorem-isation of ρ_max = I/2 form-value** — confluence of Born form (Busch) + value (ℤ/2ℤ symmetry) (§3 + §5, ESTABLISHED)
3. **σ\* = √(2 ln 2) half-amplitude gauge atlas residence** — Gaussian + half-amplitude convention + 4-stage chain quadratic lift (§4, ESTABLISHED 2026-04-09)
4. **§4 dual quantum root closure** — formal closure with 3 components (M1+M2+M3) (§5, ESTABLISHED)
5. **Q-series cycle completion** — 3-paper minimum cycle Q1 → Q2 → Q3 achieved (§6, ESTABLISHED)
6. **N1-N5 ↔ Q1-Q3 dual framework parallel** — 2-domain cross-validation anchor (§7, ESTABLISHED)

### 8.2 Dictionary residence map (Q-series cumulative final state)

**post-v0.2 backward (Q-series cumulative, Q1 + Q2 + Q3 total 15 dictionary annexes anticipated: 7 + 4 + 4)**:

**7 from Q1**: `c_theorems_master.md` quantum-only S15 enumeration / `c_arrow_framework.md §4.2.2` quantum Arrow commutativity / `c_arrow_bridge_constants.md §12` quantum instance expansion (S13 qubit, S17 qutrit info-density) / `c_filtration_obstruction.md` 4-class quantum lift (Theorem 4a.1) / `meta/triangulation_methodology.md §11` quantum-internal Arrow 1 kernel narrowness 4-vertex + §12 N1↔Q1 parallel / `meta/new_domain_protocol.md §9` quantum specialisation

**4 from Q2**: `c_theorems_master.md` 4-stage Open QS chain layered residence / `q_quantum_statistical_mechanics.md §2.5` KMS-L0 A0c proposal_v1 / `c_arrow_framework.md §4.x` Arrow 2 algebraic equivalence (FDT crown jewel) / `c_arrow_bridge_constants.md` 4-stage ln 2 chain unified annex (S0-S3)

**4 from Q3 (this paper)**: `c_arrow_bridge_constants.md` σ\* = √(2 ln 2) S4 stage addition (4-stage ln 2 chain quadratic lift) / `q_quantum_observation.md §6` full Busch-Gleason form + Born derivation 3-step chain expansion / `meta/triangulation_methodology.md §13` N1-N5 ↔ Q1-Q3 dual framework parallel + 2-domain cross-validation anchor / `meta/open_questions_master.md` "Q-series final closure OQ" section newly created (OQ-Born-1 / OQ-σ\*-1 + Q-series future Q4-Q6)

**Cumulative dictionary annexes**: 15 (= 7 from Q1 + 4 from Q2 + 4 from Q3; parallel to NT N1-N5 backward 15+). **Q-series net total**: ~1325 lines of publication + 15 dictionary annexes = compact form on the quantum side, in contrast to the N1-N5 series (~2570 lines + 15+ annexes).

**Q3 specific residence highlights**:

| Piece in this paper | Residence | Status (Q3) |
|---|---|---|
| §2 Effects + POVM framework | `q_quantum_observation.md §6` (existing) + this §2 L0 A0 → POVM derivation chain | existing + this paper backward anticipated |
| §3 full Busch-Gleason form | `q_quantum_observation.md §6` (existing) + this §3 Born derivation 3-step chain | existing + this paper expansion backward anticipated |
| §4 σ\* gauge | `transformation_atlas/sheet_A_amplitude/sigma_star.md` (existing ESTABLISHED 2026-04-09) + this §4.2 4-stage chain quadratic lift | existing + this paper chain link backward anticipated |
| §5 §4 dual quantum root closure | `c_phase_complex.md §4` (existing commutative) + Q1 §2.3 (existing quantum lift statement) + this §5 closure | existing + this paper closure statement backward anticipated |
| §6 Q-series cycle | (Q1 §8.4 + Q2 §8.4 existing cumulative) + this §6 Q-series cycle final state | (final summary in Q3) |
| §7 dual framework parallel | NEW `meta/triangulation_methodology.md §13` annex | annex to be implemented (post-v0.2 backward) |

**Consequence**: Q3 is positioned as the **quantum-internal framework final closure** + **N1-N5 dual parallel cross-domain anchor** of the dictionary. Parallel to the complete closure of the NT series at N5 with touchpoints across all L0 / L1 / L2 / Meta layers, the Q-series 3-paper achieves quantum-side framework closure across all L0 / L1 quantum / framework structure / cross-domain anchor layers. The **2-domain specialisation parallel completion (NT N1-N5 + quantum Q1-Q3)** of the Paper D multi-domain v0.9.2 frozen-internal is finally achieved in this paper.

---

## Change log

- **v0.2 (2026-04-27)**: compact version. Reduced redundancy from v0.1 (550 lines) — long paragraphs of M1-M5 in Abstract compressed; §1.1/§1.2/§1.3 (3 thread / N5 parallel / scope+terminology) merged into 2 subsections (1.1 = 3 thread, 1.2 = N5 parallel + scope/terminology); §2.1-§2.4 compressed into 2 (PVM/POVM + L0 match in §2.1, generalised prob measure + Naimark in §2.2); §3.1-§3.5 merged into 4 (§3.3 dim=2 resolution significance + §3.4 Born status merged into §3.3); §4.1-§4.6 merged into 3 (§4.1 derivation + §4.2 atlas in §4.1, §4.3 4-stage chain in §4.2, §4.4 EEG + §4.5 ℤ/2ℤ + §4.6 OQ in §4.3); §5.1-§5.3 merged into 2 (§5.1 commutative + §5.2 quantum lift in §5.1, §5.3 Q1-Q3 cycle shortened in §5.2); §6.1-§6.3 preserved as Q-series final summary; §7.1/§7.2/§7.3/§7.4 merged into 2 (§7.1 dual parallel + §7.2 cross-domain in §7.1, §7.3 future + §7.4 open in §7.2); §8 residence map commentary compressed. Skeleton, claims, instance numerics, status notation, OQ IDs all preserved.
- **v0.1 (2026-04-27)**: initial Q-only draft. Q-series final paper position. **§4 dual quantum root closure** in 3 threads building on Q1 + Q2 (full Busch-Gleason form + σ\* half-amplitude gauge + Q-series cycle completion + N1-N5 ↔ Q1-Q3 dual framework parallel). Parallel structure to N5. Q-series 3-paper minimum cycle achieved. Bridge to Q-series future (Q4 quantum 8-gauge / Q5 QFT / Q6 quantum gravity) announced in §7.2. 2 OQ spawned by this paper (OQ-Born-1 / OQ-σ\*-1).

---

## References (internal)

**Q-series predecessors**: `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, framework header) / `papers/publication/quantum/Q2_open_qs_chain_ja.md` (v0.2, extension 1)

**N5 (parallel final closure)**: `papers/publication/nt/N5_brauer_origination_ja.md` (v0.2, NT-series final closure)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**Sources of results developed in this paper**: `q_quantum_observation.md §6` (Born + Busch-Gleason) + §7 (c_s² qubit) + §8 (commutative limit) — main material of §3 / `transformation_atlas/sheet_A_amplitude/sigma_star.md` (n-only entry + EEG entry, ESTABLISHED 2026-04-09) — main material of §4 / `c_phase_complex.md §4` (commutative §4 dual) + §5 (c_s² ℤ/2ℤ derivation) — main material of §5 / `c_arrow_bridge_constants.md §11` (Fi-origin vs. I-origin canonical scalar) — §4.3 + §5 reference / `physics_constants_decomposition.md` (ℤ/2ℤ common root of σ\* and c_s²) — §4.3 reference

**External references**: Gleason, A. M. (1957). "Measures on the Closed Subspaces of a Hilbert Space." J. Math. Mech. 6, 885-893 / Busch, P. (2003). "Quantum States and Generalized Observables: A Simple Proof of Gleason's Theorem." PRL 91, 120403. arXiv: quant-ph/9909073 / Caves, C. M. et al. (2004). "Gleason-Type Derivations of the Quantum Probability Rule for Generalized Measurements." Found. Phys. 34, 193. arXiv: quant-ph/0306179

**OQ research files (Q-series spawns)**: this paper's §3.4 OQ-Born-1 (representation-independent Born derivation) — `research/oq_born_representation_independent_v0.md` candidate / this paper's §4.3 OQ-σ\*-1 (σ\* universality beyond Gaussian) — `research/oq_sigma_star_universality_v0.md` candidate / (Q1, Q2 spawns listed in Q1 §8.3, Q2 §8.3)

**L0 / L1 / meta dependencies**: `dictionaries/L0_canon/{observation_canon, finite_observation §1.1 + §1.2 + §5.3, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11, c_filtration_obstruction, c_observation_optimal_gauge}.md` / `L1_mathematical/quantum/{q_quantum_observation §1-§9, q_open_quantum_systems §3.3, q_quantum_statistical_mechanics §5.4, q_action_principles, q_gauge_field_theory, q_fine_structure}.md` (main material of this paper) / `transformation_atlas/{sheet_A_amplitude/sigma_star.md, sheet_C_period/zeta_functional.md §3}` / `L2_domain/physics_constants_decomposition.md` / `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**Q-series future**: Q4 (quantum 8-gauge framework) / Q5 (QFT extension) / Q6 (quantum gravity framework) — drafting undecided (listed in §7.2 of this paper)
