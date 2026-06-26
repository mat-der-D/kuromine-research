# Current Focus

**Session:** 20260626_HHMMSS (Session 22)

**Current direction:** WATCH-phase arXiv reconnaissance, with a focused assessment of the
2025–2026 **decidability frontier for linear-exponential Diophantine systems** (KLNOW 2025;
Dong–Shafrir arXiv:2505.19141, STOC 2026). Question: does the newly-proven decidability for
linear-exponential systems **over two primes** reach the Kuromine equation, whose exponential
part lives over exactly the two primes $\{2,3\}$? Outcome: **No — blocked by a degree
obstruction (the free cube $z^3$). Eleventh independent confirmation of the barrier.**

## Session 22 main results

1. **Decidability frontier located precisely relative to Kuromine (new, sharp).**
   - KLNOW (2025): solvability of **linear-exponential** Diophantine systems (free variables
     at degree $\le 1$ outside exponents) **over two primes** is **decidable** — and the
     proof **relies on Baker's theorem**.
   - Dong–Shafrir (arXiv:2505.19141, STOC 2026): S-unit equations over modules reduce
     (Turing-equivalently) to linear-exponential systems over the primes dividing $T$;
     decidable for $T$ with $\le 2$ prime divisors; arbitrary $T$ would be "a major
     breakthrough in number theory."
   - **Kuromine** $2^x+3^y+5=z^3$: exponential part is over **exactly two primes** ($T=6$),
     i.e. squarely inside the prime-count frontier — BUT the term $z^3$ has $z$ **free at
     degree 3** (Wolfram: $z=3^j+A \Rightarrow z^3 = 3^{3j}+3^{1+2j}A+3^{1+j}A^2+A^3$, the
     free cube $A^3$). The decidable class allows degree $\le 1$. **Kuromine is two
     polynomial degrees above the frontier.**

2. **The degree obstruction = the known per-fixed-variable wall.** A free degree-3 term per
   fixed RHS is a Mordell/Thue cubic — exactly the retired elliptic-curve / Thue-Mahler
   dead end: finite per fixed $x$, **no uniformity** across the Theorem-5 family. So the new
   decidability angle collapses onto an existing wall, AND its in-class engine (Baker) is
   already structurally dead for Kuromine (Session 5, $v_p(\Lambda_p)=0$).

3. **arXiv watch otherwise negative (eleventh confirmation).** No unconditional effective
   $\kappa<1.107$ tool. Calegari–Dimitrov–Tang (2510.04156) still the irrationality-measure
   frontier (measure for $2^{1/3}$ still $>2$). No 2026 result placing a single free
   quadratic/cubic term inside the linear-exponential decidable class.

## Where things stand (updated after Session 22)

**Every named approach (Sessions 1–19), the Session-20 theory-building framework (retired
S21), and now the linear-exponential-decidability frontier (S22) are exhausted/blocked.** The
new placement is the most precise diagnostic yet: Kuromine sits **one prime within but two
polynomial degrees above** the proven decidability frontier, and the degree gap is the same
per-fixed-variable Thue/Mordell wall already on record. Two structurally distinct barriers now
pinned: (i) the metric/analytic two-comparable-S-units barrier (need effective $\kappa<1.107$),
and (ii) the degree-3 free-cube barrier to decidability methods. Both rest, at their core, on
Baker being inapplicable here.

**The unique remaining open target (unchanged):**
$$|z^3 - 3^y| > C \cdot (z^3)^{\kappa}, \quad \kappa < 1.107, \qquad (3^y \approx z^2).$$

## Next priority

1. **[WATCH — sole active priority]** Monitor arXiv for (a) an unconditional effective
   $\kappa<1.107$ bound for $|z^3-3^y|$ / effective irrationality measure for $2^{1/3}$ below
   $\sim1.1$; OR (b) any extension of the linear-exponential decidability results (KLNOW /
   Dong–Shafrir school) to systems containing a single free **higher-degree** (quadratic or
   cubic) term, which would be the genuinely new development that could touch Kuromine. Watch
   Karimov–Luca–Nieuwveld–Ouaknine–Worrell follow-ups, Dong–Shafrir, CDT (2510.04156),
   new Bugeaud papers.
2. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs (Theorem-N corollary) — logged
   for completeness only.
3. **[DO NOT REOPEN]** The Coupling-Height framework, and any Baker-based decidability route
   (Baker is structurally dead here).
