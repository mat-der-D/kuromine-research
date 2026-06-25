# Current Focus

**Session:** 20260625_171142 (Session 7)

**Current direction:** Extension of 2-adic portrait of Theorem-5 solutions; correction to
Session 2; computation of $A \pmod{16}$ universally and $B \pmod{27}$, $B \pmod{16}$.

**Why this direction:** Session 6 suggestion #4 (compute $z \pmod{128}$) was executed,
revealing a correction to Session 2's $z \equiv 6 \pmod{32}$ claim and producing the
cleaner universal result $z \equiv 6 \pmod{16}$.

## Session 7 main results

1. **Correction to Session 2:** $z \equiv 6 \pmod{32}$ is NOT universal; it holds only for
   $k_y$ even. The correct universal statement is $z \equiv 6 \pmod{16}$.

2. **New universal congruences (Theorems E–H):**
   - $y \equiv 13 \pmod{16}$ universally [$166317 \equiv 13$, $166320 \equiv 0 \pmod{16}$].
   - $j \equiv 3 \pmod{4}$ universally [$55439 \equiv 3$, $55440 \equiv 0 \pmod{4}$].
   - $z \equiv 6 \pmod{16}$ universally (corrects Session 2).
   - $A \equiv 11 \pmod{16}$ universally. Proof: $z \equiv 6 \pmod{16}$,
     $3^j \equiv 3^3 \equiv 11 \pmod{16}$ (from $j \equiv 3 \pmod{4}$),
     so $A = z - 3^j \equiv 6 - 11 = -5 \equiv 11 \pmod{16}$.

3. **Correction to Session 6 Theorem B:** $A \equiv 27 \pmod{32}$ was stated universally
   but holds only for $k_y$ even. The $k_y$ odd sub-family has $A \equiv 11 \pmod{32}$.
   Both sub-families have $A \equiv 11 \pmod{16}$.

4. **New constraints on $B$:** $B \equiv 25 \pmod{27}$, $B \equiv 15 \pmod{16}$.

5. **Updated CRT constraints (universal):**
   - $A \equiv 427 \pmod{432}$ (was 3 separate branches mod 2592 in Session 6, now corrected to single universal mod 432).
   - $B \equiv 79 \pmod{432}$.
   - Product: $A \cdot B \equiv 37 \pmod{432}$, consistent with $2^x + 5 \equiv 37 \pmod{432}$.

6. **2-adic phantom separation:** $A_{\text{phantom}} = 3 \equiv 3 \pmod{16}$ vs.
   $A_{\text{real}} \equiv 11 \pmod{16}$. Genuine distinction but not a contradiction
   (the cube map on $\mathbb{Z}_2^\times$ is bijective; every value has a cube root).

7. **arXiv search 2026:** One new paper found (arXiv:2603.29831, cubic reciprocity for
   polynomial equation), not applicable to Kuromine. No new unconditional methods.

## Where things stand (updated after Session 7)

- All Baker variants, all congruence/local methods, all size-based methods,
  modular/Frey, primitive-divisor, Skolem: RETIRED (Sessions 1–5).
- Thue-Mahler [MEDIUM]: per-$k$ finiteness only; computationally intractable for $k \geq 1$.
- Elliptic curve (fixed $x$) [MEDIUM]: same limitation.
- New refined universal constraints: $A \equiv 427 \pmod{432}$, $B \equiv 79 \pmod{432}$,
  $y \equiv 13 \pmod{16}$, $j \equiv 3 \pmod{4}$, $z \equiv 6 \pmod{16}$.
- Session 2 result corrected: $z \equiv 6 \pmod{16}$ (not $32$) is the correct universal claim.
- Literature: no new applicable tool found in 2026 arXiv (one irrelevant cubic reciprocity paper).

**Honest assessment (Session 7):** The new constraints are genuine addenda and the
correction to Session 2 is important. But the fundamental barrier remains unchanged:
everywhere local solvability, two-comparable-S-units regime ($\kappa_\text{real} \approx 0.62$),
phantom obstruction. No proof technique is available.
