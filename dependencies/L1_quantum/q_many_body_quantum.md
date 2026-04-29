---
axis: B
position: many_body_quantum
static_dynamic: both
connected_to:
  - B.quantum_thermodynamics
  - B.quantum_chemistry
  - B.condensed_matter
  - A.algebra_analysis
  - C.complex_systems
arrow_status:
  upstream: done
  downstream: stub
updated: 2026-04-08
---

# Many-Body Quantum Mechanics

**Level**: L1 (domain-independent mathematical structure, final L1 file on B-spine)
**Dependencies**: q_quantum_thermodynamics.md (§1 free energy, §5 Landauer, §6 phase transitions), q_quantum_statistical_mechanics.md (§2 KMS, §6 BE/FD), q_open_quantum_systems.md (§4 Lindblad)
**Downstream**: quantum_chemistry.md (stub, chemistry branch), condensed_matter.md (stub, physics branch) — both L2

---

## §0 Thesis

Many-body quantum mechanics is the theory of what happens when the thermodynamic black box is opened. Where q_quantum_thermodynamics.md treated the system as characterized by macroscopic variables (F, S, T, μ), many-body QM asks: what are the microscopic constituents, how do they interact, and what collective structures emerge?

This is the B-spine's final L1 file. Everything before this point (quantum_observation → open_quantum_systems → QSM → QTD) is material-independent: it applies to any quantum system regardless of its internal composition. Many-body QM breaks this universality by introducing specific Hamiltonians, specific particle types, and specific interactions. But it does so at the L1 level — the structures described here (second quantization, quasiparticles, mean field theory, Born-Oppenheimer) are mathematical frameworks that apply across all material realizations. The choice of which Hamiltonian describes which material is L2 territory.

In L0 language: many-body QM is where the thermal window (QTD) is supplemented by a compositional window — the observer now sees not just macroscopic variables but the internal structure of the system. The central question is: **what effective degrees of freedom does this compositional window reveal?**

The central objects of many-body QM are:
1. **Second quantization** — the formalism for identical particles in variable number (§1)
2. **Interactions and symmetry** — how constituents couple and what symmetries constrain the coupling (§2)
3. **Mean field / Hartree-Fock** — the simplest variational approximation: replace many-body correlations with an effective single-particle picture (§3)
4. **Born-Oppenheimer approximation** — scale separation between fast and slow degrees of freedom (§4)
5. **Quasiparticles** — the crown jewel: interacting many-body systems develop effective degrees of freedom that behave as weakly interacting particles (§5)
6. **Spontaneous symmetry breaking and order** — the microscopic mechanism behind QTD's phase transitions (§6)

Note on ordering: Quasiparticles (§5) are the crown jewel because they answer the L0 question directly: the compositional window reveals not the bare constituents but emergent effective particles. Mean field (§3) and Born-Oppenheimer (§4) are both approximation schemes that produce quasiparticles as output — they are methods, while quasiparticles are the structural result.

---

## §1 Second Quantization

### 1.1 Fock space

For systems of identical particles with variable number, the Hilbert space is the Fock space:

    F = ⊕_{n=0}^{∞} H^{(n)}

where H^{(n)} is the n-particle Hilbert space (symmetric for bosons, antisymmetric for fermions). Fock space unifies zero-particle (vacuum), one-particle, two-particle, ... sectors into a single framework.

### 1.2 Creation and annihilation operators

The basic objects are:
- a†_k: creation operator for state k (adds one particle in state k)
- a_k: annihilation operator for state k (removes one particle from state k)

Commutation relations encode statistics (QSM §6):
- Bosons: [a_k, a†_l] = δ_{kl}
- Fermions: {a_k, a†_l} = δ_{kl}

Any n-particle observable can be written in terms of a†, a. The general Hamiltonian:

    H = Σ_{kl} t_{kl} a†_k a_l + ½ Σ_{klmn} V_{klmn} a†_k a†_l a_n a_m

where t_{kl} is the single-particle (kinetic + external potential) matrix and V_{klmn} is the two-body interaction matrix.

### 1.3 L0 translation

Second quantization is not new physics — it is a bookkeeping device that makes the permutation gauge (QSM §6.1, indistinguishability as window constraint) automatic. In L0 terms: the observer cannot distinguish identical particles, so the formalism is built to respect this constraint from the start. The creation/annihilation algebra is the algebra of observables compatible with the permutation-invariant window.

### 1.4 Number operator and conservation

The number operator N = Σ_k a†_k a_k counts total particles. If [H, N] = 0, particle number is conserved and the grand canonical approach (QTD §2.4) applies with chemical potential μ. If [H, N] ≠ 0 (pair creation/annihilation), particle number fluctuates and only the Fock space description is adequate.

---

## §2 Interactions and Symmetry

### 2.1 The interaction term

The two-body interaction V_{klmn} in §1.2 is what makes many-body physics non-trivial. Without it (V = 0), the system is a collection of independent particles described by QSM §6 (BE/FD statistics). With it, correlations emerge that are not captured by single-particle states.

The key question is not "what is V?" (that is L2, material-specific) but "what symmetries does V respect?"

### 2.2 Symmetry classification

The symmetry group G of the Hamiltonian constrains the form of V:

| Symmetry | Physical content | Constraint on V |
|---|---|---|
| Translation | Homogeneity of space | V depends only on r_1 - r_2 |
| Rotation SO(3) | Isotropy of space | V depends only on |r_1 - r_2| |
| Time reversal | Microscopic reversibility | V is real (in appropriate basis) |
| U(1) | Particle number conservation | V conserves N |
| SU(2) spin | Spin rotation invariance | V is spin-independent (or has specific spin structure) |
| Discrete (lattice) | Crystal symmetry | V respects space group G (→ L2 crystal) |

L1 content: the classification of possible symmetries. L2 content: which symmetry is realized in which material.

### 2.3 Weakly vs strongly interacting

The ratio of interaction energy to kinetic energy determines the regime:

- **Weakly interacting** (V/t ≪ 1): perturbation theory applies. Quasiparticles are well-defined (§5).
- **Strongly interacting** (V/t ~ 1): non-perturbative. Quasiparticle picture may break down. New organizational principles needed (entanglement structure, topological order).

The boundary between weak and strong coupling is where many-body physics is most difficult and most rich. QTD's phase transitions (§6) typically occur at or near this boundary.

---

## §3 Mean Field and Hartree-Fock

### 3.1 The mean field idea

Replace the many-body problem with an effective single-particle problem:

    H_{MF} = Σ_{kl} h^{eff}_{kl} a†_k a_l

where h^{eff} includes the average effect of interactions:

    h^{eff}_{kl} = t_{kl} + Σ_{mn} V_{kmln} ⟨a†_m a_n⟩

The self-consistency condition: ⟨a†_m a_n⟩ is computed from the eigenstates of h^{eff}, which depends on ⟨a†_m a_n⟩. This is a nonlinear fixed-point problem.

### 3.2 Hartree-Fock for fermions

For fermions, the variational ansatz is a single Slater determinant:

    |Ψ_{HF}⟩ = a†_{φ_1} a†_{φ_2} ... a†_{φ_N} |0⟩

The orbitals {φ_i} are determined by minimizing ⟨Ψ_{HF}|H|Ψ_{HF}⟩. This yields the Hartree-Fock equations:

    [t + V_H + V_X] φ_i = ε_i φ_i

where V_H is the Hartree (direct) potential and V_X is the exchange (Fock) potential. The eigenvalues ε_i are single-particle energies in the mean field — the first approximation to quasiparticle energies (§5).

### 3.3 L0 translation

Mean field is the observer's first approximation: replace the full many-body pattern m(S) with the best single-particle pattern m(S|_{W_1}) that the one-body window W_1 can capture. The residual m(S) - m(S|_{W_1}) is the correlation energy — the information lost by reducing the many-body window to a one-body window.

This connects to the rate-distortion picture (Landauer, QTD §5.6): the mean field observer chooses a low-rate description (single-particle states) at the cost of distortion (correlation energy). More accurate descriptions (configuration interaction, coupled cluster) increase the rate and reduce the distortion.

### 3.4 Beyond mean field

Systematic improvements:
- **Configuration interaction (CI)**: expand in multiple Slater determinants
- **Coupled cluster (CC)**: exponentiate cluster operators (size-consistent)
- **Density functional theory (DFT)**: rewrite in terms of electron density ρ(r)

Each increases the complexity of the compositional window. The hierarchy CI ⊂ CC ⊂ full CI parallels L0's hierarchy of window resolutions.

---

## §4 Born-Oppenheimer Approximation

### 4.1 Scale separation

In systems with nuclei (mass M) and electrons (mass m), the ratio m/M ≈ 1/1836 is small. Born-Oppenheimer exploits this:

1. Fix nuclear positions R = {R_1, ..., R_N}
2. Solve the electronic problem: H_el(R) ψ_n(r; R) = E_n(R) ψ_n(r; R)
3. Use E_n(R) as the effective potential for nuclear motion

The electronic energy surface E_n(R) is the central object of quantum chemistry.

### 4.2 Adiabatic and diabatic

The BO approximation is adiabatic: electrons follow nuclear motion instantaneously (fast degrees of freedom equilibrate on the timescale of slow degrees of freedom). When energy surfaces E_n(R) approach each other (conical intersections, avoided crossings), the adiabatic approximation breaks down and non-adiabatic transitions occur.

### 4.3 L0 translation: window hierarchy

BO is a hierarchical window structure:
- **Electronic window** W_el: sees electron coordinates r, treats R as parameters
- **Nuclear window** W_nuc: sees nuclear coordinates R, uses E_n(R) as effective potential

The two windows are nested: W_nuc operates on the output of W_el. This is L0's window concept applied to scale separation: different observation timescales reveal different effective structures.

The breakdown of BO at conical intersections is where the window hierarchy collapses — the fast and slow degrees of freedom become entangled, and no single-timescale window suffices.

### 4.4 BO as quasiparticle generator

BO produces quasiparticles (§5): the nuclei-on-energy-surface are quasiparticles of the electronic system. Their effective mass, interactions, and statistics are determined by the electronic energy surface E_n(R), not by the bare nuclear properties. This is the chemistry branch's version of the quasiparticle concept.

---

## §5 Quasiparticles

### 5.1 The concept

A quasiparticle is a collective excitation of an interacting many-body system that behaves, to good approximation, as a single particle with renormalized properties (effective mass, charge, lifetime).

The idea: start with the interacting ground state |Ω⟩. Add one particle (or one excitation). In a non-interacting system, this creates an eigenstate. In an interacting system, the added particle "dresses" itself with a cloud of virtual excitations from the medium — the bare particle plus its dressing cloud is the quasiparticle.

### 5.2 Landau Fermi liquid

For interacting fermions at low temperature (the Fermi liquid), Landau showed that:
1. There is a one-to-one correspondence between the excitations of the interacting system and those of a free Fermi gas
2. Each excitation (quasiparticle) has a well-defined momentum k, spin σ, and energy ε(k)
3. The quasiparticle energy ε(k) differs from the bare energy by a self-energy correction
4. Quasiparticles have finite lifetime τ(k) ∝ 1/(ε(k) - ε_F)² near the Fermi surface

The key insight: the interacting system is described not by the bare electrons but by quasielectrons — electrons dressed by interaction clouds. The Fermi surface survives (Luttinger's theorem), but the effective mass m* ≠ m.

### 5.3 Why quasiparticles are the crown jewel

Quasiparticles are the many-body realization of L0's central principle: **the observed pattern m(S|_W) is not the structure S itself but what the window reveals.**

In the many-body context:
- **S** = the exact many-body wavefunction |Ψ⟩ (exponentially complex, 10²³ degrees of freedom)
- **W** = the compositional window (what the observer can probe: single-particle excitations, response functions, spectral functions)
- **m(S|_W)** = the quasiparticle picture (a manageable number of effective degrees of freedom with renormalized properties)

The quasiparticle is what the window sees. It is not a "real" particle — it is a pattern in the observation. The bare electron is "real" but unobservable (hidden in the exponentially complex wavefunction). The quasielectron is observable but "emergent."

This is L0's philosophy instantiated in condensed matter: **reality is the structure S, but physics operates on the pattern m(S|_W). The gap between them is the many-body correlation energy — the information lost through the compositional window.**

### 5.4 The spectral function

The quasiparticle picture is formalized by the single-particle spectral function:

    A(k, ω) = -(1/π) Im G^R(k, ω)

where G^R is the retarded Green's function. For a non-interacting system, A(k, ω) = δ(ω - ε_k) — sharp peaks at bare energies. For an interacting system:

    A(k, ω) ≈ Z_k · δ(ω - ε*_k) + incoherent background

where Z_k ∈ (0,1] is the quasiparticle residue (spectral weight) and ε*_k is the quasiparticle energy. Z_k measures how much of the bare particle survives in the quasiparticle: Z = 1 is a perfect quasiparticle (non-interacting), Z → 0 means the quasiparticle dissolves into the incoherent background.

### 5.5 L0 translation of Z

The quasiparticle residue Z has a direct L0 interpretation:

    Z = fraction of single-particle information preserved by the many-body window

When Z = 1, the compositional window reveals the full single-particle structure — no information is lost. When Z < 1, part of the single-particle information has been redistributed into many-body correlations that the single-particle window cannot see. When Z → 0, the single-particle window is blind — the quasiparticle has dissolved, and a qualitatively different description is needed (spin-charge separation, topological order, etc.).

This connects to the rate-distortion framework: Z is a measure of how much of the structure survives through the compositional window. Low Z = high distortion = the single-particle description is lossy.

### 5.6 Three-stage chain completion

The B-spine's crown jewel chain is now:

```
QSM §5 FDT           QTD §5 Landauer       many_body §5 Quasiparticle
(equilibrium)    →    (information)     →    (emergence)
fluctuation =        erasure has cost        observation reveals
dissipation                                   effective particles
```

Each crown jewel addresses observation from a different angle:
- FDT: what the thermal window spontaneously reveals = how it responds to probes
- Landauer: observation has irreducible cost (kT ln 2 per bit)
- Quasiparticle: what the compositional window reveals is not what's "really there" but what's effective

---

## §6 Spontaneous Symmetry Breaking and Order

### 6.1 Microscopic mechanism

QTD §6 described phase transitions as singularities in the thermodynamic limit. Many-body QM provides the microscopic mechanism: spontaneous symmetry breaking (SSB).

SSB occurs when the ground state |Ω⟩ has lower symmetry than the Hamiltonian H. The symmetry group G of H is broken to a subgroup H ⊂ G. The order parameter ψ transforms non-trivially under G/H.

### 6.2 Goldstone theorem

When a continuous symmetry is spontaneously broken, gapless excitations (Goldstone modes) appear — one for each broken generator. These Goldstone modes are quasiparticles (§5) with specific properties:
- Dispersion ω(k) → 0 as k → 0 (gapless)
- Long-range correlations (power-law decay)

Examples:
- Broken translation → phonons (sound waves in solids)
- Broken U(1) → superfluid phonon (Bogoliubov mode)
- Broken SU(2) spin → magnons (spin waves)

### 6.3 L0 translation: gauge selection by the system

In L0, A3 (gauge invariance) states that the observer's choice of gauge should not affect the physics. SSB adds a twist: the system itself selects a gauge (a preferred direction in order-parameter space). This is the dynamical version of A3, complementing q_open_quantum_systems.md's pointer basis selection (OQ-OQS1):

- **Decoherence** (q_open_quantum_systems.md §5): the environment selects which basis survives → dynamical gauge fixing at the quantum level
- **SSB** (this section): the many-body ground state selects which symmetry-broken sector is realized → dynamical gauge fixing at the thermodynamic level

Both are instances of the environment (in a generalized sense) selecting the gauge that the observer sees.

### 6.4 Topological order

Not all many-body order is characterized by SSB. Topological order — order without a local order parameter — represents a qualitatively different phenomenon. In topological phases:
- The ground state degeneracy depends on the topology of the space
- Excitations have fractional statistics (anyons)
- No local order parameter distinguishes the phase

In L0 terms: topological order is structure that is invisible to any local window. It requires a global (topological) window to detect. This suggests that L0's window concept may need extension to include global/topological windows alongside local ones. This is OQ-MB1 (§10).

---

## §7 L0 Translation Table

### 7.1 Dictionary

| Many-body concept | L0 concept | Section |
|---|---|---|
| Second quantization | Permutation-invariant observable algebra | §1.3 |
| Interaction V | Coupling between window sectors | §2.1 |
| Mean field approximation | Single-particle window (low rate, high distortion) | §3.3 |
| Correlation energy | Information lost through one-body window | §3.3 |
| Born-Oppenheimer | Hierarchical window (fast/slow separation) | §4.3 |
| Quasiparticle | Effective degree of freedom revealed by compositional window | §5.3 |
| Quasiparticle residue Z | Fraction of single-particle info surviving many-body window | §5.5 |
| SSB | Dynamical gauge selection by the system | §6.3 |
| Goldstone mode | Gapless quasiparticle from broken continuous symmetry | §6.2 |
| Topological order | Global/topological window structure (OQ-MB1) | §6.4 |

### 7.2 The compositional window

Many-body QM introduces a compositional window W_comp on top of the spectral window W and thermal window W_β (QSM §7.2):

- **W** (spectral): which modes the observer accesses
- **W_β** (thermal): what coarse-graining scale describes the bath
- **W_comp** (compositional): what internal structure the observer resolves

The full observation window is now (W, W_β, W_comp). The richness of many-body physics comes from the interplay between these three windows:
- Mean field: W_comp resolves single particles only
- Correlated methods: W_comp resolves pair correlations, triple correlations, ...
- Exact solution: W_comp resolves the full N-body state (exponentially costly)

### 7.3 Window chain summary

The B-spine's window evolution:

```
quantum_observation:      W (spectral)
open_quantum_systems:     W + partial trace (bath window)
QSM:                      W + W_β (thermal)
QTD:                      W + W_β + Legendre gauge structure
many_body:                W + W_β + W_comp (compositional)
```

Each step adds a new dimension to the observation window. The B-spine is the progressive opening of the window structure, from the minimal spectral window to the full (spectral, thermal, compositional) observation.

---

## §8 Control Theory Connection

### 8.1 Many-body control

| Many-body setting | Control theory analogue |
|---|---|
| Quasiparticle engineering | Designing the effective single-particle picture |
| Mean field optimization | Finding the best low-rank controller |
| BO energy surface | Landscape for nuclear trajectory optimization |
| Correlation energy | Control cost of exceeding mean field |
| SSB | Bifurcation and symmetry-breaking in controlled systems |

### 8.2 Quantum simulation and control

The ultimate many-body control problem: design a Hamiltonian H that produces desired quasiparticles. This is quantum simulation — using one many-body system to emulate another. In L0 terms: engineering the compositional window to reveal specific effective degrees of freedom.

---

## §9 Bridge to L2: Chemistry and Condensed Matter

### 9.1 What this file establishes

- Second quantization as the identical-particle formalism (§1)
- Interaction and symmetry classification (§2)
- Mean field / Hartree-Fock as variational approximation (§3)
- Born-Oppenheimer as scale separation (§4)
- Quasiparticles as the crown jewel: emergent effective degrees of freedom (§5)
- SSB and topological order as organizational principles (§6)

### 9.2 The B-spine bifurcation

Many-body QM is the last L1 file on the B-spine. Here the spine splits into two L2 branches:

**Chemistry branch** (B-spine left):
many_body → quantum_chemistry → reaction_dynamics → biochemistry → molecular_biology

**New structure**: specific atoms, molecules, bonding. Born-Oppenheimer energy surfaces for specific nuclear configurations. Quasiparticles = molecular orbitals, phonons of molecular vibrations.
**What is gained**: chemical specificity — which atoms bond, how, and why
**What is preserved**: all L1 structures (QSM, QTD, many_body)

**Physics branch** (B-spine right):
many_body → condensed_matter → crystal / continuum → fluid / elastic / diffusion

**New structure**: periodic lattices, continuum fields, macroscopic phases. Quasiparticles = phonons, magnons, plasmons, excitons on specific lattices.
**What is gained**: material properties — conductivity, magnetism, superconductivity
**What is preserved**: all L1 structures

### 9.3 Arrow structure

```
q_quantum_thermodynamics.md         q_many_body_quantum.md
(thermodynamic, Legendre)    →    (interacting, quasiparticles)
                          + interactions
      preserves: potentials, phases
      loses: material-independence
                                          │
                              ┌───────────┴───────────┐
                              ↓                       ↓
                  quantum_chemistry.md        condensed_matter.md
                  (L2, chemistry)             (L2, physics)
                  + specific atoms            + specific lattices
```

### 9.4 S15 接続 (2026-04-11)

| S-ID | 本ファイルとの関係 | 層 |
|---|---|---|
| S15 | **Scan**: Green 関数 G(k,ω) = (ω - ε_k - Σ(k,ω))^{-1} (scanner = (k,ω), 加法 scan の拡張)。**Structural**: quasiparticle residue Z (0 or 非零, 整数的相転移), 格子次元 d, topological invariants (Chern number, winding number)。**Information**: entanglement entropy S_ent (area law vs volume law), topological entanglement entropy γ | 全 3 層 |
| Arrow 1 | Green 関数の極構造 (Scan) → quasiparticle spectrum の分類 (Structural: phonon/magnon/exciton) | Scan → Structural |
| Arrow 3 | ground state degeneracy (Structural, 整数) → topological entanglement entropy log D (Information) | Structural → Information |

**注**: many_body は B-spine の下流端であり、QTD の Arrow 2 (Z→F→S) の結果を受け取る側。独自の Arrow 2 は Green 関数 → self-energy → spectral function → occupation → entropy の chain。

参照: bidirectional_duality_v0.md §5, theorems_master S15。

---

## §10 Open Questions

**OQ-MB1** (structural, high priority): Does L0 need a topological window?

Topological order (§6.4) is invisible to any local window — it requires global information (ground state degeneracy on different topologies, non-local string operators). If L0's current window concept is inherently local, topological order lies outside its scope. This would mean L0 is incomplete: it captures all local observation structure but misses global/topological structure.

**Test**: Can topological invariants (Chern number, topological entanglement entropy) be expressed as m(S|_W) for some suitably defined global window W? If yes, L0 accommodates topological order by generalizing W. If no, L0 needs a new axiom for global structure.

**OQ-MB2** (quasiparticle, medium priority): Is quasiparticle breakdown the compositional version of phase transition?

In Fermi liquids, Z > 0 and quasiparticles are well-defined. In non-Fermi liquids (strange metals, Luttinger liquids), Z → 0 and the quasiparticle picture breaks down. Is this breakdown a "phase transition in the compositional window" — a singularity where the single-particle window becomes qualitatively inadequate?

If yes, there is a hierarchy of window transitions:
- QTD phase transitions: singularity in the thermal window
- Quasiparticle breakdown: singularity in the compositional window
- Decoherence: singularity in the quantum/classical window (q_open_quantum_systems.md)

All three would be instances of "the window itself undergoes a qualitative change." This connects to OQ-QSM4 (window dimensionality) and OQ-QTD4 (critical exponents).

**OQ-MB3** (entanglement, medium priority): Is many-body entanglement structure the compositional version of the thermal window?

In many-body systems, the entanglement entropy S_ent of a subsystem measures how much information is shared between the subsystem and its complement. For ground states:
- Area law: S_ent ∝ surface area of subsystem (gapped systems)
- Volume law: S_ent ∝ volume of subsystem (generic excited states)
- Logarithmic correction: S_ent ∝ (area) + c/3 log L (critical systems, conformal field theory)

The entanglement structure determines how efficiently the state can be described by tensor networks (MPS, PEPS). In L0 terms: entanglement entropy measures the information shared across the compositional window boundary. Area law = the compositional window is efficient (low rate). Volume law = the compositional window is maximally inefficient (high rate).

**OQ-MB4** (bridge, low priority): Can the chemistry-physics bifurcation be understood as a window choice?

Chemistry and condensed matter apply the same L1 structures (many_body) to different material contexts. Is the bifurcation a choice of compositional window? Chemistry: W_comp resolves individual atoms and bonds (localized). Physics: W_comp resolves collective modes and lattice periodicity (delocalized). If the bifurcation is a window choice, the two branches are gauge-equivalent descriptions of the same underlying many-body structure — different m(S|_W) for different W, same S.

---

*作成日: 2026-04-08*
*最終更新: 2026-04-08*
