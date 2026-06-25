# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization approach via $z^3 - w^3 = 2^x + 5$

**Discovered in Session 1 (2026-06-25).** For all Theorem 5 solutions, $y = 3j$ and the equation factors as $(z-w)(z^2+zw+w^2) = 2^x + 5$ with $\gcd = 1$ and $z^2+zw+w^2$ having only prime factors $\equiv 1 \pmod 3$. This is a norm form equation in $\mathbb{Z}[\omega]$ (Eisenstein integers). Key sub-questions:
- (a) Can we apply Thue-Mahler machinery to $z^3 - w^3 = 2^x + 5$ with $w = 3^j$?
- (b) Does the norm form $N(z - \omega w) = B \mid 2^x + 5$ impose new constraints on $z$ modulo primes $\equiv 1 \pmod 3$?
- (c) Is there a descent via the Eisenstein integer ring that links back to the original equation?

### [MEDIUM, partially executed] Effective Diophantine approximation to $2^{2/3}$ — resolves only the $2^x$-heavy tail

**Executed in Session 3; downgraded HIGH→MEDIUM.** Reframed $z^3 - 2^x = 3^y+5$ as a
rational approximation of the *fixed* irrational $\alpha = 2^{2/3} = 4^{1/3}$ by
$p/q = z/2^a$, $a=(x-2)/3$ (using $x\equiv2\pmod3$, so $2^x = 4\,(2^a)^3$). An exact
identity (Wolfram-verified) gives approximation exponent
$\kappa_{\text{actual}} = 3 - \tfrac{y\log3}{a\log2}$.

**Result:** Bennett's best-known measure ($\kappa\approx2.4325$) **proves no Theorem-5
solution with $x > 8.3787\,y$** (rigorous). But this is a *provably partial* tool: even an
optimal measure ($\kappa\to2$) only reaches $x > 4.7549\,y$, so the region $x\le4.755\,y$
(including the entire balanced & $3^y$-dominant regime, line $2^x=3^y$ is $x=1.585y$) is
**unreachable by any single-cube-root approximation**. Structural reason: $y=3j$ makes
$3^y=(3^j)^3$ an exact cube, so on the 3-side $z/3^j\to1$ is rational — no fixed irrational
to approximate. See `knowledge/references/irrationality_measure_approach.md`.

**Why kept at MEDIUM (not retired):** it is a genuine reduction (kills an infinite tail)
and — crucially — in the surviving region $x\le8.379y$ it **bounds $\mathrm{height}(z)$ in
terms of $y$** ($\log z\le\tfrac{8.379}{3}y\log2$), which is the concrete lever the
remaining Baker/Thue-Mahler argument needs. Remaining sub-questions:
- (a) Get/derive the explicit published $\kappa$ for $4^{1/3}$ specifically (Bennett 1997,
  arXiv:1602.05463, arXiv:2111.01044) to nail the constant in $x>8.379y$.
- (b) Check whether arXiv:2510.04156 holonomy bounds beat $\kappa=2.4325$ enough to lower
  the $8.379$ coefficient (best case $\to4.755$).

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

### [MEDIUM] Baker's method / linear forms in logarithms

**Session 1 assessment:** Matveev's bound is too weak for the Theorem 5 parameter range (minimum $x = 332645$, $y = 166317$). The bound allows $|\Lambda|$ to be as small as $\exp(-5.6 \times 10^{14})$, while the actual size is only $\exp(-47854)$. No contradiction. A refined version using Yu's p-adic Baker theorem might do better. Priority lowered pending literature search for better bounds.

### [MEDIUM] Elliptic curve approach (fix one variable)

Fixing $x = 5 + 332640k$ and studying $z^3 - 3^y = 2^x + 5$ as a family of curves. **Now linked to the factorization approach** above.

### [MEDIUM] Primitive divisor arguments (Zsygmondy)

May constrain the prime factorization of $z^3 - 5$ in ways that conflict with $2^x + 3^y$. **Connection found in Session 1:** The prime factors of $z^2+zw+w^2$ are all $\equiv 1 \pmod 3$. This is a primitive divisor-type constraint on the factorization of $2^x + 5$.

### [HIGH] Thue-Mahler / Baker for the hard core $x \le 8.379\,y$ (height of $z$ now bounded by $y$)

**Elevated in Session 3.** After the irrationality-measure reduction, the *only* surviving
region is $x \le 8.379\,y$, and there $\log z = \tfrac{x}{3}\log2 \le \tfrac{8.379}{3}\,y\log2
\approx 1.936\,y$ — i.e. the height of $z$ is now **linearly bounded by $y$**, removing the
"unknown enormous base $z$" obstacle that defeated Matveev in Sessions 1–2 (where $z$ was
free). Two concrete attacks:
- (a) **Linear form** $\Lambda = 3\log z - x\log2$ with $\log z \le 1.936\,y$: re-run the
  Matveev bound *in the hard-core region* using this bound on $\log z$, against the actual
  $\log|\Lambda| \approx y\log3 - x\log2$ (which in $x\le8.379y$ is NOT hugely negative).
  Check whether the now-bounded height makes Matveev bite. **This is the top next task.**
- (b) **Thue-Mahler** $z^3 - w^3 = 2^x+5$, $w=3^j$: for fixed $x$ a Thue equation; the
  bounded-height region may be small enough to resolve the smallest surviving cases
  ($m=0$: $k=1..4$; etc.) explicitly via arXiv:2207.14492.

**References:** arXiv:2207.14492 (Efficient resolution of Thue-Mahler equations).

### [LOW] (old framing) Thue-Mahler per-$k$ finiteness

**Session 1 framing, now subsumed by the [HIGH] hard-core entry above.** $z^3 - w^3 = N_k$
gives finitely many solutions for each fixed $k$; open question was zero solutions for all
$k\ge1$. The Session-3 reduction reframes this more usefully via the height bound.

### [LOW] Numerical search with Theorem 5 filtering

Verify computationally that no solutions exist for small $k$ (say $k \leq 5$). Not mathematically deep but can confirm the conjecture computationally and potentially reveal patterns in $2^x + 5 \pmod p$ for primes $p \equiv 1 \pmod 3$.

### [LOW] arXiv survey of exponential Diophantine equations

**Partially done in Session 1.** Found literature on Baker's method, S-unit equations, and Thue-Mahler equations. Next: search specifically for $z^3 - 3^y = C$ or $z^3 = 2^x + 3^y + C$ type results.

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.

---

## History of Changes

- **2026-06-25 (Session 1):** Added [HIGH] Factorization approach. Added [MEDIUM] Thue-Mahler equation approach. Lowered Baker's method assessment from [MEDIUM] to [MEDIUM-LOW] but kept at [MEDIUM] pending p-adic Baker investigation. Elevated $p$-adic direction to [HIGH] (tied). Noted Session 1 discoveries.
- **2026-06-25 (Session 2):** Downgraded standalone $p$-adic elimination from [HIGH] to [LOW/~RETIRED] after *proving* (not just observing) that local methods cannot obstruct the equation: the phantom is a global rational cube $(10/3)^3$, so every local condition is satisfiable. Added new [HIGH] direction "Effective Diophantine approximation to $2^{1/3}$" as the realistic global path. Completed the 2-adic structure analysis ($z\equiv6\pmod{32}$, $v_2(3^y+5)=3$). See `knowledge/references/two_adic_structure.md`.
- **2026-06-25 (Session 3):** Executed the irrationality-measure direction. **Proved (rigorously) that Bennett's effective measure for $2^{2/3}$ eliminates all Theorem-5 solutions with $x>8.3787\,y$**, but also proved it is *provably partial* (optimal $\kappa\to2$ only reaches $x>4.7549y$; region $x\le4.755y$ unreachable, structurally one-sided because $3^y$ is an exact cube). Downgraded that direction HIGH→MEDIUM (partial tool, not a finisher). **Elevated Thue-Mahler/Baker to [HIGH]** for the surviving hard core $x\le8.379y$, where the key new fact is that $\mathrm{height}(z)$ is now linearly bounded by $y$ ($\log z\le1.936y$) — removing the obstacle that defeated Matveev in Sessions 1–2. New reference `knowledge/references/irrationality_measure_approach.md`.
