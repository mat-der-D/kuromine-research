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
