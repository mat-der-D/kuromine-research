# Dead Ends

## Congruence Arithmetic (modular sieving)

**Status:** Fundamentally limited. Do not invest further effort in this direction alone.

**What was achieved:** Theorem 5 established that any solution with $x \geq 6$, $y \geq 2$ must satisfy $x \equiv 5 \pmod{332640}$ and $y \equiv -3 \pmod{166320}$. This required combining cubic residue conditions modulo 30+ primes.

**Why it cannot go further:** The phantom rational solution $(5, -3, 10/3)$ survives modulo any $m$ with $\gcd(m, 3) = 1$, because $3^{-1}$ exists in $\mathbb{Z}/m\mathbb{Z}$. The only escape is to use moduli that are powers of 3. But 37 is a cubic residue mod $3^n$ for all $n$ (proved by induction), so even this avenue is closed.

**Conclusion:** Pure congruence sieving cannot prove there are no further solutions. A fundamentally different technique is required.

**Quantitative confirmation (session 2026-06-25):** The density of admissible $x$-residues
under the only available 3-adic condition ($2^x+5$ a cubic residue mod $3^n$) was computed
exactly for $n \le 8$. It does NOT decay — it stabilises at $\approx 0.18$. So even an
idealised, fully-refined 3-adic sieve admits a positive-density set of $x$ and cannot isolate
$x=5$. Details in `knowledge/references/three_adic_density.md`.

**Sharp reason (session 2026-06-25):** The phantom is *exactly* the fibre $z^3-2^x-5=3^y$ at
$x=5,\ y=-3$, since $(10/3)^3-2^5-5 = 1/27 = 3^{-3}$. No congruence can see the sign of $y$,
so no congruence distinguishes the real branch $y\ge2$ from the phantom branch $y=-3$. The
separation exists only at the archimedean place — which is why Baker's method (not congruences)
is the right tool. See `knowledge/references/baker_method.md`.
