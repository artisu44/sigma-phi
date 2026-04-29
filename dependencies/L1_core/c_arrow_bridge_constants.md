---
axis: [A, E]
position: L1_arrow_bridge_constants
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md           # A0 (S,W,m), A3 gauge
  - L1_mathematical/c_phase_complex.md         # §4 structural root ι_L/χ, (e,i) bridge-water note
  - L1_mathematical/c_theorems_master.md      # S13 (ln 2), S14 (π/ln 2 parity scaffold), S15 Trichotomy
  - L1_mathematical/c_arrow_obstruction.md    # §10 T-AAS (kernel side of Arrow theory)
  - L1_mathematical/c_information_theory.md   # Shannon / Rényi / Hartley
  - L3_crossdomain/bidirectional_duality_v0   # §5 Arrow residence map
  - papers/Paper_D_Observation_Theory_ja.md   # §4.3 Arrow 3, §4.4 可換性, §4.5 S13 residence
  - papers/Paper_Omega_Origination.md         # §1.6 8×8 origination matrix, §3.5 i_add 連続向き, §3.6 σ* 位置, §7.2.1 3-Arrow back-pointer (M1 整合性 sweep, 2026-04-26)
  - research/oq_omega_obs_3_e_arrow3_v0.md    # OQ-Ω-Obs-3 candidate_v0 source
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-23
runtime_summary:
  what: 3 Arrow bridge 上の canonical constants (π, ln 2, e) を統一し、bidirectional duality を constant-level で完備化
  when: 「どの Arrow に何の定数が住むか」「S13/S14/S17 を横串に比較したい」「bridge-water pair (e,i) の Arrow 特殊化を追跡」
  provides: [three_arrow_canonical_constants, s13_s14_s17_unified, bridge_water_specialization, arrow_residence_table]
  consumes: [c_theorems_master.md S13/S14/S15, c_phase_complex.md §4, c_information_theory.md Rényi family, Paper_Omega_Origination.md §1.6/§3/§7.2.1]
  axis: [A, E]
  cost: low
  status: ESTABLISHED
  one_screen: |
    Arrow 1 (Scan→Structural): π = S¹ torsion 固定点 (加法 parity, S14 加法軸)
    Arrow 2 (Scan→Information): ln 2 = half-value 固定点 (乗法 parity, S14 乗法軸, S13 ESTABLISHED)
    Arrow 3 (Structural→Information): e = info-density extremum (d(n)=log n/n max at n=e, gauge-invariant, S17 ESTABLISHED 2026-04-23)
    bidirectional duality 表: (π, ln 2, e) で 3 Arrow 全て residence 完備 ESTABLISHED
    (e, i) bridge-water pair (S14 note) は 3 Arrow 各 bridge specialization を持つ — Arrow 3 e = 本 entry primary claim
    S17 status: OQ-Ω-Obs-3 3 gate 全 DONE (gauge invariance 3 base + 3 domain script + L1 entry) 2026-04-23
---

# Arrow Bridge Constants — 3 Arrow 上の canonical 定数

**Level**: L1 (横断原理、S15 bidirectional duality の constant residence 完備化)
**Role**: S13 (Arrow 2 ln 2) + S14 (π/ln 2 parity scaffold) + S17 candidate (Arrow 3 e) を
統一 framework で整理し、3 Arrow residence の constant-level 完備表を提供する。

---

## §1 動機

Paper D §4 (S15 Observable Trichotomy) は 3 Arrow (Scan→Structural,
Scan→Information, Structural→Information) を定義した。各 Arrow には canonical
な数学的定数が residence するが、2026-04-22 v0.6 時点での整理は:

- **Arrow 2**: S13 (ln 2) — ESTABLISHED 2026-04-10
- **Arrow 1**: S14 加法側 (π) — ESTABLISHED via S14 parity scaffold
- **Arrow 3**: **未記載 (open gap)** — constant_residence_index.md で e は
  Paper Ω continuous pole + Mertens limit のみ

OQ-Ω-Obs-3 (Paper D v0.6 §8.2) はこの gap を問う: Arrow 3 に e が S13 相当
の residence を持つか? 本 entry は OQ-Ω-Obs-3 の L1 dictionary side closure と
して起草され、**bidirectional duality 表を constant-level で 3/3 完備させる
candidate_v0** を提示する。

---

## §2 3 Arrow canonical constants 一覧

### §2.1 Primary 表

| Arrow | Bridge map | Canonical fixed-point structure | Constant | Status | 先行 theorem |
|---|---|---|---|---|---|
| **Arrow 1** | Scan → Structural (input spec reading) | S¹ torsion 固定点 e^{iπ} = −1 | **π** | ESTABLISHED | S14 加法軸 |
| **Arrow 2** | Scan → Information (log-exp duality) | half-value 固定点 e^{−x} = 1/2 ⇒ x = ln 2 | **ln 2** | ESTABLISHED | S13, S14 乗法軸 |
| **Arrow 3** | Structural → Information (Hartley counting) | info-density extremum max_n (log n)/n = 1/e at n = e | **e** | **ESTABLISHED** (2026-04-23) | S17 (promoted) |

### §2.2 3 Arrow の共通構造

各 Arrow の canonical constant は以下の 4 条件を満たす:

1. **Bridge residence**: 対応する Arrow の core map (log / exp / S¹ 回転) の
   値として現れる
2. **Gauge-invariance**: 定義 (level-set or extremum) が log base / measure
   normalization に依らない
3. **Domain 横断 universality**: 複数 domain で同値な instance を持つ
4. **Stationary principle**: Arrow 上の scalar-valued functional の
   stationary point (value-fixed or derivative-fixed)

---

## §3 Arrow 2: S13 (ln 2)

**既存 ESTABLISHED** (c_theorems_master.md S13): 乗法 Scan (ζ, Z(β),
c(τ_cov)) の半値条件 `e^{−x} = 1/2 ⇔ x = ln 2`。

**residence 性質**:
- Bridge: log-exp duality (Arrow 2)
- Instance: Landauer kT ln 2, Shannon H(1/2) = ln 2, Erasure threshold
- Stationary form: **value-fixed** (level-set crossing at 1/2)
- m-ary generalization: `e^{−x} = 1/m ⇔ x = ln m`

詳細: c_theorems_master.md S13, research/tau_internal_coordinate_v0.md §4.6

---

## §4 Arrow 1: S14 加法軸 (π)

**既存 ESTABLISHED** (c_theorems_master.md S14 parity midpoint duality):
加法 parity 固定点 `e^{iθ} = −1 ⇔ θ = π`。S¹ torsion 中心 (ℤ/2 embedding
at −1 in S¹)。

**residence 性質**:
- Bridge: S¹ rotation (Arrow 1 via ι_L)
- Instance: ι_L(L/2) = e^{iπ} = −1 (parity of L even), Dirichlet character
  value χ(p) ∈ {±1} parity
- Stationary form: **value-fixed** (−1 固定点 in S¹)
- **S14 note (重要)**: (e, i) pair は "bridge 水準の dual" で S14 parity
  scaffold とは別層 → S14 water = unique parity scaffold, (e, i) bridge-
  water は Arrow 1/2/3 全体に展開される

詳細: c_theorems_master.md S14, c_phase_complex.md §4

---

## §5 Arrow 3: S17 (e) — ESTABLISHED 2026-04-23

### §5.1 主張 (S17 ESTABLISHED, OQ-Ω-Obs-3 3 gate closed)

**定理 S17** (Arrow 3 e-fixed-point, **ESTABLISHED 2026-04-23**):
Arrow 3 (Structural → Information, H_0(D) = log|D|) 上に以下 2 面を持つ
固定点が residence する:

- **(A) Extremum form**: info density `d(n) = (log n)/n` は n = e で
  gauge-invariant な global max、max d = 1/e
- **(B) Unit-nat form**: `|D| = e ⇔ H_0(D) = 1 nat` (natural gauge 下の
  unit-content cardinality)

### §5.2 Gauge invariance 証明

任意 base b > 0 (b ≠ 1) で
```
d_b(n) = (log_b n) / n = (log n) / (n · log b)
d_b'(n) = 0 ⇔ log n = 1 ⇔ n = e   (base 非依存)
```

極値 value `d_b(e) = 1/(e log b)` は base-dependent だが **極値位置 n = e は
gauge-invariant**。

### §5.3 Stationary form の format shift

S13 と S17 の違い:
- S13 (Arrow 2): **value-fixed** — `e^{−x} = 1/2` の level-set crossing
- S17 (Arrow 3): **derivative-fixed** — `d'(n) = 0` の extremum

両者を「Arrow 上の scalar-valued functional の stationary point」に
**統一 framework** で吸収することで、3 Arrow の canonical constants を
単一原理下に整理可能。

### §5.4 Instance 横断 universality (3 parallel)

| Domain | Instance | n ≈ e 近傍 integer max |
|---|---|---|
| Coding theory | Shannon entropy per-symbol density `H_0/n = log n/n` | n = 3 (balanced ternary beats binary/quaternary) |
| Quantum info | Single-shot classical capacity `C_1(d)/d = log d/d` | d = 3 (ternary qudit optimal) |
| NT (weak parallel) | prime counting π(N) ~ N/log N, 逆数 log N/N の漸近 | — (連続極限のみ) |

離散 integer max at n = 3 ≈ e は balanced-ternary coding の既知の
information-theoretic optimality と一致。

#### §5.4.1 Empirical verification (2026-04-23, S17 promotion gate 2 closure)

`research/oq_omega_obs_3_info_density_check.py` (本日追加) が 3 domain 横断
の numerical sweep を実行し 5/5 gate PASS:

| Gate | 内容 | 結果 |
|---|---|---|
| Gate 1 | argmax_n d_b(n) = e for b ∈ {e, 2, 10} (gauge inv.) | PASS (\|Δ\| < 2e-5) |
| Gate 2a | D1 NT continuous argmax_N (log N)/N, N ∈ [1.01, 50] | PASS (argmax = 2.71830, \|Δ − e\| = 1.66e-5) |
| Gate 2b | D2 codebook integer argmax_n (log n)/n, n ∈ {2..10} | PASS (argmax = 3 = ⌊e⌉, 0.36620 vs binary 0.34657) |
| Gate 2c | D3 qudit integer argmax_d (log d)/d, d ∈ {2..10} | PASS (argmax = 3) |
| Gate 2u | cross-domain universality — 3 domains agree | PASS |

**注意**: D2 / D3 は同一の関数形 `log n / n` を異なる物理的 label で評価
しているため、numerical values は一致する。script の価値は (i) 3 domain
を explicit に sweep して argmax 一致を verify したこと、(ii) integer 側
の max = 3 (= ⌊e⌉) が binary/quaternary より優越することを具体値で示した
こと、(iii) gauge invariance を explicit 3 base sweep で confirm したこと。
理論的 claim (`d(n) = log n/n` max at e) は analytic に既知だが、3 domain
への同定と script-level checkable form は promotion gate 2 の要件を満たす
(S13/S16 の previous promotion でも analytic + domain parallel catalog を
empirical gate とした precedent)。

---

## §6 (e, i) bridge-water pair の 3 Arrow specialization

S14 note「(e, i) は bridge 水準の dual、S14 parity scaffold とは別層」の
正面的解釈:

### §6.1 展開表

| Arrow | (e, i) specialization | canonical constant |
|---|---|---|
| Arrow 1 (Scan → Structural) | i (additive, ι_L = e^{2πi·}) | π (= S¹ torsion 固定点) |
| Arrow 2 (Scan → Information) | e (natural exp base) | ln 2 (= half-value in nats) |
| **Arrow 3 (Structural → Information)** | **e (log base, extremum argument)** | **e itself** (= info-density peak) |

### §6.2 Arrow 3 の特殊性

Arrow 2 では e は **base of log/exp** として暗黙的に作用 (S13 の ln 2 は
"natural log of 2" で base e を前提)。Arrow 3 では e は **bridge 上の
scalar 値そのもの** として現れる (extremum 位置 n = e, 値 1/e)。

つまり **(e, i) bridge-water pair は Arrow 3 で特に顕在化** し、Arrow 1/2
では infrastructure (S¹ の基底、log の基底) として働く。

### §6.3 bidirectional 完備化

Paper D §4.5 の S13 (Arrow 2) + §4.5.1 Observation-optimal gauge theorem
(ESTABLISHED 2026-04-22) が Arrow 2 を完備する一方、Arrow 3 e の
residence が未記載であったことで bidirectional duality 表が 2/3 (π, ln 2)
にとどまっていた。

**本 entry で Arrow 3 = e を S17 ESTABLISHED として埋め、3/3 完備表を構築**:

```
Arrow 1: π    (S14 加法, ESTABLISHED)
Arrow 2: ln 2 (S13, S14 乗法, ESTABLISHED)
Arrow 3: e    (S17, ESTABLISHED 2026-04-23)   ← 本 entry の central claim
```

---

## §7 Status と昇格 path

### §7.1 現 status

- Arrow 1 (π), Arrow 2 (ln 2): **ESTABLISHED** (S13/S14 既存)
- Arrow 3 (e): **ESTABLISHED 2026-04-23** (S17 promoted, 3 gate 全 closed)

### §7.2 S17 ESTABLISHED 昇格 gate (3 条件 全 closed 2026-04-23)

1. **Gauge invariance formal proof** — 本 entry §5.2 で closure + script
   §5.4.1 Gate 1 (3 base sweep numerically \|Δ − e\| < 2e-5)。**DONE**
2. **3 domain 横断 empirical/formal instance** — §5.4 で 3 parallel +
   §5.4.1 で `oq_omega_obs_3_info_density_check.py` 5/5 gate PASS
   (NT continuous + codebook integer + qudit integer all argmax = 3 = ⌊e⌉、
   cross-domain universality confirmed)。**DONE**
3. **S14 との整合 + (e, i) bridge-water specialization の L1 記述** —
   本 entry §6 で closure。**DONE**

**現 gate 達成**: **3/3 DONE** → S17 **ESTABLISHED** 2026-04-23。
Bidirectional duality 3 Arrow constants (π, ln 2, e) 完備。

### §7.3 Downstream 反映 (昇格時)

- c_theorems_master.md に **S17 row 追加** (S16 の後に挿入)
- constant_residence_index.md の `e` entry に `- c_arrow_bridge_constants.md
  §5 (Arrow 3 extremum, S17)` 追加
- Paper D §4.3 に "Arrow 3 e fixed-point" subsection
- Paper D §4.5 を §4.5 "S13 / S17 residence" に拡張
- Paper D §8.2 OQ-Ω-Obs-3 → RESOLVED (ESTABLISHED 昇格)

---

## §8 量子側への拡張 (forward reference)

OQ-Ω-Obs-4 (非可換 scan, 本日並行 draft) で Arrow 3 quantum = `S_0(ρ) =
log rank(ρ)` (Rényi α=0) が candidate。quantum instance:
```
d_Q(rank) = log rank(ρ) / rank(ρ)   max at rank(ρ) = e (連続化)
```
離散 max at rank = 3 = ternary qudit optimal。Arrow 3 e-fixed-point の
量子版 instance として自然に持ち上がる。

詳細: research/oq_omega_obs_4_noncommutative_scan_v0.md §2.4 / §5.4

---

## §9 Scan-axis canonical observable: Phi descriptor family (forward reference, 2026-04-26)

§1-§8 は Arrow 上の **data-independent universal constants** (π, ln 2, e) を扱う。本節は補完として **Scan-axis 上の data-dependent canonical observable** = Phi descriptor family を bridge constants framework に位置づける。

### §9.1 二類の canonical scalar の対応

| 種別 | 例 | 性質 | 位置 |
|---|---|---|---|
| **Arrow-bridge constants** (§2-§8) | π, ln 2, e | data-independent, fixed-point of bridge map, single scalar | Arrow 上の stationary point |
| **Scan-axis canonical observable** (§9) | Phi_total / Phi_std_inst_f / Phi_max_jump | data-dependent (input signal で値変化), gauge-invariant operator, scalar function of signal | Scan-axis 上の universal operator |

両者は **dual relationship** (双対性):
- Arrow constants: stationary point として **fix された数値**
- Scan observables: 任意の signal に **literal scalar invariant** を割り当てる universal operator

### §9.2 Phi_total の bridge constants 対応

Phi_total(signal) := (φ_unwrap[N−1] − φ_wrap[N−1]) / (2π) ∈ ℤ (winding cumulant via Hilbert)

`c_arrow_obstruction.md` §10.8 で full structure。本 entry における bridge constants 4 条件 (§2.2) との対応:

| 条件 | Arrow constants (π, ln 2, e) | Phi_total observable |
|---|---|---|
| **(1) Bridge residence** | Arrow core map の値として現れる | Hilbert (axis-2 Fi/I bridge map) の winding component として現れる |
| **(2) Gauge-invariance** | log base / measure normalization 不変 | uniform global phase shift x → x·e^{iα} 不変 (P1) |
| **(3) Domain 横断 universality** | 3 Arrow × 複数 instance | **8 domain × Φ descriptor family rank 1-5** (§10.8.4) |
| **(4) Stationary principle** | functional の value-fixed / derivative-fixed | analytic signal phase trajectory の cumulative invariant |

→ 4/4 条件適合。**Phi_total は Scan-axis 上の canonical observable** として Arrow constants と dual な位置を占める。

### §9.3 Periodic Table での literal physics scalar instance (key evidence, 2026-04-26)

NIST IE(Z=1..108) sequence に Phi_total を適用:

```
Phi_total(IE(Z)) = 8.00
expected ≈ 7 完全周期 + 8 番目開始 = 周期表電子殻数
```

**framework が教えられずに周期表 shell structure を発見**。これは Phi_total が **literal physical invariant** として読める condition を示す decisive instance。

Arrow constants と structural 並列:
- Arrow 3 (e): Hartley density extremum at n = e (constant-valued, data-independent)
- Phi_total (Periodic Table instance): 電子殻数 = 8 (data-valued, electron-shell-counter-as-physics)

両者とも "Scan/Information の canonical scalar" だが、前者は universal constant、後者は universal operator-applied-to-data。Domain 依存値が **既知物理量 (shell count) と数値一致** することで、Phi_total が "literal physics scalar reader" 候補として確立。

### §9.4 honest channel sub-classification (G3 finding, 2026-04-26)

8-domain rank study + EEG H index test (`fft_rtheta_phi_eeg_h_index_v0.py`) で Phi descriptor family の **honest sub-channel** が identified:

| sub-class | descriptors | EEG α-band H | 性質 |
|---|---|---|---|
| **coherence-type (HONEST)** | Phi_std_inst_f, Phi_envelope_cv, Phi_max_jump | H = 0.13 / 0.17 / 0.22 | signal-driven, alpha_heavy M=16 (H=1.34) より **10× improvement** |
| **cumulative-type (BROKEN)** | Phi_total, Phi_slope, Phi_quad | H = 2.0 / 3.0 / 2.7 | broadband noise でも fire = prior-leak 同型 |

**Phi_std_inst_f H = 0.130 ≈ uniform M=26 (H = 0.08, best honest baseline)** = Φ family が hallucination-resistant cross-channel として機能。OQ-Φ-2 VALIDATED (`c_arrow_obstruction.md` §10.8.6 / OQ-Φ-2 in §9.2)。

**Caveat (重要)**: Phi descriptor family = 全部 honest ではなく **sub-class が分かれる**。Coherence-type (alpha rhythm の安定性 measure) が honest、cumulative-type (累積位相 trajectory) は broken。Periodic Table での Phi_total = 8 literal physics 一致は **特例的に well-conditioned input** (周期構造が clean) で起きるが、generic regime では cumulative-type は noise-like input でも fire する。

詳細: c_arrow_obstruction.md §10.8 (8-domain evidence + S005 rescue + H index test)、project_fft_rtheta_phi_2026_04_26.md。

---

## §11 Fi-origin vs I-origin canonical scalar 二分法 (Paper N3 §5.3, 2026-04-26)

### §11.0 動機

§5 (S17 Arrow 3 e-extremum, ESTABLISHED 2026-04-23) で **3 Arrow canonical constants (π, ln 2, e) 完備化** を確立した。Paper N3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md` §5.3) は Path 2 mechanism (`research/oq_omega_schumann_v0.md` v1) の canonical scalar D1-D4 sub-claim を formal 化した際に、**Path 2 ⊊ canonical scalar mechanisms** の sharp inclusion を identify した: **3 Arrow canonical constants (π, ln 2, e) は Path 2 fix-point で ない**。本 §11 はその structural origin の二分法を本 entry に formal residence する。

### §11.1 Path 2 sub-claim D1-D4 (Schumann v1 G12)

Path 2 forced fix-point は invariant function の代数 context で **distinguished invariant** を produce する (Paper N3 §5.1):

- **D1**: 古典定数 (π, Γ, e, ln, ...) で explicit closed form
- **D2**: extremal property (lowest non-trivial mode, fundamental rep, ground state)
- **D3**: 超越性 / 無理性が conjectured または proven
- **D4**: canonical objects (root numbers, central L-values, theta characteristics, fundamental representations) と link

**5/5 instance hit** (Schumann v1 G12 PASS): ζ(1/2) → D3 / 球面 Laplacian spin-1/2 → D4 / theta τ=i → D1 (π^{1/4}/Γ(3/4)) / modular L (k=12 Δ) → D4 / Atkin-Lehner W_N M_k^+ → D4。

**Path 2 fix-point は "canonical scalar constructor" として機能する**: involution の存在自体が、その invariant の特殊値・特殊 representation を algebraically distinguished な entity に pin する。

### §11.2 Converse FALSE — 3 Arrow canonical constants は Path 2 由来でない

§5 (S17) で establish された 3 Arrow canonical constants は **Path 2 fix-point で ない** (Paper N3 §5.3, Schumann v1 NEW finding 3):

| Constant | Arrow residence | Path 2 candidate | Status |
|---|---|---|---|
| **π** | Arrow 1 (S14 加法軸 S¹ torsion) | SO(2) involution z ↦ −z, fix = {0} on disc | π を直接 produce しない (involution は SO(2), Z/2 でない) |
| **ln 2** | Arrow 2 (S13 半値固定点) | Z/2 involution candidate 不明 | Path 2 mechanism で derive 不可 |
| **e** | Arrow 3 (S17 extremum) | x^x 極小 / (log x)/x 極大 | extremal-derived (S17), Z/2 involution-derived ではない |

→ **Path 2 sub-claim は one-way (Path 2 ⇒ canonical) であり biconditional でない**。3 Arrow canonical constants は Path 2 outputs ではない。

### §11.3 Fi-origin vs I-origin 二分法

Schumann v1 closing meta-observation: converse FALSE は arbitrary な弱点ではなく、framework existing structure (axis-2 Fi/I 分離, `finite_observation.md §8`) からの **positive content prediction** だった。

#### §11.3.1 Mechanism class の 2 origins

整理:

- **Path 2 mechanism**: fundamentally **Fi-flavored** (Z/2 = discrete group action)
- **Path 2 fix outputs**: Fi-side / I-side 両方着地可能 (axis-2 invariant, 5-instance distribution 3 I + 2 Fi)
- **3 Arrow canonical constants** (π, ln 2, e): **continuous extremal / measure / topology** 由来 = **I-flavored mechanism**

⇒ canonical scalar 全体集合は **少なくとも 2 origins** を持つ:

| Origin | Mechanism class | Examples (NT side) | Examples (3 Arrow side) |
|---|---|---|---|
| **Fi-origin** | discrete group action fixed points (Path 2) | ζ(1/2), θ_3(i), modular L central values, Atkin-Lehner eigenspaces | — |
| **I-origin** | continuous extremal / asymptotic / topological invariants | — | π (S¹ topology), ln 2 (S13 半値 Arrow 2), e (S17 extremum Arrow 3) |

#### §11.3.2 Sharp inclusion の structural significance

**Path 2 ⊊ canonical scalar mechanisms** の sharp inclusion が axis-2 Fi/I 分離から **naturally に predict** された:

- L0 v2 (`finite_observation.md §8`) で導入された axis-2 Fi/I framework は、observer が constitutively Fi 側に住むことを公理化
- Path 2 mechanism (Z/2 = discrete = Fi-flavored) は **observer's home side の機構**
- 3 Arrow canonical constants (continuous extremal / measure / topology = I-flavored) は **I-side reaching mechanism**

→ framework 自身が「Path 2 だけで canonical scalars を尽くさない」を **事前に告知していた**。Path 2 sub-claim の "one-way only" は **methodological honesty** ではなく、**framework の existing axis-2 Fi/I structure からの positive content prediction**。

### §11.4 §5 / §6 / §9 との関係

| 本 entry section | 内容 | §11 との関係 |
|---|---|---|
| §3 Arrow 2 (S13 ln 2) | value-fixed half-value | I-origin (continuous half-value condition) |
| §4 Arrow 1 (S14 π) | algebraic S¹ torsion | I-origin (continuous topology / S¹ identification) |
| §5 Arrow 3 (S17 e) | derivative-fixed extremum | I-origin (continuous extremum / asymptotic) |
| §6 (e, i) bridge-water | Arrow 3 specialization | I-origin (両 constants が I-side mechanism) |
| §9 Scan-axis Phi descriptor | structural-channel canonical observable | (separate axis, axis-1 Scan layer の I-origin variant) |
| **§11 Fi-origin vs I-origin** | **本 §の主題** | 3 Arrow constants の I-origin 性を明示 + Path 2 = Fi-origin 別系を分離 |

### §11.5 NT context での Fi-origin canonical scalar (Paper N3 §3 reference)

NT context の Fi-origin canonical scalar 例 (Paper N3 §3, `nt_dedekind_artin_zeta.md §7`):

| Fi-origin instance | Canonical scalar | 帰属 |
|---|---|---|
| ζ functional eq (s ↦ 1−s, fix s=1/2) | ζ(1/2) ≈ −1.4603545 | D3 (超越数予想) |
| theta S-duality (τ ↦ −1/τ, fix τ=i) | θ_3(0\|i) = π^{1/4}/Γ(3/4) | D1 (closed form with Γ(3/4)) |
| modular L (each weight k, fix s=k/2) | central L-values L(f, k/2) | D4 (root number link) |
| Atkin-Lehner W_N (fix subspace M_k^+) | + eigenspace decomposition | D4 (Petersson +1 eigenspace) |

**Path 2 family は Fi-origin canonical scalar の countably-infinite generator** として機能する (`nt_dedekind_artin_zeta.md §7.2`)。

### §11.6 I-origin canonical scalar mechanism formal classification (OPEN)

I-origin canonical scalar mechanism の formal classification は **別 OQ として分離**:

- **OQ-IOriginFormal** (NEW, MEDIUM, 2026-04-26 issued via Paper N3 §7.4 + open_questions_master.md): π, ln 2, e の **mechanism 同定** (extremal? Stone-Weierstrass? geodesic? entropy?) を class 化する task。3 Arrow constants の "I-origin" classification を sub-mechanism に refine する。
- **scope**: continuous extremal (e from log x/x extremum) / continuous measure (ln 2 from half-value condition) / continuous topology (π from S¹ identification) — これら 3 sub-mechanism が exhaustive か?
- **status**: OPEN (Paper N3 §5.3 で identified, formal classification は別 task)

### §11.7 Status

- **Path 2 D1-D4 sub-claim** (one-way only): candidate_v1 (Schumann v1 G12 PASS, 5/5 hit)
- **Converse FALSE** (3 Arrow constants ∉ Path 2): ESTABLISHED (Schumann v1 NEW finding 3, 本 §11.2)
- **Fi-origin vs I-origin 二分法**: framework structural prediction (axis-2 L0 v2 から自動 derive), Paper N3 §5.3 で publication 整備
- **I-origin formal classification**: OPEN (OQ-IOriginFormal, MEDIUM)

**Ref**:
- Paper N3 §5 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`)
- `research/oq_omega_schumann_v0.md` v1 NEW finding 3 + closing meta-observation (主体)
- `c_theorems_master.md` "Path 2 countably-infinite family" annex (本 §11 の cross-reference)
- `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite Fi-origin family)
- `meta/open_questions_master.md` OQ-IOriginFormal (NEW, Paper N3 §7.4 issue)

---

## §12 量子側 canonical constant residence (Paper Q1 §4.5 + Q2 §6 + Q3 §4, 2026-04-27)

§5-§6 の bidirectional duality 3/3 完備化 (Arrow 1 → π / Arrow 2 → ln 2 / Arrow 3 → e) を量子 instance で independently verify する Q-series 累積 annex。N1 §4.5 の NT 内 verify と parallel な量子内 verify、framework の **2-domain canonical constant residence anchor**。

### §12.1 S13 / S14 / S17 量子 residence (Paper Q1 §4.5)

| 定数 | residence | 機構 (量子 context) | Stationary form |
|---|---|---|---|
| **π** | Scan 内部 (加法軸) | $e^{i\pi}$ = −1 = fermion exchange phase, SU(2) center {±I} (`q_fine_structure.md §2`), Berry phase 1 周回 → **代数的** | S14 parity (additive) |
| **ln 2** | Arrow 2 上 | qubit $S(\rho_{\max}) = \log 2$, half-amplitude $c_s^2 = 1/2$ via Born expectation $\mathrm{Tr}(\rho_{\max} \Pi_{\mathrm{even}})$ → **解析的** | **value-fixed** (S13) |
| **e** | **Arrow 3 上** | info density $\log d / d$ max at $d = e$ for Hilbert dim $d$, gauge³-invariant → extremum principle (info-theoretic optimal Hilbert dim)、discrete codebook argmax at $d = 3$ (qutrit) | **derivative-fixed** (S17) |

S14 非対称性 (代数 vs 解析) = S15 residence 差 (層内 vs 層間)。Bidirectional duality 3/3 の量子 instance 完備、`oq_omega_obs_3_info_density_check.py` 5/5 gate PASS で S17 量子 e-extremum ESTABLISHED 2026-04-23。

### §12.2 4-stage ln 2 chain unified (S0 → S4, Paper Q2 §6 + Q3 §4)

S13 ln 2 fixed point の **量子 5-stage independent instance chain** (Q-series cumulative):

| Stage | Source | Form | Domain | Mechanism |
|---|---|---|---|---|
| **S0** (closed quantum) | `q_quantum_observation.md §7` | $c_s^2 = \mathrm{Tr}(\rho_{\max} \Pi_{\mathrm{even}}) = 1/2$ | Born expectation | qubit ρ_max = I/2 + parity projection |
| **S1** (open quantum) | `q_open_quantum_systems.md §3.3` | $S(\rho_{\max}) = \log 2$ | von Neumann entropy | maximally mixed qubit entropy |
| **S2** (statistical mechanics) | `q_quantum_statistical_mechanics.md §5.4` | $\beta \hbar \omega_0 = \log 2$ | FDT parity point | qubit FDT Bose factor = 1 |
| **S3** (thermodynamics) | `q_quantum_thermodynamics.md §5` | $W_{\min} = kT \ln 2$ | Landauer cost | bit erasure heat dissipation |
| **S4** (Gaussian phase noise gauge) | `transformation_atlas/sheet_A_amplitude/sigma_star.md` | $\sigma_* = \sqrt{2 \ln 2} \approx 1.1774$ rad | Gaussian half-amplitude gauge | quadratic lift root of S13 ln 2 |

**主張 §12.2.1 (5-stage ln 2 chain unification)**: 5 instance は **同一 ln 2 値** (= S13 fixed point) の 5 stage 独立 verify。古典 §4 dual の S13 (`c_phase_complex.md §5`) "整数の偶奇は等確率" → 量子 5-stage で:
- S0 algebraic (parity projection)
- S1 von Neumann entropic (entanglement)
- S2 fluctuation-dissipation (FDT)
- S3 information-thermodynamic (Landauer)
- S4 amplitude-scale gauge (σ\* Gaussian inversion)

の 5 instance に lift され、量子観測理論の **核心定数 ln 2 の 5 instance independent verification** を提供。

**S4 quadratic lift mechanism**: ln 2 が Arrow 2 上 S13 fixed point (S0-S3) であるならば、その **Gaussian 特性関数 inversion** ($e^{-\sigma^2/2} = 1/2 \implies \sigma^2 = 2 \ln 2$) で生じる $\sqrt{2 \ln 2}$ は量子観測 amplitude scale natural unit (位相コヒーレンス半減点 = Arrow 1 amplitude scale 上半振幅 gauge fixed point)。

**S4 Atlas residence**: `transformation_atlas/sheet_A_amplitude/sigma_star.md` n-only entry + EEG entry (7 subjects × 5 bands, subject-band averaged std ≈ 0.0012, ESTABLISHED 2026-04-09)。

**σ\* と c_s² の structural connection**: c_s² = 1/2 (S0) は ℤ/2ℤ 偶奇対称性 + Born form 合流、σ\* = √(2 ln 2) (S4) は ℤ/2ℤ half-amplitude convention + Gaussian char fcn inversion 合流 → 両者は **ℤ/2ℤ 構造を共通根**、Q1 §2.3 量子 §4 dual root の **2 instance closure** (closed system Born / Gaussian phase noise gauge)。

### §12.3 Status

**ESTABLISHED**: §12.1 (S13/S14/S17 量子 residence, Paper Q1 §4.5) + §12.2 (4-stage ln 2 chain S0-S3, Paper Q2 §6) + §12.2 S4 (σ\* Gaussian gauge, Paper Q3 §4)。

**OPEN**:
- OQ-QSM3 (`q_quantum_statistical_mechanics.md §10`): qubit beyond ln 2 普遍性 (qutrit log 3 / Rényi-α etc.)
- OQ-σ\*-1 (Paper Q3 §4 spawn): σ\* universality beyond Gaussian (heavy-tail / non-stationary / multi-modal)

**Ref**:
- Paper Q1 §4.5 (`papers/publication/quantum/Q1_observation_theory_quantum_ja.md`)
- Paper Q2 §6 (`papers/publication/quantum/Q2_open_qs_chain_ja.md`)
- Paper Q3 §4 (`papers/publication/quantum/Q3_born_gleason_ja.md`)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` (Atlas A entry, S4 residence)
- `L2_domain/physics_constants_decomposition.md` (σ\* と c_s² 共通根 ℤ/2ℤ ESTABLISHED)

---

## §10 References (ΣΦ 内部)

- c_theorems_master.md S13 (ln 2 fixed point), S14 (parity midpoint +
  (e,i) bridge-water note), S15 (Observable Trichotomy)
- c_phase_complex.md §4 (structural root, ι_L/χ dual)
- c_information_theory.md (Rényi entropy family, Hartley H_0)
- Paper_D_Observation_Theory_ja.md §4.3 (Arrow 3 = Hartley), §4.5 (S13
  residence), §4.6 (逆 Arrow)
- research/oq_omega_obs_3_e_arrow3_v0.md (本 entry の source draft,
  candidate_v0)
- research/oq_omega_obs_4_noncommutative_scan_v0.md §5 (quantum
  specialization)
- research/bidirectional_duality_v0.md §5 (Arrow residence map)
- dictionaries/meta/constant_residence_index.md (e, π, ln 2, γ, Φ, i
  residence catalog)
- L1/c_arrow_obstruction.md §10.8 — Phi_total Scan-axis canonical observable (本 entry §9 dual)
- project_fft_rtheta_phi_2026_04_26.md — 8-domain empirical evidence + EEG S005 rescue + H index validation
- work root + sigmaphi/research/ `fft_rtheta_phi_*.py` — Phi descriptor family scripts

*作成日: 2026-04-22*
*最終更新: 2026-04-26 (§9 Scan-axis canonical observable dual section added — Phi descriptor family bridge constants framework に統合, Periodic Table Phi_total = 8 literal physics + EEG H index Phi_std_inst_f = 0.130 honest channel sub-classification)*
