---
axis: A
position: algebra_analysis
static_dynamic: static
connected_to:
  - A.algebra_analysis
  - A.algebra_group
  - L.number_theory
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-10
runtime_summary:
  what: "Artin root numbers W(ρ), local epsilon factors, and the magnitude/sign residence split for L-function special values. Completes the functional-equation sign side left open by nt_dedekind_artin_zeta.md §4."
  when: "Q₈ sign determination, Tier √ residual analysis, functional equation sign constraints, self-dual representation parity"
  provides: [artin_root_number, local_epsilon_factor, epsilon_product_formula, magnitude_sign_split, sign_residence_principle, orthogonal_sign_freedom, symplectic_sign_forced]
  consumes:
    - "nt_dedekind_artin_zeta.md §4 (functional equation, Λ(s,ρ), W(ρ) definition)"
    - "nt_frobenius_schur.md §1-3 (FS indicator, pairing type, orthogonal/symplectic trichotomy)"
    - "nt_conductor.md §6.2 (Artin conductor local formula)"
  axis: [A]
  residual_types: [R-gauge]
  cost: small
  status: established
  key_theorems:
    - {id: epsilon_product, statement: "W(ρ) = ∏_v W_v(ρ,ψ_v,dx_v) where the product is over all places and depends on local additive character ψ_v and Haar measure dx_v, but the global product is independent of these choices", derived_in: "§2", status: established}
    - {id: symplectic_root_number, statement: "ν(ρ)=-1 (symplectic self-dual) implies W(ρ)=+1", derived_in: "§3.2", status: established}
    - {id: magnitude_sign_split, statement: "For self-dual ρ: field data (units, regulators, class numbers) determine |L(0,ρ)| or L(0,ρ)²; root number W(ρ) determines sign(L(0,ρ)). These are independent data sources.", derived_in: "§4", status: established}
  one_screen: |
    - §1: Root number definition — W(ρ) ∈ S¹ from functional equation Λ(s,ρ) = W(ρ)Λ(1-s,ρ̄). Self-dual ρ forces W(ρ) ∈ {±1} (orthogonal) or W(ρ)=+1 (symplectic).
    - §2: Local-to-global product — W(ρ) = ∏_v W_v(ρ). Archimedean factors explicit, finite ramified factors via conductor exponent + Gauss sum.
    - §3: Reality type constraints — FS indicator determines which sign constraints apply. Symplectic forced +1 (Deligne). Orthogonal sign free, carries arithmetic information.
    - §4: Magnitude/sign residence split — unit/regulator/class-number data give magnitude; root number gives sign. Independent data sources, independent dictionary residences.
    - §5: Q₈ worked example — L(0,ρ)²=16 from field data, L(0,ρ)=±4 sign from W(ρ). The sign is the Tier √ residual.
    - §6: Scope boundary — what lives here vs nt_frobenius_schur.md vs nt_dedekind_artin_zeta.md.
---

# Root Numbers and Epsilon Factors

**Level**: L1 (pure mathematics, analytic number theory)
**Dependencies**: `nt_dedekind_artin_zeta.md` §4 (functional equation), `nt_frobenius_schur.md` §1-3 (FS indicator, pairing type), `nt_conductor.md` §6.2 (Artin conductor)
**Downstream**: OQ-NT-8 (Tier √ sign resolution), `number_theory_dictionary_v0.md` §5.5 (Q₈ case log)

---

## §1 Root Number

### §1.1 Definition

From the functional equation (nt_dedekind_artin_zeta.md §4.2):

$$\Lambda(s, \rho) = W(\rho)\, \Lambda(1-s, \bar\rho)$$

the **Artin root number** $W(\rho) \in \mathbb{C}$ satisfies $|W(\rho)| = 1$.

Applying the equation twice: $W(\rho)\, W(\bar\rho) = 1$.

### §1.2 Self-Dual Constraints

When $\rho \cong \bar\rho$ (self-dual), $W(\rho)^2 = 1$, so $W(\rho) \in \{+1, -1\}$.

Self-duality is detected by the character: $\rho$ is self-dual iff $\chi_\rho$ is real-valued. This holds for both orthogonal ($\nu = +1$) and symplectic ($\nu = -1$) types.

### §1.3 Non-Self-Dual Case

When $\rho \not\cong \bar\rho$ ($\nu = 0$, complex type), $W(\rho)$ can be any element of $S^1$. However, $\rho$ and $\bar\rho$ always appear as a pair in zeta factorizations (nt_dedekind_artin_zeta.md §1.2), so the product $L(s, \rho) \cdot L(s, \bar\rho)$ has real coefficients and real special values.

---

## §2 Local-to-Global Product

### §2.1 Epsilon Factor Decomposition

$W(\rho)$ factors as a product of **local epsilon factors**:

$$W(\rho) = \prod_{v} W_v(\rho, \psi_v, dx_v)$$

where:
- $v$ ranges over all places of $k$ (archimedean and non-archimedean)
- $\psi_v$ is a local additive character
- $dx_v$ is a local Haar measure

Each local factor $W_v$ depends on the choices of $\psi_v$ and $dx_v$, but the global product is independent of these choices (Tate's thesis / Langlands normalization).

### §2.2 Archimedean Factors

For real place $v$:
- $\rho(c_v) = +1$ (complex conjugation acts trivially): $W_v = 1$
- $\rho(c_v) = -1$ (complex conjugation acts by $-1$): $W_v = i$

For complex place $v$: $W_v = i^{-\dim\rho}$ (standard normalization).

**Consequence**: The archimedean contribution to $W(\rho)$ is a power of $i$, determined by the signature $(r_1, r_2)$ and the action of complex conjugation on $\rho$.

### §2.3 Non-Archimedean Factors

For unramified $v$: $W_v = 1$.

For ramified $v$ (with conductor exponent $f_v(\rho) > 0$, see nt_conductor.md §6.2):

$$W_v(\rho) = \frac{\varepsilon_v(\rho)}{\left|\varepsilon_v(\rho)\right|}$$

where $\varepsilon_v(\rho)$ involves a local Gauss-sum-type integral over the ramification filtration. The key structural point: only finitely many places contribute nontrivially, and each is controlled by the local Artin conductor.

### §2.4 Conductor-Root Number Coupling

The Artin conductor $\mathfrak{f}(\rho) = \prod_\mathfrak{p} \mathfrak{p}^{f_\mathfrak{p}(\rho)}$ determines **which** primes contribute local epsilon factors. The conductor measures the **amount** of ramification; the local epsilon factor encodes the **orientation** of ramification.

This is a structure/sign split at the local level, parallel to the global magnitude/sign split (§4).

---

## §3 Reality Type Constraints

### §3.1 The Three Cases

| FS indicator $\nu(\rho)$ | Self-dual? | $W(\rho)$ constraint | Source |
|---|---|---|---|
| $+1$ (orthogonal) | yes | $W(\rho) \in \{+1, -1\}$ | $W(\rho)^2 = 1$ |
| $0$ (complex) | no | $W(\rho) \in S^1$ arbitrary | $\rho \neq \bar\rho$ |
| $-1$ (symplectic) | yes | $W(\rho) = +1$ forced | Deligne (§3.2) |

### §3.2 Symplectic Root Number = +1 (Deligne)

**Theorem (Deligne)**: If $\rho$ is symplectic ($\nu(\rho) = -1$), then $W(\rho) = +1$.

**意義**: For the Tier √ obstruction (nt_frobenius_schur.md §3.2), this means:
- The functional equation does **not** force a sign ambiguity on $L(s, \rho)$ for symplectic $\rho$.
- The obstruction is not that $W(\rho)$ is unknown; it is that extracting $L(0, \rho)$ from field data requires a square root (the zeta ratio gives $L(0, \rho)^2$, not $L(0, \rho)$).
- The sign of $L(0, \rho)$ is well-defined ($W(\rho) = +1$ ensures the functional equation is consistent), but **accessing** it requires epsilon-factor computation, not unit-group data.

### §3.3 Orthogonal Sign Freedom

For orthogonal $\rho$ ($\nu(\rho) = +1$), $W(\rho) \in \{+1, -1\}$ and the sign carries genuine arithmetic content:

- $W(\rho) = +1$: $L(1/2, \rho)$ is unconstrained by the functional equation.
- $W(\rho) = -1$: the functional equation forces $L(1/2, \rho) = 0$ (odd vanishing).

This parity phenomenon connects to the Birch-Swinnerton-Dyer conjecture for elliptic curves (where the relevant $\rho$ is orthogonal and the sign of $W$ predicts the parity of the Mordell-Weil rank).

---

## §4 Magnitude/Sign Residence Split

### §4.1 The Principle

For a self-dual $\rho$ in the Artin factorization of $\zeta_H$ (nt_dedekind_artin_zeta.md §1.2):

| Datum | Source | Dictionary residence |
|---|---|---|
| $|L(0, \rho)|$ or $L(0, \rho)^2$ | Field arithmetic: $h$, $R$, $w$, intermediate zeta ratios | `nt_relative_units.md`, `c_spectral.md §8` |
| $\mathrm{sign}(L(0, \rho))$ | Root number $W(\rho)$, computed via local epsilon factors | **this entry** |

These two data sources are **independent**:
- The magnitude comes from the class number formula and regulator computations (orthogonal objects).
- The sign comes from the functional equation and local Gauss sums (orientation objects).

### §4.2 Why the Split Is Intrinsic

The magnitude/sign independence is not an artifact of computation method. It reflects the structural fact that:

1. The regulator $R_K$ and class number $h_K$ are defined via lattice volumes and group orders — inherently non-negative.
2. The root number involves Gauss sums and local signs — inherently phase/orientation data.
3. When $\rho$ is extracted via zeta ratios (Tier 1/2), the ratio cancels some sign information; the remaining sign resides in the epsilon factor product.

### §4.3 Tier Classification Interaction

| Tier | Magnitude access | Sign access |
|---|---|---|
| Tier 1 strict | $L(0, \rho) = \zeta_F^*(0) / \zeta_k^*(0)$; direct ratio | Sign determined by the ratio (no residual) |
| Tier 2 relaxed | $L(0, \rho) = \zeta_{F_1}^*(0) / \zeta_{F_2}^*(0)$; two-field ratio | Sign from two leading coefficients (usually determined) |
| Tier √ impossible | $L(0, \rho)^2$ only from field data | Sign requires $W(\rho)$ computation = **root number residual** |

For Tier √, the root number is the **last datum** needed to resolve $L(0, \rho)$ from $L(0, \rho)^2$. This is the precise sense in which nt_root_numbers.md "closes" the Tier √ obstruction chain opened by nt_frobenius_schur.md.

---

## §5 Q₈ Worked Example

### §5.1 Setup

(From nt_frobenius_schur.md §4.4 and number_theory_dictionary_v0.md §5.5)

$H/\mathbb{Q}$ with $\mathrm{Gal}(H/\mathbb{Q}) \cong Q_8$, LMFDB `8.0.12230590464.1`.
$\rho$: unique 2-dimensional irreducible, $\nu(\rho) = -1$ (symplectic).

### §5.2 Magnitude from Field Data

The Artin factorization (nt_dedekind_artin_zeta.md §5.3) gives

$$\zeta_H(s) = \zeta_\mathbb{Q}(s) \cdot L(s, \chi_i) \cdot L(s, \chi_j) \cdot L(s, \chi_k) \cdot L(s, \rho)^2$$

From class number formula data:

$$L(0, \rho)^2 = \frac{h_H R_H / w_H}{R_{\sqrt{2}} R_{\sqrt{3}} R_{\sqrt{6}} / 2} = 16$$

This is a **complete** determination of the square.

### §5.3 Sign from Root Number

By Deligne's theorem (§3.2): $W(\rho) = +1$ since $\nu(\rho) = -1$.

Therefore the functional equation is consistent with both $L(0, \rho) = +4$ and $L(0, \rho) = -4$, and does **not** force a zero at $s = 0$.

The sign is determined by the local epsilon factor product:

$$\mathrm{sign}(L(0, \rho)) = \prod_{v} \mathrm{sign}_v$$

where the nontrivial contributions come from the ramified primes of $H/\mathbb{Q}$. This computation requires explicit knowledge of the higher ramification filtration at each prime dividing $\mathrm{disc}(H)$.

**Current status**: $L(0, \rho) = \pm 4$ undetermined. Resolution requires either:
1. Direct epsilon factor computation from the ramification data of `8.0.12230590464.1`, or
2. Numerical computation of $L(0, \rho)$ via LMFDB / Dokchitser's algorithm.

### §5.4 Residence Summary for Q₈

| Component | Value | Determined by | Dictionary residence |
|---|---|---|---|
| $L(0, \rho)^2$ | $16$ | $h_H, R_H, w_H$ + subfield data | `c_spectral.md §8`, `nt_relative_units.md` |
| $\nu(\rho)$ | $-1$ | Character table + power map | `nt_frobenius_schur.md §1` |
| $W(\rho)$ | $+1$ | Deligne's theorem ($\nu = -1 \Rightarrow W = +1$) | **this entry §3.2** |
| $\mathrm{sign}(L(0, \rho))$ | $\pm 1$ (open) | Local epsilon factors at ramified primes | **this entry §2.3** |
| $L(0, \rho)$ | $\pm 4$ (open) | magnitude $\times$ sign | resolved when sign computed |

---

## §6 Scope

### §6.1 This Entry Provides

- Definition and properties of Artin root numbers $W(\rho)$.
- Local-to-global epsilon factor decomposition (structural, not computational).
- Reality type constraints: orthogonal sign freedom, symplectic forced $+1$.
- The magnitude/sign residence split as a dictionary principle.
- Q₈ worked example showing the split in action.

### §6.2 This Entry Does Not Provide

- Explicit local epsilon factor computation algorithms (Dokchitser, Rohrlich). → research/ or L2.
- Elliptic curve root numbers or BSD parity predictions. → future L1 if needed.
- $p$-adic epsilon factors or Iwasawa-theoretic refinements. → out of current scope.
- The actual sign determination for the Q₈ LMFDB example. → L2 case log or research/.

### §6.3 Connection Table

| Connection | Role | Direction |
|---|---|---|
| `nt_dedekind_artin_zeta.md` §4 | functional equation, $\Lambda(s,\rho)$, $W(\rho)$ definition | upstream |
| `nt_frobenius_schur.md` §1-3 | FS indicator determines sign constraint type | upstream |
| `nt_conductor.md` §6.2 | Artin conductor determines which primes contribute $W_v$ | upstream |
| `c_spectral.md` §8 | class number formula provides magnitude side | lateral |
| `nt_relative_units.md` §2-3 | regulator provides magnitude side | lateral |
| `number_theory_dictionary_v0.md` §5.5 | Q₈ case log consumer | downstream |
| OQ-NT-8 | Tier √ sign resolution | downstream |
| `research/brauer_closure_galois_classification_v0.md` | classifier sign module | downstream |

---

*作成日: 2026-04-10*
*作成トリガー: Q₈ L(0,ρ)=±4 の sign の辞書的居場所が不在。nt_frobenius_schur.md が「sign は root-number datum」と宣言しているが、root number 自体の residence が無かった。nt_dedekind_artin_zeta.md §4 (factorization side) と対をなす functional-equation sign side。*
