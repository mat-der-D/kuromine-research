# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

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

Key sub-questions (remaining):
- (a) Can we apply Thue-Mahler machinery to the reduced equation $A(A^2+3^{j+1}A+3^{2j+1}) = 2^x+5$ for fixed $x$? (Finiteness per $x$ known; uniformity over the $x$-progression open — this is the entire difficulty, and no current tool delivers it.)
- (b) [CLOSED, Session 4] growth / primitive-divisor (Zsygmondy/BHV): inapplicable — $B$ is not a Lucas/Lehmer sequence. See RETIRED entry below.
- (c) [CLOSED negatively, Session 4] $A = z - 3^{y/3}$ cannot be forced to 1; it is provably $\sim2^{x/3}$ for any Theorem-5 solution.

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

### [LOW, ~RETIRED as standalone] $p$-adic analysis of the phantom solution

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

### [MEDIUM] Elliptic curve approach (fix one variable)

Fixing $x = 5 + 332640k$ and studying $z^3 - 3^y = 2^x + 5$ as a family of curves. **Now linked to the factorization approach** above.

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

### [MEDIUM] Thue-Mahler equation approach

**New direction identified in Session 1.** The equation $z^3 - w^3 = N_k$ with $w = 3^j$ is a Thue-Mahler type equation. For each fixed $k$, $N_k = 2^{5+332640k} + 5$ is fixed, and the Thue-Mahler theorem gives finitely many solutions. The question is whether no solution exists for any $k \geq 1$.

**References:** arXiv:2207.14492 (Efficient resolution of Thue-Mahler equations).

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

### [LOW] arXiv survey of exponential Diophantine equations

**Partially done in Session 1.** Found literature on Baker's method, S-unit equations, and Thue-Mahler equations. Session 5 adds: Miyazaki (2503.00843) solves infinite families of 4-term purely exponential equations using Baker+p-adic Baker+Skolem, but all rely on local non-solvability. The Kuromine equation's phantom blocks this route. Next: watch for new methods in the "two-comparable-S-units" regime.

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.

---

## History of Changes

- **2026-06-25 (Session 1):** Added [HIGH] Factorization approach. Added [MEDIUM] Thue-Mahler equation approach. Lowered Baker's method assessment from [MEDIUM] to [MEDIUM-LOW] but kept at [MEDIUM] pending p-adic Baker investigation. Elevated $p$-adic direction to [HIGH] (tied). Noted Session 1 discoveries.
- **2026-06-25 (Session 2):** Downgraded standalone $p$-adic elimination from [HIGH] to [LOW/~RETIRED] after *proving* (not just observing) that local methods cannot obstruct the equation: the phantom is a global rational cube $(10/3)^3$, so every local condition is satisfiable. Added new [HIGH] direction "Effective Diophantine approximation to $2^{1/3}$" as the realistic global path. Completed the 2-adic structure analysis ($z\equiv6\pmod{32}$, $v_2(3^y+5)=3$). See `knowledge/references/two_adic_structure.md`.
- **2026-06-25 (Session 3):** RETIRED "Effective Diophantine approximation to $2^{1/3}$" (was [HIGH]) with a proof that it is quantitatively dead: realized exponent $\kappa\approx0.62\ll\mu$, and the Thue value $3^y+5$ is too large by $\sim e^{138909}$ — root cause is the two-comparable-dominant-S-units regime ($3^y\approx z^2$). See `knowledge/references/irrationality_measure_obstruction.md`. Added Session-3 progress to the Factorization [HIGH] direction (reduced equation $2^x+5=A(A^2+3^{j+1}A+3^{2j+1})$, both real solutions have $A=z-3^{y/3}=1$, Eisenstein identity $4B-3w^2=(2z+w)^2$). Elevated primitive-divisor (Zsygmondy/BHV) direction to [MEDIUM-HIGH] as the best remaining non-size lead, since all size methods are now shown too weak.
- **2026-06-25 (Session 4):** RETIRED the [MEDIUM-HIGH] primitive-divisor/growth direction: its congruence form is killed by the soft obstruction (showed $A\equiv3$, $B\equiv37/3\pmod p$ for all $p\ne3$, matching the phantom; $x\bmod3$, $y\bmod6$ constant over the family), and its growth form has no Lucas/Lehmer object ($B$ not an $a^n-b^n$ sequence). RETIRED the modular/Frey-curve method as structurally inapplicable (no varying prime exponent) — created `knowledge/references/modular_method.md`. Downgraded the Factorization [HIGH] direction toward MEDIUM: closed sub-questions (b) and (c) negatively ($A$ is provably $\sim2^{x/3}$, never 1), leaving only the global/size sub-question (a) for which no adequate tool exists. Added Session-4 progress note to `knowledge/references/factorization_approach.md`. Extended numerical verification to $x,y\le2000$ (only the two known solutions). Both retirements moved to `knowledge/dead_ends.md`.
- **2026-06-25 (Session 5):** RETIRED Baker's method (all variants, including Yu's p-adic Baker): p-adic linear forms have $v_p = 0$ for $p \in \{2,3\}$ — p-adic units — so no Baker upper bound can ever be violated. RETIRED Skolem/Bertók-Hajdu: inapplicable because the phantom makes the equation locally solvable everywhere. Added A=1 sub-theorem proof (exactly $(1,0,2)$ and $(5,3,4)$ satisfy $A=1$). Documented the algebraic origin of the phantom: $c=5$ is the smallest positive integer for which $865+27c$ is a perfect cube. Checked $z\bmod37$ structure: three branches cycle over Theorem-5 family, no contradiction. Added Session-5 history entry, retired Baker and Skolem to dead ends.
