# 3-adic density of admissible $x$ (negative result, session 2026-06-25)

## Setup

For a solution with $y \ge n$, reducing $z^3 = 2^x + 3^y + 5$ modulo $3^n$ gives
$$2^x + 5 \equiv z^3 \pmod{3^n},$$
i.e. $2^x + 5$ must be a cubic residue mod $3^n$. This is the only congruence information
the 3-adic place provides about $x$ (the phantom obstruction blocks all moduli coprime to 3).

## Computation (Wolfram, exact)

Let $d(n) = \dfrac{\#\{x \bmod \mathrm{ord}_{3^n}(2) : 2^x+5 \text{ is a cube mod } 3^n\}}{\mathrm{ord}_{3^n}(2)}$
be the density of admissible $x$-residues.

| $n$ | $\mathrm{ord}_{3^n}(2)$ | #admissible | density $d(n)$ |
|----:|------------------------:|------------:|---------------:|
| 2 | 6    | 2   | 0.3333 |
| 3 | 18   | 4   | 0.2222 |
| 4 | 54   | 12  | 0.2222 |
| 5 | 162  | 30  | 0.1852 |
| 6 | 486  | 88  | 0.1811 |
| 7 | 1458 | 264 | 0.1811 |
| 8 | 4374 | 786 | 0.1797 |

## Conclusion

The density **does not decay to 0**; it stabilises around $0.18$. Therefore the 3-adic
cubic-residue condition admits a *positive-density* set of $x$ and **cannot** isolate $x=5$
(or any single class). This is a sharp, quantitative confirmation of the "hard wall" recorded
in `dead_ends.md`: a purely 3-adic sieve on $x$ is hopeless, because the limiting density is
bounded away from zero. (Intuitively, mod $3^n$ a "random" target is a cube with probability
$\approx 1/3$ once $n\ge 2$, since $[\mathbb{Z}/3^n]^* \to$ cubes is 3-to-1; the observed
$\approx 0.18$ reflects the specific arithmetic of $2^x+5$ but stays $\Theta(1)$.)

This rules out a refinement of the congruence/Theorem-5 approach that hoped the admissible
density of $x$ might shrink with $n$. It does not. The escape must come from a non-congruence
(archimedean / Baker) ingredient — see `baker_method.md`.
