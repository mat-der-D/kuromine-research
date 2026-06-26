# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [LOW — NEW, Session 27, theory-building] Cubic-Transversality / Dial–Lattice framework

**Built in Session 27 (2026-06-27)** under the SPECIAL DIRECTIVE after a negative arXiv watch.
A genuinely **archimedean-first** framework, logically distinct from the two retired
3-adic-only theory-building frameworks (Coupling-Height S20–21, Differential-Progression S24).
Full write-up: `knowledge/references/cubic_transversality_framework.md`.

**New handle (Wolfram-verified).** Genuine solution = *integer* cube root ($z\in\mathbb Z$);
phantom = *denominator-exactly-3 rational* cube root ($z=10/3$). With $W:=3z$ the equation
becomes the **dial form** $W^3 = 27\cdot 2^x + 3^{\,y+3} + 135$. A real/rational distinction,
not a $p$-adic one.

- **Lemma D — PROVED (clean output).** On the survival sheet $y\ge0$, any cube hit
  $W^3=27(2^x+3^y+5)$ has $27\mid W^3\Rightarrow 3\mid W\Rightarrow z\in\mathbb Z$. So the
  phantom's denominator-3 escape is **confined to $y<0$, OFF the Theorem-5 lattice**. This is
  the first formulation in which the phantom is provably ABSENT from the relevant sheet (not
  merely soft-obstructing). The conjecture on $\mathcal L$ reduces to **pure transversality with
  no phantom to dodge**.
- **Lemma C — UNPROVEN crux.** Effective resonance-exclusion: the exponential dial orbit
  $R_y(x)=(27\cdot2^x+3^{y+3}+135)^{1/3}$ (velocity $\theta'\asymp2^{x/3}$, Wolfram ✓) never
  lands exactly on $3\mathbb Z$ on the survival wedge. As a naive gap bound it is **vacuous**
  (= the original $27|2^x+3^y+5-z^3|$); its only route is an **effective equidistribution/
  discrepancy** bound for the dial orbit. **Honest expectation:** the two-comparable-S-units
  degeneracy likely re-surfaces here (the orbit's effective equidistribution rate is governed
  by the same Diophantine quantity that makes Baker give $v_p=0$). The framework **relocates**
  the wall to an archimedean equidistribution question; it does not yet breach it.

**Priority rationale.** Kept at LOW (not retired) because (i) Lemma D is a genuine, proved
clarification — the phantom does not obstruct the survival sheet in this formulation — and
(ii) Lemma C is the one untried *archimedean* angle. Next step: test whether effective
equidistribution can exclude a single lattice hit, or confirm it collapses to the same barrier.

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered in Session 1 (2026-06-25).** For all Theorem 5 solutions, $y = 3j$ and the equation factors as $(z-w)(z^2+zw+w^2) = 2^x + 5$ with $\gcd = 1$ and $z^2+zw+w^2$ having only prime factors $\equiv 1 \pmod 3$. This is a norm form equation in $\mathbb{Z}[\omega]$ (Eisenstein integers).

**Session 3 progress:**
- Clean equivalent single equation, with $A = z - 3^j$:
  $$2^x + 5 = A^3 + 3^{j+1}A^2 + 3^{2j+1}A = A\,(A^2 + 3^{j+1}A + 3^{2j+1}).$$
  Brute force ($x\le40$) recovers BOTH known solutions, each with **$A = z-3^{y/3} = 1$**.
- Eisenstein-norm identity $4B - 3w^2 = (2z+w)^2$ (verified on $(5,3,4)$: $148-27=121$).
- **Negative:** the inert-prime condition ($q\equiv2\bmod3$, $q\mid2^x+5 \Rightarrow q\mid z-3^j$)
  is automatically consistent (gives $3^{3j}\equiv3^y\bmod q$, automatic since $y=3j$). So the
  factorization yields no new congruence — soft obstruction again.

**Session 4 progress / downgrade:** The factorization's *congruence* content is now proven
inert (soft obstruction: $A\equiv3\pmod p$, $B\equiv37/3\pmod p$ for all $p\ne3$, matching the
phantom $A=3$, $B=37/3$). The only real-vs-phantom distinction is 3-adic ($v_3(A)=0$ vs $1$),
blocked by the $3^n$ wall. $A$ is provably huge ($\sim2^{x/3}/3 \le A \le 1.587\cdot2^{x/3}$),
so "$A=1$" is impossible for Theorem-5 — sub-question (c) is closed negatively. The direction
survives **only** in its global/size form (sub-question (a)), which still needs a tool that
does not yet exist. Effective priority is now **MEDIUM at best**, kept here as the cleanest
single-equation reformulation rather than an active lead.

**Session 15 progress (Theorem N).** New exact 3-adic valuation identity:
$2^x + 5 - A^3 = 3^{j+1}A(A+3^j)$, hence $v_3(2^x+5-A^3) = j+1$ (using $\gcd(A,3)=1$ from
Theorem I). This re-proves cleanly, via valuation, that $A$ is no fixed small integer (for
fixed $a$ coprime to 3, $v_3(2^x+5-a^3)$ is a bounded constant $\leq 3$, contradicting
$j+1 \geq 55440$). The $A=1$ band: LTE gives $v_3(2^x+4)=2$ universally $\Rightarrow j=1$
(only the known solution). See Theorem N in `knowledge/problem.md`. The *elimination*
strategy (bounded $A$ + small valuation) is closed negatively — see sub-question (a).

Key sub-questions (remaining):
- (a) [CLOSED negatively, Session 15] Bounded-$A$ / boundary-case elimination. $A$ is small
  only at the Theorem-M boundary $D := x\log2-(2j+1)\log3 \approx 0$, but the Theorem-5
  lattice never lands within $O(1)$ log-distance of it: closest *surviving* ($D\geq0$)
  approach over $k_x\leq5000$ is $D\approx55$ ($A\gtrsim10^{24}$); closest overall $D\approx10$
  is on the *eliminated* side (Wolfram). The metric face of the two-S-units barrier. Moved to
  `knowledge/dead_ends.md`. [Session 21 note: the "$D\approx55$ floor" is a finite-range
  artifact; in fact $\inf D_{\ge0}=0$ by equidistribution — but this does NOT revive the
  elimination; the Theorem-N corollary still blocks. See dead_ends.md.] (The earlier
  Thue-Mahler-per-$x$ note remains: finiteness per $x$ known; uniformity over the
  $x$-progression open, no current tool delivers it.)
- (b) [CLOSED, Session 4] growth / primitive-divisor (Zsygmondy/BHV): inapplicable — $B$ is not a Lucas/Lehmer sequence. See RETIRED entry below.
- (c) [CLOSED negatively, Session 4] $A = z - 3^{y/3}$ cannot be forced to 1; it is provably $\sim2^{x/3}$ for any Theorem-5 solution. (Re-proved 3-adically in Session 15, sub-question (a).)

### [RETIRED in Session 3] Effective Diophantine approximation to $2^{1/3}$

**Elevated in Session 2, RETIRED in Session 3 with a proof.** The reframing
$z^3 - 4W^3 = 3^y+5$ ($W=2^a$, $x=3a+2$) makes $z/W$ a rational approximation to
$2^{2/3}$. The session computed (Wolfram, two independent ways) that this approach
*cannot* work:
- The realized approximation exponent is $\kappa_{\text{real}}\approx0.62<1$, far below
  any effective irrationality measure $\mu\ge2$. Irrationality measures are *lower*
  bounds; they only constrain *good* approximations ($\kappa\ge\mu$). $z/W$ is a *bad*
  approximation, so no measure (however sharp, including arXiv:2510.04156) gives
  information.
- As a Thue lower bound a contradiction needs $\log(3^y+5)<(3-\mu)\log\max(z,W)$, but
  LHS $\approx182718$, RHS $\approx43809$ ⟹ off by $+138909$. The form value $3^y+5$ is
  far too large.

**Root cause:** $3^y$ is *not* a small perturbation of $2^x$ — $\log3^y/\log2^a\approx2.38$,
so $3^y\approx z^2$. This is the "two comparable dominant S-units" regime, beyond any
single cubic irrationality measure. See
`knowledge/references/irrationality_measure_obstruction.md`. Moved toward dead_ends.

**Session 11 strengthening.** The realized approximation exponent $\kappa_{\text{real}}$
of $z/W$ to $2^{2/3}$ is **not** a single value $\approx 0.62$; it is $0.62$ only at the
family floor $k_y = 0$ and goes **negative** for every $k_y \geq 1$ ($-1.75, -4.13, -6.51,
\dots$; Wolfram). For almost the entire Theorem-5 family the approximation *diverges*
($|2^{2/3} - z/W| \gg e^{134867} \gg 1$), because $3^y$ grows faster than $2^x$ along the
progression. So the situation is even worse than Session 3 recorded: any
separation/measure bound (a lower bound, nontrivial only for *good* approximations,
$v \geq 2$) has nothing to act on. This also rules out Badziahin's 2026 cubic-vs-rational
separation results — see the arXiv-survey [LOW] direction below.

### [LOW, ~RETIRED as standalone] $p$-adic analysis of the phantom solution

**Session 10 addendum (Suggestion #1 resolved).** The map $k_x \mapsto A$ is now written
explicitly as a 3-adic analytic function: with $g = 2^{332640}$ one has $v_3(g-1)=4$
(Wolfram), so $2^x = 32\,g^{k_x} = 32\exp_3(k_x L)$ with $L=\log_3 g$, $v_3(L)=4$, and
$A(k_x) = (32\exp_3(k_x L)+5)^{1/3}$ (the $z\equiv1\bmod3$ branch) is 3-adic analytic. By
Theorem J it is a **bijection** $\mathbb{Z}_3\to\mathbb{Z}_3$; hence for each integer target
$a\equiv22\pmod{27}$ there is a unique $s_a\in\mathbb{Z}_3$ with $A(s_a)=a$, and "$A(k_x)$
rational at integer $k_x$" reduces to "$s_a\in\mathbb{Z}\subset\mathbb{Z}_3$", which is
**3-adically undetectable** ($\mathbb{Z}$ dense in $\mathbb{Z}_3$). No analytic obstruction.
This was the last untried 3-adic idea; it is empty. Keep at LOW/~RETIRED.

**Downgraded in Session 2.** The phantom $2^5+3^{-3}+5 = (10/3)^3$ is a *global rational
cube*, hence a cube modulo every prime $p\ne3$ and (constrained to 37) mod $3^n$ for all
$n$. The cube map is a bijection mod $2^n$ and mod $3^n$ on the relevant residues, so the
equation is **locally solvable at every prime**. Therefore no p-adic / congruence
argument can *alone* refute a solution — proven, not just observed. The p-adic
computations remain useful as auxiliary constraints feeding a global argument (e.g.
$z\equiv6\pmod{32}$, $v_3(z^3-37)=4+v_3(k)$), but p-adic elimination on its own is a
dead end. See `knowledge/references/two_adic_structure.md`. (Kept at LOW only because the
derived congruences support other directions.)

### [RETIRED in Session 5] Baker's method / linear forms in logarithms (all variants)

**Session 1 assessment:** Matveev's archimedean bound is too weak (bound $\exp(-5.6\times10^{14})$ vs actual $\exp(-47854)$, no contradiction).

**Session 5 retirement:** Yu's p-adic Baker theorem also fails, for a *structural* reason not a quantitative one. For the 3-adic linear form $\Lambda_3 = x\log_3(2) - 3\log_3(z)$: $v_3(\Lambda_3) = v_3(-(3^y+5)) = 0$ (since $5 \equiv 2 \pmod 3$). For the 2-adic form: $v_2(\Lambda_2) = v_2(-(3^y+5)) - v_2(z^3) = 3 - 3 = 0$. Yu's theorem gives an *upper* bound on $v_p(\Lambda_p)$; a contradiction requires actual $v_p$ to exceed the upper bound. With $v_p = 0$, this is trivially impossible regardless of constants. **All Baker-type methods — archimedean and p-adic — are now retired.** Root cause: the "two comparable dominant S-units" regime ($3^y \approx z^2$) means no linear form of the expected type is small in any metric. See `knowledge/references/baker_method.md` and `knowledge/dead_ends.md`.

### [~RETIRED in Session 18] Elliptic curve approach (fix one variable)

Fixing $x = 5 + 332640k$ and studying $z^3 - 3^y = 2^x + 5$ as a family of curves. **Now linked to the factorization approach** above.

**Session 18 assessment (effectively retired).** This is the same per-fixed-variable wall as the Thue-Mahler direction (now retired). Fixing $x$ (or $y$) gives a Mordell / Thue equation $z^3 = 2^x + (3^y+5)$ with finitely many, effectively computable solutions per fixed value — but $N_{k_x} = 2^{5+332640k_x}+5$ has $\sim 10^5$ decimal digits, so no per-curve computation is feasible, and (as Session 4's `modular_method.md` already noted) there is **no uniformity** across the infinite family. The elliptic/Mordell route degenerates to exactly the Thue-Mahler wall: solvable case-by-case in principle, silent about the infinite Theorem-5 progression. No distinct new content beyond the retired Thue-Mahler entry; treated as ~RETIRED.

### [RETIRED in Session 4] Primitive divisor / growth arguments (Zsygmondy, Bilu–Hanrot–Voutier)

**Elevated in Session 3, RETIRED in Session 4.** Two sub-forms, both closed:
- *Congruence form* (find a prime $p\equiv1\bmod3$ that must/cannot divide $B$): dead by the
  soft obstruction. Session 4 showed $x\bmod3$, $y\bmod6$ are constant over the family, so
  $2^x,3^y,w\pmod p$ are pinned, and $A=z-w\equiv3\pmod p$ for *every* prime $p\equiv2\bmod3$
  tested — because the phantom has $A_{\text{phantom}}=3$, $B_{\text{phantom}}=37/3$, which
  reduce mod every $p\ne3$. Every congruence on $A,B$ is satisfied by the phantom.
- *Growth form* (primitive divisors of $B$ along the progression): no clean object —
  $B=(2^x+5)/(z-3^j)$ is **not** a Lucas/Lehmer $a^n-b^n$ sequence ($z,j$ both vary
  non-linearly in $x$), so Zsygmondy/BHV do not apply.

The only genuine real-vs-phantom distinction is 3-adic ($v_3(A)=0$ vs $1$; $A\bmod9\in
\{1,4,7\}$ vs $3$) and is blocked by the known "$37$ is a cube mod $3^n$" wall. Moved to
`knowledge/dead_ends.md`; details in `knowledge/references/factorization_approach.md`.

### [RETIRED in Session 4] Modular method / Frey curves

**Tried and ruled out in Session 4 (structural).** The Frey-curve / modular method needs a
*varying prime exponent* to carry the mod-$p$ Galois representation; the Kuromine equation
has only a fixed small cube exponent, with $x,y$ on fixed small bases 2,3. No Frey curve can
be built. The fixed-$y$ elliptic/Mordell route only re-derives the already-known per-$y$
finiteness, giving no uniformity over the Theorem-5 family. See
`knowledge/references/modular_method.md`. Moved to `knowledge/dead_ends.md`.

### [RETIRED in Session 18] Thue-Mahler equation approach

**New direction identified in Session 1; deeply explored and RETIRED in Session 18.** The equation $z^3 - w^3 = N_k$ with $w = 3^j$ is a Thue-Mahler type equation. For each fixed $k$, $N_k = 2^{5+332640k} + 5$ is fixed, and the Thue-Mahler theorem gives finitely many solutions. The question is whether no solution exists for any $k \geq 1$.

**Session 18 deep exploration (Wolfram), result negative.** Enumerated all four candidate castings to a single Thue-Mahler equation $F(X,Y) = (\text{S-unit})$ and showed each is broken by the additive constant 5 (the RHS is never a single S-unit):
1. $z^3-4W^3 = 3^y+5$ ($W=2^a$): RHS not a $\{2\}$-S-unit. 2. $z^3-w^3 = 2^x+5$ ($w=3^j$): RHS not a $\{3\}$-S-unit. 3. Eisenstein norm form $N(z-w\omega)=B$: $A$ varies independently; phantom-blocked. 4. $N_{\mathbb{Q}(5^{1/3})}(z-5^{1/3}) = 2^x+3^y$: RHS a *sum* of two S-units, uncontrolled.

Per-fixed-$y$ the Thue equation $z^3-4W^3=3^y+5$ is finite (Wolfram: $W=2^a$ occurs only at $y=3$, the known solution); Thue-Mahler theory gives finiteness *per equation* (via unit rank $1$ of $\mathbb{Q}(2^{1/3})$ and $|S|$) but **no uniformity** over the infinite $y$-progression. Same two-comparable-S-units / phantom barrier.

**New facts (kept, non-actionable):** (i) symmetric reframing of the hard case $z^3 - 4(2^a)^3 - (3^j)^3 = 5$ (verified on $(5,3,4)$); (ii) $v_{37}(2^x+5)=1$ exactly and universally $\Rightarrow 37\|B$; the mod-37 cube branches $z\in\{21,25,28\}$ are all soft-obstructed (phantom is a cube mod $37^n$ for all $n$). See `knowledge/references/thue_mahler_approach.md`. **Moved to `knowledge/dead_ends.md`.**

**References:** arXiv:2207.14492 (Efficient resolution of Thue-Mahler equations).

### [RETIRED in Session 14] Greatest prime factor reformulation: gpf($z^3 - 5$)

**Identified in Session 13. Retired in Session 14 (fundamental conflation).**

The original claim was: if gpf($z^3-5$) grows with $z$, then only finitely many $z$
can satisfy $z^3-5 \in \{2^a 3^b\}$, which is "exactly the Kuromine condition."

**Why this is wrong (Session 14):** The Kuromine condition is $z^3 - 5 = 2^x + 3^y$
(sum-representability), NOT $z^3-5 \in \{2^a 3^b\}$ ($\{2,3\}$-smoothness). These
are entirely different. The known solution $z=4$ gives $z^3-5=59$ (prime, gpf=59 >> 3),
yet $59 = 2^5 + 3^3$ is a valid decomposition. gpf growth does NOT prevent sum
representations.

The reformulation as $z^3-5 = 2^a 3^b$ (a different equation) has a different solution
set: Wolfram check shows $z=2$ gives $z^3-5=3=3^1$ (the ONLY $z \leq 1000$ with
$z^3-5$ being $\{2,3\}$-smooth). That equation ($z^3-5=2^a 3^b$) has at most finitely
many solutions by Runge's method / Baker's theorem, but resolving it does not resolve
the original Kuromine problem.

**Conclusion:** The direction conflates two distinct mathematical conditions. Retired.
Moved to `knowledge/dead_ends.md`.

### [MEDIUM] Theorem M and the size-partitioned Theorem-5 family

**New direction, Session 14.** Proved:

**Theorem M (new, elementary):** If $y = 3j$ and $3^{2j+1} > 2^x + 4$, then
$2^x + 3^y + 5$ is NOT a perfect cube.

*Proof:* The integer target lies strictly between consecutive cubes $(3^j)^3$ and
$(3^j+1)^3$, which are spaced $3^{2j+1}+3^{j+1}+1$ apart. $\square$

**Application to Theorem-5:** With $x = 5+332640\,k_x$ and $j = 55439+55440\,k_y$:

$$\text{Ruled out: } k_y \geq \left\lceil \frac{x\log 2/\log 3 - 110879}{110880} \right\rceil \approx \lceil 1.893\,k_x - 1.107 \rceil.$$

For $k_x=1$: all $k_y \geq 1$ ruled out (only $k_y=0$ survives).
For $k_x=2$: $k_y \geq 3$ ruled out (only $k_y \in \{0,1,2\}$ survive).
In general: the surviving pairs satisfy $k_y/k_x < 3\log_3 2 - 1 \approx 0.893$.

**Scope and limits:** Theorem M eliminates the "$3^y \gg 2^x$" regime. The surviving
cases are exactly the two-comparable-S-units regime ($2^x \geq 3^y$) — which is
precisely where all known analytic tools (Baker, Bugeaud, Badziahin, Chabauty-Kim)
also fail. Theorem M alone does NOT resolve the conjecture.

**Open sub-questions:**
- (a) [CLOSED negatively, Session 15] The boundary case $A \approx 1$ was analyzed via the
  new valuation identity (Theorem N) and the size bound $A < (2^x+5)/3^{2j} \approx 3e^{D}$.
  $A$ is small only when $D \approx 0$, but the Theorem-5 lattice never approaches the
  boundary within $O(1)$ log-distance (closest surviving $D \approx 55$, $A \gtrsim 10^{24}$;
  Wolfram). Bounded-$A$ elimination cannot fire. See dead_ends.md and `knowledge/problem.md`
  Theorem N.
- (b) [CLOSED negatively, Session 16] Companion "from-above" argument for surviving
  $A < 3^j$ cases. The "Case II window" $A \in (e^D/7,\, e^D/3)$ was derived (width
  $\sim 0.19e^D$). This window is exponentially wide (for $k_x=1$, $k_y=0$: width
  $\approx 10^{3799}$). The 2-adic analysis imposes no new constraint (2-adic cube bijection);
  the 3-adic analysis is non-obstructive (3-adic bijection, Sessions 9–10); the norm-form
  constraint on $B$ (primes $p \equiv 2\pmod 3$ dividing $2^x+5$ to odd power go to $A$)
  is phantom-compatible. No contradiction. See log/20260626_200000.md.
- (c) Can Theorem M be combined with a quantitative lower bound on $z^3 - w^3$ to
  get a further restriction? (Still requires the unavailable $\kappa < 1.107$ bound.)

**Status update (Session 16):** Both sub-questions (a) and (b) are now closed negatively.
Sub-question (c) is blocked pending the open target. The Theorem-M direction has been
fully explored; no further active sub-questions remain.

### [LOW] Special role of $c = 5$ and the phantom

**New direction, Session 16. Cyclotomic characterization derived, Session 17.**

**Session 17 findings:**
- The general phantom family ($y = -3$, $x = 5$, rational $z$) is parametrized by
  $m \geq 1$: $c_m = 27m^3 + 9m^2 + m - 32$, $z_m = (9m+1)/3$.
  Gives $c_1 = 5$, $c_2 = 222$, $c_3 = 781$.
- The identity $2^5 + 5 = 37 = \Phi_3(10)/3$ (3rd cyclotomic polynomial) is the algebraic
  origin: $37 \mid \Phi_3(10) = 10^2 + 10 + 1 = 111$.
- $c = 5$ is the unique small positive constant with this phantom structure.
- New: $y \equiv 15 \pmod{18}$ for all Theorem-5 solutions; $3^y \equiv 11 \pmod{37}$;
  $z^3 \equiv 11 \pmod{37}$; 11 is a cubic residue mod 37. Non-contradictory.
- No actionable consequence found yet.

**Open question:** Does the specific arithmetic of $c = 5$ (the phantom structure) impose
any POSITIVE constraint that could be exploited? So far it has only been an OBSTRUCTION.

**Priority:** LOW. Speculative; cyclotomic characterization derived but no concrete attack.

### [~RETIRED, Session 17] Function-field analog / Mason-Stothers inspiration

**New direction, Session 16. Concretely analyzed and negatively resolved, Session 17.**

**Session 17 findings:**
- The equation *without* the constant, $P^x + Q^y = H^3$ over $\mathbb{C}[t]$, is fully
  resolved by Mason-Stothers: only finitely many non-constant solutions.
- The equation *with* $c \neq 0$, $P^x + Q^y + c = H^3$, is NOT resolved: $\text{rad}(P^x + c)$
  has full degree $x\deg P$ (squarefree polynomial), making the Mason-Stothers bound vacuous.
  This is the function-field analog of the phantom obstruction.
- **Conclusion:** The function-field version is provably as hard as the integer version
  (same structural obstruction). The function-field analog is NOT an easier proxy.
  Any proof must exploit specific arithmetic properties of $c = 5$.

See `knowledge/references/function_field_analog.md` for full analysis. **Retired.**

### [RETIRED in Session 21] Coupling-Height / Moving-Filtration framework (theory-building)

**Built in Session 20, RETIRED in Session 21 — both candidate lemmas resolved negatively.**

**Session 21 (Wolfram numerical test + equidistribution argument):**

- **Lemma A (Depth–Size Incompatibility, the crux) — REFUTED as circular.** The mechanism
  Lemma A needs is "the smallest integer of 3-adic depth $\ge d$ relative to $N$ is
  $\approx 3^{d-2}$, hence pushed off the size band $\sigma\approx1$." Wolfram verified this
  law holds for the **fixed** target $N=37$ ($x_0=5$): smallest $a$ of depth $d$ is
  $1,4,22,49,211,697,2155,\ldots\approx 3^{d-2}$, giving $\sigma_5(a)\approx0.95(d-2)$,
  growing linearly and leaving $\sigma=1$ for $d\ge4$; implied $c_0\in[0.33,3.5]$. **BUT**
  the decisive surrogate test — a constructed *moving-style* target
  $N=22^3+3^{10}\cdot7$ — has its smallest depth-10 integer equal to the *small* number 22.
  So the "$3^{d-2}$ law" is a property of the fixed target, **not** universal. For the actual
  moving target $N(x)=2^x+5$, "a small deep cube-root ($A$) exists" is *precisely the
  Kuromine question*; Lemma A is therefore circular and cannot be proved without
  re-importing an effective irrationality measure (the unavailable tool). At the first
  surviving pair ($k_x=k_y=1$: $x=332645$, $n=j+1=110880$) the genuine $A$ has
  $\log_2 A=x/3\approx110882 < (n-2)\log_2 3\approx175737$ — smaller than the fixed-target
  law allows, which is exactly the desired contradiction *if* the law transferred; it does
  not.

- **Lemma B′ (Lattice Rigidity) — REFUTED as false.** $D(k_x,k_y)=c_0+k_xP-k_yQ$ with
  $c_0=5\log2-110879\log3=-121809.57$, $P=332640\log2=230568.48$, $Q=110880\log3=121814.13$,
  $P/Q=3\log2/\log3=1.8927892607\ldots$ **irrational** (CF $[1;1,8,3,18,2,7,2,8,\ldots]$,
  infinite). By Weyl equidistribution $\{k_xP/Q+c_0/Q\}$ is dense in $[0,1)$, so
  $\inf_{k_x}D_{\ge0}=0$. Wolfram: minimal nonnegative $D$ falls $98.5\to0.537$ by
  $k_x=84180$ and keeps decreasing. **Session 15's "$D\approx55$ floor" was a finite-range
  ($k_x\le5000$) artifact.** The $D$-lattice does approach $D=0$ arbitrarily closely. This
  does **not** revive bounded-$A$ elimination: small $D$ at huge $k_x$ gives $O(1)$ genuine
  $A$ only with $j$ enormous, so the Theorem-N corollary (fixed small $a\Rightarrow$ bounded
  $v_3$, contradicting $j+1$) still blocks it — already known.

**Conclusion:** Framework retired. Diagnostic residue: the unique non-degenerate handle
(3-adic depth $j+1$ vs phantom depth 0) is real but **non-transferable** to an archimedean
size constraint without an effective irrationality measure — a third independent
confirmation (after the metric face S15, the analytic face S3/S10/S11) of the P1–P4
conjunction barrier. Moved to `knowledge/dead_ends.md`. Full detail in
`log/20260627_120000.md`. **DO NOT REOPEN** without a new external transfer inequality.

### [SUPERSEDED] Coupling-Height / Moving-Filtration framework — original Session-20 entry

**New framework, Session 20 (theory-creator mode).** Built from the obstruction diagnosis
(the wall is a four-fold structural degeneracy P1–P4 with one non-degenerate handle: 3-adic
depth $v_3(2^x+5-A^3)=j+1\to\infty$ vs the phantom's depth 0). The framework is a
**non-additive arithmetic height coupling the archimedean place and the place 3**, indexed
by the Theorem-5 progression. Core objects (full definitions in `log/20260627_070633.md` §3):

- **Principal 3-adic cube root** $\beta(x)\in\mathbb Z_3$ of $N(x)=2^x+5$ ($\beta\equiv1\bmod3$).
- **Moving 3-adic depth** $\delta_x(a)=v_3(2^x+5-a^3)$ and the **depth filtration**
  $\mathcal F=\{F_n(x)\}$. Genuine solution: $A\in F_{j+1}\setminus F_{j+2}$ (Theorem N).
- **Size class** $\sigma_x(a)=3\log a/(x\log2)$; genuine $\sigma_x(A)\to1$.
- **Coupling Height** $\widehat H_x(a)=\sigma_x(a)\cdot(1+\delta_x(a))\cdot\mathbf1[\text{Eisenstein gate on }B]$
  — *product* across $\{\infty,3\}$, designed to vanish on the phantom (depth 0) and be
  forced large on genuine solutions (depth $j+1$).
- **Progression-rigidity** $\rho=|D|$, $D=x\log2-(2j+1)\log3$ (the two-S-units log-distance).

**Candidate lemmas (stated, NOT proven) — BOTH refuted in Session 21 (see RETIRED entry above):**
- **Lemma A (Depth–Size Incompatibility) — the crux.** $\delta_x(a)\ge j+1 \Rightarrow
  |\sigma_x(a)-1|\ge c_0(j+1)/x$. Refuted as circular (Session 21).
- **Lemma B/B′ (Lattice Rigidity).** Relativized form claimed minimal nonnegative $D$ over
  the $D$-lattice bounded below. Refuted as false (Session 21; $\inf D_{\ge0}=0$).

### [RETIRED in Session 19] Cyclotomic phantom family

**New direction, Session 17. Concretely analyzed and RETIRED in Session 19.**

The general $y = -3$ phantom family for $2^x + 3^y + c = z^3$ is parametrized by:
$$c_m = 27m^3 + 9m^2 + m - 32, \quad z_m = \frac{9m+1}{3}, \quad m \geq 1.$$

First values: $c_1 = 5$ ($z_1 = 10/3$), $c_2 = 222$ ($z_2 = 19/3$), $c_3 = 781$ ($z_3 = 28/3$).

**Session 19 deep analysis (analytic, Wolfram unavailable), result negative:**

1. **Parity partition (Theorem O):** $c_m$ odd iff $m$ odd. Odd-$m$ equations have $z$ even;
   even-$m$ equations have $z$ odd. New structural fact, non-actionable.

2. **Uniqueness of $c_1=5$ confirmed:** $2^5 + c_1 = 37$ is the UNIQUE case where
   $2^5 + c_m$ is prime $\equiv 1 \pmod 3$. For $m \geq 2$, $2^5 + c_m$ is composite with
   extraneous small-prime factors ($2$ for $m=2$, $3$ for $m=3$, etc.). $c_1 = 5$ is the
   EASIEST case in the phantom family.

3. **Forced-factor analogy:** 37's role for $c_1$ is played by 127 ($\mathrm{ord}_{127}(2)=7$)
   for $c_2$. But $37 \mid c_2$ (since $222 = 6 \cdot 37$), so $37 \nmid 2^x + c_2$ for any
   $x$ — the "forced $37 \| B$" fact is absent for $c_2$.

4. **Soft obstruction universal:** Every equation $2^x + 3^y + c_m = z^3$ is locally solvable
   at every $p \neq 3$ (phantom is a global rational cube). No modular method works for any $c_m$.

5. **No new approach:** Studying $c_m$ for $m \geq 2$ does not yield a technique applicable
   to $c_1 = 5$. The family comparison is a closed exercise.

**Conclusion:** The direction produces structural insight (parity partition, uniqueness of $c_1$'s
prime pivot) but no actionable new approach. Retired. Details in `log/20260627_000000.md`.

### [LOW] Numerical search with Theorem 5 filtering

Verify computationally that no solutions exist for small $k$ (say $k \leq 5$). Not mathematically deep but can confirm the conjecture computationally and potentially reveal patterns in $2^x + 5 \pmod p$ for primes $p \equiv 1 \pmod 3$.

**Session 4:** Exhaustive search over $0\le x,y\le 2000$ (Python, 14-prime cubic-residue
sieve) confirms only the two known solutions; sieve survivors were
$(1,0),(5,3),(1445,597),(1445,1677)$ with only the first two being cubes. The two near-miss
survivors are non-cubes and outside the Theorem-5 class. The full Theorem-5 floor
($x=332645$) remains far beyond brute force, so direct numerical refutation of the conjecture
is infeasible — keep at LOW.

### [RETIRED in Session 5] Skolem's method / Bertók-Hajdu algorithm

**Session 5 assessment:** Inapplicable by the same phantom obstruction. The Bertók-Hajdu/Miyazaki infinite-family approach (arXiv:2503.00843, 2508.17601) requires the equation to be *locally unsolvable* somewhere — the algorithm finds a modulus $N$ with no solution mod $N$ and concludes no integer solution exists. The Kuromine equation is locally solvable at every prime (proven in Session 2: the phantom $(10/3)^3$ is a global rational cube). Therefore the algorithm can never find a blocking modulus. The search would run indefinitely without result. Moved to dead ends.

### [RETIRED in Session 13] Chabauty-Kim / algebraic geometry methods

**Added and immediately retired in Session 13.** Session 12 suggested exploring Galois
representations and algebraic geometry approaches. The Chabauty-Kim framework (Affine
Chabauty I/II by Leonhardt-Lüdtke; Modular Chabauty by Zehavi; Cubic Chabauty by
Balakrishnan-Bianchi-Dogra) is the primary modern algebraic-geometry tool for integral
points. Four papers were assessed systematically:

- **arXiv:2511.15949** (Affine Chabauty I, Nov 2025): S-integral points on affine curves
  via generalized Jacobian. NOT APPLICABLE: Kuromine's $x, y$ are exponents, not
  algebraic coordinates; S-integrality cannot encode "$u = 2^x$".
- **arXiv:2602.05643** (Affine Chabauty II, Feb 2026): Algorithm for the above.
  Same barrier.
- **arXiv:2505.12947** (Modular Chabauty, May 2025): S-integral points on curves with
  elliptic fibrations. NOT APPLICABLE: provides per-fixed-$N$ Thue-Mahler solvers, but
  $N_{k_x} \approx e^{230572}$ is astronomically large; no information across the family.
- **arXiv:2604.20662** (Cubic Chabauty, Apr 2026): depth-3 Kim set for fixed elliptic
  curves of rank ≤ 2. NOT APPLICABLE: Kuromine gives a varying family of Mordell curves.

**Fifth categorical barrier (new, Session 13):** Chabauty-Kim in all forms is categorically
inapplicable to exponential Diophantine equations where two or more variables appear as
exponents of fixed bases. The Kuromine equation's two-exponential structure ($x$ and $y$
are both exponents) lies outside the algebraic category. This is a categorical mismatch,
not a quantitative gap; no improvement in depth, rank condition, or computational reach
can change this.

See log/20260626_120000.md for full analysis.

### [LOW] arXiv survey of exponential Diophantine equations

**Partially done in Session 1.** Found literature on Baker's method, S-unit equations, and Thue-Mahler equations. Session 5 adds: Miyazaki (2503.00843) solves infinite families of 4-term purely exponential equations using Baker+p-adic Baker+Skolem, but all rely on local non-solvability. The Kuromine equation's phantom blocks this route.

**Session 6 update:** Surveyed 2025-2026 arXiv. Found four potentially relevant papers; all either inapplicable or conditional on ABC:
- arXiv:2510.11753 (Cai 2025): handles a^x+b=c^y (one exponential unknown). Not applicable.
- arXiv:2601.11376 (Müller–Taktikos 2026): Effective Roth/Ridout for cube roots, conditional on ABC. Not unconditional; would still face the two-S-units regime.
- arXiv:2602.19061 (Müller 2026): Gain bounds for diagonal superelliptic equations under strong ABC. Conditional and structurally mismatched.
- arXiv:2506.20909 (Jun 2025): Reduces exponential Diophantine to ordinary via Lucas sequences; requires a structure Kuromine (with additive constant 5) does not have.
- **No new unconditional method for the two-comparable-S-units regime found.** The κ_real ≈ 0.62 barrier (Session 3) remains open.

**Session 10 update:** Assessed the two newest 2026 Bugeaud papers, which are the first
to directly bound the *difference* between a perfect power and an integral S-unit (the
Kuromine shape):
- arXiv:2604.27490 (Bugeaud, Apr 2026): effective lower bound for |z^d − q1^a1···qt^at|
  and its greatest prime factor, → ∞ with z^d, for z coprime to the q_i, d ≥ 2.
- arXiv:2503.22084 (Bugeaud, Mar 2025): the d = 2 (squares) case; greatest prime factor
  of |x² − S-unit| → ∞.
- **Assessment: NOT APPLICABLE.** Option (1) z³−2^x = 3^y+5 fails the hypothesis (z is
  even, gcd(z,2)≠1). Option (2) z³−3^y = 2^x+5 satisfies it (x odd ⇒ z coprime to 3) but
  gives no contradiction: |z³−3^y| = 2^x+5 ≈ z^{1.89} (log 230572 = 0.631·log z³), so a
  contradiction needs an *effective* exponent κ < 1.107, whereas Baker-type bounds (which
  Bugeaud uses) give κ just below d=3. The 0.631 figure is exactly the Session-3 κ_real
  barrier, now seen from the cube-vs-3^y side. Bugeaud's "→ ∞ with z^d" is trivially met
  by 2^x+5 → ∞.
- Holonomy bounds (2510.04156) re-checked: still effective irrationality measure > 2 for
  2^{1/3}, far above κ < 1.107. No new unconditional tool in the two-S-units regime.

**Session 12 update:** Assessed Zhou's IUT effective abc (arXiv:2503.14510, Mar 2025) and
did a June 2026 arXiv sweep. Zhou's result (log|abc| ≤ 3 log rad + 8√(log|abc|·log log|abc|))
is NOT APPLICABLE: the Kuromine triple has quality ≈ 0.888 < 1, so the Zhou bound is
trivially satisfied — it upper-bounds quality, but Kuromine already has quality well below 1.
June 2026 arXiv sweep: five papers (2605.31114, 2605.28449, 2605.18348, 2606.00466,
2606.02244) — none applicable (modular/Baker/recurrence methods; no variable z³; no
{2,3}-S-unit structure). Calegari–Dimitrov–Tang (2510.04156) has no published follow-up
improving the effective irrationality measure for 2^{1/3} below ~1.1. Four independent
confirmations (S3/S10/S11/S12) of the two-comparable-S-units barrier. **The open target
is unchanged.**

**Session 13 update:** Assessed four Chabauty-Kim papers (2511.15949, 2602.05643, 2505.12947,
2604.20662) — all NOT APPLICABLE for the categorical reason that Chabauty-Kim methods apply
to algebraic curves, not exponential Diophantine equations (fifth categorical barrier,
new in Session 13). June/July 2026 arXiv sweep: no new applicable paper. Holonomy-bounds
school (2510.04156) has no new result. Identified new [LOW] direction: gpf($z^3 - 5$)
reformulation (see separate direction entry). **The open target is unchanged.**

**Session 11 update:** Assessed two previously-unassessed 2024–2026 papers, the closest to
the exact quantified target found so far. Both NOT APPLICABLE:
- arXiv:2509.01105 (Badziahin, "Distance between cubics and rationals", Sep 2025; Results
  in Math. 2026): bounds |ξ − p/q| for **cubic irrationals** ξ via cubic root-separation;
  nontrivial only for good approximations 2 ≤ v ≤ 3, and **all results conditional on
  abc/Hall** (under abc: interior of D_{3,1} is u > 10 − 3v). Kuromine cannot enter that
  regime: "cube − square" needs y even but y is always odd in the family (y ≡ 3 mod 6);
  "cube − cube" degenerates (3^{y/3} is a rational integer, not a cubic irrational);
  the 2^{2/3}-Thue casting realizes v_real ≈ 0.62 at the floor (k_y=0) and **negative** for
  all k_y ≥ 1 (the approximation diverges). All far below v ≥ 2. And abc gives no leverage
  anyway — Kuromine's abc-quality ≈ 0.888 < 1 (Session 8).
- Bajpai, "Effective and Explicit S-Unit Equations with Many Terms" (UBC thesis;
  Bajpai–Bennett, Acta Arith. 214 (2024)): effective many-term S-unit equations, but
  **method = Baker's linear forms in logarithms** (retired Session 5: v_p = 0, no bound
  violable) and requires all terms to be S-units, which z³ and the constant 5 are not
  (= the Session-8 obstruction for arXiv:2505.19141). NOT APPLICABLE.

**Session 8 update:** Assessed two additional 2026 papers:
- arXiv:2505.19141 (Dong-Shafrir / Karimov et al., 2025): Decidability of linear-exponential Diophantine equations over two primes {p,q}. These are equations Σ a_i · p^{x_i} · q^{y_i} = 0. NOT APPLICABLE: Kuromine has z^3 as a term, and z is not an S-unit (not of the form 2^a·3^b). The decidability result requires all terms to be S-units in {p,q}; z^3 falls outside this class.
- arXiv:2604.18991 (Miyazaki-Scott-Styer, April 2026): Handles a^x + b^y = c^z (purely exponential, all three bases fixed). NOT APPLICABLE: Kuromine has z^3 with z as the variable, not c^z with c fixed.
- ABC conjecture assessment (Session 8): No contradiction from ABC. The radical grows as rad(2^x·(3^y+5)·z^3) ~ 2·(3^y/8)·z, giving quality q = log(z^3)/log(rad) ≈ 1/1.126 ≈ 0.888 < 1. ABC is satisfied (not violated) for all Kuromine solutions.

**Session 21 update:** WebSearch (June 2026) for unconditional effective κ<1.107 bounds and CDT follow-ups. Negative (tenth confirmation of the two-comparable-S-units barrier). Calegari–Dimitrov–Tang (arXiv:2510.04156) remains the frontier: gives effective irrationality measures for high-order roots and algorithmic resolution of two-variable S-unit / Thue–Mahler / superelliptic equations, but the effective measure for 2^{1/3} is still > 2 ≫ 1.107, and per-equation resolution gives no uniformity across the infinite Theorem-5 family. No 2026 follow-up below the ~1.1 threshold.

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.

---

## History of Changes

- **2026-06-27 (Session 27):** Negative arXiv watch (fifteenth confirmation) + SPECIAL
  DIRECTIVE theory-building. **Watch finding:** Bugeaud **arXiv:2604.27490** (Apr 2026, "On the
  difference between perfect powers and integral S-units") gives effective lower bounds for
  $|z^d - \text{S-unit}|$ that "**tend to infinity with $z^d$**" — the *trivially-met* form
  (Kuromine gap $=2^x+5\to\infty$ already), NOT a power-saving $\kappa>1$. Wolfram-re-verified
  $E\to2/3^+$ at the near-boundary surviving pair ($k_x=84180$, $D=0.53667$). **New direction
  added:** the **Cubic-Transversality / Dial–Lattice framework** [LOW], a genuinely
  *archimedean* framework distinct from the two retired 3-adic-only ones. Dial form
  $W^3=27\cdot2^x+3^{y+3}+135$ ($W=3z$); **Lemma D PROVED** (phantom's denominator-3 escape
  confined to $y<0$, so the survival sheet is phantom-free — first such formulation);
  **Lemma C UNPROVEN crux** (effective resonance-exclusion of the dial orbit from $3\mathbb Z$;
  naive gap bound vacuous; only route is effective equidistribution, where the barrier likely
  re-surfaces). No direction retired this session. New reference
  `knowledge/references/cubic_transversality_framework.md`.

- **2026-06-26 (Session 26):** WATCH-phase **target-audit pass** (Wolfram). No direction
  retired/elevated/added; no theory-building (per standing DO-NOT-ATTEMPT). Independently
  re-derived the exponent threshold on which the entire reduction rests and **corrected a
  long-standing imprecise framing** of the open target. Wolfram-verified: for surviving
  Theorem-5 pairs the realized exponent of the gap $|z^3-3^y| = 2^x+5$ **measured against
  $z^3$** is $E = \log(2^x+5)/\log(z^3) \in (2/3, 1)$, **strictly below 1 everywhere** —
  it $\to 2/3$ at the survival boundary (where $2^x \approx 3^{2j+1} \approx z^3$, so
  $3^y \approx z^3$, log-ratio $3^y/z^2 = 1.5$, NOT $3^y\approx z^2$) and $\to 1^-$ at
  $k_y=0$ (equal to $1 - e^{-47854}/\log z^3$ for $k_x=1$). **Consequence:** the
  necessary-and-sufficient open target is *any* fixed **effective** $\kappa>1$ in
  $|z^3-3^y|>C(z^3)^\kappa$ (the recorded $\kappa<1.107 = 3-3\log_3 2 = 3\log_3(3/2)$ is a
  *sufficient margin*, not a necessary ceiling; $\kappa=1$ exactly is just barely
  insufficient). The "$3^y\approx z^2$" regime label in older logs is imprecise (the $z^2$
  arises only in the auxiliary $2^{2/3}$-Thue casting, not the direct gap). The substantive
  impasse is unchanged — Baker gives $v_p(\Lambda_p)=0$ so no positive effective $\kappa$
  exists. Verified the three frame-constants again to 30 digits ($3-3\log_3 2 = 1.107210739\ldots
  = 3\log_3(3/2)$; $2\log3/(3\log2)=1.056641667\ldots$; $3\log2/\log3=1.892789261\ldots$).
  Updated `current_focus.md` (corrected target framing) and this file. Created
  `log/20260626_150517.md`. No change to `knowledge/problem.md` or `dead_ends.md`
  (a framing correction, not a new theorem or dead end).

- **2026-06-26 (Session 25):** WATCH-phase, executed as a **Wolfram-enabled
  verification-and-consolidation pass** (MCP was available this session, unlike Sessions 20
  and 24 which left numerical verifications pending). **Resolved all pending Wolfram anchors
  — first direct machine verification:** $v_3(2^{332640}-1)=4$ exactly (so $v_3(\log_3 g)=4$);
  Theorem I exact ($A\bmod81 = 49/22/76$ for $k_x\equiv0/1/2\pmod3$); Theorem L exact
  ($B\bmod81 = 52/79/25$); tangent-speed valuation $v_3(\tau)=v_3((A^3-5)L/(3A^2))=3$ (Session
  24 anchor); $\operatorname{ord}_{3^n}(2)=2\cdot3^{n-1}$; and the three frame-constants to 15
  digits ($3-3\log_32=1.10721\ldots$, $2\log3/(3\log2)=1.05664\ldots$,
  $3\log2/\log3=1.89279\ldots$). The numerical record is now self-consistent and
  machine-checked. **New diagnostic sharpening (kept, non-actionable):** the open target
  $\kappa<1.107$ for $|z^3-3^y|>C(z^3)^\kappa$ lies **below the Dirichlet floor $\mu\ge2$**, so
  it is categorically NOT an irrationality-measure statement — improving the effective measure
  for $2^{1/3}$ (the CDT-school program) can never reach it, regardless of sharpness, because
  measures only constrain *good* approximations (exponent $\ge2$). Wolfram (50-digit)
  reconfirmed the realized approximation exponent of $z/W$ to $2^{2/3}$ is **negative** for all
  $k_y\ge1$ ($-0.585,-1.377,-2.170$): $z/W$ is an *anti*-approximation. The target is a
  **sub-Dirichlet gap/separation inequality**, outside the measure paradigm. **arXiv watch
  negative (fourteenth confirmation):** CDT (2510.04156) measure for $2^{1/3}$ still $\gg2$
  (explicit bound large since $a=2$ is far from 1); KLNOW/Dong–Shafrir (2505.19141) decidability
  still only $\le2$-prime bases, degree-$\le1$ free terms. No direction retired/elevated/added;
  WATCH remains sole active priority. Created `log/20260626_140741.md`; updated
  `current_focus.md`.

- **2026-06-26 (Session 24):** WATCH-phase reconnaissance (thirteenth arXiv watch, negative)
  plus mandatory theory-building attempt 2 (Special Directive). **Built and immediately
  retired the Differential Progression Framework:** studied the 3-adic analytic curve
  $\mathcal{K}: A^3 = 32\exp_3(kL)+5$ over $\mathbb{Z}_3$, computed the tangent speed
  $\tau(k) = (A^3-5)L/(3A^2)$ with $v_3(\tau)=3$ analytically (Wolfram verification
  pending for 3-adic digit precision), and showed that the resulting inter-term constraints
  ($A(k+1)-A(k) \equiv \tau(k) \pmod{3^6}$, $v_3(\Delta A)=3$) are EQUIVALENT to the
  existing Theorem-J lifting law (Sessions 6–10). The 3-adic Taylor coefficients of
  $A(k_x)$ at any integer point ARE the Theorem-J data; the differential framework adds no
  information beyond the complete 3-adic portrait. **Fourth independent confirmation that
  3-adic data alone cannot produce an archimedean size contradiction.** Added
  Differential Progression Framework to `knowledge/dead_ends.md`. No direction priorities
  changed; WATCH remains the sole active priority. Created `log/20260626_120100.md`.

- **2026-06-26 (Session 23):** WATCH-phase reconnaissance. No direction retired or elevated; no new direction added. (i) **Independently re-verified the soft-obstruction** that underpins every phantom-blocked dead-end, catching and correcting a self-introduced mis-test in the process: the phantom RHS is $2^5+3^{-3}+5 = 1000/27 = (10/3)^3$ (NOT $37/27$); Wolfram confirms $1000/27$ is a cube residue mod **195/195** primes $p\equiv1\pmod3$ below $\approx2740$ (the mistaken $37/27$ gave only 63/195). This re-confirms that along the Theorem-5 phantom residues the equation reduces to the global rational cube $1000/27 \pmod p$ for every $p\neq3$ — so pure congruence sieving with any $\gcd(m,3)=1$ modulus is provably inert, exactly as recorded. (ii) **Sharpened the $D$-lattice equidistribution record** (Lemma B′ remains false, non-actionably): running minimum of nonnegative $D=c_0+k_xP-k_yQ$ ($P/Q=3\log2/\log3$ irrational) descends from Session 21's $0.5367$ ($k_x=84180$) to **$0.1446$ at $k_x=243595$** (Wolfram, $k_x\le1.5\times10^6$), confirming $\inf D_{\ge0}=0$; the implied genuine $A\approx3.47$ there is still blocked by the Theorem-N corollary ($j\approx1.35\times10^{10}$, fixed small $A$ has bounded $v_3$). (iii) **arXiv watch negative (twelfth confirmation):** CDT holonomy school active but on L-value irrationality ($L(2,\chi_{-3})$, $\zeta_2(5)$), no effective measure for $2^{1/3}$ below $\sim1.1$; KLNOW/Dong–Shafrir decidability settled for two primes, **explicitly open for $k\ge3$ primes**, no extension to a free higher-degree term. Created `log/20260626_110746.md`; updated `current_focus.md`. WATCH remains the sole active priority.
- **2026-06-26 (Session 22):** WATCH-phase reconnaissance; focused assessment of the 2025–2026 **decidability frontier for linear-exponential Diophantine systems** relative to Kuromine. Found and analyzed **KLNOW (Karimov–Luca–Nieuwveld–Ouaknine–Worrell, 2025)** — decidability of linear-exponential Diophantine systems **over two primes** (free variables at degree $\le 1$ outside exponents; proof **uses Baker's theorem**) — and **Dong–Shafrir (arXiv:2505.19141, STOC 2026)**, which reduces module S-unit equations to such systems (decidable for base $T$ with $\le 2$ prime divisors; arbitrary $T$ = "major breakthrough in number theory"). **Sharp new placement:** Kuromine's exponential skeleton $2^x+3^y+5$ is over **exactly two primes** ($T=6$) — *inside* the prime-count frontier — but the term $z^3$ is **degree 3 in the free variable** ($z=3^j+A\Rightarrow z^3=3^{3j}+3^{1+2j}A+3^{1+j}A^2+A^3$, Wolfram; free cube $A^3$, and $z$ not $\{2,3\}$-smooth in general so not re-encodable as a monomial), placing Kuromine **two polynomial degrees above** the degree-1 decidable class. The degree obstruction = the already-retired per-fixed-variable Thue/Mordell wall (finite per fixed $x$, no family uniformity), and KLNOW's engine (Baker) is itself dead here (Session 5). This sharpens the Session-8 note that flagged 2505.19141 as "not applicable" by pinning the *exact* reason (degree, not prime-count) and folding in the new KLNOW decidability. **Eleventh independent confirmation** of the barrier. Created `knowledge/references/linear_exponential_decidability.md`; added the dead-end entry to `knowledge/dead_ends.md`; updated `current_focus.md`. No new direction elevated; WATCH remains sole active priority, with an added watch item: any extension of the linear-exponential decidability class to a single free higher-degree (quadratic/cubic) term.
- **2026-06-27 (Session 21):** Executed the Session-20 next-suggestions: numerically tested (Wolfram) the two candidate lemmas of the **Coupling-Height / Moving-Filtration framework** and **RETIRED the framework** (both lemmas resolved negatively). **Lemma A (Depth–Size Incompatibility, the crux) REFUTED as circular:** the "smallest integer of 3-adic depth $\ge d$ is $\approx 3^{d-2}$, hence off the size band" law (verified for the fixed target $N=37$: smallest $a$ of depth $d$ runs $1,4,22,49,211,697,2155,\ldots$, $\sigma_5\approx0.95(d-2)$, implied $c_0\in[0.33,3.5]$) is a property of the *fixed* target only — a constructed moving-style surrogate $N=22^3+3^{10}\cdot7$ has its smallest depth-10 integer equal to the small number 22. For the real moving target $2^x+5$, "a small deep cube-root exists" *is* the Kuromine question, so Lemma A cannot be proved without an effective irrationality measure (unavailable). **Lemma B′ (Lattice Rigidity) REFUTED as false:** $D=c_0+k_xP-k_yQ$ with $P/Q=3\log2/\log3=1.89278926\ldots$ irrational (CF infinite) $\Rightarrow$ Weyl equidistribution $\Rightarrow\inf D_{\ge0}=0$; Wolfram running-min of nonnegative $D$ falls $98.5\to0.537$ by $k_x=84180$ and keeps decreasing — Session 15's "$D\approx55$ floor" was a finite-range ($k_x\le5000$) artifact; the $D$-lattice does approach $D=0$ (does NOT revive bounded-$A$ elimination — Theorem-N corollary still blocks). arXiv watch negative (tenth confirmation; CDT 2510.04156 still frontier, measure for $2^{1/3}$ $>2$, no $\kappa<1.107$, no family uniformity). Net: the last constructed framework is exhausted; the depth handle is real but **non-transferable** without an effective irrationality measure. Research returns to pure WATCH. Moved Coupling-Height direction to RETIRED; added it to `knowledge/dead_ends.md`; created `log/20260627_120000.md`; updated `current_focus.md`.
- **2026-06-25 (Session 1):** Added [HIGH] Factorization approach. Added [MEDIUM] Thue-Mahler equation approach. Lowered Baker's method assessment from [MEDIUM] to [MEDIUM-LOW] but kept at [MEDIUM] pending p-adic Baker investigation. Elevated $p$-adic direction to [HIGH] (tied). Noted Session 1 discoveries.
- **2026-06-25 (Session 2):** Downgraded standalone $p$-adic elimination from [HIGH] to [LOW/~RETIRED] after *proving* (not just observing) that local methods cannot obstruct the equation: the phantom is a global rational cube $(10/3)^3$, so every local condition is satisfiable. Added new [HIGH] direction "Effective Diophantine approximation to $2^{1/3}$" as the realistic global path. Completed the 2-adic structure analysis ($z\equiv6\pmod{32}$, $v_2(3^y+5)=3$). See `knowledge/references/two_adic_structure.md`.
- **2026-06-25 (Session 3):** RETIRED "Effective Diophantine approximation to $2^{1/3}$" (was [HIGH]) with a proof that it is quantitatively dead: realized exponent $\kappa\approx0.62\ll\mu$, and the Thue value $3^y+5$ is too large by $\sim e^{138909}$ — root cause is the two-comparable-dominant-S-units regime ($3^y\approx z^2$). See `knowledge/references/irrationality_measure_obstruction.md`. Added Session-3 progress to the Factorization [HIGH] direction (reduced equation $2^x+5=A(A^2+3^{j+1}A+3^{2j+1})$, both real solutions have $A=z-3^{y/3}=1$, Eisenstein identity $4B-3w^2=(2z+w)^2$). Elevated primitive-divisor (Zsygmondy/BHV) direction to [MEDIUM-HIGH] as the best remaining non-size lead, since all size methods are now shown too weak.
- **2026-06-25 (Session 4):** RETIRED the [MEDIUM-HIGH] primitive-divisor/growth direction: its congruence form is killed by the soft obstruction (showed $A\equiv3$, $B\equiv37/3\pmod p$ for all $p\ne3$, matching the phantom; $x\bmod3$, $y\bmod6$ constant over the family), and its growth form has no Lucas/Lehmer object ($B$ not an $a^n-b^n$ sequence). RETIRED the modular/Frey-curve method as structurally inapplicable (no varying prime exponent) — created `knowledge/references/modular_method.md`. Downgraded the Factorization [HIGH] direction toward MEDIUM: closed sub-questions (b) and (c) negatively ($A$ is provably $\sim2^{x/3}$, never 1), leaving only the global/size sub-question (a) for which no adequate tool exists. Added Session-4 progress note to `knowledge/references/factorization_approach.md`. Extended numerical verification to $x,y\le2000$ (only the two known solutions). Both retirements moved to `knowledge/dead_ends.md`.
- **2026-06-25 (Session 5):** RETIRED Baker's method (all variants, including Yu's p-adic Baker): p-adic linear forms have $v_p = 0$ for $p \in \{2,3\}$ — p-adic units — so no Baker upper bound can ever be violated. RETIRED Skolem/Bertók-Hajdu: inapplicable because the phantom makes the equation locally solvable everywhere. Added A=1 sub-theorem proof (exactly $(1,0,2)$ and $(5,3,4)$ satisfy $A=1$). Documented the algebraic origin of the phantom: $c=5$ is the smallest positive integer for which $865+27c$ is a perfect cube. Checked $z\bmod37$ structure: three branches cycle over Theorem-5 family, no contradiction. Added Session-5 history entry, retired Baker and Skolem to dead ends.
- **2026-06-25 (Session 6):** No new directions retired; no new directions elevated. Literature survey of 2025-2026 arXiv found no unconditional new tool for the two-S-units regime. Investigated descent-on-A: found A ≡ 4 (mod 9), A ≡ 22 (mod 27), A ≡ 27 (mod 32) [NOTE: the last is only for k_y even; corrected in Session 7], j ≡ 7 (mod 8) as new refined constraints for the Theorem-5 family; these are genuine addenda but do not yield a contradiction. Confirmed phantom-free neighboring constants c=4,6,7,... have no rational phantom and are structurally simpler, but this doesn't help resolve c=5. Updated arXiv survey [LOW] direction with Session 6 findings. Updated current_focus.md.
- **2026-06-25 (Session 7):** No new directions retired; no new directions elevated. Corrected Session 2 result: $z \equiv 6 \pmod{32}$ is not universal; the correct universal statement is $z \equiv 6 \pmod{16}$ (the full family splits into $z \equiv 6$ and $z \equiv 22 \pmod{32}$ by $k_y$ parity). Derived new universal constraints (Theorems E–H): $y \equiv 13 \pmod{16}$, $j \equiv 3 \pmod{4}$, $z \equiv 6 \pmod{16}$, $A \equiv 11 \pmod{16}$. Corrected Session 6 Theorem B: the correct universal form is $A \equiv 11 \pmod{16}$ (not $27 \pmod{32}$). Derived $B \equiv 79 \pmod{432}$ as a new universal constraint. Updated CRT: $A \equiv 427 \pmod{432}$, $B \equiv 79 \pmod{432}$, consistent with $A \cdot B \equiv 37 \pmod{432}$. Noted that $A_{\mathrm{phantom}} = 3 \equiv 3 \pmod{16}$ while $A_{\mathrm{real}} \equiv 11 \pmod{16}$ — genuine 2-adic separation but not a contradiction. arXiv 2026 search: one new paper (2603.29831, cubic reciprocity) found; not applicable. Updated current_focus.md.
- **2026-06-25 (Session 9):** No new directions retired; no new directions elevated. Completed the 3-adic portrait of the integer factor B (Theorem L), mirroring Theorems I/J for A: B ≡ 25 (mod 27) universal; B mod 81 indexed by k_x mod 3 (52/79/25 for k_x ≡ 0/1/2); B mod 3^{n-1} a function of k_x mod 3^{n-4} for n ≥ 5, inherited from Theorem J via B ≡ (2^x+5)·A^{-1} (A a 3-adic unit). Corrected Session 8 suggestion #1: B mod 729 needs k_x mod 27 (not mod 9); full 27-branch (A,B) mod 729 table computed and verified (A·B ≡ 2^x+5 mod 729 in every row). B is a 3-adic unit (v_3(B)=0), separating it from the phantom (B_phantom=37/3, v_3=-1) but non-actionably. Formalized Theorems I, J, K, L into knowledge/problem.md and created knowledge/references/adic_structure_extended.md (full 2-adic + 3-adic portraits of A and B side by side). The local portrait of a Theorem-5 solution is now complete for both coprime factors at arbitrary p-adic depth; no contradiction; fundamental barrier unchanged. Updated current_focus.md.

- **2026-06-25 (Session 8):** No new directions retired; no new directions elevated. Completed the (k_x, k_y) indexing of all A-congruence branches. Theorem I: the three branches of A mod 81 are indexed by k_x mod 3 (k_x≡0 → A≡49, k_x≡1 → A≡22, k_x≡2 → A≡76 mod 81). Theorem J: A mod 3^{n-1} uniquely determined by k_x mod 3^{n-4} for n≥5 (gcd(332640, ord_{3^n}(2))=54 for all n≥5). Theorem K: full 12-branch A mod 20736=lcm(81,256) indexed by (k_x mod 3, k_y mod 4), all 12 values listed. Corrected and completed Session 6's three-branch CRT to a six-branch CRT mod 2592 indexed by (k_x mod 3, k_y mod 2). Assessed ABC conjecture: no contradiction (quality exponent q≈0.888<1, ABC is never violated). Assessed two new 2026 arXiv papers: arXiv:2505.19141 (S-unit decidability, two primes) and arXiv:2604.18991 (a^x+b^y=c^z); both NOT APPLICABLE to Kuromine. Noted that the 3-adic expansion of A is determined digit-by-digit by k_x, confirming it is a bijection Z_3→Z_3 (no contradiction). Updated current_focus.md.

- **2026-06-25 (Session 11):** No new directions retired (all relevant ones already retired); no new directions elevated. Literature watch on a previously-unassessed, maximally on-target paper — Badziahin's "Distance between cubics and rationals" (arXiv:2509.01105 / Results in Math. 2026), which studies cubic-irrational-vs-rational separation, the geometry directly underlying |z³ − 3^y|. NOT APPLICABLE: its bounds are conditional on abc/Hall and nontrivial only for good approximations 2 ≤ v ≤ 3; Kuromine cannot be cast there ("cube − square" needs y even but y is always odd in the family; "cube − cube" degenerates to a rational nearby integer = the old factorization; the 2^{2/3}-Thue casting realizes v_real ≈ 0.62 at the floor k_y=0 and **negative** for all k_y ≥ 1 — the approximation *diverges*). This sharpens Session 3: κ_real is 0.62 only at the family floor and goes negative (−1.75, −4.13, −6.51, …) for every k_y ≥ 1, so almost the whole family has z/W not approximating 2^{2/3} at all (Wolfram). Also assessed Bajpai's effective many-term S-unit thesis (Bajpai–Bennett, Acta Arith. 214 (2024)): NOT APPLICABLE — Baker-based (retired Session 5) and requires S-unit-controlled terms, which z³ and the constant 5 are not (= Session 8 obstruction). Three independent literature lines (irrationality measures S3, Bugeaud S10, Badziahin S11) now confirm the two-comparable-S-units barrier structurally. Added a Session-11 strengthening note to the RETIRED 2^{1/3} entry and a Session-11 assessment to the arXiv-survey [LOW] direction. Updated current_focus.md.
- **2026-06-25 (Session 10):** No new directions retired; no new directions elevated. Literature watch: assessed the two newest Bugeaud "perfect-power minus integral S-unit" papers (arXiv:2604.27490, Apr 2026; arXiv:2503.22084, Mar 2025), the first 2026 results to bound exactly the Kuromine-shaped difference. NOT APPLICABLE: Option (1) z³−2^x = 3^y+5 fails the coprimality hypothesis (z even); Option (2) z³−3^y = 2^x+5 satisfies it (x odd ⇒ z coprime to 3) but gives no contradiction because |z³−3^y| = 2^x+5 ≈ z^{1.89} (log 230572 = 0.631·log z³, Wolfram), so it lands exactly on the Session-3 κ_real ≈ 0.63 two-comparable-S-units barrier; a contradiction needs an effective exponent κ < 1.107 while Baker-type bounds (which Bugeaud uses) give κ just below d=3. Resolved Session 9 Suggestion #1: made k_x ↦ A explicit as the 3-adic analytic function A(k_x) = (32·exp_3(k_x·L)+5)^{1/3} with g=2^332640, v_3(g−1)=4, L=log_3 g, v_3(L)=4 (Wolfram); by Theorem J it is a bijection Z_3→Z_3, so rationality of A at an integer k_x reduces to whether a specific s_a ∈ Z_3 lies in Z — 3-adically undetectable (Z dense in Z_3). No obstruction; last 3-adic stone turned. Added Session-10 addendum to the p-adic direction; updated arXiv survey notes; updated current_focus.md.
- **2026-06-25 (Session 12):** No new directions retired; no new directions elevated. Literature watch: assessed Zhou's effective IUT abc paper (arXiv:2503.14510, Mar 2025) — the most significant new 2025 number-theory preprint found to date, giving an effective abc bound log|abc| ≤ 3 log rad(abc) + 8√(log|abc|·log log|abc|). NOT APPLICABLE to Kuromine: the Kuromine triple (a,b,c)=(2^x, 3^y+5, z^3) has quality ≈ 0.888 < 1 (Session 8), so the Zhou bound is trivially satisfied (it upper-bounds quality at ≤ 3+ε, and Kuromine already satisfies quality < 1). Effective abc bounds help only when c ≫ rad(abc) (quality > 1); Kuromine is the opposite regime. Also did a broad June 2026 arXiv sweep: five additional papers assessed (2605.31114, 2605.28449, 2605.18348, 2606.00466, 2606.02244); none applicable. The Calegari–Dimitrov–Tang holonomy school (2510.04156) has no published follow-up below the ~1.1 exponent threshold. Four independent lines (S3/S10/S11/S12) now confirm the two-comparable-S-units barrier. Added Session-12 notes to the arXiv-survey [LOW] direction. Updated current_focus.md.
- **2026-06-26 (Session 13):** RETIRED new direction "Chabauty-Kim / algebraic geometry methods" (added and immediately retired — assessed the full cluster of 2025–2026 papers: Affine Chabauty I/II arXiv:2511.15949/2602.05643, Modular Chabauty arXiv:2505.12947, Cubic Chabauty arXiv:2604.20662). All NOT APPLICABLE for the same categorical reason: Kuromine's variables $x,y$ are exponents of fixed bases, not algebraic coordinates; Chabauty-Kim methods apply to algebraic curves and cannot encode the constraint "$u = 2^x$ for integer $x$". Established **fifth categorical barrier**: Chabauty-Kim in all forms is categorically inapplicable to two-exponential Diophantine equations. Added new [LOW] direction suggestion: "greatest prime factor of $z^3 - 5$" reformulation — if gpf($z^3-5$) grows effectively with $z$, then only finitely many $z$ can have $z^3-5$ a $\{2,3\}$-integer. June/July 2026 arXiv sweep: no new applicable paper. The Calegari–Dimitrov–Tang holonomy school has no new follow-up. Updated current_focus.md and directions.md.
- **2026-06-26 (Session 14):** RETIRED the [LOW] gpf($z^3-5$) direction (fundamental conflation: $\{2,3\}$-smoothness of $z^3-5$ is different from sum-representability as $2^x+3^y$; the known solution $z=4$ has $z^3-5=59$, prime, not $\{2,3\}$-smooth, yet $59=2^5+3^3$; moved to dead_ends.md). Proved and documented **Theorem M** (new elementary theorem): if $y=3j$ and $3^{2j+1} > 2^x+4$, then $2^x+3^y+5$ is not a perfect cube. This rigorously eliminates all Theorem-5 pairs with $k_y \geq \lceil 1.893\,k_x - 1.107\rceil$. For $k_x=1$: only $k_y=0$ survives. The surviving pairs satisfy $k_y/k_x < 3\log_3 2 - 1 \approx 0.893$, i.e., exactly the two-comparable-S-units regime ($2^x \geq 3^y$) where Baker and all analytic tools also fail. Extended numerical verification to $z \leq 10000$ (no new solutions). Added new [MEDIUM] direction entry for "Theorem M and size-partitioned Theorem-5 family." Updated current_focus.md and directions.md.
- **2026-06-26 (Session 15):** Pursued the Session-14 bounded-$A$ / boundary-case exploration (Theorem M sub-question (a), Factorization sub-question (a)). Proved and documented **Theorem N** (new exact 3-adic valuation identity): $2^x+5-A^3 = 3^{j+1}A(A+3^j)$, hence $v_3(2^x+5-A^3) = j+1$, using $\gcd(A,3)=1$ from Theorem I. Corollary: $A$ is no fixed small integer (for fixed $a$ coprime to 3, $v_3(2^x+5-a^3)$ is a bounded constant $\leq 3$, contradicting $j+1\geq 55440$; the $A=1$ band gives $v_3(2^x+4)=2$ by LTE, forcing $j=1$ = known solution). **CLOSED negatively** the bounded-$A$ elimination strategy: $A$ is small only at the Theorem-M boundary $D=x\log2-(2j+1)\log3\approx0$, but the Theorem-5 lattice never lands within $O(1)$ log-distance of it (Wolfram: closest surviving $D\approx55$ over $k_x\leq5000$, $A\gtrsim10^{24}$; closest overall $D\approx10$ on the eliminated side). This is the **metric face** of the two-comparable-S-units barrier. Added Theorem N to `knowledge/problem.md`; added the bounded-$A$ dead end to `knowledge/dead_ends.md`; closed Factorization sub-question (a) and Theorem-M sub-question (a); **promoted** Theorem-M sub-question (b) (the power-of-2 / narrow-$z$-band angle for $A<3^j$ cases) as the best concrete next lead. Updated current_focus.md and directions.md.
- **2026-06-26 (Session 17):** Pursued the two [LOW] directions: (1) function-field analog / Mason-Stothers, (2) special role of $c = 5$. For the function-field direction: proved that the equation *without* the constant ($P^x + Q^y = H^3$) is completely resolved by Mason-Stothers (only finitely many non-constant solutions, bounded by $\deg P + \deg Q$); proved that the equation *with* the constant ($P^x + Q^y + c = H^3$, $c \neq 0$) is NOT resolved by Mason-Stothers because $\text{rad}(P^x + c)$ has full degree (squarefree polynomial) — the function-field phantom obstruction. **RETIRED** the function-field direction (provably as hard as the integer case). For the $c = 5$ direction: derived the cyclotomic characterization $37 = \Phi_3(10)/3$ (3rd cyclotomic polynomial); parametrized the full phantom family $c_m = 27m^3 + 9m^2 + m - 32$, $z_m = (9m+1)/3$ ($c_1 = 5$, $c_2 = 222$, $c_3 = 781$); derived new universal congruence $z^3 \equiv 11 \pmod{37}$ for all Theorem-5 solutions (non-contradictory). Added new [LOW] direction: cyclotomic phantom family. Literature watch: negative. Six independent confirmations of the two-comparable-S-units barrier. Created `knowledge/references/function_field_analog.md`.
- **2026-06-27 (Session 20):** SPECIAL DIRECTIVE — **theory-creator mode** (all standard tools proven dead). Executed the mandatory four-step Theory-Building Protocol. **(1) Obstruction Diagnosis:** characterized the wall as the *conjunction* of four structural degeneracies — (P1) two-exponential/no-curve (kills modular & Chabauty-Kim), (P2) two-comparable-S-units (no distinguished small quantity; effective-exponent gap $0.631<\kappa<1.107$; kills Baker & irrationality measures), (P3) additive constant 5 (quality $0.888<1$; kills Thue-Mahler & ABC), (P4) phantom global rational cube (locally solvable everywhere; kills congruence/local) — with **one non-degenerate handle**: 3-adic depth $v_3(2^x+5-A^3)=j+1\to\infty$ (Theorem N) vs phantom depth 0. **(2) Framework Blueprinting:** argued the minimal bypassing machinery is a *non-additive arithmetic height coupling the archimedean place and the place 3* along the Theorem-5 progression. **(3) Axiomatic Definition:** defined the **Coupling-Height / Moving-Filtration framework**. **(4) Translation & Testing:** recast a Theorem-5 solution as an integer $A$ satisfying (T-real)∧(T-adic)∧(T-gate)∧(T-couple); stated **Lemma A** (Depth–Size Incompatibility, the crux, UNPROVEN) and **Lemma B/B′** (Lattice Rigidity). [Both refuted in Session 21.] arXiv watch: negative (ninth confirmation). Wolfram re-verified the anchors $3\log2/\log3=1.8928$ and $2\log3/(3\log2)=1.0566$.
- **2026-06-27 (Session 19):** Pursued and **RETIRED** the [LOW] Cyclotomic phantom family direction. Systematically compared $c_m = 27m^3+9m^2+m-32$ for $m=1,2,3$ (giving $c_1=5, c_2=222, c_3=781$). New: **Theorem O (parity partition)**: $c_m$ odd iff $m$ odd, hence $z$ even for odd-$m$ equations, $z$ odd for even-$m$ equations. Confirmed $c_1=5$ is uniquely special (only $c_m$ with $2^5+c_m$ prime $\equiv 1\pmod3$; all others composite with extra small-prime factors); $c_1=5$ is the EASIEST case in the family. Soft obstruction is universal (phantom is global rational cube for all $m$). No new attack strategy. Also conducted arXiv watch (negative; eighth confirmation of two-comparable-S-units barrier). **ALL non-watch directions now exhausted.** Research enters pure monitoring phase.
- **2026-06-26 (Session 18):** Deeply explored and **RETIRED** the [MEDIUM] Thue-Mahler equation approach (identified Session 1, never analyzed in depth). Enumerated all four candidate Thue-Mahler/norm-form castings and proved (Wolfram) each is broken by the additive constant 5 — the RHS is never a single S-unit. Established the symmetric reframing of the hard case $z^3 - 4(2^a)^3 - (3^j)^3 = 5$ (cube minus two S-unit-cubes = 5; verified on $(5,3,4)$). Proved $v_{37}(2^x+5)=1$ exactly and universally, hence $37\|B$; analyzed the 3-way mod-37 cube branch $z\in\{21,25,28\}$ (37 splits in $\mathbb{Z}[\omega]$), all soft-obstructed (phantom is a cube mod $37^n$ for all $n$, verified mod $37^3$; deeper 37-adic residues vary across the family). Confirmed per-fixed-$y$ Thue equation $z^3-4W^3=3^y+5$ is finite (Wolfram: $W=2^a$ only at $y=3$ = known solution) but Thue-Mahler theory gives no uniformity over the infinite progression (unit rank of $\mathbb{Q}(2^{1/3})$ is 1). **Also marked the [MEDIUM] Elliptic-curve direction as ~RETIRED** (same per-fixed-variable Mordell/Thue wall; no uniformity; $N_{k_x}\approx 10^5$ digits). arXiv watch: holonomy school (2510.04156) still $\mu>2$ for $2^{1/3}$, no new applicable 2026 follow-up (seventh confirmation of the two-S-units barrier). Created `knowledge/references/thue_mahler_approach.md`; added the Thue-Mahler dead end to `knowledge/dead_ends.md`. Updated current_focus.md and directions.md.
- **2026-06-26 (Session 16):** Pursued Theorem-M sub-question (b) — the "companion from-above" / narrow-$z$-band analysis. Derived the **Case II window** $A \in (e^D/7, e^D/3)$ for surviving pairs with $A < 3^j$ (i.e., $z \in (3^j, 2\cdot3^j)$). Width $\sim 0.19e^D$, exponentially large (for $k_x=1$, $k_y=0$: width $\approx 10^{3799}$). Confirmed: 2-adic analysis non-obstructive (2-adic cube bijection, Session 2); 3-adic analysis non-obstructive (3-adic bijection, Sessions 9–10); norm-form constraint (primes $p\equiv2\pmod3$ with odd $v_p$ in $2^x+5$ must divide $A$) phantom-compatible. **CLOSED negatively** sub-question (b). Conducted June 2026 arXiv watch: no new applicable paper; Calegari–Dimitrov–Tang (arXiv:2510.04156) has no new follow-up below $\mu\approx2$; Gherga–Siksek (arXiv:2207.14492, published ANT 2025) practical only for moderate $N$, not for $N\approx2^{332645}$. Five independent literature confirmations of the two-S-units barrier (S3/S10/S11/S12/S16). The Theorem-M direction is now **fully exhausted** (both sub-questions closed). Added new [LOW] direction suggestions: (1) special role of $c=5$ and the phantom; (2) function-field analog / Mason-Stothers inspiration. Updated current_focus.md and directions.md.
