---
axis: B
position: open_quantum_systems
static_dynamic: both
connected_to:
  - B.quantum_mechanics
  - B.quantum_statistical
  - A.algebra_analysis
  - C.control_theory
  - C.complex_systems
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-08
---

# Open Quantum Systems

**Level**: L1 (domain-independent mathematical structure)
**Dependencies**: q_quantum_observation.md (§5 テンソル積, §6 Born則, §7 c_s²), c_phase_complex.md (§5 c_s²/log 2 双子)
**Downstream**: q_quantum_statistical_mechanics.md (done), L2 domain-specific bath models

---

## §0 Thesis

An open quantum system is a quantum system observed through a finite window. The window is the partial trace over the bath — the degrees of freedom the observer cannot access. This is L0's axiom A0b (partial access) realized in quantum mechanics.

Closed quantum mechanics (q_quantum_observation.md) describes the full system H_total with unitary evolution. Open quantum systems describe what happens when the observer sees only H_S ⊂ H_total. The passage from closed to open is the passage from S to m(S|_W): from the infinite structure to what the finite window reveals.

Three structures emerge that have no closed-system analogue:
1. **Mixed states**: pure entanglement in H_total appears as classical uncertainty in H_S (§3)
2. **Irreversible evolution**: unitary dynamics in H_total becomes dissipative dynamics in H_S (§4)
3. **Pointer basis selection**: the environment selects which observables survive decoherence (§5)

---

## §1 System-Bath Decomposition

### 1.1 Tensor product structure

The total Hilbert space decomposes as:

    H_total = H_S ⊗ H_B

with Hamiltonian:

    H_total = H_S ⊗ I_B + I_S ⊗ H_B + H_int

where H_S governs the system, H_B governs the bath, and H_int couples them.

### 1.2 The decomposition is observer-dependent

Which tensor factor is called "system" and which "bath" is **the observer's choice**. This choice is a gauge in the sense of L0 A3: it determines what is observable (H_S sector) and what is traced out (H_B sector). Different observers of the same H_total, choosing different S/B splits, obtain different reduced dynamics.

**L0 parallel**: The system-bath split is the quantum version of choosing the window W in the L0 triple (S, W, m). Just as the window determines the visible algebra (finite_observation.md §1.2), the S/B split determines which observables are accessible.

### 1.3 Interaction as the boundary

H_int lives on the boundary between S and B. It mediates:
- Information flow from S to B (decoherence, §5)
- Energy flow between S and B (dissipation, §4)
- Correlations that make ρ_total ≠ ρ_S ⊗ ρ_B (entanglement, §3)

The strength of H_int relative to H_S and H_B controls the regime:
- ||H_int|| ≪ ||H_S||: weak coupling → Born-Markov → Lindblad (§4)
- ||H_int|| ~ ||H_S||: strong coupling → non-Markovian → memory effects
- ||H_int|| ≫ ||H_S||: bath-dominated → system identity dissolves

---

## §2 Partial Trace as Window Operator

### 2.1 Definition

The **partial trace** over B maps density operators on H_total to density operators on H_S:

    ρ_S = Tr_B(ρ_total) := Σ_k ⟨e_k^B| ρ_total |e_k^B⟩

where {|e_k^B⟩} is any orthonormal basis of H_B. The result is independent of basis choice.

### 2.2 What survives, what is lost

| Survives (in ρ_S) | Lost (in Tr_B) |
|---|---|
| System-local expectation values ⟨A_S⟩ | System-bath correlations ⟨A_S ⊗ B_B⟩ - ⟨A_S⟩⟨B_B⟩ |
| Diagonal populations ⟨i|ρ_S|i⟩ | Entanglement structure (Schmidt coefficients individually) |
| Off-diagonal coherences ⟨i|ρ_S|j⟩ | Bath state ρ_B and its internal structure |

### 2.3 L0 translation

| Partial trace concept | L0 concept | Reference |
|---|---|---|
| ρ_total (full state) | S (infinite structure) | A0 |
| Tr_B (partial trace) | W (window operator) | A0b |
| ρ_S = Tr_B(ρ_total) | m(S\|_W) (observed value) | A0 §1.1 |
| Tr_B discards bath | Window hides unobservable structure | A0b (partial access) |
| ρ_S depends on S/B split | m depends on window choice | A3 (gauge dependence) |

### 2.4 Control theory translation

The partial trace is the quantum version of the output equation y = Cx (control_theory.md §1):

| Control theory | Open quantum systems |
|---|---|
| State x ∈ ℝ^n | ρ_total ∈ D(H_total) |
| Output matrix C | Tr_B (partial trace operator) |
| Output y = Cx | ρ_S = Tr_B(ρ_total) |
| Unobservable subspace ker(O) | Bath degrees of freedom H_B |
| Observable subspace im(O^T) | System degrees of freedom H_S |

---

## §3 Mixed States and Entanglement Entropy

### 3.1 Entanglement generates mixedness

If ρ_total = |ψ⟩⟨ψ| is pure (S(ρ_total) = 0) but entangled across S-B, then:

    S(ρ_S) = S(ρ_B) > 0

The reduced state is mixed **not because of classical ignorance** but because quantum correlations with the bath cannot be captured by ρ_S alone. This is the irreducible cost of partial observation (A0b) in quantum mechanics.

### 3.2 von Neumann entropy

    S(ρ) = -Tr(ρ log ρ) = -Σ_k λ_k log λ_k

where {λ_k} are eigenvalues of ρ. Bounds:

    0 ≤ S(ρ_S) ≤ log(dim H_S)

- S = 0: pure state (no entanglement with bath, or bath is trivial)
- S = log d: maximally mixed state (maximal entanglement with bath)

### 3.3 The log 2 connection

For dim H_S = 2 (qubit):

    S_max = log 2

This is the same log 2 from c_phase_complex.md §5, where it appeared as the Shannon entropy of the ℤ/2ℤ uniform measure (even/odd equipartition). The quantum version:

| c_phase_complex.md §5 | Open quantum systems |
|---|---|
| ℤ/2ℤ uniform measure | Maximally mixed qubit ρ_max = I/2 |
| H(1/2) = log 2 (Shannon) | S(ρ_max) = log 2 (von Neumann) |
| c_s² = 1/2 (Born expectation) | Tr(ρ_max²) = 1/2 (purity) |
| Source: integer parity symmetry | Source: maximal S-B entanglement |

The Shannon and von Neumann entropies agree for diagonal ρ (classical limit). The passage from Shannon to von Neumann is the passage from c_phase_complex.md (commutative) to q_quantum_observation.md (non-commutative), with log 2 as the invariant that survives the lift.

### 3.4 Entropy as an observable (A2 connection)

S(ρ_S) is a function of the observation window (S/B split). As the window expands (dim H_S increases while dim H_total is fixed):

- S(ρ_S) first increases (more of the bath is included → more entropy)
- S(ρ_S) then decreases (approaching the pure total state)
- S(ρ_S) = 0 when H_S = H_total (full system is pure)

This non-monotonic behavior is an instance of A2 (convergence rate as observable): the rate at which S(ρ_S) approaches 0 as dim H_S → dim H_total encodes the entanglement structure of ρ_total. The **Page curve** (average S for random bipartitions) quantifies the typical case.

---

## §4 Lindblad Master Equation

### 4.1 Derivation context

Under the Born-Markov approximation (weak coupling, fast bath relaxation), the reduced dynamics of ρ_S obeys:

    dρ_S/dt = -i[H_eff, ρ_S] + D[ρ_S]

where:
- H_eff = H_S + Lamb shift (unitary part, modified by bath)
- D[ρ] = Σ_k γ_k (L_k ρ L_k† - (1/2){L_k†L_k, ρ}) (dissipator)

The Lindblad operators {L_k} and rates {γ_k ≥ 0} encode the bath's effect on the system.

### 4.2 CPTP and Kraus representation

The Lindblad equation generates a one-parameter semigroup of **completely positive trace-preserving** (CPTP) maps:

    Φ_t: ρ_S(0) ↦ ρ_S(t)

Any CPTP map admits a Kraus decomposition:

    Φ(ρ) = Σ_k K_k ρ K_k†,    Σ_k K_k† K_k = I

The Kraus operators {K_k} are the quantum analogues of stochastic transition matrices. K_0 ≈ I - (i H_eff + (1/2)Σ γ_k L_k†L_k)dt captures the coherent + decay part; K_k ≈ √(γ_k dt) L_k for k ≥ 1 capture quantum jumps.

### 4.3 Unitary vs dissipative: L0 A1 decomposition

The Lindblad equation separates into two structurally distinct parts:

| Component | Expression | Time-reversal | L0 error type |
|---|---|---|---|
| Unitary (Hamiltonian) | -i[H_eff, ρ] | Reversible | error_arithmetic (inherent to S) |
| Dissipative (Lindblad) | D[ρ] | **Irreversible** | error_projection (window-dependent) |

**Justification of the mapping**:
- The Hamiltonian part is intrinsic to the system (it persists even if the bath is removed). It generates phase evolution that is reversible — corresponding to error_arithmetic, which is inherent to S and cannot be reduced by better observation.
- The dissipative part arises from tracing out the bath. It is **window-dependent**: a different S/B split yields different {L_k, γ_k}. It is irreversible — corresponding to error_projection, which depends on the observer's gauge choice.

**OQ-OQS2 RESOLVED 2026-04-28** (theorem upgrade complete, see §9 for full statement): the bijection is **canonical at the generator (superoperator) level** but **mixed at the discrete Kraus operator level**. At the generator level: $\mathcal{L} = \mathcal{L}_H + \mathcal{D}$ with $\mathcal{L}_H \rho = -i[H,\rho] \leftrightarrow$ error_arithmetic and $\mathcal{D}\rho = \sum_k \gamma_k(L_k \rho L_k^\dagger - \tfrac{1}{2}\{L_k^\dagger L_k, \rho\}) \leftrightarrow$ error_projection. At the Kraus level: $K_0(dt) \approx I - i H_\text{eff} dt$ with $H_\text{eff} = H - (i/2)\sum_k \gamma_k L_k^\dagger L_k$ bundles unitary phase + anticommutator damping, so the L0 partition does not refine to individual Kraus operators. Closest-unitary diamond-norm interpretation: $\|\Phi_{dt} - U_*^{(dt)}\|_\diamond = \|\mathcal{D}\| dt + O(dt^2)$ (q_open §9 attack route as corollary). See `research/oq_oqs2_kraus_l0_bijection_v0.md` for theorem statement + V1/V2/V3 numerical verification (pure dephasing + amplitude damping instances, Kraus = Lindblad to ~1e-16).

### 4.4 Noise (error_noise) in the quantum setting

The third L0 error component — error_noise (finite-N sampling, ~5-10%) — appears in quantum systems as:

- **Quantum shot noise**: finite number of measurements to estimate ⟨A⟩
- **Quantum projection noise**: variance of measurement outcomes for non-eigenstate ρ

This is distinct from D[ρ] (which is a property of the dynamics, not the measurement statistics). The three-component decomposition survives:

    total error = Hamiltonian (arithmetic) + Lindblad (projection) + measurement statistics (noise)

---

## §5 Decoherence, Einselection, and Pointer Basis

### 5.1 Decoherence as off-diagonal decay

In the pointer basis {|i⟩} selected by H_int, the reduced density matrix evolves as:

    ⟨i|ρ_S(t)|j⟩ ~ ⟨i|ρ_S(0)|j⟩ · exp(-Γ_{ij} t)    (i ≠ j)

where Γ_{ij} > 0 are decoherence rates determined by the Lindblad operators. Diagonal elements (populations) evolve on a slower timescale (relaxation). The separation of timescales:

    τ_decoherence ≪ τ_relaxation

is generic for macroscopic baths.

### 5.2 Einselection: environment selects the gauge

The pointer basis is the eigenbasis of the **system observable that commutes with H_int**:

    [|i⟩⟨i|, H_int] ≈ 0

This is **not** chosen by the observer — it is imposed by the environment. Different environments (different H_int) select different pointer bases.

**L0 A3 connection**: In L0, gauge choice (which window to use) is the observer's decision. In decoherence theory, the environment makes this choice for the observer. Einselection is **dynamical gauge fixing**: the gauge that survives is the one stable under environmental coupling.

**Implications**:
- L0 A3 (static): the observer chooses W, and amplitude is gauge-invariant
- Decoherence (dynamic): the environment chooses the pointer basis, and diagonal populations are "gauge-invariant" (they survive decoherence)
- The passage from static to dynamic gauge is the passage from L0 to open quantum systems

### 5.3 Decoherence completes the commutative limit

After decoherence (t ≫ τ_decoherence):

    ρ_S(t) ≈ Σ_i p_i |i⟩⟨i|    (diagonal in pointer basis)

This is a **commutative** state — it is equivalent to a classical probability distribution {p_i}. All off-diagonal coherences (the non-commutative content) have been suppressed.

**q_quantum_observation.md §8 connection**: §8 listed the condition for commutative limit as [A, B] = 0. Decoherence achieves this operationally: after decoherence, the system's effective algebra is commutative, and all structures reduce to c_phase_complex.md / c_spectral.md.

This is the mechanism by which the quantum world "becomes classical." The commutative limit is not an assumption (as in q_quantum_observation.md §8) but a **dynamical consequence** of environmental coupling.

### 5.4 OQ-OQS3: Decoherence and c_s² = 1/2

The maximally decohered qubit state is ρ_max = I/2, which gives:

    c_s² = Tr(ρ_max · Π_even) = 1/2    (q_quantum_observation.md §7)
    S(ρ_max) = log 2                      (§3.3 above)

If the environment is parity-symmetric (H_int commutes with parity), the pointer basis is {|even⟩, |odd⟩}, and maximal decoherence drives any initial state to ρ_max = I/2.

**Structural prediction**: c_s² = 1/2 is not merely a property of the ℤ/2ℤ uniform measure (c_phase_complex.md §5). It is the **dynamical fixed point** of parity-symmetric decoherence. Any qubit coupled to a parity-symmetric bath will decohere to ρ_max = I/2, generating c_s² = 1/2 as the steady-state Born expectation.

This connects three levels:
- L1-base (c_phase_complex.md §5): c_s² = 1/2 from integer parity (static, algebraic)
- L1-fiber (q_quantum_observation.md §7): c_s² = 1/2 from Born rule on ρ_max (static, quantum)
- Open QS (this file §5.4): c_s² = 1/2 from decoherence fixed point (dynamic, environmental)

**Status**: Structural prediction. The three derivations give the same value, but the claim that decoherence *generates* rather than merely *permits* c_s² = 1/2 requires showing that parity-symmetric environments are generic (not special). This is OQ-OQS3.

---

## §6 L0 Translation Table

| L0 Axiom | Open Quantum Systems realization | Section |
|---|---|---|
| A0a (finiteness) | dim H_S < ∞ (finite system Hilbert space) | §1 |
| A0b (partial access) | Tr_B: observer sees ρ_S, not ρ_total | §2 |
| A0c (multi-window compatibility) | Different S/B splits of same H_total give consistent predictions for shared observables | §1.2 |
| A1 (structured error) | Lindblad: unitary (arithmetic) + dissipative (projection) + shot noise | §4.3-4.4 |
| A2 (convergence rate) | Decoherence rate Γ_{ij} encodes which coherences decay fast/slow | §5.1 |
| A3 (gauge invariance) | Populations (diagonal) are pointer-basis-invariant; coherences (off-diagonal) are gauge-dependent | §5.2 |
| A4 (non-commutative limits) | Born-Markov: lim_{coupling→0} lim_{bath→∞} ≠ reverse order | §4.1 |
| A5 (saturation) | S(ρ_S) saturates at log(dim H_S) for maximal entanglement | §3.2 |

### A4 instance: Born-Markov limit ordering

The Born-Markov approximation involves two limits:
1. Weak coupling: ||H_int||/||H_S|| → 0
2. Fast bath: τ_bath/τ_system → 0

These do not commute:
- Weak coupling first, then fast bath: standard Lindblad (Markovian, memoryless)
- Fast bath first, then weak coupling: singular coupling limit (different dynamics)

This is A4 in action: the order of limits matters, and different orders give different reduced dynamics.

---

## §7 Control Theory Connection

### 7.1 Kalman 4-subspace mapping (revised)

The Kalman decomposition (control_theory.md §6) maps to open quantum systems with the bath split into two regimes:

| Quantum concept | Kalman subspace | Observable? | Controllable? | Notes |
|---|---|---|---|---|
| Decoherence-free subspace (DFS) | O ∩ C | yes | yes | Protected logical qubits, both observable and operable |
| Decohering system subspace | O ∩ C̄ | yes | no | Phase leaks to environment; observable but not correctable without active intervention |
| Bath (weakly coupled) | Ō ∩ C | no | yes | System can influence bath via H_int, but cannot observe bath state |
| Bath (Markovian thermal) | Ō ∩ C̄ | no | no | Fully traced out; neither observable nor controllable. Markov = memoryless = no handle |

### 7.2 Markov approximation as C → C̄ transition

The Born-Markov approximation moves the bath from Ō ∩ C to Ō ∩ C̄:

- **Before Markov**: bath has memory, system can (in principle) indirectly control bath state through H_int
- **After Markov**: bath relaxes instantly, all system-to-bath influence is lost → C̄

The "strength of Markov approximation" is thus the **controllability boundary** within the unobservable subspace. This is a concrete instance of the control theory insight that the C/C̄ boundary is model-dependent (control_theory.md §6.1).

### 7.3 Quantum control as E-axis application

Active quantum control (pulse shaping, dynamical decoupling, quantum error correction) operates in O ∩ C:

| Control task | Control theory analogue |
|---|---|
| Dynamical decoupling | Feedback to cancel Lindblad dissipator |
| Quantum error correction | State estimation (syndrome measurement) + feedback (recovery operation) |
| Optimal control (GRAPE, CRAB) | LQR/H∞ for quantum systems |

The separation principle (control_theory.md §5) applies in the linear-Gaussian regime: for small perturbations around a known state, estimation (tomography) and control (pulse design) decouple. For strongly nonlinear quantum dynamics, they couple — as predicted by control_theory.md §5.3.

---

## §8 Downstream: Bridge to Quantum Statistical Mechanics

### 8.1 What this file establishes

- System-bath decomposition and partial trace (the quantum window)
- Mixed states from entanglement (quantum mixedness ≠ classical ignorance)
- Lindblad dynamics (irreversible reduced evolution)
- Decoherence and pointer basis (dynamical gauge selection)

### 8.2 What q_quantum_statistical_mechanics.md adds

The next step in the B-spine (academic_tree §5): open_QS → QSM.

**New structure**: ensemble averaging over bath states. Where open QS treats a specific ρ_total and traces out B, QSM assumes the bath is in thermal equilibrium and derives the canonical ensemble:

    ρ_thermal = e^{-βH_S} / Z,    Z = Tr(e^{-βH_S})

**Preserved**: system structure H_S, observability of system quantities
**Lost**: specific bath state ρ_B → replaced by temperature 1/β

**KMS condition**: The thermal state is characterized by the Kubo-Martin-Schwinger (KMS) condition, which is the algebraic formulation of "detailed balance." This is the bridge from Lindblad dynamics (this file) to equilibrium statistical mechanics (next file).

### 8.3 Arrow structure

```
q_quantum_observation.md          q_open_quantum_systems.md          q_quantum_statistical_mechanics.md
(closed, unitary)        →      (open, Lindblad)          →      (thermal, KMS)
                         Tr_B                               ensemble average
         preserves: Born rule               preserves: CPTP structure
         loses: purity                      loses: specific bath state
```

### 8.4 S15 接続 (2026-04-11)

| S-ID | 本ファイルとの関係 | 層 |
|---|---|---|
| S15 | **Scan**: Lindblad generator L (semigroup e^{Lt}, 乗法 scan — 減衰) + Kraus operator の unitary 部分 (加法 scan)。**Structural**: Kraus rank (整数), pointer basis dimension。**Information**: S(ρ) 増大 (decoherence → entropy production), mutual information I(S:E) | 全 3 層 |
| Arrow 2 | decoherence は Arrow 2 (Scan → Information) の **動的実現**: 純粋状態 (Scan, unitary) → 混合状態 → entropy 増大 (Information)。§5.3 の可換極限 = Scan 層から Information 層への不可逆 flow | Scan → Information |
| S13 | §3.3 の log 2 回収 (S(ρ_max) = log 2) は Arrow 2 上の S13 固定点の open QS 経由 instance | Arrow 2 固定点 |

参照: bidirectional_duality_v0.md §5.5-5.6。

---

## §9 Open Questions

**OQ-OQS1**: Is pointer basis selection the dynamical version of L0 A3 (gauge invariance)? L0 A3 treats the gauge as the observer's static choice. Decoherence makes it dynamic: the environment selects the gauge. If pointer basis ≡ dynamical gauge fixing, then A3 should be reformulated to include both static (observer-chosen) and dynamic (environment-imposed) gauge. The relationship between the two — when do they agree? when do they conflict? — is the content of this OQ.

**OQ-OQS2 RESOLVED 2026-04-28** (theorem upgrade complete; honest dual answer):

**Theorem (Lindblad-Kraus L0 error decomposition canonical bijection)**: For a Lindblad master equation $d\rho/dt = \mathcal{L}\rho$ with $\mathcal{L} = \mathcal{L}_H + \mathcal{D}$, the L0 finite-observation error decomposition (`finite_observation.md §5.1`) maps canonically to the Lindblad generator's three structural pieces:

| L0 error class | generator term | property |
|---|---|---|
| error_arithmetic | $\mathcal{L}_H \rho = -i[H, \rho]$ | system-intrinsic (independent of system-bath split), skew-adjoint → reversible |
| error_projection | $\mathcal{D}\rho = \Sigma_k \gamma_k(L_k \rho L_k^\dagger - \tfrac{1}{2}\{L_k^\dagger L_k, \rho\})$ | depends on $\{L_k, \gamma_k\}$ which is fixed by the system-bath split, eigenvalues with non-zero Re → irreversible |
| error_noise | thermal occupation $\bar n_k(\beta)$ inside $\gamma_k$ | finite-T fluctuation, vanishes at $T \to 0$ |

**Caveat (Kraus operator level)**: the discretized Kraus decomposition does **not** preserve the partition. $K_0(dt) = I - i H_\text{eff} dt + O(dt^2)$ with $H_\text{eff} = H - (i/2)\Sigma_k \gamma_k L_k^\dagger L_k$ bundles unitary phase and anticommutator damping. The L0 partition is canonical only at the generator (superoperator) level.

**Closest-unitary diamond-norm corollary**: defining $U_*^{(dt)}$ as the closest unitary to $\Phi_{dt}$ in diamond norm, $\|\Phi_{dt} - U_*^{(dt)}\|_\diamond = \|\mathcal{D}\| dt + O(dt^2)$ with $U_*^{(dt)} \to \exp(\mathcal{L}_H dt)$ as $dt \to 0$. This recovers the original attack route as a corollary: the non-unitary residual rate equals the dissipator superoperator norm = error_projection magnitude.

**Verification**: pure dephasing ($H = (\omega/2)\sigma_z$, $L_1 = \sigma_z$) and amplitude damping ($H = 0$, $L_1 = \sigma_-$); see `research/oq_oqs2_kraus_l0_bijection_v0.md` for V1 ($[\mathcal{L}_H, \mathcal{D}]$ commutator vanishing for pure dephasing) + V2 ($\|\Phi_{dt} - U_*\|/dt \to \|\mathcal{D}\|=0.5$ as $dt \to 0$) + V3 (Kraus reconstruction = $\exp(\mathcal{L} t)$ to ~$10^{-16}$). The original attack route's literal form ("Kraus partitioning into unitary $K_0$ + non-unitary $K_{k\geq 1}$") is **rejected** at the Kraus level (V3 demonstrates Kraus-level mixing) but **recovered** at the generator level + closest-unitary corollary.

**OQ-OQS3**: Does decoherence *generate* c_s² = 1/2, or merely *permit* it? The three-level derivation (§5.4) shows the same value from three independent routes. The strong claim is that parity-symmetric decoherence is generic (most physical baths have parity symmetry in some relevant sense), making c_s² = 1/2 a dynamical attractor. The weak claim is that c_s² = 1/2 is just the algebraic fact 1/2 = 1/dim(ℤ/2ℤ), and the three routes are trivially the same calculation in different notation. Distinguishing these requires an example of a non-parity-symmetric bath and checking whether c_s² ≠ 1/2 for its pointer basis.

---

*作成日: 2026-04-08*
*最終更新: 2026-04-11 (S15 接続追加)*
