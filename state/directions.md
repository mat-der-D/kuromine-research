# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered in Session 1 (2026-06-25).** For all Theorem 5 solutions, $y = 3j$ and the equation factors as $(z-w)(z^2+zw+w^2) = 2^x + 5$ with $\gcd = 1$ and $z^2+zw+w^2$ having only prime factors $\equiv 1 \pmod 3$. This is a norm form equation in $\mathbb{Z}[\omega]$ (Eisenstein integers).

**Session 3 progress:**
- Clean equivalent single equation, with $A = z - 3^j$:
  $$2^x + 5 = A^3 + 3^{j+1}A^2 + 3^{2j+1}A = A\,(A^2 + 3^{j+1}A + 3^{2j+1}).$$
  Brute force ($x\le40$) recovers BOTH known solutions, each with **$A = z-3^{y/3} = 1$**.
- Eisenstein-norm identity $4B - 3w^2 = (2z+w)^2$ (verified on $(5,3,4)$: $148-27=121$).
- **Negative:** the inert-prime condition ($q\equiv2\bmod3$, $q\mid2^x+5 \Rightarrow q\mid z-3^j$)
  is automatically consistent (gives $3^{3j}\equiv3^y\bmod q$, automatic since $y=3j$). So the
  factorization yields no new congruence — soft obstruction again.

Key sub-questions (remaining):
- (a) Can we apply Thue-Mahler machinery to the reduced equation $A(A^2+3^{j+1}A+3^{2j+1}) = 2^x+5$ for fixed $x$? (Finiteness per $x$ known; uniformity over the $x$-progression open.)
- (b) Can growth / primitive-divisor results (Zsygmondy, Bilu–Hanrot–Voutier) on $B = z^2+zw+w^2$ along the $x$-progression force a contradiction? **(elevated — see new MEDIUM-HIGH below)**
- (c) Can $A = z - 3^{y/3} = 1$ (true for both real solutions) be shown necessary? No mechanism known to bound $A$, so this is aspirational.

### [RETIRED in Session 3] Effective Diophantine approximation to $2^{1/3}$

**Elevated in Session 2, RETIRED in Session 3 with a proof.** The reframing
$z^3 - 4W^3 = 3^y+5$ ($W=2^a$, $x=3a+2$) makes $z/W$ a rational approximation to
$2^{2/3}$. The session computed (Wolfram, two independent ways) that this approach
*cannot* work:
- The realized approximation exponent is $\kappa_{\text{real}}\approx0.62<1$, far below
  any effective irrationality measure $\mu\ge2$. Irrationality measures are *lower*
  bounds; they only constrain *good* approximations ($\kappa\ge\mu$). $z/W$ is a *bad*
  approximation, so no measure (however sharp, including arXiv:2510.04156) gives
  information.
- As a Thue lower bound a contradiction needs $\log(3^y+5)<(3-\mu)\log\max(z,W)$, but
  LHS $\approx182718$, RHS $\approx43809$ ⟹ off by $+138909$. The form value $3^y+5$ is
  far too large.

**Root cause:** $3^y$ is *not* a small perturbation of $2^x$ — $\log3^y/\log2^a\approx2.38$,
so $3^y\approx z^2$. This is the "two comparable dominant S-units" regime, beyond any
single cubic irrationality measure. See
`knowledge/references/irrationality_measure_obstruction.md`. Moved toward dead_ends.

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

### [MEDIUM-HIGH] Primitive divisor / growth arguments (Zsygmondy, Bilu–Hanrot–Voutier)

**Elevated in Session 3** to the most promising *non-size-based* lead, since size methods
(Baker, irrationality measures) are now all shown too weak. The prime factors of
$B = z^2+zw+w^2$ are all $\equiv 1 \pmod 3$ (Session 1). The hope: as $x$ runs over the
progression $5+332640k$, the factor $B = (2^x+5)/(z-3^j)$ — a Lucas/Lehmer-type norm —
should acquire *primitive* prime divisors, and a primitive prime $p\equiv1\bmod3$ of $B$
imposes $z\equiv$ (cube-root data) mod $p$ that may clash with the 2-adic/3-adic
constraints ($z\equiv6\pmod{32}$, $v_3(z^3-37)=4+v_3(k)$). Caveat: any such argument must
*not* be purely local (the soft obstruction means it must use that $w=3^j$ is an integer
power, e.g. via a growth/size estimate on $B$ itself). Concrete first step: study
$v_p(z^2+zw+w^2)$ structure and whether a fixed small prime $\equiv1\bmod3$ can divide $B$
for ALL $k$ (which Zsygmondy-type results would forbid past a bounded range).

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
- **2026-06-25 (Session 3):** RETIRED "Effective Diophantine approximation to $2^{1/3}$" (was [HIGH]) with a proof that it is quantitatively dead: realized exponent $\kappa\approx0.62\ll\mu$, and the Thue value $3^y+5$ is too large by $\sim e^{138909}$ — root cause is the two-comparable-dominant-S-units regime ($3^y\approx z^2$). See `knowledge/references/irrationality_measure_obstruction.md`. Added Session-3 progress to the Factorization [HIGH] direction (reduced equation $2^x+5=A(A^2+3^{j+1}A+3^{2j+1})$, both real solutions have $A=z-3^{y/3}=1$, Eisenstein identity $4B-3w^2=(2z+w)^2$). Elevated primitive-divisor (Zsygmondy/BHV) direction to [MEDIUM-HIGH] as the best remaining non-size lead, since all size methods are now shown too weak.
