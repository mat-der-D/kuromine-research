# p-adic Methods for the Kuromine Problem

## The 3-adic Structure

The phantom solution $(x, y, z) = (5, -3, 10/3)$ lives in $\mathbb{Q}_3$ (3-adic rationals). This creates the fundamental obstruction to pure congruence methods. However, 3-adic methods may yet yield constraints that distinguish integer solutions from the phantom.

## Key 3-adic Facts

**Valuation of $2^{332640k} - 1$ (via LTE):**

By the Lifting the Exponent Lemma (LTE) for $p = 3$: since $v_3(2^{332640} - 1) = 4$ (verified by computation: $332640 = 2^5 \cdot 3^3 \cdot 5 \cdot 7 \cdot 11$, and $\text{ord}_{3^4}(2) = 54 \mid 332640$ but $\text{ord}_{3^5}(2) = 162 \nmid 332640$):

$$v_3(2^{332640k} - 1) = 4 + v_3(k)$$

**Structural result on $v_3(z^3 - 37)$:**

For solutions $(x, y, z)$ with $x = 5 + 332640k$ and $y = 166317 + 166320m$ ($k \geq 1$, $m \geq 0$):

$$z^3 - 37 = 3^y + 32(2^{332640k} - 1)$$

Since $v_3(3^y) = y \geq 166317 \gg 4 + v_3(k) = v_3(32(2^{332640k} - 1))$:

$$v_3(z^3 - 37) = 4 + v_3(k)$$

**Corollary:** The residue class of $z \pmod{3^{5+v_3(k)}}$ is determined by $k$.

## Skolem's p-adic Method

Skolem's method reduces Diophantine equations to finitely many p-adic equations, each solvable by Hensel's lemma or its failure. It is most effective when the equation can be reduced to a recurrence.

**Applicability here:** The equation $2^x + 3^y + 5 = z^3$ with $x, y$ in arithmetic progressions (from Theorem 5) has the form required by Skolem's method. Specifically: fix $a = 2^{332640}$ (the "base" of the x-progression), then $2^x = 32 \cdot a^k$. The equation becomes:

$$32 \cdot a^k + 3^y + 5 = z^3$$

This is an exponential Diophantine equation with two exponential terms. Skolem's method over $\mathbb{Z}_3$ would require showing the 3-adic "points" parameterized by $(k, m)$ do not include integer solutions.

**Obstruction:** The phantom solution $32 + 3^{-3} + 5 = (10/3)^3$ lives in $\mathbb{Z}_3$ (with $3^{-3}$ a negative power of 3, but the whole expression has a 3-adic expansion). This makes the 3-adic approach delicate.

## References

- T. Skolem, "Ein Verfahren zur Behandlung gewisser exponentieller Gleichungen," (1934).  
- J. Box, "An introduction to Skolem's p-adic method for solving Diophantine equations," Warwick, 2019. (Bachelor's thesis, warwick.ac.uk)
- K. Yu, "p-adic logarithmic forms and group varieties," *J. Reine Angew. Math.* (1994).
- arXiv:1407.6499 — Hasse-type principle for exponential Diophantine equations.
