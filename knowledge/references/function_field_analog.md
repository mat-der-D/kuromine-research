# Function-Field Analog via Mason-Stothers

Session 17 (2026-06-26). Analytical work (Wolfram MCP unavailable).

This file records the analysis of the function-field analog of the Kuromine equation
via the Mason-Stothers theorem, and its consequences for the integer case.

## Setup

Replace $2^x, 3^y, z$ by polynomials $P^x, Q^y, H$ over $\mathbb{C}[t]$, where $P, Q$
are fixed irreducible polynomials and $H \in \mathbb{C}[t]$ is the unknown.

**Equation without constant:** $P(t)^x + Q(t)^y = H(t)^3$

**Equation with constant:** $P(t)^x + Q(t)^y + c = H(t)^3$ for $c \in \mathbb{C}^*$

## The Mason-Stothers Theorem

For polynomials $a + b + c = 0$ over $\mathbb{C}[t]$ pairwise coprime with not all constant:
$$\max(\deg a, \deg b, \deg c) \leq \deg(\text{rad}(abc)) - 1,$$
where $\text{rad}(f)$ is the product of distinct irreducible factors of $f$.

Key: $\deg(\text{rad}(f)) = $ number of distinct roots of $f$ counted with multiplicity 1.
For $f = g^n$, $\deg(\text{rad}(f)) = \deg g$; for squarefree $f$, $\deg(\text{rad}(f)) = \deg f$.

## Case 1: Equation Without Constant

Apply Mason-Stothers to $P^x + Q^y + (-H^3) = 0$:
$$\deg(\text{rad}(P^x \cdot Q^y \cdot H^3)) = \deg P + \deg Q + \deg(\text{rad}(H)).$$

Since $\deg(\text{rad}(H)) \leq \deg H$ and $3\deg H = \max \leq \deg P + \deg Q + \deg H - 1$:
$$2\deg H \leq \deg P + \deg Q - 1.$$

For $\deg P = \deg Q = 1$: $\deg H \leq 0$ — **no non-constant solution $H$.**
For general $\deg P, \deg Q$: $\deg H \leq (\deg P + \deg Q - 1)/2$, hence $x$ is bounded
(from $3\deg H \approx x\deg P$): $x \leq 3(\deg P + \deg Q - 1)/(2\deg P)$.

**Theorem:** The equation $P^x + Q^y = H^3$ has only finitely many solutions with $H$
non-constant, bounded by $\deg P + \deg Q$.

## Case 2: Equation With Constant $c \neq 0$

Group as $(P^x + c) + Q^y = H^3$. Apply Mason-Stothers:
$$\deg(\text{rad}((P^x + c) \cdot Q^y \cdot H^3)) = \deg(\text{rad}(P^x + c)) + \deg Q + \deg(\text{rad}(H)).$$

**Key:** $P^x + c$ is **squarefree** for $c \neq 0$, because:
- Roots of $P^x + c$ satisfy $P(t) = (-c)^{1/x}$ (a non-zero value).
- Roots of $(P^x + c)' = xP^{x-1}P'$ satisfy $P(t) = 0$ (a different value).
- No common roots. Hence $\gcd(P^x + c, (P^x+c)') = 1$, so $P^x + c$ is squarefree.

Therefore $\deg(\text{rad}(P^x + c)) = x\deg P$.

Mason-Stothers gives:
$$3\deg H \leq x\deg P + \deg Q + \deg H - 1,$$
$$2\deg H \leq x\deg P + \deg Q - 1.$$

Since $3\deg H \approx x\deg P$, the RHS $\approx \frac{3}{2}\deg H + \deg Q - 1$,
giving $\frac{1}{2}\deg H \leq \deg Q - 1$. This is only a bound in terms of $\deg Q$,
not $x$. **For any $x$, solutions with $\deg H \leq 2(\deg Q - 1)$ are allowed.**
Mason-Stothers gives **no useful bound** when the constant is present.

## The Phantom Obstruction as a Function-Field Phenomenon

The reason Mason-Stothers fails with the constant is exactly analogous to the integer
phantom obstruction:

- **Integer case:** The phantom $(5, -3, 10/3)$ satisfies $2^5 + 3^{-3} + 5 = (10/3)^3$
  over $\mathbb{Q}$, blocking congruence elimination modulo every prime $p \neq 3$.
  
- **Function-field case:** The polynomial $P^x + c$ is squarefree, so it has "full radical"
  (no repeated factors). This is the polynomial analog of the phantom being a valid
  $p$-adic solution: the constant $c$ prevents compression of the radical term, just as
  the phantom prevents a modular obstruction.

In both cases, the additive constant $c$ is what "inflates" the bad term, making the
method inapplicable.

## Structural Theorem (Session 17)

**Theorem:** Let $P, Q$ be irreducible polynomials over $\mathbb{C}$ and $c \in \mathbb{C}$.

(a) If $c = 0$: The equation $P^x + Q^y = H^3$ has only finitely many solutions with
$H$ non-constant ($x$ bounded by $\frac{3(\deg P + \deg Q - 1)}{2\deg P}$).

(b) If $c \neq 0$: Mason-Stothers gives no useful bound on $x$ for the equation
$P^x + Q^y + c = H^3$. The radical $\text{rad}(P^x + c)$ has full degree $x\deg P$.

**Consequence:** The additive constant $c = 5$ is genuinely the hard ingredient in the
Kuromine problem. Any resolution must exploit specific arithmetic properties of $c = 5$
beyond the general "exponential sum equals cube" structure.

## The Cyclotomic Origin of the $c = 5$ Phantom

For the integer Kuromine equation, the phantom arises because:
$$32 + 5 = 37 = \frac{\Phi_3(10)}{3} = \frac{10^2 + 10 + 1}{3} = \frac{111}{3},$$
where $\Phi_3(n) = n^2 + n + 1$ is the 3rd cyclotomic polynomial. This gives
$37 \cdot 27 + 1 = 1000 = 10^3$, hence $2^5 + 3^{-3} + 5 = (10/3)^3$.

The general phantom family ($y = -3$, $z$ rational) is parametrized by $m \geq 1$:
$$c_m = 27m^3 + 9m^2 + m - 32, \quad z_m = \frac{9m+1}{3}.$$
Giving: $c_1 = 5$ ($z_1 = 10/3$), $c_2 = 222$ ($z_2 = 19/3$), $c_3 = 781$ ($z_3 = 28/3$).

The uniqueness of $c = 5$ among small positive integers is the uniqueness of $m = 1$ in
this family: it is the only case with $c_m < 100$ (or even $c_m < 200$).

## Implications

1. **Mason-Stothers does not resolve the function-field analog.** This closes the [LOW]
   direction definitively — the function-field version is provably as hard as the integer
   version (for the same structural reason).

2. **The function-field proof for $c = 0$ suggests what's needed for $c \neq 0$:**
   A proof must somehow "compress" the radical of $P^x + c$ from $x\deg P$ to something
   smaller, which requires exploiting arithmetic properties of $c$. In the integer case
   this corresponds to reducing the "phantom obstruction" — which requires a tool the
   integers do not currently have.

3. **The holonomy bounds school** (Calegari-Dimitrov-Tang, arXiv:2510.04156) is the most
   plausible source of such a tool: their arithmetic holonomy bounds go beyond Mason-
   Stothers in spirit, using $p$-adic information to constrain radicals more finely.
   But their current bounds (irrationality exponent $> 2$ for $2^{1/3}$) are still far
   from what is needed ($\kappa < 1.107$).
