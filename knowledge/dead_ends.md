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

**NOTE (corrected Session 21):** The "$D \approx 55$ floor over $k_x \leq 5000$" is a
finite-range artifact, NOT a true lower bound. Since $P/Q = 3\log2/\log3$ is irrational,
Weyl equidistribution gives $\inf_{k_x} D_{\ge0} = 0$ (Wolfram, Session 21: $D$ falls to
$0.537$ at $k_x=84180$ and keeps decreasing). This does NOT revive bounded-$A$ elimination:
the small-$D$ pairs occur at enormous $k_x$ with $j$ enormous, so $A \approx 3e^D = O(1)$
would then need a *fixed* small value at depth $j+1$ — still blocked by the Theorem-N
corollary (fixed small $a \Rightarrow$ bounded $v_3$, contradicting $j+1$). The dead-end
stands; only the "$D$ bounded away from 0" interpretation was wrong. See `log/20260627_120000.md`.

**Consequence:** Theorem N re-proves (cleanly, via valuation) that $A$ is huge, but provides
no contradiction. Closeness-to-boundary cannot be exploited. Documented in
`knowledge/problem.md` (Theorem N) and `log/20260626_174500.md`.

**NOTE (concrete instance, Session 34 — Theorem S).** Sessions 15/21 argued the closure of this
dead end *abstractly* (small $D$ at huge $k_x$ gives $O(1)$ genuine $A$ but the Theorem-N corollary
still blocks). Session 34 (Wolfram) made it **concrete** via the Convergent–Depth Trade-off Law:
the record minima of $D$ sit at the convergent denominators $q_n$ of $\rho=3\log2/\log3$ ($\mu(\rho)
=2$ numerically). At the sharpest feasible convergent $k_x=q_n=16836$ ($k_y=31866$), $D=3.7588$
forces the integer $A=z-3^j$ into the band $\approx[43,129]$ — **bounded-$A$ is actually realized at
a lattice point**. Yet $v_3(2^x+5-a^3)\le7$ for every $a\in[40,130]$ while a genuine solution would
need $v_3=j+1=1{,}766{,}706{,}480$: Theorem-N exclusion with a $\sim10^9$ margin, *with the small $A$
explicitly present*. The dead end stands, now with a verified concrete witness. See Theorem S in
`knowledge/problem.md` and `log/20260703_000000.md`.

## Thue-Mahler / norm-form approach (Session 18)

**Status:** RETIRED. No casting of the Kuromine equation as a single Thue-Mahler equation
$F(X,Y) = (\text{S-unit})$ exists; every candidate is broken by the additive constant 5.

**What was tried (Wolfram, Session 18):** Four distinct castings to a binary-form-equals-
S-unit (= Thue-Mahler) structure:
1. $z^3 - 4W^3 = 3^y + 5$ ($W=2^a$): RHS not a $\{2\}$-S-unit (the $+5$). Broken.
2. $z^3 - w^3 = 2^x + 5$ ($w=3^j$): RHS not a $\{3\}$-S-unit (the $+5$). Broken.
3. Eisenstein norm form $N_{\mathbb{Q}(\omega)}(z-w\omega) = B$, $A\cdot B = 2^x+5$:
   genuine norm form but $A$ varies independently; congruence content phantom-blocked
   (Session 4). Broken as a uniformity source.
4. $N_{\mathbb{Q}(5^{1/3})}(z - 5^{1/3}) = z^3-5 = 2^x + 3^y$ ($x^3-5$ irreducible, Wolfram):
   RHS is a *sum* of two S-units, not one, and uncontrolled. Broken.

**Why it fails:** The additive constant 5 (equivalently the two-term RHS) always prevents
the right-hand side from being a single S-unit. This is the Thue-Mahler face of the phantom
obstruction. The per-fixed-$y$ Thue equation $z^3-4W^3=3^y+5$ is finite (Wolfram: $W=2^a$
occurs only at $y=3$, the known solution), but Thue-Mahler theory gives only finiteness
*per equation* (bound via unit rank of $\mathbb{Q}(2^{1/3})$, which is $1$, and $|S|$), never
uniformity across the infinite $y$-progression — the actual open content.

**Genuine new facts produced (kept, non-actionable):**
- Symmetric reframing of the hard case: $z^3 - 4(2^a)^3 - (3^j)^3 = 5$ (verified on $(5,3,4)$).
- $v_{37}(2^x+5) = 1$ exactly and universally ($x\equiv5\pmod{36}=\mathrm{ord}_{37}(2)$,
  $2^x\equiv-5$), hence $37 \| B$. Since $37$ splits in $\mathbb{Z}[\omega]$, the mod-37 cube
  equation $z^3\equiv11$ has 3 roots $\{21,25,28\}$; the constraint $37\mid B$ (not $A$)
  selects $z\in\{21,28\}$; the phantom sits on the $z\equiv28$ branch. All soft-obstructed
  (phantom is a cube mod $37^n$ for all $n$, verified mod $37^3$; deeper residues vary across
  the family). Documented in `knowledge/references/thue_mahler_approach.md` and
  `log/20260626_230000.md`.

## Chabauty-Kim / algebraic-geometry methods (Session 13)

**Status:** Categorically inapplicable. Do not pursue any Chabauty-Kim variant.

**What was checked (Session 13):** The full 2025–2026 Chabauty-Kim cluster — Affine Chabauty I/II
(arXiv:2511.15949, 2602.05643), Modular Chabauty (arXiv:2505.12947), Cubic Chabauty
(arXiv:2604.20662).

**Why it fails (root cause):** Chabauty-Kim methods compute integral/$S$-integral points on
*algebraic curves*. Kuromine's variables $x,y$ are **exponents of fixed bases**, not algebraic
coordinates; the constraint "$u = 2^x$ for integer $x$" cannot be encoded as $S$-integrality on a
curve. This is a **categorical mismatch** (the equation lies outside the algebraic category), not a
quantitative gap — no improvement in Kim-set depth, rank condition, or computational reach can
change it. The fixed-variable specialization only re-derives the per-fixed-$N$ Mordell/Thue
finiteness already covered by the Thue-Mahler and elliptic-curve dead ends, with no family
uniformity. **Fifth categorical barrier.** Full analysis in `log/20260626_120000.md`.

## Cyclotomic phantom family (Session 17 build, Session 19 retirement)

**Status:** RETIRED. Structural insight only; no actionable attack on $c=5$.

**What was tried:** Compare the general $y=-3$ phantom family $c_m = 27m^3+9m^2+m-32$,
$z_m=(9m+1)/3$ (giving $c_1=5$, $c_2=222$, $c_3=781$) to see whether a neighboring constant is
easier and transfers a method back to $c=5$.

**Findings (Session 19, analytic):** (i) **Theorem O (parity partition):** $c_m$ is odd iff $m$ is
odd, so $z$ is even for odd-$m$ equations and odd for even-$m$ equations. (ii) $c_1=5$ is uniquely
special — the only $c_m$ with $2^5+c_m$ prime $\equiv1\pmod3$ (the forced-factor pivot $37$);
all others are composite with extra small-prime factors, and the "$37\|B$" structure is absent for
$m\ge2$ (e.g. $37\mid c_2=222$). $c_1=5$ is the *easiest* case in the family.

**Why it fails:** Every equation $2^x+3^y+c_m=z^3$ is locally solvable at every $p\ne3$ (the
phantom is a global rational cube for all $m$), so the soft obstruction is universal and no
modular method works for any $c_m$. Studying $m\ge2$ yields no technique applicable to $c_1=5$.
Full analysis in `log/20260627_000000.md`.

## Coupling-Height / Moving-Filtration framework (Session 20 build, Session 21 retirement)

**Status:** RETIRED. The Session-20 theory-building framework rested on two candidate
lemmas; Session 21 (Wolfram) resolved both negatively. Do not rebuild without a genuinely
new external "depth $\Rightarrow$ size" transfer inequality.

**The framework.** A non-additive arithmetic height coupling the archimedean place and the
place 3 along the Theorem-5 progression: principal 3-adic cube root $\beta(x)$ of
$N(x)=2^x+5$; moving depth $\delta_x(a)=v_3(2^x+5-a^3)$ and depth filtration; size class
$\sigma_x(a)=3\log_2 a/x$; Coupling Height $\widehat H_x(a)=\sigma_x(a)(1+\delta_x(a))\mathbf1[\text{gate}]$.
Designed to exploit the one non-degenerate handle (genuine depth $j+1\to\infty$ vs phantom
depth 0). Its two load-bearing lemmas:

- **Lemma A (Depth–Size Incompatibility) — REFUTED as circular.** Claimed:
  $\delta_x(a)\ge j+1\Rightarrow|\sigma_x(a)-1|\ge c_0(j+1)/x$, giving a contradiction with
  the genuine band for $k_y\ge1$. The supporting mechanism — "smallest integer of depth
  $\ge d$ is $\approx 3^{d-2}$, hence off the size band" — holds for the **fixed** target
  $N=37$ (Wolfram: smallest $a$ of depth $d$ runs $1,4,22,49,211,697,2155,\ldots$;
  $\sigma_5\approx0.95(d-2)$; implied $c_0\in[0.33,3.5]$), **but is a property of the fixed
  target only.** Decisive surrogate: the moving-style target $N=22^3+3^{10}\cdot7$ has its
  smallest depth-10 integer equal to the *small* number 22. For the real moving target
  $2^x+5$, "a small deep cube-root ($A$, size $2^{x/3}$, depth $j+1$) exists" is *exactly the
  Kuromine question*. So Lemma A is circular — provable only via an effective irrationality
  measure (the unavailable tool). See `log/20260627_120000.md`.

- **Lemma B′ (Lattice Rigidity) — REFUTED as false.** Claimed: minimal nonnegative
  $D=x\log2-(2j+1)\log3$ over the $D$-lattice is bounded below by a positive constant. False:
  $D=c_0+k_xP-k_yQ$ with $P/Q=3\log2/\log3=1.8927892607\ldots$ **irrational**, so (Weyl
  equidistribution) $\inf_{k_x}D_{\ge0}=0$. Wolfram: minimal nonnegative $D$ falls
  $98.5\to0.537$ by $k_x=84180$ and keeps decreasing. **Session 15's "$D\approx55$ floor"
  was a finite-range artifact** ($k_x\le5000$). The $D$-lattice approaches $D=0$ arbitrarily
  closely. This does NOT revive bounded-$A$ elimination: small $D$ at huge $k_x$ gives $O(1)$
  genuine $A$ only with $j$ enormous, so the Theorem-N corollary still blocks it.

**Why it fails (root cause).** The unique non-degenerate handle (3-adic depth $j+1$) is real
but **non-transferable** to an archimedean size constraint without an effective irrationality
measure for $2^{1/3}$ below $\sim1.1$ — exactly the missing tool. The coupling height is a
faithful repackaging of the obstruction, not a way around it. Third independent confirmation
of the P1–P4 conjunction barrier (after the metric face S15 and the analytic face
S3/S10/S11). Full detail in `log/20260627_120000.md`.

## Linear-exponential decidability frontier — blocked by the free cube (Session 22)

**Status:** Does NOT reach Kuromine. The 2025–2026 decidability results for
linear-exponential Diophantine systems are blocked by a **degree obstruction**. Do not
pursue a decidability/Skolem-style route unless someone extends the class to a free
higher-degree term.

**What was checked (Wolfram + arXiv watch, Session 22):** The KLNOW (2025) result makes
solvability of **linear-exponential** Diophantine systems **over two primes** decidable
(variables appear in exponents of fixed bases and at most **linearly**, degree 1, as
polynomial terms; proof **uses Baker's theorem**). Dong–Shafrir (arXiv:2505.19141, STOC
2026) reduce module S-unit equations to such systems, giving decidability when the base
$T$ has $\le 2$ prime divisors (arbitrary $T$ = "major breakthrough in number theory").

Kuromine's exponential skeleton $2^x + 3^y + 5$ is over **exactly two primes** ($T=6$) —
inside the prime-count frontier. **But the term $z^3$ has $z$ free at degree 3**, outside
the decidable (degree $\le 1$) class. After the Theorem-5 factoring $z = 3^j + A$ (Wolfram):
$z^3 = 3^{3j} + 3^{1+2j}A + 3^{1+j}A^2 + A^3$ — the free cube $A^3$ persists; $z$ is not
$\{2,3\}$-smooth in general, so it cannot be re-encoded as a monomial. Kuromine sits **one
prime within but two polynomial degrees above** the frontier.

**Why it fails (root cause).** A free degree-3 term per fixed RHS is a Mordell/Thue cubic —
exactly the **per-fixed-variable wall** already retired (elliptic-curve and Thue-Mahler dead
ends): finite/effective per fixed $x$, **no uniformity** across the infinite family. So the
decidability angle collapses onto an existing wall, and its in-class engine (Baker) is
itself structurally dead for Kuromine (Session 5, $v_p(\Lambda_p)=0$). Eleventh independent
confirmation of the barrier. Full detail in `knowledge/references/linear_exponential_decidability.md`
and `log/20260626_HHMMSS.md` (Session 22).

## Differential Progression Framework (Session 24)

**Status:** RETIRED. The 3-adic Taylor analysis of the bijection $k_x \mapsto A(k_x)$
is equivalent to the existing Theorem-J lifting law. No new information produced. Do not
rebuild without a genuinely new archimedean handle.

**What was tried (Session 24):** Studied the 3-adic analytic curve
$\mathcal{K}: A^3 = 32\exp_3(kL)+5$ over $\mathbb{Z}_3$ with $L = \log_3(2^{332640})$,
$v_3(L) = 4$. Computed the tangent speed via implicit differentiation:
$$\tau(k) = \frac{dA}{dk} = \frac{32 g^k L}{3 A^2}, \quad v_3(\tau) = 3.$$
The second derivative has $v_3(A'') = 6$. The Taylor expansion gives
$A(k+1) - A(k) \equiv \tau(k) \pmod{3^6}$, so consecutive integer inputs differ by a
multiple of $3^3 = 27$ in 3-adic value. The archimedean gap $|A(k+1) - A(k)| \approx
(332640 \log 2/3) \cdot A(k)$ is proportional to $A(k)$ — enormous but unremarkable.

**Why it fails:** The 3-adic Taylor coefficients of $A(k_x)$ at any integer point $k_0$
ARE exactly the Theorem-J lifting-law data (Sessions 6–10). The differential framework
is a repackaging of Theorems I–L, not a new tool. In particular, $v_3(\tau) = 3$
implies $A(k_0) \equiv A(k_1) \pmod{27}$ for any two integer inputs — exactly the
universal residue $A \equiv 22 \pmod{27}$ (Theorem I). The second-order term gives the
branching at depth 81 (Theorem I, three branches) — exactly already known. No constraint
beyond Theorem-J is produced at any order of the Taylor expansion.

**Root cause:** 3-adic analyticity of $A$ was already fully exploited in Session 10
(bijection $\mathbb{Z}_3 \to \mathbb{Z}_3$) and Sessions 6–10 (complete modular portrait).
Any further 3-adic computation reduces to the same data. **Fourth independent confirmation
that 3-adic data alone cannot bridge the gap to an archimedean size constraint.**

**Positive residual (kept):** Clean formulation of the Kuromine curve
$\mathcal{K}: A^3 = 32\exp_3(kL)+5$ over $\mathbb{Z}_3$ with explicit tangent speed
formula $\tau = (A^3-5)L/(3A^2)$. Compact new encoding of existing data.

See `log/20260626_120100.md` for full derivation.

## Cubic-Transversality / Dial–Lattice framework (Session 27 build, Session 28 retirement)

**Status:** RETIRED. The archimedean theory-building framework rested on the unproven crux
Lemma C; Session 28 (Wolfram) refuted Lemma C as a route. Do not reopen — Lemma C is provably
equivalent to the open target itself. **Lemma D is kept** as a correct structural clarification
(retained in `knowledge/references/cubic_transversality_framework.md`).

**The framework (Session 27).** Reformulate via $W=3z$: $W^3 = 27\cdot2^x + 3^{y+3} + 135$ (the
"dial form"). A genuine solution is an integer cube root ($z\in\mathbb Z$, i.e. $W\in3\mathbb Z$);
the phantom is a denominator-3 rational cube root ($z=10/3$, $W=10$). Regard $2^x$ as a
continuous dial sweeping $R_y(t)=(27\cdot2^t+3^{y+3}+135)^{1/3}$ across the lattice $3\mathbb Z$;
the cubic defect is $\Theta(x,y)=\operatorname{dist}(R_y(x),3\mathbb Z)$, with $\Theta=0$ iff a
solution. Two load-bearing lemmas:

- **Lemma D (Denominator Rigidity) — PROVED, KEPT.** On the survival sheet $y\ge0$, any cube hit
  $W^3=27(2^x+3^y+5)$ has $27\mid W^3\Rightarrow3\mid W\Rightarrow z\in\mathbb Z$. So the
  phantom's denominator-3 escape is structurally confined to $y<0$, OFF the Theorem-5 lattice —
  the first formulation in which the phantom is provably ABSENT from the relevant sheet. A
  genuine clarification, but not a step toward a proof (it removes the phantom from the survival
  sheet; the remaining transversality content is Lemma C).

- **Lemma C (Defect Quantization, the crux) — REFUTED as a route (Session 28).** Claimed: an
  effective resonance-exclusion / equidistribution bound forcing the dial orbit off $3\mathbb Z$.

**Why it fails (Wolfram, Session 28).** The decisive finding is an **exact identity**
(`Simplify` returns 0):
$$\operatorname{dist}\big(R_y(x),\,3\mathbb Z\big) \;=\; 3\cdot
\operatorname{dist}\big((2^x+3^y+5)^{1/3},\,\mathbb Z\big).$$
The dial-orbit discrepancy from $3\mathbb Z$ is *exactly* 3 times the **original cube-root
distance** of $z=(2^x+3^y+5)^{1/3}$ from $\mathbb Z$: the $\times27$ / $W=3z$ rescaling is undone
by the cube root, so the "new archimedean object" is the original cube-distance, not a new one.
Because the Theorem-5 family has $x\equiv2\pmod3$ (Wolfram: $5\equiv2$, $332640\equiv0$),
$2^x=4M^3$ with $M=2^{(x-2)/3}$, and in the $2^x$-dominant survival wedge
$$\operatorname{dist}\big((2^x+3^y+5)^{1/3},\mathbb Z\big)\approx
\frac{|m^3-4M^3-(3^y+5)|}{3N^{2/3}},\qquad m=\operatorname{round}(2^{2/3}M),$$
whose minimal numerator is governed by $|m^3-4M^3|$ — the rational approximation of
$2^{2/3}=4^{1/3}$ by $m/M$, **exactly the Session-3 auxiliary $2^{2/3}$-Thue quantity**. Wolfram
confirmed: (i) the discrepancy descends toward 0 along deep $2^{2/3}$-convergents (e.g.
$m=3251$, $m^3-2^{35}=83883$, $\operatorname{dist}\approx0.00265$ at $x=35$; smaller deeper), so
it has **no positive constant lower bound**; (ii) the realized approximation exponent of $m/M\to
2^{2/3}$ on the family is **sub-Dirichlet** ($\kappa\le1.21$, negative for most pairs:
$-0.377,+0.811,+1.208,+0.415,\dots$, reproducing the Session-3/11 record). An effective lower
bound $\operatorname{dist}\gg N^{-c}$ would require an effective irrationality measure
$\mu(2^{2/3})<3$ acting on *these* approximations — but they are sub-Dirichlet, so **no measure
acts** (measures only bound good approximations, exponent $\ge2$). Lemma C's only non-trivial
route (effective equidistribution) IS the two-comparable-S-units barrier in a new disguise.

**Root cause.** The dial reformulation relocated the wall to an archimedean equidistribution
question, but the cube root undoes the rescaling, returning the *identical* Session-3
sub-Dirichlet $2^{2/3}$-approximation obstruction. **Sixth independent confirmation that the
barrier is place-independent**; the attack-face inventory is now complete — metric (S15),
analytic/irrationality (S3/10/11), 3-adic-coupling (S20–21, S24), decidability/degree (S22),
and archimedean-equidistribution (S27–28) — all returning the same wall. Full detail in
`log/20260628_000000.md`. **DO NOT REOPEN** without a tool that beats the Dirichlet floor on the
$2^{2/3}$ approximation (equivalently, supplies a power-saving $\kappa>1$ gap bound).

## Integral Valuation-Budget framework (Session 38 build + retirement)

**Status:** RETIRED. Theory-building under the SPECIAL DIRECTIVE. The framework's only proved
lemma (VB-1) duplicates Cubic-Transversality Lemma D; its crux lemma (VB-2) is proved equivalent
to the missing effective $\kappa>1$ gap bound. **Seventh independent theory-building confirmation
of the wall.** Do not reopen.

**The framework (Session 38).** A local-global / valuation-budget obstruction (a *different shape*
from the three prior transfer frameworks, deliberately chosen because the wall is a local-global
failure — solvable everywhere locally, no global integer point — not a metric-transfer gap).
Records, for the factorization $2^x+5=A\cdot B$, the **valuation-budget vector**
$(v_p(A))_p$ vs $(v_p(B))_p$ at every place plus the archimedean size of $A$, and the
**phantom defect** $\partial=-\min_p\min(v_p(A),v_p(B))$ ($\partial=0$ iff $A,B\in\mathbb Z$).

- **Lemma VB-1 (Budget rigidity) — PROVED, KEPT.** On the survival sheet $k_y\ge0$ ($y\ge0$), the
  conserved budget $v_3(A)+v_3(B)=v_3(2^x+5)=0$ (Wolfram: $2^x+5\equiv1\pmod3$ universal, $x$ odd)
  plus integrality of $A,B$ forces $(v_3(A),v_3(B))=(0,0)$; the phantom's split $(1,-1)$
  ($A_{\text{ph}}=3$, $B_{\text{ph}}=37/3$) requires $y<0$. **This is exactly Cubic-Transversality
  Lemma D**, re-derived through the budget; correct but gives no constraint on genuine solutions
  ($\partial=0$ is automatic).

- **Lemma VB-2 (Height–Integrality Incompatibility) — REFUTED as a route (= the open target).**
  Claimed: no $(k_x\ge1,k_y\ge0,D\ge0)$ has the band-integer $A\in[e^D/3,3e^D]$ at depth
  $v_3(2^x+5-A^3)=j+1$. This is precisely "does the size-$e^D$ band contain the depth-$(j+1)$
  3-adic truncation of size $\sim2^{x/3}$" — the realized-gap-exponent question. A uniform proof
  requires $|z^3-3^y|>C(z^3)^\kappa$, $\kappa>1$ — the missing tool. Provably equivalent to the
  open target, not a way around it.

**Why it fails (root cause).** The $p$-adic valuation budget is conserved and self-consistent at
every place (the phantom satisfies it everywhere — Session-38 multi-prime portrait: phantom on the
family cube-root/$B$ branch at all primes $7..127$). The only datum separating genuine from
phantom is integrality, which is archimedean once the place-valuations are pinned. The local-global
angle is genuinely a new *shape* but returns the same archimedean $\kappa>1$ gap. **Seventh
confirmation.** Full statement in `knowledge/references/valuation_budget_framework.md`;
session narrative in `log/20260704_000000.md`. **DO NOT REOPEN** without a mechanism that produces
an archimedean $\kappa>1$ gap from the outset.

**Genuine residual facts (kept):** (i) the multi-prime joint portrait (phantom on the family branch
at all primes $7..127$, the sharpest single soft-obstruction demonstration); (ii) the
budget-cancellation identity $v_3(A)+v_3(B)=0$, genuine $(0,0)$ vs phantom $(1,-1)$.
