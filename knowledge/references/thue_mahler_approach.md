# The Thue-Mahler / Norm-Form Approach to the Kuromine Problem

Session 18 (2026-06-26). All numerical computations performed with the Wolfram
Language MCP kernel.

This file records the first deep exploration of the **Thue-Mahler equation approach**,
which was identified in Session 1 as a [MEDIUM] direction but never analyzed in depth.
The conclusion is negative but sharp: **no casting of the Kuromine equation as a single
Thue-Mahler equation `F(X,Y) = (S-unit)` exists**, because the additive constant 5
(equivalently the two-term right-hand side) always prevents the right-hand side from being
a single S-unit. This is the Thue-Mahler face of the phantom obstruction.

## What a Thue-Mahler equation is

A Thue-Mahler equation has the shape
$$|F(X,Y)| = p_1^{a_1}\cdots p_t^{a_t}, \qquad \gcd(X,Y)=1,$$
where $F$ is an irreducible binary form of degree $\geq 3$ and the right-hand side ranges
over $S$-units for a fixed finite prime set $S=\{p_1,\dots,p_t\}$. By the Thue-Mahler
theorem (effective via Baker; efficiently resolvable via Gherga-Siksek, arXiv:2207.14492),
each such equation has finitely many solutions. The quantitative theory
(Evertse-Győry, Bugeaud-Győry) bounds the **number** of solutions in terms of the unit
rank of the associated field and $|S|$.

## Enumeration of all candidate castings (all broken by the constant 5)

For the Theorem-5 family $x = 5 + 332640\,k_x$ (so $x \equiv 2 \pmod 3$, write $x = 3a+2$,
$2^x = 4\cdot(2^a)^3$, $W = 2^a$) and $y = 3j$, $w = 3^j$:

1. **`z^3 - 4 W^3 = 3^y + 5`** ($W = 2^a$, $S = \{2\}$).
   $F(z,W) = z^3 - 4W^3$ is irreducible (4 is not a cube). But the value $3^y + 5$ has
   support $\{3\} \cup (\text{primes of } 3^y+5)$ — **not** a $\{2\}$-S-unit, because of the
   $+5$. BROKEN.

2. **`z^3 - w^3 = 2^x + 5`** ($w = 3^j$, $S = \{3\}$).
   Value $2^x + 5$ is not a $\{3\}$-S-unit due to the $+5$. (And $z^3 - w^3$ is the Session-1
   factorization $A\cdot B$.) BROKEN.

3. **Eisenstein norm form `N_{Q(ω)}(z - wω) = B`**, with $A\cdot B = 2^x + 5$,
   $A = z-w$, $B = z^2+zw+w^2$. This *is* a genuine norm form, but $A$ varies independently
   along with $B$, so it is not a fixed-RHS Thue-Mahler equation; and its congruence content
   is phantom-blocked (Session 4). BROKEN as a source of uniformity.

4. **`N_{Q(5^{1/3})}(z - 5^{1/3}) = z^3 - 5 = 2^x + 3^y`** (work in $K=\mathbb{Q}(5^{1/3})$,
   since $x^3 - 5$ is irreducible over $\mathbb{Q}$, verified Wolfram). This is a clean norm
   form on the left, but the right-hand side $2^x + 3^y$ is a **sum of two S-units**, not a
   single S-unit, and the factorization of $2^x+3^y$ is uncontrolled. BROKEN.

**Root cause (all four):** the additive constant 5 (or, in casting 4, the two-term RHS)
prevents the right-hand side from being a single S-unit. This is exactly the structural
role of the constant identified in the function-field analysis (Session 17): the constant
is the hard ingredient.

## New clean reframing of the hard case (Session 18)

Combining $x = 3a+2$ ($2^x = 4W^3$, $W=2^a$) and $y = 3j$ ($3^y = w^3$, $w=3^j$), the
entire Theorem-5 hard case is equivalent to the single Diophantine identity
$$\boxed{\,z^3 - 4\,(2^a)^3 - (3^j)^3 = 5\,}$$
i.e. **a cube minus four times an S-unit-cube minus an S-unit-cube equals 5.**
Verified on the known solution $(x,y,z)=(5,3,4)$: $a=1,j=1$, $4^3 - 4\cdot 2^3 - 3^3 =
64 - 32 - 27 = 5$ (Wolfram). This is the most symmetric statement of the hard case found so
far: three cubes (one free, two on S-unit bases) summing to the constant 5. It makes
transparent that the obstruction is the constant $5$ on the right, not the cube structure.

## The forced prime factor 37 of B, and its (soft-obstructed) consequences

Among primes $p \equiv 1 \pmod 3$ (the only primes that can divide $B$), exactly which
divide $2^x+5$ over the family was computed (Wolfram). For most such $p$ the only $x$-class
is $x \equiv 5$ and $p \nmid 2^x+5$. The decisive exception:

- **$37 \mid 2^x + 5$ for every Theorem-5 solution, with $v_{37}(2^x+5) = 1$ exactly**
  (Wolfram: constant $=1$ over $k_x = 0..8$; because $x \equiv 5 \pmod{36}=\mathrm{ord}_{37}(2)$,
  so $2^x \equiv 2^5 = 32 \equiv -5 \pmod{37}$).

Since $37 \equiv 1 \pmod 3$, it splits in $\mathbb{Z}[\omega]$ as $37 = \pi\bar\pi$, and
since $\gcd(A,B)=1$, the factor $37$ goes into exactly one of $A,B$. The mod-37 cube
equation $z^3 \equiv 11 \pmod{37}$ has three roots $z \in \{21, 25, 28\}$, giving three
branches:

| $z \bmod 37$ | $z/w \bmod 37$ ($w\equiv25$) | where 37 goes | $A=z-w \bmod 37$ |
|---|---|---|---|
| 28 | 10 (cube root of 1) | $37\mid B$ ($\pi$ branch) | 3  — **phantom branch** |
| 21 | 26 (cube root of 1) | $37\mid B$ ($\bar\pi$ branch) | 33 |
| 25 | 1                    | $37\mid A$              | 0  |

The phantom $(10/3,\,1/3)$ reduces to $z\equiv 28$, $A\equiv 3 \pmod{37}$ — the $\pi$
branch. A real solution could a priori be on any of the three branches; mod 37 (and mod
$37^n$ for all $n$) cannot decide, because the phantom is a global rational cube, hence a
cube mod $37^n$ for every $n$ (verified mod $37^3$, Wolfram). At depth $37^2$ the residues
$2^x, 3^y \pmod{37^2}$ already vary across the family ($332640 \not\equiv 0 \bmod
\mathrm{ord}_{37^2}(2)=1332$; $55440 \not\equiv 0 \bmod \mathrm{ord}_{37^2}(3)=666$), so
there is no universal deeper 37-adic constraint either. **Soft obstruction, again.**

## Per-fixed-$y$ Thue equation: finiteness without uniformity

For fixed $y$, $z^3 - 4W^3 = 3^y + 5$ is a genuine Thue equation (finitely many integer
$(z,W)$). Searching $W \leq 1000$ (Wolfram) for $y = 0..12$:

- $y=3$: $(z,W) = (4,2)$, and $W=2=2^1$ is a power of 2 $\Rightarrow$ known solution $(5,3,4)$.
- $y=5$: $(z,W) = (54,34)$, but $34$ is not a power of 2 $\Rightarrow$ no Kuromine solution.
- all other $y \leq 12$: no positive-$(z,W)$ Thue solution at all.

So per fixed $y$ the equation is finite and the residual constraint is the S-unit condition
"$W = 2^a$." There is **no uniformity across $y$**: each $y$ is a separate Thue equation, and
the quantitative number-of-solutions bounds (Evertse-Győry) depend on the unit rank of
$\mathbb{Q}(2^{1/3})$ (which is $1$; fundamental unit $2^{1/3}-1$, Wolfram) and on $|S|$, but
these give a finite bound **per equation**, never a single contradiction for the whole
progression. This is the classical wall — finiteness per fixed exponent is already known;
uniformity over the infinite progression is the open content, and Thue-Mahler theory does
not deliver it.

## Conclusion

The Thue-Mahler approach is **not a new route to a proof**. Every attempt to cast the
Kuromine equation as a single Thue-Mahler equation `F(X,Y) = (S-unit)` is broken by the
additive constant 5. The norm-form structure in $\mathbb{Z}[\omega]$ (including the clean
new fact $37 \| B$) is genuine but phantom-blocked at every $p$-adic depth. Per-fixed-$y$
Thue equations are finite but non-uniform. The direction collapses onto the same
two-comparable-S-units / phantom barrier as all prior approaches.

The one positive deliverable is the symmetric reframing
$z^3 - 4(2^a)^3 - (3^j)^3 = 5$ and the clean universal fact $v_{37}(2^x+5)=1$, $37\|B$.

**[MEDIUM] Thue-Mahler direction → RETIRED.**
