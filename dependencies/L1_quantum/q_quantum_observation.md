---
axis: [A, B]
position: L1_fiber_quantum_theory
static_dynamic: both
connected_to:
  - A.harmonic_analysis
  - A.algebra_analysis
  - B.L1_base
  - B.quantum_mechanics
  - B.physics_layer
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-08
---

# 量子観測構造: 非可換 ι_L と射影値測度

**Level**: L1 (pure mathematics, domain-independent)
**Dependencies**: c_phase_complex.md (ι_L, ℂ* ≅ ℝ_{>0} × S¹, Pontryagin 双対), c_spectral.md (K(τ), 振幅/位相分解)
**Downstream**: L2/eeg (将来: 非可換スペクトル構造), L2/connectome (将来: テンソル積構造), L3/correspondence_table

---

## §1 動機：可換の限界と非可換への必然的拡張

### c_phase_complex.md の到達点

c_phase_complex.md は ι_L: ℤ/Lℤ → S¹ ⊂ ℂ* を構成し、**可換群**の構造を S¹ = U(1) に忠実に埋め込んだ。c_spectral.md はこれを K(τ) と F(hkl) に拡張し、可換な観測量の理論を完成させた。

しかし、この枠組みには構造的な限界がある：

1. **観測量の可換性**: K(τ₁) と K(τ₂) は常に可換（実数値だから）。異なるスケールの観測が互いに干渉しない。
2. **状態の古典性**: 観測者は点 x_j の完全な座標を知っている。「座標と運動量を同時に知れない」という制約が存在しない。
3. **相関の分解可能性**: T7 の交差項 E[cross] = 0 は、クラスターとランダム成分が **独立** であることを仮定している。

物質の最小単位である量子系では、これらすべてが破れる。本項は c_phase_complex.md の構造を **非可換に持ち上げる** ことで、可換理論と量子理論の正確な対応を確立する。

### 拡張の原理

| 可換 (phase_complex) | 非可換 (本項) |
|---|---|
| S¹ = U(1) | U(H) (ユニタリ群) |
| ι_L: ℤ/Lℤ → S¹ | π: G → U(H) (ユニタリ表現) |
| 指標 χ: G → S¹ | 既約表現 π_λ: G → U(H_λ) |
| Pontryagin 双対 | Tannaka-Krein 双対 |
| K(τ) ∈ ℝ | Tr(ρ · e^{iAτ}) ∈ ℂ |
| c_s² = 1/2 (偶奇対称) | Tr(ρ²) = 1/2 (最大混合 qubit) |

右列のすべての構造は、左列の **正確な持ち上げ** である。可換極限（[A, B] = 0）で左列に帰着する。

---

## §2 Hilbert 空間と作用素代数

### 定義

**Hilbert 空間** H は完備な内積空間 (H, ⟨·,·⟩) である。ΣΦ の文脈で関連する実現：

| 実現 | H | 内積 | ΣΦ との対応 |
|---|---|---|---|
| 有限次元 | ℂ^N | ⟨u,v⟩ = Σ ū_j v_j | DFT 行列の列空間 |
| L² 空間 | L²(S¹) | ⟨f,g⟩ = ∫_{S¹} f̄g dθ | K(τ) の連続極限 |
| Fock 空間 | ⊕_{n=0}^∞ H^{⊗n} | 対称/反対称テンソル積 | 多粒子系 |

### 作用素と交換関係

H 上の有界作用素全体 B(H) は、乗法に関して **非可換環** をなす。自己共役作用素 A = A† は観測量に対応する。

**核心**: 二つの自己共役作用素 A, B に対し、交換子

    [A, B] := AB - BA

が一般にゼロでない。これが可換理論との根本的な違いであり、量子力学の全構造はここから生じる。

### ℂ の必然性（量子版）

c_phase_complex.md §4 で「ℂ は加法と乗法の共通受け皿として最小」と示した。量子版ではさらに強い必然性がある：

**命題 (量子的 ℂ 必然性)**:
c_phase_complex.md §4 で示されたように、加法側準同型 ι_L と乗法側指標 χ の共通受け皿として ℂ は最小の位相体であった。量子版では、ι_L, χ に加えてユニタリ発展 e^{-iAt}（§4）の位相構造も同じ器で扱う必要がある。ℝ 上ではユニタリ固有値 e^{iθ} を表現できない（c_phase_complex.md §7 と同じ障害）。

すなわち、**ℂ は ι_L（数論的位相）、χ（乗法的位相）、ユニタリ発展（量子的位相）の統一的受け皿** として量子力学においても必然的に現れる。根拠は c_phase_complex.md と共通であり、量子力学に固有の追加的理由は不要である。

---

## §3 スペクトル定理：量子的 Fourier 分解

### 有限次元版

自己共役作用素 A ∈ B(ℂ^N) に対し：

    A = Σ_{j=1}^{N} λ_j |e_j⟩⟨e_j|

ここで {λ_j} は実固有値、{|e_j⟩} は正規直交固有基底。

### c_spectral.md §3 との対応

c_spectral.md の振幅/位相分解 H(k) = |H(k)|·e^{iφ(k)} は、ℂ* ≅ ℝ_{>0} × S¹ の分解であった。スペクトル定理はこれの作用素版である：

| c_spectral.md | スペクトル定理 |
|---|---|
| Fourier 係数 H(k) ∈ ℂ | 作用素 A ∈ B(H) |
| 振幅 \|H(k)\| | 固有値 λ_j ∈ ℝ |
| 位相 e^{iφ(k)} | 射影 \|e_j⟩⟨e_j\| |
| 分解 H = \|H\|·e^{iφ} | 分解 A = Σ λ_j P_j |

**重要な差異**: c_spectral.md では振幅と位相が **独立** であった（ℂ* の直積構造）。スペクトル定理では固有値 λ_j と固有射影 P_j は **同時に** 決定される — 一方を変えると他方も変わる。この「独立性の喪失」が非可換性の帰結である。

### 一般版（射影値測度）

無限次元の自己共役作用素 A に対し、スペクトル定理は：

    A = ∫_{σ(A)} λ dE(λ)

ここで E: Borel(ℝ) → Proj(H) は **射影値測度** (PVM) であり、任意の Borel 集合 Δ ⊂ ℝ に対して E(Δ) は射影作用素。

これは c_phase_complex.md §5 の Pontryagin 双対の作用素版である：
- Pontryagin: G ≅ Ĝ（指標で群を再構成）
- スペクトル定理: A を PVM E で再構成

---

## §4 ユニタリ発展：連続的 ι_L

### Stone の定理

c_phase_complex.md §2 で ι_L: ℤ/Lℤ → S¹ を「加法を乗法に変換する準同型」として定義した。これの連続版かつ非可換版が **ユニタリ発展**：

    U(t) = e^{-iAt}    (t ∈ ℝ)

ここで A は自己共役作用素（ハミルトニアン、または任意の生成子）。

**Stone の定理**: ℝ 上の強連続ユニタリ群 {U(t)}_{t∈ℝ} と自己共役作用素 A の間に一対一対応がある。

### ι_L との正確な対応

| c_phase_complex.md §2 | Stone の定理 |
|---|---|
| 離散群 ℤ/Lℤ | 連続群 ℝ |
| 目標 S¹ = U(1) | 目標 U(H) |
| ι_L(n) = e^{2πin/L} | U(t) = e^{-iAt} |
| 核 ker(ι_L) = Lℤ | 周期条件: U(T) = I ⟺ σ(A) ⊂ (2π/T)ℤ |
| 忠実性: ι_L 単射 | 忠実性: σ(A) が (2π/T)ℤ に閉じ込められない |

**帰着**: H = ℂ（1次元 Hilbert 空間）のとき、A = 2π/L は実数スカラー、U(n) = e^{-i(2π/L)n} = ι_L(n) に一致する。ι_L は Stone の定理の **1次元離散特殊化** である。

### τ-正規化の量子版

c_phase_complex.md §6 で τ(n) = (n mod L)/L と定義した。量子版では：

    τ_Q(t) := (t mod T) / T    (T = 2π/ΔE, ΔE = エネルギー間隔)

Unfolding（c_spectral.md §5）もそのまま拡張される：

    x_j^{(Q)} := (E_j - E_min) / ΔE    (E_j は固有エネルギー)

これは c_spectral.md の固有値 unfolding と形式的に同一であり、量子系のエネルギー固有値を正規化座標に写す操作である。

---

## §5 テンソル積：合成系とエンタングルメント

### 定義

二つの系 H_1, H_2 の合成系は **テンソル積** H_1 ⊗ H_2 で記述される。

    dim(H_1 ⊗ H_2) = dim(H_1) · dim(H_2)

### 可換理論に存在しない構造

c_phase_complex.md の ι_L は加法群を乗法群に写した。テンソル積は **乗法的結合** の非可換版であるが、決定的に新しい性質を持つ：

**エンタングルメント**: 合成状態 |ψ⟩ ∈ H_1 ⊗ H_2 が

    |ψ⟩ ≠ |φ₁⟩ ⊗ |φ₂⟩    (任意の |φ₁⟩ ∈ H_1, |φ₂⟩ ∈ H_2 に対して)

のとき、|ψ⟩ はエンタングルした状態である。

**古典理論との対比**:
- 可換理論（c_spectral.md §4）: T7 の交差項 E[cross] = 0 はクラスターとランダム成分の **独立性** を仮定
- 量子理論: エンタングルメントにより、部分系は一般に独立ではない。交差項が消えない。

### Schmidt 分解

任意の |ψ⟩ ∈ H_1 ⊗ H_2 は：

    |ψ⟩ = Σ_{k=1}^{r} √(p_k) |a_k⟩ ⊗ |b_k⟩

ここで p_k > 0, Σp_k = 1, r = Schmidt rank。

c_spectral.md §3 の SVD（H = UΣV†）は Schmidt 分解の行列版であり、特異値 σ_k が √(p_k) に、左右特異ベクトルが |a_k⟩, |b_k⟩ に対応する。rank-1 支配比 ρ₁ = σ₁²/Σσ_k² は最大 Schmidt 係数 p_1 に一致する。

| c_spectral.md §3 | Schmidt 分解 |
|---|---|
| 行列 H | 状態 \|ψ⟩ |
| SVD: H = UΣV† | Schmidt: \|ψ⟩ = Σ√p_k\|a_k⟩⊗\|b_k⟩ |
| 特異値 σ_k | Schmidt 係数 √p_k |
| rank-1 支配比 ρ₁ | 最大エンタングルメント確率 p_1 |
| ρ₁ ≈ 1: 単一モード | p_1 ≈ 1: ほぼ積状態（古典的） |
| ρ₁ ≈ 1/r: 均等分布 | p_k = 1/r: 最大エンタングルメント |

---

## §6 Born 則と一般化測定

### 射影測定 (PVM)

状態 ρ（密度作用素）に対し、観測量 A = Σ λ_j P_j の測定結果が λ_j となる確率は：

    Prob(λ_j) = Tr(ρ · P_j)

測定後の状態は P_j ρ P_j / Tr(ρ P_j) に変化する（射影公準）。

### 一般化測定 (POVM) と Busch-Gleason 定理

射影測定は「無限精度の測定装置」を暗黙に仮定する。L0 の有限観測者にとって、より自然な測定記述は **Effects** (POVM) である：

    Effect E: 0 ≤ E ≤ I を満たす正作用素

射影 P_j は E² = E を満たす特殊な effect であり、一般の effect はこの条件を満たさない（fuzzy measurement）。

**Busch-Gleason 定理** (Busch 2003, PRL 91, 120403):
Effects 全体 E(H) 上の一般化確率測度 v: E(H) → [0,1] が
(P1) 0 ≤ v(E) ≤ 1, (P2) v(I) = 1, (P3) 加法性（E₁+E₂+...≤I ⇒ v(Σ E_k) = Σ v(E_k)）
を満たすならば、密度作用素 ρ が存在して：

    v(E) = Tr(ρ · E)    (全ての E ∈ E(H) に対して)

### dim=2 問題の解消

元の Gleason (1957) は dim(H)≥3 を要求した。dim=2 では射影上の dispersion-free valuation（各 P に 0 か 1 のみを割り当てる）が存在し、Tr(ρP) 形に一意化されない。

Busch の決定的な発見：**これらの dispersion-free valuation は effects に拡張できない**。Bloch 球上の幾何的議論により、射影上で well-defined な非量子的 valuation は effects の連続的構造と矛盾することが示される。

結果として、**effects 上の確率測度は全ての dim で Tr(ρE) に一意化される。dim=2 の例外は消滅する。**

### L0 との整合

この結果は L0 の有限性公理と自然に整合する：

- **有限観測者** → 測定装置は有限精度 → effects (POVM) が自然な記述
- **無限精度の理想化** → 射影測定 (PVM) → dim=2 で Gleason 破綻
- L0 の有限性が **POVM を要求し**、POVM が **全 dim で Born 則を保証する**

つまり dim=2 の問題は「無限精度を仮定したから生じた人工物」であり、有限観測者には発生しない。

### Born rule 3 段 derivation chain (Paper Q3 §3, 2026-04-27)

Paper Q3 (`papers/publication/quantum/Q3_born_gleason_ja.md` v0.2) は本 §6 の Busch-Gleason を量子側 framework root closure として位置付ける。Born rule は postulate でなく **L0 axiom A0 (有限観測) からの 3 段 derivation theorem**:

$$\text{A0 (finite obs)} \xrightarrow{\text{(i)}} \text{POVM/effects (natural framework)} \xrightarrow{\text{(ii) Busch-Gleason}} \text{Tr}(\rho E) \text{ Born form (theorem)}$$

**(i) A0 → POVM/effects**: A0 finite observation → 有限精度測定装置 → fuzzy measurement → POVM が natural framework / A0a finite cardinality → $\dim \mathcal{H} < \infty$ truncation, finite POVM rank $\leq \dim \mathcal{H}^2$ / A0b partial access → ancilla-coupled measurement = system-bath coupling + projection on ancilla = effective POVM (Naimark dilation theorem)。L0 axiomatics と POVM/Effects framework が **mutually consistent**。

**(ii) Effects + (P1)-(P3) → Busch-Gleason → Tr(ρE)**: 全 dim で Born form 一意化、dim=2 Gleason 例外解消。

### Born rule status: postulate → theorem

| 期間 | Status | 残された問題 |
|---|---|---|
| **Pre-Busch** (1957-2003) | postulate | dim=2 で Gleason の dispersion-free 例外、derivation incomplete |
| **Post-Busch** (2003-) | theorem (effects framework + (P1)-(P3) → Tr(ρE) uniqueness) | OQ-Born-1: representation-independent (C\*-algebra 直接) Born derivation OPEN |

**Paper Q3 §5 §4 dual quantum root closure 主張**: c_phase_complex.md §4 commutative §4 dual の量子 non-commutative lift (Stone group + unitary representation) は本 §6 Busch-Gleason completeness で **operational 定式化 closure** + ρ_max = I/2 form (Born form, 全 dim Busch) と value (ℤ/2ℤ symmetry) の **2 source 合流** + σ\* = √(2 ln 2) gauge atlas residence (`transformation_atlas/sheet_A_amplitude/sigma_star.md`) の 3 component で formal closure (Q3 §5)。

**Connection to 4-stage ln 2 chain** (`c_arrow_bridge_constants.md §12.2`): 本 §7 の qubit c_s² = 1/2 (S0) → §3.3 S(ρ_max) = log 2 (S1) → q_quantum_statistical_mechanics §5.4 FDT parity (S2) → q_quantum_thermodynamics §5 Landauer kT ln 2 (S3) → σ\* = √(2 ln 2) Gaussian gauge (S4) の **5-stage ln 2 chain** で量子観測の核心定数 ln 2 が 5 instance independent verify。

**OQ-Born-1 spawn-off** (Paper Q3 §3 spawn): Busch-Gleason は Hilbert space + density operator framework に依存。L0 axioms から direct に C\*-algebra 上の "Born form" を derive する representation-independent route 存在問題。OPEN、Q-series future 候補 (Q2 §3.4 OQ-QSM1 と類縁問題、L0 → operator algebra embedding)。

### 文献

- Gleason, A. M. (1957). Measures on the Closed Subspaces of a Hilbert Space. J. Math. Mech. 6, 885-893.
- Busch, P. (2003). Quantum States and Generalized Observables: A Simple Proof of Gleason's Theorem. PRL 91, 120403. arXiv: quant-ph/9909073.
- Caves, C. M. et al. (2004). Gleason-Type Derivations of the Quantum Probability Rule for Generalized Measurements. Found. Phys. 34, 193. arXiv: quant-ph/0306179.
- Paper Q3 (`papers/publication/quantum/Q3_born_gleason_ja.md` v0.2, 2026-04-27): Q-series final closure paper for §4 dual quantum root

### K(τ) の量子版

c_spectral.md §1 の K(τ) = (1/N)|Σ e^{2πiτx_j}|² を量子系で書き直す。

古典的 K(τ) は点配置 {x_j} の位相コヒーレンスを測った。量子版では、「点」は固有値 {E_j} に、「配置の重み」は密度作用素 ρ の対角成分 ⟨E_j|ρ|E_j⟩ に置き換わる：

    K_Q(τ) := |Tr(ρ · e^{iAτ})|²

展開すると：

    Tr(ρ · e^{iAτ}) = Σ_j ⟨E_j|ρ|E_j⟩ · e^{iE_jτ}

ρ が純粋状態 |ψ⟩⟨ψ| のとき ⟨E_j|ρ|E_j⟩ = |⟨E_j|ψ⟩|² であり、これは固有状態への射影確率（Born 則）である。

**古典極限**: ρ が A の固有基底で対角（ρ = Σ p_j |E_j⟩⟨E_j|）のとき、K_Q(τ) は古典的 K(τ) に帰着する。K_Q(τ) の展開式は A の固有基底での対角成分 ⟨E_j|ρ|E_j⟩ のみを含むため、K_Q 自体は量子コヒーレンス（非対角項）に直接感度を持たない。コヒーレンスに感度を持つ観測量（例: A と非可換な B を含む二時刻相関 Tr(ρ · e^{iAτ} B e^{-iAτ})）は別途定義が必要であり、L2 ドメインがそれを要求したときに拡張する。

---

## §7 c_s² = 1/2 の量子的意味

### qubit の最大混合状態と偶パリティ射影

最も単純な非自明な Hilbert 空間 H = ℂ² (qubit) において、最大混合状態は：

    ρ_max = (1/2) I₂ = (1/2)(|0⟩⟨0| + |1⟩⟨1|)

偶パリティ射影 Π_even = |0⟩⟨0| に対する Born 期待値は：

    c_s² = Tr(ρ_max · Π_even) = Tr((1/2)I₂ · |0⟩⟨0|) = 1/2

*注*: qubit では Tr(ρ_max²) = 1/2（purity）が数値的に一致するが、c_s² との同定に使うのは purity ではなく **Born 期待値** Tr(ρ · Π_even) である。purity と Born 期待値が同じ値を取るのは qubit (dim=2) の偶然であり、一般次元では異なる。

### c_phase_complex.md §5 との一致

c_phase_complex.md §5 で c_s² = E[cos²(πh·t)] = 1/2 を導出した。その根拠は「整数 h の偶奇が等確率」であった。

qubit の言語では：
- |0⟩ = 偶数（cos²(πh·t) = 1）
- |1⟩ = 奇数（cos²(πh·t) = 0）
- 等確率 = 最大混合状態 ρ_max = (1/2)(|0⟩⟨0| + |1⟩⟨1|)
- c_s² = Tr(ρ_max · Π_even) = 1/2

**定理 (c_s² の量子的同値)**:
c_s² = 1/2 は以下の3つの等価な言明である：

1. **数論的**: 整数の偶奇は等確率（c_phase_complex.md §5）
2. **調和解析的**: cos²(πh·t) の h ∈ ℤ にわたる平均は 1/2
3. **量子的**: 偶パリティ射影 Π_even = |0⟩⟨0| に対する最大混合状態の Born 期待値 Tr(ρ_max · Π_even)

3つの言明は同じ数学的事実（ℤ/2ℤ の一様測度）を異なる言語で述べている。量子的定式化が特に有用になるのは、パリティ以外の対称性（連続回転、並進など）にも同じ枠組みが適用できるときである。

**スピンへの接続**: この ℤ/2ℤ は spin-1/2 の SU(2) 中心 {I, -I} として物理的に具現化する。c_s² = 1/2 のスピン的意味、ℤ/2ℤ → SU(2) 昇格、および α² 補正（微細構造）の詳細は `q_fine_structure.md` §2, §4 を参照。

### Busch-Gleason による保証

§6 の Busch-Gleason 定理により、qubit (dim=2) においても effects 上の確率測度は Tr(ρE) 形に一意化される。したがって c_s² = Tr(ρ_max · Π_even) = 1/2 は：

- **形**: effects 上の確率測度は Tr(ρ·) しかない（Busch, 全 dim）
- **値**: ρ = ρ_max = I/2 は偶奇対称性から決定（L0 + L1-base）

Born 則の形と値が **ともに定理的に導出される**。c_s² = 1/2 は L0（有限性 → POVM → Busch）と L1-base（偶奇 → ρ_max）の合流点であり、この合流が数値的に確認可能であることが ΣΦ の量子-数論接続の核心である。

---

## §8 可換極限：c_phase_complex.md への帰着

### 帰着条件

本項の全構造は、以下の条件下で c_phase_complex.md / c_spectral.md に帰着する：

    [A, B] = 0    (全ての観測量が可換)

可換な自己共役作用素は **同時対角化** 可能であり、固有基底が共有される。このとき：

| 量子構造 | 可換極限 | 帰着先 |
|---|---|---|
| H = ℂ^L, A = diag(0, 1, ..., L-1) | 固有値 = ℤ/Lℤ の元 | c_phase_complex.md §2 |
| e^{-iAt} = diag(1, e^{-it}, ..., e^{-i(L-1)t}) | 各成分 = ι_L(n) | c_phase_complex.md §2 |
| Tr(ρ · e^{iAτ}) = Σ p_j e^{ijτ} | = K(τ)^{1/2} (p_j = 1/N) | c_spectral.md §1 |
| Schmidt rank r = 1 | 積状態 = 古典的独立 | c_spectral.md §4 (T7) |
| P_j = \|j⟩⟨j\| (rank-1 射影) | = δ 関数 (点配置) | c_spectral.md §2 (F(hkl)) |

### 非可換構造が必要になる条件

L2 ドメインが以下のいずれかを示すとき、可換理論では不十分であり本項の構造が必要となる：

1. **[A, B] ≠ 0**: 二つの観測量が同時対角化できない（例: 位置と運動量）
2. **エンタングルメント**: SVD の rank-1 支配比 ρ₁ が系統的に 1 から乖離する
3. **射影値測度**: 観測が状態を不可逆に変化させる（測定の反作用）
4. **超位相因子**: 位相 φ(k) が古典的に説明できない干渉パターンを示す

**現状** (2026-04-08): L2 の crystal, FX, connectome, EEG いずれも、現在の解析精度では可換理論（c_phase_complex.md + spectral.md）で記述可能である。本項は、これらのドメインがより精密な観測で非可換構造を必要とする場合に備えた **数学的準備** として機能する。

---

## §9 後続参照マップ

### L1 内部参照

| 項目 | 本項の依存節 | 依存内容 |
|---|---|---|
| `c_phase_complex.md` §2 | §4 | ι_L = Stone の定理の 1次元離散特殊化 |
| `c_phase_complex.md` §4 | §2 | ℂ の必然性 = ユニタリ固有値の受け皿 |
| `c_phase_complex.md` §5 | §7 | c_s² = 1/2 = qubit 最大混合状態の純度 |
| `c_spectral.md` §1 | §6 | K(τ) = K_Q(τ) の可換極限 |
| `c_spectral.md` §3 | §5 | SVD = Schmidt 分解の行列版 |
| `c_spectral.md` §4 | §5 | T7 の E[cross] = 0 ⟺ エンタングルメントなし |
| `q_open_quantum_systems.md` §2 | §5 | 部分トレース = テンソル積の窓演算子 |
| `q_open_quantum_systems.md` §3.3 | §7 | log 2 双子: S(ρ_max) の open QS 経由回収 |
| `q_open_quantum_systems.md` §5.3 | §8 | decoherence が可換極限を動的に実現するメカニズム |

### S12/S15 接続 (2026-04-11)

| S-ID | 本ファイルとの関係 | 層 |
|---|---|---|
| S12 | U(t) = e^{-iAt} は S12 加法 Scan member #5。Stone 群 = phase_complex §2 ι_L の連続非可換一般化。scanner = t (時間), kernel = e^{-it}, 加法軸 | Scan (加法) |
| S15 | 本ファイルの observable は 3 分類全てに分布: **Scan** = U(t), K_Q(τ); **Structural** = dim(eigenspace), spectral multiplicity; **Information** = S(ρ) = -Tr(ρ log ρ) (§7, von Neumann entropy) | 全 3 層 |
| Arrow 1 | U(t) の spectral decomposition A = Σ λ_j P_j → 固有値の多重度 = Structural | Scan → Structural |
| Arrow 2 | §7 の S(ρ_max) = log 2 は S13 の instance: Z → F → S chain の量子版。c_s² = 1/2 (Born) → log 2 (Shannon/von Neumann) | Scan → Information |

参照: research/bidirectional_duality_v0.md §5 (S15 Observable Trichotomy), theorems_master S12/S15。

### L2 ドメイン参照（将来的）

| ドメイン | 非可換構造が必要になりうる場面 | 関連節 |
|---|---|---|
| Crystal | 磁気空間群、スピン軌道結合 | §3 (スペクトル定理) |
| FX | 観測者効果（大口取引が価格を動かす） | §6 (射影公準) |
| Connectome | ニューラルネットワークのテンソル積構造 | §5 (エンタングルメント) |
| EEG | 量子コヒーレンス仮説の検証 | §6, §7 |

### L3 クロスドメイン参照

| 項目 | 依存する節 | 依存内容 |
|---|---|---|
| `correspondence_table.md` | §8 | 可換極限の存在 = 全ドメインが共通の量子→古典帰着を持つ |
| `three_phase_taxonomy.md` | §7 | c_s² = 1/2 の量子的普遍性 |

---

*作成日: 2026-04-08*
*最終更新: 2026-04-11 (S12/S15 接続追加)*
