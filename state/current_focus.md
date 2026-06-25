# Current Focus

**Session:** 20260625_(Session 3)

**Current direction (Session 3):** Concretely tested the [HIGH] "effective irrationality
measure for 2^(1/3)" direction. Reframed `z^3 - 2^x = 3^y+5` as a rational approximation
`z/2^a` to `α = 2^(2/3) = 4^(1/3)` (using `x ≡ 2 mod 3`, so `2^x = 4·(2^a)^3`), via an
**exact identity** (Wolfram-verified). Plugged in Bennett's best-known measure
(`κ ≈ 2.4325`).

**Headline result (Session 3):** Bennett's measure **proves no Theorem-5 solution exists
with `x > 8.3787 y`** (the 2^x-dominant tail) — a genuine, rigorous reduction. But it is
provably a *partial* tool: even an optimal measure (`κ → 2`) only reaches `x > 4.7549 y`,
so the region `x ≤ 4.755 y` (containing the whole balanced & 3^y-dominant regime) is out of
reach of any single-cube-root approximation. The method is structurally one-sided because
`y = 3j` makes `3^y` an exact cube (`z/3^j → 1` rational — no fixed irrational to
approximate). Full write-up: `knowledge/references/irrationality_measure_approach.md`.

**Previous direction (Session 2):** Establishing that local methods are *provably*
insufficient (phantom is a global rational cube), redirecting to global/size methods.
Completed the 2-adic mirror of the Session-1 3-adic analysis.

**Why this direction:** Session 1 left open whether some refined p-adic argument could break the phantom obstruction. Session 2 settled this: the phantom $2^5+3^{-3}+5 = (10/3)^3$ is a *global rational cube*, so the equation is locally solvable at every prime. No congruence/p-adic argument can ever obstruct it. The realistic path forward is effective Diophantine approximation that does not pay the full height of $z$.

**Why this direction (historical, Session 1):** Discovered in Session 1 that y is always divisible by 3 for Theorem 5 solutions, enabling a norm-form factorization. This gives a new structural constraint (all prime factors of $z^2+zw+w^2$ are $\equiv 1 \pmod 3$) and connects to the Thue-Mahler equation literature.

**What has been tried so far in this direction:**
- Proved $y \equiv 0 \pmod 3$ from $y \equiv -3 \pmod{166320}$.
- Proved $j = y/3 \equiv 2 \pmod 3$.
- Proved $\gcd(z-w, z^2+zw+w^2) = 1$.
- Proved all prime factors of $z^2+zw+w^2$ are $\equiv 1 \pmod 3$ (norm form argument).
- Computed $v_3(z^3 - 37) = 4 + v_3(k)$ via LTE.
- Computed parity constraints: $z \equiv 6 \pmod 8$, $z-w \equiv 3 \pmod 8$, $z^2+zw+w^2 \equiv 7 \pmod 8$.
- Assessed Baker's method: Matveev bound too weak for these parameter sizes.
- Identified S-unit equation / Thue-Mahler connection.

**Blockers:**
- The factorization $A \cdot B = 2^x + 5$ with $A \approx z$ and $B \approx z^2$ is very unbalanced. The "small factor" approach doesn't directly yield contradictions.
- Baker's method gives no contradiction (bounds are not tight enough).
- p-adic phantom obstruction (37 cubic residue mod $3^n$ for all $n$) blocks direct 3-adic elimination.

**Session 2 additions:**
- Proved $v_2(3^y+5) = 3$ constant on the entire Theorem-5 family ⟹ $v_2(z) = 1$ exactly ⟹ $z \equiv 6 \pmod{32}$ (sharper than Session-1 $z\equiv6\pmod8$). See `knowledge/references/two_adic_structure.md`.
- Established the **soft-obstruction principle**: cube map is a bijection mod $2^n$ and mod $3^n$ (for the relevant residues), and the phantom is a global rational cube $(10/3)^3$. Hence the equation is locally solvable at every prime — no p-adic/congruence method can ever refute a solution. This *retires the hope* that a refined p-adic argument alone could work.
- Size landscape: $2^x$ dominates $3^y$ by $e^{47854}$; $z/w \approx e^{15951}$. The factorization $(z-w)(z^2+zw+w^2)$ is maximally unbalanced — both factors large — so the "small factor" idea is void.
- Confirmed by brute force: only $(1,0,2)$ and $(5,3,4)$ for $x\le40, y\le30$.

**Session 3 additions:**
- Exact identity `z/2^a - α = D/(2^(3a)·(…)) ` with `α=4^(1/3)`, `D=3^y+5`, verified in
  Wolfram. So `z/2^a` approximates `2^(2/3)` with exponent `κ_actual = 3 - logD/logq`,
  `logD = y log3`, `logq = a log2 = (x-2)/3 · log2`.
- Contradiction iff `κ_actual > κ_thm`, i.e. `y < ((3-κ)/3)(log2/log3)(x-2)`. With Bennett
  `κ=2.4325` ⟹ `x > 8.3787 y` eliminated. Best-possible `κ=2` ⟹ only `x > 4.7549 y`.
- Practical handle for the next step: in the *surviving* region `x ≤ 8.379 y`, the height of
  `z` is bounded by `log z = (x/3) log2 ≲ (8.379/3) y log2`, tying `height(z)` to `y`. This
  is the most concrete reduction of the height-of-`z` blocker noted in Sessions 1–2.

**Notes (still open from Session 1):**
- Thue-Mahler connection: apply Baker-type bounds to $z^3 - w^3 = N_k$ for explicit bounds on $z,j$ in terms of $N_k = 2^x+5$ (still the best concrete lead).
- The realistic global tool: effective irrationality measure for $2^{1/3}$ / arithmetic-holonomy bounds (arXiv:2510.04156), which avoid paying the full height of $z$.
- Literature: still want treatments of $z^3 - 3^y = C$ or $z^n - a^m = C$ specifically.
