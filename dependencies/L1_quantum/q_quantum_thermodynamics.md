---
axis: B
position: quantum_thermodynamics
static_dynamic: both
connected_to:
  - B.quantum_statistical
  - B.many_body_quantum
  - A.algebra_analysis
  - C.control_theory
  - C.complex_systems
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-08
---

# Quantum Thermodynamics

**Level**: L1 (domain-independent mathematical structure)
**Dependencies**: q_quantum_statistical_mechanics.md (§1 Gibbs, §2 KMS, §3 Z, §5 FDT), q_open_quantum_systems.md (§4 Lindblad)
**Downstream**: q_many_body_quantum.md (done), L2 domain-specific thermodynamic models

---

## §0 Thesis

Quantum thermodynamics is the theory of what survives the thermodynamic coarse-graining. Where q_quantum_statistical_mechanics.md described thermal equilibrium at finite size — Gibbs states, KMS conditions, correlation functions — QTD asks: what happens when we forget the microscopic correlations entirely and retain only macroscopic quantities (energy, entropy, temperature, pressure, chemical potential)?

This is a third coarse-graining in the B-spine chain:
1. Partial trace over bath (q_open_quantum_systems.md): lose purity
2. Thermal ensemble average (q_quantum_statistical_mechanics.md): lose specific bath state
3. Thermodynamic limit (this file): lose microscopic correlations

In L0 language, QTD is the study of the coarsest thermal window — the window that retains only extensive and intensive variables, discarding all fluctuation structure. The partition function Z(β) (QSM §3) is the bridge: it contains all microscopic information, and QTD extracts from it only the leading-order (thermodynamic limit) behavior.

The central objects of QTD are:
1. **Free energy** F = -kT log Z — the bridge from QSM to thermodynamics (§1)
2. **Legendre structure** — the web of thermodynamic potentials (§2)
3. **Thermodynamic laws** — emergent constraints from the QSM substrate (§3)
4. **Jarzynski-Crooks fluctuation theorems** — the non-equilibrium bridge connecting far-from-equilibrium processes to equilibrium free energies (§4, supporting theorem)
5. **Landauer principle** — the crown jewel: information erasure has irreducible thermodynamic cost (§5)
6. **Phase transitions** — singularities in the thermodynamic limit where the coarse-graining itself breaks down (§6)

Note on ordering: Landauer (§5) is the crown jewel, placed after Jarzynski-Crooks (§4) to complete the three-stage rocket: QSM §5 FDT (equilibrium fluctuation-dissipation) → QTD §4 Jarzynski (non-equilibrium work ↔ equilibrium free energy) → QTD §5 Landauer (information ↔ heat). Each stage generalizes the previous: linear response → arbitrary protocol → information-theoretic bound.

---

## §1 Free Energy

### 1.1 From partition function to thermodynamics

The Helmholtz free energy is defined as:

    F(β) = -kT log Z(β) = -(1/β) log Tr(e^{-βH})

This is the central object bridging QSM and QTD. From QSM §3, Z(β) encodes the full spectrum of H. F extracts from Z the quantity that governs equilibrium: the state minimizing F = ⟨H⟩ - TS is the Gibbs state ρ_β (QSM §1.2).

### 1.2 Free energy as constrained optimization

The variational characterization:

    F = min_ρ [Tr(ρH) - TS(ρ)]

where S(ρ) = -Tr(ρ log ρ) is the von Neumann entropy. The minimum is achieved uniquely by ρ_β. This reformulation makes the physical content transparent:

- Tr(ρH) = energy (wants to be low)
- TS(ρ) = entropy contribution (wants to be high)
- F = the optimal tradeoff, controlled by temperature T

At T = 0: F → E_0 (ground state energy dominates)
At T → ∞: F → -TS_max (entropy dominates, maximally mixed state)

### 1.3 Free energy and the KMS condition

From QSM §2, the KMS state at inverse temperature β minimizes F. This provides a third characterization of the KMS state (alongside maximum entropy at fixed ⟨H⟩ and the algebraic KMS condition):

    ρ is KMS at β  ⟺  ρ minimizes F at temperature 1/kβ

The free energy thus connects the algebraic (KMS) and variational (Jaynes) characterizations of equilibrium. If OQ-QSM1 succeeds (KMS from L0 A0c), then F-minimization also becomes derivable from L0.

### 1.4 Quantum free energy vs classical free energy

For quantum systems, the free energy includes contributions from quantum coherences (off-diagonal elements of ρ in the energy eigenbasis). The quantum correction:

    F_quantum - F_classical = kT · D(ρ_β || ρ_diag)

where D is the quantum relative entropy and ρ_diag is ρ_β with off-diagonal elements removed. This correction vanishes at high temperature (classical limit) and becomes significant at low temperature where quantum coherences persist. In L0 terms: the quantum correction measures the information lost by restricting the thermal window to commuting observables only.

---

## §2 Legendre Structure

### 2.1 The web of thermodynamic potentials

The four standard potentials are related by Legendre transforms:

```
                 -PV
    U(S,V,N)  ←———→  H(S,P,N) = U + PV     (enthalpy)
        |                  |
   -TS  |                  |  -TS
        ↓                  ↓
    F(T,V,N)  ←———→  G(T,P,N) = F + PV     (Gibbs free energy)
                 -PV
```

Each potential is the natural function of its variables. The Legendre transform trades a variable for its conjugate:

    S ↔ T (entropy ↔ temperature)
    V ↔ P (volume ↔ pressure)
    N ↔ μ (particle number ↔ chemical potential)

### 2.2 Why Legendre?

The Legendre transform preserves information: U(S,V,N) and F(T,V,N) contain exactly the same thermodynamic information, expressed in different coordinates. This is not a coincidence — it is the thermodynamic manifestation of a general principle: conjugate variables are related by a contact structure (symplectic geometry in the even-dimensional case).

In L0 terms, the Legendre web is a gauge structure: different potentials are different gauges (windows) on the same thermodynamic state. The choice of potential is the choice of which variables the observer controls (the natural variables) and which are measured. This is A3 (gauge invariance) applied to thermodynamics: the physics does not depend on which potential you use.

### 2.3 Maxwell relations

The equality of mixed partial derivatives (the integrability condition of the Legendre structure) yields Maxwell relations:

    (∂T/∂V)_S = -(∂P/∂S)_V
    (∂T/∂P)_S = (∂V/∂S)_P
    (∂S/∂V)_T = (∂P/∂T)_V
    (∂S/∂P)_T = -(∂V/∂T)_P

These are not independent physical laws but consequences of the Legendre structure. In the σφ dictionary: Maxwell relations are the consistency conditions for the thermodynamic gauge web — they ensure that different observation paths through the potential landscape give the same answer.

### 2.4 Grand potential

For systems with variable particle number (relevant for BE/FD statistics, QSM §6):

    Ω(T,V,μ) = F - μN = -kT log Z_grand

where Z_grand = Tr(e^{-β(H-μN)}) is the grand partition function. The grand potential is the natural object for open systems exchanging both energy and particles with a reservoir — the most coarse-grained thermal window.

---

## §3 Thermodynamic Laws

### 3.1 Emergent status

The laws of thermodynamics are not axioms in the σφ framework — they are consequences of the QSM substrate, emerging when the thermodynamic coarse-graining is applied. Each law has a microscopic origin:

### 3.2 Zeroth law (transitivity of equilibrium)

If system A is in equilibrium with B, and B with C, then A is in equilibrium with C. In KMS language (QSM §2): if ω_AB satisfies KMS at β on A∪B, and ω_BC satisfies KMS at β on B∪C, then ω_AC satisfies KMS at β on A∪C.

This is a consequence of the uniqueness of the KMS state for finite systems (QSM §1.3). In L0 terms: transitivity of equilibrium is the transitivity of the compatibility relation A0c — if observations through window W_A are compatible with W_B, and W_B with W_C, then W_A with W_C.

### 3.3 First law (energy conservation)

    dU = đQ - đW + μdN

Energy is conserved. In the quantum setting, this is the conservation of Tr(ρH) under unitary evolution. The decomposition into heat đQ = TdS and work đW = PdV is the decomposition of energy change into entropic (thermal window) and mechanical (spectral window) contributions.

L0 origin: A1 (arithmetic structure) ensures that the total is conserved; the first law is A1 applied to the thermodynamic variables.

### 3.4 Second law (entropy increase)

For an isolated system, entropy does not decrease:

    ΔS ≥ 0    (isolated system)

More precisely, for a process taking ρ_initial to ρ_final:

    S(ρ_final) ≥ S(ρ_initial) - β⟨W⟩

where ⟨W⟩ is the average work performed. The second law is the statement that the thermal window loses information monotonically.

**Microscopic origin**: The second law is a consequence of the CPTP property of quantum channels (q_open_quantum_systems.md §4). Any CPTP map Φ satisfies:

    S(Φ(ρ)) + S(Φ(σ)) ≥ S(Φ(ρ)) - D(Φ(ρ) || Φ(σ))    (data processing inequality)

The data processing inequality states that no physical process can increase the distinguishability of quantum states. When applied to thermal processes, this yields the second law: entropy increases because the thermal coarse-graining is a CPTP map that destroys distinguishability.

L0 origin: The second law is the thermal manifestation of L0's finite observation principle — the observer has finite resources, and each coarse-graining step irreversibly loses information. The arrow of entropy is the arrow of observation.

### 3.5 Third law (Nernst theorem)

    S → 0  as  T → 0

The entropy of a system approaches zero as temperature approaches absolute zero (assuming a non-degenerate ground state). In QSM language: as β → ∞, ρ_β → |0⟩⟨0| (ground state projector), and S(|0⟩⟨0|) = 0.

The third law is the statement that the maximally resolved thermal window (β = ∞) reveals a pure state — no residual uncertainty. This connects to q_quantum_observation.md: at T = 0, the thermal window is "fully open" and the only remaining coarse-graining is the spectral window W.

---

## §4 Jarzynski-Crooks Fluctuation Theorems

### 4.1 Setting: non-equilibrium work

Consider a system initially in thermal equilibrium at temperature T, subjected to a time-dependent protocol λ(t) that changes the Hamiltonian from H(λ_0) to H(λ_1) over time τ. The work performed on the system in a single realization is:

    W = ∫_0^τ (∂H/∂λ)(dλ/dt) dt

W is a random variable — different realizations of the same protocol yield different work values due to thermal fluctuations.

### 4.2 Jarzynski equality

**Statement**: For any protocol λ(t), no matter how fast or far from equilibrium:

    ⟨e^{-βW}⟩ = e^{-βΔF}

where ΔF = F(λ_1) - F(λ_0) is the equilibrium free energy difference between the initial and final Hamiltonians, and ⟨·⟩ averages over all realizations.

This is remarkable: the left side involves a non-equilibrium average over possibly violent, far-from-equilibrium processes. The right side involves only equilibrium free energies. The Jarzynski equality bridges non-equilibrium dynamics to equilibrium thermodynamics.

### 4.3 Connection to the second law

By Jensen's inequality (⟨e^X⟩ ≥ e^{⟨X⟩}):

    e^{-β⟨W⟩} ≤ ⟨e^{-βW}⟩ = e^{-βΔF}

Therefore:

    ⟨W⟩ ≥ ΔF

This is the second law for isothermal processes: the average work performed is at least the free energy difference. The Jarzynski equality is stronger — it gives the exact relation, not just the inequality.

### 4.4 Crooks fluctuation theorem

**Statement**: For a forward protocol λ(t) and its time-reverse λ̃(t) = λ(τ-t):

    P_F(W) / P_R(-W) = e^{β(W - ΔF)}

where P_F(W) is the work distribution under the forward protocol and P_R(-W) under the reverse.

Crooks implies Jarzynski (integrate both sides against e^{-βW}), but is stronger: it gives the full ratio of forward and reverse work distributions, not just the exponential average.

### 4.5 Quantum version and measurement backaction

In quantum mechanics, work is not a standard observable (there is no "work operator" — work depends on the process, not the state). The quantum Jarzynski equality requires a two-point measurement protocol:

1. Measure energy at t = 0: obtain E_m
2. Evolve under H(λ(t)) for time τ
3. Measure energy at t = τ: obtain E_n
4. Define work: W = E_n - E_m

The two measurements disturb the system — step 1 destroys coherences in the energy eigenbasis. This measurement backaction is the quantum correction to the classical Jarzynski equality. In L0 terms: the act of defining work (measuring energy twice) is itself an observation that costs information, through the same mechanism as q_quantum_observation.md §6.

For coherence-preserving protocols (no intermediate measurements), the quantum Jarzynski equality takes a modified form involving the quantum relative entropy between forward and reverse processes.

### 4.6 FDT → Jarzynski: the generalization

QSM §5 (FDT) relates fluctuations to dissipation in the linear response regime (small perturbations near equilibrium). Jarzynski generalizes this to arbitrary perturbations:

    FDT:        S(ω) ∝ Im χ(ω)              (linear, equilibrium)
    Jarzynski:  ⟨e^{-βW}⟩ = e^{-βΔF}        (nonlinear, non-equilibrium)

In the limit of slow (quasi-static) protocols, Jarzynski reduces to ⟨W⟩ = ΔF (reversible work), and the work fluctuations around this mean are governed by the FDT. Jarzynski is the exact, all-orders version of what FDT captures at leading order.

The three-stage rocket so far:
1. **FDT** (QSM §5): fluctuation = dissipation (linear, equilibrium)
2. **Jarzynski** (this section): non-equilibrium work ↔ equilibrium free energy (nonlinear, any protocol)
3. **Landauer** (§5 next): information erasure ↔ heat dissipation (information-theoretic)

---

## §5 Landauer Principle

### 5.1 Statement

**Landauer principle**: Erasing one bit of information from a physical memory requires dissipating at least kT ln 2 of heat into the environment:

    Q_dissipated ≥ kT ln 2 · (ΔI)

where ΔI is the information erased (in bits). Equality holds for a quasi-static, reversible erasure process.

### 5.2 Derivation from the second law

Consider a memory register with two states (one bit). Before erasure, the register is in a maximally mixed state ρ_init = I/2 (unknown bit). After erasure, it is in a known state ρ_final = |0⟩⟨0| (reset to 0).

The entropy change of the register:

    ΔS_register = S(ρ_final) - S(ρ_init) = 0 - k ln 2 = -k ln 2

The second law requires total entropy to not decrease:

    ΔS_total = ΔS_register + ΔS_environment ≥ 0

Therefore:

    ΔS_environment ≥ k ln 2

Since the environment is a heat bath at temperature T, ΔS_environment = Q/T, giving:

    Q ≥ kT ln 2

### 5.3 Why Landauer is the crown jewel

The Landauer principle is not just a thermodynamic inequality — it is the fundamental bridge between information theory and physics. It states:

**Information is physical. Erasing information has an irreducible thermodynamic cost.**

In the σφ framework, this is the most direct statement of the finite observation philosophy:

1. **L0's finite observer** has finite memory (window W is finite)
2. To make room for new observations, the observer must erase old ones
3. Each erasure dissipates at least kT ln 2 per bit
4. Therefore, **observation has a running thermodynamic cost**

This connects directly to the σφ information-theoretic objects:
- **D_floor** (the irreducible distortion floor): just as D_floor sets a lower bound on observation error, Landauer sets a lower bound on observation cost
- **R(D) rate-distortion**: the observer chooses how much information to retain (rate R) at what cost (distortion D). Landauer adds: and the discarded information has a physical price per bit
- **σ* = √(2 ln 2)**: the phase noise threshold. Note that σ*² = 2 ln 2 and kT ln 2 = kT · σ*²/2. Whether this numerical coincidence is structural or accidental is OQ-QTD3 (§10)

### 5.4 Quantum Landauer principle

For quantum systems, the Landauer bound generalizes:

    Q ≥ kT · [S(ρ_init) - S(ρ_final)]

This is the quantum Landauer principle: the heat dissipated is bounded by the entropy decrease of the system. For one classical bit, S(ρ_init) - S(ρ_final) = ln 2, recovering the classical result.

The quantum version is tighter when the initial state has coherences. A coherent superposition (1/√2)(|0⟩ + |1⟩) has S = 0 (pure state), so erasing it by projecting onto |0⟩ costs zero heat — the entropy doesn't change. But the coherence is destroyed, which constitutes a different kind of information loss (decoherence, not erasure). The Landauer bound captures only the entropic (classical) cost, not the coherence (quantum) cost.

This asymmetry between classical and quantum information loss is structurally important: it means the thermal window (which sees entropy) and the spectral window (which sees coherence) measure different aspects of information. This supports QSM §7.2 (OQ-QSM4): the two windows may be genuinely independent.

### 5.5 Jarzynski → Landauer: the connection

Erasure is a specific protocol: λ(t) takes H from a symmetric double-well (two degenerate states) to a single well (one state). Applying Jarzynski (§4.2) to this protocol:

    ⟨e^{-βW}⟩ = e^{-βΔF}

The free energy difference for erasure: ΔF = F_final - F_initial = 0 - (-kT ln 2) = kT ln 2. Therefore:

    ⟨e^{-βW}⟩ = e^{-β · kT ln 2} = 1/2

And by Jensen: ⟨W⟩ ≥ kT ln 2, recovering Landauer. The Jarzynski equality gives more: it gives the full work distribution for erasure, not just the bound.

The three-stage rocket is now complete:

```
QSM §5 FDT                    QTD §4 Jarzynski              QTD §5 Landauer
(equilibrium, linear)    →     (non-equilibrium, any)   →    (information, one bit)
fluctuation=dissipation        ⟨e^{-βW}⟩ = e^{-βΔF}         Q ≥ kT ln 2
                         generalize                    specialize to erasure
                         protocol                      protocol
```

Each stage is a crown jewel of its section. The chain FDT → Jarzynski → Landauer ascends from physics to information theory, which is exactly the direction σφ's B-spine travels: from physical substrate toward the observer.

### 5.6 Landauer and the observer's budget

In L0, the observer has a finite window W and performs observations that yield patterns m(S|_W). The Landauer principle adds a constraint the L0 axioms do not currently capture: **observation has a physical cost**.

An observer making N observations, each retaining R bits, must erase at least N·R bits of prior state to process the next. The total heat budget:

    Q_total ≥ NR · kT ln 2

This is the thermodynamic running cost of being a finite observer. A more efficient observer (lower R, higher D distortion floor) pays less per observation but gets less information. The rate-distortion tradeoff R(D) thus has a thermodynamic interpretation:

    Thermal cost per observation = R(D) · kT ln 2

This is the thermodynamic dual of the information-theoretic rate-distortion function. Whether this should be incorporated into L0 as a new axiom (an "observation cost" axiom) or remains a derived QTD consequence is OQ-QTD1 (§10).

### 5.7 OQ-QSM5 litmus test: does Landauer require E?

The Landauer bound Q ≥ kT ln 2 depends on a single environmental parameter: the bath temperature T. The derivation (§5.2) requires only:
- A system with well-defined entropy (von Neumann S)
- An environment at temperature T (a thermal bath)
- The second law (entropy non-decrease)

No additional environmental parameter E (coarse-graining scale, decoherence rate, etc.) is required. The bound is universal for any bath at temperature T, regardless of the bath's internal structure or the system-bath coupling details.

**Verdict on OQ-QSM5**: The Landauer derivation does NOT spontaneously require an environmental window variable E beyond temperature. Combined with the QSM §2 observation (KMS derivation from A0c outlined without needing E), this is cumulative evidence that E is formalism freedom, not structure. However, this conclusion is provisional: both tests used the standard (infinite, Markovian) bath assumption. A finite bath or non-Markovian bath might introduce corrections that effectively parametrize an E. This remains open but the weight of evidence is against E being structurally necessary.

---

## §6 Phase Transitions and the Thermodynamic Limit

### 6.1 Finite vs infinite

For finite systems (L0's domain), the partition function Z(β) is an entire function of β and the free energy F(β) is smooth everywhere. There are no phase transitions in finite systems — only crossovers.

Phase transitions emerge as singularities of the free energy density in the thermodynamic limit:

    f(β) = lim_{N→∞} -(1/Nβ) log Z_N(β)

where Z_N is the partition function for N particles. The singularity types classify phase transitions:
- First order: discontinuity in ∂f/∂β (latent heat)
- Second order (continuous): divergence in ∂²f/∂β² (divergent susceptibility)
- Higher order: Ehrenfest classification

### 6.2 Symmetry breaking

Most phase transitions involve spontaneous symmetry breaking: the Hamiltonian has a symmetry G, but the equilibrium state below a critical temperature T_c does not. The order parameter ψ measures the broken symmetry:

    ψ = 0 for T > T_c (symmetric phase)
    ψ ≠ 0 for T < T_c (broken phase)

In KMS language (QSM §2): above T_c, the KMS state is unique and G-invariant. Below T_c, multiple KMS states exist (one for each symmetry-broken sector), and the system selects one. The failure of uniqueness is the signature of phase transition in the algebraic framework.

### 6.3 L0 interpretation

Phase transitions are where the thermodynamic coarse-graining breaks down: the smooth mapping from microscopic (QSM) to macroscopic (QTD) develops a singularity. In L0 terms, the thermal window W_β has a critical value β_c where the window's resolution undergoes a qualitative change — the pattern m(S|_{W_β}) changes discontinuously (first order) or its derivatives diverge (continuous).

This connects to c_scaling_laws.md: near a continuous phase transition, observables scale as power laws with universal exponents. The sigmoid structure (c_scaling_laws.md thesis) may modify this: near T_c, the crossover from one regime to another is a sigmoid in 1/T, and the "power law" is the local slope of the sigmoid at the inflection point. This is speculative (OQ-QTD4, §10).

### 6.4 Quantum phase transitions

At T = 0, phase transitions occur as a function of a non-thermal control parameter g (magnetic field, pressure, coupling constant). These are quantum phase transitions: the ground state changes qualitatively at g = g_c.

Quantum phase transitions are driven by quantum fluctuations (uncertainty principle), not thermal fluctuations. In the (W_spectral, W_thermal) framework (QSM §7.2, OQ-QSM4): thermal phase transitions are singularities along the W_thermal direction, quantum phase transitions are singularities along the W_spectral direction. This is another argument for the 2D window structure.

---

## §7 L0 Translation Table

### 7.1 Dictionary

| QTD concept | L0 concept | Section |
|---|---|---|
| Free energy F | Optimal observation cost at temperature T | §1.2 |
| Legendre transform | Gauge change between observation modes | §2.2 |
| Maxwell relations | Consistency of the gauge web | §2.3 |
| Second law | Information loss monotonicity (CPTP) | §3.4 |
| Jarzynski equality | Non-equilibrium ↔ equilibrium via exponential average | §4.2 |
| Landauer bound | Irreducible cost of observation (kT ln 2 per bit) | §5.3 |
| Phase transition | Singularity in the thermal window | §6.3 |
| Order parameter | Symmetry-breaking pattern | §6.2 |
| Reversible process | Observation that preserves full information | §4.3 |
| Irreversibility | Information loss through thermal window | §3.4 |

### 7.2 The observation cost principle

QTD adds to the L0 translation something QSM did not: a cost structure for observation. QSM's L0 translations (QSM §7) were structural — what the thermal window reveals and what it hides. QTD's crown jewel (Landauer) adds an operational dimension: the window has a running cost.

The full L0 picture as of QTD:
- **L0 axioms**: What can be observed (window structure, partial access, gauge invariance)
- **QSM**: What thermal equilibrium looks like through the window (Gibbs, KMS, FDT)
- **QTD**: What observation costs (Landauer bound), and what happens when the window's resolution changes qualitatively (phase transitions)

### 7.3 Window update

The thermal window W_β introduced in QSM §7.2 now has richer structure:

- **Smooth regime** (T ≠ T_c): small changes in β produce small changes in m(S|_{W_β}). Thermodynamics is analytic.
- **Critical regime** (T = T_c): the window response diverges. Universality classes describe the divergence type.
- **Information cost**: maintaining the window at temperature T costs kT ln 2 per bit of processed observation.

The three-stage chain QSM → QTD in window language:
1. QSM: window exists and has spectral + thermal parameters
2. QTD §1-§3: window has Legendre gauge structure
3. QTD §4-§5: window has an operational cost (Landauer)
4. QTD §6: window has critical points (phase transitions)

---

## §8 Control Theory Connection

### 8.1 Thermodynamic control

Where QSM §8 discussed thermal control (controlling systems at finite temperature), QTD control concerns the thermodynamic protocol itself: how to design the time-dependent Hamiltonian λ(t) to achieve a desired thermodynamic transformation optimally.

| QTD setting | Control theory analogue |
|---|---|
| Protocol λ(t) | Control input u(t) |
| Work W[λ] | Control cost J[u] |
| Jarzynski ⟨e^{-βW}⟩ = e^{-βΔF} | Cost identity (moment generating function of cost) |
| Reversible protocol (⟨W⟩ = ΔF) | Optimal control (minimum cost) |
| Landauer bound | Fundamental controllability limit |
| Phase transition | Bifurcation in the controlled system |

### 8.2 Optimal thermodynamic protocols

The question "what protocol λ(t) minimizes the average dissipated work ⟨W⟩ - ΔF?" is an optimal control problem. The solution (for linear-response regime) involves the thermodynamic metric:

    g_ij = β² Cov(X_i, X_j)

where X_i are the conjugate forces. The optimal protocol follows a geodesic in this metric — the path of minimum dissipation. This thermodynamic geometry (Ruppeiner/Weinhold geometry) connects thermodynamics to differential geometry.

In L0 terms: the thermodynamic metric measures the cost of moving the observation window. Moving faster (further from geodesic) costs more dissipation. The Landauer bound is the irreducible cost at zero speed; the thermodynamic metric governs the excess cost at finite speed.

---

## §9 Bridge to Many-Body Quantum

### 9.1 What this file establishes

- Free energy as the central thermodynamic quantity (§1)
- Legendre structure as the gauge web of thermodynamics (§2)
- Thermodynamic laws as emergent from QSM (§3)
- Jarzynski-Crooks as non-equilibrium ↔ equilibrium bridge (§4)
- Landauer principle as information-thermodynamics bridge (§5)
- Phase transitions as window singularities (§6)

### 9.2 What q_many_body_quantum.md adds

The next step in the B-spine (academic_tree §5): QTD → many_body.

**New structure**: explicit many-particle interactions. Where QTD treats the system as a black box with thermodynamic variables, many-body quantum asks: what is the system made of? How do its constituents interact?

**Preserved**: thermodynamic potentials, phase transition framework, Landauer bound
**Lost**: material-independence → replaced by specific Hamiltonians (lattice models, continuum fields, interacting particles)

**Key new objects**:
- Second quantization (creation/annihilation operators)
- Mean field theory / Hartree-Fock (variational many-body states)
- Born-Oppenheimer approximation (separation of nuclear and electronic scales)
- Quasiparticles (emergent excitations of the interacting system)

### 9.3 Arrow structure

```
q_quantum_statistical_mechanics.md    q_quantum_thermodynamics.md         q_many_body_quantum.md
(thermal, KMS)                 →    (thermodynamic, Legendre)    →    (interacting, 2nd quantization)
                            thermo limit                       + interactions
      preserves: Gibbs, Z            preserves: potentials, phases
      loses: correlations             loses: material-independence
```

### 9.4 S12/S15 接続 (2026-04-11)

| S-ID | 本ファイルとの関係 | 層 |
|---|---|---|
| S15 | **Scan**: 本ファイルは QSM の Z(β) (Scan) の下流。Legendre 変換 F→S が Arrow 2 の終点。**Structural**: phase diagram topology (相数, 臨界指数の universality class)。**Information**: thermodynamic entropy S, free energy F = -kT log Z, Landauer bound kT ln 2 | Arrow 2 終点 + Information |
| Arrow 2 | **本ファイルが Arrow 2 の終点**: QSM Z(β) → F = -kT log Z → S = -∂F/∂T → Legendre 変換で全 potential を生成。Scan → Information の chain がここで完結 | Scan → Information (完結) |
| S13 | Landauer bound kT ln 2 (§5) は Arrow 2 上の S13 固定点の熱力学的 instance。e^{-βE} = 1/2 ⟹ E = kT ln 2 | Arrow 2 固定点 |

参照: bidirectional_duality_v0.md §5.5 Arrow 2, theorems_master S13/S15。

---

## §10 Open Questions

**OQ-QTD1** (structural, high priority): Should L0 include an "observation cost" axiom based on Landauer?

The current L0 axioms (A0 partial access, A1 arithmetic, A2 irreducibility, A3 gauge invariance) describe what can be observed, not what observation costs. Landauer (§5) shows that observation has an irreducible thermodynamic cost of kT ln 2 per bit erased. If this is structural (not merely a QTD consequence), L0 should include a cost axiom: "observation consumes resources proportional to the information processed."

**Test**: Does the cost axiom produce new constraints at the L0 level that cannot be derived from A0-A3 alone? If yes, it is a genuine new axiom. If all Landauer-type consequences can be derived from A0-A3 + QSM + QTD, the cost axiom is redundant.

**OQ-QTD2** (non-equilibrium, medium priority): Is there a KMS-like algebraic condition for non-equilibrium steady states?

Jarzynski and Crooks (§4) relate non-equilibrium processes to equilibrium free energies, but they do not characterize non-equilibrium steady states algebraically. A "non-equilibrium KMS condition" would extend QSM §2 beyond equilibrium. Candidates: the Gallavotti-Cohen fluctuation theorem, the Evans-Searles transient fluctuation theorem.

If such a condition exists, the QSM → QTD arrow has a parallel non-equilibrium branch, and the B-spine bifurcates into equilibrium and non-equilibrium pathways.

**OQ-QTD3** (numerical): Is the coincidence σ*² = 2 ln 2 ↔ kT ln 2 structural?

**Status: RESOLVED via S13 ESTABLISHED (2026-04-10/11).**

S13 (ln 2 Fixed-Point Principle, **ESTABLISHED**): S12 exponential scan family の乗法 scan に対し、半値条件 e^{-x} = 1/2 ⟹ x = ln 2 が σ*, Landauer, Shannon の共通構造。旧 ℤ/2ℤ retraction に抵触しない (S13 は S12+threshold を root とし、次元的等式を主張しない)。3 guards 付き、全昇格条件 CLOSED。

**S15 residence (2026-04-11)**: S13 は S15 Observable Trichotomy の **Arrow 2 (Scan → Information) 上の cross-layer 固定点**。Landauer の kT ln 2 は Scan 層 (Z(β) = Σ e^{-βE}) から Information 層 (S = -∂F/∂T) への log bridge 上で ln 2 が出現する instance。詳細: bidirectional_duality_v0.md §5.6, theorems_master S13/S15。

Both ln 2 values involve binary-related structures:
- Landauer: 2 states → S = k ln 2 → erasure cost kT ln 2. The "2" is state count. Generalizes to m states: Q ≥ kT ln m.
- σ*: half-amplitude criterion E[cos Z] = 1/2 → e^{-σ²/2} = 1/2 → σ² = 2 ln 2. The specific value depends on the half-amplitude convention (E[cos Z]=1/2).

**What survives**:
- σ* = √(2 ln 2) is confirmed as derivable (Paper_C.tex Thm C.8). The Gaussian characteristic function e^{-σ²/2} and half-amplitude threshold (E[cos Z]=1/2) are standard, not ad hoc.
- Both Landauer and σ* involve "bipartition" in some sense.

**What is retracted** (audit 2026-04-08):
- ~~"Shared root is ℤ/2ℤ uniform measure"~~: Overclaim. Landauer's "2" is state count (generalizes to m). σ*'s "2" is half-amplitude convention (E[cos Z]=1/2) (changes if threshold changes). "Bipartition," "binary choice," and "ℤ/2ℤ group structure" are distinct concepts — conflating them was force fitting.
- ~~"kT ln 2 = kT · σ*²/2 is structural"~~: The equation just says both contain ln 2. Dimensionally incoherent as a physical relation.

**σ* Type I status** (revised): σ* remains Type I-a (derivable) but with a caveat: the specific value √(2 ln 2) depends on the half-amplitude convention (E[cos Z]=1/2). The structural content is the Gaussian characteristic function decay form e^{-σ²/2}; the specific threshold that produces ln 2 is convention. See threshold invariance test in OQ-QTD6.

**Remaining question → OQ-QTD6**: Is the co-occurrence of log-family and quadratic-family constants under A1 structurally meaningful, or just standard mathematics (Shannon + CLT) being re-labeled?

**OQ-QTD4** (scaling, speculative): Are critical exponents sigmoid slopes?

From §6.3: near a continuous phase transition, observables scale as power laws with universal exponents. c_scaling_laws.md argues that power laws are local slopes of global sigmoids. If this applies to phase transitions, the critical exponent α is the slope of a sigmoid in 1/T at T_c, and universality classes correspond to sigmoid shape parameters. This would unify phase transition phenomenology with the σφ sigmoid framework.

**OQ-QTD5** (OQ-QSM5 verdict): Environmental window variable E is probably not structural.

Status: resolved (provisional). Two independent tests — KMS derivation from A0c (QSM §2.5) and Landauer derivation (§5.7) — did not require E. The standard bath assumption (infinite, Markovian, characterized by T alone) suffices for both. E may become relevant for finite/non-Markovian baths, but this is a correction, not a structural feature. Do NOT write `observation_environment.md`. Revisit only if a future derivation requires E where T alone fails.

**OQ-QTD6** (observational, medium priority): Do log-family and Gaussian/quadratic-family constants co-occur under A1?

**Observation**: Theories with independent additive structure (A1-type) tend to produce two families of universal constants:
1. **Log family**: log, ln 2, Shannon entropy — from functional equation H(AB) = H(A) + H(B) (Shannon 1948 uniqueness theorem)
2. **Gaussian/quadratic family**: 1/2, Gaussian σ², equipartition — from limit theorem Var(X+Y) = Var(X) + Var(Y) (CLT)

Both families appear frequently in A1-like settings. This is an observational pattern, not a theorem.

**What is NOT claimed** (audit 2026-04-08):
- ~~"Dual projection of A1"~~: Retracted. Shannon's theorem is an axiomatic characterization; CLT is a limit theorem. These are different types of results. No explicit map (projection, functor, or morphism) connects them. The word "projection" was premature — it requires a mathematical object that does not yet exist.
- ~~"ℤ/2ℤ is the common root"~~: Retracted as overclaim. The ln 2 in σ* depends on the half-power threshold choice (e^{-σ²/2} = 1/2); changing the threshold to 1/e gives σ² = 2, to 1/4 gives σ² = 4 ln 2. The specific value ln 2 is partially convention (half-power ≡ -3dB standard), not purely structural. Binary distinguishability is a useful heuristic but ℤ/2ℤ group structure is a stronger claim than the evidence supports. "Bipartition," "binary choice," and "ℤ/2ℤ symmetry" are distinct concepts that should not be conflated.
- ~~"4/5 hit rate exceeds threshold"~~: Retracted. The 4 confirmed cases (Shannon-Hartley, Boltzmann H, Nyquist, Fisher) are from the same log/likelihood/entropy clan, not independent domains. Independent evidence weight is ≤ 2, not 4.

**What IS claimed** (survives audit):
- Under independent additive structure, log-type and Gaussian/quadratic-type universality both appear. This is well-known mathematics (Shannon 1948, CLT), not a ΣΦ discovery.
- The ΣΦ-specific content is the **observation that both families have L0-relevant instances** (Landauer, equipartition, FDT, σ*) — i.e., they appear in observation-theoretic contexts, not just pure mathematics.
- σ* = √(2 ln 2) is confirmed as derivable (Paper_C.tex Thm C.8), but its ln 2 is partially threshold-dependent (half-amplitude convention (E[cos Z]=1/2)). The structural component (Gaussian characteristic function decay) is real; the specific value ln 2 is convention-entangled.

**Required for upgrade to structural claim**:
1. **Explicit bridge theorem**: A single mathematical statement from which both Shannon uniqueness and CLT follow as corollaries. Without this, "two families under A1" is taxonomy, not structure.
2. **Pre-registered audit table**: 20-30 candidates with predictions (log / quadratic / mixed / negative) and judgment criteria fixed before evaluation. Current post-hoc scoring is not credible.
3. **Origin taxonomy** with clear boundaries:
   - Structural origin (derivable from axioms alone)
   - Threshold/convention origin (depends on arbitrary cutoff choice)
   - Geometric origin (depends on space/metric structure)
   - Measurement origin (depends on experimental protocol)
4. **Threshold invariance test for σ***: How does the "observation-origin constant" change when the half-amplitude criterion (E[cos Z]=1/2) is replaced by 1/e-power or 1/4-power? If it moves freely, the constant is convention, not structure.
5. **Non-binary test**: If the pattern holds for m-ary systems (m > 2), the root is general finite partition, not ℤ/2ℤ specifically. Check Landauer for m-state erasure: Q ≥ kT ln m. The ln m generalization suggests the root is "finite distinguishability," not "binary" specifically.

**Hidden constant detection protocol**: See physics_constants_decomposition.md §7. The protocol itself (subtract known exact values, examine residual) is methodologically sound regardless of the dual projection status. Known instances:
- alpha_eff ≈ 0.76 in FX: c_s² + edge correction (finite_observation.md §7.5) — confirmed structural
- σ* ≈ 1.18 in EEG: √(2 ln 2) (Paper_C.tex) — confirmed derivable, convention-entangled
- φ_eff/φ ≈ 0.37 in connectome: 1/e candidate — unconfirmed, needs time-series fit with pre-registered prediction

**Falsification test results** (2026-04-08):

**F3 (Threshold invariance)**: σ*² = -2 ln α where α is threshold. σ* moves freely with threshold choice.
- α = 1/√2 (half-power): σ² = ln 2
- α = 1/2 (half-amplitude, σ* actual): σ² = 2 ln 2
- α = 1/e: σ² = 2
- α = 1/m (general): σ² = 2 ln m
**Result**: σ* is threshold-dependent. The specific value 2 ln 2 follows from α = 1/2.
**Note**: Paper_C.tex Thm C.8 contained a text error — stated "E[cos Z] = 1/√2" but the actual threshold is E[cos Z] = 1/2 (confirmed by verify_all_claims.py). Erratum applied to Paper_C.tex.

**F4 (Non-binary)**: Both Landauer and σ* generalize to m-ary:
- Landauer: Q ≥ kT ln m (m-state erasure)
- σ*: σ²_m = 2 ln m (coherence drops to 1/m)
**Result**: ln 2 is the m=2 case of ln m. Root is "finite distinguishability" (general m), not "binary" (m=2 only). ℤ/2ℤ is the minimal nontrivial example but not the unique source.

**Combined assessment**: Both tests confirm the audit's verdict — ℤ/2ℤ reduction is overclaim. The structural content of σ* is the Gaussian characteristic function form e^{-σ²/2}. The specific constants (ln 2, 2 ln 2) depend on threshold choice (convention) and partition size m (which instance of finite distinguishability).

**Status**: Observational pattern. Not a structural claim. Priority: medium. Upgrade path: items 1-5 above + F3/F4 results integrated.

---

*作成日: 2026-04-08*
*最終更新: 2026-04-08*
