# The Modular Method (Frey curves) and the Kuromine Problem

Session 4 (2026-06-25). Assessment of whether the Frey-curve / modular method
(the engine behind Fermat's Last Theorem and the generalized Fermat equation)
can be applied to $z^3 = 2^x + 3^y + 5$.

## What the modular method needs

For an equation of "signature" $(p,q,r)$ — e.g. $a^p + b^q = c^r$ — the modular
method (Frey–Hellegouarch curve $\to$ modularity (Wiles, Breuil–Conrad–Diamond–Taylor)
$\to$ Ribet level-lowering $\to$ comparison with a finite list of newforms) requires a
**varying prime exponent** $p$ (or $q,r$) to which one attaches the mod-$p$ Galois
representation on the $p$-torsion $E[p]$ of the Frey curve. Darmon's program for the
generalized Fermat equation builds *Frey representations* of signature $(r,q,p)$ precisely
around such a varying prime $p$. The standard workflow:

1. Resolve **small** exponents by elementary/elliptic methods.
2. For **large** prime exponent $p$, build the Frey curve, level-lower, and contradict the
   (finite, computable) space of newforms at the lowered level.

**Key references:**
- Bennett–Skinner, "Ternary Diophantine equations via Galois representations and modular
  forms," *Canad. J. Math.* 56 (2004).
- Darmon, "Rigid local systems, Hilbert modular forms, and Fermat's last theorem,"
  *Duke Math. J.* 102 (2000) — Frey representations of signature $(r,q,p)$.
- Bugeaud–Mignotte–Siksek, "Classical and modular approaches to exponential Diophantine
  equations," arXiv:math/0405220 (the multi-Frey technique).

## Why it does not directly apply to the Kuromine equation

In $z^3 = 2^x + 3^y + 5$:

- The only perfect-power structure is the **cube** $z^3$: a *fixed, small* exponent 3.
- The varying exponents are $x$ and $y$, but they sit on the **fixed small bases 2 and 3**,
  with an additive constant $+5$. There is **no large varying prime exponent** anywhere in
  the equation to carry a mod-$p$ Galois representation.

Equivalently, restricting to the Theorem-5 class ($x\equiv5\equiv2\pmod3$, so $2^x=4W^3$
with $W=2^{(x-2)/3}$), the equation becomes
$$z^3 + 4W^3 = 3^y + 5,$$
a relation among two cubes and the quantity $3^y+5$. This is signature $(3,3,\,\ast)$ on
the left, but the right-hand side $3^y+5$ is **not a perfect power** (it is a shifted
$S$-unit), so there is no exponent on the right to modularize either. The cube exponent 3
is far too small and fixed to drive the method (signature $(3,3,3)$ is the classical
Fermat cubic, already finite, and adds no varying $p$).

**Conclusion.** The standard single- or multi-Frey modular method is **not applicable** to
the Kuromine equation as stated: it has no varying prime exponent. This is a structural
mismatch, not a quantitative weakness.

## The one residual (already-known) elliptic angle

For each **fixed** $y$, $z^3 - 3^y = 2^x + 5$ is a Mordell-type / Thue–Mahler equation
$z^3 = 2^x + (3^y+5)$ whose solutions are finite and (in principle) effectively computable
by integral-point / descent methods on the elliptic curve $Y^2 = X^3 + \ldots$ associated
to the cubic. But:
- This only re-proves **finiteness per fixed $y$** (or per fixed $x$), which is already
  known via Thue–Mahler / $S$-unit theory.
- It gives **no uniformity** across the infinite Theorem-5 progression of $(x,y)$, which is
  the actual open content of the conjecture.

So the elliptic-curve route degenerates to the same wall as Thue–Mahler: solvable
case-by-case, silent about the infinite family.

## Sources
- arXiv:math/0405220 (Bugeaud–Mignotte–Siksek, classical & modular approaches).
- Darmon, *Duke Math. J.* 102 (2000) (Frey representations / generalized Fermat).
- arXiv:2512.04936 (survey of generalized Fermat equations of various signatures).
- arXiv:2502.09892 (asymptotic Fermat of signature $(r,r,p)$ — shows the need for a
  varying prime exponent $p$).
