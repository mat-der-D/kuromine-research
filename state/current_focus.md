# Current Focus

**Session:** 20260624_120851

**Current direction:** Factorization approach via w = 3^{y/3} (newly opened this session).
Spun out of the [HIGH] p-adic direction: while studying the 3-adic structure I found that
Theorem 5 forces y ≡ 0 (mod 3) on every remaining solution, which makes 3^y a perfect cube
and unlocks an elementary factorization z³ − w³ = 2^x + 5.

**Why this direction:** It is concrete, unconditional, and immediately productive. It
converts the equation into an S-unit / Ramanujan–Nagell family, the natural setting for
Baker's method — directly serving the [MEDIUM] Baker direction too.

**What has been established this session:**
- y ≡ 0 (mod 3) and x odd for ALL remaining solutions (x≥6, y≥2), from Theorem 5.
- NEW THEOREM: 2^x + 5 ≥ 3^{2y/3 + 1}, i.e. x > 1.0566·y (unconditional). Rules out the
  half-plane x ≲ 1.0566 y; surviving region is a one-sided cone.
- d = 1 sub-case FULLY SOLVED: reduces to 3m² − 19 = 2^{x+2}; only solutions with y≥2 is
  the known (5,3,4). (n up to 400 searched; rigorous finiteness via Ramanujan–Nagell.)
- General d: discriminant 3d(2^{x+2}+20−d³) must be a perfect square and w a 3-power;
  d ≤ ~2^{(x+2)/3}.
- Empirical sieve: d ∈ [1,500], y ≤ 240 → only the known solution appears.

Full write-up: knowledge/references/factorization_approach.md

**Blockers:** The size theorem gives only a one-sided cone (x ≳ 1.0566 y). Closing it needs
an upper bound on x in terms of y (Baker) OR a uniform argument ruling out d ≥ 2.

**Notes:** Next: (1) prove 3m²−19=2ⁿ has only n∈{3,7}; (2) Baker bound on the S-unit form to
close the cone; (3) attack d ≥ 2 via the discriminant-is-a-square + w-is-a-3-power condition.
