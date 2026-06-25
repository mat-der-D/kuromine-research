# Current Focus

**Session:** 20260625_234500 (Session 11)

**Current direction:** Literature watch on a *new, previously-unassessed* target —
the cubic-irrational-vs-rational *separation* geometry that directly underlies |z³ − 3^y|.

**Why this direction:** Session 10 left literature watch as the primary standing path and
declared the local/structural program saturated (Sessions 7–9). Rather than repeat the
saturated computation, I searched for the closest unassessed 2024–2026 papers on the exact
quantified target and found two: Badziahin's "Distance between cubics and rationals"
(arXiv:2509.01105 / Results in Math. 2026) — the most on-target paper to date, studying how
close a cubic can be to a rational — and Bajpai's effective many-term S-unit thesis.

## Session 11 main results

1. **Badziahin arXiv:2509.01105 (Results in Math. 2026) — NOT APPLICABLE.**
   - The paper bounds |ξ − p/q| for **cubic irrationals** ξ via root-separation of cubics;
     its nontrivial range is **2 ≤ v ≤ 3**, and **all results are conditional on abc/Hall**
     (under abc: interior of D_{3,1} is u > 10 − 3v).
   - Kuromine cannot be cast into that regime. Three castings, all fail (Wolfram):
     - "cube − square" (|z³ − 3^y|, Hall directly): needs y even; but y ≡ 1 (mod 2)
       (indeed ≡ 3 mod 6) for **every** member of the Theorem-5 family. Fails.
     - "cube − cube" (y = 3j): the nearby cubic 3^j is a *rational integer*, not a cubic
       *irrational* — Badziahin's machinery degenerates. (= old factorization approach.)
     - "Thue / 2^{2/3}" (the only casting giving a genuine cubic irrational): the realized
       separation exponent v_real (|2^{2/3} − z/W| ~ W^{−v_real}) is **0.623 at the floor
       k_y = 0** (= Session-3 κ_real, confirmed) and **NEGATIVE for every k_y ≥ 1**
       (−1.75, −4.13, −6.51, …): z/W *diverges* from 2^{2/3}. Far below the v ≥ 2 needed.

2. **Sharpening of Session 3:** κ_real is not a single ≈ 0.62; it is 0.62 only at the family
   floor (k_y = 0) and goes negative for all k_y ≥ 1 — for almost the whole Theorem-5 family
   the cubic approximation z/W to 2^{2/3} *diverges* (because 3^y grows faster than 2^x along
   the progression). The two-S-units barrier is thus even more severe than recorded.

3. **Bajpai effective many-term S-unit equations — NOT APPLICABLE.** Method = Baker's linear
   forms in logarithms (retired Session 5; v_p = 0 so no bound violable), and it requires all
   terms to be S-units, which z³ and the constant 5 are not (= Session 8 obstruction).

## Where things stand (updated after Session 11)

- All Baker variants, congruence/local methods, size/Thue methods, modular/Frey,
  primitive-divisor, Skolem, ABC, the explicit 3-adic-analytic map, Bugeaud
  perfect-power−S-unit bounds: RETIRED / ruled out (Sessions 1–10).
- Session 11 adds the **cubic-vs-rational separation** avenue (Badziahin 2026) to the ruled-out
  list: conditional on abc/Hall, nontrivial only for good approximations 2 ≤ v ≤ 3, and the
  Kuromine cubic approximation realizes v_real < 1 (negative for almost all members).
- abc itself gives no leverage: Kuromine's abc-quality ≈ 0.888 < 1 (Session 8), so even
  granting abc the Badziahin bounds are vacuous here.

**Honest assessment (Session 11):** No progress toward a proof; the fundamental barrier is
unchanged. Three independent literature lines now confirm it structurally: effective
irrationality measures (Session 3), Bugeaud perfect-power−S-unit differences (Session 10), and
Badziahin cubic-vs-rational separation (Session 11). All collapse on the two-comparable-S-units
regime (3^y ≈ z², κ_real ≈ 0.62 at the floor and divergent above it), and the relevant cubic
results are additionally only conditional on abc/Hall. The precise open target is unchanged: an
**unconditional effective bound with approximation exponent below ~1.1** in the
two-comparable-S-units regime — nonexistent in the 2024–2026 literature. The research remains
correctly positioned on literature watch for exactly this.
