---
axis: [A, E]
position: L1_gauge_nonabelian
static_dynamic: both
connected_to:
  - L1_mathematical/c_phase_complex.md        # §4 structural root, ι_L/χ dual (abelian case)
  - L1_mathematical/q_quantum_observation.md   # [A,B] commutator → [D_μ,D_ν]=F_{μν}
  - L1_mathematical/q_action_principles.md     # §3 path integral, §4 Wick rotation (upstream for §3 Z=∫DA)
  - L1_mathematical/c_hidden_degrees_of_freedom.md  # R-gauge: FP, Gribov, BRST
  - L1_mathematical/q_many_body_quantum.md     # SSB/gap/gapless, quasiparticle mass
  - L1_mathematical/q_quantum_statistical_mechanics.md  # KMS, Z(β), chemical potential = U(1)
  - L1_mathematical/c_spectral.md              # §8 class number formula 6-gauge
  - L1_mathematical/c_arrow_obstruction.md     # §6 第一類障害 instanton, §7 domain symmetry constraint
  - L0_canon/finite_observation.md           # A0 (S,W,m), A3 gauge invariance
  - research/hodge_conjecture_decomposition_v0.md  # §21-23 YM decomposition
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-11
runtime_summary:
  what: L1量子辞書の非可換完成。U(1)→SU(N) 拡張で gauge/mass gap/instanton/閉じ込めを統合記述
  when: gauge 場の理論、mass gap、閉じ込め、instanton、BRST、非可換構造の問い
  provides: [nonabelian_gauge, field_strength, covariant_derivative, mass_gap, confinement, instanton, wilson_loop, asymptotic_freedom, BRST_cohomology, six_layer_millennium]
  consumes: [c_phase_complex.md §2-4, q_quantum_observation.md §2-4, c_hidden_degrees_of_freedom.md R-gauge, q_many_body_quantum.md §5-6, c_spectral.md §8]
  axis: [A, E]
  residual_types: [R-gauge, R-topo]
  cost: large
  status: established
  one_screen: |
    §1 非可換 gauge 群 G (SU(N)): phase_complex ι_L の SU(N) 拡張。可換 → 非可換で [D,D]=F 出現
    §2 接続と曲率: A_μ = gauge 接続 (L-2 context)、F_{μν} = [D_μ,D_ν] (場の強度 = 非可換性の測定)
    §3 作用と経路積分: S[A] = ∫Tr(F∧*F)、Z = ∫DA e^{-S}。S7 の場の理論版 (§8)
    §4 量子化と R-gauge: FP ghost、Gribov、BRST — c_hidden_degrees_of_freedom.md R-gauge の具体化
    §5 mass gap と S16: gap = S16 tier ≥ 2 の帰結候補。D_floor spectral 版。SSB は逆 (gap→gapless)
    §6 instanton と R-topo: π₃(G)=ℤ、topological charge n、θ-vacuum。第一類障害の物理版
    §7 閉じ込めと Arrow 1: gauge-singlet のみ観測可能 = Arrow 1 の像が gauge-inv sector に制限
    §8 漸近自由性と繰り込み: β<0 → UV で自由。第三類障害が制御可能。running coupling = τ-scan 的
---

# Gauge 場の理論 — L1 量子辞書の非可換完成

**Level**: L1 (pure mathematics + mathematical physics, domain-independent)
**Role**: 既存 L1 量子辞書チェーン (quantum_observation → OQS → QSM → QTD → many_body)
の各ファイルに分散していた gauge 概念を、**非可換化** で統合する

---

## §0 位置づけ — 何がこのファイルの仕事か

L1 量子辞書は Yang-Mills を **名前で呼ばずに構造で持っている**:

| 既存 L1 entry | 持っている構造 | 非可換化で得られるもの |
|---|---|---|
| phase_complex §2-4 | ι_L: ℤ/Lℤ → S¹ ⊂ U(1) | SU(N) への拡張: 位相 → 行列値位相 |
| quantum_observation §2 | [A,B] 交換子 | [D_μ, D_ν] = F_{μν} (場の強度) |
| hidden_degrees_of_freedom §2.5 | R-gauge: FP, Gribov, BRST | 具体化: 非可換 gauge での量子化 |
| many_body_quantum §5-6 | SSB, gap/gapless, 準粒子 | 逆: 閉じ込め = gap の非摂動的起源 |
| spectral §8 | 6-gauge class number formula | YM partition function の因子分解 |
| QSM §3-4 | KMS, Z(β), μ = U(1) | 有限温度 YM, deconfinement 転移 |

**本ファイルは新概念の導入ではなく、既存概念の非可換完成**。

---

## §1 非可換 gauge 群 — U(1) → SU(N)

### §1.1 可換 (abelian) case の復習

phase_complex §2: ι_L: ℤ/Lℤ → S¹ ⊂ U(1)。
加法構造を乗法構造に変換。全ての元が可換: g₁g₂ = g₂g₁。

結果: 全ての表現が 1 次元。指標 χ: G → S¹ で完全に記述。
gauge 接続 A_μ ∈ u(1) ≅ iℝ はスカラー値。

### §1.2 非可換 (non-abelian) への拡張

G = SU(N) (N ≥ 2): N×N ユニタリ行列で det = 1。
Lie 代数 su(N) は traceless 反エルミート行列の空間。dim su(N) = N²−1。

**可換 → 非可換で何が変わるか**:

| 性質 | U(1) | SU(N), N ≥ 2 |
|---|---|---|
| 表現 | 全て 1 次元 | 非自明な高次元表現あり |
| 接続 A_μ | スカラー値 (iℝ) | 行列値 (su(N)) |
| 場の強度 F_{μν} | ∂_μA_ν − ∂_νA_μ | ∂_μA_ν − ∂_νA_μ + [A_μ, A_ν] |
| 交換子項 | 0 (可換) | [A_μ, A_ν] ≠ 0 → **自己相互作用** |
| gauge 変換 | A → A + dα (加法) | A → gAg⁻¹ + g dg⁻¹ (共役) |

**ΣΦ 読み**: phase_complex §4 の ι_L/χ dual は U(1) の場合。
SU(N) では双対構造が **非可換化** され、指標の直交性が
表現論の直交性 (Schur の補題) に置き換わる。

### §1.3 ΣΦ 公理との対応

| ΣΦ 公理 | U(1) gauge | SU(N) gauge |
|---|---|---|
| A0 (有限窓) | 有限 L の離散化 ℤ/Lℤ | 格子 gauge (Wilson の離散化) |
| A3 (gauge 不変) | 位相回転で observable 不変 | 非可換回転で observable 不変 |
| A0-ID (恒等元非対称) | χ₀ (自明指標) 分離 | 自明表現 (singlet) 分離 |

**singlet 分離 = A0-ID の非可換版**: gauge-singlet (= 自明表現) だけが
物理的 observable → 閉じ込め (§7) の代数的根拠。

---

## §2 接続と曲率 — (S, W, m) の場の理論版

### §2.1 共変微分 D_μ

D_μ = ∂_μ + A_μ

A_μ(x) ∈ su(N): gauge 接続 (connection 1-form)。
ΣΦ 配置: A_μ は **L-2 context gauge** (R8)。
場の「窓依存性」を記述する — 異なる gauge 選択 = 異なる窓。

### §2.2 場の強度 F_{μν}

F_{μν} = [D_μ, D_ν] = ∂_μA_ν − ∂_νA_μ + [A_μ, A_ν]

quantum_observation §2 の [A,B] 交換子の場の理論版。

| quantum_observation | gauge_field_theory |
|---|---|
| [A, B] (有限次元演算子) | [D_μ, D_ν] (無限次元場) |
| 非可換性の測定 | 曲率の測定 |
| Heisenberg 不確定性 | gauge 場の力 |

**ΣΦ 読み**: F_{μν} は「gauge 接続 A の非可換性から生じる残差」。
R-gauge 残差の **測定可能な部分** = F_{μν}。
gauge 不変な observable は F の関数のみ (Tr F², Tr F⁴, ...)。

### §2.3 曲率 = 有限窓のコスト

∮_C A ≠ 0 (Wilson loop) ⟺ 曲率が存在する。

ΣΦ 有限観測誤差の言語:
- 曲率 = 0: 窓の選び方に依らない (平坦接続)
- 曲率 ≠ 0: 窓の選び方で結果が変わる → gauge artifact の実体

---

## §3 作用と経路積分

### §3.1 Yang-Mills 作用

S_YM[A] = (1/2g²) ∫_{M} Tr(F_{μν} F^{μν}) d⁴x

g = coupling constant (gauge interaction の強さ)。

ΣΦ 読み: S_YM は「gauge 曲率のエネルギー」。
曲率 = 0 が真空 (最小作用)、曲率 ≠ 0 が励起。

### §3.2 経路積分 Z — S7 の場の理論版

Z = ∫ DA exp(−S_YM[A])

(S, W, m) 同定:
- S = A/G (gauge orbit の商空間、無限次元)
- W = 格子 Λ (離散化)、UV cutoff
- m = ⟨O⟩ = (1/Z) ∫ DA O[A] exp(−S)

### §3.3 S7 との因子対応 (speculative, OQ-YM-3)

spectral §8 の class number formula:
Res_{s=1} ζ_K(s) = (2^{r₁}(2π)^{r₂} · h_K · R_K) / (w_K · √|d_K|)

YM partition function の因子構造 (heuristic):

| S7 因子 | YM 因子 | gauge 署名 | 根拠 |
|---|---|---|---|
| (2π)^{r₂} | 1-loop det (周期的) | {geom, cont} | Gaussian 積分の 2π 因子 |
| R_K | saddle point 寄与 (instanton action) | {anal} | 準古典展開 e^{-8π²/g²} |
| h_K | instanton sector 数 (π₃(G) = ℤ) | {char} | topological charge n ∈ ℤ |
| √|d_K| | Faddeev-Popov det (ghost) | {mult} | gauge fixing の Jacobian |
| w_K | center symmetry ℤ_N の位数 | {addZ} | residual discrete gauge |

**status**: speculation。数値検証なし。OQ-YM-3 として保留。

---

## §4 量子化と R-gauge — FP / Gribov / BRST の具体化

hidden_degrees_of_freedom §2.5 が **R-gauge 型** として名前を挙げた概念を
ここで具体化する。

### §4.1 Faddeev-Popov (FP) ghost

gauge 固定 f(A) = 0 のもとで:
Z = ∫ DA · det(δf/δω) · δ(f(A)) · exp(−S_YM)

det(δf/δω) = FP determinant。ghost 場 c, c̄ (Grassmann) として導入:
Z = ∫ DA Dc Dc̄ exp(−S_YM − S_ghost)

ΣΦ 読み: FP determinant = **gauge orbit の体積因子の補正**。
観測 m(S|_W) が窓 W (= gauge 条件 f) に依存しないようにする正規化。
S7 の √|d_K| (判別式) が gauge Jacobian として再出現。

### §4.2 Gribov 問題

gauge 条件 f(A) = 0 が A/G 上で一意でない (Gribov copy の存在)。
A/G が非自明な topology を持つため、大域的な gauge slice が存在しない。

ΣΦ 読み: R-gauge 残差の中で **最も深い障害**。
- Tier √ の gauge 版: 離散的 (copy 数) な障害が連続的 gauge 条件で消えない
- Gribov horizon = gauge 壁 (§15.2) の場の理論版

### §4.3 BRST cohomology

BRST 変換 s: sA = Dc, sc = −c², sc̄ = B (Nakanishi-Lautrup field)。
s² = 0 → cohomology H(s) = ker s / im s。

**物理的状態 = BRST cohomology のクラス**。

ΣΦ 読み:
- s² = 0 は **exact sequence** 構造 (conductor §6.9 の Brauer 分解と同種)
- H(s) = 「gauge artifact を完全に除いた物理的内容」
- Arrow 1 の像 = gauge-invariant sector = H(s)

---

## §5 Mass gap と S16 — spectral D_floor

### §5.1 mass gap の定義

Hamiltonian H のスペクトル: H|0⟩ = 0, H|1⟩ = Δ|1⟩, Δ > 0。

```
E
↑
│ ─── Δ ───  第一励起状態
│
│ ─── 0 ───  真空
```

ミレニアム問題: Δ > 0 を示せ (SU(N) pure gauge, ℝ⁴)。

### §5.2 S16 Fejér Absorption との接続

S16 tier 分類:
1. 完全吸収 (equispaced, RMS=0): **gapless** (massless)
2. standard fingerprint: **gap は小さい**
3. deep fingerprint: **gap は大きい**
4. Wick residual: 1-operation overlay

**等間隔 = free (non-interacting)**。
注: 等間隔は「massless」ではない。HO は等間隔 (EXACT) だが gap = ℏω > 0 (massive)。
等間隔は「相互作用がない」ことを意味し、gap の有無とは独立。
massless = 線形分散 ω(k) = c|k| は等間隔とは別概念 (k-space の離散化に依存)。

S16-C: 等間隔からの任意の摂動 ε が Fejér peak を破壊。

**OQ-YM-1 Phase 1-3 結果** (2026-04-11):
- P1 (gapped + 非等間隔 → tier ≠ EXACT): 5/5 PASS
- 全 SU(N) glueball: tier = INTERMEDIATE_FP (rank-independent)
- **tier は mass gap の binary indicator として機能** (P-ν-indicator)
- S16-C は「peak 破壊 → tier ≠ EXACT」を保証するが「gap > 0」の直接証明ではない。
  tier ≠ EXACT は必要条件であり十分条件ではない (→ OQ-GFT-1)。

### §5.3 D_floor (T-SA) 接続

**Formal definition** (c_distortion_floor.md S4.5):

```
S = Hamiltonian spectrum {E_0, E_1, ...}
W = local perturbation (probe field, momentum cutoff)
G(W) = {all local operators O}
d = excitation energy
D_floor = inf_{O local} (E_excited - E_0) = Delta (mass gap)
```

mass gap Δ は spectral D_floor の **候補対応** (candidate correspondence):
- D(spectrum, vacuum_perturbation) ≥ Δ
- 真空を局所摂動しても、Δ 未満のエネルギーでは励起が生じない
- **mass gap ≈ D_floor の量子スペクトル版** (構造対応、同一性は未証明)

**Superselection guard**: D_floor は J^PC sector ごとに定義される。
混合 spectrum では D_floor = max_alpha D_floor^{(alpha)} (c_distortion_floor.md S7)。

注: YM mass gap は未解決問題、D_floor は有限観測量。
現時点では対応関係として置く。同一視は OQ-GFT-1 の解決後。

### §5.5 Dispersion-Tier Bridge (T-DTB)

**Forward chain** (proved, research/dispersion_tier_chain_v0.md):
```
gap Δ > 0  →  spacing ≠ equispaced  →  tier ≠ EXACT  (S16-C)
free (g=0) →  equispaced            →  tier = EXACT   (S16-A)
D_floor(spectrum, perturbation) ≥ Δ                    (c_distortion_floor S4.5)
```

**逆方向は不成立**: tier ≠ EXACT ⇏ Δ > 0 (massless non-equispaced 反例あり)。

**Millennium problem の位置**: ΣΦ は gap の **分類器** を提供する。
gap existence の証明は scope 外。Källén-Lehmann ρ(μ²) → spacing → tier
の chain は Wightman axioms に依存し、YM での成立自体が未証明。
Lattice transfer matrix route は axioms を bypass するが continuum limit が open。

**C-DTB conjecture**: tier = INTERMEDIATE_FP + ν ∈ GOE-like (同一 sector) → gap > 0？
Empirical support 強い (全 SU(N) + 19 系横断) が formal proof は open。

### §5.4 SSB との対比 (many_body_quantum §6)

| | SSB (many_body §6) | 閉じ込め (gauge) |
|---|---|---|
| 対称性 | 連続対称性が自発的に破れる | gauge 対称性は破れない |
| gap | gapless (Goldstone) | **gapped** (mass gap) |
| 機構 | 秩序パラメータが真空を選択 | 非摂動的動力学 |
| S16 tier | STANDARD_FP 近傍 (Goldstone = 線形分散、ν 小) | INTERMEDIATE_FP (非線形分散、ν 中) |

**SSB と閉じ込めは gap 構造の両極**: SSB は gap を消し、閉じ込めは gap を生む。
q_many_body_quantum.md は「gap が消える側」を記述し、
本ファイルは「gap が生まれる側」を記述する。**双対的完成**。

---

## §6 Instanton と R-topo — 第一類障害の物理版

### §6.1 位相的分類

A/G の連結成分: π₃(SU(N)) = ℤ (N ≥ 2)。
topological charge: n = (1/8π²) ∫ Tr(F ∧ F) ∈ ℤ。

| n | sector | 作用 |
|---|---|---|
| 0 | 摂動的真空 | S = 0 (最小) |
| ±1 | 1-instanton | S = 8π²/g² |
| ±k | k-instanton | S = 8kπ²/g² |

### §6.2 θ-vacuum = gauge 回避

|θ⟩ = Σ_n e^{inθ} |n⟩

離散セクター {|n⟩} の重ね合わせ。
θ は連続パラメータ (CP 破れの角度)。

ΣΦ 読み (§21.5 参照):
- instanton number n ∈ ℤ = 離散不変量
- 連続 gauge 変換では sector 間を移れない = 第一類障害
- θ-vacuum = 「離散情報を重ね合わせで平均」 = **gauge 回避**
- 代償: θ の値が物理に影響 (strong CP problem)

### §6.3 Arrow obstruction 分類での位置

| 障害 | 離散不変量 | gauge 回避 | 代償 |
|---|---|---|---|
| Stark ν(ρ)=−1 | ℤ/2 (sign) | L² | sign 喪失 |
| Hodge Sq³ | ℤ/n (torsion) | ⊗ℚ | torsion 喪失 |
| Crystal phase | ℤ/2 (phase sign) | |F|² | phase 喪失 |
| **YM instanton** | **ℤ (winding)** | **θ-vacuum** | **CP 破れ角 θ の導入** |

YM は **離散不変量が ℤ (無限離散)** である点で他の instances より豊か。

**第一類障害の強度階層**:

| 強度 | 離散群 | 代表 | gauge 回避のコスト |
|---|---|---|---|
| finite torsion | ℤ/2 | Stark sign, Crystal phase, Hodge Sq³ | 有限情報喪失 (1 bit) |
| finite torsion | ℤ/n | Hodge torsion (一般) | 有限情報喪失 (log n bit) |
| infinite discrete | **ℤ** | **YM instanton** | **連続パラメータ θ の導入** |

ℤ/2 → ℤ/n → ℤ と強度が上がるにつれ、gauge 回避のコストが増大する。
ℤ/2 は 1 bit の喪失で済むが、ℤ は無限の離散情報を持つため
重ね合わせ (θ-vacuum) という連続的 gauge 回避が必要。

---

## §7 閉じ込めと Arrow 1 — gauge-singlet 制限

### §7.1 閉じ込めの ΣΦ 記述

**物理**: 単独の quark (color-charged) は観測不能。
color-singlet (白色状態 = gauge 不変な状態) のみが物理的。

**ΣΦ Arrow 1**:
- Scan 層: gauge 不変 observable (Wilson loop, hadron mass, ...)
- Structural 層: quark/gluon の自由度 (gauge-dependent)

Arrow 1 の像 = gauge-singlet sector のみ。

### §7.2 Hodge (p,p) 制限との同種性

| | Hodge | YM |
|---|---|---|
| 到達可能 | (p,p)-class (パリティ不変) | gauge-singlet (gauge 不変) |
| 到達不能 | (p,q), p≠q | color-charged states |
| 制約の起源 | 代数的サイクルの次元性 | gauge 群の構造 |
| 共通構造 | **定義域の対称性が像を制約する** | 同上 |

**同種の制約構造 (same constraint type, NOT identical)**:
Arrow 1 の全射性が、定義域の対称性 (domain symmetry) によって
像 (image) を制限されるパターン。
- Hodge: 代数的サイクルの次元性 → (p,p) のみに到達
- YM: gauge 群の構造 → singlet のみに到達
- 共通: **domain symmetry constrains image**
- 非同一: 制約の具体的メカニズムは異なる (次元 vs gauge invariance)

---

## §8 漸近自由性と繰り込み — 第三類障害の制御

### §8.1 β 関数と running coupling

β(g) = μ ∂g/∂μ = −β₀g³ + O(g⁵)

SU(N): β₀ = (11N − 2N_f) / (48π²) > 0 for N_f < 11N/2。
β < 0 → UV で g → 0 (漸近自由性)。

ΣΦ 読み: running coupling は **τ-scan 的**。
- scanner = μ (energy scale)
- S12 乗法 scan: g(μ) = g₀ · (μ/μ₀)^{β₀} (leading order)
- 漸近自由: 高エネルギーで coupling が消える = scan の「吸収」

### §8.2 第三類障害の制御

| | QED (U(1)) | YM (SU(N)) |
|---|---|---|
| β | > 0 (赤外自由) | < 0 (漸近自由) |
| UV 挙動 | Landau pole (発散) | 自由 (g → 0) |
| 第三類障害 | **制御不能** | **制御可能** |
| 繰り込み | 有限次だが UV 完成でない | UV 完成 |

**漸近自由性 = 第三類障害が ΣΦ の意味で「吸収される」**。
UV 発散を有限個の counterterm で吸収 + UV で coupling 消滅。

### §8.3 IR 問題 (閉じ込め)

UV は制御済みだが IR (低エネルギー) は非摂動的。
g → ∞ as μ → 0: 強結合。
閉じ込めと mass gap はこの IR 領域の帰結。

**ΣΦ 読み**: UV = 第三類障害 (制御済)、IR = mass gap 問題 (未解決)。
第三類と第一/第二類が **スケール依存で入れ替わる**:
- UV: 第三類が主 → 繰り込みで制御
- IR: 第一類 (instanton, 離散 topology) + 未知の非摂動的機構

---

## §9 Open Questions (本ファイル固有)

| ID | Question | Priority | Ref |
|---|---|---|---|
| OQ-GFT-1 | S16 tier 分類で mass gap を判定可能か (= OQ-YM-1)。**Partial**: forward (gap→tier) proved (T-DTB)。Reverse (tier→gap) open (C-DTB conjecture) | MEDIUM | §5.2, §5.5 |
| OQ-GFT-2 | S7 → YM partition function の 6-gauge 対応は検証可能か (= OQ-YM-3) | MEDIUM | §3.3 |
| OQ-GFT-3 | Gribov 問題は §15.2 gauge 壁分類のどの壁に対応するか | MEDIUM | §4.2 |
| OQ-GFT-4 | 閉じ込め = Arrow 1 gauge-singlet 制限 は Hodge (p,p) 制限と formal に同種か (= OQ-YM-4) | MEDIUM | §7.2 |
| OQ-GFT-5 | 漸近自由性の「UV 吸収」は S16 Fejér absorption の continuous 版として記述可能か | LOW | §8.1 |
| OQ-GFT-6 | Λ_QCD (running coupling の特性スケール) は S13 instance (乗法軸上の固定点) として定式化可能か？ S12/S13 分離規約 (runtime/s12_s13_separation.md) に基づき、running coupling = S12 instance (乗法 scan)、Λ_QCD = S13 consumer (特殊値) として分離すべきか？ | MEDIUM | §8.1 |

---

## §10 辞書接続の完全リスト

| 接続先 | 接続内容 | 方向 |
|---|---|---|
| phase_complex §2-4 | U(1) → SU(N) 拡張 | upstream (一般化) |
| quantum_observation §2 | [A,B] → [D_μ,D_ν] = F | upstream (場の理論版) |
| hidden_degrees_of_freedom §2.5 | R-gauge: FP, Gribov, BRST 具体化 | downstream (具体化) |
| many_body_quantum §5-6 | SSB (gap消滅) ↔ 閉じ込め (gap生成) の双対 | parallel (双対) |
| spectral §8 | 6-gauge class number formula → YM partition function | downstream (拡張) |
| QSM §3-4 | KMS → 有限温度 YM, deconfinement | downstream (拡張) |
| action_principles §3-4 | path integral + Wick rotation (§3 Z=∫DA の母体) | upstream (依存) |
| arrow_obstruction §3,§5 | 強度階層 (§6 instanton = ℤ)、domain symmetry constraint (§7) | downstream (具体化) |
| conductor §6 | Artin conductor = constraint codim sum → YM conductor? | speculative |
| scaling_laws §1 | running coupling = scan 的 sigmoid? | speculative |
| research/hodge_conjecture_decomposition_v0.md §21-23 | YM ミレニアム分解 | cross-ref |
