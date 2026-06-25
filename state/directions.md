# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered in Session 1 (2026-06-25).** For all Theorem 5 solutions, $y = 3j$ and the equation factors as $(z-w)(z^2+zw+w^2) = 2^x + 5$ with $\gcd = 1$ and $z^2+zw+w^2$ having only prime factors $\equiv 1 \pmod 3$. This is a norm form equation in $\mathbb{Z}[\omega]$ (Eisenstein integers). Key sub-questions:
- (a) Can we apply Thue-Mahler machinery to $z^3 - w^3 = 2^x + 5$ with $w = 3^j$?
- (b) Does the norm form $N(z - \omega w) = B \mid 2^x + 5$ impose new constraints on $z$ modulo primes $\equiv 1 \pmod 3$?
- (c) Is there a descent via the Eisenstein integer ring that links back to the original equation?

### [HIGH] Effective Diophantine approximation to $2^{1/3}$ (avoid paying height of $z$)

**Elevated in Session 2.** The cleanest reframing is $z^3 - 2^x = 3^y + 5$: a cube very
close to a power of 2 (gap $\log|\Lambda|\approx-47854$ for $\Lambda=3\log z-x\log2$).
Standard Matveev fails only because the unknown base $z$ has height $\approx76857$,
making the lower bound ($\approx-5.6\times10^{14}$) far too weak. The fix is a method
that does **not** pay the full height of $z$: an effective irrationality measure
$|2^{1/3} - p/q| > c/q^{\kappa}$ with $\kappa$ close to optimal, applied with $p/q$
related to $z/2^{\lfloor x/3\rfloor}$, or the arithmetic-holonomy / hypergeometric
bounds of Bennett and of arXiv:2510.04156 (2025). Sub-questions:
- (a) Translate $z^3 - 2^x = 3^y+5$ into an approximation $|2^{1/3}-p/q|$ and read off the
  exponent needed to force $3^y+5$ to be large, contradicting $3^y+5 \ll 2^x$.
- (b) What effective $\kappa$ for $2^{1/3}$ is currently known, and is it good enough?

### [LOW, ~RETIRED as standalone] $p$-adic analysis of the phantom solution

**Downgraded in Session 2.** The phantom $2^5+3^{-3}+5 = (10/3)^3$ is a *global rational
cube*, hence a cube modulo every prime $p\ne3$ and (constrained to 37) mod $3^n$ for all
$n$. The cube map is a bijection mod $2^n$ and mod $3^n$ on the relevant residues, so the
equation is **locally solvable at every prime**. Therefore no p-adic / congruence
argument can *alone* refute a solution — proven, not just observed. The p-adic
computations remain useful as auxiliary constraints feeding a global argument (e.g.
$z\equiv6\pmod{32}$, $v_3(z^3-37)=4+v_3(k)$), but p-adic elimination on its own is a
dead end. See `knowledge/references/two_adic_structure.md`. (Kept at LOW only because the
derived congruences support other directions.)

### [MEDIUM] Baker's method / linear forms in logarithms

**Session 1 assessment:** Matveev's bound is too weak for the Theorem 5 parameter range (minimum $x = 332645$, $y = 166317$). The bound allows $|\Lambda|$ to be as small as $\exp(-5.6 \times 10^{14})$, while the actual size is only $\exp(-47854)$. No contradiction. A refined version using Yu's p-adic Baker theorem might do better. Priority lowered pending literature search for better bounds.

### [MEDIUM] Elliptic curve approach (fix one variable)

Fixing $x = 5 + 332640k$ and studying $z^3 - 3^y = 2^x + 5$ as a family of curves. **Now linked to the factorization approach** above.

### [MEDIUM] Primitive divisor arguments (Zsygmondy)

May constrain the prime factorization of $z^3 - 5$ in ways that conflict with $2^x + 3^y$. **Connection found in Session 1:** The prime factors of $z^2+zw+w^2$ are all $\equiv 1 \pmod 3$. This is a primitive divisor-type constraint on the factorization of $2^x + 5$.

### [MEDIUM] Thue-Mahler equation approach

**New direction identified in Session 1.** The equation $z^3 - w^3 = N_k$ with $w = 3^j$ is a Thue-Mahler type equation. For each fixed $k$, $N_k = 2^{5+332640k} + 5$ is fixed, and the Thue-Mahler theorem gives finitely many solutions. The question is whether no solution exists for any $k \geq 1$.

**References:** arXiv:2207.14492 (Efficient resolution of Thue-Mahler equations).

### [LOW] Numerical search with Theorem 5 filtering

Verify computationally that no solutions exist for small $k$ (say $k \leq 5$). Not mathematically deep but can confirm the conjecture computationally and potentially reveal patterns in $2^x + 5 \pmod p$ for primes $p \equiv 1 \pmod 3$.

### [LOW] arXiv survey of exponential Diophantine equations

**Partially done in Session 1.** Found literature on Baker's method, S-unit equations, and Thue-Mahler equations. Next: search specifically for $z^3 - 3^y = C$ or $z^3 = 2^x + 3^y + C$ type results.

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.

---

## History of Changes

- **2026-06-25 (Session 1):** Added [HIGH] Factorization approach. Added [MEDIUM] Thue-Mahler equation approach. Lowered Baker's method assessment from [MEDIUM] to [MEDIUM-LOW] but kept at [MEDIUM] pending p-adic Baker investigation. Elevated $p$-adic direction to [HIGH] (tied). Noted Session 1 discoveries.
- **2026-06-25 (Session 2):** Downgraded standalone $p$-adic elimination from [HIGH] to [LOW/~RETIRED] after *proving* (not just observing) that local methods cannot obstruct the equation: the phantom is a global rational cube $(10/3)^3$, so every local condition is satisfiable. Added new [HIGH] direction "Effective Diophantine approximation to $2^{1/3}$" as the realistic global path. Completed the 2-adic structure analysis ($z\equiv6\pmod{32}$, $v_2(3^y+5)=3$). See `knowledge/references/two_adic_structure.md`.
