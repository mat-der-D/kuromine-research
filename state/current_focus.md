# Current Focus

**Session:** 20260701_000000 (Session 32)

## Session 32 main result (WATCH negative, 20th confirmation; NEW Theorem P = 2-adic mirror law for $A$, + Observation Q = variable separation, Wolfram-verified)

WATCH-phase session plus a concrete Wolfram computation filling a real gap in the documented
$p$-adic portrait of $A = z - 3^j$. The 3-adic side was fully developed (Theorems I/J/K/L:
$A \bmod 3^n$ determined by $k_x \bmod 3^{n-4}$, bijection $\mathbb Z_3\to\mathbb Z_3$), but the
2-adic side was recorded only as the static fact $A \equiv 11 \pmod{16}$ (Theorem K). This
session computed the full 2-adic lifting law.

**arXiv watch (twentieth confirmation, negative).** Unchanged: Bugeaud 2503.22084 / 2604.27490
still only "$\to\infty$ with $z^d$" (not power-saving $\kappa>1$); $k\ge3$-prime decidability
(Dong–Shafrir 2505.19141, STOC 2026) still "an outstanding open problem"; degree-3 free terms
blocked (2510.00759); CDT/Badziahin $\mu(2^{1/3})>2\gg1.107$ and sub-Dirichlet-blind.

**Theorem P (NEW, Wolfram-verified) — 2-adic mirror law for $A$.** With $z = 2u$ ($u$ odd,
$v_2(z)=1$ since $v_2(3^y+5)=3$ universally on the family, $y$ odd):
1. $A \equiv 11 \pmod{16}$ universally (fixed 2-adic preamble $[1,1,0,1]$).
2. For $n\ge5$, $A \bmod 2^n$ is determined by **$k_y \bmod 2^{n-4}$** (period exactly $2^{n-4}$,
   independent of $k_x$); distinct-value count is $2^{n-4}$ (Wolfram, $n=5..11$).
3. $k_y \mapsto A$ is a **bijection $\mathbb Z_2 \to 11+16\mathbb Z_2$** — no 2-adic obstruction.
The "$-4$" offset comes from $v_2(166320)=4$, exactly mirroring the 3-adic $v_3(2^{332640}-1)=4$.
Both periods carry the same $-4$ (coincidence of the specific moduli $332640=2^5 3^3 5\cdot7\cdot11$,
$166320=2^4 3^3 5\cdot7\cdot11$). See Theorem P in `knowledge/problem.md`.

**Observation Q (NEW) — variable separation.** The 3-adic digits of $A$ are a bijective function
of $k_x$ **alone**; the 2-adic digits of $A$ are a bijective function of $k_y$ **alone** (Wolfram
$3\times3$ grid). The constant 5 couples the two places only through the archimedean size
$A \approx 2^{x/3}$. This is the sharpest $p$-adic statement of *why* all congruence/$p$-adic
methods fail: $A$ is simultaneously a free 2-adic unit (in $k_y$) and a free 3-adic unit
(in $k_x$); no congruence (at 2, at 3, or jointly by CRT) can pin it off a genuine value. The
"2 integer parameters vs 3 independent matching conditions" over-determination is a **heuristic,
not a proof** ($p$-adic conditions are satisfiable in $\mathbb Z_2,\mathbb Z_3$, not forced into
$\mathbb Z$) — the $p$-adic-side restatement of the two-comparable-S-units wall.

**Net.** No new direction; a genuinely new structural theorem (Theorem P) completes the $p$-adic
portrait and gives the cleanest positive statement of the obstruction's $p$-adic face. Confirms,
does not breach, the wall (twenty-first structural confirmation). WATCH remains the sole active
priority. No framework built (Session-28 inventory-complete verdict).

---

## Session 31 main result (WATCH negative, 19th confirmation; new Wolfram sharpening of the open-target exponent — E densely fills (2/3,1) and floors at 2/3)
**(prior session — retained below)**

## Session 31 main result (prior) — original heading preserved

**Session (prior):** 20260630_000000 (Session 31)

## Session 31 main result (WATCH negative, 19th confirmation; new Wolfram sharpening of the open-target exponent — E densely fills (2/3,1) and floors at 2/3)

This was a WATCH-phase session followed by a concrete Wolfram experiment (no new framework,
per the Session-28 inventory-complete verdict).

**arXiv watch (nineteenth confirmation, negative).** All frontiers unchanged:
- Bugeaud arXiv:2503.22084 (squares) / 2604.27490 (degree-d): effective lower bounds for
  $|z^d - S\text{-unit}|$ and its greatest prime factor still only **"tend to infinity with
  $z^d$"** — trivially met by the Kuromine gap $2^x+5\to\infty$; NOT a power-saving $\kappa>1$.
- Decidability of linear-exponential systems over $k\ge3$ primes is still confirmed
  (Dong–Shafrir, arXiv:2505.19141, STOC 2026 page) to be "**an outstanding open problem in
  number theory**"; settled only for $\le2$ primes / degree-$\le1$ free terms. Degree-3 free
  terms remain blocked (and arXiv:2510.00759, S30, proves no *general* degree-3 decidability
  theorem can exist). No LICS/STOC 2026 follow-up reaches the Kuromine regime.
- CDT holonomy arXiv:2510.04156 and Badziahin (2301.02391) effective measures for $2^{1/3}$
  still $\mu>2 \gg 1.107$; and the target is sub-Dirichlet, so measures categorically cannot
  reach it. No 2026 follow-up below $\sim1.1$.

**New Wolfram sharpening of the open target (recordable, confirms not breaches the wall).**
Computed the realized gap exponent $E=\log(2^x+5)/\log(z^3)$ at the *largest surviving* $k_y$
for several $k_x$ (Wolfram, 40-digit):

| $k_x$ | $k_y$ | $D=x\log2-(2j+1)\log3$ | $E=\log(2^x+5)/\log(z^3)$ |
|------|------|------|------|
| 1     | 0      | $108759$ | $1$ (i.e. $1-e^{-47854}$) |
| 2     | 2      | $95699$  | $0.84125\ldots$ |
| 3     | 4      | $82639$  | $0.75712\ldots$ |
| 1054  | 1993   | $121804$ | $0.66700\ldots$ |
| 4729  | 8950   | $54.99$  | $0.6666667\ldots$ |
| 84180 | 159334 | $0.5367$ | $0.66666666672\ldots$ |

As the surviving pairs approach the two-comparable-S-units boundary $D\to0^+$ (which they do
arbitrarily, $\inf D_{\ge0}=0$ by Weyl equidistribution, S21), $E$ **decreases monotonically to
$2/3^+$**; at the family floor $k_y=0$, $E=1^-$. So $E$ **densely fills $(2/3,1)$ and floors at
exactly $2/3$**. Wolfram-confirmed the floor symbolically: at the boundary $2^x\approx3^{2j+1}$,
$3^y\approx z^3$, so $E\to\lim_{j\to\infty}(2j+1)/(3j)=2/3$ (`Limit` = 2/3). This makes the
"necessary-and-sufficient $\kappa>1$" framing sharp and unbridgeable: **any** fixed effective
$\kappa$ with $2/3<\kappa<1$ is *violated* at near-boundary surviving pairs (where $E<\kappa$),
and $E<1$ everywhere, so only a uniform $\kappa>1$ resolves the family — exactly the tool that
does not exist. The realized-exponent *range* is now pinned to the half-open interval
$(2/3,1)$ with both endpoints as limit points.

**Frame constants re-confirmed to 25 digits (Wolfram):** $3-3\log_3 2=1.1072107392856\ldots$,
$3\log2/\log3=1.8927892607143\ldots$, $2\log3/(3\log2)=1.0566416671474\ldots$. Near-boundary
minimal nonnegative $D$ over $k_x\le200000$ is $0.53666886633\ldots$ at $(k_x,k_y)=(84180,159334)$.

**Net.** No new direction; the experiment sharpens (does not breach) the wall by pinning the
realized-exponent range to $(2/3,1)$. WATCH remains the sole active priority. No framework built.

## Session 30 main result (WATCH negative, 18th confirmation; new paper arXiv:2510.00759 sharpens the degree-3 decidability barrier — Wolfram-verified re-anchor)

## Session 30 main result (WATCH negative, 18th confirmation; new paper arXiv:2510.00759 sharpens the degree-3 decidability barrier — Wolfram-verified re-anchor)

This was a pure WATCH-phase session. The arXiv watch surfaced **one genuinely new, previously
unassessed paper** and the rest of the frontier was re-confirmed unchanged.

**New paper: arXiv:2510.00759 (Feb 2026), "Cubic incompleteness: Hilbert's tenth problem begins
at degree three"** — satisfiability of a *single* Diophantine equation of **total degree ≤ 3**
over $\mathbb N$ is **Σ⁰₁-complete (undecidable)**. **Assessment (confirms, does not breach, the
S22 decidability/degree face):** the S22 barrier recorded that KLNOW/Dong–Shafrir decidability
(2505.19141) is settled only for ≤2 primes and degree-≤1 free terms, with the hope of a future
extension to degree-≥2/degree-3 free terms. 2510.00759 shows that hope is **impossible in
general** — degree 3 is exactly where *universal* undecidability begins, so no *general*
decidability extension to degree-3 free terms can exist. Any decidability route to Kuromine must
therefore be a **bespoke special-structure argument** (two fixed-base exponentials + one cube),
never a general decision procedure. Stated honestly: this does **NOT** make Kuromine itself
undecidable (Kuromine is one structured family, not the universal cubic class); it **sharpens
why** the S22 face is closed and removes "await a general degree-3 decidability theorem" from the
WATCH list. **Eighteenth confirmation of the wall (negative).**

**Other frontiers unchanged:** Bugeaud 2503.22084 / 2604.27490 still only "$\to\infty$ with
$z^d$" (no power-saving $\kappa>1$); Baker $\mu(2^{1/3})\le2.955$, Voutier $\kappa<2$ only for
$(c+1)/c$ roots near 1 (not $2^{1/3}$), CDT 2510.04156 still $\mu(2^{1/3})>2\gg1.107$; and the
target is sub-Dirichlet ($E\to2/3$), so measures categorically cannot reach it.

**Wolfram re-anchor (high precision, this session).** At the near-boundary surviving pair
$(k_x,k_y)=(84180,159334)$: minimal nonnegative $D=0.53666886633\ldots$ (minimal nonneg over
$k_x\le200000$); $\log2^x=1.94093\times10^{10}$,
$\log3^y=2.91139\times10^{10}$ (so $3^y$ dominates $z^3$); realized gap exponent
$E=\log(2^x+5)/\log(z^3)=\mathbf{0.66666666670696\ldots}\to2/3^+$, far below the needed
$\kappa>1$. Frame constants re-confirmed to **25 digits**: $3-3\log_3 2=1.1072107392856277\ldots$,
$3\log2/\log3=1.8927892607143723\ldots$, $2\log3/(3\log2)=1.0566416671474375\ldots$.
Structural check (Wolfram `Factor`): $z^3-n$ is irreducible over $\mathbb Q[z]$ — Kuromine's free
term is genuinely degree 3, sitting exactly at the 2510.00759 undecidability threshold; known
solution $z=4$ for $(5,3)$ verified.

**Net.** No new direction; the new paper closes a sub-hope on the already-mature S22 face. WATCH
remains the sole active priority (item (b) narrowed: only a *special-structure* Kuromine
decidability argument, not a general degree-3 theorem). No framework built (Session-28
inventory-complete verdict).

## Session 29 main result (WATCH confirmed negative; Eisenstein-norm condition on $B$ proved AUTOMATIC, Wolfram-verified)

This session ran the mandated arXiv watch (**seventeenth confirmation, negative**) and then,
rather than re-deriving a fourth framework destined to collapse onto an existing attack face
(explicitly forbidden by the Session-28 state), executed a concrete **Wolfram density
experiment** on the one remaining multiplicative handle — the requirement that the Eisenstein
factor $B = z^2 + z\,3^j + 3^{2j}$ have **all prime factors $\equiv 1 \pmod 3$**.

**New finding (Wolfram, recordable, but inert — confirms not breaches the wall).** The
"all prime factors of $B$ are $\equiv 1 \pmod 3$" condition is **NOT** an independent constraint
that a genuine solution must satisfy by chance: it is **forced automatically** by
$\gcd(z, 3^j) = 1$ (which holds for the family since $z \equiv 1 \pmod 3$, so
$\gcd(z, 3^j)=1$). Concretely (Wolfram):
- For *arbitrary* $z \equiv 1$, $w \equiv 0 \pmod 3$ **without** the coprimality, the condition
  **fails frequently** (6 of 8 random samples) — a prime $p \equiv 2 \pmod 3$ dividing
  $\gcd(z,w)$ enters $B$ to odd power.
- With $\gcd(z,w) = 1$ enforced, the condition holds in **12 of 12** samples — classical:
  primitive values of the principal Eisenstein form $z^2+zw+w^2$ are products of split primes
  ($\equiv 1 \bmod 3$) only.

So the $B$-norm condition reduces to $\gcd(z, 3^j)=1$, which is automatic on the family.
This is a **fresh, multiplicative/density-side confirmation** of the Session-4 "soft
obstruction" verdict (previously argued congruence-side): the factorization $2^x+5 = A\cdot B$
imposes **no** new global constraint. The phantom ($A=3$, $B=37/3$) again sits on the inert side
($37/3$ is the non-integral image, but every *integer* congruence on $B$ is phantom-compatible).

**Confirmed separations (re-verified, non-actionable).** The genuine $A \equiv 427 \pmod{432}$
($22 \bmod 27$, $11 \bmod 16$) vs the phantom $A = 3$ (an exact integer, $3 \bmod$ everything):
a real 2-adic + 3-adic separation, but $A$ ranges bijectively as a 2-adic and 3-adic unit
(Sessions 6–10), so no finite/$p$-adic congruence pins it off a genuine value.

**Quantitative open-target re-anchor (Wolfram).** Independently re-derived at the near-boundary
surviving pair $(k_x,k_y) = (84180, 159334)$: minimal nonnegative $D = 0.53667$, and the
realized gap exponent $E = \log(2^x+5)/\log(z^3) = 0.66666666672\ldots \to 2/3^+$ — far below the
necessary-and-sufficient $\kappa>1$. Frame constants re-confirmed to 20 digits
($3-3\log_3 2 = 1.10721\ldots$, $3\log2/\log3 = 1.89279\ldots$, $2\log3/(3\log2) = 1.05664\ldots$).

**Net.** No new direction; the experiment confirms (does not breach) the wall and is recorded as
a sharpening of the factorization soft-obstruction. WATCH remains the sole active priority. No
framework built this session: per the Session-28 inventory-complete verdict, a fourth framework
would collapse onto the factorization/soft-obstruction face (exactly what the experiment shows).

## Session 28 main result (Lemma C REFUTED, Cubic-Transversality framework RETIRED, Wolfram-verified)

This session attacked **Lemma C** — the unproven crux of the Session-27 Cubic-Transversality /
Dial–Lattice framework — and **refuted it as a route**, retiring the framework. The decisive
finding is an **exact identity** (Wolfram `Simplify` = 0):
$$\operatorname{dist}\big(R_y(x),\,3\mathbb Z\big) \;=\; 3\cdot
\operatorname{dist}\big((2^x+3^y+5)^{1/3},\,\mathbb Z\big),\qquad
R_y(x)=(27\cdot2^x+3^{y+3}+135)^{1/3}.$$
The dial-orbit discrepancy from $3\mathbb Z$ is **exactly 3 times the original cube-root
distance** of $z=(2^x+3^y+5)^{1/3}$ from $\mathbb Z$ — the $\times27$ / $W=3z$ rescaling is
undone by the cube root, so the "new archimedean object" is the original cube-distance.

Because the Theorem-5 family has $x\equiv 2\pmod 3$ (Wolfram: $5\equiv2$, $332640\equiv0$),
$2^x=4M^3$ with $M=2^{(x-2)/3}$, and the discrepancy is governed by the rational approximation
of $2^{2/3}=4^{1/3}$ by $m/M$ ($M$ a power of two) — **exactly the Session-3 auxiliary
$2^{2/3}$-Thue quantity**. Wolfram confirmed: (i) the discrepancy descends toward 0 along deep
$2^{2/3}$-convergents (e.g. $\operatorname{dist}\approx0.0026$ at $x=35$), so it has **no
positive constant lower bound**; (ii) the realized approximation exponent on the family is
**sub-Dirichlet** ($\kappa\le1.21$, negative for most pairs). An effective lower bound would
require an effective irrationality measure $\mu(2^{2/3})<3$ acting on *these* approximations,
but they are sub-Dirichlet, so **no measure acts**. The barrier re-surfaces exactly as
Session 27 predicted. **Sixth independent confirmation** that the barrier is place-independent
(archimedean-equidistribution face). The attack-face inventory is now **complete**: metric
(S15), analytic/irrationality (S3/10/11), 3-adic-coupling (S20–21, S24), decidability/degree
(S22), archimedean-equidistribution (S27–28) — all return the same two-comparable-S-units wall.

**Kept (Lemma D, proved S27):** in the dial form the phantom's denominator-3 escape is confined
to $y<0$, so the survival sheet is phantom-free. This remains a correct structural
clarification (retained in the reference file), but is not a step toward a proof.

**arXiv watch (sixteenth confirmation, negative):** effective-equidistribution literature
(Einsiedler–Margulis–Venkatesh; W. Kim 2110.00706) is homogeneous-dynamics on
$\mathrm{SL}_n/\mathrm{SL}_n(\mathbb Z)$, not the scalar-exponential-orbit question (which by
the S28 identity is the same wall). Bugeaud 2604.27490 still only "$\to\infty$ with $z^d$".

## Session 27 main result (negative watch + new ARCHIMEDEAN framework, Wolfram-verified)

This session executed the SPECIAL DIRECTIVE Theory-Building Protocol after a conclusively
**negative arXiv watch** (fifteenth confirmation). Decisive watch finding: the April-2026
Bugeaud paper **arXiv:2604.27490 ("On the difference between perfect powers and integral
S-units")** gives effective lower bounds for $|z^d - q_1^{a_1}\cdots q_t^{a_t}|$ "that **tend
to infinity with $z^d$**" — exactly the *trivially-satisfied* form (the Kuromine gap
$|z^3-3^y|=2^x+5\to\infty$ already), NOT a power-saving $\kappa>1$. Re-verified (Wolfram) that
at the near-boundary surviving pair ($k_x=84180$, $D=0.53667$) the realized gap exponent
$E=\log(2^x+5)/\log z^3 = 0.6666666667\to 2/3^+$, far below the needed $\kappa>1$. KLNOW/
Dong–Shafrir still degree-$\le1$/two-prime; CDT holonomy still $\mu>2$ and sub-Dirichlet-blind.

**New framework built (genuinely new ARCHIMEDEAN handle, distinct from all 4 retired
frameworks).** The **Cubic-Transversality / Dial–Lattice framework**
(`knowledge/references/cubic_transversality_framework.md`):

- **New handle (verified):** a genuine solution is an *integer* cube root ($z\in\mathbb Z$);
  the phantom is a *denominator-exactly-3 rational* cube root ($z=10/3$). With $W:=3z$, the
  equation becomes (Wolfram ✓) $W^3 = 27\cdot 2^x + 3^{\,y+3} + 135$. This is a **real/rational**
  distinction, NOT a $p$-adic one — outside every retired (place-by-place) framework.
- **Lemma D (PROVED, the clean output):** on the survival sheet $y\ge0$, any cube hit
  $W^3=27(2^x+3^y+5)$ has $27\mid W^3\Rightarrow 3\mid W\Rightarrow z\in\mathbb Z$. So the
  phantom's denominator-3 escape is **structurally confined to $y<0$**, OFF the Theorem-5
  lattice. **First formulation in which the phantom is provably ABSENT from the relevant sheet**
  (rather than soft-obstructing every test). The conjecture on $\mathcal L$ becomes pure
  transversality with *no phantom to dodge*.
- **Lemma C (UNPROVEN crux):** an effective resonance-exclusion — the exponential dial orbit
  $R_y(x)=(27\cdot2^x+3^{y+3}+135)^{1/3}$ (velocity $\theta'\asymp 2^{x/3}$, Wolfram ✓) never
  lands exactly on $3\mathbb Z$ on the survival wedge. As a naive gap bound it is vacuous
  (= the original $27|2^x+3^y+5-z^3|$); its only route is an **effective equidistribution/
  discrepancy** bound for the dial orbit — where the two-comparable-S-units degeneracy is
  expected to re-surface in a new disguise. **The framework relocates the wall to an
  archimedean equidistribution question; it does not yet breach it.**

## Session 26 main result (target-framing correction, Wolfram-verified)

This session was a WATCH-phase **target-audit pass**: I independently re-derived, with
Wolfram, the precise exponent threshold on which the *entire* reduction rests, and found
that the long-standing framing of the open target was **imprecisely stated** (conflating two
different normalizations). The substantive impasse is unchanged, but the open target is now
stated correctly and more favorably.

**Corrected open target.** For any surviving Theorem-5 solution, $|z^3 - 3^y| = 2^x + 5$, and
the *realized* exponent of this gap measured against $z^3$,
$$E(k_x,k_y) = \frac{\log(2^x+5)}{\log(z^3)} \in \left(\tfrac23,\,1\right),$$
is **strictly below 1 everywhere on the surviving family** (Wolfram): it tends to $2/3$ at the
two-S-units survival boundary ($2^x \approx 3^{2j+1} \approx z^3$, where $3^y \approx z^3$, NOT
$z^2$) and up to $1^-$ at $k_y=0$ (where it equals $1 - e^{-47854}/\log z^3$ for $k_x=1$ — the
classic $e^{-47854}$ near-coincidence). Therefore:

> **Any** unconditional *effective* lower bound $|z^3 - 3^y| > C\,(z^3)^{\kappa}$ with a fixed
> $\kappa > 1$ (e.g. $\kappa = 1.107$, or even $\kappa = 1+\varepsilon$) resolves the whole
> surviving family. The value $\kappa < 1.107 = 3 - 3\log_3 2 = 3\log_3(3/2)$ recorded since
> Session 3 is a **sufficient margin**, not a necessary ceiling; the **necessary and
> sufficient** requirement is $\kappa > 1$ (strictly; $\kappa = 1$ exactly is just barely
> insufficient because $E \to 1^-$ at $k_y=0$).

**Why this does not break the impasse.** The available Baker-type machinery gives $v_p(\Lambda_p)=0$
(Session 5), i.e. no effective gap bound with **any** $\kappa > 1$ exists — the realized
exponent sitting at $1 - e^{-47854}$ is exactly the two-comparable-S-units coincidence. So the
gap between "available" ($\kappa$ effectively $\le 1$, in fact no positive effective gap bound)
and "needed" ($\kappa > 1$) is genuine. The correction makes the *target* cleaner ($\kappa>1$
rather than the mis-stated $\kappa<1.107$-vs-$z^3$) but the *wall* is identical.

**Framing note for future sessions.** The "$3^y \approx z^2$" regime description in older logs
is imprecise: at the actual hard boundary $3^y \approx z^3$ (both S-units comparable to the
cube), with $3^y/z^2$ in log-ratio $=1.5$. The "$z^2$" only appears in the auxiliary
$2^{2/3}$-Thue casting (Session 3), not in the direct $z^3 - 3^y$ gap.

## Session 25 main results (prior)
**verification-and-consolidation pass**: the MCP tool was available, so the session resolved
ALL pending Wolfram verifications flagged in Sessions 20 and 24 (which had run with MCP
unavailable), and added one genuinely new *structural sharpening* of the open target. No new
direction was opened (all are exhausted/retired); no theory-building was triggered (the
Special Directive's theory-building has already produced two frameworks, both retired, and
re-confirmed four times that 3-adic-only data cannot bridge to an archimedean constraint).

## Session 25 main results

1. **All pending Wolfram anchors confirmed (first direct numerical verification).**
   - $v_3(2^{332640}-1) = 4$ exactly (so $g = 2^{332640} \equiv 1 \pmod{3^4}$,
     $\not\equiv 1 \pmod{3^5}$; hence $v_3(\log_3 g) = 4$). [Session 10/24 claim, now verified.]
   - Theorem I exact: $A \bmod 81 = 49, 22, 76$ for $k_x \equiv 0,1,2 \pmod 3$. ✓
   - Theorem L exact: $B \bmod 81 = 52, 79, 25$ for $k_x \equiv 0,1,2 \pmod 3$. ✓
   - Tangent speed valuation $v_3(\tau) = v_3((A^3-5)L/(3A^2)) = 0+4-1-0 = 3$. ✓
     (Session 24 Differential-Progression anchor, now verified.)
   - $\operatorname{ord}_3(2)=2$, $\operatorname{ord}_9(2)=6$, $\operatorname{ord}_{27}(2)=18$. ✓
   - Threshold $3 - 3\log_3 2 = 1.10721\ldots$; square-scale $2\log3/(3\log2) = 1.05664\ldots$;
     Theorem-M slope $3\log2/\log3 = 1.89279\ldots$. All three frame-constants re-confirmed to
     15 digits.

2. **New structural sharpening of the open target (kept, non-actionable but clarifying).**
   The open target $\kappa < 1.107$ for $|z^3 - 3^y| > C(z^3)^\kappa$ lies **strictly below
   the Dirichlet floor $\mu \ge 2$** that every irrationality measure must obey. Therefore the
   target is **categorically not an irrationality-measure statement** — improving the effective
   irrationality measure for $2^{1/3}$ (the CDT-school program) can *never* reach it, no matter
   how sharp, because measures only lower-bound *good* approximations (exponent $\ge 2$).
   Reconfirmed (Wolfram, 50-digit) that the realized approximation exponent of $z/W$ to
   $2^{2/3}$ along the family is **negative** for all $k_y \ge 1$ ($-0.585, -1.377, -2.170,
   \dots$): $z/W$ is an *anti*-approximation (it diverges from $2^{2/3}$), so no measure has
   anything to act on. This refines the Session-3/11 "$\kappa_{\text{real}}<1$" record into a
   sharper diagnosis: the needed bound is a **gap/separation inequality of sub-Dirichlet
   exponent**, a type of statement outside the entire irrationality-measure paradigm.

3. **arXiv / WebSearch watch negative (fourteenth confirmation).** CDT holonomy school
   (arXiv:2510.04156) gives effective measures for $n$-th roots, but its explicit bound
   ($\le 35.1/\eta \cdot \max\{(\log 2n)/(\eta\log a),10\}^2$) is large for $a=2$ (which is
   far from 1, where the method is weak) — $\gg 2 \gg 1.107$. KLNOW / Dong–Shafrir
   (arXiv:2505.19141, STOC 2026) decidability still settled only for two-prime bases and
   degree-$\le 1$ free terms; arbitrary base / free higher-degree term still "major
   breakthrough in number theory." No 2026 follow-up reaches the Kuromine regime.

## Where things stand (substance unchanged since Session 21; target framing corrected S26)

The conjecture is reduced to a single unconditional open target. **Corrected statement
(Session 26, Wolfram):**
$$|z^3 - 3^y| > C\cdot(z^3)^{\kappa}, \quad \kappa > 1 \text{ (effective)}, \qquad (3^y \approx z^3 \text{ at the hard boundary}),$$
i.e. **any** fixed effective $\kappa>1$ suffices uniformly (the realized exponent of the gap
vs $z^3$ lies in $(2/3,1)$, strictly below 1). The previously-recorded "$\kappa<1.107$ vs
$z^3$, in the $3^y\approx z^2$ regime" was an imprecise framing (it conflated the gap-vs-$z^3$
and gap-vs-$3^y$ normalizations, and mislabeled the boundary regime). The value
$1.107 = 3-3\log_3 2$ is a safe *sufficient* margin, not a necessary ceiling.

This is a tool that does not currently exist. Note (sharpened S25) it **cannot be supplied by
any irrationality measure** of $2^{1/3}$ (those are sub-Dirichlet considerations on the
auxiliary $2^{2/3}$-Thue casting; in the direct gap framing the obstruction is that Baker
gives $v_p(\Lambda_p)=0$, hence no positive effective $\kappa$). Two structurally distinct frontiers gate it:
the metric/analytic two-comparable-S-units barrier and the degree-3 free-cube barrier to
decidability methods. Both rest on Baker being inapplicable. Two theory-building attempts
(S20–21 Coupling-Height, S24 Differential-Progression) have confirmed that no 3-adic-only
framework can bridge this gap.

## Next priority

1. **[WATCH — sole active priority]** Monitor arXiv for (a) an unconditional **effective gap
   bound** $|z^3-3^y| > C(z^3)^{\kappa}$ with any fixed $\kappa>1$ in the regime $3^y \approx
   2^x \approx z^3$ — the necessary-and-sufficient tool; watch for genuinely new *separation/gap*
   techniques (the auxiliary $2^{2/3}$-Thue casting is sub-Dirichlet, so measure improvements
   alone do not reach it); OR (b) **[narrowed, Session 30]** a *special-structure* decidability/
   finiteness argument for the specific Kuromine family (two fixed-base exponentials + one cube),
   OR the $k\ge3$-prime case — but **NOT** a *general* degree-3 decidability theorem, which
   arXiv:2510.00759 (Feb 2026) now proves cannot exist (degree 3 is the universal-undecidability
   threshold, Σ⁰₁-complete; Kuromine's $z^3$ is genuinely degree 3, Wolfram-verified). Watch
   CDT (2510.04156), Bugeaud (2503.22084 / **2604.27490** — both only "$\to\infty$ with $z^d$",
   trivially met), KLNOW / Dong–Shafrir (2505.19141), and STOC/LICS 2026 follow-ups. **Effective equidistribution / discrepancy
   bounds for scalar exponential orbits modulo a fixed lattice are now understood (Session 28
   identity) to be equivalent to (a), hence equally hard** — watch only for results that beat
   the Dirichlet floor on the $2^{2/3}$ approximation.

2. **[RETIRED, Session 28]** **Lemma C of the Cubic-Transversality framework — REFUTED.** The
   exact identity $\operatorname{dist}(R_y(x),3\mathbb Z)=3\operatorname{dist}((2^x+3^y+5)^{1/3},
   \mathbb Z)$ shows the dial-orbit discrepancy IS (three times) the original cube-distance, and
   (via $x\equiv2\bmod3\Rightarrow2^x=4M^3$) is governed by the Session-3 sub-Dirichlet
   $2^{2/3}$-approximation quantity. The discrepancy has no positive constant lower bound
   (descends to 0 along $2^{2/3}$-convergents). Framework retired; moved to `dead_ends.md`.
   Lemma D (phantom confined to $y<0$) kept as a clarification in the reference file.

3. **[DO NOT ATTEMPT]** Any further theory-building that reduces to an existing attack face. The
   inventory is complete: metric (S15), analytic/irrationality (S3/10/11), 3-adic-coupling
   (S20–21, S24), decidability/degree (S22), archimedean-equidistribution (S27–28) — six
   confirmations, all the same wall. New theory must beat the Dirichlet floor on the $2^{2/3}$
   approximation or supply a power-saving $\kappa>1$ gap bound directly; nothing short reaches it.

4. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs — Theorem-N corollary still
   blocks; logged for completeness only.
