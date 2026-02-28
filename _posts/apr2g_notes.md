# Antisymmetrized Product of Rank-Two Geminals (APr2G)

## Mathematical Notes and Intuition

This note summarizes the key mathematical ideas behind the antisymmetrized product of rank-two geminals (APr2G) introduced by Johnson et al.
in the paper [A size-consistent approach to strongly correlated systems using a generalized antisymmetrized product of nonorthogonal geminals](https://doi.org/10.1016/j.comptc.2012.09.030).
Goals:

- Understand why permanents appear in APIG.
- See why they are computationally hard.
- Understand how Borchardt’s theorem converts permanents into determinants.
- See how this leads to the APr2G ansatz.
- Clarify connections to AGP, APSG, Richardson states, and projected HFB.

---

## 1. APIG Wavefunction

The antisymmetrized product of interacting geminals (APIG) is

$$ | \Psi \rangle =
\prod_{p=1}^{P}
\left(
\sum_{i=1}^{K}
c_{i,p}
a_i^\dagger a_{\bar{i}}^\dagger
\right)
|0\rangle
$$

where

- $P$ = number of electron pairs  
- $K$ = number of spatial orbital pairs  
- $c_{i,p}$ = geminal coefficients  
- $a_i^\dagger a_{\bar{i}}^\dagger$ creates a singlet pair in orbital $i$

Because electrons are fermions,

$$
(a_i^\dagger a_{\bar{i}}^\dagger)^2 = 0
$$

so each orbital pair can be occupied at most once. Therefore,

$$
P \le K
$$

---

## 2. Expansion into Slater Determinants

Choose a Slater determinant where orbital pairs

$$
\{ i_1, i_2, \dots, i_P \}
$$

are occupied.

Each geminal must choose one of these orbitals.

There are $P!$ possible assignments:

- geminal 1 chooses $i_{\sigma(1)}$
- geminal 2 chooses $i_{\sigma(2)}$
- ...
- geminal $P$ chooses $i_{\sigma(P)}$

where $\sigma$ is a permutation.

The determinant coefficient becomes

$$
\sum_{\sigma}
\prod_{p=1}^{P}
c_{i_{\sigma(p)},p}
$$

This is exactly the **permanent** of a matrix.

---

## 3. Why the Matrix is P x P

For a fixed determinant:

- Rows correspond to geminals $p = 1, \dots, P$
- Columns correspond to the $P$ occupied orbital pairs

The coefficient matrix has dimension

$$
P \times P
$$

The Slater determinant coefficient is

$$
\mathrm{perm}(C)
$$

---

## 4. Why Permanent (Not Determinant)

Pair creation operators commute:

$$
\hat g_i^\dagger \hat g_j^\dagger =
\hat g_j^\dagger \hat g_i^\dagger
$$

Swapping two geminals does not introduce a minus sign.

Therefore we get a permanent, not a determinant.

---

## 5. Computational Difficulty

Permanent evaluation scales as

$$
\mathcal{O}(P!)
$$

This is #P-hard.

General APIG is therefore computationally intractable.

---

## 6. The Key Idea: Cauchy Structure

Johnson et al. impose the special form

$$
c_{i,p} = \frac{1}{e_i - k_p}
$$

This is a **Cauchy matrix**.

For a Cauchy matrix $C$, Borchardt’s theorem states

$$
\mathrm{perm}(C) =
\frac{\det(C \circ C)}{\det(C)}
$$

where

- $C \circ C$ is the elementwise square
- determinants are polynomial-time computable

Thus,

Permanent -> ratio of determinants

This reduces exponential scaling to polynomial scaling.

---

## 7. Pfaffians and Hafnians

The discussion connects to broader pairing algebra.

Determinant:
- Appears with antisymmetry (fermions)
- Used in Slater determinants

Permanent:
- Appears with commuting objects
- Appears in APIG

Pfaffian:
- Defined for antisymmetric matrices
- Satisfies

$$
\mathrm{Pf}(A)^2 = \det(A)
$$

- Appears in BCS and Pfaffian QMC wavefunctions

Hafnian:
- Bosonic analogue of Pfaffian
- Counts pairings without antisymmetry
- Appears in bosonic Gaussian states

Conceptually:

Determinant -> fermions  
Permanent -> boson-like pairing  
Pfaffian -> fermionic pairing  
Hafnian -> bosonic pairing  

APr2G sits inside this broader pairing structure.

---

## 8. Final APr2G Wavefunction

With the Cauchy parametrization:

$$
|\Psi_{\mathrm{APr2G}}\rangle =
\prod_{p=1}^{P}
\left(
\sum_{i=1}^{K}
\frac{1}{e_i - k_p}
a_i^\dagger a_{\bar{i}}^\dagger
\right)
|0\rangle
$$

The Slater determinant coefficients become

$$
\phi_{\{i\}} =
\frac{\det(C \circ C)}{\det(C)}
$$

This makes the ansatz polynomially tractable.

---

## 9. Hierarchy and Connections

APr1G = AGP

If

$$
c_{i,p} = f_i
$$

(all geminals identical), we obtain the antisymmetrized geminal power (AGP).

---

AGP -> Slater determinant

If only $P$ orbitals have nonzero $f_i$, AGP reduces to a single Slater determinant.

---

APr2G -> APSG

If parameters separate into orbital blocks, geminals become strongly orthogonal and we recover APSG.

---

APr2G -> Richardson wavefunction

If $k_p$ satisfy Richardson equations, APr2G reproduces exact pairing Hamiltonian eigenstates.

---

AGP <-> Projected HFB

AGP is equivalent to number-projected Hartree-Fock-Bogoliubov theory.

Hierarchy:

Slater
  subset AGP
    subset APr2G

---

## 10. Why This Paper Matters

- Makes nonorthogonal geminals computationally feasible.
- Uses Borchardt’s theorem to bypass permanent scaling.
- Unifies AGP, APSG, Richardson, and projected HFB.
- Provides size-consistent polynomial scaling.
- Connects quantum chemistry and integrable pairing models.

---
