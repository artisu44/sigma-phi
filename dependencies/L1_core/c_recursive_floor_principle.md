---
axis: [A, B]
position: L1_recursive_floor
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md           # A0 ﾂｧ5.3: D_floor > 0
  - L1_mathematical/core/c_distortion_floor.md    # D_floor formal 螳夂ｾｩ
  - L1_mathematical/quantum/q_quantum_observation.md  # SQL
  - L1_mathematical/quantum/q_quantum_thermodynamics.md  # Landauer kT ln 2
  - L1_mathematical/core/c_theorems_master.md     # S13 ln 2 fixed-point
  - L2_domain/gps_showcase.md                # 螳溯ｨｼ萓・1
  - L2_domain/ligo_showcase.md               # 螳溯ｨｼ萓・2
  - meta/open_questions_master.md             # OQ-BETA-SERIES, OQ-KAPPA-LIMIT
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-12
runtime_summary:
  what: D_floor 縺ｯ蜊倅ｸ蛟､縺ｧ縺ｯ縺ｪ縺上∵橿陦捺隼濶ｯ縺ｫ莨ｴ縺・焚縺ｪ繧狗黄逅・次逅・・荳矩剞縺ｫ鄂ｮ縺肴鋤繧上ｋ蜀榊ｸｰ逧・嚴螻､讒矩
  when: D_floor 縺ｮ譎ｮ驕肴ｧ繝ｻ荳榊庄驕ｿ諤ｧ繧定ｫ悶§繧九→縺阪∫音縺ｫ縲梧隼蝟・＠縺ｦ繧ゅぞ繝ｭ縺ｫ縺ｪ繧峨↑縺・咲炊逕ｱ繧貞撫縺・→縺・  provides: [recursive_floor_statement, GPS_LIGO_two_examples, Landauer_connection, promotion_conditions]
  consumes: [finite_observation.md ﾂｧ5.3, c_distortion_floor.md ﾂｧ2, ligo_showcase.md ﾂｧ2.3, q_quantum_thermodynamics.md ﾂｧ5]
  axis: [A, B]
  cost: low
  status: established
  one_screen: |
    D_floor Recursive Principle (conjecture):
    莉ｻ諢上・ W 縺ｫ D_floor(W)>0 縺悟ｭ伜惠縺吶ｋ縲８竊淡' 縺ｧ D_floor(W')<D_floor(W) 繧帝＃謌舌＠縺ｦ繧・    D_floor(W')>0 縺ｯ菫晄戟縲ゅ％縺ｮ蜈･繧悟ｭ舌・蜿ｯ邂怜狗ｶ壹″縲∝推髫主ｱ､縺ｯ逡ｰ縺ｪ繧狗黄逅・謨ｰ蟄ｦ蜴溽炊縺ｫ逕ｱ譚･縲・    2萓・ GPS (DOP竊但llan), LIGO (classical竊痴hot竊担QL竊辿eisenberg)縲・    Landauer (kT ln 2 竊・Maxwell demon 竊・諠・ｱ蜃ｦ逅・さ繧ｹ繝・ 縺檎ｬｬ3萓句呵｣懊・    S13 (ln 2 fixed-point) 縺ｨ縺ｮ蜷域ｵ∝庄閭ｽ諤ｧ縺ゅｊ縲よ・譬ｼ縺ｫ縺ｯ隨ｬ3萓九・蠖｢蠑冗噪讀懆ｨｼ縺悟ｿ・ｦ√・---

# Recursive Floor Principle 窶・D_floor 縺ｮ蜀榊ｸｰ逧・嚴螻､讒矩

**Level**: L1 (讓ｪ譁ｭ蜴溽炊縲‥omain-independent)
**Status**: **ESTABLISHED** (2026-04-12, GPS/LIGO/Landauer type-signature + principle-switch verified)
**Role**: D_floor > 0 縺後悟・逋ｺ逧・↑蟾･蟄ｦ髯千阜縲阪〒縺ｯ縺ｪ縺・縲瑚ｦｳ貂ｬ閠・′譛蛾剞縺ｧ縺ゅｋ髯舌ｊ蟶ｸ縺ｫ菴輔ｉ縺九・荳矩剞縺悟ｭ伜惠縺吶ｋ縲阪→縺・≧讒矩螳夂炊縺ｮ蛟呵｣・
---

## ﾂｧ1 Statement

> 莉ｻ諢上・隕ｳ貂ｬ陬・ｽｮ W 縺ｫ蟇ｾ縺励※ D_floor(W) > 0 縺悟ｭ伜惠縺吶ｋ縲・> 謚陦捺隼濶ｯ W 竊・W' 縺ｫ繧医ｊ D_floor(W') < D_floor(W) 縺碁＃謌舌＆繧後※繧ゅ・> D_floor(W') > 0 縺ｯ菫昴◆繧後ｋ縲・> 縺薙・蜈･繧悟ｭ舌・蜿ｯ邂礼┌髯舌↓邯壹￥蜿ｯ閭ｽ諤ｧ縺後≠繧翫・> 蜷・嚴螻､縺ｮ荳矩剞縺ｯ逡ｰ縺ｪ繧狗黄逅・噪繝ｻ謨ｰ蟄ｦ逧・次逅・↓逕ｱ譚･縺吶ｋ縲・
蠖｢蠑冗噪:

```
D_floor: W 竊ｦ 邃昶ｊ
竏 W: D_floor(W) > 0
竏 W, 竏・W': D_floor(W') < D_floor(W)  (謚陦捺隼濶ｯ縺ｯ蜿ｯ閭ｽ)
竏 W': D_floor(W') > 0                (繧ｼ繝ｭ縺ｫ縺ｯ蛻ｰ驕斐＠縺ｪ縺・

蜷・W_n 縺ｮ D_floor 縺ｯ逡ｰ縺ｪ繧狗黄逅・次逅・P_n 縺ｫ逕ｱ譚･:
  D_floor(W_0) 竊・P_0 (蟾･蟄ｦ逧・宛邏・
  D_floor(W_1) 竊・P_1 (邨ｱ險育噪蛻ｶ邏・
  D_floor(W_2) 竊・P_2 (驥丞ｭ千噪蛻ｶ邏・
  D_floor(W_3) 竊・P_3 (諠・ｱ逅・ｫ也噪蛻ｶ邏・
  ...
```

---

## ﾂｧ2 Existing Evidence (2 examples)

### ﾂｧ2.1 LIGO 窶・譛繧よ・遒ｺ縺ｪ蜀榊ｸｰ

```
Level 0: Classical noise limit
  蜴溽炊: 蜿､蜈ｸ蜉帛ｭｦ (蝨ｰ髴・険蜍・ 辭ｱ謠ｺ蜍・
  D_floor: ~10竅ｻﾂｹ竅ｸ /竏唏z
  蝗樣∩: suspension isolation, cryogenics
          竊・Level 1: Shot noise limit
  蜴溽炊: 蜈牙ｭ舌・邊貞ｭ先ｧ (Poisson邨ｱ險・
  D_floor: 竏・1/竏啀_laser
  蝗樣∩: 繝ｬ繝ｼ繧ｶ繝ｼ繝代Ρ繝ｼ蠅怜刈
          竊・Level 2: SQL (Standard Quantum Limit)
  蜴溽炊: 荳咲｢ｺ螳壽ｧ蜴溽炊 ﾎ肺ﾂｷﾎ廃 竕･ 邃・2
  D_floor: 竏・8邃・(mﾏ可ｲLﾂｲ)) 窶・laser power 縺ｫ萓晏ｭ倥＠縺ｪ縺・  蝗樣∩: 繧ｹ繧ｯ繧､繝ｼ繧ｺ繝牙・ (O4 縺ｧ ~3dB)
          竊・Level 3: Heisenberg limit
  蜴溽炊: 邃・per photon (驥丞ｭ舌Μ繧ｽ繝ｼ繧ｹ縺ｮ譬ｹ譛ｬ逧・怏髯先ｧ)
  D_floor: SQL / 竏哢_photon
  蝗樣∩: ???
```

蜷・Ξ繝吶Ν縺ｧ逡ｰ縺ｪ繧狗黄逅・次逅・′荳矩剞繧呈髪驟阪・Level 2竊・ 縺ｮ驕ｷ遘ｻ縺ｯ縲御ｸ咲｢ｺ螳壽ｧ蜴溽炊縲阪°繧峨碁㍼蟄舌Μ繧ｽ繝ｼ繧ｹ縺ｮ譛蛾剞諤ｧ縲阪∈縺ｮ shift縲・
### ﾂｧ2.2 GPS 窶・蟾･蟄ｦ逧・・蟶ｰ

```
Level 0: 蜿嶺ｿ｡讖溽ｲｾ蠎ｦ (繧ｳ繝ｼ繝芽ｿｽ霍｡)
  蜴溽炊: ADC蛻・ｧ｣閭ｽ + 蟶ｯ蝓溷宛髯・  D_floor: ~3 m
  蝗樣∩: 謳ｬ騾∵ｳ｢菴咲嶌霑ｽ霍｡
          竊・Level 1: 謳ｬ騾∵ｳ｢菴咲嶌 + 陬懈ｭ｣
  蜴溽炊: 螟ｧ豌励Δ繝・Ν邊ｾ蠎ｦ + 譎りｨ亥ｮ牙ｮ壼ｺｦ
  D_floor: ~0.5 m
  蝗樣∩: 莠悟捉豕｢, RTK
          竊・Level 2: Allan variance limit
  蜴溽炊: 蜴溷ｭ先凾險医・驥丞ｭ先昭繧峨℃ (Cs: ~10竅ｻﾂｹﾂｳ at 1s)
  D_floor: ~mm level (髟ｷ蝓ｺ邱・RTK)
  蝗樣∩: 蜈画ｼ蟄先凾險・(~10竅ｻﾂｹ竅ｸ) 縺ｸ縺ｮ遘ｻ陦・          竊・Level 3: 蜈画ｼ蟄先凾險・+ 逶ｸ蟇ｾ隲也噪貂ｬ蝨ｰ
  蜴溽炊: 驥榊鴨繝昴ユ繝ｳ繧ｷ繝｣繝ｫ縺ｮ貂ｬ螳夐剞逡・(GR 鬮俶ｬ｡鬆・
  D_floor: ???
```

LIGO 縺ｻ縺ｩ譏守｢ｺ縺ｧ縺ｯ縺ｪ縺・′縲．_floor 縺後檎焚縺ｪ繧句次逅・・荳矩剞縺ｫ鬆・ｬ｡鄂ｮ縺肴鋤繧上ｋ縲肴ｧ矩縺ｯ蜷後§縲・
---

## ﾂｧ3 Third Example Candidate: Landauer / S13

**S13 (ln 2 Fixed-Point Principle)**: e^{-x} = 1/2 筺ｹ x = ln 2

**Landauer 縺ｮ蜀榊ｸｰ讒矩**:
```
Level 0: Irreversible computation (蜿､蜈ｸ, 謨｣騾ｸ螟ｧ)
  D_floor: 蜈ｸ蝙狗噪縺ｫ kT ﾃ・10ﾂｳ窶・0竅ｶ per bit
  蝗樣∩: 蜿ｯ騾・ｨ育ｮ苓ｨｭ險・          竊・Level 1: Landauer limit = kT ln 2 per bit erased
  蜴溽炊: 辭ｱ蜉帛ｭｦ隨ｬ莠梧ｳ募援
  D_floor: kT ln 2 竕・2.87ﾃ・0竅ｻﾂｲﾂｹ J at 300K
  蝗樣∩: Maxwell's demon? 竊・NO (谺｡縺ｮ Level 縺悟・迴ｾ)
          竊・Level 2: 諠・ｱ蜃ｦ逅・さ繧ｹ繝・= Szilard engine
  蜴溽炊: demon 閾ｪ霄ｫ縺ｮ險俶・豸亥悉縺ｫ kT ln 2 縺悟ｿ・ｦ・  D_floor: kT ln 2 (demon 縺ｮ險育ｮ励さ繧ｹ繝・
  蝗樣∩: 驥丞ｭ占ｨ育ｮ・ 竊・驛ｨ蛻・噪 (unitary 縺ｯ蜿ｯ騾・□縺梧ｸｬ螳壹・荳榊庄騾・
          竊・Level 3: 驥丞ｭ先ｸｬ螳壹・荳榊庄騾・さ繧ｹ繝・  蜴溽炊: 豕｢蜍暮未謨ｰ蜿守ｸｮ縺ｮ繧ｨ繝ｳ繝医Ο繝斐・逕滓・
  D_floor: ???
```

**S13 縺ｨ縺ｮ謗･邯・*: ln 2 縺・Level 1窶・ 縺ｮ fixed point 縺ｨ縺励※蜃ｺ迴ｾ縺吶ｋ縲・S13 縺ｯ縲御ｹ玲ｳ・scan 縺ｮ蜊雁､譚｡莉ｶ e^{-x}=1/2 縺ｮ譎ｮ驕崎ｧ｣縲阪→縺励※縺薙ｌ繧定ｨ倩ｿｰ貂医∩縲・Recursive Floor Principle 縺ｯ縲後↑縺・ln 2 縺後＞縺､繧ょ・縺ｦ縺上ｋ縺九阪↓讒矩逧・屓遲斐ｒ荳弱∴繧句庄閭ｽ諤ｧ:
**蜷・Level 縺ｧ蜷後§蜊雁､譚｡莉ｶ縺悟・蜃ｺ迴ｾ縺吶ｋ縺九ｉ縲・*

---

## ﾂｧ4 蜩ｲ蟄ｦ逧・性諢・
> D_floor > 0 縺ｯ蛻ｶ邏・〒縺ｯ縺ｪ縺丞ｭ伜惠縺ｮ譚｡莉ｶ縺ｧ縺ゅｋ縲・
- 譛蛾剞縺ｮ隕ｳ貂ｬ閠・′辟｡髯千ｲｾ蠎ｦ縺ｫ蛻ｰ驕斐〒縺阪↑縺・％縺ｨ縺ｯ縲瑚・蜉帙・荳崎ｶｳ縲阪〒縺ｯ縺ｪ縺・- 縺昴ｌ縺ｯ縲梧怏髯舌〒縺ゅｋ縺薙→閾ｪ菴薙′隕ｳ貂ｬ繧貞庄閭ｽ縺ｫ縺吶ｋ讒矩縲阪・蟶ｰ邨・- 辟｡髯千ｲｾ蠎ｦ = D_floor = 0 竊・隕ｳ貂ｬ閠・→蟇ｾ雎｡縺ｮ蛹ｺ蛻･縺梧ｶ域ｻ・竊・縲瑚ｦｳ貂ｬ縲肴ｦょｿｵ縺檎┌諢丞袖蛹・
finite_observation ﾂｧ0 Thesis: "All observation is finite. All structure lives in the infinite limit.
The art is extracting one from the other."

Recursive Floor Principle 縺ｯ 縺薙・ thesis 縺ｮ螳夐㍼迚・
**謚ｽ蜃ｺ縺ｮ邊ｾ蠎ｦ繧剃ｸ翫￡繧九さ繧ｹ繝医・縲∫黄逅・次逅・・髫主ｱ､繧堤匳繧九さ繧ｹ繝医→蜷悟､縲・*

---

## ﾂｧ5 譏・ｼ譚｡莉ｶ (conjecture 竊・established)

1. **隨ｬ3萓九・蠖｢蠑冗噪讀懆ｨｼ**: Landauer 縺ｮ蜀榊ｸｰ讒矩縺・LIGO 縺ｨ蜷御ｸ縺ｮ type signature 繧呈戟縺､縺薙→縺ｮ遒ｺ隱・   - 蜈ｷ菴鍋噪: 蜷・Level 縺ｮ (蜴溽炊, D_floor蛟､, 蝗樣∩謇区ｮｵ, 谺｡縺ｮ蜴溽炊) 縺ｮ 4-tuple 縺・     GPS, LIGO, Landauer 縺ｧ蜷御ｸ讒矩縺ｧ縺ゅｋ縺薙→
2. **蜿堺ｾ区擅莉ｶ**: D_floor(W') = 0 縺碁＃謌舌＆繧後ｋ邉ｻ縺悟ｭ伜惠縺励↑縺・％縺ｨ縺ｮ隴ｰ隲・   - 蛟呵｣懷渚萓・ 驥丞ｭ占ｪ､繧願ｨよｭ｣隨ｦ蜿ｷ (asymptotically perfect) 竊・迚ｩ逅・ｳｻ縺ｧ縺ｯ謌千ｫ九＠縺ｪ縺・′諠・ｱ逅・ｫ也噪縺ｫ縺ｯ蜿ｯ閭ｽ?
3. **S13 縺ｨ縺ｮ蜷域ｵ・*: ln 2 縺悟推 Level 縺ｮ fixed point 縺ｨ縺励※閾ｪ辟ｶ縺ｫ蜃ｺ迴ｾ縺吶ｋ縺九・遒ｺ隱・
**graveyard 辣ｧ蜷・*: L4_errors 縺ｫ D_floor 髢｢騾｣縺ｮ falsified conjecture 縺ｪ縺・(2026-04-12 遒ｺ隱肴ｸ医∩)縲・OQ-YM-1 縺ｮ D_floor formal 縺ｯ蛻･迚ｩ (mass gap 縺ｮ蟄伜惠蛻､螳壹〒縺ゅｊ蜀榊ｸｰ讒矩縺ｧ縺ｯ縺ｪ縺・縲・
---

## Revision 2026-04-12 (Statement Update)

Legacy wording emphasized strict scalar decrease (`D_floor(W') < D_floor(W)`).
The validated invariant is stronger and different:

- Recursive-floor behavior is governed by **principle replacement**, not guaranteed scalar decrease.
- Across levels, the dominant mechanism shifts `P_n -> P_{n+1}` while `D_floor > 0` remains.
- Landauer L1-L2-L3 confirms this: the value scale `kT ln 2` can recur, but the governing principle changes.

Canonical statement:
`RFP tracks transitions of floor-governing principles across levels; nonzero floor persists under finite observation.`

---

## §6 統一不等式と β-Type 分離 (2026-04-12)

### §6.1 統一不等式の枠組み

RFP の各 Level で D_floor を支配する不等式は、共通形式に書ける:

```
D × Resource^β ≥ κ(β)
```

ここで:
- D = 精度 (distortion)
- Resource = 投入資源 (観測コスト)
- β = obstruction depth (不等式の種類を索引)
- κ(β) = 構造定数 (各不等式の sharp lower bound)

既知の (β, κ) 対:

| β | κ(β) | 不等式 | 構造定数 |
|---|---|---|---|
| 0 | ln 2 ≈ 0.6931 | Landauer: D_bit ≥ kT ln 2 | ln 2 |
| 1 | 1/2 | Heisenberg: ΔxΔp ≥ ℏ/2 | 1/2 |
| 2 | 1/√5 ≈ 0.4472 | Hurwitz: \|α-p/q\| ≥ 1/(√5 q²) | 1/√5 |

κ(β) の「構造定数」とは、物理定数 (kT, ℏ) を分離した後の純粋数論的/構造的な下限値。

### §6.2 Type I / Type II 分離 (核心)

β=1/2 (shot noise limit: δφ×√N ≥ 1, κ=1) を §6.1 の系列に投入すると、
κ(1/2) = 1 > κ(0) = ln 2 となり、β=0→1/2 で κ が増加する。
下に凸の放物線で 4 点を表現することは不可能 — **即座に破綻**。

原因分析により、**2つの異なる不等式族が混合されていた**ことが判明:

**Type I: Single-shot obstruction depth**
- 1回の測定における根本限界
- Resource は測定の「構造的深さ」を索引
- β = 0 (情報論), 1 (量子力学), 2 (数論)
- κ(β) は単調減少: ln 2 > 1/2 > 1/√5

**Type II: N-scaling exponent**
- N 回測定の統計的集約による精度改善
- Resource = 測定回数 N, β = scaling exponent
- β = 1/2 (SQL/shot noise), 1 (Heisenberg limit for N measurements)
- κ は系列内で一定 (κ=1)

```
Type I:  β=0 ─── β=1 ─── β=2
         ln2     1/2     1/√5
         info    quantum  number theory
         (obstruction depth = 代数的/構造的深さ)

Type II: β=1/2 ── β=1
         1        1
         SQL      Heisenberg (N-scaling)
         (N-scaling = 統計的集約の効率)
```

**混合禁止則**: Type I と Type II の (β, κ) を同一の κ(β) 関数に載せてはならない。
物理的根拠: Type I は single-shot の構造的限界、Type II は反復測定の統計的限界であり、
β の意味が異なる (obstruction depth ≠ scaling exponent)。

β=1 が両 Type に出現するのは偶然ではなく:
- Type I β=1: ΔxΔp ≥ ℏ/2 (共役変数ペアの同時測定)
- Type II β=1: δφ ≥ 1/N (N 光子の集約)
同じ β=1 だが、κ が異なる (1/2 vs 1)。

### §6.3 放物線 κ(β) — RETIRED (2026-04-12)

**Status**: RETIRED (undecidable → 構造的に無意味)

前セッション (2026-04-12 前半) で提案された κ(β) の放物線:
κ(β) = 0.0702β² − 0.2633β + ln 2

棄却理由:
1. **3点アーティファクト**: 2次多項式は 3 パラメータ → 3 点で自明に通る (検証力ゼロ)
2. **Type 混合**: Type I/II を混合した 4 点目 (β=1/2, κ=1) で即座に破綻
3. **Type I 内でのテスト不可能**: 非整数 β の sharp 定数が未知 (数学の未解決問題)
4. **β>2 の不在**: Diophantine 同時近似 β=1+1/n ≤ 2, Liouville β=d ≥ 2 で β>2 の自然な候補がない

放物線の「禁止境界 β*≈2.39」は Type 混合 + 3 点自明 fit の産物であり、構造的意味を持たない。

### §6.4 β = 1+1/n 系列 (Diophantine 次元)

Type I の β=2 (Hurwitz) は 1 次元有理近似の sharp bound。
n 次元同時 Diophantine 近似では:

```
max_i |α_i - p_i/q| ≤ 1 / q^{1+1/n}    (Dirichlet)
```

→ β(n) = 1 + 1/n:

| n | β(n) | sharp κ | 状態 |
|---|---|---|---|
| 1 | 2 | 1/√5 (Hurwitz) | EXACT |
| 2 | 3/2 | ??? | OPEN (Davenport-Schmidt) |
| 3 | 4/3 | ??? | OPEN |
| ∞ | →1 | →1/2 (Heisenberg) | REFUTED (current evidence) |

n→∞ で β→1 は成立するが、κ→1/2 (Heisenberg 合流) は現時点の数値探索では支持されない。
κ(2)<κ(1) が強く示唆され、少なくとも単純な「単調増加して 1/2 に接近」という図式は棄却された。

検証には n=2 の sharp constant が必要 → OQ-KAPPA-LIMIT。

### §6.5 Series A / Series B 分離と Model B (2026-04-12)

文献調査により n=2 の sharp constant は OPEN (Cusick 1983, Cassels-Swinnerton-Dyer 1955)。
Littlewood conjecture に関連する数学のフロンティア問題。

**Type I は 2 系列から構成される**:

```
Series A: β=0, κ=ln 2        (情報論, 環境依存)
Series B: β=1+1/n (n=1,2,...) (量子-数論, 環境非依存)
  n=1: β=2, κ=1/√5 (Hurwitz)
  n→∞: β→1, κ→1/2 (Heisenberg = 集積点)
```

Series A と Series B は独立: β=0 (Landauer) は Diophantine 由来ではない。
κ_A = ln 2 > κ_B(β→1) = 1/2 — 環境依存の限界は環境非依存より厳しい。

**Model B** (κ(n) の定量予測, legacy):

```
κ(n) = 1/√(4 + 1/n) = √(n/(4n+1))
```

- n=1: 1/√5 (Hurwitz exact) ✓
- n→∞: 1/√4 = 1/2 (Heisenberg) ✓
- √5 = √(4+1) の「1」を Diophantine 次元 n=1 に由来と見て「4+1/n」に一般化
- n=2 予測: κ = √(2/9) ≈ 0.4714

**Status update (2026-04-12, late): REJECTED (strong empirical)**
- 2D 実験系列で κ は増加ではなく減少方向 (κ(2) < κ(1)) が優勢。
- 予測方向が観測と逆のため、Model B は凍結。
- n=2 sharp constant 未解決のため「厳密反証」ではないが、運用上は棄却。

### §6.6 1D/2D 構造的非対称性 (2026-04-12)

κ(n) の n 依存性は、continued fractions (1D) と Jacobi-Perron (2D) の代数構造差に起因する。

**1D (continued fractions)**:
- recurrence は 2 次特性方程式 `t^2 - a t - 1 = 0`
- Vieta により根の積は常に `-1`
- この制約が periodic CF の metric 定数性を保証し、`κ(1)=1/sqrt(5)` が exact に固定される

**2D (Jacobi-Perron)**:
- recurrence は 3 次特性方程式 `t^3 - a t^2 - b t - c = 0`
- Vieta により根の積は `c` (自由)
- 1D で成立した「積=固定」の保証が消え、metric は generic に定数化しない
- その結果、観測される 0.43 近傍は「準定数」挙動であり、1D 型 exact constant ではない

**数値的定量** (Δ=49 field, pair (α₁,α₂), 626 ペア体系探索で独走):

```
q growth rate λ₁  = 20.443
|δ decay rate λ₂| = 0.2210
metric ratio r    = √λ₁ × |λ₂| = 0.9994
                   (1D 対応: λ₁×|λ₂| = 1.000 exactly)
half-life         = 1080 record steps ≈ q ~ 10^1415
practical κ(2)    ≈ 0.433 (10^1415 桁まで有効)
formal lim inf    = 0 (r < 1 → metric → 0, but absurdly slowly)
```

**κ(n) の減少メカニズム**: n 次元同時近似 = Z^{n+1} 内の 1D 直線近傍 (n 次元管) を探索。
格子点候補数 ∝ q^{(n-1)/n}。n 増加 → 候補増加 → worst case でも「逃げ場」→ κ 減少。

結論:
- `κ(1)` の exact algebraic rigidity (Vieta 保証) と `κ(2)` の非剛性は 1D/2D の構造差に起因
- `κ(n)->1/2` 合流仮説は否定的 (κ は n で減少方向)
- κ(2) の exact value は badly approximable pair (r=1 exactly) の sup — OPEN
- Schmidt (1969): badly approx pairs は full Hausdorff dimension → 存在は保証されるが explicit construction は数学のフロンティア
- OQ-KAPPA-LIMIT は OPEN のまま保持、方向修正 (合流→減少)

**κ(n) 3-point comparison (2026-04-12)**:

| n | β | κ(n) | κ/κ₁ | worst field | r (metric ratio) |
|---|---|------|------|-------------|-------------------|
| 1 | 2 | 0.4472 (exact) | 1.000 | Q(√5), Δ=5 | 1.000 (CF exact) |
| 2 | 3/2 | ≈0.433 (quasi) | 0.968 | Q(2cos(2π/7)), Δ=49 | 0.9994 |
| 3 | 4/3 | ≈0.37 (fragile) | 0.83 | Δ≈2048 quartic | ≈0.6-0.9 |

κ(1) > κ(2) > κ(3): confirmed. Drop accelerates (3%→22%). n→∞ extrapolation: κ → 0 exponentially.
n=3 の metric ratio は n=2 (0.9994) より大幅に 1 から遠く、JP 非対称性が次元増加で悪化することを示す。

### §6.7 κ(2) 数値精密化と代数的同定 (2026-04-13)

**目的**: κ(2) の exact value を Δ=49 cubic field の代数的不変量から同定。

**手法**: Q(2cos(2π/7)) の conjugate pair (α₁, α₂) に対し q ≤ 2M まで
max|αᵢ - pᵢ/q| × q^{3/2} の lim inf を直接計算。

**結果**:

```
κ-record sequence:
  q=1:        κ = 0.44504
  q=4:        κ = 0.43967
  q=81:       κ = 0.43552
  q=1,656:    κ = 0.43407
  q=33,853:   κ = 0.43320
  q=692,045:  κ = 0.43292  ← float64 精度限界で最終 record

q-growth rate: 20.4426 (安定, 3連続一致)
Aitken 外挿 (最終3点): L ≈ 0.43279
```

**Field invariants**:

```
Minimal polynomial: x³ + x² - 2x - 1 = 0
Roots: λ₁ = 1.2470, λ₂ = -0.4450, λ₃ = -1.8019
  |λ₁|, |λ₃| > 1 (2方向膨張), |λ₂| < 1 (唯一の収縮)
Units: α (N=1), α+1 (N=-1) — both fundamental
Regulator: R = 0.5255
```

**代数的候補比較**:

| Expression | Value | |κ - target| |
|---|---|---|
| √3/4 | 0.43301 | 9.2×10⁻⁵ |
| 1/√(|λ₁-λ₂|·|λ₁-λ₃|) | 0.44028 | 7.4×10⁻³ |
| |λ₂| | 0.44504 | 1.2×10⁻² |
| sin(π/7) | 0.43388 | 9.6×10⁻⁴ |

**√3/4 が最近接** だが Richardson limit (0.43279) は √3/4 より下。
float64 精度では exact 同定不可 (q ≈ 14M で必要な max_err ≈ 10⁻¹² が検出限界以下)。

**Growth rate 20.4426**:
- Regulator R = 0.5255 とは log(growth)/R = 5.743 (non-integer)
- 整数 3-term 回帰フィットは初期項の不規則性で不正確
- 代数的同定 OPEN

**Cross-field 比較** (Δ=49 worst 確認):

| Field | Δ | κ (lim inf, q≤50k) |
|---|---|---|
| Q(2cos(2π/7)) | 49 | 0.4332 ← worst |
| x³-3x-1 | 81 | 0.3473 |
| x³+x²-4x+1 | 169 | 0.3089 |
| x³+x²-4x-3 | 229 | 0.1887 |

Δ 増加 → κ 減少: worst case = 最小判別式 Δ=49 (1D と同構造: worst = Δ_min = 5)。

**Status**: κ(2) exact 同定には multiprecision 計算が必要。
√3/4 は有力候補だが確定せず。次のステップ: mpmath 導入 + q ≤ 10⁸ スキャン。
Scripts: experiments/core/oq_beta_kappa2_jp.py, _extended.py, _14M.py, _recurrence.py

### §6.8 D_floor(s) — RFP と ζ 零点 (2026-04-13, from Paper 2/Twin-Zeta bridge)

Gap-indexed factorization (Twin-Zeta session 2026-03-04) の再評価により:

```
F_{g,k}(s) = κ_g · G_k(s) · W_k(ω)  +  a_g · Δ_k(s)  +  ε_{g,k}(N)
```

この三層は S15 Observable Trichotomy と同型 (Scan / Structural / Information)。

s-依存性:
- s = 1: mod 6 arithmetic effects visible (R² drops for g ≡ 0 mod 6)
- s = 1/2: arithmetic effects vanish (R² > 0.9998 for ALL g)

**D_floor(s) 概念** (OQ-P2-2):
RFP の D_floor > 0 を Dirichlet 級数のパラメータ s に拡張すると:
- D_floor(s=1) > 0: arithmetic obstruction 残存 (mod 6 ε が factorization を乱す)
- D_floor(s=1/2) ≈ 0: arithmetic obstruction 消滅 (critical line の特殊性)

もし D_floor(s) = 0 ⟺ s = 1/2 が formal に成り立てば、
これは **RH の ΣΦ 翻訳**: ζ 零点が critical line 上にある
⟺ gap-indexed Dirichlet 級数の完全分解が s=1/2 でのみ成立。

**D_floor(s) 最終形 (2026-04-13, OQ-P2-2: 4 CONFIRMED / 1 REJECTED / 0 OPEN)**:

```
D_floor(s, N) ~ N^{-0.68} · exp(0.216 · (log N)^2 · (s - 1/2)^2)
```

| Component | Value | Evidence |
|---|---|---|
| s 依存性 | (s−1/2)² 放物型 | Model C R²>0.997 全 N |
| 曲率 | 0.216·(log N)² | R²=0.9999 (明示公式 ⟨log p⟩² と整合) |
| D₀(N) | N^{−0.68} [CI: 0.65, 0.72] | R²=0.998, 3 decades (10⁶→10⁹) |
| γ₁ dip | t_min=14.17±0.04 (γ₁=14.135) | 21σ 全点 σ-continuous |
| Gap-universal | slope variation ±4% | 11 gaps tested |
| ε_k 零点対応 | **REJECTED** (p=0.81) | Negative result, §9.4 |

**Status**: **ESTABLISHED** (全 sub-Q closed)。
Residence: research/paper2_twin_dictionary_bridge_v0.md §9, c_theorems_master.md D_floor(s)

#### §6.8.1 Dirichlet L gap universality fragment (Paper N3 §4.6, 2026-04-26)

§6.8 で確立した D_floor(s) 放物型公式は **ζ-family core** (Paper C / Paper N2) で full ESTABLISHED。Paper N3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md` §4) は本公式を Dirichlet L 系列に extension する trajectory を **honest dual reporting** で展開した。本 §6.8.1 はその **genuine extension fragment** (gap universality 12/12 PASS) を本 entry の structural extension として記録する。

##### Dirichlet L extension scope (Paper N3 §4 trajectory summary)

Paper C D_floor framework (§6.8) の Dirichlet L lifting attempt (OQ-Ω5 v1.5 系列, 2026-04-24/25) の verdict 一覧:

| Sub-result | Status | Source |
|---|---|---|
| Real / complex primitive χ σ_min = 1/2 | CONFIRMED but **universal functional eq identity-level** (SC4 catch) | Paper N3 §4.1-§4.3, T-Ω5e-v15-* rows |
| 2-quantity (\|L\|² + \|Λ\|²) coincide | **REJECTED** (G2 17.5%) | Paper N3 §4.4, T-Ω5e-v15-2quantity row |
| Paper C (log N)² curvature scaling | **REJECTED** (super-(log N)² growth) | Paper N3 §4.5, T-Ω5e-v15-dfloor-multigap-v1 row |
| **Multi-gap structural invariance** | **CONFIRMED 12/12 PASS** (genuine fragment) | Paper N3 §4.6, T-Ω5e-v15-dfloor-multigap-v1 row G3 byproduct |

##### Multi-gap universality 12/12 PASS の structural 内容

Paper N3 §4.5 (`research/oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md`) の v1b v1 sweep:
- 3 complex primitive χ (q=5 ord=4, q=7 ord=3, q=11 ord=5)
- 4 N values (10⁴, 10⁵, 10⁶, 10⁷)
- 3 gap classes (g ∈ {2, 4, 6})
- = 36 cells

主 hypothesis "(log N)² curvature scaling" が REJECTED (G2 0/3 pass) する一方、**G3 gap-class universality** (max/min ratio < 1.5 across g) は **12/12 cells で PASS** (max/min ratio < 1.15)。

これは §6.8 で確立した Paper C D_floor の **gap-universal slope variation ±4%** (11 gaps tested at ζ-family) と直接対応する structural pattern が Dirichlet L 側でも **構造的に保存される** ことを意味する。

##### Framework scope partition

| Layer | Status on Dirichlet L | Structural meaning |
|---|---|---|
| Path 2 instance class membership | ✅ CONFIRMED | weight $k = 1$ family member (`nt_dedekind_artin_zeta.md §7`) |
| σ_min = 1/2 identity-level | ✅ CONFIRMED but trivial | universal functional eq identity (SC4) |
| **Multi-gap structural invariance** | ✅ **CONFIRMED 12/12** | **本 §6.8.1 の genuine extension fragment** |
| 2-quantity Information+Structural coincide | ❌ REJECTED | Paper C 2-quantity uniqueness は ζ 固有 |
| Paper C (log N)² curvature scaling | ❌ REJECTED | naive Taylor approach mismatch |
| ζ functional equation enforcement | ζ 固有 | Paper N2 §6.1 |

**意味**: §6.8 の D_floor 放物型公式 in full form (parabolic + (log N)² + N^{−2/3} + γ₁ dip) は **ζ-family core 固有** だが、その中の **multi-gap invariance 部分** は **ζ-family member 全体で保存** される genuine structural extension fragment。これは `c_theorems_master.md` "Path 2 countably-infinite family" annex の "structural fit only" verdict と consistent: Path 2 family member は structural pattern (gap universality) を共有するが、individual member 固有 predictive content (Paper C 2-quantity coincide + (log N)² curvature) は member 個別。

##### "Structural fit only" verdict の D_floor frame での再読み

Paper N3 §4 overall verdict "Dirichlet L extension scope = structural fit only" を §6.8 frame で再読みすると:

> §6.8 D_floor public formula は **(s − 1/2)² parabolic vertex location** (s = 1/2 universal) + **multi-gap invariance** (gap universal) + **(log N)² curvature** (ζ-specific) + **N^{−2/3} decay** (ζ-specific) + **γ₁ dip locking** (ζ-specific) の 5 component で構成される。
>
> - **Parabolic vertex location** (s = 1/2): SC4 universal identity-level, Path 2 class member 全体で trivial に hold
> - **Multi-gap invariance** (slope variation < 5%): structural extension fragment, ζ-family member 全体で genuine に hold (本 §6.8.1)
> - **Curvature 0.216·(log N)²**: Paper C-level predictive content, ζ 固有 (Dirichlet L で REJECTED)
> - **D₀ ∼ N^{−2/3}**: Paper C-level predictive content, ζ 固有
> - **γ₁ dip locking**: ζ 固有 (RH translation specific to ζ zeros)

→ **§6.8 D_floor 公式の 5 component のうち 2 個 (vertex location + multi-gap invariance) が Dirichlet L family へ extension 可能、残り 3 個 (curvature scaling + decay + γ₁ dip) は ζ 固有**。

**Status**: Multi-gap universality fragment は Paper N3 v0.2 (2026-04-26) で **ζ-family member 全体で保存される structural extension fragment** として ESTABLISHED。残り 3 component の ζ 固有性は paper N2 §3 + Paper N3 §4 で formal closed (Dirichlet L extension trajectory completed)。

**Ref**:
- Paper N3 §4.6 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`)
- `research/oq_omega5_v15_dirichlet_l_dfloor_multigap_v1b_v1.md` (主体, REJECTED + G3 byproduct PASS)
- `c_theorems_master.md` "Dirichlet L extension scope (Paper N3 §4)" annex
- `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite family)

#### §6.8.2 Hasse-Weil L extension — BSD analytic rank detection (Paper N4 §3, 2026-04-26)

§6.8 ζ-family core + §6.8.1 Dirichlet L extension fragment の next layer として、Paper N4 (`papers/publication/nt/N4_hasseweil_stark_ja.md` §2-§3) で Hasse-Weil L (weight-2 modular L) extension を v2 arc 8-stage trajectory で展開。**§6.8.1 Dirichlet L "structural fit only" close と対照的に、Hasse-Weil L で framework predictive content が genuine に transfer する** ことが confirmed。本 §6.8.2 はその dictionary residence。

##### Hasse-Weil L weight-2 extension setup

Elliptic curve $E$ over ℚ (conductor $N_E$, root number $\varepsilon(E) = \pm 1$) の completed L-function:

$$\Lambda(s, E) := N_E^{s/2} \cdot (2\pi)^{-s} \cdot \Gamma(s) \cdot L(s, E)$$

Functional equation $\Lambda(s, E) = \varepsilon(E) \cdot \Lambda(2-s, E)$、involution $\sigma_E: s \mapsto 2-s$、Fix locus $s = 1$ (vs Dirichlet L $s = 1/2$, weight-class shift)。

##### BSD analytic rank detection (genuine framework predictive content)

**Theorem (N4 §3 main, v2 v8 ESTABLISHED)**: Elliptic curve $E$ with analytic rank $r$ について、central curvature

$$K_E(t) := \partial^2_\sigma \log|\Lambda(E, \sigma + it)|_{\sigma = 1}$$

は

$$K_E(t) \cdot t^2 \to r \quad \text{as} \quad t \to 0+$$

with $O(t^2)$ subleading correction。これは §6.8 D_floor 放物型公式の **ζ-family core 固有 component** (curvature 0.216·(log N)² + decay N^{−2/3} + γ₁ dip locking) とは異なる **weight-2 specific predictive content**。

##### §6.8 D_floor 公式 component 別 transfer pattern (N4 で完成)

Paper N3 §4.6 で ζ vs Dirichlet L で identify した 5 component partition + Paper N4 §3 の Hasse-Weil 結果:

| Component | ζ-family core (§6.8) | Dirichlet L (§6.8.1) | Hasse-Weil L (§6.8.2) |
|---|---|---|---|
| Parabolic vertex location | s = 1/2 | ✅ trivial (SC4 universal) | ✅ s = 1 (Fix locus, weight-2 analogue) |
| Multi-gap / conductor structural invariance | ✅ slope variation ±4% (11 gaps) | ✅ **CONFIRMED 12/12** (gap universality) | ✅ 21/24 PASS at t≥5 (4 non-CM curves) |
| Curvature scaling | ✅ 0.216·(log N)² (R²=0.9999) | ❌ REJECTED (super-(log N)²) | (different scaling: BSD K_E·t² instead) |
| Decay | ✅ N^{−2/3} (R²=0.998) | (not tested) | (different observable: K_E central curvature) |
| Zero detection | ✅ γ₁ dip 21σ-points | (not applicable) | ✅ **K_E·t² → r (analytic rank, 9/10 within 5%)** |

**重要な観察**: 各 weight-class が **異なる predictive content** を carry する:
- weight 1 (ζ): D_floor 放物型 (curvature scaling + decay + γ₁ dip) — ζ 固有
- weight 1 (Dirichlet L): structural fit only (vertex + gap universality genuine, curvature scaling REJECTED)
- weight 2 (Hasse-Weil L): **BSD analytic rank detection** (K_E·t² → r genuine, conductor universality preserved)

→ Framework predictive transfer は **weight-class dependent**、**naive component-by-component transfer ではなく weight ごとに predictive observable that's natural for that weight が異なる**。

##### 10-curve verification summary

`research/oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md` proper Iwaniec-Kowalski AFE library-grade で 10-curve test:

- Rank 0 (4 curves: 11a1, 14a1, 15a1, 17a1): K·t² ∈ [0.023, 0.030] ✓ within 5%
- Rank 1 (3 curves: 37a1, 43a1, 53a1): K·t² ∈ [1.021, 1.026] ✓ within 5%
- Rank 2 (1 curve clean: 389a1): K·t² = 2.047 ✓ within 5%
- Rank 2 (1 outlier: 433a1): K·t² = 0.121 ✗ (curve-specific Taylor coefficient anomaly $a_2 = +2$ unusual, $|c_2|$ small)
- Rank 3 (1 curve: 5077a1): K·t² = 3.093 ✓ within 5%

**9/10 curves match rank prediction within 5%**。Mean per rank class (excluding 433a1): monotone $0.027 < 1.024 < 2.047 < 3.093$。

##### "Genuine vs structural fit only" verdict の D_floor frame での再読み

Paper N3 §4 で Dirichlet L extension は "structural fit only" close、Paper N4 §3 で Hasse-Weil L extension は **genuine framework content transfer** confirmed。本 §6.8.2 は §6.8.1 Dirichlet L extension の **対照的 dual case** として記録。

| Layer | Dirichlet L (§6.8.1) | Hasse-Weil L (§6.8.2) |
|---|---|---|
| Path 2 instance class membership | ✅ weight-1 family member | ✅ weight-2 family member |
| Identity-level σ_min Fix | ✅ trivial (SC4) | ✅ s=1 |
| Structural invariance | ✅ multi-gap 12/12 | ✅ conductor 21/24 |
| **Predictive content** | ❌ structural fit only | ✅ **BSD analytic rank K·t²→r** |

**caveat (BSD claim 強度)**: 本 §6.8.2 は "BSD 予想を解いた" とは主張しない。$K_E(t) \cdot t^2 \to r$ は analytic rank の framework-side empirical detector であり、analytic rank と geometric rank の equality (BSD 予想本体) は assumed。

**Status**: candidate_v2 v8 (Paper N4 v0.2, 2026-04-26)。Hasse-Weil L weight-2 extension は **genuine framework content transfer の first instance**。

**Ref**:
- Paper N4 §3 (`papers/publication/nt/N4_hasseweil_stark_ja.md`)
- `research/oq_omega5_v15_hasse_weil_L_proper_afe_v2_v8.md` (主体, v2 v8 CONFIRMED genuine signal)
- `research/oq_omega5_v15_hasse_weil_L_central_curvature_v2_v7.md` (K_E(t) Taylor reviewer redirect)
- `c_theorems_master.md` "Hasse-Weil L extension scope" annex (本 §6.8.2 の summary)
- `nt_dedekind_artin_zeta.md §7.2` (modular L weight-2 entry)

---
