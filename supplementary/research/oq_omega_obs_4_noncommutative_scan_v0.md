---
type: open_question_resolution_draft
subject: "OQ-Ω-Obs-4 — Non-commutative scan (quantum observable) extension of S15 / 3 Arrow / T-AAS"
status: Parts-split (Part 1 Arrow 3 quantum candidate_v0 retained; Part 2 ker_entangle / T-AAS quantum lift → OQ-Ω-Obs-1 quantum path minimal CONFIRMED 2026-04-22 + OQ-Ω-Obs-4a refined form ESTABLISHED 2026-04-23; Part 3 ker_backaction → OQ-Ω-Obs-4c OPEN; Part 4 BCH 2-scanner → OQ-Ω-Obs-4b OPEN)
date: 2026-04-22 (draft), 2026-04-23 (Part 2 4a ESTABLISHED update)
depends_on:
  - q_quantum_observation.md §6 (K_Q(τ) definition + coherence 感度なし note)
  - q_quantum_observation.md §9 S12/S15 接続 table (2026-04-11 partial resolution)
  - c_theorems_master.md S12-S16, T-AAS
  - Paper_D_Observation_Theory_ja.md §4.3 (Arrow 3), §4.6 (逆 Arrow), §5 (T-AAS)
  - Paper_D_Observation_Theory_ja.md §8.4 (量子の位置)
---

# OQ-Ω-Obs-4 v0 — 非可換 scan (量子 observable) への S15 拡張

## 0. TL;DR

Paper D v0.6 §8.2 OQ-Ω-Obs-4:
> 非可換 scan (量子 observable) への拡張 — K_Q(τ) = |Tr(ρ e^{iAτ})|² の S15 residence

**既存の partial resolution** (q_quantum_observation.md §9, 2026-04-11):
- S12 member: U(t) = e^{-iAt} は加法 Scan #5 (scanner = t, kernel = e^{-it})
- S15 residence: Scan = U(t)/K_Q(τ), Structural = dim(eigenspace)/spectral multiplicity,
  Information = S(ρ) = −Tr(ρ log ρ)
- Arrow 1 (quantum): A = Σλ_j P_j (spectral decomposition) → eigenvalue multiplicity
- Arrow 2 (quantum): S(ρ_max) = log 2 = S13 instance (qubit)

**Gap を特定**:
1. **Arrow 3 (quantum)**: Structural → Information の quantum version が§9 table
   にない (classical は H_0 = log|D|)
2. **3 Arrow 可換性 (quantum)**: §4.4 extreme-limit commutativity が非可換
   系で成立するか未検証
3. **T-AAS quantum lift**: ker_gauge / ker_topo の non-commutative 拡張が未記述
4. **Quantum-specific obstruction classes**: coherence / entanglement /
   measurement back-action が T-AAS に住むか新 class が必要か未決

**本 note の候補解**:
- (A) Arrow 3 (quantum) = **log rank(ρ) = S_0(ρ)** (quantum Hartley entropy)。
  α = 0 Rényi entropy = rank の対数。Arrow 3 classical log|D| の直接量子 lift。
- (B) 3 Arrow 可換性 (quantum): β → 0 極限で Tr(ρ e^{-βA}) → Tr(ρ) = 1 な
  ので Information = log 1 = 0 (trivial)、高温極限で Z(β→0) = dim H (全状態
  等重み) → log dim H = 量子 Hartley。classical と同 commutative 構造。
- (C) T-AAS quantum lift: 3 新 obstruction class candidate:
  - **ker_coherence** (ker_gauge-lift): 測定基底選択 gauge で除去可能な
    off-diagonal ρ、K_Q(τ) は感度なし (§6 note)
  - **ker_entangle** (ker_topo-lift): Schmidt rank > 1 構造、unitary gauge
    (local U(H₁)×U(H₂)) で除去不能 — **量子側 f_rational 候補**
  - **ker_backaction** (新 layer): 測定後 ρ → P_j ρ P_j/Tr(ρ P_j) の
    irreversible 状態変化、Arrow 構造の射方向性に固有で T-AAS 枠外

**Status**: **candidate_v0** (theoretical、§9 partial resolution への拡張)。

---

## 1. 既存 §9 partial resolution の確認と拡張

q_quantum_observation.md §9 S12/S15 接続 table (2026-04-11):

| S-ID | 本 note の評価 | Status |
|---|---|---|
| S12 quantum | U(t) = S12 加法 Scan member #5。Kernel e^{-it}、scanner = t | **CONFIRMED** (既存) |
| S15 Scan | U(t), K_Q(τ) | **CONFIRMED** (既存) |
| S15 Structural | dim(eigenspace), spectral multiplicity | **CONFIRMED** (既存) |
| S15 Information | S(ρ) = −Tr(ρ log ρ) von Neumann | **CONFIRMED** (既存) |
| Arrow 1 | A = Σλ_j P_j → 多重度 = Structural | **CONFIRMED** (既存) |
| Arrow 2 | S(ρ_max) = log 2 (S13 instance) | **CONFIRMED** (既存) |
| **Arrow 3** | — | **GAP (本 note で提案)** |
| **3 Arrow 可換性** | — | **GAP (本 note で提案)** |
| **T-AAS quantum lift** | — | **GAP (本 note で提案)** |

上 3 gap を埋めるのが OQ-Ω-Obs-4 の本体。

---

## 2. Arrow 3 (quantum): log rank の residence

### 2.1 Classical Arrow 3

Paper D §4.3: Arrow 3 = Structural → Information は Hartley entropy
`H_0(D) = log |D|`。D の cardinality の対数。

### 2.2 Quantum Arrow 3 candidate

Structural (quantum) = dim(eigenspace) / spectral multiplicity / rank(ρ) の
いずれか。Information (quantum) = S(ρ) 系列 (von Neumann、Rényi family)。

**候補**: Rényi α = 0 quantum entropy
```
S_0(ρ) := log rank(ρ) = log (dim supp(ρ))
```

- Classical の `H_0 = log|D|` の直接 quantum lift
- rank(ρ) は basis 選択 (gauge) 非依存 = **gauge-invariant Structural
  quantity**
- S(ρ) von Neumann = Rényi α=1 は Arrow 2 residence、S_0(ρ) = α=0 は
  Arrow 3 residence という **Rényi α 軸による Arrow 2/3 の分離**

### 2.3 Rényi family の Arrow 配置 (提案)

```
S_α(ρ) = (1/(1−α)) log Tr(ρ^α)

α = 0  →  S_0(ρ) = log rank(ρ)         ← Arrow 3 (Structural-derived, gauge-invariant)
α = 1  →  S(ρ) = −Tr(ρ log ρ)          ← Arrow 2 (Scan-derived, von Neumann)
α = 2  →  S_2(ρ) = −log Tr(ρ²)         ← purity-derived (quantum coherence)
α = ∞  →  S_∞(ρ) = −log λ_max(ρ)       ← min-entropy (single-shot capacity)
```

**Claim**: Rényi α は量子 Information 層内部の **"Arrow index"** として機能
する。α=0 は Arrow 3 canonical (Structural → Info via cardinality), α=1 は
Arrow 2 canonical (Scan → Info via log-exp duality)。α ∈ (0,1) は両 Arrow
の interpolation、α > 1 は量子 coherence に感度を持つ追加 Arrow candidate。

### 2.4 OQ-Ω-Obs-3 との cross-check

OQ-Ω-Obs-3 (本日先行 closure) の Arrow 3 e-fixed-point は classical で
`d(n) = log n / n` max at n = e。Quantum version は:
```
d_Q(rank) = log rank(ρ) / rank(ρ)   max at rank(ρ) = e (連続化)
```

rank(ρ) ∈ {1, 2, ..., dim H} は integer-valued なので、離散最大は rank = 3
(ternary qudit = optimal classical capacity, §3 後述)。OQ-Ω-Obs-3 の
universal parallel が quantum side で確認される。

---

## 3. 3 Arrow 可換性 (quantum)

### 3.1 Classical 可換性 (Paper D §4.4)

Extreme limit (β → 0) で:
```
Z(β → 0) = Σ_n 1 = |{states}|     ← Scan → counting
S(β → 0) = log |{states}| = H_0   ← Hartley
log Z = S = Structural counting
```

### 3.2 Quantum 可換性 candidate

Quantum partition function `Z_Q(β) = Tr(e^{-βA})`. 極限:
```
β → 0:  Z_Q(β) = Tr(I) = dim H          ← 全状態 uniformly weighted
log Z_Q(β → 0) = log dim H               ← Arrow 3 quantum (Hartley)
                                            S_0(ρ_max) = log dim H
```

ρ_max = I/dim H 下で:
- Arrow 1: A の spectral multiplicity → Σ g(λ) = dim H (全 eigenspace 和)
- Arrow 2: S(ρ_max) = log dim H (von Neumann at max mixing)
- Arrow 3: S_0(ρ_max) = log rank(ρ_max) = log dim H (full rank)

**3 Arrow 全て log dim H で coincide** — classical と同型の可換性。

### 3.3 Non-commutative 特殊化

ただし [A, B] ≠ 0 observable B が scanner に加わった場合、
```
K_Q^{(A,B)}(τ_1, τ_2) := |Tr(ρ e^{iAτ_1} e^{iBτ_2})|²
```
は $\tau_1 \tau_2$ 交換順序依存。**2-scanner quantum scan** は classical
の単一 scanner 可換性から逸脱する可能性。

OQ-Ω-Obs-4 sub-question: **BCH (Baker-Campbell-Hausdorff) 展開を通じた
3 Arrow 可換性の非可換補正** は open。

---

## 4. T-AAS quantum lift — 3 新 obstruction class

Paper D §5 T-AAS: ker(Arrow 1) = ker_gauge ⊕ ker_topo (classical,
ESTABLISHED 15/15)。quantum lift で以下 3 class candidate identified:

### 4.1 ker_coherence (ker_gauge-lift)

**定義**: 密度作用素 ρ の off-diagonal 要素 (量子コヒーレンス) が Arrow 1⁻¹
で Structural target 再構成に寄与しない成分。

**理由**: K_Q(τ) 展開 (§6 note):
```
Tr(ρ · e^{iAτ}) = Σ_j ⟨E_j|ρ|E_j⟩ · e^{iE_jτ}
                   ↑
                   A の固有基底での対角成分のみ
```
**K_Q は non-diagonal ρ_{jk} (j≠k) に感度を持たない**。coherence は
Arrow 1 ⟶ Arrow 1⁻¹ round trip で失われる = ker_coherence ≠ 0。

**Gauge 除去可能性**: 測定基底の選択 (unitary transformation U) で
coherence を diagonal 化可能 — ρ' = U†ρU。これは T-AAS の ker_gauge と
同じ性質 (gauge 変換で kernel = 0)。

**Classical との違い**: classical では観測量は必ず可換で基底共有、
coherence の概念不在。**ker_coherence は量子系で新たに出現する
ker_gauge instance**。

**f_torsion への寄与**: f_torsion(φ_quantum) ⊇ dim{ker_coherence}。

### 4.2 ker_entangle (ker_topo-lift)

**定義**: 合成系 H = H_1 ⊗ H_2 上で Schmidt rank r > 1 の状態 |ψ⟩ を
product state (rank 1) に還元できない構造。

**理由**: Schmidt 分解 |ψ⟩ = Σ_k √p_k |a_k⟩⊗|b_k⟩。rank r > 1 は
**local unitary gauge** U_1 ⊗ U_2 でも保存 — r は local unitary
invariant。よって **rank r > 1 は local gauge で除去不能な Structural
obstruction**。

**T-AAS 位置**: ker_topo-lift — filtration depth (local vs global 非自明
relation) に相当。

**量子 f_rational candidate**: f_rational(φ_quantum) ⊇ dim{ker_entangle}
= Schmidt rank r の quantum version。

**意義**: OQ-Ω-Obs-1 (f_rational > 0 instance 発見 = 第 3 の壁) の
**量子側 candidate instance**。Hodge 予想の純数学側 frontier に対し、
量子エンタングルメントは **具体計測可能 f_rational candidate** を提供
する。

**Caveat**: rank r を local unitary で潰せないのは Schmidt 不変量の
定理的事実。ただしこれが T-AAS の意味で f_rational > 0 を証明するには、
Arrow 1 の non-trivial non-surj が Schmidt rank に encode されることの
formal chain が必要 — 本 note の範囲外 (dictionary work outstanding)。

### 4.3 ker_backaction (新 layer candidate)

**定義**: 測定後の状態変化 ρ ↦ P_j ρ P_j / Tr(ρ P_j) の irreversibility。

**T-AAS 枠外の理由**:
- T-AAS は kernel の **直和分解** (ker_gauge ⊕ ker_topo) を claim
- ker_backaction は **process の arrow 方向性** (forward 観測 = 不可逆)
  に固有で、state-space kernel ではなく process-space kernel

**Paper D §4.6 逆 Arrow 枠との関係**:
- Arrow 1⁻¹ = Structural → Scan lifting は classical では section modulo
  ker。量子では測定後状態変化により lifting 自体が state を変化させる
- これは §4.6 系 4.3 (完璧な生成は原理的に不可能) の **強化 quantum
  version** — 古典では section は存在 (modulo ker), 量子では section
  自体が irreversible

**新 S15 層 candidate? 否**: Paper D §4.6 主張 4.2 (OQ-Ω-Obs-2 PARTIAL
CLOSURE) で「第 4 層不要」が closed。ker_backaction は第 4 層ではなく、
**逆 Arrow の非可逆化** (section の一意性喪失) として §4.6 枠内に住む。

**提案**: ker_backaction を T-AAS 枠外の "**Arrow reversibility
obstruction**" として別 class 化、classical では trivial (自動 reversible)、
quantum で non-trivial。

### 4.4 Quantum obstruction 3 class 統合表

| Class | T-AAS 位置 | Gauge removable? | Classical analogue | Quantum-specific? |
|---|---|---|---|---|
| **ker_coherence** | ker_gauge-lift | **YES** (unitary basis 変換) | なし (可換では無意味) | **YES 新 instance** |
| **ker_entangle** | ker_topo-lift | **NO** (local unitary 不変 Schmidt rank) | なし (Schmidt rank classical 不在) | **YES 新 instance, f_rational candidate** |
| **ker_backaction** | **枠外** (process-space) | N/A (state-space ではない) | なし | **YES fundamentally new** |

Paper E §4.6.3 の 5-class classical obstruction 表 (Attractor / Noise-
residue / Stochastic basin / filtration depth / ker_gauge classical) に
対し、quantum では上 3 class が追加 → **total 8 class candidate**。

---

## 5. Non-commutative S12 family extension

### 5.1 Classical S12 (6+1 members)

Paper D §3.2 table:
- K(τ), F(h), U(t) (加法 scan)
- ζ(s), Z(β), c(τ_cov) (乗法 scan)
- σ* bridge

### 5.2 Quantum S12 extension candidates

| Quantum member | Kernel | Scanner | 可換極限 |
|---|---|---|---|
| U(t) = e^{−iAt} | 非可換 e^{−it A} | t | ι_L (A diagonal 1-dim) |
| K_Q(τ) = \|Tr(ρ e^{iAτ})\|² | quantum form factor | τ | classical K(τ) (ρ diagonal) |
| Z_Q(β) = Tr(e^{−βA}) | 分配関数 | β | classical Z(β) (A scalar) |
| 2-scanner K_Q^{(A,B)}(τ_1, τ_2) | 非可換 BCH | (τ_1, τ_2) | classical product (A=B or [A,B]=0) |

**提案**: quantum S12 は classical 6+1 の拡張ではなく、**2-scanner
extension + 非可換補正項** が量子固有。

### 5.3 S13 / S14 quantum instance

- **S13 quantum**: S(ρ_max for qubit) = log 2 (既存 §9)
- **S14 quantum**: ?
  - 加法 parity (π): fermion sign e^{iπ} = −1 (Pauli exclusion)
  - 乗法 parity (ln 2): qubit S(ρ_max) = log 2
  - **Dual pair (π_fermion, ln 2_qubit) が S14 の量子版 parity scaffold**
    candidate
- **S15 quantum**: 3 Arrow residence 確立済 (§2.2, 2.3) — Rényi α による
  Arrow 2/3 分離を量子固有構造として追加

### 5.4 OQ-Ω-Obs-3 と OQ-Ω-Obs-4 の cross-consistency

本日先行 closure した OQ-Ω-Obs-3 (Arrow 3 e fixed point):
- Classical: d(n) = log n/n max at n = e (§2.4 cross-check)
- Quantum: d_Q(rank) = log rank(ρ) / rank(ρ) max at rank(ρ) = e
  (連続化、離散最大 at rank = 3 = ternary qudit optimal)

Quantum single-shot classical capacity: C_1(d) = log d。per-level density
= log d / d。d = 3 (ternary qudit) が optimal — classical coding theory
の balanced ternary optimality と同値。**OQ-Ω-Obs-3 の quantum instance
が OQ-Ω-Obs-4 に自然に embed**。

---

## 6. Status と ESTABLISHED 昇格条件

### 6.1 現 status (2026-04-23 update: parts-split post-resolution)

元 candidate_v0 を **4-split** し、各 part に status 個別確定:

1. ✅ **Part 1** — Arrow 3 quantum = log rank(ρ) = S_0(ρ) (§2)
   → **candidate_v0 retained** (条件 1 dictionary work outstanding)
2. ✅ **Part 2** — T-AAS quantum lift + ker_entangle = f_rational
   → **minimal form CONFIRMED** (OQ-Ω-Obs-1 quantum path,
   research/oq_omega_obs_1_ker_entangle_frational_path_v0.md, 2026-04-22)
   + **refined form ESTABLISHED** (OQ-Ω-Obs-4a, 6/6 gate closed
   2026-04-23, 4-class Stabilizer/Gaussian/Eff-sim/Bell-local +
   Theorem 4a.1 unified f_rational via class infidelity + axis-2 Fi/I
   root connection + 9/9 script gate PASS, research/oq_omega_obs_4a_
   refined_quantum_hodge_v0.md)
3. ⚠ **Part 3** — ker_backaction T-AAS 枠外 formal 化
   → **OQ-Ω-Obs-4c OPEN (LOW priority)**
4. ⚠ **Part 4** — 2-scanner BCH 非可換補正の Arrow 3 residence
   → **OQ-Ω-Obs-4b OPEN (LOW priority)**

### 6.2 昇格 gate (3 条件)

**条件 1 (Arrow 3 quantum formal closure)**: Rényi α=0 ↔ Arrow 3 mapping
を L1 dictionary に formal 記述 (q_quantum_observation.md §9 を §9.1 に
拡張 + Arrow 3 quantum row 追加)。**見積 ~30 min dictionary work**。

**条件 2 (ker_entangle が f_rational candidate であることの formal
proof)**: Schmidt rank r > 1 が Arrow 1 の non-surj にどう encode される
かの formal chain。state → K_Q(τ) → multiplicity の Arrow 1 経路で
Schmidt rank 情報が消える / 保存される条件の解析。**作業量大、1 session
では困難、別 OQ-Ω-Obs-4a として切り出し推奨**。

**条件 3 (3 Arrow 可換性の 2-scanner 非可換 extension)**: BCH 展開での
第 1 non-trivial 補正項 = (1/2)[A, B] の Arrow 3 residence。**作業量
中、1 session で骨格可、詳細検証に追加 session 要**。

### 6.3 最短 promotion path

条件 1 のみ closure → OQ-Ω-Obs-4 の **Part 1 (Arrow 3 quantum)** が
candidate → ESTABLISHED 昇格。残 Part 2-4 は OQ-Ω-Obs-4a/b/c として
分割:
- **OQ-Ω-Obs-4a**: ker_entangle = f_rational quantum instance の formal
  proof
- **OQ-Ω-Obs-4b**: 2-scanner 非可換 BCH 補正の Arrow 3 residence
- **OQ-Ω-Obs-4c**: ker_backaction の T-AAS 枠外 layer としての formal 化

この **4-split 戦略** が現実的。元 OQ-Ω-Obs-4 を Part 1 closure + 3 新
sub-OQ に分解することを推奨。

---

## 7. Downstream 効果

### 7.1 Paper D への反映 (v0.7 candidate)

- §4.3 に Arrow 3 quantum subsection (S_0(ρ) = log rank, Rényi α=0
  residence)
- §4.4 可換性に quantum version (ρ_max 極限 log dim H 同期)
- §4.6.3 obstruction class 表を **5 class → 8 class** (quantum 3 追加)
- §8.2 OQ-Ω-Obs-4 を **OPEN → Part 1 candidate_v0 + 3 sub-OQ 分割**
- §8.4 「量子の位置」subsection 拡張 (2 → 3 point: K_Q, c_s², 新 Arrow 3
  quantum = log rank)

### 7.2 L1 dictionary への反映

- `q_quantum_observation.md §9.1` 新設 (Arrow 3 quantum row)
- `c_arrow_obstruction.md §10` T-AAS quantum lift subsection (ker_coherence /
  ker_entangle / ker_backaction 3 class)
- `c_theorems_master.md` に **S15-Q** (Observable Trichotomy quantum
  specialization) 候補 entry

### 7.3 OQ-Ω-Obs-1 への波及

OQ-Ω-Obs-1 = f_rational > 0 instance 発見 (第 3 の壁) は本日 Paper E
3-phase cross-invariant 未発見。**ker_entangle (Schmidt rank r > 1) が
量子側の candidate f_rational instance**。OQ-Ω-Obs-1 の closure path は:
- 応用側 (Paper E 画像 AI): filtration depth candidate identified なし
- **基礎側 (量子 entanglement): Schmidt rank r > 1 が local unitary
  gauge-persistent Structural obstruction**

この量子経路は OQ-Ω-Obs-1 を応用側 frontier (Paper E Phase 4 NeRF 待ち)
に加えて **数理側 frontier (ker_entangle formal f_rational proof)** を
開く。

---

## 8. Timeline

| Stage | Elapsed |
|---|---|
| q_quantum_observation.md 読解 + §9 partial resolution 確認 | ~10 min |
| 4 sub-gap 特定 + candidate 作成 | ~20 min |
| 3 obstruction class 概念整理 + T-AAS 位置付け | ~15 min |
| OQ-Ω-Obs-3 との cross-consistency check | ~5 min |
| 本 note 起草 | ~30 min |
| **Total (theoretical closure v0)** | **~80 min** |

---

## 参考

- q_quantum_observation.md (K_Q 定義 §6, S12/S15 接続 §9)
- c_theorems_master.md S12-S16, T-AAS
- Paper_D_Observation_Theory_ja.md §4.3 (Arrow 3), §4.4 (可換性), §4.6
  (逆 Arrow), §5 (T-AAS), §8.4 (量子位置)
- research/oq_omega_obs_3_e_arrow3_v0.md (先行 closure 本日、quantum
  instance cross-check §5.4)
- research/bidirectional_duality_v0.md §5 (S15 Observable Trichotomy
  全体構造)
