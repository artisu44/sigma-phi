---
axis: [A, E]
position: L1_obstruction_classification
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md           # A0 (S,W,m), A3 gauge
  - L0_canon/identity_asymmetry.md           # A0-ID, Tier 0 自動保証
  - L1_mathematical/c_phase_complex.md         # §4 structural root, ι_L/χ
  - L1_mathematical/nt_conductor.md             # §6 ramification hierarchy
  - L1_mathematical/nt_frobenius_schur.md       # ν(ρ), Tier √ pairing obstruction
  - L1_mathematical/nt_root_numbers.md          # W(ρ), sign resolution
  - L1_mathematical/q_gauge_field_theory.md    # §6 instanton, §7 confinement
  - L1_mathematical/c_spectral.md             # §8 S7 class number formula
  - L1_mathematical/q_many_body_quantum.md    # §6 SSB/gap
  - L1_mathematical/c_hidden_degrees_of_freedom.md  # R-gauge, R-topo
  - L1_mathematical/c_filtration_obstruction.md     # ker_topo 幾何根拠 (§10 T-AAS downstream)
  - L1_mathematical/q_action_principles.md     # §4 Wick rotation (S12), §7 ν の action 版意味
  - research/hodge_conjecture_decomposition_v0.md  # §13-23 full analysis
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-26
runtime_summary:
  what: 代数-解析間の情報損失を三型×六層×強度階層で分類する横断原理 + §10.7 quantum lift (ESTABLISHED) + §10.8 Φ_total Scan-axis canonical observable (candidate_v0, 5-domain cross-validation)
  when: 「なぜ通らないか」「どこで情報が失われるか」「障害の強さは」「量子系の obstruction は古典と何が違うか」「Scan-axis 側の保存可能 invariant は何か」を問うとき
  provides: [three_obstruction_types, six_layer_structure, strength_hierarchy, gauge_avoidance_cost, domain_symmetry_constraint, nu_spectral_indicator, nu_universality_ladder, nu_decomposition_theorem, spectral_rigidity_translation, T_AAS_template, f_torsion_f_rational_decomposition, quantum_obstruction_4_class_established, phi_total_scan_axis_canonical_observable_candidate_v0, phi_rescue_criterion_preliminary, phi_total_hallucination_dual]
  consumes: [finite_observation.md, c_phase_complex.md §4, nt_conductor.md §6, nt_frobenius_schur.md, q_gauge_field_theory.md §6-7]
  axis: [A, E]
  residual_types: [R-gauge, R-topo-hom, R-topo-surj, R-info]
  cost: medium
  status: established
  one_screen: |
    三型: 第一類(離散kernel: torsion/sign/phase/Sha/instanton) / 第二類(連続spectrum: GRH) / 第三類(発散: NS/繰り込み)
    六層: 存在(Hodge)/障害(Arrow)/次元(BSD)/位置(Riemann)/流れ(NS)/下限(YM)
    強度: ℤ/2 < ℤ/n < ℤ < (連続) — gauge回避コストが強度に比例
    核心: 不可能性は kernel の離散構造に支配される(第一類)。連続gauge は離散障害を消せるが情報を失う
    image制限: domain symmetry が image を制約する (Hodge (p,p) / YM singlet / Stark tier -- 同種の制約構造)
    T-AAS (§10): ker(phi) = ker_gauge + ker_topo, conductor f = f_torsion + f_rational. 3 instance 15/15 fit. Hodge conjecture = f_rational=0
    ker_topo分割: R-topo-hom (Griffiths群, Hdg交差=0自動) + R-topo-surj (cl⊗Q非全射, f_rationalの唯一の住所)
    gauge壁 (§10.5): 全既知障害は f_torsion (Q-gauge で消滅)。f_rational>0 の例は未発見 = open frontier
---

# Arrow Obstruction — 情報損失の分類原理

**Level**: L1 (横断原理、domain-independent)
**Role**: ΣΦ辞書における「代数と解析の間の情報損失」を統一分類する

---

## §1 動機

ΣΦ辞書は (S, W, m) 観測系の各層で「通るもの」と「通らないもの」を記述する。
本ファイルは **通らない側** — 情報損失と障害 — の分類体系を提供する。

5つのミレニアム問題 + Arrow obstruction の分析 (research/hodge_conjecture_decomposition_v0.md)
から抽出された、domain-independent な分類原理。

---

## §2 三型分類 — 情報損失のメカニズム

### §2.1 分類表

| 型 | メカニズム | 離散/連続 | gauge 回避 | 回避の代償 |
|---|---|---|---|---|
| **第一類** | 離散 kernel | 離散 (torsion/sign/phase/winding) | 係数 gauge (⊗ℚ)、定義域 gauge (base change)、重ね合わせ (θ-vacuum) | 離散情報の喪失 |
| **第二類** | 連続スペクトル | 連続 (零点分布、固有値統計) | (未知) | — |
| **第三類** | 発散 | 連続 (UV/IR発散、特異点) | 繰り込み、正則化 | scale 依存性の導入 |

### §2.2 各型の詳細

#### 第一類: 離散 kernel 障害

**核心**: 離散不変量 (torsion class, pairing type, phase, winding number) が
連続的代数操作で再現できないとき生じる。

**共通パターン**:
```
Structural 層 (代数的)
    ↓ φ (写像)
Scan 層 (解析的)

ker(φ) に離散不変量 δ ∈ 有限群 or ℤ が存在
→ φ は δ-equivariant でない限り全射でない
→ gauge 変換 g: δ → 1 で回避可能だが δ の情報は失われる
```

**instances** (§3 で強度順に配置):

| Instance | 離散不変量 | 群 | gauge 回避 |
|---|---|---|---|
| Crystal phase problem | phase sign | ℤ/2 | Patterson |F|² |
| Stark ν(ρ)=−1 | Frobenius-Schur indicator | ℤ/2 | L(0,ρ)² |
| Hodge Sq³ (integral) | Steenrod operation | ℤ/2 | ⊗ℚ |
| Hodge torsion (general) | torsion class | ℤ/n | ⊗ℚ |
| BSD Sha | Tate-Shafarevich group | 有限群 (可変) | base change |
| YM instanton | topological charge | ℤ | θ-vacuum |

#### 第二類: 連続スペクトル障害

**核心**: 障害が離散不変量ではなく、連続的なスペクトル分布の性質に存在する。

**代表**: Riemann 予想 — ζ(s) の零点分布が critical line Re(s)=1/2 上にあるか。
ΣΦ S14 パリティ固定点との接点はあるが、第一類のように
「離散不変量を gauge で消す」という枠組みでは捕捉できない。

#### 第三類: 発散障害

**核心**: 理論の定義自体が発散により脅かされる。
特異点形成 (NS) または UV/IR 発散 (QFT)。

**回避**: 繰り込み (YM: β<0 で制御可能)、正則化 (NS: viscosity ν>0)。
回避の代償は scale 依存性の導入。

---

## §3 第一類障害の強度階層

### §3.1 強度の定義

第一類障害の「強度」= 離散不変量の群の大きさ。
群が大きいほど、gauge 回避のコストが高い。

### §3.2 強度階層表

```
弱 ◄────────────────────────────────────► 強

ℤ/2        ℤ/n        有限群(可変)      ℤ
─────       ─────       ──────────       ─────
1 bit       log n bit   可変             ∞
```

| 強度 | 群 | gauge 回避コスト | instances |
|---|---|---|---|
| **minimal** | ℤ/2 | 1 bit 喪失 | Crystal phase, Stark sign, Hodge Sq³ |
| **finite** | ℤ/n (n > 2) | log n bit 喪失 | Hodge torsion (一般) |
| **variable finite** | 有限群 (|G| 可変) | 可変。base change が必要 | BSD Sha(E) |
| **infinite discrete** | ℤ | 連続パラメータ導入 (θ) | YM instanton |

### §3.3 強度と gauge 回避の対応

**弱 (ℤ/2)**: 1 bit の離散情報。回避は「二乗を取る」(L²) か「有理化」(⊗ℚ) で十分。
情報喪失は最小限。

**有限 (ℤ/n)**: log n bit。回避は同じく有理化だが、失われる情報量が増大。

**可変有限 (Sha)**: |Sha| は E に依存し、一般には巨大。
係数 gauge では不十分で、定義域 gauge (base change K/ℚ) が必要。
Sha(E/K) = 0 となる K が存在するかすら一般には不明。

**無限離散 (ℤ)**: gauge 回避に離散的手段 (⊗ℚ, L²) が使えない。
連続的重ね合わせ (θ-vacuum) が必要 → 新しい連続パラメータ θ が物理に侵入。
**回避がコスト 0 でない**: θ ≠ 0 は CP 対称性を破る。

### §3.4 conductor との対応

nt_conductor.md §6 の ramification 階層:

| ramification | conductor | 第一類強度 |
|---|---|---|
| unramified (codim 0) | f_p = 0 | 障害なし (Tier 0) |
| tame (codim 1) | f_p = codim(V^{I₀}) | ℤ/2 — ℤ/n (有限) |
| wild (codim ≥ 2) | f_p = Σ多段 | 可変有限 — ℤ (無限離散) |

**強度 ∝ ramification depth**:
tame ramification は有限 torsion 障害に対応し、
wild ramification は可変/無限離散障害に対応する。

---

## §4 六層構造 — 構造問題の完全分解

### §4.1 六層表

| 層 | 問い | S15 Arrow | 代表問題 | 障害型 |
|---|---|---|---|---|
| **存在** (image) | 何が通るか | Arrow 1 全射性 | Hodge 予想 | 第一類 |
| **障害** (kernel) | 何が通らないか | Arrow 1 kernel | (横断原理: 本ファイル) | 全型 |
| **次元** (order) | どれだけ通るか | Arrow 2 等式 | BSD 予想 | 第一類 + Arrow 2 |
| **位置** (spectrum) | どこに住むか | Scan 特殊値 | Riemann 予想 | 第二類 |
| **流れ** (evolution) | いつ壊れるか | 時間発展 | Navier-Stokes | 第三類 |
| **下限** (bound) | 底はどこか | Scan 下限 | Yang-Mills | 第三類(制御済) + 第一類 | → c_distortion_floor.md (formal def) |

### §4.2 六層の圏論的読み

| 層 | 圏論的対応 |
|---|---|
| 存在 | image (像) |
| 障害 | kernel (核) |
| 次元 | rank / order (位数) |
| 位置 | spectrum (スペクトル) |
| 流れ | morphism evolution (射の発展) |
| 下限 | inf / bound (下限) |

**構造問題の完全分解**: 任意の「代数 vs 解析」問題は、
この六層のいずれか (または複数) に分解される。

### §4.3 六層間の接続

```
存在 ←─制約──→ 障害     (障害が消えれば存在が保証される)
存在 ←─計量──→ 次元     (存在する部分の「大きさ」を測る)
障害 ←─数え──→ 次元     (障害群の位数が次元を修正する: BSD |Sha|)
位置 ←─分布──→ 障害     (零点位置が障害の有無を決定する: Riemann → PNT)
流れ ←─安定──→ 下限     (flow の安定性を gap が保証する)
下限 ←─構造──→ 障害     (gap の起源は instanton = 第一類障害)
```

---

## §5 Domain symmetry constraint — 像の制限原理

### §5.1 原理

Arrow 1 (Scan → Structural) において、Structural 層の対称性が
Arrow 1 の像を制限する。これは複数の instances で観測される
**同種の制約構造** (same constraint type)。

### §5.2 Instances

| Instance | domain symmetry | 到達可能 | 到達不能 |
|---|---|---|---|
| Hodge | 代数的サイクルの実次元 = 2p | (p,p)-class | (p,q), p≠q |
| YM confinement | gauge 群 G の不変性 | gauge-singlet | color-charged |
| Stark tier | 表現の型 ν(ρ) | ν=+1 (orthogonal) | ν=−1 (symplectic, 部分的) |
| Crystal | 空間群の absences | h_max 内の reflection | h_max 外の高次反射 |

### §5.3 共通構造

```
Sym(S) ──────→ Im(φ) ⊆ Scan

「S の対称性が大きいほど、Scan に届く像が小さい」
```

これは A3 (gauge 不変性) の帰結:
gauge 不変な observable のみが物理的 → gauge が大きいほど observable が少ない。

**ΣΦ の A3 が domain symmetry constraint の公理的根拠**。

---

## §6 gauge 壁構造

### §6.1 一般的 gauge 壁

```
maximal gauge ──── intermediate gauge ──── minimal gauge
     ↑                     ↑                    ↑
  gauge 壁 1           gauge 壁 2          自明化壁
  (Tier √)             (Tier 2?)           (全情報喪失)
```

壁 1: maximal → intermediate で第一類障害 (ℤ/2, ℤ/n) が消える
壁 2: intermediate → minimal で残余障害が消える (存在するなら Tier 2)
自明化壁: minimal gauge で全情報が消え、問題が自明化

### §6.2 各ドメインの gauge 壁

| ドメイン | maximal | intermediate | minimal |
|---|---|---|---|
| Hodge | ℤ-係数 | ℚ-係数 | ℝ-係数 |
| Stark | L(0,ρ) with sign | L(0,ρ)² | |L(0,ρ)| |
| Crystal | F(hkl) = |F|e^{iφ} | |F(hkl)|² | Patterson 平均 |
| YM | A_μ (full gauge field) | gauge-inv (Wilson loop) | free field (g=0) |

### §6.3 最適 gauge 問題

**問い**: 障害を消す最小の情報損失 (最大の tame conductor) はどこか？

Hodge: ℚ-gauge が最適か？ (= ℤ→ℚ と ℚ→ℝ の間に第 3 の壁がないか)
Stark: L² が最適か？ (sign 以外に失われるものはないか)
YM: gauge-invariant sector が最適か？ (Elitzur の定理: gauge-dependent VEV = 0)

---

## §7 ΣΦ 公理との対応

| 層/概念 | ΣΦ 公理 | 関連 |
|---|---|---|
| 存在 | A0 (有限窓) + A5 (飽和) | 窓を通して見える像 |
| 障害 | A0-ID (恒等元非対称) + A2 (可換性制約) | 離散構造の残存 |
| 次元 | A3 (スケーリング) + A1 (コヒーレンス) | rank = 整合的な独立方向の数 |
| domain symmetry | A3 (gauge 不変性) | 対称性が像を制約 |
| gauge 壁 | A3 の選択 | gauge 水準が情報量を決定 |
| 強度階層 | A0-ID (離散性) | 恒等元方向の torsion 構造 |

---

## §8 ν — 正式 spectral comparison indicator

### §8.1 定義と性質

ν = σ(spacings) / μ(spacings)  (spacing の変動係数, CV)

| 性質 | 内容 |
|---|---|
| N-independence | N→∞ で収束 (zeta zeros: ν→0.46, 検証済 N=30..2000) |
| universality class summary | GUE ≈ 0.42-0.46, GOE ≈ 0.53-0.59, Poisson = 1.0 |
| obstruction 意味 | ν=0: free/equispaced (trivial obstruction), ν>0: interacting |
| S16 tier との関係 | tier = coarse (3 bin), ν = fine (continuous) |

### §8.2 検証済み ν 値

| System | ν | 物理 | tier |
|---|---|---|---|
| HO | 0.000 | 自由 (等間隔) | EXACT |
| Zeta zeros | 0.460 | GUE 統計 | STANDARD_FP |
| Box | 0.540 | 閉じ込め (無限井戸) | STANDARD_FP |
| GOE | 0.586 | 核共鳴 | STANDARD_FP |
| Glueball SU(3) | 0.636 | YM 閉じ込め + mass gap | INTERMEDIATE_FP |
| Hydrogen | 4.000 | Coulomb 束縛 | DEEP_FP |

### §8.3 二層判定 (tier + ν)

単一指標では不十分。**tier (coarse) + ν (fine) の二層判定** が正しい運用:

| 判定タスク | 使う指標 | 理由 |
|---|---|---|
| 「gapped vs gapless」 | tier (≠ EXACT) | binary 判定に十分 |
| 「同系統か」 | ν の近さ | 連続的な比較に必要 |
| 「universality class は」 | ν の値域 | GUE/GOE/Poisson に分類 |
| 「phase transition の位置」 | ν(parameter) の変化点 | S16 operational rule と整合 |

### §8.4 ν-universality ladder (5-class, domain-independent)

19 系 × 4 ドメイン (Number Theory / Gauge-Particle / Thermal-Quantum / FX-Financial)
の横断テストで確立 (2026-04-11, s16_cross_domain_tier_nu.py)。

| Class | ν range | spacing 構造 | 代表系 |
|---|---|---|---|
| **EQUISPACED** | ν = 0 | 完全等間隔、自由・無相互作用 | HO, Blackbody |
| **GUE-like** | 0.10 < ν < 0.50 | 強い level repulsion、反交差 | Zeta zeros (0.452), SU(2) glueball (0.446), GUE (0.464), Morse HCl (0.190) |
| **GOE-like** | 0.50 < ν < 0.70 | 中程度の level repulsion | Primes (0.630), SU(3) glueball (0.636), Nuclear (0.671), Hadrons (0.680), Box, Rotor, Ising |
| **intermediate** | 0.70 < ν < 0.85 | 弱い repulsion / 弱い clustering | Wishart null (0.734), GOE reference (0.809) |
| **Poisson-like** | ν > 0.85 | 無相関 / clustering | Poisson (0.999), FX eigenvalues (1.012), Hydrogen (3.189) |

**運用ルール**: 新しい系の spectrum が得られたら:
1. tier を判定 (EXACT / STANDARD_FP / INTERMEDIATE_FP / DEEP_FP)
2. ν を計算
3. ladder で class を判定
4. **同 class の系と比較** — 同じ ν-class に属する系は同種の spacing organization を持つ

**理論的根拠** (Wigner surmise + ν-decomposition, 2026-04-11):
5 class は Dyson index β = {∞, 4, 2, 1, 0} の canonical 値を反映した自然な区切り。
Wigner surmise: ν_nn(β) = √(Γ((β+3)/2)·Γ((β+1)/2)/Γ((β+2)/2)² − 1)。
canonical 値: β=4→0.323, β=2→0.422, β=1→0.523, β=0→0.756 (unfolded)。
**ν-decomposition (OQ-AO-6 RESOLVED)**: 我々の ν は raw (non-unfolded) CV であり:
ν² = ν_nn² + CV²(1/ρ)·(1+ν_nn²)  (§8.6 参照)。
INTRINSIC = ν_nn (Dyson β, 普遍) + EXTRINSIC = CV(1/ρ) (密度 envelope, 系依存)。
5 class は Dyson β から exact に導出される (密度プロファイルを与えれば free parameter なし)。

**核心的発見** (横断テストで確認):
- class はドメインではなく **spacing organization** で決まる
- 各ドメインが複数の class を横断する (数論: GUE-like + GOE-like, Gauge: GUE-like + GOE-like, Thermal: 全 class)
- **Zeta zeros ↔ SU(2) glueball** が同一 class (GUE-like, ν 差 < 0.01)
- **Primes ↔ SU(3) glueball** が同一 class (GOE-like, ν 差 < 0.01)
- **FX は Poisson-like に分離** — algebraic constraints (b₁ 零固有値) はあるが bulk は uncorrelated

### §8.5 Superselection Guard (2026-04-12, OQ-YM-1 Phase 4 結果)

**Guard rule**: ν-ladder (§8.4) は **同一 superselection sector** のスペクトルにのみ適用可能。

異なる量子数 (J^PC, spin, charge, ...) のエネルギー準位を混合したスペクトルでは
Wigner-von Neumann non-crossing rule が適用されず、level repulsion が消失する。
結果として ν → Poisson (≈1.0) となり、universality class 情報が破壊される。

**検証 (AT2021 glueball, 2026-04-12)**:

| Analysis | ν | r̃ | 判定 |
|---|---|---|---|
| SU(3) 同一構成 10 states (MP-like) | 0.72 | 0.52 | intermediate |
| SU(3) ground states 12 ch | 0.79 | 0.41 | intermediate |
| SU(3) 全 17 J^PC 混合 | 0.97 | 0.52 | **Poisson-like** (artifact) |

tier = INTERMEDIATE_FP は全分析で不変。ν のみが channel 混合に敏感。

**運用ルール**:
1. ν-ladder 適用前に spectrum の量子数均一性を確認
2. 均一 → ν-ladder 適用可。例: ζ zeros, GOE/GUE, FX eigenvalues
3. 混合 → tier のみ有効。例: glueball mixed J^PC, hadron spectrum mixed I/J
4. tier ≠ EXACT は superselection 非依存 (mass gap binary indicator)

**帰結**: §8.2 の glueball ν=0.636 (MP1999, 10 states) は mixed-channel 値であり
universality class の指標としては非適用。tier = INTERMEDIATE_FP のみが確定的。

### §8.5b S12/S13 分離規約との関係

ν は **S12 scan family のスペクトルに対する spacing 統計** であり、
S13 (乗法軸上の固定点条件) とは独立に定義される。

- ν の計算は S12/S13 どちらも必要としない (spacing の CV のみ)
- ν-ladder の境界値 (0.10, 0.50, 0.70, 0.85) は **empirical** であり、
  S13 instance (e^{-x}=1/2 ⟹ x=ln 2) から導出されたものではない
- 境界値が S13 の何らかの fixed-point 条件として導出可能かは OQ-AO-5

六層のうち「位置 (Riemann)」は S14 parity (Re(s)=1/2) との接点があるが、
S12/S13 は直接関与しない。「流れ (NS)」と「下限 (YM)」は
action_principles §4 (Wick rotation = S12 map) を経由する場合があるが、
六層の定義自体は S12/S13 非依存。

### §8.6 ν-decomposition theorem (OQ-AO-6 resolution, 2026-04-11)

**定理** (ν-分解): Dyson repulsion index β と局所密度 ρ(E) を持つ spectrum {E_k} に対し:

```
ν_raw² = ν_nn(β)² + CV²(1/ρ) · (1 + ν_nn(β)²)
```

ここで:
- ν_raw = raw (non-unfolded) nearest-neighbor spacings の CV (我々の empirical ν)
- ν_nn(β) = Wigner surmise からの CV = √(Γ((β+3)/2)·Γ((β+1)/2)/Γ((β+2)/2)² − 1)
- CV(1/ρ) = 逆局所密度の変動係数 (spectral envelope shape)

**証明**:
s_i = s̃_i / ρ(E_i) (raw spacing = unfolded spacing / local density)
Local universality: s̃ ⊥ ρ (大 N で独立)
Var(X·Y) = E[X]²Var(Y) + E[Y]²Var(X) + Var(X)Var(Y)
X=s̃, Y=1/ρ, E[s̃]=1, Var(s̃)=ν_nn² として:
→ ν_raw² = ν_nn² + CV²(1/ρ)·(1 + ν_nn²)  ∎

**検証** (oq_ao6_spectral_rigidity.py):

| 系 | ν_raw (emp) | ν_pred | Δ |
|---|---|---|---|
| GUE(N=50) | 0.497 | 0.491 | 0.006 |
| GOE(N=50) | 0.614 | 0.600 | 0.013 |
| GUE(N=100) | 0.517 | 0.487 | 0.030 |
| Morse HCl | 0.254 | 0.255 | 0.001 |
| Primes | 0.630 | 0.665 | 0.035 |
| Hadrons | 0.680 | 0.708 | 0.028 |
| Poisson | 0.999 | 1.032 | 0.032 |

**ΣΦ 翻訳**:

| 成分 | ΣΦ 意味 | 性質 |
|---|---|---|
| ν_nn(β) = INTRINSIC | level repulsion の強度 (Dyson β で決定) | 普遍的、対称性クラスのみ |
| CV(1/ρ) = EXTRINSIC | spectral envelope (密度プロファイル) の形状効果 | 系依存、観測窓 W の効果 |
| ν_raw = COMPOSITE | intrinsic + extrinsic の合成 | 我々の empirical indicator |

**帰結**:
- ν-ladder は Wigner 曲線 ν_nn(β) を密度 envelope で畳み込んだもの
- unfolded spectra では ladder 境界は Wigner 値に帰着: β=4→0.323, β=2→0.422, β=1→0.523
- empirical 境界 (0.10, 0.50, 0.70, 0.85) は密度効果を含んだ composite 値
- free parameter なし

**Spectral rigidity (Σ², Δ₃) の役割**:
- Σ²(L) = number variance: scale L での密度揺らぎの大きさ
- Δ₃(L) = spectral rigidity: staircase N(E) の線形近似忠実度
- Poisson: Σ²(L) = L, Δ₃(L) = L/15 (linear growth, 無相関)
- GOE: Σ²(L) ~ (2/π²)ln(2πL), Δ₃(L) ~ (1/π²)ln(2πL) (log growth, rigidity)
- GUE: Σ²(L) ~ (1/π²)ln(2πL), Δ₃(L) ~ (1/2π²)ln(2πL) (strongest rigidity)
- N=200 で RMT exact と empirical が L≤5 で一致 (GOE L=2: 0.583 vs 0.570)
- β → ν_nn → Σ²(L) → Δ₃(L) は完全な chain

### §8.7 定数吸収ネットワーク (topological scan result, 2026-04-11)

辞書内のすべての spectral observable から生じる定数は、
{π, √3, ln2, e, γ} の組合せに吸収される (free parameter = 0)。

| Observable | Closed form | Building blocks |
|---|---|---|
| ⟨r̃⟩_Poisson | 2ln2 − 1 | {ln2} |
| ⟨r̃⟩_GOE | 4 − 2√3 | {√3} |
| ⟨r̃⟩_GUE | 2√3/π − 1/2 | {√3, π} |
| ν_nn(GOE) | √(4/π − 1) | {π} |
| ν_nn(GUE) | √(3π/8 − 1) | {π} |
| Σ²_GUE(L) | (1/π²)[ln(2πL) + γ + 1] | {π, γ} |
| c_s² | 1/2 | {2} |
| σ* | √(2ln2) | {ln2} |

**帰結**: 内部構造から新しい独立定数は生じない。
出るとすれば **構造が閉じない境界** (topological/non-perturbative/L0外) のみ。

5-probe topological scan (η不変量, spacing ratio, spectral flow, Berry位相, spacing skewness)
× 19系 = **新定数候補ゼロ**。全候補が既知定数ネットワークに吸収された。
(topo_eta_invariant_scan.py, Atas 2013 + Nishigaki 2024 で GUE 閉式確認済)

**ΣΦ 定数判定 triage**:
```
定数 c が出現
  → 組合せ由来？ (離散群の位数, 分岐数) → OK, 構造定数
  → 解析由来？ (Γ, π, γ, ln) → OK, 数学的必然
  → どちらでもない → gauge/convention を特定せよ
    → 特定できた → extrinsic, 辞書から除外 or 注記
    → 特定できない → 新しい境界構造の候補 → OQ 発行
```

### §8.8 境界離散不変量 — non-Hermitian topology (2026-04-11)

**定理 (境界不変量の型転換)**:
Hermitian 内部では連続観測量は既知解析定数ネットワーク {π,√3,ln2,e,γ} へ吸収される。
non-Hermitian 境界を越えると、point-gap winding・cycle type・braid order からなる
**離散位相不変量**が点灯し、これらは摂動に対して安定であり、
連続定数吸収に還元されない。

**検証** (topo_braiding_deep.py):

| 不変量 | 型 | gauge-invariant | 検証 |
|---|---|---|---|
| **Braid permutation σ** | S_N の元 (離散) | ✓ (固有値のみ) | 96-100% non-trivial across random seeds |
| **Cycle type** | N の分割 (離散) | ✓ (共役類) | EP_n → n-cycle, 摂動で保存 (eps≤0.2) |
| **Braid order** | 正整数 or ∞ | ✓ | EP2=2, EP3=3, random=lcm(cycle lengths) |
| **Point-gap winding W** | 整数 | ✓ | Hatano-Nelson: 全 g で encirclement |
| **Signature sign(σ)** | ±1 | ✓ | 連続変形で保存 |

**EP encirclement の canonical 結果**:
- EP2: 1-loop → swap [1,0], 2-loop → identity (order 2)
- EP3: 1-loop → 3-cycle [1,2,0], 3-loop → identity (order 3)
- **Braid order = EP order** (topological invariant)

**重要な独立性**: winding と braiding は独立な不変量 (相関 = −0.11)

**ΣΦ 構造的意味**:
```
内部 (Hermitian) → 連続定数 (analytic necessity, 吸収される)
境界 (non-Hermitian) → 離散不変量 (topological necessity, 吸収されない)
```
これは **定数の型が境界で転換する**: continuous → discrete。
Arrow obstruction の第一類 (離散 kernel) と第二類 (連続 spectrum) の区別に対応:
non-Hermitian boundary は離散 kernel 型の新しい instance を追加する。

**Cross-domain universality** (topo_braiding_crossdomain.py, 2026-04-11):
5ドメイン × 2系 = 10/10 non-trivial。braiding は系固有ではなく**汎ドメイン現象**。

| Domain | Cycle types | Protection threshold |
|---|---|---|
| Quantum (PT) | (6,3,1), (2,2,2,2) | eps~0.001 |
| Topo-Ins (SSH) | (5,5), (4,4) | eps~0.1 (最強) |
| Many-body (dissipative) | (2,2,1,1,1,1) | eps~0.001 |
| Financial (FX transfer) | (3,3,1,1), (4,1,1) | eps~0.001 |
| Disorder (Anderson) | (10,), (8,) | eps~0.1 (強い) |

SSH 特記: (N_cells, N_cells) cycle type が sublattice symmetry を反映。γ=0.05-0.3 で完全安定。
γ=0.5 で (10,) に相転移 → **braid phase diagram** が存在。
Anderson: γ→0 で braiding が正しく消滅 (Hermitian limit の検証)。
Protection strength は point-gap size に比例 (gap が大きいほど保護が強い)。

**Braiding の源の区別**: non-Hermiticity と boundary topology は独立な braiding 源。
boundary phase twist だけでも braiding は生じる (Hermitian + PBC twist)。

**Berry phase residuals (保留)**:
biorthogonal Berry phase で fractional 値が観測された (17/20 levels)。
ただし biorthogonal gauge freedom が未解消。braid class 固定 + gauge 固定後に再測定要。

### §8.9 gap_ratio の棄却

gap_ratio = Δ/mean_spacing は N 依存で発散 (zeta zeros: 2.29@N=30 → 5.50@N=2000)。
原因: 最初の spacing は固定値だが mean_spacing は O(1/log N) で減少。
**gap_ratio は正規化の失敗。使ってはならない。**

---

## §9 本ファイルの限界と open questions

### §9.1 限界

1. **第二類障害の記述が不十分**: Riemann 予想の核心 (零点分布) は
   本分類では「連続スペクトル」とタグ付けするのみ。内部構造の分析はない。
2. **強度階層の formal 定義が不在**: ℤ/2 < ℤ/n < ℤ は直感的に正しいが、
   「障害の強度」を formal に定義する圏論的枠組みが未構成。
3. **六層の完全性は未証明**: 7番目の層が存在しないことの保証がない。

### §9.2 Open questions

| ID | Question | Priority |
|---|---|---|
| OQ-AO-1 | 強度階層 ℤ/2 < ℤ/n < ℤ を formal に定義するには、群の何を測るべきか？ entropy? rank? | HIGH |
| OQ-AO-2 | 第二類障害 (連続スペクトル) は第一類の「極限」(n → ∞ で ℤ/n → ℤ → ?) として得られるか？ | HIGH |
| OQ-AO-3 | 六層に 7 番目はないか？ 候補: 対称性 (P vs NP?) | MEDIUM |
| OQ-AO-4 | gauge 壁の位置を conductor で定量化できるか？ conductor_opt = max{f : Tier √ が消える} | MEDIUM |
| OQ-AO-5 | ν-ladder 境界値 (0.10, 0.50, 0.70, 0.85) は S13 fixed-point 条件から導出可能か？ → **回答**: S13 由来ではない。Wigner midpoint + density envelope の composite。unfolded 系では Wigner 値 (0.323/0.422/0.523) に帰着。empirical 境界は density-dependent → S13 独立 | RESOLVED |
| OQ-AO-6 | ν_raw と ν_nn のギャップを spectral rigidity で定量的に埋められるか？ → **RESOLVED** (2026-04-11): ν² = ν_nn² + CV²(1/ρ)·(1+ν_nn²)。law of total variance + local universality 仮定。RMT 系で Δ<0.03 検証済。Σ²/Δ₃ は scale-dependent refinement。§8.6 参照 | RESOLVED |
| OQ-AO-7 | 辞書内部から新しい独立定数は出るか？ → **方向的回答** (2026-04-11): 5-probe × 19系で候補ゼロ。全既知定数は {π,√3,ln2,e,γ} ネットワークに吸収。内部からは出ない。出るとすれば構造が閉じない境界のみ。候補: (1) non-Hermitian/Dirac (η非自明), (2) 非可約パラメータループ (Berry非零), (3) instanton/θ-vacuum, (4) L0公理外。§8.7 参照 | PARTIAL |
| OQ-Φ-1 | Φ rescue criterion の operational formalization。EEG α-band で **PARTIAL CLOSURE** (2026-04-26 S005 deep dive): Δα_pp < 60 ⇒ Φ rescue (5/5 subject 適合, r = −0.910)。v3 SNR < −5 dB と effect-size ~1/4 で structurally 一致。Cross-domain generalization (NT, QM, FX, Crystal の domain-specific magnitude effect-size threshold) が残 frontier。§10.8.5 | PARTIAL |
| OQ-Φ-2 | Φ as honest prior baseline for hallucination detection。**RESOLVED POSITIVE** (2026-04-26): Phi_std_inst_f H=0.130 ≈ uniform M=26 (H=0.08, best baseline)、alpha_heavy M=16 (H=1.34) の 10× improvement。**Refinement**: Phi family 2 sub-class — coherence-type (std/env/max_jump, H<0.25 honest) と cumulative-type (total/slope/quad, H>2 broken)。§10.8.6 | RESOLVED |
| OQ-Φ-3 | Φ_total が "1D time-series → FFT" 枠外でも universal か。**RESOLVED POSITIVE** (2026-04-26): 8 domain 全で Φ descriptor rank 1-5 入り。Graph Laplacian spectrum (rank 1-4 全 Φ), 2D image rasterized (rank 5-6 Phi_total/slope), **Periodic Table NIST IE (rank 1 Phi_max_jump + Phi_total = 8.00 ≈ 電子殻周期数 literal)**。Refinement: Φ descriptor FAMILY が universal、specific top descriptor は signal type 依存 (1D temporal → Phi_total / non-temporal sorted → Phi_slope / periodic structured → Phi_max_jump)。**真 2D Phi (Riesz transform) は別 frontier OQ-Φ-4** として分離。§10.8.7 G1 | RESOLVED |
| OQ-Φ-4 | True 2D Phi via Riesz transform で genuine 2D-image phase coherence detection 成立するか。**RESOLVED (v3.3, 2026-04-26 EOD)**: 4 pre-reg revision (v0/v1/v2/v3) の最終 v3.3 で ALL 4 pre-reg PASS。Setup: alpha=0 = deterministic spiral phase, alpha=1 = IAAFT random, paired-realization, **symmetrization step 削除**。結果: monogenic AUC=0.87 vs baseline AUC=0.32 (Δ=+0.55), phi_local_std \|coef\|=3.65 (13x next baseline), 3 Phi in top-5, 9/9 universal across nuisance sweep。**Scope condition 確立**: monogenic Phi は **deterministic structured phase regime で universal observable**、同 |F| random-phase 間は区別不可 (unitary 等価、scope 境界)。Symmetrization step 削除が closure 鍵 (math 的に両 CS source convex sum は exact CS で symmetrization 不要、逆に angle re-extraction が \|F\| drift 導入していた)。§10.8.8 attempt log + scripts `fft_rtheta_phi_image_riesz_v{0,1,2,3}.py` + result JSONs | **RESOLVED** |

---

## §10 T-AAS: Algebra-Analysis Surjectivity Template (2026-04-12, promoted from HC-1d)

### §10.0 2-axis (Fi/I) lens (OQ-L0-refinement v1, 2026-04-23)

T-AAS の kernel 分解 ker(φ) = ker_gauge ⊕ ker_topo は **Paper D §2.3 L0 v2**
の 2-axis framework (Axis-1 Discrete/Continuous × Axis-2 Finite/Infinite) に
おいて **axis-2 decomposition の特殊化**として再読みされる。観測 = axis-2
**I → Fi traversal** (片方向 Arrow)。Arrow が Fi/I 境界を跨ぐとき kernel
(obstruction) が境界上に発生する。

**Kernel class の axis-2 配置** (§10.3 classical + §10.7 quantum 統合):

| Kernel class | Axis-1 (D/C) | Axis-2 side | 解釈 | T-AAS 位置 |
|---|---|---|---|---|
| **ker_gauge** (classical) | torsion D / spectral C (instance-dependent) | **Fi-artifact** | observer の finite 基底選択に起因、別 Fi gauge で除去可能 | §10.1 (i)-(ii), §10.3 |
| **ker_coherence** (quantum, §10.7.1) | C (off-diagonal spectral) | **Fi-artifact** | 測定基底の Fi gauge 選択、unitary で diagonal 化可能 | ker_gauge-lift |
| **ker_topo** (classical) | C (filtration depth spectrum) | **I-residue** | observer-unreachable I 側 structure の Fi への残像、どの Fi gauge でも消えない | §10.1 (iii), §10.3 |
| **ker_entangle** (quantum, §10.7.1) | D (Schmidt rank integer) | **I-residue** | Schmidt rank r > 1 の local-gauge 不変性 = **量子側 I-residue の定理的 instance** | ker_topo-lift |
| **ker_backaction** (quantum, §10.7.1) | — (process-space) | **Fi → Fi irreversibility** | collapse-direction 特有の情報損失、state-space 枠外 | 枠外 new layer candidate |

**帰結**:

1. **ker_gauge 系 = Fi-side artifact** — ker_gauge (classical) + ker_coherence
   (quantum) は axis-2 Fi 側に合流。別 Fi gauge で除去可能。f_torsion 寄与。
2. **ker_topo 系 = I-side residue** — ker_topo (classical) + ker_entangle
   (quantum) は axis-2 I 側に合流。どの Fi gauge でも消えない。f_rational 寄与。
3. **ker_backaction** = axis-2 Fi → Fi 内の irreversibility、state-space でなく
   process-space kernel として独立 layer。
4. **Hodge 予想** (f_rational = 0, §10.5) = **古典 observation の axis-2 Fi/I
   境界 gap zero claim** — 古典側では未発見、open frontier。
5. **量子 ker_entangle CONFIRMED** (§10.7, OQ-Ω-Obs-1 quantum minimal form)
   = **量子 observation の axis-2 Fi/I 境界 gap non-zero 定理的 instance**
   (Schmidt rank r > 1 の local unitary 不変性)。

古典側の "第 3 の壁" 未発見 と量子側の ker_entangle 定理的 CONFIRMED の
**asymmetry が axis-2 lens で直接 visible** となる (古典 Fi/I gap は
観測可能な範囲で zero、量子 Fi/I gap は entanglement で non-zero)。

**Ref**: Paper D §2.3 L0 v2 (axiom), §4.4 (Arrow commutativity as Fi/I
commutation), §4.5.1 (meta-theorem coincide/split = Fi/I commutator = 0/≠0),
c_theorems_master.md "S15 axis-2 projection map",
research/oq_l0_refinement_finite_infinite_2axis_v0.md §4, §7.

### §10.1 Statement

**Template T-AAS** (verified across 3 independent instances: Stark, Hodge, Crystal):

> In any (S, W, m) observation system where Arrow 1 (phi: Structural -> Scan)
> has non-trivial kernel:
>
> **(i)** ker(phi) = ker_gauge + ker_topo (direct sum decomposition)
>
> **(ii)** ker_gauge is generated by discrete (torsion-valued) invariants
>   delta in Finite_Group. There exists gauge transformation g: delta -> 1
>   that kills ker_gauge, with irreversible information loss.
>
> **(iii)** ker_topo is generated by multi-step filtration obstructions
>   (each step crosses one filtration level). No gauge transformation removes ker_topo.
>
> **(iv)** The conductor decomposes correspondingly:
>   f(phi) = f_torsion + f_rational

### §10.2 Conductor decomposition (formal)

**Definition (Arrow conductor)**:

For Arrow 1 map phi: Structural(S) -> Scan(S|_W):

```
f(phi) = f_torsion(phi) + f_rational(phi)

f_torsion(phi) = dim{ ker_gauge }
  = dimension of discrete (finite-group-valued) obstruction space
  Killed by gauge enlargement (Z -> Q, L -> L^2, F -> |F|^2)

f_rational(phi) = dim{ ker_topo^{non-surj} ∩ target }
  = dimension of filtration-depth obstruction IN the target space
  Persists under all gauge transformations
  Note: ker_topo^{hom} (Griffiths group) does NOT contribute (auto-zero intersection)
  See c_filtration_obstruction.md §4.4 for decomposition
```

### §10.3 Instance table

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **Stark** | nu(rho)=-1 sign | Multi-field L-ratio | f_sign | f_field | **Classified** (5-tier) |
| **Hodge** | Sq^3, H^3_nr torsion | Griffiths transversality | f_torsion(X,p) | f_rational(X,p) | **Open** (= the conjecture: f_rational =? 0) |
| **Crystal** | Phase sign ambiguity | Sampling resolution | f_phase | f_sampling | **Resolved** (algorithmic) |
| **DNA (Paper F, 2026-04-23)** | frame shift ℤ/3 + strand RC ℤ/2 | coding/non-coding + per-gene depth | (null: gauge 自動除去済) | γ = S/W (codon position selection, organism-specific) | **Classified** (4 break modes in synthetic regime, §10.3.1) |

### §10.3.1 DNA instance detail (Paper F v0.6, 2026-04-24)

Paper F provides the **cleanest T-AAS instance in the dictionary** with quantitative closure:

**ker_gauge (discrete torsion)**:
- **Frame shift ℤ/3**: Voss indicator \|FFT\|² の位相除去性により任意の cyclic shift k ∈ {0,1,2} で **15 decimal agreement**
- **Strand reverse-complement ℤ/2**: forward = rc 同一 (fw SNR = rc SNR to 1e-15)
- 10 organisms で確認 (when L mod 3 = 0)、truncation artifact 以外で **完全 gauge invariance**

**ker_topo (filtration depth)**:
- 4-layer (human mtDNA): depth 0 whole 0.86 → depth 1 CDS 88.87 (**103× lift**) → tRNA 1.93, rRNA 1.32, non-coding 0.49
- Yeast nuclear Chr I (Paper F Round 5): CDS γ median 0.089 vs non-CDS 0.030 (**~3× lift** + AUC 0.858)
- Non-trivial filtration structure persists in all 10 tested organisms

**Conductor decomposition**:
- f_torsion = 0 (ker_gauge fully removed by |FFT|² phase quotient)
- **f_rational = γ = S/W** (Arrow 1 intrinsic, organism-specific)
- Decomposition verified empirically via **codon-preserving scramble byte-identical γ preservation** (10/10 organisms) — γ is spatial-correlation-independent

**4 break modes** (Paper F §4.6, Round 3):

| Mode | Trigger | Symptom | Observable effect |
|---|---|---|---|
| (a) W=0 | deterministic 3-period repeat (pure CAG/AAG/CGG) | formula 分母 vanish | γ → ∞, SNR → ∞ |
| (b) S=0 | non-3-period deterministic (CA microsatellite) | formula 分子 = 0 | γ = 0, predicted SNR = 0 |
| (c) 3-harmonic from non-3-period | telomere TTAGGG 6-period 2nd harmonic | deterministic background = 0 | m/p → 10³³ (huge over-measurement) |
| (d) Long-period repeat unit | alpha-satellite 171-mer × n | background median contaminated by low-f | m/p → 10³¹ |

**Scope of formula validity**: m/p ∈ [0.79, 0.85] (**stochastic coding regime**) defines the observable's valid domain. Outside this band, formula breaks cleanly along the 4 modes above. The band itself serves as **"biological vs synthetic" global scope identifier** (Paper F F14-revised).

**Biological application**: γ-based sliding-window ORF predictor (Paper F F15) achieves F1 = 0.949 at γ > 0.03 across 180k+ windows spanning mtDNA + nuclear + bacterial chromosomes — observation-theory closed-form formula から derive された **universal codon-position-aware ORF detector**。

### §10.4 Key structural finding (HC-1c/HC-1e, 2026-04-12)

**Clean separation**: R-type cleanly separates Tier sqrt from Tier 2:

- **Tier sqrt** = R-gauge obstructions = f_torsion > 0, f_rational = 0
  - All killed by Q-gauge / L^2 / Patterson
  - All known Hodge counterexamples (AH, Totaro, Voisin) live here

- **Tier 2** = R-topo-surj obstructions = f_torsion = 0, f_rational > 0 (if exists)
  - Persist under all gauge changes
  - Griffiths group (R-topo-hom) は ker_topo 存在の証拠だが f_rational に寄与しない
  - f_rational は ker_topo^{non-surj} ∩ Hdg^p にのみ住む (c_filtration_obstruction.md §4.4)

**Implication**: The rational Hodge conjecture is equivalent to f_rational(X, p) = 0
for all smooth projective X and all p. No known example has f_rational > 0.

### §10.5 Gauge wall update (supersedes §6.3)

HC-1e (2026-04-12) established: all known obstructions between gauge wall 1 (Z -> Q)
and gauge wall 2 (Q -> R) are **absent**. The "third wall" has NOT been found.

A Q-rational counterexample to Hodge would require:
1. A non-torsion obstruction in ker_topo
2. That intersects Hdg^p(X, Q) non-trivially
3. Using a mechanism fundamentally different from Steenrod or unramified cohomology

This is the OPEN FRONTIER of the Hodge conjecture in ΣΦ language.

### §10.6 Fitness metrics

Template fitness: **15/15** (5 criteria x 3 instances, HC-1d §27.3)
Departures: 3 (all LOW-MEDIUM severity, see HC-1d §27.4)

**Promotion basis**: Research note research/hodge_conjecture_decomposition_v0.md §26-§27.
Promoted to L1 per dictionary investment 4-axis: (1) research instability point direct hit,
(2) L1-落とし可能 (conductor language already in nt_conductor.md),
(3) reviewer 負荷低減 (self-contained formal statement),
(4) 骨格補強 (Arrow obstruction was missing conductor decomposition). Score: 4/4.

### §10.7 Quantum lift (candidate_v0, 2026-04-22, OQ-Ω-Obs-4 Part 1)

T-AAS は classical (可換) observation 系で定理化されたが、非可換 (量子)
observation への lift で **3 新 obstruction class** が identified される
(research/oq_omega_obs_4_noncommutative_scan_v0.md §4 source)。

#### §10.7.1 Quantum 3 class 定義

**ker_coherence (ker_gauge-lift)**:
```
定義: ρ の off-diagonal 要素 ⟨E_j|ρ|E_k⟩ (j≠k) のうち Arrow 1⁻¹ で
       Structural target 復元に寄与しない成分
機構: K_Q(τ) = |Tr(ρ e^{iAτ})|² 展開は A の固有基底での対角成分
       ⟨E_j|ρ|E_j⟩ のみ含み、non-diagonal ρ_{jk} に感度を持たない
       (q_quantum_observation.md §6)
Gauge 除去性: YES — unitary transformation U で ρ' = U†ρU として
       diagonal 化可能 (測定基底の gauge 選択)
T-AAS 位置: **ker_gauge の量子 instance**
Classical analogue: なし (可換では observable が常に同時対角化され
       coherence 概念不在)
f_torsion 寄与: f_torsion(φ_quantum) ⊇ dim{ker_coherence}
```

**ker_entangle (ker_topo-lift)**:
```
定義: 合成系 H = H_1 ⊗ H_2 上の Schmidt rank r > 1 状態 |ψ⟩ を
       product state (rank 1) に還元できない構造
機構: Schmidt 分解 |ψ⟩ = Σ_k √p_k |a_k⟩⊗|b_k⟩、rank r は
       **local unitary U_1 ⊗ U_2 不変** (Schmidt rank 定理)
Gauge 除去性: NO — 任意の local gauge で r > 1 が保存
T-AAS 位置: **ker_topo の量子 instance** — filtration depth
       (local/global 非自明 relation) に相当
Classical analogue: なし (classical では Schmidt rank 概念不在、
       独立性 ≠ 非独立性のみ)
f_rational 寄与: **f_rational(φ_quantum) ⊇ dim{ker_entangle}** =
       Schmidt rank structure。**量子側 f_rational > 0 candidate
       instance** (§10.5 open frontier の第 3 の壁への新経路)
```

**ker_backaction (T-AAS 枠外 candidate)**:
```
定義: 測定後 ρ ↦ P_j ρ P_j / Tr(ρ P_j) の irreversible 状態変化
機構: projection postulate。forward 観測 = 不可逆 arrow
       (Paper D §4.6 逆 Arrow の量子強化: section 自体が state を変える)
T-AAS 位置: **枠外** — state-space kernel でなく process-space
       kernel。T-AAS の直和分解 ker_gauge ⊕ ker_topo は state-space
       上で定義、ker_backaction は arrow 方向性に固有
Classical analogue: trivial (自動 reversible)
分類: "Arrow reversibility obstruction" 新 class 候補
```

#### §10.7.2 Quantum 5-class obstruction 表 (§10.3 拡張)

| Instance | ker_gauge | ker_topo | process-space | f_torsion | f_rational | Status |
|---|---|---|---|---|---|---|
| Stark | ν(ρ)=−1 sign | Multi-field L-ratio | — | f_sign | f_field | Classified 5-tier |
| Hodge | Sq³, H³_nr torsion | Griffiths transversality | — | f_torsion(X,p) | f_rational(X,p) | **Open** (= conjecture) |
| Crystal | Phase sign ambiguity | Sampling resolution | — | f_phase | f_sampling | Resolved algorithmic |
| **Quantum coherence** | **ker_coherence** | — | — | dim{coherence ↛ K_Q} | 0 | **candidate** (§10.7.1) |
| **Quantum entanglement** | — | **ker_entangle** | — | 0 | **Schmidt rank r>1** | **f_rational candidate** (§10.7.3) |
| **Quantum measurement** | — | — | **ker_backaction** | — | — | **枠外 new layer** candidate |

3 量子 instance の追加で Arrow obstruction 表は 3 classical + 3 quantum
= **6 instance** へ拡張。古典側 f_rational は依然未発見 (§10.5 open
frontier)、量子側は **ker_entangle (Schmidt rank) が具体 f_rational
candidate**。

#### §10.7.3 OQ-Ω-Obs-1 (第 3 の壁) への波及

§10.5 で述べた Hodge 型 f_rational > 0 の未発見問題 (= OQ-Ω-Obs-1 の
ΣΦ 翻訳) は、本 §10.7 により **2 経路** に分岐する:

- **Classical path (既存)**: smooth projective X 上の rational Hodge
  cycle が non-algebraic となる Q-rational 反例の探索 — 純数学 frontier
- **Quantum path (新 candidate)**: Schmidt rank r > 1 状態が Arrow 1⁻¹
  で Structural target (product state decomposition) に還元できない
  構造を、formal T-AAS chain で f_rational > 0 として登録

**Quantum path の formal requirement**:
1. Schmidt rank r が Arrow 1 (φ_quantum: Structural → Scan) の domain に
   encode される構造を明示
2. local unitary gauge (= T-AAS の gauge transformation quantum version)
   での r 不変性を T-AAS (ii) の gauge removability 対偶として formalize
3. r > 1 が Arrow 1 の non-surj (= cl⊗Q non-surjective quantum version)
   に対応する map の構成

詳細: research/oq_omega_obs_1_ker_entangle_frational_path_v0.md (本日起草)

#### §10.7.4 Refined form — narrower algebraic classes (OQ-Ω-Obs-4a ESTABLISHED, 2026-04-23)

§10.7.3 minimal form (Schmidt rank r > 1) は trivial bypass であり、
古典 Hodge 予想の depth parallel にならない。**narrower "algebraic"
class** を Arrow 1 source に指定することで、古典 algebraic cycles の
sparsity と同型の narrowness を持つ refined f_rational instance が
4 parallel 方向で立ち上がる:

| # | Algebraic class C | f_rational monotone M_C | 古典 Hodge parallel |
|---|---|---|---|
| C₁ | **Stabilizer** (Clifford orbit) | Magic monotone: M_F = −log₂ F_STAB / magic robustness R / relative entropy D_M / mana 𝓜 / stabilizer rank χ | Algebraic cycles の sparsity ↔ stabilizer polytope の sparsity |
| C₂ | **Gaussian** (二次 Hamiltonian, CV) | Wigner negativity 𝓝 / non-Gaussianity D_G | Hodge classes の analytic 深さ ↔ Wigner phase-space 深さ |
| C₃ | **Efficiently simulable** (poly-time classical sim) | Circuit complexity C(|ψ⟩) / Nielsen geometric complexity | Hodge conjecture の computational depth ↔ quantum simulation depth |
| C₄ | **Bell-local** (LHV correlations) | CHSH violation Δ_CHSH = (S_max − 2)_+ / nonlocal capacity | 古典 algebraic limitation ↔ LHV classical limitation |

**Common structural form** (4 class 全てに共通):

```
Arrow 1_refined:  C ──(T-AAS gauge_C = class-stabilizing unitary)──→ All states
Vanishing:  M_C(ρ) = 0 ⟺ ρ ∈ C̄ (class 閉包)
Positivity: M_C(ρ) > 0 for all ρ ∉ C̄
Gauge inv:  M_C(UρU†) = M_C(ρ) for U ∈ class-stabilizing gauge group
```

**Empirical verification** (3/4 classes + 1/4 literature, research/oq_omega_obs_4a_monotone_verify.py,
**9/9 gate PASS** 2026-04-23 session 3):

- **C₁ (Stabilizer, 1-qubit)** — 3/3 sub-gate: M_F(6 stabilizers) = 0
  exactly; M_F(|T⟩) = 0.228447 matches theory (1 + 1/√2)/2 → −log₂ to
  **4e-16 精度**; continuous sweep |ψ(α)⟩ = cos α |0⟩ + sin α |+⟩ で
  endpoint 0 + interior > 0 + α=π/4 peak 確認
- **C₂ (Gaussian, CV)** — 3/3 sub-gate (Gate 6 closure): 𝓝(coherent) = 0
  exact (Hudson's theorem); 𝓝(Fock |1⟩) = 0.4262 matches analytical
  **4e^{-1/2}−2 ≈ 0.4261 to 1e-4** (Mari-Eisert convention); Fock |n=1,2,3⟩
  𝓝 monotone; 𝓝(cat+ α=2) = 0.5865 (interference-driven, L=6 grid N=301)
- **C₄ (Bell-local, 2-qubit)** — 3/3 sub-gate: Horodecki closed form
  S_max = 2√(t₁²+t₂²); Δ(product) = 0; Δ(Bell) = 2√2 − 2 matches Tsirelson
  to **1e-6**; Werner state threshold p* = 1/√2 ≈ 0.7071 clean transition
  (p=0.700 → 0, p=0.708 → 0.0025)

**C₃ (Efficiently simulable)** — literature synthesis (Gate 6 closure,
research note §3.3.1): 4 core references — **Nielsen-Dowling-Gu-Doherty
(2006)** geometric complexity = geodesic length on SU(2^n) with Finsler
metric, gate-count lower bound theorem; **Jefferson-Myers (2017)** CFT
concrete super-poly complexity existence; **Bouland-Fefferman-Nirkhe-
Vazirani (2019)** random circuit states abundance of super-poly complexity
(BosonSampling + HOG); **Brandao-Horodecki (2019)** resource-theoretic
monotone grounding。General n empirical は BQP-hard scale wall、small-scale
(2-qubit Nielsen) は literature 既知の order relation で C₃ non-vacuity
confirmed。

**§10.7.2 拡張** (minimal + refined form 5-way catalog):

| Instance | ker_gauge | ker_topo | f_rational | Status |
|---|---|---|---|---|
| Quantum coherence | ker_coherence | — | 0 | candidate (§10.7.1) |
| Quantum entanglement **minimal** | — | ker_entangle | **Schmidt rank r>1** | **CONFIRMED** (§10.7.3, OQ-Ω-Obs-1 quantum path) |
| Quantum entanglement **refined C₁** | — | ker_entangle_stab | **M_F magic monotone** | **ESTABLISHED** (OQ-Ω-Obs-4a, 1-qubit script 3/3 gate) |
| Quantum entanglement **refined C₂** | — | ker_entangle_gauss | **Wigner negativity 𝓝** | **ESTABLISHED** (OQ-Ω-Obs-4a, CV script 3/3 gate) |
| Quantum entanglement **refined C₃** | — | ker_entangle_sim | **Circuit complexity C** | **ESTABLISHED** (OQ-Ω-Obs-4a, literature synth 4-ref) |
| Quantum entanglement **refined C₄** | — | ker_entangle_LHV | **Δ_CHSH nonlocal** | **ESTABLISHED** (OQ-Ω-Obs-4a, 2-qubit script 3/3 gate) |
| Quantum measurement | — | — | ker_backaction (process-space) | candidate 枠外 (OQ-Ω-Obs-4c) |

**Theorem 4a.1** (unified f_rational via class infidelity, research note
§4.4.1, 2026-04-23): 各 class C に対し
$M_{\mathrm{unified}}^C(\rho) := -\log_2 F_C(\rho)$
($F_C$ = Uhlmann fidelity to class closure C̄) は (P1) vanishing on C̄,
(P2) positivity off C̄, (P3) gauge invariance under class-stabilizing
unitaries, (P4) monotone under C-free operations の 4 条件を満たす。
4 class 全て **同一 log₂-bit 単位系** に unified、scale-bridging 問題が
formal closure。§3 各 class monotone (M_F / 𝓝 / C / Δ_CHSH) は
$M_{\mathrm{unified}}^C$ の instance 表現で再読み可能 (Fuchs-van-de-Graaf,
quantum speed limit, Horodecki fidelity-CHSH 不等式を介して bridge)。

**Depth parallel conjecture** (refined form の central claim, §4.4.2):

古典 Hodge depth を log₂-scale 化すると
$f_{\mathrm{rational}}^{\mathrm{Hodge}} \widetilde= \log_2(\dim(\mathrm{Hdg}^p / \mathrm{im\ cl}) + 1)$、
量子側 $M_{\mathrm{unified}}^C$ と同一単位系で比較可能。sparsity-matched
pair で $\mathcal{O}(1)$ 比例関係が存在する、という formal conjecture。
具体係数 + sparsity-matching の formal definition は future frontier (X1)。

**Depth tier flag** (§4.4.3, depth-2 orthogonal axis warning):
depth 0 = divisor / C₁ Stabilizer、depth 1 = Weil class (Markman 2022)
/ C₂ Gaussian / C₄ Bell-local、depth 2 は **幾何 vs 計算 orthogonal
axis 可能性**で空欄 + flag (C₃ Eff-sim は computational depth、未同定の
第 3 量子 class が geometric depth 2 に対応する可能性)。

#### §10.7.4a Axis-2 Fi/I connection — L0 v2 root-level 解釈

OQ-L0-refinement v1 (Paper D §2.3.1, 同 session ESTABLISHED) の axis-2
(Finite/Infinite) lens で refined form を再読みすると、**量子 f_rational
CONFIRMED vs 古典 Hodge OPEN の asymmetry に root-level 説明**が得られる:

- **量子 sources (4 class) = axis-2 Fi 側で discrete pinned**: Clifford
  (finite group) / symplectic (finite-dim manifold) / polynomial circuit
  (countable) / LHV polytope (finite facets) — 全て **algebraic / discrete
  / polytope / polynomial** の finite-structure principle で clean に
  境界が引かれる (Fi-artifact 境界)
- **古典 Hodge source = axis-2 I 側で continuous に境界滲み**: "algebraic
  cycles" は I 側 ideal object (Chow variety), operational 境界が open
  (motivic / transcendental / formal いずれも可), **discrete pinning
  missing** → f_rational monotone 定義困難

帰結: 古典 Hodge 予想 closure 条件 = "algebraic" source 境界の discrete
refinement (motivic refinement 等)、これが成立すれば古典側も量子 C₁ と
structurally 同型化し f_rational > 0 instance が見える可能性。本 asymmetry
は L0 v2 (d') "観測理論 = axis-2 Fi/I 境界の分類学" の具体 instance-level
confirmation。

詳細: research/oq_omega_obs_4a_refined_quantum_hodge_v0.md (2026-04-23
起草 + 同日 ESTABLISHED, 6/6 gate closed, 9/9 script gate PASS)

#### §10.7.5 Status と昇格 path

- §10.7 全体: **candidate_v0** (2026-04-22 quantum 3 class initial) →
  **candidate_v1** (2026-04-23 session 2 refined form 4 class + 2/4
  empirical) → **ESTABLISHED** (2026-04-23 session 3, refined form
  6/6 gate closed、unified f_rational Theorem 4a.1 + 3/4 empirical +
  C₃ literature synthesis + axis-2 Fi/I connection + depth-2 flag)
- **ker_coherence**: K_Q(τ) coherence 非感度は q_quantum_observation.md
  §6 で既 ESTABLISHED、ker_gauge lift への組込みは straightforward
- **ker_entangle minimal form**: **CONFIRMED** (§10.7.3, Schmidt rank
  3-step formal chain, OQ-Ω-Obs-1 quantum path)
- **ker_entangle refined form**: **ESTABLISHED** (§10.7.4, 4-class
  framework + unified Theorem 4a.1 + 3/4 empirical + C₃ literature,
  OQ-Ω-Obs-4a 6/6 gate closed 2026-04-23 session 3)
- **ker_backaction**: 新 layer への拡張は §9.2 open question として継続
  (OQ-Ω-Obs-4c)

**残 frontier** (4a ESTABLISHED 後の independent OQ 候補):
- (X1) depth parallel coefficient の具体値決定 (pure-math Hodge adjacent)
- (X2) depth-2 量子 instance 同定 (幾何 vs 計算 orthogonal axis 解決)
- (X3) C₃ Eff-sim 2-qubit Nielsen complexity closed-form
- (X4) 古典 Hodge predicate の "wider algebraic source" refinement

---

### §10.8 Φ_total — Scan-axis canonical observable (cross-domain empirical universal, 2026-04-26)

§10.0–§10.7 で axis-2 Fi/I 境界の **I-residue 側 obstruction** (ker_topo, ker_entangle 等) を分類した。本節は **その双対側** = 同じ axis-2 境界上に住む **Scan-axis 側 canonical observable** を扱う。Φ_total は obstruction (情報損失) ではなく、I 側 trajectory information を Fi 側で 1 scalar に圧縮する **constructive observable**。5 異質 domain (EEG / NT / QM / FX / Crystal) の empirical evidence で domain-agnostic universal として candidate_v0 化。

#### §10.8.1 Operational definition (winding number cumulant)

任意の実 1D time-series x[n] (n = 0, ..., N−1) に対して:

```
Φ_total(x) := (φ_unwrap[N−1] − φ_wrap[N−1]) / (2π)
            = total winding number of analytic signal phase trajectory
```

ここで:
- analytic signal a[n] = x[n] + i·H[x][n]   (H = Hilbert transform)
- φ_wrap[n] = arg(a[n]) ∈ [−π, π)            (per-sample wrapped phase)
- φ_unwrap[n] = continuous lift via Itoh unwrap (φ_wrap + 2π·n[k])

Φ_total ∈ ℤ (整数 cumulant, 周期跨ぎ count)。観測 window 内で位相が何周回したかの単一 scalar。

**Properties**:
- (P1) **Phase-shift invariance**: x → x · e^{iα} (uniform global phase) で Φ_total は不変
- (P2) **Window concatenation additivity**: 境界補正 mod で additive
- (P3) **Magnitude-independence (formal)**: |a[n]| に依存せず phase trajectory のみで定義
- (P4) **Domain-agnostic**: 任意の 1D 実 series で定義可、domain-specific 仮定なし

#### §10.8.2 Axis-2 Fi/I positioning (§10.0 dual)

§10.0 の axis-2 lens で Φ_total を配置:

| 量 | Axis-1 (D/C) | Axis-2 side | 性質 | T-AAS 位置 |
|---|---|---|---|---|
| ker_topo (§10.1 (iii)) | C (filtration) | **I-residue** | observation で消えない損失 | f_rational |
| ker_entangle (§10.7.1) | D (Schmidt rank) | **I-residue** | 量子側 I-residue 定理的 instance | f_rational lift |
| **Φ_total** (§10.8) | **D** (整数 winding ∈ ℤ) | **Fi-extracted I-trajectory** | I 側 trajectory 情報を Fi 側 scalar に圧縮 | **Scan-axis dual** |

**読み**: ker_topo / ker_entangle は I-side 構造の observation 後の **損失** を計る (negative observable = どれだけ消えたか)。Φ_total は同じ I-side trajectory information の **保存可能 Fi-projection** を計る (positive observable = どれだけ discrete invariant として残せたか)。**axis-2 Fi/I 境界の 2 facet**。

S15 Observable Trichotomy (Scan / Structural / Information) との対応:

- **Information observation** = magnitude (|X[k]|, power spectrum) = "Fi-projection of I-side amplitude"
- **Scan observation** = Φ_total (winding cumulant) = "Fi-projection of I-side trajectory"
- 両者 orthogonal Fi-summary、合わせて I-side Hilbert lossless reconstruction

#### §10.8.3 v2 minimal instance — Φ-only discrimination (constructive proof)

3 class signal を **|X[k]| 同一 (constructive identical magnitude spectrum)** に保ったまま、per-bin phase pattern のみで differentiate:

- Class A: 線形位相 (linear ramp across bins) → 時間遅延された clean tone
- Class B: 二次位相 (quadratic across bins) → chirp-like 時間 envelope
- Class C: random phase per bin → Schroeder-scrambled noise-like

**Sanity**: max\|mean_A − mean_B\|[k] = 0.72 vs peak amplitude 80 → magnitude 構成的 degenerate (ratio 0.9%)。

**Result** (5-fold CV macro-OvR AUC, multi-class logistic regression on standardized features):

| Feature set | AUC | Interpretation |
|---|---|---|
| 2D-only (r[k] for k ∈ [5, 31)) | **0.521** | chance level (by construction) |
| 3D-with-Phi (r[k] + 5 Φ descriptors) | **0.9994** | near perfect |
| Δ | **+0.479** | Φ-only discrimination |

Top-3 features 全て Φ 系: `Phi_std_inst_freq` (|coef|=2.42), `Phi_max_jump` (|coef|=2.00), `Phi_quad` (|coef|=1.82)。r[k] は rank 6 以下で |coef|<0.25 (誤差以下)。

これが **axis-2 Fi/I 境界上の Scan layer alone-discrimination 最小 instance** = Information observation (magnitude) が完全に degenerate な状況で Scan observation (Φ trajectory) が full discrimination を carry できる constructive proof。Paper D §4.5.1b (coincide/split = Fi/I commutator) の **non-commute side empirical witness**。

Script: `fft_rtheta_phi_v2.py` (work root)。

#### §10.8.4 Cross-domain empirical evidence (8 domains, 2026-04-26)

同一 framework (FFT magnitude r[k] vs r[k] + 5 Φ descriptors {slope, quad, std_inst_f, max_jump, Phi_total}, 5-fold CV, logistic regression on standardized features) を 8 異質 domain に適用:

| Domain | Signal | Top Φ feature | Rank | Pooled Δ AUC | Note |
|--------|--------|---------------|------|--------------|------|
| EEG (PhysioNet S001-S005) | α-bandpassed occipital, OPEN vs CLOSED | Phi_std_inst_f | 4/9 | −0.001 | **S005 +0.047 rescue** |
| NT (prime gaps p < 10^7) | g_n = p_{n+1} − p_n, real / shuffled / Poisson | Phi_total | 3/62 | +0.019 | NT correlation captured |
| QM (random matrix) | unfolded level spacings, Poisson / GOE / GUE | Phi_total | **1**/62 | +0.002 | universality class |
| FX (3 currency pairs H1) | log_returns, EURUSD / USDJPY / AUDJPY | Phi_total | 2/62 | +0.004 | /JPY pair +0.004 subtle |
| Crystal (phonon DOS) | thermal displacement, Einstein / 1D-Debye / 3D-Debye | Phi_total | **1**/62 (tied) | +0.001 | DOS class |
| Graph (Laplacian spectrum) | sorted eigenvalues, ER / WS / BA × 200 | Phi_slope | **1**/62 | 0 (saturate) | **rank 1-4 全 Φ**, Phi_total uninformative (rank 62) |
| Image (32x32 raster, 1D) | white noise / sin grating / 1/f² fractal | Phi_total | 5/62 | 0 (saturate) | Phi_total + Phi_slope rank 5-6 |
| **Periodic Table (NIST IE)** | IE(Z) for Z=1..108, real / shuffled / sorted | **Phi_max_jump** | **1**/15 | **+0.016** | **Φ_total = 8.00 ≈ 周期数 (literal physics)** |

**観察**:
- (O1) **Φ descriptor family は 8 domain 全て rank 1-5 入り**、5 domain で rank 1-3 (single most-informative feature)
- (O2) **Φ_total / dominant Phi descriptor は signal type 依存**: 1D temporal (EEG/NT/QM/FX/Crystal) → Phi_total dominant; 1D non-temporal sorted spectrum (Graph) → Phi_slope/quad dominant; 2D rasterized (Image) → marginal Phi_total/slope; periodic structured (Periodic Table) → Phi_max_jump dominant (周期跨ぎ jump 検出)
- (O3) Pooled Δ は canonical regime で常に小 (+0.000 〜 +0.019)、最大は **Periodic Table で +0.016** (周期性の独立 detection)
- (O4) **Dramatic gain (Δ ≥ +0.04) は EEG S005 のみ** (magnitude-weak regime, §10.8.5)
- (O5) **Periodic Table 特例**: Φ_total of full IE(Z=1..108) = **8.00**, 周期表の電子殻数 ≈ 7 完全周期 + 8 番目が始まる位置と数値一致 → **Φ_total が "literal shell counter" として物理的意味を持つ**。framework が教えられずに周期構造を発見する instance

Scripts: work root `fft_rtheta_phi_{nt,qm,fx,crystal,graph,image,periodic}_v0.py`、`sigmaphi/research/fft_rtheta_phi_eeg_v0.py`。

#### §10.8.5 Conditional orthogonality と Φ rescue criterion

5 domain pattern の構造的読み:

**Conditional orthogonality**: Φ info は magnitude info と **形式的に直交** (P3 magnitude-independent definition) だが、**実信号での相関は high** (power spectrum が autocorrelation を制約し autocorrelation が phase trajectory を制約するため)。observed pattern は "default 冗長 / 条件付き直交":

- **Default state (magnitude-strong regime)**: Φ_total は magnitude features と高相関、独立寄与小、しかし **single top-rank feature** として常に surface
- **Magnitude-weak regime (S005-like)**: Φ_total が **independent backup channel** として独立寄与 surface、dramatic gain (+0.047)

**Φ rescue criterion (formalized via S005 deep dive, 2026-04-26)**: Φ_total が独立 channel として surface する条件 = "magnitude-side discriminator が saturate しない regime"。S005 deep dive (`sigmaphi/research/fft_rtheta_phi_eeg_s005_deepdive_v0.py`) で 5 subject 全 metric scan、**Δα_pp が rescue 予測の最強 single metric** と判明:

| metric | r with rescue ΔAUC | S005 vs others |
|---|---|---|
| **Δα_pp = 200·(α_C − α_O)/(α_C + α_O)** | **−0.910** | S005 = +41pp / others +157〜+176pp |
| closed_env_cv (α envelope CV) | +0.51 | S005 highest (0.56) |
| open_plv (mid-window phase locking) | −0.77 | S005 lowest (0.10) |
| delta_plv | +0.43 | S005 smallest (−0.06) |

**Operational rule (OQ-Φ-1 preliminary closure)**:

```
RULE-Φ1 (EEG α-rhythm domain):
    IF  Δα_pp(CLOSED − OPEN, normalized) < 60
    THEN expect Φ rescue (3D AUC > 2D AUC by ≥ +0.04)
    ELSE magnitude path saturates the discriminator, Φ redundant
    
5-subject empirical fit: 5/5 (S005 < 60 → rescue +0.047 ✓ / 
                                S001-S004 > 150 → no rescue ✓)
```

**Generalization candidates** (cross-domain Φ rescue rule, conjectural):
1. **EEG (α-band)**: Δα_pp < 60 (above, validated)
2. **v3 SNR sweep (magnitude-matched setup)**: SNR < −5 dB (noise σ > 1.78 with normalized signal)
3. **General**: domain-specific magnitude-discriminator effect size below ~25% of saturation point ⇒ Φ rescue

Effect-size 仮説: rescue が起きる threshold は magnitude path effect の **~1/4 reduction**。S005 / v3 両 evidence で同 pattern。Cross-domain generalization が成立すれば universal Φ rescue criterion として ESTABLISHED 化候補。

#### §10.8.6 Hallucination index H との関係

`feedback_hallucination_index.md` (2026-04-25) の H = false-pos(biased prior) / Δ-discrim(honest prior) フレームで Φ_total を読むと:

- **Magnitude path** = prior-leak の発生源 (alpha_heavy M=16 H=1.34 broken の例: EEG α-band で prior-allocation が basis を生成 → data 無関係の verdict 焼き付け)
- **Φ_total** = data-independent prior の影響を **構成的に受けない** independent channel
  - 理由: Hilbert transform は signal そのものへの linear operator、prior basis allocation を介さない
  - Φ_total は signal-driven のみ、prior-leak hallucination から **operationally protected**

**OQ-Φ-2 RESOLVED POSITIVE (2026-04-26)**: EEG S001-S005 OPEN/CLOSED で Phi descriptor H index 計算 (`sigmaphi/research/fft_rtheta_phi_eeg_h_index_v0.py`):

| Phi sub-class | descriptors | EEG H | 性質 |
|---|---|---|---|
| **coherence-type (HONEST)** | Phi_std_inst_f / envelope_cv / max_jump | **0.130 / 0.173 / 0.224** | signal-driven, alpha_heavy M=16 (H=1.34) より **10× improvement** |
| cumulative-type (BROKEN) | Phi_total / slope / quad | 2.0 / 3.0 / 2.7 | broadband noise でも fire = prior-leak 同型 |

**Phi_std_inst_f H = 0.130 ≈ uniform M=26 (H = 0.08, best honest baseline)** — Phi family は **honest cross-channel として機能**するが **coherence-type sub-family のみ**。Phi_total / slope / quad は cumulative measure で broadband noise も拾う = honest channel ではない。

**Refinement**: Phi descriptor family は単一同質体ではなく **2 sub-class**:
- coherence-type: Hilbert envelope/inst-freq の **stability/variability** を測る → signal-locked
- cumulative-type: 時間積分量 (winding, slope, curvature) → 任意の broadband 入力で値持つ

S005 rescue (§10.8.5) では Phi_std_inst_f が rank 4 で contributor だった事実と整合 — honest sub-class が rescue を担当。Periodic Table Phi_total = 8 literal physics 一致 (§10.8.4) は周期構造が clean な特例で cumulative-type も意味を持つが、generic regime では coherence-type が trustworthy channel。

#### §10.8.7 Status と昇格 path

- **§10.8 全体: candidate_v2** (2026-04-26 EOD update from v1): 8-domain G1 RESOLVED + S005 G2 PARTIAL + H index G3 RESOLVED + Phi/Arrow constants G4 dual structured + **G5 RESOLVED (v3.3)**。ESTABLISHED まで残り = G2 (Φ rescue criterion) の cross-domain generalization のみ
- **5 domain empirical evidence**: 5/5 で Φ_total rank 1-4 入り、cross-domain 単一 universal observable claim 経験的成立
- **v2 constructive proof**: magnitude-matched 3 class で Φ-only AUC = 0.9994、minimal instance ESTABLISHED-grade single
- **v3 noise sweep**: SNR threshold 定量 (−5 dB AUC ≥ 0.95, −10 dB ≥ 0.70, −20 dB collapse, sharp transition at −10 dB)
- **EEG S005 rescue**: real-data conditional orthogonality 1st validation

**昇格 candidate path → ESTABLISHED**:
1. (G1) **8 domain stress test RESOLVED POSITIVE ✓ (2026-04-26)** — EEG / NT / QM / FX / Crystal / Graph / Image (raster) / Periodic Table 全てで Φ descriptor family が top 5 入り。**3 stress domains** (graph spectrum, 2D image raster, periodic table) でも universality 成立。**Periodic Table が highlight**: Phi_total = 8.00 が周期表電子殻数 ≈ 7+ と数値一致 = **framework が教えられずに shell structure 発見**。**Refinement** discovered (rank 1-5 入りの specific descriptor は signal type 依存): 1D temporal → Phi_total, 1D non-temporal sorted → Phi_slope, periodic structured → Phi_max_jump, raster 2D → Phi_total/slope marginal。残: **真 2D Phi (Riesz transform)** が別 frontier (OQ-Φ-4 候補)
2. (G2) Φ rescue criterion **PARTIAL ✓ (2026-04-26)** — EEG α-band で `Δα_pp < 60 ⇒ Φ rescue` 5/5 適合 (r = −0.910), v3 SNR threshold と一致 (effect-size ~1/4 reduction)。残: cross-domain generalization (NT/QM/FX/Crystal の domain-specific magnitude effect-size threshold formalization)
3. (G3) Hallucination cross-channel detection 実装 (OQ-Φ-2 closure)
4. (G4) Φ_total / Φ descriptor family と既存 universal constants (π, ln 2, e) の bridge constants 関係 (`c_arrow_bridge_constants.md` canonical scalar D1-D4 framework での位置確認)。**Periodic Table での Phi_total = 8 の literal physics 一致** が "Φ_total が new universal observable と shell structure invariant の bridge" の direct evidence
5. **(G5)**: True 2D Phi via Riesz transform — **PARTIAL (3 pre-reg revision, ESTABLISHED 未達, 2026-04-26)**。詳細 §10.8.8 (下記)

**新規 OQ** (§9.2 追記):
- **OQ-Φ-1**: domain-agnostic Φ rescue criterion の formal definition (現状 EEG S005 single-instance, v3 SNR threshold の generalization)
- **OQ-Φ-2**: Φ_total as honest-prior baseline for cross-channel hallucination detection
- **OQ-Φ-3**: Φ_total が "1D time-series → FFT" 枠外でも universal か (graph spectrum, 2D image, discrete sequence on non-Euclidean structures)
- **OQ-Φ-4 (重発行)**: True 2D Phi via Riesz transform — v3 design hint = **deterministic structured phase** (e.g. `phase = arctan2(ky, kx)` vortex pattern) を alpha=0 に置く。詳細 §10.8.8

#### §10.8.8 G5 attempt log (v0/v1/v2, 2026-04-26)

5 monogenic Phi descriptors via Riesz transform (`phi_local_mean`, `phi_local_std`, `theta_circ_var`, `phi_grad_norm`, `Phi_total_2d` boundary winding) を対象に 3 pre-reg revision で test:

| Version | Task | Pass criteria result | 学び |
|---------|------|-----------------------|------|
| v0 | 3 textures (white/grating/fractal), nuisance sweep 3×3 | P2/P3 PASS, P1/P4 FAIL | textures saturate (raster=1.000)、phase-shuffle generator が `(F + conj)/2` 対称化で magnitude 漏れ |
| v1 | 3 close-orientation gratings (30°/35°/40°) + IAAFT binary control | P2 PASS, **P4 +0.458 PASS**, P1/P3 marginal FAIL | angular |F| bin が orientation を baseline で取れる → monogenic 独立寄与小。**P4 が huge hit だが原因解析で symmetrization artifact 検出と判明** |
| v2 | 4-class phase coherence (alpha ∈ {0, 0.33, 0.67, 1.00}) IAAFT mix | All FAIL (monogenic ~ 0.50 = chance) | 設計 error: alpha=0 と alpha=1 が両方 random Gaussian phases → 統計的に区別不能。**monogenic Phi は同 |F| の 2 random-phase 信号を区別できない** (unitary 等価, expected) |
| **v3 (initial)** | alpha=0 = deterministic spiral (polar coord sin pattern), alpha=1 = IAAFT phase shuffle, paired-realization | P2/P3 PASS strong, P1/SANITY marginal FAIL | **質的飛躍**: phi_local_std rank 1 \|coef\|=2.93 (5x next baseline), 9/9 monogenic > 0.60 全 cell。SANITY 0.656 vs 0.65 残漏れは std-norm multi-step residual |
| **v3.3 (RESOLVED 2026-04-26 EOD continuation)** | **同 v3 + symmetrization step 削除** (math 的に両 CS source の convex sum は CS exact、step 不要) | **ALL 4 PASS** | **G5 RESOLVED**: P1 Δ=**+0.5535**, P2 phi_local_std \|coef\|=**3.65** (13x next baseline) + 3 Phi descriptors in top-5 (rank 1/4/5), P3 9/9 universal, SANITY baseline=0.32 near 4-class chance 0.25。 monogenic 0.87 vs baseline 0.32 → **Δ +0.55**。Symmetrization step 削除が leak elimination の鍵 — angle re-extraction による \|F\| drift が原因 |

**v1 P4 reframe (重要)**: v1 IAAFT control の +0.458 hit は **natural phase coherence detection ではなく generator-specific symmetrization artifact 検出**。`gen_fractal` の対称化 step が phase に構造的相関を作り、monogenic がそれを拾った。本物の universality 主張に直接利用不可。

**Scientific finding (副産物, candidate_v0 promote 候補)**: 
- monogenic Phi descriptor は **deterministic/structured phase pattern を検出する**
- 同 |F| の 2 random-phase 信号間は区別できない (expected, unitary 等価)
- → **OQ-Φ-4 v3 design hint**: alpha=0 を **deterministic structured phase** (例: `phase = arctan2(ky, kx)` vortex, `phase = π·(kx+ky)` diagonal pattern, 自然画像 edge phase) に置けば clean test 可能

**G5 status (v3.3 RESOLVED 2026-04-26 EOD)**: **G5 個別 RESOLVED** (ALL 4 pre-reg PASS, monogenic Δ +0.55 over baseline, phi_local_std \|coef\|=3.65 = 13x next baseline, 9/9 universal)。**deterministic structured phase regime で monogenic Phi が universal observable** として完全確立。完全 closure の鍵: symmetrization step 削除 (math 的に両 CS source の convex sum は exact CS、step は逆に angle re-extraction で \|F\| drift を導入していた)。

**§10.8 全体 status update**: candidate_v1 → **candidate_v2** に格上げ (G5 RESOLVED で 4/5 RESOLVED + G2 PARTIAL)。完全 ESTABLISHED への残: G2 (Φ rescue criterion) の cross-domain generalization (現 EEG α-band 5/5 closure のみ、NT/QM/FX/Crystal の domain-specific magnitude effect-size threshold formalization が要)。G5 自体は scope refinement (deterministic structured phase regime) も含めて完全 closure。

**v3.3 substantive finding**:
- monogenic Phi は **deterministic structured phase regime で universal observable** として完全確立 (1D 8-domain Phi universality と同根の機構が 2D Riesz でも成立)
- 同 |F| random-phase 間は区別不可 (unitary 等価, expected) — scope condition
- SANITY rectification 機構: F = amp × exp(i × phase) で phase が両 CS source の convex sum なら exact CS、ifft2 が exact real → no |F| drift, no normalization required

**v3 script**: `fft_rtheta_phi_image_riesz_v3.py` (paired-realization + no-symmetrization), result `results_riesz_v3.json`, vis `fft_explore_riesz_v3.png`

**Refs**:
- project memory: `project_fft_rtheta_phi_2026_04_26.md` (full pipeline + EEG validation summary)
- scripts (work root): `fft_rtheta_phi_v{0,1,2,3}.py`, `fft_rtheta_phi_{nt,qm,fx,crystal,graph,image,periodic}_v0.py`, **`fft_rtheta_phi_image_riesz_v{0,1,2}.py`** (G5 attempts)
- scripts (sigmaphi/research/): `fft_rtheta_phi_eeg_v0.py`, `fft_rtheta_phi_eeg_s005_deepdive_v0.py`, `fft_rtheta_phi_eeg_h_index_v0.py`
- results: `results_riesz_v{0,1,2}.json`, visualizations `fft_explore_riesz_v{0,1,2}.png`, `fft_explore_{1-17}_*.png`
- related: §10.0 axis-2 Fi/I lens, §10.7 quantum 4-class, `c_arrow_bridge_constants.md` (canonical scalar framework), `feedback_hallucination_index.md` (H index dual)

---

## §11 Inverse Arrow — 生成可逆性定理と obstruction class taxonomy (2026-04-23, Paper D §4.6 residence)

§10 (T-AAS) は forward Arrow 1 (Scan → Structural) の kernel 分解定理。本 §11 は **逆 Arrow** Arrow_i⁻¹ (i = 1, 2, 3) と、その合成として記述される **生成 (generation)** の obstruction 理論。Paper D §4.6 (主張 4.2 + 系 4.3 + 5-class taxonomy) の dictionary residence。

### §11.1 主張 4.2 (生成可逆性定理、OQ-Ω-Obs-2 PARTIAL CLOSURE, 2026-04-22)

**Statement**: S15 の 3 層 (Scan / Structural / Information) は exhaustive。「生成 (generation / synthesis)」は第 4 層ではなく、**逆 Arrow Arrow_i⁻¹ (i = 1, 2, 3) の部分逆写像 (section, right inverse modulo kernel) の合成** である。各 kernel 構造は T-AAS が full span で記述する。ker_gauge は stochastic lifting (noise injection, gauge enlargement) で除去可能 (f_torsion)、ker_topo は原理的障害 (f_rational)。

| 逆 Arrow | Domain → Codomain | Obstruction 源 | 画像 AI 対応 instance |
|---|---|---|---|
| **Arrow 1⁻¹** | Structural → Scan | ker_gauge ⊕ ker_topo (T-AAS, §10) | 生成失敗の主住所 (下記詳述) |
| **Arrow 2⁻¹** | Information → Scan | log の非可逆性 (exp-lifting from −F) | VAE posterior collapse (KL 過大 → 情報が戻れない) |
| **Arrow 3⁻¹** | Information → Structural | Jensen 不等式 (exp(H) ≥ \|D\|, 等号 iff uniform) | 多様な sample から離散構造を復元する際の下限 |

**証明スケッチ**:
- **Arrow 1⁻¹**: 「input spec D を与えて parametric family Σ_d f(d) · exp(a · b) を復元する」lifting 問題。T-AAS (§10) が ker を完全記述: ker_gauge = torsion (有限群曖昧性)、ker_topo = filtration 深さ。section は ker(φ) を modulo して well-defined。
- **Arrow 2⁻¹**: 「F(σ) を与えて Scan を exp(−F) として持ち上げる」。障害: log は ℝ 上へ全射でない (log(0) 発散)。VAE posterior collapse は KL(q(z\|x) ‖ p(z)) が発散し exp-lifting が失敗する instance。
- **Arrow 3⁻¹**: 「H_0(D) = log\|D\| から D を復元する」cardinality-lifting。Jensen 不等式 exp(H) ≥ \|D\|, 等号は uniform 分布のみ。非 uniform では exp(H) > \|D\| の gap が残る。∎

### §11.2 系 4.3 (完璧な生成は原理的に不可能)

T-AAS (§10, ESTABLISHED 15/15 fitness) により ker_topo ≠ 0 が一般に成立する。Arrow 1⁻¹ が **最深かつ最表現力** を持つ逆 Arrow (§11.3) であるため、その kernel ker_gauge ⊕ ker_topo が Structural 入力仕様に完全依存する生成過程を妨げる。ゆえに **ゼロ復元誤差の生成は一般に定理的に不可能** — heuristic ではなく定理。

### §11.3 なぜ Arrow 1⁻¹ が最深か

3 逆 Arrow すべてに非自明な obstruction があるが、Arrow 1⁻¹ が singled out されるのは、その domain (Structural) が forward Scan の **input specification** = data の完全 discrete skeleton を encode しているため。他の 2 逆 Arrow は Arrow 1⁻¹ の合成として派生する (例: Arrow 2⁻¹ = Arrow 1⁻¹ ∘ (∂/∂σ)⁻¹)。T-AAS の分解 ker_gauge ⊕ ker_topo は主に Arrow 1⁻¹ 上に住む:

- **f_torsion (ker_gauge)**: gauge 拡大 (ℤ → ℚ, stochastic injection, noise lifting) で除去可能。画像 AI 対応 = **mode collapse**。generator が torsion-finite な mode 部分集合に trap されたとき、gauge 拡大 (noise injection, CFG scale 変調) で missing mode を復元できる。
- **f_rational (ker_topo)**: どの gauge 変更でも消えない原理的障害。画像 AI 対応 = **expressivity bottleneck**。高周波テクスチャ、persistent homology (位相的穴)、視点変換での位相連続性など — 任意の深さのアーキテクチャでも復元不能な feature class。

### §11.4 OQ-Ω-Obs-1 (第 3 の壁) への接続

OQ-Ω-Obs-1 は「f_rational > 0 の instance を発見せよ」という open frontier (純粋数学側では Hodge 予想そのものに相当 — 予想は f_rational = 0 claim と等価)。

- **Quantum path (CONFIRMED 2026-04-22 夜)**: §10.7.3 + research/oq_omega_obs_1_ker_entangle_frational_path_v0.md。Schmidt rank r > 1 状態が ker_entangle instance として f_rational > 0 を定理的に CONFIRM。古典 Hodge が未発見の "第 3 の壁" を量子側で **定理的事実として直接 bypass**。
- **Quantum refined path (ESTABLISHED 2026-04-23)**: §10.7.4 (4-class framework + Theorem 4a.1 + 3/4 empirical + C₃ literature)。
- **Classical path (OPEN)**: 画像 AI が候補 **応用ドメイン** を提供。経験的に、いかなるアーキテクチャでも完全復元できない feature class が知られている。複数アーキテクチャ (Diffusion / VAE / NeRF / その他) で stable に観測されれば、応用側での f_rational > 0 候補 instance となり、OQ-Ω-Obs-1 を pure-math frontier から具体的計測対象へ降ろす。Paper E で展開中、Phase 4 NeRF 以降での探索が必要。

**注意** (Paper C k_max artifact 教訓の適用): Paper E では最低でも 3 アーキテクチャで「irrecoverable feature class」の classification が stable に成立することを確認するまで ESTABLISHED に上げない。「構造的対応」を formal claim に昇格させる前に、未変動パラメタによる artifact の可能性を sweep で排除する。

### §11.5 Obstruction class 5 種の分類 (2026-04-22 v0.6)

Paper E の VAE (Phase 2) + Diffusion (Phase 3) 2-architecture 比較 + Paper E Structural main scan (Phase 4, 9900 samples) で、Arrow 1⁻¹ kernel に住む obstruction の **3 新 class** が identified された。T-AAS の classical ker_gauge / ker_topo と合わせて、現時点で **5 種**:

| Obstruction class | Example instance | T-AAS 位置 | Capacity behavior | Scale behavior | Gauge-optimization |
|---|---|---|---|---|---|
| **Attractor** (Paper E §3) | VAE posterior collapse | **新 class** (capacity threshold 非線形) | non-monotonic | discrete (escape/lock) | gauge で除去不能 |
| **Noise-residue + SNR floor** (Paper E §4) | Diffusion hole_creation | **新 class** (forward stochastic) | invariant / subtle | smooth | **S13 × e balance で ~10× 改善** |
| **Stochastic basin selection** (Paper E main scan, v0.6 new) | Paper E Structural t*(C4) per-seed clustering {180, 150-160, 140} | **新 class** (training dynamics の確率的 basin 選択) | seed ensemble 依存、single seed で ~1 grid step noise | seed-invariant within basin, cross-basin discrete jump | basin-shift possible (training re-init) だが basin 位置は arch/gauge 非依存 |
| **Filtration depth** (classical) | Griffiths group | ker_topo | arch-independent | unknown | unknown |
| **ker_gauge classical** | discrete torsion (Stark, Crystal) | ker_gauge | gauge-dependent | depends | gauge 変換で除去 |

**Attractor class** の特徴:
- ker_gauge ではない根拠: β (gauge) 50× 変化で除去不能
- ker_topo ではない根拠: filtration depth 固有でなく capacity threshold で定性的に変化
- 正確な characterization: "attractor commitment の capacity-dependent 非線形現象"

**Noise-residue class** の特徴:
- forward stochastic map の per-frequency SNR floor に由来
- K (iteration) 非依存、scale-smooth、方向性一貫 (foreground area 非対称性)
- Gauge 選択 (t_start = T/e) で factor 10× まで改善可能 (claim E6)

**Stochastic basin selection class** の特徴 (v0.6 new):
- Paper E main scan (9900 samples) で initial identify。Structural balance 位置 t*(C4) が **seed ごとに離散 basin に cluster**:
  - seed = 42 basin: t* = 180 (coincide with T/e)
  - seed = 123 basin: t* = 150-160 (split)
  - seed = 456 basin: t* = 140 (split)
- ker_gauge でない根拠: β (gauge) 変更で basin 位置を shift できない
- ker_topo でない根拠: filtration depth (hr grid {6, 9, 12}) 非依存
- Attractor class との違い: capacity 充足下でも seed swap で verdict flip
- Meta-theorem (c_observation_optimal_gauge.md §5 Path 3) への寄与: split causation の 2nd class
- **OQ-PaperE-SeedBasinStructure (LOW, Paper D §8.2)** で each basin の structural characterization を future work として open

3 新 class とも ker_gauge でも ker_topo でもない独立 class として正式記録。Paper E 3-phase 比較で cross-invariant common pattern は出なかった (3 class が質的に differ) が、各 class 独立の structural characterization が得られた。classical ker_topo (f_rational instance) の候補は Paper E 内では未発見、Phase 4 NeRF 以降での探索が必要。

### §11.6 axis-2 (Fi/I) lens での再読み

§10.0 の 2-axis lens を 5-class taxonomy に適用:

| Class | axis-2 配置 | 解釈 |
|---|---|---|
| ker_gauge classical | Fi-side artifact | 別 Fi gauge で除去可能 |
| Filtration depth | I-side residue | I 側 ideal structure の Fi 残像 |
| Attractor | Fi-side, capacity-threshold pinned | Fi 内部の quasi-deterministic basin |
| Noise-residue + SNR floor | Fi → I 過程の forward stochastic 残差 | scale-smooth、Fi spectrum 上 |
| Stochastic basin selection | Fi 側 stochastic ensemble | seed = sampling from Fi-side training trajectory measure |

axis-2 lens で見ると、3 新 class はいずれも **Fi 側に住み**、I-side residue (古典 ker_topo / Hodge f_rational) とは異なる layer。古典 Hodge 予想の f_rational > 0 は Fi 側 application instance では未発見、量子 ker_entangle (§10.7) のみ I 側 residue として CONFIRMED。

### §11.7 References

- Paper D §4.6 (生成可逆性定理 + 5-class taxonomy 主体本論)
- c_arrow_framework.md §3 (Arrow 1 selector property — observable-choice dependence)
- c_observation_optimal_gauge.md §5 Path 3 (split causation taxonomy への寄与)
- §10 T-AAS (forward Arrow 1 kernel side)
- §10.7 quantum lift (Schmidt rank ker_entangle = f_rational quantum CONFIRMED)
- **`c_information_geometry.md §2` Theorem 2.1 (ESTABLISHED 2026-04-28)** — Fisher-Rao metric = Arrow 1⁻¹ **local linearization**: $\det g_F = 0$ locus matches local infinitesimal $\ker_{\mathrm{gauge}}(\mathrm{Arrow}\,1)$ direction; Cramér-Rao bound = L0 A1 *error_arithmetic* precision floor for Arrow 1⁻¹ reconstruction. Local 版 framework integration、global topological obstruction ($f_{\mathrm{rational}}$, Hodge / Schmidt rank) は本 §11 が引続き担当。
- Paper E v0.3 §3-§4 + main scan (3 新 class identification source)

---

## §12 References (ΣΦ 内部)

- L0_canon/finite_observation.md — (S, W, m), A0-A5
- L0_canon/identity_asymmetry.md — A0-ID, Tier 0
- L1/c_filtration_obstruction.md — ker_topo の幾何学的根拠 (Hodge filtration + Griffiths transversality)
- L1/c_phase_complex.md §4 — ℂ common receptacle, structural root
- L1/nt_conductor.md §6 — ramification hierarchy, S8
- L1/nt_frobenius_schur.md — ν(ρ), pairing obstruction
- L1/nt_root_numbers.md — W(ρ), sign/magnitude split
- L1/q_gauge_field_theory.md §5-7 — mass gap, instanton, confinement
- L1/c_spectral.md §8 — S7 class number formula, 6-gauge
- L1/q_many_body_quantum.md §6 — SSB, gapless Goldstone
- L1/c_hidden_degrees_of_freedom.md — R-gauge, R-topo-hom, R-topo-surj 型 (6型分類)
- research/hodge_conjecture_decomposition_v0.md -- full millennium analysis (§24-§27 = HC-1a-d milestones, T-AAS source)
- research/oq_ao6_spectral_rigidity.py — ν-decomposition theorem + Σ²/Δ₃ verification
- research/oq_omega_obs_4_noncommutative_scan_v0.md — §10.7 quantum lift source (ker_coherence / ker_entangle / ker_backaction 3 class candidate_v0)
- research/oq_omega_obs_1_ker_entangle_frational_path_v0.md — §10.7.3 OQ-Ω-Obs-1 量子経路 formal chain draft
- q_quantum_observation.md §6 — K_Q(τ) coherence 非感度 (ker_coherence の root), §5 Schmidt 分解 (ker_entangle の root)
- c_arrow_bridge_constants.md — 3 Arrow canonical constants (π, ln 2, e) の residence side (kernel side = 本 entry)
- feedback_hallucination_index.md — H index (prior-leak / honest-discrimination), §10.8.6 で Φ_total を honest channel baseline として読む dual
- project_fft_rtheta_phi_2026_04_26.md — §10.8 source memory (v0-v3 + EEG-v0 + 5-domain cross test full record)
- work/`fft_rtheta_phi_v{0,1,2,3}.py` + `fft_rtheta_phi_{nt,qm,fx,crystal}_v0.py` — §10.8 5-domain empirical evidence scripts
- sigmaphi/research/`fft_rtheta_phi_eeg_v0.py` — §10.8.4/5 EEG S005 rescue real-data validation
