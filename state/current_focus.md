# Current Focus

**Session:** 20260626_230000 (Session 18)

**Current direction:** Thue-Mahler / norm-form approach (the last unexplored [MEDIUM]
direction, identified in Session 1 but never analyzed in depth). Deeply explored with
Wolfram and RETIRED: every casting of the Kuromine equation as a single Thue-Mahler
equation `F(X,Y) = (S-unit)` is broken by the additive constant 5. The Elliptic-curve
[MEDIUM] direction was also marked ~RETIRED (same per-fixed-variable wall). arXiv watch:
negative (seventh confirmation of the two-comparable-S-units barrier).

## Session 18 main results

1. **All four Thue-Mahler / norm-form castings are broken by the constant 5** (Wolfram):
   - $z^3-4W^3 = 3^y+5$ ($W=2^a$): RHS not a $\{2\}$-S-unit.
   - $z^3-w^3 = 2^x+5$ ($w=3^j$): RHS not a $\{3\}$-S-unit.
   - Eisenstein norm form $N_{\mathbb{Q}(\omega)}(z-w\omega)=B$: $A$ varies; phantom-blocked.
   - $N_{\mathbb{Q}(5^{1/3})}(z-5^{1/3}) = 2^x+3^y$: RHS a *sum* of two S-units, uncontrolled.
   Root cause: the additive constant 5 (two-term RHS) prevents a single-S-unit RHS — the
   Thue-Mahler face of the phantom obstruction.

2. **Symmetric reframing of the hard case (new):** the whole Theorem-5 family is equivalent
   to $z^3 - 4(2^a)^3 - (3^j)^3 = 5$ (a cube minus two S-unit-cubes equals 5), with
   $a=(x-2)/3$, $j=y/3$. Verified on $(5,3,4)$: $64-32-27=5$.

3. **Forced factor 37 (new clean fact):** $v_{37}(2^x+5)=1$ exactly and universally
   (because $x\equiv5\pmod{36}=\mathrm{ord}_{37}(2)$, so $2^x\equiv-5\pmod{37}$), hence
   $37\|B$. Since $37=\pi\bar\pi$ splits in $\mathbb{Z}[\omega]$, the mod-37 cube equation
   $z^3\equiv11$ has three roots $z\in\{21,25,28\}$; "$37\mid B$ not $A$" selects
   $z\in\{21,28\}$; the phantom sits on the $z\equiv28$ branch. All soft-obstructed (phantom
   is a cube mod $37^n$ for all $n$, verified mod $37^3$; deeper 37-adic residues vary across
   the family).

4. **Per-fixed-$y$ Thue equation finite, but no uniformity:** $z^3-4W^3=3^y+5$ has $W=2^a$
   only at $y=3$ (the known solution) over $y\leq12$ (Wolfram). Thue-Mahler theory gives
   finiteness per equation (unit rank of $\mathbb{Q}(2^{1/3})$ is 1) but nothing uniform over
   the infinite progression — the actual open content.

5. **arXiv watch (negative):** Calegari-Dimitrov-Tang (arXiv:2510.04156) still gives
   effective irrationality measure $\mu>2$ for $2^{1/3}$; no new applicable 2026 follow-up.
   Seventh confirmation of the two-comparable-S-units barrier (S3, S10, S11, S12, S16, S17, S18).

## Where things stand (updated after Session 18)

- **Every named approach is now exhausted:** congruences, Baker/linear forms (archimedean
  and p-adic), modular/Frey, primitive divisors, Chabauty-Kim, function-field/Mason-Stothers,
  Thue irrationality measures, Bugeaud S-units, Theorem-M size analysis, **Thue-Mahler/
  norm-form (Session 18)**, and the linked elliptic-curve route.
- **The unique remaining open target:**
  $$|z^3 - 3^y| > C \cdot (z^3)^{\kappa}, \quad \kappa < 1.107$$
  in the two-comparable-S-units regime $3^y \approx z^2$. Unconditional; no known
  technique achieves this. The holonomy school (Calegari-Dimitrov-Tang, arXiv:2510.04156)
  is the most plausible future source.

## Next priority

**[WATCH — primary]** Monitor arXiv for an unconditional effective lower bound with
$\kappa < 1.107$. All active elementary/algebraic directions ([HIGH], [MEDIUM], and the
analyzable [LOW]s) are now exhausted. The only remaining speculative direction is the
"cyclotomic phantom family" ($c = 5, 222, 781, \ldots$), which is LOW priority. Future
sessions should focus on arXiv monitoring unless a genuinely new structural angle emerges.
