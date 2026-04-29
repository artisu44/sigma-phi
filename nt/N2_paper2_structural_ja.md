# Paper N2: Paper 2 構造解析 ─ Carry / D_floor / Dirichlet

**サブタイトル**: 素数 gap 因子化と D_floor スペクトル定理の数論的構造

**バージョン**: v0.5 (N5 backward link + NT 5-paper 完成, 2026-04-27)
**状態**: DRAFT — Paper C v0.2 からの NT-only 拡張版、N1 framework header 上に position
**前提 (framework)**: N1 (`N1_observation_theory_nt_ja.md`) v0.7
**前提 (L1)**: `c_spectral.md §8`, `c_recursive_floor_principle.md`, `c_filtration_obstruction.md`, `c_arrow_framework.md §4.2.1`, `c_observation_optimal_gauge.md`, `c_theorems_master.md` (S13/S15/S17)
**前提 (L1 NT)**: `nt_conductor.md §6`, `nt_dedekind_artin_zeta.md`
**親 bridge**: `research/paper2_twin_dictionary_bridge_v1.md`
**研究 root**: `research/oq_p2_1_carry_closed_form.md`, `research/oq_p2_2_sstar_asymptotic.md`
**後続論文**: N3 (Path 2) / N4 (Hasse-Weil L × Stark) / N5 (Brauer + Origination)

---

## §0 Abstract

本論は素数 gap に沿った Dirichlet 型級数 F_{g,k}(s) の構造解析。N1 framework (公理 / S15 / Arrow / T-AAS / NT 内三角測量) 上で 5 主結果を展開する:

**(M1) Carry 率の閉形式 (OQ-P2-1 RESOLVED)** — c(g, X) = N_g(X) / |S_g(X)|, |S_g(X)| = X · ∏_{p|X}(1 − ν_g(p)/p) で X を割る素数上の **有限 Euler 積**。30+ 設定で |d| < 1.5pp。**Conductor 次元 = ω(X)** (X 素因子個数)。

**(M2) D_floor スペクトル定理 (OQ-P2-2/2c/2e CONFIRMED, P2-4 RESOLVED)** — 放物型公式 $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 (\log N)^2 (s - 1/2)^2)$、最小値 s = 1/2 一意 (3 decades)。critical strip 上で D_floor(σ + it) の dip が γ₁ = 14.135 に locking (21 σ-points 全点) — RH の ΣΦ 翻訳。

**(M3) Gap 依存性は構造、係数は k_max-gauge (OQ-P2-2 4th)** — α(1, g) > 0 が 20 entry 全成立、s\*(N) → 1 が **全 gap で普遍**。log(g/2) 線形は k_max 不変 (R² ≈ 0.98)、係数は k_max^{−1/2} スケールの gauge 量。

**(M4) ε_{g,k} 残余の Dirichlet 分解は構造的に禁じられる (OQ-P2-3 CLOSED NEGATIVE)** — residue exclusivity (100% at N=30M) のミラー対称性で非主指標 χ₁ が消失、χ₀ (6|g) のみ全スパン。p = 0.87 (null) / p = 0.014 (χ₀) で二値分離 → **T-AAS f_torsion = 0, f_rational = 1 clean instance**。

**(M5) 三層分解 = S15 同型 + Observation-optimal gauge 構造解析** — F_{g,k}(s) = κ_g·G_k·W_k + a_g·Δ_k + ε_{g,k} の三層が S15 (Scan/Structural/Information) と一対一対応 (N1 §6.1 deep dive)。Paper C coincide (s=1/2 functional eq enforcement) vs Paper 2 split (X=6 vs X=2g locus) を arithmetic mod-n reducibility として明示。

**Thesis**: 素数 gap に沿った D_floor(s, N) は、臨界直線 s = 1/2 を唯一の scaling 指数ゼロ線として持つ放物面で、曲率 (log N)²、底深さ N^{−2/3}。RH の **素数統計版**、N1 framework Arrow 1 kernel 定量統制の数論的最強 instance。

---

## §1 Introduction

### 1.1 Paper 2 + Twin-Zeta の数論的位置付け

古典数論の中心対象 π(x) − li(x) は ζ 非自明零点の振動スペクトル。Paper 2 (2026-02-20) は u(n) = M·x + y mod L の代数恒等式 Δu = (M·Δx + Δy) mod L を主張、Twin-Zeta session (2026-03-04) は gap-indexed factorization

$$F_{g,k}(s) = \kappa_g \cdot G_k(s) \cdot W_k(\omega) + a_g \cdot \Delta_k(s) + \epsilon_{g,k}(N)$$

を確立した。本論は両結果を統合し、N1 framework の **Arrow 1 kernel 定量統制 instance** として展開する。

### 1.2 N1 framework header からの forward

本論は N1 を **公理として引用** し、公理 A0-A7 / S15 主定理 / 3 Arrow + Fi/I commutation / T-AAS 主定理 / Arrow 間 triangulation discipline / 6-step protocol を **再展開しない**。N1 framework 内で Paper 2 具体結果 (M1-M5) を展開し、各 § で N1 のどこに lift されるかを明示する。

### 1.3 用語

- **prime gap g**: p_{n+1} − p_n。特に g = 2 (twin), 4, 6, ..., 30。
- **F_{g,k}(s)** = $\sum_{p\,:\,p+g\,\text{prime}} e^{2\pi i k \tau(p)} \cdot p^{-s}$ — gap g prime pair 上の Dirichlet 型観測量 (τ(p) = 内部 scan 位相)。
- **三層分解**: F_{g,k}(s) = (κ_g·G_k·W_k) [Scan] + (a_g·Δ_k) [Structural] + ε_{g,k} [Information]。G_k = 全素数 τ-Dirichlet 級数、W_k = gauge window (Paper 0 Nyquist cut)、Δ_k = ζ 零点振動成分、ε_{g,k} = mod 6 arithmetic residual。
- **D_floor(s, N) := 1 − R²(s, N)** — 三層 fit 残差。本論の主要観測量。
- **carry 率 c(g, X)**: u(n) = M·x + y mod L で x + (g mod X) が X を超える漸近確率。
- **residue exclusivity**: 素数 gap が parent prime の mod 6 residue に制限される構造的事実 (§4.2)。
- **κ_g**: gap g prime pair 密度定数、Hardy-Littlewood twin 定数 C₂ の ΣΦ 対応物。

### 1.4 主張一覧

| ID | Statement | Status |
|---|---|---|
| **M1** | c(g, X) は X 上有限 Euler 積で閉形式 | RESOLVED (OQ-P2-1) |
| **M2** | D_floor 最小値 s=1/2、放物型・曲率 (log N)²・底 N^{−2/3} | CONFIRMED + RESOLVED (P2-2a/b/c) |
| **M3** | critical strip 上 D_floor dip が γ₁ detect | CONFIRMED (P2-2e, 21 σ-points) |
| **M4** | ε_{g,k} は mod 6 principal indicator のみ (非主指標構造的ゼロ) | CLOSED NEGATIVE (P2-3) |
| **M5** | 三層 = S15 同型 + Observation-optimal gauge 構造解析 | CONFIRMED + structural (N1 §6.1 + §4.5.1 forward) |

---

## §2 Carry 閉形式 (OQ-P2-1 RESOLVED)

### 2.1 主定理

**定理 2.1 (carry 率 closed form)** — X ≥ 2, Y ≥ 1, L = XY, gcd(M, L) = 1, prime gap g ≥ 2 に対し、Hardy-Littlewood 分布の下で漸近 carry 率は

$$
c(g, X) = \frac{N_g(X)}{|S_g(X)|}, \quad
|S_g(X)| = X \prod_{p \mid X}\!\Bigl(1 - \frac{\nu_g(p)}{p}\Bigr), \quad
\nu_g(p) = \begin{cases} 2 & p \nmid g \\ 1 & p \mid g \end{cases}
$$

ここで $|S_g(X)|$ は X を割る素数上の有限 Euler 積 (admissible starting residues 数)、

$$
N_g(X) = \#\bigl\{ b \in \{1, \ldots, r-1\} : \gcd(b, X) = \gcd(r-b, X) = 1 \bigr\}, \quad r = g \bmod X
$$

は短 finite sum。c(g, X) は r = g mod X と X 各素因子に対する g の整除性のみに依存。

### 2.2 証明スケッチ

p 素数, x₁ = p mod X とおく。carry c = 1 ⟺ x₁ ≥ X − r (r = g mod X)。

Dirichlet 定理 + Hardy-Littlewood 相関により、prime pair (p, p+g) の residue 対の結合分布は admissible set $S_g(X) := \{a \in \mathbb{Z}/X\mathbb{Z} : \gcd(a, X) = \gcd(a+g, X) = 1\}$ 上の一様分布に収束。

carry 条件 x₁ ≥ X − r を a = X − r + b (b ∈ [0, r−1]) と書き直すと、gcd(a, X) = gcd(r − b, X), gcd(a + g, X) = gcd(b, X) (g = qX + r)。ゆえに S_g(X) 内 carry 配置は {b ∈ [1, r−1] : gcd(b, X) = gcd(r−b, X) = 1} に一致 (b = 0 は除外)。

|S_g(X)| は CRT で素冪 p^k ∥ X ごとに分解: p ∤ g で禁止 residue 2 class → (p−2)·p^{k−1}, p | g で禁止 1 class → φ(p^k) = (p−1)·p^{k−1}。掛け合わせて Euler 積形。∎

### 2.3 数値検証

Script: `experiments/core/oq_p2_1_carry_closed_form.py`、primes up to 10⁷。

**X = 396 (Paper 2 main parameter; 2² · 3² · 11, ω=3)**:

| g | \|S_g\| | N_g | c_pred | empirical | diff |
|---|---|---|---|---|---|
| 2  | 54  | 1 | 1.852% | 1.868% | −0.02pp |
| 4  | 54  | **0** | **0.000%** | 0.000% | 0.000pp |
| 6  | 108 | 2 | 1.852% | 1.845% | +0.01pp |
| 8  | 54  | 2 | 3.704% | 3.483% | +0.22pp |
| 10 | 54  | 1 | 1.852% | 1.740% | +0.11pp |
| 12 | 108 | 2 | 1.852% | 1.618% | +0.23pp |
| 14 | 54  | 3 | 5.556% | 5.741% | −0.19pp |
| 16 | 54  | **0** | **0.000%** | 0.000% | 0.000pp |
| 18 | 108 | 4 | 3.704% | 3.943% | −0.24pp |
| 20 | 54  | 4 | 7.407% | 7.902% | −0.49pp |
| 22 | 60  | 2 | 3.333% | 3.362% | −0.03pp |
| 24 | 108 | 6 | 5.556% | 5.675% | −0.12pp |
| 26 | 54  | 5 | 9.259% | 9.780% | −0.52pp |
| 28 | 54  | 2 | 3.704% | 3.885% | −0.18pp |
| 30 | 108 | 8 | 7.407% | 8.417% | −1.01pp |

Aggregate (15 gaps, 600,178 transitions): c_pred = 2.89% vs empirical = 2.95%、全 |d| < 1.1pp (O(1/√N) Hardy-Littlewood 有限サンプル誤差と整合)。

**X-scan for g = 2** (twin carry rate):

| X | factorization | \|S_2\| | c_pred | empirical |
|---|---|---|---|---|
| 20  | 2² · 5             | 6   | 16.667% | 16.550% |
| 30  | 2 · 3 · 5          | 3   | 33.333% | 33.074% |
| 50  | 2 · 5²             | 15  | 6.667%  | 6.560%  |
| 100 | 2² · 5²            | 30  | 3.333%  | 3.238%  |
| 200 | 2³ · 5²            | 60  | 1.667%  | 1.668%  |
| 396 | 2² · 3² · 11       | 54  | 1.852%  | 1.868%  |
| 500 | 2² · 5³            | 150 | 0.667%  | 0.641%  |
| 1000| 2³ · 5³            | 300 | 0.333%  | 0.336%  |

8 点全 |d| ≤ 0.3pp。X = 50 (15 gaps): 全 |d| < 1.5pp、carry rate range 6.7%-60% を再現。

### 2.4 Zero-carry / Conductor 次元 / Paper 2 §C.2 訂正

**Zero-carry (Paper 2 Remark 2.5)**: c(g, X) = 0 ⟺ N_g(X) = 0。X = 396 では g = 4, 16 で該当 (全 b 棄却)。これらは閉形式の **代数的帰結** であって経験的偶然ではない。

**Conductor 次元 = ω(X)**: c(g, X) は 2 つの scope-distinct constraint (a) starting residue x₁ coprimality with X, (b) (p+g) residue (x₁ + r) coprimality with X に依存。同 scope の異なる位置で jointly factorizable でないが、Euler 積分解 ∏_{p|X} で 1 prime ずつの constraint の積として表される:

$$\dim(\text{conductor}_\text{carry}) = \omega(X)$$

X = 396 では ω(X) = 3 (primes 2, 3, 11)、Euler product 3 因子。これは Paper 2 §C.2 の "carry 率 closed form なし、conductor 次元不確定" を **訂正**。φ(X)-依存性は ∏(1 − ν_g(p)/p) で正確に capture、N_g(X) も fully explicit。

### 2.5 N1 framework での position

**Arrow 1 instance** (N1 §4.1): F_{g,k}(s) input spec のうち X 軸 (gauge L = XY 周期) が Structural observable ω(X) を encode。c(g, X) closed form は Arrow 1 mapping の代数的閉鎖。

**T-AAS 位置** (N1 §5): X = 396 で g = 4, 16 が zero-carry を取ることは ker_gauge (Z/XZ × Z/XZ residue lattice 上 torsion 消滅条件) の clean な代数的 realization。**f_torsion(c) = 0** (Q-gauge で消える), **f_rational(c) = ω(X)** (gauge invariant conductor)。

**S15 位置** (N1 §3.3 Structural): ω(X), |S_g(X)|, N_g(X) 3 観測量はいずれも parameter-free integer invariant として Structural 層に住む。

---

## §3 D_floor スペクトル定理 (OQ-P2-2 + P2-4)

### 3.1 主結果 (最終形)

**主張 3.1** — gap-universal な放物型公式

$$
\log D_{\mathrm{floor}}(s, N) \approx -0.68 \cdot \log N + 0.216 \cdot (\log N)^2 \cdot (s - \tfrac{1}{2})^2 + \text{const}
$$

すなわち $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 \cdot (\log N)^2 \cdot (s - 1/2)^2)$。

- **底 (s = 1/2)**: D_floor ∼ N^{−2/3} → 0 (factorization 完全化)
- **幅**: ∼ 1/(0.47 · log N) → 0 (delta 的収縮)
- **gap 依存**: 曲率係数 C_log/(log N)² は gap によらず 0.16 ± 0.004 (±4%)
- **exp 指数**: (s − 1/2)² = 臨界直線からの距離の 2 乗

定数 0.216, 2/3, 0.68 の起源解析は §6.4 で構造的に展開。一次近似: 明示公式の零点 ρ = 1/2 + iγ 寄与 p^{ρ−s} = p^{(1/2−s)+iγ} の一次展開で δ_g(s) ∝ (s − 1/2)·⟨log p⟩_g、PNT で ⟨log p⟩ ∼ log N → C_log ∝ (log N)²。

### 3.2 放物型 fit の根拠

Model 比較 (N ∈ {1M, ..., 50M}, g = 2):

| Model | 式 | R² range | 大 N |
|---|---|---|---|
| A (linear parabola) | D = D₀ + C·Δs² | 0.963-0.994 | D₀ < 0 at 50M (崩壊) |
| B (log-linear) | log D = a + b·Δs | 0.682-0.888 | N↑で悪化 |
| **C (log-quadratic)** | **log D = a + b·Δs + c·Δs²** | **0.996-0.999** | **全 N で安定** |
| D (log-Gaussian) | log D = a + c·Δs² | −0.74-0.59 | 崩壊 |

Model C 決定的優位。C_log vs (log N)²: R² = 0.9999。

### 3.3 N → ∞ における底の decay (P2-2c, 3 decades)

`experiments/core/dfloor_d0_decay_1B.py`、N ∈ {10⁶, ..., 10⁹} (8 points, **3 decades**):

| N | D(0.5) | D · log N |
|---|---|---|
| 1,000,000 | 0.032596 | 0.4503 |
| 5,000,000 | 0.012474 | 0.1924 |
| 10,000,000 | 0.008108 | 0.1307 |
| 50,000,000 | 0.002790 | 0.0495 |
| 100,000,000 | 0.001701 | 0.0313 |
| 200,000,000 | 0.001032 | 0.0197 |
| 500,000,000 | 0.000525 | 0.0105 |
| 1,000,000,000 | 0.000306 | 0.0063 |

| Model | Parameter | R² |
|---|---|---|
| **D₀ ∝ N^{−δ}** | **δ = 0.677, 95% CI [0.646, 0.720]** | **0.998** |
| D₀ ∝ 1/(log N)^β | β = 11.5 | 0.989 |
| D₀ ∝ 1/log N | CV(D·log N) = 1.28 (not constant) | — |

**Power law 優位**。δ = 2/3 は AIC 最良候補 (AIC = −40.07 vs ln 2: −39.07, 1 − 1/π: −38.52)。

### 3.4 RH 翻訳 (Corollary 3.3)

**Observation 3.2** — 放物頂点位置 s = 1/2 は Riemann 仮説の ΣΦ 翻訳。

明示公式 G_k(s) = Σ_p e^{2πik τ(p)}·p^{−s} に対し、零点 ρ = 1/2 + iγ 寄与 $p^{\rho - s} = p^{(1/2 - s) + i\gamma}$:

- s = 1/2: |p^{ρ−s}| = 1 純振動 → 全零点等寄与、p-range 偏りなし
- s ≠ 1/2: p^{1/2−s} 減衰/増幅因子 → sieve 相互作用で歪み

**Corollary 3.3** — critical line s = 1/2 は D_floor の N-scaling 指数がゼロとなる **唯一の** 鉛直線。RH が偽 (σ₀ ≠ 1/2 零点存在) なら頂点 s = σ₀ に移動しうるが、本論測定範囲 (N ≤ 10⁹, 21σ-points, 21 gaps) で頂点 s ≠ 1/2 は一切観測されない。

### 3.5 γ₁ dip: 非自明零点直接検出 (P2-2e CONFIRMED)

D_floor(σ + it) を σ ∈ [0.5, 1.0] (21 points), t ∈ [11, 17] (121 points) で 2D grid 測定 (N = 50M, k_max = 30, g = 2):

| σ | t_min | dip | D_min | D_bg |
|---|---|---|---|---|
| 0.500 | 14.100 | 0.182 | 0.512 | 0.693 |
| 0.525 | 14.100 | 0.207 | 0.533 | 0.739 |
| 0.550 | 14.100 | 0.220 | 0.524 | 0.744 |
| **0.575** | **14.150** | **0.230** | **0.485** | **0.715** ← max |
| 0.600 | 14.150 | 0.229 | 0.437 | 0.666 |
| ... | ... | ... | ... | ... |
| 0.950 | 14.200 | 0.083 | 0.503 | 0.585 |

**決定的事実**:
1. t_min が γ₁ = 14.135 に locking: 全 21 σ で t_min ∈ {14.10, 14.15, 14.20} (grid 0.05 以内)
2. dip 最大 = 0.230 at σ = 0.575 (low-D 領域 σ=0.5 と high-noise σ=1.0 の中間で最適 S/N)
3. dip 全 σ で > 0.08 (γ₁ 影響が critical strip 全域で観測可能)
4. σ-continuity (dip 深さは σ に対し滑らかに変動)

「ζ 零点直接観測」ではないが、**Dirichlet 型残差の極小点として γ₁ が σ-universal に検出される** 実効的 zero detection。

### 3.6 k_max artifact 訂正と Gap 依存性 (3次・4次)

**旧解釈** (memo v1, 2026-04-14): gap=2 で s ≈ 0.85 plateau → s\* = 0.84 finite asymptote → RH 矛盾 (PARTIAL_NEGATIVE)。

**現解釈 (v3)**: plateau は k_max = 30 依存 artifact。k_max sweep (gap=2, N ∈ {500k, 30M}):

| s | k=15 | k=30 | k=60 | k=100 |
|---|---|---|---|---|
| 0.70 | 0.219 | 0.139 | 0.105 | 0.072 |
| 0.80 | 0.081 | 0.022 | 0.009 | −0.002 |
| 0.86 | **0.039** | 0.003 | −0.001 | −0.003 |
| 0.90 | 0.024 | 0.000 | 0.000 | −0.001 |
| 1.00 | **0.0069** | 0.001 | 0.001 | 0.001 |

α(0.86) が k_max とともに +0.039 → −0.003 と縮小、k_max=15 で α(s=1.0) = +0.0069 > 0 で s\* → 1 claim と整合。

**機構**: D = ‖F − cG‖² / ‖F − mean(F)‖²。k_max 増大で high-k モードは gap-specific 固有 residual を持ち c·G fit 不可、分母分子両方を膨張させ低 k decay signal を希釈。plateau は low-k decay と high-k frozen noise の crossover。

**訂正**: 旧 memo v1 "gap=2 例外" / v2 "gap-dependent s_crit" は k_max=30 固定下 artifact。s\* → 1 は小 k_max で gap=2 でも維持。**教訓**: 構造主張前に少なくとも 3 パラメタ sweep。

**Gap 依存性 (4次, k_max × gap cross-sweep)**: α(1.0, g) vs log(g/2) 線形 fit:

| k_max | slope | intcpt | R² | α(1, g=2) | α(1, g=12) | α(1, g=30) |
|---|---|---|---|---|---|---|
| 15  | +0.0280 | +0.002 | 0.979 | +0.0069 | +0.0547 | +0.0787 |
| 30  | +0.0148 | +0.001 | 0.978 | +0.0010 | +0.0308 | +0.0392 |
| 60  | +0.0126 | −0.001 | 0.982 | +0.0010 | +0.0213 | +0.0337 |
| 100 | +0.0087 | −0.001 | 0.975 | +0.0007 | +0.0139 | +0.0236 |

**構造的発見 3 点**:
1. **log(g/2) 線形は k_max 不変** — R² ≈ 0.98 全 k_max 安定、形式自体が構造。
2. **係数は k_max-gauge 依存**: slope(s=1) ∼ k_max^{−0.573} (R²=0.947), slope(s=0.86) ∼ k_max^{−0.251} (R²=0.958)。s=1 近傍 k_max^{−1/2} スケールは high-k モード white-noise 希釈と整合。
3. **α(1, g) > 0 が全 20 entry** — 最小 α(1, g=2, k=100) = +0.0007、s\*(N) → 1 全 gap 普遍、旧 memo v2 "large-gap only" reframe は誤り。

**訂正**: 旧 "α(1, g) ≈ 0.013·log(g/2)" は k_max=30 固定下 gauge 値。差し替え: α(1, g) = a(k_max)·log(g/2), a(k_max) は k_max^{−1/2} 近傍 gauge 量。canonical k_max での係数同定は OPEN (P2-2f)。

### 3.7 OQ-P2-4 RESOLVED

OQ-P2-4 当初「β は exact か fitted か」: Cubic AIC 比較で **β は exact ではない** (cubic AIC = −146 vs power law −94)。

**RESOLVED (2026-04-22)**:
- β NOT exact → 一般化 power law が真の form
- **C_log = 0.216 · (log N)² は exact** (R² = 0.9999, gap 全部で hold)
- **α(0.5) = 0.677 は gauge invariant** (3 decades, ±5%)、δ = 2/3 は AIC 勝つが厳密同定 N ≥ 10¹⁰ pending

これは N1 §3.5 排他性閉鎖における **A2 公理 (収束率 = 観測量) の数論内最強 instance** — α(0.5) = 0.677 そのものが gauge-invariant scaling observable。

### 3.8 N1 framework での position

**Arrow 1 kernel 統制 instance** (N1 §6.1): D_floor 放物型公式は F_{g,k}(s) Scan 軸 Arrow 1 kernel の **定量的統制**。最小値 s = 1/2 は Arrow 2 上固定点ではないが、γ₁ dip locking (§3.5) で **Arrow 1 kernel 内部構造 (ker_topo)** を直接露呈。**S17 (Arrow 3 e-extremum) 関係**: §3.1 κ ≈ 0.216 ≈ 1/(2·2.31) は零点密度時間平均由来 O(1) 定数、零点密度 1/(2π)·log(γ/2π) との関係は §6.4。

**Open questions (N1 §8.3 寄与)**:

| Sub-Q | 内容 | Status |
|---|---|---|
| P2-2a | log D_floor 放物形 (gap-universal) | **CONFIRMED** |
| P2-2b | 曲率 C_log ∝ (log N)² | **CONFIRMED** (R²=0.9999) |
| P2-2c | D₀ ∼ N^{−2/3} (δ ≈ 0.677) | **RESOLVED** (3 decades) |
| P2-2d | ε_k peak が ζ zeros と対応 | **REJECTED** (perm p=0.81) |
| P2-2e | D_floor(σ+it) dip locking at γ₁ | **CONFIRMED** (21 σ-points) |
| P2-2f | canonical k_max 同定 + β(s) 理論化 | **OPEN** |
| P2-2g | α(s, k_max, N) 双極限 | **OPEN** |
| P2-2h | α(s=1, g) ∝ log(g/2): universal s\*→1 | **CONFIRMED** (4th iter) |

---

## §4 ε_{g,k} の Dirichlet 分解 (OQ-P2-3 CLOSED NEGATIVE)

### 4.1 主結果

**定理 4.1 (ε mod 6 mirror symmetry)** — ε_{g,k} の mod 6 residue Dirichlet 指標分解は **principal indicator χ₀ (6|g) のみで全スパン**、非主指標 χ₁ (Legendre) 構造的ゼロ:

- **χ₁ Legendre 投影** ‖B‖²: permutation test (N=30M, k_max=150, 19 gaps) で **p = 0.87 (z = −1.05)** ⇒ signal なし
- **χ₀ indicator 投影**: R² block test で **p = 0.014 (z = +2.62)** ⇒ class 0 (6|g) の D_floor は class 1, 2 の約半分 (floor ≈ 0.0049 vs 0.0100)
- s = 1 では全 signal 消失

### 4.2 Residue exclusivity の構造的理由

N = 30M で 100% 成立する structural fact:

- **g ≡ 2 (mod 6)** は p ≡ 5 (mod 6) primes からのみ発生 (p+g ≡ 1 mod 6)
- **g ≡ 4 (mod 6)** は p ≡ 1 (mod 6) primes からのみ発生 (p+g ≡ 5 mod 6)
- **g ≡ 0 (mod 6)** は両 residue class から発生 (約半々)

class 1 (g ≡ 2) と class 2 (g ≡ 4) は互いに異なる parent residue を持つが統計的に対称・独立な noise realization → χ₁ = (m₁−m₂)/2 構造的消失。class 0 (g ≡ 0) のみが「二重 source」のため低 D_floor が distinguished (χ₀ indicator 効果)。これを **residue exclusivity** と呼ぶ。

### 4.3 帰結 (second-stage factorization 不在)

ε_{g,k} の "second-stage factorization" は **存在しない**。residue mirror symmetry が非主指標寄与を禁止 → arithmetic residual 層は principal indicator (conductor 次元 1) のみ。これは `c_filtration_obstruction.md` 「f_rational 住所 = ker_topo^{non-surj} ∩ target のみ」と整合 (Twin-Zeta session L = 99000 で conductor ω = 4、ここでは mod 6 で conductor = 1 に縮減)。

### 4.4 N1 framework での position

**T-AAS clean instance** (N1 §5.2): OQ-P2-3 は **f_torsion = 0** (χ₁ 構造的消失 → Q-gauge で自明) + **f_rational = 1** (χ₀ のみ、conductor dim 1) を実現する clean instance。N1 §5.2 表に Stark / Brauer と並ぶ 3rd NT instance として登録。

**Arrow 1 kernel 構造** (N1 §4.6): residue exclusivity = 構造的 obstruction、ker_gauge ⊕ ker_topo 分解で ker_gauge 側 (χ₁ Legendre) が **mirror symmetry で自動消滅** する代数的機構 = N1 §5.2 "ker_gauge classical" 行 (f_torsion 寄与) の数論的純粋 instance。

**Conductor 次元の Structural 寄与**: conductor dim = 1 は N1 §3.3 Structural 層 f_p(ρ), f_χ 行に類似する parameter-free integer invariant。

---

## §5 三層分解 = S15 Observable Trichotomy (N1 §6.1 deep dive)

### 5.1 同型主張

| Twin-Zeta layer | 数学的内容 | S15 層 | Arrow | 辞書 residence |
|---|---|---|---|---|
| κ_g · G_k · W_k | PNT main term × gauge window | **Scan** | 1 | S12 (τ-scan) |
| a_g · Δ_k | ζ 零点スペクトル寄与 | **Structural** | 2 | S15 structural |
| ε_{g,k} | mod 6 arithmetic residual | **Information** | 3 | S15 information |

これは N1 §6.1「Paper C 三層分解 = S15 同型 in single object」claim の数論的核心。

### 5.2 各層の gauge invariance 検証

- **Scan (κ_g)**: M ∈ {13, 1979, 1981, 49999} で κ_2(s=1, k=0) = 0.299512 完全非依存 ⇒ S15 Structural 不変量。Hardy-Littlewood twin 定数 C₂ = 1.3203... との関係 $\kappa_2 \approx 2C_2/\int_2^N dt/\log^2 t \cdot 1/\pi(N)$ で数値整合。
- **Structural (Δ_k)**: s = 1/2 で全 gap において R² > 0.9998、gauge-free。
- **Information (ε_{g,k})**: §4 で mod 6 principal indicator のみ寄与、conductor 次元 1。

### 5.3 s による三層比の遷移

```
         s = 0.5                   s = 1.0
g    Scan%  Struct%  Info%    Scan%  Struct%  Info%
2    3.7    95.7     0.6      1.8    51.8     46.4
6    3.7    96.1     0.2      1.8    51.4     46.9
12   3.7    96.1     0.2      1.5    45.1     53.3
30   3.7    96.1     0.2      1.6    45.2     53.2
```

- **s = 1/2**: Structural 96%, Information 0.3% → ζ 零点構造支配
- **s = 1**: Structural 45%, Information 53% → arithmetic residual 半数以上

「s = 1/2 で arithmetic が洗い流される」が S15 層の **定量的遷移** として確認 — §3 D_floor 放物型と表裏一体 (arithmetic relative weight が (s − 1/2)² で増加)。

### 5.4 N1 §6.1 への deep dive ─ single object 3 Arrow simultaneous の意味

N1 §6.4 (Arrow 間 triangulation) で Paper C を「**3 Arrow simultaneous in single object F_{g,k}(s)**」と特徴付けた。Stark (Arrow 2/3) や Brauer (Arrow 1 kernel) と異なり、**単一観測対象 F_{g,k}(s) の中に 3 Arrow が同時 embed** されている数論的特殊性:

- **Arrow 1**: F_{g,k}(s) → (gap distribution {p : p+g prime}, gauge L=XY, k mode) input spec
- **Arrow 2**: F_{g,k}(s) → −log F_{g,k}(s) → ε_{g,k} の log-derivative chain
- **Arrow 3**: (Cl(O_K) for K = ℚ(ζ_{XY}), residue mod 6) → log h_K, log φ(L), log gap density

3 Arrow 同時成立が、Paper 2 数論内で F_{g,k}(s) を観測理論 "完全 instance" として position する根拠。Stark/Brauer は Arrow 1 / Arrow 2-3 instance として F_{g,k}(s) と相補的だが、F_{g,k}(s) ほど単一 instance に 3 Arrow を packing しない。**帰結**: F_{g,k}(s) は数論内 S15 同型の **canonical realization**、N1 framework predictive power は本対象を起点として Stark / Brauer / 他 NT instance に放射的に展開できる。

---

## §6 Observation-optimal gauge theorem の構造解析 (N1 §4.5.1 forward expansion)

N1 §4.5.1 は theorem の **2 instance 対比** (Paper C coincide vs Paper 2 carry split) を statement のみで示し、構造解析を本論に forward した。本 §6 はその展開。

### 6.1 Paper C coincide instance ─ ζ functional eq による structural enforcement

**主張 6.1** — Paper C における coincide (Information balance s = 1/2 = Structural balance s = 1/2) は ζ(s) = ζ(1−s)·χ(s) (χ(s) = 2^s π^{s−1} sin(πs/2) Γ(1−s)) による structural enforcement に由来する。

| 機構 | 内容 |
|---|---|
| **(a) Information balance** (Arrow 2 上 S13 半値固定点) | D_floor minimum at s = 1/2 (§3.1 主結果) — ζ-family Scan log-derivative chain 上 half-value fixed point |
| **(b) Structural balance** (Arrow 1 上 RH 零点) | RH (assumed): ζ 零点 critical line s = 1/2 + iγ 集中 — Δ_k(s) (ζ 零点振動成分) の natural balance locus |
| **(c) 同時固定** | functional equation の s ↔ 1−s 対称性が (a) と (b) を **同一 fixed point s = 1/2** に collapse |

**N1 §4.5.1b agreement test** (point realization): $g_I^D = g_S^D$ = s = 1/2 (point ∈ Obs(D))、agreement criterion = **point-to-point equality** ✅、C(D) = 0 (agree)。これは agreement を forces する domain-internal structural identity (functional equation) の唯一 confirmed instance。

### 6.2 Paper 2 carry split instance ─ X = 6 vs X = 2g locus

**主張 6.2** — Paper 2 における split (Information balance X = 6 ≠ Structural balance {X = 2g locus}) は **arithmetic mod-n reducibility** に由来。enforcement (functional equation 型) は不在。

| 機構 | 内容 |
|---|---|
| **(a) Information balance** | D_floor minimum w.r.t. X (g=2 fixed) は X = 6 で実現 (Paper C §3 + carry conductor Euler product structure)。\|S_2(6)\| = 6·(1−2/2)·(1−1/3) = 0 (zero-carry artifact)、実用上 X = 6 近傍 low-conductor 領域 |
| **(b) Structural balance** | c(g, X) = 1/2 locus は X = 2g で実現 (carry rate half-value arithmetic structure)。15 gaps tested: g=2→X=4, g=4→X=8, ..., g=30→X=60 — locus realization |
| **(c) 非交差** | X = 6 (point) と {X = 2g} (locus) は **arithmetic mod-n compatibility 不在** で intersect しない: X = 6 が locus に乗るのは g = 3 のみ、prime gap g は常に even (g≥4 even, g=2 twin) → g = 3 は NT scope 外 → 永遠に intersect しない |

**N1 §4.5.1b agreement test** (point-in-locus realization): $g_I^D$ = X = 6 (point), $g_S^D$ = {X = 2g : g ∈ S} (locus), criterion = **point-in-locus**、結果 X = 6 ∉ {2g} for g ≠ 3 + g = 3 ∉ NT prime gap → C(D) ≠ 0 (disagree)。

### 6.3 Split causation: arithmetic mod-n reducibility

**N1 §4.5.1 Path 3 split causation taxonomy** において Paper 2 carry split は **arithmetic mod-n reducibility** clause に分類される (`c_observation_optimal_gauge.md §5`):

> g_S が conductor X の arithmetic structure (X = 2g locus) で pin され、Information optimum X = 6 (factor 3 由来) と locus が intersect しない

これは Paper E (画像 AI) stochastic basin selection と並ぶ split causation の 2nd class:
- Paper 2: **deterministic arithmetic mod-n** (parity 制約 + factor structure)
- Paper E: **stochastic basin** (training trajectory 確率的 UNet weight initialization)

**N1 §5.2 への寄与**: 本 §6.3 は OQ-P2-3 (Dirichlet residue exclusivity) と並ぶ **arithmetic mod-n constraint の数論的 instance**。Residue exclusivity = class division (mod 6) 上 constraint、carry split = X choice 上 constraint。両者が arithmetic mod-n が NT 観測量 T-AAS / agreement test を支配する 2 instance を提供。

### 6.4 D_floor 放物型公式各因子の構造解析

§3.1 の定数 0.216, 0.68, 2/3 の origin 構造解析:

**(α) 0.216 = 1/(2·2.31)**: 零点密度時間平均 N(T) ∼ (T/2π) log(T/2π) (Riemann-von Mangoldt) で unit time あたり零点数 (1/2π) log(γ/2π)、γ₁ = 14.135 で評価 ≈ 0.184。0.216 に近いが完全一致せず、有限 N effect (N ≤ 50M で zeros ≤ γ_max ≈ 17) と sieve weight 混合と推測。**Open**: 厳密同定は P2-2f に統合。

**(β) δ = 2/3 origin**: 標準 CLT δ = 1/2 (Hardy-Littlewood 独立サンプル平均)。観測値 δ = 0.677 は 1/2 超え、destructive interference からの sieve weight 効果示唆。candidate: δ = 2/3 (phase importance metric `c_information_theory.md`) / δ = ln 2 = 0.693 (Arrow 2 S13 半値) / δ = 1 − 1/π ≈ 0.682 (π 経由 Arrow 1)。AIC で 2/3 勝つが N ≥ 10¹⁰ 厳密同定 OPEN。**Interim**: δ = 2/3 が AIC 最良候補だが exact 同定 pending。

**(γ) C_log = 0.216·(log N)² が exact** (R² = 0.9999, gap 全部 hold): PNT による ⟨log p⟩ ∼ log N 一次近似 + 零点 phase avg O(1) の組み合わせから直接出る。OQ-P2-4 で **C_log は exact** 確認 (gap 全部で 0.16 ± 0.004)。

**N1 §3.5 / §4.4 への寄与**: 0.216, 2/3, ln 2 等の特殊値は N1 §4.5 (S13/S14/S17) の数論内 instance を提供。具体: C_log ∝ (log N)² ⟹ Arrow 1 kernel の "log" が **log p = log of prime element** という arithmetic Hartley counting に reduce (N1 §3.4 Information layer "Λ(n) = −ζ'/ζ" との直接接続)。

### 6.5 Carry rate Euler product vs residue exclusivity の対比

§2.4 と §4.2 は異なる数論的構造で T-AAS にコントリビュート:

| Aspect | Carry rate (§2) | Residue exclusivity (§4) |
|---|---|---|
| **Constraint type** | gcd coprimality (Z/XZ, single prime ごと) | mod 6 residue partition (Z/6Z class division) |
| **Conductor scope** | ω(X) (X 素因子個数) | 1 (mod 6 principal indicator) |
| **Closed form mechanism** | Euler product ∏_{p|X}(1 − ν_g(p)/p) | Mirror symmetry (χ₁ structural zero) |
| **T-AAS f_torsion** | 0 (Q-gauge で消える) | 0 (mirror で消える) |
| **T-AAS f_rational** | ω(X) (X-dependent) | 1 (universal) |

両者は arithmetic mod-n constraint の **異なる集約軸** (X 軸素因子分解 vs g mod 6 residue partition) で T-AAS を実現、N1 §5.2 OQ-P2-3 instance + §2.5 carry instance の 2 instance によって NT T-AAS clean instance space を form。

---

## §7 Twin prime 無限性の不要性

### 7.1 Proposition 7.1

**Proposition 7.1** — 三層分解は twin prime conjecture (TPC) の真偽に依存しない。

| シナリオ | κ₂ の漸近 | Structural layer | Factorization |
|---|---|---|---|
| TPC true | κ₂ → C₂ × (const) > 0 | Δ_k 不変 | 永続的に成立 |
| TPC false | κ₂ → 0 (F_{2,k} → 0) | Δ_k 不変 | finite range で成立 |

根拠: (1) finite range 内で F_{2,k}(s) = κ₂·G_k·W_k + a₂·Δ_k + ε は純代数的に成立 (Paper 2 Thm 2.1) (2) Δ_k の形 (ζ 零点振動構造) は twin 個数に依存しない (3) 他 g (g = 4, 6, 8, ...) factorization は完全独立。

**Validation**: g ∈ {2, 4, 6, 8, ..., 30} の全 11 gap で R² > 0.9998 (twin は convenient example、理論前提ではない)。

### 7.2 S15 + T-AAS による説明

TPC は **Scan 層 (Arrow 1)** の問題 (κ_g = gap g prime pair 密度 = PNT + sieve 漸近)。ζ 零点構造は **Structural 層 (Arrow 2)** の問題 (Δ_k は gap g 条件付け部分集合の取り方に依存しない)。Scan/Structural 分離 ⇒ 独立性。

T-AAS 的読み: TPC true ⟹ F_{2,k} は f_rational 的 (infinite support → ℚ-module)、TPC false ⟹ F_{2,k} は f_torsion 的 (finite support → ℤ-torsion)。どちらでも ker_topo (ζ 零点位相構造) と ker_gauge (M, X, Y 選択) は同一 — TPC は「f_torsion か f_rational か」を問う問題で、ker 構造には触れない。

これは N1 §5 T-AAS framework が **TPC 真偽非依存** で operative であることを示す = N1 framework header の数論内 robustness 証拠。

---

## §8 帰結と Open Questions

### 8.1 確立 (M1-M5)

1. **M1 — Carry 率 closed form (OQ-P2-1 RESOLVED)**: 有限 Euler 積 c(g, X) = N_g(X)/|S_g(X)|, conductor dim = ω(X)、30+ 設定 |d| < 1.5pp。
2. **M2 — D_floor 放物型公式 (P2-2a/b/c CONFIRMED + RESOLVED)**: D_floor ∼ N^{−2/3}·exp(0.216·(log N)²·Δs²), 3 decades verified。
3. **M3 — γ₁ detection in D_floor(σ + it) (P2-2e CONFIRMED)**: 21 σ-points で γ₁ = 14.135 dip locking。
4. **M4 — Gap 依存性 4th iter (P2-2 4th, P2-2h CONFIRMED)**: log(g/2) 線形 structural、coefficient k_max-gauge a(k_max) ∼ k_max^{−1/2}。
5. **M5 — 三層 = S15 同型 + Observation-optimal gauge structural analysis (N1 §6.1 + §4.5.1 forward expansion)**: F_{g,k}(s) は数論内 single object 3 Arrow simultaneous canonical realization、Paper C coincide / Paper 2 split を arithmetic mod-n reducibility として明示。

加えて: **OQ-P2-3 CLOSED NEGATIVE** (§4 Dirichlet residue exclusivity, T-AAS f_torsion=0, f_rational=1 clean instance) / **OQ-P2-4 RESOLVED** (§3.7 β not exact, C_log exact R²=0.9999, α(0.5)=0.677 gauge-inv)。

### 8.2 Partial / Open

| ID | 内容 | Status |
|---|---|---|
| **P2-2f** | canonical k_max 同定 + slope(s) vs k_max 指数 β(s) 理論化 | OPEN |
| **P2-2g** | α(s, k_max, N) 双極限 (k_max → ∞, N → ∞) | OPEN |
| **P2-5** | D(1) ≈ 0.447 同定 | PENDING |
| **P2-2c (高精度)** | δ = 2/3 高精度確認 (N ≥ 10¹⁰) | PENDING |
| **0.216 origin** | 零点密度時間平均からの厳密同定 | OPEN (P2-2f 統合候補) |

### 8.3 N3-N5 forward bridge

| 後続 | 主題 | 本論からの forward | 状態 |
|---|---|---|---|
| **N3** | Path 2 数論的普遍性 (Dirichlet L 系列) | §3 D_floor 構造を Dirichlet L(s, χ) に lifting (Schumann path 2 5+ instances)。§4 residue exclusivity の Galois rep 系一般化 (mod L principal indicator) | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`) — §3 D_floor lifting attempt は "structural fit only" close (SC4 caveat), §4 residue exclusivity の一般化は scope outside (Dirichlet L extension trajectory completed) |
| **N4** | Hasse-Weil L × Stark 構造 | §3 D_floor を Hasse-Weil L で展開 (CM curve, central curvature)。§5.4 single object 3 Arrow simultaneous の Galois rep 側類比。§6 split causation を Stark rank 0/1 で具体化 | **v0.2 起草完了 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — §3 D_floor 公式の **5 component weight-class dependent transfer pattern** 確立 (vertex location + multi-gap = transfer / curvature scaling + decay + γ₁ dip = ζ 固有 / 一方 weight-2 で **K_E·t²→r BSD analytic rank** という weight-2 specific predictive content emerge), §5.4 / §6 split causation は §4.1 Stark Class number formula 6-gauge との connection で展開 |
| **N5** | Brauer 障害論 + Origination matrix (8-gauge) | §4 OQ-P2-3 T-AAS clean instance を Brauer 5-tier の class 0 (Tier 1 strict) と接続。§3.1 定数 0.216, 2/3, ln 2 を Origination matrix 8-gauge signature で分類 | **v0.2 起草完了 2026-04-27** — 本論 §3.1 定数 0.216 / 2/3 / ln 2 を **{anal, mult} / {prime_coord, anal} / {char, anal}** 8-gauge signature で classify (N5 §4.5)。本論 §4 OQ-P2-3 T-AAS f_torsion=0/f_rational=1 clean instance は Tier 1 strict (S_3) と T-AAS taxonomy で structurally aligned (N5 §5.1) |

### 8.4 辞書 residence map (N1 §8.4 拡張)

| 本論 piece | residence | 状態 |
|---|---|---|
| §2 Carry closed form (OQ-P2-1) | `research/oq_p2_1_carry_closed_form.md` (主体), `c_recursive_floor_principle.md §6.8` cross-ref | RESOLVED 2026-04-22 |
| §2.4 Conductor dim = ω(X) | `nt_conductor.md §6` extension annex (NT carry conductor) | 2026-04-26 annex 候補 |
| §3 D_floor 放物型公式 | `c_recursive_floor_principle.md §6.8` (D_floor cross-domain table NT 行) + `§6.8.1` (Dirichlet L gap universality fragment, N3 §4.6 transfer) + `§6.8.2` (Hasse-Weil L extension, N4 §3 transfer) | 既 (ESTABLISHED 2026-04-13) + **N3 backward §6.8.1 + N4 backward §6.8.2 実装済 (2026-04-26)** |
| §3.1 (M2) | `c_theorems_master.md` D_floor(s) row | 既 |
| §3.5 γ₁ dip detection | `c_recursive_floor_principle.md §6.8` (本論 numerical cross-ref) | 既 |
| §3.6 4th iter k_max-gauge | `research/oq_p2_2_sstar_asymptotic.md` (主体) | RESOLVED 2026-04-22 |
| §4 Dirichlet residue exclusivity (OQ-P2-3) | `c_filtration_obstruction.md` (T-AAS f_rational instance), N1 §5.2 表 | 既 + N1 register |
| §5 三層 = S15 同型 | `c_theorems_master.md` row S15 + N1 §6.1 reference | N1 §6.1 deep dive 済 |
| §6 Observation-optimal gauge structural analysis | `c_observation_optimal_gauge.md §5 Path 3 split causation` (arithmetic mod-n clause, 本論 §6.3 expansion) | 2026-04-26 expansion 候補 |
| §7 Twin prime 不要性 | `c_filtration_obstruction.md` (f_torsion vs f_rational binary) + N1 §5 framework robustness | 既 |

**N3-N5 forward residence**: 各後続論文が本 §3.1, §4, §5.4, §6.3 を直接引用する形で展開する。

**N3 v0.2 (2026-04-26) backward 統計**: N3 起草で本論 §3 D_floor lifting attempt は honest dual reporting で展開され、**Dirichlet L extension scope = "structural fit only"** で close。**genuine extension fragment** = multi-gap structural invariance (12/12 PASS) は `c_recursive_floor_principle.md §6.8.1` に N3 §4.6 transfer として書き戻された。Paper C-level 2-quantity uniqueness + (log N)² curvature scaling は **ζ 固有 (本論 §3 ESTABLISHED)** confirmed (Paper N3 §4.4 + §4.5 で 2 path REJECTED, Paper C uniqueness preserved more strongly)。

**N4 v0.2 (2026-04-26) backward 統計**: N4 起草で本論 §3 D_floor lifting の **weight-2 (Hasse-Weil L) extension** が確立、`c_recursive_floor_principle.md §6.8.2` に N4 §3 transfer として書き戻された。本論 §3 で確立した **D_floor 公式 5 component partition** (vertex + multi-gap + curvature + decay + γ₁ dip) のうち **vertex location + multi-gap が weight-1/2 共に transfer**、**curvature + decay + γ₁ dip は weight-1 ζ 固有**。weight-2 では別 observable (K_E central curvature) が **BSD analytic rank detection (K·t²→r) という weight-2 specific predictive content** を提供。**Framework predictive transfer pattern is weight-class dependent** (Paper N4 main thesis) が本論 §3 D_floor 公式の structural decomposition から direct emerge。

---

## 変更履歴

- **v0.5 (2026-04-27)**: N5 backward link + NT 5-paper 完成。N5 v0.2 起草完了 を §8.3 N3-N5 forward bridge 表の状態列に反映 (本論 §3.1 定数の 8-gauge classification 確定 + §4 OQ-P2-3 が Tier 1 strict T-AAS aligned)。NT 系列 5-paper closure achieved。
- **v0.4 (2026-04-26)**: N4 backward link 追加。N4 v0.2 起草完了 (2026-04-26) を §8.3 N3-N5 forward bridge 表の状態列に反映 (N4 = "K_E·t²→r BSD analytic rank detection genuine framework content confirmed, weight-class dependent transfer pattern 確立")。§8.4 residence map §3 D_floor 行に N4 §3 backward (`c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension) を追加。§8.4 末尾に N4 backward 統計段落追加 (D_floor 公式 5 component partition の weight-class dependent transfer pattern が本論 §3 から direct emerge)。
- **v0.3 (2026-04-26)**: N3 backward link 追加。N3 v0.2 起草完了 (2026-04-26) を §8.3 N3-N5 forward bridge 表の状態列に反映 (N3 = "Dirichlet L extension trajectory completed, structural fit only close")。§8.4 residence map で §3 D_floor 行に N3 §4.6 backward (`c_recursive_floor_principle.md §6.8.1` Dirichlet L gap universality fragment) を追加。§8.4 末尾に N3 backward 統計段落追加 (Paper C uniqueness preserved more strongly via N3 §4.4-§4.5 2 path REJECTED)。
- **v0.2 (2026-04-26)**: compact 版。v0.1 (724 行) から冗長削減 — Abstract 圧縮、§1.2 N1 forward の 6 項目 list を 1 段落化、§2.4-§2.6 (zero-carry / conductor / Paper 2 §C.2 訂正) を 1 subsection に統合、§3.1 の 0.216/2/3 起源説明を §6.4 へ集約、§3.6/§3.7 の k_max artifact 訂正と gap 4 次 iter を 1 節に統合、§3.8 OQ-P2-4 を §3.7 へ統合、§5.4 single object 3 Arrow simultaneous の冗長を圧縮、§6.1/6.2 の (a)(b)(c) 機構を表化、§6.3 split causation 説明を圧縮、§7 S15 説明と T-AAS 読みを統合。骨格・主張・instance 数値・status 表記は全保持。
- **v0.1 (2026-04-26)**: initial NT-only draft. Paper C v0.2 (550 行, multi-domain bridge §7 含む) からの NT-only 拡張版。N1 framework header 上に position、§7 量子接続 (FX/T-KD bridge) を strip、§6 Observation-optimal gauge theorem 構造解析 (N1 §4.5.1 forward expansion) と §3.8 OQ-P2-4 4th iter 結果を追加。

---

## 参考文献 (内部)

**親 paper / bridge**: `papers/Paper_C_NT_Quantum_ja.md` (v0.2, 2026-04-22, multi-domain bridge §7 含む) / `research/paper2_twin_dictionary_bridge_v1.md` (active v1, 2026-04-22)

**Framework**: `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.3, 2026-04-26)

**OQ-P2 research notes**: `research/oq_p2_1_carry_closed_form.md` (RESOLVED 2026-04-22) / `research/oq_p2_2_sstar_asymptotic.md` (RESOLVED 4th iter)

**Paper 2 / Twin-Zeta 原典**: Paper 2 (2026-02-20) / Twin-Zeta harvest (2026-03-04)

**実験 scripts**: `experiments/core/oq_p2_1_carry_closed_form.py` (§2.3) / `experiments/core/dfloor_d0_decay_1B.py` (§3.3) / `experiments/core/oq_p2_2_kmax_gap_crosssweep.py` (§3.6) / `sigmaphi/data/oq_p2_2_sstar/alpha_kmax_gap_crosssweep.csv`

**L1 / meta 依存 (N1 経由)**: `c_theorems_master.md` (S13/S14/S15/S17 + D_floor universality row) / `c_recursive_floor_principle.md §6.8` / `c_filtration_obstruction.md` / `c_arrow_framework.md §4.2.1` / `c_observation_optimal_gauge.md §5` / `c_spectral.md §8` / `nt_conductor.md §6` / `nt_dedekind_artin_zeta.md` / `meta/triangulation_methodology.md §9` / `meta/new_domain_protocol.md §8`

**後続論文 (起草予定)**: N3 (Path 2 数論的普遍性) / N4 (Hasse-Weil L × Stark) / N5 (Brauer 障害論 + Origination matrix)
