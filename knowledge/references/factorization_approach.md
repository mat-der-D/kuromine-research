# Factorization Approach: z^3 - w^3 = 2^x + 5

## Setup

For solutions $(x, y, z)$ satisfying Theorem 5 (i.e., $x = 5 + 332640k$, $y \equiv -3 \pmod{166320}$, with $k \geq 1$), the following hold:

1. **$y$ is divisible by 3.** Proof: $y \equiv -3 \equiv 0 \pmod{3}$ since $-3 \equiv 0 \pmod 3$. (Trivial but important.)

2. **$j = y/3 \equiv 2 \pmod{3}$.** Proof: $y \equiv -3 \equiv 6 \pmod{9}$, so $j = y/3 \equiv 2 \pmod 3$.

3. **Setting $w = 3^j$, the equation becomes:**
$$z^3 - w^3 = 2^x + 5$$
$$(z - w)(z^2 + zw + w^2) = 2^x + 5$$

## Coprimality

**Claim:** $\gcd(z - w, z^2 + zw + w^2) = 1$.

**Proof:**
- $z \equiv 1 \pmod{3}$ (proved: $z^3 = 2^x + 3^y + 5 \equiv 2 + 0 + 2 \equiv 1 \pmod 3$).
- $w = 3^j \equiv 0 \pmod{3}$.
- So $z - w \equiv 1 \pmod{3}$ and $z^2 + zw + w^2 \equiv z^2 \equiv 1 \pmod{3}$.
- $\gcd(z - w, w) = \gcd(z, 3^j) = 1$ (since $\gcd(z, 3) = 1$).
- If $d \mid \gcd(z-w, z^2+zw+w^2)$ then $d \mid 3w^2$ (since $z^2 + zw + w^2 \equiv 3w^2 \pmod{z-w}$).
- Since $d \mid z - w$ implies $\gcd(d, w) = 1$, and $\gcd(d, 3) = 1$ (both expressions are $\equiv 1 \pmod 3$): $d = 1$. $\square$

## Prime Factor Constraint on $z^2 + zw + w^2$

**Claim:** Every prime factor $p$ of $B = z^2 + zw + w^2$ satisfies $p \equiv 1 \pmod{3}$.

**Proof:** $p \mid z^2 + zw + w^2$ and $p \nmid 3w$ (since $\gcd(B, 3) = 1$ as $3 \nmid 2^x + 5$, and $p \nmid w$ since $\gcd(z-w, w) = 1$ and $\gcd(z^2+zw+w^2, z-w) = 1$ implies $\gcd(B, w)$ divides $\gcd(2^x+5, 3^j)$ = 1). Thus $p \nmid w$, so we can write $u = zw^{-1} \pmod{p}$ and $u^2 + u + 1 \equiv 0 \pmod{p}$. This requires $-3$ to be a quadratic residue mod $p$, which happens iff $p \equiv 1 \pmod{3}$ (for $p > 3$). $\square$

## Norm Form Interpretation

In the ring $\mathbb{Z}[\omega]$ of Eisenstein integers ($\omega = e^{2\pi i/3}$):
- $B = z^2 + zw + w^2 = N(z - \omega w)$
- The factorization $z^3 - w^3 = (z-w) \cdot N(z - \omega w)$ corresponds to the factorization in $\mathbb{Z}[\omega]$.
- Since all prime factors of $B$ are $\equiv 1 \pmod{3}$, $B$ factors completely in $\mathbb{Z}[\omega]$.
- The prime $2 \equiv 2 \pmod{3}$ stays inert in $\mathbb{Z}[\omega]$; similarly $5 \equiv 2 \pmod{3}$ stays inert.
- So $2^x + 5$ factors in $\mathbb{Z}[\omega]$ as (unit) $\times 2^x \times 5$ times contributions from primes $\equiv 1 \pmod 3$.

## Parity Constraints

- $z \equiv 6 \pmod{8}$ (computed from $z^3 \equiv 3^{166317} + 5 \equiv 24 \pmod{32}$ and $y \equiv 1 \pmod 4$).
- $w = 3^j$ with $j$ odd: $w \equiv 3 \pmod{8}$.
- $z - w \equiv 6 - 3 = 3 \pmod{8}$ (always).
- $z^2 + zw + w^2 \equiv 36 + 18 + 9 = 63 \equiv 7 \pmod{8}$ (always).
- Product: $3 \times 7 = 21 \equiv 5 \pmod{8}$. Matches $2^x + 5 \equiv 5 \pmod{8}$ for $x \geq 3$. $\checkmark$

## Connection to Thue-Mahler Equations

For fixed $k$ (hence fixed $x$ and $N_k = 2^x + 5$), the equation $z^3 - w^3 = N_k$ with $w = 3^j$ is a special case of the Thue-Mahler equation: one seeks integer solutions $(z, j)$ to the norm form equation with the constraint that $w$ is a power of $3$. By the Thue-Mahler theorem (effective via Baker), for each fixed $N_k$, there are finitely many solutions. This gives finiteness for each individual $k$.

**The remaining challenge:** Show that across all $k \geq 1$, no solutions exist (not just finiteness for each $k$).

## The $A \equiv 3 \pmod p$ phenomenon and why the primitive-divisor congruence approach fails (Session 4)

**Setup.** Because $332640 \equiv 0 \pmod 3$ and $166320 \equiv 0 \pmod 6$, the residues $x \bmod 3 \equiv 2$ and $y \bmod 6 \equiv 3$ are *constant* across the whole Theorem-5 family. Hence for any prime $p$ with $\operatorname{ord}_p(2)\mid 332640$ and $\operatorname{ord}_p(3)\mid 55440$ (and $\mid 166320$), the quantities $2^x \bmod p$, $3^y \bmod p$, and $w=3^j \bmod p$ are all *pinned* — the same for every solution in the family.

**Observation (Wolfram, Session 4).** For every prime $p \equiv 2 \pmod 3$ satisfying the order conditions (checked $p = 11,17,23,29,41,71,89,113,281$), the cube map is a bijection mod $p$ (unique $z$), and one finds **$A = z - w \equiv 3 \pmod p$ in every case.** For primes $p\equiv1\pmod3$ (three cube roots), exactly one branch gives $A\equiv 3\pmod p$, and that branch gives $B\equiv 37/3 \pmod p$.

**Explanation — this is the phantom, again.** The phantom solution $(x,y,z)=(5,-3,10/3)$ has
$$A_{\text{phantom}} = z - w = \tfrac{10}{3} - 3^{-1} = \tfrac{10}{3}-\tfrac13 = 3, \qquad B_{\text{phantom}} = \left(\tfrac{10}{3}\right)^2 + \tfrac{10}{3}\cdot\tfrac13 + \tfrac19 = \tfrac{37}{3},$$
with $A_{\text{phantom}}\,B_{\text{phantom}} = 3\cdot\tfrac{37}{3} = 37 = 2^5+5$. Since the family's $(z,w)$ reduces to the phantom's $(10/3,\,1/3)$ modulo every prime $p\neq3$, we get $A\equiv 3$ and $B\equiv 37/3 \pmod p$ automatically. **This is the soft-obstruction principle yet again:** any congruence statement about $A$ or $B$ is satisfied by the phantom, so no choice of prime $p$ (however large, however clever) can produce a contradiction by a purely local/congruence test on the factorization. The naive "find a prime $p\equiv1\bmod3$ that must/cannot divide $B$" attack is therefore dead for the same structural reason as all prior local attacks.

## The genuine integrality distinction (real vs phantom) and why it is still blocked

The phantom and an integer solution **do** differ, but only 3-adically (powers of 3 are the one place the soft obstruction does not apply):

| quantity | integer (Theorem-5) solution | phantom |
|---|---|---|
| $w = 3^j$ | $v_3(w) = j \ge 2$ (large) | $v_3(w) = -1$ |
| $A = z - w$ | $A \equiv 1 \pmod 3$, $v_3(A)=0$; $A\bmod 9 \in\{1,4,7\}$ | $A=3$, $v_3(A)=1$, $A\bmod9=3$ |
| $B = z^2+zw+w^2$ | integer, $v_3(B)=0$, all prime factors $\equiv1\pmod3$ | $B=37/3$, $v_3(B)=-1$ |

So an integer solution provably lives on a *different 3-adic branch* of $A$ than the phantom ($v_3(A)=0$ vs $1$; $A\bmod9\in\{1,4,7\}$ vs $3$). This is exactly the place a winning argument would have to exploit. **But it is blocked by the known $3^n$ wall:** $z^3\equiv 2^x+5 \equiv 1 \pmod 9$ has the self-consistent roots $z\equiv1,4,7\pmod9$, and more generally $37$ is a cubic residue mod $3^n$ for all $n$ (problem.md), so the real branch $A\bmod 3^n$ is never forced into a contradiction. The 3-adic distinction is real but non-actionable with congruences alone.

**Net Session-4 conclusion on the primitive-divisor / congruence-on-factorization lead:** it cannot succeed by itself. A winning use of the factorization must be *global* (size or genuine algebraic-number-theory input on the integer factor $B$), not a congruence.
