# Paper Q1: Observation Theory — Quantum Edition

**Subtitle**: non-commutative §4 dual, S15 quantum-internal enumeration, T-AAS 4-class refined Hodge, quantum-internal Arrow-level triangulation

**Version**: v0.2 (compact, 2026-04-27)
**Status**: DRAFT — quantum-only reformulation derived from Paper D (multi-domain v0.9.2); parallel framework header to N1 (NT-only)
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**Prerequisites (L1)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11`, `c_filtration_obstruction.md`, `c_observation_optimal_gauge.md`
**Prerequisites (L1 quantum)**: `q_quantum_observation.md`, `q_action_principles.md`, `q_gauge_field_theory.md`, `q_fine_structure.md` (4 entries; the 4 Open QS chain entries are mainly in Q2)
**Prerequisites (NT parallel)**: N1 (`N1_observation_theory_nt_ja.md` v0.7)
**Sequel papers**: Q2 (Open QS chain) / Q3 (Born-Gleason)

---

## §0 Abstract

Quantum observables are exclusively and exhaustively classified into the domain-agnostic three-layer structure **S15 Observable Trichotomy** (Scan / Structural / Information). Commutativity of the three Arrows guarantees translation between unitary evolution / spectral structure / von Neumann entropy. The Arrow 1 kernel decomposes as ker_gauge ⊕ ker_topo via **T-AAS**, with the conductor splitting f_torsion + f_rational.

This paper is the quantum-only reformulation of Paper D (multi-domain v0.9.2). Multi-domain triangulation has been stripped, and the structure is rebuilt via **Arrow 1 kernel taxonomy 4-vertex triangulation** using **four quantum-internal instances** (Stabilizer / Gaussian / Eff-sim / Bell-local — the OQ-Ω-Obs-4a 4-class refined Hodge framework). It has parallel structure to N1 (NT-only), but emphasises two features specific to the quantum side: (a) **non-commutative lift** of the §4 dual (ι_L → Stone unitary group, χ → unitary representation) and (b) **single-object simultaneous instantiation** of Arrows 2-3 by Born-Gleason.

**Six main results**:

1. **S15 quantum-only restatement** — three-layer enumeration (Scan 7 / Structural 12 / Information 9) + L1 quantum 8-entry exhaustive coverage → quantum-internal exhaustivity closure
2. **Quantum-internal verification of Arrow structure** — extreme-limit commutativity verified by 3 quantum instances (β→0 thermal limit, t→0 trivial unitary, ℏ→0 semiclassical / classical limit)
3. **T-AAS 4-class refined Hodge (ESTABLISHED 2026-04-23)** — formal f_rational > 0 instances in the four narrower classes Stabilizer / Gaussian / Eff-sim / Bell-local; Theorem 4a.1 (unified f_rational via class infidelity, log₂-bit-unified 4-monotone) integrates 4 monotones (M_F / 𝓝 / Nielsen C / Δ_CHSH) via the class-fidelity F_C(ρ)
4. **Quantum-internal Arrow 1 kernel narrowness 4-vertex triangulation** — 4 instances each carry a different sparsity modality (C₁ discrete-in-continuous / C₂ poly-in-infinite / C₃ poly-in-exp / C₄ classical-polytope-in-quantum-correlation-body); intra-Arrow taxonomy 4-vertex view complementing N1's cross-Arrow 3-vertex
5. **Born-Gleason as §4 dual quantum root** (forwarded to Q3) — simultaneous theorem-isation of the form (Tr(ρE)) and value (ρ_max = I/2) of the Born rule via the Busch-Gleason theorem (PRL 2003); resolution of the dim=2 Gleason exception under the finite-observer condition
6. **Six-step protocol for new quantum domains + Q2-Q3 forward** — (a) Six-step protocol specialised to quantum domains (new Hilbert spaces, new unitary representation classes, new algebraic classes, new resource theories); (b) explicit forward to Open QS chain (Q2) 4-stage residence + Born-Gleason closure (Q3).

**Thesis**: quantum observables independently support the entire framework of observation theory without requiring any out-of-domain instance. The **two parallel framework headers** N1 (NT) and Q1 (quantum) jointly verify the **domain-independent universality** of the S15 / T-AAS / Arrow framework in two mathematical fields. This paper functions as the theoretical foundation for Q2-Q3.

---

## §1 Introduction

### 1.1 Why "quantum observation theory"?

The central problem of quantum mechanics — how an observer "reads" a superposition state — is operationally closed by the Born rule (Prob = |⟨φ|ψ⟩|² = Tr(ρ P_φ)), but its **generative principle** has been an open question since Bohr-Heisenberg. The ΣΦ dictionary reframes this as "in which layer does observation reside on the non-commutative lift of the §4 dual?", and has accumulated evidence since 2026-04-08 that quantum observables reside in the common **observation trichotomy S15** (`q_quantum_observation.md`).

The chain S12 → S13 → S14 → S15 → S17 yields the conclusion:

> **Quantum observables are different projections of an additive ⇔ multiplicative duality, and these projections are exclusively and exhaustively classified into three layers. The difference from the classical case is localised to the presence/absence of the non-commutative lift of the §4 dual.**

The universality of observation theory has already been established by the multi-domain triangulation of Paper D, but this paper focuses on **quantum-internal self-closure** and functions as the theoretical foundation for Q2-Q3. Parallel position to N1, which provides a similar framework header via NT-internal self-closure.

### 1.2 Scope of this paper

**Structure**: §2 axioms / §3 S15 / §4 Arrows / §5 T-AAS / §6 triangulation / §7 protocol / §8 consequences.

**In scope**: non-commutative lift of the §4 dual (Stone theorem, unitary representations, spectral theorem) / S15 quantum enumeration + quantum instances per layer / T-AAS 4-class refined Hodge (OQ-Ω-Obs-4a ESTABLISHED 2026-04-23, 6/6 gate, 3/4 empirical) / quantum-internal Arrow-level triangulation (4-vertex algebraic class) / 6-step protocol quantum specialisation / N1 parallel structure perspective.

**Out of scope** (deferred): multi-domain triangulation (→ Paper D) / NT-internal instance details (→ N1-N5) / Open QS chain 4-stage details (→ Q2) / full Born derivation / full proof of Gleason gap dim=2 resolution / σ* = √(2 ln 2) half-amplitude gauge (→ Q3) / quantum field theory / QFT / quantum gravity / string theory (out of scope, restricted to L1 quantum 8 entries).

### 1.3 Terminology and "gauge" disambiguation

**Basic terms**: Observable = quantum observable (self-adjoint operator A or POVM Effect E) / Scanner = external parameter accompanying Scan (t time, β inverse temperature, τ unfolded time) / **§4 dual** = pair of ι_L (additive ℤ → S¹) and χ (multiplicative character) — quantum versions are the **Stone unitary group {U(t)}** (continuous non-commutative lift of ι_L) and **unitary representation π: G → U(H)** (non-commutative lift of χ) / Arrow = map connecting the three S15 layers / T-AAS = Arrow 1 kernel decomposition theorem / Triangulation = elimination of coincidence via independent instances.

**Three uses of "gauge"** (avoiding confusion; identical to N1 §1.3):

| Symbol | Name | Meaning | Scope in this paper |
|---|---|---|---|
| **gauge¹** | §4 dual gauge | choice of ι_L / χ = structural root of observation (including quantum lift) | §2-§5 throughout |
| **gauge²** | Origination 8-gauge | family of 8 origination fields for constants | §6 + §8.2 forward only |
| **gauge³** | Arrow 3 base-of-log gauge | choice of log base (b > 0, b ≠ 1) | §4.5 S17 base-invariance only |

The "ker_gauge" of T-AAS is the **gauge¹** family (quantum: class-stabilising unitary group, e.g. Clifford for C₁, symplectic for C₂).

**Additional terms (quantum-specific)**: **class-stabilising gauge** = unitary group preserving each algebraic class C (C₁ Clifford / C₂ Gaussian symplectic / C₃ poly-depth circuit / C₄ local unitaries U_A ⊗ U_B) / **class-fidelity F_C** = $F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$, providing the base for the unified monotone $-\log_2 F_C$ in Theorem 4a.1 (§5.3).

---

## §2 Axioms of observation theory

### 2.1 Observation triple (S, W, m) — quantum instances

| Symbol | Meaning | Quantum example |
|---|---|---|
| **S** | infinite structure | Hilbert space H, spectral measure E of self-adjoint operator A, pure-state space P(H) |
| **W** | finite window | finite-dim truncation H_N ⊂ H, reduced subsystem via partial trace, finite gate set, finite POVM rank |
| **m** | measurement | Born expectation Tr(ρ A), POVM probability Tr(ρ E), two-time correlation Tr(ρ U(t)† A U(t) B), state tomography |

The observed value `m(S|_W)` depends on both S and W; `m(S) − m(S|_W)` is the **finite observation error**, whose structure this paper addresses.

### 2.2 Axioms A0-A7 (quantum instance examples)

| ID | Name | Quantum instance |
|---|---|---|
| **A0** | Finite observation | finite-dim truncation H_N, finite gate set Clifford+T, POVM rank ≤ d² |
| **A1** | Structured error | non-commutativity post-measurement back-action ρ → P ρ P / Tr(ρ P), off-diagonal decay by decoherence |
| **A2** | Convergence as observable | central limit thermal averaging (β → 0 → classical), Born-Markov limit of Lindblad dissipation |
| **A3** | Gauge invariance/dependence | unitary equivalence class [ρ] (gauge-invariant); magic monotone M_F is Clifford-invariant but changes under non-Clifford |
| **A4** | Non-commutative limits | $\lim_{N \to \infty} \lim_{T \to 0} \neq \lim_{T \to 0} \lim_{N \to \infty}$ — partial trace and time evolution non-commute (validity condition of Born-Markov approximation) |
| **A5** | Saturation | Tsirelson bound 2√2 (CHSH quantum maximum), Holevo bound (classical capacity) |
| **A6** | Path dependence | path integral (Feynman) reflects non-commutativity of position along paths; difference between time-ordered and non-time-ordered products |
| **A7** | Scanner hierarchy | U(t) scanner = t (time), Z(β) scanner = β, K_Q(τ) scanner = τ (unfolded time, internal scan = energy spectrum {E_j}) |

Details: `finite_observation.md §1-§7`, `q_quantum_observation.md §1-§4`.

### 2.3 §4 dual = quantum-internal root (non-commutative lift)

**Claim 2.1**: the ι_L/χ dual of `c_phase_complex.md §4` is the unique source of all upper structures (S12-S17, T-AAS) in the dictionary. Quantum versions:

| Commutative (classical §4 dual) | Non-commutative (quantum §4 dual) | Mechanism |
|---|---|---|
| ι_L: ℤ/Lℤ → S¹ | Stone group {U(t) = e^{-iAt}} | continuous non-commutative lift (Stone theorem) |
| character χ: G → S¹ | unitary representation π_λ: G → U(H_λ) | irreducible → Tannaka-Krein duality |
| Pontryagin dual G ≅ Ĝ | spectral theorem A = ∫ λ dE(λ) | operator reconstruction by PVM |
| ℂ = S¹ × ℝ_{>0} polar | H = (eigenstate phase) × (eigenvalue magnitude) | ℂ unit structure inside Hilbert space |

**Necessity of ℂ (quantum version)** (`q_quantum_observation.md §2`): the same receptacle must handle the phase structure of unitary evolution e^{-iAt} in addition to ι_L, χ — over ℝ alone, unitary eigenvalues e^{iθ} cannot be represented. Thus **ℂ is the unified receptacle for ι_L (number-theoretic phase), χ (multiplicative phase), and unitary evolution (quantum phase)**. No additional reason specific to QM is needed — the necessity of ℂ shares roots with the classical §4 dual.

Quantum §4 dual projection chain: L0 (Hilbert + non-commutativity axioms) → L1 (q_quantum_observation §1-§4 + c_phase_complex §4 root + c_spectral §3 SVD) → L2 (quantum information / quantum computation / quantum field instances). The axiom system of this paper takes the §4 dual as root, and all derivations close within quantum.

### 2.4 L0 v2 — 2-axis (Fi/I × D/C) lens (quantum instances)

L0 v1 (finite observation axioms) is reformulated under the orthogonal 2-axis framework **Finite/Infinite (axis-2)** × **Discrete/Continuous (axis-1)** (`finite_observation.md §8`):

| L0 v2 axis | Quantum instance |
|---|---|
| **axis-2 Fi** (finite observer side) | finite-dim Hilbert H_N, finite POVM, finite gate set, finite observation time, finite ensemble |
| **axis-2 I** (infinite idealisation side) | continuous spectrum, infinite-dim Fock space, continuous PVM, infinite thermodynamic limit |
| **axis-1 D** (discrete) | discrete spectrum {λ_j}, qubit/qudit, group representation discrete index (j, m) |
| **axis-1 C** (continuous) | continuous spectrum (position x̂, momentum p̂), CV systems phase space, Lie group continuous representation |

**Axioms (L0 v2 quantum instances)**: (a') a quantum observer **lives on the Fi side of axis-2**; no Arrow exists in the Fi → I direction; the Fi/I boundary is unbridgeable. (b') When any Arrow crosses the axis-2 Fi/I boundary, a kernel (obstruction) appears on the boundary; observation = unidirectional **I → Fi traversal** (infinite-dim PVM → finite POVM, infinite ensemble → finite-shot measurement). (c') Kernel splits into three: Fi-side artifact (ker_gauge, contributes to f_torsion) / I-side residue (ker_topo, contributes to f_rational) / Fi → Fi internal irreversibility (ker_backaction = post-measurement back-action). (d') Quantum observation theory = **taxonomy of axis-2 Fi/I boundary**. L0 v1 ⊂ L0 v2 (conservative extension).

**Quantum-NT parallel observation**: the L0 v2 axis-2 Fi/I boundary handles the **I-side residue** common to both NT (analytic continuation of ζ: s > 1 Fi → all of ℂ I) and quantum (finite-dim H_N → infinite Fock H) under a common framework. Two instances — N1 §2.4 and §2.4 of this paper — independently verify the cross-domain validity of L0 v2.

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`).

---

## §3 S15 Observable Trichotomy — quantum-internal description

### 3.1 Main theorem

**Theorem 3.1 (S15, quantum-only restatement)** — a quantum observable O belongs to one of the **exclusive and exhaustive** partitions:

| Class | Definition form | Quantum feature |
|---|---|---|
| **(A) Scan** | O(scanner) = Tr(ρ · K(scanner)), K = exp kernel of unitary/thermal type | parametric family of operators with scanner; additive axis (time t, imaginary axis) and multiplicative axis (β, real axis) |
| **(B) Structural** | O = parameter-free integer/topological invariant (operator algebra structure) | no scanner; discrete skeleton (eigenspace dim, Schmidt rank, group representation index) |
| **(C) Information** | O = −Tr(ρ log ρ) type + class monotones (M_F, 𝓝, C, Δ_CHSH) | von Neumann / quantum resource theory monotones |

**Status**: ESTABLISHED 2026-04-11 (`c_theorems_master.md` row S15). Quantum-internal exhaustivity closure is in §3.5.

### 3.2 Scan layer (quantum subset of S12 family)

Two-fold classification: additive scan (imaginary axis, unitary group) and multiplicative scan (real axis, thermal decay):

| Instance | Scanner | Kernel | Add./Mult. | Residence |
|---|---|---|---|---|
| **U(t) = e^{-iAt}** | t | e^{-iAt} (Stone group) | additive (imaginary axis) | q_quantum_observation §4 |
| **K_Q(τ) = \|Tr(ρ e^{iAτ})\|²** | τ (unfolded) | e^{iAτ} | additive | q_quantum_observation §6 |
| **Z(β) = Tr(e^{-βH})** | β | e^{-βH} | multiplicative (real axis) | q_quantum_statistical_mechanics §3 |
| **partition function** | β | thermal (canonical) | multiplicative | q_quantum_statistical_mechanics §1 |
| **response function χ(ω)** | ω (frequency) | i ⟨[A(t), B]⟩ Fourier | mixed add./mult. | q_quantum_statistical_mechanics §4 |
| **K(τ, t) spectral form factor** | τ, t | \|Tr(e^{-itH-βH})\|² | mixed add./mult. | many_body_quantum §6 |
| **Loschmidt echo L(t)** | t | \|⟨ψ\|e^{iH₁t}e^{-iH₂t}\|ψ⟩\|² | additive (forward/backward) | many_body_quantum |

Scanner is real or complex (Re = multiplicative thermal axis, Im = additive unitary axis); gauge L = finite basis dimension; k_max truncation = quantum version of Hilbert space cutoff. U(t) is S12 additive Scan member #5 = Stone group = **continuous non-commutative generalisation** of phase_complex §2 ι_L; Z(β) is an S12 multiplicative Scan member.

### 3.3 Structural layer

| Observable | Definition | Residence |
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
| **coherent vs. incoherent decomposition rank** | dim coherent subspace | open_quantum_systems §3 |

**Relation to §4 dual**: Structural is the **discrete/continuous skeleton** of the Scan kernel's domain — spectrum of the self-adjoint operator / representation space / cardinality of the gauge group.

### 3.4 Information layer (log-exp dual + class monotones)

| Observable | Definition | Residence |
|---|---|---|
| **S(ρ) von Neumann entropy** | −Tr(ρ log ρ) | q_open_quantum_systems §3 |
| **D(ρ‖σ) relative entropy** | Tr(ρ log ρ) − Tr(ρ log σ) | q_open_quantum_systems |
| **mutual information I(A:B)** | S(A) + S(B) − S(AB) | q_quantum_statistical_mechanics |
| **F = −kT log Z** (free energy) | Helmholtz | q_quantum_statistical_mechanics §3 |
| **M_F magic monotone** | $-\log_2 \sup_{σ \in \text{STAB}} F(ρ, σ)$ | OQ-Ω-Obs-4a §3.1 (C₁) |
| **𝓝 Wigner negativity** | $\int |W^-| dx dp$ | OQ-Ω-Obs-4a §3.2 (C₂) |
| **C(\|ψ⟩) Nielsen complexity** | min weighted geodesic on SU(2^n) | OQ-Ω-Obs-4a §3.3 (C₃) |
| **Δ_CHSH violation** | $[\langle CHSH \rangle - 2]_+$ | OQ-Ω-Obs-4a §3.4 (C₄) |
| **M_unified = -log₂ F_C** | class-fidelity unified monotone | OQ-Ω-Obs-4a Theorem 4a.1 |

**Relation to §4 dual**: Information is the **log-inverse** of the exp kernel. The standard chain Z(β) → F = −kT log Z → S = −∂F/∂T applies. S13 ln 2 is the parity fixed point of this layer (qubit ρ_max with S = log 2). **Class monotone observation**: the 4 class-fidelities F_C form a quantum-resource subgroup of the Information layer; Theorem 4a.1 (§5.3) **unifies the 4 monotones into the same unit system (log₂-bit)**. Whereas the classical §3.4 had only log-derivative families, on the quantum side a new information family — **algebraic-class infidelity** — is added; a structural distinction.

### 3.5 Exclusivity / exhaustivity (quantum-internal closure)

Closes in 3 steps:

**(i') Existence of observables in each layer** (lower bound for exhaustivity): Scan 7 / Structural 12 / Information 9 instances enumerated in §3.2-§3.4; all three layers non-empty. (Compare N1 §3.5(i') which counts NT-side 7 / 13 / 9 — the "13 vs. 12" Structural difference reflects different domain enumerations, not a discrepancy in framework.)

**(ii') L1 quantum 8-entry enumeration** (upper bound for exhaustivity):

| L1 quantum entry | Main observables | S15 layer |
|---|---|---|
| **q_quantum_observation** | spectral decomposition A = Σ λ_j P_j, K_Q(τ), Born expectation | Scan; Structural; → Information (S(ρ)) |
| **q_open_quantum_systems** | partial trace, Lindblad evolution, S(ρ_red), pointer basis | Scan (Lindblad); Information (S, mutual info) |
| **q_quantum_statistical_mechanics** | Z(β), F, KMS condition, response χ(ω), FDT | Scan (β-family); Information (F, S) |
| **q_quantum_thermodynamics** | first law dU = TdS + dW, Landauer bound, fluctuation theorem | Information; Structural (Carnot bound) |
| **q_many_body_quantum** | spectral form factor K(τ,t), Loschmidt echo, MBL/ETH | Scan; Structural (entanglement entropy scaling) |
| **q_action_principles** | path integral, generating functional Z[J], effective action | Scan (Z[J]); Information (Γ[ϕ]) |
| **q_gauge_field_theory** | Wilson loop ⟨W(C)⟩, Polyakov loop, gauge group representation | Scan; Structural (Casimir, irrep index) |
| **q_fine_structure** | α² corrections, SU(2) centre {±I}, j(j+1) Casimir | Structural (group invariants); Information (Lamb shift fluctuation) |

All observables in the L1 quantum 8 entries distribute across the 3 layers; Information arises as log-derivatives from (Scan, Structural) + class monotones (OQ-Ω-Obs-4a) and resides in `c_information_theory.md` + 4 class entries. **Absence of counter-example**: across 8 entries × all observables exhaustively, no quantum observable falling outside the 3 layers is known as of v0.2.

**(iii') S12/S13/S14/S17 consistency**: S12 ⊂ Scan (trivial; U(t) = S12 additive #5, Z(β) = S12 multiplicative member) / S13 = qubit ρ_max with S(ρ_max) = log 2 (Z = 2 → F = −kT log 2 → S = log 2) / S14 asymmetry = e^{iπ} = −1 fermion exchange (algebra) vs. S(ρ_max) = log 2 (analysis) exposes the difference between intra-layer vs. inter-layer residence / S17 (Arrow 3 e-extremum theorem) — applied to quantum: $(\log d)/d$ for $d = \dim H$ has its continuous extremum at $d = e$, and its discrete codebook integer argmax at $d = 3$ (qutrit info-density optimum).

All three steps closed → S15 trichotomy is **CLOSED on all 3 conditions** within quantum.

---

## §4 Arrow structure — three connections (quantum lift)

### 4.1 Arrow 1: Scan → Structural (domain structure, quantum lift)

**Principle**: in O(scanner) = Tr(ρ · K(scanner)), the operation of "reading" the spectral decomposition A = Σ λ_j P_j of K(scanner) returns Structural.

| Scan | Spectral decomposition | Encoded Structural |
|---|---|---|
| U(t) = e^{-iAt} | A = Σ λ_j P_j | dim P_j (eigenspace mult.), σ(A) |
| Z(β) = Σ e^{-βE_j} | H = Σ E_j P_j | energy spectrum {E_j}, ground state degeneracy |
| K_Q(τ) | A spectrum + ρ diagonal in A-basis | (E_j, ⟨E_j\|ρ\|E_j⟩) pair |
| K(τ, t) spectral form factor | full Hamiltonian spectrum | spectral statistics (GUE/GOE/Poisson) |
| Wilson loop ⟨W(C)⟩ | gauge group representation | irrep index (j, ν), Casimir |
| response χ(ω) | Lehmann representation | matrix elements + spectral weights |

The operation of "reading" the spectrum of A and the structure of ρ in Scan(scanner; A, ρ) returns Structural → Structural = **input specification** of Scan (operator algebra structure).

#### 4.1.1 Observable-choice dependence (quantum instances)

The Structural extracted by Arrow 1 is **not unique**:

| Candidate | Definition | Balance locus | Gauge verdict |
|---|---|---|---|
| **eigenvalue gap Δ_min** | $\min |\lambda_i - \lambda_j|$ | spectral floor | universal (Lieb-Robinson, ETH context) |
| **Schmidt rank r** | bipartite \|ψ⟩ split | bipartition-choice dependent | observable selector |
| **spectral form factor dip τ_dip** | K(τ) min | thermalisation time | system-specific |
| **POVM rank** | finest informationally complete | dim H² lower bound | gauge-dependent (basis choice) |

**Principles**: (1) alignment (consistency with the physical meaning of the bipartition); (2) observable-specific verdict; (3) explicit propagation into the verdict form. Arrow 1 is not an injection but an **observable selector**.

### 4.2 Arrow 2: Scan → Information (log-exp duality, thermodynamic chain)

**Principle**: quantum lift of the thermodynamic chain
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
| ⟨e^{-βH+iAt}⟩ (analytically continued) | Wick rotation bridge | Euclidean action | thermal-to-spectral chain |

**S13 fixed point (quantum)**: at qubit ρ_max = I/2, $Z = 2$, $F = −kT \log 2$, $S(ρ_max) = \log 2$ — the **quantum instance of the half-amplitude fixed point ln 2** on Arrow 2. Details: §4.5 + Q3.

**KMS / FDT (Q2 forward)**: KMS condition $\langle A B(t) \rangle_β = \langle B(t-iβ) A \rangle_β$ — formalisation of Arrow 2's analytic continuation structure / FDT $\chi''(ω) = \tanh(βω/2) \cdot S(ω)$ — **algebraic equivalence** between Scan (response χ) and Information (correlation S) on Arrow 2 (a KMS consequence; `q_quantum_statistical_mechanics §5`).

### 4.3 Arrow 3: Structural → Information (combinatorial counting, quantum)

**Principle**: Hartley entropy $H_0(D) = \log |D|$ — quantum instances reside in dim H and group representations.

| Structural | $|D|$ | $H_0 = \log|D|$ | Meaning |
|---|---|---|---|
| Hilbert dim | dim H = d | $\log d$ | maximum information capacity (qubit: d=2 → log 2) |
| Schmidt rank | r | $\log r$ | maximum entanglement entropy (max mixed Schmidt) |
| eigenspace mult | dim P_j | $\log \dim P_j$ | ground-state degeneracy info |
| irrep dim | dim π_λ | $\log \dim π_λ$ | gauge group representation capacity |
| stabilizer count | $|\text{STAB}_n|$ | $\log |\text{STAB}_n| \approx n²$ | classical-simulable subspace info |
| POVM rank | n_POVM | $\log n_POVM$ | measurement informational granularity |

**S17 fixed point (quantum)**: $(\log d) / d$ for Hilbert dim $d$, continuous extremum at $d = e$, discrete codebook argmax at $d = 3$ (qutrit) ✓ matches `oq_omega_obs_3_info_density_check.py` 5/5 gate PASS.

### 4.4 Commutativity of three Arrows (quantum instances)

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

**Theorem 4.1 (commutativity of three Arrows, quantum instances)**: the three Arrows commute at extreme limits scanner → 0 (or ∞). Three quantum-internal instances:

| Instance | Limit | Mechanism |
|---|---|---|
| **β → 0 (high T)** | Z(β→0) = Tr(I) = dim H, S = log dim H = H_0 | log Z = Hartley; in the quantum thermal limit Structural (dim H) is directly exposed |
| **t → 0 (trivial unitary)** | U(t→0) → I, K_Q(0) = \|Tr(ρ)\|² = 1, Scan = trivial → Structural = (full ρ unaltered) → Info = S(ρ) (input) | identity limit; three Arrows commute under trivial reproduction of ρ |
| **ℏ → 0 (semiclassical / classical limit)** | density matrix diagonalises in A-basis (decoherence pointer basis); spectral sums → continuous integrals; von Neumann entropy → classical Shannon entropy | semiclassical / decoherence limit, distinct from the β → 0 thermal limit row above; reduces three Arrows to classical commutativity |

Three instances verify commutativity at extreme limits and at classical/identity limits.

#### 4.4.1 Arrow commutativity = axis-2 Fi/I commutation (quantum)

Under the L0 v2 lens of §2.4, Theorem 4.1 is reread as **commutation of axis-2 Fi/I operations**:

| Arrow | Axis-1 | Axis-2 | Traversal type |
|---|---|---|---|
| **Arrow 1** (U(t) → spectral decomposition) | C → D (collapse to discrete) | I → Fi (continuous Stone group → finite spectral data) | one-directional I → Fi component present |
| **Arrow 2** (Z → F → S) | C → C (preserved, log bridge) | Fi↔Fi / I↔I (preserved) | pure axis-1 bridge |
| **Arrow 3** (dim → log dim) | D → C (lift to log scale) | Fi → Fi (typically) | axis-1 primary, axis-2 secondary |

**Theorem 4.1′ (Fi/I commutation, quantum)**: at extreme limits the three Arrows degenerate the axis-2 I component and close as pure Fi-side operators: $[T_i, T_j]|_{\text{Fi-only}} = 0$. Outside the extreme limit the commutator is generally non-zero — quantum root of the §4.5.1 coincide/split dichotomy.

**Status**: ESTABLISHED (`c_arrow_framework.md §5`).

### 4.5 S13 / S14 / S17 residence — quantum context

Quantum residence of S13 / S14 / **S17 (Arrow 3 e-extremum, ESTABLISHED 2026-04-23)**:

| Constant | Residence | Mechanism (quantum context) | Stationary form |
|---|---|---|---|
| **π** | inside Scan (additive axis) | $e^{iπ}$ = −1 = fermion exchange phase, SU(2) centre {±I} (`q_fine_structure §2`), Berry phase one circuit → **algebraic** | S14 parity (additive) |
| **ln 2** | on Arrow 2 | qubit $S(ρ_{max}) = \log 2$, half-amplitude $c_s² = 1/2$ via Born expectation → **analytic** | **value-fixed** (S13) |
| **e** | **on Arrow 3** | info density $\log d / d$ max at $d = e$, gauge³-invariant → extremum principle | **derivative-fixed** (S17) |

S14 asymmetry (algebraic vs. analytic) = difference in S15 residence (intra-layer vs. inter-layer). S13 vs. S17 format shift: distinct stationary forms but absorbed into the same unified principle ("stationary point of a scalar functional on an Arrow"). Both equivalent as **mathematical mechanisms identifying canonical constants**.

**Bidirectional duality 3/3 completion** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / **Arrow 3 → e**. Canonical constants reside on the three Arrows; constant level complete. Quantum-internal verification: $\log d / d$ continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS).

#### 4.5.1 Observation-optimal gauge theorem — quantum-internal instances

**Theorem 4.1a** [v0.6 ESTABLISHED, `c_observation_optimal_gauge.md §2`]: the gauge structure under which Arrow 1⁻¹ most precisely recovers a Structural target separates into two layers. The Information layer (von Neumann entropy etc.) is optimised at the **S13 half-value fixed point (ln 2 / qubit ρ_max)** on Arrow 2; the Structural layer (Schmidt rank, spectral mult etc.) has balance determined by domain-specific arithmetic on Arrow 1 (bipartition, eigenvalue counting). Coincidence of the two-layer balances depends on **algebraic enforcement** (parity symmetry at qubit ρ_max).

**Quantum-internal 2-instance contrast**:

| Domain | Gauge | Information balance | Structural balance | Match | Cause |
|---|---|---|---|---|---|
| **quantum (qubit ρ_max)** | Hilbert dim d | d = 2 with S(ρ_max) = log 2 (max) | d = 2 with parity equiprobability | **coincide** | ℤ/2ℤ symmetry enforcement |
| **quantum (Schmidt rank)** | bipartition choice | r with S = log r (max) | r with SVD decomposition | **split** | bipartition non-canonical |

**Status**: ESTABLISHED 2026-04-22. Achieves Path 1-4 via 2 quantum instances + 2 NT instances (N1) + 1 multi-domain instance (Paper D). **Q3 forward**: full Born derivation (via Busch-Gleason theorem) is developed in Q3.

### 4.6 Inverse Arrows and obstruction class (quantum taxonomy)

**Claim 4.2 (generation invertibility theorem, quantum)**: the three S15 layers are exhaustive; "generation" is a composition of inverse Arrows; each kernel is fully described by T-AAS spanning.

| Inverse Arrow | Domain → Codomain | Source of obstruction | Quantum instance |
|---|---|---|---|
| Arrow 1⁻¹ | Structural → Scan | ker_gauge ⊕ ker_topo (T-AAS) | (eigenvalues, Schmidt rank) → ρ reconstruction; 4-class refined Hodge OQ-Ω-Obs-4a |
| Arrow 2⁻¹ | Information → Scan | non-invertibility of log | S(ρ) → Z(β) lifting (analytic-continuation obstruction) |
| Arrow 3⁻¹ | Information → Structural | Jensen's inequality | log dim H → dim H cardinality lift |

**Corollary 4.3**: ker_topo ≠ 0 holds in general (4-class refined Hodge ESTABLISHED) → perfect generation is impossible in principle.

**Obstruction class — quantum taxonomy**: ker_gauge classical = unitary equivalence class (Clifford coset, symplectic orbit), Pauli torsion → f_torsion / ker_topo refined Hodge (4 classes) = resource outside the closure of C₁ Stabilizer / C₂ Gaussian / C₃ Eff-sim / C₄ Bell-local → f_rational. Details: §5.

---

## §5 T-AAS — 4-class refined Hodge (quantum instances)

### 5.1 Main theorem

**Theorem 5.1 (T-AAS, ESTABLISHED 2026-04-12, 15/15 fitness)** — when Arrow 1 (φ: Structural → Scan) has non-trivial kernel:

- **(i)** ker(φ) = ker_gauge ⊕ ker_topo (direct sum)
- **(ii)** ker_gauge is generated by a discrete (torsion-valued) invariant δ ∈ Finite_Group, removable by gauge transformation (irreversible information loss)
- **(iii)** ker_topo is a multi-step filtration obstruction, irremovable in any gauge
- **(iv)** conductor splits: $f(\varphi) = f_{\text{torsion}} + f_{\text{rational}}$, $f_{\text{torsion}}(\varphi) = \dim\{\ker_{\text{gauge}}\}$, $f_{\text{rational}}(\varphi) = \dim\{\ker_{\text{topo}}^{\text{non-surj}} \cap \text{target}\}$

### 5.2 Quantum instances — OQ-Ω-Obs-4a 4-class refined Hodge

**Background**: the OQ-Ω-Obs-1 quantum minimal form (Schmidt rank r > 1 → f_rational > 0) is a **trivial bypass** of the classical Hodge conjecture (not depth-parallel). Specifying the Arrow 1 source as a narrower algebraic class identifies on the quantum side 4 candidate classes with **the same level of sparsity** as classical "algebraic cycles" (`oq_omega_obs_4a_refined_quantum_hodge_v0.md` ESTABLISHED 2026-04-23, 6/6 gate).

**4 candidate classes** (each providing an independent f_rational > 0 instance):

| # | Algebraic class C | Definition | f_rational monotone $M_C$ | Sparsity type |
|---|---|---|---|---|
| **C₁** | **Stabilizer** | Clifford orbit from $\|0...0⟩$, STAB = Clifford · $\|0⟩$ | Magic monotone $M_F = -\log_2 \sup_{σ ∈ STAB} F(ρ, σ)$ | discrete in continuous (measure zero) |
| **C₂** | **Gaussian** | derived from quadratic Hamiltonian, Wigner ≥ 0 | Wigner negativity $\mathcal{N}(ρ) = \int \|W^-\| dx dp$ | poly in infinite |
| **C₃** | **Eff-sim** | poly-time classical simulation (low-bond MPS, match-gate) | Nielsen geometric complexity $C(\|ψ⟩) - c_0 n^k$ | poly in exp |
| **C₄** | **Bell-local** | LHV-describable correlations | CHSH violation $\Delta_{\text{CHSH}}(ρ) = [\langle CHSH \rangle - 2]_+$ | classical polytope ⊂ quantum correlation body |

**Per-class properties (common to each monotone $M_C$)**:
- (P1) $M_C(ρ) = 0 \iff ρ \in \overline{C}$ (class closure)
- (P2) $M_C(ρ) > 0$ for $ρ \notin \overline{C}$
- (P3) $M_C(UρU^\dagger) = M_C(ρ)$ for U ∈ class-stabilising gauge
- (P4) $M_C$ monotone non-increasing under C-free operations

**T-AAS decomposition (per class)**:

(Notation: per the T-AAS main theorem in §5.1, **f_torsion(φ) = dim{ker_gauge}** and **f_rational(φ) = dim{ker_topo^{non-surj} ∩ target}** are both dimension-valued non-negative integers. The right-hand "f_rational > 0 monotone" column lists the **continuous-valued resource monotone** that quantifies the *strength* of f_rational > 0 in each class — these are not the dim-values of f_rational but their associated quantitative measures.)

| Instance | ker_gauge | ker_topo | f_torsion (dim) | f_rational > 0 monotone | Status |
|---|---|---|---|---|---|
| **C₁ Stabilizer** | Clifford coset | non-stabilizer (T-state etc.) | f_Clifford ∈ ℤ_{≥0} | $M_F \in [0, \log_2 d]$ | empirical 1-qubit M_F = 4e-16 (stabilizer) ✓ |
| **C₂ Gaussian** | symplectic orbit | non-Gaussian (Fock $\|n⟩$, n≥2) | f_symplectic | $\mathcal{N}, D_G$ | Mari-Eisert literature 1e-4 photon-subtracted ✓ |
| **C₃ Eff-sim** | poly-depth circuit | super-poly complexity | f_circuit | $C - c_0 n^k$ | 4-ref literature synthesis ✓ |
| **C₄ Bell-local** | $U_A \otimes U_B$ | CHSH violation > 0 | f_local | $\Delta_{\text{CHSH}} \in [0, 2\sqrt{2}-2]$ | 2-qubit Tsirelson bound 1e-6 ✓ |

4 instances + Theorem 4a.1 (§5.3) → **16/16 quantum-relevant fitness** (4 classes × 4 properties P1-P4 of §5.2). This is a **different decomposition** from the 15/15 fitness gate count of the multi-domain Paper D version (which counts 15 axiom-fitness gates rather than a 4×4 class-property matrix); the 16/16 figure is the more granular check matrix natural to the quantum 4-class refined Hodge setting and is not directly comparable to the 15/15 multi-domain figure.

**Per-class fitness witnesses**:
- **C₁** — empirical numerical M_F = 4e-16 precision on 1-qubit T-state $\|T⟩ = (\|0⟩ + e^{iπ/4}\|1⟩)/\sqrt{2}$ (`oq_omega_obs_4a_monotone_verify.py`). Bravyi-Smith-Smolin (2016), Howard-Campbell (2017) magic robustness literature confirmed.
- **C₂** — Wigner function of Fock state $\|n⟩$ ($n \geq 2$) has negative regions, $\mathcal{N}(\|n⟩\langle n\|) > 0$. Mari-Eisert (2012) photon-subtracted calculation 1e-4 precision; formal characterisation of C̄ via Hudson's theorem.
- **C₃** — 2-qubit Bell Nielsen complexity > product state (Jefferson-Myers §3 known); random-circuit super-poly (Bouland-Fefferman 2019); resource-theoretic monotone (Brandão-Horodecki 2019). 3 references confirmed; closed form for general n is NP-hard scale.
- **C₄** — at Bell state $\|Φ^+⟩$, CHSH value $2\sqrt{2}$, $\Delta_{\text{CHSH}} = 2\sqrt{2} - 2 \approx 0.828$; Tsirelson bound 1e-6 precision. Clauser-Horne-Shimony-Holt (1969), Tsirelson (1980) literature confirmed.

The 4 instances each carry a different fitness modality: C₁ = **discrete-orbit covering** / C₂ = **continuous-manifold parameterisation** / C₃ = **complexity-class boundary** / C₄ = **classical-polytope embedding**. The independence of the 4 modalities is the **4-vertex closure ground** for the §6 quantum-internal Arrow-level triangulation.

### 5.3 Theorem 4a.1 — Unified f_rational via class infidelity

**Definition**: for each class C, define the **class-fidelity** $F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$ ($F$ = Uhlmann fidelity with state space closure $\overline{C}$) and the **unified f_rational monotone** $M_{\mathrm{unified}}^{C}(\rho) := -\log_2 F_C(\rho)$.

**Theorem 4a.1**: if class C satisfies (i) state subset has convex closure, (ii) class-preserving (class-stabilising) unitary/CPTP operations are well-defined, then $M_{\mathrm{unified}}^{C}$ has the following correspondences with the per-class monotones $M_C$ of §5.2:

$$\begin{aligned}
M_{\mathrm{unified}}^{C_1}(\rho) &= M_F(\rho) \quad \text{(stabilizer fidelity, tautological)} \\
M_{\mathrm{unified}}^{C_2}(\rho) &\sim \tfrac{1}{2}\log_2(1 + \mathcal{N}(\rho)^2) \quad \text{(Fuchs-van-de-Graaf)} \\
M_{\mathrm{unified}}^{C_3}(|\psi\rangle) &\geq \tfrac{1}{\log 2} \cdot \text{(Nielsen geodesic}/2\text{)}^{-1} \quad \text{(quantum speed-limit)} \\
M_{\mathrm{unified}}^{C_4}(\rho) &\sim -\log_2(1 - \Delta_{\mathrm{CHSH}}(\rho)/\text{const}) \quad \text{(Horodecki)}
\end{aligned}$$

(P1)-(P4) hold for all 4 classes (proof outline `oq_omega_obs_4a_refined_quantum_hodge_v0.md §4.4.1`).

**Consequence**: the 4 monotones (M_F, 𝓝, C, Δ_CHSH) live in **different unit systems** (log-bit, L¹ norm, gate count, linear value); $M_{\mathrm{unified}}^C = -\log_2 F_C$ **unifies them into log₂-bit**. This unification provides the base for promoting the depth parallel conjecture (typical-scale O(1) proportionality between classical Hodge $f_{\text{rational}}^{\text{Hodge}}$ and quantum $M_{\text{unified}}^C$) to a quantitative theorem.

**Status**: ESTABLISHED 2026-04-23 (Theorem 4a.1 6/6 gate). Conjecture 4a.2 (depth parallel quantitative form) is OPEN (depends on sparsity-matching definition + existence of Hodge counter-example).

### 5.4 Hodge conjecture — relation to depth parallel

**Relation between the 4-class refined framework and the classical Hodge conjecture**:
- **Classical Hodge (open frontier)**: $f_{\text{rational}}^{\text{Hodge}}(X, p) = \dim(\text{Hdg}^p/\text{im cl}) > 0$ for some smooth projective X and p — Millennium Prize problem from 1924 to the present.
- **Quantum 4-class (this paper)**: $M_{\text{unified}}^C(\rho) > 0$ in each class C **clearly exists** (T-state, Fock state, random-circuit, Bell state). Unlike classical Hodge, **counter-examples are abundant** on the quantum side.
- **Depth parallel conjecture**: Conjecture 4a.2 asserts classical-quantum typical-scale proportionality, but with no classical counter-example yet, the parallel is currently a **vacuous trivial parallel**.

**Role in this paper**: §5 T-AAS provides an anchor with **f_rational > 0 already established in 4 instances + a parallel framework to the classical Hodge open frontier**. Hodge ESTABLISHED → empirical f_rational > 0 classical instance / refute → suggestion of universal closure — the depth parallel status is determined either way. The structure "T-AAS with **16/16 fitness verified across 4 quantum instances**" guarantees framework predictive power (connection to pure-mathematics frontier via the bridge to classical Hodge).

---

## §6 Quantum-internal triangulation — Arrow 1 kernel narrowness 4-vertex

The 4 quantum instances (4 classes C₁-C₄) cover the **Arrow 1 kernel narrowness modalities of S15 with mutually different sparsity structures**, triangulating universality. Whereas the multi-domain Paper D performs "domain-level triangulation" and N1 performs "Arrow-level triangulation" (3-vertex Arrow focus), this paper adopts "**Arrow 1 kernel narrowness vertex triangulation**" (4 algebraic classes carry different sparsity modalities). The 4-vertex structure has higher dimensionality than N1's 3 vertices (Paper C / Stark / Brauer) (algebraic class taxonomy provides the internal decomposition of the Arrow 1 kernel).

### 6.1 4-vertex characterisation

| Class | Class definition | Arrow 1 kernel sparsity | ker_gauge | ker_topo | Classical Hodge parallel side |
|---|---|---|---|---|---|
| **C₁ Stabilizer** | STAB_n = Clifford orbit from $\|0...0⟩$, $\|STAB_n\| = 2^{n²+O(n)}$ discrete in $2^{2n}$ | discrete (measure zero) in continuous state space — "extremal points of the stabilizer polytope" | Clifford coset (discrete finite group) | magic resource = T-state injection ($M_F$) | convex hull of 'simple' generators (algebraic cycles ↔ stabilizer pure states) |
| **C₂ Gaussian** | derived from quadratic Hamiltonian $H = \frac{1}{2} x^T M x$, $W_\rho \geq 0$ everywhere, CV systems | poly-dim (Gaussian manifold dim ≈ N²) in infinite-dim Hilbert space — "symplectic group orbit" of vacuum | symplectic group $Sp(2N, \mathbb{R})$ orbit | Wigner negativity $\mathcal{N}$ = non-Gaussian resource | $\text{Hdg}^p \subset H^{p,p} \cap H^{2p}(X, \mathbb{Q})$ analytic ∩ rational intersection — analytic submanifold |
| **C₃ Eff-sim** | poly-time classical simulable (low-bond MPS, match-gate, stabilizer union), Nielsen $C = O(\text{poly}(n))$ | polynomial-parameter family in exp-dim state space — "BQP-vs-classical simulation frontier" | poly-depth circuit composition | super-polynomial complexity = quantum supremacy resource | the **computational complexity of the Hodge conjecture is open** (Millennium-open); the C₃ class parallels the **computational depth axis** of classical algebraic geometry |
| **C₄ Bell-local** | LHV-describable correlations, CHSH ≤ 2 (classical), Bell polytope | classical convex polytope embedded in larger quantum correlation body (Tsirelson bound $2\sqrt{2}$) | local unitaries $U_A \otimes U_B$ (pair-wise) | CHSH violation $\Delta_{\text{CHSH}}$ = nonlocal capacity | "algebraic cycles ↔ classical means" — classical correlation gap |

**Primary Arrow (common to all vertices)**: **Arrow 1 kernel** (T-AAS decomposition sparsity modality). Each monotone (M_F, 𝓝, C, Δ_CHSH) is classified to the **information layer on Arrow 3**, but in this vertex view the sparsity modality of the Arrow 1 kernel is the protagonist.

### 6.2 Closure of 4-vertex triangulation

**Closure claims**:
- **Layer level**: each class provides an independent f_rational > 0 instance → coincidence by a single class excluded.
- **Arrow level**: 4 instances have different Arrow 1 kernel sparsity modalities → the entire T-AAS Arrow 1 kernel taxonomy is independently verified (4 narrowness modalities correspond to 4 parallel directions of classical Hodge).
- **Obstruction level**: C₁ discrete-orbit covering / C₂ continuous-manifold parameterisation / C₃ complexity-class boundary / C₄ classical-polytope embedding — independence of 4 modalities is the closure ground for quantum-internal Arrow-level triangulation.

**Perspective shift (3-vertex → 4-vertex)**: in N1 the 3 NT instances each carry a different Arrow (Paper C 3 Arrows simultaneous / Stark Arrows 2-3 / Brauer Arrow 1 kernel). In this paper the 4 quantum instances each carry **different sparsity modalities of the same Arrow (Arrow 1 kernel)** — a triangulation perspective specific to the quantum side, focusing on the **internal decomposition of the Arrow 1 kernel**. N1 = cross-Arrow triangulation, Q1 = intra-Arrow taxonomy triangulation; the two are complementary perspectives.

None of the 4 quantum instances presupposes the other 3 to expose a particular sparsity modality of the Arrow 1 kernel — this independence is the evidence of quantum-internal universality.

### 6.3 N1 ↔ Q1 parallel observation (cross-paper)

| Aspect | N1 (NT) | Q1 (quantum) |
|---|---|---|
| Triangulation perspective | Arrow-level (3-vertex) | Arrow 1 kernel narrowness (4-vertex) |
| Primary instances | Paper C / Stark / Brauer | C₁ / C₂ / C₃ / C₄ |
| f_rational > 0 status | 1 open (Hodge NT-adjacent) + 3 instances ESTABLISHED | 4 ESTABLISHED instances + Hodge depth parallel conjecture |
| §4 dual lift | classical (ι_L, χ commutative) | non-commutative (Stone group, unitary representation) |
| Forward to | N2-N5 (NT-series final closure) | Q2-Q3 (Open QS chain + Born-Gleason) |

**Cross-validation**: N1 and Q1 **independently verify the same framework (S15 / 3 Arrows / T-AAS)** in 2 independent mathematical fields (NT, quantum) → the **domain-independent universality** of the framework is confirmed by 2-domain triangulation. N1 + Q1 = cross-domain anchor of universal validity of the framework.

---

## §7 Six-step protocol for new quantum domains

Procedure for new quantum domains (new Hilbert spaces, new unitary representation classes, new algebraic classes, new quantum resource theories) (`meta/new_domain_protocol.md` quantum specialisation):

| Step | Content |
|---|---|
| **0** | Identify §4 dual projection (quantum lift) — additive (Stone group {U(t)}, S¹ subgroup), multiplicative (unitary representation π: G → U(H), spectral decomposition), Bridge (Hilbert space, ℂ unit) |
| **1** | Identify Scan observable — can an exp kernel be written? additive scan ($e^{-iHt}$) / multiplicative scan ($e^{-βH}$)? S12 6+1 member correspondence? |
| **2** | Identify Structural observable — parameter-free integer/topological invariants, dim H, Schmidt rank, irrep index, group-theoretic invariants, topological invariants |
| **3** | Identify Information observable — log-derivative chain ($-\partial_T F = S$), Hartley $\log \dim H$, von Neumann $S(\rho)$, class monotones (M_F / 𝓝 / C / Δ_CHSH) |
| **4** | Verify three Arrows — Arrow 1 (does (A spectrum, ρ structure) encode Structural?), Arrow 2 ($Z \to F \to S$ thermodynamic chain), Arrow 3 (does Scan degenerate to log dim H at extreme limit?) |
| **5** | Confirm T-AAS decomposition — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? residence inside the 4-class refined Hodge (closest to which of C₁/C₂/C₃/C₄)? |
| **6** | Determine dictionary residence — residence within the L1 quantum 8 entries; propose a new entry if needed; identify connection point with Q2 Open QS chain |

**Verified applications**: per-class fitness verified for all 4 algebraic classes; 3/4 empirical (C₁ M_F 4e-16, C₂ Mari-Eisert 1e-4, C₄ Tsirelson 1e-6) + C₃ literature synthesis 4-ref.

**5 next candidates**: quantum coherence theory (Baumgratz-Cramer-Plenio 2014: incoherent in fixed basis = free states) / Quantum reference frame (G-invariance, asymmetric state resource) / Topological order (anyon braiding, Chern-Simons level) / Quantum error correction code states (stabilizer code subspace) / Quantum field theory states (CFT vacuum, Jefferson-Myers 2017 Nielsen complexity literature as C₃ extension candidate).

---

## §8 Consequences and open frontier

### 8.1 Established (quantum-only restatement)

1. **S15 Observable Trichotomy** — exhaustivity closed in 3 steps (§3.5)
2. **Arrow structure (3) and commutativity** — commutativity verified at 3 quantum instances (β→0 thermal limit, t→0 trivial unitary, ℏ→0 semiclassical / classical limit) (§4.4)
3. **T-AAS 4-class refined Hodge** — 16/16 quantum-relevant fitness across Stabilizer/Gaussian/Eff-sim/Bell-local; Theorem 4a.1 unified via class infidelity (§5.2-§5.3)
4. **Quantum-internal Arrow 1 kernel narrowness 4-vertex triangulation** — 4 instances with different sparsity modalities; intra-Arrow taxonomy view complementing N1's cross-Arrow triangulation (§6)
5. **Quantum-internal residence of S13/S14/S17** — π/ln 2/e as canonical constants on the three Arrows; complete on the 3-Arrow base (§4.5)
6. **Observation-optimal gauge theorem (quantum 2-instance contrast)** — qubit ρ_max coincide vs. Schmidt rank split as statement-only here (§4.5.1)
7. **N1 ↔ Q1 framework parallel** — same framework independently verified in 2 independent mathematical fields; 2-domain anchor of **domain-independent universality** of the framework (§6.3)

### 8.2 Q2-Q3 forward bridges

| Sequel | Topic | Forward from this paper |
|---|---|---|
| **Q2** Open QS chain | redevelop observation theory in quantum statistical mechanics language across the 4-stage chain open_quantum_systems → quantum_statistical_mechanics → quantum_thermodynamics → many_body_quantum | detailed development of §3.2 Scan family (Z(β) / response χ(ω) / KMS / FDT); §4.2 KMS-FDT equivalence on Arrow 2 (via Tomita-Takesaki modular theory); §5 perspective of T-AAS decomposition under Lindblad evolution + decoherence + pointer basis Einselection; quantum group action analogue of N3 Path 2 (KMS orbits) |
| **Q3** Born-Gleason | quantum closure of §4 dual = root; σ\* = √(2 ln 2) (half-amplitude gauge) in the Born rule + Gleason theorem framework; natural unit of quantum observation | full Busch-Gleason derivation of §2.3 §4 dual quantum root (PRL 2003, dim=2 resolution); σ\* closure of half-amplitude gauge in quantum residence of §4.5 S13 ln 2; §5 simultaneous theorem-isation of Born rule form (Tr(ρE)) and value (ρ_max = I/2) |

**8-gauge forward (N5 parallel)**: this paper makes gauge² explicit only as a listing in §1.3. Formal residence of the Origination matrix 8-gauge family quantum instances (e.g. π Berry phase, ln 2 qubit S, e info-density, ζ partition function regularisation) is reserved for the final closure of the Q-paper series (potential future Q4-Q5 candidates).

### 8.3 Open frontier

| Open question | Status | Related paper |
|---|---|---|
| **Conjecture 4a.2** (depth parallel quantitative form) | OPEN (depends on sparsity-matching definition + existence of Hodge counter-example) | §5.4, Q1 future |
| **Classical Hodge conjecture** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself, since 1924) | §5.4, NT-adjacent |
| **Quantum Reference Frame G-invariance** as 5th class candidate | OPEN | §7 next candidate |
| **Topological order (anyons) 5th class candidate** | OPEN | §7 next candidate |
| **Relation between OQ-Ω-Obs-1 minimal form and 4a refined form** | RESOLVED (4a is depth-matching extension) | OQ-Ω-Obs-4a §1 |
| **OQ-Ω-Obs-3 e-extremum** (Arrow 3 e residence) | ESTABLISHED 2026-04-23, 5/5 gate | §4.5 |
| **OQ-Ω-Obs-2 Arrow 1⁻¹ generation** | PARTIAL_CLOSED 2026-04-22 | §4.6, future |
| **σ\* = √(2 ln 2) half-amplitude gauge** | candidate (Q3 forward) | Q3 |
| **dim=2 Gleason gap full closure** (full Busch-Gleason) | ESTABLISHED 2003 (Busch PRL) | §6.1 (primary Arrow), Q3 |
| **Quantum 8-gauge origination matrix** | OPEN (Q-series future) | §8.2 |
| **Extension to quantum field theory + CFT** | out of scope (this paper restricted to L1 quantum 8 entries) | future Q-series |

### 8.4 Dictionary residence map

| Piece in this paper | Residence | Status (Q1) |
|---|---|---|
| §2.1 Axiom 1 (Dual receptacle quantum lift) | `c_phase_complex.md §4` + `q_quantum_observation.md §1-§2` | existing reuse |
| §2.2 Axioms A0-A7 (quantum instances) | `finite_observation.md §1-§7` + `observation_canon.md §2` + this §2.2 NEW quantum instance examples | existing + this paper expansion |
| §2.4 L0 v1 + L0 v2 (quantum instances) | `finite_observation.md §8` + `observation_canon.md §3` + this §2.4 NEW quantum instance examples | ESTABLISHED 2026-04-23 + this paper expansion |
| §3 S15 + quantum enumeration closure | `c_theorems_master.md` row S15 + this §3.5 quantum-only annex (NEW) | annex to be implemented (post-v0.2 backward) |
| §3.2-§3.4 Scan/Structural/Information family | `c_theorems_master.md` + `q_quantum_observation §3-§6` + `q_quantum_statistical_mechanics §3-§4` + `q_fine_structure` + `q_gauge_field_theory` | existing reuse |
| §4 three-Arrow framework (quantum lift) | `c_arrow_framework.md` | existing L1 entry as of 2026-04-23 |
| §4.4 Arrow commutativity (3 quantum instances) | `c_arrow_framework.md §4.2.1` + this §4.4 NEW quantum instance annex | annex to be implemented |
| §4.5 / §4.5.1 S13/S14/S17 residence + quantum instances | `c_arrow_bridge_constants.md §5-§6` + §11 (existing, from N3) + this §4.5 quantum expansion | existing + quantum expansion to be implemented |
| §4.6 inverse Arrows + obstruction (quantum-restricted) | `c_arrow_obstruction.md §11` + quantum subset filter | existing + this paper's quantum scope filter |
| §5 T-AAS 4-class | `c_arrow_obstruction.md §10` (T-AAS) + `oq_omega_obs_4a_refined_quantum_hodge_v0.md` (4-class formal) | existing + research file integration |
| §5.3 Theorem 4a.1 unified | `c_filtration_obstruction.md` (T-AAS f_rational instance, NEW 4-class quantum lift annex) | annex to be implemented |
| §5.4 Hodge depth parallel | `c_filtration_obstruction.md` Hodge open + this §5.4 quantum 4-instance closure annex (NEW) | annex to be implemented |
| §6 quantum-internal 4-vertex triangulation | NEW `meta/triangulation_methodology.md §11` quantum-internal Arrow 1 kernel narrowness annex | annex to be implemented |
| §7 6-step protocol (quantum specialisation) | NEW `meta/new_domain_protocol.md §9` quantum specialisation annex | annex to be implemented |
| §6.3 N1 ↔ Q1 parallel | NEW `meta/triangulation_methodology.md §12` cross-paper framework parallel annex | annex to be implemented |

**post-v0.2 backward statistics**: 7 dictionary annex write-backs anticipated after Q1 drafting: c_theorems_master quantum-only S15 enumeration / c_arrow_framework §4.2.2 quantum Arrow commutativity / c_arrow_bridge_constants §12 quantum instance expansion (S13 qubit, S17 qubit/qutrit info-density) / c_filtration_obstruction 4-class quantum lift annex (Theorem 4a.1) / meta/triangulation_methodology §11 (4-vertex) + §12 (N1 ↔ Q1 parallel) / meta/new_domain_protocol §9 quantum specialisation.

**Consequence**: this paper is positioned as the **quantum-internal framework header** of the dictionary; theorems / definitions formally reside in L0 / L1 quantum / meta entries. After drafting Q2 (Open QS chain 4-stage) + Q3 (Born-Gleason closure), the **3-layer link** (framework header → result paper → dictionary backward) **completes** (parallel to the N1-N5 series).

---

## Change log

- **v0.2 (2026-04-27)**: compact version. Reduced redundancy from v0.1 (733 lines) — Abstract 6 main results condensed; §1.1/§1.2/§1.3 simplified; §2.3 §4 dual explanation reduced to a table + 1 paragraph (necessity of ℂ citation compressed to 1 paragraph); §2.4 L0 v2 axioms (a')-(d') reduced to a paragraph; §3 per-layer commentary tabularised + only conclusion paragraphs; §3.5 closure 3-step verification simplified; §4.4 Arrow commutativity table preserved with commentary compressed; §4.4.1 Fi/I table preserved; §4.5/§4.5.1 S13/S14/S17 + observation-optimal simplified; §5 redundancy in T-AAS § reduced (4-class table + per-class fitness witness preserved as core); §5.3 Theorem 4a.1 formulae fully preserved; §5.4 Hodge depth parallel compressed; §6.1-§6.4 each-class subsections (4 subsections) compressed into 1 unified table; §6.5 closure claims + §6.6 N1↔Q1 parallel renamed and compressed into §6.2/§6.3; §7 protocol table preserved; §8.4 residence map commentary compressed + post-v0.2 backward statistics in 1 paragraph. Skeleton, claims, instance numerics, and status notation all preserved.
- **v0.1 (2026-04-27)**: initial Q-only draft. Quantum specialisation derived from Paper D v0.9.2 (multi-domain frozen-internal). Parallel framework header to N1 (NT-only). Rebuilt via Arrow 1 kernel narrowness 4-vertex triangulation by 4 quantum instances (C₁/C₄ OQ-Ω-Obs-4a 4-class refined Hodge).

---

## References (internal)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**N1 series (parallel framework header)**: `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.7, NT-only restatement)

**Sources of results developed in this paper**:
- `research/oq_omega_obs_4a_refined_quantum_hodge_v0.md` (ESTABLISHED 2026-04-23, 6/6 gate) — §5.2 4-class formal + §5.3 Theorem 4a.1
- `research/oq_omega_obs_4a_monotone_verify.py` — §5.2 empirical verification (C₁ M_F 4e-16, C₄ CHSH 1e-6)
- `research/oq_omega_obs_1_ker_entangle_frational_path_v0.md` (CONFIRMED 2026-04-22) — §4.6 minimal form (Schmidt rank → f_rational, depth-deficient)
- `research/oq_omega_obs_3_e_arrow3_v0.md` (ESTABLISHED 2026-04-23) + `oq_omega_obs_3_info_density_check.py` (5/5 gate) — §4.5 quantum S17 e-extremum
- `research/oq_omega_obs_4_noncommutative_scan_v0.md` (parent OQ for 4a)
- `research/oq_l0_refinement_finite_infinite_2axis_v0.md` (ESTABLISHED 2026-04-23) — §2.4 L0 v2 quantum instances
- `research/bidirectional_duality_v0.md` — §2.3 §4 dual root + §3.2 quantum S15 connection

**L0 / L1 / meta dependencies**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11, c_filtration_obstruction, c_observation_optimal_gauge, c_spectral §3}.md` / `L1_mathematical/quantum/{q_quantum_observation §1-§9, q_action_principles, q_gauge_field_theory, q_fine_structure}.md` (main material of this paper) / `L1_mathematical/quantum/{q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum}.md` (main material of Q2 forward) / `meta/{triangulation_methodology, new_domain_protocol}.md`

**Sequel papers**: Q2 (Open QS chain 4-stage) / Q3 (Born-Gleason + dim=2 closure + σ\* gauge) — drafting planned
