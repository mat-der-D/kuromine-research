# Current Focus

**Session:** 20260625_200000 (Session 6)

**Current direction:** Literature survey of 2025-2026 arXiv; phantom-free neighbor analysis;
descent investigation; derivation of new fine-grained constraints on A = z - 3^j.

**Why this direction:** After Session 5 cleared the board of every known method, the
remaining actionable items were: (a) scan the 2025-2026 literature for new tools in the
"two-comparable-S-units" regime; (b) pursue the descent-on-A idea suggested in Session 5;
(c) study phantom-free neighboring constants c to understand what makes c=5 uniquely hard.

## Session 6 main results

1. **Literature survey: no new unconditional tools found.**
   - arXiv:2510.11753 (Cai 2025): Handles only a^x + b = c^y (ONE exponential).
     Not applicable.
   - arXiv:2601.11376 (Müller–Taktikos 2026): Effective Roth/Ridout for cube roots,
     conditional on ABC. Does not help the two-S-units regime unconditionally.
   - arXiv:2602.19061 (Müller 2026): Gain bounds for diagonal superelliptic equations
     under strong ABC. Conditional and structurally mismatched.
   - arXiv:2506.20909 (Jun 2025): Reduces exponential Diophantine to ordinary via Lucas
     sequences, but requires a specific form that Kuromine (with additive constant 5) does not
     satisfy.
   - The κ_real ≈ 0.62 gap (Session 3) remains the fundamental barrier; no 2025-2026
     paper closes it.

2. **New constraint: j ≡ 7 (mod 8) for all Theorem-5 solutions.**
   From y = 166317 + 166320k, j = y/3 = 55439 + 55440k.
   55439 mod 8 = 7, 55440 mod 8 = 0, so j ≡ 7 (mod 8) for all k.

3. **New constraint: A ≡ 27 (mod 32) for any Theorem-5 solution.**
   Proof: z ≡ 6 (mod 32) [Session 2], j ≡ 7 (mod 8), so 3^j ≡ 3^7 ≡ 11 (mod 32).
   B = z^2 + z·3^j + (3^j)^2 ≡ 36 + 66 + 121 = 223 ≡ 31 (mod 32).
   2^x + 5 ≡ 5 (mod 32) for x ≥ 5.
   A ≡ 5 · 31^{-1} ≡ 5 · 31 = 155 ≡ 27 (mod 32). (31^{-1} ≡ 31 mod 32.)

4. **New constraint: A ≡ 4 (mod 9) for any Theorem-5 solution.**
   Proof: z^3 ≡ 2^x + 3^y + 5 ≡ 10 (mod 27) [since 3^y ≡ 0 mod 27 for y ≥ 3,
   and 2^x ≡ 2^5 = 32 ≡ 5 mod 27 for the Theorem-5 family].
   Cube roots of 10 mod 27 are {4, 13, 22}, all ≡ 4 (mod 9).
   Since 3^j ≡ 0 (mod 9) for j ≥ 2, A = z - 3^j ≡ z ≡ 4 (mod 9).
   (Previously known: A ≡ {1, 4, 7} mod 9. Now pinned to exactly 4.)

5. **New constraint: A ≡ 22 (mod 27) for any Theorem-5 solution.**
   From z^3 ≡ 37 (mod 81), cube roots are {22, 49, 76}. All ≡ 22 (mod 27).

6. **Combined CRT constraint: A ≡ {1723, 859, 2587} (mod 2592).**
   Three branches from (A mod 81 ∈ {22, 49, 76}) combined with (A mod 32 = 27) via CRT,
   with mod 2592 = lcm(81, 32). Each branch satisfies A ≡ 4 mod 9, A ≡ 22 mod 27.

7. **Phantom-free neighbor analysis.**
   c=4, 6, 7, ... (all up to 221, excluding phantom values 5, 222, ...) have no rational
   phantom at (x,y)=(5,-3). The equation for c=4 has solution (0,1,2) immediately.
   The structure of the c=5 mod-9 sieve (survivors: x≡2,5 mod 6 for y≥2) is unchanged;
   the phantom's special role is confirmed algebraically as a c=5-specific obstruction.

8. **Assessment of descent-on-A idea.**
   The descent idea (force A | something small to get A=1) was investigated.
   Result: A ≡ 3 (mod p) for every prime p ≡ 2 (mod 3) dividing 2^x+5 (confirmed).
   A ≡ 4 (mod 9) distinguishes real solutions from phantom (phantom has A=3 ≡ 3 mod 9).
   But this 3-adic distinction cannot be exploited (3^n wall, as before).
   No mechanism found to force A=1 or any other specific value via descent.

## Where things stand (updated)

- All Baker variants, all congruence/local methods, all size-based methods,
  modular/Frey, primitive-divisor, Skolem: RETIRED (Sessions 1–5).
- Thue-Mahler [MEDIUM]: per-k finiteness only; computationally intractable for k≥1.
- Elliptic curve (fixed x) [MEDIUM]: same limitation.
- New refined constraints on A documented here, but do not resolve the problem.
- Literature: no new applicable tool found in 2025-2026 arXiv.

**Honest assessment (sharpened, Session 6):** The problem remains beyond all known effective
methods. The new constraints (A ≡ 27 mod 32, A ≡ 4 mod 9, A ≡ 22 mod 27) are genuine
addenda to the picture of what a Theorem-5 solution would look like, but do not yield
a contradiction. The fundamental gap (κ_real ≈ 0.62 in the two-S-units regime) is
confirmed unchanged by the 2025-2026 literature.
