---
axis: meta
position: theorem_index
updated: 2026-04-25 late (v1b v1 multi-gap N-sweep REJECTED + G3 gap universality 12/12 byproduct PASS: v1b v0 "Paper C (log N)² dimensional match" was single-N coincidence — N-sweep revealed super-(log N)² scaling, σ_min drift 0.51→0.59 away from 0.5, R² degradation 0.98→0.78; Paper D v0.9.2 remains frozen (backport policy scope verdict change blocked); Paper C uniqueness preserved more strongly)
---

# Theorems Master List

## Theorem-level (exact, derivable)

| ID | Statement | Domain | Axioms | Status | Ref |
|---|---|---|---|---|---|
| T1 | abs_centering = 1 - 1/n for centering order n | Crystal | A0,A5 | PROVED | c_group_theory.md |
| T2 | N_constraint = C(n,2) - (n-1) for n-currency FX | FX | A0 | PROVED | nt_conductor.md |
| T3 | z+1/2 Wyckoff pairing creates l-odd absences at h-k=0 mod 3 for P6_3/mmc | Crystal | A0 | PROVED | c_group_theory.md |
| T4 | Sigmoid is the general envelope; power law is local slope | General | A5 | PROVED (calculus) | c_scaling_laws.md |
| T5 | N_eff = b竄・G) = K - M + 1 for observation graph G with K edges, M vertices | FX | A0 | PROVED (graph theory, first Betti number) | nt_conductor.md |
| T6 | abs(h) = abs_cent + C竄・h + C竄・hﾂｲ + ...; glide->codim 1 (alpha->1), screw->codim 2 (alpha->2) | Crystal | A0,A1,A2 | PROVED (h_max=4..32, 9 SGs, running alpha converges to integer codim) | L4/crystal_errors |
| T7 | E[K(tau)] = (N_cﾂｲ + N_s)/N for tau >> 1, where N_c structural zeros form coherent cluster | General | A0,A3 | PROVED (algebraic: c_spectral.md ﾂｧ4; Monte Carlo: n=3..10, error < 0.02%) | c_spectral.md ﾂｧ4 |
| T8 | ~~Boltzmann codim weight: exp(-c_sﾂｲﾂｷcodim) with c_sﾂｲ=1/2; gives A/B=竏啼 for sigmoid scaling~~ | **General** | A0,A1,A3,A5 | **RETIRED (2026-04-12)** 窶・aggregate estimation bias (Jensen 1.8-3.1x) invalidates A/B=竏啼, sigmoid, A=18.2, B=10.8. c_sﾂｲ=1/2 unaffected (竊探1). Per-trial: amp/W~竏哮ﾂｷf(ﾎｳ) (BBP corollary). Boltzmann codim target unknown 竊・OQ-T8-residual. Legacy sealed: research/t8_redefinition_draft_v0.md | c_scaling_laws.md ﾂｧ1.4 |

## Theorem candidate (2026-04-08, empirically confirmed)

| ID | Statement | Evidence | Domain | Status | Ref |
|---|---|---|---|---|---|
| T-FX | n_zero(corr_matrix) = K - rank(M) = b竄・G). Near-zero eigenvalue count = first Betti number of currency graph | r=0.9998, mode r=1.0, 128 subsets, 0 failures | FX | **CANDIDATE** (needs pure LA proof) | fx_dictionary_v1.md ﾂｧ3.1 |
| P-FX | spectrum 竕・ﾎｴ(0)ﾃ傭竄・+ MP(K-b竄・ T). Two-component decomposition, no free params | r=0.991, RMSE=0.12 | FX | **PROPOSITION** | fx_dictionary_v1.md ﾂｧ3.2 |

| T-KD | K(ﾏ・ Decorrelation Depth. **Strong** (b竄≫翁5): |corr_dip|<0.04, invariant across universe (6/6), regime (3/3 Crisis/Calm/Normal), freq H1. **Boundary** (b竄・3): conditional, fails K竕､7 or D1. T5/E-hFX 13/13 invariant (3-chain). Rejected: ﾏЮdipﾃ湧_eff=const (CV=0.39), P6 cycle length (negative). | 30 subsets + 13-config stress test (universeﾃ羊egimeﾃ庸req), bootstrap 500, surrogate | FX | **CANDIDATE** (Strong T-KD ready for external review. Boundary T-KD conditional. Failures: G4 b竄・3 |corr|=0.69, D1 b竄・5 |corr|=0.17 marginal) | research/t_gauge_ktau_theorem_v0.md |
| E-hFX | h_FX := |{ﾎｻ < threshold}| 竏・b竄・竕・0 in 85窶・3% of windows (gap/0.05 threshold). FX market is UFD-like: zero-mode count = b竄・exactly, no friction-induced extra modes. h_FX=1 in 7窶・5% (ﾎｻ竄・threshold crossing). Regime-independent (r=+0.065 vs ﾎｻ竄・. Integer plateau: only {0,1} observed. | 1994 windows, 16y H1, 12 pairs, threshold scan + regime split + temporal blocks | FX | **CANDIDATE** (NT analogy: h_K=1 竊・UFD. Supports T-KD: stable b竄・is prerequisite for decorrelation. Rejected: crisis 竊・h_FX increase is negligible r=0.065) | L3/fx_number_theory_bridge.md ﾂｧ2.1, applications/market/fx_nt_p3_class_number_real.py |
| E-P6neg | Cycle length 邃・does NOT predict arbitrage residual ﾎｵ. ﾎｱ=0.45ﾂｱ0.48, Rﾂｲ=0.04. All cycles have ﾎｵ竕・bps (spread-dominated). 邃・4 < 邃・3 (liquidity effect). FX has no wild ramification 窶・all cycles effectively unramified. | 22 cycles (邃・3..5), 10k samples each, 16y H1 | FX | **NEGATIVE RESULT** (NT ramification hierarchy does not apply to FX. Pair liquidity, not cycle length, determines residual quality) | L3/fx_number_theory_bridge.md ﾂｧ4.3, applications/market/fx_nt_p6_cycle_residual.py |
| T-GA | **Gauge-invariant exponent**: D_floor(0.5, N) = A_M * N^{-alpha} where alpha(0.5) is M-independent (CV=2.35%, 7 M values) but A_M is M-dependent (CV=74%). D_floor absolute level varies 4x with M at ALL s including s=0.5. The gauge-invariant quantity is the decay EXPONENT alpha, not D itself. kappa_g remains exactly gauge-free (CV=0%). | 7 M values, 10 N values (10^6~10^9, 3 decades), g=2. alpha mean=0.677, CV=1.60%. CV decreases monotonically with N range (4.3%->1.6%), suggesting CV->0 as N->inf | NT | **CANDIDATE** (alpha gauge-invariance confirmed at CV<2%, improving with N range. D(0.5) gauge-invariance REFUTED. Guard: M >= 1000 for shape stability) | paper2_twin_dictionary_bridge_v0.md §11.4, c_alpha_decay_exponent.md §5 |

## Empirical-level (strong fit, derivation OPEN)

| ID | Statement | R^2 | Domain | Axioms | Status | Ref |
|---|---|---|---|---|---|---|
| ~~E1~~ | ~~amp/Wishart = 18.2*(1-2^(-N_c/10.8))~~ | ~~0.9992~~ | ~~FX~~ | | **RETIRED: superseded by T-FX + P-FX** | |
| E2 | c_rank is best scalar conductor for crystals | 0.9485 | Crystal | A0 | FITTED | nt_conductor.md |
| E3 | Three-phase classification holds in crystal (GAS/LIQUID/SOLID) | N/A | Crystal+FX | A0,A1 | VALIDATED | L3 |
| E4 | Three-phase classification holds in connectome (GAS/LIQUID/SOLID) | N/A | Connectome | A0 | PRELIMINARY | L2/connectome |

## Conjectures (untested or partially tested)

| ID | Statement | Status | Priority |
|---|---|---|---|
| C1 | FX A=18.2 and B=10.8 derivable from algebraic structure | **REOPENED (2026-04-12)**: T8 SUSPENDED 窶・A=18.2, B=10.8 are artifacts of biased aggregate estimation. Per-trial scaling is amp/W ~ (ﾏ/3)ﾂｷN_c^{1/3} (power law, no saturation) | HIGH |
| C2 | base = exp(1/dim(constraint_space)) in continuous systems | OPEN | MEDIUM |
| C3 | Connectome maps to three-phase classification | PRELIMINARY (E4) | MEDIUM |
| C4 | alpha is determined by constraint_dim / target_space_dim | PARTIALLY RESOLVED (c_W exponent from A0+A1+A2, see scaling_laws ﾂｧ1.5) | HIGH |
| C5 | Conductor vector dimension = number of constraint homogeneity classes | OPEN | LOW |
| C6 | Observable type (count vs dispersion) is determined by constraint algebra (discrete vs continuous) | OPEN | HIGH |
| C7 | There are no true power laws in constrained systems 窶・only sigmoids in limited ranges | OPEN | MEDIUM |
| ~~C8~~ | ~~Crystal bulk/glide amplitude ratio approaches sqrt(e)~~ | **SUSPENDED (2026-04-12)**: c_sﾂｲ = 1/2 analytically confirmed (T1), but T8 application (A/B = 竏啼) is SUSPENDED 窶・aggregate estimation bias invalidates the numerical verification. The crystal analytic proof of c_sﾂｲ = 1/2 stands; the Boltzmann codim ratio claim does not. | |

## C1 resolution (2026-04-08, REOPENED 2026-04-12)

~~C1 is CLOSED.~~ **C1 REOPENED (2026-04-12)**: T8 SUSPENDED due to aggregate estimation bias 窶・see T8 status note above. The FX sigmoid parameters A, B were derived assuming:

    c_sﾂｲ = 1/2                          (T1 corollary: centering coherence)
    A/B = exp(c_sﾂｲ) = sqrt(e)           (T8: Boltzmann codim weight)
    B = f(c_W(K))                       (RMT Wishart fluctuation, crossover regime)
    A = B * sqrt(e)                     (exact, up to ~2% from c_W(K) drift)

The chain T1 -> T7 -> T8:

**T1 corollary** (c_s = 1/sqrt(2)):
The N_c structural zeros form a coherent orbit under the triangular arbitrage
subgroup. The interference factor satisfies c_sﾂｲ = E[cosﾂｲ(pi*phi)] = 1/2,
the exact FX translation of T1's centering interference (1 + exp(2pi*i*h.t)).

**T7** (cluster mean):
E[K(tau)] = (N_cﾂｲ + N_s)/K, with amplitude decomposition
amp_FX = (2*N_c/K) * c_s = sqrt(2) * N_c/K.

**T8** (Boltzmann codim weight):
At the saddle point of the trial-averaged form factor, each codimension
level carries weight exp(-c_sﾂｲ * codim):
  codim 0 (bulk/cluster):    weight = 1          -> determines A
  codim 1 (boundary/signal): weight = exp(-1/2)  -> determines B
  A/B = exp(c_sﾂｲ) = sqrt(e)

The only non-universal quantity is B, which inherits the Wishart bulk-edge
crossover exponent (see C4). This is not an incompleteness of T8 but a
statement that B belongs to a different universality class than c_s and A/B.

**Numerical verification** (fx_dict_c1_cs_precision.py, fx_dict_c1_AB_sqrt_e.py):
  c_s = 0.7061 +/- 0.004   vs  1/sqrt(2) = 0.7071   (0.14% match)
  A/B = 1.65 +/- 0.18      vs  sqrt(e)   = 1.6487    (0.08% match at T=100)
  Both verified across T=40..2000 and n=4..10.

**Cross-domain confirmation (C8 RESOLVED)**: Crystal systems share the same
c_sﾂｲ = 1/2, proved analytically. For any non-symmorphic element with translation
t having a half-integer component: E[cosﾂｲ(ﾏ hﾂｷt)] = 1/2 (integer h implies
hﾂｷt is half-integer, cosﾂｲ alternates 0/1 equally). This is EXACTLY the same
T1 mechanism as FX. T8 is confirmed as a 2-domain (General) theorem.

Note: sqrt(e) does NOT appear as a raw observable ratio (e.g. abs_cent/C竄・.
It enters through the Boltzmann saddle structure of the generating function.
Script: crystal_c8_sqrt_e.py.

**Status: SUSPENDED (2026-04-12)**
The numerical verification A/B 竕・竏啼 is invalidated by aggregate estimation bias
(Jensen's inequality: averaging K(ﾏ・ curves inflates amp/W by 1.8-3.1x via
differential noise cancellation). Per-trial estimation shows amp/W ~ N_c^{1/3}
(power law, no saturation, Rﾂｲ=0.990), not a sigmoid. The parameters A=18.2, B=10.8
are artifacts of fitting a biased aggregate to a wrong functional form.

The theoretical principle (Boltzmann codim weighting with c_sﾂｲ=1/2) remains
structurally motivated but its application target is unknown 窶・it does NOT govern
raw eigenvalue ratios (observed decay ~exp(-0.05k) vs predicted exp(-0.5k)).

c_sﾂｲ=1/2 itself is unaffected (T1 parity derivation is independent).
Scripts: fx_dict_c1_bias_test.py, fx_dict_c1_functional_form.py,
oq_t8_bbp_codim_synthesis.py, oq_t8_codim_series.py.

## Supplementary results (proved, not main theorems)

| ID | Statement | Domain | Status | Ref |
|---|---|---|---|---|
| S1 | ﾏ・ﾏ・ = ﾎｶ'(2ﾏ・/竏・(1+ﾎｶ(2ﾏ・)ﾂｷﾎｶ''(2ﾏ・); c-matrix 3D蜈ｱ蛻・淵縺ｮ逶ｸ髢｢. Monotonic, no stationary point. | General | PROVED (analytic + numerical p竕､997) | c_spectral.md ﾂｧ7 |
| S2 | Var(Im)/Var(Re) = (ﾎｶ(2ﾏ・-1)/(1+ﾎｶ(2ﾏ・); ﾏ・1 縺ｧ (ﾏﾂｲ-6)/(ﾏﾂｲ+6) | General | PROVED (same) | c_spectral.md ﾂｧ7 |
| S3 | (1+ﾎｶ(2ﾏ・) 縺ｮ "1" 縺ｯ諱堤ｭ牙・ g=1 縺ｮ Var(Re) 蟇・ｸ・| General | PROVED | L0/identity_asymmetry.md |
| S4 | Origination matrix (8ﾃ・): 8 螳壽焚 ﾃ・8 gauge, intrinsic/auxiliary/absent. e,ﾎｦ=single intrinsic (蟇ｾ讌ｵ). ﾎｶ,ﾏ・ﾎｳ,i_add=triple intrinsic (邨仙粋邨・ｹ・ | General | CONFIRMED (numerical, all primes 竕､ 997) | Paper ﾎｩ, constants_origin.py |
| S5 | i double origin: additive i requires 4\|L (p=2), multiplicative i requires 4\|ﾏ・L) (p竕｡1 mod 4). Independent conditions, same i=竏・1. | General | PROVED (order distribution exact match: L=15015 vs 30030) | Paper ﾎｩ, arithmetic_quartet.py |
| S6 | ﾏ・ is purely additive-side: multiplicative noise kills non-trivial characters (E[ﾏ・nu)]=0). Erasure channel threshold ﾎｵ=1/2 is universal. No multiplicative analog of ﾏ・. | General | PROVED (character orthogonality) | Paper ﾎｩ, i_double_origin_test.py |
| S7 | Class number formula = 6-gauge 遨榊・隗｣. Res ﾎｶ_K(1) = (2^r竄・ｷ(2ﾏ)^r竄つｷh_KﾂｷR_K)/(w_Kﾂｷ竏喀|d_K\|). 6 蝗蟄・(ﾏ, 2, d, h, R, w) 縺・Paper_ﾎｩ 蜈ｨ gauge 鄂ｲ蜷・{addZ,mult,char,cont,geom,anal} 縺ｫ 1:1 蟇ｾ蠢・ rank 0 Stark case, 6 factor 蜈ｨ exercise 貂・(邃・ 邃・i), 邃・竏・), 邃・竏・), 邃・竏壺・5)). H-stark-1 candidate+. | Number Theory | ESTABLISHED (Dirichlet-Hecke, ﾎ｣ﾎｦ 隱ｭ縺ｿ譁ｰ隕・ | c_spectral.md ﾂｧ8, research/stark_projection_v0.md |
| S8 | Artin conductor = constraint codim sum: f_p(ﾏ・ = ﾎ｣_i (\|I_i\|/\|I_0\|) codim(V^{I_i}). conductor_count rule 縺ｮ謨ｰ隲也沿縺ｧ縺ゅｊ縲ゝ6 縺ｮ glide/screw codim 髫主ｱ､縺ｨ structural 蜷悟ｽ｢. unramified竊団odim 0, tame竊団odim 1, wild竊団odim 竕･2. 迚ｹ谿翫こ繝ｼ繧ｹ: 閾ｪ譏手｡ｨ迴ｾ ﾏ・1 縺ｧ N(ﾏ・ = \|d_K\| 竊・S7 縺ｮ 竏喀|d_K\| 蝗蟄舌ｒ邨ｱ荳蜻ｽ蜷・ | Number Theory | ESTABLISHED (standard Artin theory, ﾎ｣ﾎｦ 蜷悟ｽ｢縺ｯ譁ｰ隕・ | nt_conductor.md ﾂｧ6, c_spectral.md ﾂｧ8.3, research/stark_projection_v0.md |

| S9 | Artin factorization: ﾎｶ_H(s) = 竏柔ﾏ・L(s,ﾏ・H/k)^{dim ﾏ±. Dedekind zeta of Galois extension decomposes by irreps via regular representation. | Number Theory | ESTABLISHED (standard, residence 譁ｰ隕・ | nt_dedekind_artin_zeta.md ﾂｧ1 |
| S10 | Intermediate field zeta: ﾎｶ_F(s) = 竏柔ﾏ・L(s,ﾏ・^{筺ｨﾏ・ Ind 1筺ｩ}. Permutation character determines factorization; dim ﾏ／{G_F} = multiplicity. Bridge to tier classification (Tier 1/2/3/竏・. | Number Theory | ESTABLISHED (standard, tier bridge 譁ｰ隕・ | nt_dedekind_artin_zeta.md ﾂｧ2 |
| S11 | Symplectic root number forced +1 (Deligne): ﾎｽ(ﾏ・=-1 筺ｹ W(ﾏ・=+1. Magnitude/sign split: field data (h,R,w) determine \|L(0,ﾏ・\| or L(0,ﾏ・ﾂｲ, root number W(ﾏ・ determines sign. Independent data sources. Orthogonal ﾏ・ W(ﾏ・竏・ﾂｱ1} free, carries arithmetic parity. | Number Theory | ESTABLISHED (Deligne, ﾎ｣ﾎｦ residence split 譁ｰ隕・ | nt_root_numbers.md ﾂｧ3-4 |
| S12 | Exponential Scan Family: **scan observables** (scanner 螟画焚繧呈戟縺､繝代Λ繝｡繝医Μ繝・け譌・ share kernel template exp(a(scanner)ﾂｷb(data)). Additive scan (imaginary axis, Sﾂｹ rotation): K(ﾏ・, F(h), U(t). Multiplicative scan (real axis, exponential damping): ﾎｶ(s), Z(ﾎｲ), c(ﾏЮcov). ﾏ・ 縺ｯ蜉豕補・荵玲ｳ・bridge (Gaussian average)縲６nified residence: scanner variables live in L-3 evaluation via specialization. **Scope**: scan observable 縺ｮ縺ｿ縲Ｔtructural / information observable 縺ｯ S12 scope 螟・(竊・S15 Observable Trichotomy 蜿ら・)縲・| Cross-domain / Meta | ESTABLISHED (dictionary structural catalog; scope boundary 譏守､ｺ 2026-04-11) | research/tau_internal_coordinate_v0.md ﾂｧ4.4 |
| S13 | ln 2 Fixed-Point Principle: S12 **荵玲ｳ・scan only** (scope: ﾎｶ(s), Z(ﾎｲ), c(ﾏЮcov)) 縺ｮ蜊雁､譚｡莉ｶ e^{-x}=1/2 筺ｹ x=ln 2 縺・characteristic scale 繧呈ｱｺ螳壹ょ刈豕・scan 縺ｯ \|e^{iﾎｸ}\|=1 諱堤ｭ峨〒蟇ｾ雎｡螟悶ぱ・=竏・2ln2), Landauer kT ln 2, Shannon H(1/2)=ln 2 縺ｯ蜷御ｸ縺ｮ辟｡谺｡蜈・婿遞句ｼ上・逡ｰ縺ｪ繧・instance縲Ｎ-ary: e^{-x}=1/m 筺ｹ x=ln m縲・*Guards**: (1) 謖・焚驛ｨ縺ｯ蟶ｸ縺ｫ辟｡谺｡蜈・ (2) "1/2" 縺ｮ謫堺ｽ懃噪諢丞袖縺ｯ instance-dependent (single-kernel-term half-weight 縺悟・騾壽歓雎｡), (3) Dirichlet 2^{-s}=1/2筺ｹs=1 縺ｯ ﾎｶ 縺ｮ讌ｵ縺ｨ縺ｯ蛻･莠玖ｱ｡. OQ-QTD3 partial resolution 蛟呵｣懊・| Cross-domain / Meta | ESTABLISHED (3 guards 譏守､ｺ, scope closed, 6-member systematic check done, m-ary 譌｢蟄倡｢ｺ隱肴ｸ・ 蜈ｨ 3 譏・ｼ譚｡莉ｶ CLOSED 2026-04-10) | research/tau_internal_coordinate_v0.md ﾂｧ4.6 |
| S15 | Observable Trichotomy: 霎樊嶌蜀・・蜈ｨ observable 縺ｯ 3 謗剃ｻ也噪繧ｯ繝ｩ繧ｹ縺ｫ蛻・｡槭＆繧後ｋ縲・*(A) Scan** = exp(a(scanner)ﾂｷb(data)) kernel 繧呈戟縺､繝代Λ繝｡繝医Μ繝・け譌・(S12 蟇ｾ雎｡, 6+1 member)縲つｧ4 dual 縺ｮ蜉豕・荵玲ｳ戊ｻｸ縺後◎縺ｮ縺ｾ縺ｾ scan 霆ｸ縲・*(B) Structural** = parameter-free 謨ｴ謨ｰ/菴咲嶌逧・ｸ榊､蛾㍼ (b竄・ h_K, codim, n_centering, f_p(ﾏ・, abs=1-1/n 遲・縲Ｔcanner 螟画焚縺ｪ縺励つｧ4 dual 縺御ｽ懃畑縺吶ｋ遨ｺ髢薙・ discrete skeleton (谺｡蜈・・菴肴焚繝ｻrank)縲・*(C) Information** = -ﾎ｣ p log p 蝙・(H, S(ﾏ・, D_KL, I(X;Y), H_ﾎｱ 遲・縲４12 family 縺ｮ log-inverse (Z竊巽竊担 chain)縲つｧ4 dual 縺ｮ諠・ｱ逧・ｰ・ｽｱ縲・*螻､髢捺磁邯・*: Scan竊担tructural 縺ｯ kernel 縺ｮ螳夂ｾｩ蝓滓ｧ矩 (譬ｼ蟄先ｬ｡蜈・ graph topology)縲４can竊棚nformation 縺ｯ log-exp duality (partition function 竊・free energy 竊・entropy)縲４tructural竊棚nformation 縺ｯ combinatorial counting (log cardinality = Hartley entropy)縲・| Cross-domain / Meta | **ESTABLISHED** (蜈ｨ 3 譏・ｼ譚｡莉ｶ CLOSED 2026-04-11: 竭HE1 enzyme 譁ｰ繝峨Γ繧､繝ｳ繝・せ繝・PASS 窶・scan/structural/information 蜈ｨ螻､縺ｫ observable 蟄伜惠 (蜉豕・scan 譛ｪ蜷悟ｮ壹〒迚・・螳悟・) 竭｡螻､髢捺磁邯・Arrow 1-3 + 蜿ｯ謠帶ｧ譚｡莉ｶ 蠖｢蠑剰ｨ倩ｿｰ貂・(ﾂｧ5.5) 竭｢S12/S13/S14 謨ｴ蜷・formal verification 螳御ｺ・窶・S12竓４can(閾ｪ譏・, S13=Arrow 2 蝗ｺ螳夂せ(cross-layer), S14 髱槫ｯｾ遘ｰ=Scan 螻､蜀・vs Arrow 2 縺ｮ residence 蟾ｮ (ﾂｧ5.6)) | research/bidirectional_duality_v0.md ﾂｧ5 |
| S16 | Fejﾃｩr Absorption Trichotomy: ﾏЮscan 縺ｯ ﾂｧ4 (邃・common receptacle) 縺ｮ add竊芭ult 譫ｶ讖九ｒ **蠎ｧ讓呎ｧ矩縺ｫ蜀・鳩** 縺吶ｋ縲・*S16-A** (蠢・ｦ∝香蛻・: K(ﾏ・=Fejﾃｩr 筺ｺ 遲蛾俣髫斐・ 邉ｻ讀懆ｨｼ (HO, Ising exact; rotor, box, phonon standard fp; hydrogen deep fp)縲・*S16-B** (fingerprint completeness): K(ﾏ・ 縺ｯ spectrum 縺ｮ complete fingerprint (autocorrelation theorem)縲・*S16-C** (all-or-nothing, proved): N竏狸(m)=4ﾏﾂｲﾎｵﾂｲmﾂｲNﾂｷVar(ﾎｴ)+O(ﾎｵﾂｳ) 竊・莉ｻ諢上・髱櫁・譏取曹蜍輔′ Fejﾃｩr peak 繧堤ｴ螢翫‥eparture 縺ｯ ﾎｵﾂｲ quadratic縲１olynomial spectra 縺ｯ蜊ｳ蠎ｧ縺ｫ鬟ｽ蜥・(all-or-nothing)縲・auss sum corollary: rigid rotor K(integer)=2 for even N縲・*蜷ｸ蜿主・鬘・4 tier**: (1) 螳悟・蜷ｸ蜿・(equispaced, RMS=0, HO/Ising), (2) standard fingerprint (divergent spacing, RMS~0.1, rotor/box/phonon), (3) deep fingerprint (convergent spacing, RMS~0.36, hydrogen), (4) Wick residual (1-operation overlay, ﾏ・・-iﾎｲ/2ﾏ)縲・*蜷ｸ蜿弱＆繧後↑縺・ｂ縺ｮ**: 蜉帛ｭｦ(t), 蠅・阜(W), 蟇ｾ遘ｰ諤ｧ鄒､蛻・｡・ 髱槫庄謠帶ｧ矩, 菴咲嶌逧・ｸ榊､蛾㍼縲・*莠悟ｱ､驕狗畑蜑・*: tier = 讒矩蛻・｡・(coarse, 3 bin), ﾎｽ = 閾ｨ逡梧─蠎ｦ (continuous)縲ら嶌霆｢遘ｻ/crossover 縺ｯ ﾎｽ-first, tier-second縲・sing 2D strip: tier 荳榊､峨□縺・ﾎｽ(T) 縺・T_c 霑大ｍ縺ｧ螟牙喧縲らｵ仙粋螳牙ｮ壽ｧ: x_e 竊・N_bound 竊・tier (STANDARD竊棚NT竊奪EEP竊呈ｶ域ｻ・縲・eeman: degeneracy lift 縺ｧ DEEP竊棚NT (STANDARD 縺ｫ縺ｯ蛻ｰ驕斐＠縺ｪ縺・= 豺ｷ蜷域ｧ矩縺ｮ髯千阜)縲・*驕狗畑蜑・(confirmed by periodic table v2, Z=1-36)**: 髱咏噪豈碑ｼ・・ tier 蜆ｪ蜈・(RMS/N vs radius r=+0.38), 閾ｨ逡梧､懷・縺ｯ ﾎｽ 蜆ｪ蜈・(ﾎｽ vs radius r=+0.08 = flat)縲・*Window declaration 蠢・・*: 蜷御ｸ邉ｻ縺ｧ繧・valence/core+valence/unique/full 縺ｧ tier 縺檎焚縺ｪ繧・(Carbon: valence=INT, core+valence=DEEP)縲８indow 譛ｪ螳｣險縺ｮ豈碑ｼ・・ AMBIGUOUS縲・| Cross-domain / Meta | **ESTABLISHED** 窶・3-layer evidence: **(i) Mathematics**: S16-A proved + 2 exact systems, S16-B autocorrelation theorem, S16-C formal proof + 6-digit numerical verification. **(ii) Empirical**: 10 molecules (NIST/Herzberg), GOE nuclear resonances (238-U scale), phonon mono/diatomic, Rydberg series; x_e 竊・tier correspondence established. **(iii) Physical chain**: thermal bridge K(ﾏ・竊短(ﾎｲ)竊辰_v(T)竊達(T)竊箪|F(hkl)\|ﾂｲ validated (Einstein exact match, Debye Tﾂｳ law, DW factor); tier predicts C_v onset shape. Figure-backed: 31-system quantum ladder, periodic table Z=1窶・6, 6 captioned figures. | c_phase_complex.md ﾂｧ4, research/tau_vs_integer_lattice_v0.md ﾂｧ4-ﾂｧ19, research/tau_absorption_*.py (4 scripts), research/s16_quantum_ladder*.py, research/s16_periodic_table.py, research/s16_real_spectra_test.py, research/s16_thermal_bridge.py, runtime/s16_apply.md |
| S14 | Parity Midpoint Duality (ﾏ, ln 2): S12 縺ｮ 2 霆ｸ荳翫・ parity 蝗ｺ螳夂せ譚｡莉ｶ縺・**髱槫ｯｾ遘ｰ dual pair** 繧呈・縺吶ゆｹ玲ｳ・ e^{-x}=1/2 筺ｹ x=ln 2 (隗｣譫千噪 parity, 蛟､縺ｮ髢ｾ蛟､)縲ょ刈豕・ e^{iﾎｸ}=-1 筺ｹ ﾎｸ=ﾏ (莉｣謨ｰ逧・parity, Sﾂｹ torsion)縲・*Guard 4 蛻・梵**: codomain involution (z竊ｦzﾌ・/ x竊ｦ1-x) 縺ｮ蝗ｺ螳夂せ縺ｨ縺励※驛ｨ蛻・噪縺ｫ邨ｱ荳蜿ｯ閭ｽ縺縺後≫р conjugation 縺ｯ ﾏ 繧堤函繧縺・ln 2 繧堤函縺ｾ縺ｪ縺・竊・讖滓ｧ九・髱槫ｯｾ遘ｰ縺梧悽雉ｪ逧・Ｑhase_complex ﾂｧ4 縺ｮ ﾎｹ_L(莉｣謨ｰ)/ﾏ・蛟､) dual 縺ｨ謨ｴ蜷医Ｎ-ary: (2ﾏ/m, ln m) 縺ｧ髱槫ｯｾ遘ｰ讒矩縺ｯ m-invariant縲・e,i) pair 縺ｯ bridge 豌ｴ貅悶・ dual 縺ｧ縺ゅｊ S14 豌ｴ貅・(parity scaffold) 縺ｨ縺ｯ蛻･螻､ 窶・S14 縺ｯ parity scaffold 縺ｮ unique pair縲・| Cross-domain / Meta | **ESTABLISHED** (蜈ｨ 3 譏・ｼ譚｡莉ｶ CLOSED 2026-04-10: 竭ﾂｧ4謨ｴ蜷・ﾎｹ_L(莉｣謨ｰ)/ﾏ・隗｣譫・縺ｮ parity 蟆・ｽｱ縺ｨ縺励※螳悟・謨ｴ蜷・竭｡莉門ｮ壽焚pair=(e,i)縺ｯ bridge 豌ｴ貅悶〒蛻･螻､, parity 豌ｴ貅悶〒縺ｯ unique 竭｢m-ary=(2ﾏ/m, ln m)縺ｧ髱槫ｯｾ遘ｰ菫晏ｭ・ | research/tau_internal_coordinate_v0.md ﾂｧ4.6 dual parity note, c_phase_complex.md ﾂｧ4 (structural root) |

| S17 | Arrow 3 e-extremum (Information Density Fixed-Point): Arrow 3 (Structural → Information, H_0(D) = log\|D\|) 上で info density d(n) := H_0/\|D\| = (log n)/n は n = e で gauge-invariant global max を取り、max d = 1/e。任意 base b > 0 (b ≠ 1) で d_b'(n) = 0 ⇔ n = e が成立し極値位置は base 非依存 (極値 value のみ base-dependent)。**Format shift**: S13 (Arrow 2 ln 2) は value-fixed (e^{−x} = 1/2 level-set crossing)、S17 (Arrow 3 e) は derivative-fixed (d'(n) = 0 extremum) — 両者は「Arrow 上 scalar-valued functional の stationary point」として統一 framework に吸収。**3 domain universality**: NT prime density log(N)/N continuous argmax ≈ e / codebook ternary bits-per-symbol log n/n integer argmax = 3 / qudit single-shot capacity log d/d integer argmax = 3。(e, i) bridge-water pair の Arrow 3 specialization = e itself (Arrow 1/2 では infrastructure として作用、Arrow 3 で顕在 scalar 値)。S15 bidirectional duality 3 Arrow canonical constants (π, ln 2, e) を完備化。| Cross-domain / Meta | **ESTABLISHED** (2026-04-23: 3 gate all closed — Gate 1 gauge invariance formal proof [c_arrow_bridge_constants.md §5.2] + 3 base sweep numerical \|Δ − e\| < 2e-5, Gate 2 cross-domain empirical verification [research/oq_omega_obs_3_info_density_check.py 5/5 PASS: NT continuous + codebook integer + qudit integer all argmax = 3 = ⌊e⌉], Gate 3 S14 / (e,i) bridge-water specialization L1 記述 [c_arrow_bridge_constants.md §6]) | c_arrow_bridge_constants.md §5 (primary), research/oq_omega_obs_3_e_arrow3_v0.md, research/oq_omega_obs_3_info_density_check.py |

| T-OG-4.1a | Observation-optimal gauge theorem (layer separated form): observation domain D において Arrow 1⁻¹ が Structural target を最精密に復元する gauge は 2 layer に分離される — Information layer = Arrow 2 S13 半値固定点 (ln 2, α̅=0.5, s=1/2)、Structural layer = Arrow 1 domain 固有 arithmetic / dynamical。 | Cross-domain / Meta | **ESTABLISHED** (2026-04-22 Paper E Structural main scan 9900 samples + Path 1-4 全達成, 2026-04-24 Paper F 4th instance [13/13 organism split] 追加で empirical base 4 倍化) | c_observation_optimal_gauge.md §2.1, Paper_D §4.5.1 |
| T-OG-4.1b | Coincidence condition (系 4.1b): 両 layer balance 同一 gauge coincidence は functional-equation 型 structural enforcement が存在するときに限る。Paper C ζ(s) = ζ(1−s) 唯一確認 instance。4-instance taxonomy (2026-04-24 Paper F 追加): Paper C coincide / Paper 2 Type II locus split / Paper E Type III stoch split / Paper F Type II biological locus split。 | Cross-domain / Meta | **ESTABLISHED** (2026-04-22) | c_observation_optimal_gauge.md §2.2, Paper_D §4.5.1 |
| T-OG-4.1c | Balance position agreement test form (系 4.1c, v0.9 honest reformulation 2026-04-23): coincide/split binary verdict は axis-2 Fi/I 上の balance position agreement。3 realization type (point / locus / stochastic ensemble) × type-dependent agreement criterion。真の 2-category lift は OQ-Ω5 open task に分離 (2026-04-24 v1 で σ-action groupoid framework partial closure)。 | Cross-domain / Meta | **ESTABLISHED as operational predicate** (2026-04-23), **theoretical grounding via OQ-Ω5 v1 2026-04-24** (定理 4.3.1 + 4.4.1) | c_observation_optimal_gauge.md §6, Paper_D §4.5.1b, research/oq_omega5_2cell_v0.md §4.3, §4.4 |
| T-Ω5-4.3.1 | σ-action groupoid functor lift theorem (unconditional): domain D が involution σ_D (σ_D² = id) を持つとき、operational constant map T_Arrow_i^D を Obs^σ(D) 上の σ_D-equivariant functor F_i に lift する path が存在する ⟺ g_i^D ∈ Fix(σ_D)。Paper C instantiation: Fix(σ_D : s ↦ 1-s) = critical line {1/2 + it : t ∈ ℝ}。**"2-cell witness" vocabulary 廃止 → "σ-action groupoid functoriality witness" に正名** (literal-check で degenerate fail 解消)。 | Cross-domain / Meta | **PARTIAL CLOSED v1** (2026-04-24, ΣΦ 独自 path, OQ-Ω5c partial closure) | research/oq_omega5_2cell_v0.md §4.3, c_observation_optimal_gauge.md §6 |
| T-Ω5-4.4.1 | s = 1/2 unique pinning (conditional theorem): assumption A (D_floor parabolic minimum at s = 1/2, Paper C §3 ESTABLISHED unconditional) + assumption B (RH, unproved) の下で、g_I^D = g_S^D = 1/2 (Paper C coincide derivation を 2 段で formal closure)。RH 不成立下では g_S^D が critical line 外 escape 可能 ⟹ coincide verdict conditional → split transition (本 series 初の RH-dependent verdict variation 具体 instance)。 | Cross-domain / Meta | **CONDITIONAL** (2026-04-24, RH + Paper C §3 依存、Paper C coincide unconditional 化は v1.5+ task) | research/oq_omega5_2cell_v0.md §4.4 |
| T-Ω5e-v15 | Dirichlet L(s, χ) 1st predictive instance (OQ-Ω5 v1 §4.5 item 1): 5/5 real primitive χ (χ_{-3}, χ_{-4}, χ_5, χ_{-7}, χ_8, conductor 3-8)、D_C (untruncated log\|Λ\|²) asymmetric-grid σ_min = 0.500000 exact + R² = 1.000。Symmetry-forced tautology concern (§7.3 self-audit, symmetric-grid + real χ functional eq. で b ≈ 0 identically forced) を §7.4 asymmetric-grid sanity check で refuted — Λ(s, χ) real-axis parabolic minimum が σ = 1/2 に locked is genuine structural content, not grid-symmetry-forced。Paper C §3 D_floor pattern を Dirichlet L に lifting する first numerical instance。 | NT / Cross-domain | **CONFIRMED** (2026-04-24 earlier, with caveat-acknowledged self-audit; mpmath mp.dps=30, script runtime ~30 sec) | research/oq_omega5_v15_dirichlet_l_first_instance_v0.md §7-§8, experiments/dirichlet_l_balance_v0.py |
| T-Ω5e-v15-cplx | Dirichlet L(s, χ) complex primitive extension (OQ-Ω5 v1 §4.5 item 1 extension): 5/5 complex primitive χ (mod 5 ord 4 / mod 7 ord 3 / mod 7 ord 6 / mod 9 ord 3 / mod 11 ord 5、4 conductors × 4 orders × parity mix)、C1-C4 全 PASS including NEW C4 functional eq sanity gate (\|F(σ, χ̄) − F(1-σ, χ)\| max < 1e-8, actual 0 exact). **SC3 post-write catch**: v0 §1 "F not σ-symmetric for complex χ" claim は incorrect — real-axis restriction では functional eq (|Λ(σ, χ)\| = |Λ(1-σ, χ̄)\|) + complex conjugation (conj(L(σ, χ)) = L(σ, χ̄) for real σ ⟹ |L(σ, χ̄)\| = |L(σ, χ)\|) chain で F(σ, χ) = F(1-σ, χ) は complex χ にも成立、asymmetric grid では tautology refute 不可。Genuine non-tautological content 保持: (a) C3 curvature > 0 (min vs max/saddle distinction), (b) C4 functional eq 0 exact, (c) ε(χ) phase non-trivial for complex χ, (d) D_A(0.5) scaling differentiated from real case。 | NT / Cross-domain | **CONFIRMED with SC3 caveat** (2026-04-24 mid, framework extends to all primitive Dirichlet χ; **SC4 supersedes SC3**: off-axis test also tautological via universal complex conjugation identity — see T-Ω5e-v15-offaxis row) | research/oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md §7-§8, experiments/dirichlet_l_balance_complex_v0.py |
| T-Ω5e-v15-offaxis | Dirichlet L(s, χ) off-real-axis 2D scan (OQ-Ω5 v1.5 v1): 8 chars (5 complex + 3 real) × 11 t ∈ [0, 30] × 9 σ asymmetric = 792 Λ evaluations。G1 80/80 (σ_min(t) ∈ [0.30, 0.70] off-axis) + G4 8/8 (off-axis functional eq sanity 0 exact) PASS。G2 0/5 + G3 0/5 FAIL on complex χ (pre-registered "Step 2 fail off-axis" completely refuted). **SC4 CRITICAL post-execution catch** (feedback rule 3-phase 3rd phase empirical validation): SC3 derivation incomplete — conj(L(σ+it, χ)) = L(σ-it, χ̄) は n real positive の coefficient conjugation identity として complex s 全域で成立 (on-axis/off-axis 問わず)、combined with functional eq で \|Λ(σ+it, χ)\| = \|Λ(σ-it, χ̄)\| = \|Λ(1-σ+it, χ)\| を ALL (σ, t) real で force。**σ_min = 1/2 は universal functional equation identity-level consequence**, NOT σ-action groupoid framework-specific predictive content on Dirichlet L。Framework predictive scope post-SC4 reassessment: Paper C Information (D_floor independent) + Structural (RH zeros) の 2-quantity independent coincide が genuine content、Dirichlet L extension は "structural fit only"。 | NT / Cross-domain | **INCONCLUSIVE with SC4 caveat** (2026-04-24 evening, framework predictive scope boundary established; single-quantity identity ≠ framework content; v1a 2-quantity test は v1.5 v1a で実行 → REJECTED) | research/oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md §7-§8, experiments/dirichlet_l_balance_offaxis_v1.py |
| T-Ω5e-v15-2quantity | Dirichlet L 2-quantity independent coincide test (OQ-Ω5 v1.5 v1a, post-SC4 genuine framework test attempt): 5 complex primitive χ × 8 t ∈ {0.5, 2, 5, 8, 12, 16, 22, 28} × 9 σ asymmetric = 360 L + 360 Λ evaluations。Q1 = \|L(σ+it, χ)\|² σ_min (bare L, NOT functional-eq-forced) + Q2 = \|Λ(σ+it, χ)\|² σ_min (completed, = 0.5 via SC4 identity) の coincide test。**REJECTED**: G2 gate (\|Q1 - 0.5\| < 0.1 for ≥70% cells) actual **17.5%** (below pre-registered rejection threshold 30%)、Q1 mean deviation 0.60-0.82 from 0.5 across 5 χ (max 3.2). **Post-execution root cause** (3-phase 3rd phase 2nd empirical validation): \|L\|² = \|Λ\|² / ((q/π)^{σ+a} · \|Γ((s+a)/2)\|²) の denominator が strongly σ-growing (exponential + Stirling) ⟹ \|L\|² σ_min は σ > 1 direction (Dirichlet series convergent regime) に push、0.5 center unwarranted。Paper C D_floor (gap-indexed prime sum residual for normalized log L expansion) は 0.5-centered parabolic by construction、一方 \|L\|² 単独は normalization 不在。**Framework scope for Dirichlet L definitively closed as "structural fit only"** — naive \|L\|² Information analog insufficient、proper D_floor_L analog (v1.5 v1b future task) required for genuine extension。 | NT / Cross-domain | **REJECTED** (2026-04-24 evening late, pre-registered rejection criterion met cleanly; 5th stage of same-day 5-stage progression v0-v1-v1a + SC1-SC4 catches) | research/oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md §5-§6, experiments/dirichlet_l_balance_2quantity_v1a.py |
| T-Ω5e-v15-dfloor-prime-v0 | Dirichlet L D_floor proper analog via prime partial sum (OQ-Ω5 v1.5 v1b v0, minimal diagnostic post-v1a REJECTION): 3 complex primitive χ (q=5 ord=4, q=7 ord=3, q=11 ord=5) × 9 σ asymmetric on N = 10⁵ (π(N) = 9592). Construction: S_χ(s, N) = Σ_{p≤N, gcd(p,q)=1} χ(p)·log(p)/p^s (Dirichlet-weighted log-prime sum); D_prime(s, χ, N) = \|S_χ(s) - ideal_1st(s)\|² / \|S_χ(0.5)\|² where ideal_1st(s) = S_χ(0.5)·(1 - (s-0.5)·⟨log p⟩) is 1st-order Taylor expansion around σ=0.5. **CONFIRMED with partial-by-construction caveat**: G1 parabolic R² ≥ 0.9 3/3 (R² 0.96-1.00), G2 \|σ_min - 0.5\| < 0.1 3/3 (drift 0.01-0.05), G3 curvature c > 0 3/3 (c ≈ 76-99), G4 T asymmetry 3/3. **Genuine empirical content post-audit**: (a) σ_min drift 0.01-0.05 from 0.5 (finite-N higher-order Taylor correction measurement), (b) parabolic R² 0.96-1.00 (2nd-order dominance empirically confirmed, non-trivial), (c) **curvature c ≈ ⟨log p⟩² = 108 dimensional match to Paper C (log N)² prediction** (Paper C derivation: curvature ∝ κ · ⟨log p⟩² via PNT), (d) SC4 universal chain 外 (prime sum only, no functional eq identity trap). σ_min location partially by construction (Taylor center) BUT curvature scaling + parabolic R² are genuine beyond construction-triviality. **Positive signal for v1b v1 full multi-gap D_floor_L_gap implementation** (next priority, includes N-sweep scaling verification + Paper C Corollary 3.3 critical line analog test). | NT / Cross-domain | **CONFIRMED-at-single-N (retrospectively reframed as single-N artifact after v1b v1 N-sweep REJECTED)** (2026-04-25, 6th stage of v1.5 progression; primary content was reported as Paper C-type Taylor residual shape return, but v1b v1 N-sweep revealed curvature super-(log N)² scaling + σ_min drift away from 0.5, retrospectively v1b v0 "dimensional match" was single-N coincidence) | research/oq_omega5_v15_dirichlet_l_dfloor_prime_sum_v1b.md §5-§6 + superseded by v1b v1 N-sweep finding in `oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md` |
| T-Ω5e-v15-dfloor-multigap-v1 | Dirichlet L D_floor multi-gap N-sweep (OQ-Ω5 v1.5 v1b v1): 3 complex primitive χ × 4 N ∈ {10⁴, 10⁵, 10⁶, 10⁷} × 3 gap classes {2, 4, 6} × 9 σ asymmetric = 324 S_g evaluations + aggregates. **Test hypothesis (rejected)**: Paper C empirical form c(s, N) = κ · (log N)² · (s-0.5)² で curvature c / ⟨log p⟩² should be **constant** across N. **Actual**: c / ⟨log p⟩² ratio is N-dependent (0.46 → 0.67 → 1.02 → 1.63 across N = 10⁴ → 10⁷), **super-(log N)² scaling**; σ_min drifts 0.51 → 0.59 **AWAY from 0.5** with N growth; R² degrades 0.98 → 0.78. Pre-registered G2 gate ((log N)² scaling ±25%) 0/3 FAIL. **Verdict**: **REJECTED** (primary hypothesis). **Post-execution root cause**: Taylor residual construction uses **fixed linear reference** = S(0.5) × (1 - (s-0.5)⟨log p⟩) — N-dependent prefactor NOT absorbed, higher-order Taylor corrections grow with N, residual minimum drifts. Paper C D_floor uses **multi-parameter fit** with separate fit coefficients per N, absorbing prefactor → genuine (s-0.5)² parabolic. **Construction mismatch** = why v1b v0/v1 naive Taylor approach fails. **POSITIVE BYPRODUCT**: **G3 gap-class universality 12/12 PASS** (max/min ratio < 1.15 across all cells) — Paper C multi-gap invariance pattern IS structurally reproduced on Dirichlet L side (genuine extension fragment preserved). **Framework scope for Dirichlet L (post-v1b v1)**: structural fit + gap universality confirmed; predictive content via naive Taylor residual REFUTED; **Paper C uniqueness preserved MORE STRONGLY** (naive paths failed twice: v1a + v1b); proper D_floor_L analog requires multi-parameter fit = v1b v2 future task. **Lesson (rule refinement)**: single-N dimensional match is insufficient for scaling law claim; N-sweep pre-registration should be mandatory. | NT / Cross-domain | **REJECTED + G3 byproduct PASS** (2026-04-25 late, 7th stage of v1.5 progression; backport policy first test: Paper D v0.9.2 frozen維持, scope verdict change blocked, sync to extension log only) | research/oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md §5-§6, experiments/dirichlet_l_dfloor_multigap_v1b_v1.py |
| T-F-F1 | Analytical gauge absorber theorem (Paper F §3): SNR(f=1/3) ≈ (N/9) · S/(0.693·W), γ := S/W (codon bias gauge invariant / composition gauge の ratio)。**10-organism formula universality ±5% across 108× genome scale (5.4 kb → 580 kb) × 6 biology domains** (動物/菌類/植物/原生/ciliate/virus/prokaryote)。γ = gauge³ direct instantiation (Paper D §6.3.1)。formula は biology-neutral mathematical identity candidate (§4.2)、"biology" は γ 値 realization にのみ localize。4 TRUE break modes catalog formal (§4.3: W=0 deterministic repeat / S=0 non-3-period / deterministic 3-harmonic / long-period repeat)。 | DNA / Biology / Cross-domain | **CONFIRMED** (2026-04-23 Round 1-2, 2026-04-24 Paper F v2 hardening via 5-round phase-space exploration) | papers/Paper_F_DNA_ja.md §3, L2/dna_dictionary_v0.md |

| T-AAS | Algebra-Analysis Surjectivity Template: ker(Arrow 1) = ker_gauge + ker_topo. f(phi) = f_torsion + f_rational. ker_gauge = discrete (torsion) invariants, killed by gauge (Z->Q, L->L^2, F->|F|^2). ker_topo = filtration depth, persists under all gauges. Hodge conjecture = f_rational(X,p)=0. | Cross-domain (Stark/Hodge/Crystal) | **ESTABLISHED** (2026-04-12, 15/15 fitness, promoted from HC-1d) | c_arrow_obstruction.md ﾂｧ10, c_filtration_obstruction.md (ker_topo 蟷ｾ菴墓ｹ諡), research/hodge_conjecture_decomposition_v0.md ﾂｧ27 |
| S-Sp6 | Sp(6) exotic invariant dimension: (Lambda^6(V tensor W))^{Sp(6)} = S_{(4,2)}(C^2) + Sym^6(C^2), dim=10. Divisor-generated=1, exotic=9 (2+7). Cauchy formula + Weyl-Brauer FFT. This is the exact shape of the dim 6 wall (wildness depth 1竊・ transition). | Geometry / Rep Theory | **PROVED** (classical invariant theory) | c_group_theory.md ﾂｧ5.5, c_filtration_obstruction.md ﾂｧ7.5.3 |

| RFP | Recursive Floor Principle (revised): under finite observation, floor removal is replaced by level transition of governing principle (`P_n -> P_{n+1}`), while `D_floor > 0` persists. Landauer (L1-L3), GPS, and LIGO share the same type signature with different dominant mechanisms. | Cross-domain / Meta | **ESTABLISHED** (2026-04-12: type-signature match + statement revision validated; S13 relation clarified as information-domain fixed-point instance) | c_recursive_floor_principle.md, c_distortion_floor.md §2, ligo_showcase.md §2.3, gps_showcase.md §2.2, q_quantum_thermodynamics.md §5 |
<!-- S15 axis-2 (Fi/I) projection map — added 2026-04-23 via OQ-L0-refinement v1 (Paper D §2.3 L0 v2). See annex below the main table. -->
| D_floor(s) | Gap-indexed factorization distortion as function of Dirichlet parameter s. **D_floor(s, N) ~ N^{-0.68} exp(0.216 (log N)^2 (s-1/2)^2)**. (a) Parabolic minimum at s=1/2 (Model C R^2>0.997, all N). (b) Curvature proportional to (log N)^2 — matches explicit formula prediction p^{1/2-s} ~ 1-(s-1/2)log p (R^2=0.9999). (c) Prefactor D0 ~ N^{-0.68} [CI: 0.65, 0.72], power law (R^2=0.998, 3 decades 10^6-10^9, beats 1/(logN)^beta). (d) Complex plane: D_floor(sigma+it) shows dip at t=gamma_1=14.135, sigma-continuous over 21 points sigma in [0.5,1.0], dip position std=0.036. Gap-universal (11 gaps tested, slope variation +/-4%). Twin independence: factorization validity does not depend on finiteness of twin primes. | Number Theory / Cross-domain | **ESTABLISHED** (2026-04-13: 4 CONFIRMED / 1 REJECTED / 0 OPEN. N=10^9 reached. Scripts: twin_zeta_s15_v2/v3, dfloor_slope_investigation, dfloor_rigorous_v5/v5b, dfloor_d0_decay_1B) | c_recursive_floor_principle.md §6.8, research/paper2_twin_dictionary_bridge_v0.md §9 |

## S15 axis-2 projection map (OQ-L0-refinement v1, 2026-04-23)

S15 Observable Trichotomy は primarily **axis-1 (Discrete/Continuous)** partition。
OQ-L0-refinement v1 (Paper D §2.3 L0 v2) で導入された **axis-2 (Finite/Infinite)**
は S15 3 class それぞれの **orthogonal variability** として分解される — 各 class
が Fi / I 両側に realization を持ち、観測者は Fi 側に住む。

| S15 class | Axis-1 | Axis-2 Fi realization (observer-reachable) | Axis-2 I realization (ideal / unreachable) |
|---|---|---|---|
| **(A) Scan** | C (continuous scanner) | 有限 window / truncated kernel: K(τ) on finite sample, numerical Z(β) with cutoff, ζ(s) partial sum Σ_{n≤N} n^{−s} | analytic continuation 全域 / complete spectral sum: K(τ) thermodynamic limit, ζ(s) as meromorphic object, U(t) on infinite-dim Hilbert |
| **(B) Structural** | D (integer / lattice invariants) | 具体 finite computation: b₁ of given graph, h_K of specific K, f_p(ρ) of concrete representation | Abstract universal class: "all b₁", Hodge class variety, Griffiths group, categorical colimit (observer-unreachable by finite procedure) |
| **(C) Information** | C (entropy on simplex) | empirical / truncated: H(X_N) on finite sample, S(ρ) on finite-rank ρ, empirical KL | thermodynamic limit: H(X) on infinite support, S(ρ) as Ansatz, I(X;Y) at infinite resolution |

**原理 (Paper D §2.3 L0 v2)**: 観測 = axis-2 **I → Fi traversal** (片方向)。3 Arrow
はいずれも axis-2 で I → Fi 成分を持ち、Fi/I 境界上に kernel (obstruction) が住む。
Kernel の axis-2 分解は **T-AAS 2-axis lens** (c_arrow_obstruction.md §10 冒頭) で
与えられる: **ker_gauge 系 = Fi-artifact** (別 Fi gauge で除去可能) / **ker_topo 系
= I-residue** (どの Fi gauge でも残る I 側残像)。

**Ref**: Paper D §2.3 (L0 v2 axiom), §4.4 (Arrow commutativity as Fi/I commutator),
§4.5.1 (meta-theorem coincide/split = Fi/I commutator = 0 / ≠ 0),
c_arrow_obstruction.md §10 冒頭 (2-axis lens),
research/oq_l0_refinement_finite_infinite_2axis_v0.md §3.1, §7.

---

## S15 NT-only enumeration closure (Paper N1 §3.5, 2026-04-26)

S15 Observable Trichotomy の **網羅性 (completeness)** は元来 HE1 enzyme 新ドメインテスト
+ S12/S13/S14 整合 verify + 層間 Arrow 1-3 形式記述の 3 条件で CLOSED された
(`research/bidirectional_duality_v0.md §5`)。Paper N1 (`papers/publication/nt/N1_observation_theory_nt_ja.md`)
は **数論内自閉 alternative path** として L1 NT 6 entries の exhaustive enumeration による
網羅性閉鎖を追加した。これは ESTABLISHED status の追加根拠 (補強) として記録する。

**3 段 NT 内 closure** (Paper N1 §3.5):

**(i') 各層に NT 観測量が存在** (網羅性 lower bound):
- Scan: ζ(s), L(s, χ), L(s, ρ, K/k), ζ_K(s), Z(β), G_k(s), F_{g,k}(s) — 7 instance
- Structural: h_K, R_K, w_K, d_K, ω(X), f_p(ρ), f_χ, b₁, codim, Cl(O_K), O_K^×, r₁, r₂ — 13 instance
- Information: H, S(ρ), Λ(n) = −ζ'/ζ, log h_K, log R_K, log w_K, D_KL, H_α, ε_{g,k} — 9 instance

**(ii') L1 NT 6 entries enumeration** (網羅性 upper bound):

| L1 NT entry | 主観測量 | S15 層 |
|---|---|---|
| nt_conductor.md | f_χ, f_p(ρ), Artin conductor f(ρ, K/k), codim 階層 | Structural |
| nt_dedekind_artin_zeta.md | ζ_K(s), Artin factorization L(s, ρ), permutation character ζ_F | Scan; ratio → Information |
| nt_frobenius_schur.md | ν(ρ) FS indicator (∈ {0, ±1}) | Structural (整数値) |
| nt_genus_class_fields.md | Hilbert class field H_K, genus field K^gen, K^gen/K の Galois 群 | Structural (有限 abelian group) |
| nt_relative_units.md | $O_{F_1}^\times / O_{F_2}^\times$, R_rel | Structural (lattice + 連続 co-volume) |
| nt_root_numbers.md | W(ρ) Artin root number, ε-factor | Structural (有限位数 root of unity) |

L1 NT 6 entries 全観測量が Structural または Scan に分類。Information 層は (Scan, Structural)
からの log-derivative 派生として `c_spectral.md` および `c_information_theory.md` の数論
射影として存在 (独立 entry を持たない)。

**(iii') S12/S13/S14 NT 内 verify**:
- S12 ⊂ Scan: 自明 (NT subset = ζ family)
- S13 = Arrow 2 ln 2 fixed point: ζ(s) functional equation s = 1/2 を NT instance
- S14 非対称: π (S¹ torsion in additive Scan, ι_2(1) = e^{iπ}) vs ln 2 (Arrow 2 上 `−log` 解析性) — 数論内完結

**counter-example の不在**: 6 entries × 各 entry 内全観測量に渡る exhaustive coverage で、
3 層のいずれにも属さない NT 観測量は Paper N1 v0.3 (2026-04-26) 時点で未知。新観測量が
将来 L1 NT に追加された場合は `meta/new_domain_protocol.md` Step 6 (辞書 residence 決定)
で再分類する。

**従来 closure (HE1) との関係**: S15 ESTABLISHED 2026-04-11 は HE1 + 多領域 instance を
universality 根拠とした。本 annex は **数論単一ドメイン内** で closure を独立に与える
alternative path であり、N1-N5 framework header としての数論内自閉性を保証する。

**Ref**: Paper N1 §3.5, papers/publication/nt/N1_observation_theory_nt_ja.md。

---

## S15 量子-only enumeration closure (Paper Q1 §3.5, 2026-04-27)

Paper Q1 (`papers/publication/quantum/Q1_observation_theory_quantum_ja.md` v0.2) は N1 と parallel な量子内自閉 alternative path として L1 量子 8 entries の exhaustive enumeration による S15 網羅性閉鎖を追加。N1 (NT-only) と Q1 (量子-only) の **2 dual framework header** が S15 trichotomy をそれぞれ独立に verify する。

**3 段量子内 closure** (Paper Q1 §3.5):

**(i') 各層に量子観測量が存在** (網羅性 lower bound):
- Scan (7 instance): U(t) = e^{-iAt}, K_Q(τ), Z(β), partition function, response χ(ω), spectral form factor K(τ,t), Loschmidt echo L(t)
- Structural (12 instance): dim eigenspace, Schmidt rank r, rank-1 dominance ρ₁, stabilizer rank χ(|ψ⟩), Wigner support volume, circuit gate count, POVM rank, group representation index, Casimir eigenvalue, topological invariant (Chern), anyon braiding statistics index θ, coherent vs incoherent decomposition rank
- Information (9 instance): S(ρ) von Neumann, D(ρ‖σ) relative entropy, mutual information I(A:B), F = −kT log Z, M_F magic monotone, 𝓝 Wigner negativity, C(|ψ⟩) Nielsen complexity, Δ_CHSH violation, M_unified = -log₂ F_C class-fidelity (Theorem 4a.1)

**(ii') L1 量子 8 entries enumeration** (網羅性 upper bound):

| L1 量子 entry | 主観測量 | S15 層 |
|---|---|---|
| q_quantum_observation.md | spectral 分解 A = Σ λ_j P_j, K_Q(τ), Born 期待値 Tr(ρ A) | Scan; Structural; → Information (S(ρ)) |
| q_open_quantum_systems.md | 部分 trace, Lindblad evolution, S(ρ_red), pointer basis | Scan (Lindblad); Information (S, mutual info) |
| q_quantum_statistical_mechanics.md | Z(β), Gibbs state ρ_β, KMS condition, response χ(ω), FDT | Scan (β-family); Information (F, S) |
| q_quantum_thermodynamics.md | first law dU = TdS + dW, Landauer kT ln 2, fluctuation theorem | Information; Structural (Carnot bound) |
| q_many_body_quantum.md | spectral form factor K(τ,t), Loschmidt echo, MBL/ETH, quasiparticle Z | Scan; Structural (entanglement entropy scaling) |
| q_action_principles.md | path integral, generating functional Z[J], effective action Γ[ϕ] | Scan (Z[J]); Information (Γ[ϕ]) |
| q_gauge_field_theory.md | Wilson loop ⟨W(C)⟩, Polyakov loop, gauge group representation | Scan; Structural (Casimir, irrep index) |
| q_fine_structure.md | α² 補正, SU(2) center {±I}, j(j+1) Casimir | Structural (group invariants); Information (Lamb shift) |

L1 量子 8 entries 全観測量が 3 層に分布、Information は class monotone (OQ-Ω-Obs-4a) として 4 class entries に住む新 information family を含む (古典 §3.4 が log-derivative 系のみだったのに対し、量子側では **algebraic-class infidelity** が加わる構造的 distinction)。

**(iii') S12/S13/S14/S17 量子内 verify**:
- S12 ⊂ Scan: U(t) は加法 #5、Z(β) は乗法 member
- S13 = qubit ρ_max の S(ρ_max) = log 2 (Z = 2 → F = −kT log 2 → S = log 2)
- S14 非対称: π (e^{iπ} = −1 fermion exchange, SU(2) center) vs ln 2 (S(ρ_max) 解析) — 層内 vs 層間 residence 差
- S17 = log d / d for d = dim H、continuous extremum at d = e、discrete codebook argmax at d = 3 (qutrit info-density optimum)

**counter-example の不在**: 8 entries × 各全観測量 exhaustive coverage で、3 層のいずれにも属さない量子観測量は Paper Q1 v0.2 (2026-04-27) 時点で未知。

**N1 (NT) との 2-domain cross-validation**: N1 NT enumeration + Q1 量子 enumeration が独立 2 数学領域で S15 trichotomy 閉鎖を提供 → framework の **ドメイン非依存普遍性** が 2-domain anchor で verify。

**Ref**: Paper Q1 §3.5, papers/publication/quantum/Q1_observation_theory_quantum_ja.md。

---

## Path 2 countably-infinite family (Paper N3 §3, OQ-Ω-Schumann v1, 2026-04-26)

S13 (`c_arrow_bridge_constants.md` §5) は ζ functional equation s = 1/2 fixed point を Arrow 2 上 canonical constant ln 2 の "value-fixed" instance として ESTABLISHED した。Paper N3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`) は OQ-Ω-Schumann v1 (`research/oq_omega_schumann_v0.md`, 2026-04-25, 13/13 gates PASS) を base に **Path 2 mechanism (Z/2 involution + invariant + non-empty fix point) を ζ singleton から countably-infinite NT family** に拡張した。本 annex はその dictionary residence。

### Path 2 abstract class predicate (一般化 v0.5 form)

数学的 object $D$ と observation parameter space $P$ に対し、$D$ が **Path 2 instance** であるとは:

1. **Z/2 group action**: σ: P → P, σ² = id involution
2. **Invariant function**: f: P → ℂ, f(σ x) = f(x)
3. **Non-empty fix point**: Fix(σ) := {x ∈ P : σ x = x} ≠ ∅

(v0 narrow form "affine Z/2 σ_c(x) = c − x on R" を v0.5 で general Z/2 group action に一般化、theta S-duality (Möbius τ ↦ −1/τ on H, fix τ = i) を含めるため)。

### 5-instance catalog (Schumann v1, 13/13 gates PASS)

| Instance | Involution | Space | Sub-family | Fix | Type | Axis-2 |
|---|---|---|---|---|---|---|
| **ζ functional eq.** | s ↦ 1−s | ℝ / critical strip | affine | s = 1/2 | **α** physical | I |
| **球面 Laplacian inv** | l ↦ −l−1 | $\mathbb{Z}_{\geq 0}$ | affine | l = −1/2 | **β** shadow | Fi |
| **theta S-duality** | τ ↦ −1/τ | $\mathfrak{H}$ | Möbius | τ = i | **α** physical | I |
| **modular L (weight k)** | s ↦ k − s | ℝ | affine | s = k/2 | **α** physical | I |
| **Atkin-Lehner W_N** | matrix order 2 on M_k | M_k(Γ_0(N)) | matrix | M_k^+ subspace | **γ** sub-obj | Fi |

axis-2 distribution: 3 I-side + 2 Fi-side, strong cross-side existence。

### Type α/β/γ trichotomy

- **Type α**: fix が同 algebraic object 内 single point (ζ critical strip 内, theta H 内, modular L ℝ 上)
- **Type β**: fix が異 object 内 single rep (球面 Laplacian → SU(2) spin-1/2 二重被覆)
- **Type γ** (Schumann v1 NEW finding 2): fix が同 object 内 sub-object (Atkin-Lehner W_N の M_k^+ eigenspace)。**Type γ formal definition は Schumann v1.5 task** として OPEN。

### Modular L weight-parametrization → countably-infinite

各 weight-k cusp newform $f$ (level $N$, character) は独立 Path 2 instance:

| weight k | functional eq. | central fix | example |
|---|---|---|---|
| 1 | Λ(s, χ) = ε·Λ(1−s, χ̄) | 1/2 | Dirichlet L (real χ); ζ when χ = 1 |
| 2 | Λ(f, s) = ε·Λ(f, 2−s) | 1 | weight-2 newform (BSD curves) |
| 4 | Λ(f, s) = ε·Λ(f, 4−s) | 2 | weight-4 newforms |
| 6 | Λ(f, s) = ε·Λ(f, 6−s) | 3 | weight-6 newforms |
| 12 | Λ(Δ, s) = ε·Λ(Δ, 12−s) | 6 | Ramanujan Δ on SL(2, ℤ) |

→ Path 2 cardinality $\geq \aleph_0$。**ζ singleton-class category error**: 従来 "Path 2 = ζ functional equation singleton" は category error。ζ は family 의 **最小 weight (k = 1) trivial character case の最小例**。

### Axis-2 Fi/I invariance (S15 axis-2 projection map との接続)

§"S15 axis-2 projection map" (S13 / S15 は axis-1 partition、axis-2 は orthogonal variability) の上で、Path 2 mechanism は **axis-2 invariant prediction**:
- Path 2 instance は Fi-side / I-side いずれにも住みうるが、predicate は axis-2 不動
- 5-instance distribution 3 I + 2 Fi で cross-side existence holds、counter-example 不在
- **Falsifiable**: Z/2 invariance instance で Fix(σ) = ∅ が axis-2 一方の側でのみ確認 → Path 2 single-class status split

**S15 axis-2 projection map との関係**: S15 trichotomy が axis-1 partition + axis-2 orthogonal variability を提供するように、Path 2 mechanism も axis-1 (Scan family member選択) × axis-2 (Fi/I 上での realization) の 2 軸で展開する。Path 2 は **axis-1 D side (Z/2 group action = discrete)** に住む mechanism だが、その fix-point は axis-1 D/C 両側に着地可能 (ζ 連続 strip = C-side, Atkin-Lehner discrete subspace = D-side)。

### Status

- **Schumann v0** (2 instances): axis-2 invariance prediction issued
- **v0.5** (3 instances, predicate generalized): Z/2 general
- **v1** (5+ instances, COUNTABLY INFINITE family): canonical scalar D1-D4 formal, Type γ flagged, 13/13 gates PASS
- **v1.5** (PENDING): Type γ formal definition + 6th pre-registered instance F3-discipline + axis-2 strong split test
- **ESTABLISHED** (PENDING): F1-F4 全 survive + 6+ instances + Type γ added

**現状 status**: **candidate_v1** (v1.5 / ESTABLISHED 昇格 pending)。Paper N3 v0.2 (2026-04-26) で publication 整備、N4 (Hasse-Weil L) で extension expected。

**Ref**: Paper N3 §2-§3, `research/oq_omega_schumann_v0.md` v1, `c_arrow_bridge_constants.md` §11 (Fi-origin vs I-origin canonical scalar 二分法、本 annex の constants-axis 連動)。

---

## Dirichlet L extension scope (Paper N3 §4, OQ-Ω5e v1.5 系列, 2026-04-26)

Paper N3 §4 trajectory (OQ-Ω5 v1.5 系列, 2026-04-24/25) の dictionary residence。framework predictive scope = "structural fit only" の close を本 annex に formal 化する (T-Ω5e-v15-* rows の overall summary)。

### Trajectory summary

| Sub-result | Status | Verdict |
|---|---|---|
| §4.1 Real primitive χ 1st instance | CONFIRMED 5/5 | T-Ω5e-v15 row |
| §4.2 Complex primitive χ extension | CONFIRMED 5/5 with SC3 caveat | T-Ω5e-v15-cplx row |
| §4.3 Off-axis 2D scan | INCONCLUSIVE with **SC4 critical catch** | T-Ω5e-v15-offaxis row |
| §4.4 2-quantity coincide v1a | **REJECTED** (G2 17.5%) | T-Ω5e-v15-2quantity row |
| §4.5 D_floor multigap v1b v1 | **REJECTED** + G3 PASS byproduct | T-Ω5e-v15-dfloor-multigap-v1 row |
| §4.6 Gap-class universality | **CONFIRMED 12/12** (genuine fragment) | (above row G3 byproduct) |

### SC4 critical catch (universal functional eq identity-level)

complex s 全域 (on/off-axis 問わず) で:

$$\overline{L(\sigma + it, \chi)} = L(\sigma - it, \bar\chi) \implies |\Lambda(\sigma + it, \chi)| = |\Lambda(1 - \sigma + it, \chi)|$$

→ σ_min = 1/2 は **universal functional equation identity-level consequence**, NOT framework-specific predictive content on Dirichlet L。

### Framework scope partition (post-v1b v1)

| Layer | Status on Dirichlet L | Source |
|---|---|---|
| Path 2 instance class membership | ✅ CONFIRMED (countably-infinite family member) | Schumann v1 |
| σ_min = 1/2 identity-level | ✅ CONFIRMED but trivial (SC4) | §4.1-4.3 |
| Multi-gap structural invariance | ✅ **CONFIRMED 12/12** (genuine fragment) | §4.5 G3 byproduct |
| 2-quantity Information+Structural coincide | ❌ REJECTED (G2 17.5%) | §4.4 |
| Paper C (log N)² curvature scaling | ❌ REJECTED (super-(log N)² growth) | §4.5 G2 |
| ζ functional equation enforcement | (ζ 固有, Paper N2 §6.1) | Paper N2 |

**"Structural fit only"** = Path 2 class membership + multi-gap universality は hold するが、Paper C-level 2-quantity uniqueness + (log N)² curvature scaling は **transfer しない** (ζ 固有)。Paper C uniqueness preserved more strongly (naive Taylor paths failed twice: v1a + v1b)。

**Ref**: Paper N3 §4, T-Ω5e-v15-* rows (5 件), `c_observation_optimal_gauge.md §8.3` OQ-Ω5e。

---

## Hasse-Weil L extension scope ─ BSD analytic rank detection (Paper N4 §3, OQ-Ω5e v1.5 v2 系列, 2026-04-26)

Paper N3 §4 で Dirichlet L extension scope を "structural fit only" close した後、Paper N4 (`papers/publication/nt/N4_hasseweil_stark_ja.md`) は **Hasse-Weil L (weight-2 modular L) で framework predictive content が genuine に transfer する** ことを示した。本 annex はその overall summary。N3 Dirichlet L "structural fit only" との対比で、framework predictive transfer pattern が **weight-class dependent** であることが demonstrate される。

### Trajectory summary (v2 arc 8-stage)

| Sub-result | Status | Source |
|---|---|---|
| §2.2 v2 v2 11a1 1st instance (non-CM weight-2) | CONFIRMED | T-Ω5e-v15-HW-v2 row 候補 |
| §2.3 v2 v3 conductor universality (4 non-CM) | 21/24 PASS at t≥5 + rank-1 BSD effect at small t | T-Ω5e-v15-HW-v3 row 候補 |
| §2.4 v2 v4-v5 amplitude rank discovery | rank 0/1 ROBUST + rank 2/3 numerical artifact (Phase 3 catch) | T-Ω5e-v15-HW-v5 row 候補 |
| §2.5 v2 v7 K_E(t) Taylor reviewer redirect | PARTIAL_CONFIRMED at t=0.3+ | T-Ω5e-v15-HW-v7 row 候補 |
| §2.6 v2 v8 proper AFE library-grade | **CONFIRMED genuine signal** (smoothing-artifact REJECTED) | T-Ω5e-v15-HW-v8 row 候補 |

### Theorem (N4 §3 main): K_E(t)·t² → r BSD analytic rank detection

**Statement**: Elliptic curve $E$ over ℚ with analytic rank $r$ について、central curvature

$$K_E(t) := \partial^2_\sigma \log|\Lambda(E, \sigma + it)|_{\sigma = 1}$$

は $K_E(t) \cdot t^2 \to r$ as $t \to 0+$、$O(t^2)$ subleading correction from $c_{r+1}$ term。

**Theoretical foundation** (reviewer Taylor argument): $\Lambda(1+z, E) = c_r z^r + c_{r+1} z^{r+1} + \cdots$ (analytic rank $r$ at $s=1$)、$|c_r|^2 (x^2 + t^2)^r$ leading order → $\partial^2_x \log|\Lambda| = r(t^2 - x^2)/(x^2 + t^2)^2$ at $x = 0$ で $K_E(t) = r/t^2 + O(1)$。

**10-curve verification (proper AFE)** (`oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md` §6):

| Curve | rank r | $K_E(0.3) \cdot (0.3)^2$ | Predicted r | Agreement |
|---|---:|---:|---:|---|
| 11a1, 14a1, 15a1, 17a1 | 0 | 0.023-0.030 | 0 | ✓ within 5% (4/4) |
| 37a1, 43a1, 53a1 | 1 | 1.021-1.026 | 1 | ✓ within 5% (3/3) |
| 389a1 | 2 | 2.047 | 2 | ✓ within 5% |
| 433a1 | 2 | 0.121 | 2 | ✗ outlier (curve-specific Taylor coefficient anomaly) |
| 5077a1 | 3 | 3.093 | 3 | ✓ within 5% |

**9 of 10 curves** match rank prediction within 5%。**Mean per rank class** (excluding 433a1): $0.027 < 1.024 < 2.047 < 3.093$ — clean monotone integer-rank progression。

**433a1 outlier**: $a_2 = +2$ unusual positive、$|c_2|$ small relative to $|c_3|$ で subleading correction dominates at $t = 0.3$、curve-specific not framework failure。

### Framework scope partition (vs N3 Dirichlet L)

| Layer | Dirichlet L (N3 §4) | Hasse-Weil L (N4 §2-§3) |
|---|---|---|
| Path 2 instance class membership | ✅ CONFIRMED (weight 1) | ✅ CONFIRMED (weight 2) |
| σ_min Fix locus identity-level | ✅ trivial (SC4 universal at s=1/2) | ✅ (s=1, weight-2 analogue) |
| Conductor / multi-gap structural invariance | ✅ 12/12 (genuine fragment) | ✅ 21/24 PASS at t≥5 (analogue) |
| 2-quantity coincide / Paper C scaling | ❌ REJECTED | (different test, BSD-style) |
| **BSD analytic rank detection** | (BSD outside Dirichlet L scope) | ✅ **CONFIRMED** $K \cdot t^2 \to r$ 9/10 curves |
| **Genuine framework content transfer** | ❌ "structural fit only" | ✅ **GENUINE** (BSD analytic rank detector) |

**Weight-class dependent transfer pattern** (Paper N4 main thesis):
- weight 1 (Dirichlet L): structural fit only (universality identity-level のみ transfer)
- weight 2 (Hasse-Weil L): **genuine** (BSD analytic rank の framework-side detector)

これは N1 framework が rich predictive structure を持つ証拠 — 各 weight-class が異なる framework content を carry し、Path 2 family member ごとに predictive scope が determined。

### Caveat (BSD claim 強度)

本 annex は "BSD 予想を解いた" とは主張しない。$K_E(t) \cdot t^2 \to r$ は **analytic rank の framework-side empirical detector** であり、analytic rank と geometric rank の equality (BSD 予想本体) は **assumed** (BSD-related)。Framework は analytic rank を $K_E$ から detect できることを示したのであって、analytic rank = geometric rank の証明 (= BSD) は scope 外。

### Status

**candidate_v2 v8** (Paper N4 v0.2, 2026-04-26)。Path 2 family の weight-2 instance (modular L family weight $k=2$ entry, `nt_dedekind_artin_zeta.md §7.2`) で、framework predictive content が genuine に transfer する **first instance**。

**v2 arc T-* rows** (5 個 row 候補) は本 annex の sub-result として簡潔参照、main table への formal addition は v0.3 task。

**Ref**:
- Paper N4 §2-§3 (`papers/publication/nt/N4_hasseweil_stark_ja.md`)
- `research/oq_omega5_v15_hasse_weil_L_*` (8 files trajectory)
- `c_recursive_floor_principle.md §6.8.2` (Hasse-Weil L D_floor extension annex)
- `nt_dedekind_artin_zeta.md §7.2` (modular L weight-2 family member)

---

## 4-stage Open QS chain S15 layered residence (Paper Q2 §2, 2026-04-27)

Paper Q2 (`papers/publication/quantum/Q2_open_qs_chain_ja.md` v0.2) は Q1 framework header の statistical/thermodynamic extension として、L1 量子 4 entries (open_QS / QSM / QTD / many-body) を **4-stage cumulative coarse-graining chain** で再構成し、各 stage が S15 全 3 層に instance を持つ + 各 stage 固有の Arrow 主担当を持つ **12-cell residence map** を提供する。N3 Path 2 universality (Schumann v1 5+ instance) と parallel な extension paper position。

**Status**: ESTABLISHED 2026-04-27 (Paper Q2 §2 + 各 4 stage entries 内 §S15 接続 cumulative 統合)。

**4-stage cumulative coarse-graining**:

| Stage | File | Coarse-graining 操作 | 失われるもの | 残るもの |
|---|---|---|---|---|
| **S1** | q_open_quantum_systems | Tr_B (partial trace over bath) | 純粋性, system-bath correlations | system-local expectation values, Lindblad CPTP |
| **S2** | q_quantum_statistical_mechanics | ensemble average (specific bath state → thermal ρ_β) | specific bath state | Gibbs state ρ_β = e^{-βH}/Z, KMS, partition function Z |
| **S3** | q_quantum_thermodynamics | thermodynamic limit (microscopic → macroscopic) | microscopic correlation functions | thermodynamic potentials (F, S, T, μ), thermo laws, Landauer |
| **S4** | q_many_body_quantum | quasiparticle distillation (bare → dressed) | bare particle identity | quasiparticle Z, Fermi liquid, topological order |

**Cumulative monotonicity**: S1 ⊂ S2 ⊂ S3 ⊂ S4 (information loss monotone)、各 stage transition で von Neumann entropy / 適切な information measure が **monotone non-decreasing** = 第二法則の量子 information theoretic 起源。

**12-cell layered residence map (S15 × 4 stage × Arrow 担当)**:

| Stage | Scan | Structural | Information | 主担当 Arrow |
|---|---|---|---|---|
| **S1 open_QS** | Lindblad semigroup $e^{Lt}$, Kraus operator unitary part | Kraus rank K, pointer basis dim, decoherence-free subspace dim | $S(\rho_S)$ entanglement entropy, mutual info $I(S:E)$ | **Arrow 1 dynamical** (decoherence pointer basis 選択 = T-AAS dynamical gauge fixing) |
| **S2 QSM** | $Z(\beta)$, Gibbs $\rho_\beta$, response $\chi(\omega)$ | dim H, spectral degeneracy $g(E_n)$, symmetry sector dim | $S(\rho_\beta)$, F = −kT log Z | **Arrow 2 algebraic** (KMS condition + FDT crown jewel) |
| **S3 QTD** | thermo state along Legendre cycle, fluctuation theorem $\langle e^{-\beta W}\rangle$ | thermo limit dimensionality d, phase boundary topology | $S = -\partial F/\partial T$, Landauer $kT \ln 2$ | **Arrow 2-3 cross** (bit と heat の Information layer × thermodynamic algebraic equivalence) |
| **S4 many-body** | spectral form factor K(τ,t), Loschmidt echo L(t) | Quasiparticle weight Z ∈ (0,1], topological invariants (Chern, anyon θ), entanglement entropy area-law coefficient | von Neumann entropy scaling, CFT central charge c | **Arrow 1⁻¹ generation** (quasiparticle = Information → Structural reverse map) |

12 cells full residence ⇒ 4-stage chain が S15 全 3 層を 4 独立 stage で independently verify、4 stage が異なる Arrow を主担当 (S1 dynamical / S2 algebraic / S3 cross / S4 reverse) → S15 Arrow 構造全体が 4-stage 独立 verify。

**Q1 §6 4-vertex parallel との関係**:
- Q1 §6 = Arrow 1 kernel narrowness 4-vertex (C₁/C₂/C₃/C₄ static algebraic class)
- Q2 §2 = 4-stage cumulative coarse-graining (S1/S2/S3/S4 dynamical chain)
- 両者は補完視点: Q1 が **static intra-Arrow taxonomy**、Q2 が **dynamical chain Arrow differentiation**

**N3 Path 2 family parallel**: Path 2 5+ instance (Schumann v1) と本 4-stage chain は両者とも **Arrow 2 (Scan → Information, log-exp 双対)** 上の extension framework、2 数学領域 (NT, 量子) で independently extend。

**Ref**: Paper Q2 §2, papers/publication/quantum/Q2_open_qs_chain_ja.md / `q_open_quantum_systems.md §8.4` / `q_quantum_statistical_mechanics.md §9.4` / `q_quantum_thermodynamics.md §7` / `q_many_body_quantum.md §7`。

---

## Negative results (documented for non-recurrence)

| ID | Claim tested | Result | Evidence | Ref |
|---|---|---|---|---|
| NEG-1 | epsilon_k residual peaks correspond to zeta zeros (5/9 match at Delta_gamma<2) | **REJECTED** | Permutation test p=0.81. Expected matches under H0 = 6.8 > observed 5. Enrichment 0.7x. Bootstrap p=0.96. Cross-gap: all gaps show enrichment <= 1.0x. Cause: 10 zeros cover 37.6% of gamma_max=53.2, making random matches frequent. | research/paper2_twin_dictionary_bridge_v0.md §9.4 |

## Foundational structures (no theorem ID 窶・algebraic prerequisites)

| Structure | Statement | Ref |
|---|---|---|
| ﾎｹ_L (additive hom) | 邃､/L邃､ 竊・Sﾂｹ, n 竊ｦ e^{2ﾏin/L}; ker = L邃､, im = ﾎｼ_L | c_phase_complex.md ﾂｧ2 |
| ﾏ・(multiplicative hom) | (邃､/L邃､)* 竊・Sﾂｹ; self-dual character group | c_phase_complex.md ﾂｧ3 |
| Common receptacle (**structural root**) | 邃・is the minimal topological field containing both ﾎｹ_L and ﾏ・targets. ﾂｧ4 = 霎樊嶌蜈ｨ菴薙・ structural root: S12/S13/S14 蜈ｨ縺ｦ ﾂｧ4 dual 縺九ｉ豢ｾ逕・| c_phase_complex.md ﾂｧ4 |
| Pontryagin 竊・c_sﾂｲ | Self-duality + half-integer parity 竍・c_sﾂｲ = 1/2 | c_phase_complex.md ﾂｧ5 竊・T1, T8 |
| ﾏ・normalization | ﾏ・n) = (n mod L)/L = arg(ﾎｹ_L(n))/2ﾏ | c_phase_complex.md ﾂｧ6 |

## Quantum foundational structures (from q_quantum_observation.md)

| Structure | Statement | Ref |
|---|---|---|
| U(t) = e^{-iAt} (Stone) | Continuous non-commutative ﾎｹ_L: 邃・竊・U(H). Reduces to ﾎｹ_L when H = 邃・ A = 2ﾏ/L | q_quantum_observation.md ﾂｧ4 |
| Spectral theorem | A = ﾎ｣ ﾎｻ_j P_j (operator Fourier decomposition). Reduces to amplitude/phase when commutative | q_quantum_observation.md ﾂｧ3 |
| Schmidt decomposition | |ﾏ遺洸 = ﾎ｣ 竏嗔_k |a_k筺ｩ竓慾b_k筺ｩ. Matrix version = SVD (c_spectral.md ﾂｧ3) | q_quantum_observation.md ﾂｧ5 |
| K_Q(ﾏ・ | |Tr(ﾏ・ｷe^{iAﾏм)|ﾂｲ. Reduces to classical K(ﾏ・ when ﾏ・diagonal | q_quantum_observation.md ﾂｧ6 |
| c_sﾂｲ = Tr(ﾏ＼max ﾂｷ ﾎ_even) | 1/2 as Born expectation of even-parity projector under maximal mixing (NOT purity; coincides numerically for qubit only) | q_quantum_observation.md ﾂｧ7 |

## Action principles structures (from q_action_principles.md)

| Structure | Statement | Ref |
|---|---|---|
| H竊猫 duality | Legendre 螟画鋤 H(q,p) = pqﾌ・・L(q,qﾌ・縲よｼ皮ｮ怜ｭ宣㍼蟄占ｫ・= H 蛛ｴ縲∫ｵ瑚ｷｯ遨榊・ = L 蛛ｴ縲ょ酔荳 S 縺ｮ逡ｰ縺ｪ繧狗ｪ・(A3 gauge) | q_action_principles.md ﾂｧ2 |
| Path integral | 筺ｨf\|i筺ｩ = 竏ｫDq e^{iS/邃殉縲ょ・邨瑚ｷｯ縺ｮ驥阪・蜷医ｏ縺・= A0 縺ｮ騾｣邯夂沿縲Ｔaddle point 竊・T8 Boltzmann codim 縺ｮ continuous迚・| q_action_principles.md ﾂｧ3 |
| Wick rotation = S12 2霆ｸ蝗櫁ｻ｢ | t竊停・iﾏ・縺ｧ e^{iS}竊弾^{-S_E}縲ょ刈豕不can(ﾎｹ_L)竊比ｹ玲ｳ不can(ﾏ・ 縺ｮ蝗櫁ｻ｢縲やр = common receptacle (phase_complex ﾂｧ4) 縺梧ｹ諡 | q_action_principles.md ﾂｧ4 |
| Z[J] 竊・correlation 竊・spectrum | Z[J] = 竏ｫDﾏ・e^{-S+Jﾏ・縲ばｴ竅ｿZ/ﾎｴJ竅ｿ = n轤ｹ逶ｸ髢｢縲Ｑole = mass = spectral gap縲４7 蝣ｴ縺ｮ逅・ｫ也沿 | q_action_principles.md ﾂｧ5-6 |
| S16-Corr (three-regime) | 蟆乗曹蜍・x_j=j+ﾎｵﾎｴ_j 縺ｫ蟇ｾ縺・ (1) N竏狸(m) = 4ﾏﾂｲﾎｵﾂｲmﾂｲNﾂｷVar(ﾎｴ)+O(ﾎｵﾂｳ) [direct]縲・2) ﾎｽﾂｲ=2ﾎｵﾂｲVar(ﾎｴ)(1竏佃≫ａ) 繧医ｊ N竏狸(m) = 2ﾏﾂｲmﾂｲNﾎｽﾂｲ/(1竏佃≫ａ)+O(ﾎｵﾂｳ) [correlated]縲ばｱ_m := 2ﾏﾂｲmﾂｲﾎｽﾂｲ/(1竏佃≫ａ) 竕ｪ 1 縺ｧ謌千ｫ九∃ｱ_m 竕ｳ 1 縺ｧ N竏狸(m) 竕､ N 縺ｮ髱櫁ｲ蛻ｶ邏・〒 clip (鬟ｽ蜥・縲ゆｸ蛾伜沺: perturbative (ﾎｱ竕ｪ1) / correlated perturbative (ﾎｱ竕ｪ1, ﾏ≫ａ竕0) / saturation (ﾎｱ竕ｳ1) | S16-C PROVED (ﾂｧ15) + P-ﾎｽ-corr CONFIRMED (ratio竕・.99 at ﾎｵ=0.01, ratio_direct竕・atio_corr within 2%) |
| P-ﾎｽ-indicator + ﾎｽ-universality ladder | ﾎｽ=0筺ｺEXACT, ﾎｽ>0筺ｺinteracting縲・-class ladder: EQUISPACED(0) / GUE-like(0.1-0.5) / GOE-like(0.5-0.7) / intermediate(0.7-0.85) / Poisson-like(>0.85)縲・9邉ｻﾃ・繝峨Γ繧､繝ｳ讓ｪ譁ｭ遒ｺ隱阪Ｄlass 縺ｯ繝峨Γ繧､繝ｳ縺ｧ縺ｯ縺ｪ縺・spacing organization 縺ｧ豎ｺ縺ｾ繧九・eta竊粘U(2) 蜷御ｸclass (ﾎｽ蟾ｮ<0.01)縲￣rimes竊粘U(3) 蜷御ｸclass (ﾎｽ蟾ｮ<0.01)縲・*Superselection Guard (2026-04-12)**: ﾎｽ-ladder 縺ｯ蜷御ｸ superselection sector 蜀・・繧ｹ繝壹け繝医Ν縺ｫ縺ｮ縺ｿ驕ｩ逕ｨ蜿ｯ閭ｽ縲ら焚縺ｪ繧矩㍼蟄先焚縺ｮ豺ｷ蜷・竊・ﾎｽ竊単oisson (repulsion 豸亥､ｱ)縲Ｕier 縺ｯ豺ｷ蜷医↓荳榊､・| arrow_obstruction ﾂｧ8.4 + ﾂｧ8.5 Guard, CONFIRMED (s16_cross_domain_tier_nu.py + s16_ym_channel.py) |

| D_floor universality | D_floor(S,W) = inf_{g in G(W)} d(m(S), m_g(S|_W))縲・ domain (NT/Control/Info/QFT/FX) 縺ｧ蜈ｱ騾壽ｧ矩: P1(>=0), P2(>0 finite W), P3(monotone), P4(vanishing)縲ゆｸ画・蛻・・隗｣: D_floor = D_arith + D_proj_irr (noise excluded)縲４ector-wise: D_floor_total = max_alpha D_floor^{(alpha)} | c_distortion_floor.md S2-S5, CONFIRMED (d_floor_verify.py, 5/5 PASS) |
| Mass Gap Binary Indicator | SU(N) glueball (N=2..12,inf) 縺ｧ tier = INTERMEDIATE_FP 縺・rank/state/channel 荳榊､峨Ｕier != EXACT 縺ｯ mass gap 縺ｮ蠢・ｦ∵擅莉ｶ縲・_floor > 0 縺ｮ spectral instance | arrow_obstruction ﾂｧ8.5 + c_distortion_floor.md S4.5, CONFIRMED (s16_ym_extended.py, AT2021 data) |
| T-DTB (Dispersion-Tier Bridge) | Gap ﾎ・0 縺ｮ髮｢謨｣ spectrum 竊・tier 竕 EXACT (S16-C forward)縲・ree field (g=0) 竊・tier = EXACT (S16-A)縲・_floor = ﾎ・for spectral systems縲・*騾・・荳肴・遶・*: tier 竕 EXACT 竍・ﾎ・> 0 (massless non-equispaced 蜿堺ｾ九≠繧・縲・illennium problem 縺ｯ gap existence (ﾎ｣ﾎｦ scope 螟・縲∃｣ﾎｦ 縺ｯ gap 竊・tier 縺ｮ forward chain 繧呈署萓・| research/dispersion_tier_chain_v0.md ﾂｧ4, PROVED (forward direction) |
| C-DTB v1.1 (conjecture) | tier=INTERMEDIATE_FP + ﾎｽ竏・OE-like [0.5,0.7] 竊・gap > 0縲・*Falsification round 1 (6 test classes, N=50..1000): SURVIVES**縲１rotection mechanism 逋ｺ隕・ GOE-like ﾎｽ 竊・STANDARD_FP lock (level repulsion 竊・regular spacing)縲！NTERMEDIATE_FP 竊・Poisson-like ﾎｽ (convergent irregular spacing)縲・*Tier-ﾎｽ exclusion zone**: gapless 邉ｻ縺ｧ荳｡譚｡莉ｶ縺ｯ讒矩逧・↓蜈ｱ蟄伜峅髮｣縲・apped bound state structure 縺ｮ縺ｿ縺御ｸ｡譚｡莉ｶ繧貞酔譎ゅ↓貅縺溘☆ | research/dispersion_tier_chain_v0.md ﾂｧ10, c_dtb_falsify.py (6 tests ﾃ・5 N-values, 20 trials each) |

## Arrow obstruction structures (from c_arrow_obstruction.md)

| Structure | Statement | Ref |
|---|---|---|
| Three obstruction types | 隨ｬ荳鬘・髮｢謨｣kernel) / 隨ｬ莠碁｡・騾｣邯嘖pectrum) / 隨ｬ荳蛾｡・逋ｺ謨｣)縲よュ蝣ｱ謳榊､ｱ縺ｮ繝｡繧ｫ繝九ぜ繝縺ｧ蛻・｡・| c_arrow_obstruction.md ﾂｧ2 |
| Strength hierarchy | 邃､/2 < 邃､/n < 譛蛾剞鄒､(蜿ｯ螟・ < 邃､縲る屬謨｣荳榊､蛾㍼縺ｮ鄒､縺悟､ｧ縺阪＞縺ｻ縺ｩ gauge 蝗樣∩繧ｳ繧ｹ繝亥｢怜､ｧ | c_arrow_obstruction.md ﾂｧ3 |
| Six-layer decomposition | 蟄伜惠(image)/髫懷ｮｳ(kernel)/谺｡蜈・order)/菴咲ｽｮ(spectrum)/豬√ｌ(evolution)/荳矩剞(bound) | c_arrow_obstruction.md ﾂｧ4 |
| Domain symmetry constraint | Structural 螻､縺ｮ蟇ｾ遘ｰ諤ｧ縺・Arrow 1 縺ｮ蜒上ｒ蛻ｶ髯舌☆繧九・3 (gauge 荳榊､画ｧ) 縺ｮ蟶ｰ邨・| c_arrow_obstruction.md ﾂｧ5 |
| Gauge wall structure | maximal竊段ntermediate竊知inimal gauge縲ょ｣√・菴咲ｽｮ縺檎ｬｬ荳鬘樣囿螳ｳ縺ｮ豸域ｻ・せ繧呈ｱｺ螳・| c_arrow_obstruction.md ﾂｧ6 |

## Gauge field theory structures (from q_gauge_field_theory.md)

| Structure | Statement | Ref |
|---|---|---|
| Non-abelian gauge (SU(N)) | phase_complex ﾎｹ_L 縺ｮ SU(N) 諡｡蠑ｵ縲ょ庄謠・竊・髱槫庄謠帙〒閾ｪ蟾ｱ逶ｸ莠剃ｽ懃畑 [A,A] 蜃ｺ迴ｾ | q_gauge_field_theory.md ﾂｧ1 |
| F_{ﾎｼﾎｽ} = [D_ﾎｼ,D_ﾎｽ] | 蝣ｴ縺ｮ蠑ｷ蠎ｦ = 髱槫庄謠帶ｧ縺ｮ貂ｬ螳・= quantum_observation [A,B] 縺ｮ蝣ｴ縺ｮ逅・ｫ也沿 | q_gauge_field_theory.md ﾂｧ2 |
| BRST cohomology | sﾂｲ=0 exact sequence, H(s) = 迚ｩ逅・噪迥ｶ諷九Ｄonductor ﾂｧ6.9 Brauer 蛻・ｧ｣縺ｨ蜷檎ｨｮ | q_gauge_field_theory.md ﾂｧ4 |
| Instanton (ﾏ竄・SU(N))=邃､) | topological charge n 竏・邃､, ﾎｸ-vacuum = 髮｢謨｣ sector 縺ｮ驥阪・蜷医ｏ縺帙らｬｬ荳鬘樣囿螳ｳ縺ｮ迚ｩ逅・沿 | q_gauge_field_theory.md ﾂｧ6 |
| Confinement = Arrow 1 restriction | gauge-singlet 縺ｮ縺ｿ隕ｳ貂ｬ蜿ｯ閭ｽ縲・odge (p,p) 蛻ｶ髯舌→蜷檎ｨｮ (螳夂ｾｩ蝓溘・蟇ｾ遘ｰ諤ｧ縺悟ワ繧貞宛邏・ | q_gauge_field_theory.md ﾂｧ7 |

## Error-derived (from L4)

| ID | Error source | Candidate theorem | Status |
|---|---|---|---|
| from ERR-C4 | CV fails for crystal | C6: observable ~ algebra matching | TO FORMALIZE |
| from ERR-F1 | Power law is sigmoid local slope | C7: sigmoid universality | TO FORMALIZE |
| from SC-2 | Constraint violations | n_eff = 1/(1-abs) as continuous conductor | TO FORMALIZE |

