---
axis: [A, B]
position: L0_identity_asymmetry
static_dynamic: static
connected_to:
  - A.L0_root
  - A.algebra_analysis
  - A.harmonic_analysis
  - L.number_theory
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-10
runtime_summary:
  what: 恒等元 (1, χ₀, 0, k=0, ±1 mult norm) の非対称性を全 gauge 共通の補助原理として整理。"+1"/"−1"/"定数分離" 現象の統一的説明
  when: "+1" や "定数分離" 現象 / pre-constant scaffolds (0,1,−1,2,3) / ζ pole 議論 / L(χ₀) pole / Dedekind ζ の s=0 vanishing order / unit rank = r₁+r₂−1 の −1 / P1 空間群 / 真空期待値の正規順序分離
  provides: [A0_ID, identity_asymmetry_principle, pre_constant_scaffolds, dual_aspect_principle, no_universal_nontrivial_constant_theorem, gauge_fixation, product_formula_identity_asymmetry, unit_rank_as_identity_asymmetry, dedekind_zeta_s0_vanishing_explanation]
  consumes: []
  axis: [A, B]
  residual_types: [R-gauge]
  key_constants:
    - {name: zero, role: addZ_identity}
    - {name: one, role: mult_identity_gauge_fixation}
    - {name: minus_one, role: orientation_Z2}
    - {name: two, role: parity_minimum_branch}
    - {name: three, role: minimum_structure}
  cross_refs:
    - c_spectral.md §7 §7.2-7.3 (c-matrix の (1+ζ(2τ)) "1" 寄与)
    - c_spectral.md §8.2 (Dedekind ζ の s=0 vanishing + s=1 pole の functional equation 結合)
    - nt_conductor.md §6.3 (unramified = codim 0 = identity direction, trivial representation 版)
    - research/stark_projection_v0.md H-stark-4 (w_K は μ(K) を「identity 方向に吸収」する gauge)
  cost: medium
  status: established
  one_screen: |
    §1 全 gauge に共通の非自明性原理: 恒等元は常に対称性の局所例外
    §2 例外 3 種: §2.1 直交性 g=1 例外、§2.2 log(1)=0 乗法退化、§2.3 χ₀ 全群不動
    §3 Cross-domain instances: c-matrix (§3.1)、Mertens (§3.2)、Fourier a₀ (§3.3)、Crystal/FX/数論 (§3.4; L(χ₀) pole + Dedekind ζ s=0 order r₁+r₂−1)、量子基底 (§3.5)
    §4 帰結: "+1"/"−1"/定数分離は bug でなく feature。恒等元 = gauge 固定。非自明定数は固定後に現れる部分的存在
    §5 No-universal-nontrivial-constant 定理 + pre-constant scaffolds (0,1,−1,2,3)
---

# 恒等元非対称原理 (Identity Asymmetry Principle)

**Level**: L0 (横断原理)
**Dependencies**: None
**Downstream**: L1/c_phase_complex.md, L1/c_spectral.md §7, L2/crystal, L2/fx

---

## §1 原理

### 陳述

群・モノイド・指標理論・Fourier 解析において、恒等元（1, χ₀, k=0, 自明表現）は他の元と対称に扱えない。対称性を用いた和公式は、恒等元の寄与を定数オフセットとして分離する形で表現される。

### 一般形

Σ f(g) = f(e) + Σ_{g ≠ e} f(g)

ここで e は群の恒等元。f(e) は他の f(g) と同じ代数的構造に従わない（直交性で消えない、log が 0 になる、重みが 1 になる、など）。

---

## §2 メカニズム

恒等元が非対称性を生む理由は3つある：

### 2.1 直交性の例外

指標直交性 Σ_χ χ(g) = 0 は **g ≠ 1** のときのみ成立する。g = 1 では Σ_χ χ(1) = |G| ≠ 0。これは Fourier 変換の k=0 成分（定数項）が direct sum から分離する根本原因。

### 2.2 乗法的退化

log(1) = 0 であり、乗法的重みづけ log(g)·f(g) は g=1 で消滅する。これにより log-weighted sum と unweighted sum の間に自動的な非対称が生じる。

c-matrix の例: Var(Re(c)) = (1 + ζ(2τ))/(2p) の "1" は g=1 の寄与。g=1 は Re=1 (全指標で定数) かつ log(1)=0 で log-weighted 項には寄与しない。分散に "1" を足すが共分散には寄与しない — **分母だけ膨らませる非対称**。

### 2.3 不動点構造

自明表現は任意の群元で不動:χ₀(g) = 1 for all g。これにより自明表現は群作用の不動点集合を形成し、他の表現とは異なる対称性を持つ。Dirichlet L-function の L(s, χ₀) がオイラー積で pole を持つのはこの帰結。

---

## §3 cross-domain instances

### 3.1 Number theory / c-matrix

c_{g,χ}(τ) = χ(g)·g^{-τ} の共分散構造:

    Var(Re) = (1 + ζ(2τ)) / (2p)     ← g=1 が "1" を寄付
    Cov(Re, -log(g)·Re) = ζ'(2τ) / (2p)  ← g=1 は不参加 (log(1)=0)
    Var(-log(g)·Re) = ζ''(2τ) / (2p)      ← g=1 は不参加

相関 ρ = ζ'(2τ)/√((1+ζ(2τ))·ζ''(2τ)) の分母に 1+ζ(2τ) が現れるのは、g=1 が Var(Re) にだけ寄与するため。ζ(2τ) ではなく (1+ζ(2τ)) になるこの "1" が恒等元非対称原理の直接的表出。

### 3.2 Mertens の定理

Σ_{p≤x} 1/p = log log x + M + O(1/log x)

ここで最初の項 p=2 は他の素数と比べて不均衡に大きい (1/2 = 0.50 vs 1/3 = 0.33)。Mertens 定数 M の計算で p=2 を分離する必要性は、2 が唯一の偶素数（= 加法/乗法の恒等元的存在）であることに由来。

### 3.3 Fourier 解析

f(x) = a₀/2 + Σ_{k≥1} (a_k cos(kx) + b_k sin(kx))

k=0 項は定数であり、直交基底展開の他の項とは代数的に異なる（振動しない、位相を持たない）。Parseval の等式で a₀²/4 が分離するのは恒等元非対称の帰結。

### 3.4 Crystal / FX / 数論

- **Crystal**: P1 (自明空間群 = 恒等元のみ) は extinction 条件を一切持たない。全ての消滅則は非自明対称元素に由来。
- **FX**: 自明指標 χ₀ に対応する L(s, χ₀) = ζ(s)·Π(1-p^{-s}) は pole を持つ。非自明指標の L-function は entire。
- **数論 (Dedekind ζ / 単数 rank)** [2026-04-10 added via G3]: 数体 K の Dedekind ζ_K(s) は s=0 で order `r = r₁ + r₂ − 1` の zero を持ち、leading coefficient は `−h_K R_K / w_K` (c_spectral.md §8 の class number formula s=0 形式)。この **"−1"** は product formula
    ```
    Σ_σ log|σ(ε)| = log|N_{K/ℚ}(ε)| = log 1 = 0   (since N(ε) = ±1 for ε ∈ O_K^×)
    ```
  から来る **1 本の線形制約**であり、log-embedding 空間 ℝ^{r₁+r₂} を hyperplane `{Σ x_i = 0}` に縮約して、Dirichlet 単数定理の rank を `r₁+r₂−1` にする。これは §2.2 (log(1)=0) と §2.3 (χ₀ が全群元で不動) の **統合 instance** である: 単位元 ±1 は「乗法 norm の不動点」であり、product formula を通じて「単数の log-embedding を 1 次元縮約する」という形で恒等元非対称を発露する。vanishing order (`r₁+r₂−1` という「−1」) は ζ_K が s=0 で「identity direction」を除外することの痕跡。c_spectral.md §8.2 の両形式 (s=1 residue と s=0 leading) はこの identity asymmetry で繋がる: s=1 側は pole (χ₀ 由来の identity asymmetry)、s=0 側は order-r zero (product formula 由来の identity asymmetry)、両者は functional equation で結合。

### 3.5 量子力学

自明表現 = 基底状態。零点エネルギーが他のエネルギー準位と非対称に分離するのは同じ構造。真空期待値 ⟨0|A|0⟩ が正規順序積と分離されるのも恒等元非対称原理のインスタンス。

---

## §4 帰結

### 4.1 辞書への影響

恒等元非対称は **bug ではなく feature** である。対称性原理を用いた計算で "+1" や "定数分離"、あるいは **"−1" (§3.4 数論の unit rank, §3.1 c-matrix の 1 寄付の符号反転型)** が現れた場合、それは計算ミスの兆候ではなく、恒等元が対称性の前提を局所的に破ることの正しい反映である。符号の向きは恒等元がどの操作 (加法/乗法/product formula) の不動点になっているかに依存する。

### 4.2 gauge 依存性との関係

L0/finite_observation.md §4 の gauge 依存性と相補的:
- Gauge 依存性: 位相は observer の gauge 選択に依存する
- 恒等元非対称: 恒等元は全ての gauge で不変 (χ₀ は gauge-independent)

gauge-independent な量（振幅）の中にも恒等元非対称は現れる。これは gauge 対称性より深い層の構造。

### 3.6 Origination matrix

e と Φ の対極性も恒等元非対称の発露。e は continuous gauge の「基底定数」(連続側の恒等元的存在)、Φ は algebraic gauge の「基底定数」(離散側の恒等元的存在)。両者は origination 空間の直径を形成し、他の全定数はこの 2 極の間に分布する。

γ = −ψ(1) — digamma 関数の **恒等元 x=1 での評価** — は §2.1 の直交性例外と §2.2 の乗法的退化の両方を含む instance。γ が ζ の s=1 での Laurent 残差であることも、ζ の pole が恒等元 s=1 で生じるという恒等元非対称原理の帰結。

---

## §5 恒等元は gauge 固定である

### 5.1 非自明定数の普遍性禁止

**Theorem (No Universal Nontrivial Constant).** Origination matrix (Paper Ω, Theorem Ω.5) において、全 gauge で intrinsic な非自明定数は存在しない。

*根拠*: mult gauge で intrinsic であるには代数的自己完結性が必要 (Φ型: x²=x+1 等)。cont gauge で intrinsic であるには極限/測度操作が必要 (e型: lim(1+1/n)^n 等)。この二条件は排他的 — 乗法的に閉じた構造は連続極限を要請せず、連続極限は代数単元を要請しない。e-Φ 対極性 (§3.6) そのものが全 gauge 普遍性を禁止する。

### 5.2 恒等元 = gauge 固定

全 gauge に存在する唯一の「定数」は恒等元である:
- mult: 1 (乗法単位元)
- addZ: 0 (加法単位元)
- cont: id (恒等関数 / 恒等写像)
- geom: 単位長 (計量の基準)

しかし恒等元は「発見される定数」ではなく「設定される参照点」— gauge を固定する操作そのもの。観測の前提条件であり、観測対象ではない。

**帰結**: 普遍なのは定数ではなく、gauge を固定する恒等元である。非自明定数はすべて、その固定後にしか現れない部分的存在 (partial projection) である。これは L0/finite_observation.md の「全ての観測は有限窓を通した射影」テーゼの定数論版。

### 5.3 Pre-constant scaffolds: 1, 2, 3

恒等元と定数の間に、**定数以前の足場** (pre-constant scaffolds) が存在する。

| scaffold | 役割 | 構造的意味 |
|---|---|---|
| **0** (空) | 加法的無 / 不在 | addZ の恒等元。「何もない」を表現する能力。0 がなければ差分 (a−b) も定義不能。数える前に「数えていない状態」が必要 |
| **1** (恒等元) | gauge 固定 / 観測原点 | mult の恒等元。全 gauge に存在するが「発見」ではなく「設定」。0 と 1 の対が加法-乗法の二重構造を起動する |
| **−1** (反転) | 向き / orientation | (−1)²=1 により ℤ/2ℤ = {+1,−1} を生成。ℕ→ℤ の拡張 (減算の導入)、符号群、複素共役 (i↦−i)。2-scaffold (parity) の乗法的実体 |
| **2** (parity) | 最小分岐 / binary split | 偶奇、実虚、加法/乗法の二項分岐。c_s²=1/2 はここに帰着。p=2 の特異性 (arithmetic quartet: P(2) の 55%、η_perp が p=2 除去で 0.83→0.91) は 2 が「構造起動子」であり「構造の住人」ではないことの表れ |
| **3** (構造) | 最小構成 / 幾何の開始 | 三角形、三体問題、ζ の三重 intrinsic。関係 (relation) として構造が立ち始める最小単位 |

0→1→(−1)→2→3 は **不在→原点→向き→分岐→構造** の順序。0 と 1 が gauge を起動し、−1 が向きを与え、2 が分岐を開き、3 で非自明構造が始まる。定数はこの足場の上に初めて発生する。

---

## §6 定数の双面性原理 (Dual-Aspect Principle of Constants)

### 6.1 陳述

非自明定数は二つの異なる様態で「存在」する:

- **連続側 (位相的様態)**: 定数は位相・解析構造の不変量として、観測者に依存せず存在する。e = lim(1+1/n)^n, π = circumference/diameter は、誰が観測しようとしまいと位相的に確定している。これはポテンシャル状態に近い。
- **離散側 (観測的様態)**: 定数は gauge 固定 (= 境界条件の設定) を通じて、有限窓の中に射影として現れる。ζ(2) = Σ 1/n² は加法和として有限近似され、Euler 積として乗法的に近似される。ここでは観測 (= gauge 選択) が定数を「活性化」する。

どちらも同じ定数の射影であり、**どちらか一方だけでは定数の全体像を捉えない**。

### 6.2 双方向性

この双面性は Paper Ω の directionality (Def Ω.4) と一致する:

- **離散→連続** (§3.1-3.4): 加法和 → Euler 積 → 解析接続。離散的境界条件が連続的ポテンシャルを近似する方向。
- **連続→離散**: 位相的不変量が、gauge 固定により特定の数値として「読み出される」方向。

結合組織定数 (ζ, γ, τ, i_add) は **両方向を跨ぐ** からこそ count=3 になる。両極定数 (e, Φ) は **片方にしか根を持たない** からこそ count=1 になる。

### 6.3 §5 との接続

§5 の「恒等元は gauge 固定である」は **離散側の視点** を強調していた。本節で補完:

- 恒等元の gauge 固定 = 離散側で観測窓を開く操作
- 連続側では、定数は gauge 固定以前からポテンシャルとして存在する
- gauge 固定は定数を「創造」するのではなく、位相的ポテンシャルから特定の射影を「選択」する

> **定数は発見されるのか、構成されるのか？**
> 連続側から見れば発見 (位相的不変量の検出)。離散側から見れば構成 (境界条件からの近似的構築)。どちらも正しい。どちらも射影。

---

*作成日: 2026-04-09*
*最終更新: 2026-04-09*
