# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization + divisor sieve of the open region (NEW, 2026-06-24)
In the open region $y\equiv0\pmod3$, so $3^y=v^3$ ($v=3^{y/3}$) and the equation factors:
$(z-v)(z^2+zv+v^2)=2^x+5$ with the two factors **coprime**. Subcase $A=z-v=1$ is already
eliminated (mod 27). Two concrete leads:
(a) Eliminate each small $A\equiv13\pmod{27}$ via the slice $A^2+3Av+3v^2=(2^x+5)/A$ using
    2-power / non-phantom congruences; large $A$ is impossible since $B\ge3v^2$ is huge.
(b) The divisor sieve: $2^x+5$ can only have prime factors in a density-$\sim1/8$ "allowed"
    set (almost all small primes forbidden). Combine with (a). NOT blocked by the phantom.
See `knowledge/references/factorization_and_divisor_sieve.md`. Rationale: this is the first
handle found that is provably outside the (now two-sided) phantom obstruction.

### [MEDIUM] $p$-adic analysis of the phantom solution
DEMOTED from HIGH (2026-06-24). The phantom is now understood to be **two-sided**: a unit
is a cube mod $3^n$ iff $\equiv\pm1\pmod9$ (always true here), AND cubing is a bijection
mod $2^n$ so the 2-adic condition is also automatic. Pure local $p$-adic analysis cannot
distinguish integer solutions from the phantom. Keep only as background; the action moved to
the factorization direction. Details in the references note Â§3.

### [MEDIUM] Baker's method / linear forms in logarithms
Refined (2026-06-24): naive Baker via $\log z$ is **ineffective** because $h(z)\sim x$ grows
linearly (the variable cube base is the core obstruction). Baker only helps in the balanced
regime $2^x\approx3^y$, but the cube condition does not force $x\log2-y\log3$ small. Worth
revisiting only via the Thue/Thue-Mahler reformulation (next entry), not directly.

### [MEDIUM] Thue / Thue-Mahler reformulation (sharpened 2026-06-24)
Since $x\equiv2\pmod3$ in the open region, $z^3-4w^3=3^y+5$ with $w=2^{(x-2)/3}$ is an
irreducible binary cubic (4 is not a cube), so for each fixed $y$ it is an effective Thue
equation with finitely many solutions. Symmetrically $z^3-v^3=2^x+5$ with $v=3^{y/3}$. The
real problem is uniformity over the free exponent. The Thue-Mahler / S-unit machinery
(Magma solvers, Bilu-Hanrot-Voutier primitive divisors) is the right framework. This is the
proper home for the "fix one variable" idea below.

### [MEDIUM] Elliptic curve approach (fix one variable)
Fixing $x = 5 + 332640k$ and studying the resulting equation in $y$ and $z$ as a curve family.
(Subsumed by the Thue/Thue-Mahler entry above for the cube case.)

### [MEDIUM] Primitive divisor arguments (Zsygmondy)
May constrain the prime factorization of $z^3 - 5$ in ways that conflict with $2^x + 3^y$.

### [LOW] Numerical search with Theorem 5 filtering
Brute-force search is not mathematically deep, but can confirm no small solutions are missed and may reveal patterns.

### [LOW] arXiv survey of exponential Diophantine equations
Search for results on equations of the form $a^x + b^y = z^n$ or $2^x + 3^y = N$. Relevant keywords: "exponential Diophantine equation", "Pillai equation", "S-unit equation", "linear forms in logarithms".

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.
