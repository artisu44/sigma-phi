---
axis: [A, C]
position: L1_arrow_framework
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md           # A0 + A7 (Scanner) + §8 axis-2 framework
  - L0_canon/observation_canon.md            # axiom table
  - L1_mathematical/c_phase_complex.md         # §4 structural root ι_L/χ
  - L1_mathematical/c_theorems_master.md      # S15, S13, S14, S17 rows
  - L1_mathematical/c_arrow_obstruction.md    # T-AAS (Arrow 1 kernel side, §10) + inverse Arrow (§11)
  - L1_mathematical/c_arrow_bridge_constants.md  # canonical constants π / ln 2 / e per Arrow
  - L1_mathematical/c_observation_optimal_gauge.md  # Arrow 1 / 2 balance theorem
  - papers/Paper_D_Observation_Theory_ja.md   # §4 (3 Arrow), §4.1.1 selector, §4.4 commutativity
arrow_status:
  upstream: done
  downstream: done
updated: 2026-04-23
runtime_summary:
  what: S15 3 層 (Scan / Structural / Information) を結ぶ 3 Arrow の formal framework — 定義 / 可換性定理 / Fi/I commutation lift
  when: 「3 Arrow が何を意味するか」「Arrow 可換性が成立する条件」「Fi/I commutation で Arrow がどう再読みされるか」
  provides: [three_arrow_definitions, arrow1_selector, commutativity_theorem, fi_i_commutation_form, arrow_traversal_table]
  consumes: [S15 Trichotomy (c_theorems_master S15), L0 v2 axis-2 framework (finite_observation §8), §4 dual root (c_phase_complex §4)]
  axis: [A, C]
  cost: medium
  status: ESTABLISHED
  one_screen: |
    Arrow 1 (Scan→Structural): input spec を読む。selector 性 — 同 domain で複数 Structural observable 候補が並立しうる
    Arrow 2 (Scan→Information): F = −log G, S = −∂F/∂σ thermodynamic chain
    Arrow 3 (Structural→Information): H_0 = log|D| Hartley counting
    可換性 (定理 4.1): scanner → extreme で Z(β→0) = |{states}|, S(β→0) = log|{states}| = H_0
    Fi/I commutation (定理 4.1a): 可換性は axis-2 Fi/I 操作の Fi-only limit 可換性として再読み
    Arrow 2 のみ axis-2 不動の pure Fi↔Fi / I↔I bridge、Arrow 1/3 は I→Fi 成分を持つ
---

# Arrow Framework — S15 3 層を結ぶ 3 Arrow

**Level**: L1 (横断 framework、S15 Trichotomy の動的構造)
**Role**: S15 の 3 静的層 (Scan / Structural / Information) を結ぶ 3 動的 Arrow を定義し、可換性定理および Fi/I commutation lift を formal に与える。observation-optimal gauge theorem (c_observation_optimal_gauge.md) と 逆 Arrow / generation (c_arrow_obstruction.md §11) はこの framework の上に立つ。

---

## §1 動機

S15 Observable Trichotomy (c_theorems_master.md S15) は辞書内任意 observable を 3 排他クラス (Scan / Structural / Information) に partition する。partition だけでは「3 層がどう **接続** されているか」が language として与えられない。

3 Arrow は層間の canonical 写像 (Scan → Structural, Scan → Information, Structural → Information) として接続を formal 化する。Arrow が definite な writing を持つことで:

- 定数 residence (S13 ln 2 = Arrow 2 上, S17 e = Arrow 3 上, S14 π = Arrow 1 上) が L1 で local に語れる (c_arrow_bridge_constants.md)
- 可換性 (定理 4.1) と Fi/I commutator (定理 4.1a) が定理として state できる
- 逆 Arrow による生成理論 (主張 4.2) と obstruction class taxonomy が formal に書ける (c_arrow_obstruction.md §11)
- domain ごとの観測量を S15 上に position するときに Arrow 経路を明示できる (Paper D §6 三角測量)

---

## §2 3 Arrow の formal 定義

### §2.1 Arrow 1: Scan → Structural (input specification reading)

**定義 (Arrow 1)**: Scan observable

    O(σ; D, f) = Σ_{d ∈ D} f(d) · exp( a(σ) · b(d) )

(L0 A7 Scanner hierarchy 形式) において、Scanner 変数 σ を **forget** し、内部の data 空間 D と weight 関数 f を返す写像

    Arrow 1 : O(σ; D, f) ↦ ( D, f, b )

を Arrow 1 と呼ぶ。Structural observable はこの (D, f, b) に依存する parameter-free integer / 位相的 invariant として抽出される。

| Scan member | D (data space) | encoded Structural observable |
|---|---|---|
| K(τ) | x_j ∈ ℝ (unfolded eigenvalues) | b₁(G) = K − M + 1 (graph Betti) |
| F(h) | r_j ∈ ℝ³/ℤ³ (atomic positions) | n_centering, codim(s) |
| ζ(s) | n ∈ ℤ_{>0} | h_K, f_p(ρ) |
| Z(β) | E_n ∈ ℝ | g(E_n) degeneracy |
| U(t) | spectral support of A | dim(eigenspace) |

**形式化**: Structural は Scan の **input specification**。Arrow 1 は parametric family を input spec に潰す forgetful map。

### §2.2 Arrow 2: Scan → Information (log-exp duality)

**定義 (Arrow 2)**: Scan generating function G(σ) = Σ_d f(d) exp(a(σ)·b(d)) の log-derivative chain

    F(σ) := −log G(σ)              [free energy]
    S(σ) := −∂F/∂σ |_{natural}     [entropy / Information]

を Arrow 2 と呼ぶ。Information observable は S(σ) の specialization (natural σ で評価) として抽出される。

| Scan O(σ) | G(σ) | F(σ) | Information |
|---|---|---|---|
| Z(β) | Σ e^{−βE} | −kT log Z | S(ρ) = −Tr(ρ log ρ) (Legendre) |
| ζ(s) | Σ n^{−s} | −log ζ(s) | Λ(n) via −ζ'/ζ |
| K(τ) | \|Σ e^{2πiτx}\|² | −log K(τ) | rate function (large deviation) |

**形式化**: Information = −∂/∂σ log Scan。log は Scan ↔ Information の bridge operator。S13 半値固定点 (e^{−x} = 1/2 ⟺ x = ln 2) はこの bridge 上の **value-fixed stationary point** (Arrow 2 上の canonical constant、c_arrow_bridge_constants.md §5)。

### §2.3 Arrow 3: Structural → Information (combinatorial counting)

**定義 (Arrow 3)**: Structural observable D (cardinality |D| を持つ) に対し、Hartley entropy

    H_0(D) := log |D|         [Rényi α = 0]

を Arrow 3 と呼ぶ。

| Structural | \|D\| | H_0 = log\|D\| | 意味 |
|---|---|---|---|
| n_centering | n | log n | centering 1 点あたりの情報量 |
| h_K | class number | log h_K | 類群の情報容量 |
| dim V^{I_i} | fixed subspace dim | log dim | ramification 1 段の freedom |

**形式化**: Information = log(Structural)。S17 e-extremum (info density d(n) = (log n)/n max at n = e) はこの Arrow 上の **derivative-fixed stationary point** (Arrow 3 canonical constant、c_arrow_bridge_constants.md §5、ESTABLISHED 2026-04-23)。

---

## §3 Arrow 1 selector property

### §3.1 多値性

Arrow 1 は **単射ではない**。同一 Scan observable から複数の Structural observable 候補 {O₁, O₂, …} が並立しうる。これは Arrow 1 が input spec を返すとき、(D, f, b) tuple の **どの aspect** を Structural observable として抽出するかに自由度があるため。

**Paper E instance** (Paper D §4.1.1, 2026-04-22 main scan 9900 samples):

| Structural observable 候補 | 定義 | Verdict (vs T/e) |
|---|---|---|
| **C2** (b₁ median) | 第 1 Betti 数の midpoint | 抽出不能 (degradation axis 非整合) |
| **C4** (χ median) | Euler 標数の midpoint | split majority 6/9 |
| **B6** (b₀ mode threshold) | topology addition onset | coincide majority 6/9 |

3 observable が異なる verdict を出す: Arrow 1 は **selector**。

### §3.2 3 原則 (Paper D §4.1.1, 2026-04-22)

1. **Alignment 原則**: Structural observable O は domain の degradation / dynamical axis と alignment しているときのみ balance を抽出可能。非 aligned observable は undetermined を返す (判定不能 ≠ balance 不在)。
2. **Observable-specific verdict 原則**: 複数 observable が異なる verdict を出す場合、domain 内部で全 observable の verdict を維持し、canonical selection は domain 固有の arithmetic / dynamical structure に基づいて別途指定する。
3. **判定 form への波及**: observable 選択が meta-theorem (c_observation_optimal_gauge.md) の "両層一致" verdict を変える場合、observable choice を verdict と併記する (Paper E: "C4 primary 下で split")。

### §3.3 Information / Structural 非対称性

Arrow 1 が selector なのに対し、Arrow 2 (log-derivative chain) は **observable-independent**。Information layer の balance 判定 (S13 半値固定点) は observable choice から自由 (log-derivative は scanner 軸固定で一意)。

これは observation-optimal gauge theorem (c_observation_optimal_gauge.md §3) の 2 layer 分離 — Information layer は observable-independent / Structural layer は observable-dependent — の Arrow framework 側根拠。

---

## §4 可換性定理

### §4.1 Statement

**定理 4.1 (3 Arrow 可換性)**: scanner σ → 0 (または ∞) の extreme limit で 3 Arrow は可換図式

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

を満たす。具体的には:

- Z(β → 0) = Σ_n 1 = |{states}| (degeneracy count = Structural)
- S(β → 0) = log |{states}| = H_0 (Hartley = Information)
- 等式: log( Z(β → 0) ) = Structural 数え上げ = Hartley entropy

**条件**: exponential kernel exp(a(σ)·b(d)) が trivial limit a(σ_*) · b(d) → 0 で counting function ( = Σ_d 1 ) に退化するとき成立。

### §4.2 6+1 member での可換条件 check

S12 family の各 member での可換条件成立:

| Scan member | σ | trivial limit a(σ_*) · b(d) → 0 | possible verdict |
|---|---|---|---|
| Z(β) | β | β → 0 ⟹ Z → \|{states}\| | OK |
| K(τ) | τ | τ → 0 ⟹ K → Σ_j 1 = \|data\| | OK |
| U(t) | t | t → 0 ⟹ U → identity (act on \|D\|-dim space) | OK |
| F(h) | h | h → 0 ⟹ F(0) = N_atoms (= \|D\|) | OK |
| ζ(s) | s | s → ∞ ⟹ Σ n^{−s} → 1 (n=1 のみ) — counting でなく **single point** | ※部分的 (s → 0 は解析接続) |
| L(s,χ) | s | s → ∞ ⟹ Σ χ(n) n^{−s} → χ(1) = 1 | ※部分的 |
| φ_τ (Gaussian bridge) | τ | τ → 0 で Gaussian → δ → \|D\| ではない | ※bridge 用、Scan 主成分でない |

**注意**: ζ / L は s → ∞ で 1 点へ退化し counting に成らない。s → 0 は解析接続経由で counting / non-counting 議論が必要 (functional equation 経由で別 limit)。可換性は **物理 partition 系 (Z / K / U / F)** で標準的に成立、**arithmetic Scan (ζ / L)** では条件付き — §4.2.1 で 3 NT instance による条件付き解決を示す。

### §4.2.1 NT 3-instance commutativity resolution (Paper N1 §4.4, 2026-04-26)

§4.2 で arithmetic Scan (ζ / L) が "条件付き" とされた点は、Paper N1 (`papers/publication/nt/N1_observation_theory_nt_ja.md` §4.4)
で **NT 3 instance による完全閉鎖** が与えられた。3 instance は extreme limit と singularity
の両方で commutativity を verify し、arithmetic Scan family の可換性を resolve する。

| Instance | Limit type | 機構 |
|---|---|---|
| **NT Instance 1 (β → 0)** | extreme limit | Z(β→0) = Σ_n 1 = \|states\|, S(β→0) = log\|states\| = H_0。NT 文脈では数体 K の素点 splitting type counting。物理 partition 系 §4.2 行 Z(β) と同型 |
| **NT Instance 2 (s → ∞)** | extreme limit | ζ(s→∞) → 1 (n=1 のみ生き残り), Scan = 1-point measure → Structural = {1} → Info = 0。**trivial commutativity** (全部 0)。Arrow 全部が axis-2 で Fi-only に閉じる退化 case |
| **NT Instance 3 (s = 1 pole)** | singularity (extreme limit でなく) | Class number formula: Res_{s=1} ζ_K(s) = (2^{r₁}·(2π)^{r₂}·h_K·R_K) / (w_K·√\|d_K\|)。Arrow 1 が (h_K, R_K, w_K, d_K, r₁, r₂) Structural skeleton encode、Arrow 2 が −log ζ_K → Λ_K (Dedekind von Mangoldt)、Arrow 3 が log h_K + log R_K − log w_K + (log の他 4 項) を生成。**3 経路同時 finite residue** で 3 Arrow commutativity が pole singularity で realize ⇒ **数論的最強 instance** |

**閉鎖性の主張**: Instance 1 (extreme β → 0) は §4.2 表の Z(β) 行と一致し可換性 OK。
Instance 2 (extreme s → ∞) は trivial limit で全 Arrow が degenerate (1-point measure)、
これも commutativity 形式的に成立。Instance 3 (s = 1 pole) は extreme limit の代わりに
**singularity residue** で 3 Arrow 同時に finite content を持つ — class number formula
そのものが Arrow 1/2/3 の同時可換性 statement の数論的 instantiation。

3 instance により arithmetic Scan の "条件付き" status は **NT 内自閉的に解決済**。
Paper N1 §6.1 で Paper C 三層分解 = S15 同型がさらに「single object F_{g,k}(s) で
3 Arrow simultaneous commutativity」instance として登場し、4th NT-internal verify を
提供する。

**§4.2 表との関係**: 表の ζ / L 行 "※部分的" status は本 §4.2.1 で NT 内 resolved。
Paper N1 §4.4 が canonical reference として使用される。

**Ref**: Paper N1 §4.4 (NT 3 instance), §6.1 (Paper C single-object 3 Arrow simultaneous)。

### §4.2.2 量子 3-instance commutativity (Paper Q1 §4.4, 2026-04-27)

§4.2.1 (NT 3-instance, Paper N1) と parallel に、Paper Q1 (`papers/publication/quantum/Q1_observation_theory_quantum_ja.md` §4.4) は **量子 3 instance による独立完全閉鎖** を提供する。N1 (NT) と Q1 (量子) の **2 dual framework header** が arithmetic vs quantum Scan family の可換性を independently verify。

| Instance | Limit type | 機構 |
|---|---|---|
| **量子 Instance 1 (β → 0, high-T thermal limit)** | extreme limit | $Z(\beta \to 0) = \mathrm{Tr}(I) = \dim \mathcal{H}$, $S = \log \dim \mathcal{H} = H_0$。log Z = Hartley、量子 thermal limit で Structural (dim H) が direct 露呈 |
| **量子 Instance 2 (t → 0, trivial unitary limit)** | extreme limit | $U(t \to 0) \to I$, $K_Q(0) = |\mathrm{Tr}(\rho)|^2 = 1$, Scan = trivial → Structural = (full ρ unaltered) → Info = $S(\rho)$ (input)。identity limit、3 Arrow が ρ の trivial reproduction で可換 |
| **量子 Instance 3 (T → ∞, classical limit)** | classical limit (extreme でなく decoherence) | $\beta H \to 0$ or $\hbar \to 0$: density matrix が A-basis で diagonalize、$Z = \sum_j e^{-\beta E_j} \to$ continuous integral、$S$ → classical entropy。decoherence limit、von Neumann → Shannon で 3 Arrow が classical commutativity に帰着 |

**閉鎖性の主張**: Instance 1 (extreme β → 0) は §4.2 表の Z(β) 行 量子 lift。Instance 2 (extreme t → 0) は U(t) 加法 Scan の trivial unitary limit。Instance 3 (classical limit) は decoherence (`q_open_quantum_systems.md §5.3`) 経由で commutative algebra に動的帰着 → §5 Fi/I commutation form の量子 dynamic instance。

**N1 (NT) との 2-domain parallel**: N1 §4.4 の 3 instance (β→0, s→∞, s=1 pole) と Q1 §4.4 の 3 instance (β→0, t→0, T→∞) はそれぞれ **arithmetic vs quantum** scanner family で 3-instance commutativity を proof-of-concept、framework の **ドメイン非依存可換性** が 2-domain anchor で verify。

**Ref**: Paper Q1 §4.4, papers/publication/quantum/Q1_observation_theory_quantum_ja.md。

### §4.2.3 Arrow 2 algebraic equivalence (FDT crown jewel, Paper Q2 §4, 2026-04-27)

Paper Q2 (`papers/publication/quantum/Q2_open_qs_chain_ja.md` §4) は Arrow 2 (Scan → Information) 上 KMS-FDT chain で Scan (response χ_AB(ω)) と Information (correlation S_AB(ω)) の **algebraic equivalence** を確立する。これは Arrow 2 の **crown jewel** instance。

**FDT statement** (`q_quantum_statistical_mechanics.md §5`):
$$S_{AB}(\omega) = \frac{2\hbar}{1 - e^{-\beta\hbar\omega}} \cdot \mathrm{Im} \chi_{AB}(\omega)$$

**Arrow 2 上 residence**:
- $\chi_{AB}(\omega)$ = Scan layer (response function, scanner ω)
- $S_{AB}(\omega)$ = Information layer (correlation, fluctuation spectrum)
- $\frac{2\hbar}{1 - e^{-\beta\hbar\omega}}$ = Bose factor bridge

両者 algebraic equivalent → Arrow 2 上 (Scan → Information) **algebraic isomorphism** at thermal equilibrium。

**Derivation chain**: KMS condition $C_{AB}(t + i\beta) = C_{BA}(t)$ → Fourier transform → $\tilde{C}_{AB}(\omega) e^{-\beta\omega} = \tilde{C}_{BA}(\omega)$ → correlator decomposition (symmetric S + antisymmetric → response χ) → FDT。$\text{KMS} \to \text{imaginary-time periodicity} \to \text{FDT}$ chain で **FDT は KMS の theorem** (postulate でなく)。

**Crown jewel status — 観測-擾乱双対性**: FDT 物理的 content は thermal equilibrium の spontaneous fluctuation = external probe response (up to Bose factor)。これは `q_quantum_observation.md §6` Born rule + Busch-Gleason 「観測 = 擾乱」原理の **thermal version** ─ closed quantum (Born collapse) と thermal (FDT fluctuation-response) は同一 structural principle (観測-擾乱双対性) の 2 instance。

**qubit FDT parity point**: $\beta\hbar\omega_0 = \log 2$ で Bose factor = 1, $S(\omega_0) = 2\hbar\gamma$, ratio $S/(2\hbar\gamma) = 1 = 2 \cdot c_s^2$ → **c_s² = 1/2 thermal echo**、4-stage ln 2 chain stage S2 (Q2 §6, c_arrow_bridge_constants §12)。

**OQ-QSM2** (representation-independent FDT): KMS は purely algebraic だが FDT (§4.1) は Fourier transform + spectral representation を使う Hilbert space tool、algebraic FDT 存在問題 OPEN。

**Ref**: Paper Q2 §4 / `q_quantum_statistical_mechanics.md §5`。

### §4.3 帰結

可換図式の存在は **ドメイン横断翻訳** を可能にする:
- 同一 S15 residence を持つ observable 同士は Arrow 経路を介して有限ステップで翻訳可能 (Paper D §8.3 方法論的帰結 1)
- 「類似」「偶然一致」の記述を捨て、formal 翻訳に置き換える

**ref**: Paper D §4.4, §8.3。

---

## §5 Fi/I commutation form (定理 4.1a)

### §5.1 axis-2 lift

L0 v2 (finite_observation.md §8) の 2-axis (Fi/I × D/C) lens において、定理 4.1 の可換性は **axis-2 Fi/I 操作の Fi-only limit 可換性** として再読みされる。

各 Arrow は axis-2 traversal 成分を持つ:

| Arrow | axis-2 traversal | 説明 |
|---|---|---|
| **Arrow 1** (Scan → Structural) | I → Fi 片方向 | I 側の "all parametric families" → Fi 側の 1 つの discrete skeleton |
| **Arrow 2** (Scan → Information) | axis-2 不動 (pure axis-1 transformation) | log-derivative は axis-2 を変えない、C 側内部で完結 |
| **Arrow 3** (Structural → Information) | 主に Fi → Fi (counting) | discrete cardinality を log-counting に lift、I-side は Stirling 漸近で限定的に登場 |

**定理 4.1a (Fi/I commutation, 2026-04-23)**: 定理 4.1 の可換性は scanner extreme limit で **3 Arrow の axis-2 traversal 成分が全て Fi-side に閉じる** ことと等価。trivial limit a(σ_*) · b(d) → 0 で:

- Arrow 1 の I → Fi 成分が **trivial** (parametric family が 1 点に潰れて Fi 側 spec のみ残る)
- Arrow 3 の Fi → Fi counting が **definite** (|D| < ∞ で log|D| が well-defined)
- 両者の合成 Arrow 1 → Arrow 3 = Arrow 2 trivial limit (log G = log |D|)

可換性 ⟺ axis-2 で全 Arrow が Fi 内に閉じる ⟺ I-side 寄与が trivial limit で死ぬ。

### §5.2 帰結 (axis-2 perspective)

- Arrow 可換性は **axis-2 default** (extreme limit で I-side が trivial に退化する標準現象)
- 非可換性 (extreme limit を取らない領域) は **axis-2 Fi/I 境界の active 状態** = kernel 発生 source (T-AAS の起源)
- functional-equation 型 enforcement (Paper C ζ(s) = ζ(1−s)) は axis-2 Fi/I 可換性を **extreme limit 外でも強制** する rare 構造 (c_observation_optimal_gauge.md §4 系 4.1c)

**ref**: Paper D §4.4.1, finite_observation.md §8 (L0 v2), c_arrow_obstruction.md §10.0 (2-axis lens), research/oq_l0_refinement_finite_infinite_2axis_v0.md §3, §4.

---

## §6 Cross-references

- **Arrow 1 kernel side (T-AAS)**: c_arrow_obstruction.md §10 — Arrow 1 が非自明 kernel を持つ場合の分解定理 (ker_gauge ⊕ ker_topo)
- **Arrow canonical constants** (π / ln 2 / e): c_arrow_bridge_constants.md §5 — 3 Arrow それぞれに residence する canonical 定数の統一表
- **Observation-optimal gauge theorem**: c_observation_optimal_gauge.md — Arrow 2 上の S13 半値固定点 vs Arrow 1 上の Structural balance の 2 layer 分離 + coincidence 条件
- **Inverse Arrow / generation**: c_arrow_obstruction.md §11 — 各 Arrow の部分逆写像と generation 理論
- **S15 axis-2 projection map**: c_theorems_master.md §"S15 axis-2 projection map" — S15 partition の axis-2 拡張表
- **三角測量**: meta/triangulation_methodology.md — Paper C / B / Ω の S15 residence 三頂点 validation

---

## §7 Status / 履歴

- **ESTABLISHED 2026-04-23**: Paper D v0.7 (本論 §4 全体) + L0 v2 (Paper D §2.3.1, finite_observation.md §8) との同時 residence。3 Arrow framework は S15 と T-AAS の間に位置する **構造的中間 layer** として正式記録。
- 上流: S15 Trichotomy (c_theorems_master.md S15, ESTABLISHED 2026-04-11), L0 A7 Scanner hierarchy (finite_observation.md §7, 2026-04-23), L0 v2 axis-2 framework (finite_observation.md §8, 2026-04-23)
- 下流: c_arrow_bridge_constants.md §5 (canonical constants per Arrow), c_observation_optimal_gauge.md (Arrow 1 vs Arrow 2 balance), c_arrow_obstruction.md §10/§11 (Arrow 1 kernel + 逆 Arrow), Paper D §6 三角測量

---

*作成日: 2026-04-23 (Paper D v0.7 → Prime v0.6 apply 作業)*
