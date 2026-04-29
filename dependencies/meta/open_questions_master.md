---
axis: meta
position: oq_index
updated: 2026-04-25 evening late (**v1.5 v2 v8 + Priority 1 + 3rd review correction**: 3rd external review round で **rank-mislabel hypothesis を REJECT** — external evidence (PARI forell docs, Sage worksheets) が 433a1 = rank 2 を支持するため、私の "433a1 actually rank 0" 仮説は premature/wrong。Diagnostic |Λ(1+εi, E)| 比較で **389a1 rank 2 → |Λ| ∝ ε² (signature perfect)、11a1 rank 0 → |Λ| const、433a1 → |Λ| const ≈ 10.86 (rank 0 signature, but external says rank 2)**。**AFE itself works correctly** (389a1 rank 2 perfect). 結論: **433a1 case は私の input data implementation bug** (Weierstrass equation likely incorrect for true LMFDB 433a1)、framework failure ではない。Methodology lesson: **input data verification against external DB (LMFDB) は test 前に mandatory**。Prior **v1.5 v2 v8 + Priority 1 — calibrated wording per 2nd external review + 433a1 deep dive identifies rank-mislabel hypothesis**: 2nd reviewer round で v2 v8 "GENUINE confirmed" wording を careful form に calibrate — "K-signal not exp-cutoff artifact (substantial advance)" + "two-implementation internal cross-check, not external library" + "433a1 outlier unresolved"。Priority 1 (433a1 deep dive at small t {0.01-0.5}, AFE-based, mp.dps=30) で **K_E(t) → 1.30 constant as t → 0**, K·t² fits 0 + 1.32·t² (R²=0.99998 linear)。これは **rank 0 signature**, NOT rank 2 (私の prior assignment 誤りの可能性極大)。LMFDB verification needed — もし 433a1 actually rank 0 なら **10/10 curves match prediction with corrected ranks**, "outlier" was rank-mislabel artifact。Framework signal **MORE robust than v2 v8 first reading**。**Methodology lesson**: input rank labels need independent (LMFDB) verification、cannot assume from memory。**17-stage progression**, NEW v2 v9 = LMFDB verification + direct K formula + external library。Prior **v1.5 v2 v8 proper Iwaniec-Kowalski AFE cross-check**: 10 curves spanning rank 0/1/2/3 で proper AFE 経由 K_E(0.3)·(0.3)² → r prediction が **9/10 curves で 5% 以内 agreement** (incl. rank 3: 5077a1 K·t²=3.09 vs predicted 3 — AFE が v2 v7 smoothed の boundary issues を fix); 433a1 outlier (K·t²=0.12) は curve-specific Taylor coefficients (small c_2) で説明、methodology issue ではない。**Functional eq satisfied to machine precision** (|Λ(s)|/|Λ(2-s)| = 1.000000 exact)。**AFE vs smoothed median |diff| = 0.025** (excellent agreement for 8 non-outlier curves)。**Framework BSD rank detection is theoretically grounded + library-grade verified** — strongest claim possible at this scope。**16-stage progression**, v2 arc from "exploratory pattern (retracted post-review)" → "library-grade verified BSD rank detection signal"。Reviewer's external review process (Phase 5) demonstrably critical for framework claim upgrading。Prior **v1.5 v2 v7 K_E(t) curvature observable test — reviewer's Taylor prediction K(t)·t² → r EMPIRICALLY VERIFIED for rank 0/1/2 (8/10 curves)**: External AI review (per `oq_omega5_v15_v2_arc_external_review_response_2026_04_25.md`) で σ_min observable は smoothing artifact 可能性指摘 + alternative observable K_E(t) := ∂²_σ log|Λ(E, σ+it)|_{σ=1} 提案 + Taylor prediction K_E(t) ≈ r/t² + O(1) を提示。v2 v7 で smoothed implementation で test、**at t=0.3 quantitative agreement**: rank 0 K·t² ≈ 0.024-0.031, rank 1 K·t² ≈ 0.984-0.990, rank 2 (389a1) K·t² ≈ 2.032 — **prediction empirically verified** for 8 curves。Auto-verdict misled by gate at t=0.1 (finite-diff h/t=0.5 too large)、Phase 3 catch on gate-design = v2 v7 lesson。**Framework BSD rank detection now theoretically grounded** via Taylor expansion at s=1。**15-stage progression**, NEW v2 v8 = library cross-check (SageMath/PARI exact L-function) で smoothing-mediated か genuine signal か最終確認。Prior **v1.5 v2 v6 conductor-adaptive smoothing CONFIRMED rank detection extending to rank 2/3**: 3 refinements (X(t, N_E) := X_base·√(N_E/32) + X_slope·|t| conductor-adaptive smoothing + σ_min ∈ [0.5, 1.5] sanity gate + direct argmin instead of parabolic fit) で v2 v5 rank 2/3 numerical breakdown を fix。**G_san 10/10**, **G1-G5 ALL PASS**, mean amplitude rank 0/1/2 monotone (0.07 < 0.14 < 0.435)。**Binary rank detection ROBUST CONFIRMED** across 10 curves spanning 4 rank classes、conductor range 11-5077。**Quantitative amplitude scaling rank 0/1/2 confirmed**、rank 3 inconclusive (n=1 + σ-grid boundary clipping at t=5)。**Framework's first quantitative non-trivial predictive content empirically established**: BSD rank detection via σ_min(t) trajectory amplitude in Hasse-Weil L domain。**14-stage progression**, NEW v2 v7 = σ-grid extension to [0.3, 1.9] + more rank-3+ samples for full quantitative ordering。Prior **v1.5 v2 v5 rank amplitude refined hypothesis test**: 10 curves spanning rank 0/1/2/3 で v2 v4 amplitude pattern を multi-rank robust test。**Rank 0 vs rank 1 amplitude separation ROBUST CONFIRMED** (4 rank-0 A∈[0.040, 0.048] vs 3 rank-1 A∈[0.178, 0.424], cluster gap 0.130, separation factor 4-9×)。**BUT Phase 3 audit catches rank 2/3 numerical breakdown**: 389a1/433a1/5077a1 で σ_min が non-physical values (-0.87, +13.08, -5.69 etc) — parabolic fit garbage from insufficient smoothing at high conductor。**G6 monotone amplitude scaling claim REJECTED as artifact-amplified**。**Framework BSD rank detection (binary rank≥1 vs rank 0) empirically established** — first non-trivial predictive content beyond functional-eq identity confirmed multi-curve robust。**13-stage progression**, NEW v2 v6 = conductor-adaptive smoothing X(t, N_E) for proper rank 2/3 numerics + σ_min sanity gate。Prior **v1.5 v2 v4 rank universality test: NAIVE rank-displacement REJECTED + NEW σ_min(t) oscillation amplitude pattern DISCOVERED**: 6 non-CM curves (3 rank-0 + 3 rank-1) で v2 v3 の "37a1 σ_min displacement at small t" hypothesis を test。Pre-registered G2 1/6 FAIL (53a1 rank-1 shows NO displacement at t=0.5 — refutes naive single-t hypothesis); G5 separation 0.147 borderline。**Post-execution discovery**: σ_min(t) **oscillation amplitude** (max_t - min_t across t-grid) IS rank-discriminating: rank-0 amplitude ∈ [0.028, 0.048] (all ≤ 0.05), rank-1 amplitude ∈ [0.164, 0.319] (all ≥ 0.16) — **clean cluster separation factor 3-6×**。Framework detects rank via **multi-t trajectory amplitude**, NOT single-t displacement。**This is genuine non-trivial predictive content** (refines v2 v3 single-curve finding to multi-curve robust signal)。**12-stage progression**, NEW v2 v5 = refined hypothesis test (more curves, finer t-grid)。Prior **v1.5 v2 v3 conductor universality CONFIRMED at t≥5 + UNEXPECTED rank-1 BSD effect**: 4 non-CM curves {11a1, 14a1, 17a1, 37a1} (conductor 11/14/17/37, rank 0/0/0/1) で G2 cross-curve consistency 21/24 PASS (gate ≥20) — **t=5,10,15 で 18/18 PERFECT** = class phenomenon empirically established; **t=0.5 で 37a1 (rank 1) outlier σ_min=0.749** — L(1, 37a1) = 0 (BSD critical zero) が σ_min を displacement する unexpected positive finding (framework empirically detects rank ≥ 1)。G1 per-curve 12/12 PASS、G4 16/16 PASS。G3 functional eq conductor-dependent degradation (X(t) tuning issue, NOT framework)、G5 bookkeeping error (LMFDB memory wrong for 14a1/17a1 expected values)。**11-stage progression**, **NEW direction**: rank universality test for σ_min-vs-rank quantitative relationship。Prior v2 v2 **v1.5 v2 v2 Hasse-Weil L t-adaptive smoothing CONFIRMED via 11a1 non-CM + PARTIAL for 32a1 CM**: t-adaptive X(t)=50+30|t| で CM 32a1 σ_min at t=10 改善 0.79 → 0.95、**非-CM 11a1 全 4 gates pass** (G1 6/8, G2 3/3, G3 4/4 perfect, G4 4/4); 32a1 CM は G1 4/8 still partial (CM 特有 half-density a_p 構造 artifact at large t)。**G3 CM vs non-CM consistency 4/4 PERFECT**。Phase 4 X_slope sweep monotone → 1 (0.963 → 0.975 → 0.986)。**Framework extension for weight-2 Hasse-Weil L established via non-CM curves** (10-stage progression)。Prior v2 v1 **v1.5 v2 v1 Hasse-Weil L smoothed + non-CM PARTIAL_CONFIRMED strengthened**: dual refinement (smoothed truncation + non-CM curve 11a1) で σ_min precision 大幅 improvement (1.38 → 1.02 at t=0.5, 1.11 → 0.94 at t=5), Phase 4 X-sweep で σ_min → 1 convergence empirically confirmed (0.86 → 0.94 → 0.97), **G3 CM vs non-CM consistency 2/3 PASS** (framework NOT CM-specific)。Unified weight-class structural fit for Dirichlet L (weight 1) + Hasse-Weil L (weight 2, CM+non-CM 両方) 全面 confirmed。G1 remaining partial fail は t-adaptive smoothing の未実装 (X=100 fixed で large-t 対応不可, v2 v2 refinement)。Prior v2 v0 **v1.5 v2 v0 Hasse-Weil L CM curve PARTIAL_CONFIRMED**: 第二候補 pivot execution, E: y²=x³-x (Cremona 32a1, CM by Z[i]) で framework weight-shift adaptability 確認 — Fix(σ_D) center shifts 0.5 → 1 (weight 1 → weight 2), σ_min ≈ 1.10-1.12 at t=5,10 (close to predicted s=1), weight-class differentiation 3/3 confirmed。**G1 functional eq ratio FAIL** は L-series truncation artifact (NOT framework failure, v2 v1 approximate functional eq implementation 要)。**Unified framework scope across weight classes** (Dirichlet L weight 1 + Hasse-Weil L weight 2 両方 "structural fit" with weight-adaptive Fix pinning) = positive information gain of pivot。Paper C uniqueness still preserved (all naive extensions remain "structural fit" level)。4-phase rule: 8-stage operationally stress-tested。Prior 2026-04-25 late: **v1b v1 multi-gap N-sweep REJECTED + G3 gap universality byproduct**: Paper D v0.9.2 frozen維持 (backport policy で scope verdict change blocked)、extension log 側 sync のみ。**Critical retrospective**: v1b v0 "Paper C (log N)² dimensional match" claim was single-N coincidence — v1b v1 N-sweep revealed c/⟨log p⟩² is N-dependent (0.46 → 0.67 → 1.02 → 1.63, not constant), σ_min drifts 0.51 → 0.59 away from 0.5 with N increase, R² degrades 0.98 → 0.78 — Taylor residual construction is NOT the right Paper C D_floor analog (missing multi-parameter fit N-dependent prefactor absorption). **Positive byproduct**: G3 gap-class universality 12/12 PASS (Paper C multi-gap invariance pattern does hold structurally on Dirichlet L side). Paper C uniqueness **preserved more strongly** (naive extension paths failed twice: v1a |L|², v1b Taylor residual). v1b v2 = proper multi-parameter fit construction = dedicated future work (non-trivial theoretical implementation). Prior 2026-04-25: Paper D v0.9.2 FROZEN-INTERNAL (F1-F6 completed) + OQ-Ω5e v1b v0 prime sum diagnostic CONFIRMED-at-single-N (now retrospectively reframed as construction-caveat + single-N artifact). Prior same-day v1a REJECTION: **OQ-Ω5e v1.5 v1a 2-quantity coincide test REJECTED** (pre-registered rejection criterion met, G2 17.5% vs ≥70% threshold): |L(σ+it, χ)|² σ_min systematically deviates 0.60-0.82 from 0.5 across 5 complex χ、Paper C-style 2-quantity independent coincide は Dirichlet L via naive |L|² path で成立せず empirically confirmed。Root cause: |L|² = |Λ|² / ((q/π)^{σ+a} · |Γ((s+a)/2)|²) の denominator が strongly σ-growing ⟹ |L|² σ_min は σ-high direction に push、0.5 center unwarranted。**Dirichlet L extension scope definitively closed as "structural fit only"** — post-SC4 scope reassessment empirically confirmed。Genuine v1b path = Paper C D_floor proper analog construction (gap-indexed χ-weighted prime sum residual) が separate future work。Prior: **OQ-Ω5e v1.5 v1 off-axis 2D scan INCONCLUSIVE with SC4 catch** (universal σ-symmetry chain via functional eq + complex conj on complex s); **v1.5 v0 complex extension CONFIRMED with SC3 catch**; **H2 + H3 5-task day**。**SC1-SC4 + v1a clean REJECTION = 2026-04-24 同日 5 stage progression demonstrating feedback rule 3-phase operation + rigorous pre-registration discipline**。Prior 2026-04-23: OQ-L0-refinement v1 + S17 + OQ-Ω-Obs-4a ESTABLISHED triple。Prior 2026-04-20: OQ-FX22/23 closure.)
---

# Open Questions (all layers)

## HIGH priority

### OQ-PT-1: ν の N 依存性 a ∝ 1/l → **MOSTLY RESOLVED**
2メカニズム統一: (1) cross-l k系列 interlace + (2) intra-l (2l+1)² 多重項。p/d/f err<0.07。s残差+0.35（内殻励起）。
→ 詳細は下の「Periodic Table S16 OQ」セクション参照

## MEDIUM priority

### OQ-BETA-SERIES: β(n)=1+1/n Diophantine 系列 (L1, 2026-04-12→04-13 update)

**問い**: Type I β は Dirichlet 同時近似 β(n)=1+1/n で索引されるか?
**Status**: Milestone 2,3 RESOLVED → **LOW に格下げ推奨**

**Milestone 更新 (2026-04-13)**:
1. n=2 sharp constant → **BLOCKED (math frontier)**. Davenport-Schmidt (1970s) 以降未解決。Cusick (1983) 下界のみ。
2. Series A/B 独立性 → **RESOLVED**. β=0 (Landauer) は非Diophantine。Type I = Series A ∪ Series B。
3. β(n) 系列完全性 → **RESOLVED**. Series B は β∈(1,2] のみ。β>2 の自然候補なし。
4. κ ↔ RFP Level 対応 → **DEFERRED** (κ(2) exact 未知)。

**文献 chain**: Davenport (1952)→Cassels (1957)→Davenport-Schmidt (1969)→Cusick (1983)→Basalov (recent)。
**Axis**: A, B
**Residence**: c_recursive_floor_principle.md §6.4-6.5
**Depends on**: Type I/II 分離 (§6.2, ESTABLISHED)

### OQ-KAPPA-LIMIT: κ(2) exact + n 依存性 (L1, 2026-04-12→04-13 major update)

**問い**: κ(n) は n に対してどう振る舞うか? κ(2) の exact value は?
**Status**: 合流仮説 (κ→1/2) **REJECTED**. κ は n で **減少**. κ(2) 精密化進行中。

**確定知見 (2026-04-12)**:
1. κ(1) = 1/√5 = 0.4472 (exact, CF Vieta 保証)
2. κ(2) < κ(1): metric ratio r = 0.9994 < 1
3. Model B: REJECTED (方向逆)
4. 1D/2D 非対称性: CF Vieta (積=-1) → exact. JP にはこの保証なし

**新知見 (2026-04-13, §6.7)**:
5. κ(2) = 0.43292 (q=692,045, float64 最終 record)
6. Aitken 外挿: L ≈ 0.43279
7. **最近接代数候補: √3/4 ≈ 0.43301** (誤差 9.2×10⁻⁵)
8. q-record 成長率 = 20.4426 (安定, 代数的同定 OPEN)
9. Regulator R = 0.5255; log(growth)/R = 5.743 (non-integer)
10. Δ=49 worst confirmed (他 cubic: Δ=81→κ=0.347, Δ=169→κ=0.309, Δ=229→κ=0.189)
11. Pair (α₁,α₂) = Pair (α₂,α₃) 対称性

**BLOCKED on**: float64 精度限界。mpmath で q≤10⁸ スキャン必要。
**残 OQ**: κ(2) exact (√3/4?), growth rate 代数的正体, κ(n→∞) 漸近
**Axis**: A, B
**Residence**: c_recursive_floor_principle.md §6.4-6.7
**Depends on**: OQ-BETA-SERIES, Schmidt (1969), mpmath

## LOW priority

### OQ-T8-residual → **CLOSED** (2026-04-13)

**判定**: 3 milestone 全 falsified, measurable target ゼロ → **CLOSE**。
c_s²=1/2 は T1 parity で存続。exp(-c_s²·k) の observable application は全滅。
再開条件: D_floor の codim 依存性が明確化した場合のみ。
Legacy: research/t8_redefinition_draft_v0.md

## Millennium-class exercises 窶・COMPLETE

### OQ-HC-1: Arrow 1 蜈ｨ蟆・ｧ髦ｻ螳ｳ谿句ｷｮ 窶・**蜈ｨ 5 milestone COMPLETE (2026-04-12)**

**譬ｸ蠢・撫**: Arrow 1 (Scan 竊・Structural) 縺ｮ (p,p)竏ｩ邃・filter 蠕後・蜈ｨ蟆・ｧ髫懷ｮｳ縺ｯ菴募梛縺・
**Residence**: research/hodge_conjecture_decomposition_v0.md

**Milestone 蛻・牡** (譛蟆上せ繧ｳ繝ｼ繝励∝推迢ｬ遶九↓ PASS/FAIL 蛻､螳壼庄閭ｽ):

| ID | Exercise | Input | Output | 蛻､螳壼渕貅・| Depends |
|---|---|---|---|---|---|
| HC-1a | **Tier 陦ｨ螳梧・** | **COMPLETE (2026-04-12)**: 5-tier ﾃ・15 蜈ｷ菴謎ｾ・(ﾂｧ13.1b)縲５ier 2 縺ｫ 4 萓・(abelian 4-fold proved, cubic 4-fold proved, K3^[2] OPEN, generic trivial)縲５ier 竏・繧・竏・a/竏・b 縺ｫ蛻・屬縲・| 縺ｪ縺・|
| HC-1b | **Arrow 蝗ｳ蠑丞庄謠帶ｧ讀懆ｨｼ** | **COMPLETE (2026-04-12)**: HRR exact on 6 varieties (P^2, K3, abelian surface, P^3, quintic CY3, P^4)縲・hi(O) Hodge = Todd integral in all cases縲つｧ24 縺ｫ險倬鹸縲・| 縺ｪ縺・|
| HC-1c | **谿句ｷｮ蝙句・鬘・* | **COMPLETE (2026-04-12)**: 10 examples, 3 R-types. **Clean separation**: Tier sqrt = R-gauge (4 examples, ALL killed by Q-gauge), Tier 2 = R-topo (4 examples, ALL persist). Rational Hodge conjecture reduces to: ker_topo cap Hdg^p(X,Q) =? 0. ﾂｧ26 縺ｫ險倬鹸縲・| HC-1a |
| HC-1d | **3-instance kernel 邨ｱ荳** (OQ-HC-5) | **COMPLETE (2026-04-12)**: Template T-AAS extracted. ker=ker_gauge+ker_topo. 15/15 fitness (5 criteria x 3 instances). Conductor: f=f_torsion+f_rational. Hodge conjecture = f_rational=0. 3 departures (Stark:hierarchy, Hodge:open, Crystal:R-comp blur). ﾂｧ27 縺ｫ險倬鹸縲・| HC-1c |
| HC-1e | **Voisin 竏・b gauge 逕溷ｭ・* (OQ-HC-6) | **COMPLETE (2026-04-12)**: All known obstructions (Steenrod Sq^3, unramified H^3_nr) VANISH under Q-gauge (both live in torsion groups; Q/Z tensor Q = 0). NO Q-rational counterexample known. "Third wall" NOT FOUND. A rational counterexample would require fundamentally new obstruction type. ﾂｧ25 縺ｫ險倬鹸縲・| 縺ｪ縺・|

**險ｭ險亥次蜑・*:
- HC-1a, HC-1b, HC-1e 縺ｯ迢ｬ遶・(荳ｦ蛻怜庄閭ｽ)
- HC-1c 縺ｯ HC-1a 縺ｫ萓晏ｭ・(tier 陦ｨ縺後↑縺・→谿句ｷｮ蛻・｡槭〒縺阪↑縺・
- HC-1d 縺ｯ HC-1c 縺ｫ萓晏ｭ・(谿句ｷｮ蝙九′縺ｪ縺・→邨ｱ荳 template 縺梧嶌縺代↑縺・
- 蜈ｨ縺ｦ exercise (霎樊嶌縺ｮ蛻・ｧ｣閭ｽ繝・せ繝・縲りｨｼ譏弱ｒ逶ｮ謖・＆縺ｪ縺・・- 蜷・milestone 縺ｯ 1 session 縺ｧ螳檎ｵ仙庄閭ｽ縺ｪ繧ｹ繧ｳ繝ｼ繝・
**Sub-OQ 謨ｴ逅・* (譌ｧ OQ-HC-2 ~ HC-9 縺ｯ milestone 縺ｫ蜷ｸ蜿・or DEFERRED):
- OQ-HC-5 竊・HC-1d
- OQ-HC-6 竊・HC-1e
- OQ-HC-2 (T8 codim ﾃ・Bloch) 竊・T8 RETIRED 縺ｫ繧医ｊ **DISSOLVED** (T8 Boltzmann 驥阪∩縺ｮ Hodge 驕ｩ逕ｨ縺ｯ譛ｪ讀懆ｨｼ縲＾Q-T8-residual 縺悟・豎ｺ)
- OQ-HC-3 (邃・conductor) 竊・HC-1c 縺ｫ蜷ｸ蜿・- OQ-HC-4 (Hodge locus codim) 竊・DEFERRED (LOW)
- OQ-HC-7 (莠碁｡・荳蛾｡樣囿螳ｳ) 竊・DEFERRED (HC-1c 蠕・
- OQ-HC-8 (BSD 6-gauge) 竊・DEFERRED (HC milestone 螟・
- OQ-HC-9 (Sha base change) 竊・DEFERRED (HC milestone 螟・
- OQ-YM-2,3,4 竊・YM branch RESOLVED, residual 縺ｯ YM milestone 螟・
## Geometric Frontier (ﾂｧ28, 2026-04-12)

| OQ | Question | Priority | Axis |
|---|---|---|---|
| OQ-HC-10 | dim 6 exotic: Generic=No exotic (FFT). Weil disc=-1 PROVED (Markman B). **Weil disc≠-1 OPEN**. **Albert III quaternionic OPEN**. Albert IV partial (Milne 2020). 3 sub-Q (§28.3b). | MEDIUM (scope 限定) | B |
| OQ-HC-11 | ker_topo hom/surj 蛻・ｧ｣縲・*RESOLVED** (L1 蜿肴丐貂・縲・| RESOLVED | D |
| OQ-HC-12 | Benoist-Ottem 竏・c 霑ｽ蜉縲・*RESOLVED**縲・| RESOLVED | C |
| OQ-HC-13 | motivic t-structure ↔ Q-R gauge. **2026-04-13: CLOSE推奨** — t-structure構成≈HC同値(Ayoub), circular dependency. Drew framework 進展なし. | LOW→**CLOSED** | C, E |
| OQ-HC-14 | Spencer-Hodge (arXiv:2506.12720, 2025.06). Spencer-VHS framework で constraint rigidity→algebraicity 主張. **未査読**. 2025年6月投稿, 査読待ち. 再開: 査読通過時. | LOW (keep) | A, E |
| OQ-HC-15 | **wildness depth = ﾎｶ 3-gauge**: addZ/mult/anal 竊・depth 0/1/2縲ばｽ-Albert-depth mapping縲・*Sign channel collapse**: ﾎｽ=-1 竊・W=+1 竊・depth 2 螢√・1 險倩ｿｰ貂・(ﾂｧ7.5)縲よｮ・ exotic 竊・ﾎｽ=-1 L髢｢謨ｰ縺ｮ讀懆ｨｼ縲・| **PARTIAL** (L1貂医∵､懆ｨｼ谿・ | B, ﾎｶ |
| OQ-HC-16 | Semi-regularity 壁 (2026-04-13 update): 3段障害=(1) σ_E injectivity for n≥4 B-secant未検証 (2) HK bridge不在 (3) disc制約. Markman 2509.23079 conditional only. §28.6b に詳述. | MEDIUM | E |
| OQ-HC-17 | **ﾎｶ 逕滓・譬ｸ**: 2/3 formal (S7,S9)縲ぱ-ﾎｦ cyclotomic 莠域ｸｬ **REFUTED** (Sp(6) exotic dim=9 遒ｺ螳壹＿(ﾎｶ竄・謗･邯壹↑縺・縲Ｂnal竊播epth 2 縺ｯ analogical 縺ｮ縺ｾ縺ｾ縲４p(6) 險育ｮ・ 10 invariants, 1 divisor, 9 exotic [PROVED]縲Ｇormal bridge 蛻･蛟呵｣懆ｦ√・ **PARTIAL** (2/3) | ﾎｶ |

## Periodic Table S16 OQ (2026-04-13)

### OQ-PT-1 (HIGH → **PARTIALLY RESOLVED**): ν の N 依存性 a ∝ 1/l の理論的導出

**問い**: 感度係数 a = dν/d(ln N) が角運動量 l に逆相関する (s:0.89, p:1.07, d:0.44, f:0.10) のはなぜか？

**解決 (2026-04-13, s16_oq_pt1_a_derivation.py)**:

1. 純 Rydberg の ν は **√N で成長** (R²=0.9999)。ln(N) は N=8-30 での近似
2. 有効多重項数 M_eff = 1.11·(2l+1)² が a を決定:
   - p(l=1): pred +0.99 vs obs +1.07 (err -0.08)
   - d(l=2): pred +0.44 vs obs +0.44 (err 0.00, calibration)
   - f(l=3): pred +0.09 vs obs +0.10 (err -0.01)
3. **メカニズム**: (2l+1)² 個の低エネルギー多重項が Rydberg ギャップを埋め、ν を安定化

**s-block 追加解析 (s16_oq_pt1_sblock_fix.py)**:
- cross-l gap filling: 4 Rydberg 系列 (s,p,d,f) の系列間準位がギャップを埋める
- k=4, M=0 モデルで a=1.24 (obs 0.89)。残差 +0.35 は内殻/二電子励起による追加 gap-filling
- **統一モデル**: a = f(k_series, M_intra)。2つの gap-filling メカニズム:
  (1) CROSS-l: 複数 Rydberg 系列の準位が interlace
  (2) INTRA-l: (2l+1)² 多重項がギャップを充填
- EXP 3 (リアルモデル): p err=0.06, d err=0.02, f err=-0.03, s err=+0.44
**Status**: **p/d/f RESOLVED, s PARTIALLY RESOLVED** (定性理解は完了、定量残差 +0.35)
**Residence**: periodic_table_dictionary §3.4
**Axis**: A, B

### OQ-PT-2 (MEDIUM): d-block ν ∝ 1/n_eff^2.5 の導出 — OPEN

**問い**: d-block のみ ν = 31.9/n^2.47 (R²=0.988) が成立する。指数 ≈ 2.5 の理論的起源は？

**試行 (s16_oq_pt234.py)**: ランダム多重項 + Slater スケーリング (E_mult ∝ 1/n^α) で α を掃引。α=0-4 で β=2.5 を再現できず。モデルが粗すぎる。

**残る仮説**: 
- LS→jj 結合転移の定量モデルが必要
- 3d: LS 結合 → 多重項が term-wise に分裂 → 中程度の ν
- 5d: jj 結合に接近 → 分裂パターンが質的に変化 → 低 ν
- β=2.5 は Slater F^k ∝ 1/n^3 と SO coupling ∝ Z^4/n^3 の競合から出る可能性

**Residence**: periodic_table_dictionary §9.1
**Axis**: A, B

### OQ-PT-3 → **RESOLVED**: f-block Θ_f の W 字型 = Hund 交換ギャップ

**解決 (s16_oq_pt234.py)**: 半充填 (N_f=7) で交換安定化エネルギーが最大 → 基底-励起間に大ギャップ → ν が 2 倍にジャンプ。閉殻 (N_f=14) は単一基底項 → 全準位がギャップ上 → ν 最大。モデルが W 字型の 2 ピーク (φ=0.5, 1.0) を定性的に再現。a も同じプロファイル（半充填/閉殻で DIVERGENT、中間で STABLE）。cos(4πφ) = Hund 則 + Pauli 排他律の Fourier 表現。

### OQ-PT-4 → **RESOLVED**: RMS = 2 体相関 (spectral form factor)

**解決 (s16_oq_pt234.py)**:
- ν = std(spacings)/mean = **1 体統計**（間隔分布の幅）
- RMS = |K(τ) - F(τ)| = **2 体相関**（spectral form factor、準位間の pair correlation）
- 同一物理レジーム内では r(RMS, ν) < 0.1（ほぼ独立）
- Cross-type では r = +0.93（Rydberg/Poisson/GOE の区別を共有）
- RMS が a 制御後も IE と +0.50 残る理由: **IE は準位間の反発パターン（2体相関）と関連**し、RMS で捕捉される

### OQ-PT-5 (LOW): E_range × IE = +0.88

**問い**: エネルギー範囲 (30番目の準位のエネルギー) が IE と r = +0.88 で強相関する理由。

**候補**: E_range ∝ IE² (水素的元素では E_range ≈ 13.6·Z_eff² eV ≈ IE·n² / Z_eff)。E_range は (Z_eff, n) の組み合わせであり、IE の別表現に過ぎない可能性。

**Residence**: periodic_table_dictionary §5.11
**Axis**: B

### OQ-PT-6 (LOW): N 依存性の他ドメイン波及

**問い**: FX, Crystal, NT, Connectome の S16 でも同様の N 依存性 (発散/収束レジーム分離) が存在するか？

**予想**: 
- NT (ゼータ零点): Rydberg 型 → 発散型（高さ T の零点を増やすと ν が変化）
- Crystal (フォノン): 多重項型 → 収束型
- FX: 混在の可能性

感度係数 a の概念が S16 の domain-universal な W 診断ツールとなるか。
**Residence**: L3 s16_cross_domain_comparison §6
**Axis**: A, B, C

## Action items

(none open)

## Paper 2 / Twin-Zeta bridge OQ (2026-04-13)

| ID | Question | Priority | Residence |
|---|---|---|---|
| OQ-P2-1 | carry 率 c(g, X) の closed form は Euler product で書けるか? φ(X) residue structure の exact formula **RESOLVED_POSITIVELY (2026-04-22)**: c(g,X) = N_g(X) / \|S_g(X)\| where \|S_g(X)\| = X · ∏_{p\|X}(1 - ν_g(p)/p) (**finite Euler product** over primes of X, ν_g(p)=2 if p∤g else 1) and N_g(X) = #{b ∈ [1, r-1] : gcd(b,X) = gcd(r-b,X) = 1} with r = g mod X (short finite sum). 数値検証: X=396 (15 gaps, \|d\|<1.1%), X=50 (15 gaps, \|d\|<1.5%), X-scan g=2 (8 values of X, \|d\|<0.3%). g=4,16 carry=0 (Remark 2.5) は N_g(X)=0 で構造的に説明。§C.2「closed form 未導出」を訂正。conductor dim = ω(X) (X の素因数個数). | **CLOSED** | research/oq_p2_1_carry_closed_form.md, experiments/core/oq_p2_1_carry_closed_form.py |
| OQ-P2-2 | **D_floor(s) s-dependence**: **RESOLVED_POSITIVELY_UNIVERSAL (2026-04-22, 4th rev)**. Four-stage investigation: (1) gap=2 plateau at 0.85 → (2) gap universality check (gap=2 excep) → (3) k_max sweep at gap=2 (plateau is artifact) → (4) **k_max × gap cross-sweep (this rev)**: α(1, g) > 0 over all 20 entries (5 gaps × 4 k_max). Log(g/2) linear form invariant (R² ≈ 0.98 across k_max ∈ {15, 30, 60, 100}), coefficient k_max-gauge (slope(s=1) ∼ k_max^{−0.573}, R²=0.947; slope(s=0.86) ∼ k_max^{−0.251}). **s*(N) → 1 universal across all tested gaps** — NOT "large-gap only" as prior reframe claimed. Prior claim "α(1.0, g) ≈ 0.013·log(g/2)" was k_max=30 gauge value; correct form: α(1, g) = a(k_max)·log(g/2). Mechanism: high-k Fourier modes contribute gap-independent white noise that dilutes low-k signal (~1/√k_max at s=1). Remaining open: P2-2f (canonical k_max choice) + P2-2g (N→∞ and k_max→∞ double limit). | **CLOSED** | c_distortion_floor.md §S8, c_alpha_decay_exponent.md §4/§5, research/oq_p2_2_sstar_asymptotic.md (4th iter section), experiments/core/oq_p2_2_{alpha_profile_gap2,gap_universality,kmax_sweep_gap2,kmax_gap_crosssweep}.py, data/oq_p2_2_sstar/ |
| OQ-P2-3 | ε の second-stage factorization: mod 6 substructure を Dirichlet character χ(mod 6) で分解可能か? **CLOSED_NEGATIVE_STRUCTURAL (2026-04-22)**: 非主成分 χ₁ (Legendre) は p=0.87 (z=-1.05) で signal なし; χ₀ indicator のみ有意 (class 0 = 6\|g gaps の R² が class 1+2 より有意に高い, p=0.014, z=+2.62, D_floor 差 ~2×) at s=0.5. s=1 では全 signal なし (memo v1 の「s=1 で visible」は**再現せず**). 構造的説明: prime gap の residue exclusivity (g≡2 mod 6 ← p≡5 のみ, g≡4 mod 6 ← p≡1 のみ, g≡0 mod 6 ← 両方; 100% 成立) により、class 1/2 は統計的に独立 noise realization となり χ₁ = (m₁-m₂)/2 は構造的にゼロ。class 0 の distinguished な低 D_floor は「二重 residue source」効果 (χ₀ indicator). | **CLOSED** | Twin-Zeta §7.5, research/paper2_twin_dictionary_bridge_v1.md §3.2, experiments/core/oq_p2_3_{dirichlet_mod3,s1_check,mirror_mechanism}.py, data/oq_p2_3_dirichlet/ |

## FX Paper B follow-up OQ (2026-04-17, post-OQ-FX19 v0.4)

### OQ-FX22 (CLOSED 2026-04-20, 6TH-LEG CANDIDATE): Signal B saturated standalone walk-forward viability

**元問い**: OQ-FX19 honest で Signal B (|d(λ₁)/dt| smooth-20 P90 revert) saturated bucket (decor > 0.92) が Sh_hon = +0.490 (N=99) と Signal B 最大 bucket。TPY ≈ 56 で legacy sqrt(40) assumption に近く inflation factor も最小 (~1.8×)。walk-forward 両半分 positive かつ既存 5 leg と orthogonal なら 6 番目の独立 tradable leg 昇格可能か?

**Closure** (via `fx_oq_fx22_signal_b_saturated.py`, pre-registered 2018-10-17 midpoint, |r|<0.30 threshold):

| metric | value | verdict |
|---|---|---|
| full | N=99, $\mathrm{Sh}^\mathrm{hon}=+0.490$ | OQ-FX19 reproduction |
| **h1 ($<$2018-10-17)** | N=33, $\mathrm{Sh}^\mathrm{hon}=\mathbf{+0.423}$ | $+$ |
| **h2 ($\ge$2018-10-17)** | N=66, $\mathrm{Sh}^\mathrm{hon}=\mathbf{+0.632}$ | $+$ |
| monthly PnL $r$ vs S11_TBE | $-0.009$ (134月) | orthogonal |
| monthly PnL $r$ vs PA_extremes | $-0.017$ (172月) | orthogonal |
| monthly PnL $r$ vs PA_saturated | $+0.058$ (105月) | orthogonal |
| monthly PnL $r$ vs C_dead_zone (OQ-FX21) | $-0.003$ (185月) | orthogonal |

**Structural注**: B_saturated と PA_saturated は同じ decor bucket (> 0.92) を共有するが monthly $r=+0.058$ で独立。機構が異なる (Signal B = spectral velocity |dλ₁/dt|, PA = spectral level λ₁) ため saturated decor regime 下でも別事象を捕捉している。h2 が h1 より強い ($+0.632$ vs $+0.423$) のは EPY 9.60 vs 4.14 で post-COVID 期に saturation events が集中したため。

**Verdict**: pre-registered decision matrix で **6th-leg candidate** 昇格。Paper B 5-leg strategy table に Signal B_saturated を 6 番目として追加。Destruction mechanism picture は依然 4-channel のまま (Signal B は既存 Gram phase channel の velocity-mode)。

**Residence**: Paper B §7.5 5-leg table → 6-leg, §7.5 Signal B bullet, §9.1 OQ-FX22 row, §12 script table, `fx_oq_fx22_signal_b_saturated.py`。

**Axis**: D (destruction / strategy).

### OQ-FX23 (CLOSED 2026-04-20, PARTIAL CONCERN): §7.6 / §11 per-trade trading model event-clustering check

**元問い**: OQ-FX18 stats audit (2026-04-17) は「§7.6/§11 は raw per-trade 報告で ANN 乗数なしなので audit の影響を受けない」と記録したが、その audit は ANN inflation しか測定していない。cross-sectional event clustering (同一 t で複数 pair が fire) の per-trade 分散過小評価 bias は §7.6 の +0.130 / CI [+0.047, +0.210] に本当に影響しないか?

**Closure** (via `fx_oq_fx23_clustering_check.py`, bt_v6_final BASE config 再現, bootstrap 5000 iter seed 42):

| metric | value |
|---|---|
| N_trades / N_events / N_days | 401 / 190 / 69 |
| avg pairs/event | 2.11 (max 11) |
| span | 14.28 yrs |
| **per-trade raw Sh (§7.6 reproduction)** | $+0.1299$ ≈ §7.6 の $+0.130$ |
| per-event (basket sum) Sh | $+0.1434$ |
| **per-event (basket mean) Sh** | **$+0.1044$** |
| per-day (basket sum) Sh | $+0.2047$ |
| honest ann-event Sh (EPY=13.31) | $+0.5229$ |
| **clustering factor (trade/event_mean)** | **$+1.244$ (24% inflation)** |
| per-trade bootstrap CI | $[+0.032, +0.221]$ ≈ §7.6 $[+0.047, +0.210]$ |
| per-trade block-5 CI | $[+0.030, +0.216]$ |
| per-event (sum) bootstrap CI | $[+0.006, +0.261]$ |
| per-event (mean) bootstrap CI | $[-0.038, +0.234]$ |
| per-event block-5 CI (sum) | $[-0.016, +0.280]$ |

**Findings**:
- **§7.6 per-trade Sh $+0.1299$ is reproducible** (matches $+0.130$ reported). Pre-trade bootstrap CI $[+0.032, +0.221]$ approximates the reported $[+0.047, +0.210]$ (minor drift from different seed / boot method).
- **Clustering factor 1.24**: per-trade Sh is ~24% inflated relative to per-event mean. Basket-mean honest reading = $+0.1044$.
- **CI overlap holds**: per-event mean point $+0.1044$ is well inside per-trade CI $[+0.032, +0.221]$, and per-trade point $+0.130$ is inside per-event mean CI $[-0.038, +0.234]$. The §7.6 significance claim ($p{=}0.0004$) is qualitatively robust.
- **Per-event bootstrap is wider**: basket-mean lower bound $-0.038$ crosses zero. Event-level significance is marginal (lower bound near 0). The block-5 per-event sum CI $[-0.016, +0.280]$ also straddles 0.
- **Honest ann-event Sh $+0.5229$** (EPY=13.31) is much larger than the raw per-trade number because of annualization. This is the most "correct" headline reading for a strategy firing 13× per year.

**Verdict**: **PARTIAL CONCERN**. Prior memo claim "§7.6 unaffected by OQ-FX18 stats audit" was too strong. Per-trade $+0.130$ has a 24% clustering inflation vs per-event mean $+0.104$; the significance claim survives but with narrower margin at event level (per-event lower CI near 0). Recommended: (a) Paper B §7.6 に clustering caveat を追記, (b) headline を per-trade $+0.130$ と per-event mean $+0.104$ の両方を併記, (c) annualized $+0.523$ を "honest canonical" として併記。§7.6 の sign-level finding (positive, Asia×crosses localization, 48-72h scale) は全て不変。

**Residence**: Paper B §7.6 footnote + §9.1 OQ-FX23 row + §12 script table, `fx_oq_fx23_clustering_check.py`。

**Axis**: meta / audit.

### OQ-FX20 (CLOSED 2026-04-19, COSMETIC): S11 leg generator method-level discrepancy (fx_oq_fx16_portfolio vs fx_phase_conditioned_portfolio)

**元問い**: OQ-FX19 reproduction (`fx_oq_fx19_direct_measure.py`, uses `fx_oq_fx16_portfolio.generate_s11_tbe_trades`) は legacy-convention combined Sh = +2.14 を返したが、Paper B v0.1–v0.3 §7.3 は phase_conditioned.run() 由来で +3.60 を quote していた。両者の S11 leg は同じ gate algebra ($-2.9 < z < -2.5$ AND decor 両端 AND $|\text{loading}|\ge 0.15$ AND ev-mom sign match) を共有するが、operational knob に diff がある:

| knob | phase_conditioned | oq16 |
|---|---|---|
| warmup | CORR+600 = **852** | max(CORR+ZSCORE, GRAM+20) = **1260** |
| hour reject | なし | hours 20–23 除外 |
| PnL calc | `sum(returns_mat[t+1:end+1, pi])` | `log(close[end]/close[t])` ffill'd |
| pair column order | USDCHF first | EURUSD first |
| spread table | tight (1.0–2.5 bp) | wide (1.5–3.5 bp) |
| annualization (native) | $\sqrt{252/2}=11.22$ | $\sqrt{40}=6.32$ (downstream stats) |

**Closure** (via `fx_oq_fx20_s11_method_audit.py`, PC-pair-ordered struct shared across 6 variants):

| variant | $N$ | raw per-trade Sh | $\mathrm{Sh}_{\sqrt{126}}$ | $\mathrm{Sh}^\mathrm{hon}$ (day bucket) |
|---|---|---|---|---|
| PC native (warmup 852, no hour-reject, PC spreads) | 24 | $+0.218$ | $+2.442$ | $+0.230$ |
| PC + hour-reject 20-23 | 24 | $+0.219$ | $+2.458$ | $+0.233$ |
| PC + warmup 1260 | 24 | $+0.218$ | $+2.442$ | $+0.230$ |
| PC + warmup 1260 + hour-reject 20-23 | 24 | $+0.219$ | $+2.458$ | $+0.233$ |
| OQ16 canonical (`generate_s11_tbe_trades`) | 24 | $+0.212$ | $+2.375$ | $+0.227$ |
| PC + OQ16 spreads + OQ16 warmup + OQ16 hour-reject | 24 | $+0.212$ | $+2.375$ | $+0.227$ |

**Findings**:
- **Trade count invariant** ($N=24$ for all 6 variants) — warmup 852↔1260 は S11 gate が空白区間で fire しないため ΔN=0、HOUR_REJECT 20–23 も S11 が該当時間に fire しないため ΔN=0。
- **Legacy Sh delta $\pm 0.07$** ($+2.375$ vs $+2.458$, max range $0.083$) — OQ16 spreads が wider ($\Delta\text{spread}\approx 0.5$ bp) で mean_bp を $+21.71\to+20.96$ に減じた spread-table 効果のみ。
- **Honest day-bucket Sh 不変** ($+0.227$–$+0.233$, range $0.006$) — pre-registered 閾値下で method knob は全て cosmetic。
- **+3.60 vs +2.14 combined gap は S11 leg 起因ではない**。S11 alone の legacy $\mathrm{Sh}_{\sqrt{126}}$ は全 variant で $+2.38$–$+2.46$、combined figure への差分は S13 leg 再実装 or S11+S13 pool 方法 (per-pair concat vs per-event concat, weight 方式) に由来する。honest reading ($+0.378$, OQ-FX19) は両者 invariant。

**Verdict**: **CLOSED_COSMETIC**。S11 generator 方法差は $\le 3\%$ の legacy Sh で honest 不変。Paper B v0.5 の §7.3 magnitude claim ($\mathrm{Sh}^\mathrm{hon}=+0.378$) は S11 leg method knob に robust。+3.60 vs +2.14 gap は S13 or pool aggregation 由来で別 OQ が必要なら FX24 として発行予定 (現状 LOW: honest +0.378 が invariant なので Paper claim への影響なし)。

**Residence**: `applications/market/fx_oq_fx20_s11_method_audit.py` (new wrapper, no existing script modified), Paper B §7.3 footnote (method invariance note), §12 script table。

**Axis**: meta / audit.

### OQ-FX21 (CLOSED 2026-04-19, 5-CHANNEL CANDIDATE): Signal C dead-zone tradability と "inverted bimodal" ラベル妥当性

**Closure summary**: `fx_oq_fx21_dead_zone_closure.py` walk-forward + orthogonality 実測:
- full N=352, Sh_hon = +0.197 (OQ-FX19 再現)
- **h1** (< 2018-10-17): N=148, Sh_hon = **+0.300**
- **h2** (≥ 2018-10-17): N=204, Sh_hon = **+0.119** (soft positive, 両半分 + 成立)
- **Monthly PnL Pearson r**: vs S11_TBE = **-0.013** (134 overlap月), vs PA_extremes = **-0.011** (174 overlap月)
- 閾値 (pre-registered): |r| < 0.3 → **両方 orthogonal**
- 両半分 + & 両 orthogonal → **5-channel candidate** 昇格 (pre-registered rule)

**Notes**:
- (a) dead-zone standalone tradability: **YES** (両半分 +, ortho 2/2)
- (b) label reframe: legacy "inverted bimodal (extremes)" → **"dead-zone exclusive / 単峰"** 確定 (honest で positive は dead-zone のみ)
- (c) A/B との機構相違: A/B 系は U 字 (extremes ∪ saturated)、C 系は dead-zone 単峰 — cluster-coupling 軸は質的に異なる destruction

**Caveats**:
- h2 Sh_hon +0.119 は marginal。h1 +0.300 との劣化は decor regime shift の可能性あり (要追試)。
- 年次 firing は dense (EPY ≈ 22-30) で S11/PA (EPY ≈ 1-2) と qualitatively 異なるタイムスケール。monthly correlation orthogonality は robust だが decor-regime-conditioned correlation は未測定。
- N=352 は十分だが pre-registered bootstrap 未実施 (monthly r ≈ 0 が rare-event ではないことは 174 月 × r≈−0.01 で担保)。

**下流影響**:
- Paper B §7.5 第4 channel: "inverted bimodal" 表現を "dead-zone exclusive / single-peak" に書換
- §11 Thesis 4-channel destruction: (iv) の具体形を "dead-zone exclusive" に確定、直交性は 5-channel 拡張形で維持
- §12.7.4 candidate(corrected) 行 → promoted to "5-channel candidate"
- Paper B v0.4a → v0.5

**Residence**: Paper B §7.5 / §11 / §12.7.4, `fx_oq_fx21_dead_zone_closure.py`, `fx_phase_texture_bimodal.py` dead-zone gate

### OQ-FX21 (MEDIUM, ORIGINAL ISSUE — superseded by closure above 2026-04-19): Signal C dead-zone tradability と "inverted bimodal" ラベル妥当性

**問い**: OQ-FX19 honest measurement 後、Signal C (cluster spread P90) の bucket 分布は legacy と逆転した。honest 値:
- extremes: Sh_hon $=-0.106$ (N=89)
- saturated: $-0.040$ (N=54)
- structured: $-0.107$ (N=35)
- dead-zone: **$+0.197$** (N=352) ← C channel 唯一の positive bucket

legacy (inflated) では "extremes が最も効く inverted-bimodal" と framing していたが、honest では dead-zone が唯一の positive、それ以外は全て non-positive。これは以下の 3 問を提起する:

(a) **dead-zone standalone tradability**: +0.197 は N=352 での統計的有意性を持つか? 独立戦略として walk-forward 分割 (calendar midpoint 2018-10-17) で両半分 positive を達成できるか?
(b) **label 妥当性**: 「inverted bimodal」(extremes ≒ saturated で機能) から「dead-zone exclusive」(dead-zone のみで機能) への reframing が必要か? これは 4-channel destruction の C channel の構造的解釈を変える (対称 U 字 vs. 単一谷底)。
(c) **Signal A/B との非対称の機構**: A/B は saturated + extremes で機能 (U 字)、C は dead-zone で機能 (逆 U 字 ではなく単峰か?)。cluster-coupling 軸が他 2 軸と質的に異なる destruction 機構を持つ可能性。

**優先度判断**: MEDIUM。Paper B v0.4 §12.7 / §7.5 第4 channel 記述の structural claim を直接書き換え得る。§11 Thesis の "4 つの直交チャネル" は維持されるが (iv) の具体形が変わる。

**Depends on**: OQ-FX19 (CLOSED 2026-04-17) の honest Signal C buckets (既得)

**Residence**: Paper B §7.5 (第 4 channel 記述), §12.7.4 candidate(corrected) 行, fx_phase_texture_bimodal.py (dead-zone gate の既存実装)

**Axis**: A (spectral structure), D (destruction taxonomy)

**Close path**:
1. `fx_oq_fx19_direct_measure.py` ベースで dead-zone only standalone trades を抽出
2. walk-forward calendar midpoint split で両半分 Sh_hon 測定
3. PA_extremes / S11_TBE と temporal orthogonality を確認 (monthly PnL correlation)
4. 両半分 + かつ既存 leg と orthogonal なら 5-channel 戦略 candidate 昇格 / 片半分 negative なら legacy labeling を "dead-zone weak candidate, C 軸は A/B とは異なる機構" に縮退

**Trigger to close**: dead-zone walk-forward 両半分結果 + orthogonality 表の追加、Paper B §7.5 第 4 channel 節の再記述。

## FX Cross-Asset Port — 7-domain market regime classifier (2026-04-25)

Tracked in L3 `dictionaries/L3_crossdomain/market_regime_2d_classifier_v0.md` (v0.85). Single-day session arc: 4 → 7 domains, 3 refutes, 4 axis discoveries, 1 methodology pivot.

### OQ-FX-CRYPTO-1/2/3 (CLOSED 2026-04-25, Crypto port outcomes)
Crypto S11_TBE inversion mechanism (decor 100/100 trades on HIGH = monomodal aligned). PA channel survives. T-AAS-universal hypothesis refuted by Equity. See L3 §Refuted hypothesis history.

### OQ-FX-EQUITY-1/2 (CLOSED 2026-04-25, Equity port outcomes)
Equity 4/4 negative across 8/8 walk-forward halves. "Sustained-trend kill" mechanism: PA mean-reversion bets fail under directional drift; S11 correlation-breakdown trend-with bets also fail.

### OQ-FX-3DOMAIN-1 / 4DOMAIN-1/2/3 (mixed status 2026-04-25)
- **OQ-FX-4DOMAIN-1** (OPEN): Can M4 ~7% threshold be derived from microstructure (24/5 vs 24/7 vs storage)?
- **OQ-FX-4DOMAIN-2** (CLOSED_REFUTE_SOFT 2026-04-25): Bonds 5th-domain pre-reg; PA legs 3/3 sign-confirmed but S11 sign-flipped → +M3 axis added.
- **OQ-FX-4DOMAIN-3**: ≥6 domains needed for proper 2D threshold calibration. Now have 7.

### OQ-FX-5DOMAIN-1/2 (CLOSED 2026-04-25, REITs verdict)
- **OQ-FX-5DOMAIN-1** (CLOSED_REFUTE_HARD): 3D rule (decor_LOW, M4, M3) failed sign 0/4 on REITs. Discovered ρ=λ₁/K rank-1 cell.
- **OQ-FX-5DOMAIN-2** (CLOSED_REFUTE_PARTIAL): K=6 attenuation hypothesis refuted as primary mechanism (REITs PA legs not in K-attenuated brackets).

### OQ-FX-6DOMAIN-1/2 (mixed status 2026-04-25)
- **OQ-FX-6DOMAIN-1** (DEFERRED): rank-1 cell confirmation (still 1 instance: REITs). Tested via PrecMet but landed in 3D scope (ρ=0.75). Alternative basket needed (utility ETFs ρ > 0.95).
- **OQ-FX-6DOMAIN-2** (CLOSED_REFUTE_HARD): PrecMet 7th-domain pre-reg failed sign 1/4. ρ revealed as **continuous PA boundary** (~0.7 within monomodal regime), not binary scope.

### OQ-FX-7DOMAIN-1/1a/1b/2 (current frontier)
- **OQ-FX-7DOMAIN-1** (PARTIAL_CLOSE 2026-04-25): Multi-axis OLS regression on 7-domain Sharpes. PA legs CV-validated (LOO R²=0.65-0.82, sign 6-7/7); S11 linear failed sign 2/7.
- **OQ-FX-7DOMAIN-1a** (PARTIAL_CLOSE 2026-04-25): S11 2-stage solver. Cell-rule sign 7/7 in-sample (cell × K interaction) + |S11| OLS magnitude LOO R²=0.75 → combined R²=0.90. Caveat: cell rule reverse-engineered, no CV for sign rule.
- **OQ-FX-7DOMAIN-1b** (NEW HIGH): 8th-domain external pre-reg test using v0.85 candidate model (PA + S11 2-stage). Single test promotes v0.85 → v1. Candidate baskets: utility ETFs (XLU/VPU/IDU/FXU/RYU/FUTY), Asian equity (EWJ/EWA/EWZ/EWY/INDA/EEM).
- **OQ-FX-7DOMAIN-2** (OPEN MEDIUM): External test of ρ ≈ 0.7 PA boundary hypothesis. Subsumed by 7DOMAIN-1b if Asian equity chosen.

**Reusable principle (potential feedback)**: When a hand-crafted classifier hits 3 successive refutations on the same calibration sequence with each refute producing a refinement that fails on the next test, switch to model-fitting (regression with CV) rather than continue rule iteration.

## Observation Theory OQ (Paper D §8.2, tracked primarily in Paper D, 2026-04-23 snapshot)

Paper D の Open frontier は §8.2 が primary owner。本 section は cross-reference snapshot。

### OQ-Ω-Obs-1 (RESOLVED-split 2026-04-22 + 2026-04-23)
**Quantum path**: minimal form **CONFIRMED** (Schmidt rank r > 1, 2026-04-22 research/oq_omega_obs_1_ker_entangle_frational_path_v0.md) + refined form **ESTABLISHED** (OQ-Ω-Obs-4a, 2026-04-23, 4-class Stab/Gauss/Eff-sim/Bell-local + Theorem 4a.1 unified f_rational, research/oq_omega_obs_4a_refined_quantum_hodge_v0.md)。
**Classical path**: **OPEN** (Paper E Phase 4 NeRF 継続、3-phase cross-invariant 未発見、古典 Hodge 予想 f_rational=0 未証明と構造同型)。
**Axis-2 Fi/I root**: 量子 Fi-discrete pinned / 古典 I-continuous 境界滲み asymmetry (c_arrow_obstruction.md §10.7.4a)。

### OQ-Ω-Obs-2 (PARTIAL CLOSURE, 2026-04-22)
S15 第 4 層不要、生成 = 逆 Arrow 合成 (Paper D §4.6 主張 4.2)。T-AAS kernel が obstruction 構造を full span。

### OQ-Ω-Obs-3 (RESOLVED / S17 ESTABLISHED, 2026-04-23)
Arrow 3 e-extremum、3/3 gate closed (gauge inv 3 base + 3 domain script 5/5 PASS + L1 bridge_constants entry)。
**3 Arrow canonical constants 完備** (π / ln 2 / **e**)。c_theorems_master.md S17 row + c_arrow_bridge_constants.md §5 + Paper D §4.5/§4.5.0。

### OQ-Ω-Obs-4 (parts-split)
- **Part 1** Arrow 3 quantum (log rank): candidate_v0 (q_quantum_observation.md §9 dictionary work outstanding)
- **Part 2** ker_entangle + T-AAS quantum lift: OQ-Ω-Obs-1 minimal CONFIRMED + **OQ-Ω-Obs-4a refined ESTABLISHED**
- **Part 3** (OQ-Ω-Obs-4c) ker_backaction: **OPEN (LOW)**
- **Part 4** (OQ-Ω-Obs-4b) 2-scanner BCH: **OPEN (LOW)**

### OQ-Ω-Obs-4a (ESTABLISHED, 2026-04-23)
Refined quantum Hodge 4-class framework (Stabilizer / Gaussian / Eff-sim / Bell-local)、Theorem 4a.1 unified f_rational via class infidelity (log₂-bit 統一単位系、P1-P4 proved)、3/4 empirical + C₃ literature 4-ref、axis-2 Fi/I root connection、depth-2 orthogonal axis flag。**6/6 gate closed**、9/9 script gate PASS。c_arrow_obstruction.md §10.7.4/4a/5。

### OQ-L0-refinement (ESTABLISHED v1, 2026-04-23)
L0 axiom v2 (2-axis Fi/I × D/C framework)。**3/3 gate closed**: c_theorems_master.md S15 axis-2 projection map annex + c_arrow_obstruction.md §10.0 2-axis (Fi/I) lens + Paper D §2.3.1 L0 v2 + §4.4.1 Fi/I commutation + §4.5.1b Fi/I commutator 系 4.1c。1 行 summary: ΣΦ 観測理論 = axis-2 Fi/I 境界の分類学。

### OQ-Paper2-Balance (OPEN MEDIUM → v1 で OQ-Ω5g に generalize / 統合, 2026-04-24)
Paper 2 carry (c=1/2) と D_floor min の X 同時固定可能性。v0.5 HIGH → v0.6 MEDIUM (rate-limiting 解消, meta-theorem が Paper E 経由で ESTABLISHED)。**2026-04-24 OQ-Ω5 v1 §5.1 で categorical root cause 化**: candidate σ_g(X) = 2g/X は g-parametric family で universal involution でない (v1 framework の locus realization Type II)。残存独立 OQ は **OQ-Ω5g (universal involution systematic search)** として generalize、Paper F (clade-parametric dispersion, Type II biological instance) と統合。

### OQ-Ω5 (2-category lift / σ-action groupoid framework, candidate_v1 2026-04-24)
Paper D §4.5.1b の真の categorical formalization。candidate_v0 (2026-04-23) → **candidate_v1 (2026-04-24, ΣΦ 独自 path selected)** で Gate 3 partial formal closure: **定理 4.3.1 unconditional** (σ_D-equivariant functor lift requirement ⟹ g_I, g_S ∈ Fix(σ_D) = critical line) + **定理 4.4.1 conditional on RH + Paper C §3 parabolic minimum** (s = 1/2 unique pinning) + **§5.4 4-instance categorical taxonomy** (Paper C coincide via universal σ_D + Paper 2 / F locus Type II σ_g non-universality + Paper E Type III stochastic σ_D 不在)。Connes-Marcolli は v1 で citation 不使用 (v1.5 以降の保留)。**5 sub-OQ (a-e) 状態 v1**: c/d closed/closed-deferred、a/b/e OPEN。**v1 で new 4 sub-OQ issue**: f/g/h/i (§8.3 below)。
**Residence**: `research/oq_omega5_2cell_v0.md` (v1 closure, 2026-04-24 10:36), `L1_mathematical/core/c_observation_optimal_gauge.md` §8.2 (v1 cross-ref), Paper D §4.5.1b (operational tool independent).

### OQ-Ω5a (OPEN v2, 真の 2-category axiom verification)
C_Ω が genuine 2-category (associativity + interchange + 8 gauge Type A 1-cell table) か。v1 では σ-action groupoid framework が functor/groupoid level で完結し、真の 2-cat structure 未 exercise。

### OQ-Ω5b (OPEN v1.5, C_Ω^stoch construction)
Paper E stochastic ensemble を uniform 記述する stochastic σ-action framework の formal construction。v1 §5.2 で Paper E split root cause (σ_D 不在 + random fiber) として re-identify 済み。

### OQ-Ω5c (PARTIAL CLOSED v1, Paper C ζ functional eq. σ-groupoid witness)
定理 4.3.1 unconditional + 定理 4.4.1 conditional on RH で formal 化。v1 で "2-cell witness" vocabulary 廃止 → "σ-action groupoid functoriality witness" に正名。残 sub-residuals は §4.7 で 3 項目 identify → OQ-Ω5h 等に分離。

### OQ-Ω5d (CLOSED_DEFERRED v1, Connes-Marcolli path)
v1 で ΣΦ 独自 path 選択確定、Connes-Marcolli citation 不使用。v1.5 以降の OQ-Ω5f/Ω5i trigger 時に再 open 可能 (BC system / adelic framework が natural setting になる case)。

### OQ-Ω5e (OPEN v1.5, predictive instance discovery) → **1st instance real + complex CONFIRMED 2026-04-24, SC3 caveat**
OQ-Ω5 v1 §4.5 5 predictive items: (1) Dirichlet L(s,χ), (2) Hecke / Artin L, (3) Hasse-Weil L, (4) non-involution domain negative, (5) RH-dependent verdict variation。
**v1.5 v0 real primitive (2026-04-24 earlier) status**: **item 1 Dirichlet L(s, χ) CONFIRMED** — 5/5 real primitive χ (χ_{-3}, χ_{-4}, χ_5, χ_{-7}, χ_8, conductor 3-8)、**D_C (untruncated log|Λ|²) で σ_min = 0.500000 exact + R² = 1.000** on asymmetric grid (symmetric-grid tautology concern を §7.4 asymmetric-grid sanity check で refuted)、C1-C3 全 pre-registered gate PASS。Residence: `research/oq_omega5_v15_dirichlet_l_first_instance_v0.md` + script `experiments/dirichlet_l_balance_v0.py`。
**v1.5 v0 complex primitive (2026-04-24 later) status**: **complex extension CONFIRMED with SC3 caveat** — 5/5 complex primitive χ (mod 5 ord 4 / mod 7 ord 3 / mod 7 ord 6 / mod 9 ord 3 / mod 11 ord 5)、C1-C4 全 PASS including NEW C4 gate (functional eq sanity |F(σ, χ̄) − F(1-σ, χ)| < 1e-8, actual 0 exact on all 5)。**SC3 post-write catch**: v0 §1 initial claim "F not σ-symmetric for complex χ" は **incorrect** — real-axis restriction では functional eq + complex-conjugation chain (|L(σ, χ̄)| = |L(σ, χ)| for real σ via conj(L(σ, χ)) = L(σ, χ̄)) により F(σ, χ) = F(1-σ, χ) は complex χ にも成立、asymmetric grid では tautology refute 不可。Genuinely non-tautological predictive test は **off-real-axis 2D scan (t ≠ 0, γ₁(χ) zero detection)** が要 (v1.5 v1 task 前倒し priority shift)。
**v1.5 v0 complex main contributions**: (a) framework extended to all primitive Dirichlet χ (real + complex 10 characters total), (b) C4 functional eq sanity NEW gate design for complex / non-self-conjugate L-function templates, (c) SC3 post-write catch = feedback rule 3rd empirical validation (SC1/SC2/SC3 all same-day 2026-04-24)。
Residence: `research/oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md` + script `experiments/dirichlet_l_balance_complex_v0.py`。残 item 2-5 継続 open。
**v1.5 v1 off-axis 2D scan INCONCLUSIVE with SC4 post-execution catch (2026-04-24 evening)**: 8 chars × 11 t × 9 σ = 792 Λ evaluations、Gates G1 80/80 + G4 8/8 PASS (framework structural fit numerically confirmed across (σ, t) ∈ [0.35, 0.82] × [0, 30])、G2 0/5 + G3 0/5 FAIL on complex χ (pre-registered "Step 2 fail off-axis" prediction completely refuted、σ_min(t) locked at 0.5 across all t)。**SC4 post-execution catch**: SC3 derivation を critical 修正 — conj(L(σ+it, χ)) = L(σ-it, χ̄) は complex s 全域で成立 (n real positive ⟹ conj(n^{σ+it}) = n^{σ-it}、coefficient conjugation χ → χ̄ は off-axis にも apply)、combined with functional eq で |Λ(σ+it, χ)| = |Λ(σ-it, χ̄)| = |Λ(1-σ+it, χ)| を ALL (σ, t) real で force。σ_min = 1/2 は **universal functional equation identity-level consequence**, NOT σ-action groupoid framework-specific predictive content on Dirichlet L domain。
**Post-SC4 framework predictive scope reassessment**:
  - **Paper C genuine content 保持**: Paper C coincide は Information (D_floor, gap-indexed factorization, independent of functional eq) + Structural (RH zeros) 両方 σ=1/2 で coincide — これは **2-quantity independent coincide** であり functional eq 単独では derive しない
  - **Dirichlet L extension scope**: "structural fit" のみ (functional eq + σ_D involution 存在 confirm)、σ_min = 1/2 は identity-level で "predictive content" 外出しなし
  - **Genuine framework extension test path** (post-SC4): Paper C-style Information + Structural 2-quantity independent coincide analog を domain-specific に define して test する必要あり、Dirichlet L では単純な σ_min metric では insufficient
Residence: `research/oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md` + script `experiments/dirichlet_l_balance_offaxis_v1.py`。
**v1.5 v1a 2-quantity coincide test REJECTED (2026-04-24 evening late)**: Spec pre-registered "Q1 = |L(σ+it, χ)|² σ_min (genuine, not functional-eq-forced) は Q2 = |Λ|² σ_min = 0.5 と coincide" hypothesis を 5 complex χ × 8 t = 40 cells で test。結果 **G2 gate 17.5% (|Q1 - 0.5| < 0.1 threshold)** vs pre-registered rejection threshold 30% ⟹ **REJECTED**。Q1 mean deviation from 0.5 = 0.60-0.82 across 5 χ (max 3.2)、|L|² σ_min は σ=0.5 center ではなく σ-high direction (Dirichlet series convergent regime σ > 1 近) に pushed。
**Post-execution root-cause** (feedback rule 3-phase 3rd phase の 2nd empirical validation): |L|² = |Λ|² / ((q/π)^{σ+a} · |Γ((s+a)/2)|²)、denominator が strongly σ-growing (Stirling + exponential) ⟹ |L|² は σ-asymmetric with minimum pushed to σ > 1。Paper C D_floor は gap-indexed prime partial sum residual for **normalized log L** (explicit formula expansion) で 0.5-centered parabolic structure が built-in、一方 |L|² 単独は gamma factor compensation 不在で 0.5 center 保証なし。
Residence: `research/oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md` + script `experiments/dirichlet_l_balance_2quantity_v1a.py`。
**Framework scope for Dirichlet L (post-v1a definitive closure)**:
  - **Structural fit only**: functional eq + σ_D involution 存在 confirmed、category-theoretic formal structure apply
  - **Predictive content beyond functional eq identity**: **NOT present via |L|² Information analog** (v1a refuted naive approach)
  - **Paper C uniqueness 保持**: Paper C の genuine 2-quantity coincide content は Paper C-specific、naive |L|² extension では獲得不能
  - **Genuine extension path (open for future v1b)**: Paper C D_floor proper analog construction for Dirichlet L (gap-indexed χ-weighted prime sum residual、explicit formula expansion around σ=0.5 を基に)
**Revised v1.5 roadmap (post-v1a)**:
  - ~~v1.5 v1a (attempted)~~: REJECTED (|L|² is NOT Paper C Information analog, empirically demonstrated)
  - **v1.5 v1b v0 (2026-04-25, CONFIRMED minimal diagnostic)**: χ-weighted prime partial sum Taylor residual around σ=0.5 で parabolic structure 実証 (3/3 complex χ, R² 0.96-1.00, curvature c ≈ 76-99)。Paper C (log N)² prediction dimensional match (⟨log p⟩² ≈ 108 for p ≤ 10⁵)。σ_min drift 0.01-0.05 from 0.5 は finite-N higher-order Taylor correction。Residence: `research/oq_omega5_v15_dirichlet_l_dfloor_prime_sum_v1b.md` + `experiments/dirichlet_l_dfloor_prime_sum_v1b.py`。**Post-execution audit** (3-phase 3rd phase 3rd empirical validation): σ_min = 0.5 partially by construction (Taylor expansion center) BUT R² > 0.9 + curvature dimensional match = genuine empirical content beyond construction-center triviality。SC4 universal chain 外 (prime sum only, no functional eq identity trap)。
  - ~~v1.5 v1b v1 (attempted)~~: **REJECTED + G3 byproduct** (2026-04-25 late): v1b v0 "(log N)² dimensional match" was single-N coincidence, v1b v1 N-sweep で curvature super-(log N)² scaling + σ_min drifts 0.51 → 0.59 + R² degrades 0.98 → 0.78、Taylor residual construction is NOT Paper C D_floor analog. **Positive byproduct**: G3 gap-class universality 12/12 PASS (Paper C multi-gap invariance holds). Residence: `research/oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md` + `experiments/dirichlet_l_dfloor_multigap_v1b_v1.py`.
  - **v1.5 v1b v2 decomposition note (2026-04-25 late)**: `research/oq_omega5_v15_dirichlet_l_dfloor_decomposition_note_v0.md`。Paper C D_floor = 2-stage fit (gap-indexed residual Stage 1 で N-dep prefactor absorb + parabolic Stage 2 per-N 3 params a/b/c, b(N)→0 empirically under RH via zero-phase cancellation → σ_min stability at 0.5)。v1b v0/v1 naive Taylor は **Stage 1 欠如** で N-dep drift 吸収不能、REJECTED root cause identified。v1b v2 tractability = **uncertain**: Stage 1 χ-weighted ideal model spec が non-trivial theoretical work。**Strategic recommendation**: 第一候補 (v1b v2 implementation) を pursue する前に **第二候補 (Hecke / Artin L pivot) を先行** 推奨、理由 = Dirichlet L は 2x refuted (Paper C uniqueness already strongly preserved, 深掘りは diminishing return)、Hecke / Artin は universality class difference で framework scope boundary sharpening に直接貢献 (information gain per cost higher)。
  - **v1.5 v2 v0 Hasse-Weil L CM curve PARTIAL_CONFIRMED (2026-04-26)**: E: y²=x³-x (Cremona 32a1) で framework weight-shift adaptability empirically 確認 — σ_min ≈ 1.10-1.12 at t=5, 10 (close to Fix(σ_D: s↔2-s) = s=1), weight-class differentiation 3/3 (σ_min ≠ 0.5)。G1 functional eq ratio FAIL は L-series truncation artifact。Residence: `research/oq_omega5_v15_hasse_weil_L_cm_curve_v2_v0.md` + `experiments/hasse_weil_L_cm_curve_v2_v0.py`。**Unified framework scope across weight 1, 2 classes**: Dirichlet L (weight 1, Fix=0.5) + Hasse-Weil L (weight 2, Fix=1) 両方 "structural fit" with weight-adaptive Fix(σ_D) pinning。
  - **v1.5 v2 v1 Hasse-Weil L smoothed + non-CM PARTIAL_CONFIRMED strengthened (2026-04-26 午後)**: smoothed truncation L_smooth(s) = Σ a_n exp(-n/X) / n^s (X=100 primary, X-sweep {50, 100, 200}) + non-CM curve 11a1 (Cremona, conductor 11, LMFDB a_p verified)。σ_min precision 大幅 improvement、Phase 4 X-sweep で → 1 convergence 確認。CM vs non-CM consistency 2/3 pass。Residence: `research/oq_omega5_v15_hasse_weil_L_smoothed_and_noncm_v2_v1.md` + `experiments/hasse_weil_L_smoothed_and_noncm_v2_v1.py`。
  - **v1.5 v2 v2 (2026-04-26 晩) — CONFIRMED via 11a1 non-CM + PARTIAL 32a1 CM**: t-adaptive smoothing X(t) = 50 + 30|t|、**非-CM curve 11a1 全 4 gates pass**, 32a1 CM は G1 large-t 特有 artifact (half-density a_p)。G3 CM vs non-CM consistency 4/4 PERFECT。Residence: `research/oq_omega5_v15_hasse_weil_L_t_adaptive_v2_v2.md` + `experiments/hasse_weil_L_t_adaptive_v2_v2.py`。**Framework extension to weight-2 Hasse-Weil L empirically established for non-CM curves**。
  - **v1.5 v2 v3 (2026-04-25) — CONFIRMED conductor universality at t≥5 + UNEXPECTED rank-1 BSD effect**: 4 non-CM curves test, G2 21/24 PASS (perfect 18/18 at t∈{5,10,15})、37a1 (rank 1) σ_min displacement at t=0.5 から L(1, E)=0 BSD effect が framework に detect される unexpected positive content。Residence: `research/oq_omega5_v15_hasse_weil_L_conductor_universality_v2_v3.md` + `experiments/hasse_weil_L_conductor_universality_v2_v3.py`。
  - **v1.5 v2 v4 (2026-04-25) — Naive REJECTED + NEW oscillation-amplitude pattern**: 6 curves test, single-t displacement hypothesis REJECTED (53a1 rank-1 NO displacement at t=0.5)、**oscillation amplitude across t IS rank-discriminating** (rank-0 ≤ 0.05, rank-1 ≥ 0.16, clean factor 3-6×)。Residence: `research/oq_omega5_v15_hasse_weil_L_rank_universality_v2_v4.md` + `experiments/hasse_weil_L_rank_universality_v2_v4.py`。
  - **v1.5 v2 v5 (2026-04-25) — PARTIAL_CONFIRMED with Phase 3 catch**: 10 curves test。Rank 0 vs rank 1 amplitude separation ROBUST CONFIRMED (multi-curve, factor 4-9× clean separation), but rank 2/3 numerical breakdown (parabolic fit garbage from high-conductor smoothing inadequacy)。**G6 monotone scaling REJECTED as artifact**。Phase 3 catches gates auto-passing despite non-physical σ_min values。**Framework BSD rank detection (binary) empirically confirmed** as first non-trivial predictive content。Residence: `research/oq_omega5_v15_hasse_weil_L_rank_amplitude_v2_v5.md` + `experiments/hasse_weil_L_rank_amplitude_v2_v5.py`。
  - **v1.5 v2 v6 (2026-04-25) — CONFIRMED rank detection extending to rank 2/3**: conductor-adaptive smoothing + sanity gate + argmin で rank 2/3 numerical breakdown fixed。10/10 curves sanity-pass、binary rank detection ROBUST + monotone amplitude rank 0/1/2 confirmed (0.07 < 0.14 < 0.435)。Residence: `research/oq_omega5_v15_hasse_weil_L_conductor_adaptive_v2_v6.md` + `experiments/hasse_weil_L_conductor_adaptive_v2_v6.py`。
  - **v1.5 v2 v7 (2026-04-25) — reviewer redirect: K_E(t) Taylor prediction VERIFIED**: external AI review proposed K_E(t) := ∂²_σ log|Λ|_{σ=1} as theoretically-grounded alternative to A(E)。Pre-registered prediction K_E(t)·t² → r empirically validated for rank 0/1/2 (8 curves) at t=0.3。Phase 3 catch on gate-design (t=0.1 finite-difference too aggressive)。Residence: `research/oq_omega5_v15_hasse_weil_L_central_curvature_v2_v7.md` + `experiments/hasse_weil_L_central_curvature_v2_v7.py`。
  - **v1.5 v2 v8 (2026-04-25) — proper AFE cross-check CONFIRMED genuine**: SageMath/PARI 不在のため proper Iwaniec-Kowalski AFE via mpmath gammainc で実装、functional eq machine precision satisfied、9/10 curves K·t²→r prediction match within 5%、rank 3 fixes smoothed boundary issues。**Reviewer's smoothing-artifact diagnosis REJECTED**, signal genuine。Residence: `research/oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md` + `experiments/hasse_weil_L_proper_afe_v2_v8.py`。
  - **v1.5 v2 v8 Priority 1 + 3rd review correction (2026-04-25 evening late) — 433a1 implementation bug confirmed**: rank-mislabel hypothesis REJECTED per 3rd external review (PARI/Sage external evidence supports 433a1 = rank 2)。Diagnostic |Λ(1+εi, E)| confirms **AFE works for 389a1 rank 2 perfectly** (|Λ| ∝ ε² profile)、**fails for 433a1** (|Λ| const ≈ 10.86 = rank 0 signature) → my **Weierstrass equation likely incorrect** for true LMFDB 433a1。**Real implementation bug, NOT framework failure or rank relabeling**。Residence: `research/oq_omega5_v15_v2_arc_external_review_response_3_2026_04_25.md` + `experiments/hasse_weil_L_433a1_central_value_check.py` + `experiments/hasse_weil_L_433a1_deep_dive_v2_v8_priority1.py`。
  - **v1.5 v2 v9 (NEW NEXT)**: (a) LMFDB verification of 433a1 rank、(b) direct K formula via Λ''/Λ - (Λ'/Λ)² (no finite-difference), (c) external Sage/PARI confirmation if installable、(d) more rank-3/4 curves with verified ranks
  - **v1.5 v2 v10**: 高 weight (4, 6) modular form L-function で weight universality 拡張
  - **v1.5 v2 v11**: 4-phase + Phase 5 external review formal consolidation document
  - **v1.5 v2 v6**: Hecke / Artin L weight-1 higher-rank alternative
  - **v1.5 v2 v7**: proper Iwaniec-Kowalski AFE for clean G3 functional eq + conductor-adaptive smoothing
  - **v1.5 v3**: Hasse-Weil higher-conductor / non-CM curves
  - **v1.5 v4**: feedback rule 4-phase operation formal consolidation (8-stage validation data に基づく document)
  - v1.5 v3: Hasse-Weil L
  - v1.5 v4: feedback rule 3-phase operation formal consolidation
**feedback rule 3-phase operation empirical validation (2026-04-24 same-day 5-stages + 2026-04-25 v1b v0 = 6-stage progression)**: SC1 (pre/post-write) + SC2 (post-write) + SC3 (post-write) + SC4 (post-execution, 1st empirical validation) + **v1a clean REJECTION** + **v1b v0 CONFIRMED with partial-by-construction caveat** (post-execution audit 3rd empirical validation: root-cause curvature ≈ ⟨log p⟩² dimensional match が construction-center triviality を超えた genuine content 識別)。6 stage progression が 3-phase rule の discipline value を empirically 確立: 4 in-session catches + 1 clean REJECTION + 1 partial-construction-aware CONFIRMED。

### OQ-Ω5f (NEW OPEN v2, 真の 2-cell layer)
Parallel non-constant functor 間の natural transformation framework 構築。v1 §4.7 item 3 で identify、BC system candidate setting。

### OQ-Ω5g (NEW OPEN v1.5, universal involution systematic search)
Paper 2 candidate σ_g(X) = 2g/X / Paper F complement involution σ_F の universal extension exhaustive search。旧 OQ-Paper2-Balance を generalize。clade/g-parametric dispersion の Type II locus realization を uniform に extend する involution が存在するかの exhaustive search。

### OQ-Ω5h (NEW OPEN v1.5, Paper C Structural balance op def)
Paper C §3 は D_floor minimum (Information side) を specify、Structural side balance point "t = 0 axis-symmetric" は §4.4 で natural choice として暗黙採用。より rigorous な Arrow 1 上 Structural balance finder T_Arrow1^C specification が未確定。

### OQ-Ω5i (NEW OPEN v2, higher-rank functional equation lift)
Hecke / Artin / Weil (weight-shift variant) L-function への σ-action groupoid framework lift。v1 §4.5 predictive item 2-3 の formal lift。

## DNA (Paper F) OQ (2026-04-24 v2 update)

Paper F v2 で 6 OQ-DNA の reclassification 完了。primary residence: `papers/Paper_F_DNA_ja.md §8`、mirror: `L2_domain/dna_dictionary_v0.md`。

### OQ-DNA-1 / OQ-DNA-1a (CLOSED, 2026-04-23 Round 1 / Round 0)
3-vertex → 10-vertex triangulation complete, formula ±5% universal / Composition gauge absorber γ = S/W analytical, verified ±1%。

### OQ-DNA-4 (CLOSED_NEGATIVE_STRUCTURAL, 2026-04-24 v2)
Synthetic minimal genome で Path 2 coincide 達成可能か → **structurally excluded**。13/13 organism 全 split (10 natural + Mycoplasma minimal + phiX174 overlapping + 3 nuclear)、synthetic 11 sequences も "designed coincide" testable 条件満たさず。Biological sense-strand translational selection が sign-breaking、ζ 型 functional-equation enforcer 不在 (§8.3.1)。**v1 §5.3 Type II locus realization の biological instance** と整合。

### OQ-DNA-6 (PARTIALLY CLOSED, 2026-04-24 Round 4-5)
γ > 0.03 → F1 = 0.949 across 180k+ windows (F15 ORF predictor として biological application established)。

### OQ-DNA-2 (PARTIAL_CLOSED, 2026-04-24 v2)
γ-feature depth saturation 確認 — 3 nuclear organism で AUC 0.826-0.858 narrow band、organism-structure-blind (operon-scale signal 不在)。γ は operon-scale に対し implicit low-pass filter。残: 別 observable (MI at operon scale ~1-5 kb) の depth-2 test (Paper F scope 外、v3 候補)。

### OQ-DNA-3 (PARTIAL_CLOSED qualitative, 2026-04-24 v2)
F8 COX1 top-3 per-CDS 7/7 universal は DNA barcoding literature (dN/dS 0.02-0.10 universally low) と qualitative consistent。定量 scatter plot (per-CDS γ vs literature dN/dS) は v3 work (external dataset 要)。

### OQ-DNA-7 (PARTIAL_CLOSED scope bound, 2026-04-24 v2)
整数 period formula extension は structural closure: **β-strand (p=2) 直接拡張可能** (letters-by-letters even-odd difference generalize)、**α-helix (p=3.6 non-integer)** は single-bin DFT assumption 破り新 formalism 必要。

### OQ-DNA-5 (DEFERRED, blocker: AA-stratified data, 2026-04-24)
20 AA 別 codon 冗長度 × gene-specific AA usage での γ stratification。既存 11 JSON は AA-level partition 含まず、新規 measurement run 要 (既存 FASTA reuse、~30-60 min scope)。

### OQ-DNA-F-1 (DEFERRED, blocker: 3-DOF constrained distribution derivation, 2026-04-24)
3-DOF correlated exp sum median/mean = 0.825 の closed form。Pure Gamma(3,β) = 0.891 既知、constraint + Fourier-bin correlation で 0.825 shift の導出 pathway。Paper D appendix or separate mathematical note が optimal venue。

### OQ-PaperE-SeedBasinStructure (OPEN LOW, new v0.6)
Paper E structural basin {180 / 150-160 / 140} の UNet weight init 特徴化。9-15 seeds CI narrowing future work。meta-theorem status 不変。

### 4a post-ESTABLISHED future frontier (X1-X4, 2026-04-23)
4a ESTABLISHED に含まれない独立 future OQ:
- **X1**: depth parallel coefficient 具体値 (sparsity-matched pair の O(1) proportion、pure-math Hodge adjacent)
- **X2**: depth-2 量子 instance 同定 (幾何 vs 計算 orthogonal axis、未同定第 3 量子 class 探索)
- **X3**: C₃ Eff-sim 2-qubit Nielsen complexity closed-form
- **X4**: 古典 Hodge "wider algebraic source" refinement (motivic 等, pure-math OQ)

## Resolved archive (1-line summaries)

| OQ | Result | Date |
|---|---|---|
| OQ-Algorithmic-f_rational (I1 §5.2) | **ESTABLISHED**: 定理 5.2 algorithmic instance of Theorem 4a.1。$f_{\mathrm{rational}}^{\mathrm{alg}}(x;B) := K(x\|B)$ in bits via Solomonoff prior $F_C \asymp 2^{-K(x\|B)}$。5 instance (random/periodic/sparse/π/structured+noise) + V1 conditional + V2 UTM-gauge = 7/7 PASS at \|x\|=65536b。Rate range [0.007, 1.0] = 5 orders。Framework 内 f_rational 最 general instance ($\|x\|$ scaling free)。`c_information_theory.md §8.5` backward. 3 successor OQ spawn. | 2026-04-28 |
| OQ-OQS2 (Q2 §5.3) | **ESTABLISHED (honest dual answer)**: 定理 5.1 generator level canonical bijection ($\mathcal{L}_H$ ↔ error_arithmetic / $\mathcal{D}$ ↔ error_projection / $\bar n_k(\beta)$ ↔ error_noise) + Kraus level mixed caveat ($K_0$ bundles unitary phase + anticommutator damping) + closest-unitary diamond corollary $\|\Phi_{dt}-U_*\|_\diamond = \|\mathcal{D}\|dt$。dephasing+amplitude damping V1/V2/V3 PASS。Spawned `feedback_structural_match_at_correct_level.md`. 3 successor OQ spawn. | 2026-04-28 |
| OQ-Renyi-Scaffold-Continuous (I1 §3.3) | **ESTABLISHED**: 定理 3.3.1 Rényi α-family parametric scan of scaffold-emergence axis、4 anchor (α=0 Hartley / α=1 Shannon / α≥2 collision / α=∞ min-entropy) + 系 3.3.2 (monotone non-increasing per van Erven & Harremoës 2014)。`c_information_theory.md §1.5` Theorem 1.5.1 backward. | 2026-04-28 |
| OQ-Schumann-v1.5 (a) Type γ formal (N3 §2.2) | **DONE**: 定義 2.2 (3-condition formal predicate: 同-object proper sub-object fix + algebraic distinction + non-point/non-shadow)。Atkin-Lehner $W_N$ の $M_k^+ \subsetneq M_k(\Gamma_0(N))$ canonical instance + theta characteristics 6th instance pre-reg。N3 v0.5 bump。(b)(c) v1.5 task pending. | 2026-04-28 |
| OQ-S17-Codebook-3-Universal (I1 §4.3) | **ESTABLISHED (docs fix)**: 既に 2026-04-23 に 5/5 gate PASS で確立済 (3 setting NT/Codebook/Qudit + gauge invariance)、I1 §8.3 OQ 表 OPEN → ESTABLISHED 整合修正。successor OQ-S17-Density-Form-Universal spawn (どの info-theoretic 設定で関連 density が log(n)/n form を取るか)。 | 2026-04-28 |
| OQ-P1-Capacity (I2 §4.2) | **CANDIDATE_RESOLVED_NEGATIVE**: published $C \approx 2.18$ bits/symbol が **5.5× over-stated** (Hartley count ≠ Shannon mutual-info + σ²/σ dimensional error compound)。Honest Shannon $C_{\sigma_*} = \log_2(2\pi) - h(\mathrm{WG}(\sigma_*)) \approx 0.40$ bits/symbol (M1 closed-form + M2 Blahut-Arimoto cross-check, agreement 1.7e-4 bits)。σ\* honest 解釈: "phase channel capacity が ½ bit を切る noise level"。I2 v0.2 patch 6 spot APPLIED。spawned `feedback_capacity_hartley_vs_shannon.md`. | 2026-04-28 |
| OQ-FX7 (T-FX linear-algebra proof) | **PROVED**: nullity(C)=K-rank(B)=b1(G) via Sigma>0 + incidence rank (n-c(G)). research/t_fx_linear_algebra_proof_v0.md. 23/23 numerical PASS (K_n, paths, cycles, disconnected, FX G8, random). T-FX promoted CANDIDATE->PROVED. §3.2 two-component decomp becomes corollary. | 2026-04-15 |
| OQ-FX10 (42-pair autonomy) | **CLOSED, NEGATIVE**: Structural autonomy is G8-locked. h_FX=0 rate 99%→10% on Full_42p. EM subset shows mode h_FX=-1 (peg/intervention → Sigma singular, rank(B Sigma B^T) < rank(B)); Scandi shows mode h_FX=+1 (NOK-SEK co-move → near-empirical rank deficiency). Both failure modes match T-FX regularity clause (Sigma>0). h_FX sign promoted to peg detector. §13.1bis added. | 2026-04-15 |
| OQ-FX11 (destruction + surprise) | **CLOSED, SPLIT**: decor destruction is pre-state dominated, surprise adds nothing (R² 0.695→0.699, ΔAIC+1.7). lambda1 destruction gains materially from I·S interaction (R² 0.414→0.599, ΔAIC−5.59). Promoted D_lambda1 = −0.56 + 3.55·I + 0.12·I·S − 0.56·pre_l1. Sign of §11.6.5 reversed: high-surprise events concentrate, not disperse. §13.2bis added. | 2026-04-15 |
| OQ-FX13 (phase texture bimodal) | **CLOSED, CORRECTED 2026-04-15**: Initial "inverted-bimodal / return-space specific" finding was a lookahead-bug artifact (full-sample P95 threshold in fx_phase_texture_bimodal.py signal_to_trades). After honest expanding-window (min_hist=2000) re-run: Signal A (Gram λ₁ P95 revert) is bimodal saturation-dominated (saturated +2.24 N=19, extremes +1.72 N=26); Signal B (|d(λ₁)/dt|) is genuinely bimodal (struct +0.21 N=94, sat +1.22 N=99, dead-zone flat); Signal C (cluster spread) is the only inverted-bimodal (dead-zone +0.26 N=352). T-BE holds on 4/5 signals — it is a broad spectral-decor law, not return-space specific. Cluster-coupling axis (C) is the single exception, suggesting a secondary destruction regime. §13.6.4 rewritten, Paper B §7.5 v0.3. | 2026-04-15 |
| OQ-FX16 (complementary portfolio) | **CLOSED, REFRAMED 2026-04-15**: Original dead-zone complementary hypothesis REJECTED — Phase_A with dead-zone gate has Sh -1.50 OOS (honest threshold). Unexpected finding: Phase_A with extremes gate (N=16) is a standalone parallel leg to S11_TBE with Sh +1.57, PnL/DD +1.87, both halves + (+1.79/+1.35) — cleanest phase-space strategy yet. Monthly PnL correlation -0.086 (temporally orthogonal, same regime). Combined S11_TBE + PA_extremes yields Sh +0.93 PnL/DD +1.14, BELOW PA alone — S11 half1 loss drags combined equity curve down. §13.6.5 added, Paper B §7.5.1. OQ-FX17 issued (PA_extremes vs S11_TBE dominance question). | 2026-04-15 |
| OQ-FX17 (PA_extremes vs S11_TBE dominance) | **CLOSED, INCONCLUSIVE_PA_PREFERRED 2026-04-15**: bootstrap dominance test (`fx_oq_fx17_dominance.py`, 5000 iter) is underpowered at N_PA=16 / N_S11=26 — both Sharpe 95% CIs span zero (S11 [-1.55, +4.00], PA [-2.09, +4.45]), diff CI [-3.97, +4.49] p(diff≤0)=0.385. Dominance NOT demonstrable by bootstrap alone. HOWEVER walk-forward on calendar midpoint (2018-10-17) is decisive: PA both halves + (+1.787/+1.346), S11 REGIME-DEPENDENT (half1 −1.435, half2 +2.351 — overall Sh +0.895 is half2-driven). Forward pick (train=pre→test=post) = PA→+1.346; backward pick = S11→−1.435. Yearly counts reveal legs fire in DISJOINT YEARS: S11 clusters in 2012/2018/2024 (crisis years), PA in 2011/2020/2022-26 (low-vol / distributed). New character classification: PA = stable leg, S11 = regime-dependent leg. Parallel framing (§7.5.1) retained and strengthened. No archival of S11. OQ-FX18 issued (S11_TBE half1/half2 regime asymmetry investigation). | 2026-04-15 |
| OQ-FX18 (S11 regime asymmetry → stats audit) | **CLOSED, STATS_AUDIT_MAJOR 2026-04-17**: Intended S11_TBE half1/half2 investigation instead uncovered event clustering (N=26 trades / 10 events / 3 days) and wider annualization inflation. `fx_honest_stats.py` built to compute event-level annualized Sharpe Sh_hon = raw_ev * sqrt(events_per_year). Honest values: S11_TBE Sh_hon=+0.205 (was +0.895, inflation 4.37x), PA_extremes +0.262 (was +1.572, 6.00x), PA_dead_zone −0.404 (was −1.500, 3.71x), PA_saturated +0.257 (was +1.448, 5.62x), combined +0.236 (was +0.931, 3.95x). Root causes: (1) OQ-FX16 uses `ANN=sqrt(40)` and `fx_phase_conditioned_portfolio.py` uses `ANN=sqrt(252/2)=11.22`, both assume continuous trading but strategies fire ~1-3 times/year; (2) per-pair trade count treats ~8 cross-sectional basket siblings as independent. Paper B §7.3/§7.5/§7.5.1/§7.5.2 rewritten with honest numbers + legacy strike-through. §11 (§7.6) uses raw per-trade reporting without ANN multiplier — unaffected by this audit. Sign-level findings (bimodal, parallel framing, 4-channel destruction, walk-forward PA robustness) all preserved. OQ-FX19 issued (direct D_full_strict and Signal A/B/C re-measurement with trade-list export). | 2026-04-17 |
| OQ-FX19 (direct D_full_strict + Signal A/B/C honest measurement) | **CLOSED, HONEST_MEASUREMENTS_REPORTED 2026-04-17**: `fx_oq_fx19_direct_measure.py` (wrapper, no modifications to existing scripts) reuses `fx_oq_fx16_portfolio.generate_s11_tbe_trades` for the §7.3 S11 leg, re-implements the S13 CB-date straddle leg from `fx_phase_conditioned_portfolio.py`, and calls `fx_honest_stats.honest_stats_from_trades` for event-level annualization. **§7.3 D_full_strict** (day-bucket events, N_ev=17, EPY=1.27): S11 Sh_hon=+0.205 (was reported +1.59 vs `sqrt(126)` ANN), S13 +0.444 (was +4.88), **combined +0.378** (was +2.14 via OQ-FX19 reproduction, legacy Paper B v0.1–v0.3 quoted +3.60 — inflation ≈ 5.65× vs the reproduced legacy or ≈ 9.5× vs the originally-quoted). Per-event PnL: mean +34 bp, std 101 bp, 64.7% positive, crisis-catching character. **§7.5 Signal A/B/C** (event = entry_idx bucket): Signal A extremes +0.364, saturated +0.522, dead-zone −0.015; Signal B extremes +0.366, saturated +0.490, dead-zone −0.025; Signal C extremes −0.106 (legacy sqrt40 was −0.27, inflation 2.54×), saturated −0.040, dead-zone **+0.197** (C best bucket). Signal B inflation is smallest (~1.8–2.5×) because N=886 gives TPY≈56 ≈ sqrt(40) assumption. **Structural verdict preserved**: Signal A/B bimodal saturation-dominated, Signal C inverted (dead-zone best) but weakened to Δ≈+0.3 between extremes and dead-zone (vs A/B's Δ≈+0.5 saturated vs dead-zone). 4-channel destruction intact. Paper B v0.4 published with §7.3/§7.5 tables populated with event-level honest values. | 2026-04-17 |
| OQ-HC-1 (Arrow 1 蜈ｨ蟆・ｧ) | **5/5 COMPLETE**: HC-1a(tier陦ｨ16萓・ 竏・c Benoist-Ottem霑ｽ蜉, Markman 2022蜿肴丐), HC-1b(HRR 6varieties exact), HC-1c(R-type蛻・｡・竏・R-gauge蜈ｨ豸・ 2=R-topo蜈ｨpersist), HC-1d(T-AAS 15/15 fit, f=f_torsion+f_rational), HC-1e(Voisin蜈ｨQ豸域ｻ・ 隨ｬ3螢∵悴逋ｺ隕・. **Promoted**: T-AAS + f_rational/f_torsion + c_filtration_obstruction.md 竊・L1 | 2026-04-12 |
| OQ-FX-NT-2 (session product) | RESOLVED: additive variance decomposition (f_overlap=0.22, 12pﾃ・5y stable). Residence = ﾂｧ7 covariance (additive), not ﾂｧ8 L-function (multiplicative). Session boundaries robust | 2026-04-12 |
| OQ-YM-1 (mass gap D_floor) | RESOLVED: tier=INTERMEDIATE_FP 蜈ｨSU(N) 荳榊､・mass gap binary indicator遒ｺ螳壹・_floor formal螳御ｺ・c_distortion_floor S4.5/S6.2/S7)縲Ｔingle-channel ﾎｽ DEFERRED(lattice蠕・■) | 2026-04-12 |
| OQ-ﾎｩ2 (ﾎｦ_p twin) | Literal NO (p=5 only), concept YES (莉｣謨ｰ讌ｵ竊担tark unit chain valid, rank 0 verified). Paper_ﾎｩ ﾂｧ4.4 豕ｨ險・| 2026-04-12 |
| OQ5 (base formula) | NEGATIVE: exp(1/dim) fails both domains. Crystal=integer, FX=2^(1/B) with ln2 essential. No closed form; base requires full RMT derivation of B | 2026-04-12 |
| OQ7 (conductor dim) | CONFIRMED: dim(conductor) = # scope-distinct constraint classes. Scalar iff homogeneous scope. Verified: FX(1), Crystal-simple(1), Crystal-complex(2-3), Connectome(竕･3), NT-Artin(3) | 2026-04-12 |
| OQ1 (FX sigmoid) | DISSOLVED: question ill-posed (sigmoid parameters don't exist). c_sﾂｲ=1/2 answered by T1. A/B=竏啼 dissolved with T8. Residual 竊・OQ-T8 | 2026-04-08竊・4-12 |
| OQ6 (230 SG delta_glide) | All 230 validated, promoted to T6 | 2026-04-08 |
| OQ8 (FX dict v4) | FINANCIAL_DICTIONARY_v4.md created | 2026-04-08 |
| OQ-TI-2 (S16 Fejﾃｩr) | S16 ESTABLISHED (A+B+C proved, 6 systems) | 2026-04-11 |
| OQ-FX-NT-3 (h_FX) | h_FX=0 in 85-93% windows (UFD-like market) | 2026-04-11 |
| OQ-FX-NT-6 (cycle conductor) | NEGATIVE: 邃・竓ｬ ﾎｵ (Rﾂｲ=0.04). Liquidity > length | 2026-04-11 |
| S12-S15 chain | All ESTABLISHED. ﾂｧ4 = structural root | 2026-04-10/11 |
| Crystal basics | abs fraction, n_centering, 3-phase YES, abs=1-1/n | 2026-04-07 |
| FX fit | ~~Sigmoid > power law~~ **INVALIDATED**: aggregate bias. Per-trial: power law N_c^{1/3} wins (Rﾂｲ=0.990 vs sigmoid 0.706) | 2026-04-07竊・4-12 |
| AI2 (FX dict v4) | DONE | 2026-04-08 |
| OQ-ﾎｩ4 (ﾎｶ Voronin) | NEGATIVE: triple intrinsic 竊・universality is superficial. Universality = {mult,anal} pair (Euler product + continuation). Dirichlet L, Hurwitz ﾎｶ also universal but not triple intrinsic | 2026-04-12 |
| OQ2 (alpha dim ratio) | CLOSED (ill-posed): alpha is sigmoid local slope varying with N, not fundamental. Crystal has no sigmoid. C4/Wishart crossover already covers B-dependence | 2026-04-12 |
| OQ-ﾎｩ3 (mult noise) | ALREADY KNOWN: T1/T2 separation in NMR. T2 dephasing = E[ﾏ・ﾎｽ)]=0 (spin echo, Hahn 1950). ﾎ｣ﾎｦ contribution = algebraic unification, not new experiment | 2026-04-12 |
| OQ-CG-1 (ﾏ・scanning) | RESOLVED via S12+S15. ﾏЮscan = scan family member #1, Scan螻､ residence. Remaining (R9 formal, gauge morphism) deferred to R9 | 2026-04-12 |
| OQ3 (B stability) | PARTIAL: amp/W converges (~10-12 at n竕･12) but sigmoid B drifts (5.4竊・.47). A/B竊・.13 (竕竏啼). T8 may be small-n. Functional form issue | 2026-04-12 |
| OQ-ﾎｩ1 (directionality) | CLOSED: partial order (Def ﾎｩ.4) already captures structure. Functor formulation adds categorical language without substance. Reopen if compositional law found | 2026-04-12 |
| OQ4-HE1 (enzyme sigmoid) | CLOSED: HE1a (sigmoid AIC test) invalidated 窶・sigmoid form is aggregate artifact. HE1b (A/B=竏啼) dead 窶・T8 SUSPENDED. No ﾎ｣ﾎｦ-specific prediction remains | 2026-04-12 |
| OQ-conn (connectome) | DEFERRED: blocked on real adjacency data. Provisional 3-phase applied (C.elegans F=GAS/M=SOLID, Witvliet=LIQUID). Vector conductor suspected (dim竕･3) | 2026-04-12 |
| OQ-FX-NT-4 (R_FX regulator) | NEGATIVE: corr(R_FX,ﾎｻ竄・=+0.385 窶・regime-dependent, not invariant. Crisis 14.95 > Normal 10.28 > Calm 8.55. h_FX=structural(stable), R_FX=volumetric(crisis-tracking). NT analogy breaks | 2026-04-12 |
| AI1 (Paper I L0 ref) | Added (A0, A5; see L0 canon) to abstract | 2026-04-12 |

## Closed (2026-04-12, speculative trim)

| OQ | Reason |
|---|---|
| OQ-FX-NT-1 (splitting type) | LOW; three_phase_taxonomy already covers classification |
| OQ-FX-NT-5 (Artin factorization) | No theoretical foundation for G_FX; premature |
| OQ-FX-NT-S (class number formula) | Prerequisites incomplete; h_FX竕｡0 trivializes numerator |
| OQ-ﾎｩ5 (2-category directionality) | Merged into OQ-ﾎｩ1 as approach candidate |
| OQ-ﾎｩ8 (count=1 constants) | Catalog exercise, no structural insight expected |
| OQ-ﾎｩ9 (meta-matrix) | Overlaps OQ-ﾎｩ1; gauge-dependence already noted in ﾂｧ5.3 |
| OQ-ﾎｩ10 (intersection value) | No progress path identified |

## Update 2026-04-12 late (Type I/II follow-up)

### Session 2026-04-13 全 OQ 処理結果

**MEDIUM (4件処理)**:
- OQ-BETA-SERIES: milestone 2,3 RESOLVED → LOW. n=2 = math frontier (1970s).
- OQ-KAPPA-LIMIT: κ(2) = 0.43292, √3/4 candidate, float64 limit. §6.7 追記.
- OQ-HC-10: Generic=no exotic (FFT修正). 3 sub-Q. §28.3b 追記. HIGH→MEDIUM.
- OQ-HC-16: Semi-reg 3段障害特定. §28.6b 追記. MEDIUM 維持.

**LOW→CLOSED (3件)**:
- OQ-T8-residual: 3 milestone 全滅 → CLOSED.
- OQ-HC-13: t-structure≈HC circular → CLOSED.
- OQ-BETA-SERIES: → LOW (MEDIUM から格下げ).

**LOW→KEEP (1件)**:
- OQ-HC-14: Spencer-Hodge 未査読 preprint. 査読待ち.

**PARTIAL→維持 (2件)**:
- OQ-HC-15: L1 formal mapping 完了. sign channel は analogical. 部分解決維持.
- OQ-HC-17: 2/3 formal 維持. anal↔depth 2 の formal bridge 未発見. §29 cyclotomic REFUTED.

**残 OPEN OQ summary (2026-04-13 end)**:
- HIGH: なし
- MEDIUM: OQ-KAPPA-LIMIT, OQ-HC-10, OQ-HC-16
- LOW: OQ-BETA-SERIES, OQ-HC-14
- PARTIAL: OQ-HC-15 (L1済/検証残), OQ-HC-17 (2/3 formal)
- CLOSED (new): OQ-T8-residual, OQ-HC-13

---

## Path 2 数論的普遍性 OQ (Paper N3, 2026-04-26 issued)

Paper N3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md` §7.4) で identify された OQ 群。OQ-Ω-Schumann v1 (13/13 gates PASS, ESTABLISHED PENDING) の v1.5 promotion + Hecke-Artin / Hasse-Weil L extension + I-origin canonical scalar formal classification。

### OQ-Schumann-v1.5 (MEDIUM, partial closure 2026-04-28): Type γ formal definition + 6th pre-registered instance

**Source**: Paper N3 §6.1, `research/oq_omega_schumann_v0.md` v1 G13 F4 partial trigger
**Scope**: OQ-Ω-Schumann v1.5 promotion task の 3 sub-component:
- (a) **Type γ formal definition** ✅ **DONE 2026-04-28** (Paper N3 §2.2 定義 2.2): 3-condition formal predicate (i) 同-object proper sub-object fix / (ii) sub-object algebraic distinction / (iii) non-point + non-shadow。Atkin-Lehner W_N の M_k^+ ⊂ M_k(Γ_0(N)) canonical instance 確立、各 level N で independent → countably-infinite Type γ subfamily。N3 v0.5 bump。
- (b) **6th pre-registered instance** (F3-discipline test): theta characteristics on Riemann surfaces (even-characteristic involution の fix locus Θ^+ ⊊ Θ) pre-registered (N3 §2.2 末尾)、D1-D4 hit を independent verify は pending。
- (c) **Axis-2 strong split test**: 4+ Fi instance & 4+ I instance で symmetric strong cross-side split が hold するか。pending。

**Promotion path**: (a) 完了、(b)(c) pending → ESTABLISHED 候補 (要 F1-F4 全 survive + 6+ instances + sub-claim survives F3 pre-reg)

### OQ-Schumann-HeckeArtin-Ext (LOW → MEDIUM, 2026-04-26): Hecke / Artin L extension

**Source**: Paper N3 §7.3 N4 forward, Schumann v1 NEW finding 1 (modular L weight-parametrization countably-infinite)
**Scope**:
- Hecke L-functions (Größencharakter L on number fields) の Path 2 instance status
- Artin L-functions (general Galois rep) の functional equation involution が countably-infinite family を generate するか
- Atkin-Lehner Type γ instance の Hecke / Artin context での analogue

**Status**: candidate (Hecke L が Path 2 instance を提供することは modular L weight-1 case の自然な拡張と推測されるが、formal verification 未完)。N4 (Hasse-Weil L × Stark) で expected to expand。

### OQ-Schumann-HasseWeil-Ext (PARTIAL_RESOLVED 2026-04-26 via Paper N4): Hasse-Weil L extension + SC4 propagation

**Source**: Paper N3 §7.3 N4 forward, §4 Dirichlet L "structural fit only" close
**Original scope**: Hasse-Weil L が Dirichlet L 級と同様 structural fit only か / それとも N2 §3 Paper C-level predictive content の transfer がある別 case か / BSD predictions との connection。

**Resolution (Paper N4 v0.2, 2026-04-26)**: **Dirichlet L "structural fit only" とは異なる結果**:
- Hasse-Weil L weight-2 framework extension が v2 arc 8-stage trajectory で展開、最終 v2 v8 proper AFE library-grade で **K_E(t)·t² → r as t → 0+** (BSD analytic rank の framework-side empirical detector) confirmed (9/10 curves match within 5%, smoothing-artifact diagnosis REJECTED)
- これは N3 Dirichlet L "structural fit only" close とは異なり、**Hasse-Weil L で genuine framework predictive content が transfer する**
- **Framework predictive transfer pattern is weight-class dependent**: weight 1 (Dirichlet L) structural fit only / weight 2 (Hasse-Weil L) genuine (BSD analytic rank detector)
- conductor universality 21/24 PASS at t≥5 (Dirichlet L gap universality 12/12 PASS との analogue)
- BSD predictions connection: K_E(t)·t² → r が analytic rank detector、ただし "BSD 予想を解いた" とは主張せず、analytic rank と geometric rank equality は assumed

**Status**: **PARTIAL_RESOLVED** (Paper N4 で main claim closed, 残 sub-OQ は OQ-BSD-HigherRank に分離)。

**Residence**: Paper N4 §3 (`papers/publication/nt/N4_hasseweil_stark_ja.md`), `c_theorems_master.md` "Hasse-Weil L extension scope" annex, `c_recursive_floor_principle.md §6.8.2`, `nt_dedekind_artin_zeta.md §7.2`。

### OQ-BSD-HigherRank (NEW MEDIUM, 2026-04-26): K_E(t)·t² → r for r ≥ 4

**Source**: Paper N4 §7.4 open frontier, OQ-Schumann-HasseWeil-Ext spawn-off
**Scope**:
- Paper N4 §3 で 10-curve verification は rank 0/1/2/3 を cover (5077a1 rank 3 が highest verified)
- $r \geq 4$ elliptic curves で K_E(t)·t² → r prediction が hold するか
- candidates: rank 4 elliptic curves (LMFDB に rank ≥ 4 curve exist, e.g., conductor ~10⁴-10⁶ region)
- Higher rank computational cost (smoothed AFE は conductor large → truncation budget 増大)

**Promotion path**: r ≥ 4 verification 成功 → BSD analytic rank detection が universal across all ranks (N4 framework content 強化)。

**Status**: OPEN (computational extension task)。

### OQ-433a1-Outlier (NEW LOW, 2026-04-26): 433a1 curve-specific Taylor coefficient anomaly diagnosis

**Source**: Paper N4 §3.3 + `oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md` §6.5
**Scope**:
- 433a1 で K_E(0.3)·(0.3)² = 0.121 vs predicted r = 2 (curve-specific outlier)
- $a_2 = +2$ unusual positive、$|c_2|$ small relative to $|c_3|$ で subleading correction dominates at moderate t
- **Diagnostic test**: t = 0.05 or smaller で K_E·t² → 2 leading-order limit に到達するか empirical verify
- Curve-specific feature であり framework / methodology failure ではないが、systematic 検証 task

**Status**: LOW (curve-specific, not framework critical)。

### OQ-4VertexClosure (NEW MEDIUM, 2026-04-26): Hasse-Weil 4th vertex triangulation formal closure

**Source**: Paper N4 §6.3 4-vertex extension proposal, `meta/triangulation_methodology.md §10`
**Scope**:
- N1 §6 NT-internal Arrow 間 triangulation (3-vertex Paper C / Stark / Brauer) の Hasse-Weil 拡張 (4-vertex)
- Hasse-Weil L の Arrow 焦点 formal 化 (現在 "Arrow 2 + Information BSD" は vague)
- 4-vertex closure proof: S15 + 3 Arrow を exhaustive かつ independent に cover することの formal verify
- §6 inclusion criteria との整合性 check (3+ instance, independent authorship, different vertex)

**Promotion path**: formal 化 → §9 3-vertex ESTABLISHED status を保ったまま §10 4-vertex を ESTABLISHED 昇格、Hecke L extension で 5+ vertex への自然拡張可能性を probe。

**Status**: proposal_v1 (Paper N4 v0.2)。Paper N4 v0.3 task または Paper N5 forward。

### OQ-IOriginFormal (MEDIUM, 2026-04-26): I-origin canonical scalar mechanism formal classification

**Source**: Paper N3 §5.3, `c_arrow_bridge_constants.md §11.6`
**Scope**:
- 3 Arrow canonical constants (π, ln 2, e) の "I-origin" mechanism を sub-class に refine
- Sub-mechanism candidates:
  - **continuous extremal**: e from log x/x extremum (S17), ln 2 from half-value crossing (S13)
  - **continuous measure**: ln 2 from Shannon entropy half-value, e from Boltzmann e^{-x}
  - **continuous topology**: π from S¹ identification (S14), e from R^×_+ exponential
  - **continuous geodesic**: ?
- これら 3-4 sub-mechanism が exhaustive か?
- 各 sub-mechanism に対応する canonical scalar の comprehensive catalog

**Promotion path**: I-origin sub-mechanism formal classification → 3-mechanism partition (Fi-origin Path 2 + 3-4 I-origin sub-classes) で canonical scalar mechanism space が exhaustive coverage される

### OQ-DfloorLProperAnalog (MEDIUM, 2026-04-26): D_floor_L proper multi-parameter fit analog

**Source**: Paper N3 §4.5 v1b v1 REJECTED root cause
**Scope**:
- v1a + v1b 両 naive Taylor approach REJECTED の根本原因 = N-dependent prefactor が NOT absorbed
- Paper C D_floor は **multi-parameter fit** with separate fit coefficients per N → genuine $(s-0.5)^2$ parabolic
- Dirichlet L proper analog: multi-parameter fit version の D_floor_L 構築 + N-sweep + gap-class universality 同時 verify

**Promotion path**: proper analog 構築 → 2-quantity coincide test 再 attempt → Paper C uniqueness が ζ 固有か Dirichlet L へ transfer するかの definitive resolution

### Path 2 OQ summary (2026-04-26 end, post-N4 update)

- HIGH: なし
- MEDIUM: OQ-Schumann-v1.5, OQ-IOriginFormal, OQ-DfloorLProperAnalog, **OQ-BSD-HigherRank** (NEW Paper N4 spawn), **OQ-4VertexClosure** (NEW Paper N4 spawn)
- LOW → MEDIUM (re-priority): OQ-Schumann-HeckeArtin-Ext (Paper N5 expected expansion path)
- LOW: **OQ-433a1-Outlier** (NEW Paper N4 spawn, curve-specific not framework)
- **PARTIAL_RESOLVED (Paper N4)**: OQ-Schumann-HasseWeil-Ext (main claim closed via K_E·t²→r BSD analytic rank detection genuine, sub-OQ are spawned: OQ-BSD-HigherRank + OQ-433a1-Outlier + OQ-4VertexClosure)
- 関連 deferred: OQ-Ω-Schumann-BackAction (LOW, dissipative cavity ↔ ker_backaction, Schumann origin remark)

---

## NT 系列 final closure OQ (Paper N5, 2026-04-27 issued)

Paper N5 (`papers/publication/nt/N5_brauer_origination_ja.md`) で identify された OQ 群。Brauer 障害論詳細 + Origination matrix 8-gauge generalization から spawn。

### OQ-NT-6 (MEDIUM, Paper N1 §6.2 で initially issued, N5 §3.5 で formal scope): Atlas grammar functor formalization

**Source**: Paper N5 §3.5, Stark Atlas grammar Tier-dependent functor uniform construction
**Scope**:
- Tier 1 / 2 / √ / ∞ 各々に対する Atlas grammar entry の uniform construction
- Stark の R-gauge complete representation 定理 (Paper N4 §4.3) を **functorial に extend**
- f_n / phi_phase / N_X / comp_X / observable / residual_type の Tier-dependent specification

**Promotion path**: Tier 1-3+/√/∞ 全 Tier で Atlas grammar functor が construct → R-gauge complete representation 定理 が functorial structure を獲得 → candidate+ promotion。

**Status**: OPEN (Paper N5 v0.2 で task scope acknowledged)。N5 v0.3+ または Q1 (Quantum 観測理論版) との連動 post-N5 task。

### OQ-Tier3-Plus-Search (MEDIUM, NEW 2026-04-27): Tier 3+ multi-rational instance identification

**Source**: Paper N5 §2.4
**Scope**: Tier 3+ form $L(s, \rho) = \prod_i \zeta_{F_i}(s)^{n_i}$ (multi-field rational combination, $n_i \in \mathbb{Z}$) の concrete instance を identify する task。Candidate groups: $S_4 / V_4$ (3-dim irrep), $A_5$ (3/4/5-dim irreps), 一般 non-abelian simple groups higher-dim irrep。

**Status**: OPEN (verified instance 不在、computational search task)。OQ-NT-7 v0.3 sub-OQ として実装可能。

### OQ-Tier-Sqrt-Resolution (MEDIUM, NEW 2026-04-27): Q_8 Tier √ sign obstruction resolution

**Source**: Paper N5 §3.3
**Scope**: $L^2 = 16$ rational だが $L = \pm 4$ sign 外 — sign を representation-theoretic data + ε-factor data から determined する method を identify。Proposed methods: (i) quaternionic descent (ε-factor sign formula) (ii) Deligne-Langlands sign formula (iii) higher derivative $L''(0, \rho)$ で sign determined。

**Status**: OPEN (existence proposal レベル、concrete formula 未確定)。Tier √ structural intrinsic obstruction の workaround。

### NT final closure OQ summary (2026-04-27)

- MEDIUM: **OQ-NT-6** (Atlas grammar functor formalization), **OQ-Tier3-Plus-Search** (NEW), **OQ-Tier-Sqrt-Resolution** (NEW)
- 既 OPEN との関係: OQ-Schumann-HeckeArtin-Ext (Hecke L general extension は Tier ∞ Hecke direct と相性)、OQ-HasseWeil-8Gauge-NewSignature (8-gauge new signature question)、OQ-4VertexClosure (proposal_v2 → ESTABLISHED 昇格 task)。

**NT 系列 N1-N5 全体 OQ 数 (2026-04-27 end)**: 約 15 件 (Path 2 5 件 + N4 spawn 3 件 + N5 spawn 3 件 + 既存 OQ-NT-6/7/8 + 関連 deferred)。NT closure は achieved だが full formal closure は OQ residue として N5 v0.3+ / Q1-Q3 forward / future N に分散。

---

## Q-series final closure OQ (Papers Q1-Q3, 2026-04-27 issued)

NT N1-N5 closure と同日達成された Q1-Q3 量子系列 (Q1 framework header + Q2 Open QS chain extension + Q3 Born-Gleason final closure, 計 1325 行) の OQ summary。Q-series cumulative で **proposal_v1 3 件 + OPEN 6 件 + Q-series future Q4-Q6 candidate** を発生。

### OQ-Born-1 (MEDIUM, NEW 2026-04-27): Representation-independent Born derivation

**Source**: Paper Q3 §3.4
**Scope**: Busch-Gleason 定理 (PRL 2003) は Hilbert space + density operator framework に依存。L0 axioms から direct に C\*-algebra 上の "Born form" を derive する **representation-independent route** 存在問題。

**Connection**: OQ-QSM1-Refined (KMS from L0 A0c, proposal_v1) と類縁問題 — 両者とも L0 → operator algebra embedding の technical gap を共有、同時 closure が L0 framework の operator algebra-level rigorous 化に必要。

**Status**: OPEN。Q-series future 候補。

### OQ-σ\*-1 (LOW, NEW 2026-04-27): σ\* universality beyond Gaussian

**Source**: Paper Q3 §4.3
**Scope**: σ\* = √(2 ln 2) は Gaussian phase noise + half-amplitude convention の合流で derive (`transformation_atlas/sheet_A_amplitude/sigma_star.md`)。Gaussian 仮定外で σ\* analog 存在? heavy-tail Lévy noise / non-stationary noise / multi-modal noise distribution。Gaussian 特性関数 form 破綻 domain で half-amplitude convention $E[\cos Z] = 1/2$ を解いて生じる threshold は σ\* universality test。

**Status**: OPEN。EEG empirical verify (`sheet_A_amplitude/sigma_star.md` Entry 2) では非ガウス性が帯域平均で相殺 (subject-band averaged std ≈ 0.0012)、より extreme non-Gaussian noise (heavy-tail, fractal) regime で σ\* form 不変性は test 課題。Q-series future 候補。

### OQ-MBQ1 (MEDIUM, NEW 2026-04-27): 4-stage chain 5th algebraic class candidate

**Source**: Paper Q2 §7.3
**Scope**: many-body stage S4 が 4-stage chain final closure を提供するか (= Q1 §5 T-AAS 4-class が many-body context で 5+ class extension を持つか)? Candidate 5th class: Topological order (anyon braiding, Q1 §7 next candidate listed) / Strongly-correlated regime (Z = 0 non-Fermi liquid) / Quantum spin liquid。

**Status**: OPEN (Paper Q2 §7.2 で topological order を 1 件 explicitly identify、formal class 化は future)。

### OQ-QSM1-Refined (proposal_v1, Paper Q2 §3 expansion 2026-04-27): KMS as L0 A0c quantum instance

**Source**: Paper Q2 §3 + `q_quantum_statistical_mechanics.md §2.5.1` annex
**Scope**: Tomita-Takesaki modular flow $\sigma_t = \Delta^{it} A \Delta^{-it}$ を bridge とする L0 A0c (multi-window compatibility) → KMS condition derivation。Schematic chain: L0 A0c (compatibility) ⟹ modular flow consistency at $\beta_1, \beta_2$ ⟹ KMS condition。

**Gap**: Step 2 → 3 (L0 compatibility translation to modular flow consistency) が rigorous でない — L0 A0c は state-level compatibility, modular flow consistency は operator algebra automorphism consistency、両者間に "embedding L0 → operator algebra" が必要 (現 L0 axiom 範囲では不足)。

**Connection**: OQ-Born-1 と同根の technical gap (L0 → operator algebra embedding)、両者同時 closure 必要。

**Status**: proposal_v1 (Paper Q2 §3.3, `q_quantum_statistical_mechanics.md §2.5.1` formal 化済)。元 OQ-QSM1 (`q_quantum_statistical_mechanics.md §10`) を proposal レベルに昇格。

### OQ-OQS1-Refined (proposal_v1, Paper Q2 §5 expansion 2026-04-27): Pointer basis Einselection as dynamical L0 A3

**Source**: Paper Q2 §5
**Scope**: decoherence による pointer basis 選択は L0 A3 (gauge invariance) の **動的 version**: 静的 gauge (observer choice) → 動的 gauge (environment selection)。Q1 §5.2 4 static algebraic class (C₁-C₄) が **Q2 dynamical environment-selected class** に lift。$[|i\rangle\langle i|, H_{int}] \approx 0$ が dynamical gauge condition。

**Status**: proposal_v1 (Paper Q2 §5.2 主張 5.1)。L0 A3 reformulation (static + dynamic 2 mode 拡張) rigorous formulation は OQ-OQS1 future work。

### OQ-OQS2 ✅ ESTABLISHED 2026-04-28: Lindblad dissipator = error_projection (generator-level canonical bijection)

**Source**: `q_open_quantum_systems.md §4.3 + §9 OQ-OQS2` / Paper Q2 §5.3
**Scope**: Lindblad equation $d\rho/dt = -i[H_{eff}, \rho] + D[\rho]$ の Unitary part (reversible, error_arithmetic) + Dissipative part (irreversible, error_projection)。Kraus decomposition $\Phi(\rho) = \sum_k K_k \rho K_k^\dagger$ が L0 error decomposition の CPTP realization candidate。

**Resolution (定理 5.1, Paper Q2 §5.3 v0.3 2026-04-28, `research/oq_oqs2_kraus_l0_bijection_v0`)**: **honest dual answer** — bijection は **generator (superoperator) level で canonical**、**Kraus operator level で mixed**。

| L0 error class | Lindblad generator term |
|---|---|
| error_arithmetic | $\mathcal{L}_H \rho = -i[H,\rho]$ (skew-adjoint, system-intrinsic, reversible) |
| error_projection | $\mathcal{D}\rho = \sum_k \gamma_k(L_k \rho L_k^\dagger - \tfrac{1}{2}\{L_k^\dagger L_k, \rho\})$ (system-bath split-dependent, irreversible) |
| error_noise | thermal $\bar n_k(\beta)$ inside $\gamma_k$ (T → 0 で vanish) |

**Kraus level caveat**: $K_0(dt) = I - i H_\text{eff} dt + O(dt^2)$ with $H_\text{eff} = H - (i/2)\sum_k \gamma_k L_k^\dagger L_k$ bundles unitary phase + anticommutator damping → Kraus operators 個別では partition 不可。

**Closest-unitary diamond-norm corollary**: $\|\Phi_{dt} - U_*^{(dt)}\|_\diamond = \|\mathcal{D}\| dt + O(dt^2)$、$U_*^{(dt)} \to \exp(\mathcal{L}_H dt)$ as $dt \to 0$。元 attack route を corollary として recover。

**Numerical verification**: pure dephasing ($H=(\omega/2)\sigma_z$, $L=\sigma_z$) + amplitude damping ($H=0$, $L=\sigma_-$) で V1/V2/V3 = **3/3 PASS** (Kraus reconstruction = exp($\mathcal{L}t$) to ~$10^{-16}$)。

**Spawned 3 successor OQs**: OQ-OQS2-NonMarkovian (memory kernels) / OQ-OQS2-DiamondNorm-Proper (proper SDP) / OQ-OQS2-MultiJump (d ≥ 3)。

### OQ-Q-MBQ-Reverse-Arrow (proposal_v1, Paper Q2 §7 2026-04-27): Quasiparticle Z = Arrow 1⁻¹ obstruction monotone

**Source**: Paper Q2 §7
**Scope**: Landau Fermi liquid quasiparticle weight $Z = |\langle k|\psi_q\rangle|^2 \in (0, 1]$ は Arrow 1⁻¹ "generation" operation (Q1 §4.6) の many-body context での residual obstruction monotone。$Z = 1$: trivial (free, Arrow 1 invertible) / $Z \in (0, 1)$: partial (interacting, lossy) / $Z = 0$: full (non-Fermi liquid, breaks)。T-AAS lens: $Z < 1$ は ker_topo > 0 の many-body instance。

**Status**: proposal_v1 (Paper Q2 §7.1 主張 7.1)。BCS pairing instability + topological order anyon braiding の many-body Arrow 1 kernel dynamical structure として OQ-MBQ1 と connected。

### Conjecture 4a.2 (OPEN, Paper Q1 §5.4): Depth parallel quantitative form

**Source**: Paper Q1 §5.4 + `c_filtration_obstruction.md §8.5.4`
**Scope**: 古典 Hodge $f_{\mathrm{rational}}^{\mathrm{Hodge}}(X, p) \widetilde{=} \log_2(\dim(\mathrm{Hdg}^p / \mathrm{im\ cl}) + 1)$ と量子 unified $M_{\mathrm{unified}}^C = -\log_2 F_C$ の typical scale O(1) 比例関係 conjecture。

**Status**: OPEN (Conjecture)。古典側 counterexample 不在で current vacuous trivial parallel、(1) sparsity-matching formal definition (2) "typical scale" probability measure (3) 古典 Hodge counterexample 存在の 3 要件依存。

### Q-series future Q4-Q6 candidates

| 候補 paper | 主題 | Status |
|---|---|---|
| **Q4** 量子 8-gauge framework | N5 §4 origination matrix 8-gauge family の量子 instance (axis-1 D 5 + axis-1 C 3 family の量子 specialization) | OPEN, Q-series future |
| **Q5** QFT extension | 量子場論 (CFT / Wilsonian RG / regularization framework) の S15 residence | OPEN, Q-series future |
| **Q6** 量子重力 framework | 重力 + 観測理論 (background-independent observation, holographic principle) | OPEN, Q-series future |

### Q-series final closure OQ summary (2026-04-27)

- **MEDIUM (NEW)**: OQ-Born-1 (representation-independent Born), OQ-MBQ1 (4-stage 5th class)
- **LOW (NEW)**: OQ-σ\*-1 (σ\* universality beyond Gaussian)
- **proposal_v1 (Q-series formalize)**: OQ-QSM1-Refined (KMS L0 A0c), OQ-OQS1-Refined (pointer basis dynamical A3), OQ-Q-MBQ-Reverse-Arrow (quasiparticle Z)
- **OPEN (Q1 既存)**: Conjecture 4a.2 (depth parallel quantitative form)
- **OPEN (Q2 既存)**: OQ-QSM2 (algebraic FDT), OQ-QSM3 (ln 2 beyond qubit)
- **ESTABLISHED 2026-04-28**: OQ-OQS2 (Kraus error decomposition → 定理 5.1 generator-level canonical bijection + 3 successor OQ spawn)
- **future Q4-Q6 candidate**: 量子 8-gauge / QFT extension / 量子重力

**Q-series Q1-Q3 全体 OQ 数 (2026-04-27 end)**: 約 12 件 (Q3 spawn 3 件 + Q1/Q2 既存 + proposal_v1 3 件 refined + Q-series future 3 candidate)。Q-series 3-paper minimum closure は achieved だが full formal closure は OQ residue として Q-series future Q4-Q6 / NT-Q dual framework future / L0 → operator algebra embedding 等の **N1-N5 ↔ Q1-Q3 dual framework cross-domain joint task** に分散。

**N1-N5 + Q1-Q3 dual framework total OQ 数 (2026-04-27 end)**: NT 約 15 件 + Q-series 約 12 件 = **計 27 件**。Paper D 多領域版 + 2 dual framework header (NT, 量子) + dual framework parallel structure (`meta/triangulation_methodology.md §13`) で **観測理論 universal validity 2-domain anchor** 達成、residual OQ は future framework extension の forward task として queued。

---

## I-series Information theory OQ (Papers I1-I2, 2026-04-28 issued/closed batch)

Paper I1 (Information framework header v0.3) + I2 (Communication theory v0.2) で identify された OQ 群。**2026-04-28 verification audit batch**: 4 closures (P1 honest Shannon / S17 docs fix / Renyi parametric scan / Algorithmic f_rational) + 3 successor OQ spawn。

### OQ-P1-Capacity ✅ CANDIDATE_RESOLVED_NEGATIVE 2026-04-28: σ\* phase-channel honest Shannon capacity

**Source**: Paper I2 §4.4 spawn / `papers/publication/information/I2_communication_theory_ja.md:220` 主張 4.1 v0
**Resolution (`research/oq_p1_capacity_v0.md`)**: published $C_{\sigma_*} \approx 2.18$ bits/symbol は 2 issues で **5.5× over-stated**: (a) Hartley level count を Shannon mutual-info capacity と取り違え、(b) denominator が dimensional に $\sigma_*^2$ (variance) → $\sigma_*$ (linear width) であるべき。Honest Shannon capacity $C_{\sigma_*} = \log_2(2\pi) - h(\mathrm{WG}(\sigma_*)) \approx 0.40$ bits/symbol (M1 closed-form + M2 Blahut-Arimoto cross-check, M=512 で agreement 1.7e-4 bits)。σ\* honest 解釈: "wrapped-Gaussian phase channel capacity が ½ bit/symbol を切る noise level"。
**I2 v0.2 patch APPLIED 2026-04-28**: §0 abstract M3 + §4.2 主張 4.1 + §4.4 + §9.1 anchor (e) row + §11 P1 row + §11.3 観察 11.3.2 の 6 spot 修正 + 変更履歴 entry 追加。
**Spawned feedback rule**: `feedback_capacity_hartley_vs_shannon.md` (capacity claim は両 axis (Hartley count / dimensional units inside log) check 必須)。

### OQ-S17-Codebook-3-Universal ✅ ESTABLISHED 2026-04-23 (docs fix 2026-04-28): codebook argmax = 3 universality

**Source**: Paper I1 §4.3 / §8.3
**Resolution**: Paper I1 §8.3 OQ 表 OPEN → ESTABLISHED 整合修正。実体は `research/oq_omega_obs_3_e_arrow3_v0.md` で 2026-04-23 に S17 promotion gate 5/5 PASS で確立済 (3 setting NT/Codebook/Qudit + gauge invariance 3 base)。Paper I1 v0.2 patch (S17-Codebook-3 OPEN → ESTABLISHED + spawn successor OQ-S17-Density-Form-Universal)。
**Successor OPEN**: OQ-S17-Density-Form-Universal (どの info-theoretic 設定で関連 density が $d(n)=\log n/n$ form を取るかの classification)。

### OQ-Renyi-Scaffold-Continuous ✅ ESTABLISHED 2026-04-28: Rényi α-family parametric scan

**Source**: Paper I1 §3.3 / §8.3
**Resolution (Paper I1 §3.3 定理 3.3.1)**: Rényi α-family $\{H_\alpha\}_{\alpha \in [0, \infty]}$ は scaffold-emergence axis の continuous parametric scan、4 anchor (α=0 Hartley scaffold-base / α=1 Shannon transition / α≥2 collision 3+ proper / α=∞ min-entropy worst-case) + 系 3.3.2 (monotone non-increasing per van Erven & Harremoës 2014)。`c_information_theory.md §1.5` Theorem 1.5.1 + Corollary 1.5.2 として L1 dictionary に backward。

### OQ-Algorithmic-f_rational ✅ ESTABLISHED 2026-04-28: Theorem 4a.1 algorithmic instance

**Source**: Paper I1 §5.2 / §8.3 / `c_information_theory.md §8`
**Resolution (Paper I1 §5.2.1 定理 5.2)**: $f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B)$ in bits、Theorem 4a.1 unified $M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B} = -\log_2 F_C \asymp K(x|B)$ via Solomonoff prior。Class $C^{\mathrm{alg}}_B$ = computably-encodable distributions given $B$、convex closure + class-preserving operations 両方 ✓。Properties: gauge-asymptotic invariance (Kolmogorov invariance) + reducible by structural conditioning + provably > 0 for generic $x$ + uncomputable but per-string finite。**Framework 内 f_rational instance 中、最強の "obstruction provably non-zero AND non-computable" 例**。`c_information_theory.md §8.5` Theorem 8.5.1 として L1 dictionary に backward。
**5 instance + V1 + V2 = 7/7 PASS** (`research/oq_algorithmic_f_rational_v1.py`、$|x|=65536$ bits、$K_{\mathrm{upper}} = \min(\mathrm{gzip}, \mathrm{bz2}, \mathrm{lzma})$)。Rate range [0.0067, 1.003] = 5 orders of magnitude。
**Spawned 3 successor OQs**: OQ-Alg-MDL-Tightness (MEDIUM, $K_{\mathrm{upper}}^{\mathrm{MDL}} - K(x|B)$ tightness) / OQ-Alg-Hodge-Parallel (LOW, Conjecture 4a.2 5th data point) / OQ-Alg-Quantum-Cross (MEDIUM, $K(\rho)$ via tomography → Q1 4-class bridge)。

### OQ-I-Bekenstein-Extension (OPEN, Paper I1 §6.5 spawn): 6th anchor for 5-anchor info limit theorem

**Source**: Paper I1 §6.5 / §8.3
**Scope**: Bekenstein bound $S \leq 2\pi RE/\hbar c$ + Margolus-Levitin $\Delta t \geq \pi\hbar/2E$ を I1 §6 5-anchor framework に追加して **6-anchor** に拡張。Q-series Q6 future (量子重力) と並行で gravity / relativistic processing speed 込み。
**Status**: OPEN (gravity scope outside)、Q-series Q4-Q6 future と joint。

### I-series final closure OQ summary (2026-04-28 end)

- **ESTABLISHED 2026-04-28 (4 件)**: OQ-S17-Codebook-3-Universal (docs fix) / OQ-Renyi-Scaffold-Continuous (定理 3.3.1) / OQ-Algorithmic-f_rational (定理 5.2) / OQ-OQS2 (定理 5.1, Q-series cross-link)
- **CANDIDATE_RESOLVED_NEGATIVE 2026-04-28**: OQ-P1-Capacity (5.5× inflation correction, I2 v0.2)
- **OPEN (本論 spawn)**: OQ-I-Bekenstein-Extension (gravity, Q-series Q6 future)
- **OPEN (本論 spawn 2026-04-28 successors)**: OQ-S17-Density-Form-Universal (form classification) / OQ-Alg-MDL-Tightness / OQ-Alg-Hodge-Parallel / OQ-Alg-Quantum-Cross
- **OPEN (Conjecture 4a.2 cross-link)**: depth parallel quantitative form (Q1 §5.4)

**I1-I2 全体 OQ 数 (2026-04-28 end)**: 約 9 件 (4 ESTABLISHED + 1 CANDIDATE_RESOLVED_NEGATIVE + 4 spawned successors + 1 Bekenstein future)。

**N1-N5 + Q1-Q3 + I1-I2 triple framework total OQ 数 (2026-04-28 end)**: NT 約 15 件 + Q-series 約 12 件 + I-series 約 9 件 = **計 36 件**。Paper D 6-domain triangulation + **3 framework header + content paper triple anchor** (NT N1-N5 / 量子 Q1-Q3 / 情報 I1-I2) で観測理論 universal validity 完成、residual OQ は future framework extension の forward task として queued。

**Spawned feedback rules (2026-04-28 batch)**:
- `feedback_capacity_hartley_vs_shannon.md`: capacity claim は Hartley count ≠ Shannon mutual-info、dimensional units inside log() check 必須 (P1 σ\*-channel 5.5× inflation 由来)
- `feedback_structural_match_at_correct_level.md`: bijection 主張は operator/generator/Choi/diamond 等 algebraic level を pin (OQ-OQS2 Kraus level mixed / generator level clean 由来)

