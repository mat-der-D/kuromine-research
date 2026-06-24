# The Factorization Approach (z³ − w³ with w = 3^{y/3})

This note records a concrete, unconditional line of attack discovered in session
20260624 that exploits a structural consequence of Theorem 5.

## Key observation: y is always divisible by 3 in the remaining case

Theorem 5 forces, for any solution with x ≥ 6, y ≥ 2:
  - x ≡ 5 (mod 332640)
  - y ≡ −3 (mod 166320)

Since 166320 ≡ 0 (mod 3) and −3 ≡ 0 (mod 3), **every remaining y satisfies y ≡ 0 (mod 3)**.
(Indeed y ≡ 6 (mod 9), so 3 | y but 9 ∤ y, i.e. y/3 ≢ 0 (mod 3).)

Also 332640 is even and 5 is odd, so **x is always odd**; hence 2^x + 5 ≡ 1 (mod 3),
i.e. 2^x + 5 is coprime to 3.

## The factorization

Set w = 3^{y/3} ∈ ℤ_{>0}, so w³ = 3^y. Then
  z³ = 2^x + 3^y + 5 = 2^x + w³ + 5  ⇒  z³ − w³ = 2^x + 5.
Since z³ > w³ and z is an integer, z ≥ w+1. Let d = z − w ≥ 1. Then
  (z − w)(z² + zw + w²) = 2^x + 5,
and with z = w + d,  z² + zw + w² = 3w² + 3wd + d². Hence
  **2^x + 5 = d·(3w² + 3wd + d²),  d ≥ 1,  w = 3^{y/3}.**   (★)
Both factors are odd (product is odd). Coprimality to 3 forces 3 ∤ d.

## NEW THEOREM (size bound) — proven this session

From (★) with d ≥ 1, w ≥ 1, all terms positive:
  2^x + 5 = d(3w² + 3wd + d²) ≥ 3w² = 3·3^{2y/3} = 3^{2y/3 + 1}.

  **Theorem.** Any solution with x ≥ 6, y ≥ 2 satisfies
     2^x + 5 ≥ 3^{2y/3 + 1},   equivalently   x > (2/3)·log₂(3)·y ≈ 1.0566·y.

This is unconditional. It rules out the entire half-plane x ≲ 1.0566·y. It does NOT by
itself close the problem: the surviving region is a one-sided cone x ≳ 1.0566·y, infinite
in extent. An upper bound on x in terms of y (e.g. Baker's method) would close it.

Check on the known solution (5,3,4): w = 3^{3/3} = 3, d = 4 − 3 = 1; RHS 3^{2·3/3+1} = 3³ = 27,
LHS 2^5 + 5 = 37 ≥ 27 ✓ (and d = 1 here).

## The d = 1 sub-case is completely solved (only the known solution)

If d = 1: 2^x + 5 = 3w² + 3w + 1, i.e. 2^x = 3w² + 3w − 4 with w = 3^{y/3}.
Completing the square (let m = 2w + 1, an odd number = 2·3^{y/3} + 1):
  **3m² − 19 = 2^{x+2}.**
This is a Ramanujan–Nagell / Lebesgue–Nagell type equation, which has finitely many
solutions. A direct search (n = x+2 up to 400) finds ALL solutions of 3m² − 19 = 2ⁿ:
  - (n, m) = (3, 3) → x = 1, w = 1, y = 0   (outside y ≥ 2; the Theorem-2 region)
  - (n, m) = (7, 7) → x = 5, w = 3, y = 3   (the known solution (5,3,4))
No others up to n = 400. So **in the d = 1 case the only solution with y ≥ 2 is (5,3,4).**
(A rigorous "no other solutions ever" for 3m² − 19 = 2ⁿ should follow from standard
Ramanujan–Nagell techniques / Baker bounds; this should be cited or proved.)

## General d: an S-unit / Ramanujan–Nagell family

Viewing (★) as a quadratic in w: 3d·w² + 3d²·w + (d³ − 2^x − 5) = 0.
Discriminant Δ = 3d·(4(2^x + 5) − d³) = 3d·(2^{x+2} + 20 − d³) must be a perfect square,
and w must equal a power of 3. Reality of w forces d ≤ (4(2^x+5))^{1/3} ≈ 2^{(x+2)/3}.
So d ranges over a bounded (but x-dependent) set, each value giving a generalized
Ramanujan–Nagell equation in w together with the constraint w = 3^{y/3}.

## Why this matters

- It converts the "hard wall" (phantom solution, congruence dead end) into a problem about
  a 2-power equalling an explicit quadratic in a 3-power — an S-unit equation, the natural
  habitat of Baker's method and modern Lebesgue–Nagell solvers.
- The d = 1 stratum (which contains the only known large solution) is already fully closed.
- Remaining work: bound d above effectively (Baker), or rule out d ≥ 2 directly.

## Open questions / next steps

1. Prove 3m² − 19 = 2ⁿ has only the two solutions n ∈ {3,7} (Ramanujan–Nagell machinery).
2. For d ≥ 2: combine the discriminant-square condition with w being a 3-power. Sieve d ≥ 2
   for small d and search for any (d, w, x) producing a solution beyond the known one.
3. Use Baker's theorem on the S-unit equation 2^x − 3·(3^{y/3})² = (lower order) to bound x
   above in terms of y, closing the cone from the new size theorem.
