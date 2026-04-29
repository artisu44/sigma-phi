---
axis: [A, B, E]
position: L1_action_bridge
static_dynamic: both
connected_to:
  - L1_mathematical/q_quantum_observation.md     # Hamiltonian side (spectral theorem, Stone)
  - L1_mathematical/q_quantum_statistical_mechanics.md  # Z(β) = Tr(e^{-βH}), KMS
  - L1_mathematical/q_quantum_thermodynamics.md  # F = -kT ln Z, Legendre web
  - L1_mathematical/q_many_body_quantum.md       # Fock space, second quantization
  - L1_mathematical/q_gauge_field_theory.md      # S_YM, Z = ∫DA e^{-S}, BRST
  - L1_mathematical/c_phase_complex.md           # §4 ℂ common receptacle, ι_L/χ dual
  - L1_mathematical/c_spectral.md               # §7-8 zeta, class number formula
  - L1_mathematical/c_scaling_laws.md            # running coupling, saddle point
  - L0_canon/finite_observation.md             # A0 (S,W,m)
  - L0_canon/external_time.md                  # t/τ separation
  - research/oq_ym1_mass_gap_verification_plan.md  # S16 gap test
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-11
runtime_summary:
  what: Hamiltonian (演算子/スペクトル) と Lagrangian (作用/経路) の二重記述を橋渡し。Wick rotation、生成汎関数 Z[J]、相関→スペクトル変換を統一的に記述
  when: 作用原理、経路積分、Wick rotation、generating functional、saddle point、連続極限の問い
  provides: [lagrangian, action, euler_lagrange, path_integral, wick_rotation, generating_functional, correlation_to_spectrum, hamiltonian_lagrangian_duality, saddle_point, effective_action]
  consumes: [q_quantum_observation.md (H, spectral theorem), QSM (Z(β), KMS), c_phase_complex.md §4 (ℂ receptacle), q_gauge_field_theory.md §3 (S_YM)]
  axis: [A, B, E]
  residual_types: [R-info, R-gauge]
  cost: large
  status: established
  one_screen: |
    §1 L = T−V, S = ∫L dt, δS=0 (Euler-Lagrange)。最小作用 = 観測の variational 記述
    §2 H↔L 双対: Legendre 変換 H(q,p) = pq̇−L(q,q̇)。演算子量子論 = H 側、経路積分 = L 側
    §3 Path integral: ⟨f|i⟩ = ∫Dq e^{iS[q]/ℏ}。全経路の重ね合わせ = A0 の連続版
    §4 Wick rotation: t→−iτ で e^{iS} → e^{-S_E}。振動積分→収束積分。S12 加法→乗法 bridge
    §5 Z[J] generating functional: Z[J] = ∫Dφ e^{-S+Jφ}。全相関関数の母関数
    §6 Correlation → spectrum: ⟨φ(x)φ(0)⟩ ~ e^{-m|x|}。pole = particle mass = spectral gap
    §7 S12/S16 接続: exp kernel の action 版。K(τ)↔Z(β) thermal bridge の理論的母体
---

# 作用原理 — Hamiltonian と Lagrangian の二重記述

**Level**: L1 (domain-independent mathematical physics)
**Role**: 既存 L1 量子辞書チェーン (全て Hamiltonian/spectral 側) に
**Lagrangian/action/path integral 側** の入口を提供する中継層

---

## §0 なぜこのファイルが必要か

L1 量子辞書の現状:

```
quantum_observation ──→ OQS ──→ QSM ──→ QTD ──→ many_body ──→ gauge_field_theory
     [A,B]           Tr_B      Z(β)     F=-kTlnZ   Fock      S_YM, Z=∫DA
     spectral thm    Lindblad  KMS      Legendre   SSB/gap   BRST, mass gap
```

**全て Hamiltonian (演算子/スペクトル) 言語で記述されている**。

同じ構造には Lagrangian (作用/経路) 側からの記述がある。
両者は Legendre 変換で繋がる双対記述であり、
一方だけでは S16 thermal bridge (K(τ)→Z(β)) や
Wick rotation (振動→減衰) の「なぜ」が不完全。

---

## §1 Lagrangian と作用 — variational 記述

### §1.1 Lagrangian

L(q, q̇, t) = T − V (運動エネルギー − ポテンシャル)

**ΣΦ 読み**: L は瞬時的な「運動の cost function」。
- T = 変化の速度に対する cost (kinetic)
- V = 位置に対する cost (potential)
- L = net cost (差)

### §1.2 作用

S[q] = ∫_{t_i}^{t_f} L(q(t), q̇(t), t) dt

**ΣΦ 読み**: S[q] は経路 q(t) 全体の「総 cost」。
(S, W, m) 同定:
- S (structure) = 可能な全経路の空間 + 作用汎関数 S[q]
- W (window) = 境界条件 q(t_i), q(t_f) (有限窓)
- m (measurement) = 停留経路 q_cl (古典) or 遷移振幅 ⟨f|i⟩ (量子)

注: 作用 S[q] 自体は S (構造) の一部であり m (測定) ではない。
m は S[q] を使って得られる output (古典: δS=0 の解、量子: §3 の経路積分)。

### §1.3 Euler-Lagrange 方程式

δS = 0 ⟹ d/dt (∂L/∂q̇) = ∂L/∂q

**最小作用原理**: 物理的経路は作用を停留させる経路。

**ΣΦ 読み**: 最小作用 = 「観測の variational 記述」。
有限窓 W (境界条件) のもとで、
S の停留点が「最も可能性の高い観測」。

---

## §2 Hamiltonian ↔ Lagrangian 双対

### §2.1 Legendre 変換

p = ∂L/∂q̇ (共役運動量)
H(q, p) = pq̇ − L(q, q̇)

H と L は **同じ力学の異なる窓 (gauge)**:
- L: (q, q̇) 空間 — 位置と速度
- H: (q, p) 空間 — 位置と運動量

| | Lagrangian | Hamiltonian |
|---|---|---|
| 変数 | (q, q̇) | (q, p) |
| 方程式 | 2階 ODE (Euler-Lagrange) | 1階 ODE の組 (Hamilton) |
| 量子化 | 経路積分 ∫Dq e^{iS} | 演算子 Ĥ, スペクトル |
| 自然な言語 | 場の理論、相対論 | 束縛系、スペクトル分析 |
| L1 での residence | **本ファイル** | q_quantum_observation.md |

### §2.2 ΣΦ 的意味: 二重窓 (dual window)

L と H は同じ S (力学系) に対する異なる W (窓):
- W_L = Lagrangian 窓: 位置-速度の初期/終端条件
- W_H = Hamiltonian 窓: 位置-運動量の初期条件

**A3 (gauge 不変性)**: L 記述と H 記述は gauge 変換で結ばれる。
物理的 observable (エネルギー、散乱振幅、...) は両方の窓で同じ値を与える。

q_quantum_thermodynamics.md の Legendre web (U↔F↔H↔G) はこの構造の
熱力学版。ここでは力学版を記述している。

---

## §3 経路積分 — 全経路の重ね合わせ

### §3.1 Feynman の経路積分

⟨q_f, t_f | q_i, t_i⟩ = ∫ Dq(t) exp(iS[q]/ℏ)

全ての可能な経路 q(t) について、各経路に位相 e^{iS/ℏ} を与えて重ね合わせる。

**ΣΦ 読み**: 
- S (structure) = 全経路空間 (無限次元)
- W (window) = 境界条件 q_i, q_f (有限窓)
- m (measurement) = ⟨f|i⟩ (遷移振幅)

**A0 の連続版**: 有限窓 (境界条件) を通して無限構造 (全経路) を見る。
各経路は位相 S[q]/ℏ で重みづけされ、干渉する。

### §3.2 停留位相近似 (saddle point)

ℏ → 0 で e^{iS/ℏ} は急速に振動 → 停留点 δS = 0 の近傍のみ寄与。

⟨f|i⟩ ≈ e^{iS_cl/ℏ} · det(−δ²S/δq²)^{-1/2}

**ΣΦ 読み**: 古典極限 = saddle point。
T8 の Boltzmann codim 重み e^{-c_s²·codim} は停留位相近似と
同種の構造 (exponential suppression of higher-order terms) を持つが、
T8 は離散 (codim ∈ ℤ)、saddle point は連続 (fluctuation ∈ ℝ) であり、
formal な同一視には intermediate step が必要 (→ OQ)。
saddle point の fluctuation determinant が 1-loop correction に対応。

### §3.3 量子化の対応 (H vs L)

| Hamiltonian 量子化 | 経路積分量子化 |
|---|---|
| [q̂, p̂] = iℏ | ∫Dq e^{iS/ℏ} |
| 時間発展 e^{-iĤt/ℏ} | ∫Dq e^{iS/ℏ} with 固定端 |
| スペクトル H|n⟩=E_n|n⟩ | saddle point + fluctuation |
| gauge_field_theory §4 BRST | gauge fixing in path integral |

---

## §4 Wick rotation — 振動から減衰へ

### §4.1 定義

t → −iτ (Minkowski → Euclidean)

e^{iS[q]/ℏ} → e^{-S_E[q]/ℏ}

Minkowski 作用 S (振動的、oscillatory) が
Euclidean 作用 S_E (減衰的、exponentially damped) に変わる。

### §4.2 なぜ回せるのか — ℂ common receptacle

phase_complex §4: ℂ は加法 (ι_L) と乗法 (χ) の共通受け皿。

Wick rotation はこの構造の **連続版**:

| phase_complex §4 | Wick rotation |
|---|---|
| ι_L: ℤ → S¹ ⊂ ℂ (加法→乗法) | e^{it}: ℝ → S¹ ⊂ ℂ (時間→位相) |
| χ: ℤ* → S¹ ⊂ ℂ (乗法→乗法) | e^{-τ}: ℝ → ℝ₊ ⊂ ℂ (虚時間→減衰) |
| ℂ = common receptacle | ℂ = t と τ を統一する体 |

**Wick rotation が可能な理由**: ℂ が両方 (振動 e^{it} と減衰 e^{-τ}) を
同時に収容するから。これは §4 の「ℝ では不十分、ℂ が必要」の **力学版**。

### §4.3 S12 加法→乗法 bridge

S12 Exponential Scan Family の 2 軸:
- 加法 scan: e^{i·scanner·data} (imaginary axis, S¹ rotation)
- 乗法 scan: e^{-scanner·data} (real axis, exponential damping)

**Wick rotation は S12 の 2 軸間の回転**:
t (加法 scan) → −iτ (乗法 scan)

| S12 member | Minkowski (加法) | Euclidean (乗法) |
|---|---|---|
| K(τ) ↔ Z(β) | K(τ) = |Σ e^{2πiτE}|² | Z(β) = Σ e^{-βE} |
| U(t) ↔ ρ(β) | U(t) = e^{-iHt} | ρ(β) = e^{-βH}/Z |
| F(h) ↔ Patterson | F(h) = Σ f e^{2πihx} | P(u) = Σ |f|² e^{-2πu²} |

### §4.4 S16 thermal bridge の理論的母体

S16 では K(τ) → Z(β) → C_v(T) → B(T) → |F(hkl)|² の thermal bridge を
経験的に確立した。Wick rotation はこの bridge の **理論的根拠**:

K(τ) (加法 scan, 位相空間) と Z(β) (乗法 scan, 温度空間) は
τ → −iβ/2π で結ばれる。S16-C の Wick residual tier はこの回転の
「1-operation overlay」として理解される。

**S12/S13 分離** (runtime/s12_s13_separation.md):
- Wick rotation 自体 = **S12 inter-axis map** (本節の scope)
- Wick 後の乗法軸上で β = ln2/ΔE という特定値が現れる場面 =
  **S13 consumer** (S13 が applicable になるが、Wick が S13 を含むわけではない)
- 本節は S12 map のみを記述。S13 consumer としての thermal 特殊値は
  QSM / QTD 側の記述に委ねる。

---

## §5 生成汎関数 Z[J] — 全相関の母関数

### §5.1 定義

Z[J] = ∫ Dφ exp(−S[φ] + ∫ J(x)φ(x) dx)

J(x) = 外部源 (source field)。

### §5.2 相関関数の生成

⟨φ(x₁)...φ(x_n)⟩ = (1/Z) δⁿZ[J] / δJ(x₁)...δJ(x_n) |_{J=0}

**Z[J] から全ての相関関数が得られる** (母関数)。

### §5.3 ΣΦ 的位置

Z[J] は S7 (class number formula) の場の理論版:
- S7: Res ζ_K(s) = 代数的不変量の積 (6-gauge)
- Z[J]: 場の理論の分配関数 = 全物理情報の母関数

gauge_field_theory §3.3 の S7→YM 因子対応は Z[J] を通して実現される。

### §5.4 連結生成汎関数 W[J] と有効作用 Γ[φ_cl]

W[J] = ln Z[J] (連結部分)
Γ[φ_cl] = W[J] − ∫ Jφ_cl (Legendre 変換)

| | Z[J] | W[J] | Γ[φ_cl] |
|---|---|---|---|
| 生成するもの | 全相関 | 連結相関 | 1PI (1-particle irreducible) 頂点 |
| 物理的意味 | 分配関数 | 自由エネルギー | 有効ポテンシャル |
| QTD 対応 | Z | F = −kT ln Z | G (Gibbs) |

**Legendre 変換が QTD §2 の熱力学ポテンシャル web と同一構造**。

---

## §6 Correlation → Spectrum bridge

### §6.1 Spectral representation

⟨φ(x)φ(0)⟩ = ∫ dμ ρ(μ) e^{-μ|x|}

スペクトル密度 ρ(μ) の Laplace 変換。

### §6.2 Pole = mass = gap

2点相関関数の最も遅い減衰:
⟨φ(x)φ(0)⟩ ~ e^{-m|x|} for |x| → ∞

**m = 最低質量 = spectral gap**。

ΣΦ 読み: 相関関数の指数減衰率 = S16 の K(τ) の τ→∞ 挙動。
mass gap Δ > 0 ⟺ 相関関数が指数的に減衰。

### §6.3 Mass gap の action 版定義

Hamiltonian 版: Δ = E₁ − E₀ (spectral gap)
Lagrangian 版: Δ = − lim_{|x|→∞} ln⟨φ(x)φ(0)⟩ / |x| (相関長の逆数)

**両者は Wick rotation で等価** (spectral theorem + transfer matrix)。

---

## §7 S12/S16 接続 — exp kernel の action 版

### §7.1 S12 exp kernel = 経路積分の kernel

S12: scan observable は exp(a(scanner)·b(data)) 型の kernel を持つ。

経路積分: ⟨f|i⟩ = ∫Dq exp(iS[q]/ℏ)。
S[q] = ∫ L dt は「data = q(t)」に対する「scanner = ℏ⁻¹」の作用。

**経路積分は S12 の exp kernel template を共有する上位構造**:
- scanner = ℏ⁻¹ (or β⁻¹ in Euclidean)
- data = 経路 q(t) (or 場 φ(x))
- kernel = exp(iS/ℏ) (or exp(−S_E/ℏ))

注: 経路積分は S12 の「instance」ではなく「上位構造」。
S12 は 1-variable scan (τ, β, s, ...) を記述するが、
経路積分は全経路空間上の functional integration。
共通するのは exp kernel の template であり、scope が異なる。

### §7.2 S16 tier の action 版意味

S16 tier は K(τ) の Fejér 乖離で定義される。
K(τ) は spectral autocorrelation。

Action 版: K(τ) の各 mode は exp(2πiτE_j) = exp(iS_j) の寄与。
Fejér kernel = 全 mode が等間隔 (自由場) の場合の K(τ)。

**S16 tier = 作用の mode 構造が自由場からどれだけ離れているか**。

- EXACT: S = Σ ½ωφ² (自由場、等間隔)
- STANDARD_FP: S = free + 弱い相互作用
- INTERMEDIATE_FP: S = free + 強い相互作用
- DEEP_FP: S = 強い束縛 (Coulomb 等)

### §7.3 ν の action 版意味

ν = σ(spacings)/μ(spacings)。

自由場: spacings 等間隔 → ν = 0。
相互作用: spacings 不等間隔 → ν > 0。

**ν は相互作用の「作用への寄与」の尺度**:
ν = 0 ⟺ S = quadratic (free)
ν > 0 ⟺ S に non-quadratic 項あり (interaction)

---

## §8 辞書接続

| 接続先 | 本ファイルが提供するもの | 方向 |
|---|---|---|
| q_quantum_observation.md | H↔L 双対 (§2)、量子化の対応 (§3.3) | parallel |
| QSM | Z(β) の path integral 版 (§3, §4) | upstream (母体提供) |
| QTD | Legendre web の力学版 (§5.4) | parallel |
| q_gauge_field_theory.md | S_YM の一般化 (§3)、BRST の path integral 版 | upstream |
| phase_complex §4 | Wick rotation の ℂ 的根拠 (§4.2) | downstream (具体化) |
| S12 | exp kernel の action 版 (§7.1) | downstream |
| S16 | thermal bridge の理論的母体 (§4.4)、tier の action 版意味 (§7.2) | downstream |
| c_spectral.md §8 | Z[J] → class number formula の場の理論版 (§5.3) | downstream |
| external_time.md | t/τ 分離の Wick rotation 版 (§4) | parallel |
