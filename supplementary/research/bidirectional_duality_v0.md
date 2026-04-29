---
type: research_note
mode: draft
status: established_v0
date: 2026-04-10
updated: 2026-04-11
depends_on:
  - research/tau_internal_coordinate_v0.md (§4.4 S12, §4.6 S13/S14)
  - dictionaries/L1_mathematical/c_phase_complex.md (§4 ι_L/χ dual, structural root)
  - dictionaries/L1_mathematical/c_theorems_master.md (S12-S15)
scope_constraints:
  - Meta-structural observation。新定理 NO。
  - S12→S13→S14→S15 chain から見えた辞書全体の構造を記述する。
  - §6 新ドメイン protocol を提供。
answers: "ΣΦ 辞書は全体として何を記述しているのか?"
runtime_summary: |
  S15 Observable Trichotomy — 辞書 observable の 3 分類 (ESTABLISHED 2026-04-11)
  ─────────────────────────────────────────────────────────
  ROOT: c_phase_complex.md §4 (ι_L/χ dual = 辞書の structural root)
  
  3 CLASS (排他的・網羅的):
    Scan        = exp(a·b) kernel, scanner変数あり  [S12: K(τ),F(h),U(t),ζ(s),Z(β),c(τ)]
    Structural  = parameter-free 整数/位相不変量     [b₁, h_K, codim, n_cent, f_p(ρ)]
    Information = -Σp log p 型, S12 の log-inverse   [H, S(ρ), D_KL, H_α]
  
  3 ARROW (層間接続):
    Scan→Structural:  D,f が structural を encode (定義域構造)
    Scan→Information:  log-derivative chain (Z→F→S)  ← S13 ln2 はここの固定点
    Structural→Info:   Hartley entropy log|D|
  
  S14 非対称: π = Scan 内部 (代数), ln2 = Arrow 2 上 (解析)
  可換性: scanner extreme limit で 3 Arrow が閉じる
  
  新ドメイン protocol: §6 (6-step). HE1 enzyme 検証済.
---

# Bidirectional Duality v0 — ΣΦ 辞書の meta-structure

## §1 観察

S12 (Exponential Scan Family) → S13 (ln 2 Fixed-Point Principle) → S14 (Parity Midpoint Duality) の chain が、ΣΦ 辞書全体の構造を露呈させた。

**ΣΦ がやってきたことは、加法⇔乗法の双対の辞書を書くことだった。**

各ドメイン (FX, EEG, crystal, number theory, quantum) は同じ双対構造の異なる射影。S12 が family の存在を示し、S13 が乗法側の固定点を見つけ、S14 が加法側との非対称性を明示した — そこで初めて「全部同じことをやっていた」と見える。

## §2 双対の表

| 加法側 | 乗法側 | Bridge | 辞書内所在 |
|---|---|---|---|
| ι_L (加法準同型) | χ (乗法指標) | ℂ (共通受け皿) | c_phase_complex.md §4 |
| τ_scan (S¹ 回転) | τ_cov (指数減衰) | exp(a·b) kernel | tau_internal_coordinate_v0.md §4.3 |
| π (代数的 parity) | ln 2 (解析的 parity) | parity scaffold ℤ/2ℤ | S14 (tau_internal_coordinate_v0.md §4.6) |
| K(τ), F(h), U(t) | ζ(s), Z(β), c(τ_cov) | S12 exponential scan family | tau_internal_coordinate_v0.md §4.4 |
| 位相 (arg z) | 振幅 (\|z\|) | polar decomposition z = \|z\|e^{iθ} | L0_core_proposition.md |
| 整数の加法構造 | 整数の乗法構造 | Artin factorization (S9) | nt_dedekind_artin_zeta.md §1 |
| 離散 (格子 ℤ³) | 連続 (スペクトル ℝ) | Fourier / spectral theory | c_spectral.md §1-2 |
| 数論 (L-function) | 量子 (partition function) | 同じ exp kernel の別 instance | S12 catalog |
| 有限 (有限群, 格子) | 無限 (連続群, スペクトル) | completion / limit | c_phase_complex.md §2-3 |

## §3 S12-S14 が明かしたもの

### §3.1 S12: family の発見

辞書の全 observable が exp(a(scanner)·b(data)) という 1 つの kernel template の instance であること。加法 scan (虚軸, S¹) と乗法 scan (実軸, (0,1]) の 2 分類。

これにより「辞書内の各ドメインは何をしているのか」の答えが出た: **全て同じ exponential kernel の異なる specialization**。

### §3.2 S13: 乗法側の固定点

乗法 scan に半値条件 e^{-x} = 1/2 を課すと x = ln 2 が強制される。σ*, Landauer kT ln 2, Shannon H(1/2) が同一の無次元方程式の異なる instance であること。

これにより「なぜ ln 2 が至る所に現れるのか」の答えが出た: **S12 乗法 scan family の parity 固定点**。

### §3.3 S14: 非対称 duality

加法側の parity 条件は e^{iπ} = -1 (Euler's identity)。π と ln 2 は dual pair だが機構が異なる: π は代数的 (S¹ の torsion, ℂ の conjugation から導出可能)、ln 2 は解析的 (kernel の値閾値, codomain の順序構造から導出)。

これにより「parity scaffold がどう射影されるか」の答えが出た: **加法側は代数的に、乗法側は解析的に、同じ ℤ/2ℤ が異なる機構で現れる**。

### §3.4 双対構造の全景

S14 の非対称性は ΣΦ 辞書全体の構造を反映する:

- **c_phase_complex.md §4** が辞書の structural root: ι_L/χ dual が全ての上位構造の源泉
- **S12** が辞書の observable catalog: 全ドメインの observable を 1 template に集約
- **S13/S14** が辞書の定数論: なぜ特定の定数 (π, ln 2, e, σ*) が現れるかを双対構造から説明

辞書の各層:
- **L0**: 双対構造の公理的基盤 (位相/振幅 = arg/|·| の分離)
- **L1**: 双対構造の数学的記述 (phase_complex, spectral, etc.)
- **L2**: 双対構造のドメイン射影 (FX, EEG, crystal, etc.)
- **L3**: 双対構造のクロスドメイン接続 (情報理論, 因果推論, etc.)

## §4 downstream — 次回以降の課題

### §4.1 辞書改訂

c_phase_complex.md §4 の位置づけを明示的に「辞書の structural root」として記述。現在は L1 の 1 ファイルだが、辞書全体の indexing principle になる可能性。

### §4.2 新ドメイン検討の protocol

新しいドメインや observable を検討する際の最初の問い:
1. 加法側か乗法側か?
2. Bridge は何か (exp kernel の具体形)?
3. S13 の半値条件はどう読めるか?
4. S14 の非対称性はどう現れるか?

### §4.3 S14 昇格条件

1. 非対称 duality の記述が phase_complex §4 と整合するか確認
2. 他の定数 pair (e と i, etc.) が同様の非対称 dual を示すか検討
3. m-ary 一般化: π → 2π/m, ln 2 → ln m の dual pair 整合性

### §4.4 辞書五層構造との関係

reference_dictionary_structure.md の L0-L4 構造が「双対のどの側を記述しているか」でタグ付けできるか検討。これにより辞書の navigability が向上する可能性。

## §5 Observable 3 分類 — S12 scope boundary (2026-04-11)

S12 反例探索により、辞書内 observable は 3 層に分類される:

### §5.1 Scan observable (S12 対象)

exp(a(scanner)·b(data)) template に乗る。scanner 変数を持つパラメトリック族。

| Instance | Scanner | Kernel | 加法/乗法 |
|---|---|---|---|
| K(τ), F(h), U(t) | τ, h, t | e^{i·const·scanner} | 加法 |
| ζ(s), Z(β), c(τ_cov) | s, β, τ_cov | e^{-scanner·f(data)} | 乗法 |
| σ* (bridge) | — | Gaussian average: 加法→乗法 | cross |

### §5.2 Structural observable (S12 scope 外)

Parameter-free 整数/位相的不変量。scanner 変数を持たない。

| Observable | 定義形式 | 所在 |
|---|---|---|
| b₁(G) = K - M + 1 | 線形位相 (Betti) | nt_conductor.md T5 |
| h_K | 類群の位数 | c_spectral.md §8 |
| codim(s) | 3 - dim(zone) | nt_conductor.md §5, T6 |
| n_centering = \|L/L'\| | 格子商の位数 | crystal T1 |
| f_p(ρ) = Σ codim 重み和 | Artin conductor | nt_conductor.md §6 S8 |
| abs = 1 - 1/n | 有理関数 (exp 下流) | crystal T1 |

**§4 dual との関係**: structural observable は双対構造の **discrete skeleton** — 加法/乗法 dual が作用する空間の次元・位数・rank を数える。exp kernel の「入れ物」の形状。

### §5.3 Information observable (log-exp dual)

H = -Σ p log p 型。S12 family の逆操作。

| Observable | 定義 | S12 との接続 |
|---|---|---|
| H(X) = -Σ p log p | Shannon | log of counting measure |
| S(ρ) = -Tr(ρ log ρ) | von Neumann | -∂F/∂T where F = -kT log Z(β) |
| D_KL(p\|\|q) | KL divergence | log-likelihood ratio |
| H_α(X) | Rényi | (1/(1-α)) log Σ p^α |

**§4 dual との関係**: information observable は exp kernel の **log-inverse**。Z(β) → F = -kT log Z → S = -∂F/∂T。加法/乗法 dual の **情報的射影**。S13 の ln 2 はこの層の parity 固定点。

### §5.4 3 分類の構造

```
§4 (ι_L / χ dual)
  ├── Scan observable     = dual の parametric family    (S12)
  ├── Structural observable = dual が作用する空間の skeleton (S12 scope 外)
  └── Information observable = dual の log-inverse          (S12 の逆)
```

3 分類は排他的かつ網羅的 (辞書内の全 observable がいずれかに属する)。S12 は 3 分類の最上層 (scan) のみを claim しており、structural と information の存在は S12 の否定ではなく scope 境界の明示。

### §5.5 層間接続の形式的記述

3 クラスは孤立していない。§4 dual を介した 3 本の接続が存在する。

#### Arrow 1: Scan → Structural（定義域構造）

Scan observable は常に次の形を取る:

    O(scanner) = Σ_{d ∈ D} f(d) · exp(a(scanner) · b(d))

ここで **D** (data 空間) と **f** (算術/幾何関数) が structural observable を encoding する:

| Scan member | D (data 空間) | Structural observable encoded |
|---|---|---|
| K(τ) | x_j ∈ ℝ (unfolded eigenvalues) | b₁(G) = dim ker (rank deficiency of graph) |
| F(h) | r_j ∈ ℝ³/ℤ³ (atomic positions) | n_centering = \|L/L'\|, codim(s) |
| ζ(s) | n ∈ ℤ_{>0} | h_K (class group order), f_p(ρ) (Artin conductor) |
| Z(β) | E_n ∈ ℝ (energy levels) | degeneracy g(E_n) (integer multiplicity) |
| U(t) | spectral decomposition of A | dim(eigenspace) (integer multiplicity) |
| c(τ_cov) | g ∈ ℤ_{>0} (group elements) | group structure (order, conjugacy classes) |

**形式化**: Scan(scanner; D, f) の D と f を「読む」操作が structural observable を返す。Structural は Scan の **input specification**。

#### Arrow 2: Scan → Information（log-exp 双対）

Scan → Information の標準経路は **熱力学的 chain**:

```
partition sum:   G(scanner) = Σ_d f(d) · exp(a · b)        ← Scan
free energy:     F(scanner) = -log G(scanner)               ← log (bridge)
entropy:         S = -∂F/∂(scanner)|_{natural}              ← Information
```

具体例:

| Scan | G(scanner) | F | Information observable |
|---|---|---|---|
| Z(β) | Σ e^{-βE} | -kT log Z | S(ρ) = -Tr(ρ log ρ) via Legendre transform |
| ζ(s) | Σ n^{-s} | -log ζ(s) | von Mangoldt Λ(n) via -ζ'/ζ (logarithmic derivative) |
| K(τ) | \|Σ e^{2πiτx}\|² | -log K(τ) | rate function (large deviation) |

**形式化**: Information = -∂/∂(scanner) log Scan。log が Scan と Information の **bridge operator**。S13 の ln 2 は、この bridge 上の parity 固定点 (log(1/2) = -ln 2)。

#### Arrow 3: Structural → Information（combinatorial counting）

Structural → Information の接続は **Hartley entropy** (Rényi α=0):

    H_0(D) = log |D|

D の cardinality (structural) の対数 (information)。

| Structural | |D| | H_0 = log |D| | 意味 |
|---|---|---|---|
| n_centering | n | log n | centering 1 点あたりの情報量 |
| h_K | class number | log h_K | 類群の情報容量 |
| dim V^{I_i} | fixed subspace dim | log dim | ramification 1 段の freedom |

**形式化**: Information = log(Structural)。Structural が「いくつあるか」を数え、Information が「何 bit か」を答える。

#### 3 本の Arrow の整合

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

3 本の arrow は可換: Scan の定義域 D (Structural) の cardinality の log = Scan の trivial scanner limit での entropy。

具体例: Z(β→0) = Σ_n 1 = |{states}| (degeneracy count = Structural)。S(β→0) = log |{states}| = H_0 (Hartley = Information)。

**可換性の条件**: scanner → 0 (or ∞) の extreme limit で Scan が D の cardinality に退化するとき成立。これは exponential kernel が trivial limit で counting function に退化することの帰結。

### §5.6 S12/S13/S14 整合性 — formal verification (2026-04-11)

S15 の 3 分類の中で S12–S14 がどこに residence するかを確定する。

#### S12: Scan 層の定義

S12 = Scan 層の catalog。S15.Scan は S12 を包含する形で定義されている。整合は自明 (tautological)。

#### S13: Arrow 2 上の固定点

S13 の半値条件 e^{-x} = 1/2 ⟹ x = ln 2 を S15 で追跡:

| 層 | ln 2 の現れ方 | 根拠 |
|---|---|---|
| Scan (乗法) | scanner 値: kernel = 1/2 となる位置 | S13 statement |
| Information | H(1/2) = ln 2 (Shannon binary entropy) | c_information_theory.md §1 |
| Arrow 2 | log(e^{-ln2}) = log(1/2) = -ln 2 → 同定 | §5.5 log bridge |

**S13 は Scan 層内の statement ではなく、Arrow 2 (Scan → Information) 上の cross-layer 固定点**。ln 2 が至る所に出る理由: Scan ↔ Information の bridge 上の固定点であり、どちらの層から見ても同じ値が見える。

#### S14: Scan 層内 vs Arrow 2 の residence 差

| 定数 | S15 residence | 機構 |
|---|---|---|
| π | Scan 層内部 (加法軸) | S¹ torsion ι_2(1) = e^{iπ} = -1。群構造だけで決定 → **代数的** |
| ln 2 | Arrow 2 上 (Scan → Information bridge) | 半値条件 + log bridge。値域の順序構造が必要 → **解析的** |

**S14 の非対称性 (代数 vs 解析) = S15 の residence 差 (層内 vs 層間)**:

```
π:    Scan(加法) ── 内部固定点 ── 代数的 (torsion, 群論的)
ln 2: Scan(乗法) ── Arrow 2 ──→ Information ── 解析的 (log bridge, 順序論的)
```

非対称が「本質的」(S14 Guard 4 で確認済) な理由: Scan 層内の固定点は群の torsion (代数的構造) で決まり、Arrow 2 上の固定点は log の単調性 (順序構造) で決まる。この 2 つは異なる数学的機構であり、S15 の層構造が非対称を **強制** する。

#### §4 dual → S15 の対応

| §4 の構成要素 | S15 での residence | 帰結 |
|---|---|---|
| ι_L (加法準同型) | Scan 層 (加法軸) | additive scan kernel を定義 |
| χ (乗法指標) | Scan 層 (乗法軸) + Arrow 2 | multiplicative scan + L-function log-derivative → Information |
| ℂ* = S¹ × ℝ_{>0} | 3 層の ambient | S¹ = Scan (加法), ℝ_{>0} = Arrow 2 domain, log ℝ = Information |

§4 の「ℂ が共通受け皿」= S15 の「3 層が ℂ* 内で合流」。ℂ* の polar decomposition z = |z|e^{iθ} が S15 の 3 層を生む: arg (Scan 加法), |·| (Scan 乗法 → Arrow 2), log|·| (Information)。

#### 判定

S12/S13/S14 は S15 の 3 分類 + Arrow 構造の中で矛盾なく residence が確定する。特に S13/S14 は単一層に収まらず、Arrow 2 を跨ぐ cross-layer statement であることが明らかになった。**条件③ CLOSED** ✓

---

## §6 新ドメイン検討 Protocol (S15 準拠)

新しいドメインまたは observable を辞書に追加する際の標準手順。§4.2 の 4 問を S15 の 3 分類で再構成。

### Step 0: §4 dual の射影を同定

- そのドメインの加法構造は何か? (周期性, 格子, 群加法)
- 乗法構造は何か? (積, 分解, 指数減衰)
- Bridge (ℂ 上の共通受け皿) は何か?

### Step 1: Scan observable の同定

- exp(a(scanner)·b(data)) kernel が書けるか?
- 書ける場合: 加法 scan (虚軸) か 乗法 scan (実軸) か?
- S12 の既存 6 member のどれに対応するか? 新 member か?

### Step 2: Structural observable の同定

- Parameter-free 整数/位相的不変量は何か?
- Scan の data 空間 D の構造 (次元, 位数, rank) を列挙
- 既存の structural observable (b₁, h_K, codim, n_centering) との対応

### Step 3: Information observable の同定

- Scan の log-derivative chain で何が出るか? (free energy → entropy)
- Hartley entropy log|D| は何を意味するか?
- 既存の information observable (H, S, D_KL) との対応

### Step 4: 層間接続の検証

- Arrow 1 (Scan → Structural): D と f が structural を encoding しているか?
- Arrow 2 (Scan → Information): log-derivative chain が well-defined か?
- Arrow 3 (Structural → Information): log cardinality が意味を持つか?
- 可換性: scanner extreme limit で 3 本が閉じるか?

### Step 5: S13/S14 との接続

- 乗法 scan member がある場合: 半値条件 e^{-x} = 1/2 は何を意味するか?
- S14 の非対称 dual pair はどう現れるか?

### Step 6: 判定

- 3 分類の全てに 1 つ以上の observable があれば: **完全ドメイン**
- Scan のみ or Structural のみ: **部分ドメイン** (欠けている層を明示)
- 3 分類のいずれにも入らない observable がある場合: **S15 反例候補** → 3 分類の修正を検討

---

---

## §7 Post-v0 updates — 3 Arrow canonical constants 完備 (2026-04-23)

本 note は 2026-04-10 作成、S12-S14 (Arrow 1/2 residence) を確定した
段階の research root。その後 S17 (Arrow 3 e-extremum) + L0 v2
(2-axis framework) + OQ-Ω-Obs-4a (refined quantum Hodge) が ESTABLISHED
され、本 note の framework が定数レベル 3/3 完備に拡張された。

### §7.1 S17 ESTABLISHED — Arrow 3 residence 完備 (2026-04-23)

**§5 Arrow residence map の Arrow 3 列**が S17 ESTABLISHED で埋まった:

| Arrow | Bridge | Canonical constant | residence form | Status |
|---|---|---|---|---|
| Arrow 1 | Scan → Structural | **π** (S¹ torsion) | 代数的 parity | ESTABLISHED (S14 加法軸) |
| Arrow 2 | Scan → Information | **ln 2** (half-value e^{-x}=1/2) | 解析的 parity, value-fixed | ESTABLISHED (S13) |
| Arrow 3 | Structural → Information | **e** (info density max, d(n)=log n/n) | derivative-fixed extremum | **ESTABLISHED (S17, 2026-04-23)** |

S13 (value-fixed, level-set crossing) と S17 (derivative-fixed, extremum)
は **format shift** を伴うが、「Arrow 上の scalar-valued functional の
stationary point」で統一される。詳細:
- research/oq_omega_obs_3_e_arrow3_v0.md (S17 RESOLVED)
- c_arrow_bridge_constants.md §5 (Arrow 3 primary reference)
- Paper D §4.5 "S13/S14/S17 residence" + §4.5.0 format shift

### §7.2 L0 v2 ESTABLISHED — 2-axis framework での再読み (2026-04-23)

本 note の "bidirectional duality = 加法/乗法" (axis-1 D/C) に **axis-2
Finite/Infinite (Fi/I)** が直交 axis として追加された (OQ-L0-refinement
v1 ESTABLISHED)。2-axis framework で:

- **Scan** class = axis-1 C (continuous scanner), axis-2 Fi-Finite (有限 window
  / truncated kernel) or I-Infinite (analytic continuation 全域)
- **Structural** = axis-1 D (integer invariants), axis-2 Fi (具体 computation)
  or I (abstract universal class)
- **Information** = axis-1 C, axis-2 Fi (empirical truncated) or I
  (thermodynamic limit)

観測 = axis-2 **I → Fi traversal** (片方向 Arrow)。§5 で示した S13/S14
residence は axis-2 lens で refine 可能 (I+C 閉じ込め vs Fi/I bridge)。
詳細: research/oq_l0_refinement_finite_infinite_2axis_v0.md (ESTABLISHED),
Paper D §2.3.1 L0 v2。

### §7.3 OQ-Ω-Obs-4a ESTABLISHED — 量子 Hodge refined form (2026-04-23)

本 note §5 で提示した Arrow 1 (Scan → Structural) の quantum lift が、
refined narrower algebraic class (Stabilizer / Gaussian / Eff-sim /
Bell-local) で定理化された:

- **Theorem 4a.1 (unified f_rational via class infidelity)**: 各 class C
  に対し $M_{unified}^C := -\log_2 F_C$ (Uhlmann fidelity to class closure)
  が vanishing / positivity / gauge-inv / monotone の 4 条件を満たす。
  4 class 全て **log₂-bit 統一単位系** で scale-bridging formal closure。
- **Axis-2 Fi/I root-level connection** (L0 v2 の具体 instance): 量子
  4 sources = Fi 側 discrete pinned, 古典 Hodge source = I 側 continuous
  境界滲み — 古典/量子 f_rational asymmetry の root cause identify。

詳細: research/oq_omega_obs_4a_refined_quantum_hodge_v0.md (ESTABLISHED,
6/6 gate), c_arrow_obstruction.md §10.7.4/4a/5, Paper D §8.2。

### §7.4 本 note の位置づけ

本 note は **S15 (Observable Trichotomy) の research root** として
2026-04-10 時点の snapshot。その後 S17 + L0 v2 + OQ-Ω-Obs-4a が
派生し、本 note の framework が拡張された形。§7 は post-v0 update
index として機能、詳細は各 downstream document へ。

---

*作成日: 2026-04-10 (§5: 2026-04-11, §5.5/§5.6/§6: 2026-04-11)*
*作成トリガー: S14 Guard 4 分析後のユーザー insight — 「やってたのは加法⇔乗法の双方向近似だった」*
*§7 post-v0 update: 2026-04-23 (S17 + L0 v2 + OQ-Ω-Obs-4a triple ESTABLISHED)*
