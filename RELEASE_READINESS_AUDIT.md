---
status: AUDIT (recommendations only, no edits applied)
date: 2026-04-28
scope: 10 papers (N1-N5 / Q1-Q3 / I1-I2) × 2 languages (_ja / _en) = 20 markdown files
goal: Light release-readiness audit + internal-completion strategy
---

# Release-Readiness Audit — N1-N5 / Q1-Q3 / I1-I2

## 1. Headline

**Verdict**: ready for release **after a metadata sync pass**. No content blockers; all "TODO" markers are intentional open frontiers (already labelled). Internal-completion strategy is **bundle the dependency files** rather than inline them (Light approach).

**Total stale items**: ~14 metadata fixes (4 _ja header version + 7 _ja cross-refs + 3 _en cross-refs).
**Total external dependencies**: 30 dictionary files + 24 research files referenced.
**Critical "must bundle" set**: 9 dict files (top dependency tier, ≥5 paper refs).

---

## 2. Paper-by-paper roster

| # | Paper | _ja | _en | _ja lines | _en lines | Status |
|---|---|---|---|---|---|---|
| 1 | N1 Observation Theory — NT version | v0.7 ✓ | v0.7 | 663 | 669 | ESTABLISHED content |
| 2 | N2 Paper 2 Structural (ζ-core) | v0.5 ✓ | v0.5 | 565 | 567 | ESTABLISHED content |
| 3 | N3 Path 2 Dirichlet Universality | **v0.4 ✗** | v0.5 | 449 | 451 | _ja header stale |
| 4 | N4 Hasse-Weil + Stark | v0.3 ✓ | v0.3 | 492 | 498 | ESTABLISHED content |
| 5 | N5 Brauer + Origination 8-gauge | v0.2 ✓ | v0.2 | 416 | 421 | ESTABLISHED content |
| 6 | Q1 Observation Theory — quantum | v0.2 ✓ | v0.2 | 595 | 597 | ESTABLISHED content |
| 7 | Q2 Open QS chain | **v0.2 ✗** | v0.3 | 349 | 349 | _ja header stale |
| 8 | Q3 Born-Gleason + σ\* | v0.2 ✓ | v0.2 | 395 | 397 | ESTABLISHED content |
| 9 | I1 Information framework + 5-anchor | **v0.1 ✗** | v0.3 | 618 | 629 | _ja header stale |
| 10 | I2 Communication theory + 5 proposals | **v0.1 ✗** | v0.2 | 619 | 621 | _ja header stale |

Paper sizes: ~349-669 lines per file. Total ~5160 lines (_ja) + ~5200 lines (_en) = ~10360 lines for the 10-paper set.

All 10 papers currently carry `Status: DRAFT` in the header. For release, recommend upgrading to `Status: RELEASE v1.0 (frozen 2026-04-28)` or similar.

---

## 3. Stale metadata findings (mechanical fixes, ~30 min)

### 3.1 _ja header **Version** field (4 fixes)

| paper | current | should be |
|---|---|---|
| `N3_path2_dirichlet_universality_ja.md` line 5 | `v0.4 (2026-04-27)` | `v0.5 (Type γ formal definition + v1.5 task split, 2026-04-28)` |
| `Q2_open_qs_chain_ja.md` line 5 | `v0.2 (compact, 2026-04-27)` | `v0.3 (OQ-OQS2 ESTABLISHED + 定理 5.1 Lindblad-Kraus L0 bijection, 2026-04-28)` |
| `I1_information_theory_framework_ja.md` line 5 | `v0.1 (initial Information-only draft, 2026-04-27)` | `v0.3 (Algorithmic-f_rational ESTABLISHED + 定理 5.2; Renyi 定理 3.3.1; S17-Codebook docs fix; 2026-04-28)` |
| `I2_communication_theory_ja.md` line 5 | `v0.1 (initial Information-only draft, 2026-04-27)` | `v0.2 (P1 capacity correction: 2.18 → 0.40 bits/symbol honest Shannon, 2026-04-28)` |

**Cause**: today's `_en` headers were updated (per user's earlier metadata-sync request) but the `_ja` parallel updates were missed.

### 3.2 _ja cross-paper version refs (~10 fixes)

| paper | location | current | should be |
|---|---|---|---|
| N2_ja line 6 | `前提 (framework)` | `N1 v0.3` | `N1 v0.7` |
| N3_ja line 6 | `前提 (framework)` | `N1 v0.4 / N2 v0.2` | `N1 v0.7 / N2 v0.5` |
| N4_ja line 6 | `前提 (framework)` | `N1 v0.5 / N2 v0.3 / N3 v0.2` | `N1 v0.7 / N2 v0.5 / N3 v0.5` |
| N5_ja line 6 | `前提 (framework)` | `N1 v0.6 / N2 v0.4 / N3 v0.3 / N4 v0.2` | `N1 v0.7 / N2 v0.5 / N3 v0.5 / N4 v0.3` |
| Q2_ja line 11 | `N parallel` | `N3 v0.4` | `N3 v0.5` |
| Q3_ja `前提 (Q1, Q2)` | inline | `Q2 v0.2` | `Q2 v0.3` |
| I2_ja `前提 (I1)` | inline | `I1 v0.1` | `I1 v0.3` |

### 3.3 _en cross-paper version refs (~3 fixes)

| paper | current | should be |
|---|---|---|
| N4_en line 6 | `N3 v0.4` | `N3 v0.5` |
| N5_en line 6 | `N3 v0.4` | `N3 v0.5` |
| Q3_en | `Q2 v0.2` | `Q2 v0.3` |

### 3.4 DRAFT → RELEASE status flag (10 papers)

Each paper currently states `Status: DRAFT`. For a v1.0 release freeze, recommend changing to:
```
**Status (Japanese)**: RELEASE v1.0 (frozen 2026-04-28; series closure ESTABLISHED)
**Status (English)**: RELEASE v1.0 (frozen 2026-04-28; series closure ESTABLISHED)
```

This is a release-discipline statement, not a content change. The user can choose to keep DRAFT instead if continued revision is expected.

---

## 4. Dependency map (for internal-completion bundling)

### 4.1 Critical-tier dictionary files (≥5 paper references — must bundle)

| File | Refs by | Role |
|---|---|---|
| `c_theorems_master.md` | 10 | S12-S17 master theorem table |
| `c_observation_optimal_gauge.md` | 8 | optimal gauge theorem residence |
| `c_arrow_framework.md` | 7 | 3-Arrow theory body |
| `observation_canon.md` | 6 | L0 canon entry |
| `identity_asymmetry.md` | 6 | identity theorems S1-S3 |
| `finite_observation.md` | 6 | A0-A7 axioms (L0 root) |
| `c_filtration_obstruction.md` | 6 | Hodge / Theorem 4a.1 unified f_rational |
| `q_quantum_observation.md` | 5 | Born / Busch-Gleason / σ\* |
| `c_information_theory.md` | 5 | Shannon + 5-strand + Fisher §6 |

→ **9 critical files**. Without these, the 10-paper set cannot be read self-contained.

### 4.2 Medium-tier (3-4 refs — recommended to bundle)

`nt_root_numbers.md` (4) / `c_arrow_bridge_constants.md` (4) / `q_quantum_statistical_mechanics.md` (3) / `q_open_quantum_systems.md` (3) / `nt_relative_units.md` (3) / `nt_frobenius_schur.md` (3) / `nt_dedekind_artin_zeta.md` (3) — **7 files**.

### 4.3 Domain-specific (1-2 refs — optional bundle)

`nt_genus_class_fields.md` (2) / `c_recursive_floor_principle.md` (2) / `zero_one_two_scaffold.md` (1) / `q_quantum_thermodynamics.md` (1) / `q_many_body_quantum.md` (1) / `q_gauge_field_theory.md` (1) / `q_fine_structure.md` (1) / `q_action_principles.md` (1) / `physics_constants_decomposition.md` (1) / `c_spectral.md` (1) / `c_control_theory.md` (1) / `nt_conductor.md` (1, also referenced by N1 indirectly) — **~13 files**.

Note: `c_information_geometry.md` (NEW today) not yet referenced by any of the 10 papers; it lives as forward-task L1 entry.

### 4.4 Research files (24 referenced)

Verification scripts + OQ research notes. Can go in `supplementary/research/` folder. Reproducibility evidence.

### 4.5 Within-bundle cross-references

The 10 papers reference **each other** extensively:
- N2/3/4/5 chain: each cites prior papers
- Q1 → Q2 → Q3 chain: each cites prior
- I1 → I2: I2 explicitly extends I1
- Cross-domain: I1 ↔ N1 ↔ Q1 triple framework parallel; N3 ↔ Q2 (universality extensions); N5 ↔ Q3 ↔ I2 (final closures)

These within-bundle refs are valid and will work if the bundle is shipped together.

---

## 5. Internal-completion strategy: **bundle, don't inline**

### Recommended structure

```
sigmaphi-publication-v1.0/
├── README.md                         ← master index (NEW, see §6)
├── papers/
│   ├── nt/
│   │   ├── N1_observation_theory_nt_{ja,en}.md
│   │   ├── N2_paper2_structural_{ja,en}.md
│   │   ├── N3_path2_dirichlet_universality_{ja,en}.md
│   │   ├── N4_hasseweil_stark_{ja,en}.md
│   │   └── N5_brauer_origination_{ja,en}.md
│   ├── quantum/
│   │   ├── Q1_observation_theory_quantum_{ja,en}.md
│   │   ├── Q2_open_qs_chain_{ja,en}.md
│   │   └── Q3_born_gleason_{ja,en}.md
│   └── information/
│       ├── I1_information_theory_framework_{ja,en}.md
│       └── I2_communication_theory_{ja,en}.md
├── dependencies/
│   ├── L0_canon/
│   │   ├── observation_canon.md
│   │   ├── finite_observation.md
│   │   ├── identity_asymmetry.md
│   │   └── zero_one_two_scaffold.md  (if exists)
│   ├── L1_mathematical/core/
│   │   ├── c_theorems_master.md
│   │   ├── c_arrow_framework.md
│   │   ├── c_arrow_obstruction.md
│   │   ├── c_arrow_bridge_constants.md
│   │   ├── c_filtration_obstruction.md
│   │   ├── c_observation_optimal_gauge.md
│   │   ├── c_information_theory.md
│   │   ├── c_recursive_floor_principle.md
│   │   └── c_spectral.md
│   ├── L1_mathematical/quantum/
│   │   ├── q_quantum_observation.md
│   │   ├── q_quantum_statistical_mechanics.md
│   │   ├── q_open_quantum_systems.md
│   │   ├── q_quantum_thermodynamics.md
│   │   ├── q_many_body_quantum.md
│   │   ├── q_gauge_field_theory.md
│   │   ├── q_fine_structure.md
│   │   └── q_action_principles.md
│   └── L1_mathematical/number_theory/
│       ├── nt_conductor.md
│       ├── nt_dedekind_artin_zeta.md
│       ├── nt_frobenius_schur.md
│       ├── nt_genus_class_fields.md
│       ├── nt_relative_units.md
│       └── nt_root_numbers.md
└── supplementary/
    └── research/
        ├── (24 referenced research notes + scripts)
        └── INDEX.md (which paper references what)
```

This packaging makes the 10-paper set **internally self-contained** without inlining or rewriting any content. ~30 dict files + 24 research files copied. No content additions.

### Alternative (rejected for Light scope)

A "Foundations Preamble" paper that inlines critical L0 + L1 content (e.g., `P0_foundations`) — requires writing a new paper or significantly expanding N1/Q1/I1. Heavy. Defer to next cycle if external academic publication is decided.

---

## 6. Master README (NEW deliverable)

A `papers/publication/README.md` (or top-level `RELEASE_INDEX.md` if bundling) is recommended. Suggested contents:

```markdown
# ΣΦ Publication Bundle v1.0 (2026-04-28)

10-paper observation-theory series in 3 mathematical fields:
- **NT (5 papers)**: framework header → ζ-core → Path 2 universality → Hasse-Weil BSD → Brauer + 8-gauge final
- **Quantum (3 papers)**: framework header → Open QS extension → Born-Gleason + σ\* root closure
- **Information (2 papers)**: framework header + 5-anchor → communication theory + 5 novel proposals

## Reading order (recommended)

For first-time readers:
1. Start with N1 (or Q1, or I1) depending on background
2. The 3 framework headers (N1, Q1, I1) are independent — pick one
3. Within each series, papers are linear: N1→N2→...→N5
4. Cross-series links: I1 ↔ N1 ↔ Q1 (triple framework parallel, formalised in I2 §9.2)

## Dependencies

- Self-contained reading: see `dependencies/` folder
- Verification scripts: see `supplementary/research/`

## Status

ESTABLISHED 2026-04-28. 10-paper minimum closure achieved:
- NT series N1-N5: Brauer 5-tier + 8-gauge final closure
- Quantum series Q1-Q3: Born + Gleason + σ\* foundational closure
- Information series I1-I2: 5-anchor information limit theorem + 3-tier communication theory
- **Triple framework parallel** (I2 §9.2): 3-domain anchor for observation theory universal validity
```

---

## 7. Open frontier (intentional, non-blocking)

3 explicit TBD markers — all labelled future work, not release blockers:
- N3_ja line 99: "未確認 candidate ... TBD (v1.5 expansion task)" — Type γ involution sub-family, recorded as v1.5 promotion
- N5_ja line 315-316: "TBD" for higher-weight modular L + Hecke L extensions, both labelled as forward tasks (N3 §3.3 forward / N5 §3 + Q forward)

These belong to the framework's **ongoing research frontier** and are appropriately labelled. They do not block release of v1.0.

---

## 8. Action checklist (for release v1.0)

Estimated 1.5 sessions total.

- [ ] **Phase A — Metadata sync** (~30 min, mechanical)
  - [ ] 4 _ja header Version field updates (§3.1)
  - [ ] ~7 _ja cross-paper version ref updates (§3.2)
  - [ ] ~3 _en cross-paper version ref updates (§3.3)
  - [ ] (optional) 10 papers: DRAFT → RELEASE v1.0 status flag (§3.4)

- [ ] **Phase B — Bundle assembly** (~45 min)
  - [ ] Create `dependencies/` folder structure (§5)
  - [ ] Copy 9 critical + 7 medium L1 dict files
  - [ ] Optionally include 13 domain-specific files
  - [ ] Create `supplementary/research/INDEX.md` mapping research → paper

- [ ] **Phase C — Master index** (~15 min)
  - [ ] Write `papers/publication/README.md` per §6 template
  - [ ] (optional) Reading-order guide
  - [ ] (optional) ASCII diagram of paper dependencies

- [ ] **Phase D — Final validation** (~15 min)
  - [ ] Re-run audit grep to confirm zero stale refs
  - [ ] Verify all bundled dependency files actually exist
  - [ ] git tag `publication-v1.0` (if version-controlled)

After Phase A-D: release-ready artifact is `sigmaphi-publication-v1.0/` directory tree.

---

## 9. Out of scope for this audit (explicit deferral)

- **Heavy "inline self-contained" variants** of each paper (Paper D-S style). Defer to next cycle if external academic peer review is decided as target.
- **Bibliography expansion**: each paper currently has a "References" or "References (ΣΦ internal)" section but external citation list is sparse. For external publication targets, would need standardised bibliography pass per paper. Defer.
- **Figure / diagram additions**: papers currently text-only. Diagram-rich version would be a separate visualisation pass. Defer.
- **English/Japanese content parity sweep**: file lengths agree within ~5% across all 10 papers, suggesting parity, but full content diff is out of scope for this audit. Spot-checked structural elements (theorem numbering, status changes) are consistent.
- **Paper Ω, Paper D, Paper E, Paper F**: not in the 10-paper closure set; separate publication track if desired.

---

## 10. Recommendation

**Apply Phase A** (metadata sync, ~30 min, all 14 fixes mechanical) **immediately** to remove inconsistencies. After Phase A, the 10 papers form an internally consistent set.

**Phase B + C** (bundle + README) **as a single ~1 hour commit** — that produces a self-contained `publication-v1.0/` directory.

**Phase D** is housekeeping after the above.

After this audit, no further "膨らみ" is expected — release is mostly mechanical packaging of already-completed work.
