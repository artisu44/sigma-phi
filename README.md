# ΣΦ Publication Bundle v1.0

**Frozen**: 2026-04-28
**Scope**: 10-paper observation-theory series across 3 mathematical fields, with bundled L0/L1 dictionary dependencies + reproducibility supplementary.
**Languages**: each paper provided in both Japanese (`_ja.md`) and English (`_en.md`); all 10 paper headers and prerequisite cross-references are version-synchronised.

## 1. Series structure

The bundle realises a **triple framework header parallel** (NT × Quantum × Information):

```
                    framework header
                   ──────┬─────┬─────┬──────
                         N1    Q1    I1
                         │     │     │
          ζ-core         N2    │     │
          universality   N3    Q2    │
          BSD genuine    N4    │     │
          final closure  N5    Q3    I2
```

| Series | Papers | Field | Closure mechanism |
|---|---|---|---|
| **N (5 papers)** | N1 → N2 → N3 → N4 → N5 | Number theory | Brauer 5-tier failure mode + 8-gauge Origination matrix final closure |
| **Q (3 papers)** | Q1 → Q2 → Q3 | Quantum mechanics | Born-Gleason root closure (Busch-Gleason + dim ≥ 2 + σ\* gauge) |
| **I (2 papers)** | I1 → I2 | Information theory | 5-anchor information limit theorem (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) |

**Triple parallel formal completion**: I2 §9.2 (Claim 9.2). Each framework header (N1, Q1, I1) is an independent specialisation of the Paper D 6-domain triangulation's 3-domain anchor; together they provide universal-validity coverage for observation theory across NT / quantum / information.

## 2. The 10 papers

| # | File | Lang | Version | Title (subtitle) |
|---|---|---|---|---|
| 1 | `nt/N1_observation_theory_nt` | ja+en | v0.7 | NT framework header — S15 trichotomy, Arrow framework, T-AAS, NT-internal triangulation |
| 2 | `nt/N2_paper2_structural` | ja+en | v0.5 | ζ-core structural analysis — Carry / D_floor / Dirichlet residue |
| 3 | `nt/N3_path2_dirichlet_universality` | ja+en | v0.5 | Path 2 NT universality — countably-infinite via modular L + Type α/β/γ trichotomy |
| 4 | `nt/N4_hasseweil_stark` | ja+en | v0.3 | Hasse-Weil L × Stark — weight-2 BSD analytic rank detection (genuine framework transfer) |
| 5 | `nt/N5_brauer_origination` | ja+en | v0.2 | Brauer obstruction theory + 8-gauge Origination matrix — NT-series final closure |
| 6 | `quantum/Q1_observation_theory_quantum` | ja+en | v0.2 | Quantum framework header — 4-class refined Hodge + Arrow framework + T-AAS quantum lift |
| 7 | `quantum/Q2_open_qs_chain` | ja+en | v0.3 | Open QS chain extension — 4-stage cumulative coarse-graining + KMS-FDT-Landauer arc + Lindblad-Kraus L0 bijection (定理 5.1) |
| 8 | `quantum/Q3_born_gleason` | ja+en | v0.2 | Born-Gleason — §4 dual quantum root closure + σ\* = √(2 ln 2) half-amplitude gauge |
| 9 | `information/I1_information_theory_framework` | ja+en | v0.3 | Information framework header — 0/1/2 scaffold lens + 5-anchor information limit + 定理 3.3.1 Renyi parametric scan + 定理 5.2 Algorithmic f_rational |
| 10 | `information/I2_communication_theory` | ja+en | v0.2 | Communication theory 3-tier + 5 novel proposals — I-series final closure (P1 σ\* honest Shannon ≈ 0.40 bits/symbol) |

Total: ~5160 lines (Japanese set) / ~5200 lines (English set).

## 3. Reading order

### First-time readers

The 3 framework headers (N1, Q1, I1) are **independent entry points** — pick the one closest to your background:

- **NT background** → start with **N1**, then proceed N2 → N3 → N4 → N5 in order
- **Quantum background** → start with **Q1**, then Q2 → Q3
- **Information theory / CS background** → start with **I1**, then I2

After completing one series, the cross-domain links surface naturally:
- **N1 ↔ Q1 ↔ I1** triple framework parallel (formalised in I2 §9.2)
- **N3 ↔ Q2** universality extension parallel (Path 2 NT ↔ Open QS chain)
- **N5 ↔ Q3 ↔ I2** final-closure parallel
- **N4 BSD** ↔ **Q3 σ\*** ↔ **I2 P1 channel** — three quantitative closure benchmarks

### Cross-references inside the bundle

Every "see X §Y" pointer either:
- targets a section within the same paper (most common)
- targets another of the 10 papers (always within bundle, version-synced)
- targets a `dependencies/` L0/L1 dictionary file (bundled in §4)
- targets a `supplementary/research/` verification note (bundled in §5)

External (textbook / arXiv / journal) citations are listed in each paper's References section.

## 4. `dependencies/` — bundled L0/L1 dictionary

The 10 papers reference **30 L0/L1 dictionary entries**. All are bundled here for self-contained reading:

```
dependencies/
├── L0_canon/                        (4 files; finite_observation A0-A7 axioms + external_time t/τ separation)
├── L1_core/                         (11 files; Arrow framework, T-AAS, theorems master, etc.)
├── L1_quantum/                      (8 files; Born/POVM, open QS, FDT, Landauer, many-body)
├── L1_nt/                           (6 files; conductor, ζ, Frobenius-Schur, Stark, root numbers, class fields)
└── meta/                            (3 files; OQ master register, physics constants, control theory cross-domain)
```

| Tier | Files | Role |
|---|---|---|
| L0_canon | observation_canon, finite_observation, identity_asymmetry, **external_time** | A0-A7 axioms, S1-S3 identity theorems, t (external window parameter) / τ (internal scan coordinate) separation principle. NT-side currently uses τ-only formulations (no t role); Q-side (Schrödinger evolution, decoherence dynamics) and I-side (rolling-window observation, sequential channel use) load t explicitly — bundled here for cross-series consistency and Q/I forward content. |
| L1_core | c_theorems_master (S12-S17), c_arrow_framework, c_arrow_obstruction (T-AAS + Arrow 1⁻¹), c_arrow_bridge_constants, c_filtration_obstruction (Theorem 4a.1 unified f_rational), c_observation_optimal_gauge, c_information_theory, c_information_geometry (NEW 2026-04-28), c_phase_complex, c_recursive_floor_principle, c_spectral | core mathematical framework |
| L1_quantum | q_quantum_observation, q_quantum_statistical_mechanics, q_open_quantum_systems, q_quantum_thermodynamics, q_many_body_quantum, q_gauge_field_theory, q_fine_structure, q_action_principles | quantum-side L1 |
| L1_nt | nt_conductor, nt_dedekind_artin_zeta, nt_frobenius_schur, nt_genus_class_fields, nt_relative_units, nt_root_numbers | NT-side L1 |
| meta | open_questions_master, physics_constants_decomposition, control_theory | OQ register + 1 L2/L3 reference |

### Note on `zero_one_two_scaffold.md`

I1 §2.3 references this as an L0_canon entry. The current concept is recorded in private memory rather than as a public dictionary file. Treat the reference as a forward placeholder — the formal L0_canon entry will be created as an independent task. All load-bearing content of the 0/1/2 scaffold lens is **inlined** within I1 §2.3, so the reference is informational only.

## 5. `supplementary/research/` — reproducibility supplementary

26 research notes, verification scripts, and clean run logs. Reproduces all "X/Y PASS" / "ESTABLISHED" claims. Index at [`supplementary/research/INDEX.md`](supplementary/research/INDEX.md).

3 research-note placeholders are referenced but **not yet written** (forward-task OQs):
- `oq_born_representation_independent_v0.md` — Q3 §7 OQ-Born-1
- `oq_qsm1_kms_l0_a0c_v0.md` — Q2 §3 OQ-QSM1-Refined
- `oq_sigma_star_universality_v0.md` — Q3 §7 OQ-σ\*-1

These represent open frontier work and do not block v1.0 release.

## 6. Status (frozen 2026-04-28)

All 10 papers are headed `Status: DRAFT`. For this v1.0 freeze, **the content is considered ESTABLISHED at the dictionary residence level**; the DRAFT label in the paper headers reflects the framework's ongoing-revision posture, not unfinished content. Each paper's main results have:

- Status row at the top of §1 / §2 / etc. marking individual claims as `ESTABLISHED` / `candidate_v1` / `proposed`
- Numerical or formal verification cited (per `supplementary/research/`)
- Cross-arrow consistency at log₂-bit unit (Theorem 4a.1 `c_filtration_obstruction.md §8.5`)

## 7. Open frontier (intentional, non-blocking)

Each series has `Open frontier` sections (`§7.4` / `§8.3` / similar) listing future-task OQs. Examples:

- **NT**: OQ-NT-7/8 Brauer 5-tier completeness + 8-gauge new signature for weight-2; OQ-Tier3-Plus-Search; OQ-433a1-Outlier
- **Q**: Q-series future Q4 (quantum 8-gauge specialisation), Q5 (QFT extension), Q6 (gravity); Conjecture 4a.2 depth parallel quantitative form
- **I**: OQ-I-Bekenstein-Extension (gravity/relativistic 6th anchor); OQ-S17-Density-Form-Universal; OQ-Alg-MDL/Hodge/Quantum cross-links; OQ-IG-1 to OQ-IG-Paper-Readiness (5 OQs spawned by today's `c_information_geometry.md` L1 expansion)

These are **intentionally open** and recorded in `dependencies/meta/open_questions_master.md` for forward tracking.

## 8. Reproducibility & verification

| Claim | Verification artifact |
|---|---|
| S17 e-extremum (Arrow 3) | `supplementary/research/oq_omega_obs_3_info_density_check.py` (5/5 gate PASS) |
| 4-class refined Hodge | `supplementary/research/oq_omega_obs_4a_monotone_verify.py` |
| Schumann v1 Path 2 | `supplementary/research/schumann_path2_check.py` |
| Lindblad-Kraus L0 bijection (Q2 §5.3 定理 5.1) | `supplementary/research/oq_oqs2_kraus_l0_bijection_v0.{py,md}` (3/3 PASS) |
| Algorithmic f_rational (I1 §5.2.1 定理 5.2) | `supplementary/research/oq_algorithmic_f_rational_v1.{py,md}` (7/7 PASS) |
| P1 honest Shannon capacity (I2 §4.2) | `supplementary/research/oq_p1_capacity_v0.{py,md}` (M1+M2 cross-check, 1.7e-4 bits agreement) |
| Fisher-Rao = Arrow 1⁻¹ (`c_information_geometry.md` §2 Theorem 2.1) | `supplementary/research/c_information_geometry_v0_verify.py` (3/3 PASS) |

All scripts are Python 3 + numpy/scipy. Run from the bundle root or supplementary/research/ folder.

## 9. Citation

When citing this bundle:
```
ΣΦ Publication Bundle v1.0 (frozen 2026-04-28)
10 papers across NT / Quantum / Information observation theory
+ bundled L0/L1 dictionary + reproducibility supplementary
```

For citing individual papers, use the paper file path + version (e.g., `papers/publication/quantum/Q3_born_gleason_ja.md v0.2`).

## 10. Audit trail

This bundle was prepared via a release-readiness audit pass (Phase A-D) on 2026-04-28. The audit report `RELEASE_READINESS_AUDIT.md` (in this folder) documents:

- 14 metadata sync fixes applied (Phase A)
- 30 dict + 24 research dependency files copied (Phase B)
- this README + `supplementary/research/INDEX.md` written (Phase C)
- final verification grep (Phase D, no remaining stale refs)

The audit confirmed: zero content blockers, all "TODO" markers are intentional open-frontier flags, and the 10-paper set forms an internally consistent and reproducibility-supported collection.
