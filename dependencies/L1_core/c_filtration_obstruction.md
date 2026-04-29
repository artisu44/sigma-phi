---
axis: [A, E]
position: L1_filtration_obstruction
static_dynamic: static
connected_to:
  - L0_canon/finite_observation.md               # A0 (S,W,m), Arrow 1
  - L1_mathematical/core/c_arrow_obstruction.md   # §10 T-AAS (ker_gauge+ker_topo), §6 gauge wall
  - L1_mathematical/core/c_hidden_degrees_of_freedom.md  # R-topo 型定義
  - L1_mathematical/core/c_phase_complex.md       # §4 structural root, ι_L
  - L1_mathematical/core/c_boundary_invariants.md # discrete invariant taxonomy
  - L1_mathematical/core/c_spectral.md            # S7 class number formula
  - L1_mathematical/number_theory/nt_conductor.md # §6 ramification hierarchy, S8
  - L1_mathematical/number_theory/nt_frobenius_schur.md  # pairing obstruction (Tier sqrt), nu trichotomy
  - L1_mathematical/number_theory/nt_root_numbers.md     # S11 sign channel, W(rho) constraint
  - L1_mathematical/number_theory/nt_dedekind_artin_zeta.md  # S9 Artin factorization, zeta-depth bridge
  - L1_mathematical/quantum/q_gauge_field_theory.md      # confinement = gauge singlet 制約
  - research/hodge_conjecture_decomposition_v0.md # §13-§16, §26 full analysis
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-12
runtime_summary:
  what: ker_topo の幾何学的根拠 — Hodge filtration + Griffiths transversality が多段障害を生む原理
  when: Arrow 1 kernel の R-topo 側の起源、f_rational の幾何的意味、Tier 2 障害の構造を問うとき
  provides: [hodge_filtration_formal, griffiths_transversality, multi_step_obstruction_principle, abel_jacobi_intermediate, griffiths_group, ker_topo_hom_surj_decomposition, filtration_depth_conductor, tier_filtration_correspondence, dim_dependent_ker_topo_components, wildness_depth, codim_visibility_decay, zeta_depth_correspondence, sign_channel_collapse]
  consumes: [c_arrow_obstruction.md §10 T-AAS, c_hidden_degrees_of_freedom.md R-topo, nt_conductor.md §6, finite_observation.md A0]
  axis: [A, E]
  residual_types: [R-topo-hom, R-topo-surj]
  cost: medium
  status: established
  one_screen: |
    Hodge filtration: F^n ⊂ F^{n-1} ⊂ ... ⊂ F^0 = H^n(X,C)。codim p の代数的起源 ⟹ F^p に住む
    Griffiths transversality: ∇(F^p) ⊂ F^{p-1} ⊗ Ω¹。filtration を 1段ずつしか跨げない
    多段障害原理: codim p は p 段の filtration jump を要求 → 各段に kernel 発生の余地
    p=1: 1段 → 指数列で closure (Lefschetz 1,1) → ker_topo = 0
    p≥2: 多段 → Griffiths 群 ≠ 0、Mumford 無限次元 → ker_topo 存在
    ker_topo 2成分: hom (Griffiths群, Hdg交差=自動0) + non-surj (cl⊗Q非全射, f_rational の源)
    T-AAS §10 根拠: ker_topo = 多段 filtration 障害の空間、f_rational = dim(ker_topo^{non-surj} ∩ Hdg^p)
    Hodge conjecture = ker_topo^{non-surj} ∩ Hdg^p(X,Q) = 0 (全既知例で成立、反例未発見)
---

# Filtration Obstruction — ker_topo の幾何学的根拠

**Level**: L1 (横断原理、domain-independent 構造を幾何的に具体化)
**Role**: T-AAS (§10 of c_arrow_obstruction.md) の ker_topo 側に、
Hodge filtration と Griffiths transversality による幾何学的基盤を与える

---

## §1 動機

T-AAS は ker(phi) = ker_gauge + ker_topo を宣言し、
ker_gauge (離散 torsion 障害) は §10.4 で R-gauge 型として完全に位置づけられた。
しかし ker_topo の **内部構造** — なぜ gauge で消えないのか、
なぜ多段合成で生じるのか — は c_arrow_obstruction.md に記述がない。

本エントリは HC-1a tier 表 (research/hodge_conjecture_decomposition_v0.md §13.1b) を
seed として、ker_topo の幾何学的起源を L1 レベルで定式化する。

**投入根拠** (4-axis): (1) T-AAS の片翼が未根拠 = research 不安定点直撃,
(2) Hodge filtration は既存理論の再配置で L1 落とし可能,
(3) f_rational の幾何的意味が明示されれば reviewer 負荷低減,
(4) ker_gauge/ker_topo の非対称構造が骨格補強。Score: 4/4。

---

## §2 Hodge Filtration — 形式的定義

### §2.1 Hodge 分解

X を C 上の滑らかな射影多様体 (dim = n) とする。

```
H^k(X, C) = bigoplus_{p+q=k} H^{p,q}(X)
```

H^{p,q} は (p,q)-形式の空間。conjugation: H^{p,q} = conj(H^{q,p})。

### §2.2 Hodge filtration

```
F^p H^k(X, C) = bigoplus_{i >= p} H^{i, k-i}(X)
```

降鎖: F^k ⊂ F^{k-1} ⊂ ... ⊂ F^1 ⊂ F^0 = H^k(X, C)。

**ΣΦ 読み**: F^p は「codim p 以上の精度を持つ構造成分」。
窓 W が見える精度に階層がある。p が大きいほど deeper structure。

### §2.3 代数的サイクルの filtration 位置

codim p の代数的サイクル Z の cycle class cl(Z) は:

```
cl(Z) in F^p H^{2p}(X, C) ∩ conj(F^p H^{2p}(X, C)) = H^{p,p}(X)
```

**核心**: 代数的起源を持つクラスは F^p に住む。
Hodge 予想は逆 — F^p ∩ conj(F^p) ∩ H^{2p}(X, Q) の全元が代数的起源を持つか。

---

## §3 Griffiths Transversality — 1段制約

### §3.1 定義

X が族 {X_t} の一員として変形するとき、Gauss-Manin 接続 nabla に対して:

```
nabla(F^p) ⊂ F^{p-1} ⊗ Omega^1
```

**filtration は 1段ずつしか跨げない**。

### §3.2 ΣΦ 翻訳

Griffiths transversality は Arrow 1 map phi: Structural -> Scan に対する
**帯域制約 (bandwidth constraint)** である:

| 物理的比喩 | Griffiths 対応 |
|---|---|
| 信号が 1 octave/step しか変化できない | nabla(F^p) ⊂ F^{p-1} |
| p octave の変化には p step 必要 | codim p = p 段の filtration jump |
| 各 step で情報が漏れ得る | 各段の kernel が ker_topo に寄与 |

### §3.3 conductor 言語との接続

nt_conductor.md §6 の ramification 階層:

| Ramification | conductor f_p | Hodge 対応 | 障害 |
|---|---|---|---|
| unramified (codim 0) | 0 | Tier 0: H^{0,0}, H^{n,n} | なし (identity) |
| tame (codim 1) | codim(V^{I_0}) | Tier 1: H^{1,1}, Lefschetz | 1段 → closure |
| wild (codim >= 2) | Sum(|I_i|/|I_0|)·codim | Tier 2: H^{p,p}, p >= 2 | 多段 → open |

**S8 の Hodge 版**: Hodge conductor = Sum_{k=0}^{p-1} codim(F^{p-k}/F^{p-k+1})。
tame (p=1) は Lefschetz で閉じる。wild (p >= 2) は closure 未確定。

---

## §4 多段障害原理 — なぜ p >= 2 で ker_topo が生じるか

### §4.1 p = 1: 1段 closure

```
0 -> Z -> O_X -> O_X* -> 0   (指数完全列)
```

接続準同型 delta: H^1(X, O*) -> H^2(X, Z) が cycle class map。
Lefschetz (1,1): delta の像 tensor Q = H^{1,1} ∩ H^2(X, Q)。

**1段の準同型で代数側と解析側が一致する**。filtration jump = 1。
ker_topo(p=1) = 0。

### §4.2 p >= 2: 多段合成

codim p の cycle class map は **p 段の合成構造** を持つ:

```
phi = phi_p ∘ phi_{p-1} ∘ ... ∘ phi_1

phi_k: F^k / F^{k+1} → F^{k-1} / F^k   (Griffiths 1段)
```

各 phi_k に独立な kernel が生じ得る:

```
ker_topo = Sum_{k=1}^{p} ker(phi_k)   (filtration grading ごとの寄与)
```

**p = 1**: 合成は trivial (1段) → kernel 発生の余地なし → Lefschetz で closure
**p = 2**: 2段合成 → 中間の ker(phi_1) or ker(phi_2) が非自明化し得る
**p >> 1**: 多段合成 → 各段の kernel が蓄積 → 指数的に見えにくくなる

### §4.3 Abel-Jacobi map — 中間層の証拠

```
          cl                    AJ
Z^p(X) ────→ H^{2p}(X,Z)    CH^p(X)_hom ────→ J^p(X)
  |               |              |                 |
Structural    Scan∩Struct    Structural(mod~)    中間 Jacobian
```

| | p = 1 | p >= 2 |
|---|---|---|
| 中間 Jacobian | J^1(X) = Alb(X) | J^p(X) (一般) |
| AJ | 全射 (古典) | 全射とは限らない |
| Griffiths 群 | 0 (自明) | 一般に ≠ 0 |
| ΣΦ window | W = 1段 (十分) | W = p 段 (不足する場合あり) |

**Griffiths 群 Gr^p(X) = CH^p_hom(X) / CH^p_alg(X)**:
AJ でも検出できないが零でない cycle 類。
ker_topo の直接的存在証拠。

### §4.4 ker_topo の 2 成分分解

**重要な構造的事実**: Griffiths 群は定義により cycle class map の kernel
(homologically trivial cycles) の中に住む。したがって:

```
ker_topo = ker_topo^{hom} (+) ker_topo^{non-surj}

ker_topo^{hom}:  Griffiths 群 Gr^p(X)。homologically trivial だが
                 algebraically non-trivial なサイクル。
                 → Hdg^p(X,Q) との交差は自動的に 0 (定義による)
                 → f_rational への寄与: 0

ker_topo^{non-surj}: cl ⊗ Q の像の余次元。
                 → Hdg^p(X,Q) \ Im(cl ⊗ Q) に住む
                 → f_rational = dim(ker_topo^{non-surj} ∩ Hdg^p(X,Q))
```

**帰結**: f_rational > 0 の反例は Griffiths 群からは来ない。
反例があるとすれば cycle class map の **非全射性** (non-surjectivity) から来る。
Griffiths 群の非自明性は ker_topo^{hom} の証拠であり、
f_rational とは独立の現象。

### §4.5 具体的存在定理

| 結果 | ker_topo の内容 | 意味 |
|---|---|---|
| Griffiths (quintic 3-fold) | Gr^2 ≠ 0 | AJ-trivial だが代数的に非自明なサイクルが存在 |
| Clemens (generic quintic) | Gr^2 は可算無限 | ker_topo は有限次元ではない |
| Mumford (一般曲面) | CH_0 無限次元 | 有限窓 W で全体を捕捉不可能 |
| Nori (一般型) | connectivity 限界 | cycle class が中次元以上で非全射 |

**R-type 精密化**: Griffiths/Clemens/Mumford = R-topo-hom (f_rational に寄与しない)。
Nori connectivity 限界 = R-topo-surj の候補 (cl が非全射)。
全て gauge-independent。

### §4.6 dim 依存の ker_topo 成分数 — wildness depth + T6 類似

ker_topo の「成分数」は dim/codim に伴って増大する。
T6 (crystal codim 分解: abs(h) = abs_cent + C_1/h + C_2/h^2) と同種のパターン。

壁には 2 種類ある:
- **technique wall**: 同じ wildness depth 内での手法限界。突破可能
- **conductor wall**: 新しい generator type 出現 (wildness depth 上昇)。本質的な壁

#### Hodge 環の generator 構造 (Moonen-Zarhin 1999)

```
dim <= 5: Hdg*(A) = <divisors> + <Weil classes>     (2 generator types)
dim >= 6: Hdg*(A) = <divisors> + <Weil> + <exotic>  (3+ generator types)
```

**Weil classes**: abelian 2n-fold A with CM by imaginary quadratic K に対して
H_W(A, eta) = Lambda^{2n}_K H^1(A, Q)。中間コホモロジー H^{2n} 内の 2次元 Q-部分空間。
divisor の cup product では生成できず、codim n のサイクル構成が必要。

**Exotic classes** (dim >= 6): divisor でも Weil でもない Hodge 類。
Albert 分類 (Type I-IV) の複合的相互作用から出現。構成手法が存在しない。

#### 壁の分類表 (修正版)

| dim | Generator types | wildness depth | 壁の種類 | 状態 | 手法 |
|---|---|---|---|---|---|
| 2-3 | divisors のみ | 0 (tame) | — | **PROVED** | Lefschetz (1,1) |
| 4 | div + Weil | 1 (wild-1) | technique wall | **PROVED** | Markman A: hyper-Kahler J^3 (b_3=8) |
| 5 | div + Weil | 1 (wild-1) | technique wall | **PROVED** (Markman B, 2025) | secant sheaf + semi-reg → sixfold → pullback |
| **6** | div + Weil + exotic? | **2 (wild-2)** | **conductor wall** | **OPEN** | semi-reg 拡張必要 + exotic 未制御 |
| 7+ | div + Weil + exotic | 2+ (wild-2+) | conductor wall | **OPEN** | 未知 |

**Markman の 2 手法**:
- **手法 A** (2018, arXiv:1805.11574): Kum^n の J^3 → abelian fourfold。
  b_3(Kum^n) = 8 (位相不変量) → fourfold に固定。dim 4 限定。
- **手法 B** (2025, arXiv:2502.03415 + 2509.23403): secant sheaf + Orlov 導来同値 + semi-regularity。
  split Weil 型 abelian sixfold で代数性証明 → Schoen degeneration で全 fourfold。
  Moonen-Zarhin: dim 5 の Weil 類は quotient fourfold から pullback → dim 5 も closure。
  **dim >= 8 は semi-regularity の twisted reflexive sheaf 版が未証明**。

#### conductor wildness depth

```
wildness_depth(A, dim g) = max { d : Hdg*(A) に depth-d generator が必要 }

depth 0: divisor classes (Lefschetz で代数化、全 dim)
depth 1: Weil classes (Markman で代数化、dim <= 5)
depth 2: exotic classes (手法なし、dim >= 6)
depth k: ?-classes (dim >> 1、未分類)
```

| dim 範囲 | wildness depth | 壁の性質 | conductor_Hodge |
|---|---|---|---|
| 2-3 | 0 | — | 0 (proved) |
| 4-5 | 1 | technique wall (同一 depth 内) | 0 (proved, Markman 2025) |
| **6+** | **2+** | **conductor wall (depth 上昇)** | **OPEN** (exotic = f_rational 候補) |

#### T6 との同種性 (修正版)

| T6 (Crystal) | Hodge filtration | 共通パターン |
|---|---|---|
| codim-0 (centering) → 常に存在 | depth-0 (divisor) → Lefschetz | 最低次は常に制御可能 |
| codim-1 (glide) → O(1/h) | depth-1 (Weil) → Markman | 次の段で technique-dependent 障害 |
| codim-2 (screw) → O(1/h^2) | **depth-2 (exotic) → ?** | **高次障害は本質的に新しい手法を要求** |

**修正**: 前版では dim 5 を壁としたが、Markman 2025 + Moonen-Zarhin で突破済み。
真の conductor wall は **dim 6** (exotic class 出現、wildness depth 1→2)。

**結晶との対応精密化**:
- symmorphic ↔ Moonen-Zarhin 制御範囲 (dim <= 5): 高次補正が消える
- non-symmorphic ↔ 制御外 (dim >= 6): 高次補正 (exotic class) が点灯
- 結晶では空間群で一様に決まる。Hodge では variety の endomorphism 構造に依存

---

## §5 Tier-Filtration 対応表

HC-1a tier 表 (§13.1b) を filtration depth で再整理する。

### §5.1 対応原理

```
Tier = f(filtration_depth, gauge)

filtration_depth = 0  →  Tier 0 (identity, automatic)
filtration_depth = 1  →  Tier 1 (Lefschetz closure)
filtration_depth >= 2 →  Tier 2 (open) OR Tier sqrt (Z-gauge fails)

Tier sqrt と Tier 2 の分離: gauge behavior
  R-gauge (torsion obstruction) → Tier sqrt (Q-gauge で消滅)
  R-topo-hom  (Griffiths 群) → ker_topo 存在証拠だが f_rational = 0
  R-topo-surj (非全射障害) → Tier 2 (全 gauge で持続、f_rational の唯一の住所)
```

### §5.2 HC-1a 多様体の filtration 分類

| 多様体 | dim | codim p | filt_depth | Tier | R-type | ker_topo 状態 |
|---|---|---|---|---|---|---|
| P^n (端) | n | 0, n | 0 | 0 | — | 不在 (自明) |
| Abelian variety A (端) | g | 0, g | 0 | 0 | — | 不在 (自明) |
| P^n (超平面) | n | 1 | 1 | 1 | — | = 0 (Lefschetz) |
| K3 surface | 2 | 1 | 1 | 1 | — | = 0 (Picard = Hdg^1) |
| Abelian surface | 2 | 1 | 1 | 1 | — | = 0 (Lefschetz) |
| Smooth hypersurface | n-1 | 1 | 1 | 1 | — | = 0 (Hard Lefschetz) |
| Abelian 4-fold | 4 | 2 | 2 | 2 | R-topo-surj | ker_topo^{non-surj} ∩ Hdg^2 = 0 (Markman 2022) |
| Smooth cubic 4-fold | 4 | 2 | 2 | 2 | R-topo-surj | ker_topo^{non-surj} ∩ Hdg^2 = 0 (Zucker 1977) |
| Generic X ⊂ P^5 | 4 | 2 | 2 | 2 | R-topo-surj | = 0 (Lefschetz forced h^{2,2}=1) |
| K3^{[2]} (Hilbert) | 4 | 2 | 2 | 2 | R-info | OPEN (h^{2,2}=232) |
| BU(n) approx (Totaro) | high | 2 | 2 | sqrt-a | R-gauge | N/A (Sq^3 torsion; Q で消滅) |
| Voisin example | high | >= 2 | >= 2 | sqrt-b | R-gauge | N/A (H^3_nr; Q で消滅) |
| Eilenberg-MacLane | high | 4 | 4 | sqrt-a | R-gauge | N/A (iterated Sq^3; Q で消滅) |

### §5.3 構造的読み取り

1. **filt_depth = 0, 1**: ker_topo は必ず 0。1段以下では filtration 障害が原理的に発生しない
2. **filt_depth >= 2, R-gauge**: ker_topo は無関係。障害は torsion (ker_gauge) に属し Q-gauge で除去される
3. **filt_depth >= 2, R-topo-hom**: ker_topo^{hom} ≠ 0 は存在する (Griffiths, Clemens)。
   ただし Hdg^p との交差は定義により 0 → f_rational に無関係 (見かけの壁)
4. **filt_depth >= 2, R-topo-surj**: ker_topo^{non-surj} ∩ Hdg^p(X, Q) = 0 が全既知例で成立 = **Hodge 予想そのもの**

---

## §6 f_rational の幾何的定義

T-AAS §10.2 の f_rational(phi) = dim{ker_topo} に幾何的内容を与える。

### §6.1 Hodge instance

```
f_rational(X, p) = dim_Q { alpha in Hdg^p(X, Q) : alpha not_in Im(cl ⊗ Q) }

  = dim_Q ( Hdg^p(X,Q) / Im(cl^p ⊗ Q) )
```

**Hodge 予想** = f_rational(X, p) = 0 for all smooth projective X and all p.

### §6.2 Filtration depth 解釈

f_rational は filtration の多段合成における **非到達次元** を測る:

```
f_rational(X, p) = Sum_{k=1}^{p} dim(ker_topo_k ∩ Hdg^p(X, Q))

  where ker_topo_k = ker(phi_k) restricted to rational Hodge classes
```

各 filtration 段 k での kernel 寄与の合計。
p = 1 では Lefschetz が ker_topo_1 = 0 を保証するため f_rational = 0。

### §6.3 Stark との対照

| | Stark | Hodge |
|---|---|---|
| f_torsion | dim{sign obstruction} = |{rho : nu(rho) = -1}| | dim{torsion obstruction} = |{alpha : Sq^3(alpha) != 0}| |
| f_rational | dim{multi-field L-ratio obstruction} | dim{filtration-depth obstruction} |
| 予想 | f_rational > 0 は 5-tier で分類済 | f_rational = 0 が Hodge 予想 |

**非対称性**: Stark では f_rational > 0 の instance が存在する (multi-field case)。
Hodge では f_rational > 0 の instance が **未発見** — これが open frontier。

---

## §7 Visibility Decay — codim 増大による検出困難度

### §7.1 指数的減衰

多段合成の各段で kernel が生じる確率を独立と仮定すると、
codim p の class が代数的起源を持つ「可視性」は:

```
visibility(p) ~ prod_{k=1}^{p} (1 - epsilon_k)
```

epsilon_k が各段の kernel 割合。epsilon_k が一定なら指数減衰。

Research note §13.4 の codim 重み e^{-p/2} はこの指数的描像と整合する:
- p = 1: e^{-0.5} ~ 0.61 (Lefschetz で closure)
- p = 2: e^{-1} ~ 0.37 (Abel-Jacobi が必要)
- p = 3: e^{-1.5} ~ 0.22 (higher Chow complex が必要)

### §7.2 ΣΦ 解釈

有限窓 W (A0) の帯域は filtration depth に制約される。
codim p の情報を通すには W が p 段分の帯域を持つ必要がある。
帯域不足 = ker_topo の源。

---

## §7.5 zeta-depth 対応 — ζ の 3-gauge が wildness depth を生成する

### §7.5.1 対応表

ζ の 3-gauge 構造 (Paper Omega: addZ + mult + anal) が wildness depth の 3段に一対一対応:

| zeta gauge | 数学的内容 | wildness depth | Hodge generator | 代数化手法 |
|---|---|---|---|---|
| **addZ** (加法和 Sum 1/n^s) | 級数の収束、線形構造 | 0 (tame) | divisor | Lefschetz |
| **mult** (Euler 積 Prod(1-p^{-s})^{-1}) | 素数の独立性、因子分解 | 1 (wild-1) | Weil class | Markman (Artin 因子分解依存) |
| **anal** (解析接続) | 非自明零点、大域構造 | 2 (wild-2) | exotic class | **なし** |

### §7.5.2 Frobenius-Schur 指標と Albert 分類の橋

S9 (Artin 因子分解): zeta_H(s) = Prod_rho L(s, rho)^{dim rho}

各 L(s, rho) は表現 rho の型 (FS 指標 nu) で分類される。
Albert 分類 (abelian varieties の endomorphism algebra) との対応:

| FS nu(rho) | 表現型 | Albert Type | involution | depth |
|---|---|---|---|---|
| +1 (orthogonal) | 実 | Type I (totally real) / **Type II (indef. quat.)** | 直交的 | 0-1 |
| 0 (complex) | 複素 | Type IV (CM) | ユニタリ | 1 (Weil) |
| -1 (quaternionic) | 四元数 | **Type III (definite quat.)** | 交代的 | 2 (exotic, partial) |

**注意**: Type II (indefinite quaternion) は直交的 involution → ν=+1 であり ν=-1 ではない。
Type III (definite quaternion) のみが交代的 involution → ν=-1。

**Mumford 反例**: Type I (End=Q) でも exotic class が出現する (MT群 SL(2)^3)。
したがって depth 2 の源は 2 つ:
- **Source A**: Type III (ν=-1) — Sp(2n) 表現論で n≥3 (dim≥6) に新 invariants [PROVED]
- **Source B**: Exceptional MT groups (Type I, ν=+1) — Mumford型 [PROVED, dim 4 から存在]

depth 2 = ν=-1 exclusively は **誤り**。正確には depth 2 = {Type III (ν=-1)} ∪ {Exceptional MT}。

### §7.5.3 dim 6 壁のメカニズム — Sp(2n) 表現論 [PROVED]

MZ dim ≤ 5 closure が dim 6 で破れる正確な理由:

Type III abelian variety (dim 2n, definite quaternion End) の Hodge 群 ⊂ Sp(2n)。
中間外積 Lambda^{2n}(C^{2n}) 内の Sp(2n)-invariants:

| n | dim 2n | Sp-invariants | divisor+Weil で説明可能か | 状態 |
|---|---|---|---|---|
| 1 | 2 | symplectic form のみ | YES | trivial |
| 2 | 4 | form + Weil 関連 | YES | PROVED |
| **3** | **6** | **form powers + 新しい invariants** | **NO** | **MZ 制御外** |
| 4+ | 8+ | さらに多くの invariants | NO | OPEN |

**核心**: Sp(6) 不変量の計算 [PROVED, Cauchy formula + Weyl-Brauer FFT]:

Type III abelian 6-fold: V = C^6 (Sp(6) standard), W = C^2 (quaternion 構造)。
```
(Lambda^6(V tensor W))^{Sp(6)} = S_{(4,2)}(C^2) + Sym^6(C^2)
                                  dim 3          dim 7       total = 10
divisor 生成 (omega^3 系): dim 1
exotic (divisor 外): dim 9 = 2 (S_{(4,2)} 余剰) + 7 (Sym^6)
```

10 次元中 1 次元のみが divisor で説明でき、9 次元が exotic。
このうち Weil classes が占める次元は variety 依存 (Abdulali)。
**truly exotic (divisor でも Weil でもない) の存在/次元は OPEN**。

### §7.5.4 Sign channel hypothesis — CONJECTURAL

S11 (nt_root_numbers.md §3): ν=-1 → W(ρ)=+1 (Deligne)。

| nu(rho) | W(rho) | sign 自由度 | 代数化への影響 |
|---|---|---|---|
| +1 (orthogonal) | W in {+1, -1} 自由 | 2 channels | sign が parity を運ぶ |
| 0 (complex) | W in S^1 | 連続 | phase 情報あり |
| -1 (quaternionic) | W = +1 強制 | 1 channel | magnitude のみ |

**仮説** (CONJECTURAL — 公刊文献になし):
depth 2 で手法が存在しない理由の一つとして、ν=-1 表現の sign channel 閉鎖が
cycle 構成の道具を制限している可能性。

ただし:
1. W(ρ)=+1 と cycle 構成困難の直接的接続は **未証明**
2. Mumford 型 exotic (Type I, ν=+1, W 自由) は sign channel が開いているのに
   exotic — sign channel 以外の障害も存在する
3. 正確な声明: sign channel collapse は depth 2 壁の **十分条件ではない**。
   Type III (ν=-1) 由来の exotic には寄与し得るが、全 exotic を説明しない

**Status**: CONJECTURAL (仮説)。OQ-HC-15 の「formal か analogical か」の答え:
ν-depth 対応は **部分的 formal** (Type III/Sp 表現論) + **analogical** (sign channel)。

### §7.5.5 ζ の生成核としての意味

Paper Omega §2.4: ζ = generating kernel (addZ+mult+anal で唯一の 3-gauge intrinsic)、
gamma = boundary residue kernel (ζ の Laurent 定数項)。

ζ の 3-gauge と wildness depth の対応:
- addZ (加法和) → depth 0 (divisor = 線形、級数収束)
- mult (Euler 積) → depth 1 (Weil = 因子分解、素数独立性)
- anal (解析接続) → depth 2 (exotic = 大域構造、非自明零点)

**対応の status**:

| 層 | 対応の性質 | 根拠 |
|---|---|---|
| addZ ↔ depth 0 | **FORMAL** | S7 (class number formula) が Lefschetz に直結 |
| mult ↔ depth 1 | **FORMAL** | S9 (Artin 因子分解) が Weil class の構造を決定 |
| anal ↔ depth 2 | **ANALOGICAL** | 3段目の一致は構造的だが formal proof なし |

**Type III / Sp 接続による部分的形式化**:
anal gauge に対応する L 関数成分のうち、ν=-1 (Type III) 部分は
Sp(2n) 表現論を介して dim 6 exotic class を [PROVED で] 生む。
ただし Mumford 型 exotic (Type I) は mult gauge 側の異常 (MT 群の例外性)
であり、anal gauge だけでは説明できない。

**暫定結論**: ζ-depth 対応は **2/3 formal + 1/3 analogical**。
depth 0-1 は formal (S7, S9 を通じて確立)。
depth 2 は部分的 (Type III → Sp invariant theory) + 残余は analogical。
完全な formal 化には Mumford 型 exotic の ζ 側表現が必要 → OQ-HC-17。

---

## §8 Open Questions

| ID | Question | Priority |
|---|---|---|
| OQ-FO-1 | ker_topo^{non-surj} (§4.4) の各 filtration 段寄与を測る不変量は何か？ Griffiths 群は ker_topo^{hom} 側であり f_rational に寄与しない。non-surj 側の段別 indicator が必要。 | HIGH |
| OQ-FO-2 | visibility decay (§7.1) の epsilon_k は codim k に依存するか定数か？ abelian dim ≤ 5 で全段 closure (Markman 2025)。dim 6 で epsilon_k > 0 (exotic) — sign channel collapse (§7.5.3) が原因か？ | HIGH |
| OQ-FO-3 | Nori connectivity theorem の filtration depth 翻訳: connectivity bound が ker_topo のどの段を kill するか定量化できるか？ | MEDIUM |
| OQ-FO-4 | ker_topo^{hom} (Griffiths 群) と ker_topo^{non-surj} の相互作用: hom 側が大きい (Clemens: countably infinite) とき non-surj 側は制約されるか？ | MEDIUM |
| OQ-FO-5 | depth 2 の 2 源 (Type III/Sp と Mumford/exceptional MT) の ζ 側表現: Type III は ν=-1 → anal gauge 経由で partial formal。Mumford 型は mult gauge 側の MT 群異常性 — これを ζ の Euler 積構造で記述できるか？ | HIGH |

---

## §8.5 4-class quantum lift — Theorem 4a.1 unified f_rational (Paper Q1 §5, 2026-04-27)

§4-§6 で展開した f_rational の幾何的 (Hodge / Stark) 視点と parallel に、Paper Q1 (`papers/publication/quantum/Q1_observation_theory_quantum_ja.md` §5) は **量子側 4-class refined Hodge framework** を T-AAS Arrow 1 kernel narrowness の 4 instance taxonomy として確立する。古典 Hodge は f_rational > 0 の存在問題そのものが open frontier (Millennium 1924-) だが、量子側では 4 candidate algebraic class それぞれで **f_rational > 0 instance ESTABLISHED**、古典-量子 depth parallel conjecture (Conjecture 4a.2) を提供する。

**Status**: ESTABLISHED 2026-04-23 (`research/oq_omega_obs_4a_refined_quantum_hodge_v0.md` 6/6 gate, 4-class formal + per-class monotone + Theorem 4a.1 unified + 3/4 empirical)。

### §8.5.1 4 candidate algebraic class

| # | Class C | 定義 | f_rational monotone $M_C$ | sparsity type |
|---|---|---|---|---|
| **C₁** | Stabilizer | Clifford orbit from $|0...0\rangle$, STAB = Clifford · $|0\rangle$ | Magic monotone $M_F = -\log_2 \sup_{\sigma \in STAB} F(\rho, \sigma)$ | discrete in continuous (measure zero) |
| **C₂** | Gaussian | 二次 Hamiltonian 由来, Wigner ≥ 0 (Hudson's theorem) | Wigner negativity $\mathcal{N}(\rho) = \int \|W^-\| dx \, dp$ | poly in infinite |
| **C₃** | Eff-sim | Poly-time classical simulable (low-bond MPS, match-gate) | Nielsen geometric complexity $C(|\psi\rangle) - c_0 n^k$ | poly in exp |
| **C₄** | Bell-local | LHV-describable correlations (CHSH ≤ 2) | CHSH violation $\Delta_{\text{CHSH}}(\rho) = [\langle CHSH \rangle - 2]_+$ | classical polytope ⊂ quantum correlation body |

各 monotone は 4 properties (P1)-(P4) を満たす: vanishing on $\overline{C}$ / positivity off / class-stabilizing gauge invariance / monotone non-increasing under C-free operations。

### §8.5.2 T-AAS 分解 (per class)

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **C₁ Stabilizer** | Clifford coset (discrete finite group) | non-stabilizer (T-state etc.) | f_Clifford ∈ ℤ_{≥0} | $M_F \in [0, \log_2 d]$ | empirical 1-qubit M_F = 4e-16 (stabilizer) ✓ |
| **C₂ Gaussian** | symplectic orbit $Sp(2N, \mathbb{R})$ | non-Gaussian (Fock $|n\rangle$, n≥2) | f_symplectic | $\mathcal{N}, D_G$ | Mari-Eisert (2012) photon-subtracted 1e-4 ✓ |
| **C₃ Eff-sim** | poly-depth circuit | super-poly complexity | f_circuit | $C - c_0 n^k$ | 4-ref literature synthesis (Nielsen / Jefferson-Myers / Bouland-Fefferman / Brandao-Horodecki) ✓ |
| **C₄ Bell-local** | local unitaries $U_A \otimes U_B$ | CHSH violation > 0 | f_local | $\Delta_{\text{CHSH}} \in [0, 2\sqrt{2}-2]$ | 2-qubit Tsirelson 1e-6 ✓ |

4 instance + Theorem 4a.1 (§8.5.3) で **16/16 量子-relevant fitness** verify。

### §8.5.3 Theorem 4a.1 — Unified f_rational via class infidelity

Per-class monotone (M_F, 𝓝, C, Δ_CHSH) は **異なる単位系** (log-bit, L¹ norm, gate count, linear value) に住むが、**class-fidelity** $F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$ (Uhlmann fidelity with class closure) で **統一**:

$$M_{\mathrm{unified}}^{C}(\rho) := -\log_2 F_C(\rho)$$

**Theorem 4a.1**: class C が (i) convex closure を持つ state subset、(ii) class-preserving unitary/CPTP operations が well-defined、を満たせば $M_{\mathrm{unified}}^C$ は §8.5.1 各 class monotone と以下の対応を持つ (proof outline `oq_omega_obs_4a_refined_quantum_hodge_v0.md §4.4.1`):

$$\begin{aligned}
M_{\mathrm{unified}}^{C_1}(\rho) &= M_F(\rho) \quad \text{(stabilizer fidelity, tautological)} \\
M_{\mathrm{unified}}^{C_2}(\rho) &\sim \tfrac{1}{2}\log_2(1 + \mathcal{N}(\rho)^2) \quad \text{(Fuchs-van-de-Graaf)} \\
M_{\mathrm{unified}}^{C_3}(|\psi\rangle) &\geq \tfrac{1}{\log 2} \cdot \text{(Nielsen geodesic}/2\text{)}^{-1} \quad \text{(quantum speed-limit)} \\
M_{\mathrm{unified}}^{C_4}(\rho) &\sim -\log_2(1 - \Delta_{\mathrm{CHSH}}(\rho)/\text{const}) \quad \text{(Horodecki)}
\end{aligned}$$

(P1)-(P4) 4 class 全てで holds、4 monotone が **同一単位系 (log₂-bit)** に統一。

### §8.5.4 古典 Hodge 予想 depth parallel (Conjecture 4a.2)

**Conjecture 4a.2 (unified depth parallel)**: 古典 Hodge の f_rational を log₂ scale 化:
$$f_{\mathrm{rational}}^{\mathrm{Hodge}}(X, p) \ \widetilde{=}\ \log_2(\dim(\mathrm{Hdg}^p / \mathrm{im\ cl}) + 1)$$

(Hodge 予想真なら右辺 = 0、偽なら > 0)。Unified 量子 f_rational $M_{\mathrm{unified}}^C = -\log_2 F_C$ も log₂-bit、両者 **同一単位系で比較可能**:

> 各 class C と古典 Hodge (p, X) の組で sparsity-ratio-matched pair を取ると、$M_{\mathrm{unified}}^C$ の typical scale と $f_{\mathrm{rational}}^{\mathrm{Hodge}}$ の typical scale に $\mathcal{O}(1)$ の比例関係が存在。

**Status**: OPEN。Conjecture は (1) sparsity-matching formal definition (2) "typical scale" probability measure (3) 古典 Hodge counterexample 存在の 3 要件依存。古典側 counterexample 不在で current vacuous trivial parallel。

### §8.5.5 N1 (NT) との関係

N1 §5.4 で Hodge 予想を **NT-adjacent open frontier** (T-AAS f_rational > 0 candidate, NT 内 instance なし、scope outside but framework anchor) として position。Q1 §5 (本 §8.5) は量子側で **4 instance ESTABLISHED + depth parallel conjecture** を提供 → 古典 Hodge 予想に対し N1 (open anchor) と Q1 (4 instance + parallel) の **2-domain assault** を framework 内で実現。

**Ref**:
- Paper Q1 §5 (`papers/publication/quantum/Q1_observation_theory_quantum_ja.md`)
- `research/oq_omega_obs_4a_refined_quantum_hodge_v0.md` (ESTABLISHED 2026-04-23, 6/6 gate)
- `research/oq_omega_obs_4a_monotone_verify.py` (empirical 1-qubit M_F + 2-qubit CHSH)
- `research/oq_omega_obs_1_ker_entangle_frational_path_v0.md` (minimal form, depth-deficient)
- Paper N1 §5.4 (NT-adjacent Hodge open frontier)

---

## §9 References (ΣΦ 内部)

- L0_canon/finite_observation.md — A0 (S,W,m)、有限窓の帯域制約
- L1/c_arrow_obstruction.md §10 — T-AAS: ker = ker_gauge + ker_topo, f = f_torsion + f_rational
- L1/c_arrow_obstruction.md §6 — gauge wall 1 (Z→Q), wall 2 (Q→R)
- L1/c_hidden_degrees_of_freedom.md §2.5 — R-topo 型定義
- L1/nt_conductor.md §6 — ramification 階層 (S8)
- L1/nt_frobenius_schur.md — pairing obstruction (ker_gauge 側), ν trichotomy
- L1/nt_root_numbers.md §3-4 — S11: W(rho) sign constraint, magnitude/sign split
- L1/nt_dedekind_artin_zeta.md §1 — S9: Artin factorization, zeta-depth bridge
- L1/c_boundary_invariants.md — 離散不変量分類 (R-topo の境界版)
- L1/c_spectral.md §8 — S7 class number formula, 6-gauge (ζ の s=1 留数)
- research/hodge_conjecture_decomposition_v0.md §13-§16, §26, §28 — HC-1a tier 表、R-type 分類、境界地図
