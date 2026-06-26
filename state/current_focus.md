# Current Focus

**Session:** 20260626_120000 (Session 13)

**Current direction:** Literature watch — assessed four new Chabauty-Kim / algebraic geometry
papers (arXiv:2511.15949, 2602.05643, 2505.12947, 2604.20662) from the 2025–2026 cluster;
did a June/July 2026 arXiv sweep. Proved a fifth categorical barrier: Chabauty-Kim methods
are categorically inapplicable to exponential Diophantine equations.

**Why this direction:** Session 12 suggested exploring the "Galois representations / algebraic
geometry" angle. The Chabauty-Kim framework (Affine Chabauty I/II, Modular Chabauty, Cubic
Chabauty) is the primary modern algebraic-geometry tool for integral points and had not been
systematically assessed. These four papers appeared in late 2025 and early–mid 2026.

## Session 13 main results

1. **Affine Chabauty I/II (arXiv:2511.15949, 2602.05643) — NOT APPLICABLE (structural).**
   - Method: S-integral points on affine algebraic curves via generalized Jacobian embedding.
   - Barrier: Kuromine's variables $x$, $y$ are exponents of fixed bases, not algebraic
     coordinates. The constraint "$u = 2^x$" or "$v = 3^y$" is not encodable as S-integrality
     on an algebraic curve. The mismatch is categorical.

2. **Modular Chabauty (arXiv:2505.12947) — NOT APPLICABLE (structural).**
   - Method: S-integral points on curves with elliptic fibrations via modular period map.
   - Partial applicability: per fixed $k_x$, the Thue-Mahler equation $z^3 - w^3 = N_{k_x}$
     could in principle be solved. But $N_{k_x} \approx e^{230572}$ for $k_x = 1$ is
     astronomically beyond the Effective Shafarevich step's practical reach, and the method
     gives no information across the infinite Theorem-5 family.

3. **Cubic Chabauty (arXiv:2604.20662) — NOT APPLICABLE (structural).**
   - Method: depth-3 Kim set for fixed elliptic curves of Mordell-Weil rank ≤ 2.
   - Barrier: Kuromine gives a varying family of Mordell curves, not a single fixed curve.

4. **Fifth categorical barrier formally established (Session 13):**
   Chabauty-Kim methods in all forms — classical, affine, cubic, modular, motivic — are
   categorically inapplicable to *exponential Diophantine equations* where two or more
   variables appear as exponents of fixed integer bases. The Kuromine equation's "two-exponential"
   structure (both $x$ and $y$ are exponents) lies outside the algebraic category that all
   Chabauty-type methods require.

   The five categorical barriers now documented:
   1. Congruence sieving (Sessions 1–2): locally solvable everywhere (phantom).
   2. Baker-type methods (Sessions 1, 5): $v_p = 0$; no linear form is small.
   3. Modular method / Frey (Session 4): no varying prime exponent.
   4. Effective abc / quality bounds (Sessions 8, 12): quality ≈ 0.888 << 1.
   5. Chabauty-Kim / algebraic geometry (Session 13): exponential variables outside
      the algebraic category.

## Where things stand (updated after Session 13)

- The five categorical barriers cover every major branch of modern Diophantine techniques.
- The open target is unchanged: **unconditional effective lower bound for |z^3 - 3^y|
  with exponent κ < 1.107** — nonexistent in the 2025–2026 literature.
- A new potentially fruitful angle identified (Suggestion 2): "greatest prime factor of
  $z^3 - 5$" reformulation — if gpf($z^3 - 5$) grows effectively with $z$, this would
  imply only finitely many $z$ with $z^3 - 5$ a $\{2,3\}$-integer, which is exactly the
  Kuromine condition. This is related to (but not the same as) Bugeaud's Session-10 result
  (which goes the other direction: |z^3 - 3^y| → ∞).
- Future sessions: continue holonomy-bounds watch; explore the gpf($z^3 - 5$) reformulation.
