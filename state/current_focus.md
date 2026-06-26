# Current Focus

**Session:** 20260627_000000 (Session 19)

**Current direction:** Cyclotomic phantom family — the last active non-watch [LOW]
direction. Systematically compared equations $2^x + 3^y + c_m = z^3$ for
$c_m = 27m^3 + 9m^2 + m - 32$ ($c_1=5, c_2=222, c_3=781$). Result: RETIRED. The
comparison confirms $c_1=5$ is the simplest case (uniquely prime pivot $37 = 2^5 + c_1$),
but no new attack strategy emerges. arXiv watch: negative (eighth confirmation).
**ALL non-watch directions are now exhausted.** The research enters a pure monitoring phase.

## Session 19 main results

1. **Parity partition theorem (new, analytic):** $c_m$ is odd iff $m$ is odd. Consequently,
   $z$ is even for odd-$m$ equations and odd for even-$m$ equations (for $x,y \geq 1$).

2. **Uniqueness of $c_1 = 5$ (confirmed):** $c_1 = 5$ is the unique $c_m$ where
   $2^5 + c_m$ is prime $\equiv 1 \pmod 3$ (the prime 37). For all $m \geq 2$,
   $2^5 + c_m$ is composite with extraneous small-prime factors (2 for $m=2$, 3 for $m=3$,
   etc.). $c_1 = 5$ is the easiest case in the phantom family by simplicity of forced-prime
   structure.

3. **Forced-factor analogy (new):** For $c_2 = 222$: the role of 37 is played by 127
   ($\mathrm{ord}_{127}(2)=7$). Crucially, $37 \mid c_2$ (since $222 = 6 \cdot 37$), so
   $37 \nmid 2^x + c_2$ for any $x$ — the $37 \| B$ forced-factor fact of Session 18 is
   absent for $c_2$.

4. **Soft obstruction universal (confirmed):** Every equation $2^x + 3^y + c_m = z^3$
   is locally solvable at every prime $p \neq 3$ (phantom is a global rational cube).
   No modular/local method works for any $c_m$.

5. **Cyclotomic family RETIRED:** No new attack strategy emerges from the comparison.

6. **arXiv watch (negative):** No new applicable paper in June/July 2026. Eighth
   confirmation of the two-comparable-S-units barrier.

## Where things stand (updated after Session 19)

**Every named approach is exhausted:**
- Congruence sieving, Baker/linear forms (archimedean and p-adic), modular/Frey,
  primitive divisors, Chabauty-Kim, function-field/Mason-Stothers, Thue irrationality
  measures, Bugeaud S-units, Theorem-M size analysis, Thue-Mahler/norm-form,
  elliptic-curve, cyclotomic phantom family, special role of $c=5$.

**The unique remaining open target:**
$$|z^3 - 3^y| > C \cdot (z^3)^{\kappa}, \quad \kappa < 1.107,$$
in the two-comparable-S-units regime $3^y \approx z^2$. Unconditional; no known
technique achieves this. The holonomy school (Calegari-Dimitrov-Tang, arXiv:2510.04156)
is the most plausible future source.

## Next priority

**[WATCH — only]** Monitor arXiv for an unconditional effective lower bound with
$\kappa < 1.107$. ALL non-watch directions are now exhausted. Future sessions should
focus solely on arXiv monitoring.
