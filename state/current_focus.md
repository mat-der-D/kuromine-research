# Current Focus

**Session:** 20260626_150000 (Session 14)

**Current direction:** Elementary size-based elimination (Theorem M) — proved a new
rigorous theorem that rules out the "$3^y \gg 2^x$" half of the Theorem-5 parameter
space. Corrected and retired the gpf($z^3 - 5$) direction. Extended numerical
verification to $z \leq 10000$.

**Why this direction:** Session 13 identified the gpf($z^3-5$) reformulation as an
unexplored direction. Investigation of this direction via Wolfram led to discovering a
conflation (gpf smoothness vs. sum-representability), which in turn prompted a direct
size analysis of the factorization $z^3 - w^3 = 2^x + 5$ — producing Theorem M.

## Session 14 main results

1. **Corrected the gpf($z^3-5$) reformulation — retired.**
   - $z^3 - 5$ being a $\{2,3\}$-integer (meaning gpf $\leq 3$) is different from
     $z^3 - 5$ being representable as $2^x + 3^y$. The known solution $z=4$ has
     $z^3-5=59$ (prime, gpf=59), yet $59 = 2^5 + 3^3$ is a valid decomposition.
   - The gpf growth argument does not apply to the sum-representability condition.
   - Direction retired; see directions.md and dead_ends.md.

2. **Theorem M (new, rigorous, elementary):**
   If $y = 3j$ and $3^{2j+1} > 2^x + 4$, then $2^x + 3^y + 5$ is NOT a perfect cube.
   *Proof:* consecutive cubes $(3^j)^3$ and $(3^j+1)^3$ are spaced $3^{2j+1}+3^{j+1}+1$
   apart; if $3^{2j+1} > 2^x+5$, the target lies strictly between them. $\square$

3. **Application to Theorem-5 family:**
   For $k_x = 1$: all $k_y \geq 1$ are eliminated by Theorem M.
   For general $k_x$: $k_y \geq \lceil (x \log_3 2 - 110879)/110880 \rceil$ is eliminated,
   where $x = 5 + 332640\,k_x$. The threshold is $\approx 1.893\,k_x - 1$.

4. **Structural interpretation:**
   Theorem M eliminates the regime where $3^y \gg 2^x$ (i.e., $k_y/k_x > 3\log_3 2 - 1
   \approx 0.893$). The surviving cases are exactly the two-comparable-S-units regime
   ($2^x \approx 3^y$ or $2^x > 3^y$) — the hard cases for Baker-type methods.

5. **Extended numerics:** No new solutions for $z \leq 10000$ (Wolfram).

## Where things stand (updated after Session 14)

- Theorem M is a NEW provable result, the first new theorem on the equation itself since
  Session 1. It eliminates ~53% of Theorem-5 parameter pairs $(k_x, k_y)$ in any
  bounded range.
- Theorem M does NOT resolve the conjecture: the surviving parameter space is infinite.
- The surviving pairs (where $2^x \geq 3^y$) are exactly those in the two-S-units regime
  where Baker, Bugeaud, Badziahin, and all known analytic tools fail.
- The single most important unresolved case: $(k_x, k_y) = (1, 0)$, i.e., whether
  $2^{332645} + 3^{166317} + 5$ is a perfect cube. (Theorem M does not rule this out.)
- The open target is unchanged: **unconditional effective lower bound for $|z^3 - 3^y|$
  with exponent $\kappa < 1.107$** in the two-comparable-S-units regime.
- Next priority: formally add Theorem M to `knowledge/problem.md`; explore the
  boundary case $A \approx 1$ and whether bounded-$A$ combined with congruences
  yields a contradiction.
