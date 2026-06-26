# Current Focus

**Session:** 20260626_110746 (Session 23)

**Current direction:** WATCH-phase reconnaissance (the sole active priority since Session 21),
with (i) a fresh, properly-targeted arXiv watch on the two open frontiers (effective
irrationality measure for $2^{1/3}$ below $\sim1.1$; extension of the linear-exponential
decidability class to a free higher-degree term), (ii) an independent re-verification of the
soft-obstruction characterization (the foundation of every "phantom" dead-end), and (iii) a
concrete extension of the $D$-lattice equidistribution record. Outcome: **No new applicable
tool. Twelfth independent confirmation of the barrier. Dead-end record re-verified correct.**

## Session 23 main results

1. **Soft-obstruction re-verified from scratch (and a self-caught mis-test corrected).** The
   phantom $(5,-3,10/3)$ has RHS $2^5 + 3^{-3} + 5 = 1000/27 = (10/3)^3$ exactly (Wolfram).
   This is a global rational cube, hence a cube in $\mathbb{Q}_p$ for **every** prime
   $p\neq3$: tested over all 195 primes $p\equiv1\pmod3$ below $\approx 2740$, $1000/27$ is a
   cube residue in **195/195** cases. (An initial test mistakenly used $37/27$ — NOT the
   phantom RHS — and got only 63/195; the corrected value $1000/27$ gives 195/195.) This
   independently confirms the entire family of "phantom-blocked" dead-ends (congruence sieve,
   Skolem/Bertók–Hajdu, primitive-divisor congruence form, modular) rests on a correct fact:
   along the Theorem-5 phantom residues ($x\equiv5$, $3^y\equiv3^{-3}$), the equation reduces
   to $1000/27 \pmod p$ — always a cube. No congruence with $\gcd(m,3)=1$ can ever fire.

2. **$D$-lattice equidistribution record sharpened (Lemma B′ remains false, non-actionably).**
   With $D(k_x,k_y)=c_0+k_xP-k_yQ$, $P/Q=3\log2/\log3=1.8927892607\ldots$ irrational, the
   running minimum of nonnegative $D$ continues to descend: Session 21 had $D=0.5367$ at
   $k_x=84180$; this session reaches **$D=0.1446$ at $k_x=243595$** (Wolfram, search to
   $k_x\le1.5\times10^6$). Confirms $\inf_{k_x}D_{\ge0}=0$. The genuine $A\approx3e^{D}\approx
   3.47$ at that pair would need $v_3(2^x+5-A^3)=j+1\approx1.35\times10^{10}$ for a fixed
   small $A$ — impossible (Theorem-N corollary: bounded valuation for fixed small $a$). So the
   ever-closer boundary approach is real but stays **non-actionable**, exactly as recorded.

3. **arXiv watch negative (twelfth confirmation).**
   - **CDT holonomy school (Calegari–Dimitrov–Tang):** active and advancing on *L-value
     irrationality* (now $L(2,\chi_{-3})$, $\mathbb{Q}$-linear independence of $1,\zeta(2),
     L(2,\chi_{-3})$; follow-ups on $\zeta_2(5)$), but **no** effective irrationality measure
     for $2^{1/3}$ below $\sim1.1$ has appeared. The frontier for our target is unmoved.
   - **Decidability school (KLNOW 2025 / Dong–Shafrir 2505.19141, STOC 2026):** decidability
     of linear-exponential Diophantine systems is settled for **two primes** (uses Baker) and
     **explicitly open for $k\ge3$ primes**. No 2026 result extends the decidable class to a
     free **higher-degree** (quadratic/cubic) term — which is exactly what Kuromine's free
     cube $z^3$ would require. Kuromine remains "one prime within, two polynomial degrees
     above" the frontier (Session 22 placement, unchanged).

## Where things stand (unchanged in substance since Session 21)

Every named approach (Sessions 1–19), the Session-20 theory-building framework (retired S21),
the linear-exponential decidability frontier (S22), and this session's re-verification (S23)
all confirm the same wall. The conjecture is reduced to a single unconditional open target:
$$|z^3 - 3^y| > C\cdot(z^3)^{\kappa}, \quad \kappa < 1.107, \qquad (3^y \approx z^2),$$
a tool that does not currently exist. Two structurally distinct frontiers gate it: the
metric/analytic two-comparable-S-units barrier (need effective $\kappa<1.107$), and the
degree-3 free-cube barrier to decidability methods. Both rest on Baker being inapplicable.

## Next priority

1. **[WATCH — sole active priority]** Monitor arXiv for (a) an unconditional effective
   $\kappa<1.107$ bound for $|z^3-3^y|$ / effective irrationality measure for $2^{1/3}$ below
   $\sim1.1$ (watch CDT-school follow-ups — they are productive but on L-values, not roots);
   OR (b) any extension of the linear-exponential decidability results to systems with a
   single free **higher-degree** term, OR the $k\ge3$-prime case (explicitly open). Watch
   KLNOW / Dong–Shafrir, CDT (2510.04156), new Bugeaud papers.
2. **[VERY LOW / likely empty]** Near-boundary small-$D$ pairs (now down to $D=0.1446$ at
   $k_x=243595$) — Theorem-N corollary still blocks; logged for completeness only.
3. **[DO NOT REOPEN]** Coupling-Height framework; any Baker-based decidability route (Baker is
   structurally dead here); pure congruence sieving (soft-obstruction re-verified this session).
