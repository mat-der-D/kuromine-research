# Research Directions

Directions are listed with a priority estimate and current status.

---

## Active Directions

### [HIGH] $p$-adic analysis of the phantom solution
The phantom solution $(5, -3, 10/3)$ is a 3-adic obstruction. Understanding why integer solutions are different from the phantom in the 3-adic sense may be the key.
- **2026-06-25 progress:** Proved the valuation-splitting identity. In the surviving case
  ($x\equiv5\bmod6$), with $w=(2^x+5)^{1/3}\in\mathbb{Z}_3$, $z^3-w^3=3^y$ factors with
  $v_3(z^2+zw+w^2)=1$ exactly, so $y=v_3(z-w)+1$. The phantom is the same branch at
  $v_3(10/3)=-1$ (non-integer), explaining why congruences can't see it. This reformulates
  the case as a 3-adic Diophantine-approximation problem (→ feeds the Baker/Yu direction).
  Writeup: `knowledge/references/padic_branch_analysis.md`. The identity is rigorous but does
  not bound $y$ alone; remains [HIGH] to push toward an analytic bound.

### [HIGH] Baker's method / linear forms in $p$-adic logarithms (Yu)
**Raised from MEDIUM on 2026-06-25.** The 3-adic reformulation above recasts the surviving
case as: integer $z$ must be 3-adically close to $w=(2^x+5)^{1/3}$ with $v_3(z-w)=y-1$. This
is exactly the setting of Yu's $p$-adic linear forms in logarithms, which can give an
*effective upper bound* on $y$ that congruences provably cannot. Literature confirms this is
the standard, successful route for $a^x+b^y=c^z$ equations
(Cambridge MPCPS; HRJ episciences). Next: set up the linear form
$\Lambda = x\log 2 + y\log 3 + \log(\dots)$ / the $p$-adic analogue and extract a concrete
bound with explicit constants.

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
