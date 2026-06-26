# Linear-Exponential Diophantine Systems and the Decidability Frontier (Session 22)

## Why this reference exists

The Kuromine equation's exponential part lives over exactly the two primes $\{2,3\}$.
The 2025–2026 decidability frontier for **linear-exponential Diophantine systems** is
known precisely up to **two distinct prime bases**. This made it urgent to check
whether Kuromine falls inside that newly decidable class. It does **not** — and the
reason is sharp and worth recording: a **degree obstruction** (the free cube $z^3$),
not (this time) the two-comparable-S-units metric barrier.

## The relevant 2025–2026 results

### Karimov–Luca–Nieuwveld–Ouaknine–Worrell (KLNOW, 2025)

Proved: it is **decidable** whether a given system of **linear-exponential Diophantine
equations over two primes** admits a solution. A linear-exponential equation has the
shape
$$\sum_i c_i\, b_i^{\,n_i} \;+\; \sum_i d_i\, n_i \;=\; e,$$
where the $b_i$ are drawn from a **fixed** finite set of bases, the $n_i$ are the
unknowns appearing **in the exponents** and (at most **linearly**, degree 1) as ordinary
polynomial terms, and $c_i,d_i,e$ are fixed integers. The proof **relies on Baker's
theorem** (linear forms in logarithms).

### Dong–Shafrir, arXiv:2505.19141 (STOC 2026)

Studies S-unit equations over finitely presented modules over Laurent polynomial rings:
equations $x_1 m_1 + \cdots + x_k m_k = m_0$ with variables ranging over **monomials**
(coefficient 1). Main reductions:
- For $T$ a prime power: the solution set is effectively $p$-normal (Derksen–Masser style).
- For general $T$: deciding solvability of an S-unit equation is **Turing-equivalent to
  solving a system of linear-exponential Diophantine equations** over the primes dividing
  $T$.
- Combined with KLNOW (2025): **decidable when $T$ has at most two distinct prime
  divisors.**
- Explicit caveat from the paper: *"Proving either decidability or undecidability in the
  case of arbitrary $T$ would entail major breakthroughs in number theory."*

## Why Kuromine is outside this class — the degree obstruction

Kuromine: $2^x + 3^y + 5 = z^3$.

1. **Exponential part is over exactly two primes.** The terms $2^x$, $3^y$, $5$ are
   linear-exponential over the base set $\{2,3\}$ ($T = 6$, two prime divisors). If the
   right-hand side were a third fixed-base power (e.g. $7^w$), the whole equation would be
   a ternary linear-exponential equation over $\{2,3,7\}$ — three primes, just past the
   proven two-prime frontier, but morally in-family.

2. **The cube $z^3$ has $z$ free, degree 3.** The unknown $z$ ranges over **all** integers;
   it is *not* a power of a fixed base. Generic family solutions have $z \approx 2^{x/3}$,
   which is not $\{2,3\}$-smooth (the two known $z = 2, 4$ are powers of 2 by coincidence,
   but the family is not). Hence $z$ cannot be re-encoded as a monomial on $\{2,3\}$.

3. **Even after the Theorem-5 factoring the cube persists.** With $z = 3^j + A$ (Wolfram):
   $$z^3 = 3^{3j} + 3^{1+2j}A + 3^{1+j}A^2 + A^3,$$
   so the free integer $A \sim 2^{x/3}$ enters at **degree 3** ($A^3$) and degree 2
   ($A^2$). The linear-exponential decidable class allows free variables at **degree $\le
   1$** outside exponents. Kuromine sits at **degree 3** — two degrees above the frontier.

   | quantity | value |
   |---|---|
   | distinct primes in exponential part | 2 ($T=6$) |
   | max polynomial degree in a free variable | 3 (the cube) |
   | max degree allowed in the decidable class | 1 (linear-exponential) |

## What this means

- The decidability frontier reaches the *exponential skeleton* of Kuromine (two primes,
  exactly where KLNOW is decidable) but is **blocked by the free cube**, a **degree
  obstruction** independent of (and orthogonal to) the two-comparable-S-units metric
  barrier that blocked Baker.
- The degree-3 free cube, per fixed RHS, is a Mordell/Thue cubic — exactly the
  **per-fixed-variable wall** already retired (elliptic-curve and Thue-Mahler dead ends):
  finite and effectively solvable per fixed $x$ (or $y$), but **no uniformity** across the
  infinite Theorem-5 family.
- KLNOW's proof **uses Baker's theorem** — already structurally dead for Kuromine
  (Session 5, $v_p(\Lambda_p)=0$). So even the in-class machinery rests on the retired
  tool.

This is the **eleventh independent confirmation** of the barrier, and the most precise
placement to date: Kuromine sits **exactly one prime within, but two polynomial degrees
above**, the proven decidability frontier — and the degree gap is the same per-fixed-
variable Thue/Mordell wall already on record.

## References
- Karimov, Luca, Nieuwveld, Ouaknine, Worrell (2025): decidability of linear-exponential
  Diophantine systems over two primes (uses Baker's theorem).
- Dong, Shafrir, *S-unit equations in modules and linear-exponential Diophantine
  equations*, arXiv:2505.19141, STOC 2026.
- Cross-references in this repo: `knowledge/dead_ends.md` (Baker, Thue-Mahler,
  elliptic-curve entries); `knowledge/references/thue_mahler_approach.md`.
