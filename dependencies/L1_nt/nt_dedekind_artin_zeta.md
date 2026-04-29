---
axis: A
position: algebra_analysis
static_dynamic: static
connected_to:
  - A.algebra_analysis
  - A.algebra_constraint
  - L.number_theory
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-10
runtime_summary:
  what: "Dedekind zeta factorization, Artin formalism, and analytic class number formula — structural residence for L-function decomposition via representation theory."
  when: "Galois extension zeta decomposition, intermediate field zeta ratio, Stark branch numerical verification, tier classification L-function side"
  provides: [dedekind_zeta_factorization, artin_formalism, permutation_character_zeta, intermediate_field_zeta, class_number_formula_artin_view, functional_equation_artin]
  consumes:
    - "nt_conductor.md §6 (Artin conductor, local formula, induction/Brauer)"
    - "c_spectral.md §8 (class number formula 6-gauge, rank 0 Stark)"
    - "nt_frobenius_schur.md §1 (FS indicator, real/complex/quaternionic trichotomy)"
    - "nt_relative_units.md §2-3 (regulator, sub-quotient unit group)"
    - "identity_asymmetry.md §3.4 (vanishing order structural explanation)"
  axis: [A]
  residual_types: [R-gauge, R-comp]
  cost: small
  status: established
  key_theorems:
    - {id: Artin_factorization, statement: "ζ_H(s) = ∏_ρ L(s,ρ,H/k)^{dim ρ} for H/k Galois with G=Gal(H/k)", derived_in: "§1", status: established, cross_refs: ["nt_conductor.md §6.9"]}
    - {id: intermediate_field_zeta, statement: "ζ_F(s) = ∏_ρ L(s,ρ)^{⟨ρ, Ind_{G_F}^G 1⟩} for intermediate field F = H^{G_F}", derived_in: "§2", status: established, cross_refs: ["brauer_closure_galois_classification_v0.md §2"]}
    - {id: class_number_formula_artin, statement: "Res_{s=1} ζ_K(s) = 2^{r₁}(2π)^{r₂} h_K R_K / (w_K √|d_K|)", derived_in: "§3", status: established, cross_refs: ["c_spectral.md §8.2"]}
  one_screen: |
    - §1: Artin factorization — ζ_H = ∏ L(s,ρ)^{dim ρ}. Every Dedekind zeta of a Galois extension decomposes into Artin L-functions indexed by irreps.
    - §2: Intermediate field zeta — ζ_F = ∏ L(s,ρ)^{⟨ρ, Ind 1⟩}. Permutation character determines which L-factors appear; this is the bridge to tier classification.
    - §3: Analytic class number formula — s=1 residue and s=0 leading coefficient. Artin view: trivial character contribution = ζ_ℚ with known residue; nontrivial characters carry h_K R_K / w_K.
    - §4: Functional equation — completed L-function Λ(s,ρ) with Artin conductor N(ρ), gamma factors, root number W(ρ). Connects to nt_conductor.md §6.2-6.4.
    - §5: D₄ / Q₈ / A₄ worked pointers + §5.4 ℚ(√−23) h=3 canonical example (全検証済). Connects to brauer_closure_galois_classification_v0.md.
    - §6: Scope boundary — what lives here vs c_spectral.md §8 vs nt_conductor.md §6.
---

**Level**: L1 (pure mathematics, representation-theoretic)
**Dependencies**: nt_conductor.md §6, c_spectral.md §8, nt_frobenius_schur.md §1, identity_asymmetry.md §3.4
**Downstream**: number_theory_dictionary_v0.md §5, brauer_closure_galois_classification_v0.md, OQ-NT-7/8

# Dedekind Zeta Factorization and Artin Formalism

## §1 Artin Factorization

### §1.1 Setting

$H/k$ a Galois extension of number fields, $G = \mathrm{Gal}(H/k)$.
$\mathrm{Irr}(G) = \{\rho_0 = 1, \rho_1, \dots, \rho_m\}$ the set of irreducible complex representations of $G$.

**定義**: The **Artin L-function** attached to $\rho \in \mathrm{Irr}(G)$ is

$$L(s, \rho, H/k) = \prod_{\mathfrak{p} \nmid \mathrm{disc}} \det\bigl(I - \rho(\mathrm{Frob}_\mathfrak{p})\, N\mathfrak{p}^{-s}\bigr)^{-1}$$

extended to ramified primes via the $I_\mathfrak{p}$-fixed subspace (see nt_conductor.md §6.2 for the local conductor).

### §1.2 Factorization Identity

**Theorem (Artin factorization)**:

$$\zeta_H(s) = \prod_{\rho \in \mathrm{Irr}(G)} L(s, \rho, H/k)^{\dim \rho}$$

**証明の骨子**: The regular representation decomposes as $\mathrm{reg}_G = \bigoplus_\rho \rho^{\oplus \dim \rho}$. Each Euler factor of $\zeta_H$ at an unramified prime $\mathfrak{P} | \mathfrak{p}$ contributes $\det(I - \mathrm{Frob}_\mathfrak{P}\, N\mathfrak{P}^{-s})^{-1}$. Collecting over the $\mathrm{Frob}$-orbit of $\mathfrak{P}$ and using the regular representation decomposition yields the product. ■

**特殊ケース** ($k = \mathbb{Q}$): $\rho_0 = 1$ gives $L(s, 1) = \zeta_\mathbb{Q}(s)$, so

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot \prod_{\rho \neq 1} L(s, \rho)^{\dim \rho}$$

This isolates the "nontrivial" L-factor content.

### §1.3 Abelian Case

$G$ abelian $\Rightarrow$ all $\rho$ are 1-dimensional characters $\chi$, and $L(s, \chi)$ is a Hecke L-function. The factorization becomes

$$\zeta_H(s) = \prod_{\chi \in \hat{G}} L(s, \chi)$$

No exponents $> 1$ appear. This is the setting where rank 1 abelian Stark operates (c_spectral.md §8.6).

---

## §2 Intermediate Field Zeta

### §2.1 Permutation Character Formula

Let $F$ be an intermediate field $k \subseteq F \subseteq H$ with $F = H^{G_F}$ for subgroup $G_F \leq G$. The **permutation character** of $G$ on $G/G_F$ is $\mathrm{Ind}_{G_F}^G 1$.

**Theorem (intermediate field zeta)**:

$$\zeta_F(s) = \prod_{\rho \in \mathrm{Irr}(G)} L(s, \rho)^{\langle \rho,\, \mathrm{Ind}_{G_F}^G 1 \rangle}$$

where $\langle \cdot, \cdot \rangle$ is the inner product on class functions of $G$.

**Frobenius reciprocity** gives $\langle \rho, \mathrm{Ind}_{G_F}^G 1 \rangle = \langle \mathrm{Res}_{G_F} \rho, 1 \rangle = \dim \rho^{G_F}$, the dimension of $G_F$-fixed vectors in $\rho$.

### §2.2 Zeta Ratio = L-function Extraction

Dividing by $\zeta_k(s) = L(s, 1)$:

$$\frac{\zeta_F(s)}{\zeta_k(s)} = \prod_{\rho \neq 1} L(s, \rho)^{\dim \rho^{G_F}}$$

This is the **bridge to tier classification** (nt_conductor.md §6.9.3):

| Tier | Condition | L-function extraction |
|---|---|---|
| Tier 1 strict | $\exists F$: $\dim \rho^{G_F} = 1$ and $\rho$ is the **only** nontrivial factor | $L(s,\rho) = \zeta_F / \zeta_k$ (single ratio) |
| Tier 2 relaxed | $L(s,\rho) = \zeta_{F_1} / \zeta_{F_2}$ via two intermediate fields | rational combination of two zeta quotients |
| Tier 3+ multi | requires $\geq 3$ intermediate fields | product of multiple zeta ratios |
| Tier $\sqrt$ | $L(s,\rho)$ itself not a zeta ratio; only $L(s,\rho)^2$ is | nt_frobenius_schur.md: $\nu(\rho) = -1$ quaternionic obstruction |

### §2.3 Examples (Pointers)

**D₄ ($|G|=8$)**: $\rho_2$ (2-dim faithful) satisfies $\dim \rho_2^{G_F} = 1$ for some index-4 subfield $F$. Tier 1 strict: $L(s, \rho_2) = \zeta_F / \zeta_\mathbb{Q}$.
→ Numerical: brauer_closure_galois_classification_v0.md §5-6, $R_{\mathrm{rel}} = 0.633$.

**Q₈ ($|G|=8$)**: $\rho_2$ (2-dim faithful) has $\dim \rho_2^{G_F} = 0$ for all proper subgroups $G_F$ (all index-2 subgroups yield $\rho_2^{G_F} = 0$ since $\rho_2$ restricted to any $\mathbb{Z}/4$ has no fixed vector). Tier $\sqrt$ impossible: $L(s, \rho_2)$ not extractable as any zeta ratio; only $L(s, \rho_2)^2 = 16$ at $s = 0$.
→ Numerical: brauer_closure_galois_classification_v0.md §7-8; nt_frobenius_schur.md §4.4.

**A₄ ($|G|=12$)**: $\rho_3$ (3-dim) has $\dim \rho_3^{V_4} = 1$ where $V_4 \trianglelefteq A_4$. Tier 1 strict: $\zeta_F(s) = \zeta_\mathbb{Q}(s) \cdot L(s, \rho_3)$ for the non-Galois quartic $F = H^{V_4}$.
→ brauer_closure_galois_classification_v0.md §11.

---

## §3 Analytic Class Number Formula

### §3.1 Classical Statement

For a number field $K$ of degree $n = r_1 + 2r_2$ over $\mathbb{Q}$:

**$s = 1$ residue form**:

$$\mathrm{Res}_{s=1}\, \zeta_K(s) = \frac{2^{r_1} (2\pi)^{r_2}\, h_K\, R_K}{w_K \sqrt{|d_K|}}$$

**$s = 0$ leading coefficient form** (vanishing order $r = r_1 + r_2 - 1$):

$$\zeta_K^*(0) \;:=\; \lim_{s \to 0} s^{-r}\, \zeta_K(s) \;=\; -\frac{h_K\, R_K}{w_K}$$

The $-1$ in the vanishing order is the product formula constraint $\sum \log|\sigma(\varepsilon)| = 0$ (identity_asymmetry.md §3.4).

### §3.2 6-Gauge Decomposition

The $s = 1$ formula decomposes into 6 factors with distinct gauge signatures (c_spectral.md §8.3):

| Factor | Gauge signature | Role |
|---|---|---|
| $(2\pi)^{r_2}$ | $\{$cont, geom$\}$ | Complex archimedean Haar volume |
| $2^{r_1}$ | $\{$addZ$\}$ | Real archimedean Haar volume (parity minimum) |
| $\sqrt{|d_K|}$ | $\{$mult, anal$\}$ | Minkowski co-volume $=$ Artin conductor of trivial character (nt_conductor.md §6.4) |
| $h_K$ | $\{$mult$\}$ | Class group cardinality |
| $R_K$ | $\{$mult, cont$\}$ | Log-embedding lattice co-volume (regulator) |
| $w_K$ | $\{$char$\}$ | Torsion units $= |\mu(K)|$ |

5-case numerical witness: c_spectral.md §8.5 ($\mathbb{Q}$, $\mathbb{Q}(i)$, $\mathbb{Q}(\sqrt{2})$, $\mathbb{Q}(\sqrt{5})$, $\mathbb{Q}(\sqrt{-5})$). All 6 gauges exercised as singleton main driver in at least one case.

### §3.3 Artin View of Class Number Formula

For $H/k$ Galois with $G = \mathrm{Gal}(H/k)$, the factorization §1.2 gives

$$\mathrm{Res}_{s=1}\, \zeta_H(s) = \mathrm{Res}_{s=1}\, \zeta_k(s) \cdot \prod_{\rho \neq 1} L(1, \rho)^{\dim \rho}$$

The class number formula for $H$ is therefore **partitioned** by irreps:
- $\rho_0 = 1$: contributes $\mathrm{Res}_{s=1}\, \zeta_k(s)$ (known by induction on degree)
- Each $\rho \neq 1$: contributes $L(1, \rho)^{\dim \rho}$ carrying the "new" arithmetic of $H/k$

For $k = \mathbb{Q}$ and $H$ abelian: each $L(1, \chi) \neq 0$ (Dirichlet's theorem on primes in arithmetic progressions) and is expressible via Gauss sums.

---

## §4 Functional Equation

### §4.1 Completed L-function

For $\rho \in \mathrm{Irr}(G)$, define

$$\Lambda(s, \rho) = N(\rho)^{s/2} \cdot \gamma(s, \rho) \cdot L(s, \rho)$$

where:
- $N(\rho) = |d_k|^{\dim \rho} \cdot \mathfrak{f}(\rho)$ is the **Artin conductor** (nt_conductor.md §6.2 gives the local $f_\mathfrak{p}(\rho)$; $\mathfrak{f}(\rho) = \prod_\mathfrak{p} N\mathfrak{p}^{f_\mathfrak{p}(\rho)}$)
- $\gamma(s, \rho) = \prod_{v | \infty} \gamma_v(s, \rho)$ collects archimedean gamma factors:
  - Real place, $\rho(\text{conj}) = +1$: $\Gamma_\mathbb{R}(s) = \pi^{-s/2} \Gamma(s/2)$
  - Real place, $\rho(\text{conj}) = -1$: $\Gamma_\mathbb{R}(s+1)$
  - Complex place: $\Gamma_\mathbb{C}(s) = 2(2\pi)^{-s} \Gamma(s)$

### §4.2 Functional Equation

$$\Lambda(s, \rho) = W(\rho)\, \Lambda(1 - s, \bar{\rho})$$

where $W(\rho) \in \mathbb{C}$, $|W(\rho)| = 1$ is the **Artin root number**.

**Constraints on** $W(\rho)$:
- $\rho$ self-dual with $\nu(\rho) = +1$ (orthogonal): $W(\rho) \in \{\pm 1\}$
- $\rho$ self-dual with $\nu(\rho) = -1$ (symplectic): $W(\rho) = +1$ (forced)
- $\rho$ not self-dual: $W(\rho) \overline{W(\bar{\rho})} = 1$; individual $W(\rho)$ can be any unit complex

→ nt_root_numbers.md §2-3 houses $\varepsilon$-factor local-global product formula and sign constraints by reality type.

---

## §5 Worked Patterns (Mini-Index)

### §5.1 Cyclic Cubic: $\mathbb{Q}(\sqrt[3]{m})$ inside $H/\mathbb{Q}$ with $G = \mathbb{Z}/3$

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s, \chi_3) \cdot L(s, \bar{\chi}_3)$$

Rank 1 Stark: $L'(0, \chi_3) = -(1/e_\chi) \log|\sigma(\varepsilon_\chi)|$.
Concrete case $K = \mathbb{Q}(\sqrt{-23})$, $h_K = 3$: number_theory_dictionary_v0.md §5.3.

### §5.2 D₄ ($|G| = 8$)

$\mathrm{Irr}(D_4) = \{1, \chi_1, \chi_2, \chi_3, \rho_2\}$ with $\dim = \{1,1,1,1,2\}$.

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s,\chi_1) \cdot L(s,\chi_2) \cdot L(s,\chi_3) \cdot L(s,\rho_2)^2$$

$\rho_2$: Tier 1 strict ($\exists$ index-4 subfield $F$ with $\zeta_F = \zeta_\mathbb{Q} \cdot L(s, \rho_2)$).
Numerical target: $R_{\mathrm{rel}} = 0.633$ for splitting field of $x^4 - 2$.
→ brauer_closure_galois_classification_v0.md §5-6.

### §5.3 Q₈ ($|G| = 8$)

$\mathrm{Irr}(Q_8) = \{1, \chi_i, \chi_j, \chi_k, \rho_2\}$ with $\dim = \{1,1,1,1,2\}$.

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s,\chi_i) \cdot L(s,\chi_j) \cdot L(s,\chi_k) \cdot L(s,\rho_2)^2$$

$\rho_2$: Tier $\sqrt$ impossible ($\nu(\rho_2) = -1$, quaternionic). $L(s,\rho_2)^2 = 16$ at $s = 0$; individual $L(0,\rho_2)$ sign $= \pm 4$ undetermined.
→ brauer_closure_galois_classification_v0.md §7-8; nt_frobenius_schur.md §4.4.

### §5.4 Canonical Example: $\mathbb{Q}(\sqrt{-23})$, $h_K = 3$

**選定理由**: 最小の $h > 1$ imaginary quadratic field で、abelian Stark (rank 1) が作動し、Hilbert class polynomial が disc = $d_K$ と一致する稀な例。

**Field data**:

| 不変量 | 値 | 備考 |
|---|---|---|
| $d_K$ | $-23$ | fundamental discriminant |
| $h_K$ | $3$ | class number |
| $w_K$ | $2$ | $\mu(K) = \{\pm 1\}$ |
| $(r_1, r_2)$ | $(0, 1)$ | imaginary quadratic |
| $R_K$ | $1$ | rank 0 unit group |
| $\mathrm{Cl}(K)$ | $\mathbb{Z}/3\mathbb{Z}$ | cyclic |

**Kronecker factorization**: $\zeta_K(s) = \zeta_\mathbb{Q}(s) \cdot L(s, \chi_{-23})$

$\chi_{-23}$ は conductor 23 の実指標（Kronecker symbol）。

**Class number formula verification**:

$$L(1, \chi_{-23}) = \frac{2\pi \cdot 3}{2 \cdot \sqrt{23}} = \frac{3\pi}{\sqrt{23}} = 1.965202054\ldots$$

- Partial sum ($5 \times 10^5$ terms): relative error $1.2 \times 10^{-11}$
- Euler product ($\pi(10000)$ primes): relative error $2.1 \times 10^{-4}$

**$s = 0$ value**: $\zeta_K(0) = -h_K R_K / w_K = -3/2$（vanishing order $r = r_1 + r_2 - 1 = 0$）

**Hilbert class polynomial**: $H_{-23}(x) = x^3 - x - 1$
- $\mathrm{disc}(x^3 - x - 1) = -4(-1)^3 - 27(-1)^2 = -23 = d_K$
- Real root: $\alpha \approx 1.32472$ (plastic number)
- $H = \mathbb{Q}(\sqrt{-23}, \alpha)$, $[H : K] = 3 = h_K$

**Artin factorization (over $K$)**:
- $G = \mathrm{Gal}(H/K) = \mathbb{Z}/3\mathbb{Z}$, $\mathrm{Irr}(G) = \{1, \chi_3, \bar{\chi}_3\}$
- $\zeta_H(s) = \zeta_K(s) \cdot L(s, \chi_3) \cdot L(s, \bar{\chi}_3)$
- **Tier: ALL Tier 1 strict** (abelian, all irreps 1-dim)

**Over $\mathbb{Q}$ (Galois closure)**:
- $\mathrm{Gal}(H/\mathbb{Q}) = S_3$, $\mathrm{Irr}(S_3) = \{1, \mathrm{sgn}, \rho_2\}$
- $\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s, \mathrm{sgn}) \cdot L(s, \rho_2)^2$

**6-gauge main driver**: $h_K = 3$ (mult gauge)。$(2\pi)^{r_2}$, $\sqrt{|d_K|}$ は non-trivial だが $h_K$ が唯一の $> 1$ 整数因子。

**Rank 1 Stark**: $L'(0, \chi_3) = -(1/e_\chi) \log|\sigma(\varepsilon_\chi)|$ (abelian Stark unit in $H$)。
→ c_spectral.md §8.6, number_theory_dictionary_v0.md §5.3。

→ Script: `research/canonical_q_sqrt_neg23.py`

### §5.5 A₄ ($|G| = 12$)

$\mathrm{Irr}(A_4) = \{1, \omega, \bar{\omega}, \rho_3\}$ with $\dim = \{1,1,1,3\}$.

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s,\omega) \cdot L(s,\bar{\omega}) \cdot L(s,\rho_3)^3$$

$\rho_3$: Tier 1 strict via $V_4$-fixed space ($\dim \rho_3^{V_4} = 1$). Non-Galois quartic $F$ gives $\zeta_F = \zeta_\mathbb{Q} \cdot L(s, \rho_3)$.
→ brauer_closure_galois_classification_v0.md §11.

---

## §6 Scope and Connections

### §6.1 What Lives Here

- Artin factorization identity and its immediate corollaries
- Intermediate field zeta decomposition via permutation characters
- Analytic class number formula in Artin-theoretic framing
- Functional equation structure (conductor, gamma, root number)
- Mini-index of group-specific factorization patterns

### §6.2 What Lives Elsewhere

| Content | Residence | Reason |
|---|---|---|
| Artin conductor local formula $f_\mathfrak{p}(\rho)$ | nt_conductor.md §6.2 | conductor = constraint count (T6 domain) |
| Induction invariance, Brauer decomposition | nt_conductor.md §6.9 | conductor downstream of induction |
| Class number formula 6-gauge witness table | c_spectral.md §8.3-8.5 | spectral = measurement/observable domain |
| Frobenius-Schur indicator $\nu(\rho)$ | nt_frobenius_schur.md §1 | FS = representation-intrinsic datum |
| Regulator, sub-quotient unit group | nt_relative_units.md §2-3 | units = algebraic structure domain |
| Vanishing order $r_1 + r_2 - 1$ structural explanation | identity_asymmetry.md §3.4 | identity = L0 canonical |
| Genus class fields, $\mathrm{Cl}_K / \mathrm{Cl}_K^2$ | nt_genus_class_fields.md | genus = class field theory domain |
| Rank 1 Stark instances, case logs | number_theory_dictionary_v0.md §5 | L2 domain-specific |
| D₄/Q₈/A₄ full numerical verification | brauer_closure_galois_classification_v0.md | research layer |
| Root number $\varepsilon$-factor calculus | nt_root_numbers.md §1-5 | sign residence, magnitude/sign split |

### §6.3 Connection Table

| Connection | Role | Direction |
|---|---|---|
| nt_conductor.md §6 | Artin conductor $\to$ functional equation $N(\rho)$ | upstream |
| c_spectral.md §8 | class number formula 6-gauge | lateral (shared theorem, different framing) |
| nt_frobenius_schur.md §1-4 | $\nu(\rho)$ determines $W(\rho)$ constraint and tier | upstream |
| nt_relative_units.md §2 | $R_K$ in class number formula | upstream |
| identity_asymmetry.md §3.4 | vanishing order structural origin | upstream |
| nt_genus_class_fields.md | genus quotient $\to$ quadratic subcharacters | upstream |
| number_theory_dictionary_v0.md §5 | case log consumer | downstream |
| brauer_closure_galois_classification_v0.md | tier classification consumer | downstream |
| OQ-NT-7 / OQ-NT-8 | tier theory $\to$ factorization patterns | downstream |
| nt_root_numbers.md §1-5 | $W(\rho)$ detailed calculus, magnitude/sign split | lateral |

---

## §7 Modular L countably-infinite Path 2 family (Paper N3 §3.3, 2026-04-26)

### §7.0 動機

§4 (Functional Equation) は数体 K の Dedekind ζ_K と Artin L(s, ρ, K/k) に対する functional equation の **completed L-function 形式** + **functional equation identity** を formal にした。本 §7 は functional equation の **fixed point structure** を Path 2 class instance として整理する。Paper N3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md` §3.3) で OQ-Ω-Schumann v1 (`research/oq_omega_schumann_v0.md`, 13/13 gates PASS) base に確立された **modular L weight-parametrization countably-infinite family** が本 §7 の主要 content。

### §7.1 Modular L family の Path 2 instance status

各 cusp newform $f \in S_k(\Gamma_0(N), \chi)$ (weight $k$, level $N$, character $\chi$) は **completed L-function**

$$\Lambda(f, s) = N^{s/2} (2\pi)^{-s} \Gamma(s) L(f, s)$$

を持ち、**functional equation**

$$\Lambda(f, s) = \varepsilon(f) \cdot \Lambda(\tilde{f}, k - s)$$

($\tilde{f}$ = $f$ の complex conjugate dual newform, $\varepsilon(f) \in \mathbb{C}$, $|\varepsilon(f)| = 1$) を満たす。**involution** $\sigma_k : s \mapsto k - s$ は $\sigma_k^2 = \mathrm{id}$ で **central fix point** $s = k/2$ を持つ。

→ 各 $(k, N, f)$ tuple が **独立 Path 2 instance** を提供する。

### §7.2 Weight-level-newform 列挙による countably-infinite cardinality

Path 2 class member の cardinality を weight × level × newform 列挙で評価:

| weight $k$ | functional eq. | central fix $s = k/2$ | instance example |
|---|---|---|---|
| 1 | $\Lambda(s, \chi) = \varepsilon \cdot \Lambda(1-s, \bar\chi)$ | 1/2 | Dirichlet L (real χ); ζ when χ = χ_0 trivial |
| 2 | $\Lambda(f, s) = \varepsilon \cdot \Lambda(f, 2-s)$ | 1 | weight-2 newform (e.g., $f_{11}$ of $X_0(11)$, BSD curves) |
| 4 | $\Lambda(f, s) = \varepsilon \cdot \Lambda(f, 4-s)$ | 2 | weight-4 newforms |
| 6 | $\Lambda(f, s) = \varepsilon \cdot \Lambda(f, 6-s)$ | 3 | weight-6 newforms |
| 12 | $\Lambda(\Delta, s) = \varepsilon \cdot \Lambda(\Delta, 12-s)$ | 6 | Ramanujan $\Delta$ on $\mathrm{SL}(2, \mathbb{Z})$ |
| ... | $\Lambda(f, s) = \varepsilon \cdot \Lambda(\tilde{f}, k-s)$ | $k/2$ | each weight $k \geq 1$ |

**Cardinality 評価**:
- 各 weight $k$ で $S_k(\Gamma_0(N), \chi)$ の dimension は finite (Riemann-Roch on $X_0(N)$)
- level $N$ は $\mathbb{Z}_{\geq 1}$ 全体を range
- weight $k$ も $\mathbb{Z}_{\geq 1}$ 全体を range
- 各 $(k, N)$ で newforms 個数 finite だが nonzero

→ Path 2 instance cardinality $\geq \aleph_0$ (countably-infinite)。

### §7.3 ζ singleton-class category error の解消

**従来 framework での扱い**: Paper C / Paper N2 で "Path 2 = ζ functional equation singleton" と暗黙に扱われていた。Path 2 mechanism は ζ 固有の現象として framework 内で位置付けられていた。

**Paper N3 §3.3 訂正**: ζ は Path 2 unique instance ではなく、**最小 weight (k = 1) trivial character case の最小例**。Path 2 abundant family の specific configuration:
- $k = 1$: weight-1 (= Dirichlet L)
- $\chi$ = trivial character: ζ = $L(s, \chi_0)$
- $N = 1$: level 1 (trivial level)

Path 2 mechanism (Z/2 involution + invariant + non-empty fix) は **NT 内に countably-infinite に存在する** family の predicate であり、ζ は specific element に過ぎない。

### §7.4 §1 Artin factorization との関係

§1 で示した Artin factorization $\zeta_H(s) = \prod_\rho L(s, \rho)^{\dim \rho}$ は、各 $L(s, \rho)$ が **independent Path 2 instance** であることを implicit に主張している:

- 各 $\rho \in \widehat{G}$ (irreducible representation of $G = \mathrm{Gal}(H/k)$) で $L(s, \rho)$ は own functional equation を持つ
- functional equation の involution $\sigma_\rho : s \mapsto 1 - s$ (Artin L) または $s \mapsto k - s$ (modular L)
- fix point は each weight に依存する specific value

**従って**: §1 Artin factorization は Path 2 family の **product structure を具体化**: $\zeta_H = \prod_\rho L(s, \rho)^{\dim \rho}$ は countably-infinite family member の product として書かれる。

### §7.5 §4 Functional equation との関係

§4.2 で示した completed L-function functional equation $\Lambda(s, \rho, K/k) = W(\rho) \Lambda(1-s, \bar\rho, K/k)$ は、本 §7 で **Path 2 predicate**:
- (1) involution: $s \mapsto 1 - s$ (Artin L) または $s \mapsto k - s$ (modular L) — Z/2 group action satisfied
- (2) invariant: $|\Lambda(s, \rho)|^2$ — functional equation under involution
- (3) non-empty fix: $s = 1/2$ (Artin) または $s = k/2$ (modular) — central fix existence

を全 Artin / modular L family member で **automatic に satisfy する**。

### §7.6 Type α/β/γ trichotomy (Schumann v1 NEW finding 2)

Path 2 instance の fix-point realization は 3 type 分類 (`research/oq_omega_schumann_v0.md` v1):

- **Type α** (physical): fix が同 algebraic object 内 single point。modular L (each weight k) は all Type α (fix s = k/2 が complex plane 内 specific point)
- **Type β** (shadow): fix が異 object 内 single rep。NT context では rare (Path 2 NT instances は ほぼ all α)
- **Type γ** (sub-object): fix が同 object 内 sub-object。**Atkin-Lehner W_N on $S_k(\Gamma_0(N))$** が NT context での Type γ instance — fix が $S_k^+ \subset S_k$ eigenspace (Petersson +1 eigenspace, point fix でない)

**Atkin-Lehner involution** (level $N$ で $q | N$ の prime $q$ に対する):

$$W_q = \begin{pmatrix} 0 & -1 \\ N & 0 \end{pmatrix} \text{ acts on } S_k(\Gamma_0(N))$$

$W_q^2 = (-1)^k N \cdot \mathrm{id}$ で even weight $k$ では $W_q^2 = \mathrm{id}$ (modulo scalar)、order-2 involution。Petersson inner product 不変、$S_k = S_k^+ \oplus S_k^-$ eigenspace decomposition、$S_k^+$ = +1 eigenspace = Type γ fix sub-object。

### §7.7 Scope と検証

**提供するもの**:
- Modular L family の Path 2 instance status (§7.1, §7.2)
- ζ singleton-class category error 解消 (§7.3)
- §1 Artin factorization と §4 Functional equation の Path 2 lens 再読み (§7.4-§7.5)
- Type α/β/γ trichotomy の NT instance specification (§7.6)

**提供しないもの** (scope 外):
- 各 newform $f$ の central L-value $L(f, k/2)$ の具体計算 (BSD-type, LMFDB consumer)
- Atkin-Lehner involution の sub-object fix が canonical scalar D1-D4 のどれに hit するか具体検証 (Paper N3 §5.2 で完了済)
- Fi-origin vs I-origin canonical scalar 二分法 (`c_arrow_bridge_constants.md §11` に residence)
- Falsification gates F1-F4 (Paper N3 §6, `research/oq_omega_schumann_v0.md` v1 G13 主体)

**Status**: candidate_v1 (Schumann v1 13/13 gates PASS, ESTABLISHED PENDING v1.5 完了 — Type γ formal definition + 6th pre-registered instance)。Paper N3 v0.2 (2026-04-26) で publication 整備、N4 (Hasse-Weil L) で elliptic curve / abelian variety への extension expected。

**Ref**:
- Paper N3 §3 (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`)
- `research/oq_omega_schumann_v0.md` v1 (主体)
- `c_theorems_master.md` "Path 2 countably-infinite family" annex (本 §7 の cross-domain summary)
- `c_arrow_bridge_constants.md §11` (Fi-origin vs I-origin canonical scalar 二分法)

---

*作成日: 2026-04-10*
*作成トリガー: D₄/Q₈ 数値検証で ζ_H = ∏ L(s,ρ)^{dim ρ} と ζ_F permutation character 分解が research 側に散在。OQ-NT-7/8 の根を太くするための L1 structural residence。*
*§7 追加: 2026-04-26 (Paper N3 v0.2 modular L countably-infinite annex)*
