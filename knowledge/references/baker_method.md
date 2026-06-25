# Baker's Method / Linear Forms in Logarithms

## Core Theorem (Matveev 2000, Corollary 2.3)

For a nonzero linear form
$$\Lambda = b_1 \log a_1 + b_2 \log a_2 + \cdots + b_n \log a_n$$
with $a_i \in \mathbb{Z}_{\geq 2}$, $b_i \in \mathbb{Z}$:

$$\log|\Lambda| > -1.4 \cdot n^{4.5} \cdot 30^{n+3} \cdot \log a_1 \cdots \log a_n \cdot (1 + \log \max\{|b_1|, \ldots, |b_n|\})$$

**Key reference:** E.M. Matveev, "An explicit lower bound for a homogeneous rational linear form in the logarithms of algebraic numbers. II," *Izvestiya: Mathematics* 64 (2000), 1217–1269.

**Baker–Wüstholz (1993):** "Logarithmic forms and group varieties," *J. Reine Angew. Math.* 442, 19–62. Gives a sharp lower bound with linear dependence on $\log B$.

## Application to the Kuromine Problem

**Setup:** $z^3 = 2^x + 3^y + 5$. If $2^x \gg 3^y$ (which holds for solutions in the Theorem 5 class), then $z \approx 2^{x/3}$ and the linear form is:

$$\Lambda = x \log 2 - 3 \log z$$

**Bound:** $|\Lambda| \leq 2(3^y + 5)/2^x$, so $\log|\Lambda| \approx y \log 3 - x \log 2$.

For the minimum Theorem 5 case ($x = 332645$, $y = 166317$):
- $\log|\Lambda| \approx -47854$
- Matveev lower bound: $\approx -5.6 \times 10^{14}$

**Conclusion:** The bound does not give a contradiction. Baker's method as stated is too weak for these parameter ranges without significantly refined estimates.

## p-adic Baker (Yu's theorem)

For p-adic linear forms $\Lambda_p = b_1 \log_p a_1 + \cdots + b_n \log_p a_n$:

$$v_p(\Lambda_p) \leq C(n, p, a_1, \ldots, a_n) \cdot \log B$$

This is relevant for the 3-adic analysis of the equation. See `references/p_adic_methods.md`.

## S-unit Equations (Evertse–Schlickewei–Schmidt)

The equation $2^x + 3^y + 5 = z^3$ can be viewed as an S-unit equation with $S = \{2, 3, 5\}$. The general theorem guarantees finitely many solutions. However, the bound is ineffective (not useful for explicit computation).

For effective finiteness via Thue-Mahler: the sub-equation $z^3 - 3^y = 2^x + 5$ where $w = 3^{y/3}$ satisfies $z^3 - w^3 = 2^x + 5$, and $2^x$ ranges over S-units for $S = \{2\}$. The Thue-Mahler theorem gives finitely many $(z, w)$ for each fixed $N = 2^x + 5$.

**Reference:** arXiv:2207.14492 — Efficient resolution of Thue-Mahler equations.
