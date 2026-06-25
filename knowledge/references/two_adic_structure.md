# 2-adic Structure of Theorem 5 Solutions

This is the 2-adic mirror of the 3-adic analysis in `factorization_approach.md`
and the Session-1 log. Computations performed with Wolfram (Session 2, 2026-06-25).

## Setup

For a Theorem-5 solution, $x = 5 + 332640k$ ($k \ge 1$) and
$y = 166317 + 166320m$ ($m \ge 0$). Note:
- $x$ is odd and $x \equiv 5 \pmod 6$ (so $3 \nmid x$, $2^x$ is not a cube).
- $y$ is always odd (166317 odd, 166320 even).

## Key 2-adic fact: $v_2(3^y + 5) = 3$ on the whole family

Computed $v_2(3^y + 5)$ for $y = 166317 + 166320m$, $m = 0,\dots,6$:
in every case $v_2(3^y + 5) = 3$ (i.e. $3^y + 5 \equiv 8 \pmod{16}$,
$\not\equiv 0 \pmod{16}$).

This is constant because $y$ is pinned to a fixed residue modulo a high power of 2:
$166320 = 2^4 \cdot 3 \cdot 5 \cdot 7 \cdot \dots$ keeps $y$ fixed mod $16$ across the
family, and $v_2(3^y+5)$ only depends on $y$ modulo a small power of 2.

## Consequence: $v_2(z) = 1$, i.e. $z \equiv 2 \pmod 4$

From $z^3 = 2^x + (3^y + 5)$ with $x = 5 + 332640k \ge 332645 \gg 3$:
$$v_2(z^3) = v_2(3^y + 5) = 3 \quad\Longrightarrow\quad v_2(z) = 1.$$

So $z$ is exactly $2 \cdot(\text{odd})$. This is consistent with, and sharper than, the
Session-1 result $z \equiv 6 \pmod 8$.

## Sharper: $z \equiv 6 \pmod{32}$

Working mod $2^x$ (with $x$ huge), $z^3 \equiv 3^y + 5 \pmod{2^x}$, and since the cube
map is a bijection on $(\mathbb{Z}/2^n)^\*$ (because $\gcd(3, 2^{n-1}) = 1$), $z$ is
**uniquely determined modulo $2^x$** by $3^y + 5$. Writing $z = 2u$ with $u$ odd,
$8u^3 \equiv 3^y + 5 \pmod{2^x}$, so $u^3 \equiv (3^y+5)/8 \pmod{2^{x-3}}$.

Computing the (unique) cube root mod a moderate power of 2 for $y = 166317$ gives
$u \equiv 3 \pmod{16}$, hence
$$z = 2u \equiv 6 \pmod{32}.$$

## Why this does NOT yield a contradiction (the soft-obstruction principle)

The cube map being a bijection mod $2^n$ means: for **every** target value $3^y + 5$,
there is a unique $z \pmod{2^x}$ solving $z^3 \equiv 2^x + 3^y + 5$. The 2-adic
equation is therefore **always solvable**. The 2-adic analysis determines $z$ but can
never refute the existence of a solution.

The same is true 3-adically (Session 1: 37 is a cubic residue mod $3^n$ for all $n$)
and modulo every prime $p$, because of the following global fact.

## The phantom is a global rational cube (root cause of all local solvability)

The phantom value is
$$2^5 + 3^{-3} + 5 = 37 + \tfrac{1}{27} = \tfrac{1000}{27} = \left(\tfrac{10}{3}\right)^3.$$
It is a **perfect cube in $\mathbb{Q}$**. Hence for every prime $p \ne 3$ it is a cube
modulo $p$ (reduce $10/3$), and for $p = 3$ the constrained value $37$ is a cube mod
$3^n$ for all $n$. Therefore **no finite set of primes (and no single prime power) can
locally obstruct the equation**. Every local condition is satisfiable.

**Conclusion.** Local/congruence/$p$-adic methods are provably insufficient *on their
own*: the obstruction is a single global rational point that is locally everywhere a
cube. A genuine proof must use a *global* tool that exploits **size** (Baker's method /
linear forms in logarithms, or a holonomy/hypergeometric effective approximation).

## Size landscape (Session 2, Wolfram)

For the smallest admissible parameters $x = 332645$, $y = 166317$:
- $x \log 2 \approx 230572$, $y \log 3 \approx 182718$.
- $2^x / 3^y \approx e^{47854}$: the $2^x$ term **dominates** $3^y$ massively.
- $z \approx 2^{x/3}$, $w = 3^{y/3}$, and $z/w \approx e^{15951}$.

So in $z^3 - w^3 = 2^x + 5$ the factorization $(z-w)(z^2+zw+w^2)$ is maximally
**unbalanced**: $z - w \approx z$ and $z^2 + zw + w^2 \approx z^2$. The hope of finding a
"small factor" to exploit is therefore void — both factors are large.

The cleaner reframing is $z^3 - 2^x = 3^y + 5$: a cube extremely close to a power of 2,
with gap $\log|\Lambda| \approx -47854$ for $\Lambda = 3\log z - x\log 2$. The
difficulty for Baker is that the height of the unknown base $z$ is enormous
($\log z \approx 76857$), which makes the Matveev lower bound (about
$-5.6\times10^{14}$) far weaker than the actual $-47854$ — no contradiction. A method
that avoids paying the full height of $z$ (e.g. effective irrationality measures for
$2^{1/3}$, or arithmetic-holonomy bounds, arXiv:2510.04156) is the realistic path.
