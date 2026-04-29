---
axis: A
position: algebra_group
static_dynamic: static
connected_to:
  - A.algebra_analysis
  - A.algebra_constraint
  - A.harmonic_analysis
  - L.number_theory
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-10
runtime_summary:
  what: Relative units, norm-one lattice, relative regulator. Tier 2 Stark の数論的基盤。O_{F_1}^× / O_{F_2}^× (sub-quotient unit group) と norm-one sublattice N^1_{F_1/F_2} の定義・関係・住処
  when: Tier 2 relaxed Stark closure / sub-quotient unit residence / regulator ratio / D_4 Stark normalization / relative unit vs quotient unit の区別
  provides: [relative_unit_group, norm_one_lattice, relative_regulator, sub_quotient_unit, regulator_ratio, unit_rank_arithmetic]
  consumes: [nt_conductor.md §6, c_spectral.md §8, number_theory_dictionary_v0.md §6.2]
  axis: [A]
  residual_types: [R-gauge]
  key_theorems:
    - {id: rel_unit_rank, statement: "rank(O_{F_1}^×) - rank(O_{F_2}^×) = rank of relative unit lattice", derived_in: "§2.3", status: established}
    - {id: regulator_ratio, statement: "R_{rel} = R_{F_1} / R_{F_2} (up to rational factor from index)", derived_in: "§3.2", status: established}
  cost: small
  status: established
  one_screen: |
    §1 Relative units = O_{F_1}^× ∩ ker(N_{F_1/F_2}): units of F_1 whose norm to F_2 is a root of unity.
    §2 Sub-quotient unit group O_{F_1}^× / O_{F_2}^× = Tier 2 Stark unit residence (OQ-NT-7 §13).
       rank = r_{F_1} - r_{F_2} (Dirichlet rank difference). isotypic complement of trivial component.
    §3 Relative regulator R_rel = covolume of relative unit lattice in log-embedding.
       R_rel = R_{F_1}/R_{F_2} × [index correction]. Tier 2 Stark formula magnitude.
    §4 Norm-one lattice N^1 ⊂ O_{F_1}^× vs sub-quotient: 同じ rank, finite index 差.
       N^1 is intrinsic (kernel of norm map). Sub-quotient depends on embedding F_2 ↪ F_1.
    §5 Bridge to Tier theory: Tier 1 uses O_F^×, Tier 2 uses O_{F_1}^×/O_{F_2}^×,
       Tier 3+ uses virtual multi-field combination. Same rank arithmetic, increasing structural complexity.
---

# Relative Units and Relative Regulator

**Level**: L1 (pure mathematics, domain-independent)
**Dependencies**: number_theory_dictionary_v0.md §6.2 (regulator R_K), nt_conductor.md §6 (Artin conductor), c_spectral.md §8 (class number formula)
**Downstream**: research/brauer_closure_galois_classification_v0.md §12-13 (Tier 2 Stark), number_theory_dictionary_v0.md §8 OQ-NT-7

---

## §1 Definitions

### §1.1 Setting

$F_2 \subset F_1$ は数体の拡大 ($F_2$ は部分体)。典型的状況: Galois 拡大 $H/\mathbb{Q}$ の中間体 tower $\mathbb{Q} \subset F_2 \subset F_1 \subset H$。

記号:
- $O_{F_i}^\times$ = $F_i$ の整数環の単数群
- $\mu(F_i)$ = $F_i$ の roots of unity
- $r_{F_i} = r_1(F_i) + r_2(F_i) - 1$ = Dirichlet unit rank (identity_asymmetry.md §3.4 由来の "$-1$")
- $N_{F_1/F_2} : F_1^\times \to F_2^\times$ = norm 写像

### §1.2 Norm-one units (relative units, strict sense)

$$O_{F_1}^{\times, N=1} := \ker\bigl(N_{F_1/F_2} : O_{F_1}^\times \to O_{F_2}^\times\bigr)$$

元 $u \in O_{F_1}^\times$ で $N_{F_1/F_2}(u) \in \mu(F_2)$ を満たすもの。norm が root of unity になる単数全体。

**注意**: 厳密には $\ker(N) = \{u : N(u) = 1\}$ だが、unit group では $N(u) \in O_{F_2}^\times$ が自動で、$N(u) \in \mu(F_2)$ と $N(u) = 1$ の差は有限 (Hilbert 90 経由)。辞書では $N(u) \in \mu(F_2)$ の広い定義を norm-one lattice、$N(u) = 1$ の狭い定義を strict norm-one と呼ぶ。両者の index は $|\mu(F_2)|$ で有限。

### §1.3 Sub-quotient unit group

$$O_{F_1}^\times / O_{F_2}^\times$$

$F_2 \subset F_1$ の inclusion が $O_{F_2}^\times \hookrightarrow O_{F_1}^\times$ を誘導する。この商が **sub-quotient unit group**。

**OQ-NT-7 §13 との接続**: Tier 2 relaxed Stark の unit residence は $O_{F_1}^\times / O_{F_2}^\times$ である (research/brauer_closure_galois_classification_v0.md §13.4)。GPT-5.4 revision R3 で classical relative units との関係が明示された。

### §1.4 Norm-one vs sub-quotient の関係

**定理 (Herbrand quotient の系)**: $O_{F_1}^{\times, N=1}$ と $O_{F_1}^\times / O_{F_2}^\times$ は

- **同じ rank** を持つ (§2.3 参照)
- **有限 index 差** のみ異なる

理由: norm 写像の exact sequence $1 \to \ker N \to O_{F_1}^\times \xrightarrow{N} N(O_{F_1}^\times) \to 1$ と $O_{F_2}^\times \hookrightarrow O_{F_1}^\times$ の cokernel を比較する。$N(O_{F_1}^\times) \cap O_{F_2}^\times$ が有限 index で $O_{F_2}^\times$ に収まるため、kernel と cokernel の $\mathbb{Z}$-rank は一致。

**辞書的に重要な区別**:

| 性質 | Norm-one $O_{F_1}^{\times, N=1}$ | Sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ |
|---|---|---|
| 定義 | $\ker(N_{F_1/F_2})$ (intrinsic) | image of quotient map (embedding-dependent) |
| Galois 作用 | $N$-compatible | $\mathrm{Gal}(F_1/F_2)$ acts naturally |
| Stark unit residence | classical formulation | Tier 2 formulation (OQ-NT-7 §13) |
| K-theory 視点 | $K_1$-theoretic kernel | $K_1$ relative group |
| 計算容易性 | norm 条件 check | quotient computation |

**実用**: Tier 2 Stark では sub-quotient が自然 (Stark formula の RHS が quotient structure を持つため)。Classical number theory では norm-one が自然 (Hilbert 90, Hasse norm theorem との接続)。両者は有限 index で同じ lattice を記述する。

---

## §2 Rank Arithmetic

### §2.1 Dirichlet unit theorem の復習

数体 $K$ に対し:

$$O_K^\times \cong \mu(K) \times \mathbb{Z}^{r_K}, \quad r_K = r_1(K) + r_2(K) - 1$$

ここで $r_1$ = real embedding 数、$r_2$ = complex conjugate pair 数、$[K:\mathbb{Q}] = r_1 + 2r_2$。

### §2.2 拡大 $F_2 \subset F_1$ の rank 差

$$r_{\mathrm{rel}} := r_{F_1} - r_{F_2}$$

これが relative unit lattice の rank。

### §2.3 例

| $F_2 \subset F_1$ | $(r_1, r_2)_{F_2}$ | $(r_1, r_2)_{F_1}$ | $r_{F_2}$ | $r_{F_1}$ | $r_{\mathrm{rel}}$ |
|---|---|---|---|---|---|
| $\mathbb{Q} \subset \mathbb{Q}(\alpha)$ (cubic, 1 real) | (1,0) | (1,1) | 0 | 1 | **1** |
| $\mathbb{Q} \subset \mathbb{Q}(\sqrt{5})$ (real quad) | (1,0) | (2,0) | 0 | 1 | **1** |
| $\mathbb{Q}(\sqrt{2}) \subset \mathbb{Q}(\sqrt{2}, \sqrt{-7})$ | (2,0) | (0,2) | 1 | 1 | **0** |
| $\mathbb{Q} \subset \mathbb{Q}(\zeta_5)$ (cyclotomic 4th) | (1,0) | (0,2) | 0 | 1 | **1** |
| $\mathbb{Q}(\sqrt{2}) \subset F_1$ ($D_4$ 例, OQ-NT-7 §12) | (2,0) | depends | 1 | depends | **$r_{F_1} - 1$** |

**Tier 理論との接続** (research/brauer_closure_galois_classification_v0.md):
- **Tier 1**: $F_2 = \mathbb{Q}$, $r_{\mathrm{rel}} = r_{F_1}$. Stark unit は $O_{F_1}^\times$ 全体に住む。
- **Tier 2**: $F_2 \neq \mathbb{Q}$, $r_{\mathrm{rel}} = r_{F_1} - r_{F_2} \geq 1$. Stark unit は $O_{F_1}^\times / O_{F_2}^\times$ に住む。
- **Tier 3+**: virtual combination. 単一の $r_{\mathrm{rel}}$ では記述不完全。

### §2.4 Rank 公式の由来

$F_1/F_2$ が Galois (cyclic of prime degree $p$) のとき:

$$r_{F_1} = p \cdot r_{F_2} + (\text{signature change from ramification})$$

$\mathbb{Q}$ 上の degree $n$ 体では $r = r_1 + r_2 - 1$ で、$r_1 + 2r_2 = n$。拡大での signature 変化は ramification (real place が complex に変わる) に完全支配される。

---

## §3 Relative Regulator

### §3.1 Log-embedding

Dirichlet の log-embedding $\lambda : O_K^\times \to \mathbb{R}^{r_1 + r_2}$:

$$\lambda(u) = (d_v \log|u|_v)_{v \in S_\infty \setminus \{v_0\}}$$

ここで $d_v = 1$ (real place), $d_v = 2$ (complex place), $v_0$ は product formula で除く place。

### §3.2 Relative regulator の定義

$\varepsilon_1, \ldots, \varepsilon_{r_{\mathrm{rel}}}$ を relative unit lattice ($O_{F_1}^{\times, N=1}$ mod torsion) の基底とする。

$$R_{\mathrm{rel}} := |\det(\lambda(\varepsilon_i) \text{ projected to relative subspace})|$$

**$R_{F_1} / R_{F_2}$ との関係**: class number formula の factorization

$$\frac{\zeta_{F_1}(s)}{\zeta_{F_2}(s)} \sim \frac{h_{F_1} R_{F_1} / w_{F_1}}{h_{F_2} R_{F_2} / w_{F_2}} \cdot (\text{analytic factors})$$

から、Tier 2 Stark formula の magnitude は

$$R_{\mathrm{rel}} = \frac{R_{F_1}}{R_{F_2}} \cdot \frac{1}{[O_{F_1}^\times : O_{F_2}^\times \cdot O_{F_1}^{\times, N=1}]}$$

index 因子は有限 (§1.4)。$h_{F_1} = h_{F_2} = 1$ の best case で:

$$R_{\mathrm{rel}} = \frac{R_{F_1}}{R_{F_2}}$$

これが OQ-NT-7 §12 の $D_4$ Stark formula の RHS magnitude ($R_{F_1}/R_{F_2}$) の根拠。

### §3.3 例: ℚ(√−23) ケースの再解釈

number_theory_dictionary_v0.md §5.3 のケース:
- $F_2 = \mathbb{Q}$, $F_1 = \mathbb{Q}(\alpha)$ (cubic, plastic constant)
- $r_{F_2} = 0$, $r_{F_1} = 1$, $r_{\mathrm{rel}} = 1$
- $R_{F_1} = \log|\alpha_1|$, $R_{F_2} = 1$ (convention)
- $R_{\mathrm{rel}} = \log|\alpha_1| \approx 0.28122$

これは Tier 1 strict ($F_2 = \mathbb{Q}$) なので relative regulator は absolute regulator と一致。

### §3.4 例: $D_4$ ケースの展望 (OQ-NT-7 §12 参照)

$K = \mathbb{Q}(\sqrt{-14})$, $\mathrm{Gal}(H/\mathbb{Q}) = D_4$ のとき:
- $F_2 = \mathbb{Q}(\sqrt{2})$ (real quadratic, $r_{F_2} = 1$)
- $F_1 =$ degree-4 intermediate field ($r_{F_1} \geq 2$)
- $r_{\mathrm{rel}} = r_{F_1} - 1 \geq 1$
- $R_{\mathrm{rel}} = R_{F_1} / R_{F_2}$ (Tier 2 relaxed)

これが Tier 1 と Tier 2 の構造的差異の源: Tier 1 は $R_{F_1}$ 単独、Tier 2 は **ratio**。ratio は 2 体の unit group を同時に要求し、"bookkeeping" ではない独立情報を含む。

---

## §4 Isotypic 分解との関係

### §4.1 $G$-module 構造

$H/k$ が Galois, $G = \mathrm{Gal}(H/k)$, $N \trianglelefteq G$ with $F_1 = H^N$。$G/N$ が $O_{F_1}^\times \otimes \mathbb{Q}$ に作用。

Dirichlet unit theorem の $\mathbb{Q}[G/N]$-module 版:

$$O_{F_1}^\times \otimes \mathbb{Q} \cong \bigoplus_{\chi \in \widehat{G/N}} V_\chi^{m_\chi}$$

ここで $V_\chi$ は $\chi$ に対応する irreducible $\mathbb{Q}[G/N]$-module、$m_\chi$ は multiplicity (Stark regulator matrix 由来)。

### §4.2 Trivial isotype = $O_{F_2}^\times \otimes \mathbb{Q}$

$\chi = \chi_0$ (trivial character of $G/N$) の isotype は $(G/N)$-invariant 部分:

$$(O_{F_1}^\times \otimes \mathbb{Q})^{G/N} = O_{F_2}^\times \otimes \mathbb{Q}$$

よって sub-quotient $O_{F_1}^\times / O_{F_2}^\times$ は **非自明 isotype の直和** (mod torsion)。

### §4.3 χ-isotype と Stark unit

Rank-1 abelian Stark: 非自明 character $\chi$ に対して $\chi$-isotype が 1 次元 ⟹ その生成元 $\varepsilon_\chi$ が Stark unit。

- **Tier 1**: 非自明 isotype 全体が $O_{F_1}^\times$ 内で trivial isotype と直和
- **Tier 2**: 非自明 isotype は $O_{F_1}^\times / O_{F_2}^\times$ に住む。trivial 成分を quotient で除去。
- isotypic projection $e_\chi = \frac{1}{|G/N|} \sum_{\sigma \in G/N} \chi^{-1}(\sigma) \sigma$ が射影子

**number_theory_dictionary_v0.md §5.3.6 の再解釈**: ℚ(√−23) の $O_H^\times \otimes \mathbb{C}$ の $A_3$-isotypic 分解で、trivial 成分 = 0 (虚二次, $r_K = 0$)、$\chi$-成分 = 1-dim、$\bar\chi$-成分 = 1-dim、合計 rank 2 = $r_H$。§5.3.7 の projection $P_\chi(v(\alpha))_0 = 0.2812 \neq 0$ は $\alpha$ が $\chi$-isotype に非自明成分を持つことの数値確認。

---

## §5 Scope と他辞書との接続

### §5.1 本エントリが提供するもの

- Norm-one units, sub-quotient units の定義と関係 (§1)
- Rank arithmetic: $r_{\mathrm{rel}} = r_{F_1} - r_{F_2}$ (§2)
- Relative regulator の定義と $R_{F_1}/R_{F_2}$ との関係 (§3)
- Isotypic 分解との接続、$e_\chi$ 射影子 (§4)

### §5.2 本エントリが提供しないもの (scope 外)

- Stark conjecture 本体 → research/stark_projection_v0.md
- Tier 理論の全体像 → research/brauer_closure_galois_classification_v0.md
- Frobenius-Schur indicator と quaternionic obstruction → nt_frobenius_schur.md
- 具体数体の unit group 計算値 → number_theory_dictionary_v0.md §5-6
- K-theory 的解釈の深化 ($K_2$ 以上) → OQ-NT-8 §14.9 (open)

### §5.3 他辞書接続

| 接続先 | 接続点 | 方向 |
|---|---|---|
| nt_conductor.md §6 | Artin conductor → norm map の ramification 依存性 | upstream |
| c_spectral.md §8 | class number formula → regulator 因子の分母 | upstream |
| number_theory_dictionary_v0.md §6.2 | R_K 定義 → R_rel の特殊化 | downstream |
| number_theory_dictionary_v0.md §5.3 | ℚ(√−23) の isotypic 分解の再解釈 | downstream |
| research/brauer_closure_galois_classification_v0.md §12-13 | Tier 2 Stark unit residence | downstream |
| nt_frobenius_schur.md | pairing type → norm-one lattice が orthogonal pairing を持つ理由 | lateral |

---

*作成日: 2026-04-10*
*作成トリガー: OQ-NT-7 external audit (GPT-5.4 R3/R4) で relative unit / sub-quotient の辞書不在が指摘。Tier 2 安定化のための L1 基盤。*
