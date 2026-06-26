# Current Focus

**Session:** 20260626_HHMMSS (Session 25)

**Current direction:** WATCH-phase (sole active priority). This session was a Wolfram-enabled
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

## Where things stand (unchanged in substance since Session 21)

The conjecture is reduced to a single unconditional open target:
$$|z^3 - 3^y| > C\cdot(z^3)^{\kappa}, \quad \kappa < 1.107, \qquad (3^y \approx z^2),$$
a tool that does not currently exist — and (sharpened this session) **cannot be supplied by
any irrationality measure**, since $\kappa < 1.107 < 2$ is below the Dirichlet floor. The
target is a sub-Dirichlet gap inequality. Two structurally distinct frontiers gate it:
the metric/analytic two-comparable-S-units barrier and the degree-3 free-cube barrier to
decidability methods. Both rest on Baker being inapplicable. Two theory-building attempts
(S20–21 Coupling-Height, S24 Differential-Progression) have confirmed that no 3-adic-only
framework can bridge this gap.

## Next priority

1. **[WATCH — sole active priority]** Monitor arXiv for (a) an unconditional **sub-Dirichlet
   gap bound** $|z^3-3^y| > C(z^3)^{\kappa<1.107}$ in the $3^y \approx z^2$ regime — note this
   is NOT an irrationality measure (it is below the $\mu\ge2$ floor), so watch for genuinely
   new *separation/gap* techniques, not measure improvements; OR (b) any extension of the
   linear-exponential decidability results (KLNOW / Dong–Shafrir) to a single free
   higher-degree term, OR the $k\ge3$-prime case. Watch CDT (2510.04156), Bugeaud, and
   STOC/LICS 2026 follow-ups.
2. **[DO NOT ATTEMPT]** Any further 3-adic-only theory-building — the 3-adic portrait is
   complete (Theorems I–N, all now Wolfram-verified) and any such framework reduces to
   Theorem-J. New theory must introduce a genuinely new archimedean handle.
3. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs — Theorem-N corollary still
   blocks; logged for completeness only.
