# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] Factorization approach via $w = 3^{y/3}$  (NEW, session 20260624)
Theorem 5 forces $y \equiv 0 \pmod 3$ on every remaining solution, so $3^y = w^3$ with
$w = 3^{y/3} \in \mathbb{Z}$. The equation factors as $z^3 - w^3 = 2^x + 5$, i.e.
$d(3w^2 + 3wd + d^2) = 2^x + 5$ with $d = z - w \ge 1$. This yielded a new unconditional
size theorem $2^x + 5 \ge 3^{2y/3+1}$ ($x > 1.0566\,y$) and a complete resolution of the
$d=1$ stratum (reduces to Ramanujan–Nagell $3m^2 - 19 = 2^{x+2}$; only known solution survives).
Most promising concrete line. Next: bound $d$ above (Baker) / close the cone, and kill $d\ge 2$.
See `knowledge/references/factorization_approach.md`.

### [HIGH] $p$-adic analysis of the phantom solution
The phantom solution $(5, -3, 10/3)$ is a 3-adic obstruction. Note clarified this session:
$37$ is a genuine cube in $\mathbb{Z}_3$ (Hensel-lifts to a unique $w \equiv 1 \pmod 3$),
distinct from the phantom $10/3$ (which has $v_3 = -1$, not in $\mathbb{Z}_3$). Understanding
why integer solutions differ from the phantom in the 3-adic sense may still be key.

### [MEDIUM] Baker's method / linear forms in logarithms
Effective but potentially yields only very large bounds. Worth understanding what bounds it would give for this specific equation.
**Now directly actionable** (raised relevance): the factorization approach reduces the problem
to an S-unit equation $2^x - 3\cdot(3^{y/3})^2 = \text{(lower order in }d)$. A Baker bound here
would supply the missing upper bound on $x$ and close the cone from the new size theorem.

### [MEDIUM] Elliptic curve approach (fix one variable)
Fixing $x = 5 + 332640k$ and studying the resulting equation in $y$ and $z$ as a curve family.

### [MEDIUM] Primitive divisor arguments (Zsygmondy)
May constrain the prime factorization of $z^3 - 5$ in ways that conflict with $2^x + 3^y$.

### [LOW] Numerical search with Theorem 5 filtering
Brute-force search is not mathematically deep, but can confirm no small solutions are missed and may reveal patterns.

### [LOW] arXiv survey of exponential Diophantine equations
Search for results on equations of the form $a^x + b^y = z^n$ or $2^x + 3^y = N$. Relevant keywords: "exponential Diophantine equation", "Pillai equation", "S-unit equation", "linear forms in logarithms".

---

## Retired Directions

### [RETIRED] Pure congruence sieving
See `knowledge/dead_ends.md`. Cannot eliminate the phantom solution by this method alone.
