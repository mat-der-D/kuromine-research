# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Two-place (archimedean × 3-adic) linear forms in logarithms — *the main thrust*
**Raised to the top in session 2026-06-25.** The three-term equation reduces to a 2-log
archimedean form $\Lambda_1 = 3\ln z - x\ln 2$ (Regime A) bounding $x\ln2 - y\ln3$, plus a
3-adic form $y = v_3(z^3-2^x-5)$ bounding $y$. Together they give an effective absolute bound
on $x,y$; LLL reduction + search then finishes. This is the concrete route to an actual
finiteness/uniqueness theorem. Next: explicit Matveev (real) and Yu (3-adic) constants.
See `knowledge/references/baker_method.md`.

### [HIGH] p-adic analysis of the phantom solution — *reframed, partially resolved*
Session 2026-06-25 found the phantom is exactly the fibre $z^3-2^x-5=3^y$ at $x=5,y=-3$
($(10/3)^3-32-5=1/27=3^{-3}$). A **purely** 3-adic argument cannot separate the real branch
$y\ge2$ from the phantom $y=-3$ — that separation lives only at the archimedean place. So this
direction is now subsumed by the two-place Baker direction above. Remaining purely-3-adic
sub-questions (e.g. 3-adic Newton-polygon obstructions on $z$) are likely also blocked by the
phantom and are LOW value; pursue only if the Baker route stalls.

### [MEDIUM] Elliptic curve approach (fix one variable)
Fixing $x = 5 + 332640k$ and studying $3^y + (2^x+5) = z^3$ as a Mordell family in $(y,z)$.
For each fixed $x$ and each residue of $y$ mod 3 this is a genuine Mordell equation
$Z^3 = 3^{3m}\cdot(\dots)$; finitely many integer points per curve (Faltings/Baker). Could
handle finitely many $x$ once an upper bound on $x$ exists. Complementary to the Baker route.

### [MEDIUM] Primitive divisor arguments (Zsygmondy)
May constrain the prime factorization of $z^3-5 = 2^x+3^y$. Untried.

### [LOW] Numerical search with Theorem 5 filtering
Session 2026-06-25 cleared $x\equiv5\pmod6,\ x\le600,\ y\le300$ (only $(5,3,4)$) using an
exact integer Newton cube-root test. Can be extended with Theorem-5's full modulus to push
much higher cheaply, useful as the endgame after a Baker bound.

### [LOW] arXiv survey of exponential Diophantine equations
Partly done 2026-06-25 (see `knowledge/references/baker_method.md`): this exact equation has
no known published resolution; standard tool is Gel'fond–Baker. Survey arXiv:1808.06557 and the
solution-count bounds arXiv:1702.03424 / 1808.06272 for technique, not direct applicability.

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom by congruences alone. Session
2026-06-25 added a sharp quantitative confirmation: the 3-adic admissible-$x$ density
stabilises at ~0.18 (does not decay), so even a perfected 3-adic sieve fails. See
`knowledge/references/three_adic_density.md`.
