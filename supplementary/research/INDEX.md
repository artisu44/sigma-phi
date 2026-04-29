# Supplementary research notes — index

This folder contains 26 research notes / verification scripts / clean run logs cited by the 10 publication papers (N1-N5 / Q1-Q3 / I1-I2). They are reproducibility evidence and are not load-bearing for paper readability.

## Mapping: paper → research files

### N-series

| Paper | Research files cited |
|---|---|
| **N1** | `bidirectional_duality_v0.md` (S15 cross-Arrow 3-vertex anchor), `oq_l0_refinement_finite_infinite_2axis_v0.md` |
| **N2** | `paper2_twin_dictionary_bridge_v1.md` (parent bridge document) |
| **N3** | `oq_omega_schumann_v0.md` (v1 Path 2 13/13 gates), `schumann_path2_check.py` (verification script) |
| **N4** | `stark_projection_v0.md` (rank 0/1 + 6-gauge + Atlas grammar), Hasse-Weil arc 8-stage v2_v0 → v2_v8 (not all included; main results referenced in N4 §2 + §3) |
| **N5** | `brauer_closure_galois_classification_v0.md` (Tier 1/2/3+ success), `brauer_closure_failure_taxonomy_v0.md` (Tier √/∞ failure + Q_8 LMFDB witness), `stark_projection_v0.md` |

### Q-series

| Paper | Research files cited |
|---|---|
| **Q1** | `oq_omega_obs_1_ker_entangle_frational_path_v0.md` (Schmidt rank ker_entangle = f_rational quantum CONFIRMED), `oq_omega_obs_3_e_arrow3_v0.md` (S17 Arrow 3 e-extremum 5/5 gate, ESTABLISHED 2026-04-23), `oq_omega_obs_3_info_density_check.py` (S17 verification 5/5 PASS), `oq_omega_obs_4_noncommutative_scan_v0.md`, `oq_omega_obs_4a_refined_quantum_hodge_v0.md` (4-class refined Hodge ESTABLISHED, 6/6 gate), `oq_omega_obs_4a_monotone_verify.py` (1-qubit M_F + 2-qubit CHSH verification) |
| **Q2** | `oq_omega_obs_4a_refined_quantum_hodge_v0.md`, `oq_oqs2_kraus_l0_bijection_v0.md` (NEW 2026-04-28; 定理 5.1 Lindblad-Kraus L0 bijection, V1/V2/V3 PASS), `oq_oqs2_kraus_l0_bijection_v0_run_log.txt` (clean run log), `oq_qsm1_kms_l0_a0c_v0.md` (forward-task placeholder, **not yet written** — note in §9 Q2) |
| **Q3** | `oq_omega_obs_3_e_arrow3_v0.md`, `oq_sigma_star_universality_v0.md` (forward-task placeholder, **not yet written** — note in Q3 §7), `oq_born_representation_independent_v0.md` (forward-task placeholder, **not yet written** — note in Q3 §7), `oq_p2_1_carry_closed_form.md`, `oq_p2_2_sstar_asymptotic.md` |

### I-series

| Paper | Research files cited |
|---|---|
| **I1** | `oq_omega_obs_3_e_arrow3_v0.md` (S17 ESTABLISHED), `oq_omega_obs_3_info_density_check.py` (5/5 gate PASS), `oq_omega_obs_4a_refined_quantum_hodge_v0.md` (4-class), `oq_omega_obs_1_ker_entangle_frational_path_v0.md`, **`oq_algorithmic_f_rational_v1.md` (NEW 2026-04-28; 定理 5.2)**, **`oq_algorithmic_f_rational_v1.py` (NEW; 7/7 PASS)**, `oq_algorithmic_f_rational_v1_run_log.txt`, `oq_algorithmic_f_rational_audit_v0.md` (audit record, superseded by v1) |
| **I2** | **`oq_p1_capacity_v0.md` (NEW 2026-04-28; CANDIDATE_RESOLVED_NEGATIVE)**, **`oq_p1_capacity_v0.py` (NEW; M1+M2 cross-check)**, `oq_p1_capacity_v0_run_log.txt` |

## Forward-task placeholders (referenced but not yet written)

These 3 research notes are referenced as forward-task placeholders. Their absence is intentional — the relevant OQ is genuinely open frontier work, not a missing artifact:

- `oq_born_representation_independent_v0.md` — referenced from Q3 §7 (OQ-Born-1: representation-independent Born rule)
- `oq_qsm1_kms_l0_a0c_v0.md` — referenced from Q2 §3 (OQ-QSM1-Refined: KMS as L0 A0c instance, formal embedding)
- `oq_sigma_star_universality_v0.md` — referenced from Q3 §7 (OQ-σ*-1: σ\* universality beyond Gaussian phase noise)

These are **future-task OQ candidates**, not blockers for v1.0 release.

## Today's additions (2026-04-28)

- `oq_p1_capacity_v0.{py,md}` + run log — I2 §4.2 P1 capacity correction (2.18 → 0.40 honest Shannon)
- `oq_oqs2_kraus_l0_bijection_v0.{py,md}` + run log — Q2 §5.3 OQ-OQS2 ESTABLISHED via 定理 5.1
- `oq_algorithmic_f_rational_v1.{py,md}` + run log + audit_v0 — I1 §5.2.1 OQ-Algorithmic-f_rational ESTABLISHED via 定理 5.2
- `c_information_geometry_v0_verify.py` + run log — companion to NEW L1 entry `dependencies/L1_core/c_information_geometry.md` (Theorem 2.1 Fisher-Rao = Arrow 1⁻¹ verification)
