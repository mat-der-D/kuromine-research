# Current Focus

**Session:** 20260625_213000 (Session 8)

**Current direction:** Structural analysis of the 3-adic parametrization of A by k_x;
12-branch CRT of A mod 20736; correction and completion of the (k_x, k_y) indexing
of all branches; assessment of ABC conjecture and 2026 arXiv literature.

**Why this direction:** Session 7 suggestions #1 and #2 — correct the Session 6
three-branch CRT and compute the 4-branch A mod 6912 (= lcm(256,27)). This session
extended that to the full 12-branch A mod 20736 = lcm(256,81) with (k_x, k_y) indexing.

## Session 8 main results

1. **Theorem I (new):** The three branches of A mod 81 are indexed by k_x mod 3:
   - k_x ≡ 0 (mod 3): A ≡ 49 (mod 81)
   - k_x ≡ 1 (mod 3): A ≡ 22 (mod 81)
   - k_x ≡ 2 (mod 3): A ≡ 76 (mod 81)
   Proof: z^3 ≡ 2^x + 5 mod 243 (since 3^y ≡ 0 mod 243 for y ≥ 5), and
   ord_243(2) = 162, gcd(332640, 162) = 54, so x mod 162 takes 3 values.

2. **Theorem J (new):** A mod 3^{n-1} is uniquely determined by k_x mod 3^{n-4} for all n ≥ 5.
   Pattern: gcd(332640, ord_{3^n}(2)) = 54 for all n ≥ 5, giving period 3^{n-4}.
   The full 3-adic expansion of A in Z_3 is determined by the 3-adic expansion of k_x.

3. **Theorem K (new):** 12-branch characterization of A mod 20736 = lcm(81,256):
   Indexed by (k_x mod 3, k_y mod 4). All 12 values:
   {859, 1291, 3451, 5611, 7771, 8203, 10363, 12523, 14683, 15115, 17275, 19435}
   The first Theorem-5 case (k_x=1, k_y=1) gives A ≡ 5611 (mod 20736).

4. **Correction: Session 6 three branches {1723, 859, 2587} confirmed for k_y even.**
   The full 6-branch (k_y even/odd × k_x mod 3) picture mod 2592:
   {427, 859, 1291, 1723, 2155, 2587} — these replace the erroneous "3 branches universal".

5. **ABC conjecture assessment:** ABC gives NO contradiction. The quality exponent for
   Kuromine is q ≈ 0.888 < 1, meaning C ≪ rad(ABC), so ABC is never violated.

6. **3-adic parametrization insight:** The map k_x → A (in Z_3) is an injective
   3-adic map: A ≡ 1 + 1·3 + 2·9 + (k_x mod 3)·27 + ... (first 3 universal digits of A in Z_3
   are [1,1,2,...]; digit 3 encodes k_x mod 3 via a permutation of Z/3Z). This is a
   bijection Z_3 → Z_3, confirming no 3-adic contradiction.

7. **2026 arXiv survey:**
   - arXiv:2505.19141 (Dong-Shafrir/Karimov et al., 2025): decidability of linear-exponential
     Diophantine over 2 primes. NOT APPLICABLE — z^3 is not an S-unit term.
   - arXiv:2604.18991 (Miyazaki-Scott-Styer, April 2026): a^x+b^y=c^z. NOT APPLICABLE —
     different structure (Kuromine's cube exponent is fixed, z is variable).

## Where things stand (updated after Session 8)

- All Baker variants, all congruence/local methods, all size-based methods,
  modular/Frey, primitive-divisor, Skolem: RETIRED (Sessions 1–5).
- Thue-Mahler [MEDIUM]: per-k finiteness only; computationally intractable for k ≥ 1.
- Elliptic curve (fixed x) [MEDIUM]: same limitation.
- ABC conjecture: does not help (q ≈ 0.888 < 1; C ≪ rad(ABC)).
- Linear-exponential decidability (Karimov et al.): not applicable (z^3 not an S-unit term).
- Universal constraints (accumulation over sessions):
  - z ≡ 6 (mod 16) [Session 7, corrects Session 2]
  - A ≡ 427 (mod 432) [Session 7, universal]
  - B ≡ 79 (mod 432) [Session 7]
  - A ≡ 49/22/76 (mod 81) for k_x ≡ 0/1/2 (mod 3) respectively [Theorem I, Session 8]
  - Full 12-branch A mod 20736 indexed by (k_x mod 3, k_y mod 4) [Theorem K, Session 8]
  - 3-adic expansion of A determined digit-by-digit by k_x [Theorem J, Session 8]

**Honest assessment (Session 8):** The structural picture is now very detailed and the
(k_x, k_y) parametrization of all congruence branches has been completed. No contradiction
has been found. The fundamental barrier (two-comparable-S-units regime, phantom obstruction,
everywhere local solvability) is unchanged. The 3-adic structure shows A is a 3-adic integer
injectively parametrized by k_x — consistent with existence but not proving it.
