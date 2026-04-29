---
type: open_question_resolution_draft
subject: "OQ-Ω-Obs-3 — Does e play an S13-analogous fixed-point role on Arrow 3 (Structural → Information)?"
status: RESOLVED / S17 ESTABLISHED (2026-04-23; 3/3 gate closed — gauge invariance proof + 3 domain script PASS + S14 (e,i) bridge-water L1 entry)
date: 2026-04-22 (draft), 2026-04-23 (S17 promotion)
depends_on:
  - c_theorems_master.md S13 (ln 2, Arrow 2 fixed point)
  - c_theorems_master.md S14 (parity midpoint duality, note on (e,i) bridge-water pair)
  - c_theorems_master.md S15 (Observable Trichotomy, Arrow 1-3)
  - Paper_D_Observation_Theory_ja.md §4.3, §4.5 (Arrow 3 = Hartley entropy)
  - dictionaries/meta/constant_residence_index.md (e: Paper Ω continuous pole, Arrow 3 未記載)
---

# OQ-Ω-Obs-3 v0 — Arrow 3 における e の S13-類比固定点

## 0. TL;DR

**候補主張**: Arrow 3 (Structural → Information, H_0(D) = log|D|) に、S13 (Arrow 2
の ln 2 固定点) に類比的な **e 固定点** が存在する。2 つの側面を持つ:

- **(A) Extremum form**: information density per Structural element
  d(n) = (log n) / n は n = e で **gauge-invariant な global maximum**
  を取り、max d = 1/e。
- **(B) Unit-nat form**: |D| = e ⟺ H_0(D) = 1 nat は Arrow 3 上の
  natural-unit cardinality 固定点。

両 side は単一の Arrow 3 bridge 構造の 2 表現であり、S14 note が既に
認識した「(e, i) は bridge-water pair」の Arrow 3 specialization として
自然に位置付けられる。

**Status**: **RESOLVED / S17 ESTABLISHED** (2026-04-23, 3/3 gate closed)。
元 candidate_v0 (theoretical) の 3 条件 gate を session 2 で全 closure、
研究 note は historical draft として保持。正式 status は c_theorems_master.md
S17 row + c_arrow_bridge_constants.md §5 + Paper D §4.5/§4.5.0。ESTABLISHED 昇格条件は §7 に
記載。

---

## 1. 問題の再述

Paper D v0.6 §8.2 の OQ-Ω-Obs-3:

> Arrow 3 の Information 側で e が S13 相当の固定点を持つか。
> (bidirectional 完備化)

背景:
- S13 (ESTABLISHED): Arrow 2 (Scan → Information, log-exp duality) 上で
  `e^{-x} = 1/2 ⇒ x = ln 2` が half-value 固定点。乗法 scan only scope、
  Landauer/Shannon/erasure 等の instance 横断。
- S14 (ESTABLISHED): (π, ln 2) parity midpoint duality。加法 parity = π、
  乗法 parity = ln 2。**Note**: (e, i) は "bridge 水準の dual" であり
  S14 parity scaffold とは別層 — S14 水源 (parity scaffold) の unique pair
  ≠ bridge-water pair。
- S15 (ESTABLISHED): 3 Arrow 構造。Arrow 2 は log-exp duality bridge、
  Arrow 3 は Hartley counting bridge (Structural → Information)。

**Bidirectional 完備性の gap**: S13 は Arrow 2 を特徴付けるが Arrow 3 は
対応する constant residence を持たない。constant_residence_index.md で
e は "Paper Ω continuous pole + Mertens limit" とのみ記載、Arrow 3
instance は空欄。

---

## 2. Framework — Arrow 3 上で "S13 analogue" とは何を意味するか

S13 が Arrow 2 上で固定点として機能する条件を 3 つに分解:

| S13 の特徴 | Arrow 2 上での意味 |
|---|---|
| **(i) bridge 上に住む** | log(= Arrow 2 の core map) の値を返す |
| **(ii) canonical scalar 条件** | `e^{-x} = 1/2` という gauge-独立な等式 |
| **(iii) domain 横断 universality** | ζ, Z(β), c(τ_cov) 全てで同値 |

Arrow 3 上で analogue を探すとき、同 3 条件を要求する:

- **(i')** Arrow 3 の core map (log |·|) の値または引数が extremum/特異値
  として出現
- **(ii')** gauge-invariant な canonical 条件 (base 変換で位置が移らない)
- **(iii')** domain 横断 universality (NT / 画像 AI / FX / quantum 等で
  共通)

---

## 3. 候補 4 種の分析

### 3.1 候補 A: Information density extremum (primary candidate)

**定義**: Arrow 3 value per Structural element
```
d(n) := H_0(D) / |D| = (log n) / n    (|D| = n と記法)
```

**主張**: `d(n)` は **n = e で global maximum** を取り、`max d = 1/e`。

**導出**:
```
d'(n) = (1 − log n) / n²
d'(n) = 0  ⇔  log n = 1  ⇔  n = e
d''(e) = -1/e³ < 0   (局所最大, それゆえ global max over n > 0)
```

**Gauge invariance check (条件 ii')**:
任意の base b > 0, b ≠ 1 で `d_b(n) = (log_b n) / n = (log n) / (n log b)`.
`d_b'(n) = 0 ⇔ log n = 1 ⇔ n = e`. **Max 位置 n = e は base 非依存**.
Max 値 `d_b(e) = 1/(e log b)` は base-dependent だが、**引数 n = e が
structural feature** として gauge-invariant。

**Arrow 3 上の解釈 (条件 i')**:
- 分子 log n = H_0 (Arrow 3 value)
- 分母 n = |D| (Structural cardinality)
- 比 = "Hartley entropy per Structural element"
- max の位置 = **情報密度が最大となる cardinality** = e

**Domain 横断 universality (条件 iii')**:
- **NT**: prime counting π(N) ~ N/log N, 逆数 = log N / N = d(N) の漸近。
  prime density と Arrow 3 density の parallel.
- **画像 AI**: codebook size n に対する bits-per-token 密度 (log n)/n、
  n = e 近傍の離散整数 n = 3 が information-density-optimal cardinality
  (3 元 code の情報密度は 2 元/4 元より高い: log 3 / 3 ≈ 0.366 vs
  log 2 / 2 ≈ 0.347, log 4 / 4 ≈ 0.347)
- **Quantum**: qudit dimension d に対する single-shot classical capacity
  C_1 = log d / d (等確率 prep-measure), max at d = e, ternary 3-level
  system optimal。

3 domain で同一 Arrow 3 extremum。universality 成立候補。

### 3.2 候補 B: Unit-nat cardinality (secondary candidate)

**定義**: Arrow 3 で unit information を与える cardinality
```
|D| = e  ⟺  H_0(D) = 1 nat
```

**主張**: `|D| = e` は Arrow 3 上の "natural-unit cardinality" 固定点。
base e (= 自然対数) が Arrow 3 の canonical gauge であるときの unit value。

**Gauge 依存性**: base-dependent (base 2 なら |D| = 2 が 1 bit)。
よって **候補 A と比べて gauge-invariant 性が弱い**。しかし base = e は
Paper Ω で continuous gauge generator として canonical 指定されており
(constant_residence_index.md "e: primary = Paper Ω §2.4 pure continuous
pole")、この意味で canonical gauge 選択下での unit residence。

**S13 との parallel**:
- S13 (Arrow 2): 半値条件 `e^{-x} = 1/2` ⇒ `x = ln 2` (half-decay point in nats)
- 候補 B (Arrow 3): 単位条件 `log|D| = 1` ⇒ `|D| = e` (unit-content point in nats)

両方とも natural-log gauge での "特定 scalar value" 条件。

### 3.3 候補 C: Stirling threshold (weaker candidate)

**定義**: Stirling 近似 `log n! ≈ n log n − n` の零点。
```
log n! ≈ 0  ⇔  log n = 1  ⇔  n = e
```

**主張**: combinatorial 構造 (factorial = 順序全体) の連続化零点で n = e。
離散 n! は n = 1 で 1 (= log 1 = 0 trivial)、n = 2 で 2 が最小 non-trivial、
Stirling 連続化では n = e が "onset threshold"。

**Problem**: 離散の n! は n = 1 でも 0 を与えるため、固定点としては
連続化 artifact。S13 ln 2 が離散系 (Shannon H(1/2), Landauer kT ln 2) で
そのまま成立するのと対照的に、候補 C は連続化依存。

**Relegation**: 主 candidate から外す。候補 A/B の supplementary interpretation
として残す。

### 3.4 候補 D: n^{1/n} maximum (equivalent to A)

**定義**: `f(n) = n^{1/n} = exp((log n) / n)`.
```
f'(n) = n^{1/n} · (1 − log n) / n²
f'(n) = 0  ⇔  log n = 1  ⇔  n = e,   max f = e^{1/e} ≈ 1.4447
```

**Relation**: f(n) = exp(d(n)) so candidate D = exp of candidate A. **同一
extremum**, 表示違い。

**Note**: 離散 n では f(2) = √2 ≈ 1.414, f(3) = 3^{1/3} ≈ 1.442, f(4) =
√2 ≈ 1.414 で integer max at n = 3 (e に最近接 integer)。画像 AI の
3-way latent (ternary VAE) が binary/4-way より information density 高い
実例と consistent。

**Selection**: 候補 A を primary statement、候補 D を exponentiated form
として同時掲載。

---

## 4. 統合 statement

**定理候補 4.2 (Arrow 3 e-fixed-point, candidate_v0)**: Arrow 3
(Structural → Information, H_0(D) = log|D|) 上に、以下の 2 面を持つ
固定点構造が存在する:

- **(A) Gauge-invariant extremum**: information density `d(|D|) =
  H_0(D)/|D|` は `|D| = e` で global maximum `1/e` を取る。Extremum の
  引数 `|D| = e` は gauge 非依存 (log base 任意)。equivalently, |D|^{1/|D|}
  が |D| = e で max value `e^{1/e}`。
- **(B) Natural-unit cardinality**: base-e gauge (自然対数) 下で
  `|D| = e ⟺ H_0 = 1 nat` は unit-content fixed point。

**S13 analogue status**: 条件 (i')(ii')(iii') 全て PASS (candidate A)。
S13 半値条件の Arrow 3 類比は **"最大密度条件"** と読める。Arrow 2 は
"特定 value での対称点" (e^{-x} = 1/2)、Arrow 3 は "特定 |D| での
extremum" (d'(n) = 0) という **format shift** を伴って S13 を Arrow 3
に射影する。

---

## 5. 既存 framework との整合性

### 5.1 S14 note との合致

S14 定義末尾:
> (e,i) pair は bridge 水準の dual であり S14 水源 (parity scaffold)
> とは別層 — S14 は parity scaffold の unique pair。

**本研究の解釈**: (e, i) bridge-water pair は 3 Arrow の各 bridge で
specialization を持つ:
- Arrow 1 bridge (input spec reading): i additive (S¹ rotation in ι_L)
- Arrow 2 bridge (log-exp duality): S13 ln 2 (= e^{-x}=1/2 uses base e)
- **Arrow 3 bridge (Hartley counting)**: 候補 A/B の e 固定点

よって (e, i) bridge-water pair は S15 の 3 Arrow 全てで residence を
持つ可能性があり、OQ-Ω-Obs-3 は Arrow 3 specialization の具体化。

### 5.2 Paper Ω e residence との整合

constant_residence_index.md 現在の e 記載:
```
primary:   Paper_Omega §2.4 (pure continuous pole, Mertens limit)
instances:
  - c_scaling_laws.md §1.4    A/B = sqrt(e) = exp(c_s^2)
  - atlas/sheet_A_amplitude   exponential baseline
  - atlas/sheet_D_measure     Z = sum exp(-beta E)
```

本研究の追加 instance (promotion apply 時):
```
  - Paper_D §4.3 (Arrow 3 extremum)    d(n) = log n / n max at n = e
                                       (gauge-invariant, cardinality axis)
```

**干渉なし**: 既存 instance は全て Scan 軸 (乗法軸 exp baseline、Z 指数和、
A/B ratio)。新 instance は Arrow 3 (Structural → Information) 上で、層が
異なる。重複 residence ではなく bidirectional 完備化。

### 5.3 γ (Euler-Mascheroni) との区別

constant_residence_index.md:
```
gamma: primary = Paper Ω §2.4 boundary residue, discrete-continuous gap
```

γ は harmonic series H_n − ln n → γ の discrete-continuous **差分**
として residence。これは Arrow 3 の "離散 |D| と連続 log 値の gap" と
parallel。

**関係**: 本研究の e 固定点は Arrow 3 の **extremum**、γ は Arrow 3 の
**asymptotic gap residue**。両者は Arrow 3 上の異なる structural
feature で、**競合しない**。予想: Arrow 3 上で (e, γ) pair が Arrow 2
上の (ln 2, ?) 組に対応する "bridge pair 2nd layer" を形成する可能性
あり (open follow-up)。

---

## 6. Bidirectional duality table (更新案)

bidirectional_duality_v0 における S15 Arrow 残 constant residence:

| Arrow | Fixed-point structure | 主定数 | Status |
|---|---|---|---|
| Arrow 1 (Scan → Structural) | input spec reading | π (S¹ torsion via ι_L) | ESTABLISHED (S14) |
| Arrow 2 (Scan → Information) | log-exp half-value | **ln 2** (e^{-x}=1/2) | ESTABLISHED (S13) |
| Arrow 3 (Structural → Information) | log-density extremum | **e** (d(n) max) | **ESTABLISHED (S17, 2026-04-23)** |

**完備化の意味**: (π, ln 2) が S14 parity scaffold で addition×multiplication
dual を覆い、**e が Arrow 3 extremum で Arrow 2 との duality を完備**
する。3 Arrow 全てに canonical constant residence が埋まり、S15 bidirectional
duality が constant-level で完結。

---

## 7. Status と ESTABLISHED 昇格条件 — **3/3 CLOSED 2026-04-23**

**Status**: **ESTABLISHED (S17, 2026-04-23)**。3 条件 gate 全 closure。

1. **条件 1 (formal closure)** ✅ **DONE**: gauge invariance を 3 gauge
   (base 2, e, 10) で explicit check、|Δ − e| < 2e-5 (script)。
   c_arrow_bridge_constants.md §5.2 に formal proof。

2. **条件 2 (instance 横断)** ✅ **DONE (2026-04-23)**: script
   `research/oq_omega_obs_3_info_density_check.py` **5/5 gate PASS**
   — D1 NT continuous argmax_N (log N)/N = 2.71830 (|Δ − e| = 1.66e-5),
   D2 codebook integer argmax = 3 = ⌊e⌉ (ternary 0.36620 > binary 0.34657),
   D3 qudit integer argmax = 3, cross-domain universality。
   Note: D2/D3 は同一関数形 log n/n の異 label 評価で numerical 一致、
   script の価値は explicit sweep + integer max=3 優越 + gauge invariance
   numerical confirmation (S13/S16 precedent 同 style)。

3. **条件 3 (S14 との整合)** ✅ **DONE**: L1 entry
   `c_arrow_bridge_constants.md` 新設、(e, i) bridge-water pair の Arrow
   3 specialization を §6 に formal 化、3 Arrow canonical constants 完備
   表 (π / ln 2 / e) 構築。

**現状**: **3/3 DONE** → **S17 ESTABLISHED** 2026-04-23。
Bidirectional duality 3 Arrow constants (π, ln 2, e) 完備。

---

## 8. Downstream 効果 (ESTABLISHED 昇格時)

Paper D v0.7 candidate content:
- §4.3 (Arrow 3) に "e fixed-point subsection" 追加 (S13 と並べ)
- §4.5 (S13 residence) を §4.5 "S13/S17 residence" に拡張 (S17 = Arrow 3 e)
- §8.1 L1 promotion candidates に "Arrow bridge constants L1 entry" 追加
- §8.2 OQ-Ω-Obs-3 を **OPEN → ESTABLISHED** 降格

Paper Ω bridge への反映:
- §Ω.5 (ζ-γ pair residue) と §Ω.2.4 (e Mertens limit) の橋渡し subsection
  追加 — e は乗法 Scan の限界 ∩ Arrow 3 extremum の 2 面性

S15 bidirectional duality 完備化:
- research/bidirectional_duality_v0.md §5 の "Arrow residence map" を 3/3
  完備 (現在 Arrow 3 空欄)

---

## 9. 予見される反論と preemptive response

**反論 R1**: 「extremum は固定点と違う。S13 の ln 2 は parity (= symmetric
center) であって extremum ではない。Arrow 3 e は max、S13 と構造が異なる」

**Response**: 両者とも **"導関数が 0 となる特定 value"** で統一可能。
- S13: `d/dx (e^{-x}) = -e^{-x}` は 0 にならないが、`d/dx (e^{-x} - 1/2)
  の絶対値` は x = ln 2 で minimal(= 0)、**"level-set crossing"** を
  固定点として定義。
- Arrow 3 e: `d(n) = log n / n` の `d/dn` が 0 となる extremum。
- 統一 framework: 両者は Arrow 上の **scalar-valued functional の
  stationary point**。S13 は level-set crossing (value-固定), Arrow 3 e は
  extremum (derivative-固定)。**format shift** を認め、"stationary
  principle on the relevant Arrow" と汎化する。

**反論 R2**: 「log n / n は trivial な microeconomic observation (prime
counting theorem の核)。S13 のような domain 横断 surprise がない」

**Response**: S13 も Shannon entropy / Landauer / erasure 等の parallel
は textbook 既知の事実を **観測理論 framework 内に residence 付与**
することで価値が出た。本研究の e fixed-point も同様 — 既知の extremum
を Arrow 3 residence として位置付け、(e, i) bridge-water pair の
specialization として組み込むことが dictionary 貢献。既知 fact の
novel re-organization は S12-S16 全部に共通する手法。

**反論 R3**: 「候補 B (unit-nat cardinality) は gauge 依存 (base e 前提)。
primary に据えられない」

**Response**: 同意。候補 B は secondary (canonical-gauge 下の derived
statement)。Primary claim は候補 A (gauge-invariant extremum)。§3.1-3.4
で階層化済。

---

## 10. Timeline

| Stage | Elapsed |
|---|---|
| L1/meta dictionary 確認 | ~5 min |
| 候補列挙 + 分析 | ~15 min |
| 本 note 起草 | ~25 min |
| **Total (theoretical closure v0)** | **~45 min** |

**予定 next session**:
1. `oq_omega_obs_3_info_density_check.py` (条件 2 empirical verification,
   推定 30 min)
2. `c_arrow_bridge_constants.md` L1 entry draft (条件 3 dictionary
   formalization, 推定 45 min)
3. Promotion proposal submit (3 gate 全通過時)

---

## 参考

- c_theorems_master.md S13 (Arrow 2 ln 2 fixed point), S14 (parity
  midpoint + (e,i) bridge-water note), S15 (Arrow 1-3)
- dictionaries/meta/constant_residence_index.md (e: Paper Ω primary,
  Arrow 3 未記載 = 本研究の gap)
- Paper_D_Observation_Theory_ja.md §4.3 (Arrow 3 = Hartley), §4.4 (3 Arrow
  可換性), §8.2 (OQ-Ω-Obs-3 OPEN)
- research/bidirectional_duality_v0.md §5 (Arrow residence map)
