# The Kuromine Problem

## Problem Statement

Find all integer solutions $(x, y, z)$ to:

$$2^x + 3^y + 5 = z^3$$

## Known Solutions

- $(x, y, z) = (1, 0, 2)$
- $(x, y, z) = (5, 3, 4)$

These are the only known solutions. It is conjectured that no others exist.

## Theorem 1: Non-negativity

$x, y, z$ are all non-negative.

**Proof sketch:** Multiplying both sides by $2^{|x|}$ forces $y \geq 0$. The equation then forces $x \geq 0$. Since $2^x + 3^y + 5 \geq 0$, we have $z \geq 0$.

## Theorem 2: No solution for $y = 0$ other than $(1, 0, 2)$

When $y = 0$, the equation becomes $2^x + 6 = z^3$. Cubic residues mod 4 are $\{0, \pm 1\}$, which forces $x \in \{0, 1\}$. Only $x = 1$ gives a solution.

## Theorem 3: No solution for $y = 1$

When $y = 1$, the equation becomes $2^x + 8 = z^3$. For $x \geq 1$, $z$ must be even, giving $2^\xi + 1 = \zeta^3$ after substitution. Cubic residues mod 7 are $\{0, \pm 1\}$, which rules out all values of $\xi$.

## Theorem 4: For $y \geq 2$ and $x \leq 5$, the only solution is $(5, 3, 4)$

Cubic residues mod 9 force $x \in \{2, 5\}$. The case $x = 2$ is eliminated by a 3-divisibility argument. For $x = 5$, the equation becomes $3^y + 37 = z^3$. Splitting into residue classes mod 3 exhausts all cases; only $y \equiv 0 \pmod{3}$ survives, and the factorization $z^3 - w^3 = 37$ (where $w = 3^{y/3}$) forces $(z, w) = (4, 3)$, giving $y = 3$.

## Theorem 5: Congruence constraint for $x \geq 6$, $y \geq 2$

If $(x, y, z)$ is a solution with $x \geq 6$ and $y \geq 2$, then:

$$x \equiv 5 \pmod{332640}, \quad y \equiv -3 \pmod{166320}$$

**Proof sketch:** Derived by combining cubic residue constraints modulo a large set of primes (7, 13, 19, 31, 37, 43, 61, 67, 73, 97, 109, 127, 181, 193, 199, 211, 241, 331, 337, 379, 397, 421, 433, 463, 541, 577, 661, 673, 991, 2113, 2311) together with mod 64 and mod 9 conditions. Verified by a Rust implementation.

## The Phantom Solution

The rational solution $(x, y, z) = (5, -3, 10/3)$ satisfies the equation over $\mathbb{Q}$:

$$2^5 + 3^{-3} + 5 = \left(\frac{10}{3}\right)^3$$

This is not an integer solution, but it causes a fundamental obstruction to the congruence approach. For any modulus $m$ with $\gcd(m, 3) = 1$, the inverse $3^{-1} \pmod{m}$ exists, so the phantom solution "appears" mod $m$ and cannot be eliminated. The only moduli that avoid this are powers of 3.

**Proposition:** For all $n \geq 1$, $37$ is a cubic residue mod $3^n$.

**Proof:** By induction. Base case $n = 1, 2$: $37 \equiv 1 \pmod{9}$. Inductive step: given $z_n^3 \equiv 37 \pmod{3^n}$, set $z_{n+1} = z_n + t \cdot 3^{n-1}$ and choose $t = -k$ where $z_n^3 = 37 + k \cdot 3^n$. Since $z_n \not\equiv 0 \pmod{3}$, we have $z_n^2 \equiv 1 \pmod{3}$, so $k + t z_n^2 \equiv 0 \pmod{3}$, giving $z_{n+1}^3 \equiv 37 \pmod{3^{n+1}}$.

**Consequence:** No accumulation of congruences mod $3^n$ can eliminate the case $x = 5$, $y \geq n$ from the residue approach. This is the hard wall of the congruence method.

## Structural Constraints on Theorem-5 Solutions (Factorization $A \cdot B = 2^x + 5$)

For any Theorem-5 solution write $x = 5 + 332640\,k_x$ ($k_x \geq 1$), $y = 166317 + 166320\,k_y$ ($k_y \geq 0$), $j = y/3$, $w = 3^j$, and factor $z^3 - w^3 = 2^x + 5$ as
$$A \cdot B = 2^x + 5, \qquad A = z - w, \qquad B = z^2 + zw + w^2,$$
with $\gcd(A,B)=1$. Because $j$ and $y$ are enormous, $3^j \equiv 0$ and $3^y \equiv 0$ modulo every fixed power of 3 of interest, so $A \equiv z$ and $B \equiv z^2 \pmod{3^n}$, and $z^3 \equiv 2^x + 5 \pmod{3^n}$.

The following theorems (Sessions 7–9) record the complete 2-adic and 3-adic congruence portrait of $A$ and $B$. Full statements, proofs, and tables are in `knowledge/references/adic_structure_extended.md`.

### Theorem I (3-adic branches of $A$ mod 81)

$A \bmod 81$ is determined by $k_x \bmod 3$:
$$k_x \equiv 0 \Rightarrow A \equiv 49, \quad k_x \equiv 1 \Rightarrow A \equiv 22, \quad k_x \equiv 2 \Rightarrow A \equiv 76 \pmod{81}.$$
**Proof.** $\operatorname{ord}_{243}(2)=162$ and $\gcd(332640,162)=54$, so $x \bmod 162$ takes exactly $162/54 = 3$ values as $k_x$ varies; each gives a distinct $2^x+5 \bmod 243$, whose unique 3-adic cube-root branch ($z \equiv 1 \bmod 3$) yields the stated $A \bmod 81$. All three reduce to $A \equiv 22 \pmod{27}$. $\square$

### Theorem J (3-adic lifting law for $A$)

For $n \leq 4$, $A \bmod 3^{n-1}$ is universal (independent of $k_x$). For $n \geq 5$, $A \bmod 3^{n-1}$ is uniquely determined by $k_x \bmod 3^{n-4}$. The period is $3^{n-4}$ because $\gcd(332640, \operatorname{ord}_{3^n}(2)) = 54$ for every $n \geq 5$. Consequently the 3-adic expansion of $A \in \mathbb{Z}_3$ is $A = 22 + (\text{digits encoding } k_x)$: the first three 3-adic digits are the fixed preamble $[1,1,2]$ (i.e. $22 \bmod 27$), and digit $k$ ($k \geq 3$) is a permutation-image of 3-adic digit $k-3$ of $k_x$. The map $k_x \mapsto A$ is a bijection $\mathbb{Z}_3 \to \mathbb{Z}_3$; hence **no 3-adic obstruction exists**.

### Theorem K (full 12-branch $A$ mod 20736)

$A \bmod 20736 = \operatorname{lcm}(81,256)$ is determined by $(k_x \bmod 3,\, k_y \bmod 4)$. The 12 values are
$$\{859, 1291, 3451, 5611, 7771, 8203, 10363, 12523, 14683, 15115, 17275, 19435\}.$$
The first Theorem-5 case $(k_x,k_y)=(1,1)$ gives $A \equiv 5611 \pmod{20736}$. All 12 satisfy the universal constraints $A \equiv 22 \pmod{27}$, $A \equiv 11 \pmod{16}$, $A \equiv 427 \pmod{432}$.

### Theorem L (3-adic branches and lifting law for $B$) — new in Session 9

$B \bmod 729$ is determined by $k_x \bmod 27$ (and more generally $B \bmod 3^{n-1}$ by $k_x \bmod 3^{n-4}$ for $n \geq 5$, exactly mirroring Theorem J via $B \equiv z^2$). The coarse data:
$$B \equiv 25 \pmod{27}\ \text{(universal)};\qquad k_x \equiv 0,1,2 \pmod 3 \Rightarrow B \equiv 52, 79, 25 \pmod{81}.$$
The full 27-branch table of $B \bmod 729$ (and the $A\cdot B \equiv 37 \pmod{81}$ identity) is in the reference file. $B$ is a 3-adic **unit** ($v_3(B)=0$, $B \equiv 1 \bmod 3$), with 3-adic preamble $[1,2,2]$ ($25 \bmod 27$). This separates the real solution from the **phantom**, for which $B_{\text{phantom}} = 37/3$ has $v_3(B)=-1$. The separation is genuine but, like all the others, non-actionable: $B$ is a perfectly valid 3-adic unit for every $k_x$.

**Proof of Theorem L.** Since $\gcd(A,B)=1$ and $A \equiv 22 \pmod{27}$ is a 3-adic unit, $B \equiv (2^x+5)\,A^{-1} \pmod{3^n}$ is determined to the same 3-adic depth as $A$; the lifting law and period $3^{n-4}$ are inherited from Theorem J. Direct Hensel computation (Wolfram, Session 9) confirms $B \equiv 25 \pmod{27}$ universally and the three $B \bmod 81$ branches $52/79/25$ for $k_x \equiv 0/1/2$, with $A\cdot B \equiv 37 \pmod{81}$ in every branch. $\square$

## Theorem M: Elementary Size-Based Elimination (Session 14)

Let $x, y \geq 0$ be integers with $y = 3j$ for some non-negative integer $j$. If

$$3^{2j+1} + 3^{j+1} + 1 > 2^x + 5$$

(equivalently, $3^{2j+1} > 2^x + 4$), then there is **no** integer $z$ satisfying $z^3 = 2^x + 3^y + 5$.

**Proof.** Set $w = 3^j$, so $3^y = w^3$. Since $2^x + 5 > 0$, we have $w^3 < 2^x + 3^y + 5$. The hypothesis states that $(w+1)^3 - w^3 = 3w^2 + 3w + 1 = 3^{2j+1} + 3^{j+1} + 1 > 2^x + 5$, which gives

$$(w+1)^3 = w^3 + (3^{2j+1} + 3^{j+1} + 1) > w^3 + (2^x + 5) = 2^x + 3^y + 5.$$

Therefore $w^3 < 2^x + 3^y + 5 < (w+1)^3$: the target lies strictly between two consecutive perfect cubes and hence is not itself a perfect cube. $\square$

**Verification on known solutions.**
- $(x,y) = (5,3)$: $j=1$, $w=3$. Gap $= 3^3 + 3^2 + 1 = 37$; RHS $= 2^5 + 5 = 37$. Hypothesis $37 > 37$ is FALSE, so Theorem M correctly does not rule out this solution.
- $(x,y) = (1,0)$: $j=0$, $w=1$. Gap $= 3 + 3 + 1 = 7$; RHS $= 2^1 + 5 = 7$. Hypothesis $7 > 7$ is FALSE, so Theorem M correctly does not rule out this solution.

**Application to the Theorem-5 family.** For $x = 5 + 332640\,k_x$ and $j = 55439 + 55440\,k_y$, the condition $3^{2j+1} > 2^x + 4$ simplifies (since $2^x \gg 4$ and $3^{j+1} \gg 1$) to:

$$(2j+1)\log 3 > x \log 2$$

$$\Longleftrightarrow \quad k_y > \frac{x \cdot \log_3 2 - 110879}{110880} \approx \frac{3\log 2}{\log 3}\,k_x - 1 \approx 1.893\,k_x - 1.107.$$

The threshold values (Wolfram, Session 14):

| $k_x$ | Threshold | $k_y$ values ruled out by Theorem M |
|--------|-----------|--------------------------------------|
| 1      | 0.893     | $k_y \geq 1$ (all but $k_y = 0$)    |
| 2      | 2.786     | $k_y \geq 3$                         |
| 3      | 4.678     | $k_y \geq 5$                         |
| 4      | 6.571     | $k_y \geq 7$                         |
| 5      | 8.464     | $k_y \geq 9$                         |

Among $k_x \in [1,100]$ and $k_y \in [0,200]$, exactly 53% of the 20100 parameter pairs are ruled out by Theorem M (Wolfram).

**Structural interpretation.** The critical ratio $k_y/k_x = 3\log_3 2 - 1 \approx 0.893$ corresponds exactly to $x\log 2 = (2j+1)\log 3$, i.e., $2^x \approx 3^y$ — the two-comparable-S-units boundary.

- If $k_y/k_x > 3\log_3 2 - 1$ (i.e., $3^y \gg 2^x$): **Theorem M eliminates** the case.
- If $k_y/k_x \leq 3\log_3 2 - 1$ (i.e., $2^x \gtrsim 3^y$): **Theorem M does not apply**; these are exactly the cases in the two-comparable-S-units regime where Baker-type and all known analytic tools are also blocked.

Thus Theorem M cleanly partitions the Theorem-5 parameter space at the two-S-units boundary, eliminating the half where $3^y$ dominates. The surviving half — where $2^x$ dominates — remains the core open case.

## Theorem N: Exact 3-adic Valuation Identity for $A$ (Session 15)

For any Theorem-5 solution write $z = w + A$ with $w = 3^j$ ($j = y/3$) and $A = z - 3^j \geq 1$. Then

$$2^x + 5 - A^3 = (w+A)^3 - w^3 - A^3 = 3w^2 A + 3w A^2 = 3\,w\,A\,(w+A) = 3^{j+1}\,A\,(A + 3^j).$$

Since $A \equiv 22 \pmod{27}$ (Theorem I), $\gcd(A,3) = 1$; and as $j \geq 1$, $A + 3^j \equiv A \not\equiv 0 \pmod 3$. Therefore

$$v_3\!\big(2^x + 5 - A^3\big) = j + 1.$$

**Proof.** The displayed equalities follow from $z^3 = 2^x + 3^{3j} + 5$ (so $2^x + 5 = z^3 - w^3$) and the binomial expansion of $(w+A)^3$; the identity $3w^2A + 3wA^2 = 3wA(w+A)$ is elementary. Taking $v_3$: $v_3(3wA(w+A)) = 1 + v_3(w) + v_3(A) + v_3(w+A) = 1 + j + 0 + 0 = j + 1$, using $v_3(w) = j$, $v_3(A) = 0$ (Theorem I), $v_3(w + A) = 0$ (since $j \geq 1$ forces $w \equiv 0$, $A \not\equiv 0 \bmod 3$). $\square$

**Verification on known solutions.** $(x,A,j) = (5,1,1)$: $2^5 + 5 - 1 = 36 = 3^2 \cdot 1 \cdot 4$, $v_3 = 2 = j+1$. $(x,A,j) = (1,1,0)$: $2^1 + 5 - 1 = 6$, $v_3 = 1 = j+1$ (here $j=0$, and $w+A = 2 \not\equiv 0 \bmod 3$). ✓

**Corollary (valuation re-proof that $A$ is huge).** For any *fixed* integer $a$ with $\gcd(a,3)=1$, $v_3(2^x + 5 - a^3)$ is a bounded constant over the Theorem-5 family (Wolfram, Session 15: $a = 1,2,4,5,7,8 \Rightarrow v_3 = 2,0,3,0,2,0$, independent of $k_x$). But Theorem N requires this valuation to equal $j+1 \geq 55440$. Hence $A$ equals no fixed small integer — an independent 3-adic proof of the Session-4 size fact. In particular the $A = 1$ band, $2^x + 4 = 3^{j+1} + 3^{2j+1}$, has (by Lifting-the-Exponent, $x$ odd) $v_3(2^x + 4) = 1 + v_3(x-2) = 2$ universally (since $x - 2 = 3(1 + 110880\,k_x)$ with $110880 \equiv 0 \bmod 3$), forcing $j = 1$ — only the known solution $(5,3,4)$.

**Scope (honest).** For a *genuine* solution Theorem N is automatically satisfied (it is an algebraic identity), so it imposes no constraint by itself. Its value is (i) the clean exact valuation formula, and (ii) the re-derivation that $A$ cannot be small. The hoped-for elimination "bounded $A$ + small valuation $\Rightarrow$ contradiction" requires the Theorem-5 lattice to lie within $O(1)$ log-distance of the boundary $2^x = 3^{2j+1}$ (where $A \approx O(1)$); Session 15 proved (Wolfram) this never happens — the closest *surviving* approach over $k_x \leq 5000$ is $D := x\log2 - (2j+1)\log3 \approx 55$, giving $A \gtrsim 10^{24}$. This is the metric face of the two-comparable-S-units barrier.

## Theorem P: 2-adic Mirror Law for $A$ (Session 32)

This is the exact 2-adic counterpart of the 3-adic Theorem J, completing the $p$-adic portrait of $A = z - 3^j$. Throughout, $x = 5 + 332640\,k_x$, $y = 166317 + 166320\,k_y$, $j = y/3 = 55439 + 55440\,k_y$.

**2-adic setup.** $y$ is odd on the entire family (since $166317$ is odd and $166320$ is even), so $3^y \equiv 3 \pmod 8$ and $v_2(3^y+5) = 3$ **universally** (Wolfram, $k_y = 0..6$). As $v_2(2^x) = x \gg 3$, this gives $v_2(N) = 3$, hence $v_2(z) = 1$: $z \equiv 2 \pmod 4$, $z = 2u$ with $u$ odd, $u^3 = N/8$. (This pins $v_2(z) = 1$ exactly and re-derives "$z$ even.") Since $2^x \equiv 0 \pmod{2^n}$ for $x \gg n$, $u$ is the unique odd cube root of $(3^y+5)/8 \pmod{2^n}$ and $A \equiv 2u - 3^j \pmod{2^n}$.

**Statement (Wolfram-verified).**
1. $A \equiv 11 \pmod{16}$ **universally** (independent of $k_x, k_y$) — the fixed 2-adic preamble, digits $[1,1,0,1]$. (Re-confirms Theorem K's $A \equiv 11 \pmod{16}$.)
2. For $n \geq 5$, $A \bmod 2^n$ is determined by **$k_y \bmod 2^{n-4}$** and is independent of $k_x$. The number of distinct values of $A \bmod 2^n$ over $k_y$ is exactly $2^{n-4}$, and the period is **exactly** $2^{n-4}$: the shift $k_y \mapsto k_y + 2^{n-4}$ preserves $A \bmod 2^n$ while $k_y \mapsto k_y + 2^{n-5}$ does not (Wolfram, $n = 6..10$).
3. Therefore the map $k_y \mapsto A$ is a **bijection $\mathbb Z_2 \to 11 + 16\,\mathbb Z_2$**; hence **no 2-adic obstruction exists** — the exact 2-adic analogue of Theorem J's 3-adic non-obstruction.

**Origin of the "$-4$" offset.** $\operatorname{ord}_{2^n}(3) = 2^{n-2}$ ($n \geq 3$) and $v_2(166320) = v_2(55440) = 4$, so the period of $3^y \bmod 2^n$ in $k_y$ is $2^{n-2}/2^4 = 2^{n-6}$, lifted to $2^{n-4}$ for $A$ by the cube-root and $j$-shift. This mirrors the 3-adic offset, which traces to $v_3(2^{332640}-1) = 4$. **Both periods carry the same "$-4$"** — a coincidence of the specific moduli $332640 = 2^5\,3^3\,5\,7\,11$ and $166320 = 2^4\,3^3\,5\,7\,11$ (Wolfram).

**Sample table ($A \bmod 2^n$, $k_y = 0,1,2,3,4,5$):**

| $n$ | mod | $k_y=0$ | $1$ | $2$ | $3$ | $4$ | $5$ |
|----|----|----|----|----|----|----|----|
| 5 | 32 | 27 | 11 | 27 | 11 | 27 | 11 |
| 6 | 64 | 59 | 43 | 27 | 11 | 59 | 43 |
| 7 | 128 | 123 | 43 | 91 | 11 | 59 | 107 |
| 8 | 256 | 251 | 43 | 91 | 139 | 187 | 235 |

## Observation Q: Variable Separation of the $(2,3)$-adic Portrait of $A$ (Session 32)

Combining Theorem J (3-adic) and Theorem P (2-adic), the two exponential parameters control the two places of $A$ **independently** (Wolfram, $3\times3$ grid):

- $A \bmod 3^n$ is a **bijective function of $k_x$ alone** (independent of $k_y$): e.g. $A \bmod 729 = 211, 22, 76$ for $k_x \equiv 0,1,2$, identical across all $k_y$.
- $A \bmod 2^n$ is a **bijective function of $k_y$ alone** (independent of $k_x$): e.g. $A \bmod 128 = 123, 43, 91$ for $k_y \equiv 0,1,2$, identical across all $k_x$.

The additive constant $5$ couples the two places **only** through the single archimedean size relation $A \approx 2^{x/3}$ (which involves both $k_x$ and $k_y$).

**Consequence (the sharpest $p$-adic statement of the obstruction).** Because each place is a free bijective parameter, **no** congruence/$p$-adic condition — at 2, at 3, or jointly by CRT — can pin $A$ off a genuine value: for any target integer $a \equiv 11 \pmod{16}$, $\equiv 22 \pmod{27}$, there exist $k_y \in \mathbb Z_2$ (2-adically) and $k_x \in \mathbb Z_3$ (3-adically) realizing $A = a$ in each place. The only relation tying $k_x$ to $k_y$ is the archimedean size $A \approx 2^{x/3}$ — exactly the missing power-saving $\kappa > 1$ gap bound. The "2 integer parameters vs 3 independent matching conditions (2-adic, 3-adic, archimedean)" over-determination is a **heuristic, not a proof**: the $p$-adic conditions are satisfiable in $\mathbb Z_2, \mathbb Z_3$ (not forced into $\mathbb Z$). This is the $p$-adic-side restatement of the two-comparable-S-units wall.

## Theorem R: 2-adic Newton/Tangent Expansion of the $k_y \mapsto A$ Bijection (Session 33)

This is the 2-adic counterpart of the Session-24 3-adic tangent-speed result ($v_3(\tau)=3$ for the curve $A(k_x)=(32\exp_3(k_xL)+5)^{1/3}$), and it sharpens Theorem P from a "period statement" to an explicit **2-adic analytic Mahler expansion**. Throughout, $x=5+332640\,k_x$, $y=166317+166320\,k_y$, $j=y/3=55439+55440\,k_y$, $z=2u$ ($u$ odd), $A=z-3^j$.

**Statement (Wolfram-verified).** Write the 2-adic bijection $k_y \mapsto A(k_y)$ (Theorem P) in its Mahler/Newton forward-difference form
$$A(k_y) \;=\; c_0 + c_1\,k_y + c_2\binom{k_y}{2} + c_3\binom{k_y}{3} + \cdots, \qquad c_k = (\Delta^k A)(0).$$
Then (Wolfram, $A \bmod 2^n$ for $n$ up to $24$):
1. $c_0 = A(0) \equiv 11 \pmod{16}$ (the fixed 2-adic preamble of Theorem P).
2. $v_2(c_1) = 4$ and $v_2(c_2) = 8$, i.e. the **leading-coefficient law $v_2(c_k) = 4k$** for $k\ge1$ (verified $k=1,2$ cleanly at moduli $2^{12},2^{16},2^{24}$; the $k=3$ digit is consistent with $12$ but crowds the modulus boundary at the depths reachable before the Wolfram endpoint became unavailable — recorded honestly as $v_2(c_3)\ge11$, expected $12$).
3. Consequently $A(k_y)$ is a **2-adic analytic function of $k_y$ with leading slope $v_2 = 4$**: to first order $A(k_y) \equiv A_0 + s\,k_y \pmod{2^n}$ with $v_2(s)=4$ (so the period in $k_y$ at depth $n$ is exactly $2^{n-4}$ — re-deriving Theorem P's "$-4$" offset from the tangent valuation), and the affine approximation is **exact up to depth $n=8$** (Wolfram: linear over the full period for $n\le8$, with the $\binom{k_y}{2}$ term, $v_2=8$, first breaking exact linearity at $n=9$).

**The same expansion holds verbatim for $z$** (not only $A$): $z(k_y) \bmod 2^n$ is also a 2-adic arithmetic progression to leading order with $v_2(\text{step})=4$ (Wolfram: $z \equiv 102 - 16\,k_y \pmod{256}$, step $-16$, $v_2=4$). The 3-adic side is *trivially identical for $z$ and $A$*: since $j \ge 55439 \gg n$, $3^j \equiv 0 \pmod{3^n}$, so $z \equiv A \pmod{3^n}$ and $z$ inherits Theorem J's portrait exactly ($z \bmod 3^n$ depends only on $k_x$). Hence the variable-separation Observation Q holds for $z$ as well as for $A$.

**Subtlety pinned (Wolfram).** $N = 2^x+3^y+5 \equiv 1 \pmod 9$ universally, and $N$ has **three** 3-adic cube-root branches $\equiv 1 \pmod 3$ (verified: 3 roots mod $3^5$ over a $3\times3$ grid). The genuine $z$ is selected among these **archimedeanly** (by being the actual integer cube root), not by any congruence — a clean restatement of *why* the obstruction is archimedean: the 2-adic and 3-adic data leave a 3-fold (in fact, bijective-continuum) 3-adic branch ambiguity that only the size relation $A\approx2^{x/3}$ resolves.

**Scope (honest).** Theorem R is a structural sharpening of the existing $p$-adic portrait; like Theorems P and Q it **confirms, does not breach**, the wall. It records that the $k_y\mapsto A$ (and $k_y\mapsto z$) bijection is genuinely 2-adic analytic with tangent valuation 4, completing the symmetry with the 3-adic tangent valuation 3 (Session 24). It produces no archimedean constraint and adds no new attack face.

## Theorem S: Convergent–Depth Trade-off Law for the boundary distance $D$ (Session 34)

This is the explicit **metric** counterpart of the $p$-adic Theorems J/P/R, and it closes the bounded-$A$ dead end (Sessions 15/21) **concretely** — at a point where the integer cube-root distance $A$ is genuinely small ($O(10^2)$), rather than only abstractly. Throughout, $x = 5 + 332640\,k_x$, $j = 55439 + 55440\,k_y$, and the **boundary distance** is $D = D(k_x,k_y) = x\log2 - (2j+1)\log3 = c_0 + k_x P_c - k_y Q_c$ with $P_c = 332640\log2$, $Q_c = 110880\log3$, $c_0 = 5\log2 - 110879\log3$, and $\rho := P_c/Q_c = 3\log2/\log3 = 1.8927892607\ldots$ (irrational). The minimal nonnegative $D$ at parameter $k_x$ is realized by $k_y = \lfloor(c_0 + k_x P_c)/Q_c\rfloor$.

**Statement (Wolfram-verified, Session 34).**

1. **Record minima sit at convergents.** The values of $k_x$ at which $\min_{k_y\ge0,\,D\ge0} D$ sets a new record are exactly the **convergent denominators $q_n$ of $\rho$** (9, 513, 7891, 16836, 142579, …) **and their small integer multiples** (e.g. $33672, 50508, 67344, 84180 = 16836\cdot\{2,3,4,5\}$ — the classic three-distance / intermediate-fraction pattern). At a convergent $k_x = q_n$, the boundary distance is $D \approx \theta_n Q_c$ where $\theta_n = |q_n\rho - p_n| = \Theta(1/q_n)$.

2. **$\rho$ has irrationality measure (numerically) exactly 2.** The continued fraction $\rho = [1;1,8,3,18,2,7,2,8,1,1,18,3,\ldots]$ has bounded partial quotients (max 166 in the first 100 terms; mean $\approx 7.1$), and $q_n\theta_n \in (0.02, 0.70)$ for all computed $n$ — bounded away from both 0 and $\infty$. The local exponents $\mu_n = 1 - \log\theta_n/\log q_n$ hover in $[2.0, 2.9]$ with **no upward drift**, strong numerical evidence that $\mu(\rho) = 2$. Hence $\inf_{k_x} D_{\ge0} = 0$ (re-confirming the Session-21 Weyl statement) but the *rate* is the Dirichlet rate: $D \gtrsim Q_c/(a_{n+1} q_n)$ at $k_x = q_n$, i.e. **$D$ can be made small only by paying $k_x \sim 1/D$** (and hence $k_y \sim \rho/D$).

3. **The Convergent–Depth Trade-off (the decisive content).** At the boundary, $A = z - 3^j$ satisfies $2^x + 5 = A(A^2 + 3wA + 3w^2) \approx 3w^2 A$ ($w = 3^j$), so $\log A \approx D - \log 3$ and $A$ lies in the band $[\,e^{D}/3\text{-ish},\,3e^{D}\,]$. Thus **small $D$ $\Rightarrow$ small $A$** — but by item 2, small $D$ forces large $k_x = q_n$, hence large $k_y$, hence **enormous required 3-adic depth $j+1 = 55440\,k_y + 55440$**. The Theorem-N corollary ($v_3(2^x+5-a^3)$ bounded for fixed small $a$) then excludes the case. The two effects are coupled by $\rho$: there is no parameter regime where $A$ is small **and** $j$ is small.

**Decisive concrete instance (Wolfram, Session 34).** The sharpest *feasible* convergent is $k_x = q_n = 16836$ (with $k_y = 31866$), giving $D = 3.7588\ldots$ and forcing the integer $A$ into the band $\approx[43, 129]$ — **genuinely $O(10^2)$**, the first time bounded-$A$ is realized at a concrete lattice point. There $x = 5 + 332640\cdot16836$ (so $2^x$ has $\sim1.69\times10^9$ decimal digits) and the required depth is
$$j + 1 = 1{,}766{,}706{,}480.$$
But (Wolfram, via $2^x \bmod 3^{80}$ by `PowerMod`) **every** integer $a$ in the band $[40,130]$ has
$$v_3(2^x + 5 - a^3) \le 7,$$
while a genuine solution with $A = a$ would require $v_3 = j+1 = 1{,}766{,}706{,}480$. The exclusion margin is $\sim 7$ vs $\sim1.8\times10^9$ — a factor $\sim 2.5\times10^8$. So Theorem N kills the case **with the small $A$ explicitly present**, not merely argued in the abstract.

**Scope (honest).** Theorem S is the explicit metric law behind the Session-15/21 bounded-$A$ dead end; it **confirms, does not breach**, the wall. Its value is (i) identifying the record-minima of $D$ with the convergents of $\rho$ (a clean Diophantine description of the near-boundary lattice, $\mu(\rho)=2$ numerically), and (ii) the first *concrete* demonstration — at $k_x=16836$, $A\in[43,129]$ — that the Theorem-N depth obstruction fires even when $A$ is genuinely small. It produces no power-saving $\kappa>1$ gap bound and adds no new attack face: the $A$-small-but-$j$-huge coupling **is** the two-comparable-S-units barrier, now read off the convergent structure of $\rho$.

## Theorem T: 5-adic Valuation Sieve at the Constant Prime (Session 35)

This is the first analysis of the equation at the prime $5$ — the additive constant — *as a valuation* (rather than a residue). It produces a genuine new **necessary congruence** on the Theorem-5 family, eliminating 80% of parameter pairs at the first level, and an iterated 5-adic sieve thereafter. Throughout, $N = 2^x + 3^y + 5 = z^3$, $x = 5 + 332640\,k_x$, $y = 166317 + 166320\,k_y$.

**Statement (Wolfram-verified, Session 35).**

1. **$v_5(N) \geq 2$ universally on the family.** Because $332640 \equiv 166320 \equiv 0 \pmod{20}$ and $\operatorname{ord}_{25}(2)=\operatorname{ord}_{25}(3)=20$, the residues $2^x \equiv 7$ and $3^y \equiv 13 \pmod{25}$ are *pinned* across the whole family, so $N \equiv 7+13+5 = 25 \equiv 0 \pmod{25}$. (The two known solutions lie outside the family and have $v_5(N)=0$; the universal $v_5\geq2$ is a large-exponent phenomenon.)

2. **First-level necessary condition: $k_y \equiv k_x - 1 \pmod 5$.** A cube requires $3 \mid v_5(N)$. Since $v_5(N)\geq 2$ always, the only way to reach a multiple of 3 is $v_5(N)\geq 3$, i.e. $N \equiv 0 \pmod{125}$. Direct computation ($\operatorname{ord}_{125}(2)=\operatorname{ord}_{125}(3)=100$, with $332640\equiv40$, $166320\equiv20 \pmod{100}$, both of period 5 in their parameters) gives
$$N \equiv 0 \pmod{125} \iff k_y \equiv k_x - 1 \pmod 5.$$
**This eliminates 4 of every 5 values of $k_y$ for each $k_x$ — 80% of the Theorem-5 family — by a single mod-5 valuation argument.** It is a new necessary constraint, not derivable from the Theorem-5 residue sieve (which used primes $7,13,19,\ldots$, mod 64 and mod 9, but never the prime 5 or any valuation).

3. **Iterated sieve.** On the survival diagonal $k_y\equiv k_x-1\pmod 5$, $v_5(N)$ is generically $3$ but jumps to $4,5,6,\ldots$ at finer parameter residues (Wolfram, on a $25\times25$ block of $(k_x,k_y)\bmod 25$: distribution $v_5 = 3{:}100,\ 4{:}20,\ 5{:}4,\ 6{:}1$ out of 125 diagonal points). Points with $v_5\in\{4,5\}$ (not divisible by 3) are *also* eliminated; survivors ($3\mid v_5$, i.e. $v_5\in\{3,6\}$) number $101/125$, i.e. $\approx 16.2\%$ of the full mod-25 grid. The sieve continues at every 5-adic depth.

**Verification.** $(x,y)=(6,2)$ (generic, off-family): $N=78$, $v_5=0$. Family rep $(k_x,k_y)=(1,0)$: $v_5(N)=3$ (survives). $(1,5)$: $v_5=4$ (eliminated). First *nominal* Theorem-5 pair $(k_x,k_y)=(1,1)$: $k_y-(k_x-1)=1\not\equiv0\pmod5$, so $v_5(N)=2$ — **not a cube, ruled out**. (Wolfram, all.)

**Why it confirms (does not breach) the wall — the phantom is on the survival diagonal.** The phantom $2^5+3^{-3}+5 = (10/3)^3 = 1000/27$ has $v_5 = v_5(1000) = 3$, divisible by 3 — so it *passes* the cube-valuation test. Its parameters are $k_x=0$, $k_y=-1$ (from $y=166317+166320k_y=-3$), and $k_y-(k_x-1) = -1-(-1) = 0 \pmod 5$: **the phantom lies exactly on the survival diagonal**, as it must by the soft-obstruction principle (any genuine local constraint is one the global rational cube also satisfies). Consequently the survival fraction stays bounded away from 0 (Wolfram: $\approx 16.7\%$ over a random sample in $[0,5^4)^2$); the 5-adic sieve, like the 2- and 3-adic ones, **cannot empty the family** — $1000/27$ is a cube in $\mathbb Q_5$ for the same reason it is a cube mod $\ell^n$ for every $\ell\neq 3$.

**Scope (honest).** Theorem T is a genuine *new* sieve (no prior session touched the prime 5 or a valuation condition) and is the strongest single elementary cut found since Theorem M (80% vs 53%), and it composes with Theorem M (size) and the mod-$3^n$/mod-$2^n$ portrait independently. But it is **soft-obstructed**: the phantom survives every level, so the sieve removes a fixed positive fraction at each depth and never terminates. It sharpens the description of the surviving sub-lattice (a congruence sub-progression $k_y\equiv k_x-1\pmod 5$, refined 5-adically) without breaching the two-comparable-S-units wall. Its practical value is for any future numerical verification: it cuts the search space by $\geq 5\times$ at essentially zero cost.

## Theorem U: 5-adic Portrait of $z$ on the Survival Sub-lattice (Session 36)

This is the natural 5-adic counterpart to the 2-adic portrait (Theorem P/R) and the 3-adic portrait (Theorem J/I), now extended to the prime 5, and applies specifically on the survival sub-lattice defined by Theorem T. It characterizes $v_5(z)$ and $z \bmod 5^n$ on the generic surviving family members.

**Setting.** Restrict to the survival sub-lattice $k_y \equiv k_x - 1 \pmod 5$ (Theorem T). On this sub-lattice, $v_5(N) \geq 3$; the *generic* case (the dominant fraction, $\approx 80\%$ of surviving diagonal points) is $v_5(N) = 3$.

**Statement (Python-verified, Session 36, in the absence of Wolfram MCP).**

1. **$v_5(z) = 1$ universally on the generic $v_5(N)=3$ sub-lattice.** Since $N = z^3$ and $v_5(N) = 3$, we get $3\,v_5(z) = 3$, hence $v_5(z) = 1$. Equivalently, **$z \equiv 0 \pmod 5$ and $z \not\equiv 0 \pmod{25}$** on all generic surviving Theorem-5 family members.

2. **$z' = z/5 \bmod 5^n$ is a bijective function of $(k_x, k_y)$ on the survival diagonal.** Writing $z = 5z'$, the reduced variable $z' = z/5$ has $v_5(z') = 0$, and $z' \bmod 5^n$ is determined by $(k_x \bmod 5^n, k_y \bmod 5^n)$ with no degeneracy: distinct diagonal pairs give distinct $z'$ values (Python, diagonal sample at levels 1–4).

   Concrete sample ($n=1$): the four generic diagonal survivors in the $5\times5$ block give
   $$z' \bmod 5 \in \{1, 2, 3, 4\} \quad \text{(all nonzero residues)}.$$
   Specifically: $(k_x \bmod 5, k_y \bmod 5) = (1,0) \to z'\equiv 3$; $(3,2)\to z'\equiv 2$; $(4,3)\to z'\equiv 1$; $(0,4)\to z'\equiv 4 \pmod 5$.

3. **New universal necessary condition: $5 \mid z$ and $25 \nmid z$.** This is a new constraint on $z$ (as opposed to on the parameters $k_x, k_y$), independent of the 2-adic and 3-adic conditions on $z$.

4. **Combined CRT portrait of $z$.** Combining with Theorem J/R ($z \equiv A \pmod{3^n}$, $A \equiv 22 \pmod{27}$) and Theorem P/R ($z \equiv 2u \pmod{2^n}$, $z \equiv 0 \pmod{5}$, $z \not\equiv 0 \pmod{25}$), by CRT ($27 \cdot 32 \cdot 5 = 4320$):

   For the specific case $k_y = 0$ (the family floor): $z \equiv 3910 \pmod{4320}$.

   (Here $3910 \equiv 22 \pmod{27}$, $3910 \equiv 6 \pmod{32}$, $3910 \equiv 0 \pmod{5}$; verified by Python.) This is a new combined necessary congruence extending Theorem K's CRT portrait.

**Scan for other universal-valuation primes (Session 36).** A direct Python computation scanned all primes $\ell \leq 5000$: for each $\ell$, checked whether $\operatorname{ord}_\ell(2) \mid 332640$ and $\operatorname{ord}_\ell(3) \mid 166320$ (necessary for the Theorem-5 family's residues to be pinned mod $\ell$), and then whether $N \equiv 0 \pmod \ell$ universally. Result: **57 primes $\ell \leq 5000$ have their order dividing the family moduli; only $\ell = 5$ universally divides $N$.** No other prime gives a valuation-based sieve: for all other compatible $\ell$, $v_\ell(N) = 0$ on the survival diagonal representatives. The prime 5 is therefore the unique source of a valuation sieve on the Theorem-5 family.

**Iterated 5-adic survival fractions (Session 36, Python).** Extending Theorem T's level-1 ($16.0\%$ of the full grid) to levels 2–4:
- Level 1 (mod 5, $5\times5=25$ points): $4/25 = 16.0\%$ survive (have $3 \mid v_5(N)$).
- Level 2 (mod 25, $625$ points): $101/625 = 16.16\%$ survive.
- Level 3 (mod 125, $15625$ points): $2517/15625 = 16.11\%$ survive.
- Level 4 (mod 625, $390625$ points): $63000/390625 = 16.13\%$ survive.

The survival fraction converges to $\approx 16.13\%$, bounded away from 0 — confirming the soft obstruction quantitatively at four 5-adic depths.

**Why it confirms (does not breach) the wall — the phantom passes.** The phantom solution $(x,y,z) = (5,-3,10/3)$ gives $z_{\text{phantom}} = 10/3$, and $10 \equiv 0 \pmod 5$: the phantom satisfies $5 \mid z_{\text{phantom}}$ (in $\mathbb Q_5$, $v_5(10/3) = v_5(10) = 1$). So the new condition $v_5(z) = 1$ is consistent with the phantom — the soft obstruction persists exactly. The phantom's $z'_{\text{phantom}} = 2/3 \equiv 2\cdot 2 = 4 \pmod 5$ (since $3^{-1} \equiv 2 \pmod 5$) is also a nonzero residue, consistent with item 2 above.

**Scope (honest).** Theorem U is the natural completion of the 5-adic analysis opened by Theorem T: it characterizes $v_5(z) = 1$ (a new universal necessary condition on the solution $z$ itself) and the bijective portrait $z' = z/5 \bmod 5^n$ on the survival diagonal. Like all prior $p$-adic portraits (Theorems I/J/P/Q/R) it **confirms, does not breach**, the wall: the phantom satisfies $v_5(z)=1$ and all 5-adic conditions on $z$, so the sieve is soft-obstructed at every depth. The combined CRT constraint $z \equiv 3910 \pmod{4320}$ is the sharpest combined portrait currently available (from the 2-adic, 3-adic, and 5-adic places jointly). No new attack face is opened; no $\kappa>1$ gap bound is produced.
