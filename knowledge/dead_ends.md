# Dead Ends

## Congruence Arithmetic (modular sieving)

**Status:** Fundamentally limited. Do not invest further effort in this direction alone.

**What was achieved:** Theorem 5 established that any solution with $x \geq 6$, $y \geq 2$ must satisfy $x \equiv 5 \pmod{332640}$ and $y \equiv -3 \pmod{166320}$. This required combining cubic residue conditions modulo 30+ primes.

**Why it cannot go further:** The phantom rational solution $(5, -3, 10/3)$ survives modulo any $m$ with $\gcd(m, 3) = 1$, because $3^{-1}$ exists in $\mathbb{Z}/m\mathbb{Z}$. The only escape is to use moduli that are powers of 3. But 37 is a cubic residue mod $3^n$ for all $n$ (proved by induction), so even this avenue is closed.

**Conclusion:** Pure congruence sieving cannot prove there are no further solutions. A fundamentally different technique is required.

## Effective irrationality measures for $2^{1/3}$ (Session 3)

**Status:** Provably insufficient for the Theorem-5 parameter range. Do not pursue as a
route to a contradiction.

**What was tried:** Reframe $z^3 = 2^x+3^y+5$ with $x=3a+2$ as the Thue form
$z^3 - 4W^3 = 3^y+5$ ($W=2^a$), making $z/W$ a rational approximation to
$\alpha = 2^{2/3}$, and apply an effective irrationality measure
$|\alpha - p/q| > c/q^\mu$ (Baker $\mu\approx2.96$, Chudnovsky/Bennett $\mu\approx2.43$,
holonomy bounds arXiv:2510.04156 sharper but $>2$).

**Why it fails (two independent computations, Wolfram):**
1. The approximation $z/W$ realizes exponent $\kappa_{\text{real}}\approx0.62<1$, far
   below any $\mu\ge2$. Irrationality measures are *lower* bounds and only constrain
   *good* approximations ($\kappa\ge\mu$). $z/W$ is a *bad* approximation, so no measure
   (however sharp) yields a constraint.
2. As a Thue lower bound, a contradiction needs $\log(3^y+5)<(3-\mu)\log\max(z,W)$, but
   LHS $\approx182718$ vs RHS $\approx43809$: off by $+138909$.

**Root cause:** $3^y$ is *not* a small perturbation of $2^x$. $\log3^y/\log2^a\approx2.38$,
so $3^y\approx z^2$ — the "two comparable dominant S-units" regime, which no single cubic
irrationality measure can resolve. Improving the constant $\mu$ cannot help. See
`knowledge/references/irrationality_measure_obstruction.md`.

## Primitive-divisor / congruence test on the factor $B = z^2+zw+w^2$ (Session 4)

**Status:** The purely *congruence-based* version is a dead end (same soft obstruction).
The growth/size version is unworkable for lack of a clean recurrence. Do not pursue a
congruence-on-the-factorization contradiction.

**What was tried:** Use the coprime factorization $2^x+5 = A\cdot B$ ($A=z-3^j$,
$B=z^2+z\,3^j+3^{2j}$, all prime factors of $B$ being $\equiv1\pmod3$) and look for a prime
$p\equiv1\pmod3$ that must (or cannot) divide $B$, hoping to clash with the 2-adic/3-adic
data.

**Why it fails (Wolfram, Session 4):** Since $332640\equiv0\pmod3$ and $166320\equiv0\pmod6$,
the residues $x\bmod3\equiv2$, $y\bmod6\equiv3$ are constant over the whole Theorem-5 family,
so $2^x,3^y,w \pmod p$ are pinned for any $p$ with suitable orders. Computation then shows
$A\equiv 3\pmod p$ for *every* tested prime $p\equiv2\pmod3$ (and the phantom-matching branch
for $p\equiv1\pmod3$ gives $A\equiv3$, $B\equiv37/3$). The reason is exactly the phantom:
$A_{\text{phantom}} = \tfrac{10}{3}-\tfrac13 = 3$ and $B_{\text{phantom}}=\tfrac{37}{3}$ reduce
mod every prime $p\ne3$. So *every* congruence on $A$ or $B$ is automatically satisfied by the
phantom — the soft-obstruction principle, now confirmed on the factorization. The only genuine
real-vs-phantom distinction ($v_3(A)=0$ vs $1$; $A\bmod9\in\{1,4,7\}$ vs $3$) is 3-adic and is
blocked by the known "$37$ is a cube mod $3^n$ for all $n$" wall. Moreover $B=(2^x+5)/(z-3^j)$
is not an $a^n-b^n$ Lucas/Lehmer sequence (both $z$ and $j$ vary non-linearly with $x$), so
Zsygmondy / Bilu–Hanrot–Voutier primitive-divisor theorems do not apply. Documented in
`knowledge/references/factorization_approach.md`.

## p-adic Baker / Yu's theorem (Session 5)

**Status:** Definitively closed. Do not pursue p-adic Baker in any form.

**What was tried:** Applied Yu's p-adic Baker theorem to both the 2-adic and 3-adic linear forms arising from the equation.

- 3-adic form: $\Lambda_3 = x\log_3(2) - 3\log_3(z)$ has $v_3(\Lambda_3) = v_3(2^x - z^3) = v_3(-(3^y+5)) = 0$, since $5 \equiv 2 \pmod 3$ so $v_3(3^y + 5) = 0$.
- 2-adic form: $v_2(\Lambda_2) = v_2(2^x - z^3) - v_2(z^3) = v_2(-(3^y+5)) - 3 = 3-3 = 0$.

**Why it fails:** Yu's theorem gives an *upper* bound: $v_p(\Lambda_p) \leq C(n,p,\ldots)\cdot\log B$. A contradiction requires the actual $v_p$ to *exceed* this upper bound. Since both actual $v_p$ values are 0, the condition $0 \leq C\cdot\log B$ is trivially satisfied for any positive $C$. No information is obtained.

**Root cause:** Same as the archimedean Baker failure — the "two comparable dominant S-units" regime ($3^y \approx z^2$) means no linear form (in any metric, archimedean or p-adic) is forced to be small. This rules out every Baker-type method. Improvement in constants cannot help.

## Skolem's method / Bertók-Hajdu algorithm (Session 5)

**Status:** Inapplicable. Same phantom obstruction.

**What was tried:** The Bertók-Hajdu algorithm (and its application in Miyazaki's infinite-family results, e.g., arXiv:2503.00843) finds a modulus $N$ such that the equation has no solution mod $N$, concluding no integer solution exists. Searched the 2025-2026 literature for applicable methods.

**Why it fails:** The Kuromine equation $2^x + 3^y + 5 = z^3$ is *locally solvable at every prime* (proven in Session 2: the phantom $(10/3)^3$ is a global rational cube, so it is a cube modulo every prime $p \neq 3$, and 37 is a cube modulo $3^n$ for all $n$). The Bertók-Hajdu algorithm requires local non-solvability to terminate with a "no solutions" conclusion. Since the equation is everywhere locally solvable, the algorithm would never find a blocking modulus.

**Consequence:** Any method relying on a local-global Hasse-type principle for exponential equations is blocked by the phantom obstruction. This includes all variants of Skolem's p-adic method in its standard form.

## Modular method / Frey curves (Session 4)

**Status:** Not applicable. Structural mismatch, not a quantitative gap.

**Why:** The modular method (FLT, generalized Fermat, Darmon's program) requires a *varying
prime exponent* to carry the mod-$p$ Galois representation on a Frey curve's $p$-torsion. The
Kuromine equation $z^3=2^x+3^y+5$ has only a *fixed small* exponent (the cube, 3); its varying
exponents $x,y$ sit on the fixed small bases 2,3 with an additive constant. There is no large
varying prime exponent anywhere, so no Frey curve / Frey representation can be built. The
fixed-$y$ elliptic/Mordell route only re-proves the already-known finiteness per fixed $y$ and
says nothing about the infinite Theorem-5 family. See `knowledge/references/modular_method.md`.

## gpf($z^3-5$) reformulation (Session 14)

**Status:** Retired due to a fundamental conflation. Do not pursue.

**What was proposed (Session 13):** If the greatest prime factor of $z^3-5$ grows effectively
with $z$, then only finitely many $z$ can have $z^3-5$ a $\{2,3\}$-integer (meaning all prime
factors $\leq 3$), which was claimed to be "exactly the Kuromine condition."

**Why the conflation is fatal:** The Kuromine condition is $z^3-5 = 2^x + 3^y$ —
sum-representability as a specific two-term exponential sum — NOT $z^3-5$ being a $\{2,3\}$-smooth
integer (i.e., $z^3-5 = 2^a 3^b$). These are entirely different conditions:

- $z=4$: $z^3-5 = 59$ (prime). gpf($59$) = 59, which is NOT $\leq 3$. So $59$ is NOT a
  $\{2,3\}$-smooth integer. Yet $59 = 32 + 27 = 2^5 + 3^3$, which IS the Kuromine condition —
  and $(x,y,z)=(5,3,4)$ is a known Kuromine solution.

The gpf-smoothness approach addresses the equation $z^3-5 = 2^a 3^b$ (a different equation),
which IS a standard Ramanujan-Nagell type and has at most finitely many solutions by Baker's
method. But resolving THAT equation does not resolve the Kuromine equation $2^x + 3^y + 5 = z^3$.

**Wolfram check:** Among $z \leq 1000$, only $z=2$ gives $z^3-5=3=3^1$ (a $\{2,3\}$-smooth
integer). The equation $z^3-5=2^a 3^b$ is trivially finite. But this says nothing about the
original problem.

## Bounded-$A$ elimination via the boundary case (Session 15)

**Status:** The strategy "force $A = z - 3^j$ to be a small fixed integer, then kill it with
the 3-adic valuation" is a dead end for the Theorem-5 family. The valuation identity itself
(Theorem N) is correct and is kept; only the *elimination* fails.

**What was tried:** Theorem N gives the exact identity $2^x + 5 - A^3 = 3^{j+1}A(A+3^j)$ with
$v_3(2^x+5-A^3) = j+1$. For any *fixed* small $a$, $v_3(2^x+5-a^3)$ is a bounded constant
(Wolfram: $\leq 3$ for $a \leq 8$), which contradicts $j+1 \geq 55440$. So if $A$ could be
forced into a bounded range, every value would be eliminated. The factorization bound
$A < (2^x+5)/3^{2j} \approx 3e^{D}$ ($D = x\log2 - (2j+1)\log3$) makes $A$ small precisely at
the Theorem-M boundary $D \approx 0$.

**Why it fails (Wolfram, Session 15):** The Theorem-5 lattice never approaches the boundary
$D = 0$ closely enough. $D = c_0 + k_x P - k_y Q$ with $P/Q = 3\log2/\log3 \approx 1.8928$
irrational; the closest *surviving* ($D \geq 0$) approach over $k_x \leq 5000$ is $D \approx 55$
(at $(k_x,k_y)=(4729,8950)$), giving $A \gtrsim 3e^{55} \approx 6\times10^{24}$. The closest
overall approach, $D \approx 10$ at $(1054,1994)$, is on the *eliminated* ($D<0$) side. Each
unit of $(k_x,k_y)$-lattice distance to the boundary line costs $\sim 10^5$ in $D$, so $A \sim
e^{D}$ is never $O(1)$ for a surviving pair. The bounded-$A$ contradiction therefore cannot
fire. This is the **metric face of the two-comparable-S-units barrier**: the family is near
the $2^x = 3^y$ boundary in exponent *slope* but never in absolute log-*distance*, and $A$
measures exactly that distance.

**Consequence:** Theorem N re-proves (cleanly, via valuation) that $A$ is huge, but provides
no contradiction. Closeness-to-boundary cannot be exploited. Documented in
`knowledge/problem.md` (Theorem N) and `log/20260626_174500.md`.
