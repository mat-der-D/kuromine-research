# 3-adic Branch Analysis of the Kuromine Equation

**Topic:** A rigorous 3-adic reformulation of the equation in the surviving case, computed and verified during the 2026-06-25 session.

## Setup

The equation is $2^x + 3^y + 5 = z^3$. By Theorem 5, any remaining solution with
$x \ge 6$, $y \ge 2$ satisfies $x \equiv 5 \pmod{332640}$ and $y \equiv -3 \pmod{166320}$.
In particular $x \equiv 5 \pmod 6$.

## The cube root of $2^x+5$ in $\mathbb{Z}_3$

For $y \ge 2$, reducing mod 9 gives $2^x + 5 \equiv z^3 \pmod 9$. Computation:

| $x \bmod 6$ | $2^x+5 \bmod 9$ | unit cube mod 9? |
|---|---|---|
| 0 | 6 | no |
| 1 | 7 | no |
| 2 | 0 | (not a unit; $v_3=2$ or $3$) |
| 3 | 4 | no |
| 4 | 3 | no |
| 5 | 1 | **yes** |

Unit cubes mod 9 are $\{1, 8\}$. Only $x \equiv 5 \pmod 6$ makes $2^x+5$ a unit that is a cube
residue. For these $x$, $w := (2^x+5)^{1/3}$ **exists in $\mathbb{Z}_3$** and is a unit with
$w \equiv 1 \pmod 3$. (Verified by `PowerMod[2^x+5, 1/3, 3^10]` for $x = 5,11,17,23,332645$.)

The case $x \equiv 2 \pmod 6$ has $v_3(2^x+5) \in \{2,3\}$ (computed: $x=2,8,20 \to v_3=2$;
$x=14 \to v_3=3$), so $2^x+5$ is generally not a 3-adic cube — consistent with the
elimination of the $x=2$-type cases in Theorem 4.

## The valuation-splitting identity (main computed result)

Write the equation as
$$ z^3 - w^3 = 3^y, \qquad (z-w)(z^2+zw+w^2) = 3^y. $$
Here $z$ is a 3-adic unit (since $z^3 \equiv 37 \equiv 1 \pmod 3$ for the $x=5$ specialization,
and generally $z^3 = 2^x+5+3^y$ is a unit). All three 3-adic cube roots of $2^x+5$ are
$\equiv 1 \pmod 3$ and $\equiv 4 \pmod 9$ in the $x=5$ case (the three roots of $37$ mod $3^n$
coincide mod 9 and first differ mod 27). Hence $z \equiv w \pmod 9$ for the matching branch.

**Key identity:** $z^2+zw+w^2 = (z-w)^2 + 3zw$. Since $z \equiv w \pmod 3$ we have
$v_3((z-w)^2) \ge 2 > 1 = v_3(3zw)$ (as $z,w$ are units). Therefore
$$ \boxed{v_3(z^2+zw+w^2) = 1 \text{ exactly},} $$
whenever $z \equiv w \pmod 3$. (Verified over 50 random units: valuation is always 1.)

Consequently the entire factorization's 3-valuation lands on the first factor:
$$ \boxed{y = v_3(z - w) + 1.} $$

Because $z \equiv w \pmod 9$ (both $\equiv 4 \bmod 9$ in the $x=5$ case), $v_3(z-w) \ge 2$,
giving $y \ge 3$ — automatically, with equality for the known solution.

## The known solution and the phantom in this language

- **Real solution** $x=5,y=3,z=4$: with $r=37^{1/3}\in\mathbb{Z}_3$ ($r \equiv 22 \bmod 27$,
  base-3 digits $\dots121222210102$), $v_3(4-r)=2$ and $v_3(4^2+4r+r^2)=1$, summing to
  $y=3$. ✓ Note $v_3(4^3-37)=v_3(27)=3$ exactly: $z=4$ matches the 3-adic branch only to
  precision $3^3$ — it is the genuine integer, not a deep approximation.

- **Phantom** $x=5,y=-3,z=10/3$: $(10/3)^3-37 = 1/27 = 3^{-3}$, so $y=-3$. The phantom is
  the **same equation on the same branch** but with $z=10/3 \notin \mathbb{Z}_3$
  ($v_3(10/3)=-1$). This is exactly why congruences (which only test $z \in \mathbb{Z}/3^n$)
  cannot exclude it: the phantom is invisible to any test that assumes $z$ is a 3-adic integer.

## What this buys us (reformulation)

In the surviving case the problem is **equivalent** to:

> Bound the integers $z$ (3-adic units, $\equiv 4 \bmod 9$) for which the integer $z^3 - (2^x+5)$
> is a pure power of 3, i.e. for which $z$ is 3-adically close to the cube root
> $w=(2^x+5)^{1/3}\in\mathbb{Z}_3$ with $v_3(z-w) = y-1$.

This is a **3-adic Diophantine-approximation / linear-forms-in-3-adic-logarithms** statement:
$z-w$ small 3-adically while $z,w$ algebraic. This is precisely the regime of **Yu's $p$-adic
linear forms in logarithms**, the effective tool that can bound $y$ (hence $z$, hence $x$ via
size). Pure congruences cannot, because they cannot see the $v_3(10/3)=-1$ pole; a $p$-adic
*analytic* bound can.

## Numerical confirmation (this session)

Exact perfect-cube test `IntegerQ[Surd[n,3]]` (bulletproof, no floating point):
- $0 \le x,y \le 120$: only $(1,0)$ and $(5,3)$.
- $x \in \{5,11,\dots,605\}$ ($x\equiv5 \bmod 6$), $2 \le y \le 400$ (high-precision exact
  test): only $(5,3)$.

## Caveats / honesty

- The valuation identity $y = v_3(z-w)+1$ is **rigorously proven** above (it is elementary).
- The claim that this case is *equivalent* to a 3-adic linear-forms problem is a **reformulation
  framing**, not yet a theorem bounding $y$. Turning it into a finite bound requires invoking
  Yu's theorem with explicit constants — not yet done.
- The identity does **not** by itself bound $y$: 3-adically there are integers $z$ with
  $v_3(z-w)$ arbitrarily large, so the obstruction (phantom) genuinely persists at the
  congruence level. The hoped-for gain is that an *analytic* (Baker/Yu) bound separates the
  genuine integer $z$ from the 3-adic branch.
