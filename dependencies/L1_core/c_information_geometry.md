---
axis: A
position: information_geometry
static_dynamic: both
connected_to:
  - A.information_theory
  - A.harmonic_analysis
  - A.probability_statistics
  - B.quantum_observation
  - B.quantum_thermodynamics
  - C.metrology
  - C.causal_inference
arrow_status:
  upstream: done
  downstream: stub
updated: 2026-04-28
---

# Information Geometry

**Level**: L1 (domain-independent mathematical structure)
**Dependencies**: `c_information_theory.md` (§3 KL, §6 Fisher / Cramér-Rao / Fisher-Rao); `c_arrow_obstruction.md` (§10 T-AAS, §11 Arrow 1⁻¹ generation reverse); `q_quantum_observation.md` (§4 Born rule); `finite_observation.md` (A0, A5 precision limit)
**Downstream**: metrology.md, q_quantum_thermodynamics.md (§8.2 Ruppeiner-as-Fisher)

---

## §0 Thesis

Where `c_information_theory.md §6` defines Fisher information as a scalar / matrix quantity and §6.5 sketches the Fisher-Rao Riemannian metric, this dictionary entry **formalises the geometric content** in two directions:

1. **Classical → quantum extension** (§3-4): Quantum Fisher Information (QFI), Bures metric, Berry phase / Fubini-Study geometry — the quantum extensions of Fisher / Fisher-Rao.
2. **Geometric ↔ T-AAS framework integration** (§2): the central theorem **Fisher-Rao = Arrow 1⁻¹ local linearization** ties information-geometric structure to `c_arrow_obstruction.md §11` reverse-Arrow theory and identifies Cramér-Rao as the L0 precision floor for inverse-generation.

The L1 thesis: **information geometry is the local geometry of Arrow 1⁻¹** — the inverse Arrow that would generate Structural input from Information / Scan observations. Its global obstructions are T-AAS (`c_arrow_obstruction.md §11`); its local linearization is the Fisher-Rao metric.

This entry is the L1 dictionary residence for proposed paper-level work on information geometry. Paper-level closure (would-be I3 or I4 information geometry) is **deferred** until 5+ instances + Q-I cross-arrow content (Berry / QFI bridge) accumulate.

---

## §1 Recap of classical information geometry

(Detailed coverage in `c_information_theory.md §6`; this section gives the references for §2 onward.)

| Quantity | Symbol | Reference |
|---|---|---|
| Fisher information (scalar) | $I_F(\theta) = E_\theta[(\partial_\theta \log p)^2]$ | `c_information_theory.md §6.1` |
| Fisher information matrix | $[I_F(\theta)]_{ij} = E_\theta[(\partial_i \log p)(\partial_j \log p)]$ | §6.1 |
| Cramér-Rao bound | $\mathrm{Cov}(\hat\theta) \succeq I_F(\theta)^{-1}$ | §6.2 |
| Score function | $s(x|\theta) = \partial_\theta \log p(x|\theta)$ | §6.3 |
| Fisher-Rao metric | $ds^2 = \sum_{ij} [I_F(\theta)]_{ij}\, d\theta_i d\theta_j$ | §6.5 |
| KL local expansion | $D_{KL}(p_\theta \| p_{\theta+d\theta}) \approx \tfrac{1}{2}\, d\theta^T I_F\, d\theta$ | §6.5 |
| Ruppeiner = Fisher-Rao on Gibbs | $g_{ij} = \beta^2 \mathrm{Cov}(X_i, X_j)$ | `q_quantum_thermodynamics.md §8.2` |

---

## §2 Theorem 2.1 (central): Fisher-Rao = Arrow 1⁻¹ local linearization

### §2.1 Statement

Let $\{p(x|\theta)\}_{\theta \in \Theta}$ be a smooth parametric family with $\Theta \subset \mathbb{R}^d$ open, satisfying standard regularity (smooth log-likelihood, Fisher matrix positive-definite on the parameter range of interest).

**Theorem 2.1 (Fisher-Rao = Arrow 1⁻¹ local linearization, ESTABLISHED 2026-04-28)**: the Fisher-Rao metric $g_F(\theta) = I_F(\theta)$ is the **local linearization** of the inverse Arrow $\mathrm{Arrow}\,1^{-1}: \mathrm{Information / Scan} \to \mathrm{Structural}$ (`c_arrow_obstruction.md §11`) in the following 3-fold sense:

(A) **KL → Fisher quadratic form** (Information-side distance):
$$D_{KL}(p_\theta \,\|\, p_{\theta+\epsilon}) = \tfrac{1}{2}\,\epsilon^T g_F(\theta)\,\epsilon + O(\|\epsilon\|^3)$$
The Information-layer distance ($D_{KL}$) has, at lowest order in the parameter perturbation, the quadratic form determined by $g_F$.

(B) **Cramér-Rao = Arrow 1⁻¹ precision floor**:
$$\mathrm{Cov}_\theta(\hat\theta) \succeq \frac{1}{n}\, g_F(\theta)^{-1} \quad \text{(any unbiased $\hat\theta$ from $n$ i.i.d. samples)}$$
Cramér-Rao is the **finite-observation precision limit** for the Arrow 1⁻¹ reconstruction of $\theta$ from observations — irreducible by any algorithm or gauge choice (matches the L0 A1 *error_arithmetic* role within the Information-Geometry domain).

(C) **Local Riemannian inversion**: the Fisher-Rao Riemannian structure $(\Theta, g_F)$ defines a metric, geodesic distance, and Levi-Civita connection on parameter space; locally (away from $\det g_F = 0$ singularities), Arrow 1⁻¹ acts as a smooth diffeomorphism on $(\Theta, g_F)$, and the geodesic distance measures the **statistical distinguishability** of $\theta$ vs $\theta + \epsilon$ from the observer's perspective.

### §2.2 Proof sketch

(A) follows from second-order Taylor expansion of $D_{KL}(p_\theta \| p_{\theta+\epsilon}) = E_\theta[\log(p_\theta / p_{\theta+\epsilon})]$ in $\epsilon$. The first-order term vanishes by $\partial_\theta E_\theta[1] = 0$; the second-order term is $\tfrac{1}{2} \epsilon^T E_\theta[(\partial_i \log p)(\partial_j \log p)] \epsilon = \tfrac{1}{2} \epsilon^T g_F \epsilon$ after one integration by parts. Standard reference: Kullback (1959), §2.

(B) is the matrix Cramér-Rao bound, proved by Cauchy-Schwarz on the score-statistic inner product. Reference: Lehmann-Casella, *Theory of Point Estimation*, §2.6.

(C) follows from positive-definiteness of $g_F$ on the regularity domain. Singularities $\det g_F = 0$ correspond to **local rank loss of Arrow 1⁻¹** — i.e., parameter directions in which the observation cannot distinguish $\theta$ from $\theta + \epsilon$ to first order. These match the T-AAS local kernel:

$$\ker(g_F(\theta)) \ \cong\ \text{local infinitesimal } \ker_{\mathrm{gauge}}(\mathrm{Arrow}\,1)|_\theta$$

### §2.3 L0 / T-AAS interpretation

| Information-Geometry quantity | L0 / T-AAS role |
|---|---|
| Fisher metric $g_F(\theta)$ (positive-definite locus) | local linearization of $\mathrm{Arrow}\,1^{-1}$ |
| $\det g_F(\theta) = 0$ locus | local infinitesimal $\ker_{\mathrm{gauge}}$ direction (`c_arrow_obstruction.md §11.5`) |
| Cramér-Rao bound $g_F^{-1}/n$ | $n$-sample precision floor (L0 A1 *error_arithmetic* in IG domain) |
| KL local expansion $\tfrac{1}{2}\epsilon^T g_F \epsilon$ | Information-side metric, second-order |
| Fisher-Rao geodesic | "shortest reconstruction path" for Arrow 1⁻¹ |
| Sufficient-statistic invariance (Cencov) | gauge-invariance under L0-A3-style observer-window choice |

The Fisher metric **does not detect** the **global** topological obstructions of Arrow 1⁻¹ (= $\ker_{\mathrm{topo}}$, $f_{\mathrm{rational}}$ in T-AAS language). Those live globally on the parameter manifold and require finer tools (TDA, Hodge — `c_information_theory.md §9` + `c_filtration_obstruction.md`). Local linearization is the sharp scope of Theorem 2.1.

### §2.4 Status

ESTABLISHED 2026-04-28. Numerical verification (Gaussian families): see `research/c_information_geometry_v0_verify.py` for $D_{KL}$ vs Fisher quadratic-form agreement on $N(\mu, \sigma^2)$ at varying $\mu, \sigma$.

---

## §3 Quantum Fisher Information and Bures metric

### §3.1 Symmetric logarithmic derivative (SLD) and QFI

For a smooth family of density operators $\rho(\theta)$, the **symmetric logarithmic derivative** $L_\theta$ is the self-adjoint operator solving:
$$\partial_\theta \rho = \tfrac{1}{2}(L_\theta \rho + \rho L_\theta)$$

The **Quantum Fisher Information (QFI)** is:
$$\mathcal{F}_Q(\theta) = \mathrm{Tr}(\rho L_\theta^2) = \mathrm{Tr}(L_\theta\, \partial_\theta \rho)$$

For pure states $\rho = |\psi(\theta)\rangle\langle\psi(\theta)|$:
$$\mathcal{F}_Q(\theta) = 4\,(\langle\partial_\theta\psi|\partial_\theta\psi\rangle - |\langle\psi|\partial_\theta\psi\rangle|^2)$$

### §3.2 Quantum Cramér-Rao

For any quantum estimator $\hat\theta$ of θ from $n$ copies of $\rho(\theta)$:
$$\mathrm{Var}(\hat\theta) \geq \frac{1}{n\,\mathcal{F}_Q(\theta)}$$

This is the quantum version of Theorem 2.1(B); QFI is the local-linearization of $\mathrm{Arrow}\,1^{-1}$ in the **quantum-observation domain**.

### §3.3 Bures metric

The **Bures metric** on the manifold of density operators:
$$ds_{\mathrm{Bures}}^2 = \tfrac{1}{4}\, \mathrm{Tr}\!\left[ (\partial_i \rho)\, L_j \right]\, d\theta_i d\theta_j = \tfrac{1}{4}\,\mathcal{F}_Q^{ij}\, d\theta_i d\theta_j$$

Bures = quantum Fisher-Rao (up to factor ¼). For pure states it reduces to the **Fubini-Study metric** on projective Hilbert space $\mathbb{P}(\mathcal{H})$.

### §3.4 Classical limit

For commuting density operators $[\rho(\theta), \partial_\theta \rho] = 0$ (e.g., diagonal $\rho$ in a fixed basis), $L_\theta = \partial_\theta \log \rho$ and $\mathcal{F}_Q$ reduces to classical Fisher information. The QFI ≥ classical Fisher inequality (`Braunstein-Caves 1994`) quantifies the quantum-classical gap.

---

## §4 Berry phase and Fubini-Study geometry

### §4.1 Berry phase definition

For a parameter-dependent family of pure states $|\psi(\theta)\rangle$ with adiabatic transport along a closed loop $C$ in $\Theta$:
$$\gamma_{\mathrm{Berry}}(C) = i \oint_C \langle\psi(\theta)|\partial_\theta \psi(\theta)\rangle\, d\theta$$

This is a **gauge-dependent** local connection 1-form $A_\theta = i\langle\psi|\partial_\theta\psi\rangle$ but a **gauge-invariant** integral around a loop (Berry's theorem, 1984).

### §4.2 Connection to Fubini-Study and QFI

The Berry curvature 2-form $F = dA$ and the Fubini-Study metric $g_{\mathrm{FS}}$ on $\mathbb{P}(\mathcal{H})$ together form the **complex (hermitian) structure** $g_{\mathrm{FS}} - i F/2$ on parameter space (Provost-Vallee 1980). Equivalently:
$$\mathcal{F}_Q^{ij}(\theta)/4 = \text{Re}\big(\langle\partial_i\psi|\partial_j\psi\rangle - \langle\partial_i\psi|\psi\rangle\langle\psi|\partial_j\psi\rangle\big) = g_{\mathrm{FS}}^{ij}(\theta)$$

So **QFI / 4 = Fubini-Study metric = real part of the quantum geometric tensor**, while the imaginary part is the Berry curvature.

### §4.3 σ\* / Q3 connection (informal)

The framework's σ\* gauge (`q_quantum_observation.md §6`, Q3 §4) sits in the same algebraic family — phase coherence + half-amplitude Born — as the Berry-phase gauge. A formal claim "σ\* gauge = Berry-curvature half-amplitude threshold" is **candidate**, recorded as OQ-IG-Berry-Sigma in §9.

---

## §5 Wasserstein distance and optimal transport

### §5.1 Wasserstein-2 distance

For probability measures $\mu, \nu$ on $\mathbb{R}^d$ with finite second moments:
$$W_2(\mu, \nu) = \left(\inf_{\pi \in \Pi(\mu,\nu)} \int \|x - y\|^2\, d\pi(x,y)\right)^{1/2}$$
where $\Pi(\mu, \nu)$ is the set of couplings with marginals $\mu, \nu$.

### §5.2 Otto calculus and Wasserstein-Fisher relation

Otto (2001) identifies $W_2$-geodesics with displacement interpolation. The Wasserstein distance is **NOT** a Riemannian distance in general, but on the formal infinite-dim manifold of probability densities it admits a "Wasserstein metric tensor" $g_W$ that is **distinct from $g_F$**:
- Fisher-Rao $g_F$: log-derivative inner product (Information-layer structure)
- Wasserstein $g_W$: gradient-flow / mass-transport (spatial / geometric structure)

### §5.3 Cross-Arrow correspondence (candidate_v0)

A natural conjecture for the framework: the 3 canonical distances on probability measures correspond to the 3 Arrows:

| distance | structural content | candidate Arrow correspondence |
|---|---|---|
| $W_2$ Wasserstein | spatial / mass-transport (real-line geometry) | **Arrow 1** (Scan → Structural reads spatial skeleton) |
| $D_{KL}$ Kullback-Leibler | log-likelihood ratio (relative entropy) | **Arrow 2** (Scan → Information, log-exp duality) |
| $g_F$ Fisher-Rao (local) | parameter-distinguishability | **Arrow 1⁻¹** (Information → Structural local inversion, Theorem 2.1) |

**Status**: candidate_v0. (i)(ii) are reasonable upon inspection; (iii) is Theorem 2.1. Forming a full correspondence theorem is OQ-IG-3Distances-3Arrows (§9).

---

## §6 Numerical verification

`research/c_information_geometry_v0_verify.py` (companion script):

**Test 1 — Gaussian KL ↔ Fisher quadratic form**: for $p_\mu = N(\mu, 1)$ vary $\mu$ and verify $D_{KL}(p_\mu \| p_{\mu+\epsilon}) = \tfrac{1}{2}\epsilon^2 + O(\epsilon^3)$ matches the analytic Fisher value $I_F(\mu) = 1$.

**Test 2 — Multi-parameter Gaussian**: for $p_{\mu,\sigma} = N(\mu, \sigma^2)$ verify $g_F = \mathrm{diag}(1/\sigma^2, 2/\sigma^2)$ matches numerical KL Hessian.

**Test 3 — Local rank loss**: at a degenerate parametrization $p_{\theta} = N(\theta + \theta, 1)$ (over-parameterized), verify $\det g_F = 0$ along the redundant direction — local instance of Arrow 1⁻¹ kernel.

---

## §7 L0 translation table

| Information-Geometry quantity | L0 axiom / framework role |
|---|---|
| Parameter manifold $\Theta$ | structural moduli of allowed worlds |
| Fisher metric $g_F(\theta)$ | A1 instance: precision-bearing structure on parameter space |
| Cramér-Rao bound | A0 + A5 instance: finite-observation precision limit |
| QFI $\mathcal{F}_Q$ | A1 quantum-domain instance |
| Bures / Fubini-Study | A3 (gauge invariance) instance: invariant under sufficient-statistics + unitary gauge |
| Berry phase | A4 (boundary) instance: holonomy of parameter loops |
| Wasserstein $W_2$ | A1 spatial-domain instance |
| Theorem 2.1 | bridge between A1 (Information local distance) and §11 (Arrow 1⁻¹ kernel theory) |

---

## §8 Open Questions

**OQ-IG-1 (MEDIUM)**: prove or refute the 3 distances ↔ 3 Arrows correspondence (§5.3). Wasserstein ↔ Arrow 1 link is candidate; KL ↔ Arrow 2 is established at the algebraic level (`c_arrow_framework.md §4`); Fisher ↔ Arrow 1⁻¹ is Theorem 2.1.

**OQ-IG-Berry-Sigma (LOW, framework-Q link)**: formalise "σ\* gauge ⟺ Berry-curvature half-amplitude threshold" (§4.3). Connects framework σ\* (q_quantum_observation §6) to geometric phase content.

**OQ-IG-QFI-Algorithmic (MEDIUM)**: bridge between QFI and the algorithmic f_rational of `c_information_theory.md §8.5` (Theorem 8.5.1). Quantum tomography classical record gives a $K(\rho)$ — relate it to $\mathcal{F}_Q$ density. Cross-link with Paper I1 §5.2.1 OQ-Alg-Quantum-Cross.

**OQ-IG-RankLoss-T-AAS (MEDIUM)**: characterise the local kernel $\ker(g_F(\theta))$ in T-AAS terms (`c_arrow_obstruction.md §11.5`'s 5-class taxonomy). Theorem 2.1's §2.3 gives the qualitative match; rigorous identification is open.

**OQ-IG-Paper-Readiness (META, framework hygiene)**: paper-level lift (would-be I3 / I4 information geometry) is **deferred** until 5+ instances + Q-I cross-arrow Berry/QFI content accumulate per `feedback_dictionary_first.md` (dictionary first, paper second). Trigger condition for paper draft: 3+ ESTABLISHED theorems on this entry + 1 cross-arrow QFI bridge with Q3.

---

## §9 References

**Internal**:
- `c_information_theory.md §3, §6` (Fisher, KL, Fisher-Rao recap)
- `c_arrow_obstruction.md §10-§11` (T-AAS, Arrow 1⁻¹ generation reverse)
- `c_filtration_obstruction.md §8.5` (Theorem 4a.1 unified f_rational scale)
- `q_quantum_observation.md §4, §6` (Born rule, σ\* gauge — Q-side)
- `q_quantum_thermodynamics.md §8.2` (Ruppeiner = Fisher-Rao on Gibbs)
- `finite_observation.md §5.1` (L0 A1 error decomposition)

**External (standard textbook)**:
- Amari, *Information Geometry and Its Applications* (Springer 2016) — classical info-geom standard
- Helstrom, *Quantum Detection and Estimation Theory* (1976) — QFI / quantum Cramér-Rao
- Bengtsson-Życzkowski, *Geometry of Quantum States* (CUP 2017) — Bures / Fubini-Study / Berry
- Otto, *The geometry of dissipative evolution equations* (2001) — Wasserstein / Otto calculus
- Provost-Vallee, *Riemannian structure on manifolds of quantum states* (Comm. Math. Phys. 1980) — quantum geometric tensor
- Braunstein-Caves, *Statistical distance and the geometry of quantum states* (PRL 1994) — QFI ≥ classical Fisher
- Kullback, *Information Theory and Statistics* (1959), §2 — KL local expansion
- Lehmann-Casella, *Theory of Point Estimation* (Springer 1998), §2.6 — Cramér-Rao matrix form

---

## §10 Position note (paper-deferred)

This entry exists as **L1 dictionary residence** for information-geometry content that would otherwise live as paper material. Per `feedback_dictionary_first.md` ("dictionary = body, paper = projection"), paper-level closure is deferred. The would-be I3 / I4 information-geometry paper trigger condition is recorded in OQ-IG-Paper-Readiness (§8).

Slot conflict note: I-series I3 v0.0 is currently the **biological direction paper** (`papers/publication/information/I3_bio_communication_direction_*.md`). If/when an information-geometry paper is written, it would naturally take I4 (or rename schemes), but this is a future-cycle decision.

---

## Change log

- **v0.1 (2026-04-28)**: NEW L1 entry. §0 thesis + §1 classical recap (delegated to c_information_theory §6) + **§2 central Theorem 2.1 (Fisher-Rao = Arrow 1⁻¹ local linearization)** with 3-fold statement (KL → Fisher quadratic / Cramér-Rao precision floor / local Riemannian inversion) + §3 QFI / Bures + §4 Berry / Fubini-Study + §5 Wasserstein + §6 numerical verification placeholder + §7 L0 translation + §8 4 OQ + §9 references + §10 paper-deferral note. Paper-level lift deferred per `feedback_dictionary_first.md`. Slot conflict (I3 = bio) noted in §10.
