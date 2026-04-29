---
axis: C
position: control_theory
static_dynamic: both
connected_to:
  - C.complex_systems
  - C.dynamical_systems
  - C.scaling
  - A.algebra_analysis
  - B.fx
  - B.crystal
  - D.electrophysiology
  - D.connectomics
arrow_status:
  upstream: done
  downstream: stub
updated: 2026-04-08
---

# Control Theory Dictionary

## 0. Thesis

Control theory is the engineering formalization of L0's finite observation axioms. The state-space model (x, y = Cx) is the triple (S, W, m) in operator form. Observability asks "what can the window see?", controllability asks "what can the window reach?", and estimation theory (Kalman) is the optimal reconstruction of S from m(S|_W).

ΣΦ has been predominantly an observation theory. Control theory contributes the **dual** perspective: not just what structure is visible, but what structure is actionable. This duality (see/reach) is the C-axis bridge between L0 axioms and E-axis applications.

---

## 1. State-Space Model ↔ L0 Triple

### 1.1 The correspondence

| Control theory | L0 (finite_observation.md) | Role |
|---|---|---|
| State x ∈ ℝ^n | S (infinite structure) | The full object |
| Output y = Cx ∈ ℝ^p | m(S\|_W) | What the window shows |
| Output matrix C | W (window operator) | Which components are visible |
| Input u, B matrix | (no L0 analogue) | **New**: what the observer can change |
| Dynamics A (ẋ = Ax + Bu) | (implicit in L0) | How S evolves |

L0 treats S as static or externally evolving. Control theory adds two structures L0 lacks:
1. **Input**: the observer can perturb the system (Bu term)
2. **Dynamics**: the system has autonomous evolution (Ax term)

### 1.2 Finite-dimensional axiom

Control theory's standard setting is dim(x) = n < ∞. This is exactly A0a (finiteness). The infinite-dimensional generalization (PDEs, distributed control) parallels L0's "infinite limit as mathematical idealization."

### 1.3 Discrete vs continuous time

| Setting | Dynamics | L0 parallel |
|---|---|---|
| Continuous: ẋ = Ax + Bu | Differential flow | Infinite-precision limit |
| Discrete: x_{k+1} = Ax_k + Bu_k | Map iteration | **Operationally native** to L0 |

L0's finite observer naturally works in discrete time. Continuous-time control is the mathematical idealization (like L → ∞ in number theory).

---

## 2. Observability ↔ A0b (Partial Access)

### 2.1 Definition

A system (A, C) is **observable** if the initial state x_0 can be uniquely determined from the output history {y_0, y_1, ..., y_{n-1}}.

**Rank condition**: Observable iff rank(O) = n, where:

```
O = [C; CA; CA²; ...; CA^{n-1}]    (observability matrix)
```

### 2.2 Translation to L0

| Observability concept | L0 translation |
|---|---|
| rank(O) = n (fully observable) | Window W reveals all of S |
| rank(O) = r < n (partially observable) | W sees r-dimensional projection of S |
| Unobservable subspace ker(O) | Structure invisible to window W |
| Observable decomposition | Decomposition of S into visible + invisible parts |

**A0b says**: the observer obtains one outcome per measurement. In control terms, this is p < n (output dimension less than state dimension). The observer needs **multiple measurements across time** (the rows CA^k) to reconstruct x — this is exactly "repeated measurements on identically prepared systems" from A0b.

### 2.3 Observability Gramian

The observability Gramian W_o = Σ_{k=0}^{T-1} (A^k)^T C^T C A^k quantifies **how well** each state direction is observed. Its eigenvalues measure observation quality per direction:

- Large eigenvalue → well-observed direction (fast convergence)
- Small eigenvalue → poorly observed direction (slow convergence)
- Zero eigenvalue → unobservable direction

**L0 parallel**: This is A2 (convergence rate as observable). The Gramian eigenvalue spectrum tells you WHICH parts of S converge fast/slow under increasing observation window T. The condition number κ(W_o) = λ_max/λ_min is the observability analogue of the resolution-channel tradeoff (§2.1 in finite_observation.md).

### 2.4 Cross-domain instances

| Domain | State x | Output y = Cx | Unobservable subspace |
|---|---|---|---|
| Number theory | {a_n mod L} full distribution | Fourier modes k ≤ k_N = floor(ω/2) | Modes k > k_N (aliased by finite window) |
| Crystal | ρ(r) electron density (full) | F(hkl) for \|h\| ≤ h_max | High-frequency components ρ_k with \|k\| > h_max |
| FX | Full N×N correlation matrix | Eigenvalue spectrum (K pairs) | Eigenvector phases (gauge-dependent, A3) |
| Connectome | Full synaptic weight matrix W | EEG electrode signals | Deep-source activity orthogonal to electrode sensitivity |

---

## 3. Controllability ↔ "What Can the Window Reach?"

### 3.1 Definition

A system (A, B) is **controllable** if any target state x_f can be reached from any initial state x_0 in finite time via some input sequence {u_k}.

**Rank condition**: Controllable iff rank(R) = n, where:

```
R = [B, AB, A²B, ..., A^{n-1}B]    (controllability matrix)
```

### 3.2 The duality theorem

**Observability and controllability are dual**: (A, C) is observable iff (A^T, C^T) is controllable.

**L0 interpretation**: The structure you can **see** (observability) and the structure you can **change** (controllability) are related by transposition. This is not a coincidence — it reflects the algebraic symmetry between row-rank and column-rank. In L0 terms: the algebra of visible observables and the algebra of actionable interventions are dual lattices.

### 3.3 L0 has no controllability axiom (yet)

L0 axioms A0-A6 describe observation but NOT intervention. The observer in L0 is passive — they choose the window W but cannot perturb S. Control theory says this is half the story.

**Implication for E-axis**: FX trading is a control problem. The trader (observer) both:
- Estimates the market state (observability → Kalman filter → estimation)
- Acts on the market (controllability → position sizing → control)

The separation principle (§5) says these two tasks decouple, which is why ΣΦ's observation-only theory can succeed as the estimation half of a control system, without needing to model the control half.

### 3.4 Controllability Gramian and energy

The controllability Gramian W_c = Σ_{k=0}^{T-1} A^k B B^T (A^k)^T quantifies the **energy cost** to reach each state direction:

- Large eigenvalue of W_c → cheaply reachable direction
- Small eigenvalue → expensive direction
- Zero eigenvalue → unreachable direction

**Balanced realization**: When W_o and W_c are simultaneously diagonalized (balanced truncation), the Hankel singular values σ_i = √(λ_i(W_o W_c)) measure the **joint importance** of each state direction — how observable AND controllable it is. Model reduction discards directions with small σ_i.

**L0 parallel**: Balanced truncation is a principled coarse-graining. The retained directions are the "effective degrees of freedom" — analogous to the effective participation ratio phi_eff/phi from finite_observation.md §6.

---

## 4. Estimation Theory ↔ Optimal Reconstruction from Finite Window

### 4.1 The Kalman filter

Given:
- Dynamics: x_{k+1} = A x_k + B u_k + w_k (process noise)
- Observation: y_k = C x_k + v_k (measurement noise)
- w_k ~ N(0, Q), v_k ~ N(0, R)

The Kalman filter computes the **minimum-variance estimate** x̂_k of x_k given {y_0, ..., y_k}.

### 4.2 Translation to L0

| Kalman concept | L0 concept | Reference |
|---|---|---|
| Process noise Q | error_arithmetic (inherent to S) | A1 (structured error) |
| Measurement noise R | error_noise (finite-N sampling) | A1 §5.1 |
| Innovation y_k - C x̂_k | error_projection (window-dependent) | A1 §5.1 |
| Kalman gain K_k | Optimal weighting of new observation | A2 (convergence rate) |
| Steady-state P_∞ (Riccati solution) | Floor deviation D_floor | A0 §5.3 |

**Key insight**: The Kalman filter's steady-state covariance P_∞ is the solution to the algebraic Riccati equation:

```
P = A P A^T - A P C^T (C P C^T + R)^{-1} C P A^T + Q
```

P_∞ > 0 whenever Q > 0 — there is always residual uncertainty. This is the control-theoretic version of L0's D_floor > 0: **no finite observer achieves zero error**.

### 4.3 Innovation sequence and structured error

The Kalman innovation ε_k = y_k - C x̂_k is white noise if the model is correct. Structured patterns in ε_k indicate model misspecification — this is exactly L0's A1 (the gap between observation and theory is not noise but structure).

**L4 connection**: ΣΦ's error catalogs (FX_errors.md, crystal_errors.md) are innovation analyses. If an "error" shows temporal structure, it is not noise but an unmodeled state dimension.

### 4.4 Information filter form

The dual Kalman filter works in information space (inverse covariance). The information matrix I_k = P_k^{-1} is additive:

```
I_{k+1} = A^{-T} I_k A^{-1} + C^T R^{-1} C
```

Each observation adds C^T R^{-1} C to the information. This is the control-theoretic version of the resolution-channel tradeoff: each measurement channel adds rank(C^T R^{-1} C) to the information matrix, but at cost R (noise per channel).

---

## 5. Separation Principle and A3 (Gauge Invariance)

### 5.1 Statement

For linear-Gaussian systems, the optimal control law decomposes:

```
optimal control = optimal estimation (Kalman filter) + optimal feedback (LQR)
```

The estimation problem and the control problem can be solved **independently**. The estimator does not need to know the control objective; the controller can treat the estimate as if it were the true state.

### 5.2 Two independent structures in ΣΦ

The separation principle and A3 (gauge invariance) are **distinct** claims that happen to coexist in ΣΦ:

| Principle | Statement | Scope |
|---|---|---|
| Separation (control theory) | Estimation and control can be solved independently | LTI + Gaussian systems |
| A3 (ΣΦ) | Amplitudes are gauge-invariant; phases are gauge-dependent | All observation triples (S, W, m) |

These are not equivalent. A3 says amplitude and phase are different *categories*. Separation says estimation and control are independent *subproblems*. The structural parallel is:

- Both assert a decomposition into two decoupled parts
- Both break down when commutativity fails (A4 / nonlinearity)

Whether separation is *derivable* from A0-A6 is OQ-CT2 (see §10.3). If derivable, the parallel becomes a theorem. If not, it is a suggestive analogy only.

**ΣΦ implication (regardless of OQ-CT2)**: The dictionary project (L0-L4) is the estimation half. The E-axis applications (trading, engineering) are the control half. The separation principle (where it holds) says these can be developed independently — which is consistent with the dictionary-first philosophy. But this consistency is not yet a proof of structural necessity.

### 5.3 Where separation breaks down

The separation principle requires:
1. Linear dynamics
2. Gaussian noise
3. Full state estimation (no constraints)

When any of these fail (nonlinear systems, heavy-tailed noise, partial observability), estimation and control couple.

**Suggestive but unproven A4 connection**: The breakdown conditions (nonlinearity, heavy tails, partial observability) *resemble* A4's non-commutative limits — both involve situations where order of operations matters. But the correspondence is not established:

- Linear ↔ commutative is standard (operator algebra)
- Gaussian ↔ ? (no clear L0 axiom singles out Gaussian noise)
- Full state estimation ↔ ? (A0b says access is partial, but this is the observation side, not the estimation completeness)

Whether "separation breaks down iff A4 dominates" is an open question (OQ-CT5, see §10.3).

---

## 6. Kalman Decomposition ↔ ΣΦ Error Structure

### 6.1 The four subspaces

Every LTI system decomposes into four invariant subspaces:

```
State space ℝ^n = (O ∩ C) ⊕ (O ∩ C̄) ⊕ (Ō ∩ C) ⊕ (Ō ∩ C̄)
```

where O = observable, C = controllable, bar = complement.

| Subspace | Observable? | Controllable? | ΣΦ interpretation |
|---|---|---|---|
| O ∩ C | yes | yes | Actionable structure (E-axis target) |
| O ∩ C̄ | yes | no | Observable but immutable (L0 constraints, physical constants) |
| Ō ∩ C | no | yes | Controllable but invisible (hidden market microstructure) |
| Ō ∩ C̄ | no | no | Inaccessible (qualia wall, §B tree bottom) |

### 6.2 Error decomposition mapping

| L0 error component | Kalman subspace | Reducible? |
|---|---|---|
| error_arithmetic (~26%) | O ∩ C̄ (visible, immutable) | No — inherent to S |
| error_projection (~60-70%) | O ∩ C (visible, actionable) | Yes — by better gauge (window) choice |
| error_noise (~5-10%) | stochastic (within O) | Yes — by N^{-1/2} averaging |
| D_floor | P_∞ (Riccati residual) | No — irreducible at finite dim |

### 6.3 Transfer function and input-output view

The transfer function G(z) = C(zI - A)^{-1}B maps inputs to outputs, bypassing the state entirely. Only the O ∩ C subspace contributes to G(z). This is the "minimal realization" — the smallest state-space that reproduces input-output behavior.

**L0 parallel**: The minimal realization is what the observer can both see and affect. dim(minimal realization) ≤ n, with equality iff the system is both observable and controllable. The gap n - dim(minimal realization) measures the **hidden structure** — state dimensions that exist but are either invisible or immutable from the observer's perspective.

---

## 7. Stability and Lyapunov — Suggestive Phase Correspondence

### 7.1 Stability types

| Stability | Eigenvalue condition | Suggestive phase analogue |
|---|---|---|
| Asymptotically stable | all |λ_i(A)| < 1 | SOLID-like: constraints enforce return to equilibrium |
| Marginally stable | |λ_i(A)| ≤ 1, some = 1 | LIQUID-like: neutral directions coexist with stable ones |
| Unstable | some |λ_i(A)| > 1 | GAS-like: no effective constraint enforcement |

### 7.2 Lyapunov function as constraint strength

A Lyapunov function V(x) ≥ 0 with V̇(x) < 0 certifies stability. The decay rate -V̇/V is the constraint enforcement speed.

**Caveat**: This stability ↔ phase correspondence is **suggestive, not established**. The three-phase taxonomy (three_phase_taxonomy.md) classifies systems by *structural constraint count* (static, algebraic). Stability classifies by *dynamical eigenvalue location* (dynamic, analytic). These operate on different axes:

- Three-phase is about HOW MANY constraints → sigmoid position
- Stability is about HOW FAST constraints enforce → eigenvalue magnitude

The two may be related (more constraints → more stable, generically) but this is not proven in ΣΦ. A system with many algebraic constraints (SOLID) can still be dynamically unstable if the constraints are not enforced by the dynamics. Conversely, a system with few constraints (GAS) can be dynamically stable if the few constraints are strong.

**Status**: Analogy only. Not promoted to theorem or OQ — insufficient substance for either.

---

## 8. Robust Control ↔ Structured Uncertainty

### 8.1 H∞ control

H∞ control minimizes the worst-case gain from disturbance to output:

```
min_K max_w ||G_{cl}(K)||_∞
```

This is minimax: the controller (observer) optimizes against the worst-case perturbation.

### 8.2 L0 interpretation

The H∞ norm ||G||_∞ = max_ω σ_max(G(jω)) measures the worst-case amplification at any frequency. This is the control-theoretic version of:

- **A0 (finite window)**: the observer cannot eliminate all disturbances
- **A1 (structured error)**: the worst-case frequency ω* reveals WHICH part of the disturbance is hardest to reject — this is the controlling structure
- **A2 (convergence as observable)**: σ_max(G(jω)) as a function of the number of actuators/sensors is a convergence rate observable

### 8.3 μ-analysis and structured uncertainty

μ-analysis handles **structured** uncertainty (some parameters uncertain, others known). The structured singular value μ measures robustness against a specific uncertainty structure.

**L0 parallel**: ΣΦ's error decomposition (arithmetic/projection/noise) IS a structured uncertainty description. error_arithmetic is the "structured" part (known to be irreducible); error_noise is the "unstructured" part (reducible by averaging). μ-analysis is the tool for handling exactly this kind of mixed uncertainty.

---

## 9. Cross-Domain Translation Table

### 9.1 Concepts

| Control concept | Number theory | Crystal | FX | Connectome |
|---|---|---|---|---|
| State x | {a_n mod L} distribution | ρ(r) electron density | Σ(t) correlation matrix | W synaptic weight matrix |
| Output y = Cx | Residue counts in window | F(hkl), \|h\| ≤ h_max | Eigenvalues of Σ(K-window) | EEG electrode voltages |
| Observable subspace | Fourier modes k ≤ k_N | Reciprocal space \|k\| ≤ h_max | Top-K eigenspace | Electrode-resolvable sources |
| Unobservable subspace | Modes k > k_N (aliased) | \|k\| > h_max (truncated) | Eigenvector phases | Deep sources orthogonal to electrodes |
| Process noise Q | Prime irregularity | Thermal motion (Debye-Waller) | Market microstructure noise | Synaptic noise, neurotransmitter fluctuation |
| Measurement noise R | Counting error (finite N) | Counting statistics | Finite-sample Wishart noise | Electrode thermal noise |
| Kalman gain | Optimal weighting of next prime | Optimal h_max extension | Optimal rolling window update | Optimal source localization |
| Floor deviation D_floor | D_floor(φ(L)) | DW factor (irreducible) | 2% residual in A (c_W) | Spatial resolution limit |

### 9.2 Duality instances

| Domain | Observation dual | Control dual | Separation valid? |
|---|---|---|---|
| Number theory | Count primes (passive) | (no control dual: primes are immutable) | N/A — pure observation |
| Crystal | Measure diffraction (passive) | Crystal growth / doping (active) | Approximately (growth ≈ linear) |
| FX | Estimate Σ(t) (Kalman) | Position sizing (LQR/Kelly) | Yes for Gaussian returns; no for fat tails |
| Connectome | Observe EEG (passive) | Stimulation (TMS, DBS, optogenetics) | Open — nonlinear neural dynamics |

---

## 10. What Control Theory Adds to ΣΦ

### 10.1 Completed translations

| ΣΦ concept | Control formalization | Status |
|---|---|---|
| Finite window (A0) | State-space model (A, B, C) | §1: done |
| Partial access (A0b) | Observability rank condition | §2: done |
| Structured error (A1) | Kalman innovation analysis | §4.3: done |
| Convergence rate (A2) | Gramian eigenvalue spectrum | §2.3: done |
| Gauge invariance (A3) | Separation principle | §5: done |
| Error decomposition | Kalman four-subspace decomposition | §6: done |
| Three-phase taxonomy | Stability classification | §7: done |

### 10.2 New structures not yet in L0

| New concept | What it adds | Potential L0 extension |
|---|---|---|
| Controllability | What the observer can **change** | A0b' (partial reach) dual to A0b |
| Input design | **Optimal perturbation** to maximize information | Active experiment design |
| Feedback | Using y to update u | Adaptive window selection |
| Robust control (H∞) | Worst-case guarantee | Minimax observation theory |
| Model reduction | Principled coarse-graining | phi_eff as Hankel truncation |

### 10.3 Open questions

**OQ-CT1**: Does ΣΦ need a controllability axiom? L0 is purely observational. If E-axis applications (FX trading, neural stimulation) require control, should L0 be extended to include an "actionability" axiom?

**OQ-CT2**: Is the separation principle a theorem or an axiom in ΣΦ? If it is derivable from A0-A6, then the dictionary-first philosophy (estimation before control) is structurally justified. If it requires additional axioms, the separation is contingent.

**OQ-CT3**: Balanced truncation gives dim(minimal realization) as the "effective state dimension." Is this related to the effective participation ratio phi_eff/phi? Both measure "how much of the theoretical capacity is actually used."

**OQ-CT4**: μ-analysis handles mixed structured/unstructured uncertainty. Can the L0 error decomposition (arithmetic + projection + noise) be reformulated as a μ-analysis problem? If so, robust control tools become directly applicable to ΣΦ error reduction.

**OQ-CT5**: Is the breakdown of the separation principle equivalent to A4 (non-commutative limits) dominance? The separation principle fails when linearity, Gaussianity, or full estimation breaks. A4 says limit order matters. If these are the same condition expressed in different languages, then OQ-CT2 (derivability of separation from L0) and OQ-CT5 (its breakdown condition) become two faces of the same problem: separation holds iff the system is in the "commutative regime" of A4. Attack route: formalize "commutative regime" as the joint condition A0a + linearity + Gaussian, and check whether A0-A6 imply or merely permit this regime.

### 10.4 Downstream references (files that use this dictionary)

| File | Section used | How it is used |
|---|---|---|
| `q_open_quantum_systems.md` §2.4 | §1 (state-space ↔ L0) | Partial trace as quantum version of y = Cx |
| `q_open_quantum_systems.md` §7.1 | §6 (Kalman 4-subspace) | Bath 2-row decomposition: weak-coupling vs Markovian |
| `q_open_quantum_systems.md` §7.2 | §6 (Kalman 4-subspace) | Markov approximation as C → C̄ transition |
| `q_open_quantum_systems.md` §7.3 | §5 (separation principle) | Quantum control as separation principle instance |
