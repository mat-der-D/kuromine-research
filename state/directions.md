# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered in Session 1 (2026-06-25).** For all Theorem 5 solutions, $y = 3j$ and the equation factors as $(z-w)(z^2+zw+w^2) = 2^x + 5$ with $\gcd = 1$ and $z^2+zw+w^2$ having only prime factors $\equiv 1 \pmod 3$. This is a norm form equation in $\mathbb{Z}[\omega]$ (Eisenstein integers). Key sub-questions:
- (a) Can we apply Thue-Mahler machinery to $z^3 - w^3 = 2^x + 5$ with $w = 3^j$?
- (b) Does the norm form $N(z - \omega w) = B \mid 2^x + 5$ impose new constraints on $z$ modulo primes $\equiv 1 \pmod 3$?
- (c) Is there a descent via the Eisenstein integer ring that links back to the original equation?

### [HIGH] $p$-adic analysis of the phantom solution

The phantom solution $(5, -3, 10/3)$ is a 3-adic obstruction. Understanding why integer solutions are different from the phantom in the 3-adic sense may be the key. **Session 1 result:** $v_3(z^3 - 37) = 4 + v_3(k)$ gives a concrete 3-adic constraint. However, the phantom (37 is a cubic residue mod $3^n$ for all $n$) blocks pure 3-adic elimination. The next step is p-adic Baker / Yu's theorem applied to $3^y = z^3 - 2^x - 5$.

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
