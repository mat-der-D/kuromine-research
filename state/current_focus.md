# Current Focus

**Session:** 20260625_180000 (Session 5)

**Current direction:** Assessed p-adic Baker (Yu's theorem) quantitatively; analyzed the
algebraic structure of the constant c=5; proved the A=1 sub-theorem; assessed
Skolem/Bertók-Hajdu method; investigated z mod 37 structure.

**Why this direction:** After Session 4 retired the last active non-size lead, the
remaining [MEDIUM] directions were Baker/Yu's p-adic Baker (never computed
quantitatively), the Thue-Mahler approach, and the "constant 5" speculative angle from
Session 4's next suggestions. These were the highest-value remaining moves.

## Session 5 main results

1. **p-adic Baker (Yu's theorem): definitively retired.** For both relevant p-adic linear
   forms (p=2 and p=3), the actual p-adic valuation is 0 — these are p-adic *units*.
   - $v_3(2^x - z^3) = v_3(-(3^y+5)) = 0$ (since $5 \equiv 2 \pmod 3$, $v_3(5)=0$).
   - $v_2(2^x - z^3) - v_2(z^3) = v_2(-(3^y+5)) - 3 = 3-3 = 0$.
   Yu's theorem gives an *upper* bound on $v_p(\Lambda_p)$; a contradiction requires the
   actual $v_p$ to exceed that upper bound. With $v_p = 0$, no upper bound can ever be
   violated. This is the same root cause as the archimedean failure: all linear forms
   (archimedean and p-adic) are far from zero in the "two comparable S-units" regime.

2. **A=1 sub-theorem proved.** The equation $2^x + 5 = 1 + 3^{j+1} + 3^{2j+1}$ (i.e.,
   $A = z - 3^j = 1$) has *exactly* two non-negative integer solutions:
   - $j=0$: $2^x = 2$, $x=1$ giving solution $(1,0,2)$.
   - $j=1$: $2^x = 32$, $x=5$ giving solution $(5,3,4)$.
   For $j \geq 2$ even: $v_2(\text{value}) = 1 \neq v_2(\text{value})$ for any power of 2
   (value $\gg 2$). For $j \geq 3$ odd: $v_2(\text{value}) = 3$, value $= 8 \cdot (\text{odd})$
   with odd part $\gg 1$. In both cases the value cannot be a pure power of 2. This
   confirms and provides a clean proof for the two known solutions being the only A=1 cases.

3. **Constant c=5 algebraically characterized.** The equation $2^x + 3^y + c = z^3$ has
   a rational phantom solution $(5, -3, z_0)$ at $(x,y) = (5,-3)$ if and only if
   $865 + 27c$ is a perfect cube. The smallest positive $c$ satisfying this is $c=5$
   (giving $10^3 = 1000$). The sequence is $c \in \{-32, 5, 222, 781, 1844, \ldots\}$
   (corresponding to cube root $n \equiv 1 \pmod 9$: $n = 1, 10, 19, 28, 37, \ldots$).
   For all other small positive $c$ (e.g., $c=4, 6, 7, \ldots$), no rational phantom exists
   at $(5,-3)$ and congruence methods may succeed. This is the precise algebraic reason
   $c=5$ is maximally obstructed: it is the first small positive integer generating a global
   rational cube phantom.

4. **Skolem/Bertók-Hajdu: inapplicable.** The Bertók-Hajdu algorithm requires the equation
   to be *locally unsolvable* somewhere (no local solution implies no global solution).
   The Kuromine equation is locally solvable at every prime (Session 2). Therefore the
   Bertók-Hajdu/Miyazaki infinite-family approach cannot confirm absence of solutions.

5. **Thue-Mahler for k=1: computationally intractable.** $N_1 = 2^{332645}+5$ has
   approximately 100,133 decimal digits. No algorithm can explicitly resolve the Thue-Mahler
   equation for this input.

6. **z mod 37 structure.** $37 \mid N_k = 2^x + 5$ for all $k \geq 1$ (since $\mathrm{ord}_{37}(2) = 36 \mid 332640$). The Theorem-5 family has z mod 37 cycling through all three branches
   ({21, 25, 28}) as $k$ varies (verified for $k=0,\ldots,5$). This confirms no fixed
   branch contradiction is possible via 37-adic data alone. The phantom is in the $z \equiv
   28 \pmod{37}$ branch.

## Where things stand (board state)

- Local / congruence / p-adic (standalone): RETIRED (Session 2)
- Single irrationality measure / 2-term linear form: RETIRED (Session 3)
- Full 3-log Baker (Matveev, archimedean): RETIRED (Sessions 1, 3)
- p-adic Baker (Yu's theorem): RETIRED (this session)
- Primitive-divisor / Zsygmondy: RETIRED (Session 4)
- Modular / Frey-curve method: RETIRED (Session 4)
- Skolem / Bertók-Hajdu: RETIRED (this session)
- Thue-Mahler (theoretical): [MEDIUM] — per-k finiteness only; uniformity open; computationally intractable
- Elliptic curve (fixed x): [MEDIUM] — same limitation

**Honest assessment (sharpened):** Every known effective global tool (all Baker variants,
all approximation measures) and every local/algebraic/combinatorial tool (congruences,
factorization, Skolem, modular method) has now been assessed and found insufficient, with
explicit quantitative or structural reasons for each failure. The board is now essentially
cleared of plausible near-term attacks. A breakthrough would require either:
(a) A new effective method for "two comparable large S-units summing to a cube" (the
    simultaneous approximation regime $3^y \approx z^2$), or
(b) A coupling of the 3-adic integrality distinction ($v_3(A)=0$ for real solutions vs
    $v_3(A_{\text{phantom}})=1$) to a global size bound — mechanism presently unknown.

## Notes on remaining positive/structural results

- The A=1 sub-theorem gives a clean characterization of the two known solutions.
- The c=5 characterization explains the phantom's origin algebraically.
- The problem is now documented with six independent reference files, one for each retired
  method cluster.
