---
axis: A
position: quantum_relativistic
static_dynamic: static
connected_to:
  - A.phase_complex
  - B.quantum_observation
  - B.gauge_field_theory
  - B.periodic_table
arrow_status:
  upstream: established
  downstream: established
updated: 2026-04-13
---

# 微細構造: スピン軌道結合と角運動量の ΣΦ 的導出

**Level**: L1 (pure mathematics + relativistic correction, domain-independent)
**Dependencies**:
- `c_phase_complex.md` §2 (ι_L), §5 (c_s² = 1/2, ℤ/2ℤ)
- `q_quantum_observation.md` §3 (spectral theorem), §5 (tensor product)
- `c_arrow_obstruction.md` (Arrow Type I/II)

**Downstream**:
- `periodic_table_dictionary_v0.md` §8 (PQ5: NIST validation)
- `chemistry_dictionary_v0.md` §2 (quantum numbers)
- `physics_constants_decomposition.md` §6 (alpha hierarchy)

---

## §1 動機

### 1.1 欠落の発見

PQ5 (periodic_table_dictionary §8) で判明: NIST 実測スペクトルの S16 tier は量子欠損モデルの予測と 50% しか一致しない。Fe は STANDARD_FP (model: DEEP_FP)、Cu は INTERMEDIATE_FP (model: DEEP_FP)。原因は**微細構造多重項**の存在であり、これが量子辞書のどこにも記述されていなかった。

### 1.2 本ファイルの位置

```
q_quantum_observation.md (非相対論 QM)
    ↓ α² 補正
q_fine_structure.md (本ファイル: 相対論的 1-body 補正)
    ↓ 場の量子化
q_gauge_field_theory.md (非摂動的場の理論)
```

q_quantum_observation は [A,B] ≠ 0 から始まり、スペクトル定理・ユニタリ発展・Born 則を導出するが、**全て非相対論的**。本ファイルは α² のオーダーで初めて現れる相対論的補正を ΣΦ の言葉で定式化する。

---

## §2 スピンの ΣΦ 的起源

### 2.1 ℤ/2ℤ から SU(2) へ

c_phase_complex §5 で確立された c_s² = 1/2 は ℤ/2ℤ の一様測度に由来する。化学辞書 §2.2 ではこれを Pauli 排他律に接続した。ここでは L1 レベルで厳密に定式化する。

**スピン群 SU(2) の ℤ/2ℤ 的根**:

ℤ/2ℤ の ι_L インスタンス:

    ι₂: ℤ/2ℤ → S¹,   m_s ↦ e^{iπm_s}

m_s = ±1/2 に対し ι₂(+1/2) = e^{iπ/2} = i, ι₂(-1/2) = e^{-iπ/2} = -i。この 2 点が S¹ 上の対蹠点を成す。

SU(2) はこの離散対称性の連続化:

    SU(2) = { e^{-iθ n̂·σ/2} : θ ∈ [0, 4π), n̂ ∈ S² }

ここで σ = (σ_x, σ_y, σ_z) は Pauli 行列。ℤ/2ℤ は SU(2) の中心 {I, -I} として埋め込まれる:

    ℤ/2ℤ ↪ Z(SU(2)) ↪ SU(2)

### 2.2 c_s² = 1/2 のスピン的意味

σ_z の固有値 ±1/2 に対する Born 確率:

    P(m_s = +1/2) = P(m_s = -1/2) = 1/2

これは ℤ/2ℤ 上の一様分布であり、c_s² = E[cos²(πt)] = 1/2 の spin-1/2 における具現化。**スピンは c_s² = 1/2 の最小の物理的キャリア**。

### 2.3 スピンと ι_L の入れ子構造

chemistry_dictionary §2.3 の入れ子:

```
ι_n → ι_l → ι_{m_l} → ι_{m_s}
```

最内層 ι_{m_s} は常に ℤ/2ℤ であり、殻容量の因子 2 の起源。本ファイルでは、この ι_{m_s} が ι_l と**結合する**ことで微細構造が生まれる過程を §3 で導出する。

---

## §3 角運動量結合 = テンソル積の分解

### 3.1 q_quantum_observation §5 からの導出

テンソル積 H_L ⊗ H_S における角運動量の結合:

    V_l ⊗ V_s = V_{l+s} ⊕ V_{l+s-1} ⊕ ... ⊕ V_{|l-s|}

ここで V_j は角運動量 j の既約表現（dim = 2j+1）。

spin-1/2 (s = 1/2) の場合:

    V_l ⊗ V_{1/2} = V_{l+1/2} ⊕ V_{l-1/2}    (l ≥ 1)
    V_0 ⊗ V_{1/2} = V_{1/2}                     (l = 0)

### 3.2 結合角運動量 J の ι_L 的読解

全角運動量 J = L + S に対する ι_J:

    ι_J: ℤ/(2J+1)ℤ → S¹,   m_J ↦ e^{2πi m_J/(2J+1)}

J は l と s の ι_L インスタンスの「結合」から生じる。Clebsch-Gordan 係数 ⟨l, m_l; s, m_s | j, m_j⟩ は ι_l と ι_s から ι_j への変換行列。

### 3.3 ι_L の結合則

| 入力 | 結合 | 出力 | 物理的意味 |
|------|------|------|-----------|
| ι_l (軌道) ⊗ ι_s (スピン) | Clebsch-Gordan | ι_j (全角運動量) | 1電子の微細構造 |
| ι_{l₁} ⊗ ι_{l₂} | — | ι_L (全軌道) | 多電子の角運動量合成 |
| ι_L ⊗ ι_S | — | ι_J (全角運動量) | 多電子の LS 結合 |

---

## §4 微細構造 Hamiltonian

### 4.1 摂動展開

非相対論的 Hamiltonian H₀ に対する α² 補正:

    H = H₀ + H_SO + H_rel + H_Darwin

| 項 | 式 | 物理的起源 | α 依存性 |
|----|-----|-----------|----------|
| H₀ | -ℏ²∇²/2m - Ze²/r | 非相対論的 Schrodinger | α⁰ |
| H_SO | ξ(r) L·S | スピン軌道結合（磁気的） | α² |
| H_rel | -p⁴/8m³c² | 運動エネルギーの相対論補正 | α² |
| H_Darwin | (πℏ²/2m²c²) Ze² δ³(r) | Zitterbewegung（s 軌道のみ） | α² |

### 4.2 L·S の固有値

L·S = (J² - L² - S²)/2 の固有値:

    ⟨L·S⟩ = [j(j+1) - l(l+1) - s(s+1)] / 2

水素原子の微細構造エネルギー（Dirac の厳密解の 1 次近似）:

    E_fs(n, j) = -(α² / 2n) × E_n × [n/(j+1/2) - 3/4]

ここで E_n = -13.6/n² eV。**α² がエネルギー補正のスケールを設定する。**

### 4.3 ΣΦ 的解釈

微細構造は ι_L の入れ子に新しい層を追加する:

```
α⁰: ι_n (主量子数)          → gross structure
α²: ι_n → ι_j (全角運動量)  → fine structure
α⁴: ι_n → ι_j → ι_F (核)   → hyperfine structure
```

各層は前の層の縮退を解く。α は「ι_L の入れ子の深さを一段掘る」パラメータ。

---

## §5 Lande 間隔則

### 5.1 導出

多電子原子の LS 結合項 ²ˢ⁺¹L_J において、スピン軌道エネルギーは:

    E_SO(J) = (A/2) [J(J+1) - L(L+1) - S(S+1)]

隣接 J 間のエネルギー差:

    E(J) - E(J-1) = A × J

これが **Lande 間隔則**: 多重項内の隣接準位間隔は J に比例する。

### 5.2 Fe I ⁵D 多重項による検証

NIST 実測値 (cm⁻¹): ⁵D₄ = 0.00, ⁵D₃ = 415.93, ⁵D₂ = 704.01, ⁵D₁ = 888.13, ⁵D₀ = 978.07

| 遷移 | 間隔 (cm⁻¹) | J | 間隔/J | |
|------|-------------|---|--------|---|
| ⁵D₄→⁵D₃ | 415.93 | 4 | 103.98 | |
| ⁵D₃→⁵D₂ | 288.08 | 3 | 96.03 | |
| ⁵D₂→⁵D₁ | 184.12 | 2 | 92.06 | |
| ⁵D₁→⁵D₀ | 89.94 | 1 | 89.94 | |

平均 A = 95.50 cm⁻¹、相対散布 5.6%。Lande 則は良い近似だが厳密ではない（2 次補正 ∝ J² が 5.6% のずれを生む）。

⁵F 多重項 (L=3, S=2) では A = 86.96 cm⁻¹、散布 2.3%（L が大きいほど Lande 近似が改善）。

### 5.3 単一多重項の S16

Lande 間隔パターン（間隔 ∝ J）は**等差数列ではない**:

| スペクトル | S16 Tier | RMS/N |
|-----------|----------|-------|
| 等差数列 (同範囲, 5 点) | EXACT | 0.0000 |
| Fe ⁵D (Lande, 5 点) | DEEP_FP | 0.3449 |
| Fe ⁵F (Lande, 5 点) | DEEP_FP | 0.3398 |
| 理想 Lande (完全 ∝J, 5 点) | DEEP_FP | 0.3298 |

**単一の Lande 多重項は DEEP_FP である**。間隔 ∝ J は単調減少列であり、等間隔から遠い。

### 5.4 複数多重項の重畳効果

Fe の NIST スペクトルが STANDARD_FP に落ちるのは、複数多重項の重畳による:

| 組み合わせ | N | S16 Tier | RMS/N |
|-----------|---|----------|-------|
| ⁵D のみ | 5 | DEEP_FP | 0.345 |
| ⁵F のみ | 5 | DEEP_FP | 0.340 |
| ⁵D + ⁵F | 10 | INTERMEDIATE_FP | 0.263 |
| NIST 全 30 準位 | 30 | STANDARD_FP | 0.146 |

**メカニズム**: 異なる多重項の準位が互いのギャップを埋め合い、全体の間隔分布を均一化する。遷移金属（多数の低い多重項を持つ）でこの効果が最大になる。

**ΣΦ 的読解**: 各 Lande 多重項は ι_J の 1 つのインスタンス。複数の ι_J インスタンスが異なるスケール A で重畳すると、全体のスペクトルの非等間隔性が相殺される。これは crystal_dictionary の空間群における centering 操作（系統消滅による均一化）と同種の効果。

---

## §6 LS 結合 vs jj 結合

### 6.1 二つの結合スキーム

同一の全角運動量 J を構成する二つの順序:

**LS 結合** (Russell-Saunders):

```
(l₁ ⊗ l₂ ⊗ ... → L) ⊗ (s₁ ⊗ s₂ ⊗ ... → S) → J
```

**jj 結合**:

```
(l₁ ⊗ s₁ → j₁) ⊗ (l₂ ⊗ s₂ → j₂) ⊗ ... → J
```

### 6.2 選択条件

| | LS 結合 | jj 結合 |
|---|---|---|
| 条件 | H_ee >> H_SO | H_SO >> H_ee |
| 適用範囲 | 軽い原子 (Z < ~30) | 重い原子 (Z > ~70) |
| 良い量子数 | L, S, J | j₁, j₂, ..., J |
| 中間領域 | Z ~ 30-70: 中間結合 | |
| ΣΦ 的意味 | テンソル積の分解順序の選択 | |

### 6.3 Arrow Type I としての結合スキーム選択

LS と jj は同じ最終空間（全 J が同一）に到達する二つの経路。どちらが「正しい」かは H_ee / H_SO の比で決まる離散的選択であり、**Arrow Type I**（離散的障害）に分類される。

中間結合（Z ~ 30-70）では LS も jj も良い量子数を与えず、中間結合行列の対角化が必要。これは Arrow の「partially resolved」状態に対応する。

---

## §7 α の階層的位置づけ

### 7.1 エネルギースケールの階層

| 構造 | α 依存性 | エネルギースケール | ΣΦ の層 |
|------|---------|-------------------|---------|
| Gross (殻構造) | α⁰ | ~eV | ι_n の入れ子 (§2-§3 of chemistry_dict) |
| Fine (多重項分裂) | α² | ~10⁻³ eV | ι_j の追加層 (本ファイル) |
| Hyperfine (核スピン) | α⁴ × m_e/m_p | ~10⁻⁶ eV | ι_F の追加層 |
| Lamb shift (QED) | α⁵ | ~10⁻⁶ eV | D_floor Level 2 |

### 7.2 Type I / Type III の具体化

physics_constants_decomposition の分類:

- **Type I** (c_s² = 1/2): 殻構造（周期表の行・列）を決定。α に依存しない
- **Type III** (α ≈ 1/137): 殻構造内の微細分裂幅を決定。構造を作らないが精度を決める

本ファイルはこの役割分担を定量的に示す: α⁰ で周期表が決まり、α² で多重項が割れ、α⁴ で超微細構造が現れる。α は「解像度のダイアル」として機能し、回すたびに ι_L の入れ子が一段深くなる。

### 7.3 D_floor との関係

periodic_table_dictionary §1.3 の D_floor 階層:

| Level | D_floor | α 依存性 |
|-------|---------|---------|
| 0 | 装置分解能 | なし（技術的） |
| 1 | 自然線幅 Γ | α³ (許容遷移) |
| 2 | Lamb shift | α⁵ |

微細構造の分裂幅 (~α² × eV) は D_floor Level 1 の自然線幅 (~α³ × eV) より大きい。したがって微細構造は原理的に観測可能であり、D_floor には阻まれない。超微細構造 (~α⁴ × m_e/m_p × eV) は自然線幅と同程度であり、D_floor Level 1 に近づく。

---

## §8 S16 への接続: PQ5 の完全な説明

### 8.1 問題の再定式化

PQ5 の問い: なぜ NIST 実測スペクトルは量子欠損モデルの予測より常に低い RMS/N を示すか?

### 8.2 回答

**3 段階のメカニズム**:

1. **Gross structure** (量子欠損モデルが捉える): 1/(n-δ)² 系列。非等間隔性が高い (DEEP_FP/INTERMEDIATE_FP)

2. **Fine structure** (本ファイルが追加): 各 gross level が J 多重項に分裂。Lande 間隔則により間隔 ∝ J。単一多重項は DEEP_FP だが、**複数多重項の重畳が間隔を均一化する**

3. **多重項密度効果**: 遷移金属 (d-block) は開殻 d 電子により多数の低い項 (⁵D, ⁵F, ³P, ³H, ...) を持つ。これらの多重項が密集し、互いのギャップを埋め合って全体の RMS/N を劇的に下げる

### 8.3 元素タイプ別の予測

| タイプ | 多重項数 | 予測 | NIST で確認 |
|--------|---------|------|------------|
| 水素 | 1 (各 n に 1 term) | Model ≈ NIST | H: 0.307 → 0.281 (近い) |
| アルカリ | 少 (doublet のみ) | Model > NIST (微小) | Na: 0.228 → 0.154 |
| p-block | 中 (triplet/singlet 混在) | Model > NIST | C: 0.252 → 0.147 |
| d-block | 多 (多数の term) | **Model >> NIST** | Fe: 0.524 → 0.146 |
| 希ガス | 中 (閉殻だが励起 config 多い) | Model > NIST | Kr: 0.272 → 0.179 |

d-block の乖離が最大であることは、多重項密度効果の強さと一致する。

### 8.4 PQ7 への基盤

PQ7 (Lande 均一化の定理化) に必要な要素:

1. Lande 間隔則 (§5) → 多重項内の間隔構造
2. 多重項数 M と全準位数 N の関係 → 準位密度
3. 異なるスケール A₁, A₂, ... の重畳 → 間隔分布の均一化条件

### 8.5 T-LU: Lande 均一化定理（候補、PQ7 RESOLVED）

**Scripts**: inline experiments (PQ7), root cause analysis

#### 8.5.1 数値的証拠

M 個の Lande 多重項（L=2, S=2, A ∈ [50,150], E₀ ∈ [0, 10000] cm⁻¹）の重畳 (100 試行/M):

| M | N | RMS/N (mean) | Tier |
|---|---|-------------|------|
| 1 | 5 | 0.330 | DEEP_FP |
| 2 | 10 | 0.252 | INTERMEDIATE_FP |
| 5 | 25 | 0.159 | INTERMEDIATE_FP |
| 8 | 40 | 0.127 | STANDARD_FP |
| 12 | 60 | 0.106 | STANDARD_FP |
| 20 | 100 | 0.100 | STANDARD_FP |
| 40 | 200 | 0.100 | STANDARD_FP |

#### 8.5.2 T-LU (Lande Uniformization, candidate)

M 個の Lande 多重項の重畳スペクトルの S16 departure:

    RMS/N(M) ≈ C · M^{-β} + RMS_∞

| パラメータ | 値 | 起源 |
|-----------|-----|------|
| β | **0.29** | Poisson 収束率（クラスタ内相関による CLT からの偏差） |
| C | ~0.33 | M=1 (単一多重項) の値 |
| RMS_∞ | **~0.10** (τ_max=5.0) | Poisson-格子距離（S16 測定窓のアーティファクト） |

#### 8.5.3 根本原因の切り分け

**RMS_∞ = 0.10 ≠ 0 の原因**:

S16 は「格子（等間隔）からの距離」を測る。K(τ) と Fejér kernel F(τ) の比較において:

| スペクトル型 | K(τ) | F(τ) との乖離 |
|------------|------|-------------|
| 格子（等間隔） | K = F（定義的一致） | RMS = 0 |
| Poisson（ランダム一様） | K(τ) → 1 (τ>0) | RMS/N = **0.10** (τ_max=5.0) |

飽和値は τ_max 依存:

| τ_max | RMS_∞ |
|-------|-------|
| 1.0 | 0.045 |
| 5.0 | **0.100** (S16 標準設定) |
| 10.0 | 0.507 |

**RMS_∞ は物理量ではなく、S16 の測定窓における Poisson-格子距離**。多重項重畳は格子ではなく **Poisson に収束する**ため、この距離がゼロにならない。

数値的確認:
- Random uniform N=100 → RMS/N = 0.10002
- Random uniform N=1000 → RMS/N = 0.09990
- Equispaced + Gaussian jitter (σ/d = 1.0) → RMS/N = 0.10000

σ/d ≥ 0.5 でジッタが格子間隔の半分を超えると Poisson に収束。

**β = 0.29 ≠ 0.50 の原因**:

| クラスタ型 | β | 備考 |
|-----------|---|------|
| Lande 多重項 | -0.294 | |
| ランダム単点 | **-0.294** | Lande と同一 |
| CLT 予測 (iid) | -0.500 | 独立同分布の場合 |

**Lande 構造は β に影響しない**。β = -0.29 は「相関のあるクラスタの Poisson 収束率」であり、クラスタの内部構造（Lande、等間隔、ランダム）に依存しない普遍定数。CLT の -0.5 との差 (~0.2) はクラスタ内間隔の相関に由来する。

#### 8.5.4 T-LU の完全な読解

```
M 個の多重項重畳
    ↓ M → ∞ (β ≈ 0.29)
Poisson 過程（ランダム一様間隔）
    ↓ ≠ (距離 = RMS_∞ ≈ 0.10)
格子（等間隔 = EXACT = RMS = 0）
```

**3 つの帰結**:

1. **収束先は Poisson であって格子ではない**: 多重項をいくら重ねても EXACT にはならない。多重項重畳は秩序を生まず、個別の秩序を洗い流して Poisson に帰着させる

2. **β は普遍的**: Lande 構造に特異な効果はない。どんなクラスタ（Lande、等間隔、ランダム）でも同じ β ≈ 0.29 で Poisson に収束する。化学的に意味があるのはクラスタの**数 M** だけ

3. **Fe/Co/Ni が STANDARD に達するのは M が十分大きいから**: M ≥ 7-8 で RMS/N ≈ 0.13 (STANDARD 閾値 0.15 以下)。遷移金属の開殻 d 電子が生む多数の低い項が M を稼ぐ

**ΣΦ 的位置づけ**: T-LU は S16 における「秩序の洗い流し定理」。個別の Lande 構造（ι_J のインスタンス）は S16 レベルでは DEEP_FP だが、十分多くのインスタンスの重畳は構造を消去して Poisson に帰着させる。これは c_arrow_obstruction の Type II 障害（連続スペクトル的ノイズ）の具体的メカニズム。

crystal_dictionary の centering 操作との対比: centering は系統消滅で**特定の反射を選択的に消す**（構造を作る操作）。T-LU は多重項重畳で**全ての構造を非選択的に洗い流す**（構造を壊す操作）。方向が逆。

---

## §9 辞書接続マップ

### L1 内部参照

| 項目 | 本辞書の依存節 | 依存内容 |
|------|---------------|---------|
| `c_phase_complex.md` §2 | §2, §3 | ι_L → スピン、角運動量結合 |
| `c_phase_complex.md` §5 | §2 | c_s² = 1/2 → スピン ℤ/2ℤ |
| `q_quantum_observation.md` §3 | §4 | spectral theorem → 微細構造固有値 |
| `q_quantum_observation.md` §5 | §3 | tensor product → Clebsch-Gordan |
| `c_arrow_obstruction.md` | §6 | Arrow Type I → LS/jj 選択 |
| `c_spectral.md` §1 | §5, §8 | K(τ) → S16 分類 |

### L2 参照

| ドメイン | 本辞書との関係 | 状態 |
|---------|---------------|------|
| periodic_table_dictionary_v0 §8 | PQ5 の理論的根拠を提供 | 接続確立 |
| chemistry_dictionary_v0 §2 | スピン ℤ/2ℤ の L1 昇格版 | 接続確立 |
| physics_constants_decomposition §6 | α の階層的位置づけの詳細 | 接続確立 |

### Open Questions

| ID | 問い | 優先度 |
|----|------|--------|
| FQ1 | 中間結合 (Z~30-70) の ΣΦ 的定式化。LS/jj のどちらも良くない領域で Arrow obstruction はどう記述されるか | MEDIUM |
| FQ2 | 超微細構造 (ι_F 層) の辞書化。核スピン I との結合 F = J + I | LOW |
| FQ3 | Lamb shift (QED) と D_floor Level 2 の正式な接続 | LOW |

---

*作成日: 2026-04-13*
*最終更新: 2026-04-13*
