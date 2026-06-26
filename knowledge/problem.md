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
