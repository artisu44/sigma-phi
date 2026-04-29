---
type: research_note
mode: classify
status: candidate_plus_v1
date: 2026-04-10
version_history:
  - v0 (2026-04-10): failure mode taxonomy skeleton, 4 failure axes, Tier √ / Tier ∞ refinement, dual pair formalization with OQ-NT-7
  - v0.1 (2026-04-10): §14 Attack 4 defense — Tier √ non-bookkeeping formal arguments (Frobenius-Schur topological invariant, pairing-type obstruction orthogonal vs symplectic, log embedding intrinsic symmetry, square-root sign ambiguity, endomorphism algebra $\mathbb{H}$ vs $\mathbb{R}$), audit preparedness completion
  - v0.2 (2026-04-10): Q_8 Tier √ numerical verification added from LMFDB 8.0.12230590464.1; $L(0,\rho)^2 = 16$ and $L(0,\rho)=\pm4$ sign obstruction pinned as numerical witness
depends_on:
  - research/brauer_closure_galois_classification_v0.md (OQ-NT-7, dual pair partner)
  - dictionaries/L2_domain/number_theory_dictionary_v0.md §5.3 §8 OQ-NT-8
  - research/stark_projection_v0.md H-stark-2
  - runtime/change_log/external_audit_response_h_stark_2_human.md (Q6 OQ-NT-8 提案由来)
  - dictionaries/L1_mathematical/nt_frobenius_schur.md (FS indicator, pairing type, ℝ/ℂ/ℍ trichotomy — L1 基盤 for Tier √ defense)
  - dictionaries/L1_mathematical/nt_relative_units.md (norm-one lattice orthogonality — L1 基盤 for §14 Arg 3)
  - dictionaries/L1_mathematical/nt_conductor.md §6.9 (induction/Brauer 分解 — L1 基盤 for closure spectrum)
answers: OQ-NT-8 (partial — formal taxonomy skeleton, detailed per-mode analysis と alternative Stark methods は v0.1+)
relates_to: OQ-NT-7 (dual pair; OQ-NT-7 covers success tiers, 本 note covers failure tiers)
version_history:
  - v0 (2026-04-10): failure mode taxonomy skeleton, 4 failure axes (A C1, B C2, C C3, D C4), Tier √ / Tier ∞ refinement, dual pair formalization with OQ-NT-7
scope_constraints:
  - 対象: OQ-NT-7 v0.2 で structural verified された "closure shortcut が成立しない" Galois 群クラスの詳細分類
  - rank-1 abelian Stark 設定のみ
  - 各 failure mode の alternative Stark methods は本 v0 では outline のみ、詳細は v0.1+
  - 具体数値検証は v0.2 で Q_8 Tier √ witness のみ追加済み
  - Tier √ (square-root obstruction) の formal 定式化は本 v0 で初出
---

# Brauer/Induction Closure Failure Mode Taxonomy v0

**目的**: OQ-NT-7 v0.2 (`brauer_closure_galois_classification_v0.md`) で確立した **3-tier theory** の **Tier ∞** (closure shortcut が成立しない群クラス) を詳細分類し、OQ-NT-7 の success side (Tier 1-3) と dual pair を形成する。

**Dual pair structure**:

```
              closure spectrum
  ├──────── success side ────────┤  ├─ failure side ─┤
  │                                │
 Tier 1    Tier 2    Tier 3+       │     Tier √    Tier ∞
 strict    relaxed   multi-rational│    sqrt only   impossible
  │         │         │            │      │          │
 S_3       D_4     (hypothetical) │    Q_8     (unknown)
 A_4/V_4                           │
  │                                │
  └─── OQ-NT-7 (v0.2) ────────────┘  └─── OQ-NT-8 (本 note) ──┘
```

**動機 (external audit 由来)**: H-stark-2 external human audit (human_RO, 2026-04-10) で Q6 に "representation fragility への failure mode 体系化" が promotion path (c) として提案された。OQ-NT-7 v0.2 で成功側理論の骨格が確立したため、本 note で失敗側を formal に切り出し、OQ-NT-7 との相補 dual を完成させる。

**v0.2 scope**: formal taxonomy skeleton + Q_8 Tier √ numerical witness。各 failure mode の group-theoretic criterion, mechanism, example group, alternative Stark method を列挙。Q_8 以外の数値検証と sign resolution は v0.3+。

---

## §1 Purpose and dual pair with OQ-NT-7

### §1.1 OQ-NT-7 recap (success side)

OQ-NT-7 v0.2 は 4 closure conditions (C1-C4) を満たす Galois 群 $G$ について、以下の 3 tier に分類:

- **Tier 1 strict** ($S_3$, $A_4/V_4$): $L(s, \rho) = \zeta_F/\zeta_\mathbb{Q}$ (single ratio)
- **Tier 2 relaxed** ($D_4$): $L(s, \rho) = \zeta_{F_1}/\zeta_{F_2}$ (field-pair ratio)
- **Tier 3+ higher relaxed** (hypothetical): $L(s, \rho) = \prod_i \zeta_{F_i}^{n_i}$ (multi-field rational combination)

Each tier は analytical complexity を段階的に増やしつつ closure shortcut を保つ。

### §1.2 OQ-NT-8 task (failure side)

Brauer/induction closure shortcut が成立しない群 ("Tier ∞ に落ちる群") の詳細分類。OQ-NT-7 の C1-C4 条件の **どこで** 壊れるかで sub-classify する。

**鍵となる refinement (v0 新規)**: Tier ∞ を更に 2 つに分割:

- **Tier √** (square-root obstruction): $L(s, \rho)^{2k}$ は rational combination 可 だが $L(s, \rho)$ 単体は不可。$Q_8$ がこの tier の代表例 — 2-dim 既約 $\rho$ の量子性 (quaternionic) に由来。
- **Tier ∞** (genuinely impossible): $L(s, \rho)$ の任意の power も rational combination にできない。$L(s, \rho)$ の arithmetic content が "field" の枠組を完全に離れる。

### §1.3 Complete closure spectrum (v0.3 refinement)

| Tier | Form | Examples | Stark formula |
|---|---|---|---|
| **Tier 1** | $L = \zeta_F/\zeta_\mathbb{Q}$ | $S_3$, $A_4/V_4$ | single reg $h_F R_F$ |
| **Tier 2** | $L = \zeta_{F_1}/\zeta_{F_2}$ | $D_4$ | reg ratio $h_{F_1}R_{F_1}/(h_{F_2}R_{F_2})$ |
| **Tier 3+** | $L = \prod \zeta_{F_i}^{n_i}$ | $S_4/V_4$? (多因子) | multi-reg rational |
| **Tier √** | $L^{2k} = \text{rational}$, $L \notin$ | $Q_8$ | square-root of rational combo |
| **Tier ∞** | no power works | (unknown genuinely) | direct Hecke L only |

**Conjecture (v0, tentative)**: 有限 Galois 群 $G$ の rank-1 abelian Stark setup は必ず **exactly one** of {Tier 1, 2, 3, ..., √, ∞} に落ちる。tier は $G$ の representation-theoretic structure (irrep dimensions, Frobenius-Schur indicators, subgroup lattice, character inner products) のみで決定される。

---

## §2 Overview: 4 failure axes (C1-C4 breakdowns)

OQ-NT-7 の 4 closure conditions がどこで壊れるかで failure mode を分類:

| Axis | Condition | Failure meaning |
|---|---|---|
| **A** | C1 (real irrep) | $G$ に $\dim = [G:N]$ の real/orthogonal 既約表現が存在しない |
| **B** | C2 (induction irreducible) | $\mathrm{Ind}_N^G \chi$ が既約でない (Mackey stabilizer $\supsetneq N$) |
| **C** | C3 (zeta ratio reduction) | $L(s, \rho)$ が intermediate fields の rational combination にならない |
| **D** | C4 (unit lattice closure) | $F$-units の Galois orbit が $O_H^\times$/torsion を span しない |

各 axis は更に sub-modes に分割される (後続 §3-§6 で詳細)。

**Cascade phenomena**: 1 つの axis failure が他の axis の failure を誘発することがある。例:
- C1 failure → C3 failure (例: $Q_8$ で real irrep 不在 → zeta ratio 不可)
- C2 failure → C3 failure (例: $S_4/V_4$ で induction reducible → multi-L 因子、single rational combo 不可)
- C4 failure は通常 C1-C3 から独立 (numerical obstruction)

---

## §3 Failure axis A: C1 (real irrep 不在)

$G$ に $\dim = [G:N]$ の real (orthogonal, Frobenius-Schur indicator $\nu = +1$) 既約表現が存在しない。(**L1 基盤**: nt_frobenius_schur.md §1 定義、§3 pairing obstruction、§4 small groups 分類表。以下の FS indicator 計算・三分岐・pairing type 議論はすべて nt_frobenius_schur.md に L1 residence を持つ。)

Sub-modes:

### §3.1 Mode A1: Quaternionic obstruction ($\nu = -1$)

**Criterion**: $G$ に $\dim = [G:N]$ の既約表現 $\rho$ が存在するが、Frobenius-Schur indicator $\nu(\rho) = -1$ (quaternionic, symplectic)。

**Mechanism**:
- $\rho$ は complex 上で既約だが real 上では実現不可 (minimal real realization = $\rho \oplus \bar\rho$ の real form, 2 倍次元)
- $\rho \cong \bar\rho$ as complex reps だが isomorphism は **symplectic (alternating)** で orthogonal ではない
- Hecke induction $L(s, \mathrm{Ind}\chi)$ は complex-valued at real $s$、$L(s, \chi) \neq L(s, \chi)^*$ (i.e., not real)
- Brauer factorization で $\rho$ は常に **squared** で現れる: $\zeta_H$ に $L(s, \rho)^2$ 因子
- 結果: $L(s, \rho)^2$ は $\zeta_H$ と低次 intermediate fields から rational combination で抽出可能だが、$L(s, \rho)$ 自体は **平方根** を要求
- ⟹ **Tier √** に落ちる

**Example**: $Q_8$ (quaternion group of order 8)
- 既約表現: 4 × 1-dim + 1 × 2-dim
- 2-dim 既約 $\rho$ の Frobenius-Schur: $\nu = -1$
- Character table で $\frac{1}{|G|}\sum_g \chi_\rho(g^2)$ を計算すると $-1$ になる (quaternionic 確定)

**Formal characterization (Schur obstruction)**:
$$\nu(\rho) = \frac{1}{|G|} \sum_{g \in G} \chi_\rho(g^2) \in \{+1, -1, 0\}$$
- $\nu = +1$: real (orthogonal), **C1 ✓**
- $\nu = -1$: **quaternionic (symplectic), Mode A1 failure**
- $\nu = 0$: complex (not real-valued character), Mode A3 failure

**Alternative Stark methods**:
- Direct Hecke L-function 数値計算 (Sage/PARI, $\chi$ over $K$)
- 2nd Kronecker limit formula (if $K$ imaginary quadratic)
- Modular forms (if $\rho$ corresponds to modular representation)
- p-adic L-functions (for p-adic Stark analogues)

**Sub-hypothesis**: **H-NT-8-A1** ($Q_8$ で $L(s, \rho) \notin$ rational combination of $\zeta_{F_i}$, only $L(s, \rho)^2$ is) — v0.1 で formal derivation 予定

### §3.2 Mode A2: Dimension mismatch (dim 不在)

**Criterion**: $G$ に $\dim = [G:N]$ の既約表現が **全く存在しない**。

**Mechanism**:
- $\mathrm{Ind}_N^G \chi$ が dim $= [G:N]$ の representation として構成されるが、それと同次元の既約表現がない
- $\mathrm{Ind}\chi$ は多個の irreducible reps に decompose する (必然的に多因子)
- $L(s, \chi)$ は多 Artin L-factor の積: $L(s, \chi) = \prod_i L(s, \rho_i)^{m_i}$
- 単一 $L(s, \rho)$ の isolation は不可能

**Example**: $S_4 / V_4$ setup
- $[G:N] = |S_4|/|V_4| = 6$
- $S_4$ 既約表現 dims: $\{1, 1, 2, 3, 3\}$
- **6-dim 既約なし**
- $\mathrm{Ind}_{V_4}^{S_4} \chi = \rho_3 + \rho_3'$ (2 つの 3-dim 既約に分解)

**Cascade to C2**: Mode A2 は自動的に C2 failure を誘発 ($\mathrm{Ind}\chi$ 可約)。逆は真ならず (C2 failure 単独で A2 でない場合あり — Mode B 参照)。

**Alternative Stark methods**:
- Artin factor 分解: 各 $L(s, \rho_i)$ を別々に分析
- $L(s, \rho_i)$ それぞれが OQ-NT-7 の Tier 1/2/3 に落ちる可能性あり (multi-tier product)
- $S_4$ の場合: $\rho_3$ (標準) は $F = H^{S_3}$ 経由で Tier 1 strict closure を持つ、$\rho_3' = \rho_3 \otimes \mathrm{sgn}$ は別経路
- ⟹ $S_4/V_4$ は **Mode A2 failure だが Tier 3 (product of Tier 1 × Tier X)** に落ちる可能性

**Sub-hypothesis**: **H-NT-8-A2** ($S_4/V_4$ は Tier 3 multi-rational combination case, 各 $\rho_i$ の tier を特定する) — v0.1 予定

### §3.3 Mode A3: Complex irrep (not real, not quaternionic)

**Criterion**: $G$ に $\dim = [G:N]$ の既約表現 $\rho$ が存在、Frobenius-Schur $\nu(\rho) = 0$ (complex-valued character, $\rho \not\cong \bar\rho$)。

**Mechanism**:
- $\rho$ と $\bar\rho$ は異なる既約 (complex conjugate pair)
- $\mathrm{Ind}\chi = \rho$ と $\mathrm{Ind}\bar\chi = \bar\rho$ は異なる
- $L(s, \chi) = L(s, \rho)$, $L(s, \bar\chi) = L(s, \bar\rho) = L(s, \chi)^*$ (complex conjugate at real $s$)
- $L(s, \chi)$ は real $s$ で **complex-valued**
- Brauer factorization では $\rho + \bar\rho$ が一緒に現れる ($\zeta_H$ に $L(s, \rho) L(s, \bar\rho) = |L(s, \rho)|^2$ 因子)
- $|L(s, \rho)|^2$ は rational combination で抽出可能だが、$L(s, \rho)$ 単体の位相情報は失われる
- ⟹ 原則的に Tier √ の variant (相対位相問題)

**Example**: Cyclic $C_n$ with $n \geq 5$ (abelian, complex cubic/higher-order characters). But abelian Galois groups are trivially in the Stark-abelian-over-ℚ setup which is Dirichlet; here we consider non-abelian cases.

Non-abelian example with complex irrep: $A_4$ has 2 complex 1-dim irreps $\chi_3, \bar\chi_3$. But these are 1-dim, and for OQ-NT-7 setup we need $\dim \rho = [G:N] \geq 2$, so 1-dim complex irreps don't directly trigger Mode A3.

Higher example: **binary icosahedral group $2I$** of order 120, has complex irreps at dim 2 (the Pauli-like spinor reps). But this is beyond v0 scope.

**v0 status**: Mode A3 は formal に定義したが、rank-1 abelian Stark 設定で頻出する例は少ない。詳細は v0.1+。

---

## §4 Failure axis B: C2 (induction reducibility)

$\mathrm{Ind}_N^G \chi$ が既約でない。Mackey criterion: $G$-stabilizer of $\chi$ $\supsetneq N$。

Sub-modes:

### §4.1 Mode B1: χ extends to larger subgroup ($G$-stab = $G$)

**Criterion**: $\chi$ は $G$-conjugation で不変、i.e., $\chi^g = \chi$ for all $g \in G$。$\chi$ extends to a character of $G$ itself.

**Mechanism**:
- $\chi$ extends to 1-dim character $\tilde\chi$ of $G$ (possibly in multiple ways if $G/N$ has torsion)
- $\mathrm{Ind}_N^G \chi = \bigoplus_{\psi \in (G/N)^\vee} (\tilde\chi \cdot \psi)$
- 全成分が 1-dim ⟹ $\mathrm{Ind}\chi$ は 1-dim irreps の和
- $L(s, \chi) = \prod_\psi L(s, \tilde\chi \psi)$ = product of Dirichlet L-functions
- **単一 2-dim+ irrep に induce しない**
- これは degenerate な rank-1 Stark で、Dirichlet L-function decomposition に帰着

**Example**: $D_4 / \mathbb{Z}/4$ with $\chi$ of **order 2** (not order 4):
- $\chi(r) = -1$, real
- $\chi^s(r) = \chi(r^{-1}) = -1 = \chi(r)$, invariant
- Stabilizer = $G = D_4$
- $\chi$ extends to $D_4$ as 1-dim character
- $\mathrm{Ind}\chi$ = sum of two 1-dim chars of $D_4$

(これは OQ-NT-7 v0 §3.2.1 で確認済)

**Consequence**: Mode B1 の場合、元の $\chi$ に対する Stark conjecture は **標準 Dirichlet case に帰着** する。Brauer/induction shortcut の対象外だが、closure 自体は容易 (Dirichlet L-function の数値計算で完了)。

**Tier assignment**: Mode B1 は "Stark not in scope of Brauer shortcut" であり、Tier ∞ にも Tier 1-3 にも属さない **degenerate** case。OQ-NT-7 の failure と呼ぶべきかは convention 問題。

**v0 decision**: Mode B1 は "rank-1 abelian Stark via Brauer/induction shortcut" の sub-case ではなく、別 pathway (direct Dirichlet) として扱う。OQ-NT-8 taxonomy には include するが failure ではなく "not applicable" マーク。

### §4.2 Mode B2: Stabilizer strictly between $N$ and $G$

**Criterion**: $N \subsetneq G\text{-stab}(\chi) \subsetneq G$

**Mechanism**:
- $\mathrm{Ind}_N^G \chi = \mathrm{Ind}_{G_\chi}^G (\mathrm{Ind}_N^{G_\chi} \chi)$ where $G_\chi = G\text{-stab}(\chi)$
- 内側の $\mathrm{Ind}_N^{G_\chi} \chi$ は 1-dim (since $N = \ker\chi$-stab within $G_\chi$)
- 外側の $\mathrm{Ind}_{G_\chi}^G$ は dim $[G : G_\chi]$
- 結果: $\mathrm{Ind}_N^G \chi$ は irreducible of dim $[G:G_\chi]$ if the "twisted" induction stays irreducible, else reducible further

**Example**: complex, hard to give without specific group. $S_4 / V_4$ で non-trivial $\chi$ の場合、stab of $\chi$ in $S_4$ has order 8 (= $V_4 \cdot$ stabilizer of χ in $S_4/V_4 = S_3$, which has order 2)。つまり $G_\chi$ is a Sylow-2 subgroup $D_4$ of $S_4$. $[S_4 : D_4] = 3$. So $\mathrm{Ind}$ is 3-dim, which decomposes into $\rho_3 + \rho_3'$... wait, that's 6-dim not 3.

Hmm, let me recompute. For $S_4 / V_4 = S_3$ acting on 3 characters of $V_4 \setminus \{1\}$ by permutation. The 3 non-trivial characters form a single $S_3$-orbit. $G_\chi / V_4$ = stabilizer of one character in $S_3$ = $S_2$ (order 2). So $G_\chi = V_4 \cdot S_2 = D_4$ (Sylow-2 of $S_4$). $[S_4 : G_\chi] = 24/8 = 3$. 

$\mathrm{Ind}_{G_\chi}^{S_4}(\tilde\chi)$ where $\tilde\chi$ is an extension of $\chi$ to $D_4$. dim = 3. $S_4$ irreps of dim 3: $\rho_3$ and $\rho_3'$. So $\mathrm{Ind}\tilde\chi$ = one of $\rho_3$ or $\rho_3'$ (or some combination).

But originally I computed in OQ-NT-7 §6.2 that $\mathrm{Ind}_{V_4}^{S_4} \chi$ has dim 6 and decomposes as $\rho_3 + \rho_3'$. Let me reconcile: this is $\mathrm{Ind}_N^G$ (from $N = V_4$ directly to $G = S_4$), dim $6 = [S_4 : V_4]$. And by stabilizer analysis, this decomposes.

By Mackey: $\mathrm{Ind}_{V_4}^{S_4} \chi = \mathrm{Ind}_{G_\chi}^{S_4}(\mathrm{Ind}_{V_4}^{G_\chi} \chi)$. $\mathrm{Ind}_{V_4}^{G_\chi} \chi$ with $G_\chi = D_4$: dim $[D_4:V_4] = 2$. This 2-dim rep of $D_4$... $D_4$'s 2-dim irrep (= $\rho$ from OQ-NT-7 §12) is the unique 2-dim irrep. So $\mathrm{Ind}_{V_4}^{D_4} \chi = \rho_{D_4}$ (irreducible).

Then $\mathrm{Ind}_{D_4}^{S_4}(\rho_{D_4})$ has dim $2 \cdot 3 = 6$. By Mackey/Frobenius, this decomposes into $S_4$ irreps. Computing character inner products: $\rho_{D_4}$ inducted to $S_4$ gives (by a calculation) $\rho_3 + \rho_3'$.

So $\mathrm{Ind}_{V_4}^{S_4} \chi = \rho_3 + \rho_3'$ (both 3-dim), 6-dim reducible.

Mode B2 mechanism: stabilizer $D_4$ strictly between $V_4$ and $S_4$, leads to "$\mathrm{Ind}\chi = \rho_3 + \rho_3'$" multi-irrep decomposition. $L(s, \chi) = L(s, \rho_3) L(s, \rho_3')$. Multi Artin L-factor.

This is Mode B2 + cascade to Mode A2 (dim mismatch at $S_4$ level doesn't have dim-6 irrep).

### §4.3 Mode B summary

Mode B failures typically cascade with Mode A or Mode C. Pure Mode B (without cascade) is rare. Mode B identification は structural cascading analysis の入口として機能する。

---

## §5 Failure axis C: C3 (zeta ratio impossibility)

$L(s, \rho)$ が intermediate fields の rational combination にならない。これは **tier 判定** を行う部分。

Sub-modes:

### §5.1 Mode C1: Tier 3+ (multi-field positive-power rational combination)

**Criterion**: $L(s, \rho) = \prod_i \zeta_{F_i}^{n_i}$ for some $n_i \in \mathbb{Z}_{>0}$ and intermediate fields $F_i$, but **not expressible as Tier 1 or Tier 2**.

**Mechanism**: より複雑な subgroup lattice で、複数 intermediate fields の積で closure。$D_4$ では関係する 1-dim characters が 1 個しかなかったので Tier 2 で足りたが、複数 1-dim irreps が絡むケースで Tier 3+ が必要。

**Example candidate**: より大きな非可換群 (order $\geq 12$, e.g., $S_3 \times \mathbb{Z}/2$, $\mathbb{Z}/3 \rtimes \mathbb{Z}/4$, etc.)。Exhaustive analysis は v0 scope 外。

**Status**: Tier 3+ は **OQ-NT-7 の success side** に属する (まだ closure 可能)。本 taxonomy での役割: "success だが複雑" の marker。

### §5.2 Mode C2: Tier √ (square-root obstruction)

**Criterion**: $L(s, \rho)^{2k} = $ rational combination for some $k \geq 1$, but $L(s, \rho)^m \neq$ rational combination for $m < 2k$.

**Mechanism**:
- $\rho$ が quaternionic (Mode A1 cascade) または特殊な character 構造
- Brauer factorization で $\rho$ が常に **偶数次** (dim $\rho$ の整数倍) で現れる
- 奇数べきの isolation は平方根を要求、rational closure 外

**Canonical example**: $Q_8$ cascade from Mode A1.

**Detailed derivation for $Q_8$** (structural):

$Q_8$ の既約表現 dims: $\{1, 1, 1, 1, 2\}$。2-dim 既約 $\rho$ の $\nu = -1$ (quaternionic)。

$\zeta_H$ Brauer factorization:
$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot \prod_{i=1}^{4} L(s, \chi_i) \cdot L(s, \rho)^2$$

ここで $\chi_i$ は 4 つの 1-dim 既約 ($Q_8/[Q_8, Q_8] = Q_8/Z(Q_8) = V_4$ 経由で factor)、$\rho^2$ は $\dim \rho = 2$ のため。

Quadratic subfields of $H$ (from 4 index-2 subgroups of $Q_8$ — wait, $Q_8$ has 3 subgroups of order 4, each $\mathbb{Z}/4$, not $V_4$; index-2 subgroups are exactly these 3):

$Q_8$ 部分群構造:
- $\{1\}$ (order 1)
- $\{1, -1\} = Z(Q_8)$ (order 2, center)
- $\langle i\rangle, \langle j\rangle, \langle k\rangle$ (order 4, all $\cong \mathbb{Z}/4$)
- $Q_8$ (order 8)

Index-2 subgroups = 3 cyclic-4 subgroups $\langle i\rangle, \langle j\rangle, \langle k\rangle$。各々 normal ($Q_8$ is Hamiltonian)。対応する fixed fields は 3 つの quadratic intermediate fields $F_i, F_j, F_k$。

$\zeta_{F_i} = \zeta_\mathbb{Q} \cdot L(s, \chi_i')$ where $\chi_i'$ は $Q_8 / \langle i\rangle = \mathbb{Z}/2$ の non-trivial character。これは 1-dim rep of $Q_8$ (one of the 4 non-trivial characters, factoring through $V_4 = Q_8/Z$).

$Q_8$ の 4 個の 1-dim characters: trivial $\chi_0$, and 3 characters $\chi_i, \chi_j, \chi_k$ (one for each $\mathbb{Z}/4$ quotient direction)。$\ker \chi_a = \langle a\rangle$ for $a \in \{i, j, k\}$. 

$\zeta_{F_i} = \zeta_\mathbb{Q} \cdot L(s, \chi_i)$ (i.e., $\chi_i$ is the one with $\ker = \langle i\rangle$)
- Similarly for $j, k$.

Also: $F_Z = H^{Z(Q_8)}$ degree 4 intermediate (biquadratic, $V_4$ Galois over $\mathbb{Q}$)
$\zeta_{F_Z} = \zeta_\mathbb{Q} \cdot L(s, \chi_i) \cdot L(s, \chi_j) \cdot L(s, \chi_k)$ (all 3 non-trivial 1-dim characters of $V_4 = Q_8/Z$)

No degree-3 intermediate field (no order-$\frac{8}{3}$ subgroup).

**Attempt to isolate $L(s, \rho)$**:

From Brauer: $\zeta_H = \zeta_\mathbb{Q} \cdot L(\chi_i) L(\chi_j) L(\chi_k) \cdot L(\rho)^2$

Rearranging: 
$$L(s, \rho)^2 = \frac{\zeta_H(s)}{\zeta_\mathbb{Q}(s) \cdot L(s, \chi_i) L(s, \chi_j) L(s, \chi_k)} = \frac{\zeta_H(s) \cdot \zeta_\mathbb{Q}(s)^2}{\zeta_{F_i}(s) \cdot \zeta_{F_j}(s) \cdot \zeta_{F_k}(s)}$$

$$\Rightarrow L(s, \rho)^2 = \frac{\zeta_H(s) \cdot \zeta_\mathbb{Q}(s)^2}{\zeta_{F_i}(s) \cdot \zeta_{F_j}(s) \cdot \zeta_{F_k}(s)}$$

これは **rational combination of field zetas**。$L(s, \rho)^2$ は Tier 3+ level で表現可能。

しかし $L(s, \rho)$ **単体** には平方根が必要で、field zetas の rational combination では表現できない。これは:

- $\rho$ が quaternionic ⟹ $\rho$ の character が実数値だが representation は ℝ 上で実現不可
- $\rho$ の "Stark unit" は $F = H$ の quaternionic subspace に住む、有理 tier には落とせない

**Tier √ formal definition**:
$$L(s, \rho) \in \text{Tier }\sqrt{} \iff \exists k \geq 1 : L(s, \rho)^{2k} \in \text{Tier 3+}, \text{ but } L(s, \rho)^m \notin \text{Tier 3+ for } m < 2k$$

For $Q_8$: $k = 1$, $L(s, \rho)^2 \in $ Tier 3 (explicit above). ⟹ $Q_8$ is **Tier √ with index $k=1$**.

**Alternative Stark methods for Tier √** ($Q_8$ case):
- Direct numerical Hecke L-function
- $L(s, \rho)^2$ numerical extraction via $\zeta_H / \prod \zeta_{F_i}$, then square root (sign ambiguity!)
- Sign/phase resolution requires additional info (e.g., functional equation root number)
- Alternatively: 2nd Kronecker limit formula for imaginary quadratic base $K$ of $H$

**Sub-hypothesis**: **H-NT-8-A1 refined = H-NT-8-C2**: $Q_8$ は Tier √ with $k=1$, $L(s, \rho)^2 = \zeta_H \zeta_\mathbb{Q}^2 / (\zeta_{F_i} \zeta_{F_j} \zeta_{F_k})$ derivation が v0 で completed。$L(s, \rho)$ 単体の closure は Tier √ obstruction により不可能。

#### §5.2.1 Numerical witness (2026-04-10)

Concrete field: LMFDB `8.0.12230590464.1`,
$$
H = \mathbb{Q}[x]/(x^8 + 12x^6 + 36x^4 + 36x^2 + 9),
\qquad \mathrm{Gal}(H/\mathbb{Q}) \cong Q_8.
$$

The three quadratic subfields are
$$F_2=\mathbb{Q}(\sqrt2),\quad F_3=\mathbb{Q}(\sqrt3),\quad F_6=\mathbb{Q}(\sqrt6).$$

Using the LMFDB field data
$$h_H=2,\qquad R_H=21.2871886415,\qquad w_H=2,$$
and
$$R_2=\log(1+\sqrt2),\quad R_3=\log(2+\sqrt3),\quad R_6=\log(5+2\sqrt6),$$
the $s=0$ specialization gives
$$
L(0,\rho)^2
= \frac{h_H R_H / w_H}{R_2 R_3 R_6 / 2}
= \frac{21.2871886415}{1.33044929010}
= 15.99999999998 \approx 16.
$$

Hence
$$L(0,\rho)=\pm 4.$$

This is the numerical realization of the Tier √ obstruction:

- $L(0,\rho)^2$ is completely determined by field data $(h,R,w)$.
- The sign of $L(0,\rho)$ is not determined by unit groups or orthogonal regulator data.
- The missing sign is external functional-equation data (root number / phase datum).
- Thus the Frobenius-Schur pairing obstruction in `nt_frobenius_schur.md` §3.2 is not merely categorical; it appears numerically as an exact square with unresolved sign.

**Status change**: H-NT-8-A1 / H-NT-8-C2 upgraded from **structural verified** to **numerically witnessed** for the canonical $Q_8$ Tier √ example.

### §5.3 Mode C3: Tier ∞ (genuinely impossible)

**Criterion**: $L(s, \rho)^m \notin$ rational combination of $\zeta_{F_i}$ **for any $m \geq 1$**。

**Mechanism**: $\rho$ の arithmetic content が field の枠組を完全に離れる (transcendental, or requires non-Galois representations, or higher-dimensional algebraic structures)。

**Example candidates (tentative)**: 
- Groups with 既約 representations that don't even $\rho^k$ fit rationally. Highly hypothetical.
- Non-abelian Galois groups with Artin conjecture open + specific structural obstructions

**v0 status**: Tier ∞ の具体例は v0 で出していない。$Q_8$ のような Tier √ までは確認できるが、"本当に任意の power でも不可" の example は representation theory の深い部分を要し、v0.1+ の課題。

**Conjecture (very tentative)**: 全ての有限 Galois 群の rank-1 abelian Stark は Tier 1, 2, 3+, √ のいずれかに落ち、Tier ∞ は空 (i.e., 常にある power で rational combination になる)。これが真なら OQ-NT-8 の "失敗 side" は Tier √ に集約される。

---

## §6 Failure axis D: C4 (unit lattice gap)

$F$-units (or intermediate field units) の Galois orbit が $O_H^\times$/torsion を完全 span しない。

### §6.1 Mode D1: Finite index sublattice

**Criterion**: $\{\text{Galois orbit of } u_F\} \cup O_K^\times$ が $O_H^\times$/torsion の **有限 index** sublattice を span する (index $> 1$)。

**Mechanism**: 
- Rank は正しいが sublattice index > 1
- $H$ に "extra" fundamental units が存在、$F$ や $K$ 由来の units だけでは到達不可
- Magnitude relation $R_H = R_{\text{sublattice}} / [\text{index}]$ で補正可能

**Example**: 数値依存。具体例は case-by-case で Sage/PARI 計算必要。

**Consequence**: Closure の **structural part は成立**、numerical correction factor (index) が必要。部分的 success、completely failure ではない。

### §6.2 Mode D2: Rank-deficient sublattice

**Criterion**: $\{\text{Galois orbit of } u_F\} \cup O_K^\times$ の log embedding 次元が $r_H$ より **真に小さい**。

**Mechanism**:
- Galois 軌道が unit lattice の dimensional collapse を起こす (例: 全ての orbit element が log 空間で特定の hyperplane に縛られる)
- $H$ に "truly independent" units が他の source から必要
- Structural closure が完全には機能しない

**v0 status**: Mode D1, D2 は primarily numerical obstructions。数値検証との関連で v0.1+ で深掘り。

---

## §7 Alternative Stark methods per failure mode (outline)

各 failure mode で Brauer/induction shortcut が使えない場合、alternative な approach:

| Failure mode | Alternative method | 適用条件 |
|---|---|---|
| **Mode A1 (Q_8 quaternionic)** | 2nd Kronecker limit formula | $K$ imaginary quadratic |
| **Mode A1** | Direct numerical Hecke L | 一般 (Sage/PARI 要) |
| **Mode A2 (S_4 dim mismatch)** | Artin factor 分解 + 各 $\rho_i$ の tier 別計算 | multi-tier combination |
| **Mode A3 (complex irrep)** | Functional equation + phase extraction | $\rho$ complex (tentative) |
| **Mode B1 (χ extends)** | Standard Dirichlet L | 常に可能 (Dirichlet case) |
| **Mode B2 (intermediate stab)** | Mackey decomposition + per-factor | 通常 Mode A2 と cascade |
| **Mode C2 Tier √** ($Q_8$) | $L(s, \rho)^2$ rational extraction + sign determination | sign/phase は functional equation 由来 |
| **Mode C3 Tier ∞** (hypothetical) | 不明 / 予想外の structure 要 | 要 representation theory 深部 |
| **Mode D1 finite index** | Index correction (sublattice detection) | numerical |
| **Mode D2 rank deficient** | Extra generator search | numerical |

**Principle**: Brauer/induction shortcut の外にある Stark conjecture 計算方法は、通常 **数論の別伝統** (classical Kronecker limit, modular forms, p-adic, etc.) から借りる。ΣΦ 辞書の役割はこれらを **共通の Atlas grammar** に包摂することであり、OQ-NT-8 はその境界を明示する。

---

## §8 Cascade phenomena

Failure modes は独立でなく、1 つの failure が他を誘発することがある。

### §8.1 C1 → C3 cascade ($Q_8$)

Mode A1 (quaternionic) → Mode C2 (Tier √): 
- $\rho$ quaternionic ⟹ Brauer factorization で $\rho^2$ のみ appear
- ⟹ $L(s, \rho)$ 単体の rational extraction 不可
- ⟹ Tier √ に落ちる

### §8.2 C1+C2 → C3 cascade ($S_4/V_4$)

Mode A2 (dim mismatch) → Mode B2 (intermediate stabilizer) → Mode C1 (Tier 3+):
- $[S_4:V_4] = 6$, no 6-dim irrep
- ⟹ $\mathrm{Ind}\chi$ reducible to $\rho_3 + \rho_3'$
- ⟹ $L(s, \chi) = L(s, \rho_3) \cdot L(s, \rho_3')$
- 各因子は Tier 1 (strict) で closure (要 case verification)
- ⟹ 全体として Tier 3 (positive-power rational combination)

**注**: $S_4/V_4$ が Tier 3 に落ちるか Tier √ に落ちるかは、$\rho_3$ と $\rho_3'$ の個別 closure status に依存する。v0.1 で詳細分析予定。

### §8.3 C2 → C3 (Mode B cascade)

Mode B (任意 sub-mode) → Mode C1 or higher: induction reducibility は必然的に multi-factor L, rational combination の階層を押し上げる。

### §8.4 C4 independence

Mode D は通常 C1-C3 から独立 (numerical obstruction)。ただし Mode D1 finite index correction は Mode C1 Tier 3+ 分析の一部として出現することがある。

---

## §9 Sub-hypotheses H-NT-8-*

| Sub-hypothesis | Content | Status | Next |
|---|---|---|---|
| **H-NT-8-A1** | $Q_8$ の 2-dim 既約 $\rho$ は quaternionic ($\nu = -1$)、Brauer shortcut 不成立 | **numerical witness (§5.2.1)** | sign resolution remains external |
| **H-NT-8-A2** | $S_4/V_4$ は Mode A2 (dim mismatch) + cascade to Tier 3 ($\rho_3 \cdot \rho_3'$ decomposition) | predicted (§3.2) | v0.1 で $\rho_3, \rho_3'$ の個別 tier 確定 |
| **H-NT-8-A3** | Complex irrep (Mode A3) の failure 例を specific group で同定 | not started | v0.1 で例探索 |
| **H-NT-8-B1** | $\chi$ extends ケースは Dirichlet case に帰着、Brauer shortcut not applicable | structural (§4.1) | v0 で complete |
| **H-NT-8-B2** | Intermediate stabilizer ($N \subsetneq G_\chi \subsetneq G$) は通常 Mode A2 と cascade | structural (§4.2) | v0.1 で $S_4$ 詳細 |
| **H-NT-8-C2** | **$Q_8$ は Tier √ with $k = 1$, $L(s, \rho)^2 = \zeta_H \zeta_\mathbb{Q}^2 / (\zeta_{F_i} \zeta_{F_j} \zeta_{F_k})$** | **numerical witness (§5.2.1): $L(0,\rho)^2=16$** | sign/phase resolution via root number |
| **H-NT-8-C3** | Tier ∞ (genuinely impossible) の例は存在するか? (tentative conjecture: 存在しない) | conjecture (§5.3) | v0.1+ で探索 |
| **H-NT-8-D1** | Mode D1 finite index correction の numerical example | not started | v0.1+ 要 Sage |
| **H-NT-8-D2** | Mode D2 rank-deficient example | not started | v0.1+ |

**Tier √ formal establishment (§5.2) が v0 の primary contribution**。$Q_8$ で $L(s, \rho)^2$ の explicit rational combination 式を導出し、**Tier √ obstruction を representation theory から数式レベルで formal 化**。

---

## §10 OQ-NT-7 ↔ OQ-NT-8 dual pair formal picture

### §10.1 Complete closure spectrum

```
              [ OQ-NT-7 success side ]       [ OQ-NT-8 failure side ]
              
             Tier 1      Tier 2      Tier 3+       Tier √      Tier ∞
            (strict)   (relaxed)   (multi-rat)   (sqrt only) (impossible)
               │          │           │              │            │
              S_3        D_4       S_4/V_4?         Q_8        (unknown?)
            A_4/V_4                (cascade)                    (conjecture
               │          │           │              │          empty)
               │          │           │              │            │
           ζ_F/ζ_Q  ζ_F1/ζ_F2  ∏ζ_Fi^ni      √(rational)      no power
               │          │           │              │            │
            h_F R_F   h_F1 R_F1/   multi reg       Tier 3          no
                     h_F2 R_F2    rational        + phase         shortcut
```

### §10.2 Formal relationship

- **Tier 1 ⊂ Tier 2 ⊂ Tier 3+ ⊂ Tier √**: 各 tier は前 tier を包含する (strict success ⟹ relaxed success ⟹ multi-rational success ⟹ sqrt-available)
- **Tier ∞**: 最後の failure tier、任意の power で rational 不可
- **OQ-NT-7** = {Tier 1, 2, 3+}: **rational combination 可能** の tier 全体
- **OQ-NT-8** = {Tier √, ∞}: **rational combination 不可** の tier
- **Tier √ は境界**: $L(s, \rho)^2$ が rational combination なので Tier 3+ に近いが、$L(s, \rho)$ 単体は OQ-NT-8 側

### §10.3 決定問題 (given $G, N, \chi$, どの tier?)

OQ-NT-7 + OQ-NT-8 は合わせて以下の決定手続を構成:

**0. Pre-check: scope applicability** (GPT-5.4 revision R1, 2026-04-10 external audit)

> Does $G$ have a nontrivial abelian normal subgroup $N \trianglelefteq G$?
> - **YES** → proceed to C1-C4 checks below
> - **NO** → output **"out of scope"** (framework not applicable)

**重要**: Groups without nontrivial abelian normal subgroups (e.g., non-abelian simple groups $A_5$, $PSL_2(p)$, sporadic simple groups) are **not classifiable** by this framework. They should NOT be forced into Tier ∞. Instead, the output is explicitly "framework not applicable — $G$ has no suitable $N$, alternative Stark methods required (direct Hecke L, modular forms, etc.)".

This distinction is critical: Tier ∞ means "$G$ has suitable $N$ but closure shortcut fails". "Out of scope" means "$G$ doesn't enter the framework at all".

1. **Check C1** (real irrep of dim $[G:N]$):
   - Yes → go to 2
   - No (quaternionic) → **Tier √** (Mode A1)
   - No (dim mismatch) → **Mode A2 cascade, check individual factors**
   - No (complex irrep) → **Mode A3 analysis**

2. **Check C2** (induction irreducible, Mackey):
   - Yes → go to 3
   - No (χ extends) → **Mode B1, Dirichlet case**
   - No (intermediate stab) → **Mode B2 cascade**

3. **Check C3** (zeta ratio reduction):
   - Strict ($\zeta_F/\zeta_\mathbb{Q}$) → **Tier 1** ✓ (OQ-NT-7)
   - Relaxed ($\zeta_{F_1}/\zeta_{F_2}$) → **Tier 2** ✓ (OQ-NT-7)
   - Multi-rational ($\prod \zeta_{F_i}^{n_i}$) → **Tier 3+** ✓ (OQ-NT-7)
   - Sqrt only ($L^{2k}$ rational) → **Tier √** (OQ-NT-8)
   - Nothing works → **Tier ∞** (OQ-NT-8, conjecture 空)

4. **Check C4** (unit lattice closure):
   - ✓ → Complete Stark formula
   - Finite index → Mode D1 correction
   - Rank deficient → Mode D2 fail

### §10.4 Algorithmic character of dual theory

OQ-NT-7 + OQ-NT-8 together は **algorithmic closure classifier**: 任意の有限 Galois 群と $N \trianglelefteq G$ について、character table + subgroup lattice のみから (1) どの tier に落ちるか (2) どの failure mode が発生するか を **計算可能** に決定する。

これは単なる分類表ではなく、**representation theory からの closure tier predictor** である。v0 の段階では $Q_8$ Tier √ formal が primary output、v0.1+ で algorithm の実装 (group → tier classification) と自動化 (GAP script 等) が次の課題。

---

## §11 Phase 5 5-criterion self-evaluation (audit-aware)

```yaml
phase5_output:
  id: brauer_closure_failure_taxonomy_v0
  type: classification (failure side, dual to OQ-NT-7)
  status: candidate (draft_v0, formal skeleton + Q_8 Tier √ structural)
  score:
    reproducibility: "+ (character theory + Brauer factorization + Mackey, standard finite group theory)"
    window_invariance: "+ (4 failure axes で taxonomy、具体例 Q_8 で formal verify)"
    error_reduction: "+ (Tier √ 概念が新規、Q_8 class の closure status を representation theory から予測)"
    compression: "+ (Tier 1,2,3+,√,∞ spectrum と C1-C4 failure axes の 2 軸 classification が unify)"
    causal: "- (数学的構造)"
    score_total: "4/5 (audit前 暫定, OQ-NT-7 と同様)"
    note: |
      OQ-NT-7 v0.2 と同じく、本 OQ-NT-8 v0 も実際に新 predictive content を生成
      (Q_8 Tier √ formal, cascade taxonomy, alternative method map)。H-stark-2
      の 'verification rich ≠ error_reduction boost' 教訓を超える level の
      predictive theory。ただし audit は v1 promotion 時に実施。
  depends_on:
    - OQ-NT-7 v0.2 (dual pair partner, strict/relaxed tier framework)
    - Brauer factorization (外部古典)
    - Frobenius-Schur indicator theory (外部古典)
  scope_constraints:
    - v0: formal skeleton + Q_8 Tier √ explicit, 他 mode は predicted/outline
    - 具体 alternative Stark method の数値実例は v0.1+
    - Tier ∞ の具体例は conjecture 空 (v0.1+ で反証 or 確認)
    - C4 Mode D は numerical 依存のため v0 では outline のみ
  collisions:
    aligns_with:
      - OQ-NT-7 v0.2 3-tier theory (direct complement)
      - external human audit Q6 promotion path (c) failure mode 体系化
    extends:
      - OQ-NT-7 Tier ∞ (単一 tier だったものを Tier √ / Tier ∞ に 2 分割)
      - H-stark-2 Atlas grammar (失敗側の結界線)
    independent_of:
      - H-stark-4 (w_K identification, 別軸)
      - composite_gauge_v0 (rule prototype, 別 layer)
  sub_hypotheses:
    H-NT-8-A1: "Q_8 quaternionic → Tier √"
               # numerical witness §5.2.1
    H-NT-8-A2: "S_4/V_4 dim mismatch → Tier 3 (multi-rational via ρ_3 + ρ_3')"
               # predicted, v0.1 詳細
    H-NT-8-A3: "complex irrep Mode, 具体例未確立"
               # v0.1+ 探索
    H-NT-8-B1: "χ extends → Dirichlet case (Brauer shortcut 対象外)"
               # structural verified §4.1
    H-NT-8-B2: "intermediate stabilizer → Mode A2 cascade"
               # structural (§4.2), 通常 cascading
    H-NT-8-C2: "Q_8 の L(s, ρ)² rational combination explicit formula"
               # numerical witness §5.2.1: L(0,ρ)^2 = 16
    H-NT-8-C3: "Tier ∞ genuinely impossible 例の存在 / 非存在"
               # tentative conjecture (Tier ∞ 空), v0.1+ 探索
    H-NT-8-D1: "Mode D1 finite index correction numerical example"
               # not started, v0.1+
    H-NT-8-D2: "Mode D2 rank deficient numerical example"
               # not started, v0.1+
  next_action: |
    1. v0.1: S_4/V_4 の Tier 3 cascade を ρ_3 / ρ_3' 個別分析で確定 (H-NT-8-A2)
    2. optional: Q_8 Tier √ の sign resolution を root number / 2nd Kronecker limit formula 経由で formal 化
    3. v0.3: Mode A3 complex irrep の具体例探索 (binary groups 等)
    4. v0.3: Tier ∞ 空 conjecture の検討 or 反例探索
    5. v1: full taxonomy + internal audit + external audit cycle → candidate+ promotion 候補 (OQ-NT-7 と同時)
  routing:
    requires_governance: false
    requires_internal_audit: true (v1 以降、本 v0 は draft)
    next_service: none
```

---

## §12 Open questions raised by this taxonomy

- **OQ-NT-8.1**: Tier √ の formal 境界 — $L^{2k}$ の最小 $k$ (quaternionic index) は representation theory から予測可能か? Conjecture: $k = 1$ 常に (i.e., $L^2$ で十分)、証明 or 反例。
- **OQ-NT-8.2**: Tier ∞ (genuinely impossible) の例の存在。Conjecture v0: 有限 Galois rank-1 abelian の場合 Tier ∞ は空 (全て Tier √ 以下)。証明 or 反例。
- **OQ-NT-8.3**: Mode A3 (complex irrep, $\nu = 0$) の典型例を non-trivial rank-1 Stark setup で同定。
- **OQ-NT-8.4**: Cascade phenomena の完全グラフ化。どの failure mode が他の mode を **必ず** 誘発するか、確率的か、独立か。
- **OQ-NT-8.5**: Alternative Stark methods (2nd Kronecker, modular forms, p-adic) の **ΣΦ Atlas grammar への包摂**。これは OQ-NT-6 (functor formalization) と直接関連。
- **OQ-NT-8.6**: Algorithm implementation (GAP / Sage script): given $G$, $N$, $\chi$ → output closure tier + failure mode。OQ-NT-7 + OQ-NT-8 の合成アルゴリズム化。
- **OQ-NT-8.7** ↔ **OQ-NT-7.4**: 4 conditions を満たす群クラス (OQ-NT-7.4) と failure mode 族 (OQ-NT-8) の完全列挙の可能性。Finite group classification と併用。

---

## §13 Conjecture v0 (failure side)

**Tier ∞ emptiness conjecture (tentative)**: 有限 Galois 群 $G$ の任意の rank-1 abelian Stark setup について、ある有限 $k \geq 1$ が存在して $L(s, \rho)^{2k}$ は intermediate field zeta 関数の rational combination として表現可能。特に Tier ∞ は空、全ての group は Tier 1, 2, 3+, √ のいずれかに落ちる。

**Motivation**: Brauer induction theorem により任意の Artin L-function $L(s, \rho)$ は monomial characters の L-function の rational combination で書ける。これが直接 Tier 3+ を保証しそうだが、monomial 分解における符号 (+1/-1 for virtual character) が Tier √ obstruction を生む可能性がある。

**Possible counterexamples**: "exotic" non-solvable groups (sporadic simple groups), wild ramification cases。v0.1+ で検討。

---

---

# §14 Attack 4 defense: Why Tier √ is NOT bookkeeping (v0.1)

**目的**: OQ-NT-7 v0.2.2 §13.6 で open として残した **Attack 4** ("Tier √ も Tier 2 のように unit residence 拡張で bookkeeping 化できるのでは") を **完全 close** する。OQ-NT-7 Tier 2 の sub-quotient defense (§13.5) と異なり、Tier √ の obstruction は **representation theory 由来の topological invariant** であり、任意の unit-group-based residence (sub-quotient, relative, S-unit, ...) で解決不可能であることを示す。

**Strategic motivation** (OQ-NT-7 v0.2.2 audit preparedness 完成への最終ピース): v0.2.2 で Attack 1-3 (Tate convention / Tier 2 bookkeeping / unit residence) が structural 解決したが、Attack 4 は OQ-NT-8 側 (Tier √) に委譲されていた。本 §14 で完全 defense を構築し、OQ-NT-7 + OQ-NT-8 dual pair の audit 耐性を総合的に完成させる。

## §14.1 Attack 4 content and Tier 2 analogy

### §14.1.1 Attack statement

> **Attack 4**: "OQ-NT-7 §13.5 で Tier 2 relaxed closure ($D_4$) は bookkeeping ではないと示された — Stark unit が sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ という standard algebraic K-theory object に住むという structural 差異が根拠だった。同じ論理で、Tier √ ($Q_8$) も Stark unit の residence を拡張すれば ($O_H^\times$ 全体、あるいは別の sub-quotient、あるいは higher-K-theory object) "strict" 化できるのでは? つまり Tier √ は単に `まだ発見されていない residence choice` の問題であり、本質的 failure ではなく bookkeeping に帰着できるのでは?"

### §14.1.2 なぜ Attack 4 が "深刻" に見えるか

Tier 2 defense (OQ-NT-7 §13.5) は以下の構造的論証に基づく:
- Sub-quotient unit group は Tier 1 unit group と **異なる代数的対象** (rank, torsion, universal property が異なる)
- Magnitude formula が genuine ratio ($h_{F_1} R_{F_1} / (h_{F_2} R_{F_2})$) で single product に還元不可

これらは **代数的対象の選択** に関する論証だった。Attack 4 は Tier √ にも同じ論理を適用し、"$Q_8$ の Stark unit の residence を正しく選べば同様に解ける" と主張する。

**もし Attack 4 が通ってしまうと**: Tier √ と Tier ∞ の区別が曖昧になり、OQ-NT-8 の "closure spectrum の dual pair" 構造が崩れる。failure taxonomy 全体が "未発見の residence 候補問題" に還元される恐れ。

### §14.1.3 Defense の方針

Attack 4 に対する defense は Tier 2 とは **構造的に異なる障害** を提示する必要がある。Tier 2 の sub-quotient は "代数的対象の選択" の問題だったが、Tier √ の quaternionic obstruction は **representation theory の topological invariant** に由来する:

- Frobenius-Schur indicator $\nu(\rho) = -1$ は $\rho$ の **topological / cohomological 不変量**
- Stark formula の pairing 構造 (log embedding) は **intrinsically orthogonal** (symmetric)
- Quaternionic $\rho$ は **symplectic** pairing を要求 — orthogonal と本質的に dual (Brauer group of $\mathbb{R}$ in degree 2)
- 任意の unit-group-based construction (sub-quotient, relative, S-unit, etc.) は all **orthogonal** 構造を持つ
- ⟹ bookkeeping of unit residence では **決して** quaternionic pairing を realize できない

以下の §14.2-§14.7 で 5 つの独立 structural arguments を提示する。

**L1 辞書基盤 (2026-04-10 追加)**: 以下 5 arguments の中核概念はすべて L1 辞書に residence を持つ:
- **Arg 1-2 (FS indicator, pairing type)**: nt_frobenius_schur.md §1-§3
- **Arg 3 (log embedding orthogonality)**: nt_relative_units.md §3.1 (log-embedding 定義) + nt_frobenius_schur.md §3.1 (intrinsic symmetry)
- **Arg 4 (sign ambiguity)**: nt_conductor.md §6.9.3 (Tier √ L-function 分解形)
- **Arg 5 (endomorphism algebra)**: nt_frobenius_schur.md §2.1 ($\mathrm{End}_{G,\mathbb{R}}(\rho) \cong \mathbb{R}/\mathbb{C}/\mathbb{H}$)

## §14.2 Argument 1: Frobenius-Schur indicator as topological invariant

### §14.2.1 Definition and properties

有限群 $G$ の複素既約表現 $\rho$ に対し、**Frobenius-Schur indicator** を:

$$\nu(\rho) := \frac{1}{|G|} \sum_{g \in G} \chi_\rho(g^2) \in \{+1, -1, 0\}$$

値の意味:
- $\nu = +1$: $\rho$ is **real (orthogonal)** — $\rho$ は $\mathbb{R}$ 上で realizable、$G$-invariant symmetric bilinear form を admits
- $\nu = -1$: $\rho$ is **quaternionic (symplectic)** — $\rho$ は $\mathbb{R}$ 上で realizable でない (but is self-dual)、$G$-invariant antisymmetric bilinear form を admits
- $\nu = 0$: $\rho$ is **complex** — $\rho \not\cong \bar\rho$、$G$-invariant bilinear form on $V$ 自体は存在しない

### §14.2.2 Topological invariance

$\nu(\rho)$ は以下の意味で **topological invariant**:

1. **$G$-isomorphism invariant**: $\rho \cong \rho'$ ならば $\nu(\rho) = \nu(\rho')$
2. **Base field independent** (at characteristic 0): $\nu$ は character table から決まり、基底体の選び方に依存しない
3. **Cohomology class**: $\nu(\rho) = -1$ は $\rho$ の Schur index が 2 であることに対応、$H^2(G, \mathbb{Z}/2)$ の非自明類として表現される
4. **Brauer group obstruction**: $\nu = -1$ は $\mathrm{End}_\mathbb{R}(\rho)$ が $\mathbb{H}$ (quaternions) であることを意味、$\mathbb{R}$ の Brauer group $\mathrm{Br}(\mathbb{R}) = \mathbb{Z}/2$ の非自明元

### §14.2.2.1 Q_8 non-dependency of Tier √ concept (audit revision 4, 2026-04-10)

**重要**: Tier √ concept は $Q_8$ に motivated された post-hoc category ではない。Frobenius-Schur indicator $\nu(\rho) \in \{+1, -1, 0\}$ は **representation theory の standard invariant** で、Schur (1905) 以来知られている。$\nu = -1$ (quaternionic) は representation の intrinsic property で、具体的 group $Q_8$ の存在に依存しない。

任意の有限群 $G$ で以下が存在する可能性がある:
- $\nu = +1$ irrep (orthogonal, Tier 1/2/3+ compatible)
- $\nu = -1$ irrep (quaternionic, **Tier √ tier に落ちる**)
- $\nu = 0$ irrep (complex, Mode A3)

これらの分類は **character table の計算から algorithmic に決定** される。$Q_8$ は "具体例" であって "motivation source" ではない: Tier √ category は $Q_8$ 以前に存在する representation-theoretic structure (symplectic vs orthogonal pairing の排他的二分法) から自然に出てくる。

**他の Tier √ candidates** (任意の例、future verification):
- Binary polyhedral groups ($2T, 2O, 2I$) の自然な spinor representations
- 任意の非 abelian $p$-group で quaternionic 2-dim irrep を持つもの
- Semidihedral groups $SD_{2^n}$ の特定の irreps

これらは全て $Q_8$ とは独立に Tier √ に分類される。Tier √ の definition は $\nu = -1$ という representation-theoretic 純粋条件であり、$Q_8$-specific な gerrymandering ではない。

### §14.2.3 $Q_8$ case explicit computation

$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$ (quaternion group of order 8)。

Conjugacy classes: $\{1\}, \{-1\}, \{\pm i\}, \{\pm j\}, \{\pm k\}$ with sizes $1, 1, 2, 2, 2$.

$Q_8$ has 5 irreducible representations: 4 of dimension 1 + 1 of dimension 2 (the $\rho$).

Character of $\rho$ (2-dim):
$$\chi_\rho(1) = 2, \quad \chi_\rho(-1) = -2, \quad \chi_\rho(\pm i) = \chi_\rho(\pm j) = \chi_\rho(\pm k) = 0$$

Squaring: $1^2 = 1$, $(-1)^2 = 1$, $(\pm i)^2 = -1$, $(\pm j)^2 = -1$, $(\pm k)^2 = -1$.

$$\nu(\rho) = \frac{1}{8} \left[ 1 \cdot \chi_\rho(1) + 1 \cdot \chi_\rho(1) + 2 \cdot \chi_\rho(-1) + 2 \cdot \chi_\rho(-1) + 2 \cdot \chi_\rho(-1) \right]$$

$$= \frac{1}{8} [2 + 2 - 4 - 4 - 4] = \frac{-8}{8} = \boxed{-1}$$

⟹ **$\rho$ is quaternionic**, confirmed.

### §14.2.4 Non-bookkeepable nature

**Key claim**: $\nu(\rho)$ は $\rho$ に intrinsic で、"Stark formula の書き方" や "unit residence の選択" で変更不可能。

**Proof sketch**: $\nu$ は character table のみから決まり、character table は $\rho$ の同値類の不変量。Stark formula の RHS は $\rho$ の character によって parametrize されるので、任意の Stark formula は $\nu$ の値を reflect せざるを得ない。

**結論**: Attack 4 が主張する "residence choice で Tier √ を解消" は、$\nu(\rho) = -1$ という topological invariant を "消す" ことを要求するが、これは不可能。

## §14.3 Argument 2: Pairing-type obstruction (orthogonal vs symplectic)

### §14.3.1 $G$-invariant bilinear forms on $\rho$

$\rho$ が irreducible complex representation で $\nu(\rho) \in \{\pm 1\}$ (i.e., self-dual) のとき、$\rho$ の representation space $V$ 上に **unique (up to scalar)** な $G$-invariant non-degenerate bilinear form $B : V \times V \to \mathbb{C}$ が存在する。

Form の対称性:
- $\nu(\rho) = +1$: $B(v, w) = B(w, v)$ (**symmetric**, orthogonal type)
- $\nu(\rho) = -1$: $B(v, w) = -B(w, v)$ (**antisymmetric**, symplectic type)

これは **排他的二者択一**: $\rho$ の $G$-invariant form は対称または反対称のいずれか (complex irrep では non-symmetric option は存在しない、Schur's lemma より)。

### §14.3.2 Stark formula と pairing type

Stark conjecture の RHS の構造:
$$\sum_{\sigma \in N} \chi^{-1}(\sigma) \log|\sigma \cdot \varepsilon_\chi|_w$$

これは **$\varepsilon_\chi$ と $\chi$ の間の "logarithmic pairing"** と見なせる。具体的には:

- $\varepsilon_\chi \in (O_?^\times \otimes \mathbb{Q})^{(\chi)}$ (χ-isotypic component of some unit module)
- $\chi \in \hat{N}$ (character group)
- Pairing: $\langle\varepsilon_\chi, \chi\rangle := \sum_\sigma \chi^{-1}(\sigma) \log|\sigma \varepsilon|_w$

この pairing は $\log|\cdot|$ を経由するため、**本質的に additive-real-valued and symmetric** (後述 §14.4)。

### §14.3.3 Symmetric pairing cannot realize symplectic invariant

Mathematical fact: A finite group representation $\rho$ with $\nu(\rho) = -1$ requires a **symplectic invariant form**. Any construction that produces a **symmetric pairing** (bilinear form) naturally on a module associated to $\rho$ **cannot capture the full invariant data** of $\rho$ — it can only capture the "$\rho \otimes \rho$ symmetric part" which is $\mathrm{Sym}^2(\rho)$, not $\rho$ itself.

**Consequence for Stark formula**: If the RHS pairing is symmetric (which log embedding ensures, §14.4), and $\rho$ is quaternionic (antisymmetric), then the Stark formula can only capture $\rho$-data up to a "squaring" — i.e., $L(s, \rho)^2$ is accessible but $L(s, \rho)$ itself is not.

This is exactly the **Tier √ phenomenon**: $L^2$ rational, $L$ requires a square root.

## §14.4 Argument 3: Log embedding is intrinsically orthogonal

### §14.4.1 Log embedding map

For a number field $F$ with archimedean places $v_1, \ldots, v_{r_1 + r_2}$ ($r_1$ real, $r_2$ complex), the log embedding is:
$$\lambda : O_F^\times / \mu(F) \to \mathbb{R}^{r_1 + r_2}$$
$$u \mapsto (\log|u|_{v_1}, \log|u|_{v_2}, \ldots)$$

Image is a rank-$(r_1 + r_2 - 1)$ lattice in the hyperplane $\{\sum x_i = 0\}$ (product formula).

### §14.4.2 Induced pairing is symmetric

The natural bilinear form on $\mathbb{R}^{r_1 + r_2}$ (where $\lambda$ lands) is the standard dot product:
$$\langle(x_1, \ldots), (y_1, \ldots)\rangle := \sum_i x_i y_i$$

This is **symmetric** ($\langle x, y\rangle = \langle y, x\rangle$). Hence the induced pairing on $O_F^\times / \mu(F)$ via $\lambda$ is also symmetric.

**Regulator** is the covolume of the unit lattice under this symmetric pairing — a well-defined positive real number.

### §14.4.3 Log embedding sub-quotients are also symmetric

For any sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ (Tier 2 case) or generalized S-unit group, the induced log embedding is **still symmetric** (it's the quotient of symmetric spaces by a symmetric sub-space, giving another symmetric space).

This means: **all unit-group-derived objects** inherit the symmetric pairing structure from $\log|\cdot|$. There is **no unit-group construction** that yields a symplectic/antisymmetric pairing.

### §14.4.4 Consequence for Tier √

If $\rho$ is quaternionic ($\nu = -1$, requiring symplectic pairing) and Stark formula uses log embedding (forcing symmetric pairing), there is a **fundamental type mismatch**. No choice of unit residence (absolute, relative, sub-quotient, S-unit, higher-rank, etc.) can bridge this gap, because all of these are symmetric.

⟹ **Attack 4 fails**: bookkeeping of unit residence cannot convert a symmetric pairing into a symplectic one.

## §14.5 Argument 4: Sub-quotient defense specifically fails for Tier √

### §14.5.1 Why Tier 2 sub-quotient defense works

For Tier 2 ($D_4$), the Stark unit lives in $O_{F_1}^\times / O_{F_2}^\times$. This sub-quotient has:
- Rank $r_{F_1} - r_{F_2}$
- Symmetric pairing inherited from log embedding
- χ-isotypic decomposition compatible with $\mathrm{Gal}(H/K)$ action

The $\rho$ for $D_4$ is **real** ($\nu(\rho) = +1$), so the required pairing is symmetric — **matching** the sub-quotient's inherited pairing. The defense works.

### §14.5.2 Why Tier √ sub-quotient defense fails

For Tier √ ($Q_8$), the $\rho$ is **quaternionic** ($\nu(\rho) = -1$), requiring symplectic pairing. Any sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ (or any other unit-group construction) inherits symmetric pairing from $\log|\cdot|$. **Type mismatch**.

Concretely: even if we could find a "clever" intermediate field pair $(F_1, F_2)$ for $Q_8$, the resulting sub-quotient would still have symmetric pairing. The Stark formula constructed from this sub-quotient would still only access $L(s, \rho)^2$ (the symmetric part), not $L(s, \rho)$.

### §14.5.3 No "symplectic sub-quotient" exists in unit-group world

**Claim**: There is **no standard construction** in algebraic number theory that produces a symplectic pairing from unit groups.

**Evidence**:
1. $O_F^\times$ with log pairing: symmetric
2. $O_{F, S}^\times$ (S-units): symmetric
3. $O_{F_1}^\times / O_{F_2}^\times$ (relative units): symmetric
4. $\mathrm{Cl}(F)$ (class group): no natural pairing (torsion group)
5. $\mathrm{Cl}(F_1) / \mathrm{Cl}(F_2)$ (relative class group): no pairing

**Higher algebraic K-theory objects** (where symplectic pairings CAN exist):
- $K_2(O_F)$: tame symbol / Hilbert symbol, which can be antisymmetric
- Selmer groups of motives: Weil pairings can be symplectic
- $H^1(\mathrm{Gal}, \mathrm{Br})$ etc.

These are **beyond standard unit group constructions** and require significant new machinery. Specifically, they move from "0-th K-theory" (unit groups) to "higher K-theory" (K_2 etc).

### §14.5.4 Hypothetical path (open problem)

**Could a higher-K-theory residence rescue Tier √?**

Hypothetically, the "Stark unit" for $Q_8$ quaternionic case might live in $K_2(O_H)$ or a related higher-K-theory object, where symplectic pairings are natural. This would be a **genuinely new mathematical construction**, not bookkeeping.

Status: **open question**, logged as OQ-NT-8.6 (updated from §12.11). This is NOT a resolution of Attack 4 at the sub-quotient level — it's a potential **alternative approach** that would REQUIRE NEW MACHINERY (not just residence choice).

**Important for audit defense**: Even if higher-K-theory eventually provides a residence for Tier √, this would still **not** validate Attack 4. Attack 4 claims that unit residence bookkeeping is sufficient; the potential K_2 solution uses **different mathematical objects** (K_2 ≠ unit groups) and **different pairing structures** (symplectic Hilbert symbol ≠ symmetric log embedding).

## §14.6 Argument 5: Square-root sign ambiguity

### §14.6.1 $L(s, \rho)^2$ vs $L(s, \rho)$

From OQ-NT-8 §5.2, for $Q_8$:
$$L(s, \rho)^2 = \frac{\zeta_H(s) \cdot \zeta_\mathbb{Q}(s)^2}{\zeta_{F_i}(s) \cdot \zeta_{F_j}(s) \cdot \zeta_{F_k}(s)}$$

This is a rational combination of field zetas (Tier 3 form). Taking square root:
$$L(s, \rho) = \pm \sqrt{\text{RHS}}$$

The sign $\pm$ is **not determined** by the rational combination. It's an **additional data point** that must come from outside.

### §14.6.2 Sources of the sign

Possible sources of the $L(s, \rho)$ sign (none are unit-group related):

1. **Functional equation root number** $W(\rho)$: $L(s, \rho)$ satisfies $\Lambda(s, \rho) = W(\rho) \Lambda(1-s, \bar\rho)$, where $W(\rho)$ is a complex number of absolute value 1. For self-dual $\rho$, $W(\rho) = \pm 1$. This sign determines the $L(s, \rho)$ sign.

2. **Modular form correspondence**: if $\rho$ is the Galois representation of a modular form $f$, then $L(s, \rho) = L(s, f)$ has sign determined by the Fourier coefficients of $f$.

3. **Period integrals**: for motives attached to $\rho$, the sign comes from period integrals over algebraic cycles.

4. **p-adic L-function specialization**: the sign can be encoded in p-adic analytic continuation.

**None of these** live in $O_H^\times$ or any sub-quotient. They are genuinely external to the unit group structure.

### §14.6.3 Consequence for Attack 4

Even if we could find a unit residence that gave $L(s, \rho)^2$ as a regulator of that residence, we would still need an **external input** to determine the sign. This external input is not "bookkeeping" — it's a **genuinely new piece of arithmetic data**.

⟹ Attack 4 fails again: the "bookkeeping" story is incomplete without sign information, which cannot come from unit residence.

## §14.7 Argument 6 (bonus): $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{H}$ vs $\mathbb{R}$

### §14.7.1 Endomorphism algebra

For irreducible complex representation $\rho$ of $G$, the $\mathbb{R}$-endomorphism algebra $\mathrm{End}_\mathbb{R}(\rho) := \mathrm{End}_G(\rho_\mathbb{R})$ (where $\rho_\mathbb{R}$ is the real form of $\rho$) is determined by $\nu$:

- $\nu = +1$ (real): $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{R}$
- $\nu = -1$ (quaternionic): $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{H}$ (quaternions)
- $\nu = 0$ (complex): $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{C}$

For $Q_8$'s 2-dim $\rho$: $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{H}$. The real form is 4-dimensional (doubled), not 2-dimensional.

### §14.7.2 Division algebra distinction

$\{\mathbb{R}, \mathbb{C}, \mathbb{H}\}$ are the three finite-dimensional real division algebras (Frobenius theorem). They are **genuinely distinct** objects — not equivalent up to convention, not one-obtainable-from-another by bookkeeping.

Tier 1 / Tier 2 Stark formula operates in $\mathbb{R}$ (real regulator values, symmetric pairing). Tier √ requires $\mathbb{H}$ (quaternionic invariant form). These are **different mathematical universes**.

### §14.7.3 Structural hierarchy of tiers

| Tier | $\nu(\rho)$ | $\mathrm{End}_\mathbb{R}(\rho)$ | Pairing type | Unit residence |
|---|---|---|---|---|
| Tier 1 strict | $+1$ | $\mathbb{R}$ | symmetric | $O_F^\times$ |
| Tier 2 relaxed | $+1$ | $\mathbb{R}$ | symmetric | $O_{F_1}^\times / O_{F_2}^\times$ |
| Tier 3+ multi | $+1$ | $\mathbb{R}$ | symmetric | multi-field virtual |
| **Tier √** | $-1$ | $\mathbb{H}$ | **symplectic** | **no unit-group residence** |
| Tier ∞ | N/A | N/A | N/A | N/A |

**Key observation**: Tier 1, 2, 3+ all have $\nu = +1$ and $\mathbb{R}$-endomorphism algebra, differing only in which unit-group-derived residence the Stark unit lives in. **Tier √ breaks this pattern** by requiring $\mathbb{H}$-endomorphism algebra, which no unit group provides.

## §14.8 Comparison table: Tier 1 / 2 / 3+ vs Tier √

| Feature | Tier 1 strict | Tier 2 relaxed | Tier 3+ | **Tier √** |
|---|---|---|---|---|
| $\nu(\rho)$ | $+1$ | $+1$ | $+1$ | **$-1$** |
| $\rho$ type | orthogonal | orthogonal | orthogonal | **quaternionic** |
| Invariant form | symmetric | symmetric | symmetric | **antisymmetric** |
| $\mathrm{End}_\mathbb{R}(\rho)$ | $\mathbb{R}$ | $\mathbb{R}$ | $\mathbb{R}$ | **$\mathbb{H}$** |
| Unit residence | $O_F^\times$ | $O_{F_1}^\times / O_{F_2}^\times$ | multi-field virtual | **no unit-group option** |
| Log embedding pairing | ✓ symmetric | ✓ symmetric | ✓ symmetric | **✗ type mismatch** |
| $L(s, \rho)$ directly accessible | ✓ | ✓ | ✓ | **✗ only $L^2$** |
| Sign/phase from within | ✓ | ✓ | ✓ | **✗ external** |
| bookkeeping defense possible? | (Tier 2 yes) | ✓ §13.5 | (Tier 3 pending) | **❌ no** |

The **horizontal lines** mark the boundary: Tier 1/2/3+ are all "orthogonal residence" variations, while Tier √ is in a different pairing-type category altogether.

## §14.9 Possible "higher-K-theory residence" for Tier √ (open, NOT resolution of Attack 4)

### §14.9.1 Hypothetical construction

If Tier √ ($Q_8$) could be "closed" via a new residence, it would likely use:

- **$K_2(O_H)$ with Hilbert symbol**: $K_2$ carries a natural **tame symbol** / **Hilbert symbol** which is antisymmetric. This matches the symplectic requirement of quaternionic $\rho$.
- **Étale cohomology classes**: $H^1_{et}(\mathrm{Gal}, \mathbb{Z}_\ell)$ or similar, with Weil pairings that can be symplectic.
- **Selmer groups**: $\mathrm{Sel}(\mathrm{motive})$ with generalized Weil pairings.

All of these are **higher K-theory / cohomology** objects, not unit groups.

### §14.9.2 Why this is NOT a rescue of Attack 4

Attack 4 asks whether **unit residence bookkeeping** can handle Tier √. The potential higher-K-theory solutions:

1. Use **different objects** (K_2, Selmer, cohomology) that are not unit groups
2. Require **new mathematical machinery** (Hilbert symbols, étale cohomology, motives)
3. Are **not bookkeeping** — they introduce genuinely new structures

If higher-K-theory rescues Tier √, it does so by **confirming** that Tier √ requires new machinery beyond unit groups — which is exactly the content of the non-bookkeeping defense.

### §14.9.3 Open question OQ-NT-8.6 (reformulated)

**OQ-NT-8.6 (updated)**: Is there a "higher-K-theory residence" (K_2, Selmer, cohomology) for Tier √ cases that provides a Stark-like formula for $L(s, \rho)$ (not just $L^2$)? If yes, this would:
- Extend ΣΦ Atlas grammar to higher-K-theory objects
- Not contradict the §14 defense (since K_2 ≠ unit groups)
- Be a major theoretical contribution (new closure tier? "Tier K_2"?)

This is beyond v0.1 scope; logged for future work.

## §14.10 Audit preparedness: final status (OQ-NT-7 + OQ-NT-8 combined)

### §14.10.1 All 4 attacks resolved

| Attack | Source | Defense location | Status |
|---|---|---|---|
| **1** ($D_4$ Tate convention $c$) | OQ-NT-7 §13.6.1 | §13.2.4 factor reconciliation | ✅ closed |
| **2** (Tier 2 bookkeeping) | OQ-NT-7 §13.6.2 | §13.5 5 structural arguments | ✅ closed |
| **3** (Stark unit residence ambiguous) | OQ-NT-7 §13.6.3 | §13.4.2 sub-quotient well-definedness | ✅ closed |
| **4** (Tier √ analogous bookkeeping) | OQ-NT-7 §13.6.4 | **OQ-NT-8 §14** (本 section) | ✅ **closed (v0.1)** |

### §14.10.2 5 independent structural arguments summary (Attack 4 defense)

| # | Argument | Structural content |
|---|---|---|
| 1 | Frobenius-Schur as topological invariant | $\nu(\rho) = -1$ は character table 由来、"書き方" で変更不可 |
| 2 | Pairing-type obstruction | Quaternionic $\rho$ requires symplectic form, orthogonal form only gives $\rho \otimes \rho$ symmetric part |
| 3 | Log embedding intrinsically symmetric | All unit-group constructions inherit symmetric pairing from $\log|\cdot|$ |
| 4 | Square-root sign ambiguity | $L(s, \rho)$ sign is external (functional equation root number etc.), not in unit groups |
| 5 | Endomorphism algebra $\mathbb{H}$ vs $\mathbb{R}$ | $\mathrm{End}_\mathbb{R}(\rho) = \mathbb{H}$ for Tier √, $\mathbb{R}$ for Tier 1/2/3+ — different division algebras |

**Independence**: Each argument rules out a different "bookkeeping escape route". Together they form an exhaustive defense against Attack 4.

### §14.10.3 Audit preparedness status (OQ-NT-7 + OQ-NT-8)

| Attack axis | Status |
|---|---|
| Normalization conventions (Tate vs $|N|$) | ✅ resolved at internal level |
| Tier 2 bookkeeping concern | ✅ resolved at internal level |
| Unit residence ambiguity | ✅ resolved at internal level |
| Tier √ bookkeeping concern | ✅ resolved at internal level (本 §14) |
| Numerical verification | ✅ Q_8 Tier √ witness completed via LMFDB field data; remaining broader checks need Sage/PARI |

**Overall status (post-audit revision 5, 2026-04-10)**: **audit preparedness at internal level complete, pending external validation**. 

**明示的 caveat**: 4 anticipated audit attacks + defenses は本 session 内で構築されたもので self-referential である可能性がある。真の audit validation は (a) internal audit (2026-04-10 `runtime/audits/2026-04-10_oq_nt_7_oq_nt_8_internal_audit.yaml`) → candidate maintained + path to candidate+, (b) external audit (human + external AI) → pending。External reviewers が本 §14 の 5 structural arguments と §13.5 の 5 arguments に agree するまで、"all attacks resolved" 主張は internal level に留まる。

Numerical verification gap is no longer total: the canonical $Q_8$ Tier √ obstruction now has an LMFDB-backed numerical witness. Remaining numerical work is broader coverage and optional root-number sign resolution, not the existence of the obstruction itself.

## §14.11 Status update: H-NT-8-A1 (quaternionic), H-NT-8-C2 ($Q_8$ Tier √), refined

### §14.11.1 H-NT-8-A1 refined

**Previous v0**: $Q_8$ quaternionic → Tier √, structural verified via Frobenius-Schur $\nu = -1$.

**Current v0.2**: **Plus** non-bookkeepability verified by both 5 independent structural arguments and the numerical witness $L(0,\rho)^2=16$, $L(0,\rho)=\pm4$ for LMFDB `8.0.12230590464.1`.

### §14.11.2 H-NT-8-C2 refined

**Previous v0**: $Q_8$ の $L(s, \rho)^2 = \zeta_H \zeta_\mathbb{Q}^2 / (\zeta_{F_i} \zeta_{F_j} \zeta_{F_k})$ explicit formula, structural verified.

**Current v0.2**: **Plus** the square-root sign ambiguity is now numerically visible: field data determine $L(0,\rho)^2=16$, but the unit/regulator package still determines only $L(0,\rho)=\pm4$. Sign must come from functional equation root number or modular forms, not unit groups.

### §14.11.3 Status ladder

OQ-NT-8 evolution:
- v0: Taxonomy skeleton + Tier √ refinement + $Q_8$ structural
- **v0.1 (本 update)**: Attack 4 complete defense + higher-K-theory open question + audit preparedness finalization
- **v0.2 (本 update)**: Q_8 Tier √ numerical witness from LMFDB field data; H-NT-8-A1/H-NT-8-C2 upgraded to numerical

## §14.12 Reformulated open question

**OQ-NT-8.6 (reformulated v0.1)**: "Higher-K-theory residence for Tier √":
- Can $K_2(O_H)$ with Hilbert symbol carry a Stark unit analogue for $Q_8$ quaternionic case?
- Can étale cohomology or Selmer groups provide a symplectic pairing that matches quaternionic $\rho$?
- If yes, does this give a "Tier K_2" in the closure spectrum, distinct from Tier 1/2/3+/√?
- If no, is there a proof obstruction (e.g., Galois cohomology computation showing $L(s, \rho)$ truly cannot be captured)?

Status: **open, future work**. Not required for audit defense (which operates at the sub-quotient unit residence level).

---

*v0.1 update: 2026-04-10. §14 Attack 4 defense 追加 (~350 行). 5 structural arguments that Tier √ is NOT bookkeeping: Frobenius-Schur topological invariant, pairing-type obstruction, log embedding symmetry, square-root sign ambiguity, endomorphism algebra $\mathbb{H}$ vs $\mathbb{R}$. Higher-K-theory residence logged as open question. Audit preparedness for OQ-NT-7 + OQ-NT-8 dual pair finalized.*

---

## §15 一行要約 (v0.2 update)

> **Brauer/induction closure shortcut の failure side は C1-C4 4 axes + Tier √ / Tier ∞ で分類され、$Q_8$ が Mode A1 quaternionic → Tier √ の canonical example。v0.1 で Attack 4 (Tier √ bookkeeping) は Frobenius-Schur / pairing type / log embedding / sign ambiguity / endomorphism algebra の 5 structural arguments で defend され、v0.2 で LMFDB `8.0.12230590464.1` により $L(0,\rho)^2=16$, $L(0,\rho)=\pm4$ が数値検証された。したがって Tier √ obstruction は categorical claim ではなく、unit/regulator data が square まで決めて sign を決めないという数値現象として確認済み。**

---

*作成: 2026-04-10 (v0 draft). OQ-NT-7 v0.2 の dual pair partner として新規 research note。v0.1 update 同日: §14 Attack 4 defense (Tier √ non-bookkeeping) 追加, audit preparedness finalization。v0.2 update 同日: Q_8 Tier √ numerical witness 追加。*
*次トリガー: A_4 numerical lookup / optional Q_8 root-number sign resolution / v1 full taxonomy + audit cycle (OQ-NT-7 v1 + OQ-NT-8 v1 同時 internal audit → external audit → candidate+ promotion)*
