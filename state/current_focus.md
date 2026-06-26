# Current Focus

**Session:** 20260627_180000 (Session 27)

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

1. **[WATCH — primary]** Monitor arXiv for (a) an unconditional **effective gap
   bound** $|z^3-3^y| > C(z^3)^{\kappa}$ with any fixed $\kappa>1$ in the regime $3^y \approx
   2^x \approx z^3$ — watch for genuinely new *separation/gap* techniques (the auxiliary
   $2^{2/3}$-Thue casting is sub-Dirichlet, so measure improvements alone do not reach it); OR
   (b) any extension of the
   linear-exponential decidability results (KLNOW / Dong–Shafrir) to a single free
   higher-degree term, OR the $k\ge3$-prime case. Watch CDT (2510.04156), Bugeaud
   (2503.22084 / **2604.27490** — both only "$\to\infty$ with $z^d$", trivially met), and
   STOC/LICS 2026 follow-ups. **Also now watch: effective equidistribution / discrepancy bounds
   for exponential orbits $\{2^{x/3}\bmod \text{lattice}\}$** (the new Lemma-C frontier).
2. **[LOW — new, theory-building]** Attempt **Lemma C (Defect Quantization)** of the new
   Cubic-Transversality framework: can the exponential dial orbit
   $R_y(x)=(27\cdot2^x+3^{y+3}+135)^{1/3}$ be proved transversal to $3\mathbb Z$ on the survival
   wedge via an *effective equidistribution/discrepancy* bound? Honest expectation: the
   two-comparable-S-units degeneracy likely re-surfaces here; but the formulation is genuinely
   new (archimedean, phantom-free on $y\ge0$ by the proved Lemma D) and is the one untried
   angle. A clean negative (the discrepancy rate is exactly the same Diophantine quantity that
   makes Baker give $v_p=0$) would retire it and confirm the barrier is place-independent.
2. **[DO NOT ATTEMPT]** Any further 3-adic-only theory-building — the 3-adic portrait is
   complete (Theorems I–N, all now Wolfram-verified) and any such framework reduces to
   Theorem-J. New theory must introduce a genuinely new archimedean handle.
3. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs — Theorem-N corollary still
   blocks; logged for completeness only.
