---
status: candidate_v0 → CANDIDATE_RESOLVED_NEGATIVE
date: 2026-04-28
target_OQ: OQ-P1-Capacity (I2 §4.4 spawn)
target_paper: I2 §0 Abstract M3, §4.2 主張 4.1
verdict: published 2.18 bits/symbol figure is ~5.5× over the honest Shannon capacity
honest_capacity_bits_per_symbol: 0.4000  # at σ* = √(2 ln 2)
methods: M1 (closed-form integration) + M2 (Blahut-Arimoto) + M3 (Gaussian approx)
script: research/oq_p1_capacity_v0.py
---

# OQ-P1-Capacity v0 — honest Shannon capacity of the σ\* phase channel

## 1. Question

Does the I2 §4.2 capacity claim
$$C_{\sigma_*} = \log_2(2\pi / \sigma_*^2) = \log_2(\pi / \ln 2) \approx 2.18 \text{ bits per phase symbol}$$
hold under a rigorous Shannon mutual-information calculation?

## 2. Setup

Channel: $\phi = \theta + N \pmod{2\pi}$, $\theta \in [0, 2\pi)$ input phase, $N$ wrapped Gaussian noise of standard deviation $\sigma$. Capacity:
$$C(\sigma) = \max_{p(\theta)} I(\theta; \phi) = h(\phi) - h(\phi \mid \theta)$$

The conditional entropy $h(\phi \mid \theta) = h(\text{WG}(\sigma))$ is independent of the input. Wrapped-Gaussian convolution preserves uniformity, so a uniform input yields a uniform output, achieving $h(\phi) = \log_2(2\pi)$. Therefore:
$$C(\sigma) = \log_2(2\pi) - h(\text{WG}(\sigma)) \quad \text{[uniform input is optimal]}$$

## 3. Two independent issues with the published derivation

### 3.1 Dimensional inconsistency

I2 §4.2 derivation reads:
> "phase $\theta \in [0, 2\pi)$ continuous + σ\* threshold で resolvable distinct phase levels = $2\pi/\sigma_*^2$ (Gaussian noise width pi resolution)、Hartley $\log_2$ で bits 化."

A "level count" should divide a circumference $2\pi$ (rad) by a *width* $\sigma_*$ (rad), giving a dimensionless count. Dividing by $\sigma_*^2$ (rad²) gives units of rad⁻¹, which cannot be log-counted.

| variant | formula | numerical | comment |
|---|---|---|---|
| **paper (σ²)** | $\log_2(2\pi/\sigma_*^2)$ | 2.180 | dimensionally inconsistent |
| linear (1σ) | $\log_2(2\pi/\sigma_*)$ | 2.416 | dimensionally consistent |
| 2σ (Rayleigh) | $\log_2(2\pi/(2\sigma_*))$ | 1.416 | conventional resolution |
| half-circle | $\log_2(2\pi/\pi) = 1$ | 1.000 | binary phase floor |

That the paper's choice numerically lands at 2.18 is a coincidence of $\sigma_*^2 = 2\ln 2 \approx 1.39$.

### 3.2 Hartley counting ≠ Shannon capacity

Even with a dimensionally consistent level count, $\log_2(\text{count})$ is the **Hartley (cardinality) bound**, not the achievable mutual-information rate. For a phase channel with continuous noise, a brick-wall "resolvable / unresolvable" model is a coarse upper bound. Shannon capacity is strictly less.

## 4. Honest computation

Three independent methods at $\sigma = \sigma_* = \sqrt{2 \ln 2}$:

| method | value (bits/symbol) | notes |
|---|---|---|
| **M1** closed-form $\log_2(2\pi) - h(\text{WG}(\sigma_*))$ | **0.3998** | numerical integration of WG entropy |
| **M2** Blahut-Arimoto, $M = 512$ discretisation | **0.3996** | optimal input deviates from uniform by $4.4 \times 10^{-16}$ |
| **M3** Gaussian small-σ approximation $\frac{1}{2}\log_2(2\pi/(e\sigma_*^2))$ | 0.3688 | wrapping correction $\approx +0.03$ bits |

M1 and M2 agree to $1.7 \times 10^{-4}$ bits, confirming the closed-form derivation and the optimality of uniform input. M3 is slightly low because at $\sigma_* \approx 1.18$ rad wrapping starts to matter; the exact M1 value sits between the small-σ Gaussian approx and $\log_2(2\pi)$ as expected.

**Honest capacity at σ\*: ≈ 0.40 bits/symbol.**

## 5. σ-sweep (honest capacity vs σ)

| label | σ | C_honest (bits/symbol) | published-form $\log_2(2\pi/\sigma^2)$ |
|---|---|---|---|
| σ = 0.3 | 0.300 | 2.341 | 6.125 |
| σ = 0.5 | 0.500 | 1.605 | 4.652 |
| σ = 0.7 | 0.700 | 1.119 | 3.681 |
| σ = 1.0 | 1.000 | 0.612 | 2.652 |
| **σ\* = √(2 ln 2)** | **1.177** | **0.400** | **2.180** |
| σ = 1.5 | 1.500 | 0.160 | 1.482 |
| σ = 2.0 | 2.000 | 0.027 | 0.652 |
| σ = 3.0 | 3.000 | 0.000 | undefined |

Asymptotics: $C \to \log_2(2\pi) \approx 2.65$ as $\sigma \to 0$; $C \to 0$ as $\sigma \to \infty$. Both correct.

## 6. Inflation ratio

$$\frac{C_{\text{published}}}{C_{\text{honest}}} = \frac{2.180}{0.400} \approx 5.45$$

The published 2.18 figure overstates the honest Shannon capacity by a factor of ~5.5×. The two errors compound: ~1.5× from the σ² → σ dimension fix, and ~3.6× from Hartley → Shannon.

## 7. Reinterpretation of σ\*

The honest capacity at $\sigma = \sigma_*$ is ≈ 0.40 bits/symbol — close to the natural channel-engineering threshold of "½ bit/symbol" below which a phase-coded channel becomes practically useless. This gives σ\* a **clean Shannon-theoretic meaning**:

> $\sigma_*$ is the noise level at which the wrapped-Gaussian phase channel's capacity drops below ≈ ½ bit per symbol.

This is consistent with — and arguably stronger than — the "half-amplitude convention $E[\cos Z] = 1/2$" framing, because it ties σ\* to a **standard quantitative information-theoretic threshold** rather than a magnitude-based heuristic.

## 8. Implications

### 8.1 I2 abstract / §4.2 corrections required

| location | current text | proposed correction |
|---|---|---|
| §0 Abstract M3 | "提案 capacity $C_{\sigma_*} \approx 2.18$ bits/symbol" | "honest Shannon capacity $C_{\sigma_*} \approx 0.40$ bits/symbol (uniform-input wrapped Gaussian phase channel, M1+M2 cross-check)" |
| §4.2 主張 4.1 | $C = \log_2(2\pi/\sigma_*^2) \approx 2.18$ | $C = \log_2(2\pi) - h(\text{WG}(\sigma_*)) \approx 0.40$ |
| §4.2 derivation outline | "Hartley $\log_2$ で bits 化" | replace with "uniform-input optimality + wrapped-Gaussian differential entropy via numerical integration" |
| §4.2 comparison to Shannon-Hartley | "P1 が ~2x advantage" | **REJECTED** — at σ\*, P1 capacity (0.40) is below typical Shannon-Hartley AWGN at moderate SNR. Phase encoding is **not** a density-advantage paradigm at the σ\* operating point. |

### 8.2 Downstream effects

- **§4.3 EEG empirical verification**: σ\* damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ remains valid (this is a magnitude/coherence statement, not a capacity statement). The information-theoretic *interpretation* shifts from "2.18 bits/symbol channel" to "<½-bit/symbol channel threshold."
- **§4.4 Status**: P1 should be **demoted from candidate_v1 to candidate_v0_corrected**. The proposal "phase-noise-bounded channel as standalone communication paradigm with quantitative capacity" is preserved, but the *quantitative* claim must be replaced with the honest 0.40 figure.
- **§11 Practical Tradeoff Comparison Table (P1 row)**: net advantage column needs to drop the "~2x density advantage" claim.

### 8.3 What is *not* affected

- σ\* itself ($\sigma_* = \sqrt{2\ln 2}$) as a half-amplitude gauge threshold (Q3 §4) is unchanged.
- 5-stage ln 2 chain stage S4 is unchanged.
- I1 §6 anchor (e) σ\* phase observation gauge is unchanged (this is gauge, not capacity).
- The σ\*-channel as a *qualitative* paradigm (phase-noise-bounded coherent channel) survives; only its *quantitative* capacity claim is corrected.

## 9. 4-phase mathematical vocabulary literal check

(per `feedback_mathematical_vocabulary_literal_check.md`)

| phase | check | result |
|---|---|---|
| pre-write | "capacity" used in I2 means Shannon mutual-info, not Hartley count | **VIOLATED** in published §4.2 |
| pre-write | "σ\*" / "σ\*²" units consistent in formula | **VIOLATED** ($\log_2(2\pi/\sigma_*^2)$ has units rad⁻¹ inside log) |
| post-write | computed C cross-check between methods | **PASS** (M1 ≈ M2 to 1.7e-4 bits) |
| post-exec | σ-sweep asymptotics correct | **PASS** ($C \to \log_2(2\pi) = 2.65$ at σ→0, $C \to 0$ at σ→∞) |
| scaling | linear vs σ² parametric sensitivity | **CONFIRMED** that σ² is wrong dimensional choice |

## 10. Pre-flight under final metric (per `feedback_metric_generator_dependency`)

- **Generator**: wrapped Gaussian phase channel $\phi = \theta + N$ with $N \sim \text{WG}(\sigma_*)$
- **Null**: σ → ∞ wrapped Gaussian (output uniform regardless of input)
- **Final metric**: Shannon mutual-information capacity (bits/symbol)
- **Signal C(σ\*) = 0.400, null C(σ → ∞) → 0**
- **Signal/null gap**: 0.400 bits — clean separation, no confusion with null.

## 11. Hallucination index H

(per `feedback_hallucination_index.md`)

- **biased prior** (= published 2.18): asks reader to accept Hartley counting as Shannon capacity
- **null** (σ → ∞ uniform output): C = 0
- **honest signal** (σ\*): C = 0.400
- **discrim signal − null**: 0.400 bits

H_published = (2.18 − 0) / (0.400 − 0) ≈ **5.45**

H ≥ 1 → broken. The published figure overstates the discrim by 5.45× → **clearly broken** by the H index criterion.

## 12. Status & next steps

- **OQ-P1-Capacity** → **CANDIDATE_RESOLVED_NEGATIVE_PUBLISHED** (the proposed 2.18 figure is wrong; the honest Shannon capacity is ~0.40).
- **Action 1 (paper-level, recommended)**: update I2 §0 Abstract M3 + §4.2 + §4.4 + §11 P1 row with the honest 0.40 figure (drafted in §8.1 above). **Recommend explicit mark in §4.2: "v0.1 retraction of the v0 2.18 estimate, replaced with M1+M2 verified 0.40."**
- **Action 2 (downstream)**: re-examine I2 §11.5 OQ-Practical-Tradeoff-Quantification — the P1 row of the implementation table needs honest numbers, which this OQ now supplies.
- **Action 3 (no action needed)**: σ\*-as-gauge claims (Q3, I1 §6, sheet_A) are unaffected.

## 13. Files

- `research/oq_p1_capacity_v0.py` — verification script (M1 + M2 + M3 + σ-sweep + dimensional check)
- `research/oq_p1_capacity_v0.md` — this file

## 14. Honest scope caveat

The 0.40 bits/symbol value is for the **idealised wrapped-Gaussian phase channel with continuous input**. Real phase-encoded channels (PSK, QPSK, 8-PSK, etc.) use **discrete input constellations** and achieve different capacities depending on the constellation size. A discrete M-PSK system with M = 4 at σ\* would have capacity bounded above by both 2 (= log₂ 4) and 0.40 (continuous bound) — i.e., still 0.40. For the σ\*-channel framing as a *theoretical coherent channel paradigm*, the continuous-input bound is the correct quantity.
