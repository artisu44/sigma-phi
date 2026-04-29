---
status: AUDIT (light touch, no commit)
date: 2026-04-28
target_OQ: OQ-Algorithmic-f_rational (I1 §5.2 + §8.3 spawn)
verdict: candidate scope question ≤ resolved cleaner than expected
recommendation: candidate → ESTABLISHED promotion is feasible; user judgment required for proceed/hold
---

# OQ-Algorithmic-f_rational — light-touch audit

## 0. Light-touch framing

User instruction: 軽く触る (audit only, no commit). Per `feedback_discipline_calibration.md` 3-tier (audit / paper / promote). This file is **audit tier only** — does NOT update I1 §5.2 / §8.3, does NOT save memory entries. Stops at "candidate scope question resolution + recommendation."

## 1. The worry I flagged earlier

In the OQ verification batch (2026-04-28), I rated this OQ ★★★ → ★★ with caveat:

> "f_rational が uncomputable な量を扱うには工夫が要る (uncomputable は dim じゃない)。**ここで詰まる可能性あり**。"

Specifically: T-AAS f_rational has been historically described as $\dim(\ker_{\mathrm{topo}}^{\mathrm{non-surj}} \cap \mathrm{target})$ ([c_arrow_obstruction.md §10.2:659](C:/Users/aruti/OneDrive/Desktop/work/sigmaphi/dictionaries/L1_mathematical/core/c_arrow_obstruction.md:659)) — a dimension. Kolmogorov K(x) is uncomputable, takes integer values bounded by $|x| + O(1)$, and cannot naturally be a "dimension".

## 2. Audit finding: the worry was over-strict

Existing T-AAS instances (`c_arrow_obstruction.md §10.3`, [c_filtration_obstruction.md §8.5](C:/Users/aruti/OneDrive/Desktop/work/sigmaphi/dictionaries/L1_mathematical/core/c_filtration_obstruction.md)) show **flexibility beyond strict integer dim**:

| Instance | f_rational form | type |
|---|---|---|
| Hodge | $\dim(\mathrm{Hdg}^p / \mathrm{im\ cl})$ | strict integer dim |
| Stark | $f_{\mathrm{field}}$ = log L-ratio | real-valued, log-scale |
| Crystal | $f_{\mathrm{sampling}}$ = sampling resolution | real scalar |
| **DNA (Paper F)** | $\gamma = S/W$ codon position selection | **real-valued ratio in $[0, 1]$** |
| Quantum 4-class (Q1 §5) | $M_{\mathrm{unified}}^C = -\log_2 F_C(\rho)$ | log₂-bit, real-valued |

**Theorem 4a.1** (`c_filtration_obstruction.md §8.5.3:582`) explicitly **unifies these to a common log₂-bit unit** via class-fidelity:

$$M_{\mathrm{unified}}^{C}(\rho) := -\log_2 F_C(\rho), \quad F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$$

Conjecture 4a.2 lifts the classical Hodge dim to the same log₂-bit unit:
$$f_{\mathrm{rational}}^{\mathrm{Hodge}}(X, p) \ \widetilde{=}\ \log_2(\dim(\mathrm{Hdg}^p / \mathrm{im\ cl}) + 1)$$

So the framework's canonical f_rational unit is **bits** (log₂-fidelity), not "dim" — and Theorem 4a.1 is the unifier. The "dim" label in early T-AAS writing was the Hodge instance; the unified form is bit-valued.

## 3. Algorithmic instance plugs in cleanly

Define for a string $x$ with structural background $B$ (known L1/L2 theorems, conditioning data):

$$f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B) \quad \text{[bits]}$$

where $K(x|B)$ is the conditional Kolmogorov complexity (length of shortest program producing $x$ given $B$).

**Theorem 4a.1 unification**: this is the unified form. The "class" $C^{\mathrm{alg}}_B$ = computably-encodable distributions given $B$. Its closure under convex combinations + Solomonoff mixing gives the universal prior $m(x|B) = 2^{-K(x|B)}$ (up to multiplicative constant). Then:
$$F_{C^{\mathrm{alg}}_B}(\delta_x) = \sup_{q \in \overline{C}^{\mathrm{alg}}_B} q(x) \asymp 2^{-K(x|B)}$$
$$\Rightarrow \quad M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B}(x) = -\log_2 F_{C^{\mathrm{alg}}_B}(\delta_x) \asymp K(x|B)$$

(The $\asymp$ hides the universality additive constant from Coding Theorem.)

**Conditions check**:
- (i) convex closure: ✓ (mixtures of computable distributions are computable up to log overhead)
- (ii) class-preserving operations: ✓ (computable transformations preserve "computably-encodable")

**Properties of $K(x|B)$ as f_rational**:
- **Persistence under gauge**: ✓. Changing UTM gauge changes $K(x|B)$ by $O(1)$, vanishing as fraction $O(1)/|x| \to 0$ for long strings — gauge-invariant in the asymptotic limit (this is Kolmogorov's invariance theorem).
- **Reducible by structure**: ✓. Better $B$ (more known theorems) reduces $K(x|B)$. This **is** the L4 error reframing in §8.4 of `c_information_theory.md`: error magnitude = irreducible algorithmic content rate.
- **Provably $> 0$ in non-trivial case**: ✓. Kolmogorov's theorem shows most strings $x$ of length $n$ have $K(x) \geq n - O(\log n)$ — generic strings have positive irreducible content.
- **Uncomputable**: ✓. $K(x|B)$ is uncomputable in $x$ (halting problem), but **definitionally finite** for each individual $x$. This is the canonical "obstruction is provably non-zero AND non-computable" case — the strongest f_rational > 0 instance in the framework.

## 4. Scope verdict (for the original (a)/(b)/(c) trichotomy I posed)

| scope | evaluation |
|---|---|
| (a) Generalize T-AAS f_rational beyond dim | **NOT NEEDED**. Theorem 4a.1 already provides the bit-valued unification; algorithmic instance plugs in via Solomonoff prior. |
| (b) Define ω_K = "Kolmogorov rank" = ∞ | **NOT THE RIGHT FRAMING**. The natural quantity is $K(x \mid B)$ itself (finite per-x), not a single rank summarising. |
| (c) Restrict to qualitative parallel only | **NOT NEEDED**. Quantitative formulation is clean. |

So the candidate was **stronger than I initially judged** — the audit pass clears the dim-semantics worry by showing Theorem 4a.1 already handles non-dim instances.

## 5. What ESTABLISHED promotion would require

This is **not done in this audit**. To promote OQ-Algorithmic-f_rational from candidate to ESTABLISHED:

1. **Formal Theorem block** in I1 §5.2 lifting the row entry to a numbered theorem (analogous to §3.3 Renyi-Scaffold and N3 §2.2 Type γ patches done earlier today)
2. **2+ concrete instances** (analogous to Q1 §5 4-class verification):
   - Instance 1: random vs structured string examples (binary expansion of π vs random binary string at same length)
   - Instance 2: connection to MDL — show $K(x|B)$ ≥ MDL upper bound, and the gap matches "uncomputable residue"
3. **L0 axiom A1 connection**: explicit derivation that $K(x|B)/|x|$ is the L0 "irreducible-by-window" rate for the algorithmic projection of A1
4. **Cross-arrow consistency**: verify $K(x|B)$ as f_rational is consistent with Hodge / Quantum f_rational under the Theorem 4a.1 unified scale (typical-scale comparison, similar to Conjecture 4a.2)

Estimated effort: 1 session (~1h), in line with other ★★ tier closures done today.

## 6. Honest scope caveats

- **Universality additive constant**: $K(x|B)$ depends on UTM choice up to $O(1)$. The framework's gauge-invariance claim holds *asymptotically* (as $|x| \to \infty$), which matches existing T-AAS practice (Stark $f_{\mathrm{field}}$ also has a convention-dependent normalization).
- **Conditional vs unconditional**: $K(x)$ unconditional is also acceptable as f_rational (with $B$ = "trivial structural prior"). The conditional form is more general and connects to L4 error refinement directly.
- **Upper bound vs exact**: $K(x|B)$ cannot be computed but **upper bounds** can (any computable encoding gives an upper bound). Practical use is via tightest known computable upper bound (e.g., Lempel-Ziv complexity, MDL, neural compression). For framework-level claims this is fine — the existence claim ($K(x|B) > 0$ for generic $x$) is provable; numerical estimation uses upper bounds.
- **Scope of "structural background $B$"**: in framework usage, $B$ = full L1/L2 dictionary. In a specific application, $B$ = the relevant subset of theorems already known. Both are valid uses.

## 7. Recommendation (3 options for user)

| option | description | effort |
|---|---|---|
| **A. ESTABLISHED promotion** | Apply §5 plan: I1 §5.2 row → formal Theorem (like Renyi 定理 3.1), §8.3 OQ table candidate → ESTABLISHED, write 1-2 instances + memory entry. | ~1 session (~1h) |
| **B. candidate_v1 only** | Update I1 §5.2 row text to cite Theorem 4a.1 unified form + K(x\|B) formula (no formal Theorem block, no §8.3 status change). Light improvement, leaves OQ open for future verification. | ~15 min |
| **C. status quo** | Leave I1 untouched. This audit note stands as a forward-task signpost. | 0 |

**My recommendation: Option B** ("candidate_v1 cite of Theorem 4a.1") — captures the audit finding without committing to full ESTABLISHED before instance verification. Matches `feedback_discipline_calibration.md` (don't stack at every cycle).

If the user wants ESTABLISHED (Option A), the §5 plan above is the path. The audit content here covers ~70% of the formal content already.

## 8. Files

- `research/oq_algorithmic_f_rational_audit_v0.md` — this file (audit only)
- No script — audit is conceptual; instance verification scripts would come with Option A only.

## 9. Light-touch closure

The user's "軽く触ってみる" instruction is honored: this audit clears the dim-semantics worry, identifies Theorem 4a.1 as the unifier, plugs in the K(x|B) candidate cleanly, and stops at recommendation without committing. User judgment required for next step.
