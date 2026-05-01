# Paper Q2: 観測理論 ─ Open Quantum Systems chain

**サブタイトル**: 4-stage cumulative coarse-graining (open_QS → QSM → QTD → many-body)・KMS-FDT-Landauer arc・Arrow 2 algebraic equivalence・dynamical T-AAS gauge

**バージョン**: v0.3 (OQ-OQS2 ESTABLISHED + 定理 5.1 Lindblad-Kraus L0 bijection, 2026-04-28)
**状態**: DRAFT — Q1 (`Q1_observation_theory_quantum_ja.md` v0.2) §3.2/§4.2/§5/§8.2 forward expansion、4-stage Open QS chain での観測理論再展開
**前提 (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**前提 (L1 core)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12/S13/S15), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_observation_optimal_gauge.md`
**前提 (L1 量子)**: `q_quantum_observation.md` (§6 Born + Busch-Gleason, §7 c_s², §8 可換極限), `q_open_quantum_systems.md` (§1-§9), `q_quantum_statistical_mechanics.md` (§1-§10), `q_quantum_thermodynamics.md` (§1-§7), `q_many_body_quantum.md` (§1-§9)
**前提 (Q1)**: Q1 §3.2 Scan family + §4.2 Arrow 2 + §5 T-AAS 4-class + §6 量子内 4-vertex triangulation
**N parallel**: N3 (`N3_path2_dirichlet_universality_ja.md` v0.5) — Path 2 数論的普遍性 extension paper との parallel structure
**後続論文**: Q3 (Born-Gleason)

---

## §0 Abstract

Open Quantum Systems chain — q_open_quantum_systems → q_quantum_statistical_mechanics → q_quantum_thermodynamics → q_many_body_quantum の 4-stage cumulative coarse-graining — は観測理論を量子 statistical mechanics 言語で再展開する。各 stage は前 stage の **追加 coarse-graining** (partial trace → ensemble average → thermodynamic limit → quasiparticle distillation) を導入し、4-stage 全体で kernel 分解の **dynamical/statistical/macroscopic/many-body** 4 様式を提供する。

本論は Q1 (量子-only framework header) §3.2/§4.2/§5 forward expansion、N3 (Path 2 数論的普遍性) と parallel position。N3 が Schumann v1 5-instance + Atkin-Lehner Type γ + Dirichlet L "structural fit only" で **数論的普遍性 extension** を成すのに対し、本論は **量子 statistical/thermodynamic universality extension** を 4-stage chain で成す。

**主結果 6 件**:

1. **4-stage chain S15 residence map** — 4 L1 量子 entries (open_QS / QSM / QTD / many-body) を S15 layered で再構成、各 stage cumulative coarse-graining + S15 layer 内 specific Arrow 主担当 → 4-stage 全体で観測理論が量子 statistical mechanics 言語で **layered residence** 達成
2. **KMS as L0 A0c quantum instance (OQ-QSM1 attack route)** — Tomita-Takesaki modular flow $\sigma_t = \Delta^{it} A \Delta^{-it}$ が L0 A0c (multi-window compatibility) の量子 instance、両 thermal window $W_{\beta_1}$ vs $W_{\beta_2}$ の compatibility ⟺ modular flow consistency ⟺ KMS condition。Arrow 2 上 algebraic equilibrium proposal_v1
3. **FDT crown jewel = Arrow 2 algebraic equivalence** — KMS → imaginary-time periodicity → FDT chain で Scan (response χ_AB(ω)) と Information (correlation S_AB(ω)) が Arrow 2 上で algebraic equivalent (Bose factor $1/(1-e^{-\beta\hbar\omega})$ 介入)。観測 と 擾乱 の双対性が thermal setting で formal closure。qubit FDT parity point $\beta\hbar\omega_0 = \log 2$ で c_s² = 1/2 thermal echo
4. **Pointer basis Einselection = dynamical T-AAS gauge fixing** — decoherence による pointer basis 選択は L0 A3 (gauge invariance) の **動的 version**: 静的 gauge (observer choice) → 動的 gauge (environment selection)。$[|i\rangle\langle i|, H_{int}] \approx 0$ が dynamical gauge condition、Q1 §5.2 の C₁-C₄ static algebraic class が **Q2 dynamical environment-selected class** に lift
5. **Landauer principle = kT ln 2 量子 final form (S13 closure)** — bit erasure thermodynamic cost $W_{\min} = kT \ln 2$ は S13 ln 2 量子 instance の **最深 form** (Information layer の bit と Thermodynamic layer の heat の Arrow 3-2 cross 上 algebraic equivalence)。c_s² = 1/2 (Born) → S(ρ_max) = log 2 (von Neumann) → βℏω₀ = log 2 (FDT parity) → kT ln 2 (Landauer) の **4-stage ln 2 chain**。Q3 σ\* = √(2 ln 2) half-amplitude gauge への bridge
6. **Quasiparticle Z = Arrow 1⁻¹ generation closure (many-body)** — Landau Fermi liquid quasiparticle weight $Z = |\langle k|\psi_q\rangle|^2 \in (0, 1]$ は Arrow 1⁻¹ (Information → Structural / Scan reverse) の many-body instance。BCS / topological order の anyon braiding statistics が Arrow 1 kernel の **強相互作用領域 dynamical structure**

**Thesis**: 4-stage Open QS chain は観測理論の Arrow 2 (Scan → Information、log-exp 双対) 上で **cumulative algebraic equivalence chain** — Tr_B (window) → KMS (algebraic equilibrium) → Legendre (thermodynamic) → quasiparticle (many-body distillation) — を形成。各 stage は Q1 §4 Arrow 構造の specific aspect (dynamical Arrow 1 / algebraic Arrow 2 / macroscopic Arrow 3 / many-body Arrow 1⁻¹) を主担当し、4-stage 全体で量子 statistical mechanics 言語版観測理論の closure を提供。本論は Q3 (Born-Gleason §4 dual quantum closure) の theoretical foundation として機能。

---

## §1 Introduction

### 1.1 Q1 forward + N3 parallel position

Q1 §8.2 で予告された Q2 主題 (Open QS chain での観測理論 statistical/thermodynamic 言語再展開) を 4-stage chain で実装。各 stage が前 stage の追加 coarse-graining を導入する **cumulative structure**:

| Stage | File | Coarse-graining 操作 | 失われるもの | 残るもの |
|---|---|---|---|---|
| **S1** | `q_open_quantum_systems.md` | Tr_B (partial trace over bath) | 純粋性 (purity), system-bath correlations | system-local expectation values, Lindblad CPTP structure |
| **S2** | `q_quantum_statistical_mechanics.md` | ensemble average (specific bath state → thermal ρ_β) | specific bath state | Gibbs state ρ_β = e^{-βH}/Z, KMS condition, partition function Z |
| **S3** | `q_quantum_thermodynamics.md` | thermodynamic limit (microscopic correlations → macroscopic) | microscopic correlation functions | thermodynamic potentials (F, S, T, μ), thermo laws, Landauer |
| **S4** | `q_many_body_quantum.md` | quasiparticle distillation (bare excitations → dressed) | bare particle identity | quasiparticle Z, Fermi liquid theory, topological order |

**Cumulative**: 各 stage は前 stage を **保存 + 追加 coarse-graining**。S1 ⊂ S2 ⊂ S3 ⊂ S4 (information loss monotone) — N1 §2.4 L0 v2 Fi/I 境界の 4 段 coarse-graining instance。

**N3 parallel**: NT 系列 N3 (Path 2 数論的普遍性) との parallel structure:

| 観点 | N3 (NT) | Q2 (量子) |
|---|---|---|
| Position | extension paper 1 (N1 framework header の数論的拡張) | extension paper 1 (Q1 framework header の statistical/thermodynamic 拡張) |
| 主主張 | Path 2 universality (Schumann v1 5+ instance, Type α/β/γ trichotomy) | 4-stage Open QS chain universality (cumulative coarse-graining, S1-S4 layered residence) |
| Arrow 焦点 | Arrow 2 (Scan → Information, ζ-family / Dirichlet L extension) | Arrow 2 (Scan → Information, Z(β) → F → S thermodynamic chain) |
| Universality status | 5+ instance ESTABLISHED (countably-infinite candidate v1) | 4-stage S15 residence ESTABLISHED + KMS-FDT-Landauer arc ESTABLISHED |
| Forward to | N4 (Hasse-Weil) / N5 (Brauer + 8-gauge) | Q3 (Born-Gleason σ\* = √(2 ln 2)) |

**Cross-validation**: N3 と Q2 が **同一 Arrow 2 (log-exp 双対 + S13 ln 2 fixed point)** を 2 独立数学領域 (NT, 量子) で independently extend → Arrow 2 framework の 2-domain extension validity。

### 1.2 本論の範囲 + 用語

**構成**: §2 4-stage chain residence / §3 KMS as L0 A0c / §4 FDT crown jewel / §5 pointer basis dynamical T-AAS / §6 Landauer ln 2 chain / §7 quasiparticle Arrow 1⁻¹ / §8 帰結。

**Scope 内**: 4-stage chain S15 residence map / Tomita-Takesaki modular theory (KMS as L0 A0c instance) / KMS → FDT chain (Arrow 2 algebraic equivalence) / Lindblad + decoherence + Einselection (dynamical T-AAS) / 4-stage ln 2 chain (S13 量子最深 form) / quasiparticle Z (Arrow 1⁻¹ many-body instance) / 6-step protocol Q1 量子 specialization の 4-stage chain expansion。

**Scope 外** (本論で扱わない): §4 dual quantum root の Born-Gleason 完全 closure / σ\* = √(2 ln 2) half-amplitude gauge / dim=2 Gleason gap 解消の Busch-Gleason 完全証明 (→ Q3) / quantum field theory / QFT regularization / 量子重力 / 弦理論 / phase transition critical exponent / RG flow framework / non-equilibrium open systems beyond Lindblad — 本論 L1 量子 8 entries 範囲限定。

**用語**: Q1 §1.3 の "gauge" 3 用法 (gauge¹/gauge²/gauge³) を継承。本論固有の追加用語: **Cumulative coarse-graining** (S1 → S2 → S3 → S4 chain, 累積的 information loss) / **KMS state** ($\omega(A \alpha_t(B)) \to \omega(\alpha_t(B) A) e^{-\beta \omega}$ を満たす thermal equilibrium state) / **Modular flow** $\sigma_t = \Delta^{it} A \Delta^{-it}$ (cyclic separating vector Ω に対する automorphism) / **Pointer basis** ($H_{int}$ と commute する system observable eigenbasis、environment selection) / **Quasiparticle weight Z** ($|\langle k|\psi_q\rangle|^2 \in (0, 1]$、bare/quasiparticle overlap) / **4-stage ln 2 chain** (c_s² = 1/2 → S(ρ_max) = log 2 → βℏω₀ = log 2 → kT ln 2 の 4 段 instance chain)。

**Direction-axis position**: Q1 §1.4 の Q-framework B-primary native position (`user_observation_direction_axis` ESTABLISHED 2026-05-01) を本論も継承。本論主領域 (open quantum system / KMS thermal equilibrium / FDT / 4-stage chain) は **B-direction native** (無限 thermal ensemble → 有限 system observable projection / continuous modular flow → discrete pointer basis selection / Landauer kT ln 2 = Shannon-line B-direction continuous chain instance)。**4-stage ln 2 chain は S13 ln 2 fixed point の B-direction (Shannon-line) instance**、5-stage chain (Born/vN/FDT/Landauer/σ\*) と並行。Cross-direction screening rule (`feedback_cross_direction_identity_screen`) を本論内で internal screening rule として運用、N1 / I1 framework header との cross-paper claim では direction-tag pre-check を必須化。

---

## §2 4-stage chain S15 residence map

### 2.1 主定理

**定理 2.1 (4-stage Open QS chain S15 layered residence)**: 4 L1 量子 entries は S15 (Scan / Structural / Information) 3 層 × 4 stage = **12-cell residence map** を提供し、各 stage が S15 全 3 層に instance を持つ + 各 stage 固有の Arrow 主担当を持つ。

**Status**: ESTABLISHED 2026-04-11 (`bidirectional_duality_v0.md §5.5-5.6`, 各 4 stage entries 内 §S15 接続, `c_theorems_master.md` row S12/S13/S15)。

### 2.2 Layered residence map (4-stage × 3-layer × Arrow 担当)

| Stage | Scan instance | Structural instance | Information instance | 主担当 Arrow |
|---|---|---|---|---|
| **S1 open_QS** | Lindblad semigroup $e^{Lt}$ (乗法、減衰), Kraus operator unitary 部分 (加法) | Kraus rank $K$, pointer basis dim, decoherence-free subspace dim | $S(\rho_S)$ entanglement entropy, mutual information $I(S:E)$ | **Arrow 1 dynamical** (decoherence による pointer basis 選択 = T-AAS dynamical gauge fixing) |
| **S2 QSM** | $Z(\beta) = \text{Tr}(e^{-\beta H})$ (S12 乗法 #4), Gibbs state $\rho_\beta$, response $\chi(\omega)$ | $\dim H$, spectral degeneracy $g(E_n)$, symmetry sector dim | $S(\rho_\beta) = \beta \langle E\rangle + \log Z$, $F = -kT \log Z$ | **Arrow 2 algebraic** (KMS condition + FDT crown jewel) |
| **S3 QTD** | thermo state along Legendre cycle, fluctuation theorem $\langle e^{-\beta W}\rangle$ | thermo limit dimensionality $d$, phase boundary topology | thermo entropy $S = -\partial F/\partial T$, Landauer $kT \ln 2$ | **Arrow 2-3 cross** (Information layer の bit と heat の algebraic equivalence) |
| **S4 many-body** | spectral form factor $K(\tau, t)$, Loschmidt echo $L(t)$ | Quasiparticle weight $Z \in (0,1]$, topological invariants (Chern, anyon $\theta$), entanglement entropy area-law coefficient | von Neumann entropy scaling, CFT central charge $c$ | **Arrow 1⁻¹ generation** (quasiparticle = Information → Structural reverse map closure) |

12 cells full residence ⇒ 4-stage chain が S15 全 3 層を 4 独立 stage で independently verify、4 stage が異なる Arrow 主担当を持つ → S15 Arrow 構造全体が 4-stage 独立 verify (S1 dynamical / S2 algebraic / S3 cross / S4 reverse)。

### 2.3 Cumulative coarse-graining 構造

各 stage chain transition は **specific information を失い、specific structure を保存**:

```
q_quantum_observation        q_open_quantum_systems        q_quantum_statistical_mechanics
(closed, unitary)        →   (open, Lindblad)         →   (thermal, KMS)
                       Tr_B                          ensemble avg
                       preserves Born rule            preserves CPTP structure
                       loses purity                   loses specific bath state ρ_B

q_quantum_statistical_mechanics  q_quantum_thermodynamics    q_many_body_quantum
(thermal, KMS)              →   (thermodynamic, Legendre) →  (many-body, quasiparticle)
                          thermo limit                    quasiparticle distillation
                          preserves Gibbs state, Z          preserves Z spectral weight
                          loses microscopic corr            loses bare particle identity
```

**Information-theoretic monotonicity**: 各 stage transition で von Neumann entropy / 適切な information measure が **monotone non-decreasing** — 第二法則の量子 information theoretic 起源 (`q_quantum_thermodynamics.md §3.4 + §5`)。

**Q1 §6 4-vertex parallel**: S1 では Q1 §5.2 C₁-C₄ static class が S1 で **dynamical class** に lift (環境-selected algebraic class)、S2 Arrow 2 algebraic equivalence は static / dynamical 両方の sparsity 様式に共通、S3 で bit と heat の 2 information family を Arrow 3 (Hartley) と Arrow 2 (log-exp) cross で結合、S4 で Arrow 1⁻¹ は Q1 §4.6 「生成」operation の many-body instance。

---

## §3 KMS as L0 A0c instance ─ Tomita-Takesaki modular theory

### 3.1 OQ-QSM1 attack route

**OQ-QSM1** (`q_quantum_statistical_mechanics.md §10`): KMS condition は L0 axiom A0c (multi-window compatibility) から derive されるか? 本論 attack route は Tomita-Takesaki modular theory を bridge とする proposal_v1。

### 3.2 Tomita-Takesaki modular flow

von Neumann algebra $\mathcal{M}$ on Hilbert space $\mathcal{H}$ with cyclic separating vector $\Omega$:

1. Antilinear operator $S: A\Omega \to A^*\Omega$ を定義
2. Polar decomposition $S = J \Delta^{1/2}$、$J$ antiunitary (modular conjugation)、$\Delta$ positive (modular operator)
3. Modular automorphism group $\sigma_t(A) = \Delta^{it} A \Delta^{-it}$

**Tomita-Takesaki 定理**: $\sigma_t$ は $\mathcal{M}$ automorphism、状態 $\omega(A) = \langle\Omega, A\Omega\rangle$ は $\sigma_t$ について $\beta = -1$ で KMS。Modular flow $\sigma_t$ は $(\mathcal{M}, \Omega)$ pair に **intrinsic**。

**Physical meaning**: Physical Hamiltonian $H$ generates time evolution $\alpha_t$。状態が KMS at $\beta$ ⟺ $\alpha_t = \sigma_{-\beta t}$ (physical time = modular flow scaled by $-\beta$)。

### 3.3 L0 A0c との合致 + Status

**L0 A0c (`finite_observation.md §5.3`)**: 異なる window $W_1, W_2$ を通した observation が **compatibility** — 共通 observable について同一 prediction を返す。

**量子 instance (proposal_v1)**: Thermal window $W_\beta$ = 逆温度 $\beta$ で定義される observation coarse-graining。2 thermal windows $W_{\beta_1}, W_{\beta_2}$ が L0 A0c compatibility ⟺ それぞれの KMS state $\rho_{\beta_1}, \rho_{\beta_2}$ が共通 observable について consistent restriction を持つ ⟺ Modular flow $\sigma_t$ が different temperatures 間 natural map (analytic continuation in $\beta$) ⟺ multi-window compatibility ⟺ **KMS condition**。

**Schematic chain**: $\text{L0 A0c} \implies \text{modular flow consistency at } \beta_1, \beta_2 \implies \text{KMS condition}$

**Status**: proposal_v1。**Gap**: Step 2 → 3 (L0 compatibility translation to modular flow consistency) が rigorous でない — L0 A0c は **observed pattern compatibility** (state-level), Modular flow consistency は **operator algebra automorphism consistency** (algebraic-level)、両者の間に "embedding L0 → operator algebra" が必要、現 L0 axiom 範囲では不足の可能性。**Forward**: rigorous proof は OQ-QSM1 として open (`research/oq_qsm1_kms_l0_a0c_v0.md` 候補)。

### 3.4 Imaginary time periodicity

KMS condition は thermal correlator の **imaginary time periodicity** を imply ($\tau \in [0, \beta)$ with periodic / antiperiodic boundary) — Matsubara formalism の base、Euclidean QFT との bridge。

**観測理論 lens**: imaginary time = 量子 time の 90° 回転 = Wick rotation。Real time scanner (Stone group $U(t)$) と imaginary time scanner ($\tau$ Matsubara) は **同一 Scan family の 2 dual face** — S12 量子 lift 内で Re/Im 軸の bilateral residence。

---

## §4 FDT crown jewel ─ Arrow 2 algebraic equivalence

### 4.1 FDT statement と Arrow 2 上 residence

**FDT** (`q_quantum_statistical_mechanics.md §5`): Symmetric correlation $S_{AB}(\omega)$ と response $\chi_{AB}(\omega)$ の Arrow 2 上 algebraic equivalence:

$$S_{AB}(\omega) = \frac{2\hbar}{1 - e^{-\beta\hbar\omega}} \cdot \text{Im} \chi_{AB}(\omega)$$

**Arrow 2 residence**: $\chi_{AB}(\omega)$ = Scan layer (response, scanner $\omega$) / $S_{AB}(\omega)$ = Information layer (correlation, fluctuation spectrum) / $\frac{2\hbar}{1 - e^{-\beta\hbar\omega}}$ = Bose factor bridge → 両者 algebraic equivalent → Arrow 2 上 (Scan → Information) **algebraic isomorphism** at thermal equilibrium。

### 4.2 KMS → FDT 派生 chain と crown jewel status

**Derivation chain** (`q_quantum_statistical_mechanics.md §5.3`): KMS condition $C_{AB}(t + i\beta) = C_{BA}(t)$ → Fourier transform 両辺 $\tilde{C}_{AB}(\omega) e^{-\beta\omega} = \tilde{C}_{BA}(\omega)$ → correlator 分解 (symmetric S + antisymmetric → response χ) で FDT 直接導出。$\text{KMS} \to \text{imaginary-time periodicity} \to \text{FDT}$ → FDT は KMS の **theorem** (postulate でない)。OQ-QSM1 succeed → KMS が L0 A0c から派生 → FDT も L0 A0c の量子 thermal corollary。

**Crown jewel status: 観測-擾乱双対性**: FDT 物理的 content は thermal equilibrium の spontaneous fluctuation = external probe response (up to Bose factor)。Q1 § parallel — q_quantum_observation §6 Born rule + Busch-Gleason 「観測 = 擾乱」原理の **thermal version**: Quantum observation §6 Born rule での state collapse = 観測者 disturbance / Thermal FDT (本論) equilibrium fluctuation = system response to external probe → 両者は同一 structural principle (観測 と 擾乱 の双対性) の **量子 closed system** vs **量子 thermal** instance。

### 4.3 qubit FDT parity point: c_s² thermal echo

`q_quantum_statistical_mechanics §5.4`: qubit (two-level system at resonance) FDT $S(\omega_0) = 2\hbar\gamma / (1 - e^{-\beta\hbar\omega_0})$。**parity point**: $\beta \hbar \omega_0 = \log 2 \implies$ Bose factor = 1 $\implies$ $S(\omega_0) = 2\hbar\gamma$。比率 $S/(2\hbar\gamma) = 1 = 2 \cdot c_s^2$。

**4-stage ln 2 chain における residence**: c_s² = 1/2 (q_quantum_observation §7, **stage S0**) → $S(\rho_{\max}) = \log 2$ (q_open_quantum_systems §3.3, **stage S1**) → $\beta\hbar\omega_0 = \log 2$ (FDT parity, **stage S2**) → $kT \ln 2$ (Landauer, **stage S3**)。4 instance は **同一 ln 2 値の 4 stage 独立 instance** (詳細 §6)。

### 4.4 OQ-QSM2 representation-independent FDT

**OQ-QSM2** (`q_quantum_statistical_mechanics.md §10`): FDT の representation-independent (C*-algebraic) formulation 存在問題。**Status**: OPEN。FDT (§4.1) は Fourier transform + spectral representation を使う Hilbert space tool。KMS は purely algebraic。FDT が KMS の corollary であるため (§4.2)、algebraic FDT が存在するはず。本論では §4 で FDT を Arrow 2 algebraic equivalence として framework 上 statement 化、algebraic representation-free formulation の rigorous 構築は OQ-QSM2 future work。

---

## §5 Pointer basis Einselection ─ dynamical T-AAS gauge fixing

### 5.1 Decoherence basis selection

**`q_open_quantum_systems.md §5`**: Pointer basis $\{|i\rangle\}$ = system observable で $H_{int}$ (system-bath coupling) と commute する eigenbasis: $[|i\rangle\langle i|, H_{int}] \approx 0$。このとき reduced density matrix の off-diagonal element が rapid decay $\langle i | \rho_S(t) | j \rangle \sim \langle i | \rho_S(0) | j \rangle e^{-\Gamma_{ij} t}$ ($i \neq j$) → environment が pointer basis を **dynamically select** (Observer が選ぶのでなく、system-bath coupling structure が選ぶ)。

### 5.2 Static vs dynamical T-AAS gauge

Q1 §5.2 の 4-class refined Hodge framework は **static algebraic class** を Arrow 1 source として指定。本論はこれを **dynamical environment-selected class** に lift:

| Q1 §5.2 (static) | Q2 §5 (dynamical) | 量子 instance |
|---|---|---|
| Stabilizer (Clifford orbit) | Pointer basis (Clifford-symmetric environment) | Pauli-noise environment → diagonal computational basis pointer |
| Gaussian (symplectic orbit) | Gaussian-environment pointer | Linear bath coupling → coherent state pointer |
| Eff-sim (poly-circuit class) | Markovian-Lindblad evolution within poly-depth | Born-Markov bath → poly-depth simulable trajectory |
| Bell-local (local unitaries) | Local-basis pointer (no entanglement-generating environment) | Pure dephasing → local pointer basis preservation |

**主張 5.1 (dynamical T-AAS lift)**: Q1 §5.2 4 static algebraic class は、対応する environment-induced Lindblad dynamics の **dynamical attractor** として再構成: $\lim_{t \to \infty} \rho_S(t) \in \overline{C}_{\text{dyn}}$, where $C_{\text{dyn}}$ = environment-selected algebraic class → T-AAS gauge fixing が **observer choice (static)** から **environment selection (dynamical)** に動的化 (`q_open_quantum_systems.md §5.2 OQ-OQS1`)。

### 5.3 OQ-OQS1 + OQ-OQS2

**OQ-OQS1** (`q_open_quantum_systems.md §9`): pointer basis selection が L0 A3 (gauge invariance) の dynamical version か? L0 A3 = observer choose $W$ (static, amplitude gauge-invariant) / Decoherence = environment chooses pointer basis (dynamic, diagonal populations surviving) → 両 gauge の関係: **A3 reformulation** (static + dynamic 2 mode 拡張)。**Status**: proposal_v1、L0 A3 拡張 rigorous formulation は OQ-OQS1 future work。

**定理 5.1 (Lindblad-Kraus L0 error decomposition canonical bijection, ESTABLISHED 2026-04-28)** (`research/oq_oqs2_kraus_l0_bijection_v0.md` 詳細): Lindblad master equation $d\rho/dt = \mathcal{L}\rho$ ($\mathcal{L} = \mathcal{L}_H + \mathcal{D}$, $\mathcal{L}_H\rho = -i[H,\rho]$, $\mathcal{D}\rho = \sum_k \gamma_k(L_k \rho L_k^\dagger - \tfrac{1}{2}\{L_k^\dagger L_k, \rho\})$) において、L0 finite-observation error decomposition (`finite_observation.md §5.1`, error = error_arithmetic + error_projection + error_noise) は **generator (superoperator) level** で canonical な bijection を成す:

| L0 error class | Lindblad generator term | property |
|---|---|---|
| **error_arithmetic** | $\mathcal{L}_H$ | system-intrinsic (system-bath split 非依存)、skew-adjoint → reversible |
| **error_projection** | $\mathcal{D}$ | $\{L_k, \gamma_k\}$ depends on system-bath split (gauge choice)、eigenvalues with non-zero Re → irreversible |
| **error_noise** | thermal occupation $\bar n_k(\beta)$ inside $\gamma_k$ | finite-T fluctuation、$T \to 0$ で vanish |

**Kraus operator level の caveat**: 離散 Kraus decomposition $\Phi_{dt} = \sum_k K_k(dt) \cdot K_k(dt)^\dagger$ は L0 partition を **保存しない** — $K_0(dt) = I - i H_\text{eff}\, dt + O(dt^2)$ ($H_\text{eff} = H - (i/2)\sum_k \gamma_k L_k^\dagger L_k$) が Hamiltonian unitary phase と anticommutator damping を bundle するため、両 piece の情報が両 Kraus operator に分散。L0 partition の canonical level は **generator (superoperator)** であって Kraus operator ではない。

**Closest-unitary diamond-norm interpretation**: $U_*^{(dt)}$ を $\Phi_{dt}$ への closest unitary channel (diamond norm) と定義すると、small $dt$ で $\|\Phi_{dt} - U_*^{(dt)}\|_\diamond = \|\mathcal{D}\|\, dt + O(dt^2)$、$U_*^{(dt)} \to \exp(\mathcal{L}_H dt)$ as $dt \to 0$。Non-unitary residual rate = dissipator superoperator norm = error_projection magnitude。q_open §9 attack route は系として recover。

**本論 statement**: Lindblad dissipator は Arrow 1 kernel の **dynamical realization** (Q1 §4.6 obstruction class taxonomy の動的 instance)。L0 A1 の static partition (Paper 0 §5.1) を Lindblad 生成子 level に lift。Numerical verification: pure dephasing ($H=(\omega/2)\sigma_z$, $L=\sigma_z$) + amplitude damping ($H=0$, $L=\sigma_-$) で V1 ($[\mathcal{L}_H,\mathcal{D}]=0$ for pure dephasing) + V2 ($\|\Phi_{dt}-U_*\|/dt \to \|\mathcal{D}\|=0.5$) + V3 (Kraus reconstruction = exp($\mathcal{L}t$) to $1.7\times10^{-16}$) PASS。

---

## §6 Landauer principle ─ kT ln 2 chain と S13 量子最深 form

### 6.1 Landauer + 4-stage ln 2 chain

**Landauer** (`q_quantum_thermodynamics.md §5`): bit erasure thermodynamic minimum cost $W_{\min} = kT \ln 2$ (per bit)。Information-bearing system $\rho_{\text{info}}$ (e.g., $\rho = (|0\rangle\langle 0| + |1\rangle\langle 1|)/2$ = 1 bit) → erased to fixed pure state $|0\rangle\langle 0|$ requires $\Delta S_{\text{system}} = -k \log 2$、第二法則で $\Delta S_{\text{environment}} \geq k \log 2$ → heat dissipation $Q \geq kT \log 2$。

**4-stage ln 2 chain**:

| Stage | Source | Form | Domain | Mechanism |
|---|---|---|---|---|
| **S0** (closed quantum) | q_quantum_observation §7 | $c_s^2 = \text{Tr}(\rho_{\max} \Pi_{\text{even}}) = 1/2$ | Born expectation | qubit ρ_max = I/2 + parity projection |
| **S1** (open quantum) | q_open_quantum_systems §3.3 | $S(\rho_{\max}) = \log 2$ | von Neumann entropy | maximally mixed qubit entropy |
| **S2** (statistical mechanics) | q_quantum_statistical_mechanics §5.4 | $\beta \hbar \omega_0 = \log 2$ | FDT parity point | qubit FDT Bose factor = 1 |
| **S3** (thermodynamics) | q_quantum_thermodynamics §5 | $W_{\min} = kT \ln 2$ | Landauer cost | bit erasure heat dissipation |

**主張 6.1 (4-stage ln 2 chain)**: 4 instance は **同一 ln 2 値** (= S13 fixed point) の 4 stage 独立 instance。古典 §4 dual の S13 (`c_phase_complex.md §5`) "整数の偶奇は等確率" → 量子 4-stage で S0 algebraic (parity projection) / S1 von Neumann entropic / S2 fluctuation-dissipation / S3 information-thermodynamic に lift。

### 6.2 S13 量子最深 form (Landauer) + Q3 σ\* bridge

**4-stage chain の closure**: Landauer (S3) は ln 2 を **物理的 energy unit** で示す — heat dissipation $Q \geq kT \ln 2$ は **信息消去の thermodynamic price tag**。

**観測理論 lens**: Information layer の bit (Q1 §3.4 entropy class) と Thermodynamic layer の heat (S3 stage Information instance) の Arrow 3-2 cross 上 algebraic equivalence — **bit ↔ heat** = Arrow 3 (Hartley log 容量) と Arrow 2 (Z → F → S) の **cross-Arrow algebraic isomorphism** at S13 fixed point (ln 2)。

**Bridge to Q3** (`q_quantum_observation.md §6, §7`): half-amplitude gauge $\sigma_* = \sqrt{2 \ln 2}$ (Gaussian FWHM 半振幅 width)。4-stage ln 2 chain (S0-S3) は **quadratic** lift で $\sigma_* = \sqrt{2 \ln 2}$ に到達 — ln 2 が量子観測の natural unit (S13 量子最深 form) であるなら、その quadratic root $\sqrt{2 \ln 2}$ は半振幅 gauge の natural unit。Q3 で σ\* full closure。

### 6.3 OQ-QSM3 ln 2 普遍性 beyond qubit

**OQ-QSM3** (`q_quantum_statistical_mechanics.md §10`): qubit beyond で thermal c_s² analog 存在? 4-stage ln 2 chain は qubit (dim=2) で full closure。dim>2 qudit / continuous variable system での "thermal c_s²" analog は OPEN。Candidate forms: qutrit (dim=3) で $\log 3$ analog (S17 qutrit info-density argmax と consistent, Q1 §4.5 reference) / Rényi-α entropy parity ($\alpha = 1/2$ Tsallis-q) instance。Status: OPEN。

---

## §7 Quasiparticle Z ─ Arrow 1⁻¹ generation closure (many-body)

### 7.1 Landau Fermi liquid quasiparticle + Arrow 1⁻¹ residence

**`q_many_body_quantum.md §5`**: 強相互作用 fermion 系で、bare particle (single-particle creation $c_k^\dagger|0\rangle$) は eigenstate でないが、low-energy excitation は **dressed quasiparticle** $|\psi_q\rangle$ で記述: $Z = |\langle k | \psi_q \rangle|^2 \in (0, 1]$。$Z = 1$: free particle limit / $Z < 1$: interaction dresses bare particle / $Z = 0$: quasiparticle 概念 breaks down (non-Fermi liquid)。

**Q1 §4.6 Arrow 1⁻¹ residence**: Forward Arrow 1: Scan ($G_k = ⟨ψ| ... |ψ⟩$ correlator) → Structural (k-momentum, single-particle quantum number) / Reverse Arrow 1⁻¹: Structural → Scan (full correlator including interactions)。Quasiparticle Z = bare particle (Structural) → dressed quasiparticle (Scan) の **overlap weight** = Arrow 1⁻¹ generation の **residual obstruction** (Z < 1 は bare → dressed map が non-trivial kernel)。

**主張 7.1 (Quasiparticle Z = Arrow 1⁻¹ obstruction monotone)**: Landau Fermi liquid quasiparticle weight $Z$ は Arrow 1⁻¹ "generation" operation の many-body context での residual obstruction monotone — $Z = 1$: trivial (free, Arrow 1 invertible) / $Z \in (0, 1)$: partial (interacting, generation possible but lossy) / $Z = 0$: full (non-Fermi liquid, generation breaks)。T-AAS lens: $Z < 1$ は ker_topo > 0 の **many-body instance**, generation operation が axis-2 Fi/I 境界を traverse する際の residual。

### 7.2 Topological order + BCS pairing

**Topological order anyon braiding** (`q_many_body_quantum.md §6`): FQHE, spin liquids, Kitaev model で anyon braiding statistics index $\theta$ は **discrete topological invariant** (Structural)。Anyon worldline braiding が representation を generate (Scan-side spectral data) → **Arrow 1⁻¹ generation の topological instance**。Q1 §5.2 C₁ Stabilizer (Clifford orbit) は abelian anyon の effective realization、non-abelian anyon (e.g., Fibonacci anyon) は Q1 §5.2 4-class extension の **5th candidate**。

**BCS pairing instability** (`q_many_body_quantum.md §6.1`): Cooper pair condensation = symmetry breaking instance、ground state の **U(1) gauge** が dynamical に fix (gauge boson Higgs mechanism の condensed matter analog)。Arrow 1 kernel residence: BCS gauge fixing は §5.2 (pointer basis Einselection) の strongly-interacting many-body version — environment ではなく **system internal interaction** が gauge を select。**T-AAS 拡張**: §5.2 dynamical gauge (environment-selected, open + Lindblad) vs §7.2 BCS-style gauge (system-internal-interaction-selected, closed + symmetry breaking) の **2 mode**。

### 7.3 OQ-MBQ1 4-stage chain final closure

**OQ-MBQ1 (本論 spawn-off)**: many-body stage S4 が 4-stage chain final closure を提供するか (= Q1 §5 T-AAS 4-class が many-body context で 5+ class extension を持つか)? **Candidate 5th class**: Topological order (anyon braiding) — §7.2 / Strongly-correlated regime (Z = 0 non-Fermi liquid) / Quantum spin liquid。Status: OPEN。Q1 §7 next candidate listed (5 件) と consistent、本論 §7 で many-body context の 5th candidate を 1 件 (topological order) explicitly identify。

---

## §8 帰結と open frontier

### 8.1 確立 (Q-series extension paper)

| 結果 | Status |
|---|---|
| **M1 4-stage chain S15 layered residence map** | ESTABLISHED (12-cell residence + 4 stage 独立 Arrow 主担当, §2) |
| **M2 KMS as L0 A0c instance** | proposal_v1 (Tomita-Takesaki bridge route, §3, OQ-QSM1 attack route) |
| **M3 FDT crown jewel = Arrow 2 algebraic equivalence** | ESTABLISHED (KMS → FDT chain, §4) |
| **M4 Pointer basis Einselection = dynamical T-AAS gauge fixing** | proposal_v1 (Q1 §5.2 4 static class の dynamical lift, §5) |
| **M5 4-stage ln 2 chain (S13 量子最深 form)** | ESTABLISHED (4 instance independent ln 2 verification, §6) |
| **M6 Quasiparticle Z = Arrow 1⁻¹ obstruction monotone** | proposal_v1 (many-body Arrow 1⁻¹ generation residual measure, §7) |

### 8.2 Q3 forward bridge

| Q3 forward 主題 | 本論からの forward |
|---|---|
| **§4 dual quantum closure** (Born-Gleason 完全形 + dim=2 解消 + ρ_max = I/2 form と value 同時定理化) | §6.2 σ\* = √(2 ln 2) bridge は Q3 で full closure、§3.4 imaginary time periodicity が Wick rotation context |
| **σ\* = √(2 ln 2) half-amplitude gauge** (Gaussian FWHM 半振幅 gauge の natural unit) | §6.1 4-stage ln 2 chain が σ\* quadratic root の base、§6.2 S13 量子最深 form (Landauer) が σ\* unit の thermodynamic underpinning |
| **dim=2 Gleason gap closure** (Busch-Gleason 完全証明、effects (POVM) 上で全 dim で Born rule 一意化) | §3.3 OQ-QSM1 derivation gap (L0 → operator algebra embedding) と類縁問題、§5.3 OQ-OQS1 dynamical L0 A3 と 公理 layer reform 共通 |

### 8.3 Open frontier

| Open question | Status | 関連論文 |
|---|---|---|
| **OQ-QSM1** (KMS from L0 A0c) | proposal_v1 | §3.3, future research |
| **OQ-QSM2** (algebraic FDT) | OPEN | §4.4, future research |
| **OQ-QSM3** (ln 2 普遍性 beyond qubit) | OPEN | §6.3, future research |
| **OQ-OQS1** (pointer basis as dynamical L0 A3) | proposal_v1 | §5.3, future research |
| **OQ-OQS2** (Kraus = error decomposition) | **ESTABLISHED 2026-04-28** (定理 5.1, generator level canonical bijection + Kraus level mixed caveat + closest-unitary diamond-norm corollary, `research/oq_oqs2_kraus_l0_bijection_v0`) | §5.3 |
| **OQ-MBQ1** (4-stage chain 5th class) | OPEN (本論 spawn-off) | §7.3, Q-series future |
| **σ\* = √(2 ln 2) gauge formal closure** | candidate (Q3 forward) | §6.2, Q3 |
| **Born rule derivation 完全形** | partial closure (本論 §6 bridge), full Q3 | §6.2, Q3 |
| **Topological order as 5th algebraic class** | candidate | §7.2, Q1 §7 next candidate |
| **OQ-OQS3** (decoherence generates c_s² = 1/2) | OPEN | §6 4-stage chain context |

### 8.4 辞書 residence map

| 本論 piece | residence | 状態 (Q2) |
|---|---|---|
| §2 4-stage chain S15 residence map | `c_theorems_master.md` row S15 + 各 4 stage entries §S15 接続 (既存) | 既 + 本論 NEW 4-stage layered annex 想定 |
| §3 KMS as L0 A0c | `q_quantum_statistical_mechanics.md §2.5` (既) + 本 §3 proposal_v1 expansion | 既 attack route + 本論 proposal_v1 |
| §4 FDT crown jewel | `q_quantum_statistical_mechanics.md §5` (既) + 本 §4.2 観測-擾乱双対性 expansion | 既 + 本論 Arrow 2 algebraic isomorphism statement |
| §5 dynamical T-AAS | `q_open_quantum_systems.md §5` (既) + 本 §5.2 Q1 4-class dynamical lift | 既 + 本論 NEW dynamical lift table |
| §6 4-stage ln 2 chain | `q_open_quantum_systems §3.3 + q_quantum_statistical_mechanics §5.4 + q_quantum_thermodynamics §5` (既) + 本 §6.1 chain unification | 既 separately + 本論 NEW unified chain statement |
| §7 quasiparticle Arrow 1⁻¹ | `q_many_body_quantum.md §5` (既) + 本 §7.1 Arrow 1⁻¹ residence | 既 + 本論 NEW Arrow 1⁻¹ residence statement |

**post-v0.2 backward (Q-series cumulative, Q1 + Q2 合算 計 10 件)**: Q1 由来 7 件 (`c_theorems_master.md` 量子-only S15 enumeration / `c_arrow_framework.md §4.2.2` 量子 Arrow 可換性 / `c_arrow_bridge_constants.md §12` 量子 instance / `c_filtration_obstruction.md` 4-class quantum lift / `meta/triangulation_methodology.md §11` 量子 4-vertex + §12 N1↔Q1 parallel / `meta/new_domain_protocol.md §9` 量子 specialization) + Q2 追加 4 件 (`c_theorems_master.md` 4-stage chain layered residence annex / `q_quantum_statistical_mechanics.md §2.5` KMS-L0 A0c proposal_v1 expansion / `c_arrow_framework.md §4.x` Arrow 2 algebraic equivalence (FDT crown jewel) / `c_recursive_floor_principle.md` or `c_arrow_bridge_constants.md` 4-stage ln 2 chain unified annex)。

**帰結**: Q2 は dictionary に対して **量子 statistical/thermodynamic extension** として位置付けられ、4-stage chain の S15 layered residence は L1 量子 4 entries の framework integration を formal 化。Q3 (Born-Gleason §4 dual closure) 起草後、framework header (Q1) → extension (Q2) → closure (Q3) の **3 層 link が完成** (N1-N5 系列と並行)。

---

## 変更履歴

- **v0.3 (2026-04-28)**: OQ-OQS2 closure。§5.3 を candidate (future work) から **定理 5.1 (Lindblad-Kraus L0 error decomposition canonical bijection)** に lift、generator level canonical bijection ($\mathcal{L}_H \leftrightarrow$ error_arithmetic / $\mathcal{D} \leftrightarrow$ error_projection / $\bar n_k(\beta) \leftrightarrow$ error_noise) + Kraus level mixed caveat ($K_0$ bundles unitary phase + anticommutator damping) + closest-unitary diamond-norm corollary ($\|\Phi_{dt} - U_*\|_\diamond = \|\mathcal{D}\|dt$) を完全 formal 化。§8.3 OQ 表 OPEN → ESTABLISHED 整合修正。Numerical verification: pure dephasing + amplitude damping 2 instance で V1/V2/V3 全 PASS、Kraus reconstruction = exp($\mathcal{L}t$) to ~1e-16 (`research/oq_oqs2_kraus_l0_bijection_v0`)。q_open_quantum_systems.md §4.3 + §9 dictionary entry も同期更新。Honest dual reporting: 元 attack route (Kraus operator partition) 字義通りは V3 で **rejected**、generator level + closest-unitary corollary で **recovered**。spawned 3 successor OQ (OQS2-NonMarkovian / OQS2-DiamondNorm-Proper / OQS2-MultiJump)。

- **v0.2 (2026-04-27)**: compact 版。v0.1 (531 行) から冗長削減 — Abstract M1-M6 各長文段落圧縮、§1 4 subsection (Q1 forward / N3 parallel / 範囲 / 用語) を 2 subsection に統合 (1.1 で Q1 forward+N3 parallel、1.2 で 範囲+用語)、§2.2/§2.3/§2.4 の 3 subsection (residence map / cumulative / Arrow differentiation) を 2 subsection に圧縮 (Arrow differentiation を §2.2 末尾と §2.3 末尾に統合)、§3.1-§3.5 の 5 subsection を 4 subsection に統合 (§3.3 L0 A0c 合致 + §3.4 Status を §3.3 に統合)、§4.1-§4.5 の 5 subsection を 4 subsection に統合 (§4.2 KMS→FDT 派生 + §4.3 観測-擾乱双対性 を §4.2 に統合)、§5.1-§5.4 を 3 subsection に統合 (§5.3 OQ-OQS1 + §5.4 Lindblad OQ-OQS2 を §5.3 に統合)、§6.1-§6.5 を 3 subsection に統合 (§6.1 statement + §6.2 chain を §6.1 に統合、§6.3 closure + §6.4 Q3 bridge を §6.2 に統合、§6.5 OQ-QSM3 は §6.3 に維持)、§7.1-§7.5 を 3 subsection に統合 (§7.3 anyon + §7.4 BCS を §7.2 に統合)、§8.4 residence map 説明圧縮 + post-v0.2 backward 統計を 1 段落に。骨格・主張・instance 数値・status 表記は全保持。
- **v0.1 (2026-04-27)**: initial Q-only draft. Q1 §3.2/§4.2/§5/§8.2 forward expansion。4-stage Open QS chain (open_QS → QSM → QTD → many-body) で観測理論を量子 statistical mechanics 言語で再展開。N3 Path 2 数論的普遍性 と parallel structure。KMS-FDT-Landauer arc + dynamical T-AAS + 4-stage ln 2 chain + quasiparticle Arrow 1⁻¹ の 4 主題で 6 主結果。Q3 (Born-Gleason σ\* = √(2 ln 2)) への bridge を §6.4 で予告。

---

## 参考文献 (内部)

**Q1 (前身 framework header)**: `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, 量子-only restatement)

**N3 (parallel extension paper)**: `papers/publication/nt/N3_path2_dirichlet_universality_ja.md` (v0.4, Path 2 数論的普遍性)

**Paper D 系列 (前身)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain §6 量子部分)

**本論で展開される結果の出典**: `q_open_quantum_systems.md` §1-§9 (§2 stage S1 + §5 pointer basis Einselection + §6 ln 2 chain S1) / `q_quantum_statistical_mechanics.md` §1-§10 (§2 stage S2 + §3 KMS + §4 FDT + §6 ln 2 chain S2) / `q_quantum_thermodynamics.md` §1-§7 (§2 stage S3 + §6 Landauer ln 2 chain S3) / `q_many_body_quantum.md` §1-§9 (§2 stage S4 + §7 quasiparticle Arrow 1⁻¹) / `q_quantum_observation.md` §6 Born + §7 c_s² + §8 可換極限 (§6 ln 2 chain S0 + §4.2 観測-擾乱双対性 reference)

**OQ research files (forward)**: `q_quantum_statistical_mechanics §10` OQ-QSM1 (KMS from L0 A0c) / OQ-QSM2 (algebraic FDT) / OQ-QSM3 (ln 2 beyond qubit) / OQ-QSM4 (2D window) / OQ-QSM5 (E variable) / `q_open_quantum_systems §9` OQ-OQS1 (pointer basis dynamical A3) / OQ-OQS2 (Kraus error decomposition) / OQ-OQS3 (decoherence generates c_s²) / 本論 spawn OQ-MBQ1 (4-stage chain 5th class candidate)

**L0 / L1 / meta 依存**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4-§5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_observation_optimal_gauge, c_recursive_floor_principle}.md` / `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum}.md` (本論主体, 5 entries) / `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**後続論文**: Q3 (Born-Gleason + dim=2 closure + σ\* = √(2 ln 2) gauge) — 起草予定
