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
- **2026-06-25 (Session 6):** No new directions retired; no new directions elevated. Literature survey of 2025-2026 arXiv found no unconditional new tool for the two-S-units regime. Investigated descent-on-A: found A ≡ 4 (mod 9), A ≡ 22 (mod 27), A ≡ 27 (mod 32) [NOTE: the last is only for k_y even; corrected in Session 7], j ≡ 7 (mod 8) as new refined constraints for the Theorem-5 family; these are genuine addenda but do not yield a contradiction. Confirmed phantom-free neighboring constants c=4,6,7,... have no rational phantom and are structurally simpler, but this doesn't help resolve c=5. Updated arXiv survey [LOW] direction with Session 6 findings. Updated current_focus.md.
- **2026-06-25 (Session 7):** No new directions retired; no new directions elevated. Corrected Session 2 result: $z \equiv 6 \pmod{32}$ is not universal; the correct universal statement is $z \equiv 6 \pmod{16}$ (the full family splits into $z \equiv 6$ and $z \equiv 22 \pmod{32}$ by $k_y$ parity). Derived new universal constraints (Theorems E–H): $y \equiv 13 \pmod{16}$, $j \equiv 3 \pmod{4}$, $z \equiv 6 \pmod{16}$, $A \equiv 11 \pmod{16}$. Corrected Session 6 Theorem B: the correct universal form is $A \equiv 11 \pmod{16}$ (not $27 \pmod{32}$). Derived $B \equiv 79 \pmod{432}$ as a new universal constraint. Updated CRT: $A \equiv 427 \pmod{432}$, $B \equiv 79 \pmod{432}$, consistent with $A \cdot B \equiv 37 \pmod{432}$. Noted that $A_{\mathrm{phantom}} = 3 \equiv 3 \pmod{16}$ while $A_{\mathrm{real}} \equiv 11 \pmod{16}$ — genuine 2-adic separation but not a contradiction. arXiv 2026 search: one new paper (2603.29831, cubic reciprocity) found; not applicable. Updated current_focus.md.
- **2026-06-25 (Session 9):** No new directions retired; no new directions elevated. Completed the 3-adic portrait of the integer factor B (Theorem L), mirroring Theorems I/J for A: B ≡ 25 (mod 27) universal; B mod 81 indexed by k_x mod 3 (52/79/25 for k_x ≡ 0/1/2); B mod 3^{n-1} a function of k_x mod 3^{n-4} for n ≥ 5, inherited from Theorem J via B ≡ (2^x+5)·A^{-1} (A a 3-adic unit). Corrected Session 8 suggestion #1: B mod 729 needs k_x mod 27 (not mod 9); full 27-branch (A,B) mod 729 table computed and verified (A·B ≡ 2^x+5 mod 729 in every row). B is a 3-adic unit (v_3(B)=0), separating it from the phantom (B_phantom=37/3, v_3=-1) but non-actionably. Formalized Theorems I, J, K, L into knowledge/problem.md and created knowledge/references/adic_structure_extended.md (full 2-adic + 3-adic portraits of A and B side by side). The local portrait of a Theorem-5 solution is now complete for both coprime factors at arbitrary p-adic depth; no contradiction; fundamental barrier unchanged. Updated current_focus.md.

- **2026-06-25 (Session 8):** No new directions retired; no new directions elevated. Completed the (k_x, k_y) indexing of all A-congruence branches. Theorem I: the three branches of A mod 81 are indexed by k_x mod 3 (k_x≡0 → A≡49, k_x≡1 → A≡22, k_x≡2 → A≡76 mod 81). Theorem J: A mod 3^{n-1} uniquely determined by k_x mod 3^{n-4} for n≥5 (gcd(332640, ord_{3^n}(2))=54 for all n≥5). Theorem K: full 12-branch A mod 20736=lcm(81,256) indexed by (k_x mod 3, k_y mod 4), all 12 values listed. Corrected and completed Session 6's three-branch CRT to a six-branch CRT mod 2592 indexed by (k_x mod 3, k_y mod 2). Assessed ABC conjecture: no contradiction (quality exponent q≈0.888<1, ABC is never violated). Assessed two new 2026 arXiv papers: arXiv:2505.19141 (S-unit decidability, two primes) and arXiv:2604.18991 (a^x+b^y=c^z); both NOT APPLICABLE to Kuromine. Noted that the 3-adic expansion of A is determined digit-by-digit by k_x, confirming it is a bijection Z_3→Z_3 (no contradiction). Updated current_focus.md.

- **2026-06-25 (Session 11):** No new directions retired (all relevant ones already retired); no new directions elevated. Literature watch on a previously-unassessed, maximally on-target paper — Badziahin's "Distance between cubics and rationals" (arXiv:2509.01105 / Results in Math. 2026), which studies cubic-irrational-vs-rational separation, the geometry directly underlying |z³ − 3^y|. NOT APPLICABLE: its bounds are conditional on abc/Hall and nontrivial only for good approximations 2 ≤ v ≤ 3; Kuromine cannot be cast there ("cube − square" needs y even but y is always odd in the family; "cube − cube" degenerates to a rational nearby integer = the old factorization; the 2^{2/3}-Thue casting realizes v_real ≈ 0.62 at the floor k_y=0 and **negative** for all k_y ≥ 1 — the approximation *diverges*). This sharpens Session 3: κ_real is 0.62 only at the family floor and goes negative (−1.75, −4.13, −6.51, …) for every k_y ≥ 1, so almost the whole family has z/W not approximating 2^{2/3} at all (Wolfram). Also assessed Bajpai's effective many-term S-unit thesis (Bajpai–Bennett, Acta Arith. 214 (2024)): NOT APPLICABLE — Baker-based (retired Session 5) and requires S-unit-controlled terms, which z³ and the constant 5 are not (= Session 8 obstruction). Three independent literature lines (irrationality measures S3, Bugeaud S10, Badziahin S11) now confirm the two-comparable-S-units barrier structurally. Added a Session-11 strengthening note to the RETIRED 2^{1/3} entry and a Session-11 assessment to the arXiv-survey [LOW] direction. Updated current_focus.md.
- **2026-06-25 (Session 10):** No new directions retired; no new directions elevated. Literature watch: assessed the two newest Bugeaud "perfect-power minus integral S-unit" papers (arXiv:2604.27490, Apr 2026; arXiv:2503.22084, Mar 2025), the first 2026 results to bound exactly the Kuromine-shaped difference. NOT APPLICABLE: Option (1) z³−2^x = 3^y+5 fails the coprimality hypothesis (z even); Option (2) z³−3^y = 2^x+5 satisfies it (x odd ⇒ z coprime to 3) but gives no contradiction because |z³−3^y| = 2^x+5 ≈ z^{1.89} (log 230572 = 0.631·log z³, Wolfram), so it lands exactly on the Session-3 κ_real ≈ 0.63 two-comparable-S-units barrier; a contradiction needs an effective exponent κ < 1.107 while Baker-type bounds (which Bugeaud uses) give κ just below d=3. Resolved Session 9 Suggestion #1: made k_x ↦ A explicit as the 3-adic analytic function A(k_x) = (32·exp_3(k_x·L)+5)^{1/3} with g=2^332640, v_3(g−1)=4, L=log_3 g, v_3(L)=4 (Wolfram); by Theorem J it is a bijection Z_3→Z_3, so rationality of A at an integer k_x reduces to whether a specific s_a ∈ Z_3 lies in Z — 3-adically undetectable (Z dense in Z_3). No obstruction; last 3-adic stone turned. Added Session-10 addendum to the p-adic direction; updated arXiv survey notes; updated current_focus.md.
