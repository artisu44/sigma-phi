---
axis: A
position: algebra_analysis
static_dynamic: static
connected_to:
  - A.harmonic_analysis
  - A.algebra_constraint
  - B.L1_fiber
  - B.crystal
  - B.fx
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-10
structural_role: root  # §4 = dictionary structural root (S12/S13/S14 源泉)
---

# ℤ ↔ S¹ 二重準同型と ℂ の必然性

**Level**: L1 (pure mathematics, domain-independent)
**Dependencies**: None (foundational)
**Downstream**: L1/nt_conductor.md §4.1, L1/c_scaling_laws.md §1.4, L1/c_theorems_master.md (T1,T8,S12,S13,S14), L2/crystal, L2/FX, L3/correspondence_table, research/tau_internal_coordinate_v0.md (§4.4), research/bidirectional_duality_v0.md (§2 双対表)

---

## §1 動機：加法と乗法を同時に保持する体

整数論の構造を連続的に表現するには、次の2つの操作を **同時に** 保持する写像が必要である：

1. **加法** n + m（整数の和、周期構造、フーリエ解析）
2. **乗法** n × m（整数の積、素因子分解、ディリクレ指標）

実数体 ℝ は加法群 (ℝ, +) と乗法群 (ℝ_{>0}, ×) を持ち、exp: (ℝ, +) → (ℝ_{>0}, ×) で繋がるが、ℝ* の有限位数の元は {±1} のみである。したがって、有限巡回群 ℤ/Lℤ の構造（特に L 次単位根）を乗法側に埋め込むことができない。

ℂ はこの障害を解消する最小の体である。ℂ* は任意の有限位数の元 e^{2πi/L} を含み、加法的周期性を乗法的位相として表現できる。

本項ではこの「二重準同型」構造を明示的に構成し、ΣΦ 理論全体がこの構造に依存していることを示す。

---

## §2 加法側準同型 ι_L

### 定義

L を正整数とする。**加法側準同型** ι_L を次のように定義する：

    ι_L : ℤ/Lℤ  →  S¹ ⊂ ℂ*
    n    ↦  e^{2πin/L}

### 基本性質

1. **準同型**: ι_L(n + m) = ι_L(n) · ι_L(m)。加法を乗法に変換する。
2. **核**: ker(ι_L) = Lℤ（mod L で 0 になる元のみ）。
3. **像**: im(ι_L) = μ_L = {ζ ∈ ℂ* : ζ^L = 1}（L 次単位根群）。
4. **同型**: ι_L は ℤ/Lℤ ≅ μ_L を誘導する（有限巡回群の忠実表現）。

### 加法→乗法変換の定理化

**Theorem (加法-乗法変換)**:
ι_L は ℤ/Lℤ の加法構造を S¹ の乗法構造に **忠実に** 翻訳する唯一の（生成元の像を固定した上での）単射準同型である。

*証明*: ℤ/Lℤ は巡回群であり、準同型は生成元 1 の像 ι_L(1) = e^{2πi/L} で完全に決定される。ker = Lℤ より単射。μ_L が位数 L の巡回群であることから全射。■

**重要**: この変換において、加法的な「距離」(n - m) mod L は乗法的な「角度差」2π(n-m)/L に写る。整数の算術的構造が、S¹ 上の幾何学的構造として現れる瞬間がここである。

### §2.1 Canonical Example: $L = 7$ ($\mathbb{Z}/7\mathbb{Z}$ の $\iota_7$)

**選定理由**: $L = 7$ は素数かつ $\geq 3$。$(\mathbb{Z}/7\mathbb{Z})^* = \mathbb{Z}/6\mathbb{Z}$ が巡回群で指標理論がクリーン。$\mathbb{R}$ では表現不可能（§7 の最小性実証）。全値を目視確認可能な最小の非自明サイズ。

**$\iota_7$ の全値**:

| $n$ | $\mathrm{Re}(\iota_7)$ | $\mathrm{Im}(\iota_7)$ | $\arg/2\pi$ |
|---|---|---|---|
| 0 | $1.000$ | $0.000$ | $0$ |
| 1 | $0.623$ | $0.782$ | $1/7$ |
| 2 | $-0.223$ | $0.975$ | $2/7$ |
| 3 | $-0.901$ | $0.434$ | $3/7$ |
| 4 | $-0.901$ | $-0.434$ | $4/7$ |
| 5 | $-0.223$ | $-0.975$ | $5/7$ |
| 6 | $0.623$ | $-0.782$ | $6/7$ |

全て $|\iota_7(n)| = 1$（$S^1$ 上）。$\iota_7(1) = \omega_7$ は primitive 7th root of unity。

**数値検証** (research/canonical_z7_iota.py):

| 検証項目 | 結果 | 残差 |
|---|---|---|
| 準同型性: $\iota_7(n+m) = \iota_7(n) \cdot \iota_7(m)$ | PASS | $< 10^{-15}$ |
| DFT ユニタリ性: $H_7 H_7^* = I$ | PASS | $< 10^{-14}$ |
| Pontryagin 直交性: $\langle \chi_k, \chi_l \rangle = 7 \delta_{k,l}$ | PASS | $< 10^{-13}$ |
| $\tau$-正規化: $\iota_7(n) = e^{2\pi i \cdot \tau(n)}$, $\tau(n) = n/7$ | PASS | exact |
| S16 Fejér 一致: $K(\tau) = F_7(\tau)$ (等間隔スペクトル) | PASS | $< 10^{-13}$ |

**Dirichlet 指標群**: $(\mathbb{Z}/7\mathbb{Z})^* \cong \mathbb{Z}/6\mathbb{Z}$（原始根 $g = 3$: $3^k \bmod 7 = [3,2,6,4,5,1]$）。6 個の Dirichlet 指標 $\chi_0, \ldots, \chi_5$ で位数 $\{1, 6, 3, 2, 3, 6\}$。

**$\mathbb{R}$ 不十分性の直接実証**: $\omega_7 = 0.623 + 0.782i \notin \mathbb{R}$。$\mathbb{R}^*$ の有限位数元は $\{\pm 1\}$ のみ。$L \geq 3$ では $\mu_L \not\subset \mathbb{R}^*$ であり、$\iota_L$ は $\mathbb{R}$ 内に構成不可能。→ §7 の $\mathbb{C}$ 最小性の数値実証。

---

## §3 乗法側準同型 χ

### 定義

L を正整数とする。**ディリクレ指標** χ を次のように定義する：

    χ : (ℤ/Lℤ)*  →  S¹ ⊂ ℂ*

ここで (ℤ/Lℤ)* = {n ∈ ℤ/Lℤ : gcd(n, L) = 1} は mod L の乗法群（既約剰余群）。

### 基本性質

1. **準同型**: χ(nm) = χ(n) · χ(m)。乗法を乗法に保存する。
2. **有限位数**: χ(n)^{φ(L)} = 1（全ての χ(n) は φ(L) 次以下の単位根）。
3. **直交性**: Σ_{n ∈ (ℤ/Lℤ)*} χ₁(n) χ₂(n)* = φ(L) · δ_{χ₁,χ₂}。

### 指標群の自己双対性

**Theorem (有限アーベル群の自己双対)**:
((ℤ/Lℤ)*)^ ≅ (ℤ/Lℤ)* （非カノニカル同型）。

指標群 ((ℤ/Lℤ)*)^ は (ℤ/Lℤ)* と同じ群構造を持つ。すなわち、指標の数は φ(L) 個であり、各指標 χ_k は (ℤ/Lℤ)* の元を S¹ に送る。

この自己双対性は §5 の Pontryagin 双対の有限版であり、ΣΦ の DFT 構造の代数的根拠となる。

---

## §4 二重構造の整合：ℂ は共通受け皿（辞書の structural root）

> **Structural Root Declaration (2026-04-10)**:
> 本節 §4 は ΣΦ 辞書全体の structural root である。S12 (Exponential Scan Family) の加法/乗法分類、S13 (ln 2 固定点)、S14 (π/ln 2 非対称 duality) は全て本節の ι_L/χ dual から派生する。辞書の各層 (L0–L3) は本節の双対構造の異なる射影を記述している。
> - L0: 位相/振幅分離 = arg/|·| = 加法/乗法の polar 射影
> - L1: 双対構造の数学的記述 (本ファイル, spectral, scaling_laws 等)
> - L2: 双対構造のドメイン固有射影 (FX, Crystal, EEG 等)
> - L3: クロスドメインでの双対構造の合流 (情報理論, 因果推論 等)
>
> 参照: research/bidirectional_duality_v0.md (meta-structure 観察)

### 核心命題

§2 の ι_L と §3 の χ は、異なる代数的源泉（加法 vs 乗法）から出発しながら、**同じ S¹ ⊂ ℂ*** に着地する。これは偶然ではない。

**Theorem (共通受け皿)**:
ℂ は次の2条件を同時に満たす最小の位相体である：

(i) 加法群 ℤ/Lℤ の忠実表現空間を含む（任意の L について μ_L ⊂ ℂ*）。
(ii) 乗法群 (ℤ/Lℤ)* の指標群の値域を含む（全ての χ が ℂ* に値を取る）。

*ℝ が不十分な理由*: ℝ* の有限位数の元は {±1} のみ。L ≥ 3 のとき μ_L ⊄ ℝ* であり、条件 (i) を満たさない。

### 数論的意味

この整合が意味するのは、**フーリエ解析**（加法構造の分解）と **L-関数理論**（乗法構造の分解）が同じ ℂ の中で合流するということである。

具体的には：
- **DFT**: H_{jk} = (1/√L) · ι_L(jk) = (1/√L) · e^{2πijk/L}。加法側の ι_L が行列要素を定める。
- **L-関数**: L(s, χ) = Σ_{n=1}^∞ χ(n) n^{-s}。乗法側の χ が係数を定める。
- 両者が S¹ ⊂ ℂ* に値を取ることで、**同一の解析的枠組み**（複素解析）で統一的に扱える。

### ΣΦ における帰結

ΣΦ の観測量は常に次の形を取る：

    observable = |Σ_n f(n) · e^{2πi·phase(n)}|² / normalization

ここで e^{2πi·phase(n)} は §2 の ι_L の一般化であり、f(n) は算術関数（しばしば §3 の χ と関連する）。加法側の位相構造と乗法側の算術構造が **同じ ℂ の中で干渉する** ことが、観測量が非自明な構造を持つ根本的理由である。

### τ-scan は Fourier 座標を内蔵する (S16)

**S16 (Fourier Absorption Principle, CANDIDATE 2026-04-11)**:
τ_scan (c_spectral.md §1) は上記の add↔mult 架橋を **座標構造に内蔵** している。

ℤ格子（古典座標）では加法構造と乗法構造は独立であり、両者の架橋には **明示的な変換** (Fourier, Laplace, Boltzmann, Dirichlet etc.) が必要。τ-scan 座標では、この架橋が走査操作に吸収される:

```
ℤ格子:  x_j (加法的差分) → [明示的 Fourier 変換] → e^{2πikx_j} (乗法的位相)
τ座標:  x_j → exp(2πi·τ·x_j) — τ を動かす行為自体が Fourier 解析
```

**数値検証** (research/tau_absorption_verify.py):
- 等間隔スペクトル (調和振動子 E_n = n+1/2) に対して K(τ) = Fejer kernel が **厳密に一致** (残差 < 10^{-13})
- 非等間隔スペクトル (水素原子 E_n = -1/n²) に対して K(τ) は Fejer から系統的に偏差 → 非等間隔性を **spectral fingerprint** として encode

**吸収されるもの** (= τ の定義に内蔵):

| 古典的変換 | τ座標での対応 | 吸収度 |
|---|---|---|
| Fourier e^{2πikx} | τ-scan の定義そのもの | 完全 (等間隔で exact) |
| Boltzmann e^{-βE} | τ-scan の Wick rotation (τ → -iβ/2π) | 構造同型 |
| Dirichlet n^{-s} | log-scale τ-scan (e^{-τ·log(n)}) | log変換 1 操作 |

**吸収されないもの**: 力学 (t 側)、境界条件 (W 側)、対称性群の分類 (群そのもの)

§4 の「ℂ が共通受け皿」を座標レベルで言い直すと: **τ は ℂ 内の add↔mult 架橋を座標に焼き込んだ scanning parameter** であり、辞書の observable = |Σ f(n) e^{2πi·phase(n)}|² は τ-scan の K(τ) の重み付き版に他ならない。

詳細: research/tau_vs_integer_lattice_v0.md。OQ-TI-2 (完全吸収の条件) は同 §8 で open。

---

## §5 Pontryagin 双対と c_s² = 1/2 への伏線

### Pontryagin 双対の明示的構成

有限アーベル群 G = ℤ/Lℤ に対し、Pontryagin 双対群は：

    Ĝ = Hom(G, S¹) ≅ ℤ/Lℤ

同型の明示的構成：k ∈ ℤ/Lℤ に対し χ_k(n) := e^{2πink/L} と定義すれば、χ_k ∈ Ĝ であり、k ↦ χ_k は群同型 ℤ/Lℤ → Ĝ を与える。

### DFT との関係

DFT 行列 H = (H_{jk})_{j,k=0}^{L-1} の各行は：

    H_{j,·} = (1/√L) · (χ_j(0), χ_j(1), ..., χ_j(L-1))

すなわち、**DFT の各行は Pontryagin 双対群の元** である。DFT が直交行列であることは、指標の直交関係（§3）の行列版に他ならない。

これが ΣΦ Paper A の H 行列定義の代数的根拠である。

### ゲージ不変性との接続

ΣΦ のゲージ不変性（Paper B）は、Pontryagin 双対の以下の性質から従う：

    Σ_{n ∈ ℤ/Lℤ} χ_k(n) = L · δ_{k,0}

k ≠ 0 のとき指標値の総和が消えることは、**位相の一様回転に対して観測量が不変**であることを意味する。これは ΣΦ の公理 A3（ゲージ不変性）の数学的実体である。

### c_s² = 1/2 への伏線

Pontryagin 双対の構造から、**半整数並進** t = (t₁, ..., t_d) に対する干渉因子が決定される。centering 並進 t が半整数成分を持つとき：

    1 + e^{2πi h·t}  ∈  {0, 2}    (h·t が半整数 or 整数)

この因子の二乗平均は：

    c_s² := E[cos²(π h·t)] = 1/2

なぜなら、h が整数を走るとき h·t は整数と半整数を **等確率で** 取るからである（整数の偶奇等分配）。

この c_s² = 1/2 は T1 の直接的帰結であり、T8 の Boltzmann codim 重み exp(-c_s² · codim) = exp(-codim/2) の源泉である。**Pontryagin 双対の自己双対性が、整数の偶奇対称性を通じて、理論の基本定数 c_s² = 1/2 を確定する**。

（完全な導出は L1/c_theorems_master.md T1, T8 を参照。）

### log 2 = ℤ/2ℤ の Shannon エントロピー

c_s² = 1/2 と同じ ℤ/2ℤ 一様測度から、もう一つの基本定数が生じる。偶奇等確率 p_even = p_odd = 1/2 に対する Shannon エントロピーは：

    H(1/2) = -Σ p_k log p_k = -(1/2)log(1/2) - (1/2)log(1/2) = log 2

ここで log は自然対数。

**c_s² と log 2 の関係**:
- c_s² = 1/2 は ℤ/2ℤ 一様測度の **確率値**（Born 期待値、線形スケール）
- log 2 は同じ測度の **情報量**（Shannon エントロピー、対数スケール）
- 両者は同一の源泉（偶奇対称性）から生じるが、異なる量を測る

**ΣΦ における帰結**:
- c_s² → T8 の Boltzmann codim weight: exp(c_s²) = √e（c_scaling_laws.md §1.4）
- log 2 → qubit の von Neumann エントロピー: S(ρ_max) = log 2（q_quantum_observation.md §7 との接続）
- log 2 → 位相ノイズ閾値: σ* = √(2 log 2)（physics_constants_decomposition.md §2.1、導出確認。ガウス特性関数 + half-amplitude convention (E[cos Z]=1/2)。具体値は閾値選択に依存する点に注意。q_quantum_thermodynamics.md OQ-QTD3）

log 2 は c_s² = 1/2 と **双子** の定数であり、確率的側面を c_s² が、情報的側面を log 2 が担う。

---

## §6 τ-正規化との接続

### τ の定義

ΣΦ の正規化座標 τ は次のように定義される：

    τ : ℤ  →  [0, 1)
    n  ↦  (n mod L) / L

ここで L は基本周期（ΣΦ の文脈では L = XY）。

### §2 の ι_L との関係

τ と ι_L は偏角を介して直結する：

    ι_L(n) = e^{2πin/L} = e^{2πi·τ(n)}    (∵ n mod L = τ(n)·L)

すなわち：

    τ(n) = arg(ι_L(n)) / 2π

### 連続極限

L → ∞ の極限で、τ は [0,1) 上の一様分布に近づく。§2 の離散的な μ_L（L 点の単位根格子）が S¹ 全体を稠密に埋め尽くす過程が、τ の連続化に対応する。

    L 有限:  τ ∈ {0, 1/L, 2/L, ..., (L-1)/L}  ↔  μ_L ⊂ S¹
    L → ∞:   τ ∈ [0, 1)                          ↔  S¹ 全体

### ΣΦ ネイティブ座標における観測

ΣΦ の枠組みでは、「観測」は次のように定式化される：

> **有限観測者は整数 n を数えるが、観測の位相構造は τ(n) ∈ S¹ として現れる。**

整数の離散性と位相の連続性を架橋するのが τ-正規化であり、これは §2 の ι_L を「偏角座標で読む」操作に他ならない。§4 で述べた「加法構造と乗法構造の合流点」が、ΣΦ では τ 座標上で実現される。

---

## §7 ℂ の最小性

### 主張

加法群 (ℤ/Lℤ, +) と乗法群 ((ℤ/Lℤ)*, ×) の**両方**の忠実表現を含む位相体のうち、ℂ は最小である。

### ℝ が不十分な理由（再掲・精密版）

ℝ* の有限部分群は {1} と {±1} のみ。これは ℝ* ≅ {±1} × ℝ_{>0} であり、ℝ_{>0} は torsion-free（有限位数の元が単位元のみ）であることによる。

したがって L ≥ 3 のとき、μ_L の忠実表現は ℝ* 内に構成できず、ι_L が定義できない。exp: ℝ → ℝ_{>0} は加法→乗法の準同型を与えるが、**周期性を持たない**（ker = {0}）。

### ℂ が十分な理由

ℂ* ≅ S¹ × ℝ_{>0} であり、S¹ は任意の有限巡回群 ℤ/Lℤ を部分群として含む（μ_L ⊂ S¹）。exp: ℂ → ℂ* は **周期 2πi** を持ち、ker = 2πiℤ。この周期性が有限位数の元の存在を保証する。

### 他の候補への備考

**四元数 ℍ**: 非可換体。ℍ* は S³ を含み、単位根は存在するが、**指標理論（§3）が崩壊する**。有限アーベル群の指標は可換体への準同型として定義されるため、ℍ は §3 の受け皿になれない。

**p-進体 ℂ_p**: 代数的閉包かつ完備だが、通常の位相（p-進距離）は S¹ の位相と両立しない。DFT の直交性は **ユニタリ性**（|e^{iθ}| = 1 がアルキメデス的絶対値で成立）に依存しており、p-進絶対値ではこれが保証されない。

*注*: ℂ の一意性をカテゴリ論的に厳密に特徴づけるには Gelfand-Mazur の定理（ℝ 上の Banach 代数の枠組み）が必要だが、ΣΦ の L1 で必要なのは上記の最小性のみである。完全な一意性証明は L2 以降の課題とする。

---

## §8 後続参照マップ

本項（ℤ ↔ S¹ 二重準同型）は以下の L1-L4 項目の基盤である：

### L1 内部参照

| 項目 | 依存する節 | 依存内容 |
|---|---|---|
| `c_theorems_master.md` T1 | §2, §5 | centering extinction = ι_L の核の構造 |
| `c_theorems_master.md` T8 | §5 | c_s² = 1/2 = Pontryagin 双対の偶奇対称性 |
| `c_theorems_master.md` S12 | §4, §6 | exponential scan family: additive/multiplicative dual kernels share ℂ receptacle |
| `c_theorems_master.md` S13 | §4 | ln 2 固定点 = §4 乗法 scan の半値条件 |
| `c_theorems_master.md` S14 | §4 | π/ln 2 非対称 duality = §4 ι_L(代数)/χ(解析) dual の parity 射影 |
| `q_quantum_observation.md` §7 | §5 (log 2) | S(ρ_max) = log 2 = qubit von Neumann エントロピー |
| `q_open_quantum_systems.md` §3.3 | §5 (log 2 双子) | Shannon↔von Neumann 回収、decoherence 経由の c_s²=1/2 生成 (OQ-OQS3) |
| `q_open_quantum_systems.md` §5.4 | §5 (c_s²) | 3レベル導出: 代数的/量子的/動的の合流点 |
| `physics_constants_decomposition.md` §2 | §5 (c_s², log 2) | Type I 定数の源泉としての ℤ/2ℤ |
| `nt_conductor.md` §4.1 | §2 | FX centering coherence = ι_L の FX 翻訳 |
| `c_scaling_laws.md` §1.4 | §4 | DFT 構造 = 加法側 ι_L の行列版 |
| `c_group_theory.md` §1 | §2 | centering 準同型 = ι_L の特殊化 |

### L2 ドメイン参照

| 項目 | 依存する節 | 依存内容 |
|---|---|---|
| `crystal_dictionary_v1.md` | §2, §5 | 構造因子 F(hkl) = Σ f_j · ι_L(h·r_j) |
| FX dictionary (v4) | §3, §4 | 対数価格 = 加法群、為替レート = 乗法群 |
| `connectome_dictionary_v0.md` | §4 | 隣接行列の固有値 = S¹ 上のスペクトル |

### L3 クロスドメイン参照

| 項目 | 依存する節 | 依存内容 |
|---|---|---|
| `correspondence_table.md` | §4, §5 | 全ドメインが同じ S¹ に着地する理由 |
| `tau_internal_coordinate_v0.md` §4.4 | §4, §6 | scanner variable の family catalog (K(τ), F(h), ζ(s), Z(β), U(t), c(τ_cov)) |
| `three_phase_taxonomy.md` | §5 | c_s² = 1/2 がドメイン非依存である理由 |

### L4 エラー参照

| 項目 | 依存する節 | 依存内容 |
|---|---|---|
| `crystal_errors.md` ERR-C4 | §4 | CV が失敗する理由 = 加法/乗法の混同 |
| `FX_errors.md` ERR-F1 | §7 | べき則→シグモイド = ℝ 的近似の限界 |

---

*作成日: 2026-04-08*
*最終更新: 2026-04-08*
