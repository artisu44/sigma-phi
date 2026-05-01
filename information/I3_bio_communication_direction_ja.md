# Paper I3: Biological Communication Paradigm Selection ─ direction paper

**サブタイトル**: 生物の通信手段選択法則 (DNA / EEG / 神経系) ・物理制約 → I-series 5-paradigm 対応・既存研究 anchor + 3+ instance pre-registration discipline

**バージョン**: v0.0 (direction placeholder, 2026-04-27)
**状態**: DIRECTION PAPER — full formalization 前の方向性配置、既存研究 (Paper F DNA + EEG σ\* atlas) を anchor として bundle、3+ biological instance pre-registration accumulation 後 v0.1 起草移行。**本 paper は formal status claim でなく forward task plan**
**前提 (I-series)**: I1 v0.1 (5-anchor 情報量限界 theorem), I2 v0.1 (信号論 / 量子通信論 / 新規通信論 5 proposals + §11 dual evaluation)
**前提 (既存生物 anchor)**:
- `papers/Paper_F_DNA_ja.md` v0.6 (DNA × 観測理論, 13 organisms ESTABLISHED 2026-04-26)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` Entry 2 (EEG verified ESTABLISHED 2026-04-09)
- `dictionaries/L2_domain/{dna_dictionary, eeg_dictionary, connectome_dictionary}_v0.md`
**前提 (memory)**:
- `feedback_dual_evaluation_math_engineering.md` (math + engineering 直交 axis)
- `user_012_non_integer_scaffold.md` (0/1/2 scaffold framework lens)
**後続論文**: I3 v0.1 起草 (3+ instance pre-registration accumulation 後), I-series cumulative future

---

## §0 動機 (本 direction paper の position)

User insight (2026-04-27): "**生物は DNA / EEG / 神経系 と通信手段を選択している可能性、ニューロンや DNA の長さで選択** ─ 物理制約 (length, speed, error tolerance) が paradigm 選択を駆動する"。

**主張 (working hypothesis, 本 direction paper)**:

> 生物進化は I-series 5-anchor framework + I2 §11 dual evaluation (math + engineering trade-off) を **independently 自然選択** している:
> - DNA codon = 3 が S17 codebook argmax と一致 (`oq_omega_obs_3_info_density_check.py` 5/5 gate ESTABLISHED 2026-04-23) ─ **数学的 framework prediction が ~40 億年の進化で independent verify**
> - EEG 5 bands phase coherence = P1 σ\*-channel ESTABLISHED 動作 (Entry 2, `sheet_A_amplitude/sigma_star.md`) ─ **biological signal context で empirical 確認済**
> - Sweet spot (math gain + 実装軽量) を生物が **進化的に selection** ─ dual evaluation framework と converge

ただし本 direction paper は **full formal claim でない** ─ 現状 ESTABLISHED biological anchor 2 件 (DNA + EEG)、framework triangulation discipline (`meta/triangulation_methodology.md §6.1` 3-vertex 必須) で 3+ instance pre-registration が **structural claim 昇格条件**。本 paper は forward task plan として方向性配置。

### §0.1 Direction-axis position (biological anchor の A/B native split)

`user_observation_direction_axis` (ESTABLISHED 2026-05-01) の A/B observation direction axis において、本論 2 ESTABLISHED biological anchor は **異 direction native の 2 anchor** で I framework の "A + B co-resident" structure を biological context で再現:

| Anchor | Direction | Native | Biological context |
|---|---|---|---|
| **DNA codon = 3** (S17 codebook argmax instance) | **A-native** (discrete codebook integer argmax = 3) | Hartley density discrete optimum (整数 cardinality count) | Genetic code 進化的固定 (~40億年) |
| **EEG σ\* = √(2 ln 2)** (P1 σ\*-channel instance) | **B-native** (continuous Shannon entropy ½-bit threshold) | wrapped-Gaussian phase channel capacity | Brain phase coherence regulation (real-time) |

**Pattern observation**: 生物 2 anchor の direction split は I1 framework の Hartley A / Shannon B 1+4 split と integral structurally consistent — **biology が discrete (A-side) と continuous (B-side) の 2 paradigm を異なる scale (genetic code vs brain phase) で同時 deploy** している。これは "biology が I-series 5-paradigm framework を independent 自然選択" hypothesis (本論主張) を direction-axis layer で **2-anchor split as evidence** で補強。

**3+ instance pre-registration への direction-tag prediction**: 本論 §3.2 で挙げた pre-reg candidates (LFP / ribosome / 等) は direction-tag で advance prediction 可能 — 神経 oscillation = B-side native (continuous entropy regulation 候補)、ribosome codon-reading = A-side native (discrete codebook 候補)、これにより triangulation 3-vertex が direction-axis triangulation (A + B + bridge) として組まれれば最強の framework anchoring が達成される。

**Audit reference**: `project_graveyard_audit_complete_2026_05_01` (direction-axis Tier 0 reflection)、I1 §1.4 (Hartley A / Shannon B 1+4 split)。

---

## §1 既存生物 anchor (research already done)

### §1.1 DNA codon = 3 (S17 codebook argmax instance)

**Source**: `papers/Paper_F_DNA_ja.md` v0.6 (DNA × 観測理論, 2026-04-26 ESTABLISHED, 880 行)

**主結果 (本 direction paper relevance)**:
- **F1 (Analytical gauge absorber theorem)**: SNR(1/3) ≈ (N/9) · S / (0.693 · W), $\gamma = S/W$ organism-specific gauge-invariant codon selection index
- **F2 (10-organism formula universality)**: 10/10 organisms ±5% across 108× genome scale × 6 biology domains → **biology-neutral mathematical identity** candidate
- **F14-revised + F15 (γ classifier)**: $\gamma > 0.03 \to F1 = 0.949$ across 180k+ windows、AUC 0.78-0.996 across 10 genomes
- **DNA Round 1-5 5-round expansion**: 13 organisms, 11 synthetic, 180k+ sliding windows

**Codon = 3 と S17 codebook argmax = 3 の一致** (本 direction paper 主張 1):
- DNA codon = 3-letter window over 4-base alphabet (4³ = 64 codons → 20 amino acids + stop)
- S17 codebook integer argmax = 3 (qutrit info-density optimum, `c_arrow_bridge_constants.md §12.1`)
- **両者 independently arrived at 3** — Paper F は 1968 年 Crick/Nirenberg 解読、S17 は 2026-04-23 5/5 gate ESTABLISHED、~58 年隔たって converge
- **Hypothesis**: DNA evolved 3-letter codon window because it sits at S17 info-density optimum (5.5% Hartley density advantage vs 2-letter, equivalent to 4-letter but with manageable redundancy structure)

**Position in framework**:
- Paper F は Paper D §6.3.1 で **4 頂点目 candidate** (NT / 量子 / 定数 + DNA) として position 済
- I1/I2 framework lens で **P3 qutrit codebook biological instance** に lift 可能

### §1.2 EEG σ\* = √(2 ln 2) (P1 σ\*-channel instance)

**Source**: `dictionaries/transformation_atlas/sheet_A_amplitude/sigma_star.md` Entry 2 (A_sigma_star_eeg, ESTABLISHED 2026-04-09)

**主結果 (本 direction paper relevance)**:
- PhysioNet EEG dataset: 7 subjects (S001-S050), 64 channels, 160 Hz
- 5 bands: $\delta$ (0.5-4 Hz), $\theta$ (4-8), $\alpha$ (8-13), $\beta$ (13-30), $\gamma$ (30-100) × 3 conditions
- σ\* = √(2 ln 2) ≈ 1.1774 rad threshold で damage curve $D(\sigma) = 2f(1 - e^{-\sigma^2/2})$ verify
- **subject-band averaged std ≈ 0.0012**, 7/7 一致 → effective Gaussian approximation 高精度成立
- E_X residual main metric: subject-by-subject + band-by-band 詳細 (`research/eeg_real_validation.py`)

**EEG = P1 σ\*-phase channel biological instance** (本 direction paper 主張 2):
- I2 §4 P1 σ\*-phase channel proposal: $C_{\sigma_*} \approx 2.18$ bits/symbol, ~2x AWGN advantage at same SNR
- EEG empirical: 5 bands で σ\* threshold operative ─ phase coherence broadcast network
- **Hypothesis**: 脳の長距離 (cm-scale) 神経網は P1 σ\*-phase channel を選択 ─ 信号論 binary spike (axon scale, mm-scale) に対し phase coherence (network scale, cm-scale) で長距離 coordination + ~2x density advantage

### §1.3 既存 L2 dictionary (3 entries)

**Source**:
- `dna_dictionary_v0.md` (482 行): DNA codon analysis, Voss indicator power spectrum, m/p band identification, organism catalog
- `eeg_dictionary_v0.md` (203 行): EEG signal processing, 2/3 phase ratio, σ sweep
- `connectome_dictionary_v0.md` (210 行): network structure, b₁ Betti, $\rho_1$ rank-1 dominance

**Direction paper relevance**: 3 L2 dictionary は biology-domain L2 specialization、I-series I3 の biological framework lens 統合の base layer。

---

## §2 物理制約 → paradigm selection 仮説

### §2.1 Length-scale → speed → density 階層仮説

**仮説 2.1 (physical-constraint paradigm selection)**: 生物 communication paradigm 選択は以下の物理制約 chain で駆動される (working hypothesis, 本 direction paper):

| 物理 axis | 制約 | Paradigm requirement | I-series match |
|---|---|---|---|
| **Length** | μm (synapse) ↔ mm (axon) ↔ cm (cortex) ↔ m (sciatic) ↔ km (chemical signaling? 未検討) | scale 大 → coordination 必要 | 長 → P1 phase / 短 → Shannon binary |
| **Speed** | 1 ms (action potential) ↔ 100 ms (EEG burst) ↔ s (hormone) ↔ min-h (DNA replication) | speed 高 → simple encoding | 高速 → Shannon binary / 低速 → P3 qutrit-style |
| **Error tolerance** | 1 bit error tolerable (axon) ↔ 0 bit error allowed (DNA replication) | error 低 → redundancy 必要 | low-error → 量子 / DNA 風 redundancy / high-error → Shannon lossy |
| **Bandwidth** | nat 単位 / sec | bw 高 → density 必要 | high-bw → P3 qutrit / low-bw → Hartley scalar |

### §2.2 5-paradigm biological instance 推測

| 生物系 | 物理 character | I-series paradigm 推測 | Status |
|---|---|---|---|
| **DNA (codon)** | long storage (~Gb), low speed (~kb/s), 0-error tolerance, error-correcting redundancy | **P3 qutrit codebook lift** (codon = 3-letter window) | ESTABLISHED biological instance (Paper F F1, 2026-04-26) |
| **EEG (oscillation)** | long-range (cm-scale cortex), medium speed (10-100 Hz oscillation), phase-coherent broadcast, ~2x density via phase | **P1 σ\*-phase channel** | ESTABLISHED biological instance (sigma_star.md Entry 2, 2026-04-09) |
| **Action potential (axon)** | short-range (mm-cm), fast (10-100 m/s), binary spike, 1-bit error tolerable | **Shannon binary BSC/BEC** | classical, 信号論 base instance |
| **Synaptic transmission** | very short (μm), fast (~1 ms), continuous-graded vesicle release | **Shannon AWGN (Gaussian channel)** | classical |
| **Hormonal signaling (endocrine)** | very long-range (whole-body), very slow (sec-h), concentration-graded broadcast | **Shannon AWGN slow-channel** | classical |
| **Quorum sensing (bacteria)** | medium range (mm), medium speed (min), threshold-collective | **Hartley + threshold (P1 simplified)** | classical / framework hybrid |

**観察**: 生物が **5-paradigm spectrum** を physical constraint 階層に応じて selection している ─ 信号論 (Shannon binary / AWGN) は短距離・高速・error-tolerant、I-series novel (P1 / P3) は長距離・error-critical・density-limited。

### §2.3 Sweet spot biological selection

I2 §11 で identified した **framework sweet spot** (P1 + P3, math gain + 実装軽量) が **biological systems で進化的選択** されている観察:

| Sweet spot | Biological selection | 進化的圧力 |
|---|---|---|
| **P3 qutrit codebook** (5.5% Hartley density gain) | DNA codon = 3 (4-letter alphabet で 3-letter window) | 0-error tolerance + storage compactness の同時要求 |
| **P1 σ\*-phase channel** (~2x AWGN advantage at same SNR) | EEG 5-band phase coherence networks | long-range cortex coordination + bandwidth limit + biological energy budget |

**Hypothesis (本 direction paper, working)**: **生物進化が math advantage + 実装軽量 sweet spot を independently select している** ─ I-series framework の paradigm 選択法則と converge。これは framework が抽象的 mathematical structure でなく **physical world's structural commitment** を describe している evidence。

---

## §3 Forward task: 3+ instance pre-registration discipline

### §3.1 現状 anchor 数 vs triangulation discipline

**Triangulation discipline** (`meta/triangulation_methodology.md §6.1`): structural claim 昇格には **3-vertex 必須** ─ 2-vertex は scaffold/preparation 範囲、3+ で relational structure proper。

**現状 ESTABLISHED biological anchor**: 2 件 (DNA codon + EEG σ\*) → **2-vertex scaffold 段階**、structural claim 昇格不可。

### §3.2 3+ instance pre-registration candidates

I3 v0.1 起草前に必要な **3+ biological instance pre-registration**:

| Candidate biological instance | 物理 character | I-series paradigm hypothesis | Pre-registration要件 |
|---|---|---|---|
| **Axon spike train coding** | binary 0/1, fast | **Shannon BSC** | spike rate vs phase coding empirical separation, AUC measurement |
| **Hormonal concentration coding** | continuous, slow | **Shannon AWGN** | concentration-graded SNR vs Shannon-Hartley capacity 比較 |
| **Synaptic phase synchrony (LFP)** | network-level phase, medium speed | **Hybrid Shannon + P1** | LFP phase coherence vs σ\* threshold empirical |
| **Quorum sensing threshold** | bacterial AHL concentration | **P1 simplified (threshold-collective)** | Hill coefficient → σ\*-analog 検証 |
| **Bird song / vocal communication** | acoustic frequency-time | **Shannon + P1 hybrid** | song spectral analysis + phase coherence |
| **Plant hormonal signaling** | very slow + diffuse | **Shannon broadcast slow-channel** | concentration kinetics |
| **Ribosome translation rate** | DNA codon → amino acid speed | **P3 qutrit instance extension** | codon usage bias + speed correlation |

**Pre-registration discipline** (`feedback_two_step_synthetic_validation.md` 風):
- **Step 1**: pre-reg generator + family + nuisance + metric を formal 化
- **Step 2**: ≥80% detection across family before real biological data
- **Step 3**: biological data で empirical 検証 (AUC + structural identifier)

3+ instance ESTABLISHED 後、I3 v0.1 起草移行可能。

### §3.3 検証順序提案

**Priority 1 (最も近い anchor)**:
- **Synaptic phase synchrony (LFP)** ─ EEG (P1 ESTABLISHED) の neural-scale extension、既存 L2 connectome_dictionary + EEG framework から bridge 容易
- **Ribosome translation rate** ─ DNA codon (P3 ESTABLISHED) の biological extension、既存 Paper F framework から bridge 容易

**Priority 2 (新規 framework anchor)**:
- **Axon spike train coding** ─ Shannon binary biological instance、I2 §2 信号論 0/1/2 scaffold biological verification
- **Hormonal concentration coding** ─ Shannon AWGN biological instance、長 time-scale broadcast

**Priority 3 (extension 候補)**:
- Quorum sensing / bird song / plant hormonal — biological diversity extension

3 件 Priority 1 ESTABLISHED で **5 instance triangulation** (DNA + EEG + 2 priority 1) 達成、I3 v0.1 起草移行 trigger。

---

## §4 Forward task plan

### §4.1 短期 (next 1-3 sessions)

1. **既存 ESTABLISHED 2 anchor (DNA + EEG) の framework lens 再読み annex** を I2 §12 に追加 (軽量 1-page expansion、本 I3 v0.0 の core content を I2 に inject)
2. **Priority 1 candidates pre-registration** ─ synaptic phase synchrony + ribosome translation の formal pre-reg note 起草 (`research/oq_bio_priority1_v0.md` 候補)
3. **Memory cross-reference** ─ 本 direction paper を memory に project entry として保存

### §4.2 中期 (instance accumulation, ~2026-Q3 想定)

1. Priority 1 (LFP + ribosome) empirical 検証 → ESTABLISHED 化
2. **5-instance triangulation 達成** 後 I3 v0.1 full formal 起草
3. I-series I3 (Biological paradigm selection) として publication folder 移行

### §4.3 長期 (framework extension)

1. Priority 2 (axon + hormonal) extension で **5+ biological domains** triangulation
2. Plant / fungal / archaeal communication paradigms へ extend → cross-domain biological framework
3. **Convergent evolution evidence** ─ 異なる lineage が同 framework anchor を independently select している evidence accumulate (e.g., octopus neural + mammal cortex で同様 σ\* threshold)

---

## §5 帰結 (direction paper status)

### §5.1 Status summary

**現状 (2026-04-27)**:
- **2 biological anchor ESTABLISHED**: DNA codon (Paper F F1, 2026-04-26) + EEG σ\* (Entry 2, 2026-04-09)
- **Working hypothesis**: 生物進化が I-series sweet spot (math + 実装軽量) を independently select
- **Discipline**: 2-vertex scaffold 段階、structural claim 昇格不可、3+ instance pre-registration 必要
- **Forward**: Priority 1 (LFP + ribosome) で 5-instance triangulation 達成 → I3 v0.1 起草 trigger

### §5.2 既存研究との接続

| 既存研究 | 本 direction paper relevance |
|---|---|
| Paper F DNA × 観測理論 v0.6 (`papers/Paper_F_DNA_ja.md`) | DNA codon = 3 = S17 codebook argmax ESTABLISHED instance |
| sheet_A_amplitude/sigma_star.md Entry 2 | EEG σ\* = √(2 ln 2) phase channel ESTABLISHED instance |
| Paper D §6.3.1 (Paper F as 4 頂点目 candidate) | Paper F が 多領域 4-vertex triangulation の biological vertex |
| dna_dictionary_v0.md / eeg_dictionary_v0.md / connectome_dictionary_v0.md | L2 biological domain entries (3 件) |
| `feedback_dual_evaluation_math_engineering.md` | Sweet spot (math + 実装軽量) が biological selection と converge という 主張 root |
| `user_012_non_integer_scaffold.md` | 0/1/2 scaffold lens (信号論 0/1 base + 3+ relational structure proper) と biological paradigm selection の structural alignment |

### §5.3 本 paper の position

**本 paper は formal status claim でなく forward task plan**:
- I-series I3 v0.0 placeholder として publication/information/ folder に配置
- 既存研究 anchor 2 件 + 5-paradigm biological instance hypothesis + 3+ instance pre-registration discipline + forward task plan を bundle
- **次 session 以降の biological extension work の base**

I3 v0.1 起草 trigger: Priority 1 candidates (LFP + ribosome) ESTABLISHED → 5-instance triangulation 達成。

---

## 変更履歴

- **v0.0 (2026-04-27, direction paper)**: initial direction paper placeholder。User insight (2026-04-27) "生物が DNA / EEG / 神経系 と通信手段を選択している可能性、ニューロンや DNA の長さで selection" を direction paper として配置。既存研究 (Paper F DNA + EEG σ\* atlas) を biological anchor 2 件として bundle、5-paradigm biological instance hypothesis を working level で記録、3+ instance pre-registration discipline (`meta/triangulation_methodology.md §6.1` 3-vertex 必須) を discipline として明示、Priority 1-3 candidates listing で forward task plan 確立。Full formalization (v0.1) は 5-instance triangulation 達成後に trigger。

---

## 参考文献 (内部)

**I-series predecessors**:
- `papers/publication/information/I1_information_theory_framework_ja.md` (v0.1, framework header)
- `papers/publication/information/I2_communication_theory_ja.md` (v0.1, communication theory + 5 proposals + §11 dual evaluation)

**既存 biological research (本 direction paper anchor)**:
- `papers/Paper_F_DNA_ja.md` (v0.6, DNA × 観測理論, 2026-04-26 ESTABLISHED, 16 main results)
- `dictionaries/transformation_atlas/sheet_A_amplitude/sigma_star.md` Entry 2 (A_sigma_star_eeg, ESTABLISHED 2026-04-09)
- `dictionaries/L2_domain/{dna_dictionary, eeg_dictionary, connectome_dictionary}_v0.md`
- `research/eeg_real_validation.py` (EEG empirical script)

**Memory dependencies**:
- `feedback_dual_evaluation_math_engineering.md` (math + engineering 直交 axis, sweet spot 概念)
- `user_012_non_integer_scaffold.md` (0/1/2 scaffold framework lens)
- `feedback_two_step_synthetic_validation.md` (pre-registration discipline)

**Framework dependencies**:
- I1 §6 5-anchor mathematical info limit theorem
- I2 §11 dual evaluation framework + paradigm sweet spot
- `c_arrow_bridge_constants.md §12.1` (S17 codebook argmax = 3, ESTABLISHED 2026-04-23 5/5 gate)
- `c_arrow_bridge_constants.md §12.2` (5-stage ln 2 chain, ESTABLISHED 2026-04-27)
- `meta/triangulation_methodology.md §6.1` (3-vertex 必須 discipline)

**Forward references**:
- I3 v0.1 起草 (Priority 1 candidates ESTABLISHED 後)
- `research/oq_bio_priority1_v0.md` (LFP + ribosome pre-reg note 候補, 未起草)
- I-series cumulative future (4th framework header / 多域 communication etc.)
