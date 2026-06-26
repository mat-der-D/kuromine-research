# Extended $p$-adic Structure of Theorem-5 Solutions ($A$ and $B$)

This file documents the complete 2-adic and 3-adic congruence portrait of the two
coprime factors
$$A = z - w, \qquad B = z^2 + zw + w^2, \qquad A \cdot B = 2^x + 5,$$
of a hypothetical Theorem-5 solution, where $w = 3^j$, $j = y/3$. It collects and
unifies the results of Sessions 6–9. All computations performed with Wolfram (Session 9
for the $B$ tables; earlier sessions for $A$).

## Parametrization

$$x = 5 + 332640\,k_x \quad (k_x \geq 1), \qquad y = 166317 + 166320\,k_y \quad (k_y \geq 0),$$
$$j = y/3 = 55439 + 55440\,k_y, \qquad w = 3^j.$$

Because $j, y$ are enormous, $3^j \equiv 0$ and $3^y \equiv 0$ modulo every fixed power of
3 considered below. Hence modulo $3^n$:
$$A \equiv z, \qquad B \equiv z^2, \qquad z^3 \equiv 2^x + 5 \pmod{3^n}.$$
The cube-root branch is pinned by $z \equiv 1 \pmod 3$ (since $z^3 = 2^x+3^y+5 \equiv 1 \pmod 3$).

Two universal arithmetic facts drive everything:
- $\gcd(332640, \operatorname{ord}_{3^n}(2)) = 54$ for all $n \geq 5$ (and $= \operatorname{ord}_{3^n}(2)$ for $n \leq 4$). This forces the **3-adic period $3^{n-4}$** for both $A$ and $B$ at level $3^{n-1}$.
- $166320 \equiv 0 \pmod{16}$, so $y$ is pinned mod 16 and the **2-adic structure** of $z$ (hence $A,B$) is governed by $k_y$.

---

## 3-adic portrait

### Universal residues (independent of $k_x, k_y$)

| quantity | mod 3 | mod 9 | mod 27 |
|---|---|---|---|
| $A$ | 1 | 4 | 22 |
| $B$ | 1 | 7 | 25 |

(Check $A B \equiv 22\cdot 25 = 550 \equiv 10 \pmod{27}$; and $2^x+5 \equiv 32+5 = 37 \equiv 10 \pmod{27}$. ✓)

### $A$ mod $3^{n}$, indexed by $k_x$ (Theorems I, J)

- **Theorem I.** $A \bmod 81$: $k_x \equiv 0 \Rightarrow 49$, $k_x \equiv 1 \Rightarrow 22$, $k_x \equiv 2 \Rightarrow 76$ (mod 81).
- **Theorem J.** For $n \geq 5$, $A \bmod 3^{n-1}$ is a function of $k_x \bmod 3^{n-4}$ (period $3^{n-4}$).
- 3-adic expansion: $A = [1,1,2,\,d_3(k_x),\,d_4(k_x),\dots]_3$ — fixed preamble $22$ (mod 27), then digit $k$ ($k\geq3$) tracks 3-adic digit $k-3$ of $k_x$. Bijection $\mathbb{Z}_3 \to \mathbb{Z}_3$.

9-branch $A \bmod 243$ (indexed by $k_x \bmod 9$), with the underlying $z^3 \equiv 2^x+5$:

| $k_x \bmod 9$ | $x \bmod 486$ | $2^x+5 \bmod 729$ | $z \bmod 243$ | $A \bmod 81$ |
|---|---|---|---|---|
| 0 | 5   | 37  | 211 | 49 |
| 1 | 59  | 685 | 103 | 22 |
| 2 | 113 | 604 | 238 | 76 |
| 3 | 167 | 523 | 130 | 49 |
| 4 | 221 | 442 | 22  | 22 |
| 5 | 275 | 361 | 157 | 76 |
| 6 | 329 | 280 | 49  | 49 |
| 7 | 383 | 199 | 184 | 22 |
| 8 | 437 | 118 | 76  | 76 |

### $B$ mod $3^{n}$, indexed by $k_x$ (Theorem L, Session 9)

By coprimality and $A \equiv 22 \pmod{27}$ a 3-adic unit, $B \equiv (2^x+5) A^{-1} \pmod{3^n}$,
so $B$ inherits Theorem J's lifting law verbatim:

- **$B \equiv 25 \pmod{27}$, universal.**
- **$B \bmod 81$:** $k_x \equiv 0 \Rightarrow 52$, $k_x \equiv 1 \Rightarrow 79$, $k_x \equiv 2 \Rightarrow 25$.
- **$B \bmod 243$ has period 9; $B \bmod 729$ has period 27** in $k_x$ (verified, and genuinely not period 9).
- 3-adic expansion: $B = [1,2,2,\,e_3(k_x),\dots]_3$ — fixed preamble $25$ (mod 27), then $k_x$-tracking digits. $B$ is a 3-adic **unit** ($v_3(B)=0$).

Full 27-branch table of $(A,B) \bmod 729$ indexed by $k_x \bmod 27$ (with $A\cdot B \equiv 2^x+5 \pmod{729}$ verified in every row):

| $k_x \bmod 27$ | $A \bmod 729$ | $B \bmod 729$ | $A\cdot B \bmod 729$ |
|---|---|---|---|
| 0  | 697 | 295 | 37  |
| 1  | 22  | 484 | 442 |
| 2  | 76  | 673 | 118 |
| 3  | 130 | 133 | 523 |
| 4  | 184 | 322 | 199 |
| 5  | 238 | 511 | 604 |
| 6  | 292 | 700 | 280 |
| 7  | 346 | 160 | 685 |
| 8  | 400 | 349 | 361 |
| 9  | 454 | 538 | 37  |
| 10 | 508 | 727 | 442 |
| 11 | 562 | 187 | 118 |
| 12 | 616 | 376 | 523 |
| 13 | 670 | 565 | 199 |
| 14 | 724 | 25  | 604 |
| 15 | 49  | 214 | 280 |
| 16 | 103 | 403 | 685 |
| 17 | 157 | 592 | 361 |
| 18 | 211 | 52  | 37  |
| 19 | 265 | 241 | 442 |
| 20 | 319 | 430 | 118 |
| 21 | 373 | 619 | 523 |
| 22 | 427 | 79  | 199 |
| 23 | 481 | 268 | 604 |
| 24 | 535 | 457 | 280 |
| 25 | 589 | 646 | 685 |
| 26 | 643 | 106 | 361 |

(The $A\cdot B \bmod 729$ column cycles with period 9 — it equals $2^x+5 \bmod 729$, which depends on $k_x \bmod 9$ — while $A,B$ individually need $k_x \bmod 27$. The first Theorem-5 case $k_x=1$ gives $A\equiv 22$, $B \equiv 484 \pmod{729}$.)

9-branch $B \bmod 243$ (indexed by $k_x \bmod 9$):
$$k_x \equiv 0,1,2,3,4,5,6,7,8 \;\Rightarrow\; B \equiv 52, 241, 187, 133, 79, 25, 214, 160, 106 \pmod{243}.$$

**$A\cdot B \equiv 37 \pmod{81}$ universally** (since $2^x \equiv 32 \pmod{81}$ for all $k_x$, as $\operatorname{ord}_{81}(2)=54 \mid 332640$):

| $k_x \bmod 3$ | $A \bmod 81$ | $B \bmod 81$ | $A\cdot B \bmod 81$ |
|---|---|---|---|
| 0 | 49 | 52 | 37 |
| 1 | 22 | 79 | 37 |
| 2 | 76 | 25 | 37 |

---

## 2-adic portrait

### Universal residues

| quantity | value | source |
|---|---|---|
| $v_2(3^y+5)$ | 3 | Session 2 |
| $z$ | $\equiv 6 \pmod{16}$ | Session 7 (corrects Session 2's mod 32) |
| $z$ | $\equiv 6$ or $22 \pmod{32}$ by $k_y$ parity | Session 7 |
| $y$ | $\equiv 13 \pmod{16}$ | Session 7 |
| $j$ | $\equiv 3 \pmod 4$, $\equiv 7 \pmod 8$ | Sessions 6, 7 |
| $A$ | $\equiv 11 \pmod{16}$ | Session 7 (corrects Session 6's mod 32) |
| $B$ | $\equiv 79 \pmod{432}$, i.e. $\equiv 15 \pmod{16}$ | Session 7 |

$A \bmod 2^n$ depends on $k_y \bmod 2^{n-4}$ (analogous 2-adic lifting law; Sessions 2/6/7).
The four $A \bmod 256$ branches indexed by $k_y \bmod 4$ are $\{123, 235, 91, 11\}$
(combined with the three $A \bmod 81$ branches to give Theorem K's 12 values).

---

## CRT summary (universal class)

$$A \equiv 427 \pmod{432}, \qquad B \equiv 79 \pmod{432}, \qquad A\cdot B \equiv 37 \pmod{432}.$$
($432 = 16 \cdot 27$; check $427 \cdot 79 = 33733 \equiv 37 \pmod{432}$. ✓)

---

## Why none of this yields a contradiction (the phantom, again)

The real-vs-phantom 3-adic separation is now visible on **both** factors:

| quantity | integer (Theorem-5) solution | phantom $(10/3,\,1/3)$ |
|---|---|---|
| $w=3^j$ | $v_3=j\ge2$ | $v_3=-1$ |
| $A$ | $v_3(A)=0$, $A \equiv 22 \pmod{27}$, 3-adic preamble $[1,1,2]$ | $A=3$, $v_3=1$ |
| $B$ | $v_3(B)=0$ (unit), $B \equiv 25 \pmod{27}$, preamble $[1,2,2]$ | $B=37/3$, $v_3=-1$ |

So an integer solution lives on a different 3-adic branch from the phantom for *both*
$A$ and $B$. But the separation is non-actionable: Theorems J and L show that for **every**
$k_x \in \mathbb{Z}_3$ there is a perfectly consistent 3-adic unit pair $(A,B)$ with
$A\cdot B = 2^x+5$. The maps $k_x \mapsto A$ and $k_x \mapsto B$ are bijections
$\mathbb{Z}_3 \to \mathbb{Z}_3$ (after the fixed 3-digit preambles), so no 3-adic
congruence — at any depth — can refute existence. This is the same hard $3^n$ wall
("37 is a cube mod $3^n$ for all $n$") seen from the factorization side, now confirmed
on the integer factor $B$ as well.

For every prime $\ell \neq 3$, the soft obstruction applies: the phantom reduces to
$(A,B)\equiv(3,\,37\cdot 3^{-1}) \pmod{\ell^n}$, an everywhere-valid local solution. No
$\ell$-adic constraint on $A$ or $B$ can ever be violated.

**Conclusion.** The local portrait is now complete to arbitrary 2-adic and 3-adic depth.
It is fully self-consistent and proves only that a Theorem-5 solution is *locally
admissible everywhere*. A proof of nonexistence must come from a genuinely global tool
(size / effective transcendence), which remains unavailable in the
two-comparable-S-units regime ($3^y \approx z^2$, $\kappa_{\mathrm{real}} \approx 0.62$).
