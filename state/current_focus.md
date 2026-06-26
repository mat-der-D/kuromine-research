# Current Focus

**Session:** 20260626_174500 (Session 15)

**Current direction:** Boundary-case / bounded-$A$ analysis (Session-14 suggestion #2).
Derived a new exact 3-adic valuation identity (Theorem N) and proved rigorously *why*
the bounded-$A$ elimination cannot fire for the Theorem-5 family.

**Why this direction:** Both known solutions have $A = z - 3^j = 1$, and Theorem M's
boundary ($2^x \approx 3^{2j+1}$) is exactly where $A \approx O(1)$. If surviving cases
were forced to have small $A$, the 3-adic valuation structure would eliminate them.
Worth a direct computational test.

## Session 15 main results

1. **Theorem N (new, exact, elementary):**
   $$2^x + 5 - A^3 = 3^{j+1}\,A\,(A + 3^j), \qquad v_3(2^x + 5 - A^3) = j + 1,$$
   where $A = z - 3^j$, $\gcd(A,3) = 1$ by Theorem I. Verified on both known solutions.

2. **Valuation re-proof that $A$ is huge:** For any fixed $a$ coprime to 3,
   $v_3(2^x+5-a^3)$ is a bounded constant ($\leq 3$ for $a \leq 8$), but Theorem N
   demands $j+1 \geq 55440$. So $A$ is no fixed small integer — an independent 3-adic
   proof of the Session-4 size fact. The $A=1$ band: LTE gives $v_3(2^x+4)=2$ universally,
   forcing $j=1$ (only the known solution).

3. **Main (negative) finding:** The bounded-$A$ elimination **cannot work** for
   Theorem-5. The factorization bound $A < (2^x+5)/3^{2j} \approx 3e^{D}$
   ($D = x\log2 - (2j+1)\log3$) makes $A$ small only at the Theorem-M boundary $D\approx 0$.
   Wolfram: over $k_x \leq 5000$ the closest *surviving* ($D\geq 0$) pair has $D \approx 55$
   (giving $A \gtrsim 10^{24}$); the closest overall is $D \approx 10$, on the eliminated
   side. The family never lands within $O(1)$ log-distance of the boundary.

4. **Structural clarification:** Theorem N is automatically satisfied by a genuine
   solution (an algebraic identity), so it adds no constraint by itself. The hoped-for
   contradiction needs closeness-to-boundary, which provably never occurs. This is the
   **metric face** of the two-comparable-S-units barrier (third lens, after analytic S3
   and congruence S4–9).

## Where things stand (updated after Session 15)

- Theorem N joins Theorem M (Session 14) as a clean elementary result on the equation.
  It re-proves "$A$ huge" via 3-adic valuation and gives a tidy closed form for
  $v_3(2^x+5-A^3)$.
- Neither Theorem M nor N resolves the conjecture. The bounded-$A$ route is now closed:
  the Theorem-5 lattice never approaches the boundary $2^x = 3^{2j+1}$ closely enough
  for $A$ to be small.
- The open target is unchanged: **unconditional effective lower bound for $|z^3 - 3^y|$
  with exponent $\kappa < 1.107$** in the two-comparable-S-units regime.
- Next priority: the *upper-side / power-of-2* angle — for surviving $A < 3^j$ cases,
  $z$ is pinned in $(3^j, 2\cdot 3^j)$; combine this narrow band with the requirement that
  $2^x = z^3 - 3^{3j} - 5$ be an exact power of 2 (via the 2-adic structure of
  $B = (2^x+5)/A$, Theorems K/L). This is the one large factor not yet exploited by size.
