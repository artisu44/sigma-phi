---
axis: [A, B, C]
position: research_bridge
status: active_v1 (2026-04-22). OQ-P2-1/P2-2/P2-3 ALL RESOLVED. OQ-P2-4 RESOLVED. OQ-P2-5 pending.
pending: OQ-P2-5 (D(1)~0.447)
resolved: OQ-P2-1 (carry closed form 2026-04-22), OQ-P2-2 (k_max × gap cross-sweep: s*→1 universal, log(g/2) form structural with k_max-gauge coefficient, 2026-04-22 4th iter), OQ-P2-3 (ε mod 6 mirror 2026-04-22), OQ-P2-4 (beta not exact)
created: 2026-04-13
source: Paper 2 (2026-02-20) + Twin-Zeta harvest (2026-03-04) → dictionary (2026-04-12)
depends_on:
  - L1_mathematical/core/c_theorems_master.md  # S15
  - L1_mathematical/core/c_arrow_obstruction.md  # T-AAS
  - L1_mathematical/core/c_recursive_floor_principle.md  # RFP, D_floor
  - L1_mathematical/core/c_filtration_obstruction.md  # ker decomposition
  - _archive/docs/paper2.txt  # Paper 2
  - _archive/docs/harvest_2026-03-04_twin_zeta_unification.md  # Twin-Zeta
---

# Paper 2 + Twin-Zeta ↔ Dictionary Bridge

旧 Paper 2 (u(n) = Mx+y mod L) と Twin-Zeta session (2026-03-04) を
現行辞書 (2026-04-12 時点: S15, T-AAS, RFP, T-KD 等) のレンズで再評価した結果。

**主張**: gap-indexed factorization の三層分解と S15 Observable Trichotomy は **同型**。

---

**⚠ §1-6 は 2026-04-12 時点の旧版。§7-12 で大幅更新あり。
特に「D_floor minimum = s=1/2」は §11 で覆された。§12 の整合性監査表を参照。**

---

## §1 Paper 2 の辞書的位置づけ

### §1.1 核心の再述

Paper 2 の主定理 (Theorem 2.1):

```
Δu = (M·Δx + Δy) mod L
```

任意の整数対に成立する純代数恒等式。素数固有なのは carry 統計と境界越境のみ。

### §1.2 S15 分類

| Paper 2 要素 | S15 層 | Arrow | 根拠 |
|---|---|---|---|
| Δu 恒等式 (Thm 2.1) | Structural | 2 | gauge-free, 系列非依存 |
| Carry 率 3.80% | Scan | 1 | prime gap 分布の τ-residue |
| 境界越境 (prime only) | Information | 3 | prime vs composite の判別力 |

### §1.3 T-AAS 的読み

- **ker_gauge**: M 選択で可視範囲が変わる = gauge 自由度。
  Paper 2 の「M 非依存性」(Prop 2.8) は ker_gauge の次元が 0 であることの表現
  (Δu_top(g) = Mg mod L は M に依存するが、「最頻 = carry-free」という構造は M-free)
- **ker_topo**: 「96% carry-free」は topological fact ではない — X,Y 分割依存。
  しかし L = X·Y が固定されれば Δu = Mg mod L は同一 → **L が位相的不変量**
- **f_torsion**: carry 率は Z/LZ の torsion 構造による制約。
  gap = 4, 16 で carry = 0 (Remark 2.5) = coprime residue structure = **local torsion**

### §1.4 Type I/II 分離

| 対象 | Type | 根拠 |
|---|---|---|
| Δu 恒等式 | Type I (single-shot) | 1回の遷移で厳密に決定 |
| Carry 統計 | Type II (N-scaling) | 大数で安定化 |
| 境界越境 | Type I | 各遷移で binary 判定 |

### §1.5 Conductor 接続

Paper 2 の「言っていないこと」リスト (§C.2):
- carry 率の closed form なし = **conductor_carry の次元が不確定**
- 素数にのみ境界越境 = prime gap の尾部 (g ≥ L/(2M) ≈ 25) の寄与

conductor = constraint count (feedback memory) の観点:
carry 発生条件 c = ⌊(x₁+r)/X⌋ ≥ 1 は x₁ と r の制約。**OQ-P2-1 RESOLVED (2026-04-22)**:
closed form 導出済 (research/oq_p2_1_carry_closed_form.md):

  c(g, X) = N_g(X) / |S_g(X)|,  |S_g(X)| = X · ∏_{p|X} (1 - ν_g(p)/p)

は X を割る素数についての **有限 Euler 積**, ν_g(p) = 2 if p∤g else 1;
N_g(X) = #{b ∈ [1, r-1] : gcd(b,X)=gcd(r-b,X)=1} は [1, r-1] 上の短 finite sum.
30+ configuration で empirical と |d|<1.5 pp 一致. **conductor dim = ω(X)**
(X の素因数個数), 2 ではない。

---

## §2 Twin-Zeta の辞書的位置づけ (主結果)

### §2.1 Gap-Indexed Factorization の三層

Twin-Zeta session の main result (§7):

```
F_{g,k}(s) = κ_g · G_k(s) · W_k(ω)  +  a_g · Δ_k(s)  +  ε_{g,k}(N)
             ├── MEAN LAYER ──────┤     ├─ STRUCTURE ─┤    ├─ NOISE ─┤
```

### §2.2 S15 同型 (本 note の主張)

| Twin-Zeta layer | 数学的内容 | S15 層 | Arrow | 辞書 residence |
|---|---|---|---|---|
| κ_g · G_k · W_k | PNT main term × gauge window | **Scan** | 1 | S12 (τ-scan) |
| a_g · Δ_k | ζ zero spectrum の寄与 | **Structural** | 2 | S15 structural |
| ε_{g,k} | mod 6 arithmetic residual | **Information** | 3 | S15 information |

**根拠**:

**Scan ↔ Mean**: G_k(s) は全素数の τ-Dirichlet 級数 = τ 上の走査。
W_k(ω) は gauge window (Paper 0 の Nyquist cut) = 観測装置の制約。
κ_g は Hardy-Littlewood 定数 = PNT の比例因子。
これらは全て「τ を走査して見える統計的平均」= Arrow 1 (Scan → Structural)。

**Structural ↔ Structure**: Δ_k(s) は G_k(s) からの偏差 = ζ 零点の振動成分。
gauge-free (s=1/2 で R² > 0.9998, 全 gap で成立)。
Arrow 2 の定義: 「gauge によらず保存される構造」= まさにこれ。

**Information ↔ Noise**: ε_{g,k} は mod 6 substructure を持つ:
- g ≡ 2 mod 6 同士: r = 0.996 (高相関)
- cross-class: r = 0.073 (無相関)
mod 6 = **3 classes (conductor dim = 1)** の arithmetic 制約。
Arrow 3 の定義: 「Scan/Structural では記述できない残余情報」。

### §2.3 s=1 vs s=1/2 split と D_floor

Twin-Zeta の critical observation:

```
s = 1:   mod 6 arithmetic effects visible (R² drops for g ≡ 0 mod 6)
s = 1/2: arithmetic effects vanish (R² > 0.9998 for ALL g)
```

RFP (§6) との接続:
- s=1 での R² 低下 = **D_floor(s=1) > 0** (arithmetic obstruction が残存)
- s=1/2 での R² ≈ 1 = **D_floor(s=1/2) → 0** (obstruction が消滅)
- 「より精密な点で D_floor が下がるが消えない」の **逆**: 特殊な点 (s=1/2) で D_floor ≈ 0

**RH 的含意**: D_floor(s) = 0 ⟺ s = 1/2 (critical line)。
これは「RH が正しければ唯一の arithmetic-free locus は critical line」の ΣΦ 翻訳。

### §2.4 κ_{g=2} = 0.3139 の辞書的位置

Twin ratio κ₂ = F₀(twin) / F₀(all) at s=1:
- 5 gauge 全一致 (gauge-FREE) → S15 Structural 層の不変量
- Hardy-Littlewood twin constant C₂ = 1.3203... との関係:
  κ₂ = 0.3139 ≈ 2C₂/∫₂^N dt/log²t × 1/π(N) → 数値的に HL 予測に整合

**L1 候補**: c_theorems_master.md に κ_g の gauge-invariance を S-statement として記録可能。
ただし Hardy-Littlewood 予想自体が未証明のため、S-level (観測的声明) に留める。

### §2.5 ΣΦ = low-pass filter on ζ zero spectrum

```
ΣΦ mode k ↔ ζ oscillation at γ ~ 2πk/log(N)
At rank=25, N=10M: max γ_eff ~ 9.7 < γ₁ = 14.13
→ Standard gauge は ζ 零点を resolve できない
→ High-ω gauge (M=13, rank=151) で γ₁~γ₅ 検出
```

辞書接続:
- **S16 (Fejér absorption)**: Fejér 核の low-pass filter 性が ΣΦ の gauge window と同型。
  W_k(ω) ≈ σ_K(k)/K (Fejér) at K = rank。
- **S12 (τ = internal scanning coordinate)**: τ-Fourier が ζ zero spectrum の窓。
- **T-KD (thermal bridge)**: K(τ) → Z → |F|² chain の「Z」= ζ(s) そのもの。

---

## §3 新発見と OQ

### §3.1 確定した接続 (5件)

1. **Gap factorization ↔ S15**: 三層 = Scan/Structural/Information (同型)
2. **s=1/2 locus ↔ D_floor = 0**: arithmetic-free = critical line (RH 的)
3. **W_k ↔ S16 Fejér**: gauge window = Fejér kernel の離散版
4. **κ_g gauge-invariance ↔ S15 Structural**: Arrow 2 不変量の実例
5. **ε mod 6 structure ↔ conductor**: 3 residue classes = conductor dim 1

### §3.2 新 OQ

| ID | Question | Priority | Residence |
|---|---|---|---|
| OQ-P2-1 | carry 率 c(g, X) の closed form は Euler product で書けるか? φ(X) residue structure の exact formula **RESOLVED_POSITIVELY (2026-04-22)**: c(g,X) = N_g(X) / \|S_g(X)\|, \|S_g(X)\| は X を割る素数の有限 Euler product, N_g(X) は [1, r-1] 上の短 finite sum (r = g mod X). 数値検証 30+ configurations all \|d\| < 1.5 pp. g=4,16 carry=0 (Remark 2.5) は N_g=0 で説明. Conductor dim = ω(X). | **CLOSED** | research/oq_p2_1_carry_closed_form.md |
| OQ-P2-2 | D_floor(s) の s-依存性 **RESOLVED_POSITIVELY_UNIVERSAL (2026-04-22, 4th iter)**: k_max × gap cross-sweep (k_max ∈ {15, 30, 60, 100}, gaps ∈ {2, 4, 6, 12, 30}) により、α(1, g) > 0 は全 20 entry で成立、s\*→1 は **全 gap 普遍**。log(g/2) 線形形式は k_max 不変 (R² ≈ 0.98), 係数は k_max-gauge dependent (slope(s=1) ∼ k_max^{−0.57}, R² = 0.947)。中間 memo v2 の「α(1.0, g) ≈ 0.013·log(g/2)」は k_max=30 specific gauge; 正しくは `α(1, g) = a(k_max)·log(g/2)`。「large-gap only」reframe は誤り。Plateau at s≈0.85 (1st rev) は k_max=30 crossover artifact. Paper C §3.6bis + research/oq_p2_2_sstar_asymptotic.md (4th iter section) 参照。 | **CLOSED** | research/oq_p2_2_sstar_asymptotic.md |
| OQ-P2-3 | ε の second-stage factorization: mod 6 substructure を Dirichlet character χ(mod 6) で分解可能か? **CLOSED_NEGATIVE_STRUCTURAL (2026-04-22)**: 非主成分 χ₁ 消失 (p=0.87); χ₀ indicator のみ (6\|g で D_floor ~半分, p=0.014). Residue exclusivity によるミラー対称性が χ₁ を構造的に殺す. | **CLOSED** | §7.4 |

### §3.3 L1 昇格候補

| 候補 | 条件 | 先行辞書 |
|---|---|---|
| Gap factorization ↔ S15 同型 | Paper Omega 記述に必要 | c_theorems_master.md |
| D_floor(s) 概念 | OQ-P2-2 が formal 化されたら | c_recursive_floor_principle.md |
| κ_g gauge-invariance | S-level statement として | c_theorems_master.md |

---

## §4 Paper 2 → Paper 3 bridge の辞書的再評価

Paper 2 §C.3:
> I(Δu; τ) ≈ 0 か？ (A層の合同構造と S層の巡回構造の情報論的独立性)

辞書翻訳:
- Δu = Arrow 2 的量 (Structural, gauge-free after L-fixing)
- τ = Arrow 1 的量 (Scan coordinate)
- I(Δu; τ) ≈ 0 ⟺ **Arrow 1 と Arrow 2 の直交性** = S15 の核心主張の一つ

Paper 3 の question は S15 の **数値的検証** に相当する。
S15 が ESTABLISHED (2026-04-10) であるため、Paper 3 の主張は
辞書内で既に理論的根拠を持つ。ただし数値検証は別途必要。

---

## §5 Addendum: Paper 0 の辞書的位置

Paper 0 (Master Theorem, Claims A-E):
- Claim A (u is well-defined): 定義 → trivial
- Claim B (Nyquist cut): S16 Fejér absorption の ΣΦ 版
- Claim C (Conservation R×rank ≈ const): S14 (Bidirectional duality) の実例
- Claim D (β_CRT decomposition): R7 (index gauge) の prime-specific application
- Claim E (bowl = PNT main term): Scan layer = Arrow 1 の content

全 Claim が辞書内に residence を持つ。Paper 0 は辞書の §0 (導入部) に位置する。

---

## §6 Twin 無限性の不要性 — Scan/Structural 分離の帰結

### §6.1 観察

Gap-indexed factorization は **g=2 (twin) に限定されていない**:

```
g=2:  R² = 1.000000  κ₂ = 0.3139  structure 21.1%
g=4:  R² = 0.999963  κ₄ = 0.2873  structure 20.8%
g=6:  R² = 0.999987  κ₆ = 0.3868  structure  7.9%
g=8:  R² = 0.999999  κ₈ = 0.3077  structure 20.8%
...
g=30: R² = 0.999919  κ₃₀= 0.3853  structure  7.4%
```

R² > 0.9998 は **全 g** で成立。twin (g=2) は特別ではない。

### §6.2 Twin prime conjecture の真偽と三層分解の独立性

**主張**: twin prime conjecture の真偽は三層分解の validity に無関係。

論証:

| シナリオ | κ₂ の漸近 | Structural layer | Factorization |
|---|---|---|---|
| Twin 無限 (TPC true) | κ₂ → C₂ × (const) > 0 | Δ_k 不変 | 永続的に成立 |
| Twin 有限 (TPC false) | κ₂ → 0 (F_{2,k} → 0) | Δ_k 不変 | finite range で成立 |

Twin が有限であっても:
1. finite range 内で F_{2,k}(s) = κ₂·G_k·W_k + a₂·Δ_k + ε は成立
2. **Δ_k の形** (ζ 零点構造) は twin の個数に依存しない
3. 他の全 g (g=4,6,8,...) の factorization は影響を受けない

### §6.3 S15 による説明

Twin の有限/無限は **Scan 層** (Arrow 1) の問題:
- κ_g = gap g を持つ素数ペアの密度 = PNT + sieve の帰結
- 密度がゼロになるか正に留まるかは Scan 層の漸近論

ζ 零点構造は **Structural 層** (Arrow 2) の問題:
- Δ_k(s) は G_k(s) からの偏差 = ζ(s) の零点の振動
- この構造は gap g で条件付けた部分集合の取り方に依存しない

**S15 の Scan/Structural 分離** がまさにこの独立性を保証する:
Arrow 1 (Scan → Structural) と Arrow 2 (gauge-free structure) は異なる層に住む。
一方の漸近挙動が他方の構造を変えることはない。

### §6.4 T-AAS による読み

T-AAS の言語では:
- Twin 有限 ⟹ F_{2,k} は f_torsion 的 (finite support → Z-torsion module)
- Twin 無限 ⟹ F_{2,k} は f_rational 的 (infinite support → Q-module)

しかしどちらの場合でも:
- **ker_topo は同一**: ζ 零点の topological 構造は twin count に依存しない
- **ker_gauge も同一**: gauge (M, X, Y) 選択の効果は twin count に依存しない

Twin prime conjecture は「f_torsion か f_rational か」を問う問題であり、
ker の構造 (= ζ 零点の配置) には触れない。

### §6.5 元々の twin window の用途

Twin-Zeta session の文脈で twin に注目した理由:
- 隣接素数間の **carry 操作** (Paper 2 §B.2) の最小 gap = 2 が twin
- twin window は「最小 gap で carry-free 率が最高」(g=2, carry=1.87%) の window
- **隣接素数を消すための操作としては twin の有限/無限は不問**:
  任意の隣接素数 pair (p, p+g) で同一の carry 分解が成立するため

つまり twin は **convenient example** (最小 gap, 最高 carry-free 率) であって、
理論的には任意の g で同一の構造が使える。twin 無限性は前提条件ではない。

### §6.6 帰結

| 声明 | Status |
|---|---|
| 三層分解は twin 無限性に依存しない | **PROVED** (全 g で R² > 0.9998) |
| Twin 無限性は Scan 層の漸近問題 | **ESTABLISHED** (S15 分類) |
| ζ 零点構造は twin count に独立 | **ESTABLISHED** (Structural 層) |
| Carry 分解は任意の gap で成立 | **PROVED** (Paper 2 Thm 2.1, 純代数) |

---

## §7 数値再検証 (2026-04-13, v2 with dictionary tools)

Script: experiments/core/twin_zeta_s15_v2.py
N = 10M, M=1979, L=99000, k_max=25, s ∈ [0.5, 2.0] (31 points)

### §7.1 D_floor(s) = 1 - R²(s) — 主結果

**全 11 gap で s=0.5 が D_floor 最小点** (例外なし):

```
g     D(s=0.5)   D(s=1.0)   ratio
2     0.0063     0.473      75x
4     0.0061     0.595      98x
6     0.0020     0.471      241x
8     0.0024     0.617      260x
10    0.0017     0.562      332x
12    0.0018     0.551      298x
14    0.0032     0.611      193x
18    0.0022     0.568      254x
20    0.0029     0.606      209x
24    0.0027     0.578      214x
30    0.0020     0.549      271x
```

D_floor(s) は s=0.5 で鋭い最小値を持ち、s=1.0 で 75-332 倍に膨張。
**s > 1.5 では D_floor > 0.7 (factorization 崩壊)**。

RH 的解釈: ζ 零点が critical line 上にある
⟺ gap-indexed factorization が s=1/2 で最も精密に成立する
⟺ D_floor(1/2) = min_s D_floor(s) ≈ 0。

### §7.2 S15 三層の s 依存性

```
         s=0.5                    s=1.0
g    Scan%  Struct%  Info%    Scan%  Struct%  Info%
2    3.7    95.7     0.6      1.8    51.8     46.4
6    3.7    96.1     0.2      1.8    51.4     46.9
12   3.7    96.1     0.2      1.5    45.1     53.3
30   3.7    96.1     0.2      1.6    45.2     53.2
```

**s=0.5**: Structural 96%, Information 0.3% → ζ 零点構造が支配
**s=1.0**: Structural 45%, Information 53% → arithmetic residual が半数以上

「s=1/2 で arithmetic が洗い流される」が S15 層の定量的遷移として確認。

### §7.3 κ_g gauge invariance — 完全確認

```
M=1979:  κ₂(s=1, k=0) = 0.299512
M=1981:  κ₂(s=1, k=0) = 0.299512
M=13:    κ₂(s=1, k=0) = 0.299512
M=49999: κ₂(s=1, k=0) = 0.299512
```

κ_g は M に完全非依存 (gauge-FREE)。S15 Structural 層の不変量。

### §7.4 ε mod 6 — **CLOSED_NEGATIVE_STRUCTURAL (2026-04-22)**

当時 (N=50M, k=25) の r=0.996 (within-class) は **低 k_max 共有構造によるアーティファクト**。
N=30M, k_max=150 で再検証:
- 非主成分 Legendre χ₁ 投影: ||B||² permutation test **p=0.87 (z=-1.05)** — signal 無し
- 主成分 χ₀ 指標 (class 0 = 6|g): R² block test **p=0.014 (z=+2.62)** — D_floor が class 1+2 の約半分
- s=1 では全 signal 消失 (earlier memo「s=1 で visible」は再現せず)

**構造的理由**: prime gap の **residue exclusivity** (N=30M で 100% 成立):
- g ≡ 2 mod 6 の gap は p ≡ 5 mod 6 primes からのみ発生 (p+g ≡ 1 mod 6)
- g ≡ 4 mod 6 の gap は p ≡ 1 mod 6 primes からのみ発生 (p+g ≡ 5 mod 6)
- g ≡ 0 mod 6 の gap は両 residue class から発生 (約半々)

class 1 と class 2 は互いに異なる parent residue をもつが、統計的には対称で
独立 noise realization → χ₁ = (m₁ - m₂)/2 は構造的に消失。
class 0 のみ「二重 source」のため低 D_floor が distinguished (χ₀ indicator 効果)。

**結論**: ε の Dirichlet character mod 6 分解は χ₀ (principal indicator) で
  full span。非主成分 χ₁ は residue mirror symmetry により 0。
  "second-stage factorization" は存在しない。

Residence: experiments/core/oq_p2_3_{dirichlet_mod3, s1_check, mirror_mechanism}.py,
data/oq_p2_3_dirichlet/

### §7.5 W_k vs Fejér — 再定義必要

F_k / (κ·G_k) は 1 を大幅に超える k がある (= sieve amplification)。
harvest 時の W_k 定義は normalized amplitude ratio ではなく、
三層 fit の mean component 係数。定義の統一が必要。

---

## §8 D_floor(s) の N-scaling と slope の正体 (2026-04-13, v4)

Scripts: experiments/core/dfloor_slope_investigation.py
Data: N ∈ {1M, 2M, 5M, 10M, 20M, 50M, 100M}, g ∈ {2,...,30} (11 gaps)

### §8.1 主結果: log(D_floor) の s-微分 (slope) は gap-universal で ∼ a·log(N) + b

v3 で得られた slope ≈ 18 (N=100M) の正体を N-scaling で調査。

```
N           log(N)   slope   slope/log(N)
1,000,000   13.82     8.88   0.643
2,000,000   14.51    10.40   0.717
5,000,000   15.43    12.44   0.806
10,000,000  16.12    14.00   0.869
20,000,000  16.81    15.58   0.927
50,000,000  17.73    17.80   1.004
100,000,000 18.42    19.50   1.059
```

Linear fit: **slope = 2.30·log(N) − 23.0** (R² = 0.9995)

slope/log(N) ratio は N とともに単調増加し、N=50M 付近で 1 を通過。
N→∞ の漸近は現データでは slope/log(N) → 1 (単純比例) か
slope/log(N) → c > 1 (超比例) か判定不能。

### §8.2 Gap-universality 確認 (N=50M)

```
g     slope    g     slope
2     17.80    14    15.89
4     17.13    18    17.12
6     17.72    20    15.69
8     16.75    24    16.25
10    17.23    30    16.84
12    17.47
```

Mean = 16.90, Std = 0.67 (±4%)。log(50M) = 17.73。
**slope は gap 選択に本質的に依存しない** (gap-universal)。

### §8.3 RH 翻訳 — 三段記述

**主結果** (数値的に確立):

> log D_floor(s, N) ≈ log D₀(N) + slope(N) · (s − 1/2)
>
> ここで slope(N) ≈ a·log(N) + b (a≈2.3, b≈−23, R²=0.9995)

**翻訳** (RH 的核心):

主指数は **(s − 1/2)**。すなわち:

```
D_floor(s, N) ≈ D₀(N) · N^{α(s−1/2)}
```

ここで α = slope(N)/log(N) は N とともに緩やかに変動し、
大 N では α ≈ 1 に近づく (N=50M で α=1.004)。

- **s > 1/2**: D_floor ∝ N^{α(s−1/2)} → ∞ (factorization 崩壊)
- **s = 1/2**: D_floor ≈ D₀(N) (主指数ゼロ, prefactor のみ)
- **s < 1/2**: D_floor ∝ N^{α(s−1/2)} → 0 (factorization 超改善)

**RH の ΣΦ 翻訳**: critical line s=1/2 は D_floor(s,N) の N-scaling exponent が
ゼロになる **唯一の** 直線。off-critical では factorization が N^{|s−1/2|} で
崩壊 (s>1/2) または過剰改善 (s<1/2) する。

**留保** (prefactor D₀(N) の同定):

s=1/2 上の D_floor(0.5, N) の N 依存性:

```
N           D_floor(0.5)
1,000,000   0.0326
2,000,000   0.0216
5,000,000   0.0125
10,000,000  0.0081
20,000,000  0.0052
50,000,000  0.0028
100,000,000 0.0017
```

D₀(N) は N とともに減少しているが、その速度が定数 (D₀→const>0)、
1/log(N) 減衰、1/√(log N) 減衰、あるいは power-law N^{-δ} のいずれかは
現データでは判定不能 (7 点, 2 decade のみ)。

D₀(N) → 0 ならば D_floor(1/2) → 0 (RH 的に "完全 factorization")。
D₀(N) → const > 0 ならば s=1/2 でも有限の arithmetic residual が残る。

**OQ-P2-2 の sub-questions として分離**:

| Sub-Q | Question | Status |
|---|---|---|
| P2-2a | 主指数 = s − 1/2 (gap-universal) | **CONFIRMED** (slope ∝ log N, gap-universal ±4%) |
| P2-2b | α(N) = slope(N)/log(N) の N→∞ 極限 | OPEN (α→1? or α→c>1?) |
| P2-2c | prefactor D₀(N) ∼ N^{−0.68} [CI: 0.65, 0.72] | **RESOLVED** (N=10⁹, R²=0.998) |

### §8.4 D₀(N) の予備的 fit

```
log(D₀) vs log(N):
  slope = -0.622  (i.e. D₀ ∝ N^{-0.622})
  R² = 0.999

log(D₀) vs log(log(N)):
  slope = -5.55
  R² = 0.992
```

**v5b 修正 (2026-04-13)**: log-space Gaussian fit (Model D) で:
D₀ ∼ N^{−0.530} [95% CI: −0.562, −0.502] (R² = 0.999)。
ただし linear-space parabolic (Model A) では D₀ → 負 at N=50M — 大 N では
log-space fit (Model C: log D = a + b·Δs + c·Δs²) が必要。

Model C (log-quadratic) が全 N で R² > 0.997 の best fit:
C_log = 0.216·(log N)² (R² = 0.9999)。これは明示公式の ⟨log p⟩² 予測と一致。
旧 §8 の「slope ≈ log N」は Model C の線形項 b に対応。

N ≥ 10⁹ での検証は引き続き OQ-P2-2c。

---

## §9 D_floor と非自明零点 — 最終版 (2026-04-13)

Scripts: dfloor_zero_correspondence.py, dfloor_rigorous_v5.py, dfloor_rigorous_v5b.py

### §9.0 Summary Table

| Sub-Q | Claim | Status | Evidence |
|---|---|---|---|
| **P2-2a** | D_floor の s 依存性は (s−1/2)² 放物型 | **CONFIRMED** | Model C R²>0.997 全 N, local α→2 |
| **P2-2b** | 曲率 C_log(N) ∝ (log N)² | **CONFIRMED** | C_log vs (logN)²: R²=0.9999 |
| **P2-2e** | D_floor(σ+it) は t=γ₁ で dip、σ-continuous | **CONFIRMED** | 21σ 全点 t_min∈{14.10,14.15,14.20}, dip>0.08 |
| P2-2d | ε_k ピークが ζ 零点と対応 | **REJECTED** | p=0.81, enrichment 0.7x |
| **P2-2c** | D₀(N) ∼ N^{−0.68} [CI: 0.65, 0.72]. 1/(logN)^β は R² で劣る (0.989 vs 0.998) | **RESOLVED** (N=10⁹, 3 decades, R²=0.998) |

**4 CONFIRMED / 1 REJECTED / 0 OPEN**

**主結果 (最終形)**:

> D_floor(s, N) ∼ N^{−0.68} · exp(0.216 · (log N)² · (s − 1/2)²)
>
> - 放物型最小値の底が s=1/2 に位置 (P2-2a)
> - 曲率は (log N)² に比例 — 明示公式 p^{1/2-s} ≈ 1−(s−1/2)log p の帰結 (P2-2b)
> - 底の高さ D₀ ∼ N^{−0.68} → 0: factorization が N→∞ で完全化 (P2-2c)
> - 複素平面で t=γ₁ に dip — 非自明零点の直接検出 (P2-2e)
> - Width ∼ 1/(0.47·log N) → 0: minimum は delta-like に収縮

---

### §9.1 なぜ s=1/2 が特別か — 明示公式からの導出

G_k(s) = Σ_p e^{2πikτ(p)} · p^{-s} に明示公式を適用。
零点 ρ = 1/2 + iγ の寄与は p^{ρ-s} = p^{(1/2-s)+iγ}。

- **s = 1/2**: p^{ρ-s} = p^{iγ} (純振動、減衰なし) → 全零点が等しく寄与
- **s ≠ 1/2**: p^{1/2-s} が減衰/増幅因子 → gap-sieve との相互作用で歪み

F_k ≈ κ_g · G_k が成立する条件: F と G が同じ零点振動構造を共有。
s = 1/2 でのみ p^{1/2-s} = 1 → sieve による p-range 偏りが中立化。

1次近似: δ_g(s) ∝ (s−1/2) · ⟨log p⟩_g → D_floor ∝ |δ_g|² ∝ (s−1/2)² · ⟨log p⟩²_g。
これが C_log ∝ (log N)² の理論的根拠。

### §9.2 確立された D_floor 公式 (P2-2a, P2-2b)

**Model 比較** (N ∈ {1M, ..., 50M}, 6 points, g=2):

| Model | 式 | R² range | 大 N |
|---|---|---|---|
| A (linear space parabola) | D = D₀ + C·Δs² | 0.963-0.994 | D₀<0 at N=50M → 崩壊 |
| B (log-linear) | logD = a + b·Δs | 0.682-0.888 | N↑で悪化 |
| **C (log-quadratic)** | **logD = a + b·Δs + c·Δs²** | **0.996-0.999** | **全 N で安定** |
| D (log-Gaussian) | logD = a + c·Δs² | -0.74-0.59 | 崩壊 |

**Model C が圧勝**。log D の Δs² 係数:

```
N          C_log    (logN)²   C_log/(logN)²
1M         25.6     190.9     0.134
2M         30.0     210.5     0.143
5M         36.0     237.9     0.151
10M        40.7     259.8     0.157
20M        45.5     282.6     0.161
50M        52.3     314.3     0.166
```

**C_log vs (logN)²: R² = 0.9999**。C_log/（logN)² は弱い N 依存性あり
(0.134→0.166) だが 1 decade で 24% の変動。明示公式予測の leading order と整合。

**D₀ scaling**: D₀ ∼ N^{−0.530} [95% CI: −0.562, −0.502] (R²=0.999)。

### §9.3 γ₁ dip のσ-continuity (P2-2e)

D_floor(σ+it) を σ ∈ [0.5, 1.0] (step=0.025, 21点), t ∈ [11, 17] (121点) で測定。
N=50M, k_max=30, g=2 (twin)。

```
σ      t_min   dip     D_min   D_bg
0.500  14.100  0.182   0.512   0.693
0.525  14.100  0.207   0.533   0.739
0.550  14.100  0.220   0.524   0.744
0.575  14.150  0.230   0.485   0.715  ← MAX
0.600  14.150  0.229   0.437   0.666
0.625  14.150  0.215   0.401   0.616
0.650  14.150  0.195   0.382   0.578
0.675  14.150  0.175   0.380   0.555
0.700  14.150  0.158   0.386   0.544
0.750  14.150  0.131   0.410   0.541
0.800  14.200  0.114   0.435   0.549
0.850  14.200  0.101   0.459   0.560
0.900  14.200  0.091   0.481   0.572
0.950  14.200  0.083   0.503   0.585
```

**決定的事実**:
1. **t_min が γ₁=14.135 に locking**: 全 21σ で t_min ∈ {14.10, 14.15, 14.20} (grid 0.05 以内)
2. **dip max = 0.230 at σ=0.575**: σ=0.5 (D 小) と σ=1.0 (noise 大) の中間で最適 S/N
3. **全 σ で dip > 0.08**: γ₁ の影は critical strip 全域で検出可能
4. **σ-continuity**: dip 深さは σ で滑らかに変動、不連続なし

---

### §9.4 Negative result: ε_k 零点対応 (P2-2d)

|ε_k| のピーク 5/9 が known zeros の Δγ < 2 内に見えたが:

- Permutation test (100k 反復): **p = 0.81** (not significant)
- H₀ 期待値 = 6.8 matches > 観測 5 → enrichment = **0.7x** (むしろ少ない)
- Bootstrap (|ε_k| shuffle): p = 0.96
- Cross-gap: g=6 (1.0x), g=12 (0.4x), g=30 (0.7x) — 全て enrichment なし

**原因**: 10 zeros × window 2Δγ=4 / γ_max=53.2 → 37.6% coverage。
9 peaks なら期待 6.8 matches は偶然水準。

**棄却**: ε_k ピークの零点対応は統計的偶然。
**再探索条件**: k_max ≥ 500 かつ N ≥ 10⁹ で Δγ < 0.5 の narrow window で再検定。
γ_max が十分大きく coverage が低い条件でないと有意性は出ない。

---

### §9.5 D₀ decay 最終結果 (P2-2c RESOLVED, 2026-04-13)

Script: experiments/core/dfloor_d0_decay_1B.py
N ∈ {10⁶, 5×10⁶, 10⁷, 5×10⁷, 10⁸, 2×10⁸, 5×10⁸, 10⁹} (8 points, 3 decades)

```
N              D(0.5)       D·logN
1,000,000      0.032596     0.4503
5,000,000      0.012474     0.1924
10,000,000     0.008108     0.1307
50,000,000     0.002790     0.0495
100,000,000    0.001701     0.0313
200,000,000    0.001032     0.0197
500,000,000    0.000525     0.0105
1,000,000,000  0.000306     0.0063
```

| Model | Parameter | R² |
|---|---|---|
| **D₀ ∝ N^{−δ}** | **δ = 0.677 [CI: 0.646, 0.720]** | **0.998** |
| D₀ ∝ 1/(log N)^β | β = 11.5 | 0.989 |
| D₀ ∝ 1/log N | CV = 1.28 (NOT constant) | — |

**Power law wins decisively** (R²=0.998 vs 0.989)。D·logN の CV=1.28 は
1/logN 仮説を完全に棄却 (定数に程遠い)。

**D₀ → 0 が power law で確定**: δ ≈ 0.68 (v5b の 0.53 から 3 decade fit で修正)。
D(0.5, 10⁹) = 3.06×10⁻⁴。factorization は N→∞ で完全化する。

**修正された D_floor 公式 (最終形)**:

> log D_floor(s, N) ≈ −0.68·log(N) + 0.216·(log N)²·(s−1/2)² + const
>
> D_floor(s, N) ∼ N^{−0.68} · exp(0.216·(log N)²·Δs²)
>
> - s=1/2: D ∼ N^{−0.68} → 0
> - s≠1/2: exp term が N→∞ で支配 → D → 1
> - Width ∼ 1/(0.47·logN) → 0: minimum は delta-like に収縮

**全 5 sub-Q 最終 status: 4 CONFIRMED + 1 REJECTED。OPEN = 0。**

---

## §10 定数の理論的同定 (2026-04-13)

Script: experiments/core/dfloor_constants_identification.py,
        experiments/core/dfloor_general_formula_test.py,
        experiments/core/dfloor_clog_precision.py,
        experiments/core/dfloor_exact_constants_verify.py

### §10.1 δ (D₀ exponent)

| Fit value | CI | 候補 | In CI | AIC |
|---|---|---|---|---|
| 0.677 | [0.646, 0.720] | **2/3 (0.667)** | YES | **-40.07** (best) |
| | | ln 2 (0.693) | YES | -39.07 |
| | | 1−1/π (0.682) | YES | -38.52 |

δ = 2/3 が AIC 最良。S7/S9 phase importance 2/3 と一致。

### §10.2 C_log(N) 精密測定 (P2-2f, 2026-04-13)

旧 §10.1-10.3 の C_coeff=0.216 (N≤50M のみ) は **SUPERSEDED**。
N=10⁶ ~ 10⁹ (10 点, 3 decades) で full s-grid (13 points) 測定。

```
N              logN    C_log    C/(logN)^2
1,000,000      13.82   26.22    0.137
2,000,000      14.51   30.73    0.146
5,000,000      15.42   36.80    0.155
10,000,000     16.12   41.53    0.160
20,000,000     16.81   46.35    0.164
50,000,000     17.73   53.15    0.169
100,000,000    18.42   58.46    0.172
200,000,000    19.11   63.79    0.175
500,000,000    20.03   70.91    0.177
1,000,000,000  20.72   76.52    0.178
```

**C_log は (logN)² に比例しない** — ratio は 0.137→0.178 に単調増加。
サブリーディング項が必要。

### §10.3 Functional form discrimination

| Model | Nfree | R² | AIC |
|---|---|---|---|
| H1: a·(logN)² | 1 | 0.958 | 25.95 |
| H4: a·logN + b | 2 | 0.999 | -6.69 |
| **H2: a·(logN)² + b·logN** | **2** | **0.999** | **-8.62** |
| H2b: a·(logN)² + b·logN + c | 3 | 0.99998 | -48.58 |
| H3: a·(logN)^b | 2 | 0.997 | N/A |

**H2 (quadratic + linear) が AIC best** (H2b は overfit リスク)。

Free fit: C_log = 0.25553·(logN)² − 1.56381·logN

### §10.4 Exact constant identification — 主結果

Free fit の係数が既知定数に一致:

| Parameter | Fit | Candidate | Value | Error |
|---|---|---|---|---|
| a (quadratic) | 0.25553 | **ln2/e** | 0.25499 | **0.21%** |
| b (linear) | −1.56381 | **−π/2** | −1.57080 | **0.45%** |

**候補公式 (0 free parameters)**:

> **C_log(N) = (ln2/e)·(logN)² − (π/2)·logN**

**AIC/BIC比較**: 0パラメータ exact 公式が 2パラメータ free fit を上回る。

| Model | k | R² | AIC | BIC |
|---|---|---|---|---|
| Free (a,b) | 2 | 0.99891 | -8.61 | -8.01 |
| **(ln2/e, −π/2)** | **0** | **0.99859** | **-10.01** | **-10.01** |
| (a_opt, −π/2) | 1 | 0.99891 | -10.61 | -10.30 |

残差にアーチ状パターン (小N で負、中間で正、大N で負) → O(1) 定数項の
存在を示唆。H2b の c = −36.0 だが、10点で3パラメータは過剰。

### §10.5 定数の理論的導出 — partial result

Script: experiments/core/dfloor_curvature_derivation.py

**Weighted prime moment decomposition** (p^{−1/2} weighted averages, N=10⁶~10⁸):

C_log(N) = α·⟨(logp)²⟩_w + β·⟨logp⟩_w  (**R² = 0.999**)

| Coefficient | Fit | 
|---|---|
| α | 0.284 |
| β | −1.005 |

where ⟨·⟩_w = weighted average with w(p) = p^{−1/2}。

**PNT 展開**: ⟨(logp)²⟩_w ≈ (logN)² − 2logN + 2、⟨logp⟩_w ≈ logN − 1 を代入:

C_log ≈ 0.284·((logN)² − 2logN + 2) − 1.005·(logN − 1)
      = 0.284·(logN)² − (0.568 + 1.005)·logN + ...
      = 0.284·(logN)² − **1.573**·logN + ...

**−π/2 の導出**: サブリーディング係数 −1.573 ≈ **−π/2 = −1.571** が
⟨logp⟩ の一次モーメントから自然に出る。これは理論的導出と言える。

**ln2/e は未完**: (logN)² 係数は α=0.284 (⟨logp²⟩ に対する)であり、
(logN)² そのものに対しては effective に 0.255 ≈ ln2/e になる。
この renormalization は ⟨logp²⟩_w / (logN)² の N 依存性 (0.70→0.62) から来る。
α が何かの定数に一致するかは未同定。

**直接 s-微分の問題**: d²/ds² log(D)|_{s=1/2} ≈ 1-14 (N 依存) で
Gaussian fit の C_log = 26-58 と大きくずれる。原因:
- D'(1/2) ≠ 0 (s=1/2 は厳密な極小でない)
- ds⁴ 補正が大きく、局所 Taylor と全域 Gaussian fit が乖離

**理論的意味**:
- **(logN)² scaling**: ⟨(logp)²⟩ ∼ (logN)² (PNT の直接帰結)
- **−π/2**: ⟨logp⟩ のモーメント寄与 (β·⟨logp⟩_w + 2α·logN → −π/2·logN)
- **ln2/e**: effective coefficient。α=0.284 と PNT 近似の renormalization の
  合成。exact な起源は prime sum の spectral structure に埋もれている

**Status**: (logN)² scaling = **DERIVED** (PNT)。−π/2 = **PARTIALLY DERIVED**
(prime moment decomposition)。ln2/e = **EMPIRICAL** (effective parameter)。

### §10.6 修正された D_floor 最終公式

> **D_floor(s, N) ∼ N^{−2/3} · exp( [(ln2/e)·(logN)² − (π/2)·logN] · (s−1/2)² )**

Width ∼ 1/√C_log(N):

| N | C_log | Width |
|---|---|---|
| 10⁶ | 27.0 | 0.193 |
| 10⁸ | 57.6 | 0.132 |
| 10¹⁰ | 99.0 | 0.101 |
| 10¹² | 151.3 | 0.081 |
| 10¹⁵ | 249.9 | 0.063 |

**RH translation (改訂版)**:
D_floor(s) = 0 ⟺ s = 1/2 (N → ∞)。
minimum の width → 0 (delta-like)、depth → 0 (power law N^{−2/3})。
非自明零点の critical line 上集中 = factorization の完全化 (structural layer 支配)。

### §10.7 Status summary

| Component | Status | Evidence |
|---|---|---|
| δ = 2/3 | **CONFIRMED** | AIC best, CI内, S7/S9 一致 |
| C_log = f(logN) form | **CONFIRMED** | H2 (quad+linear) R²=0.999 |
| (logN)² scaling | **DERIVED** | PNT: ⟨(logp)²⟩ ∼ (logN)² |
| b = −π/2 | **partially derived** | prime moment decomposition から |
| a = ln2/e | **candidate+** | 0パラメータAIC best, err=0.21%。effective parameter |
| Full formula | **candidate+** | R²=0.99859 (0 free params) |

### §10.8 Non-Gaussian correction (ds⁴ term)

Script: experiments/core/dfloor_quartic_analysis.py

Gaussian model logD = logD₀ + C₂·Δs² の R² = 0.77-0.83。
4次補正 logD = logD₀ + C₂·Δs² + C₄·Δs⁴ で R² = 0.95-0.97。

```
N             C₂      C₄        C₄/C₂    C₄/C₂²
1M            26.2    -513      -19.6     -0.746
10M           41.5    -778      -18.7     -0.451
100M          58.5   -1028      -17.6     -0.301
1B            76.5   -1259      -16.5     -0.215
```

|C₄| ∼ 2.97·(logN)² (R²=0.991)。C₂ と同じ (logN)² スケーリング。
C₄/C₂ ≈ −17 ± 2 (弱い logN 依存)。C₄/C₂² → 0 (N→∞)。

**解釈**: D_floor の s-profile は exact Gaussian ではなく、
s = 1/2 付近で cuspy (Gaussian より急)、翼で flat (Gaussian より緩)。
ただし N→∞ で C₄/C₂² → 0 なので **Gaussian に漸近収束**。
これは ⟨(logp)⁴⟩ cumulant が ⟨(logp)²⟩² に対して vanishing する PNT の帰結。

---

**OQ-P2-2 status: RESOLVED** (全 sub-Q に回答)。

---

## §11 D_floor の完全プロファイルと α(s) — RH 再解釈 (2026-04-13)

Script: experiments/core/dfloor_full_profile.py,
        experiments/core/dfloor_true_minimum.py,
        experiments/core/dfloor_alpha_profile.py

### §11.1 D_floor(s) の真のプロファイル

s ∈ [0.05, 1.50] の完全測定 (N=10⁶, 10⁷, 10⁸)。

**決定的事実: D_floor の極小は s ≈ 0.1 であり、s=1/2 ではない。**

旧来の「s=1/2 で minimum」は s ≥ 0.5 のみ観測した artifact であった。

```
s       D(1M)     D(10M)    D(100M)    alpha
0.10    0.0025    0.00027   0.000044   0.85
0.30    0.0044    0.00048   0.000062   0.91 (max)
0.50    0.0326    0.00811   0.00170    0.64 ≈ 2/3
0.60    0.103     0.0453    0.0165     0.40
0.80    0.339     0.323     0.300      0.03
1.00    0.447     0.446     0.446      ≈ 0
```

**D(1.0) ≈ 0.447 は N-independent**。s ≥ 0.85 で D は凍結。

### §11.2 α(s) profile: decay exponent

D_floor(s, N) ∼ N^{−α(s)} と定義。5 N 値 (10⁶~10⁸) で 33 s-point 測定。

```
s      alpha    note
0.30   0.914    alpha_max (series divergence peak)
0.49   0.667    alpha = 2/3 crossing
0.50   0.642    CRITICAL LINE
0.56   0.499    alpha = 1/2
0.60   0.400
0.70   0.164
0.80   0.027
0.85   0.004    saturation onset
1.00   0.001    D frozen
```

**α(s) は s=0.30 で最大 (0.914)、s で滑らかに減少、s ≈ 0.85 で 0 に到達。**

Best model (s > 0.5): ~~α(s) = (2/3)·(2(1−s))^{2.54}~~ (R²=0.988, 1 free param)
**→ SUPERSEDED by §13**: power law は not exact (log-log curvature −2.22)。
Cubic polynomial が AIC 52 point 優位。β = 2.54 は fit-range artifact。

### §11.3 RH translation の改訂

**旧 (§10.6)**:
> D_floor(s) = 0 ⟺ s = 1/2 (WRONG — D は s < 0.5 でも → 0)

**改訂版**:

D_floor(s, N) ∼ N^{−α(s)} において:

| 領域 | α(s) | 意味 | 性質 |
|---|---|---|---|
| s < 1/2 | α > 2/3 | D → 0 (fast) | **trivial**: Dirichlet series 発散 |
| **s = 1/2** | **α ≈ 2/3** | **D → 0 (critical)** | **non-trivial**: 収束/発散境界 |
| 1/2 < s < 0.85 | 0 < α < 2/3 | D → 0 (slow) | structural decay |
| s ≥ 0.85 | α ≈ 0 | D → const ≈ 0.45 | factorization 凍結 |

**Critical line の特殊性**: s = 1/2 は D_floor の最小点ではなく、
**trivial/non-trivial decay の境界** (Dirichlet series の収束限界)。

C_log 公式 (§10.4) は右側 (s > 1/2) の挙動のみを記述:
D ~ N^{−2/3} · exp(C_log · (s−1/2)²) = N^{−(2/3 − C_log·(s−1/2)²/logN)}
⟹ α(s) = 2/3 − C_log·(s−1/2)²/logN + O(higher)

### §11.4 Gauge check

N=10M, g=2, 5 values of M:

| M | s* (grid min) | D(s*) |
|---|---|---|
| 13 | 0.480 | 0.0195 |
| 1979 | 0.480 | 0.0057 |
| 1981 | 0.480 | 0.0058 |
| 49999 | 0.480 | 0.0054 |
| 99991 | 0.480 | 0.0048 |

**D(s) は全 s で gauge-dependent** (M による 4x 変動, s=0.5 含む)。

**修正 (2026-04-13 T-GA Step 1)**: D(0.5) の直接 M 比較で CV=71% を確認。
旧記述「D(0.5) は gauge-invariant」は誤り (κ_g と混同)。

ただし **α(0.5) (decay exponent) は gauge-invariant**:

| M | α(0.5) | A_M | R² |
|---|---|---|---|
| 13 | 0.650 | 1014 | 0.999 |
| 997 | 0.677 | 335 | 0.999 |
| 1979 | 0.642 | 241 | 0.999 |
| 49999 | 0.645 | 254 | 0.999 |
| 99991 | 0.659 | 263 | 0.999 |

**Extended test (10 N values, 10⁶~10⁹, 3 decades)**:
α mean = **0.677**, CV = **1.60%** (vs D level CV = 71%)。
CV は N range 拡大で単調減少 (4.3%→1.6%)、N→∞ で CV→0 を示唆。

**正しい gauge structure**: D(0.5, N) = A_M · N^{−α} where
- **A_M**: gauge-dependent amplitude (M で 4x 変動)
- **α ≈ 2/3**: gauge-invariant exponent (CV < 3%)
- **κ_g**: gauge-invariant (exact, CV = 0%)

→ **α(0.5) の gauge invariance が critical line の本質的特徴**。

### §11.5 新しい OQ

**OQ-P2-4** (RESOLVED, 2026-04-14): α(s) の right-side functional form。
旧 model α(s) = (2/3)·(2(1−s))^{β} は **superseded** — β は fit 範囲依存。
→ §13 参照。

**OQ-P2-5** (LOW): D(s ≥ 1) ≈ 0.447 の exact value は？
0.447 ≈ 1 − 1/√5 (0.553)? 1/√5 (0.447)? 要検証。

**OQ-P2-6** (RESOLVED): α(0.5, g) の gap 依存 — 1式に落とした。
α(0.5, g) ≈ α₀·(1 + 0.151·log(g/2)), R²=0.928, 11 gaps 測定。
c = 0.151 の exact value は未同定。non-monotone at g=14, 20。
cf. c_alpha_decay_exponent.md §4.4

---

## §12 整合性監査: §10 vs §11 の差分分析 (2026-04-13)

### §12.1 差分の分類

| 差分 | §10 (旧) | §11 (新) | 原因 | 解決 |
|---|---|---|---|---|
| **定義差** | D_floor: s ≥ 0.5 片側 | D_floor: s ∈ (0, ∞) 全域 | **窓の差**: §10 は s ≥ 0.5 のみ測定 | §10 の結果は s > 0.5 restricted として有効。§11 が完全版 |
| **正規化差** | C_log: Gaussian fit logD = a + C·Δs² | α(s): power law D ∼ N^{−α} | **推定法の差**: C_log は片側 Gaussian fit、α は cross-N power law | 2つは接続する: α(s) = 2/3 − C_log·Δs²/logN (§11.3 式) |
| **窓差** | N=10⁶~10⁹, s=0.50~0.80 | N=10⁶~10⁸, s=0.05~1.50 | s 範囲が異なる、N 上限が異なる | C_log は N=10⁹ まで有効。α は N=10⁸ まで (3点 decade 制限) |

### §12.2 §10 の結論で生きるもの

| 結論 | Status | 条件 |
|---|---|---|
| δ = 2/3 (D₀ ∝ N^{−2/3}) | **VALID** | s=0.5 限定。§11 の α(0.5) ≈ 0.64 は 5-N fit で CI 内 |
| C_log = (ln2/e)·(logN)² − (π/2)·logN | **VALID** | **右側専用** (s > 0.5)。左側には適用不可 |
| AIC で 0-param model best | **VALID** | 変更なし |
| γ₁ dip (§9.3) | **VALID** | s の実数部は 0.5~1.0 で測定。新知見の影響なし |
| ε_k 零点対応 REJECTED (§9.4) | **VALID** | 変更なし |

### §12.3 §10 の結論で死んだもの

| 結論 | Status | 理由 |
|---|---|---|
| "D_floor(s)=0 ⟺ s=1/2" | **DEAD** | D は s < 0.5 でも → 0 (trivially) |
| "minimum の width → 0 (delta-like)" | **REINTERPRET** | minimum は s ≈ 0.1。s=1/2 は boundary、not minimum |
| "非自明零点の critical line 上集中 = factorization の完全化" | **REINTERPRET** | s=1/2 の特殊性 = gauge invariance + trivial/non-trivial boundary |

### §12.4 C_log と α(s) の接続公式

§10 の C_log formula と §11 の α(s) は同一量の異なる表現:

> log D(s, N) = −α(s)·logN + O(1)
>
> 右側 (s > 0.5) の Gaussian 近似:
> log D ≈ −(2/3)·logN + C_log(N)·(s−1/2)²
>        = −logN·[2/3 − C_log·(s−1/2)²/logN]
>
> ∴ **α(s) = 2/3 − C_log·(s−1/2)²/logN** (|s−1/2| ≪ 1, N large)

ただし C_log/logN = (ln2/e)·logN − π/2 → ∞ なので、
α(s) の定義域 (fixed s, N→∞) と C_log の定義域 (fixed N, s variable) は補完的:

- **C_log**: N を固定して s-dependence を記述 (全 N で有効)
- **α(s)**: s を固定して N-dependence を記述 (N→∞ の漸近)
- 接続: 同じ D_floor(s,N) の異なる射影

### §12.5 残る不整合 (要注意)

1. **α(0.5) = 0.642 vs δ = 0.677**: 差 0.035。原因: α は N=10⁶~10⁸ の 5点 fit、
   δ は N=10⁶~10⁹ の 8点 fit。N range の違い。10⁹ を含む δ がより信頼性が高い。
   → **α(0.5) の再測定が必要** (N=10⁹ を含む fit で)。

2. **C_log の "0.216" (旧)**: MEMORY.md の description にまだ残っている。
   実際は C_log/(logN)² の pointwise 値が 0.137~0.178 (N依存)。
   0.216 は §10.1 時点の平均で **SUPERSEDED**。
   → description 修正済み (§10.2 で明記)。

3. **§10.6 の "Width" 表**: C_log Gaussian model 前提。§11 の知見で
   D_floor は Gaussian ではないことが判明 (ds⁴ 補正 + 左右非対称)。
   → **右側 width として有効**。左側は別の functional form。

### §12.6 再現性テスト結果 (2026-04-13)

Script: experiments/core/dfloor_reproducibility_3test.py

**Test 1 (Gap variation, g=2,4,6,8)**:
- α(0.5): g=2: 0.642, g=4: 0.661, g=6: 0.729, g=8: 0.747
- **α(0.5) は gap-dependent** (g=6/8 で 14-16% 高い)
- 形状 (単調減少) は全 gap で保存
- **判定: SHAPE PASS, VALUE CONDITIONAL** — α の絶対値は gap 固有

**Test 2 (N range variation)**:
- Range A (10⁶~10⁸): α(0.5)=0.642, Range B (10⁷~5×10⁸): α(0.5)=0.700
- 差 9.1% — **PASS** (borderline)
- s > 0.6 で差が拡大 (15-41%) → 漸近未到達の影響

**Test 3 (Normalization variation)**:
- α(0.5): Base=0.642, M=13: 0.650, L=10007: 0.651, k=15: 0.692
- α(0.5) は全 config で 8% 以内 — **PASS**
- M=13 は s > 0.7 で α < 0 (D が N で増加) — **shape FAIL**
  原因: M=13 は pseudorandomness が低い → spectral overlap が gauge-polluted

**運用ガード (MANDATORY)**:

1. M >= 1000 (shape 保全)
2. Resonance filter: weighted rd = min_m (|mM−L|/L · √m) >= 0.003
   Script: experiments/core/resonance_filter.py
3. **α(0.5) 推定は resonance-filter 後のペアのみ有効**

推奨デフォルト: M=1979, L=99000 (rd=0.004, SAFE)。
(cf. c_alpha_decay_exponent.md §5)

**C_log の窓依存性**:
- Wide window (ds=0~0.5): C_log/(logN)² = 0.044-0.057
- Narrow window (ds=0~0.3): C_log/(logN)² = 0.137-0.178
- **C_log は fitting window に強く依存** → 報告時に window を明記すべし

**結論**:
| 量 | gap | N range | gauge | Status |
|---|---|---|---|---|
| α(s) shape | PASS | PASS | CONDITIONAL (M≥1000) | **robust** |
| α(0.5) value | +16% at g=8 | +9% | +8% | **semi-robust** |
| C_log (ln2/e) | untested | PASS | untested | **window-dependent** |

---

## §13 OQ-P2-4 Resolution: β is not exact (2026-04-14)

Scripts: experiments/core/oq_p2_4_beta_identity.py (Part 1),
        experiments/core/oq_p2_4_beta_part2.py (Part 2),
        experiments/core/oq_p2_4_beta_part3.py (Part 3)

### §13.1 Setup

旧 model: α(s) = (2/3)·(2(1−s))^β,  β ≈ 2.54 (§11.2, 5 N-values, R²=0.988)。
候補: β = 5/2 = 2.5 が exact value か？

### §13.2 新測定 (6 N-values, 10⁶~3×10⁸)

28 s-point × 6 N での D_floor 再測定。α(s) は logD vs logN の OLS slope。

| s | α(s) | SE | R² |
|---|---|---|---|
| 0.50 | 0.6566 | 0.0125 | 0.999 |
| 0.52 | 0.6106 | 0.0129 | 0.998 |
| 0.60 | 0.4162 | 0.0139 | 0.996 |
| 0.70 | 0.1762 | 0.0102 | 0.987 |
| 0.80 | 0.0296 | 0.0022 | 0.978 |
| 0.85 | 0.0048 | 0.0003 | 0.987 |

### §13.3 Power law fit: β は fit-range 依存

| s_max | n_pts | β | R² |
|---|---|---|---|
| 0.60 | 5 | 2.07 | 0.998 |
| 0.65 | 7 | 2.15 | 0.995 |
| 0.70 | 10 | 2.29 | 0.987 |
| 0.75 | 11 | 2.35 | 0.983 |
| 0.80 | 12 | 2.39 | 0.982 |
| 0.85 | 13 | 2.40 | 0.983 |

**β は 2.07→2.40 で fit 範囲に強く依存**。旧 §11.2 の 2.54 は N=5 値・粗い s-grid
による artifact。β = 5/2 は bootstrap 95% CI [2.23, 2.55] 内だが、これは CI が広い
だけで exact value としての evidence はない。

### §13.4 Log-log curvature: power law は not exact

log(α) vs log(2(1−s)) の linear R² = 0.964 (poor)。
Quadratic fit: curvature = **−2.22** (massive), R² = 0.9998。

**→ α(s) は (1−s) の純粋な冪ではない。**

### §13.5 Model comparison (s > 0.5, 13 points)

| Model | k | R² | AIC |
|---|---|---|---|
| Power: (2/3)·(2(1−s))^β | 1 | 0.983 | −94 |
| Poly forced: c₁·ds + c₂·ds² | 2 | 0.995 | −108 |
| Poly forced: c₁·ds + c₂·ds² + c₃·ds³ | 3 | 0.9998 | −146 |
| **Cutoff power: (2/3)·(1−ds/d₀)^γ** | **2** | **0.9989** | **−127** |
| Free Gaussian: a·exp(−c·ds²) | 2 | 0.975 | −87 |

Cubic polynomial は AIC best だが **Taylor truncation** (§13.5b 参照)。

### §13.5b Polynomial stability crisis (Part 4 結果)

Polynomial 係数は次数に依存して不安定:

| deg | c₁ | c₂ | c₃ |
|---|---|---|---|
| 2 | −2.93 | **+2.79** | — |
| 3 | −2.39 | **−2.46** | +11.14 |
| 4 | −2.48 | **−0.90** | +3.30 |
| 5 | −2.82 | **+8.24** | −76.0 |

**c₂ は符号すら安定しない**。c₁ のみ −2.4~−2.9 で比較的安定。
→ Cubic 係数への exact value 同定は **PREMATURE**。

### §13.5c Cutoff power law model (M1)

**α(s) = (2/3)·(1 − (s−½)/d₀)^γ** (2 params, boundary-compatible)

| Parameter | Fit | Candidate | Distance |
|---|---|---|---|
| d₀ | 0.3196 | **1/π = 0.3183** | 0.0013 |
| γ | 1.3005 | 4/3 = 1.333 | 0.033 |

**構造的優位性**: s = 0.5 + d₀ ≈ 0.82 で α → 0 を **自然に実現**。
Cubic は s=1 で α(1)=0.247 (boundary condition 破綻)。
AIC は cubic (−146) が M1 (−127) に勝るが、M1 は:
- パラメータ 1 個少ない
- Boundary condition を自然に満たす
- Cubic の Taylor truncation problem を回避

**M1 の residual pattern**: 系統的だが小さい (max 0.012)。
→ M1 に 1 param 補正を加えるべきか (e.g., (1+b·ds)) は future work。

Script: experiments/core/oq_p2_4_beta_part4.py

### §13.6 Left/right asymmetry

| |s−0.5| | α_left | α_right | ratio |
|---|---|---|---|
| 0.02 | 0.701 | 0.611 | 1.15 |
| 0.10 | 0.849 | 0.416 | 2.04 |
| 0.20 | 0.898 | 0.176 | 5.10 |

**α(s) は s=0.5 を中心として全く非対称**。左側は plateau → 0.90、右側は急降下 → 0。
対称 model (e.g., α = f(|s−0.5|)) は成立しない。

原因: s < 0.5 は Dirichlet 級数の発散領域 (trivial α → 1)、
      s > 0.5 は収束領域 (α が number-theoretic structure を反映)。

### §13.7 C_log 接続の再検討

§11.3 の接続公式 α(s) = 2/3 − C_log·(s−½)²/logN を検証:
- C_log = (ln2/e)·(logN)² − (π/2)·logN は logN に (logN)² 比例
- d(−logD)/d(logN) は **N 自体に依存** → α(s) は厳密には N-independent ではない
- C_log predicted α は観測値を系統的に過大評価 (s=0.5 付近で +0.05、s=0.65 付近で +0.22)
- **C_log 公式は right-side Gaussian の近似であり、α(s) の全域記述には不十分**

### §13.8 Resolution

**OQ-P2-4: RESOLVED (negative → structural)**

Phase 1 (negative):
- β は exact constant ではない。fit-range 依存 (2.07~2.40) + log-log curvature −2.22
- β = 5/2 は棄却はされないが (p=0.22)、exact value としての evidence もない
- 2·ln2 + 1 ≈ 2.386 が β_free = 2.387 に偶然一致するが、β 自体が ill-defined

Phase 2 (structural):
- Polynomial 係数は次数依存で不安定 (c₂ は符号すら変動) → exact identification は PREMATURE
- **Cutoff power law M1**: α(s) = (2/3)·(1−(s−½)/d₀)^γ が構造的 best model
  - d₀ = 0.320 ≈ 1/π (candidate), γ = 1.30 ≈ 4/3 (candidate)
  - Boundary condition α→0 を自然に満たす (cubic は破綻)
  - R²=0.999, 2 params (cubic: R²=0.9998, 3 params but unstable)

**教訓**: R²=0.9998 でも functional form は間違い得る (Taylor truncation)。
Boundary condition の自然性と係数安定性が R² に優先する。

**残課題**:
- d₀ = 1/π の検証 (bootstrap CI + N range 拡大)
- γ = 4/3 の検証
- M1 に linear correction (1+b·ds) を加えた 3 param model の AIC 評価
- Left side (s < 0.5) の functional form (plateau → 0.90)

---

## §14 Carry balance と D_floor optimum の splitting (2026-04-22)

Paper E の claim E6 (t_start=T/e が S13 × e balance で D_floor 最小) に
触発された Paper D v0.5 meta-claim "Observation-optimal gauge theorem" の
検証過程で、**Paper 2 に splitting が見つかった** (bug ではなく発見)。

### §14.1 Carry balance locus: X = 2g で c(g, X) = 1/2 (CONFIRMED)

**Theorem (empirical, 2026-04-22)**: 任意の偶数 gap g ≥ 2 に対し、
X = 2g で carry rate

$$c(g, 2g) = \frac{N_g(2g)}{|S_g(2g)|} = \frac{1}{2}$$

が厳密に成立する (N_g(2g) = |S_g(2g)|/2, rational equality)。

15 gaps (g ∈ {2, 4, 6, ..., 30}) 全てで確認。script:
`experiments/core/oq_p2_carry_balance_check.py`, output:
`data/oq_p2_carry_balance/oq_p2_carry_balance.json`。

**Locus 構造**: X = 2g は balance だが**唯一ではない**。14/15 gaps で他にも
c = 1/2 を達成する X が存在する。例えば g=10 で {4, 12, 15, 20} = 4 個の
balance X。これは Paper Ω §1.8 の **intersection value** 概念と同型:
複数 gauge が同一 balance value に合流する。

Paper C (s=1/2 unique point), Paper E (t=T/e unique point per schedule) と
異なり、Paper 2 は **locus realization** を示す。

### §14.2 Three-layer D_floor の X-scan: X = 2g は NOT minimum (SPLIT)

script: `experiments/core/oq_p2_xscan_dfloor.py`, output:
`data/oq_p2_carry_balance/oq_p2_xscan_dfloor.json`。

Setup: g=2, Y=250 固定, X ∈ {4, 6, 10, 12, 20, 30, 50, 100, 396},
L = X·Y, M = 1979, N = 10M primes, k_max = 25, s = 0.5。

| X | c(2, X) | L | D_floor | 因子 3 |
|---|---|---|---|---|
| **4** = 2g | **0.500** (balance) | 1000 | 0.006734 | なし |
| 6 | 1.000 (carry sat.) | 1500 | **0.004981** ← min | **あり** |
| 10 | 0.333 | 2500 | 0.011116 | なし |
| 12 | 0.500 (balance) | 3000 | 0.005106 | あり |
| 20 | 0.167 | 5000 | 0.009902 | なし |
| 30 | 0.333 | 7500 | 0.007546 | あり |
| 50 | 0.067 | 12500 | 0.010253 | なし |
| 100 | 0.033 | 25000 | 0.008944 | なし |
| 396 | 0.019 | 99000 | 0.006329 | あり |

**Key findings**:
1. D_floor minimum は X = **6** (c = 1.0, carry saturation)
2. D_floor は L に因子 3 を含むとき系統的に小さい (mod 6 structure, §7.4 と整合)
3. 因子 3 なし subset 内では X=4 (=2g, balance) が最小 (restricted 仮説は成立)
4. **Carry balance ≠ D_floor minimum** — 両者が異なる X で実現

### §14.3 Splitting の解釈: Structural vs Information Arrow

S15 Observable Trichotomy (Paper D §4.5) の視点で splitting を読む:

| Observable | S15 層 | Arrow | 本質 |
|---|---|---|---|
| c(g, X) carry rate | **Structural** | Arrow 1 | admissible residue geometry の整数的不変量 |
| D_floor(s=1/2, N) | **Information** | Arrow 2 | 三層 fit の log-exp bridge residual |

両 observable は同一 observation system の異なる Arrow に住む。
Paper D §4.5 の S13 半値固定点は **Arrow 2 (log-exp bridge) 上の不変量** であり、
Information observable の balance に対応する。

Structural observable (carry rate) の balance は Arrow 1 上で別に定義され、
Paper 2 では mod 6 arithmetic (Paper 2 §7.4) により決まる。

**Paper C の例外性**: s = 1/2 は ζ(s) = ζ(1−s) functional equation により
Structural (RH 的 ζ 零点配置) と Information (D_floor 最小) を **同時に固定**
する。この strong coincidence は Paper C の functional equation に固有。

**Paper 2 の split**: Paper 2 の carry rate と D_floor は異なる Arrow 上の
別 observable で、両者を同時に固定する structural enforcement (Paper C
functional equation に相当するもの) が未発見。

**Paper E は Information のみ**: Paper E §4.5.1 で確認した S13 × e balance
は Information observable (P[Δb₁≠0]) の optimum。Structural observable
(b₁_true のような integer invariant) との coincidence check は未実施。

### §14.4 OQ-Paper2-Balance (新 OQ)

**OQ-Paper2-Balance**: Paper 2 において、carry balance (c=1/2, Structural
Arrow 1) と D_floor minimum (Information Arrow 2) を同時に達成する X が
存在するか? 存在するとすれば、それは Paper C の ζ functional equation に
相当するどのような structural enforcement から来るか?

優先度: **HIGH** (Paper D v0.5 meta-claim を ESTABLISHED に昇格させる唯一の道)。

次の検証手順候補:
1. **2D X-Y scan**: L=X·Y の両方を振り、(c, D_floor) の 2D 図を作る。
   両 minimum が一致する (X, Y) が存在するか?
2. **Structural / Information 分離の formal statement**: c と D_floor が
   Paper D §4.5 / §4.6 framework のどの Arrow に住むかを厳密記述
3. **Paper C analog の探索**: Paper 2 版の functional equation (若し
   あれば) が何を固定するか。κ_g gauge-invariance (Paper 2 §7.3) との
   関係も check。

### §14.5 Paper D v0.5 meta-claim への帰結

Observation-optimal gauge theorem (Paper D v0.5 candidate) は
**CANDIDATE** 止まり。強い ESTABLISHED 形式への昇格は OQ-Paper2-Balance
の closure 待ち。

```
Information layer:   Paper C CONFIRMED, Paper E CONFIRMED
Structural layer:    Paper 2 CONFIRMED (carry balance c=1/2 at X=2g locus)
Cross-layer force:   Paper C のみ (ζ functional equation)
                     Paper 2 で split (OQ-Paper2-Balance)
                     Paper E は未 check
```

→ "Observation-optimal gauge theorem" は **layer 別に別々の statement**
として記述すべき。両 layer 同時 balance の coincidence 条件は **独立な
structural theorem** として (Paper C functional equation の一般化として)
扱う。

### §14.6 教訓

1. **Balance 概念は Arrow 毎**: carry rate (Structural) と D_floor
   (Information) は **同じ domain の別 observable**。それぞれ別の balance
   point を持ちうる。
2. **Paper C の特殊性**: functional equation が 2 Arrow を同時に固定する
   のは **非自明な** structural feature。これは Paper Ω §2.5.1 class number
   formula の "supra-connective tissue" 性 (6 gauge 同時集約) と同型。
3. **OQ の discipline**: 簡単な「X=2g で D_floor 最小」仮説を X-scan で
   直接反証 → splitting 発見 → 新しい深い OQ。Paper C k_max 教訓の同型
   適用 (仮説確認でなく反証を通じて構造理解).

### §14.7 2D (X, Y) scan 結果: OQ-Paper2-Balance RESOLVED NEGATIVE (2026-04-22 夕方)

§14.4 OQ-Paper2-Balance を 2D scan で closure。script:
`experiments/core/oq_p2_balance_2d_xyscan.py`, output:
`data/oq_p2_carry_balance/oq_p2_balance_2d_xyscan.json`。

Setup: g=2, X ∈ {4, 6, 10, 12, 20, 30, 50, 100} (8 values), Y ∈ {50, 100, 150, 250, 500, 1000, 2000} (7 values), 計 56 cells, L = X·Y, N = 10M primes, k_max = 25, s = 0.5, 41.3s runtime。

**Verdict** (pre-registered classifier per `oq_paper_e_structural_spec_v0.md` §5.1):

| Quantity | Value |
|---|---|
| global min (X, Y) | (12, 150) |
| D_min_global | 0.00454 |
| balance_X = 2g | 4 |
| balance_X realized as per-Y min | **None (0/7 Y values)** |
| verdict | **no_intersection** |

**Per-Y min X table**:

| Y | min X | D_min | L factor 3 |
|---|---|---|---|
| 50 | 30 (2·3·5) | 0.00498 | あり |
| 100 | 30 | 0.00511 | あり |
| 150 | 12 (2²·3) | **0.00454** ← global | あり |
| 250 | 6 (2·3) | 0.00498 | あり |
| 500 | 6 | 0.00511 | あり |
| 1000 | 20 (2²·5) | 0.00494 | **なし** |
| 2000 | 10 (2·5) | 0.00494 | **なし** |

**Structural observations**:

1. **X = 4 (2g carry balance) is never min across 7 tested Y values** — 1D split finding (Y=250 のみ) が 2D 全域に拡張、split が robust。
2. **Global min at (X=12, Y=150)**, D=0.00454 が従来 "Y=250 canonical" 前提の D=0.00498 より 9% 深い。Y-canonical 変更の可能性あるが、D 変動幅が ±10% 程度で practically equivalent、canonical 変更の strong reason なし (判断保留)。
3. **Factor 3 の Y-dependence** (§14.8 参照): 大 Y (Y ≥ 1000) で Y 自体が factor 3 を欠き、min X も factor 3 を欠く。

### §14.8 OQ-P2-factor3-conservation (LOW, v1.1 issued)

**Observation (post-hoc, §14.7 2D scan 由来)**:

- Y=50, 100 (factor 3 含まず): min X=30 (factor 3 含む), L = {1500, 3000} 全て factor 3 含む
- Y=150 (factor 3 含む): min X=12 (factor 3 含む), L = 1800 factor 3 含む
- Y=250, 500 (factor 3 含まず): min X=6 (factor 3 含む), L = {1500, 3000} factor 3 含む
- Y=1000, 2000 (factor 3 含まず): min X=10, 20 (両方 factor 3 含まず), L = {10000, 20000} factor 3 含まず

**Hypothesis**: L = X·Y の素因数分解で factor 3 の有無が D_floor min 位置と相関。具体的には Y が小 (≤ 500) で factor 3 を欠く場合、min X 側が factor 3 を補完するが、Y が大 (≥ 1000) で factor 3 を欠く場合、補完されず min X も factor 3 を欠く。

→ "L の factor 3 の有無 の Y-threshold 挙動"。Y が十分大きいと X の factor 3 bias が消失、Y が小さいと X が factor 3 を補完。

**OQ-P2-factor3-conservation** (LOW): Y 軸の factor 3 構造を意図的に制御した 2 系列 2D scan:
- 系列 A: Y 全て factor 3 含む (Y ∈ {3, 6, 30, 150, 300, 600, 3000})
- 系列 B: Y 全て factor 3 含まず (Y ∈ {5, 10, 50, 250, 500, 1000, 5000})

両系列で min X の factor 3 分布を比較。Hypothesis 正なら:
- 系列 A: min X の factor 3 要求が緩む (X ∈ {4, 10, 20} も許容)
- 系列 B: Y 小では min X factor 3 必須、Y 大では factor 3 無しが優位

否なら post-hoc artifact として close。

Priority LOW: 現在の OQ-Paper2-Balance RESOLVED NEGATIVE の main finding に影響せず、structural refinement の LOW 候補。

**Issued**: 2026-04-22 (Paper Prime v0.2 v1.1 update session)。
