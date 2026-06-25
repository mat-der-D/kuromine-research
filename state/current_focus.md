# Current Focus

**Session:** 20260625_HHMMSS (Session 10)

**Current direction:** Two prongs, per Session 9's suggestions.
(1) **Literature watch** — assess the two new 2026 Bugeaud papers on "differences between
perfect powers and integral S-units" for applicability to Kuromine.
(2) **Suggestion #1** — make the 3-adic map k_x ↦ A explicit as a 3-adic analytic function
and decide whether its rationality at integer k_x is genuinely obstructed.

**Why this direction:** Session 9 declared the local/structural program saturated and
recommended weighting literature watch over further local computation. The two Bugeaud
papers (arXiv:2604.27490, arXiv:2503.22084) are the first 2026 results that directly bound
the *difference* between a perfect power and an S-unit — exactly the Kuromine shape — so
they had to be evaluated carefully. Suggestion #1 was the one remaining untried 3-adic idea.

## Session 10 main results

1. **Bugeaud 2604.27490 / 2503.22084 assessed — NOT APPLICABLE (same κ-barrier).**
   - Bugeaud proves an *effective* lower bound for |z^d − q1^a1···qt^at| and for its
     greatest prime factor, tending to ∞ with z^d, for z coprime to the q_i, d ≥ 2.
   - **Option (1)** z³ − 2^x = 3^y+5 (U = 2^x): FAILS the hypothesis. z is even
     (z³ = 2^x+3^y+5 with 3^y+5 even, 2^x even ⇒ z even), so gcd(z,2) ≠ 1.
   - **Option (2)** z³ − 3^y = 2^x+5 (U = 3^y): hypotheses **satisfied** — for Theorem-5,
     x is odd ⇒ 2^x+5 ≡ 1 (mod 3) ⇒ z coprime to 3. The difference |z³−3^y| = 2^x+5.
   - **But no contradiction:** |z³−3^y| = 2^x+5 has log ≈ 230572 ≈ 0.631·log(z³)
     (Wolfram). So 2^x+5 ≈ z^{1.89}. A contradiction would require an *effective*
     approximation exponent κ < 1.107 (need 2^x+5 < z^{3−κ}). Baker-type effective
     bounds — which Bugeaud's proof uses — deliver κ just below d = 3 (gain ~ 10^−huge),
     i.e. only |z³−3^y| > const. Useless against 2^x+5 ≈ z^{1.89}.
   - The figure 230572/365439 = **0.631** is *exactly* the Session-3 κ_real ≈ 0.62
     two-comparable-S-units barrier, now confirmed from the cube-vs-3^y side. Bugeaud's
     "→ ∞ with z^d" is trivially satisfied by 2^x+5 → ∞; it carries no obstruction.

2. **Suggestion #1 (3-adic analytic map A(k_x)) — resolved, no obstruction.**
   - Wolfram: g := 2^332640 satisfies v_3(g−1) = 4 exactly (g ≡ 1 mod 3^4, ≢ mod 3^5).
   - Hence 2^x = 32·g^{k_x} = 32·exp_3(k_x·L) with L = log_3(g), v_3(L) = 4 (Wolfram,
     verified). So 2^x — and therefore z(k_x) = (32 exp_3(k_x L)+5)^{1/3} (z ≡ 1 mod 3
     branch) and A(k_x) = z(k_x) (since 3^j → 0 3-adically) — are genuine **3-adic
     analytic functions** of k_x ∈ Z_3.
   - By Theorem J, A(·) is a **bijection** Z_3 → Z_3. So for each target integer value
     a ≡ 22 (mod 27) there is a unique s_a ∈ Z_3 with A(s_a) = a. "Is there an integer
     k_x with A(k_x) a rational integer of size ~2^{x/3}/3?" ⇔ "is the 3-adic number s_a
     a rational integer?" Z is 3-adically **dense** in Z_3, so this is undetectable by
     3-adic analysis. **No 3-adic-analytic obstruction exists** — confirming the
     Session 9 expectation, now with the explicit analytic map in hand.

3. **Other 2026 arXiv items scanned:** holonomy bounds (2510.04156, already assessed
   Session 3) still give effective irrationality measure > 2 for 2^{1/3}, far above the
   κ < 1.107 needed; "Multiple Legendre polynomials in Diophantine approximation",
   Jacobsthal/consecutive-power papers — none unconditional in the two-S-units regime.

## Where things stand (updated after Session 10)

- All Baker variants, congruence/local methods, size/Thue methods, modular/Frey,
  primitive-divisor, Skolem, ABC: RETIRED / ruled out (Sessions 1–8).
- Local (2-adic + 3-adic) portrait of A and B: COMPLETE to arbitrary depth (Sessions 7–9);
  Session 10 adds the explicit 3-adic-analytic form A(k_x) = (32 exp_3(k_x L)+5)^{1/3},
  v_3(L)=4 — and shows it carries no obstruction (bijective ⇒ density wall).
- The two newest 2026 Bugeaud "perfect-power minus S-unit" papers are NOT APPLICABLE:
  Option (1) fails coprimality, Option (2) lands on the κ ≈ 0.63 barrier.

**Honest assessment (Session 10):** No progress toward a proof; the fundamental barrier is
unchanged. The most directly relevant new literature (Bugeaud's effective bounds on
perfect-power−S-unit differences) is provably defeated by the same two-comparable-S-units
regime (κ_real ≈ 0.63 < required 1.107). The last 3-adic stone (Suggestion #1) is turned
over and is empty: A(k_x) is an explicit 3-adic analytic bijection, so rationality at an
integer argument is 3-adically invisible. Future work should remain on literature watch for
a genuinely unconditional effective irrationality measure for 2^{1/3} (or 3^{y}-vs-z^3) with
exponent below ~1.1 — which does not currently exist.
