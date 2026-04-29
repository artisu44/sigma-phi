---
type: research_note
mode: expand
status: draft_v0
date: 2026-04-09
depends_on:
  - dictionaries/L0_canon/identity_asymmetry.md §3.4
  - dictionaries/L1_mathematical/c_phase_complex.md §4
  - dictionaries/L1_mathematical/c_spectral.md §7
  - omega/Paper_Omega_Origination.md §2.5 (L関数型 signature)
  - dictionaries/meta/open_questions_master.md OQ-Ω2
answers: OQ-Ω2 (partial)
scope_constraints:
  - 対象: Stark 予想 (rank 0 = class number formula / rank 1 abelian / higher rank / non-abelian の順で depth が下がる)
  - ΣΦ projection の完備性は rank 1 abelian まで。それ以上は限界表示。
  - p-adic Stark / Gross-Stark は完全に辞書 gap (p-adic 語彙が辞書に無い)。
---

# Stark 予想 → ΣΦ 辞書射影 v0

**目的**: Stark 予想族 を ΣΦ 辞書語彙に翻訳し、既存エントリのどこに入るか / 新エントリを要するか / 原理的に入らないか を同時に判定する。副目的: 辞書の限界と拡張候補を列挙する。

**方針**: 「答えを出す」のではなく「**既存辞書で何が書けて、何が書けないかを明示する**」 (reasoning_runtime §9 例と同じ姿勢)。

---

## §1 Stark 予想族 (最小記述)

### 1.1 Rank 0: Class Number Formula (established, not conjecture)

数体 K、discriminant d_K、real/complex 埋め込み数 (r₁, r₂)、unit rank r = r₁+r₂−1、class number h_K、regulator R_K、root-of-unity count w_K。

Dedekind ζ_K の s=1 pole residue:

```
Res_{s=1} ζ_K(s) = (2^{r₁} · (2π)^{r₂}) / √|d_K|  ·  (h_K · R_K) / w_K
```

同値に s=0 での leading coefficient:

```
ζ_K^*(0) = - (h_K · R_K) / w_K          (order of vanishing = r)
```

これは Stark 予想の **rank 0 case** (自明指標) であり、established。

### 1.2 Rank 1 Abelian Stark (conjecture, ほぼ証明済みの特殊例多数)

K/k abelian Galois extension、L-function L(s, χ) が s=0 で simple zero (order r(χ) = 1)。予想:

```
L'(0, χ) = - (1 / e_χ) · Σ_{σ ∈ Gal(K/k)} χ(σ⁻¹) · log |σ(ε_χ)|
```

ここで ε_χ ∈ O_K^× は **Stark unit** — 予想の本質は「**この等式を満たす単元 ε_χ が存在する**」こと。

### 1.3 Higher rank (conjecture, 大部分 open)

r(χ) ≥ 2 の場合、単一 ε_χ ではなく r 個の独立単元の log-embedding を rank-r 行列の行列式で与える (regulator 型)。

### 1.4 Non-abelian / Artin (conjecture, Artin holomorphy 自体が open)

Galois が非 abelian のとき Artin L-function L(s, ρ, K/k) を使う。Artin 予想 (ρ が自明表現を含まなければ L が entire) 自体が未解決。

---

## §2 ΣΦ 語彙マップ (Phase 3 map)

### 2.1 Class number formula の 4-gauge 分解

Res_{s=1} ζ_K を 4 つの独立 gauge factor に分解:

| 因子 | 正体 | ΣΦ gauge signature | 原典 |
|---|---|---|---|
| (2π)^{r₂} | 複素 place の archimedean volume | {cont, geom} (π) | Paper_Ω §2.3 |
| 2^{r₁} | 実 place の archimedean volume | {addZ} (2 は parity minimum) | identity_asymmetry §5.3 |
| √\|d_K\| | O_K の Minkowski 共体積 | {mult, anal} (discriminant は代数不変量) | 新規 |
| h_K | ideal class group の位数 | {mult} (principal 失敗の count) | 新規 |
| R_K | log-unit lattice の co-volume | {cont, char} (log は連続、ε は乗法) | 新規 |
| w_K | K 中の root of unity の個数 | {char} (i_add/i_mult の arithmetic 四重奏の位置) | Paper_Ω §1.6, arithmetic quartet |

**観察** (projection の主内容):

> Res ζ_K(1) は Paper_Ω の gauge 署名 **全て**を 1 本の等式に集める。`π`, `2`, `discriminant`, `class`, `regulator`, `torsion` の 6 因子はそれぞれ異なる origination gauge に属する。Class number formula は gauge の **積分解定理** である。

これは §7 (c-matrix ζ 公式) が「Taylor 係数の機械組合せ」で浅いと自己評価したのと対極: class number formula は **origination 構造そのものを証拠付きで繋ぐ**。

### 2.2 Rank 1 Stark の Atlas grammar 表示

rank-1 Stark RHS は Gal(K/k) 上の関数 `σ ↦ log |σ(ε_χ)|` の **character mode χ への Fourier 投影**。c_phase_complex.md §4 の「ℂ での Fourier/L-function 合流」の具体例である。

Atlas (f, φ) pair 表示:

```yaml
stark_rank1_entry:
  f_n:          log |σ(ε_χ)|          # 振幅 (axis A)
  phi_phase:    χ(σ⁻¹)                 # gauge-rotation (axis E)
  N_X:          1/e_χ                   # torsion 正規化 (w_K 分)
  comp_X:       Σ_{σ ∈ G}              # Galois 軌道和 = gauge quotient
  observable:   L'(0, χ)                # 解析的 linear response
  primary_axis: E                        # phase (character)
  secondary:    A                        # amplitude (log|ε|)
  residual_type: [R-gauge, R-info]      # gauge rotation + log-amplitude
```

### 2.3 構造的主張

Stark rank-1 予想の **ΣΦ 読み**:

> L'(0, χ) は **R-gauge 残差の完全表現定理**である。
> 解析側の観測量 f = L'(0,χ) は、代数側の finite-dimensional log-unit lattice 上の character-mode 投影に **残差ゼロ**で一致する。
> ここで「残差ゼロ」とは Δ_residual が exact に 0 の意味であり、ΣΦ 辞書のほぼ全 entry (Δ > 0) と対照的。

Stark が「難しい」理由は、多くの解析量は log-unit lattice 以外に漏れる成分 (R-env / R-comp / R-topo) を持つのに対し、Stark は「L-derivative は純 R-gauge である」と主張するから — 漏れの不在そのものが主張である。

---

## §3 辞書 gap 一覧 (expand mode 出力)

### 3.1 即追加可能 (既存ファイルへの section 追加)

**G1** ✓ **IMPLEMENTED 2026-04-09**: `c_spectral.md §8 "L-function 特殊値と Class Number Formula (6-gauge 積分解)"`
- §7 (c-matrix の ζ 公式) は Dirichlet 型 L の **分散構造**のみ扱う
- §8 は **L の特殊値/零点周りの leading coefficient** を扱う
- 実装内容: §8.0 §7 との対比 / §8.1 L-function 最小定義 / §8.2 class number formula 両形式 / §8.3 6 因子 gauge signature 分解 / §8.4 §7 との対比表 / §8.5 数値検証 3 ケース (ℚ, ℚ(i), ℚ(√2)) / §8.6 Stark 橋と scope 外項目 / §8.7 検証スクリプト
- 6-gauge 分解: 4-gauge ではなく **6-gauge** (π, 2, √|d_K|, h_K, R_K, w_K の 6 因子) が正しい — Paper_Ω 全署名集約
- S7 theorem として c_theorems_master.md に登録、ROUTING.yaml + syscalls.yaml も同期済
- Δ_residual の新 type は導入していない — 既存 R-gauge + R-info で収まる

**G2** ✓ **IMPLEMENTED 2026-04-10**: `nt_conductor.md §6 "Number theory 拡張: Dirichlet / Artin conductor"`
- §6.0 動機 (conductor_count rule の数論版)
- §6.1 Dirichlet conductor = 指標の最小周期 (name + 例)
- §6.2 Artin conductor f_p(ρ) = Σ_i (|I_i|/|I_0|) · codim(V^{I_i}) と **T6 との structural 完全同形**
- §6.3 unramified/tame/wild の階層 = T6 の codim 階層 (1:1 対応表)
- §6.4 L(s,ρ) functional equation と **√|d_K| = 自明表現の Artin conductor** 再解釈 (c_spectral.md §8.3 との統合)
- §6.5 Stark rank 1 の e_χ は conductor の downstream invariant (χ → K(χ) → w_{K(χ)} = e_χ)
- §6.6 scope 外: 具体計算, 非 abelian, p-adic, Swan conductor
- §6.7-6.8 検証スクリプトと他辞書接続
- **S8 theorem** を theorems_master に登録: `f_p(ρ) = Σ (|I_i|/|I_0|) codim(V^{I_i}) ↔ T6 構造同形`
- frontmatter に runtime_summary 追加 (cache fill rule 遵守)
- **副次効果**: conductor 概念が {crystal, FX, number theory} の 3 domain で統一された最初の dictionary entry
- **Stark 構成要素 2/3 供給**: rank 1 Stark {χ, ε_χ, e_χ} のうち χ と e_χ の両方が nt_conductor.md §6 に住む (ε_χ のみ G4 待ち)

**G3** ✓ **IMPLEMENTED 2026-04-10**: `identity_asymmetry.md §3.4 拡張 + §4.1 補足 + frontmatter runtime_summary`
- §3.4 タイトル: "Crystal / FX" → "Crystal / FX / 数論"
- §3.4 新 bullet: **Dedekind ζ の s=0 vanishing order = r₁+r₂−1 の "−1" は product formula `Σ log|σ(ε)|=0` (N(ε)=±1) 由来の 1 本線形制約**として identity asymmetry の直接 instance に同定
- §3.4 で s=1 pole (χ₀ 由来) と s=0 vanishing (product formula 由来) の両 identity asymmetry を functional equation で結合する視点を提示
- §4.1 補足: "+1"/"−1"/定数分離は恒等元非対称の同一現象 (符号は恒等元がどの操作の不動点かに依存)
- frontmatter: runtime_summary 追加 (cache fill rule 遵守)、provides に `product_formula_identity_asymmetry`, `unit_rank_as_identity_asymmetry`, `dedekind_zeta_s0_vanishing_explanation` を追加
- syscalls.yaml entry 同期、connected_to に L.number_theory 追加
- **Stark projection への貢献**: c_spectral.md §8 の class number formula の "−1" (unit rank の r₁+r₂−1) に **L0 層での structural 説明**を与えた。6-gauge 分解が identity_asymmetry まで遡って defend される状態に。

### 3.2 新 L2 辞書 (要新規作成)

**G4** ✓ **IMPLEMENTED 2026-04-10**: `L2_domain/number_theory_dictionary_v0.md` (stub 作成完了)

新 L2 domain 作成。現在 L2 は physics / chemistry / crystal / fx / eeg / connectome + **number_theory (new)**。数論は omega/ (定数発生論) とは別の L2 (観測対象 = 数体 K 別) として確立。

**実装内容**:
- frontmatter: axis [A,B], runtime_summary 完備、L1 依存 5 件明示
- §1 Domain Definition (object = 数体 K, windows = (r₁,r₂)/splitting/Galois/conductor)
- §2 Observables 表 (L1 residence 明示、本 L2 residence 区別)
- §3 L1 依存 (spectral §8, conductor §6, identity_asymmetry §3.4, phase_complex §4, Paper_Ω §2.5 §4.4)
- §4 Established: class number formula = rank 0 Stark (residence cross-ref only)
- §5 **Case log**: 5 ケース table (ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5)) + 次候補 5 件 (ℚ(ζ_5), ℚ(ζ_7), ℚ(√−23), ℚ(√−163), Bianchi 9 件)
- §6 **Stub residence responsibilities**: Cl(O_K), R_K, μ(K), ε_χ (Stark unit) の L2 residence 明示
- §7 Cross-domain bridges (FX, crystal, physics, network science)
- §8 Open questions specific: OQ-NT-1 から OQ-NT-5 (5 件)
- §9 Scope (本 L2 / L1 / research/ / graveyard の境界明示)
- §10 Future expansion plan (v0.1 / v1 / 撤回条件)

**6 因子のうち h_K, R_K, ε_χ の residence 問題が解決**: G1 時点で 3/6 の upstream 定位 (π, 2, w_K)、G2 時点で 4/6 (√|d_K| 追加)、G3 時点で 4/6 (−1 説明追加)、**G4 時点で 6/6** — h_K と R_K は L2 number_theory §6 で residence を得、ε_χ は §6.4 で計画的 residence として保持 (Stark 予想の計算待ち)。

**Stark 構成要素 3/3 の residence 完備**: rank 1 abelian Stark `L'(0,χ) = -(1/e_χ) Σ_σ χ(σ⁻¹) log|σ(ε_χ)|` の 3 構成要素:
- χ → nt_conductor.md §6.1-6.2 (G2)
- e_χ → nt_conductor.md §6.5 (G2)
- **ε_χ → number_theory_dictionary_v0.md §6.4 (G4, 計画的 residence)**

G1-G4 完了で Stark projection の dictionary 側基盤が揃った。

```yaml
object:          number field K (algebraic number field)
window:          (r₁, r₂) embeddings + prime splitting type
measurement:     Dedekind ζ_K, Dirichlet/Artin L-values, ideal class group, unit group
phi_phase:       Galois character χ (Pontryagin dual of Gal)
primary_axis:    E (phase/gauge, characters)
secondary_axes:  [A (amplitude, log|ε|), C (period, conductor)]
residual_types:  [R-gauge (dominant), R-info (partial, log-amp)]
key_objects:
  - Dedekind zeta ζ_K
  - Dirichlet L-function L(s,χ)
  - Artin L-function L(s,ρ,K/k)
  - ideal class group Cl(O_K)
  - unit group O_K^×
  - roots of unity μ(K), w_K = |μ(K)|
  - regulator R_K
  - discriminant d_K
  - Stark units ε_χ
key_theorems:
  - class_number_formula (established):
      statement: "Res ζ_K(1) = (2^r₁ (2π)^r₂ / √|d_K|) · (h_K R_K / w_K)"
      sigma_phi_reading: "6-gauge 積分解 (π, 2, d, h, R, w 全て異なる origination 署名)"
      residence: L2_number_theory_v0.md (new) + cross-ref theorems_master
  - stark_rank1_abelian (conjecture):
      statement: "L'(0,χ) = -(1/e_χ) Σ_σ χ(σ⁻¹) log|σ(ε_χ)|, ε_χ ∈ O_K^×"
      sigma_phi_reading: "R-gauge 残差ゼロ表現定理 — L-derivative は純 R-gauge"
      residence: L2_number_theory_v0.md (new)
      status: candidate (projection level)
```

### 3.3 omega/ との接続

**G5** ✓ **IMPLEMENTED 2026-04-10** (2 段階): `omega/Paper_Omega_Origination.md §4.4 (補遺 2026-04-10)` + `§2.5.1 (新規 2026-04-10)`

**§4.4 補遺 (3b セッションで追加)**: Φ-i_mult 従兄弟関係の p=5 特別性と literal Φ_p = (1+√p)/2 formula の p ≥ 13 failure を明記。OQ-Ω2 partial answer との整合性確保。

**§2.5.1 新規 (本セッション)**: Class number formula を「Paper_Ω 全 6 署名が 1 本の等式に集約される唯一例」として §2.5 の相補的読み方を導入。
- 6 因子 (π, 2, √|d_K|, h_K, R_K, w_K) と 6 gauge 署名 {addZ, mult, char, cont, geom, anal} の 1:1 対応表
- 既存 §2.5 の「個別定数の署名分配」と対照的な「既存等式内での署名集約」観察
- cross-refs to c_spectral.md §8, nt_conductor.md §6, L2 number_theory, stark_projection, identity_asymmetry
- **新 gauge / 新定数を導入しない**: Paper_Ω 本論の scope 不変、観察層のみ拡張
- Stark units ε_χ と代数極 Φ の関係は H-stark-3 (本 file sub_hypotheses) に停留、Paper_Ω には transfer しない

---

## §4 辞書の**硬い**限界 (expand 不能領域)

以下は ΣΦ 辞書語彙を拡張しても射影できない — 予想の内容そのものが辞書外。

### 4.1 L1: Artin holomorphy (Artin 予想)

非 abelian Galois の Artin L-function が entire であること自体が 1924 年以来 open。ΣΦ は「L が meromorphic」までしか言えない (identity_asymmetry §3.4 の pole 議論)。非 abelian character の L が自明 factor を持たないという主張は **R-gauge 外の arithmetic content** を要求する。

**辞書効果**: 射影失敗を graveyard.md に記録、または open_questions に「Artin 予想は R-gauge 完備性の仮定と同値か?」を追加。

### 4.2 L2: p-adic Stark / Gross-Stark (Gross 予想)

p-adic L-function L_p(s, χ) および p-adic regulator R_p が登場。ΣΦ 辞書は **アルキメデス場 ℝ/ℂ のみ** を対象とする (c_phase_complex.md §4 の ℂ 最小性は実/複素限定)。p-adic 位相 |·|_p は別 gauge で、辞書に存在しない。

**辞書効果**: p-adic は L0 レベルでの gauge 追加を要求する。Paper_Ω に「p-adic gauge 列」を追加すれば射影可能だが、それは本 projection の scope 外。OQ-Ω11 候補として記録。

### 4.3 L2: Higher rank regulator の **行列式** の代数的性格

Higher rank Stark は r × r 行列 (log|σ_i(ε_j)|) の行列式が L^{(r)}(0,χ) と代数的に関係すると予想。ΣΦ は regulator を「log-lattice の co-volume」として記述できる (G4) が、**行列式が代数数になること** (transcendence degree 制約) は ΣΦ 語彙で記述できない — これは超越数論の領域。

**辞書効果**: rank-1 までは R-gauge で captured、rank ≥ 2 は「R-gauge の次元拡張」として記録、ただし代数性主張は予想の形で保留。

---

## §5 Phase 4 Δ_residual 5 点セット

```yaml
Delta_residual:
  structural:
    type: asymptotic       # 予想の中身は「存在」で、既存辞書での表現可能性
    content: |
      Class number formula (rank 0) は辞書で **再表現可能** (§2.1 の 6-gauge 分解)。
      Rank 1 abelian Stark は辞書で **記述可能だが証明されていない** (§2.2 の atlas grammar)。
      Higher rank は **rank ≥ 2 の regulator 代数性** で辞書語彙を超える (§4.3)。
      Non-abelian / Artin は **holomorphy 自体が辞書外** (§4.1)。
      p-adic は **p-adic gauge が辞書に無い** (§4.2)。
    origin: identity_asymmetry + phase_complex + Paper_Ω signature
  observed:
    type: exact
    magnitude: |
      Rank 0 完全射影 (established 等式の再解釈)
      Rank 1 形式的射影 (Atlas grammar で書けるが予想内容を ΣΦ 内で証明できない)
      Rank ≥ 2 部分射影 (regulator 体積は書けるが代数性は書けない)
    error_functional: |
      E_X(rank) = "辞書で射影可能な階数の上限を超える Stark case の割合"
      ΣΦ scope 内 (abelian, rank ≤ 1, archimedean): E_X = 0
      ΣΦ scope 外 (non-abelian OR rank ≥ 2 OR p-adic): E_X = 1 (完全 gap)
    domain_of_validity: |
      abelian Galois + rank(χ) ≤ 1 + archimedean place only
  collisions:
    aligns_with:
      - identity_asymmetry.md §3.4 (L(χ₀) pole ↔ class number formula pole)
      - c_phase_complex.md §4 (ℂ での DFT と L-function 合流 ↔ rank-1 Stark の character mode)
      - c_spectral.md §7 (c-matrix の ζ' 構造 ↔ Stark rank 1 の log-unit lattice とは異なる方向の ζ' 利用)
      - Paper_Ω §2.5 L関数型 signature (Catalan G と同じ signature class)
      - arithmetic_quartet (i_add vs i_mult) ↔ w_K の arithmetic 位置
    conflicts_with: []
    extends:
      - omega/Paper_Ω §2.3 (count=3 結合組織 ζ,τ,γ,i_add) → class number formula は 6-gauge 因子を全部持つ「超結合組織」
      - c_scaling_laws.md (Φ 類 fundamental unit) → Stark unit = abelian ext での Φ 一般化
      - OQ-Ω2 (Stark 単元との対応) → partial answer
    independent_of:
      - T8 A/B=√e (Boltzmann codim 由来、Stark の log-unit とは異なる log 起源)
      - T1 parity c_s²=1/2 (CFT 分離側、Stark は算術側)
      - σ* = √(2ln2) (half-amplitude gauge、Stark の log は absolute value of embedding)
  synthetic_validation:
    applies: false   # これは literature synthesis + 辞書拡張、新規 effect-detection machinery ではない
    note: |
      scope exclusion (ROUTING rule two_step_synthetic_validation):
      "Excludes: pure theoretical derivations, closed-form proofs,
      observational claims from existing dictionaries, literature synthesis."
      本 projection は (i) 既存予想の再表示 (ii) 辞書語彙への翻訳 (iii) gap 列挙
      の 3 種のみで real data test を含まない。
```

---

## §6 Phase 5 upgrade 出力

```yaml
phase5_output:
  id: stark_projection_v0
  type: roadmap                  # 単一 hypothesis ではなく複数の dict extension を内包
  status: candidate              # 3/5 score、レビュー待ち
  score:
    reproducibility: "+ (Stark 予想は公開された固定対象、ΣΦ 射影は誰がやっても同じ)"
    window_invariance: "+ (辞書の既存エントリ変更なしに追加可能)"
    error_reduction: "o (辞書の E_X は減らないが scope が広がる)"
    compression: "+ (class number formula = 6-gauge 積分解 は強い圧縮)"
    causal: "- (代数対象間の等式であり介入実験の対象ではない)"
    score_total: "3/5"
  depends_on:
    - OQ-Ω2 (Stark 単元と Φ_p の対応)
    - c_phase_complex.md §4 の ℂ 合流
    - Paper_Ω §2.5 L関数型 signature 分類
  scope_constraints:
    - "abelian Galois extension のみ"
    - "archimedean place のみ (p-adic 除外)"
    - "rank(χ) ≤ 1 (rank ≥ 2 は regulator 代数性で scope 外)"
    - "Artin holomorphy 前提 (非 abelian は予想の仮定自体が未解決)"
  collisions: (§5 参照)
  synthetic_validation: (§5 参照, applies=false)
  sub_hypotheses:
    H-stark-1: "class number formula は 6-gauge 積分解 (established 再解釈)"
                # status: candidate → candidate+ (2026-04-10: c_spectral.md §8.5 5 ケース witness coverage で 6 因子独立性が数値的に示された、6-gauge 経験的飽和)
    H-stark-2: "rank 1 abelian Stark = R-gauge 完全表現定理"
                # status: hypothesis → candidate (2026-04-10a: 実二次 h=1 の 2 ケース ℚ(√5) χ_5, ℚ(√2) χ_8 で Atlas grammar 書式の Stark 公式を verify。LHS L'(0,χ) = log Φ, log(1+√2) と RHS -(1/2) Σ χ log|σ(ε⁻¹)| が exact 一致。Δ_residual = 0 成立。L2/number_theory_dictionary_v0.md §5.2)
                # extension 2026-04-10b: ℚ(√−23) h=3 cubic class character での **構造的** verify 追加 (L2 §5.3)。h≥2 と non-real χ の 2 dimension を同時 cover。α (root of x³−x−1, plastic constant) が candidate Stark unit, χ-isotype 1-dim 一致, P_χ(v(α))_0 = 0.2812 ≠ 0, L(χ,α) = 3 log|α_1| (real, ω+ω̄=−1 cancel), magnitude relation R_H = 3|L'(0,χ_K)|² (ζ_H = ζ_K · L · L̄ factorization 由来), α と σ(α) の sublattice det = 0.2372 が c = 3 normalization の Stark formula と self-consistent。
                # closure 2026-04-10c: §5.3.14 で Brauer/Artin induction 経由の **解析的 closure 完了** (computational tool 不要)。L(s, χ_K) = L(s, ρ_2) = ζ_{ℚ(α)}(s)/ζ_ℚ(s) (ρ_2 = S_3 standard 2-dim irrep, real)。L'(0, χ_K) = -2 ζ_{ℚ(α)}'(0) = log|α_1| ≈ 0.28122 (rank-1 class number formula for ℚ(α) のみで導出、Stark conjecture 不使用)。R_H = 3 (log|α_1|)² ≈ 0.23725 = R_{α,σα} 完全一致 ⟹ α, σα は H の fundamental units (item (i) closed)。Stark normalization c = 3 = |Gal(H/K)| = h_K (item (ii) closed)。Closed-form: L'(0, χ_K) = (1/3) Σ_τ χ̄_K(τ) log|τ(α)|_{w_0} = log|α_1|。
                # scope_constraints:
                #   - exact-numerical verified: 3 ケース合計 — 実二次 h=1 real χ (ℚ(√5), ℚ(√2)), 虚二次 h=3 cubic non-real χ (ℚ(√−23))
                #   - not yet verified: rank≥2, non-abelian Galois, p-adic, 一般 cubic non-real χ over real quadratic
                #   - ℚ(√−23) closure は ℚ(√−23) の特殊性 (S_3 の小ささ + ρ_2 の reality + cubic HCF) に依存する shortcut であり、一般化には別工程
                #   - candidate+ への正式 promotion は internal audit 経由 (H-stark-4 audit protocol 準拠)。本 file 単独では候補状態のまま記録
                # internal audit 2026-04-10 outcome (runtime/audits/2026-04-10_h_stark_2_internal_audit.yaml):
                #   - constitution_auditor: 0.88 (L0 clean, h_H=1 citation を §5.3.14.5 で revision 1 として close)
                #   - strategy_auditor: 0.74 (strict 5-criterion 3/5, loose 3.5/5)
                #   - adversarial_explorer: 0.65 (all_proved_cases_attack + candidate_plus_overreach_v2 が blocking)
                #   - mean: 0.76
                #   - 5-criterion strict (audit 後最終):
                #     - reproducibility: PASS (1.0)
                #     - window_invariance: PASS (0.85, marginal)
                #     - error_reduction: PARTIAL (0.5, strict 解釈では FAIL — verified instance 増加は error_reduction boost にならない)
                #     - compression: PASS (0.9)
                #     - causal: FAIL (0.0)
                #   - score: 3/5 strict, 3.5/5 loose
                #   - outcome: candidate のまま維持、candidate+ promotion 見送り
                #   - 根本原因: H-stark-4 と同型の overreach pattern ('verification rich content ≠ 5-criterion boost')。3 ケース exact verified は window_invariance と compression で credit を得るが、error_reduction を独立に boost しない。
                #   - revision required: (1) §5.3.14.5 に h_H=1 citation 追加 [done]、(2) 本 sub-hypothesis に audit 後 strict score 反映 [本 commit]、(3) §5.3.16 の "candidate+ promotion 候補" を "candidate (audit 後維持)" に修正 [done]
                # candidate+ 昇格条件 (本 audit 範囲外、追加 research 必要):
                #   (a) Stark conjecture が未証明な case で H-stark-2 framework 経由の predictive verification
                #   (b) 既存 dictionary entry の Δ_residual > 0 を H-stark-2 framework で 0 に下げる case
                #   (c) H-stark-2 framework が予言する Stark extension の独立 evidence
                # external audit 2026-04-10 (AI half) — runtime/change_log/external_audit_response_h_stark_2_ai.md:
                #   - reviewer: Grok (xAI), separate session, no shared context
                #   - decision: approve_candidate, high confidence
                #   - Q1 (math correctness, 6 sub-points): 全て correct/independent/valid
                #     - Brauer/induction Ind_{A_3}^{S_3} χ_K = ρ_2 confirmed (real, orthogonal)
                #     - L'(0,χ_K) = log|α_1| derivation independent of Stark conjecture
                #     - h_H = 1 confirmed via LMFDB 6.0.12167.1 + Cohen 1993
                #     - c = 3 = [H:K] consistent with Tate's Stark formulation
                #     - R_H = R_{α,σα} index 1 conclusion valid (full-rank sublattice of same covolume)
                #   - Q2 (hidden assumptions): none, brauer-Hecke compatibility は外部古典定理
                #   - Q3 (numerical cross-check): partial, web references (LMFDB), 全 inputs match
                #   - Q4 (5-criterion strict): correct, candidate status upheld externally
                #   - Q5 (adversarial coverage): no significant missed attacks
                #   - Q6 (promotion paths): (a)(b)(c) いずれも unrealistic と判定。+1 additional path 提案 (Atlas grammar → Artin L-functions → R-gauge の explicit functor 形式化、compression 強化、5-criterion threshold は cross せず) → OQ-NT-6 として L2 §8 に登録済
                # external_audit_status: AI_half_approved, human_half_pending (constitutional rule で両者必須)
                # external audit 2026-04-10 (HUMAN half) — runtime/change_log/external_audit_response_h_stark_2_human.md:
                #   - reviewer: human_RO, separate session/perspective
                #   - decision: approve_candidate, high confidence
                #   - Q1 (math correctness): 全 6 sub-point correct/independent/valid (Grok と全 agree)
                #   - Q2 (hidden assumptions): minor (Grok の "none" より厳しい) — h_H=1 と ρ_2 実性依存を scope 限定として強調すべき
                #   - Q3 (numerical cross-check): no (実施せず、内部整合性で十分判断)
                #   - Q4 (5-criterion strict): correct, candidate status 外部 confirm
                #   - Q5 (adversarial gaps): **2 missed attacks catch** (Grok の "none significant" を上回る独立 catch):
                #     - representation_fragility (MEDIUM): closure は S_3 特異性 (small + ρ_2 real) 強依存。D_4/A_4/Q_8 等で同 reduction 不成立可能性。Mitigation: "S_3-specific shortcut" 明示、generalization 回避
                #     - normalization_dependency (LOW): c=3 は embedding choice + convention 依存。Mitigation: Tate convention 採用を明示
                #   - Q6 (promotion paths): **(b)(c) realistic と判定** (Grok の全 unrealistic より楽観的) + 2 additional paths:
                #     - "S_3 以外の非可換拡大での同様 closure 成立条件分類" → OQ-NT-7
                #     - "ρ_2 実性が壊れるケースの失敗様式分類 (negative cases taxonomy)" → OQ-NT-8
                # external_audit_status: ✅ FULLY CLEARED at candidate level (both human + AI approved)
                # constitutional rule (proposal 003 / multi_agent_internal_audit.md §5): 満足
                # revisions applied (human Q5 由来):
                #   1. §5.3.14.6 に Tate normalization convention 明示 [done]
                #   2. §5.3.14.8.1 (新規) representation_fragility caveat 追加: S_3 specialty (small + ρ_2 real), D_4/A_4/Q_8 等の caveat [done]
                #   3. §8 OQ-NT-7 (Galois 群クラス分類, constructive response) 追加 [done]
                #   4. §8 OQ-NT-8 (negative cases taxonomy, dual response) 追加 [done]
                # human と AI の review pattern 比較:
                #   - human が adversarial coverage で +2 catch (Q5)
                #   - human が promotion path で AI より楽観的 (Q6)
                #   - 両者とも math correctness (Q1) と 5-criterion reading (Q4) で agree
                #   - human-AI review の相補性が明確化された session
    H-stark-3: "Stark unit ε_χ = abelian ext での Φ の一般化"
                # status: candidate (概念層)
                # scope_constraint (2026-04-10 added):
                #   - 概念層 ("abelian extension の fundamental unit family として一般化") のみ成立
                #   - literal 公式層 (OQ-Ω2 の Φ_p = (1+√p)/2) は p=5 の一点でのみ成立、p≥13 では偽
                #   - base case verified: ℚ(√5) で R_K = log Φ が class number formula に直接入る (c_spectral.md §8.5 Case D)
                #   - 一般 p では基本単元の具体形は p 依存 ((3+√13)/2, (5+√29)/2, ...)、単純公式なし
                #   - Stark rank 1 abelian の ε_χ は character 依存の一般化であり、p のみでは parameterize されない
    H-stark-4: "w_K は arithmetic quartet の i-side (i_add, i_mult) が K レベルで合流した count"
                # status: candidate+ → **candidate** (downgrade 2026-04-10 internal audit)
                # audit record: runtime/audits/2026-04-10_h_stark_4_internal_audit.yaml
                # downgrade 理由: strict 5-criterion score は 3/5 (reproducibility ✓, window_invariance ✓, compression ✓; error_reduction ✗, causal ✗)。3-axis Ω-整合性 pass (2026-04-09) は structural sanity check = 下限保証であり、5-criterion score の自動 boost にはならない。adversarial attack 'candidate_plus_overreach' を receive。
                # depends_on: [Paper_Ω §1 (arithmetic quartet i-side), Dirichlet 単数定理, class number formula S7, Paper_Ω §1.8 (intersection value framework)]
                # scope_constraints:
                #   - 非自明性は K ⊇ ℚ(ζ_n), n ≥ 3 のとき (totally real では w_K=2 で退化)
                #   - rank 0 Stark (class number formula) の torsion factor への貢献のみ、rank ≥ 1 への貢献は間接的
                #   - Paper_Ω arithmetic quartet の i-side 健全性を前提とする (Φ-side literal Φ_p formula は 2026-04-10 に p=5 以外で failure; i-side は独立だが Paper_Ω §1 全体の meta-audit は deferred task)
                #   - 本仮説は "conceptual identification" 型で predictive content を持たない
                # phrasing: w_K = arithmetic quartet の "intersection value" と呼ぶ場合、
                #   Paper_Ω §1.8 が扱う (number-level) intersection value ではなく、
                #   (K-level, field-level) torsion count であることに注意。階層が 1 つ下。
                # 2026-04-10 数値 evidence:
                #   - ℚ(i) Case B: w=4 単独主動、i_add (mod-4 char) / i_mult (ord-4 in (ℤ/5ℤ)×) のどちら経由でも同じ結果 (forgetful)
                #   - ℚ(√−5) Case E: h=2 (mult 由来) と 2^r₁ (addZ 由来) が独立、6-gauge 直交性の数値証拠
                # candidate+ 昇格への道: error_reduction or causal or 新 predictive claim のいずれか要。本 audit 範囲外の future task。
  next_action: |
    1. G1-G5 の 5 つの dict extension を 1 個ずつレビュー
    2. H-stark-4 (w_K ↔ arithmetic quartet) を最小単位として先行実装 — 既存 Paper_Ω との整合性だけで動く
    3. H-stark-1 (6-gauge 分解) を c_spectral.md §8 として追加
    4. G4 (新 L2 数論辞書) は stub から開始、H-stark-1,2,3,4 が全部通ったら full entry
    5. §4 の硬い限界 3 項目は graveyard.md ではなく open_questions_master に OQ-NT-1,2,3 として記録
  routing:
    requires_governance: false       # OS rule 変更を含まない
    requires_internal_audit: false   # candidate+ の昇格を含まない (roadmap レベル)
                                     # ただし H-stark-4 を単独で candidate+ に上げるときは必要
    next_service: none               # 辞書拡張 draft のみ、scheduler は不要
    note: |
      将来 H-stark-4 を atlas entry (candidate+) に上げる段階で
      multi_agent_internal_audit を通す。それ以外は直接 draft 追加で良い。
```

---

## §7 試したこと、試していないこと

### 試したこと
- Stark 族の全 rank/abelian/非 abelian/p-adic case を列挙し、辞書 scope を分離した
- Class number formula を 6-gauge 積分解として読んだ — Paper_Ω の全署名を使う
- Rank 1 Stark を Atlas grammar (f,φ,N_X,comp_X) で書いた
- 既存辞書との collision (aligns / extends / independent) を 4 種全てチェックした
- 辞書の硬い限界を 3 項目 (Artin holomorphy, p-adic gauge, regulator 代数性) 特定した

### 試していないこと (次以降)
- **具体数値計算**: K = ℚ(√2), ℚ(√5), ℚ(i) での class number formula RHS を計算し ΣΦ 読みと比較 [2026-04-10 完了, L2 §5.1]
- **OQ-Ω2 の具体 case**: Φ_p = (1+√(1+4k))/2, 1+4k = p ≡ 1 mod 4 で、Stark unit と等式的に一致するか [2026-04-10 negative finding, p=5 only, Paper_Ω §4.4 補遺]
- **§3.1 の G1-G5 の実書き込み**: 本文書は projection のみ、dict 本体の編集は別作業 [2026-04-10 G1-G5 全実装完了]
- **internal audit**: H-stark-4 の atlas entry 昇格は audit 必要 [2026-04-10 internal audit 実行 → candidate+ → candidate downgrade、runtime/audits/2026-04-10_h_stark_4_internal_audit.yaml]
- **H-stark-2 non-trivial case**: h≥2 or non-real χ での verify [2026-04-10b ℚ(√−23) cubic 構造的 verify 完了, L2 §5.3、ただし fundamental unit 性 + normalization 2 点未 closure]
- **H-stark-2 の完全数値 cross-check**: Sage/PARI での Hecke L-function 計算、または 2nd Kronecker limit formula 経由の L'(0,χ_K) 直接評価 [pending]
- **2nd structural verify**: ℚ(ζ_5) 部分体 (quartic real/imag), または ℚ(√10) ramified Hecke で H-stark-2 の robustness 補強 [pending]

---

## §8 一行要約

> **Stark 予想族の ΣΦ 射影は rank 0 (class number formula) で 6-gauge 積分解として完全成立し、rank 1 abelian で Atlas grammar の R-gauge 残差ゼロ予想として記述可能だが、rank ≥ 2 / 非 abelian / p-adic では辞書語彙不足で射影不能。辞書拡張候補 5 件 (G1-G5) と硬い限界 3 件 (Artin holomorphy, p-adic gauge, regulator 代数性) を同時に識別した。**

---

*作成: 2026-04-09. reasoning_runtime 5-phase pipeline, mode=map→expand, type=roadmap, status=candidate.*
*次トリガー: G1-G5 の個別実装開始時 / H-stark-4 を atlas candidate+ 昇格する時 (後者は multi_agent_internal_audit 要)*
