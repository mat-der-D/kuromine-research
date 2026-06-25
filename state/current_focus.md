# Current Focus

**Session:** 20260625_HHMMSS (Session 3)

**Current direction:** Tested the Session-2 [HIGH] lead — effective irrationality
measure for 2^(1/3) applied to z^3 - 2^x = 3^y + 5 — to decide whether it can actually
close the problem. **It cannot, for a structural reason**, now proven. Then probed the
algebraic factorization route for a non-size-based contradiction; derived a clean
equivalent reduction but found every consequence collapses to consistency (soft
obstruction).

**Why this direction:** Session 2 elevated effective approximation to 2^(1/3) to [HIGH]
as "the realistic global path" but never carried out the quantitative check. Doing so was
the highest-value next step: either it works (huge) or it is ruled out (clears the board).

## Session 3 main results

1. **Effective irrationality measures for 2^(1/3) are provably useless here.** Writing
   x = 3a+2, 2^x = 4(2^a)^3, the equation is the Thue form z^3 - 4W^3 = 3^y + 5 (W = 2^a),
   so z/W approximates α = 2^(2/3). Two independent computations (Wolfram):
   - The realized approximation exponent is κ_real ≈ **0.62 < 1**, far below any
     effective μ ≥ 2. Irrationality measures (lower bounds) only bite on *good*
     approximations (κ ≥ μ); z/W is a *bad* one. No information.
   - As a Thue lower bound: a contradiction needs log(3^y+5) < (3-μ)·log max(z,W);
     LHS ≈ 182718, RHS ≈ 43809, so LHS - RHS ≈ +138909 > 0. The form value 3^y+5 is
     far too large.
   Root cause: **3^y is not a small perturbation** — log(3^y)/log(2^a) ≈ 2.38, so
   3^y ≈ z^2. This is the "two comparable dominant S-units" regime. The sharper 2025
   holonomy bounds (arXiv:2510.04156) do not help: they only improve μ, but no μ rescues
   a κ_real of 0.62. Documented in `knowledge/references/irrationality_measure_obstruction.md`.

2. **Clean equivalent reduction of the whole problem.** With A = z - 3^j, w = 3^j:
   `2^x + 5 = A^3 + 3^{j+1} A^2 + 3^{2j+1} A = A·(A^2 + 3^{j+1}A + 3^{2j+1})`,
   verified to recover BOTH known solutions by brute force (x≤40): (1,0,2) and (5,3,4),
   both with **A = z - 3^{y/3} = 1**.

3. **Eisenstein-norm identity:** 4B - 3w^2 = (2z+w)^2 (B = z^2+zw+w^2), i.e. the standard
   `4·norm = square + 3·(...)`. Verified on (5,3,4): 4·37 - 3·9 = 121 = 11^2.

4. **Negative algebraic finding:** the inert-prime condition (every prime q ≡ 2 mod 3
   dividing 2^x+5 divides z - 3^j) is *automatically* consistent: q | z-3^j with the
   equation gives 3^{3j} ≡ 3^y mod q, automatic because y = 3j. So the factorization
   yields no new congruence — another instance of the soft-obstruction principle.

## Where things stand

- Local methods: provably insufficient (Session 2 — phantom is a global cube).
- Single irrationality measure / 2-term linear form: provably insufficient (Session 3).
- Full 3-log Baker (Matveev): too weak by ~10^10 (Session 1, re-confirmed Session 3).
- Algebraic factorization: produces only self-consistent identities so far; no
  contradiction. The one genuinely suggestive fact is that both real solutions have
  A = z - 3^{y/3} = 1 (maximally balanced), whereas any Theorem-5 solution would have
  A ≈ z ≈ e^{76857} (maximally unbalanced). If one could prove A must be small, done —
  but no mechanism to bound A is known.

**Honest assessment:** every *currently known effective* global tool is quantitatively
too weak for the Theorem-5 parameter range, and every *local/algebraic* tool is defeated
by the soft obstruction. The problem genuinely sits beyond current effective methods.
This is now documented, not just suspected.

## Notes / still open

- The reduction `2^x+5 = A(A^2+3^{j+1}A+3^{2j+1})` is the cleanest single-equation form.
  Worth attacking as a Thue-Mahler equation in (A, 3^j) for fixed x — but finiteness per
  x is already known; the open part is uniformity over the infinite x-progression.
- Possible fresh angle (untried): exploit that A·B = 2^x+5 with B = norm and the SPECIFIC
  prime 2 — e.g. growth/primitive-divisor (Zsygmondy/Bilu-Hanrot-Voutier) constraints on
  the factor B = z^2+zw+w^2 as x grows along the progression.
- arXiv:2207.14492 (Thue-Mahler resolution) still un-executed for a concrete k=1 case.
