# Current Focus

**Session:** 20260627_140000 (Session 35)

This file is a snapshot of where the research currently stands. Per-session narratives live in the
`log/` files; the change history is summarized in `state/directions.md`; theorems are stated in
`knowledge/problem.md`.

## Status in one line

The conjecture is reduced to a single unconditional open target — an effective gap bound with a
fixed $\kappa>1$ — that no current tool supplies. Research is in a **WATCH** phase: monitor arXiv,
and record any new structural facts found along the way. As of Session 35 there have been **24
consecutive negative confirmations** of the two-comparable-S-units barrier.

## The open target (corrected framing, Session 26)

For any surviving Theorem-5 solution, $|z^3 - 3^y| = 2^x + 5$. The realized exponent of this gap
against $z^3$,
$$E = \frac{\log(2^x+5)}{\log(z^3)} \in \left(\tfrac23,\,1\right),$$
is strictly below 1 everywhere and densely fills $(2/3,1)$ (Session 31): it $\to 2/3^+$ at the
two-comparable-S-units boundary ($3^y \approx z^3$) and $\to 1^-$ at $k_y=0$. Therefore:

> **Any** unconditional *effective* lower bound $|z^3 - 3^y| > C\,(z^3)^{\kappa}$ with a fixed
> $\kappa > 1$ resolves the whole surviving family. The recorded $\kappa < 1.107 = 3-3\log_3 2$ is
> a sufficient margin, not a necessary ceiling; the necessary-and-sufficient requirement is
> $\kappa > 1$ (strictly — $\kappa=1$ is just barely insufficient).

**Why it is hard.** Baker-type machinery gives $v_p(\Lambda_p)=0$ (Session 5), so no effective gap
bound with any $\kappa>1$ exists by that route. The target is **sub-Dirichlet** (Session 25): it
lies below the floor $\mu\ge2$ obeyed by every irrationality measure, so improving the effective
measure for $2^{1/3}$ (the CDT program) can never reach it — the auxiliary $2^{2/3}$-Thue
approximation $z/W$ is in fact an *anti*-approximation (exponent negative for all $k_y\ge1$). Two
structurally distinct frontiers gate the problem: the metric/analytic two-comparable-S-units
barrier, and the degree-3 free-cube barrier to decidability methods. Both rest on Baker being
inapplicable.

## What is established (knowledge accumulated, all in `knowledge/problem.md`)

- **Theorem M** (size): $3^{2j+1}>2^x+4 \Rightarrow$ not a cube; survivors satisfy
  $k_y/k_x<0.893$ (the hard two-comparable-S-units regime).
- **Theorem N** ($p$-adic depth): $v_3(2^x+5-A^3)=j+1$, re-proving $A\sim2^{x/3}$.
- **Theorems I–L, P, Q, R** ($p$-adic portrait of $A=z-3^j$): $A$ is a free 3-adic unit (digits
  $\leftrightarrow k_x$) and a free 2-adic unit (digits $\leftrightarrow k_y$), with explicit
  lifting/tangent laws (3-adic slope $v_3=3$, 2-adic slope $v_2=4$), coupled only by the
  archimedean size — the sharpest $p$-adic statement of the soft obstruction.
- **Theorem S** (metric): record minima of the boundary distance $D=x\log2-(2j+1)\log3$ sit at the
  convergent denominators of $\rho=3\log2/\log3$ ($\mu(\rho)=2$ numerically); small $D$ (small $A$)
  only at huge $k_x$ (huge depth $j+1$), so bounded-$A$ is excluded by Theorem N with a $\sim10^9$
  margin at the first concrete witness ($k_x=16836$).
- **Theorem T** (5-adic sieve, the constant prime): $v_5(N)\geq2$ universally, and a cube needs
  $3\mid v_5$, forcing $k_y\equiv k_x-1\pmod5$ — a new necessary congruence eliminating 80% of the
  family; soft-obstructed (phantom has $v_5=3$).

Together these complete the local/metric portrait across all three places (metric, 2-adic, 3-adic)
and confirm — from every angle tried — that the obstruction is **archimedean**: the $p$-adic data
leave $A$ a free parameter, and only the size relation $A\approx2^{x/3}$ ties it to a genuine
solution. No local or congruence method can supply that.

## Attack-face inventory (complete since Session 28 — DO NOT rebuild)

Every theory-building attempt and every standard tool returns the same two-comparable-S-units wall:
metric (S15), analytic/irrationality (S3/10/11), 3-adic-coupling (S20–21, S24), decidability/degree
(S22), archimedean-equidistribution (S27–28). New theory must beat the Dirichlet floor on the
$2^{2/3}$ approximation or supply a power-saving $\kappa>1$ gap bound directly; nothing short
reaches it.

## Next priority

1. **[WATCH — sole active priority]** Monitor arXiv for either:
   - (a) an unconditional **effective gap bound** $|z^3-3^y|>C(z^3)^\kappa$ with any fixed
     $\kappa>1$ in the regime $3^y\approx2^x\approx z^3$ — the necessary-and-sufficient tool; watch
     for genuinely new *separation/gap* techniques (measure improvements alone do not reach the
     sub-Dirichlet target, and effective-equidistribution of scalar exponential orbits is — by the
     Session-28 identity — equivalent to this same target); OR
   - (b) **[narrowed, Session 30]** a *special-structure* decidability/finiteness argument for the
     Kuromine family (two fixed-base exponentials + one cube), or the $k\ge3$-prime case — but
     **not** a general degree-3 decidability theorem (arXiv:2510.00759 proves none can exist).

   Key papers to track: Bugeaud (2503.22084, 2604.27490), CDT holonomy (2510.04156), Badziahin,
   KLNOW / Dong–Shafrir (2505.19141), and STOC/LICS 2026 follow-ups.

2. **[DO NOT ATTEMPT]** Further theory-building that reduces to an existing attack face (inventory
   complete; six confirmations, all the same wall).

3. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs — Theorem-N corollary still blocks
   (Theorem S); logged for completeness only.
