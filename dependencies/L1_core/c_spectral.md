---
axis: A
position: harmonic_analysis
static_dynamic: static
connected_to:
  - A.algebra_analysis
  - B.crystal
  - B.fx
  - B.quantum_chemistry
  - D.electrophysiology
  - D.connectomics
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-08
runtime_summary:
  what: K(τ) スペクトルコヒーレンス + F(hkl) 構造因子 + unfolding + ζ spectral §7 + L-function 特殊値 (class number formula 6-gauge 分解) §8
  when: K(τ) / F(hkl) / spectral statistics / unfolding / Marchenko-Pastur / GUE / T7 / L-function 特殊値 / class number formula / Stark rank 0
  provides: [K_tau, structure_factor, unfolding, T7_spectral_form_factor, spectral_section_7_zeta, L_function_minimal_defs, class_number_formula, class_number_formula_6_gauge_decomposition, dedekind_zeta_special_value]
  consumes: [c_phase_complex.md, identity_asymmetry.md, omega/Paper_Omega_Origination.md]
  axis: [A]
  residual_types: [R-info, R-topo, R-gauge]
  cost: large
  status: established
  key_constants:
    - {name: rho_zeta_spectral, value: "ζ'(2)/√((1+ζ(2))ζ''(2)) = -0.4088", derived_in: "§7"}
    - {name: lambda2_over_lambda1, value: "(1+ρ)/(1-ρ) = 0.4196", derived_in: "§7"}
  key_theorems:
    - {id: T7, statement: "E[K(τ)] = (N_c² + N_s)/N for τ >> 1", derived_in: "§4"}
    - {id: class_number_formula, statement: "Res_{s=1} ζ_K(s) = (2^r₁ (2π)^r₂ h_K R_K)/(w_K √|d_K|); 6-gauge 積分解 (Paper_Ω 署名 {addZ,mult,char,cont,geom,anal} 全揃い)", derived_in: "§8.2-§8.3", status: established, cross_refs: [research/stark_projection_v0.md, omega/Paper_Omega_Origination.md §2.5]}
  one_screen: |
    §1 K(τ) := (1/N)|Σ exp(2πi·τ·x_j)|². coherent → N, random → 1.
    §2 F(hkl) = Σ f_j exp(2πi h·r_j). 結晶版 K(τ).
    §3 振幅 |H| × 位相 e^{iφ} 分解.
    §4 T7: E[K] = (N_c² + N_s)/N for τ ≫ 1. 構造ゼロが coherent cluster.
    §5 Unfolding (= τ-normalization): mean spacing 1 へ正規化.
    §6 Marchenko-Pastur baseline + 大域 spectral 不変量.
    §7 ζ spectral: ρ = ζ'(2)/√((1+ζ(2))ζ''(2)) = -0.4088 (正確、p→∞). Taylor 係数 statistical, 浅い.
    §8 Class number formula: Res ζ_K(1) = (2^r₁(2π)^r₂ h R)/(w √|d|). 6 因子 (π, 2, d, h, R, w) が Paper_Ω 全 gauge 署名 {addZ,mult,char,cont,geom,anal} に 1 対 1 対応. rank 0 Stark established. rank 1 abelian は research/stark_projection_v0.md へ橋渡し.
---

# スペクトル構造: K(τ), 構造因子, 形式因子

**Level**: L1 (pure mathematics, domain-independent)
**Dependencies**: c_phase_complex.md (ι_L, τ-normalization, ℂ* ≅ ℝ_{>0} × S¹)
**Downstream**: L1/c_scaling_laws.md §1.4 (T8), L1/c_theorems_master.md (T7), L2/crystal, L2/FX, L2/connectome

---

## §1 K(τ) の定義と動機

### 問題設定

有限個の実数値 {x_1, ..., x_N} が与えられたとき、その中に **周期的構造** が存在するかを検出したい。ランダムな点列と構造的な点列を区別する統計量が必要である。

### 定義

スケールパラメータ τ > 0 に対し、**スペクトルコヒーレンス** K(τ) を次のように定義する：

    K(τ) := (1/N) |Σ_{j=1}^{N} e^{2πi·τ·x_j}|²

### c_phase_complex.md との関係

この定義は c_phase_complex.md §2 の加法側準同型 ι_L の連続版である。ι_L は離散的な ℤ/Lℤ を S¹ に送ったが、K(τ) は実数値の点 x_j を S¹ に射影し、その **コヒーレンス**（位相の揃い具合）を測る：

    e^{2πi·τ·x_j} ∈ S¹    (x_j の τ-スケールでの S¹ 射影)
    Σ_j e^{2πi·τ·x_j}      (S¹ 上のベクトル和 = コヒーレンス)
    K(τ) = |...|² / N       (正規化された強度)

### 基本的な振る舞い

- **完全コヒーレント**: 全 x_j が τ に対して同位相 → K(τ) = N（最大値）
- **完全ランダム**: 位相が S¹ 上一様 → K(τ) → 1（大数の法則、N → ∞）
- **構造的**: 一部がコヒーレント、残りがランダム → 1 < K(τ) < N

K(τ) が 1 を有意に超えるとき、スケール τ に周期構造が存在する。

---

## §2 構造因子 F(hkl)

### 定義

結晶学の構造因子は、原子位置 {r_j} と散乱因子 {f_j} に対して：

    F(hkl) := Σ_{j=1}^{N_atom} f_j · e^{2πi (h·r_j)}

ここで h = (h, k, l) は逆格子ベクトル（整数）、r_j は原子の分率座標である。

### §1 の K(τ) との代数的同型

F(hkl) と K(τ) は同一の代数的構造の異なる実現である：

| | K(τ) | F(hkl) |
|---|---|---|
| 入力点 | 実数 x_j (unfolded 固有値) | ベクトル r_j (原子位置) |
| パラメータ | 連続 τ ∈ ℝ_{>0} | 離散 h ∈ ℤ³ |
| 重み | 均等 (1/N) | 散乱因子 f_j |
| S¹ 射影 | e^{2πi·τ·x_j} | e^{2πi h·r_j} |
| 出力 | コヒーレンス強度 | 回折強度 |I(hkl)| = |F|² |

両者はともに **点配置の Fourier 変換** であり、c_phase_complex.md §2 の ι_L を一般化したものである。

### centering extinction の再導出

centering 並進 t (例: I centering で t = (1/2, 1/2, 1/2)) が存在するとき、各原子 j に対して r_j' = r_j + t も原子位置である。F(hkl) への寄与は：

    f_j · e^{2πi h·r_j} · (1 + e^{2πi h·t})

因子 (1 + e^{2πi h·t}) は c_phase_complex.md §5 で見た干渉因子そのものである。h·t が半整数のとき因子は 0 となり、F(hkl) = 0（系統消滅）。

これが c_group_theory.md §1 の centering extinction 定理の Fourier 的証明であり、K(τ) と F(hkl) が同じ代数的メカニズムで構造的零点を生むことを示す。

---

## §3 形式因子と振幅/位相分解

### 正規化された Fourier 係数

任意の counting measure μ = Σ_j δ(x - x_j) に対し、その Fourier 変換の正規化された係数を：

    H(k) := F̂(k) / κ(k)

と定義する。ここで F̂(k) = Σ_j e^{2πi·k·x_j} は非正規化 Fourier 係数、κ(k) は密度ベースラインの補正因子（null model からの期待値）。

### 振幅/位相分解

H(k) は複素数であるから：

    H(k) = |H(k)| · e^{iφ(k)}

と分解される。ここで：
- **振幅** |H(k)| ∈ ℝ_{≥0} — density structure（「どれだけ存在するか」）
- **位相** φ(k) ∈ (-π, π] — transition structure（「どの方向に偏っているか」）

### 独立性の代数的根拠

この分解が非自明なのは、|H| と φ が **独立な情報チャネル** であることによる。

ℂ* の直積分解 ℂ* ≅ ℝ_{>0} × S¹ は、ノルム（ℝ_{>0} 成分）と偏角（S¹ 成分）を代数的に分離する。c_phase_complex.md §4 で見たように、|H| は乗法構造（ノルム = 算術的振幅）に、φ は加法構造（偏角 = 位相干渉）に対応する。

この独立性は ℝ では実現できない。ℝ 値の Fourier 係数は符号（±1 ≅ ℤ/2ℤ）しか持たず、「振幅は大きいが位相がランダム」と「振幅は小さいが位相が整列」を区別できない。ℂ の S¹ 成分が連続的な位相空間を提供することで、振幅と位相が独立に変動できる（c_phase_complex.md §7、ℂ の最小性）。

### SVD による情報分解

H(k) を行列として配列したとき（行 = gap index 等、列 = Fourier index）、SVD は：

    H = U · Σ · V†

振幅情報は特異値 σ_i に、位相情報は U, V の列ベクトルに分離される。rank-1 支配比 ρ₁ = σ₁² / Σσ_i² が 1 に近いほど、振幅構造が単一モードに集中している。

具体的な gap index g の定義や計算式は domain-specific であり、L2 の各辞書に委ねる。

---

## §4 T7: クラスター平均定理

### 定理 (T7)

N 個の点のうち、N_c 個がスケール τ に対してコヒーレントクラスターを形成し、残り N_s = N - N_c 個がランダム位相を持つとき：

    E[K(τ)] = (N_c² + N_s) / N

ただし τ >> 1（cluster scale と random scale が十分分離している条件）。

### 導出

K(τ) の定義を展開する：

    N · K(τ) = |Σ_j e^{2πi·τ·x_j}|²
             = |Σ_{j∈C} e^{2πi·τ·x_j} + Σ_{j∈R} e^{2πi·τ·x_j}|²

ここで C = コヒーレントクラスター（|C| = N_c）、R = ランダム成分（|R| = N_s）。

**Step 1 (クラスター寄与)**:
C の N_c 点はスケール τ で同位相である。すなわち e^{2πi·τ·x_j} ≈ e^{iθ_0} for all j ∈ C。したがって：

    |Σ_{j∈C} e^{2πi·τ·x_j}|² = N_c²

位相が完全に整列しているため、ベクトル和の長さは N_c（constructive interference）。

**Step 2 (ランダム寄与)**:
R の N_s 点は S¹ 上で一様ランダム。ランダムウォークの期待値より：

    E[|Σ_{j∈R} e^{2πi·τ·x_j}|²] = N_s

各項の自己相関は 1、異なる項間の交差項は E[e^{i(θ_j - θ_k)}] = 0 で消える。

**Step 3 (交差項)**:
クラスターとランダム成分の交差項：

    E[2 Re(Σ_{j∈C} e^{iθ_j} · Σ_{k∈R} e^{-iθ_k})] = 0

ランダム成分の位相が一様であるため、交差項の期待値は消える。

**合計**:

    E[N · K(τ)] = N_c² + N_s
    E[K(τ)] = (N_c² + N_s) / N                                    ■

### 解釈

- N_c = 0 (全ランダム): E[K] = N/N = 1（null baseline）
- N_c = N (全コヒーレント): E[K] = N²/N = N（最大コヒーレンス）
- 中間: N_c² 項が支配的 → K(τ) はコヒーレントクラスターのサイズに **二次的に** 感度を持つ

二次依存性 N_c² は constructive interference の本質であり、位相整列がもたらす信号増幅を反映する。これは §1 の K(τ) 定義に内在する ℂ の構造（ベクトル和の長さ）から自然に導かれる。

### 振幅形式

T7 を振幅として書き直すと：

    amp := K(τ) - 1
         = (N_c² + N_s)/N - 1
         = (N_c² + N_s - N)/N
         = (N_c² - N_c)/N          (∵ N - N_s = N_c)
         = N_c(N_c - 1)/N

すなわち amp ∝ N_c² / N（N_c >> 1 のとき）。この振幅が conductor（制約の数）によってどう決まるかは c_scaling_laws.md §1.4 (T8) に委ねる。

---

## §5 Unfolding: 固有値版の τ-正規化

### 定義

観測された固有値 {ev_1 ≤ ev_2 ≤ ... ≤ ev_N} に対し、**unfolded 固有値** を：

    x_j := (ev_j - ev_min) / Δ

と定義する。ここで Δ = mean spacing = (ev_max - ev_min) / (N - 1)。

### τ-正規化との統一

Unfolding は整数の τ-正規化(c_phase_complex.md §6)と同じ操作を固有値に対して行う：

| | 整数 | 固有値 |
|---|---|---|
| 生データ | n ∈ ℤ | ev_j ∈ ℝ |
| 正規化 | τ(n) = (n mod L)/L | x_j = (ev_j - ev_min)/Δ |
| 値域 | [0, 1) (L-周期) | [0, N-1] (非周期) |
| S¹ 射影 | ι_L(n) = e^{2πi·τ(n)} | e^{2πi·τ·x_j} |
| 除去される構造 | 周期 L の大域的位置 | 平均固有値密度 |
| 残る構造 | 周期内の微細構造 | 密度からの偏差 |

両者に共通するパイプラインは：

    生データ → 正規化（大域構造の除去）→ S¹ 射影 → コヒーレンス計算

ΣΦ における「観測」はすべてこのパイプラインのインスタンスである。正規化の具体的な形（mod L, mean spacing, etc.）はドメインに依存するが、S¹ 射影以降の代数的構造は **ドメイン非依存** である。

### Null model

Unfolded 固有値に対する null model は：
- **FX**: Wishart(K, T) 行列の固有値 → K(τ) のベースライン = 1 + O(1/T)
- **Crystal**: P 格子（centering なし）→ abs = 0
- **Connectome**: Erdős-Rényi G(N, p) → φ_eff / φ(N)

Null からの乖離が「構造」であり、その乖離量が amp（§4 の振幅形式）として測定される。各ドメインの null model の詳細は L2 に委ねる。

---

## §6 辞書内参照の閉包

### chain: ι_L → DFT → K(τ) → T7 → T8

本項の内容は以下の chain で辞書全体を接続する：

```
c_phase_complex.md §2       ι_L : ℤ/Lℤ → S¹ (加法側準同型)
       ↓
c_phase_complex.md §5       DFT 行列 H の各行 = Pontryagin 双対群の元
       ↓
c_spectral.md §1            K(τ) = |Σ e^{2πi·τ·x_j}|²/N (ι_L の連続版)
       ↓
c_spectral.md §2            F(hkl) = Σ f_j e^{2πi h·r_j} (ι_L の結晶版)
       ↓
c_spectral.md §3            H = |H|·e^{iφ} (ℂ* ≅ ℝ_{>0} × S¹ の帰結)
       ↓
c_spectral.md §4            T7: E[K(τ)] = (N_c² + N_s)/N
       ↓
c_scaling_laws.md §1.4      T8: A/B = exp(c_s²) = √e (Boltzmann codim weight)
       ↓
c_phase_complex.md §5       c_s² = 1/2 (Pontryagin 双対の偶奇対称性)
```

最後のステップが c_phase_complex.md に戻ることで、L1 内部で **閉じた参照ループ** が形成される。§7 のゼータ関数公式はこの chain の外に位置する supplementary branch で、L0/identity_asymmetry.md と直接接続する。これは循環論法ではなく、異なる角度からの整合性確認である：
- c_phase_complex.md: **なぜ** ℂ が必要か（代数的必然性）
- c_spectral.md: **何を** ℂ で計算するか（K(τ), F(hkl), 形式因子）
- c_scaling_laws.md: **どう** 結果が組織化されるか（sigmoid, codim weight）

### T7 と T8 の居場所について

T7 と T8 は辞書の異なる層に住む：

| 定理 | 主題 | 層 | 居場所 |
|---|---|---|---|
| T7 | K(τ) の期待値（スペクトル量の構造定理） | spectral | c_spectral.md §4 |
| T8 | amp/conductor 関数形（scaling の決定因子） | scaling | c_scaling_laws.md §1.4 |

T7 は「K(τ) がなぜこの値を取るか」を答える **spectral の定理**。T8 は「その値が conductor とどう関係するか」を答える **scaling の定理**。chain で繋がるが、住所は異なる。

---

## §7 c-matrix 共分散のゼータ関数公式

### 動機

c-matrix c_{g,χ}(τ) = χ(g)·g^{-τ} の各エントリを 3D 実ベクトル (Re(c), Im(c), -log(g)·Re(c)) と見なしたとき、共分散行列の固有値比がゼータ関数の導関数で完全に決まる。

3番目の座標 -log(g)·Re(c) は τ に関する微分 d/dτ[Re(c)] であり、τ-正規化が整数の乗法構造に対して行う圧縮の痕跡を測る。

### §7.1 共分散の閉公式 (p → ∞)

指標直交性と |χ(g)|=1 から、τ > 1/2 において (p-1)² 個のエントリの共分散行列は対角ブロック構造を持つ：

    Var(Re)              = (1 + ζ(2τ)) / (2p)
    Var(Im)              = (ζ(2τ) - 1) / (2p)
    Var(-log(g)·Re)      = ζ''(2τ) / (2p)
    Cov(Re, -log(g)·Re)  = ζ'(2τ) / (2p)
    Cov(Re, Im) = Cov(Im, -log(g)·Re) = 0

各式の導出:
- g=1 は全指標で Re=1, Im=0, log(1)=0。Var(Re) への寄与は 1/(2p) であり、これが (1+ζ(2τ)) の "1" の起源（L0/identity_asymmetry.md §3.1）
- g ≥ 2 の寄与は指標直交性 (1/n)Σ_χ Re²(χ(g)) = 1/2 を用いて Σ_{g≥2} g^{-2τ}/2 = (ζ(2τ)-1)/2
- Cov と Var(3rd) の式は Σ_{g≥2} log(g)·g^{-2τ} = -ζ'(2τ)+0 および Σ_{g≥2} log²(g)·g^{-2τ} = ζ''(2τ) から

### §7.2 スペクトル相関

3番目の座標を std(Re) に正規化すると、3×3 相関行列は：

    |  1     0     ρ  |
    |  0     1     0  |
    |  ρ     0     1  |

ここで

    **ρ(τ) = ζ'(2τ) / √((1 + ζ(2τ)) · ζ''(2τ))**

これは p → ∞ で厳密。有限 p での補正は O(1/p²)。

### §7.3 固有値比

上記相関行列の固有値は λ₁ = σ²(1+ρ), λ₂ = σ²_Im, λ₃ = σ²(1-ρ) (ただしλ₂とλ₃の大小は τ に依存)。正規化後:

    **λ₂/λ₁ = (1 + ρ(τ)) / (1 - ρ(τ))**   (Re-3rd 面内の比)
    
    **Var(Im)/Var(Re) = (ζ(2τ) - 1) / (1 + ζ(2τ))**

τ=1 での値:

| 量 | 公式 | 数値 |
|---|---|---|
| ρ | ζ'(2)/√((1+ζ(2))·ζ''(2)) | -0.4088 |
| λ₂/λ₁ | (1+ρ)/(1-ρ) | 0.4196 |
| Var(Im)/Var(Re) | (π²/6 - 1)/(π²/6 + 1) = (π²-6)/(π²+6) | 0.2438 |

### §7.4 τ プロファイルと既知定数との交叉

ρ(τ) は τ ∈ (1/2, ∞) で単調増加:
- τ → 1/2⁺: ρ → -1 (ζ(1⁺) 発散、最大カップリング)
- τ = 0.795: ρ = -1/2 (λ₂/λ₁ = 1/3)
- τ = 1.000: ρ = -0.4088
- τ = 1.244: ρ = -1/3 (λ₂/λ₁ = 1/2)
- τ = 1.911: λ₂/λ₁ = 2/3
- τ → ∞: ρ → 0 (カップリング消滅)

停留点はない。τ=1 に特別な構造はない。

### §7.5 数論的位置づけ

この公式は乗法構造の圧縮測度を与える:

- 整数の素因子分解は π(N) 次元空間に住む (各素数 = 1 座標)
- τ-正規化 g^{-τ} はこれを log(g) = Σ aᵢ log(pᵢ) の 1D 射影に圧縮する
- ρ(τ) は「圧縮による相関注入量」を測る
- 圧縮の残差（log(g) で捕まらない乗法構造）は c-matrix の固有値を Δ(λ₂/λ₁) ≈ +0.28 動かす (tau_multiplicative_dim.py)

**評価**: 主定理 (T1-T8) と同格ではない。ζ の Taylor 係数の機械的組み合わせであり、数論的深さは I_phase=2/3 や c_s²=1/2 に及ばない。L1 observable catalog の supplementary item として記録。

### §7.6 検証スクリプト

- zeta_formula.py: τ=1 での導出と p={23,...,997} での検証
- rho_tau_general.py: τ 一般化、交叉点探索、停留点チェック
- tau_multiplicative_dim.py: 乗法構造の次元分解、残差の影響

---

## §8 L-function 特殊値と Class Number Formula (6-gauge 積分解)

### §8.0 動機と §7 との関係

§7 は c-matrix `c_{g,χ}(τ) = χ(g)·g^{-τ}` の共分散で ζ'(2τ) を機械的組み合わせとして現した (§7.5 自己評価「Taylor 係数の機械的組み合わせ、数論的深さは浅い」)。

§8 は同じ ζ'/L-leading coefficient を **algebraic unit の log-embedding** として現す方向を導入する — §7 が「c-matrix の **分散**」に住むのに対し、§8 は「L-function の **特殊値**」に住む。両者は ζ' を共有するが、視点と数論的 depth が異なる。具体的対比: §8.4 を参照。

### §8.1 L-function の最小定義

(c_phase_complex.md §4 の「DFT と L-function の ℂ 合流」からの再引用 + 拡張)

| 型 | 記号 | 定義 (Re(s) > 1) |
|---|---|---|
| Riemann ζ | ζ(s) | Σ n^{-s} = ∏_p (1-p^{-s})^{-1} |
| Dirichlet L | L(s, χ) | Σ χ(n) n^{-s} = ∏_p (1-χ(p) p^{-s})^{-1} |
| Dedekind ζ | ζ_K(s) | Σ_{a ⊂ O_K} N(a)^{-s} = ∏_p (1-N(p)^{-s})^{-1} |
| Artin L | L(s, ρ, K/k) | ∏_p det(1-ρ(Frob_p) N(p)^{-s})^{-1} |

全て s=1 周辺で meromorphic continuation を持ち、自明指標に対応するものは simple pole、非自明は entire (identity_asymmetry.md §3.4)。

### §8.2 Class Number Formula (Dirichlet-Hecke)

数体 K、`[K:ℚ] = n`、実埋込数 `r₁`、複素埋込対数 `r₂` (n = r₁+2r₂)。単数 rank `r = r₁+r₂−1`、class number `h_K`、regulator `R_K`、roots of unity の数 `w_K`、discriminant `d_K`。

**公式 (s=1 residue form)**:

    Res_{s=1} ζ_K(s) = (2^{r₁} · (2π)^{r₂} · h_K · R_K) / (w_K · √|d_K|)

**等価形式 (s=0 leading coefficient form)**:

    ζ_K^*(0) = − (h_K · R_K) / w_K   (at vanishing order r = r₁+r₂−1)

両形式は functional equation で結ばれる。s=0 形式は 3 因子 (h, R, w) のみ、s=1 形式は追加 3 因子 (2^{r₁}, (2π)^{r₂}, √|d_K|) を露出する。**6-gauge 分解**として読むには s=1 形式を使う。

### §8.3 6 因子の gauge signature 分解

各因子を Paper_Ω Origination (omega/Paper_Omega_Origination.md §1.6, §2.5) の gauge 署名にマップ:

| 因子 | 役割 | Paper_Ω 署名 | 近傍定数 |
|---|---|---|---|
| `(2π)^{r₂}` | 複素 place の archimedean Haar volume | {cont, geom} | π |
| `2^{r₁}` | 実 place の archimedean Haar volume | {addZ} | 2 (parity minimum scaffold, L0/identity_asymmetry §5.3) |
| `√\|d_K\|` | O_K の Minkowski 共体積 / 素数 ramification の積 | {mult, anal} | discriminant (新規) |
| `h_K` | ideal class group の位数 (principal ideal 失敗の count) | {mult} | discrete mult 不変量 |
| `R_K` | O_K^× の **自由部分** の log-embedding 格子 co-volume | {mult, cont} | Φ 系 fundamental unit の対数 |
| `w_K` | O_K^× の **torsion 部分** = `\|μ(K)\|` = K 内在の character mode 数 | {char} | arithmetic quartet (i_add/i_mult) |

**観察**:

1. **6 因子の役割は互いに直交する** — (複素 place volume / 実 place volume / Minkowski 共体積 / class 商 / 自由単数 co-volume / torsion 単数 count) の 6 軸で分解される。Dirichlet 単数定理 `O_K^× ≅ μ(K) × ℤ^r` により `R_K` と `w_K` は hard-separated (軸 3: H-stark-4 で別途検証)。

2. **Paper_Ω の全 gauge 署名が揃う**: {addZ, mult, char, cont, geom, anal} の 6 gauge が 1 本の等式に集結する唯一の既存辞書例。§7 (Taylor 係数組み合わせ) と対照的に、class number formula は **origination 構造そのものの積分解定理**として読める。

3. **ζ-γ pair との関係**: Paper_Ω §2.4 は ζ を「生成核 (generating kernel)」、γ を「境界差分核 (boundary residue)」と位置づける。Class number formula は ζ_K の s=1 pole residue であり、**ζ が境界で γ 的役割を果たす局面**。K = ℚ の場合 `Res ζ(1) = 1` が自明化するが、一般 K ではこの 1 が 6 因子に分裂する。

#### §8.3.1 4-Layer Provenance Table (R9 prototype)

§8.3 の 6 tag が **どの source layer から注入されるか** を追跡する。composite_gauge_rules_v1.md の 4-layer hierarchy (L-0 intrinsic / L-1 index / L-2 context / L-3 evaluation) に従う。

**Provenance decomposition of `Res_{s=1} ζ_K(s)`**:

| 因子 | 署名 | L-0 (intrinsic) | L-1 (index, R7) | L-2 (context, R8) | L-3 (evaluation, R9) |
|---|---|---|---|---|---|
| `(2π)^{r₂}` | {cont, geom} | — | — | — | **{cont, geom}**: archimedean Haar normalization. `Eval = Res_{s=1}` + archimedean completion が注入 |
| `2^{r₁}` | {addZ} | **{addZ}**: 2 is the parity scaffold (identity_asymmetry) | — | — | exponent `r₁` は L-3 (embedding count) |
| `√\|d_K\|` | {mult, anal} | — | **{mult}**: index = ramified primes (R7 §2.2) | **{anal}**: functional eq. normalization role (R8 §3.3) | — |
| `h_K` | {mult} | — | **{mult}**: index = ideal class group (R7 §2.2) | — | — |
| `R_K` | {mult, cont} | — | **{mult}**: index = unit group lattice (R7 §2.2) | — | **{cont}**: log-embedding co-volume は L-3 (continuous evaluation of lattice) |
| `w_K` | {char} | — | — | — | **{char}**: torsion counting operator (L-3); `w_K = \|μ(K)\|` は evaluation-time discrete count |

**Layer 分布**:
- **L-0**: {addZ} × 1 (2 の parity scaffold)
- **L-1 (R7)**: {mult} × 3 (`√|d_K|`, `h_K`, `R_K` — 全て index 集合構造由来)
- **L-2 (R8)**: {anal} × 1 (`√|d_K|` の functional equation role)
- **L-3 (R9)**: {cont, geom, char, addZ(exponent)} × 4 件 (`(2π)^{r₂}`, `R_K` の cont、`w_K`、`r₁`)

**結論**: class number formula の 6 tag は 4 layer 全てにわたって分布する。**L-3 (evaluation) が担う tag は {char, cont, geom} の 3 tag + exponent の {addZ}** であり、これは composite_gauge_v0.md §13.6 の scope-conditioned candidate と整合する。特に:

- function body (`ζ_K(s)` as Dirichlet series / Euler product) は {mult, addZ, anal} を運ぶ (composite_gauge_v0 §6)
- evaluation (`Res_{s=1}` + archimedean completion + torsion counting) が {char, cont, geom} を注入

これは R9 の **最初の完全 witness**: 1 本の等式内で L-3 evaluation layer が他 3 layer と分離して動作する実例。

*(本表は `dictionaries/meta/evaluation_gauge_operators_v0.md` の G_eval map prototype の実地検証。R9 rule 本体は未 promote、研究段階。)*

### §8.4 §7 との対比 (両 ζ' の位置づけ)

| 観点 | §7 | §8 |
|---|---|---|
| 対象 | c-matrix `c_{g,χ}(τ) = χ(g)·g^{-τ}` の共分散 | Dedekind ζ_K の s=1 residue |
| 使う ζ の量 | ζ(2τ), ζ'(2τ), ζ''(2τ) — Taylor 係数 | ζ_K^*(0) = -h_K R_K/w_K — 特殊値 leading coefficient |
| 圏 | statistical (分散/相関) | algebraic (代数対象の等式) |
| Gauge | 1 gauge 内 (p → ∞ limit の分散構造) | 6 gauge の積分解 |
| §7.5 自己評価 | 「浅い」(I_phase=2/3 や c_s²=1/2 に及ばない) | — |
| Paper_Ω 整合度 | partial (1 signature のみ) | full (6 signature 全揃い) |

**結論**: §7 と §8 は同じ辞書ファイル内に併置される 2 つの視点であり、同じ ζ' を異なる depth で扱う。両者に優劣はなく、役割が異なる。§7 は spectral statistics 側、§8 は arithmetic geometry 側。

### §8.5 数値検証: 3 ケース

**Case A: K = ℚ**
- (r₁, r₂) = (1, 0), d_K = 1, h = 1, R = 1 (rank 0, empty det), w = 2
- RHS = (2 · 1 · 1 · 1) / (2 · 1) = **1**
- LHS = Res ζ(1) = 1 ✓

**Case B: K = ℚ(i)**
- (r₁, r₂) = (0, 1), |d_K| = 4, h = 1, rank = 0 so R = 1, w = 4 (μ = {±1, ±i})
- RHS = (1 · 2π · 1 · 1) / (4 · 2) = **π/4**
- LHS = ζ(1) residue × L(1, χ_{-4}) = 1 · (Leibniz: π/4) = π/4 ✓
- **注目**: rank 0 (単数は全て torsion) → R_K が trivial、w_K が単数群全体 4 を取る。6 因子の役割分離の境界例。

**Case C: K = ℚ(√2)**
- (r₁, r₂) = (2, 0), d_K = 8, h = 1, fundamental unit ε = 1+√2, R = log(1+√2) ≈ 0.8814, w = 2
- RHS = (4 · 1 · 1 · log(1+√2)) / (2 · 2√2) = **log(1+√2)/√2 ≈ 0.6232**
- LHS = 1 · L(1, χ_8) = 1 · (2·1·log(1+√2))/√8 = log(1+√2)/√2 ≈ 0.6232 ✓ (Dirichlet 実二次公式)
- **注目**: rank 1 (1+√2 は無限位) → R_K が log(1+√2) を取り、w_K は {±1} のみで 2。torsion/free 分離の非自明例。

**Case D: K = ℚ(√5)** — Paper_Ω 代数極 Φ の base case
- (r₁, r₂) = (2, 0), d_K = 5 (5 ≡ 1 mod 4), h = 1, **基本単数 ε = Φ = (1+√5)/2** (黄金比, N(Φ) = -1), R = log Φ ≈ 0.4812, w = 2
- RHS = (4 · 1 · 1 · log Φ) / (2 · √5) = **2 log Φ / √5 ≈ 0.4304**
- LHS = 1 · L(1, χ_5) = 2 log Φ / √5 ✓
- **注目**: R_K スロットに Paper_Ω §2.5 の「代数極 {mult}」クラスの基底定数 Φ が **素の形**で入る唯一の既存実例。rank 0 Stark level での H-stark-3 (Stark unit = abelian Φ 一般化) 概念層の base case 確認。

**Case E: K = ℚ(√−5)** — class number 初非自明ケース
- (r₁, r₂) = (0, 1), d = -5, -5 ≡ 3 mod 4 → d_K = -20, |d_K| = 20, √|d_K| = 2√5
- **h = 2** (有名な非 PID: 6 = 2·3 = (1+√−5)(1−√−5))、rank = 0 so R = 1、w = 2
- RHS = (1 · 2π · 2 · 1) / (2 · 2√5) = **π / √5 ≈ 1.4050**
- LHS = 1 · L(1, χ_{-20}) = (2π h) / (w √|d_K|) = π/√5 ✓ (Dirichlet 虚二次公式)
- **注目**: 6-gauge 分解の **直交性** の数値的証拠。分子の「2」が 2^{r₁} (addZ, ここでは 1 で消失) ではなく h_K (mult, ここで初めて非自明) から来る — 2 つの「2 らしさ」が gauge 的に別物であることが数値的に分離される最初の辞書内例。

5 ケース全てで等式が数値的に verify。各ケースが異なる gauge 軸を「主動因子」として exercise し、6 因子の独立性が経験的に示される。

**6 因子 witness coverage 表**:

| Gauge factor | 署名 | 主動になるケース | 非主動ケースでの値 |
|---|---|---|---|
| 2^{r₁} | {addZ} | ℚ, ℚ(√2), ℚ(√5) (=2 or 4) | ℚ(i), ℚ(√−5) で 1 |
| (2π)^{r₂} | {cont, geom} | ℚ(i), ℚ(√−5) (=2π) | ℚ, ℚ(√2), ℚ(√5) で 1 |
| √\|d_K\| | {mult, anal} | ℚ(√2,√5,√−5,i) (=√8,√5,2√5,2) | ℚ で 1 |
| h_K | {mult} | **ℚ(√−5) のみ** (=2) | 他 4 ケースで 1 |
| R_K | {mult, cont} | ℚ(√2) (log(1+√2))、**ℚ(√5) (log Φ)** | ℚ, ℚ(i), ℚ(√−5) で 1 (rank 0) |
| w_K | {char} | **ℚ(i) のみ** (=4) | 他 4 ケースで 2 |

**6 factor 全てが少なくとも 1 ケースで主動因子として exercise される** → 6-gauge 分解の経験的完全性 (S7 の empirical saturation)。特に:
- h_K の単独主動ケース (ℚ(√−5)) と w_K の単独主動ケース (ℚ(i)) の存在により、**両者が class number formula の分子で役割衝突しないことが数値的に verify される** (軸 2 の 6-gauge 役割衝突チェック、H-stark-4 の補強)

5 ケースで等式が数値的に verify。特に w_K と R_K の分離が ℚ(i) (w 中心) と ℚ(√2) (R 中心) の両極で示され、さらに h_K と 2^{r₁} の分離が ℚ(√−5) と ℚ(√2) の対比で示される。

### §8.6 Scope と Stark 予想への橋

**§8 の範囲 (established)**: Dirichlet-Hecke の class number formula = rank 0 Stark case。全数体 K で証明済。

**§8 の範囲外 (conjecture)**:
- **Rank 1 abelian Stark**: `L'(0, χ) = -(1/e_χ) Σ_σ χ(σ⁻¹) log|σ(ε_χ)|` — L-derivative を Galois 軌道上の character-weighted log-amplitude で表現する予想。ΣΦ 語彙では **R-gauge 残差ゼロ予想**として記述可能。詳細: `research/stark_projection_v0.md §2.2-2.3`。
- **Higher rank** (r(χ) ≥ 2): regulator 型行列式の代数性、超越数論領域、辞書 scope 外。
- **非 abelian / Artin**: Artin holomorphy が未解決、辞書 scope 外。
- **p-adic Stark**: p-adic gauge が L0 辞書に未追加、辞書 scope 外。

これら scope 外項目は `research/stark_projection_v0.md §4` (hard limits) に記録。§8 は rank 0 部分のみ established として受け持つ。

### §8.7 検証スクリプト

- (未実装) `class_number_formula_verify.py`: §8.5 の 3 ケース + ℚ(ζ_5), ℚ(√−5), ℚ(ζ_7) の RHS 直接計算と SageMath / LMFDB の residue 値の照合
- §8.5 の 3 ケースは closed-form で verify 済、script は regression test 用

---

*作成日: 2026-04-08*
*最終更新: 2026-04-09 (§8 added: class number formula 6-gauge decomposition, research/stark_projection_v0.md G1)*
