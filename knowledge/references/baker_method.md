# Baker's Method for $2^x + 3^y + 5 = z^3$

This note develops the linear-forms-in-logarithms (Baker's method) approach to the
Kuromine equation and records the key structural finding from session 2026-06-25.

## Literature status

- This exact equation $2^x + 3^y + 5 = z^3$ does **not** appear to have a published
  resolution. The closest published work concerns *purely* exponential ternary equations
  $a^x + b^y = c^z$ (surveys: Bennett, Miyazaki–Yuan–Pink; arXiv:1808.06557).
- The standard effective tool for such equations is the **Gel'fond–Baker method**:
  lower bounds for linear forms in logarithms of algebraic numbers (Baker, Matveev for the
  archimedean place; Yu for the $p$-adic place), combined with LLL / Baker–Davenport reduction.
- General results (e.g. arXiv:1702.03424, 1808.06272) bound the *number* of solutions of
  $a^x+b^y=c^z$, but our equation has a constant term $+5$ and a perfect-cube RHS, so it is a
  three-term equation and not directly covered.

Sources:
- https://arxiv.org/pdf/1808.06557 (survey of $a^x+b^y=c^z$)
- https://arxiv.org/pdf/1702.03424 , https://arxiv.org/pdf/1808.06272 (bounds on # solutions)

## Reduction of the three-term equation to two-term linear forms

A solution with large $x,y$ is dominated by one of the two exponential terms. Assume
$x \ge 6$, $y \ge 2$ (Theorems 1–4 handle the rest; Theorem 4 already settles $x \le 5$).

**Regime A ($2^x$ dominant, $x\ln 2 \ge y\ln 3$).**
$$z^3 - 2^x = 3^y + 5 > 0,\qquad 0 < \frac{3^y+5}{2^x} \le 1 \ (\text{up to }O(3^{-y})).$$
Set $\Lambda_1 = 3\ln z - x\ln 2 > 0$. Then $e^{\Lambda_1} = z^3/2^x = 1 + (3^y+5)/2^x$, so
$$0 < \Lambda_1 = \ln\!\Big(1+\tfrac{3^y+5}{2^x}\Big) < \frac{4\cdot 3^y}{2^x}
\ \Longrightarrow\ \ln \Lambda_1 < \ln 4 + y\ln 3 - x\ln 2. \tag{A}$$
Verified at the known solution $(5,3,4)$: $\Lambda_1 = 3\ln 4 - 5\ln 2 = \ln(1+u)$ with
$u=(3^3+5)/2^5 = 1$ exactly (boundary case: the two terms are equal there).

**Regime B ($3^y$ dominant).** Symmetric, with $\Lambda_1' = 3\ln z - y\ln 3$ and
$\ln\Lambda_1' < \ln C + x\ln 2 - y\ln 3$.

A **Matveev lower bound** for the 2-log form $\Lambda_1 = |3\ln z - x\ln 2|$ gives
$$\ln \Lambda_1 > -C\,(\ln z)(\ln x),\qquad \ln z \approx \tfrac{x\ln2}{3}.$$
With $n=2$ logs the Matveev base constant is on the order of $7.7\times 10^8$, which (after
the self-consistent solve) typically yields a raw bound $x \lesssim 10^{14}$–$10^{16}$.
Combined with (A) this bounds the gap $|x\ln 2 - y\ln 3|$ but, by itself, does **not** bound
$x$ — both $x$ and $y$ can grow with the gap staying small.

## The closing mechanism requires a 3-adic linear form

The archimedean form pins down only the *difference* $x\ln 2 - y\ln 3$. To bound $x,y$
individually one needs a second, independent inequality. The natural one is **3-adic**:
$$z^3 - 2^x - 5 = 3^y \quad\Longrightarrow\quad v_3\!\big(z^3 - 2^x - 5\big) = y.$$
A $p$-adic linear form in logarithms (Yu's theorem) bounds $y = v_3(\cdots)$ from above by
$\ll (\ln z)(\ln x)$, giving a second inequality. The archimedean and 3-adic bounds together
are what close off $x,y$ to an absolute (effective) constant — after which LLL reduction +
direct search finishes the proof.

## Key structural finding (session 2026-06-25): the phantom is "$y=-3$"

The phantom solution $(x,y,z) = (5,-3,10/3)$ satisfies **exactly**
$$\Big(\tfrac{10}{3}\Big)^3 - 2^5 - 5 = \tfrac{1}{27} = 3^{-3},$$
i.e. it is literally the equation $z^3 - 2^x - 5 = 3^y$ at $x=5,\ y=-3$.

Consequences:
- **Why congruence sieving fails (made precise).** Reduction mod $m$ with $\gcd(m,3)=1$
  cannot see the sign of $y$ (it only sees $3^y \bmod m$, and $3^{-3}\bmod m$ exists).
  Reduction mod $3^n$ sees $2^x+5 \equiv z^3$, which the phantom satisfies for all $n$
  (37 is a cube mod $3^n$). So **no** finite set of congruences distinguishes the real branch
  $y\ge 2$ from the phantom branch $y=-3$.
- **Why Baker's method *can* succeed where congruences cannot.** The archimedean linear form
  $\Lambda_1$ *does* see the sign/size of $y$: it uses $|3^y| = 3^y$ as a real magnitude,
  for which $y\ge 2$ and $y=-3$ are entirely different. The archimedean place is exactly the
  information the phantom obstruction hides from every non-archimedean (congruence) place.

This reframes the HIGH-priority $p$-adic direction: the phantom is a $\mathbb{Q}_3$-point of the
fibre $x=5$, and the only place where the real branch separates from it is the **archimedean**
place. The intended proof is therefore a *two-place* (real $\times$ 3-adic) linear-forms argument,
not a purely 3-adic one.

## Concrete next steps

1. Make Regime-A/B inequality (A) fully rigorous including the $+5$ and the $O(3^{-y})$ terms.
2. Pin down explicit Matveev constants for $\Lambda_1$ (heights $h(2)=\ln2$,
   $h(z)\approx \tfrac{x\ln2}{3}$) to get a concrete numerical bound on $x$.
3. Set up the 3-adic (Yu) bound for $y=v_3(z^3-2^x-5)$ and combine.
4. After an absolute bound $x<X_0$ is in hand, LLL-reduce and finish by search
   (the search in this session already clears $x\le 600,\ y\le 300$ with no new solution).
