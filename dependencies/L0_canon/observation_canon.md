---
axis: [A, B]
position: L0_canon_root
static_dynamic: both
connected_to:
  - L0_canon/finite_observation.md
  - L0_canon/identity_asymmetry.md
  - atlas/L0_core_proposition.md
  - atlas/classification_axes.md
arrow_status:
  upstream: none
  downstream: done
updated: 2026-04-23
runtime_summary:
  what: 4-pillar Stack の入口。1ページに圧縮された公理集
  when: 公理を確認したい / 全体図が必要なとき (常に最初に読む候補)
  provides: [stack_entry, axiom_overview, atlas_bridge_summary, dictionary_directions]
  consumes: [finite_observation.md, identity_asymmetry.md]
  axis: [A, B]
  residual_types: []
  cost: small
  status: established
  one_screen: |
    Stack 4-pillar:  Canon (why) → Atlas (how) → Dictionary (what here) → Ω (sister)
    観測 = (S, W, m). 公理 A0–A6 + A0-ID. Born chain: A0a + A0b + A0c → frame function → Tr(ρE).
    Atlas grammar: f_n = n∘G or G∘n, φ = (φ_absorbed, φ_phase), comp_X, Δ = (Δ_abs, Δ_res), E_X.
    Dictionary 5 軸: A 振幅 / B スケール / C 周期 / D 測度 / E 位相 (反転).
    Residual 5 型: R-info / R-env / R-comp / R-topo / R-gauge.
    Ω は姉妹理論 (定数 origination), Canon の下位ではない.
---

# Observation Canon

**Level**: L0 root entry-point (1-page canon)
**Role**: Stack 全体の入口。詳細本文は `finite_observation.md`、定数論姉妹は `omega/Paper_Omega_Origination.md`。

---

## §0 一文 thesis

> **観測者は有限で、対象は無限。観測は有限窓を通した射影であり、窓が見える代数を決める。**

全ての L1 定理、L2 測定、L3 対応、L4 誤差は最終的にこの一文に帰着する。

---

## §1 三つの primitive

観測は triple `(S, W, m)`:

| 記号 | 意味 | 例 |
|---|---|---|
| **S** | 無限構造 (object) | 素数分布、結晶格子、固有値スペクトル、確率密度 |
| **W** | 有限窓 (window) | Z_L、hkl grid、rolling T、有限次元 H |
| **m** | 測定 (measurement) | counting、回折、spectral statistics、Born |

観測値 `m(S|_W)` は S と W の両方に依存する。理論は `m(S)` を語り、実験は `m(S|_W)` を測る。差 `m(S) − m(S|_W)` が **finite observation error**。

---

## §2 五つの axioms

| ID | 名称 | 一行 |
|---|---|---|
| **A0** | Finite observation | 全ての観測は有限窓を通る射影。窓が visible algebra を決める。(A0a 有限性 / A0b 部分性 / A0c 多窓整合性) |
| **A1** | Structured error | 有限-無限間のギャップは noise ではなく構造。`error = arithmetic + projection + noise` に分解される |
| **A2** | Convergence as observable | 収束率そのものが観測量。alpha が小さい = 深い構造が遅く支配する |
| **A3** | Gauge invariance / dependence | 振幅は gauge 不変、位相は gauge 依存。混同は category error |
| **A4** | Non-commutative limits | `lim_T lim_B ≠ lim_B lim_T`。canonical な「無限極限」は存在しない、path 依存 |
| **A5** | Saturation | 有限 constraint 系では power law は sigmoid の局所近似。サチる先 A が有限-conductor 観測の真の予測値。scope: 有限 constraint count に限定 (scale-free 系では非適用) |
| **A6** | Path dependence of saturation | A への接近は path 依存。`A4` の系として、どの極限列を取るかで A 自身も変わりうる |
| **A7** | Scanner hierarchy | Scan observable は scanner 変数 σ を持つパラメトリック族 `O(σ; D, f) = Σ_d f(d) exp(a(σ)·b(d))`。(D, f) = Arrow 1 の input spec、σ = Arrow 2/3 が evaluate する軸。S15 partition の前提 (2026-04-23) |

詳細: `finite_observation.md` §1–§7。

### L0 v2 — axis-2 (Finite / Infinite) framework (2026-04-23)

A0 を 2-axis (axis-1 D/C × axis-2 Fi/I) lens で再定式化し、観測 = axis-2 **I → Fi traversal** の片方向性として明示する。観測者は constitutively Fi 側に住み、Fi → I lifting の不在が kernel を生む。

- (a') 完全観測 = Fi → I 到達不能 (≡ A0)
- (b') Arrow が axis-2 Fi/I 境界を跨ぐとき kernel 発生
- (c') T-AAS kernel は axis-2 で 3 分解 — Fi-artifact (ker_gauge) / I-residue (ker_topo) / Fi→Fi irreversibility (ker_backaction)
- (d') 観測理論 = "axis-2 Fi/I 境界の分類学" (新 content)

L0 v1 ⊂ L0 v2 (conservative extension; v1 全 statement は v2 から復元可能、(d') のみ v2 新規)。

**1 行 thesis**: ΣΦ 観測理論 = axis-2 Fi/I 境界の分類学。

詳細: `finite_observation.md` §8。

---

## §3 補助原理 (adjunct principles)

### A0-ID — Identity asymmetry

> 群・指標・Fourier の **恒等元 (1, χ₀, k=0, 自明表現)** は他の元と対称に扱えない。「+1」や定数オフセットは bug ではなく feature。

`identity_asymmetry.md`。これは A3 (gauge) より深い層 — 全 gauge で不変な唯一の存在。

### t — External time (window parametrization)

> 外部時間 t は有限窓 W の parametrization 座標。t は W に属し、τ は S に属す。混同は category error。

`external_time.md`。finite_observation.md §2 の T (窓幅) が何であるかを明示化し、τ (内部走査座標, research/tau_internal_coordinate_v0.md) との分離を原理として定式化。各 L2 ドメインでの t の trivial/non-trivial 判定を含む。

### Observation cost (Landauer) — derived, not axiom

観測には熱的コストが伴う (Landauer)。現時点で L0 公理には入れず、QTD/many_body の派生として保持。将来 L0 に格上げ可能性は open question。

### Pre-constant scaffolds 0,1,−1,2,3

定数発生以前の足場 (`identity_asymmetry.md` §5.3)。`不在 → 原点 → 向き → 分岐 → 構造` の順序で、定数はこの足場の上に初めて発生する。Ω 起源論 (`omega/Paper_Omega_Origination.md`) と直接接続。

---

## §4 Atlas grammar への橋

Canon は **why** を与える。Atlas は **how** を与える。Dictionary は **what it means here** を与える。

Atlas (`transformation_atlas/L0_core_proposition.md`) は次の symbolic vocabulary を canonical syntax として導入する:

| 記号 | 役割 | Canon との対応 |
|---|---|---|
| `n` | 正規化 (∈ N_X) | A3 の gauge choice |
| `G_X` | 観測射影 (canonical truncation) | A0 の有限窓 W |
| `S_X` | 再構成 (gauge を含む section) | A2 の漸近補完 |
| `f_n` | 正規化観測量 = `n ∘ G` または `G ∘ n` | m(S|_W) |
| `φ_absorbed` | n に吸収された因子 | gauge-fixed 部分 |
| `φ_phase` | N_X-quotient で消えない残差自由度 | A3 の位相側 |
| `comp_X` | `S(G(X)) → X` の比較射 | finite observation error の出口 |
| `Δ = (Δ_absorbed, Δ_residual)` | ズレの二層分解 | A1 の構造誤差 |
| `E_X` | sheet 固有 error functional | A1 の measurable witness |

Atlas は **公理ではなく canonical syntax**。L0 (Canon) と L2 (Dictionary) を繋ぐ grammar。詳細: `atlas/classification_axes.md` の 5 軸 (A 振幅 / B スケール / C 周期 / D 測度 / E 位相)。

---

## §5 Dictionary directions

各 L1/L2 辞書は Atlas grammar の **意味論** を担う。「`φ_phase` がこの分野で何という名で現れるか」を受ける層。

| 辞書 | 窓の type | φ_phase の現れ方 |
|---|---|---|
| `L1/information_theory` | information window | `H(Y\|X)`, `R(D)`, `I_F`, persistence |
| `L1/open_quantum_systems` | environmental window | mixedness, decoherence, pointer basis |
| `L1/quantum_statistical_mechanics` | thermal window `(W, W_β)` | thermal mixing, KMS state |
| `L1/many_body_quantum` | compositional window | quasiparticle weight `Z`, correlation residue |
| `L1/spectral` | spectral window | unfolding, c_W(K), edge corrections |
| `L1/phase_complex` | phase window | argument structure, gauge orbit |
| `L2/crystal_dictionary` | reciprocal window (h_max) | arg F(hkl), 位相問題 |
| `L2/fx_dictionary` | rolling window (T, n_ccy) | eigenvector phase, c_s² |
| (候補) `L1/topological_invariants` | global/topological window | Berry phase, winding number |

各辞書は Atlas の `φ_phase` を **新発明せず受ける**。L1 の `c_hidden_degrees_of_freedom.md` がこの residual freedom の **型分類** を与える橋渡し層。

---

## §6 Side branch: Origination (Ω)

`omega/Paper_Omega_Origination.md` は Canon の下位ではなく **姉妹理論**。

- Canon: 「有限観測がどう見えるか」を与える
- Ω: 「定数がどの gauge で intrinsic か」を分類する (origination matrix)

両者は corollary `A0+A3` (`finite_observation.md` §8) で接続するが、merge しない。Ω は **定数論版 finite observation** であり、observation grammar の言語ではなく gauge signature の言語。

---

## §7 Stack 全体図

```
Layer 0 (Canon)        この文書 + finite_observation + identity_asymmetry
        │
        │ provides: why
        ▼
Layer 1 (Atlas)        transformation_atlas/  ← canonical syntax
        │              L0_core_proposition + classification_axes + sheet_A〜E
        │ provides: how
        ▼
Layer 2 (Dictionary)   dictionaries/L1〜L4    ← semantic content
        │              + meta/, + L1/c_hidden_degrees_of_freedom.md (型付け橋)
        │ provides: what it means here
        ▼
       L2 domains      crystal, fx, chemistry, eeg, connectome, ...

Side branch (Ω)        omega/Paper_Omega_Origination.md
                       constant origination / gauge signature
                       sister theory, not subordinate
```

**読み順**: この `observation_canon.md` → 興味のある Layer → 必要に応じ `finite_observation.md` の該当 §へ。

---

*作成日: 2026-04-09*
*最終更新: 2026-04-09*
