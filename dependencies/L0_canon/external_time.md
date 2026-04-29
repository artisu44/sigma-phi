---
axis: [A, D]
position: L0_external_time
static_dynamic: dynamic
connected_to:
  - A.L0_root
  - D.L0_root
  - L0_canon/finite_observation.md
  - L0_canon/identity_asymmetry.md
  - research/tau_internal_coordinate_v0.md
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-11
runtime_summary:
  what: 外部独立変数 t の辞書的定義。有限窓 W の parametrization 座標であり、観測対象 S の内部構造ではない。τ (内部走査座標) との構造的分離を原理として定式化
  when: 時間変数を含む議論 / t と τ の混同リスクがあるとき / L2 ドメインで「時間」が現れたとき
  provides: [t_definition, t_tau_separation_principle, t_domain_instances]
  consumes: [finite_observation.md, tau_internal_coordinate_v0.md]
  axis: [A, D]
  residual_types: [R-gauge]
  key_constants: []
  cross_refs:
    - finite_observation.md §1 (S, W, m triple)
    - finite_observation.md §2 (uncertainty principle, T limit)
    - finite_observation.md §4 (gauge invariance)
    - research/tau_internal_coordinate_v0.md §0-§1 (τ 三種分類)
    - c_spectral.md §1 (K(τ) spectral form factor)
    - fx_dictionary_v1.md (rolling window T)
    - physics_dictionary_v0.md (Schrodinger parameter)
  cost: small
  status: established
  one_screen: |
    §1 定義: t は有限窓 W の parametrization 座標 (外部独立変数)
    §2 t/τ 分離原理: t は W に属し τ は S に属す。混同は category error
    §3 t の 4 つの構造的役割: 窓位置・窓幅・順序・因果
    §4 L2 instances: FX=tick/calendar, QM=Schrodinger, crystal=measurement, thermo=relaxation, EEG=sampling, NT=なし
    §5 t が辞書に不在だった理由と帰結
---

# 外部時間 t (External Time)

**Level**: L0 (横断原理 / 補助)
**Dependencies**: finite_observation.md (S, W, m triple)
**Downstream**: 全 L2 domain で t を含む議論

---

## §1 定義

### 1.1 陳述

**外部時間 t** は、有限窓 W の parametrization に用いられる独立変数である。

finite_observation.md §1 の観測 triple (S, W, m) において、W は多くの場合 t によって index される:

    W = W(t)    (窓は t の関数)
    m(S|_{W(t)})  (観測値は t を通じて W に依存する)

t は **観測者が設定するパラメータ** であり、対象 S の内部構造ではない。

### 1.2 形式的位置

```
対象 S ──────── 内部構造 (τ, h, s, ...)
  │
  │ 有限窓 W(t)
  ↓
観測 m(S|_{W(t)}) ── 外部パラメータ (t)
```

t は射影演算 `S ↦ S|_W` の **引数** であり、S の性質ではない。これは A3 (gauge invariance) の語彙で言えば: t は **gauge 選択の一次元** である。

### 1.3 t が定数でない理由

static observation (t を固定した一回の測定) では t は定数として消えるため、辞書に明示的エントリが不要だった。t が非自明になるのは:

- 複数の観測を並べるとき (時系列)
- 窓を移動させるとき (rolling window)
- 因果順序が問題になるとき (before/after)

つまり t は **観測の列 {m_i} を組織する座標** である。

---

## §2 t/τ 分離原理

### 2.1 原理

> **t は W に属し、τ は S に属す。両者の混同は category error である。**

| | 外部時間 t | 内部座標 τ |
|---|---|---|
| **所属** | 窓 W の座標 | 対象 S の座標 |
| **設定者** | 観測者 | 構造 |
| **変域** | ℝ (物理時間) or 離散 (tick) | 定義域に依存 (ℝ_{>0}, [0,1), ℤ³, ...) |
| **gauge 性** | gauge 選択の一次元 | gauge 不変な内部パラメータ |
| **可変性** | 観測者が自由に動かせる | 構造が決める |

### 2.2 finite_observation.md との接続

finite_observation.md §2.2 の非可換極限:

    lim_{T→∞} lim_{B→∞} ≠ lim_{B→∞} lim_{T→∞}

ここで **T は t の窓幅** (= observation time) であり、τ ではない。T→∞ は「窓を無限に広げる」操作であって、「内部構造のパラメータを動かす」操作ではない。

この区別は A4 (non-commutative limits) の正確な読みに必要:
- T (外部) を先に飛ばす = 観測窓を先に無限化
- B (外部) を先に飛ばす = 分解能を先に無限化
- τ は S 側の話なので、この極限交換の **対象** であり **操作子** ではない

### 2.3 混同が起きやすい場面

1. **FX**: rolling window の長さ T (外部) と spectral form factor K(τ) の τ (内部) が同じ「時間的なもの」に見える
2. **QM**: Schrodinger 方程式の t (外部パラメータ) と系の internal frequency ω = E/ℏ (内部) が Fourier dual に見える
3. **Thermo**: 緩和時間 t_relax (外部測定) と平衡状態の β = 1/kT (内部パラメータ) の混同

いずれも §2.1 の表に戻れば区別できる: 「誰が設定するか」が判定基準。

---

## §3 t の 4 つの構造的役割

t が辞書の中で果たしうる役割は 4 つに分類される。

### 3.1 窓位置 (window position)

W(t) = [t - T/2, t + T/2] のように、t は窓の中心位置を指定する。窓をスライドさせることで同じ S の異なる部分が見える。

FX の rolling window、EEG の epoch 切り出しがこの型。

### 3.2 窓幅 (window duration)

T = t_end - t_start は窓の「大きさ」を決める。finite_observation.md §2 の T はこの意味。T が大きいほど多くの情報が見えるが、A2 (convergence) の速度で収束する。

### 3.3 順序 (ordering)

t₁ < t₂ は観測に順序を与える。これは S の性質ではなく **観測の列に対する構造**。時系列解析は本質的にこの順序を前提とする。

### 3.4 因果 (causality)

t が物理時間を表す場合、t₁ < t₂ は「t₁ の観測が t₂ の観測に影響しうる」という因果構造を暗示する。ΣΦ の辞書はこの因果構造を **現時点では取り扱わない** (§5 参照)。

---

## §4 L2 domain instances

### 4.1 FX

| 役割 | 具体例 |
|---|---|
| 窓位置 | rolling window の中心時刻 |
| 窓幅 | T = 1日、5日、20日 etc. |
| 順序 | return の時系列順 |
| 因果 | regime shift の前後関係 |

FX で t は **tick time** (市場 clock) と **calendar time** (壁時計) の二重性を持つ。市場が閉じている間 tick time は止まるが calendar time は進む。この二重性自体が gauge 選択 (A3) の instance。

### 4.2 QM (Schrodinger parameter)

| 役割 | 具体例 |
|---|---|
| 窓位置 | 測定時刻 |
| 窓幅 | 測定の時間分解能 Δt |
| 順序 | 測定の時間順 |
| 因果 | unitarity: U(t₂,t₁) の因果伝播 |

QM での t は Schrodinger 方程式 iℏ∂ψ/∂t = Hψ の独立変数。これは **S の内部パラメータに見える** が、ΣΦ の分類では「ψ(t) は窓 W(t) を通した観測の列」と読む。t は S (Hamilton 系) ではなく W (観測のタイムスタンプ) に属す。

ただし注意: QM の場合、t は力学方程式に入るため、純粋に「外部」とは言い切れない。これは open question として残す (§5.2)。

### 4.3 Crystal (measurement time)

| 役割 | 具体例 |
|---|---|
| 窓位置 | 回折実験の開始時刻 |
| 窓幅 | exposure time |
| 順序 | データ収集順 (通常は物理的に無関係) |
| 因果 | radiation damage の蓄積 |

結晶学では t はほぼ trivial。構造は time-independent (理想結晶は永遠に同じ)。t が非自明になるのは **radiation damage** (長時間照射で構造が変わる) や **time-resolved crystallography** のような特殊状況のみ。

### 4.4 Thermodynamics (relaxation time)

| 役割 | 具体例 |
|---|---|
| 窓位置 | 系の状態観測時刻 |
| 窓幅 | 平衡化に要する時間 |
| 順序 | 非平衡→平衡の方向性 |
| 因果 | 第二法則 (エントロピー増大) |

Thermo では t は **不可逆性の方向** を与える唯一の外部パラメータ。τ_relax (緩和時間) は S の内部特性時間であり、t とは区別される。

### 4.5 EEG (sampling clock)

| 役割 | 具体例 |
|---|---|
| 窓位置 | epoch の中心時刻 |
| 窓幅 | epoch 長 (e.g., 2 sec) |
| 順序 | trial 順 |
| 因果 | stimulus → response の時間方向 |

EEG では t は sampling clock (250 Hz etc.) によって離散化されている。連続 t の離散近似。

### 4.6 Number Theory

**t は存在しない。**

数論は本質的に time-independent。素数分布、L-function、ζ(s) のいずれも t に依存しない。これは数論が ΣΦ 辞書の中で **最も純粋に static な domain** であることの表現。

数論における「窓」は t ではなく **N** (上限) や **L** (conductor) によって parametrize される。これらは §3 の分類で言えば「窓幅」に対応するが、時間的な順序や因果構造を持たない。

---

## §5 t が辞書に不在だった理由と帰結

### 5.1 理由

辞書の出発点が **数論** (c-matrix, spectral form factor) と **結晶学** (回折パターン) であり、どちらも §4.6, §4.3 の通り t が trivial なドメイン。辞書の骨格が t-independent な問題から組み上がったため、t は自然に省略された。

FX、EEG、QM が接続された時点で t は非自明になっていたが、rolling window の T は finite_observation.md §2 に暗黙に含まれており、独立のエントリとして意識されなかった。

### 5.2 Open questions → research 移設 + 部分解決

OQ-ET-1 (QM の t は純粋に外部か), OQ-ET-2 (因果構造の scope) は **research/external_time_oq_v0.md** に移設。

**OQ-ET-3 (t/τ 分離の判定基準) → 部分解決、meta に昇格:**
- `dictionaries/meta/t_separation_diagnostics.md` — IAC + r_trend による STATIC/DYNAMIC/MIXED 判定
- Var_t/Var_τ ratio は判定量として **棄却** (Static GOE ratio=21 vs FX ratio=3.6 で判別力なし)
- 検証済: FX (DYNAMIC), Static GOE (STATIC), GOE→Poisson (DYNAMIC), Quench (DYNAMIC)
- 動的ドメインでは (S, W, m) triple を m(S(t)|_{W(t)}) に拡張が必要

### 5.3 帰結

t のエントリが存在することで:

1. **finite_observation.md の T が何であるか** が明示的になる (T = §3.2 の窓幅)
2. **τ との混同** が原理レベルで防がれる (§2)
3. **L2 ドメインごとの t の trivial/non-trivial 判定** が一覧できる (§4)
4. 将来 **時間依存の定理** を辞書に入れる際の受け皿ができる

---

*作成日: 2026-04-11*
*最終更新: 2026-04-11*
