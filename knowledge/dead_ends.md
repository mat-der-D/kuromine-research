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
