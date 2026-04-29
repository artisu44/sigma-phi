---
axis: A
position: information_theory
static_dynamic: both
connected_to:
  - A.harmonic_analysis
  - A.algebra_analysis
  - A.probability_statistics
  - B.quantum_thermodynamics
  - B.quantum_statistical
  - C.control_theory
  - C.network_science
  - C.causal_inference
  - D.metrology
arrow_status:
  upstream: done
  downstream: stub
updated: 2026-04-08
---

# Information Theory

**Level**: L1 (domain-independent mathematical structure)
**Dependencies**: finite_observation.md (A0-A5), q_quantum_thermodynamics.md (§5 Landauer), q_quantum_observation.md (§6 Born rule)
**Downstream**: metrology.md (D), inference_control.md (C), fault_taxonomy.md (L4∩C), network_science.md (C), multi_agent.md (C∩E), causal_inference.md (C)

---

## §0 Thesis

Information theory is the mathematics of what a finite observer can know, transmit, and compress. Where L0 axiomatises "all observation is finite," information theory quantifies the consequences: how much can be learned (capacity), how much must be lost (rate-distortion), and what is the irreducible cost of forgetting (Landauer, q_quantum_thermodynamics.md §5).

The central claim of this file is that information theory is not a single theory but a **bundle of five strands**, each answering a different L0 question:

| Strand | Core object | L0 question |
|---|---|---|
| Shannon (§1-§3) | H, I, D_KL | How much can the window transmit? |
| Rate-Distortion (§4) | R(D) | How much must the window discard? |
| Information Bottleneck (§5) | I(X;T) vs I(T;Y) | What should the window keep for a task? |
| Fisher / Geometry (§6) | I_F(θ), g_ij | How sensitive is the window to parameters? |
| Algorithmic (§8) | K(x) | How complex is the object itself, independent of the window? |

These five strands share L0's finite-observation axiom A0a as root, but diverge in what they measure. Shannon measures the observer's channel. Fisher measures the observer's sensitivity. Kolmogorov measures the object's intrinsic complexity. The σφ contribution is to see them as five projections of the single fact: **the observer is finite, the object is not**.

Bayesian inference (§7) is the operational glue: given the information-theoretic constraints, how should the observer update beliefs? TDA (§9) asks what topological features survive the coarse-graining — the shape that persists through the window.

Note on ordering: §1-§3 build Shannon's framework (entropy → mutual information → divergence). §4-§5 address lossy compression and task-relevant compression. §6 shifts to parametric sensitivity. §7 gives the decision-theoretic wrapper. §8-§9 are the two "beyond Shannon" extensions (algorithmic complexity, topological persistence). §10 is the L0 translation table, §11 bridges to downstream files, §12 collects open questions.

---

## §1 Shannon Entropy

### 1.1 Definition

For a discrete random variable X with distribution p(x) over alphabet X:

    H(X) = -Σ_x p(x) log p(x)

Convention: log = log₂ gives bits; log = ln gives nats. The σφ dictionary uses nats (consistent with Landauer's kT ln 2 and Fisher information), converting to bits where noted.

### 1.2 Operational meaning: source coding theorem

Shannon's source coding theorem (1948): N i.i.d. draws from X can be losslessly compressed to NH(X) + o(N) bits, and no shorter encoding exists.

This is an L0 statement: **the window's capacity sets the compression floor**. An observer with a channel of capacity C bits per use can transmit at most C bits per observation. If H(X) > C, lossless transmission is impossible — the observer must either accept distortion (§4) or increase the window.

### 1.3 Properties

- **Non-negativity**: H(X) ≥ 0, with equality iff X is deterministic
- **Maximum**: H(X) ≤ log|X|, with equality iff X is uniform
- **Chain rule**: H(X,Y) = H(X) + H(Y|X) — total uncertainty decomposes into marginal + conditional
- **Subadditivity**: H(X,Y) ≤ H(X) + H(Y), with equality iff X ⊥ Y

The chain rule is the information-theoretic manifestation of A1 (arithmetic structure / independence): for independent sources, H(X,Y) = H(X) + H(Y). This is exactly Shannon's 1948 uniqueness axiom — the only continuous, monotonic function satisfying H(AB) = H(A) + H(B) for independent events is H = -Σ p log p (up to constant).

### 1.4 Conditional entropy and equivocation

    H(Y|X) = Σ_x p(x) H(Y|X=x) = -Σ_{x,y} p(x,y) log p(y|x)

H(Y|X) is the residual uncertainty about Y after observing X. In L0 terms: this is the information that the window W_X cannot capture about Y. If Y is the full structure S and X is the observation m(S|_W), then H(S|X) = H(S) - I(X;S) is the unresolved structure — the finite observation error expressed in nats.

### 1.5 Rényi entropy (parametric family)

    H_α(X) = (1/(1-α)) log Σ_x p(x)^α,    α > 0, α ≠ 1

The limit α → 1 recovers Shannon entropy. Special cases:
- α = 0: H_0 = log|support(X)| (Hartley entropy — counts nonzero probabilities)
- α = 2: H_2 = -log Σ p(x)² (collision entropy — related to participation ratio φ_eff/φ in connectome_dictionary_v0.md)
- α → ∞: H_∞ = -log max_x p(x) (min-entropy — worst-case)

The Rényi family parameterises a continuum of "how much the observer cares about rare vs common events." Shannon (α=1) is the balanced point. Min-entropy (α=∞) is the security-critical limit (cryptography). Collision entropy (α=2) is the observable that connectome φ_eff/φ implicitly computes: the effective number of participating modes.

**Theorem 1.5.1 (Rényi scaffold-emergence parametric scan, ESTABLISHED 2026-04-28, Paper I1 §3.3 定理 3.3.1)**: $\{H_\alpha\}_{\alpha \in [0, \infty]}$ is a continuous parametric scan of the **scaffold-emergence axis** (`user_012_non_integer_scaffold.md`) with 4 anchor structure: α=0 Hartley (scaffold-base, 0/1/2 binary 2-domain) / α=1 Shannon (2-domain → 3+ relational transition) / α≥2 collision and beyond (3+ relational structure proper) / α=∞ min-entropy (worst-case relational, security limit). Corollary 1.5.2 (Paper I1 系 3.3.2): $H_\alpha$ is monotonically non-increasing in α (van Erven & Harremoës 2014), so scanning α from 0 to ∞ traces the full axis once via monotone descent. See `papers/publication/information/I1_information_theory_framework_ja.md §3.3` for the full proof sketch + S12 additive Scan family link.

---

## §2 Mutual Information and Channel Capacity

### 2.1 Mutual information

    I(X;Y) = H(X) - H(X|Y) = H(Y) - H(Y|X) = H(X) + H(Y) - H(X,Y)

I(X;Y) is the information that X and Y share. It is symmetric, non-negative, and zero iff X ⊥ Y.

Equivalent form via KL divergence (§3):

    I(X;Y) = D_KL(p(x,y) || p(x)p(y))

This measures how far the joint distribution is from the product of marginals — the departure from independence.

### 2.2 Channel capacity

A discrete memoryless channel p(y|x) has capacity:

    C = max_{p(x)} I(X;Y)

Shannon's channel coding theorem (1948): reliable communication at rate R is possible iff R < C. Above C, any code has nonzero error probability.

In L0 terms: C is the maximum rate at which the window W can transmit structure from S. The channel p(y|x) is the window's transfer function — it maps input (what the object emits) to output (what the observer receives). Noise in the channel is the observation error.

### 2.3 Data processing inequality

For any Markov chain X → Y → Z:

    I(X;Z) ≤ I(X;Y)

**No processing of the observation can create information about the source that wasn't in the observation.** This is the information-theoretic statement of L0's finite window principle: the window W sets an upper bound on recoverable information, and no downstream computation can exceed it.

This inequality was already used in q_quantum_thermodynamics.md §3.4 (second law as data processing inequality for CPTP maps). The connection is structural: the second law of thermodynamics IS the data processing inequality applied to quantum channels.

### 2.4 Gaussian channel

For additive Gaussian noise Y = X + N, N ~ N(0, σ²), with power constraint E[X²] ≤ P:

    C = (1/2) log(1 + P/σ²)    [bits per use]

This is the Shannon-Hartley theorem. The signal-to-noise ratio P/σ² determines capacity. In L0 terms: the observation window's resolution (σ) and the object's signal strength (P) jointly determine how much structure is recoverable per observation.

Note: the 1/2 prefactor is the same c_s² = 1/2 that appears throughout the σφ dictionary (correspondence_table.md §7). In the Gaussian channel, it arises from the half-degree-of-freedom per real dimension. Whether this is the same c_s² or a coincidence is an open question (OQ-IT1, §12).

---

## §3 KL Divergence and Relative Entropy

### 3.1 Definition

The Kullback-Leibler divergence from q to p:

    D_KL(p || q) = Σ_x p(x) log(p(x)/q(x))

Properties:
- **Non-negative**: D_KL(p || q) ≥ 0, with equality iff p = q (Gibbs' inequality)
- **Not symmetric**: D_KL(p || q) ≠ D_KL(q || p) in general
- **Not a metric**: violates triangle inequality

### 3.2 Operational interpretations

1. **Model selection cost**: D_KL(p || q) = expected excess code length when using code optimised for q to encode data from p. The observer who assumes the wrong model q pays D_KL(p || q) extra nats per observation.

2. **Statistical discrimination**: In hypothesis testing between p and q, D_KL(p || q) governs the exponential rate of type II error decay (Stein's lemma). More divergent distributions are easier to distinguish — the observer needs fewer samples.

3. **Free energy connection**: From q_quantum_thermodynamics.md §1.2, the variational free energy:

        F(ρ) = Tr(ρH) + kT · D_KL(ρ || ρ_β)

    The free energy of any state ρ exceeds the equilibrium free energy by exactly kT · D_KL(ρ || ρ_β). The KL divergence measures the thermodynamic cost of being out of equilibrium.

### 3.3 f-divergences and the divergence family

D_KL is a member of the f-divergence family D_f(p || q) = Σ q(x) f(p(x)/q(x)):

| f(t) | Divergence | Role in σφ |
|---|---|---|
| t log t | KL divergence | Model mismatch cost |
| (t-1)² | χ² divergence | Small-perturbation limit |
| -log t | Reverse KL | Mode-seeking inference |
| |t-1|/2 | Total variation | Worst-case distinguishability |

All f-divergences satisfy the data processing inequality (§2.3): D_f(p_X || q_X) ≥ D_f(p_Y || q_Y) for any channel X → Y. This is the general form of "the window cannot increase distinguishability."

---

## §4 Rate-Distortion Theory

### 4.1 The lossy compression problem

When lossless compression requires more than the channel can carry (H(X) > C), the observer must accept distortion. Rate-distortion theory asks: what is the minimum rate R (bits per source symbol) needed to reconstruct the source with average distortion at most D?

### 4.2 Rate-distortion function

Given a distortion measure d(x, x̂) and distortion threshold D:

    R(D) = min_{p(x̂|x): E[d(X,X̂)] ≤ D} I(X; X̂)

R(D) is a convex, non-increasing function. Key points:
- R(0) = H(X) (lossless requires full entropy)
- R(D_max) = 0 (above maximum distortion, no bits needed)

### 4.3 Gaussian rate-distortion

For X ~ N(0, σ²) with squared-error distortion d(x, x̂) = (x - x̂)²:

    R(D) = (1/2) log(σ²/D)    for 0 < D ≤ σ²

This is the dual of the Gaussian channel capacity (§2.4): channel capacity tells you how much you can send; rate-distortion tells you how much you must keep.

### 4.4 L0 translation: the distortion floor

In L0, the finite observation error m(S) - m(S|_W) is the distortion introduced by the window W. Rate-distortion theory formalises the tradeoff:

- **Rate R**: the number of bits the observer retains per observation
- **Distortion D**: the expected error between the true structure and the reconstruction

The rate-distortion function R(D) is the **fundamental limit of the finite observer**: it quantifies the minimum information needed to achieve a given reconstruction quality. This was already referenced in q_quantum_thermodynamics.md §5.3 (D_floor as the irreducible distortion) and §5.6 (thermal cost per observation = R(D) · kT ln 2).

The σφ-specific claim: every L2 observable (φ_eff/φ, K(τ), abs) is implicitly at some operating point (R*, D*) on its domain's rate-distortion curve. The L4 errors are deviations from R(D) — either the observer is above the curve (inefficient) or claims to be below it (impossible, hence error).

### 4.5 Machine-oriented rate-distortion

Classical rate-distortion assumes human-meaningful distortion (MSE, perceptual quality). Machine-oriented rate-distortion replaces d(x, x̂) with a task loss: how well does the compressed representation serve a downstream task?

This connects directly to the Information Bottleneck (§5): IB is rate-distortion where the distortion is measured by task-relevant information loss, not reconstruction error.

---

## §5 Information Bottleneck

### 5.1 Setup

Given a Markov chain X → T → Y, where:
- X is the input (raw observation)
- T is the compressed representation
- Y is the target (task-relevant variable)

The Information Bottleneck (Tishby, Pereira, Bialek 1999) optimises:

    min_{p(t|x)} [I(X;T) - β · I(T;Y)]

where β controls the tradeoff between compression (small I(X;T)) and relevance (large I(T;Y)).

### 5.2 The IB curve

As β varies from 0 to ∞, the optimal T traces a curve in the (I(X;T), I(T;Y)) plane:

- β → 0: T is maximally compressed (constant), I(T;Y) = 0
- β → ∞: T retains everything relevant, I(T;Y) = I(X;Y)
- Intermediate β: the representation keeps only what is needed for Y

The IB curve is the Pareto frontier of the compression-relevance tradeoff. Points below the curve are unachievable. Points above are inefficient (retaining irrelevant information).

### 5.3 L0 translation: task-directed observation

IB formalises a core L0 principle: **the window should retain only what serves the observer's purpose**.

| IB concept | L0 concept |
|---|---|
| X (input) | S (full structure) |
| T (representation) | m(S\|_W) (observation through window) |
| Y (target) | The specific pattern the observer seeks |
| I(X;T) (complexity) | Window capacity / observation cost |
| I(T;Y) (relevance) | Useful information extracted |
| β (tradeoff) | Observer's resource constraint |

This extends L0 beyond passive observation: L0's axioms describe what the window shows (A0) and how errors are structured (A1). IB adds the question: **given a purpose, what is the optimal window?**

### 5.4 IB and deep learning

Deep neural networks can be viewed as successive IB compressions: each layer T_l compresses the input further while (ideally) retaining task-relevant information. The IB perspective predicts:

1. **Training dynamics**: early training increases I(T;Y) (fitting); late training decreases I(X;T) (compression)
2. **Generalisation**: representations near the IB frontier generalise better than those far from it
3. **Layer depth**: deeper layers are further along the IB curve (more compressed, more task-specific)

These predictions are debated (the compression phase may depend on activation functions and training details), but the IB framework provides the right language for asking the question.

### 5.5 IB and state representation in RL

In reinforcement learning with complex observations (images, sensor data), the agent needs a representation of state that is sufficient for decision-making but not unnecessarily detailed. This is exactly IB:

- X = raw observation (pixels, sensor readings)
- T = learned state representation
- Y = optimal action or value function

The IB framework explains why raw pixels are inefficient for RL: they contain vast amounts of task-irrelevant information (textures, lighting, background). A good representation compresses X to T while retaining what matters for Y.

This connects to inference_control.md (downstream): POMDP belief states are the Bayesian solution to the same problem. IB provides the information-theoretic framework; POMDP provides the decision-theoretic framework.

---

## §6 Fisher Information and Information Geometry

### 6.1 Fisher information

For a parametric family p(x|θ), the Fisher information about θ is:

    I_F(θ) = E_θ[(∂/∂θ log p(x|θ))²] = -E_θ[∂²/∂θ² log p(x|θ)]

For a parameter vector θ ∈ ℝ^d, the Fisher information matrix:

    [I_F(θ)]_{ij} = E_θ[(∂/∂θ_i log p)(∂/∂θ_j log p)]

### 6.2 Cramér-Rao bound

For any unbiased estimator θ̂ of θ:

    Var(θ̂) ≥ 1/I_F(θ)    (scalar case)
    Cov(θ̂) ≥ I_F(θ)^{-1}  (matrix case, Löwner order)

**No unbiased estimator can have variance below the inverse Fisher information.** This is the estimation-theoretic dual of Shannon's source coding theorem: Shannon bounds the compression rate from below; Cramér-Rao bounds the estimation variance from below.

In L0 terms: Cramér-Rao is the precision limit of the finite window. The observer's best estimate of θ has irreducible variance 1/I_F(θ), regardless of the estimation method. More Fisher information = more precise observation.

### 6.3 Fisher information and the score function

The score function s(x|θ) = ∂/∂θ log p(x|θ) measures the sensitivity of the likelihood to parameter changes. Fisher information is the variance of the score:

    I_F(θ) = Var_θ[s(X|θ)]

High Fisher information means the likelihood landscape is steep — small changes in θ produce large changes in the distribution. This makes θ easy to estimate. Low Fisher information means the landscape is flat — the observer cannot distinguish nearby parameter values.

### 6.4 Gaussian Fisher information and σ*

For X ~ N(μ, σ²), the Fisher information about μ is:

    I_F(μ) = 1/σ²

For X ~ N(0, σ²), the Fisher information about σ is:

    I_F(σ) = 2/σ²

The connection to σ* = √(2 ln 2) (q_quantum_thermodynamics.md §10, OQ-QTD6): Fisher information I_F(θ) = E[(∂ log p/∂θ)²] is where the log family (Shannon entropy, Landauer) meets the quadratic family (Gaussian variance, equipartition). The score function ∂ log p/∂θ is a log derivative; its variance I_F is a quadratic expectation. Fisher information is literally the quadratic moment of a logarithmic quantity.

This does not resolve OQ-QTD6 (whether the co-occurrence is structural or taxonomic), but it identifies the precise meeting point: Fisher information is where the two families intersect.

### 6.5 Information geometry

The Fisher information matrix I_F(θ) defines a Riemannian metric on the space of probability distributions:

    ds² = Σ_{ij} [I_F(θ)]_{ij} dθ_i dθ_j

This is the Fisher-Rao metric. Geodesic distance in this metric measures the statistical distinguishability of distributions — how many observations are needed to tell θ from θ + dθ.

Key connections:
- **KL divergence** (§3) is the local distance: D_KL(p_θ || p_{θ+dθ}) ≈ (1/2) dθ^T I_F(θ) dθ
- **Thermodynamic metric** (q_quantum_thermodynamics.md §8.2): the Ruppeiner metric g_ij = β² Cov(X_i, X_j) IS the Fisher-Rao metric of the Gibbs family, with θ = β (inverse temperature). The geodesics of optimal thermodynamic protocols are geodesics of the Fisher-Rao metric.

In L0 terms: information geometry equips the space of "possible worlds" (parametric distributions) with a metric derived from the observer's sensitivity. Nearby worlds that the observer can easily distinguish are far apart in Fisher-Rao distance. Nearby worlds that look identical through the window are close. The geometry is not a property of the worlds — it is a property of the observer's window.

**Forward to dedicated entry**: an extended treatment of information geometry — including the central theorem **Fisher-Rao = Arrow 1⁻¹ local linearization** (`c_information_geometry.md §2`, ESTABLISHED 2026-04-28), Quantum Fisher Information / Bures metric (§3), Berry phase / Fubini-Study (§4), Wasserstein / optimal transport (§5), and the candidate 3 distances ↔ 3 Arrows correspondence (§5.3) — is collected in `c_information_geometry.md`.

### 6.6 Natural gradient

The natural gradient ∇̃ = I_F^{-1} ∇ adjusts the parameter update direction for the Fisher-Rao geometry. In optimisation:

    θ_{t+1} = θ_t - η I_F(θ_t)^{-1} ∇L(θ_t)

This is the steepest descent direction in the space of distributions (not in parameter space). Natural gradient descent is invariant to parameterisation — it descends along the statistical manifold, not along arbitrary coordinates.

In L0 terms: the natural gradient is the A3-invariant (gauge-invariant) update. Ordinary gradient descent depends on the parameterisation (gauge choice). Natural gradient does not. This connects A3 (gauge invariance) to optimisation theory.

---

## §7 Bayesian Inference and Decision Theory

### 7.1 Bayes' theorem as observation update

    p(θ|x) = p(x|θ) p(θ) / p(x)

| Bayesian term | L0 term |
|---|---|
| Prior p(θ) | Observer's initial belief about S |
| Likelihood p(x\|θ) | Window W's transfer function |
| Posterior p(θ\|x) | Updated belief after observation m(S\|_W) |
| Evidence p(x) | Normalisation (marginal likelihood) |

Bayesian inference is the mathematical implementation of L0's observation process: the observer starts with prior knowledge, receives an observation through a finite window, and updates beliefs according to the window's transfer function.

### 7.2 Conjugate priors and sufficient statistics

When prior and posterior belong to the same family (conjugacy), the observation can be summarised by a sufficient statistic T(x) without information loss:

    I(θ; X) = I(θ; T(X))

Sufficient statistics are L0-optimal compressions: they are the minimal representation of the observation that retains all parameter information. This connects to IB (§5): a sufficient statistic for θ achieves the IB optimum for the task of estimating θ.

### 7.3 Model comparison and Bayesian Occam's razor

The evidence (marginal likelihood) p(x) = ∫ p(x|θ) p(θ) dθ naturally penalises complex models: a model that spreads its prior over a large parameter space has lower evidence unless the data warrant the complexity. This is the Bayesian Occam's razor.

Connection to AIT (§8): Bayesian model comparison and minimum description length (MDL) are asymptotically equivalent. Both implement the same principle: prefer the simplest explanation consistent with the data. The difference is implementation — Bayesian via priors, MDL via code lengths.

### 7.4 Decision theory: loss functions and risk

Given posterior p(θ|x), the optimal action a* minimises expected loss:

    a* = argmin_a E_{θ|x}[L(θ, a)]

| Loss function | Optimal action | Role |
|---|---|---|
| Squared loss | Posterior mean | Estimation |
| 0-1 loss | Posterior mode (MAP) | Classification |
| Absolute loss | Posterior median | Robust estimation |
| Log loss | Predictive distribution itself | Probability forecasting |

The choice of loss function encodes the observer's purpose. Different losses produce different optimal windows — the same observation supports different actions depending on what the observer needs. This is the decision-theoretic complement to IB's compression-relevance tradeoff (§5.3).

---

## §8 Algorithmic Information Theory

### 8.1 Kolmogorov complexity

The Kolmogorov complexity K(x) of a string x is the length of the shortest program that produces x on a universal Turing machine:

    K(x) = min_{p: U(p) = x} |p|

K(x) is:
- **Uncomputable**: no algorithm can compute K(x) for all x (halting problem)
- **Invariant**: up to O(1) additive constant, independent of the choice of universal Turing machine
- **Upper-bounded by description**: K(x) ≤ |x| + O(1) (the identity program)

### 8.2 Algorithmic vs Shannon entropy

Shannon entropy H(X) is a property of a distribution over strings. Kolmogorov complexity K(x) is a property of a single string. The relationship:

    E[K(X)] ≈ H(X)    (for i.i.d. sources)

Shannon measures the average complexity of the source. Kolmogorov measures the complexity of the individual output.

In L0 terms, this distinction is fundamental:
- **Shannon**: How much can the window transmit on average? (property of the observation process)
- **Kolmogorov**: How complex is this particular observation? (property of the object)

The window (Shannon) and the object (Kolmogorov) are L0's two sides. A random string has high K but may come from a high-entropy source (high H). A structured string has low K but may also come from a high-H source (atypical draw). The gap K(x) - H(X) measures how typical x is within its source — a single-instance version of the observation-vs-structure distinction.

### 8.3 Minimum Description Length (MDL)

MDL principle: the best model M for data D is the one that minimises:

    L(M) + L(D|M)

where L(·) is code length. L(M) is model complexity; L(D|M) is data fit. This implements the Occam tradeoff computably (unlike raw Kolmogorov complexity).

MDL connects to:
- **Bayesian model comparison** (§7.3): asymptotically equivalent, with L(M) ↔ -log p(M) and L(D|M) ↔ -log p(D|M)
- **Rate-distortion** (§4): MDL minimises total description length; R(D) minimises rate at fixed distortion. Both are compression under constraint.
- **IB** (§5): IB compresses for a task; MDL compresses for reconstruction. IB adds a purpose; MDL is purpose-agnostic.

### 8.4 Structural complexity vs random complexity

A string can be complex for two reasons:
1. **Structural complexity**: the string encodes a rich pattern (low K relative to apparent complexity)
2. **Random complexity**: the string has no pattern (K ≈ |x|)

AIT provides the language to separate these. For a σφ observable O measured on domain D:

- If K(O|D) << |O|: the observable is structurally determined — the domain predicts it (this is the L1 theorem case)
- If K(O|D) ≈ |O|: the observable is domain-independent noise — no compression possible (this is the L4 error case)

The AIT perspective reframes L4 errors: an error entry is a residual whose Kolmogorov complexity cannot be reduced by conditioning on known L1/L2 structure. If K(residual | known_theorems) ≈ |residual|, the residual is genuinely random. If K(residual | known_theorems) << |residual|, a theorem is missing.

### 8.5 Algorithmic f_rational — Theorem 4a.1 instance (ESTABLISHED 2026-04-28)

**Theorem 8.5.1 (Algorithmic instance of Theorem 4a.1, Paper I1 §5.2.1 定理 5.2)**: For an observation x ∈ {0,1}* with structural background B (known L1/L2 dictionary content), the conditional Kolmogorov complexity is the unified f_rational of the algorithmic class:

    f_rational^alg(x; B) := K(x | B)    [bits]

This is the Theorem 4a.1 (`c_filtration_obstruction.md §8.5.3`) unified $M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B} = -\log_2 F_C \asymp K(x|B)$ via the Solomonoff prior interpretation $F_C(\delta_x) \asymp 2^{-K(x|B)}$, where $C^{\mathrm{alg}}_B$ = computably-encodable distributions given B.

**Properties** (matching L0 A1 axiom `finite_observation.md §5.1`):
- Gauge-asymptotic invariance: UTM gauge change → O(1) shift, vanishing as rate O(1)/|x| → 0 (Kolmogorov invariance theorem)
- Reducible by structural conditioning: better B reduces K(x|B) — this *is* §8.4's L4 error reframing
- Provably > 0 for generic x: counting argument gives K(x) ≥ |x| - O(log|x|) for almost all length-|x| strings
- Uncomputable but per-string finite: framework's strongest "obstruction provably non-zero AND non-computable" instance

**Numerical verification**: 5 instances + V1 (conditional reduction) + V2 (UTM-gauge asymptotic invariance) = **7/7 PASS** at |x| = 65536 bits using K_upper = min(gzip, bz2, lzma) as tightest computable upper bound. Rate range [0.0067, 1.003] across structurally-determined → algorithmically-random regimes — 5 orders of magnitude. See `research/oq_algorithmic_f_rational_v1.md` + `_v1.py`.

**Cross-arrow consistency at log₂-bit unit**: algorithmic instance scales freely with |x|, extending the Theorem 4a.1 unified f_rational range beyond Hodge / Q1 4-class / Stark (which are dim-bounded by their specific structures). Algorithmic f_rational sits at the **uncomputable extreme** of the framework's f_rational instance spectrum.

**Spawned successor OQs** (Paper I1 §8.3): OQ-Alg-MDL-Tightness (MEDIUM), OQ-Alg-Hodge-Parallel (LOW, Conjecture 4a.2 5th data point), OQ-Alg-Quantum-Cross (MEDIUM, K(ρ) via tomography classical record → Q1 4-class bridge).

---

## §9 Topological Data Analysis

### 9.1 Persistent homology

Given a point cloud X ⊂ ℝ^d, persistent homology tracks topological features (connected components, loops, voids) as a scale parameter ε increases:

1. At each scale ε, build a simplicial complex (e.g., Vietoris-Rips: connect points within distance ε)
2. Compute homology groups H_k of the complex
3. Track which features persist across scales: birth time b_i, death time d_i
4. Record as a persistence diagram: {(b_i, d_i)} in the (birth, death) plane

Features with long persistence (d_i - b_i large) are topological signal. Features with short persistence are noise.

### 9.2 L0 translation: what survives coarse-graining

Persistent homology directly implements the L0 question: **as the observation window changes resolution (ε), what topological features persist?**

| TDA concept | L0 concept |
|---|---|
| Scale parameter ε | Window resolution (L0 §1, Nyquist-like) |
| Birth time b_i | Scale at which feature first becomes visible |
| Death time d_i | Scale at which feature merges / disappears |
| Persistence d_i - b_i | Robustness to coarse-graining |
| Persistence diagram | Spectrum of topological observables at all resolutions |

The persistence diagram is a resolution-indexed observable — it shows what the observer sees at each level of coarse-graining. Long-lived features are structural (L1). Short-lived features are noise (L4 candidates).

### 9.3 Stability theorem

The bottleneck distance between persistence diagrams is bounded by the Hausdorff distance between point clouds:

    d_bottleneck(Dgm(X), Dgm(Y)) ≤ d_Hausdorff(X, Y)

This stability result means: small perturbations of the data produce small perturbations of the persistence diagram. The topological signal is robust to noise — exactly the property an L0 observer needs.

### 9.4 Connections to other sections

- **Shannon entropy of persistence diagrams**: Persistence entropy H_P = -Σ_i (l_i/L) log(l_i/L), where l_i = d_i - b_i and L = Σ l_i. This is Shannon entropy (§1) applied to the normalised lifetime distribution.
- **Information content of topology**: How many bits does the persistence diagram carry about the underlying manifold? This connects rate-distortion (§4) to topological features.
- **TDA for representation spaces**: Applying persistent homology to the latent space of neural networks reveals the topology of learned representations. This connects to IB (§5): does IB compression preserve or destroy topological features?

### 9.5 Betti numbers and the three-phase taxonomy

The Betti numbers β_k count independent k-dimensional topological features:
- β_0: connected components
- β_1: independent loops
- β_2: enclosed voids (cavities)

Connection to three_phase_taxonomy.md:
- **GAS** phase: many connected components (high β_0), few loops → fragmented structure
- **LIQUID** phase: intermediate connectivity, loops forming → transitional
- **SOLID** phase: few components (low β_0), complex loop structure (high β_1) → integrated structure

This is speculative (OQ-IT6, §12), but persistent homology could provide a topological characterisation of the GAS/LIQUID/SOLID classification that is currently defined by domain-specific observables (φ_eff/φ for connectomes, absorption for crystals).

---

## §10 L0 Translation Table

### 10.1 Dictionary

| Information theory concept | L0 concept | Section |
|---|---|---|
| Shannon entropy H(X) | Information content of the observation | §1 |
| Source coding theorem | Compression floor of the window | §1.2 |
| Mutual information I(X;Y) | Shared information between two windows | §2.1 |
| Channel capacity C | Maximum transmission rate of the window | §2.2 |
| Data processing inequality | Window cannot create information | §2.3 |
| KL divergence D_KL | Observation cost of wrong model | §3.2 |
| Rate-distortion R(D) | Compression-fidelity tradeoff of the window | §4.4 |
| Distortion floor D_min | Irreducible observation error | §4.4 |
| Information Bottleneck | Task-optimal window design | §5.3 |
| Fisher information I_F(θ) | Window sensitivity to parameter | §6.2 |
| Cramér-Rao bound | Precision limit of the window | §6.2 |
| Fisher-Rao metric | Statistical geometry of distinguishability | §6.5 |
| Natural gradient | Gauge-invariant optimisation | §6.6 |
| Posterior p(θ\|x) | Updated belief after observation | §7.1 |
| Kolmogorov complexity K(x) | Intrinsic complexity of the object | §8.2 |
| MDL | Optimal model = shortest total description | §8.3 |
| Persistence diagram | Resolution-indexed topological observable | §9.2 |

### 10.2 The five questions, revisited

Each strand answers a different L0 question:

```
L0: "All observation is finite"
 │
 ├─ §1-3 Shannon: "How much can the window transmit?" → capacity C
 ├─ §4 Rate-Distortion: "How much must the window discard?" → R(D)
 ├─ §5 IB: "What should the window keep?" → I(T;Y)
 ├─ §6 Fisher: "How sensitive is the window?" → I_F(θ)
 ├─ §7 Bayes: "How should the observer update?" → p(θ|x)
 ├─ §8 AIT: "How complex is the object itself?" → K(x)
 └─ §9 TDA: "What shape survives coarse-graining?" → persistence diagram
```

### 10.3 Connection to existing constants

| σφ constant | Information-theoretic role | Section |
|---|---|---|
| c_s² = 1/2 | Gaussian channel prefactor (§2.4), Fisher I_F(σ) prefactor (§6.4) | §2.4, §6.4 |
| ln 2 | Shannon bit = Landauer cost unit | §1.1, QTD §5 |
| σ* = √(2 ln 2) | Fisher-meets-Shannon threshold (§6.4) | §6.4 |
| kT ln 2 | Landauer cost per bit (QTD §5.1) | §4.4 |

---

## §11 Bridges to Downstream Files

### 11.1 → metrology.md (D axis)

Information theory provides the theoretical bounds. Metrology asks: **in practice, how close does the observer get?** Measurement uncertainty (Type A: statistical, Type B: systematic) maps to:
- Type A: sampling noise → Shannon entropy of the estimator
- Type B: calibration bias → KL divergence from true distribution

The bridge: information theory says R(D) is the limit; metrology quantifies where real instruments sit relative to that limit.

### 11.2 → inference_control.md (C axis)

POMDP is Bayesian inference (§7) applied to sequential decision-making under partial observability. The belief state b(s) = p(s|history) is the posterior (§7.1) updated over time. Control-as-inference recasts optimal control as posterior inference over trajectories.

The bridge: information theory provides the static bounds (capacity, R(D), IB). Inference-control adds the dynamic dimension (sequential update, feedback, planning).

### 11.3 → fault_taxonomy.md (L4∩C)

AIT (§8) provides the language for fault classification: if K(residual | model) ≈ |residual|, the residual is noise. If K(residual | model) << |residual|, the model is missing structure. Changepoint detection asks: when did K(residual | model) jump?

The bridge: information theory defines what "normal" looks like (the rate-distortion operating point). Fault taxonomy defines departures from normal.

### 11.4 → network_science.md (C axis)

Mutual information (§2.1) between nodes measures coupling. Channel capacity (§2.2) constrains edge bandwidth. Rate-distortion (§4) governs compression in distributed settings. Queueing theory describes what happens when arrival rate exceeds service capacity (the finite-resource analogue of exceeding channel capacity).

### 11.5 → multi_agent.md (C∩E)

Multiple observers sharing information ↔ distributed source coding (Slepian-Wolf, Wyner-Ziv). Game theory payoffs as information-constrained decisions (§7.4). Common knowledge as mutual information condition.

### 11.6 → causal_inference.md (C axis)

Mutual information I(X;Y) cannot distinguish correlation from causation. Causal inference adds the do-calculus: I(X; Y | do(Z)) ≠ I(X; Y | Z) in general. This is the information-theoretic gap that causal inference fills.

---

## §12 Open Questions

**OQ-IT1** (numerical, medium priority): Is the 1/2 in the Gaussian channel capacity C = (1/2)log(1+SNR) the same c_s² = 1/2 as in the σφ dictionary?

In the Gaussian channel, 1/2 arises from the real-valued channel having half a complex degree of freedom. In the σφ dictionary, c_s² = 1/2 arises from ℤ/2ℤ parity (centering coherence). Both involve "halving," but the mechanisms differ. Test: does the complex Gaussian channel have capacity log(1+SNR) (no 1/2)? If yes, the 1/2 is dimension-counting, not c_s².

**OQ-IT2** (structural, high priority): Is the IB curve a universal observable?

If every L2 domain has an IB-like tradeoff (compression vs relevance), the IB curve might be an L3-level cross-domain structure. Test: compute IB curves for crystal (what hkl structure to keep for space group identification), FX (what price history to keep for prediction), and connectome (what connectivity to keep for function prediction). If the curves have universal shape features, promote to L3.

**OQ-IT3** (structural, medium priority): Does persistent homology provide a topological characterisation of the three phases?

From §9.5: GAS/LIQUID/SOLID might correspond to distinct persistence diagram signatures. Test on connectome data: compute persistence diagrams for C. elegans female (GAS, φ_eff/φ = 0.399), Witvliet 8 (LIQUID, 0.176), and C. elegans male (SOLID, 0.065). If persistence signatures separate the phases, this becomes a topology-based phase classifier.

**OQ-IT4** (foundational, high priority): Should information theory be an L0 axiom or an L1 theorem?

Currently placed at L1 (domain-independent mathematical structure). But the data processing inequality is arguably more fundamental than any specific L1 theorem — it is the mathematical content of "the window cannot create information." If the data processing inequality is derivable from A0 (finite window) + A1 (structured error) alone, it belongs at L0. Test: attempt the derivation.

**OQ-IT5** (bridge, medium priority): Is the Fisher-Rao metric the natural geometry of L0?

If the space of "possible observations" carries a Fisher-Rao metric (§6.5), and this metric governs both statistical inference and thermodynamic cost (§6.5 + QTD §8.2), then Fisher-Rao geometry might be the intrinsic geometry of the L0 observer's world. This would give L0 a geometric structure beyond the algebraic structure of A0-A5.

**OQ-IT6** (speculative, low priority): TDA and the three-phase taxonomy (§9.5).

Speculative connection between persistent homology signatures and GAS/LIQUID/SOLID. Requires computational verification on existing datasets (connectome, crystal disorder). Low priority until OQ-IT3 is tested.

**OQ-IT7** (bridge, medium priority): What is the relationship between Kolmogorov complexity and the conductor?

The conductor (nt_conductor.md) measures constraint scope. Kolmogorov complexity measures intrinsic complexity. For structured domains, K(observable | conductor_constraints) should be small — the conductor determines the observable up to residual noise. Is there a formal bound: K(O) ≤ f(conductor) + noise? This would connect AIT to the conductor framework.

---

*作成日: 2026-04-08*
*最終更新: 2026-04-08*
