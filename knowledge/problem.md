# The Kuromine Problem

## Problem Statement

Find all integer solutions $(x, y, z)$ to:

$$2^x + 3^y + 5 = z^3$$

## Known Solutions

- $(x, y, z) = (1, 0, 2)$
- $(x, y, z) = (5, 3, 4)$

These are the only known solutions. It is conjectured that no others exist.

## Theorem 1: Non-negativity

$x, y, z$ are all non-negative.

**Proof sketch:** Multiplying both sides by $2^{|x|}$ forces $y \geq 0$. The equation then forces $x \geq 0$. Since $2^x + 3^y + 5 \geq 0$, we have $z \geq 0$.

## Theorem 2: No solution for $y = 0$ other than $(1, 0, 2)$

When $y = 0$, the equation becomes $2^x + 6 = z^3$. Cubic residues mod 4 are $\{0, \pm 1\}$, which forces $x \in \{0, 1\}$. Only $x = 1$ gives a solution.

## Theorem 3: No solution for $y = 1$

When $y = 1$, the equation becomes $2^x + 8 = z^3$. For $x \geq 1$, $z$ must be even, giving $2^\xi + 1 = \zeta^3$ after substitution. Cubic residues mod 7 are $\{0, \pm 1\}$, which rules out all values of $\xi$.

## Theorem 4: For $y \geq 2$ and $x \leq 5$, the only solution is $(5, 3, 4)$

Cubic residues mod 9 force $x \in \{2, 5\}$. The case $x = 2$ is eliminated by a 3-divisibility argument. For $x = 5$, the equation becomes $3^y + 37 = z^3$. Splitting into residue classes mod 3 exhausts all cases; only $y \equiv 0 \pmod{3}$ survives, and the factorization $z^3 - w^3 = 37$ (where $w = 3^{y/3}$) forces $(z, w) = (4, 3)$, giving $y = 3$.

## Theorem 5: Congruence constraint for $x \geq 6$, $y \geq 2$

If $(x, y, z)$ is a solution with $x \geq 6$ and $y \geq 2$, then:

$$x \equiv 5 \pmod{332640}, \quad y \equiv -3 \pmod{166320}$$

**Proof sketch:** Derived by combining cubic residue constraints modulo a large set of primes (7, 13, 19, 31, 37, 43, 61, 67, 73, 97, 109, 127, 181, 193, 199, 211, 241, 331, 337, 379, 397, 421, 433, 463, 541, 577, 661, 673, 991, 2113, 2311) together with mod 64 and mod 9 conditions. Verified by a Rust implementation.

## The Phantom Solution

The rational solution $(x, y, z) = (5, -3, 10/3)$ satisfies the equation over $\mathbb{Q}$:

$$2^5 + 3^{-3} + 5 = \left(\frac{10}{3}\right)^3$$

This is not an integer solution, but it causes a fundamental obstruction to the congruence approach. For any modulus $m$ with $\gcd(m, 3) = 1$, the inverse $3^{-1} \pmod{m}$ exists, so the phantom solution "appears" mod $m$ and cannot be eliminated. The only moduli that avoid this are powers of 3.

**Proposition:** For all $n \geq 1$, $37$ is a cubic residue mod $3^n$.

**Proof:** By induction. Base case $n = 1, 2$: $37 \equiv 1 \pmod{9}$. Inductive step: given $z_n^3 \equiv 37 \pmod{3^n}$, set $z_{n+1} = z_n + t \cdot 3^{n-1}$ and choose $t = -k$ where $z_n^3 = 37 + k \cdot 3^n$. Since $z_n \not\equiv 0 \pmod{3}$, we have $z_n^2 \equiv 1 \pmod{3}$, so $k + t z_n^2 \equiv 0 \pmod{3}$, giving $z_{n+1}^3 \equiv 37 \pmod{3^{n+1}}$.

**Consequence:** No accumulation of congruences mod $3^n$ can eliminate the case $x = 5$, $y \geq n$ from the residue approach. This is the hard wall of the congruence method.
