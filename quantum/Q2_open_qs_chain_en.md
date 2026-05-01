# Paper Q2: Observation Theory — Open Quantum Systems chain

**Subtitle**: 4-stage cumulative coarse-graining (open_QS → QSM → QTD → many-body), KMS-FDT-Landauer arc, Arrow 2 algebraic equivalence, dynamical T-AAS gauge

**Version**: v0.3 (OQ-OQS2 ESTABLISHED + Theorem 5.1 Lindblad-Kraus L0 bijection, 2026-04-28)
**Status**: DRAFT — forward expansion of Q1 (`Q1_observation_theory_quantum_ja.md` v0.2) §3.2/§4.2/§5/§8.2; redevelopment of observation theory across the 4-stage Open QS chain
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**Prerequisites (L1 core)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12/S13/S15), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_observation_optimal_gauge.md`
**Prerequisites (L1 quantum)**: `q_quantum_observation.md` (§6 Born + Busch-Gleason, §7 c_s², §8 commutative limit), `q_open_quantum_systems.md` (§1-§9), `q_quantum_statistical_mechanics.md` (§1-§10), `q_quantum_thermodynamics.md` (§1-§7), `q_many_body_quantum.md` (§1-§9)
**Prerequisites (Q1)**: Q1 §3.2 Scan family + §4.2 Arrow 2 + §5 T-AAS 4-class + §6 quantum-internal 4-vertex triangulation
**N parallel**: N3 (`N3_path2_dirichlet_universality_ja.md` v0.5) — parallel structure to the Path 2 NT universality extension paper
**Sequel paper**: Q3 (Born-Gleason)

---

## §0 Abstract

The Open Quantum Systems chain — q_open_quantum_systems → q_quantum_statistical_mechanics → q_quantum_thermodynamics → q_many_body_quantum, a 4-stage cumulative coarse-graining — redevelops observation theory in quantum statistical mechanics language. Each stage introduces an **additional coarse-graining** over the previous stage (partial trace → ensemble average → thermodynamic limit → quasiparticle distillation), and the 4-stage as a whole provides 4 modalities of kernel decomposition: **dynamical/statistical/macroscopic/many-body**.

This paper is a forward expansion of Q1 (quantum-only framework header) §3.2/§4.2/§5; parallel position to N3 (Path 2 NT universality). Whereas N3 establishes **NT universality extension** with Schumann v1 5-instance + Atkin-Lehner Type γ + Dirichlet L "structural fit only", this paper establishes **quantum statistical/thermodynamic universality extension** across the 4-stage chain.

**Six main results**:

1. **4-stage chain S15 residence map** — reconstruct the 4 L1 quantum entries (open_QS / QSM / QTD / many-body) layered by S15; each stage cumulative coarse-graining + a specific Arrow primarily responsible within an S15 layer → the 4-stage as a whole achieves **layered residence** of observation theory in quantum statistical mechanics language
2. **KMS as L0 A0c quantum instance (OQ-QSM1 attack route)** — Tomita-Takesaki modular flow $\sigma_t = \Delta^{it} A \Delta^{-it}$ is the quantum instance of L0 A0c (= multi-window compatibility axiom, `finite_observation.md §5.3`); compatibility of two thermal windows $W_{\beta_1}$ vs. $W_{\beta_2}$ ⟺ modular flow consistency ⟺ KMS condition. proposal_v1 of algebraic equilibrium on Arrow 2
3. **FDT crown jewel = Arrow 2 algebraic equivalence** — chain KMS → imaginary-time periodicity → FDT makes Scan (response χ_AB(ω)) and Information (correlation S_AB(ω)) algebraically equivalent on Arrow 2 (with the Bose factor $1/(1-e^{-\beta\hbar\omega})$ as bridge). Duality of observation and disturbance closes formally in a thermal setting. The qubit FDT parity point $\beta\hbar\omega_0 = \log 2$ is the thermal echo of c_s² = 1/2
4. **Pointer basis Einselection = dynamical T-AAS gauge fixing** — pointer basis selection by decoherence is the **dynamical version** of L0 A3 (gauge invariance): static gauge (observer choice) → dynamical gauge (environment selection). $[|i\rangle\langle i|, H_{int}] \approx 0$ is the dynamical gauge condition; the C₁-C₄ static algebraic classes of Q1 §5.2 lift to **dynamical environment-selected classes in Q2**
5. **Landauer principle = quantum final form of kT ln 2 (S13 closure)** — bit erasure thermodynamic cost $W_{\min} = kT \ln 2$ is the **deepest form** of the quantum instance of S13 ln 2 (algebraic equivalence on Arrow 3-2 cross between bit in Information layer and heat in Thermodynamic layer). The **4-stage ln 2 chain**: c_s² = 1/2 (Born) → S(ρ_max) = log 2 (von Neumann) → βℏω₀ = log 2 (FDT parity) → kT ln 2 (Landauer). Bridge to Q3 σ\* = √(2 ln 2) half-amplitude gauge
6. **Quasiparticle Z = Arrow 1⁻¹ generation closure (many-body)** — Landau Fermi liquid quasiparticle weight $Z = |\langle k|\psi_q\rangle|^2 \in (0, 1]$ is the many-body instance of Arrow 1⁻¹ (Information → Structural / Scan reverse). Anyon braiding statistics in BCS / topological order is the **dynamical structure of the Arrow 1 kernel in the strong-interaction regime**

**Thesis**: the 4-stage Open QS chain forms a **cumulative algebraic equivalence chain** on Arrow 2 (Scan → Information, log-exp dual) of observation theory — Tr_B (window) → KMS (algebraic equilibrium) → Legendre (thermodynamic) → quasiparticle (many-body distillation). Each stage carries a specific aspect of the Q1 §4 Arrow structure (dynamical Arrow 1 / algebraic Arrow 2 / macroscopic Arrow 3 / many-body Arrow 1⁻¹) as its primary responsibility, providing the closure of observation theory in quantum statistical mechanics language across all 4 stages. This paper functions as the theoretical foundation for Q3 (§4 dual quantum closure via Born-Gleason).

---

## §1 Introduction

### 1.1 Forward from Q1 + parallel position with N3

The Q2 topic announced in Q1 §8.2 (redevelopment of observation theory in statistical/thermodynamic language across the Open QS chain) is implemented across the 4-stage chain. **Cumulative structure** in which each stage introduces an additional coarse-graining over the previous stage:

| Stage | File | Coarse-graining operation | What is lost | What remains |
|---|---|---|---|---|
| **S1** | `q_open_quantum_systems.md` | Tr_B (partial trace over bath) | purity, system-bath correlations | system-local expectation values, Lindblad CPTP structure |
| **S2** | `q_quantum_statistical_mechanics.md` | ensemble average (specific bath state → thermal ρ_β) | specific bath state | Gibbs state ρ_β = e^{-βH}/Z, KMS condition, partition function Z |
| **S3** | `q_quantum_thermodynamics.md` | thermodynamic limit (microscopic correlations → macroscopic) | microscopic correlation functions | thermodynamic potentials (F, S, T, μ), thermo laws, Landauer |
| **S4** | `q_many_body_quantum.md` | quasiparticle distillation (bare excitations → dressed) | bare particle identity | quasiparticle Z, Fermi liquid theory, topological order |

**Cumulative**: each stage **preserves the previous + adds coarse-graining**. S1 ⊂ S2 ⊂ S3 ⊂ S4 (information loss monotone) — instance of 4-step coarse-graining of the L0 v2 Fi/I boundary in N1 §2.4.

**N3 parallel**: parallel structure to N3 (Path 2 NT universality) of the NT series:

| Aspect | N3 (NT) | Q2 (quantum) |
|---|---|---|
| Position | extension paper 1 (NT extension of N1 framework header) | extension paper 1 (statistical/thermodynamic extension of Q1 framework header) |
| Main claim | Path 2 universality (Schumann v1 5+ instances, Type α/β/γ trichotomy) | 4-stage Open QS chain universality (cumulative coarse-graining, S1-S4 layered residence) |
| Arrow focus | Arrow 2 (Scan → Information, ζ-family / Dirichlet L extension) | Arrow 2 (Scan → Information, Z(β) → F → S thermodynamic chain) |
| Universality status | 5+ instances + Type α/β/γ trichotomy ESTABLISHED (Type γ formal Definition 2.2 closed 2026-04-28); v1.5 remaining = 6th pre-registered instance (theta characteristics) + axis-2 strong split | 4-stage S15 residence ESTABLISHED + KMS-FDT-Landauer arc ESTABLISHED |
| Forward to | N4 (Hasse-Weil) / N5 (Brauer + 8-gauge) | Q3 (Born-Gleason σ\* = √(2 ln 2)) |

**Cross-validation**: N3 and Q2 **independently extend the same Arrow 2 (log-exp dual + S13 ln 2 fixed point)** in 2 independent mathematical fields (NT, quantum) → 2-domain extension validity of the Arrow 2 framework.

### 1.2 Scope and terminology

**Structure**: §2 4-stage chain residence / §3 KMS as L0 A0c / §4 FDT crown jewel / §5 pointer basis dynamical T-AAS / §6 Landauer ln 2 chain / §7 quasiparticle Arrow 1⁻¹ / §8 consequences.

**In scope**: 4-stage chain S15 residence map / Tomita-Takesaki modular theory (KMS as L0 A0c instance) / KMS → FDT chain (Arrow 2 algebraic equivalence) / Lindblad + decoherence + Einselection (dynamical T-AAS) / 4-stage ln 2 chain (deepest quantum form of S13) / quasiparticle Z (many-body instance of Arrow 1⁻¹) / 4-stage chain expansion of the 6-step protocol Q1 quantum specialisation.

**Out of scope** (deferred): full Born-Gleason closure of §4 dual quantum root / σ\* = √(2 ln 2) half-amplitude gauge / full Busch-Gleason proof of dim=2 Gleason gap resolution (→ Q3) / quantum field theory / QFT regularisation / quantum gravity / string theory / phase transition critical exponents / RG flow framework / non-equilibrium open systems beyond Lindblad — restricted to L1 quantum 8 entries.

**Terminology**: inherits the 3 uses of "gauge" from Q1 §1.3 (gauge¹/gauge²/gauge³). Additional terms specific to this paper: **cumulative coarse-graining** (S1 → S2 → S3 → S4 chain, cumulative information loss) / **KMS state** (thermal equilibrium state satisfying $\omega(A \alpha_t(B)) \to \omega(\alpha_t(B) A) e^{-\beta \omega}$) / **modular flow** $\sigma_t = \Delta^{it} A \Delta^{-it}$ (automorphism for cyclic separating vector Ω) / **pointer basis** (system-observable eigenbasis commuting with $H_{int}$, environment selection) / **quasiparticle weight Z** ($|\langle k|\psi_q\rangle|^2 \in (0, 1]$, bare/quasiparticle overlap) / **4-stage ln 2 chain** (4-instance chain c_s² = 1/2 → S(ρ_max) = log 2 → βℏω₀ = log 2 → kT ln 2).

**Direction-axis position**: this paper inherits the Q-framework B-primary native position from Q1 §1.4 (`user_observation_direction_axis` ESTABLISHED 2026-05-01). The primary domain of this paper (open quantum systems / KMS thermal equilibrium / FDT / 4-stage chain) is **B-direction native** (projection from infinite thermal ensemble onto finite system observable / continuous modular flow → discrete pointer-basis selection / Landauer kT ln 2 = a B-direction continuous-chain instance on the Shannon line). **The 4-stage ln 2 chain is a B-direction (Shannon-line) instance of the S13 ln 2 fixed point**, parallel to the 5-stage chain (Born / vN / FDT / Landauer / σ\*). The cross-direction screening rule (`feedback_cross_direction_identity_screen`) is operated within this paper as an internal screening rule; cross-paper claims with the N1 / I1 framework headers require a mandatory direction-tag pre-check.

---

## §2 4-stage chain S15 residence map

### 2.1 Main theorem

**Theorem 2.1 (4-stage Open QS chain S15 layered residence)**: the 4 L1 quantum entries provide a **12-cell residence map** of S15 (Scan / Structural / Information) 3 layers × 4 stages, with each stage having instances in all 3 S15 layers + a stage-specific primary Arrow.

**Status**: ESTABLISHED 2026-04-11 (`bidirectional_duality_v0.md §5.5-5.6`, S15 connection sections within each of the 4 stage entries, `c_theorems_master.md` rows S12/S13/S15).

### 2.2 Layered residence map (4-stage × 3-layer × Arrow assignment)

| Stage | Scan instance | Structural instance | Information instance | Primary Arrow |
|---|---|---|---|---|
| **S1 open_QS** | Lindblad semigroup $e^{Lt}$ (multiplicative, decay), unitary part of Kraus operator (additive) | Kraus rank $K$, pointer basis dim, decoherence-free subspace dim | $S(\rho_S)$ entanglement entropy, mutual information $I(S:E)$ | **Arrow 1 dynamical** (pointer basis selection by decoherence = T-AAS dynamical gauge fixing) |
| **S2 QSM** | $Z(\beta) = \text{Tr}(e^{-\beta H})$ (S12 multiplicative #4), Gibbs state $\rho_\beta$, response $\chi(\omega)$ | $\dim H$, spectral degeneracy $g(E_n)$, symmetry sector dim | $S(\rho_\beta) = \beta \langle E\rangle + \log Z$, $F = -kT \log Z$ | **Arrow 2 algebraic** (KMS condition + FDT crown jewel) |
| **S3 QTD** | thermo state along Legendre cycle, fluctuation theorem $\langle e^{-\beta W}\rangle$ | thermo limit dimensionality $d$, phase boundary topology | thermo entropy $S = -\partial F/\partial T$, Landauer $kT \ln 2$ | **Arrow 2-3 cross** (algebraic equivalence between bit in Information layer and heat) |
| **S4 many-body** | spectral form factor $K(\tau, t)$, Loschmidt echo $L(t)$ | quasiparticle weight $Z \in (0,1]$, topological invariants (Chern, anyon $\theta$), entanglement entropy area-law coefficient | von Neumann entropy scaling, CFT central charge $c$ | **Arrow 1⁻¹ generation** (quasiparticle = closure of Information → Structural reverse map) |

12 cells full residence ⇒ the 4-stage chain independently verifies all 3 S15 layers across 4 independent stages, and the 4 stages have different primary Arrows → the entire S15 Arrow structure is independently 4-stage verified (S1 dynamical / S2 algebraic / S3 cross / S4 reverse).

### 2.3 Cumulative coarse-graining structure

Each stage transition **loses specific information and preserves specific structure**:

```
q_quantum_observation        q_open_quantum_systems        q_quantum_statistical_mechanics
(closed, unitary)        →   (open, Lindblad)         →   (thermal, KMS)
                       Tr_B                          ensemble avg
                       preserves Born rule            preserves CPTP structure
                       loses purity                   loses specific bath state ρ_B

q_quantum_statistical_mechanics  q_quantum_thermodynamics    q_many_body_quantum
(thermal, KMS)              →   (thermodynamic, Legendre) →  (many-body, quasiparticle)
                          thermo limit                    quasiparticle distillation
                          preserves Gibbs state, Z          preserves Z spectral weight
                          loses microscopic corr            loses bare particle identity
```

**Information-theoretic monotonicity**: at each stage transition, von Neumann entropy / appropriate information measure is **monotone non-decreasing** — quantum-information-theoretic origin of the second law (`q_quantum_thermodynamics.md §3.4 + §5`).

**Q1 §6 4-vertex parallel**: at S1, the static C₁-C₄ classes of Q1 §5.2 lift to **dynamical classes** (environment-selected algebraic classes); the S2 Arrow 2 algebraic equivalence is common to both static / dynamical sparsity modalities; at S3, the 2 information families (bit and heat) combine via Arrow 3 (Hartley) and Arrow 2 (log-exp) cross; at S4, Arrow 1⁻¹ is the many-body instance of the "generation" operation in Q1 §4.6.

---

## §3 KMS as L0 A0c instance — Tomita-Takesaki modular theory

### 3.1 OQ-QSM1 attack route

**OQ-QSM1** (`q_quantum_statistical_mechanics.md §10`): can the KMS condition be derived from L0 axiom A0c (multi-window compatibility)? The attack route in this paper uses Tomita-Takesaki modular theory as bridge — proposal_v1.

### 3.2 Tomita-Takesaki modular flow

For a von Neumann algebra $\mathcal{M}$ on Hilbert space $\mathcal{H}$ with cyclic separating vector $\Omega$:

1. Define antilinear operator $S: A\Omega \to A^*\Omega$.
2. Polar decomposition $S = J \Delta^{1/2}$; $J$ antiunitary (modular conjugation), $\Delta$ positive (modular operator).
3. Modular automorphism group $\sigma_t(A) = \Delta^{it} A \Delta^{-it}$.

**Tomita-Takesaki theorem**: $\sigma_t$ is an automorphism of $\mathcal{M}$, the state $\omega(A) = \langle\Omega, A\Omega\rangle$ is KMS for $\sigma_t$ at $\beta = -1$. The modular flow $\sigma_t$ is **intrinsic** to the pair $(\mathcal{M}, \Omega)$.

**Physical meaning**: a physical Hamiltonian $H$ generates time evolution $\alpha_t$. A state is KMS at $\beta$ ⟺ $\alpha_t = \sigma_{-\beta t}$ (physical time = modular flow scaled by $-\beta$).

### 3.3 Match with L0 A0c + Status

**L0 A0c (`finite_observation.md §5.3`)**: observations through different windows $W_1, W_2$ have **compatibility** — they return identical predictions on common observables.

**Quantum instance (proposal_v1)**: thermal window $W_\beta$ = observation coarse-graining defined at inverse temperature $\beta$. Two thermal windows $W_{\beta_1}, W_{\beta_2}$ have L0 A0c compatibility ⟺ each KMS state $\rho_{\beta_1}, \rho_{\beta_2}$ has consistent restriction to common observables ⟺ modular flow $\sigma_t$ gives a natural map between different temperatures (analytic continuation in $\beta$) ⟺ multi-window compatibility ⟺ **KMS condition**.

**Schematic chain**: $\text{L0 A0c} \implies \text{modular flow consistency at } \beta_1, \beta_2 \implies \text{KMS condition}$

**Status**: proposal_v1. **Gap**: step 2 → 3 (translation of L0 compatibility to modular flow consistency) is not rigorous — L0 A0c is **observed pattern compatibility** (state-level), modular flow consistency is **operator algebra automorphism consistency** (algebraic-level); an "embedding L0 → operator algebra" is needed between the two and may be insufficient under the current L0 axioms. **Forward**: rigorous proof open as OQ-QSM1 (`research/oq_qsm1_kms_l0_a0c_v0.md` candidate).

### 3.4 Imaginary time periodicity

The KMS condition implies **imaginary time periodicity** of thermal correlators ($\tau \in [0, \beta)$ with periodic / antiperiodic boundary) — base of the Matsubara formalism, bridge to Euclidean QFT.

**Observation theory lens**: imaginary time = 90° rotation of quantum time = Wick rotation. Real-time scanner (Stone group $U(t)$) and imaginary-time scanner ($\tau$ Matsubara) are **two dual faces of the same Scan family** — bilateral residence on Re/Im axes within the S12 quantum lift.

---

## §4 FDT crown jewel — Arrow 2 algebraic equivalence

### 4.1 FDT statement and residence on Arrow 2

**FDT** (`q_quantum_statistical_mechanics.md §5`): algebraic equivalence between the symmetric correlation $S_{AB}(\omega)$ and response $\chi_{AB}(\omega)$ on Arrow 2:

$$S_{AB}(\omega) = \frac{2\hbar}{1 - e^{-\beta\hbar\omega}} \cdot \text{Im} \chi_{AB}(\omega)$$

**Arrow 2 residence**: $\chi_{AB}(\omega)$ = Scan layer (response, scanner $\omega$) / $S_{AB}(\omega)$ = Information layer (correlation, fluctuation spectrum) / $\frac{2\hbar}{1 - e^{-\beta\hbar\omega}}$ = Bose factor bridge → algebraic equivalence between the two → **algebraic isomorphism** on Arrow 2 (Scan → Information) at thermal equilibrium.

### 4.2 KMS → FDT derivation chain and crown jewel status

**Derivation chain** (`q_quantum_statistical_mechanics.md §5.3`): KMS condition $C_{AB}(t + i\beta) = C_{BA}(t)$ → Fourier transform of both sides $\tilde{C}_{AB}(\omega) e^{-\beta\omega} = \tilde{C}_{BA}(\omega)$ → correlator decomposition (symmetric S + antisymmetric → response χ) directly yields FDT. $\text{KMS} \to \text{imaginary-time periodicity} \to \text{FDT}$ → FDT is a **theorem** of KMS (not a postulate). If OQ-QSM1 succeeds → KMS is derived from L0 A0c → FDT is a quantum thermal corollary of L0 A0c.

**Crown jewel status: observation-disturbance duality**: the physical content of FDT is "spontaneous fluctuation in thermal equilibrium = response to external probe (up to Bose factor)". Q1 § parallel — q_quantum_observation §6 Born rule + Busch-Gleason "observation = disturbance" principle has a **thermal version**: state collapse under Born rule in quantum observation §6 = observer disturbance / thermal FDT (this paper) equilibrium fluctuation = system response to external probe → both are the **quantum closed system** vs. **quantum thermal** instances of the same structural principle (duality of observation and disturbance).

### 4.3 qubit FDT parity point: c_s² thermal echo

`q_quantum_statistical_mechanics §5.4`: qubit (two-level system at resonance) FDT $S(\omega_0) = 2\hbar\gamma / (1 - e^{-\beta\hbar\omega_0})$. **Parity point**: $\beta \hbar \omega_0 = \log 2 \implies$ Bose factor = 1 $\implies$ $S(\omega_0) = 2\hbar\gamma$. Recall $c_s^2 = 1/2$ (qubit Born expectation parity, q_quantum_observation §7); the FDT parity ratio reproduces this value: $S/(2\hbar\gamma) = 2 c_s^2 = 1$.

**Residence in the 4-stage ln 2 chain**: c_s² = 1/2 (q_quantum_observation §7, **stage S0**) → $S(\rho_{\max}) = \log 2$ (q_open_quantum_systems §3.3, **stage S1**) → $\beta\hbar\omega_0 = \log 2$ (FDT parity, **stage S2**) → $kT \ln 2$ (Landauer, **stage S3**). The 4 instances are **4 independent stage instances of the same ln 2 value** (details in §6).

### 4.4 OQ-QSM2 representation-independent FDT

**OQ-QSM2** (`q_quantum_statistical_mechanics.md §10`): existence problem of representation-independent (C*-algebraic) formulation of FDT. **Status**: OPEN. FDT (§4.1) uses Fourier transform + spectral representation, Hilbert space tools. KMS is purely algebraic. Since FDT is a corollary of KMS (§4.2), an algebraic FDT should exist. In this paper §4 states FDT as Arrow 2 algebraic equivalence at the framework level; rigorous construction of an algebraic representation-free formulation is OQ-QSM2 future work.

---

## §5 Pointer basis Einselection — dynamical T-AAS gauge fixing

### 5.1 Decoherence basis selection

**`q_open_quantum_systems.md §5`**: pointer basis $\{|i\rangle\}$ = system-observable eigenbasis commuting with $H_{int}$ (system-bath coupling): $[|i\rangle\langle i|, H_{int}] \approx 0$. Then off-diagonal elements of the reduced density matrix decay rapidly $\langle i | \rho_S(t) | j \rangle \sim \langle i | \rho_S(0) | j \rangle e^{-\Gamma_{ij} t}$ ($i \neq j$) → the environment **dynamically selects** the pointer basis (it is not the observer that chooses, but the system-bath coupling structure).

### 5.2 Static vs. dynamical T-AAS gauge

The 4-class refined Hodge framework of Q1 §5.2 specifies **static algebraic classes** as Arrow 1 source. This paper lifts these to **dynamical environment-selected classes**:

| Q1 §5.2 (static) | Q2 §5 (dynamical) | Quantum instance |
|---|---|---|
| Stabilizer (Clifford orbit) | Pointer basis (Clifford-symmetric environment) | Pauli-noise environment → diagonal computational basis pointer |
| Gaussian (symplectic orbit) | Gaussian-environment pointer | linear bath coupling → coherent state pointer |
| Eff-sim (poly-circuit class) | Markovian-Lindblad evolution within poly-depth | Born-Markov bath → poly-depth simulable trajectory |
| Bell-local (local unitaries) | Local-basis pointer (no entanglement-generating environment) | pure dephasing → local pointer basis preservation |

**Claim 5.1 (dynamical T-AAS lift)**: the 4 static algebraic classes of Q1 §5.2 are reconstructed as **dynamical attractors** of the corresponding environment-induced Lindblad dynamics: $\lim_{t \to \infty} \rho_S(t) \in \overline{C}_{\text{dyn}}$, where $C_{\text{dyn}}$ = environment-selected algebraic class → T-AAS gauge fixing dynamicises from **observer choice (static)** to **environment selection (dynamical)** (`q_open_quantum_systems.md §5.2 OQ-OQS1`).

### 5.3 OQ-OQS1 + OQ-OQS2

**OQ-OQS1** (`q_open_quantum_systems.md §9`): is pointer basis selection a dynamical version of L0 A3 (gauge invariance)? L0 A3 = observer chooses $W$ (static, amplitude gauge-invariant) / decoherence = environment chooses pointer basis (dynamic, diagonal populations surviving) → relation between the two gauges: **A3 reformulation** (extension to static + dynamic 2 modes). **Status**: proposal_v1; rigorous formulation of L0 A3 extension is OQ-OQS1 future work.

**Theorem 5.1 (Lindblad-Kraus L0 error decomposition canonical bijection, ESTABLISHED 2026-04-28)** (`research/oq_oqs2_kraus_l0_bijection_v0.md` for details): for a Lindblad master equation $d\rho/dt = \mathcal{L}\rho$ with generator decomposition $\mathcal{L} = \mathcal{L}_H + \mathcal{D}$, $\mathcal{L}_H \rho = -i[H, \rho]$, $\mathcal{D}\rho = \sum_k \gamma_k(L_k \rho L_k^\dagger - \tfrac{1}{2}\{L_k^\dagger L_k, \rho\})$, the L0 finite-observation error decomposition (`finite_observation.md §5.1`, error = error_arithmetic + error_projection + error_noise) admits a canonical bijection at the **generator (superoperator) level**:

| L0 error class | Lindblad generator term | property |
|---|---|---|
| **error_arithmetic** | $\mathcal{L}_H$ | system-intrinsic (independent of system-bath split), skew-adjoint → reversible |
| **error_projection** | $\mathcal{D}$ | $\{L_k, \gamma_k\}$ depends on the system-bath split (gauge choice), eigenvalues with non-zero real part → irreversible |
| **error_noise** | thermal occupation $\bar n_k(\beta)$ inside $\gamma_k$ | finite-T fluctuation, vanishes at $T \to 0$ |

**Kraus operator level caveat**: the discretised Kraus decomposition $\Phi_{dt} = \sum_k K_k(dt) \cdot K_k(dt)^\dagger$ does **not** preserve the partition. $K_0(dt) = I - i H_\text{eff}\, dt + O(dt^2)$ with $H_\text{eff} = H - (i/2)\sum_k \gamma_k L_k^\dagger L_k$ bundles the Hamiltonian unitary phase and the anticommutator damping. The L0 partition is canonical only at the generator level, not at the discrete Kraus-operator level.

**Closest-unitary diamond-norm interpretation**: defining $U_*^{(dt)}$ as the closest unitary channel to $\Phi_{dt}$ in diamond norm, $\|\Phi_{dt} - U_*^{(dt)}\|_\diamond = \|\mathcal{D}\| dt + O(dt^2)$ with $U_*^{(dt)} \to \exp(\mathcal{L}_H dt)$ as $dt \to 0$. The non-unitary residual rate equals the dissipator superoperator norm = error_projection magnitude; recovers the q_open §9 attack route as a corollary.

**Statement of this paper**: the Lindblad dissipator is the **dynamical realisation** of the Arrow 1 kernel (dynamical instance of the obstruction class taxonomy of Q1 §4.6). Lifts the static L0 A1 partition (Paper 0 §5.1) to the Lindblad generator level. Numerical verification: pure dephasing ($H = (\omega/2)\sigma_z$, $L_1 = \sigma_z$) + amplitude damping ($H = 0$, $L_1 = \sigma_-$) with V1 ($[\mathcal{L}_H, \mathcal{D}] = 0$ for pure dephasing, exact) + V2 ($\|\Phi_{dt} - U_*\|/dt \to \|\mathcal{D}\| = 0.5$ as $dt \to 0$) + V3 (Kraus reconstruction = $\exp(\mathcal{L} t)$ to $1.7 \times 10^{-16}$) all PASS.

---

## §6 Landauer principle — kT ln 2 chain and the deepest quantum form of S13

### 6.1 Landauer + 4-stage ln 2 chain

**Landauer** (`q_quantum_thermodynamics.md §5`): bit erasure thermodynamic minimum cost $W_{\min} = kT \ln 2$ (per bit). Information-bearing system $\rho_{\text{info}}$ (e.g. $\rho = (|0\rangle\langle 0| + |1\rangle\langle 1|)/2$ = 1 bit) → erased to fixed pure state $|0\rangle\langle 0|$ requires $\Delta S_{\text{system}} = -k \log 2$; second law gives $\Delta S_{\text{environment}} \geq k \log 2$ → heat dissipation $Q \geq kT \log 2$.

**4-stage ln 2 chain**:

| Stage | Source | Form | Domain | Mechanism |
|---|---|---|---|---|
| **S0** (closed quantum) | q_quantum_observation §7 | $c_s^2 = \text{Tr}(\rho_{\max} \Pi_{\text{even}}) = 1/2$ ($\Pi_{\text{even}}$ = parity projector onto the even-eigenvalue subspace) | Born expectation | qubit ρ_max = I/2 + parity projection |
| **S1** (open quantum) | q_open_quantum_systems §3.3 | $S(\rho_{\max}) = \log 2$ | von Neumann entropy | maximally mixed qubit entropy |
| **S2** (statistical mechanics) | q_quantum_statistical_mechanics §5.4 | $\beta \hbar \omega_0 = \log 2$ | FDT parity point | qubit FDT Bose factor = 1 |
| **S3** (thermodynamics) | q_quantum_thermodynamics §5 | $W_{\min} = kT \ln 2$ | Landauer cost | bit erasure heat dissipation |

**Claim 6.1 (4-stage ln 2 chain)**: the 4 instances are 4 independent stage instances of the **same ln 2 value** (= S13 fixed point). The classical §4 dual S13 (`c_phase_complex.md §5`) "even/odd integers are equiprobable" lifts in 4 quantum stages: S0 algebraic (parity projection) / S1 von Neumann entropic / S2 fluctuation-dissipation / S3 information-thermodynamic.

### 6.2 Deepest quantum form of S13 (Landauer) + bridge to Q3 σ\*

**Closure of the 4-stage chain**: Landauer (S3) shows ln 2 in **physical energy units** — heat dissipation $Q \geq kT \ln 2$ is the **thermodynamic price tag of information erasure**.

**Observation theory lens**: algebraic equivalence on the Arrow 3-2 cross between bit in Information layer (Q1 §3.4 entropy class) and heat (S3-stage Information instance) — **bit ↔ heat** = **cross-Arrow algebraic isomorphism** between Arrow 3 (Hartley log capacity) and Arrow 2 (Z → F → S) at the S13 fixed point (ln 2).

**Bridge to Q3** (`q_quantum_observation.md §6, §7`): half-amplitude gauge $\sigma_* = \sqrt{2 \ln 2}$ (Gaussian FWHM half-amplitude width). The 4-stage ln 2 chain (S0-S3) reaches $\sigma_* = \sqrt{2 \ln 2}$ via a **quadratic** lift — if ln 2 is the natural unit of quantum observation (deepest quantum form of S13), its quadratic root $\sqrt{2 \ln 2}$ is the natural unit of the half-amplitude gauge. Full closure of σ\* in Q3.

### 6.3 OQ-QSM3 ln 2 universality beyond qubit

**OQ-QSM3** (`q_quantum_statistical_mechanics.md §10`): does a thermal c_s² analogue exist beyond qubit? The 4-stage ln 2 chain achieves full closure at qubit (dim=2). A "thermal c_s²" analogue for dim>2 qudit / continuous variable systems is OPEN. Candidate forms: $\log 3$ analogue at qutrit (dim=3) (consistent with the S17 qutrit info-density argmax referenced in Q1 §4.5) / Rényi-α entropy parity ($\alpha = 1/2$ Tsallis-q) instance. Status: OPEN.

---

## §7 Quasiparticle Z — Arrow 1⁻¹ generation closure (many-body)

### 7.1 Landau Fermi liquid quasiparticle + Arrow 1⁻¹ residence

**`q_many_body_quantum.md §5`**: in strongly interacting fermion systems, bare particles (single-particle creation $c_k^\dagger|0\rangle$) are not eigenstates, but low-energy excitations are described by **dressed quasiparticles** $|\psi_q\rangle$: $Z = |\langle k | \psi_q \rangle|^2 \in (0, 1]$. $Z = 1$: free particle limit / $Z < 1$: interaction dresses bare particle / $Z = 0$: quasiparticle concept breaks down (non-Fermi liquid).

**Arrow 1⁻¹ residence in Q1 §4.6**: forward Arrow 1: Scan ($G_k = ⟨ψ| ... |ψ⟩$ correlator) → Structural (k-momentum, single-particle quantum number) / reverse Arrow 1⁻¹: Structural → Scan (full correlator including interactions). Quasiparticle Z = **overlap weight** between bare particle (Structural) → dressed quasiparticle (Scan) = **residual obstruction** of Arrow 1⁻¹ generation (Z < 1 is non-trivial kernel of bare → dressed map).

**Claim 7.1 (Quasiparticle Z = Arrow 1⁻¹ obstruction monotone)**: the Landau Fermi liquid quasiparticle weight $Z$ is the residual obstruction monotone of the Arrow 1⁻¹ "generation" operation in many-body context — $Z = 1$: trivial (free, Arrow 1 invertible) / $Z \in (0, 1)$: partial (interacting, generation possible but lossy) / $Z = 0$: full (non-Fermi liquid, generation breaks). T-AAS lens: $Z < 1$ is a **many-body instance of ker_topo > 0**, residual when the generation operation traverses the axis-2 Fi/I boundary.

### 7.2 Topological order + BCS pairing

**Topological order anyon braiding** (`q_many_body_quantum.md §6`): in FQHE, spin liquids, Kitaev model, the anyon braiding statistics index $\theta$ is a **discrete topological invariant** (Structural). Anyon worldline braiding generates a representation (Scan-side spectral data) → **topological instance of Arrow 1⁻¹ generation**. The Q1 §5.2 C₁ Stabilizer (Clifford orbit) is the effective realisation of abelian anyons; non-abelian anyons (e.g. Fibonacci anyons) are the **5th candidate** of Q1 §5.2 4-class extension.

**BCS pairing instability** (`q_many_body_quantum.md §6.1`): Cooper pair condensation = symmetry breaking instance; the **U(1) gauge** of the ground state is dynamically fixed (condensed-matter analogue of the gauge boson Higgs mechanism). Arrow 1 kernel residence: BCS gauge fixing is the strongly-interacting many-body version of §5.2 (pointer basis Einselection) — the **system internal interaction**, not the environment, selects the gauge. **T-AAS extension**: §5.2 dynamical gauge (environment-selected, open + Lindblad) vs. §7.2 BCS-style gauge (system-internal-interaction-selected, closed + symmetry breaking) **2 modes**.

### 7.3 OQ-MBQ1 4-stage chain final closure

**OQ-MBQ1 (this paper's spawn-off)**: does the many-body stage S4 provide the final closure of the 4-stage chain (= does the Q1 §5 T-AAS 4-class admit a 5+ class extension in many-body context)? **5th class candidates**: topological order (anyon braiding) — §7.2 / strongly correlated regime (Z = 0 non-Fermi liquid) / quantum spin liquid. Status: OPEN. Consistent with the 5 next candidates listed in Q1 §7; this paper §7 explicitly identifies one (topological order) as a 5th candidate in many-body context.

---

## §8 Consequences and open frontier

### 8.1 Established (Q-series extension paper)

| Result | Status |
|---|---|
| **M1 4-stage chain S15 layered residence map** | ESTABLISHED (12-cell residence + 4 stages with independent primary Arrows, §2) |
| **M2 KMS as L0 A0c instance** | proposal_v1 (Tomita-Takesaki bridge route, §3, OQ-QSM1 attack route) |
| **M3 FDT crown jewel = Arrow 2 algebraic equivalence** | ESTABLISHED (KMS → FDT chain, §4) |
| **M4 Pointer basis Einselection = dynamical T-AAS gauge fixing** | proposal_v1 (dynamical lift of Q1 §5.2 4 static classes, §5) |
| **M5 4-stage ln 2 chain (deepest quantum form of S13)** | ESTABLISHED (independent ln 2 verification across 4 instances, §6) |
| **M6 Quasiparticle Z = Arrow 1⁻¹ obstruction monotone** | proposal_v1 (residual measure of many-body Arrow 1⁻¹ generation, §7) |

### 8.2 Q3 forward bridge

| Q3 forward topic | Forward from this paper |
|---|---|
| **§4 dual quantum closure** (full Born-Gleason + dim=2 resolution + simultaneous theorem-isation of ρ_max = I/2 form and value) | the σ\* = √(2 ln 2) bridge in §6.2 closes fully in Q3; the imaginary time periodicity in §3.4 is the Wick rotation context |
| **σ\* = √(2 ln 2) half-amplitude gauge** (natural unit for Gaussian FWHM half-amplitude gauge) | the 4-stage ln 2 chain in §6.1 is the base of the σ\* quadratic root; the deepest quantum form of S13 (Landauer) in §6.2 is the thermodynamic underpinning of the σ\* unit |
| **dim=2 Gleason gap closure** (full Busch-Gleason proof; Born rule uniquely fixed across all dim on effects (POVM)) | analogous to the OQ-QSM1 derivation gap (L0 → operator algebra embedding) in §3.3; common axiom-layer reform with the dynamical L0 A3 in OQ-OQS1 §5.3 |

### 8.3 Open frontier

| Open question | Status | Related paper |
|---|---|---|
| **OQ-QSM1** (KMS from L0 A0c) | proposal_v1 | §3.3, future research |
| **OQ-QSM2** (algebraic FDT) | OPEN | §4.4, future research |
| **OQ-QSM3** (ln 2 universality beyond qubit) | OPEN | §6.3, future research |
| **OQ-OQS1** (pointer basis as dynamical L0 A3) | proposal_v1 | §5.3, future research |
| **OQ-OQS2** (Kraus = error decomposition) | **ESTABLISHED 2026-04-28** (Theorem 5.1, generator level canonical bijection + Kraus level mixed caveat + closest-unitary diamond-norm corollary, `research/oq_oqs2_kraus_l0_bijection_v0`) | §5.3 |
| **OQ-MBQ1** (4-stage chain 5th class) | OPEN (this paper's spawn-off) | §7.3, Q-series future |
| **σ\* = √(2 ln 2) gauge formal closure** | candidate (Q3 forward) | §6.2, Q3 |
| **Full Born rule derivation** | partial closure (§6 bridge of this paper); full Q3 | §6.2, Q3 |
| **Topological order as 5th algebraic class** | candidate | §7.2, Q1 §7 next candidate |
| **OQ-OQS3** (decoherence generates c_s² = 1/2) | OPEN | §6 4-stage chain context |

### 8.4 Dictionary residence map

| Piece in this paper | Residence | Status (Q2) |
|---|---|---|
| §2 4-stage chain S15 residence map | `c_theorems_master.md` row S15 + S15 connection sections within each of the 4 stage entries (existing) | existing + this paper's NEW 4-stage layered annex anticipated |
| §3 KMS as L0 A0c | `q_quantum_statistical_mechanics.md §2.5` (existing) + this §3 proposal_v1 expansion | existing attack route + this paper proposal_v1 |
| §4 FDT crown jewel | `q_quantum_statistical_mechanics.md §5` (existing) + this §4.2 observation-disturbance duality expansion | existing + this paper Arrow 2 algebraic isomorphism statement |
| §5 dynamical T-AAS | `q_open_quantum_systems.md §5` (existing) + this §5.2 dynamical lift of Q1 4-class | existing + this paper NEW dynamical lift table |
| §6 4-stage ln 2 chain | `q_open_quantum_systems §3.3 + q_quantum_statistical_mechanics §5.4 + q_quantum_thermodynamics §5` (existing) + this §6.1 chain unification | existing separately + this paper NEW unified chain statement |
| §7 quasiparticle Arrow 1⁻¹ | `q_many_body_quantum.md §5` (existing) + this §7.1 Arrow 1⁻¹ residence | existing + this paper NEW Arrow 1⁻¹ residence statement |

**post-v0.2 backward (Q-series cumulative, Q1 + Q2 total 10 entries)**: 7 from Q1 (`c_theorems_master.md` quantum-only S15 enumeration / `c_arrow_framework.md §4.2.2` quantum Arrow commutativity / `c_arrow_bridge_constants.md §12` quantum instances / `c_filtration_obstruction.md` 4-class quantum lift / `meta/triangulation_methodology.md §11` quantum 4-vertex + §12 N1↔Q1 parallel / `meta/new_domain_protocol.md §9` quantum specialisation) + 4 added by Q2 (`c_theorems_master.md` 4-stage chain layered residence annex / `q_quantum_statistical_mechanics.md §2.5` KMS-L0 A0c proposal_v1 expansion / `c_arrow_framework.md §4.x` Arrow 2 algebraic equivalence (FDT crown jewel) / `c_recursive_floor_principle.md` or `c_arrow_bridge_constants.md` 4-stage ln 2 chain unified annex).

**Consequence**: Q2 is positioned as a **quantum statistical/thermodynamic extension** of the dictionary; the S15 layered residence of the 4-stage chain formalises the framework integration of L1 quantum 4 entries. After drafting Q3 (Born-Gleason §4 dual closure), the **3-layer link** framework header (Q1) → extension (Q2) → closure (Q3) **completes** (parallel to N1-N5 series).

---

## Change log

- **v0.3 (2026-04-28)**: OQ-OQS2 closure. §5.3 lifted from candidate (future work) to **Theorem 5.1 (Lindblad-Kraus L0 error decomposition canonical bijection)**: generator level canonical bijection ($\mathcal{L}_H \leftrightarrow$ error_arithmetic / $\mathcal{D} \leftrightarrow$ error_projection / $\bar n_k(\beta) \leftrightarrow$ error_noise) + Kraus level mixed caveat ($K_0$ bundles unitary phase + anticommutator damping) + closest-unitary diamond-norm corollary ($\|\Phi_{dt} - U_*\|_\diamond = \|\mathcal{D}\| dt$). §8.3 OQ table: OPEN → ESTABLISHED. Numerical verification: pure dephasing + amplitude damping with V1/V2/V3 all PASS, Kraus reconstruction = $\exp(\mathcal{L}t)$ to ~$10^{-16}$ (`research/oq_oqs2_kraus_l0_bijection_v0`). q_open_quantum_systems.md §4.3 + §9 dictionary entries synchronised. Honest dual reporting: original attack route (Kraus operator partition) literal form **rejected** at V3, **recovered** at generator level + closest-unitary corollary. Spawned 3 successor OQ (OQS2-NonMarkovian / OQS2-DiamondNorm-Proper / OQS2-MultiJump).

- **v0.2 (2026-04-27)**: compact version. Reduced redundancy from v0.1 (531 lines) — long paragraphs of M1-M6 in Abstract compressed; §1 4 subsections (Q1 forward / N3 parallel / scope / terminology) merged into 2 (1.1 = Q1 forward+N3 parallel, 1.2 = scope+terminology); §2.2/§2.3/§2.4 3 subsections (residence map / cumulative / Arrow differentiation) compressed into 2 (Arrow differentiation merged into the end of §2.2 and §2.3); §3.1-§3.5 5 subsections merged into 4 (§3.3 L0 A0c match + §3.4 status merged into §3.3); §4.1-§4.5 5 subsections merged into 4 (§4.2 KMS→FDT derivation + §4.3 observation-disturbance duality merged into §4.2); §5.1-§5.4 merged into 3 (§5.3 OQ-OQS1 + §5.4 Lindblad OQ-OQS2 merged into §5.3); §6.1-§6.5 merged into 3 (§6.1 statement + §6.2 chain merged into §6.1, §6.3 closure + §6.4 Q3 bridge merged into §6.2, §6.5 OQ-QSM3 kept as §6.3); §7.1-§7.5 merged into 3 (§7.3 anyon + §7.4 BCS merged into §7.2); §8.4 residence map commentary compressed + post-v0.2 backward statistics in 1 paragraph. Skeleton, claims, instance numerics, and status notation all preserved.
- **v0.1 (2026-04-27)**: initial Q-only draft. Forward expansion of Q1 §3.2/§4.2/§5/§8.2. Redevelops observation theory in quantum statistical mechanics language across the 4-stage Open QS chain (open_QS → QSM → QTD → many-body). Parallel structure to N3 Path 2 NT universality. Six main results across 4 main themes: KMS-FDT-Landauer arc + dynamical T-AAS + 4-stage ln 2 chain + quasiparticle Arrow 1⁻¹. Bridge to Q3 (Born-Gleason σ\* = √(2 ln 2)) announced in §6.4.

---

## References (internal)

**Q1 (predecessor framework header)**: `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, quantum-only restatement)

**N3 (parallel extension paper)**: `papers/publication/nt/N3_path2_dirichlet_universality_ja.md` (v0.5, Path 2 NT universality + Type γ formal)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain §6 quantum part)

**Sources of results developed in this paper**: `q_open_quantum_systems.md` §1-§9 (§2 stage S1 + §5 pointer basis Einselection + §6 ln 2 chain S1) / `q_quantum_statistical_mechanics.md` §1-§10 (§2 stage S2 + §3 KMS + §4 FDT + §6 ln 2 chain S2) / `q_quantum_thermodynamics.md` §1-§7 (§2 stage S3 + §6 Landauer ln 2 chain S3) / `q_many_body_quantum.md` §1-§9 (§2 stage S4 + §7 quasiparticle Arrow 1⁻¹) / `q_quantum_observation.md` §6 Born + §7 c_s² + §8 commutative limit (§6 ln 2 chain S0 + §4.2 observation-disturbance duality reference)

**OQ research files (forward)**: `q_quantum_statistical_mechanics §10` OQ-QSM1 (KMS from L0 A0c) / OQ-QSM2 (algebraic FDT) / OQ-QSM3 (ln 2 beyond qubit) / OQ-QSM4 (2D window) / OQ-QSM5 (E variable) / `q_open_quantum_systems §9` OQ-OQS1 (pointer basis dynamical A3) / OQ-OQS2 (Kraus error decomposition) / OQ-OQS3 (decoherence generates c_s²) / this paper's spawn OQ-MBQ1 (4-stage chain 5th class candidate)

**L0 / L1 / meta dependencies**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4-§5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_observation_optimal_gauge, c_recursive_floor_principle}.md` / `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum}.md` (main material of this paper, 5 entries) / `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**Sequel paper**: Q3 (Born-Gleason + dim=2 closure + σ\* = √(2 ln 2) gauge) — drafting planned
