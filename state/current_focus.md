# Current Focus

**Session:** 20260625 (first research session)

**Current direction:** [HIGH] 3-adic analysis of the phantom solution.

**Why this direction:** Congruence sieving is a proven dead end precisely *because* of the
3-adic phantom $(5,-3,10/3)$. The [HIGH] direction asks us to understand the 3-adic structure
that distinguishes integer solutions from the phantom. This is the natural next step and the
prerequisite for any effective (Baker/Yu) bound.

**What has been done in this direction:**
- Reformulated the surviving case ($x \equiv 5 \bmod 6$, $y \ge 2$) 3-adically.
- Proved the **valuation-splitting identity**: writing $z^3 - w^3 = 3^y$ with
  $w = (2^x+5)^{1/3} \in \mathbb{Z}_3$, the factor $z^2+zw+w^2$ has 3-adic valuation
  *exactly 1* (via $z^2+zw+w^2 = (z-w)^2 + 3zw$ and $z\equiv w \bmod 3$). Hence
  $y = v_3(z-w) + 1$.
- Showed all three 3-adic cube roots of $37$ are $\equiv 4 \pmod 9$, so $z \equiv 4 \pmod 9$
  and $y \ge 3$ automatically; equality for the known $(5,3,4)$.
- Located the phantom: $z=10/3$ is the *same branch* with $v_3(10/3)=-1$, i.e. a non-integer
  3-adic point — exactly invisible to congruences.
- Numerically confirmed (exact `IntegerQ[Surd[n,3]]`) no solutions besides $(1,0,2)$ and
  $(5,3,4)$ for $x,y \le 120$, and for $x \equiv 5 \bmod 6$ up to $x=605$, $y \le 400$.

Full writeup: `knowledge/references/padic_branch_analysis.md`.

**Where things stand / Blockers:** The identity $y = v_3(z-w)+1$ is rigorous but does **not**
bound $y$ by itself (3-adically $z-w$ can be arbitrarily small — the phantom obstruction
persists at the congruence level). The reformulation reframes the problem as a 3-adic
Diophantine-approximation / linear-forms-in-logarithms statement, which is the regime where
Yu's $p$-adic theory can in principle give an effective upper bound on $y$. Converting the
framing into an explicit bound (with constants) is the open next step.

**Notes:** Literature check confirms the standard route for $a^x+b^y=c^z$ is exactly
p-adic linear forms in logs (Yu) + computational verification. Next session should pursue
the Baker/Yu bound concretely, now elevated to [HIGH].
