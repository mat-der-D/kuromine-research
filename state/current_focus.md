# Current Focus

**Session:** 20260704_000000 (Session 38)

## Session 38 main results (WATCH negative, 27th confirmation; NEW framework built+retired under SPECIAL DIRECTIVE; new Wolfram computations)

WATCH-phase session that (1) ran the arXiv watch (negative, 27th confirmation); (2) produced two
**genuinely new Wolfram computations** — a joint multi-prime cube-root/$B$ portrait and the 3-adic
valuation-budget cancellation; and (3) honored the **THEORY-BUILDING SPECIAL DIRECTIVE** by
constructing a new-*shape* framework — the **Integral Valuation-Budget Framework** — and, honestly,
finding that it too reduces to the wall (crux Lemma VB-2 = the missing $\kappa>1$ gap bound).

**arXiv watch (twenty-seventh confirmation, negative).** Unchanged: Bugeaud 2604.27490 still only
"$\to\infty$ with $z^d$" (not power-saving $\kappa>1$); $k\ge3$-prime decidability (Dong–Shafrir
2505.19141) still "outstanding open problem"; CDT/Badziahin $\mu(2^{1/3})>2\gg1.107$. No new paper.

**New Wolfram computations (genuine, recorded):**
1. **Multi-prime joint portrait.** For $(k_x,k_y)=(1,1)$, at every prime $p\in\{7,13,19,31,37,43,
   61,67,73,97,109,127\}$, the phantom cube root $z_{\text{ph}}\equiv10\cdot3^{-1}$ is one of the
   three family roots and $B_{\text{ph}}\equiv37\cdot3^{-1}$ is among the family $B$-values
   (at $p=37$: roots $\{21,25,28\}$, $37\mid B$ on $z\in\{21,28\}$, phantom on $z\equiv28$). The
   sharpest single demonstration that the soft obstruction holds jointly across many primes.
2. **Budget cancellation.** $v_3(A)+v_3(B)=v_3(2^x+5)=0$ universally (Wolfram; $2^x+5\equiv1\pmod3$,
   $x$ odd). Genuine $(v_3(A),v_3(B))=(0,0)$ vs phantom $(1,-1)$ — the exact reason 3-adic
   valuation is blind to the genuine/phantom distinction.

**Integral Valuation-Budget Framework (NEW, built + RETIRED under SPECIAL DIRECTIVE).** A
local-global / valuation-budget obstruction (a *different shape* from the three prior transfer
frameworks, chosen because the wall is a local-global failure, not a metric transfer). Lemma VB-1
(budget rigidity) **proved** but = Cubic-Transversality Lemma D (no constraint on genuine
solutions). Lemma VB-2 (height–integrality incompatibility, the crux) **proved equivalent to the
missing effective $\kappa>1$ gap bound**. **Seventh independent theory-building confirmation** of
the wall. Full statement: `knowledge/references/valuation_budget_framework.md`.

Twenty-seventh structural confirmation. WATCH remains the sole active priority. No new knowledge-base
theorem (the framework's proved lemma duplicates Lemma D).

---

This file is a snapshot of where the research currently stands. Per-session narratives live in the
`log/` files; the change history is summarized in `state/directions.md`; theorems are stated in
`knowledge/problem.md`.

## Status in one line

The conjecture is reduced to a single unconditional open target — an effective gap bound with a
fixed $\kappa>1$ — that no current tool supplies. Research is in a **WATCH** phase: monitor arXiv,
and record any new structural facts found along the way. As of Session 38 there have been **27
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
(S22), archimedean-equidistribution (S27–28), and local-global/valuation-budget (S38). Four
theory-building frameworks (Coupling-Height, Differential-Progression, Cubic-Transversality,
Integral-Valuation-Budget) all reduced to the wall. New theory must beat the Dirichlet floor on the
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
   complete; seven theory-building confirmations, all the same wall — the latest, S38's
   Integral-Valuation-Budget framework, exhausts the local-global angle too). A new framework is
   worth building only if it carries, from the outset, a mechanism producing an archimedean
   $\kappa>1$ gap.

3. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs — Theorem-N corollary still blocks
   (Theorem S); logged for completeness only.
