# Current Focus

**Session:** 20260625_230000 (Session 9)

**Current direction:** Computed the full 3-adic congruence portrait of the integer
factor B (Session 8 suggestion #1) — the B-analog of Theorems I/J for A — and formalized
the accumulated structural theorems (I, J, K, L) into the knowledge base.

**Why this direction:** Session 8 left two concrete, tractable tasks: (1) push the B
constraints to the same 3-adic depth already achieved for A; (2) formalize Theorems I–K
(and now L) into `problem.md` plus a dedicated reference file. Both completed this session.

## Session 9 main results

1. **Theorem L (new):** Full 3-adic structure of B = (2^x+5)/A.
   - B ≡ 25 (mod 27), universal (the B-analog of A ≡ 22 mod 27).
   - B mod 81 indexed by k_x mod 3: k_x≡0 → 52, k_x≡1 → 79, k_x≡2 → 25 (mod 81).
   - B mod 3^{n-1} is a function of k_x mod 3^{n-4} for n ≥ 5 (period 3^{n-4}),
     inherited from Theorem J via B ≡ (2^x+5)·A^{-1} mod 3^n (A is a 3-adic unit).
   - **Correction to Session 8 suggestion #1:** B mod 729 needs k_x mod **27**, not mod 9.
     (Suggestion said "mod 9"; the true period at level 3^6 is 3^{7-4}=27. Theorem J
     applies with n=7.) Full 27-branch (A,B) mod 729 table computed and verified
     (A·B ≡ 2^x+5 mod 729 in every row).
   - B is a 3-adic unit (v_3(B)=0, B ≡ 1 mod 3), 3-adic preamble [1,2,2]. This separates
     the real solution from the phantom (B_phantom = 37/3, v_3 = -1), but the separation
     is non-actionable (B is a valid 3-adic unit for every k_x).

2. **Formalization (Session 8 suggestion #4):**
   - Added Theorems I, J, K, L to `knowledge/problem.md` with statements and proof sketches.
   - Created `knowledge/references/adic_structure_extended.md` with the full side-by-side
     2-adic and 3-adic portraits of A and B, all tables, and the phantom non-actionability
     discussion.

3. **Cross-checks (Wolfram):** A·B ≡ 37 mod 81 universally; A ≡ 427, B ≡ 79 mod 432
   (427·79 ≡ 37 mod 432); the three (A,B) mod 81 branches all multiply to 37. All verified.

## Where things stand (updated after Session 9)

- All Baker variants, congruence/local methods, size methods, modular/Frey,
  primitive-divisor, Skolem, ABC: RETIRED / ruled out (Sessions 1–8).
- Thue-Mahler [MEDIUM], elliptic curve (fixed x) [MEDIUM]: per-k finiteness only; intractable.
- The local (2-adic + 3-adic) portrait of a hypothetical Theorem-5 solution is now
  COMPLETE for both factors A and B to arbitrary p-adic depth:
  - A mod 3^{n-1} ← k_x mod 3^{n-4}; A mod 2^n ← k_y mod 2^{n-4}.
  - B mod 3^{n-1} ← k_x mod 3^{n-4} (Theorem L, this session); B mod 2^n ← k_y.
  - Universal CRT class: A ≡ 427 (mod 432), B ≡ 79 (mod 432), A·B ≡ 37 (mod 432).
- Both k_x ↦ A and k_x ↦ B are bijections Z_3 → Z_3: no 3-adic obstruction, confirming
  the phantom/"37 is a cube mod 3^n" wall from the factorization side on BOTH factors.

**Honest assessment (Session 9):** The structural/local portrait is now as complete as it
can be — both coprime factors are fully characterized 2-adically and 3-adically, and both
are bijective Z_3-images of k_x. This is a clean, finished piece of bookkeeping. It does
not advance toward a proof: the fundamental barrier (phantom global rational cube,
two-comparable-S-units regime, everywhere local solvability) is unchanged. No new tool.
