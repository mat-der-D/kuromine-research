# Factorization Approach: z^3 - w^3 = 2^x + 5

## Setup

For solutions $(x, y, z)$ satisfying Theorem 5 (i.e., $x = 5 + 332640k$, $y \equiv -3 \pmod{166320}$, with $k \geq 1$), the following hold:

1. **$y$ is divisible by 3.** Proof: $y \equiv -3 \equiv 0 \pmod{3}$ since $-3 \equiv 0 \pmod 3$. (Trivial but important.)

2. **$j = y/3 \equiv 2 \pmod{3}$.** Proof: $y \equiv -3 \equiv 6 \pmod{9}$, so $j = y/3 \equiv 2 \pmod 3$.

3. **Setting $w = 3^j$, the equation becomes:**
$$z^3 - w^3 = 2^x + 5$$
$$(z - w)(z^2 + zw + w^2) = 2^x + 5$$

## Coprimality

**Claim:** $\gcd(z - w, z^2 + zw + w^2) = 1$.

**Proof:**
- $z \equiv 1 \pmod{3}$ (proved: $z^3 = 2^x + 3^y + 5 \equiv 2 + 0 + 2 \equiv 1 \pmod 3$).
- $w = 3^j \equiv 0 \pmod{3}$.
- So $z - w \equiv 1 \pmod{3}$ and $z^2 + zw + w^2 \equiv z^2 \equiv 1 \pmod{3}$.
- $\gcd(z - w, w) = \gcd(z, 3^j) = 1$ (since $\gcd(z, 3) = 1$).
- If $d \mid \gcd(z-w, z^2+zw+w^2)$ then $d \mid 3w^2$ (since $z^2 + zw + w^2 \equiv 3w^2 \pmod{z-w}$).
- Since $d \mid z - w$ implies $\gcd(d, w) = 1$, and $\gcd(d, 3) = 1$ (both expressions are $\equiv 1 \pmod 3$): $d = 1$. $\square$

## Prime Factor Constraint on $z^2 + zw + w^2$

**Claim:** Every prime factor $p$ of $B = z^2 + zw + w^2$ satisfies $p \equiv 1 \pmod{3}$.

**Proof:** $p \mid z^2 + zw + w^2$ and $p \nmid 3w$ (since $\gcd(B, 3) = 1$ as $3 \nmid 2^x + 5$, and $p \nmid w$ since $\gcd(z-w, w) = 1$ and $\gcd(z^2+zw+w^2, z-w) = 1$ implies $\gcd(B, w)$ divides $\gcd(2^x+5, 3^j)$ = 1). Thus $p \nmid w$, so we can write $u = zw^{-1} \pmod{p}$ and $u^2 + u + 1 \equiv 0 \pmod{p}$. This requires $-3$ to be a quadratic residue mod $p$, which happens iff $p \equiv 1 \pmod{3}$ (for $p > 3$). $\square$

## Norm Form Interpretation

In the ring $\mathbb{Z}[\omega]$ of Eisenstein integers ($\omega = e^{2\pi i/3}$):
- $B = z^2 + zw + w^2 = N(z - \omega w)$
- The factorization $z^3 - w^3 = (z-w) \cdot N(z - \omega w)$ corresponds to the factorization in $\mathbb{Z}[\omega]$.
- Since all prime factors of $B$ are $\equiv 1 \pmod{3}$, $B$ factors completely in $\mathbb{Z}[\omega]$.
- The prime $2 \equiv 2 \pmod{3}$ stays inert in $\mathbb{Z}[\omega]$; similarly $5 \equiv 2 \pmod{3}$ stays inert.
- So $2^x + 5$ factors in $\mathbb{Z}[\omega]$ as (unit) $\times 2^x \times 5$ times contributions from primes $\equiv 1 \pmod 3$.

## Parity Constraints

- $z \equiv 6 \pmod{8}$ (computed from $z^3 \equiv 3^{166317} + 5 \equiv 24 \pmod{32}$ and $y \equiv 1 \pmod 4$).
- $w = 3^j$ with $j$ odd: $w \equiv 3 \pmod{8}$.
- $z - w \equiv 6 - 3 = 3 \pmod{8}$ (always).
- $z^2 + zw + w^2 \equiv 36 + 18 + 9 = 63 \equiv 7 \pmod{8}$ (always).
- Product: $3 \times 7 = 21 \equiv 5 \pmod{8}$. Matches $2^x + 5 \equiv 5 \pmod{8}$ for $x \geq 3$. $\checkmark$

## Connection to Thue-Mahler Equations

For fixed $k$ (hence fixed $x$ and $N_k = 2^x + 5$), the equation $z^3 - w^3 = N_k$ with $w = 3^j$ is a special case of the Thue-Mahler equation: one seeks integer solutions $(z, j)$ to the norm form equation with the constraint that $w$ is a power of $3$. By the Thue-Mahler theorem (effective via Baker), for each fixed $N_k$, there are finitely many solutions. This gives finiteness for each individual $k$.

**The remaining challenge:** Show that across all $k \geq 1$, no solutions exist (not just finiteness for each $k$).
