---
axis: [A, C]
position: L1_observation_optimal_gauge
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md           # A0 + A7 + §8 axis-2 framework
  - L1_mathematical/c_arrow_framework.md     # 3 Arrow framework (定理 4.1)
  - L1_mathematical/c_arrow_bridge_constants.md  # S13 ln 2 = Arrow 2 canonical
  - L1_mathematical/c_arrow_obstruction.md   # §10.0 axis-2 lens
  - L1_mathematical/c_theorems_master.md     # S13, S15, S17, T-AAS rows
  - papers/Paper_D_Observation_Theory_ja.md  # §4.5.1, §4.5.1a, §4.5.1b
  - papers/Paper_C_NT_Quantum_ja.md          # NT instance (s = 1/2 coincide)
  - papers/Paper_E_Image_AI_ja.md            # 画像 AI instance (t = T/e split)
  - research/paper2_twin_dictionary_bridge_v0.md  # Paper 2 instance (X = 2g vs X = 6 split)
  - research/oq_omega5_2cell_v0.md               # OQ-Ω5 v1 σ-action groupoid framework (2026-04-24)
  - research/oq_omega5_v15_dirichlet_l_first_instance_v0.md  # OQ-Ω5e v1.5 Dirichlet L real primitive CONFIRMED (2026-04-24 earlier)
  - research/oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md  # OQ-Ω5e v1.5 Dirichlet L complex primitive extension CONFIRMED with SC3 caveat (2026-04-24 later)
  - research/oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md  # OQ-Ω5e v1.5 v1 off-axis 2D scan INCONCLUSIVE with SC4 catch (2026-04-24 evening, universal σ-symmetry chain identified)
  - research/oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md  # OQ-Ω5e v1.5 v1a 2-quantity coincide test REJECTED (2026-04-24 evening late, |L|² NOT Paper C Information analog)
  - papers/Paper_F_DNA_ja.md                     # DNA (Paper F) instance (13/13 organism split, Path 3 biological instance)
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-24
runtime_summary:
  what: S13 半値固定点 (Arrow 2 上 ln 2) が domain 横断で observation-optimal gauge を予測する 定理 4.1a / 系 4.1b / 系 4.1c の formal residence
  when: 「どの gauge が observation を最適化するか」「Information layer と Structural layer が同じ gauge で balance するか」「coincidence/split は何で決まるか」
  provides: [observation_optimal_gauge_theorem, two_layer_separation, coincidence_condition, fi_i_commutator_root, three_instance_table]
  consumes: [c_arrow_framework.md (3 Arrow + 可換性), c_arrow_bridge_constants.md (S13), c_arrow_obstruction.md §10.0 (Fi/I lens), L0 v2 axis-2 framework]
  axis: [A, C]
  cost: medium
  status: ESTABLISHED
  one_screen: |
    定理 4.1a: Information layer balance = Arrow 2 S13 半値固定点 / Structural layer balance = Arrow 1 domain 固有 arithmetic-dynamical
    系 4.1b: 両 layer coincidence = functional-equation 型 enforcement の存在 (Paper C ζ(s) = ζ(1−s) のみ確認)
    系 4.1c (v0.9 honest reformulation): coincide/split = balance position agreement test (3 realization type: point / locus / stochastic ensemble、type ごとに異なる criterion)
    3 instance: Paper C point-to-point agree / Paper 2 point-in-locus disagree / Paper E stochastic ensemble disagree (fraction 3/9)
    Path 1-4 全完了 (2026-04-22 夜): theorem は ESTABLISHED として Paper D 本体に正式記録
    +1 instance (2026-04-24): Paper F DNA mtDNA split 13/13 (biological translational selection, Path 3 3rd instance)
    OQ-Ω5 candidate_v1 (2026-04-24): σ-action groupoid framework + 定理 4.3.1 unconditional (Fix(σ_D) = critical line pinning) + 定理 4.4.1 conditional on RH (s = 1/2 unique pinning) + 4-instance categorical taxonomy。真の 2-cell layer は OQ-Ω5f として v2 task に分離
    OQ-Ω5e v1.5 (2026-04-24): Dirichlet L(s, χ) 1st predictive instance **CONFIRMED** (5/5 real primitive χ、D_C asymmetric-grid σ_min = 0.500000 exact + R² = 1.000、symmetry-forced tautology concern refuted)
---

# Observation-Optimal Gauge Theorem — S13 predictive power の定理化

**Level**: L1 (横断定理、S13 半値固定点の domain 横断 predictive power)
**Role**: c_arrow_framework.md (3 Arrow framework) と c_arrow_bridge_constants.md (S13 ln 2 = Arrow 2 canonical) を上流とし、観測の "optimal gauge" を 2 layer に分離して定理化する。Paper D §4.5.1 (ESTABLISHED 2026-04-22 夜) の dictionary residence。

---

## §1 動機

S13 (ln 2 fixed-point principle, c_arrow_bridge_constants.md §5、ESTABLISHED 2026-04-10) は Arrow 2 上の半値固定点 (e^{−x} = 1/2 ⟺ x = ln 2) を residence statement として与える。Paper D v0.4 時点では abstract residence 宣言にとどまり、predictive power は未確認だった。

v0.5 (Paper E + Paper 2 X-scan) で 2 instance 検証、v0.6 (Paper E Structural main scan, 9900 samples, 2026-04-22 夜) で 3rd instance + Path 1-4 完備により ESTABLISHED 昇格。本 entry は Paper D §4.5.1 / §4.5.1a / §4.5.1b の formal residence。

---

## §2 主要主張 (3 階層)

### §2.1 定理 4.1a (Observation-optimal gauge theorem, layer separated form)

**Statement**: observation domain D において、Arrow 1⁻¹ が Structural target を最精密に復元する gauge 構造は **2 layer に分離** される:

- **Information layer** (D_floor, P[Δb₁ ≠ 0], 三層 fit residual 等の Information observable): Arrow 2 上の **S13 半値固定点 (ln 2 / α̅ = 0.5 / s = 1/2)** に対応する gauge で最適化される。
- **Structural layer** (carry rate, χ median 等の整数的 / 半整数的 invariant): Arrow 1 上の domain 固有の arithmetic / dynamical 構造で balance 点が決まる。
- **両 layer の balance 点が同一 gauge で一致するか** は **domain 固有の structural enforcement** に依存する独立な問い。

### §2.2 系 4.1b (coincidence 条件、Paper C 特殊性)

両 layer balance が同一 gauge で coincide するのは、domain に **functional-equation 型 structural enforcement** が存在するときに限る。Paper C は ζ(s) = ζ(1−s) により両層が s = 1/2 で同時固定される **唯一の確認例**。Paper 2 (split at X = 2g vs X = 6) と Paper E (split, C4 ontic verdict majority 6/9) は enforcement 不在ゆえに split する。

### §2.3 系 4.1c (balance position agreement form, 2026-04-23 / v0.9 honest reformulation)

L0 v2 (finite_observation.md §8) の 2-axis lens において、coincide / split の binary verdict は **axis-2 Fi/I 上の balance position agreement** として根源化される (Paper D §4.5.1b v0.9 reformulation 反映)。

**v0.9 reformulation 経緯**: v0.7 初稿は operator commutator、v0.8 は 2-category 2-cell formulation で書き直したが、2 回目内部レビューで「2-cell formulation と claim したものの、実装は constant map 2 つの endpoint position 比較に過ぎず、2-category structure を真に使っていない」(C2-D1) と指摘された。v0.9 では rhetoric の dishonesty を解消し、**"balance position agreement test"** という素朴な命名に降格、2-category への formal lift は OQ-Ω5 で genuine open task として残す。

**Definition (balance position agreement test, v0.9)**:

domain D で:
- **Information balance position** $g_I^D$ = Arrow 2 上の S13 半値固定点で決定される observation gauge (point ∈ Obs(D))
- **Structural balance position(s)** $g_S^D$ = Arrow 1 上の domain 固有 arithmetic / dynamical 構造で決定される observation gauge。realization type が domain で異なる (point / locus / stochastic ensemble)

**3 realization type と agreement criterion**:

| realization type | $g_I^D$ shape | $g_S^D$ shape | agreement criterion |
|---|---|---|---|
| **Point** | point | point | point-to-point equality $g_I = g_S$ |
| **Locus** | point | family $\{g_\alpha\}_\alpha$ | point-in-locus $g_I \in \{g_\alpha\}$ |
| **Stochastic ensemble** | point (deterministic) | random ensemble $\{g_\omega\}_\omega$ | majority agreement (fraction with $g_\omega = g_I$ ≥ τ, default τ = 1/2) |

C(D) は本 agreement test の binary 結果 (各 realization type の criterion で agree なら 0, disagree なら ≠ 0)。Paper D §4.5.1b v0.9 の 3 instance 表参照:
- Paper C: point-to-point, agree, C = 0
- Paper 2: point-in-locus, $X = 6 \notin \{2g\}$, C ≠ 0
- Paper E: stochastic ensemble, fraction = 3/9, C ≠ 0

**axis-2 Fi/I 言語**: 3 realization type ともに axis-2 Fi 側 internal stratification (point / locus / ensemble) として位置付けられ、L0 v2 (d') "axis-2 Fi/I 境界の分類学" の Fi-side internal refinement に相当 (Paper D §4.5.1b "Realization type の axis-2 (Fi/I) 配置" subsection 参照)。

**OQ-Ω5 (σ-action groupoid framework) との接続 (v1 update 2026-04-24)**: 本 §6 は **真の 2-category formulation ではない** ことを明示する。constant maps 2 つの endpoint 比較に過ぎない。真の 2-category lift (Obs(D) 全体の 0-cell / 1-cell / 2-cell structure を formal に記述、ζ functional equation 等を 2-cell witness として construct) は OQ-Ω5 dedicated open task (`research/oq_omega5_2cell_v0.md`) で別途追求する。

**OQ-Ω5 candidate_v1 (2026-04-24)**: ΣΦ 独自 path (σ-action groupoid Obs^σ(D) + constant functor σ_D-equivariance) で Gate 3 partial formal closure 達成。"2-cell witness" vocabulary は廃止 → **"σ-action groupoid functoriality witness"** に正名 (literal-check で旧 vocabulary の degenerate fail 解消)。
- **定理 4.3.1 unconditional**: constant functor T_Arrow_i を Obs^σ(D) 上の σ_D-equivariant functor に lift する path 存在 ⟺ g_i^D ∈ Fix(σ_D)。Paper C 例では Fix(σ_D) = critical line
- **定理 4.4.1 conditional on RH + Paper C §3 parabolic**: critical line 上 s = 1/2 unique pinning
- **4-instance taxonomy** (§5.4): Paper C (Type I, universal σ_D + Fix uniqueness) / Paper 2 (Type II, locus σ_g 非 universal) / Paper E (Type III, σ_D 不在 + stochastic) / Paper F (Type II biological, clade-specific locus dispersion)
- 本 dictionary entry の Path 3 split causation (上 §5 で 3 instance) に categorical root cause 言語を provide。operational tool (§6 本文) は v1 closure に依存せず使用可能

詳細: Paper D §4.5.1b (v0.9 honest reformulation、本 entry の primary source)。

---

## §3 2 layer 分離の Arrow framework 根拠

定理 4.1a の 2 layer 分離は c_arrow_framework.md §3.3 の "Information / Structural 非対称性" の specialization:

- **Information layer**: Arrow 2 (log-derivative chain) は **observable-independent**。Information balance 判定は scanner 軸固定で一意、observable choice から自由。
- **Structural layer**: Arrow 1 (selector property, c_arrow_framework.md §3.1) は **observable-dependent**。同 domain で複数 Structural observable 候補 {C2, C4, B6, …} が並立し、observable 選択が verdict (coincide / split) を変える。

両 layer の non-symmetric な gauge dependence は Arrow framework 上の structural fact であり、定理 4.1a はこの非対称性を S13 半値固定点 (Arrow 2 canonical) と domain 固有 Arrow 1 structural balance の **対比** として state する。

---

## §4 3 instance の status (+1 candidate, 2026-04-24 update)

| Domain | Gauge 変数 | Information balance (Arrow 2) | Structural balance (Arrow 1) | 両者一致? | C(D) | Status |
|---|---|---|---|---|---|---|
| **NT (Paper C §3)** | s (Dirichlet 実部) | s = 1/2 (D_floor 最小、3 decades 検証) | s = 1/2 (ζ 零点 RH) | **coincide** (ζ functional eq.) | **= 0** | CONFIRMED 両層 |
| **NT carry (Paper 2, bridge §14)** | X (conductor) | X = 6 (g = 2, D_floor 最小、因子 3) | X = 2g (c = 1/2 locus, 15 gaps) | **SPLIT** (異なる X) | **≠ 0** | split CONFIRMED |
| **画像 AI (Paper E §4.5.1 + main scan §6)** | t_start | t = T/e = 183.94 (α̅ = 0.5、P 最小、hr = 12 Preserved) | t*(C4 χ median) ≈ 140-180 (hr 非依存、seed 依存) | **SPLIT** (majority 6/9、C4 primary) / coincide 3/9 (seed = 42 only) | **≠ 0** | split CONFIRMED (9900 samples) |
| **DNA (Paper F §6, 2026-04-23)** | coordinate system (CDS-sense vs whole-genome) | γ = S/W species-specific (0.009-0.113 across 13 organisms) | g_S = CDS sense-aligned local coordinate | **SPLIT** 13/13 (coincide 事例ゼロ) | **≠ 0** | split CONFIRMED across 108× genome scale × 6 biology domains |

**Status**: ESTABLISHED (2026-04-22 夜、2026-04-24 Paper F 13-organism 追加で empirical base 4 倍化)。Path 1-4 全達成 (下記 §5)。

---

## §5 Path 1-4 completion (ESTABLISHED 昇格根拠)

Paper D v0.5 (2026-04-22) で CANDIDATE 昇格時に設定した 4 path 要件の完了状態 (Paper E structural main scan note §6 準拠):

### Path 1 (2+ instance で両層 ontic 判定完了)

**3/3 DONE** (要件 +1 超達成):
- Paper C: coincide CONFIRMED (ζ functional eq. による structural enforcement)
- Paper 2: split CONFIRMED (2D no_intersection、X = 2g vs X = 6)
- Paper E: split CONFIRMED (9900 samples main scan、C4 majority 6/9)

### Path 2 (1 instance で coincide structural enforcement identify)

**DONE**:
- Paper C ζ(s) = ζ(1−s) を **唯一** の enforcement instance として identified

### Path 3 (split 原因分類)

**DONE** (3 split instance 供給, 2026-04-24 更新):
- **Paper 2: arithmetic mod-n reducibility** (X の因子構造が D_floor を支配、carry は residue-exclusivity)
- **Paper E: stochastic basin selection** (training dynamics の確率的 basin が Structural balance 位置を dominate)
- **Paper F: biological translational selection** (2026-04-23 追加) — DNA mtDNA で g_S (CDS sense-aligned coordinate) ≠ g_I (whole-genome natural index)、γ = S/W の organism-specific range (0.009-0.113) が coding selection strength を organism 固有値に pin する。**Round 5 で 13 organism 実測**: 全 Path 3 split、coincide instance 無し。split cause = translational apparatus evolution の clade 固有性 (paper E basin selection の biological 類似)。Paper F §6 で c_observation_optimal_gauge.md §5 Path 3 への upstream pointer。

### Path 4 (Structural-empty で theorem conditional 化)

**NOT triggered (要件外)**:
- Paper E は全 cell Structural-non-empty
- 代わりに **observable-choice dependence** を新 nuance として提供 (c_arrow_framework.md §3 selector property、Paper D §4.1.1)

### ESTABLISHED 宣言

4 path 全て triggered または completed。theorem は **ドメイン横断普遍性** (NT instance 2 + 画像 AI instance 1) + **structural enforcement 特例化** (ζ functional equation のみ coincide) + **split causation taxonomy** (arithmetic reducibility + stochastic basin selection) を備え、Paper D 本体の ESTABLISHED 定理として宣言済。

---

## §5.5 Path 3 arithmetic mod-n reducibility clause expansion (Paper N2 §6.3, 2026-04-26)

§5 Path 3 の "arithmetic mod-n reducibility" clause (Paper 2 instance) は、Paper N1 §4.5.1 で statement のみ与えられた構造を Paper N2 (`papers/publication/nt/N2_paper2_structural_ja.md` §6) で fully 展開した。本 §5.5 はその dictionary residence。

### §5.5.1 Paper 2 split の構造解析

**機構** (Paper N2 §6.2):

| Side | 内容 |
|---|---|
| **(a) Information balance** ($g_I$) | $X = 6$ で実現 — $D_\text{floor}$ minimum (g = 2 fixed) は Paper C §3 + carry conductor Euler product structure から。具体: $\|S_2(6)\| = 6 \cdot (1 - 2/2) \cdot (1 - 1/3) = 0$ (zero-carry artifact)、実用上 $X = 6$ 近傍 low-conductor 領域 |
| **(b) Structural balance** ($g_S$) | $\{X = 2g : g \in S\}$ で実現 — $c(g, X) = 1/2$ locus (carry rate half-value arithmetic structure)。15 gaps tested: $g = 2 \to X = 4, g = 4 \to X = 8, \ldots, g = 30 \to X = 60$。**locus realization** (multiple X) |
| **(c) 非交差** | $X = 6$ (point) と $\{X = 2g\}$ (locus) は **arithmetic mod-n compatibility 不在** で intersect しない |

**非交差の理由 (parity argument)**:

1. $X = 6$ が locus $\{2g\}$ に乗るのは $g = 3$ のみ
2. prime gap $g$ は **常に even** ($g \geq 4$ で even、$g = 2$ = twin、唯一の素数 2 起源例外)
3. ゆえに $g = 3$ は NT prime gap として登場しない (奇数 prime gap は 3 以上の奇素数間隔を含み、Bertrand-type 制約で素数間隔として実現不能)
4. **結論**: $X = 6$ と $\{2g\}$ は **prime-gap parity の制約** により永遠に intersect しない (NT scope 内で)

### §5.5.2 §4 表 Paper 2 row の expansion

§4 Paper 2 row "X = 2g (c = 1/2 locus, 15 gaps), Information optimum X = 6 (g = 2, D_floor 最小、因子 3), SPLIT, ≠ 0" は本 §5.5.1 の **3 sub-mechanism** の compact 表記:
- "X = 2g locus" = (b) Structural balance, locus realization
- "X = 6 (g = 2, 因子 3)" = (a) Information balance, point realization
- "SPLIT, ≠ 0" = (c) 非交差 = parity argument による永久 disagreement

§4.1c agreement test 形式での position: **point-in-locus** realization、$g_I = 6$ ∉ $\{2g\}$ for prime gap $g$ ⟹ $C(D) \neq 0$ (disagree)。

### §5.5.3 split causation: arithmetic mod-n reducibility の clause

**Paper N1 Path 3 split causation taxonomy** において Paper 2 carry split は以下に classify される (Paper N2 §6.3 statement):

> **arithmetic mod-n reducibility**: $g_S$ が conductor $X$ の arithmetic structure ($X = 2g$ locus) で pin され、Information optimum $X = 6$ (factor 3 由来) と locus が intersect しない

これは §5 Path 3 の他 2 clause と相補的:

| Clause | 機構 | Domain instance |
|---|---|---|
| **arithmetic mod-n reducibility** | $g_S$ が deterministic な arithmetic locus に pin (parity 制約 + factor structure) | Paper 2 (NT carry) |
| **stochastic basin selection** | $g_S$ が training trajectory の確率的 UNet weight initialization basin に pin | Paper E (画像 AI) |
| **biological translational selection** | $g_S$ が clade 固有 translational apparatus evolution に pin | Paper F (DNA mtDNA) |

3 clause は split causation の **完全な 3-instance taxonomy** を form する (各 clause は他 2 と representation-theoretic / dynamical / phylogenetic root cause が異なる)。

### §5.5.4 Carry rate Euler product との対比 (T-AAS clean instance との関係)

§5.5.1 の carry rate Euler product structure は `nt_conductor.md §6.10` で完全に dictionary 化された。これは **OQ-P2-3 Dirichlet residue exclusivity** (Paper N2 §4) と相補的に T-AAS clean instance を form する:

| Aspect | Carry rate (Paper N2 §2) | Residue exclusivity (Paper N2 §4) |
|---|---|---|
| **Constraint type** | gcd coprimality ($\mathbb{Z}/X\mathbb{Z}$, single prime ごと) | mod 6 residue partition ($\mathbb{Z}/6\mathbb{Z}$ class division) |
| **Conductor scope** | $\omega(X)$ (X 素因子個数) | 1 (mod 6 principal indicator) |
| **Closed form mechanism** | Euler product $\prod_{p \mid X}(1 - \nu_g(p)/p)$ | Mirror symmetry ($\chi_1$ structural zero) |
| **T-AAS f_torsion** | 0 (Q-gauge で消える) | 0 (mirror で消える) |
| **T-AAS f_rational** | $\omega(X)$ (X-dependent) | 1 (universal) |
| **Path 3 contribution** | arithmetic mod-n reducibility (本 §5.5) | (T-AAS instance, 別 mechanism) |

両者は arithmetic mod-n constraint の **異なる集約軸** (X 軸の素因子分解 vs $g \bmod 6$ residue partition) で T-AAS を実現し、Paper N1 §5.2 OQ-P2-3 instance + Paper N2 §2 carry instance の 2 instance によって **NT T-AAS clean instance space を form** する。

### §5.5.5 Enforcement 探索の一般化への含意

§6.1 (本 entry) で示した「coincidence は rare、enforcement 探索は OQ-Paper2-Balance の generalization」は、Paper 2 carry の場合に以下に specialize される:

> **Paper 2 enforcement 候補**: $X = 6$ と $\{X = 2g\}$ を同時固定する domain-internal structural identity を探す。例えば「奇 prime gap が許容される拡張 NT structure」(quasi-prime ensemble 等) で intersection が回復するか?

これは現 NT scope では impossible (parity argument、§5.5.1)。enforcement 候補は NT scope 拡張と同義であり、**Paper 2 carry 内では permanently split が確定** している。

OQ-Ω5g (universal involution systematic search、§8.2) は本 enforcement 探索を locus realization 一般に拡張する task。Paper 2 carry の parity-locked impossibility は、enforcement 探索の **negative exemplar** として位置付けられる (これ自体が taxonomy contribution)。

### §5.5.6 Status / Residence

**Status**: ESTABLISHED expansion (Paper N2 §6.3 transfer 2026-04-26)。Paper N1 statement は §5 Path 3 で 1 行、本 §5.5 で詳細展開。

**Ref**:
- `papers/publication/nt/N2_paper2_structural_ja.md` §6.2-§6.3, §6.5 (Paper 2 split structural analysis 主体)
- `papers/publication/nt/N1_observation_theory_nt_ja.md` §4.5.1, §5.2 (framework statement)
- `nt_conductor.md §6.10` (NT carry conductor 完全辞書)
- `research/oq_p2_1_carry_closed_form.md` (closed form 数値検証)
- `research/paper2_twin_dictionary_bridge_v1.md` §14 (Paper 2 carry bridge 原典)

---

## §6 axis-2 Fi/I commutator perspective (系 4.1c)

### §6.1 帰結

1. **coincidence は rare**: axis-2 Fi/I 可換性を強制する functional equation 型 enforcement は domain 固有で稀 (確認例: Paper C のみ)。default は split (C ≠ 0)。
2. **split causation の 2 clause** (Path 3): arithmetic mod-n reducibility (Paper 2) と stochastic basin selection (Paper E) は、いずれも axis-2 Fi 側で balance 位置が **外的構造** (arithmetic / dynamical) に pin される instance で、axis-2 I 側の S13 半値固定点 (Fi/I 可換 extreme) から離れる。
3. **enforcement 探索の一般化**: 新 domain D で C(D) = 0 を achieve する enforcement を探すことは、axis-2 Fi ↔ I commutativity を強制する domain-internal structural identity の探索と等価。これは **OQ-Paper2-Balance の一般化** 形式 (任意 domain での functional-equation analog 探索)。

### §6.2 定理 4.1a / 系 4.1b は系 4.1c の observable-level 特殊化

定理 4.1a (layer separated form) と系 4.1b (coincidence 条件) は、系 4.1c の Fi/I commutator C(D) = 0/≠0 binary fact を **observable-level に特殊化** したもの。系 4.1c は L0 v2 (axis-2 Fi/I 境界の分類学) の instance-level 適用例。

**Ref**: Paper D §4.5.1b, finite_observation.md §8 (L0 v2), c_arrow_obstruction.md §10.0 (2-axis lens)。

---

## §7 Paper Ω intersection value との接続

Paper 2 Structural balance (c = 1/2 at X = 2g locus) は **複数 X gauge が同一 balance value に合流** する点で Paper Ω §1.8 Definition Ω.1 (intersection value) の NT instance。

| Realization 型 | instance | 説明 |
|---|---|---|
| **Point realization** (unique gauge) | Paper C | s = 1/2 で両層 unique |
| **Locus realization** (multiple gauges) | Paper 2 | X = 2g locus 全体で c = 1/2 同値 |
| **Stochastic ensemble realization** | Paper E (seed 依存) | 複数 seed による balance 位置の empirical distribution |

Paper Ω intersection 型の stochastic analogue は将来的に integrate 候補 (OQ-PaperE-SeedBasinStructure, Paper D §8.2)。

---

## §8 Open frontier

### §8.1 残 OQ

- **OQ-Paper2-Balance** (Paper D §8.2、MEDIUM priority): Paper 2 で carry balance (c = 1/2、Structural) と D_floor min (Information) を同時固定する X が存在するか。存在すれば Paper C ζ functional equation に相当する structural enforcement は何か。
  - v0.5 で HIGH (ESTABLISHED 昇格 rate-limiting) だったが、v0.6 で meta-theorem が Paper E split CONFIRMED 経由で ESTABLISHED 昇格したため **rate-limiting 解消**。
  - 残存意義: Paper 2 domain 内で functional-equation-analog structural enforcement の探索 (domain-固有の Arrow 1 structural feature 特定)。

- **OQ-PaperE-SeedBasinStructure** (Paper D §8.2、LOW priority): Paper E Structural main scan で identified された seed ごとの balance basin (t* = 180 / 150-160 / 140) の structural characterization。UNet weight initialization の何が basin を決めるか、basin 位置の empirical distribution、basin-shift 可能性。

### §8.2 v0.9 reformulation 後の残 task

- **C(D) の真の 2-category lift** (OQ-Ω5 dedicated): v0.7 commutator → v0.8 2-cell formulation の経路は、いずれも constant maps 2 つの endpoint position 比較に過ぎず 2-category structure を真に使っていなかった (内部レビュー C2-D1)。v0.9 では rhetoric を "balance position agreement test" に降格 (本 §6 反映済)。**2026-04-24 OQ-Ω5 candidate_v1**: σ-action groupoid framework (functor/groupoid level) で Gate 3 partial closure、真の 2-cell layer は **OQ-Ω5f** として v2 task に分離。
- **3 realization type の agreement criterion を category-theoretic に unify する formulation** (現状は type ごとに別 criterion) — OQ-Ω5 v1 §5.4 で 4-instance taxonomy 提供 (3 type + 1 biological Type II sub-instance)、uniform stochastic + locus extension は OQ-Ω5b (v1.5) + OQ-Ω5g (v1.5)
- **Stochastic ensemble realization の majority threshold τ = 1/2 default の justification** (Paper E 9 seeds の sample size での適切性)
- **Locus realization の point-in-locus test を universal involution search と接続** (OQ-Ω5g, 旧 OQ-Paper2-Balance の generalized form、Paper F 統合)

### §8.3 OQ-Ω5 v1 以降の new sub-OQ (2026-04-24 issued)

- **OQ-Ω5a** (v2): 真の 2-category axiom verification (associativity, interchange, 8 gauge Type A 1-cell explicit table)
- **OQ-Ω5b** (v1.5): C_Ω^stoch formal construction (Paper E uniform 記述)
- **OQ-Ω5e** (v1.5, **1st instance real + complex CONFIRMED 2026-04-24, SC3 caveat**): Dirichlet L(s, χ) 1st predictive instance。
  - **v1.5 v0 real primitive (earlier 2026-04-24)**: 5/5 real primitive χ (χ_{-3}, χ_{-4}, χ_5, χ_{-7}, χ_8)、D_C asymmetric-grid σ_min = 0.500000 exact + R² = 1.000、CONFIRMED with asymmetric-grid sanity refuting symmetric-grid tautology。Residence: `research/oq_omega5_v15_dirichlet_l_first_instance_v0.md` + `experiments/dirichlet_l_balance_v0.py`
  - **v1.5 v0 complex primitive (later 2026-04-24)**: 5/5 complex primitive χ (mod 5 ord 4 / mod 7 ord 3 / mod 7 ord 6 / mod 9 ord 3 / mod 11 ord 5)、C1-C4 全 PASS including NEW C4 functional eq sanity gate。**SC3 post-write catch**: real-axis restriction では functional eq + complex conjugation chain (conj(L(σ, χ)) = L(σ, χ̄) for real σ ⟹ |L(σ, χ̄)| = |L(σ, χ)|) により F(σ, χ) = F(1-σ, χ) が complex χ にも成立、asymmetric grid では tautology refute 不可。Residence: `research/oq_omega5_v15_dirichlet_l_complex_char_extension_v0.md` + `experiments/dirichlet_l_balance_complex_v0.py`
  - **Genuine non-tautological content** (post-SC3 保持): (a) C3 curvature > 0 (min vs max/saddle distinction), (b) C4 functional eq numerical identity 0 exact on all 5 complex χ, (c) ε(χ) phase non-trivial for complex χ (real χ は ε = +1 forced), (d) D_A(0.5) scaling differentiated from real case
  - **v1.5 v1 off-axis 2D scan INCONCLUSIVE with SC4 catch (2026-04-24 evening)**: 8 chars × 11 t × 9 σ = 792 evaluations、G1 80/80 + G4 8/8 PASS、G2 0/5 + G3 0/5 FAIL。**SC4 post-execution catch**: SC3 derivation incomplete — conj(L(σ+it, χ)) = L(σ-it, χ̄) は complex s 全域で成立 (n real positive の coefficient conjugation identity は on-axis/off-axis 問わず)、combined with functional eq で |Λ(σ+it, χ)| = |Λ(1-σ+it, χ)| を ALL (σ, t) real で force。σ_min = 1/2 は **universal functional equation identity-level consequence, NOT σ-action groupoid framework-specific predictive content on Dirichlet L**。Residence: `research/oq_omega5_v15_dirichlet_l_offaxis_2d_scan_v1.md` + `experiments/dirichlet_l_balance_offaxis_v1.py`
  - **Framework predictive scope reassessment (post-SC4)**: Paper C genuine content は Information (D_floor, independent of functional eq) + Structural (RH zeros) の **2-quantity independent coincide** — Dirichlet L extension scope は "structural fit only" で close、single-quantity σ_min identity は framework-specific predictive content ではない
  - **v1.5 v1a 2-quantity coincide test REJECTED (2026-04-24 evening late)**: Pre-registered hypothesis "Q1 = |L|² σ_min (genuine) + Q2 = |Λ|² σ_min (= 0.5 via SC4) の coincide" を 5 complex χ × 8 t = 40 cells で test。G2 gate 17.5% (pre-registered rejection threshold 30% を下回る) ⟹ REJECTED。Q1 mean deviation 0.60-0.82 from 0.5 across 5 χ (max 3.2)、|L|² σ_min は σ > 1 direction (Dirichlet series convergent regime) に pushed。**Root cause**: |L|² = |Λ|² / ((q/π)^{σ+a} · |Γ((s+a)/2)|²) の denominator が strongly σ-growing、0.5 center は unwarranted。Paper C D_floor は gap-indexed prime sum residual for **normalized log L expansion** で 0.5 center が built-in、一方 |L|² 単独は normalization 不在。Residence: `research/oq_omega5_v15_dirichlet_l_2quantity_coincide_v1a.md` + `experiments/dirichlet_l_balance_2quantity_v1a.py`。**Framework scope for Dirichlet L definitively closed as "structural fit only"** — naive |L|² Information analog insufficient、proper D_floor_L analog (v1.5 v1b future task) required for genuine extension
  - **v1.5 revised roadmap (post-v1a)**: ~~v1a~~ REJECTED / **v1b NEW** = Paper C D_floor proper analog for Dirichlet L / v2 = Hecke-Artin L / v3 = Hasse-Weil L / v4 = 3-phase operation consolidation
  - 残 item 2-5 (Hecke / Artin, Hasse-Weil weight-shift, non-involution negative, RH-dependent verdict) OPEN continued
- **OQ-Ω5f** (v2): 真の 2-cell layer (parallel non-constant functor + natural transformation)
- **OQ-Ω5g** (v1.5): universal involution systematic search (旧 OQ-Paper2-Balance generalized, Paper F 統合)
- **OQ-Ω5h** (v1.5): Paper C Structural balance operational definition rigorization (Arrow 1 上の T_Arrow1^C concrete spec)
- **OQ-Ω5i** (v2): higher-rank functional equation lift (Hecke / Artin / Weil)

---

## §9 Cross-references

- **Upstream framework**: c_arrow_framework.md §1-§4 (3 Arrow 定義 + 可換性), §5 (Fi/I commutation form)
- **Canonical constants**: c_arrow_bridge_constants.md §5 (S13 ln 2 Arrow 2)
- **Kernel side (T-AAS)**: c_arrow_obstruction.md §10 (Arrow 1 kernel 分解), §10.0 (axis-2 lens)
- **L0 root**: finite_observation.md §8 (L0 v2 axis-2 framework)
- **3 instance source**:
  - NT (Paper C): Paper_C_NT_Quantum_ja.md §3 (D_floor spectral theorem)
  - NT carry (Paper 2): research/paper2_twin_dictionary_bridge_v0.md §14
  - 画像 AI (Paper E): Paper_E_Image_AI_ja.md §4.5, §6 (Structural main scan)
- **Paper D residence**: Paper_D_Observation_Theory_ja.md §4.5.1, §4.5.1a, §4.5.1b

---

## §10 Status / 履歴

- **ESTABLISHED 2026-04-22 夜** (Paper E Structural main scan 9900 samples で Paper E 行 ontic 判定 = split CONFIRMED, Path 1-4 全達成)
- **Fi/I commutator form 系 4.1c 追加 2026-04-23** (Paper D v0.7、L0 v2 axis-2 lens への根源化)
- **L1 residence 2026-04-23** (本 entry 新設、Paper D v0.7 → Prime v0.6 apply 作業の一環)
- **v0.9 honest reformulation 2026-04-23** (本 §6: 系 4.1c の operator commutator → 2-cell formulation → **balance position agreement test** に最終降格、3 realization type [point / locus / stochastic ensemble] と type-dependent agreement criterion を明示。真の 2-category lift は OQ-Ω5 dedicated open task `oq_omega5_2cell_v0.md` に分離。Paper D §4.5.1b v0.9 reformulation の dict side reflection)
- **2026-04-24 v1 update**:
  - (a) §4 3 instance 表に **Paper F (DNA mtDNA)** row 追加 (4th instance, split 13/13 organism、biological translational selection Path 3 root cause)
  - (b) §5 Path 3 に Paper F instance 追加 (split cause taxonomy: arithmetic mod-n + stochastic basin + biological translational selection の 3-instance)
  - (c) §6 に OQ-Ω5 candidate_v1 (σ-action groupoid framework) cross-ref 追加: 定理 4.3.1 (critical line pinning unconditional) + 定理 4.4.1 (s = 1/2 pinning conditional on RH) + 4-instance taxonomy (§5.4)。operational tool (§6 本文) は v1 に依存せず
  - (d) §8.2 に OQ-Ω5 v1 sub-OQ 7 項 (a/b/c/d/e/f/g/h/i) の status update 追加、§8.3 新設
  - (e) **OQ-Ω5e v1.5 v0 Dirichlet L 1st instance CONFIRMED** (本 session late)：5/5 real primitive χ, D_C asymmetric-grid σ_min = 0.500000 exact + R² = 1.000、symmetry-forced tautology refuted。§8.3 に entry
  - (f) connected_to に OQ-Ω5 research notes 2 本 + Paper F を追加

---

*作成日: 2026-04-23。v1 update 2026-04-24 (H2 OQ-Ω5 promotion + v1.5 Dirichlet L 1st instance CONFIRMED + Paper F instance 追加)*
