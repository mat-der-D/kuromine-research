# Dead Ends

## Congruence Arithmetic (modular sieving)

**Status:** Fundamentally limited. Do not invest further effort in this direction alone.

**What was achieved:** Theorem 5 established that any solution with $x \geq 6$, $y \geq 2$ must satisfy $x \equiv 5 \pmod{332640}$ and $y \equiv -3 \pmod{166320}$. This required combining cubic residue conditions modulo 30+ primes.

**Why it cannot go further:** The phantom rational solution $(5, -3, 10/3)$ survives modulo any $m$ with $\gcd(m, 3) = 1$, because $3^{-1}$ exists in $\mathbb{Z}/m\mathbb{Z}$. The only escape is to use moduli that are powers of 3. But 37 is a cubic residue mod $3^n$ for all $n$ (proved by induction), so even this avenue is closed.

**Conclusion:** Pure congruence sieving cannot prove there are no further solutions. A fundamentally different technique is required.

## Effective irrationality measures for $2^{1/3}$ (Session 3)

**Status:** Provably insufficient for the Theorem-5 parameter range. Do not pursue as a
route to a contradiction.

**What was tried:** Reframe $z^3 = 2^x+3^y+5$ with $x=3a+2$ as the Thue form
$z^3 - 4W^3 = 3^y+5$ ($W=2^a$), making $z/W$ a rational approximation to
$\alpha = 2^{2/3}$, and apply an effective irrationality measure
$|\alpha - p/q| > c/q^\mu$ (Baker $\mu\approx2.96$, Chudnovsky/Bennett $\mu\approx2.43$,
holonomy bounds arXiv:2510.04156 sharper but $>2$).

**Why it fails (two independent computations, Wolfram):**
1. The approximation $z/W$ realizes exponent $\kappa_{\text{real}}\approx0.62<1$, far
   below any $\mu\ge2$. Irrationality measures are *lower* bounds and only constrain
   *good* approximations ($\kappa\ge\mu$). $z/W$ is a *bad* approximation, so no measure
   (however sharp) yields a constraint.
2. As a Thue lower bound, a contradiction needs $\log(3^y+5)<(3-\mu)\log\max(z,W)$, but
   LHS $\approx182718$ vs RHS $\approx43809$: off by $+138909$.

**Root cause:** $3^y$ is *not* a small perturbation of $2^x$. $\log3^y/\log2^a\approx2.38$,
so $3^y\approx z^2$ — the "two comparable dominant S-units" regime, which no single cubic
irrationality measure can resolve. Improving the constant $\mu$ cannot help. See
`knowledge/references/irrationality_measure_obstruction.md`.
