# Research Directions

Directions are listed with a priority estimate and current status. Retired directions are
recorded as one-line markers; their full reasoning lives in `knowledge/dead_ends.md` (and the
cited session logs). Theorems are stated in `knowledge/problem.md`.

---

## Active Directions

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered Session 1.** For all Theorem-5 solutions $y=3j$ and the equation factors as
$(z-w)(z^2+zw+w^2)=2^x+5$ with $w=3^j$, $\gcd=1$, and $z^2+zw+w^2$ having only prime factors
$\equiv1\pmod3$ — a norm-form equation in the Eisenstein integers $\mathbb Z[\omega]$. Clean
single-equation form with $A=z-3^j$, $B=z^2+z3^j+3^{2j}$:
$$2^x+5 = A\,(A^2+3^{j+1}A+3^{2j+1}) = A\cdot B.$$

**Current status: MEDIUM in practice.** All *congruence* and *multiplicative* content is soft-
obstructed (the phantom $A=3$, $B=37/3$ reduces mod every $p\ne3$; the Eisenstein "primes
$\equiv1\bmod3$" condition on $B$ is forced automatically by $\gcd(z,3^j)=1$ — S29). $A$ is
provably $\sim2^{x/3}$ (never the phantom value), so "$A=1$" is impossible. The complete $p$-adic
portrait of $A$ is documented as Theorems I–L, N, P, Q, R in `knowledge/problem.md`: $A$ is a free
3-adic unit (digits $\leftrightarrow k_x$) and a free 2-adic unit (digits $\leftrightarrow k_y$),
coupled only by the archimedean size. The direction survives **only** in its global/size sub-
question (a), which needs an effective $\kappa>1$ gap bound that does not exist.

Sub-questions: (a) global/size elimination — open, blocked on the missing $\kappa>1$ tool;
(b) growth/primitive-divisor — CLOSED S4 ($B$ is not Lucas/Lehmer); (c) bounded-$A$ — CLOSED
negatively S4/S15 ($A\sim2^{x/3}$).

### [MEDIUM] Theorem M and the size-partitioned Theorem-5 family

**Session 14.** **Theorem M** (elementary): if $y=3j$ and $3^{2j+1}>2^x+4$ then $2^x+3^y+5$ is not
a cube (target trapped between consecutive cubes). Eliminates the "$3^y\gg2^x$" regime: surviving
pairs satisfy $k_y/k_x<3\log_3 2-1\approx0.893$. The survivors are exactly the two-comparable-
S-units regime ($2^x\geq3^y$) where all known analytic tools also fail; Theorem M alone does not
resolve the conjecture.

**Status: fully explored.** Sub-questions (a) bounded-$A$ at the boundary $D\approx0$ and
(b) the companion "from-above" $A<3^j$ window are both CLOSED negatively (S15/S16); the metric
structure is pinned by **Theorem S** (Convergent–Depth Trade-off Law, S34): record minima of the
boundary distance $D=x\log2-(2j+1)\log3$ sit at the convergent denominators of $\rho=3\log2/\log3$
($\mu(\rho)=2$ numerically), so small $D$ (hence small $A$) only occurs at huge $k_x$ (hence huge
depth $j+1$), the two coupled by $\rho$ — Theorem-N exclusion fires with $\sim10^9$ margin at the
first concrete bounded-$A$ lattice point ($k_x=16836$). Sub-question (c) (combine with a
quantitative gap bound) is blocked pending the same $\kappa>1$ tool.

**Session-37 addition (Theorem V):** The Session-34 witness ($k_x=16836$) is independently
eliminated by Theorem T (fails $k_y\equiv k_x-1\pmod5$). The sharpest T-surviving near-boundary
pair ($k_x=84180$, $D=0.537$, $A\in\{1..5\}$) is independently eliminated by Theorem P ($A\equiv11
\pmod{16}$ forces $A\ge11$) and also by Theorem N ($v_3\le3$ vs depth $j+1=8.8\times10^9$).
The three filtering tools T, P, N have non-overlapping action domains and collectively cover all
explicitly computable near-boundary cases.

### [LOW] Special role of $c=5$ and the phantom

**Session 16–17, 35.** Cyclotomic origin: $2^5+5=37=\Phi_3(10)/3$; $c=5$ is the unique small
positive constant with the phantom structure $(10/3)^3$. **Theorem T** (5-adic Valuation Sieve,
S35) is the first use of the prime 5 as a valuation: $v_5(N)\geq2$ universally, and a cube needs
$3\mid v_5(N)$, forcing the new necessary congruence $k_y\equiv k_x-1\pmod5$ — eliminating 80% of
the family (refinable 5-adically, survivors $\approx16.2\%$ of the mod-25 grid). **Soft-
obstructed**: the phantom has $v_5=3$ on the survival diagonal, so the sieve never empties the
family.

**Open question:** does the arithmetic of $c=5$ impose any *un*-obstructed positive constraint?
**Full answer after S35–S36:** Theorem T ($k_y\equiv k_x-1\pmod5$, 80% elimination) and
Theorem U ($v_5(z)=1$, combined CRT $z\equiv3910\pmod{4320}$, prime-5-unique scan, survival
fraction $\to16.13\%$ at four 5-adic depths) are genuine new positive constraints — both
soft-obstructed (phantom satisfies them). The 5-adic face is now **fully analyzed**; no
further 5-adic analysis expected to yield a new result. Practical value: cheapest combined
search cut ($\geq5\times$ from T, $\geq5\times$ more from U), composing independently with
Theorem M (size) and the $p$-adic portrait.

### [LOW] Numerical search with Theorem 5 filtering

Confirms the conjecture for small $k$ and probes for patterns; cannot reach the Theorem-5 floor
($x=332645$). Exhaustive search $0\le x,y\le2000$ (S4) and $z\le10000$ (S14) found only the two
known solutions. For any future verification, apply the filters in order of cost: Theorem T
($k_y\equiv k_x-1\pmod5$, $\geq5\times$), Theorem M (size, $\sim$half), then the mod-$3^n$/mod-$2^n$
portrait — all independent, so they compose multiplicatively.

### [LOW] arXiv survey / WATCH (sole active priority)

**Ongoing literature watch.** As of Session 39, **28 consecutive negative confirmations** of the
two-comparable-S-units barrier. The necessary-and-sufficient open target is any unconditional
*effective* gap bound $|z^3-3^y|>C(z^3)^\kappa$ with a fixed $\kappa>1$ (the realized exponent
$E=\log(2^x+5)/\log(z^3)$ densely fills $(2/3,1)$, S31). Frontier, unchanged:

- **Bugeaud** (arXiv:2503.22084, 2604.27490): effective $|z^d-S\text{-unit}|$ bounds only
  "$\to\infty$ with $z^d$" — trivially met, not power-saving.
- **CDT holonomy** (arXiv:2510.04156) and **Badziahin**: effective $\mu(2^{1/3})>2\gg1.107$;
  the target is sub-Dirichlet, so irrationality measures categorically cannot reach it (S25).
- **Decidability** (KLNOW; Dong–Shafrir arXiv:2505.19141, STOC 2026): settled only for $\le2$
  primes / degree-$\le1$ free terms; $k\ge3$ primes "an outstanding open problem"; a *general*
  degree-3 decidability theorem is provably impossible (arXiv:2510.00759, S30) — watch only for a
  *bespoke special-structure* Kuromine argument.

Watch for genuinely new *separation/gap* techniques that beat the Dirichlet floor on the
$2^{2/3}$ approximation or supply $\kappa>1$ directly. See the arXiv reference notes under
`knowledge/references/`.

---

## Retired Directions

Full reasoning for each is in `knowledge/dead_ends.md`; the original derivations are in the cited
session logs.

- **[RETIRED S3] Effective irrationality measure for $2^{1/3}$** — realized exponent
  $\kappa_{\text{real}}<1$ (negative for $k_y\ge1$); measures only constrain good approximations.
  Two-comparable-S-units regime. (dead_ends.md; `irrationality_measure_obstruction.md`.)
- **[RETIRED S4] Primitive divisor / growth (Zsygmondy, BHV)** — congruence form soft-obstructed;
  $B$ is not a Lucas/Lehmer sequence. (dead_ends.md.)
- **[RETIRED S4] Modular method / Frey curves** — no varying prime exponent; no Frey curve.
  (dead_ends.md; `modular_method.md`.)
- **[RETIRED S5] Baker's method (all variants, incl. Yu's $p$-adic Baker)** — $v_p(\Lambda_p)=0$
  for $p\in\{2,3\}$, so no Baker upper bound can be violated. (dead_ends.md; `baker_method.md`.)
- **[RETIRED S5] Skolem / Bertók-Hajdu** — needs local non-solvability; the phantom makes the
  equation locally solvable everywhere. (dead_ends.md.)
- **[RETIRED S13] Chabauty-Kim / algebraic geometry** — categorical mismatch (exponents are not
  algebraic coordinates). Fifth categorical barrier. (dead_ends.md; `log/20260626_120000.md`.)
- **[RETIRED S14] gpf($z^3-5$) reformulation** — conflates $\{2,3\}$-smoothness with sum-
  representability. (dead_ends.md.)
- **[RETIRED S18] Thue-Mahler / norm-form** — no single-S-unit casting survives the additive
  constant 5; finiteness per fixed $y$ but no family uniformity. (dead_ends.md;
  `thue_mahler_approach.md`.)
- **[RETIRED S18] Elliptic / Mordell curve (fix one variable)** — same per-fixed-variable wall as
  Thue-Mahler; $N_{k_x}$ has $\sim10^5$ digits, no uniformity. (dead_ends.md.)
- **[RETIRED S19] Cyclotomic phantom family** — Theorem O (parity partition) and uniqueness of
  $c_1=5$ derived, but soft obstruction universal; no transfer to $c=5$. (dead_ends.md;
  `log/20260627_000000.md`.)
- **[RETIRED S21] Coupling-Height / Moving-Filtration framework** (theory-building) — both lemmas
  refuted: Lemma A circular, Lemma B′ false ($\inf D_{\ge0}=0$). 3-adic depth handle non-
  transferable. (dead_ends.md; `log/20260627_120000.md`.)
- **[RETIRED S24] Differential Progression framework** (theory-building) — 3-adic Taylor data is
  equivalent to the Theorem-J lifting law; no new information. (dead_ends.md;
  `log/20260626_120100.md`.)
- **[RETIRED S22] Linear-exponential decidability route** — blocked by the free degree-3 cube term
  (collapses onto the per-fixed-variable wall; engine is Baker, itself dead). (dead_ends.md;
  `linear_exponential_decidability.md`.)
- **[RETIRED S28] Cubic-Transversality / Dial–Lattice framework** (theory-building) — Lemma C
  refuted via the exact identity $\operatorname{dist}(R_y(x),3\mathbb Z)=3\operatorname{dist}
  ((2^x+3^y+5)^{1/3},\mathbb Z)$, returning the Session-3 sub-Dirichlet $2^{2/3}$ obstruction.
  Lemma D (phantom confined to $y<0$) kept as a clarification. **DO NOT REOPEN.** (dead_ends.md;
  `cubic_transversality_framework.md`; `log/20260628_000000.md`.)
- **[RETIRED S38] Integral Valuation-Budget framework** (theory-building, SPECIAL DIRECTIVE) —
  local-global / valuation-budget obstruction. Lemma VB-1 (budget rigidity) proved but = Cubic-
  Transversality Lemma D; Lemma VB-2 (height–integrality incompatibility) proved equivalent to the
  missing $\kappa>1$ gap bound. Seventh theory-building confirmation. Kept residuals: multi-prime
  joint portrait (phantom on family branch at all primes $7..127$) and the budget-cancellation
  identity $v_3(A)+v_3(B)=0$. (dead_ends.md; `valuation_budget_framework.md`; `log/20260704_000000.md`.)
- **[RETIRED S39] Geometry-of-Numbers / Successive-Minima framework** (theory-building, SPECIAL
  DIRECTIVE) — keep the equation 2-dimensional via the log-lattice of forms $L_1=x\log2-3\log z$,
  $L_2=y\log3-3\log z$; ask whether successive minima admit a Minkowski determinant bound. Lemma GN-1
  (Degeneration Law) **proved & kept** (new fact): on the survival wedge $\lambda_1=|L_1|\sim
  e^{-(x\log2-y\log3)}$ super-tiny, $\lambda_2=|L_2|\sim x\log2-y\log3$ huge, $\det\to0$ — lattice
  maximally degenerate; exact offset $(-\log|L_1|)-D=(1-j)\log3$ (Wolfram). Lemma GN-2 (crux) proved
  equivalent to the open $\kappa>1$ gap bound (problem collapses to the single $\{\log2,\log3\}$ first
  minimum). Eighth theory-building confirmation. (dead_ends.md; `geometry_of_numbers_framework.md`;
  `log/20260627_060000.md`.)
- **[RETIRED] $p$-adic elimination (standalone)** — phantom is a global rational cube, so the
  equation is locally solvable at every prime; congruence sieving alone is inert. Derived
  congruences are kept as auxiliary constraints. (dead_ends.md; `p_adic_methods.md`,
  `two_adic_structure.md`.)

---

## History of Changes

One line per session; full detail in the corresponding `log/` file and (for retirements)
`knowledge/dead_ends.md`.

- **S1 (2026-06-25):** Added [HIGH] Factorization and [MEDIUM] Thue-Mahler; elevated $p$-adic.
- **S2 (2026-06-25):** Downgraded standalone $p$-adic elimination to [LOW] (phantom = global
  rational cube ⇒ locally solvable everywhere); added [HIGH] effective-approx-to-$2^{1/3}$.
- **S3 (2026-06-25):** RETIRED effective-approx-to-$2^{1/3}$ ($\kappa_{\text{real}}\approx0.62$,
  Thue value too large); added the reduced equation $2^x+5=A\cdot B$; elevated primitive-divisor.
- **S4 (2026-06-25):** RETIRED primitive-divisor and modular/Frey; downgraded Factorization toward
  MEDIUM (sub-qs (b),(c) closed); search to $x,y\le2000$.
- **S5 (2026-06-25):** RETIRED Baker (all variants, $v_p=0$) and Skolem; $A=1$ sub-theorem; phantom
  algebraic origin ($c=5$).
- **S6 (2026-06-25):** Literature survey, no new tool; refined congruences on $A$ (descent).
- **S7 (2026-06-25):** Corrected universal constraints (Theorems E–H; $A\equiv11\bmod16$).
- **S8 (2026-06-25):** $(k_x,k_y)$-indexed $A$-branches (Theorems I/J/K); ABC quality $0.888<1$.
- **S9 (2026-06-25):** 3-adic portrait of $B$ (Theorem L); local portrait complete for both factors.
- **S10 (2026-06-25):** $k_x\mapsto A$ explicit 3-adic analytic bijection; Bugeaud papers N/A.
- **S11 (2026-06-25):** Badziahin (2509.01105) N/A; $\kappa_{\text{real}}$ negative for $k_y\ge1$.
- **S12 (2026-06-25):** Zhou IUT-abc (2503.14510) N/A (quality $<1$); June-2026 sweep negative.
- **S13 (2026-06-26):** RETIRED Chabauty-Kim (categorical, fifth barrier); added/explored gpf idea.
- **S14 (2026-06-26):** RETIRED gpf (conflation); proved **Theorem M**; added [MEDIUM] Theorem-M
  direction; search to $z\le10000$.
- **S15 (2026-06-26):** Proved **Theorem N** ($v_3(2^x+5-A^3)=j+1$); CLOSED bounded-$A$ (metric face).
- **S16 (2026-06-26):** CLOSED Theorem-M sub-q (b) (Case-II window); added [LOW] $c=5$ and
  function-field directions.
- **S17 (2026-06-26):** RETIRED function-field analog (as hard as integer case); cyclotomic
  characterization of $c=5$; added [LOW] cyclotomic phantom family.
- **S18 (2026-06-26):** RETIRED Thue-Mahler and (≈)elliptic-curve (per-fixed-variable wall);
  $v_{37}(2^x+5)=1$.
- **S19 (2026-06-27):** RETIRED cyclotomic phantom family (Theorem O; soft obstruction universal).
  All non-watch directions exhausted; enter monitoring.
- **S20 (2026-06-27):** SPECIAL DIRECTIVE — built Coupling-Height / Moving-Filtration framework
  (Lemmas A, B; both refuted S21).
- **S21 (2026-06-27):** RETIRED Coupling-Height (Lemma A circular, Lemma B′ false, $\inf
  D_{\ge0}=0$); 3-adic depth handle non-transferable.
- **S22 (2026-06-26):** RETIRED linear-exponential decidability route (free degree-3 cube blocks);
  added watch item.
- **S23 (2026-06-26):** WATCH (12th, neg); re-verified soft obstruction ($1000/27$ cube mod 195/195
  primes); $D$-min descends to $0.1446$.
- **S24 (2026-06-26):** SPECIAL DIRECTIVE — built & RETIRED Differential Progression framework
  (≡ Theorem-J lifting law).
- **S25 (2026-06-26):** WATCH (14th, neg); verified all pending Wolfram anchors; target is sub-
  Dirichlet (outside the measure paradigm).
- **S26 (2026-06-26):** WATCH (target-audit); corrected open target to "any effective $\kappa>1$",
  realized exponent $E\in(2/3,1)$.
- **S27 (2026-06-27):** SPECIAL DIRECTIVE — built Cubic-Transversality / Dial–Lattice framework
  (Lemma D proved, Lemma C unproven crux).
- **S28 (2026-06-28):** RETIRED Cubic-Transversality (Lemma C refuted via exact dist-identity);
  attack-face inventory complete; WATCH sole priority.
- **S29 (2026-06-26):** WATCH (17th, neg); proved the Eisenstein-norm condition on $B$ is automatic
  (multiplicative-side soft obstruction).
- **S30 (2026-06-26):** WATCH (18th, neg); arXiv:2510.00759 — no *general* degree-3 decidability
  theorem can exist; narrowed watch item (b).
- **S31 (2026-06-26):** WATCH (19th, neg); realized gap exponent $E$ densely fills $(2/3,1)$, floors
  at $2/3$ — pins the $\kappa>1$ target as sharp.
- **S32 (2026-06-26):** WATCH (20th, neg); proved **Theorem P** (2-adic mirror law) and
  **Observation Q** (variable separation), completing the $p$-adic portrait.
- **S33 (2026-06-26):** WATCH (22nd, neg); proved **Theorem R** (2-adic Newton/tangent expansion,
  slope $v_2=4$), completing the 2-/3-adic tangent-valuation symmetry.
- **S34 (2026-06-26):** WATCH (23rd, neg); proved **Theorem S** (Convergent–Depth Trade-off Law);
  first concrete bounded-$A$ lattice point, excluded with $\sim10^9$ margin.
- **S35 (2026-06-27):** WATCH (24th, neg); proved **Theorem T** (5-adic valuation sieve,
  $k_y\equiv k_x-1\bmod5$, eliminates 80%); first use of the prime 5; soft-obstructed.
- **S36 (2026-06-27):** WATCH (25th, neg); proved **Theorem U** (5-adic portrait of $z$:
  $v_5(z)=1$ universally on survival sub-lattice; bijective $z'=z/5 \bmod 5^n$; prime-5-unique
  scan; combined CRT $z\equiv3910\pmod{4320}$; survival fraction $\to16.13\%$). Wolfram MCP
  unavailable; Python-verified.
- **S37 (2026-06-27):** WATCH (26th, neg). (i) **CORRECTION to Theorem R**: exact law
  $v_2(c_k)=4k$ is FALSE — $v_2(c_3)=11\ne12$, $|v_2(c_k)-4k|\le2$ for $k\le50$; corrected
  to slope/analyticity statement ($\liminf v_2(c_k)/k=4$). (ii) **Theorem V**: sharpest
  T-surviving near-boundary pair $(k_x=84180, k_y=159334, D=0.537)$ has $A\in\{1..5\}$,
  eliminated by Theorem P alone ($A\equiv11\bmod16$ forces $A\ge11>5.13$); Session-34 witness
  $(k_x=16836)$ eliminated by Theorem T alone. Python-verified.
- **S38 (2026-06-27):** WATCH (27th, neg). SPECIAL DIRECTIVE — built & RETIRED the **Integral
  Valuation-Budget framework** (local-global obstruction; Lemma VB-1 = Cubic-Transversality
  Lemma D; Lemma VB-2 = the open $\kappa>1$ target; seventh theory-building confirmation). New
  Wolfram: multi-prime joint portrait (phantom on family cube-root/$B$ branch at all primes
  $7..127$) and budget cancellation $v_3(A)+v_3(B)=v_3(2^x+5)=0$, genuine $(0,0)$ vs phantom
  $(1,-1)$.
- **S39 (2026-06-27):** WATCH (28th, neg; checked & ruled out Le–Miyazaki arXiv:2508.17601 —
  purely-exponential, blocking-modulus engine, phantom blocks it). SPECIAL DIRECTIVE — built &
  RETIRED the **Geometry-of-Numbers / Successive-Minima framework** (fifth distinct shape; keep the
  log-lattice 2-D). Lemma GN-1 (Degeneration Law) **proved & kept**: survival-wedge log-lattice is
  maximally degenerate ($\lambda_1\sim e^{-(x\log2-y\log3)}$, $\lambda_2\sim x\log2-y\log3$,
  $\det\to0$), exact offset $(-\log|L_1|)-D=(1-j)\log3$ (Wolfram). Lemma GN-2 (crux) = the open
  $\kappa>1$ target (collapses to the single $\{\log2,\log3\}$ first minimum). Eighth theory-building
  confirmation.
