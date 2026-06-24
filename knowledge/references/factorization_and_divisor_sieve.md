# Factorization approach and the divisor sieve (session 2026-06-24)

This note records new structural results about the **open region** of the Kuromine
problem, i.e. the only surviving case after Theorem 5:

$$x \equiv 5 \pmod{332640}, \qquad y \equiv -3 \pmod{166320}, \qquad x,y \text{ both large.}$$

(Smallest open point: $x = 332645$, $y = 166317$.) Throughout, $332640 = 2^5\cdot3^3\cdot5\cdot7\cdot11$.

## 1. Both exponents are forced large, with $2^x$ dominant near the boundary

At the smallest open point $x\log 2 = 230572 > y\log 3 = 182718$, so $2^x$ dominates,
but $3^y \gg 2^{2x/3}$ (the cube-gap scale), so $z$ is **not** near $2^{x/3}$.
In general a solution may sit in any of three regimes:
- (A) $2^x$ dominant, (B) $3^y$ dominant, (C) balanced $2^x\approx 3^y$.
None is forced.

## 2. Why naive Baker (linear forms in logs via the cube root) is INEFFECTIVE

The only linear form that the cube condition forces to be small is one involving
$\log z$, e.g. $\Lambda = 3\log z - x\log 2$ in regime A. But $h(z)\sim \tfrac{x}{3}\log 2$
grows **linearly** in $x$, so the Matveev/Laurent lower bound
$\log|\Lambda| \gtrsim -C\,h(z)\log x$ is too weak to beat the upper bound
$\log|\Lambda|\approx y\log3 - x\log2$. No upper bound on $x$ results.

**Root cause:** equations $a^x+b^y=c^z$ are Baker-tractable because all three bases are
*fixed* (constant height). Here the "third base" is the **variable** $z$ of the cube
$z^3$, whose height grows with the solution. This variable cube base is the essential
obstruction to Baker's method. Baker would only help in the balanced regime C, but the
cube condition does **not** force $x\log 2 - y\log 3$ to be small, so even regime C is
not directly closable this way.

## 3. The phantom is TWO-SIDED (completes the congruence dead-end)

Clean characterizations (both verified symbolically for all relevant moduli):

- **3-adic:** A unit $u$ is a cube mod $3^n$ for every $n$ **iff** $u\equiv\pm1\pmod 9$.
  In the open region $x\equiv5\pmod6$, so $2^x+5\equiv1\pmod9$, hence $2^x+5$ is a cube
  mod $3^n$ for **all** $n$. (This is exactly the "37 is a cube mod $3^n$" phantom.)
- **2-adic:** Cubing is a **bijection** on $(\mathbb Z/2^n)^\times$ (since
  $\gcd(3,2^{n-1})=1$). For the open region $v_2(3^y+5)=3$ exactly, so
  $3^y+5 = 8\cdot(\text{odd})$ is always $8\times$a cube mod $2^n$, forcing only
  $z\equiv2\pmod4$ and **no** further constraint.

So **both** the 2-adic and 3-adic local conditions are automatically satisfiable.
Congruence/local methods are genuinely exhausted from both sides.

## 4. Factorization (the productive new direction)

In the open region $y\equiv0\pmod3$ (because $3\mid166320$), so $3^y=v^3$ with
$v:=3^{y/3}$ a large power of $3$ ($9\mid v$). The equation becomes

$$z^3 - v^3 = 2^x + 5, \qquad (z-v)(z^2+zv+v^2) = 2^x+5.$$

Write $A := z-v \ge 1$ and $B := z^2+zv+v^2 = A^2+3Av+3v^2$. Then:

- $2^x+5$ is **odd** and $\equiv1\pmod3$ (since $x$ is odd), so $3\nmid 2^x+5$.
- $\gcd(A,B)\mid 3v^2$ and $3\nmid AB$, hence $\boxed{\gcd(A,B)=1}$ — a **coprime**
  factorization (this is the same mechanism that resolved the $x=5$ case in Theorem 4,
  where $z^3-w^3=37$).
- Since $B = A^2+3Av+3v^2 \ge 3v^2$ is huge, $A = (2^x+5)/B$ is comparatively small;
  $x\log2 \approx \log A + (1+2y/3)\log3$.

### 4a. $A=1$ (i.e. $z=v+1$) is eliminated
Then $3v^2+3v-4=2^x$. With $9\mid v$ this gives $2^x\equiv -4\equiv23\pmod{27}$, forcing
$x\equiv11\pmod{18}$. But $18\mid332640$ so the open region has $x\equiv5\pmod{18}$.
Contradiction. **Subcase $A=1$ has no solution in the open region.**

### 4b. Mod-27 selects an $A$-class (phantom again)
For general (large) $v$, reducing mod $3^{s+1}$ gives $A^3\equiv2^x+5\pmod{3^{s+1}}$, which
is solvable for any $s$ by the phantom (Â§3). The binding mod-27 shadow is
$A^3\equiv37\equiv10\pmod{27}$, i.e. $A\equiv13\pmod{27}$ (the only odd class coprime to 3).
So **high powers of 3 give nothing new** — consistent with the dead-end. Leverage must come
from 2-power moduli and other primes.

## 5. The divisor sieve: $2^x+5$ has restricted prime divisors

For a prime $p$, $p\mid 2^x+5$ for some $x\equiv5\pmod{332640}$ **iff** there is a residue
$r\bmod\operatorname{ord}_p(2)$ with $r\equiv5\pmod{\gcd(332640,\operatorname{ord}_p(2))}$
and $2^r\equiv-5\pmod p$. Computing this:

- **Allowed** small primes (can divide $2^x+5$): $37,47,53,59,103,139,167,173,179,263,\dots$
- **Forbidden** primes (cannot, in the open class): $5,7,11,13,17,19,23,29,31,41,43,61,67,
  71,73,79,83,89,97,101,107,109,113,127,131,137,\dots$ — almost all small primes.
- Density of allowed primes up to 5000: $\approx 81/667 \approx 0.12$.

**Consequence:** in the open region $2^x+5$ is composed **only** of "allowed" primes
(density $\sim1/8$). This is a genuine multiplicative constraint that the phantom does
**not** block (the phantom blocks cube-residue sieves; this is a divisor sieve).
It is not by itself a contradiction, but combined with the coprime factorization
$2^x+5=A\cdot B$, $A\equiv13\pmod{27}$, it is a new handle worth pushing.

## 6. Open questions / next steps
1. Can small $A\equiv13\pmod{27}$ candidates be eliminated systematically? Each fixed $A$
   gives a slice $B=A^2+3Av+3v^2=(2^x+5)/A$ — a two-variable exponential equation in
   $(v,x)=(3^{y/3},x)$ that may be killed by 2-adic / other-prime congruences not blocked
   by the phantom. If ALL small $A$ die and large $A$ is impossible (since $B\ge3v^2$ huge
   forces $A$ small), this could finish the problem.
2. Characterize the "allowed" primes via a Chebotarev/splitting condition (likely a
   condition on $\operatorname{ord}_p(2)$ and $\gcd$ with $332640$). A clean description
   would let us estimate how often $2^x+5$ can be allowed-prime-only.
3. The Thue slice: for fixed $y$, $z^3-4w^3=3^y+5$ ($w=2^{(x-2)/3}$, since $x\equiv2\pmod3$)
   is an irreducible Thue equation (4 is not a cube), effectively solvable; the difficulty
   is uniformity over $y$.
