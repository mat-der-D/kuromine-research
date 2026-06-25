# Current Focus

**Session:** 20260625_152000 (Session 4)

**Current direction:** Pursued the Session-3 top lead — the primitive-divisor / congruence
attack on the factor $B = z^2+zw+w^2$ in $2^x+5 = A\cdot B$ ($A=z-3^j$). Determined
decisively that its *congruence* form is dead (soft obstruction strikes again, now on the
factorization), pinned down the precise real-vs-phantom 3-adic distinction, extended the
numerical verification, and assessed the modular/Frey-curve method (not applicable).

**Why this direction:** It was the [MEDIUM-HIGH] "best remaining non-size lead" after
Session 3 retired all size-based methods. Settling whether it can work — and exactly why
not — is the highest-value move, mirroring how Sessions 2–3 cleanly closed the local and
irrationality-measure directions.

## Session 4 main results

1. **The $A\equiv 3\pmod p$ phenomenon, explained.** Because $332640\equiv0\pmod3$ and
   $166320\equiv0\pmod6$, the residues $x\bmod3\equiv2$, $y\bmod6\equiv3$ are *constant*
   over the whole Theorem-5 family, so $2^x,3^y,w=3^j\pmod p$ are pinned for any prime $p$
   with suitable multiplicative orders. Wolfram then shows $A=z-w\equiv 3\pmod p$ for
   **every** tested prime $p\equiv2\pmod3$ ($p=11,17,23,29,41,71,89,113,281$), and the
   phantom-matching branch for $p\equiv1\pmod3$ gives $A\equiv3$, $B\equiv37/3$. **Cause:**
   the phantom has $A_{\text{phantom}}=\tfrac{10}3-\tfrac13=3$, $B_{\text{phantom}}=\tfrac{37}3$,
   which reduce mod every $p\ne3$. So every congruence on the factorization is satisfied by
   the phantom — the soft-obstruction principle, now confirmed on $A,B$. **The naive
   primitive-divisor/congruence contradiction is therefore impossible.**

2. **The genuine integrality distinction (real vs phantom) is 3-adic and blocked.**
   Integer solution: $v_3(A)=0$, $A\equiv1\pmod3$, $A\bmod9\in\{1,4,7\}$, $B$ a genuine
   integer with $v_3(B)=0$ and all prime factors $\equiv1\pmod3$. Phantom: $A=3$
   ($v_3=1$, $\bmod9=3$), $B=37/3$ ($v_3=-1$). They differ only at powers of 3 — exactly
   where the soft obstruction does not apply — but the difference is non-actionable because
   $37$ is a cubic residue mod $3^n$ for all $n$ (the known $3^n$ wall): the real branch
   $A\bmod3^n$ is never forced into a contradiction.

3. **$B$ is not a Lucas/Lehmer sequence.** $B=(2^x+5)/(z-3^j)$ with both $z$ and $j$ varying
   non-linearly in $x$, so Zsygmondy / Bilu–Hanrot–Voutier primitive-divisor theorems do
   **not** apply. The "growth" form of the lead has no clean object to act on.

4. **Modular / Frey-curve method: not applicable (structural).** It needs a *varying prime
   exponent* for the mod-$p$ Galois representation; the Kuromine equation has only the fixed
   small cube exponent, with $x,y$ on fixed small bases. No Frey curve can be built. The
   fixed-$y$ elliptic route only re-derives the known per-$y$ finiteness. See
   `knowledge/references/modular_method.md`.

5. **Numerical verification extended.** Exhaustive search (Python, cubic-residue sieve mod
   14 primes) over $0\le x,y\le 2000$ (~4M pairs) leaves only 4 sieve-survivors:
   $(1,0),(5,3),(1445,597),(1445,1677)$; only the first two are actual cubes (the two known
   solutions). The latter two are non-cubes outside the Theorem-5 class ($1445\not\equiv5
   \bmod332640$). **No new solutions for $x,y\le 2000$.**

## Where things stand (board state)

- Local / congruence / $p$-adic: provably insufficient (Session 2; reconfirmed on the
  factorization in Session 4 — phantom $A=3$, $B=37/3$ reduce everywhere).
- Single irrationality measure / 2-term linear form: provably insufficient (Session 3).
- Full 3-log Baker (Matveev): too weak by $\sim10^{10}$ (Sessions 1,3).
- Primitive-divisor / congruence on factorization: dead in congruence form, no object in
  growth form (Session 4).
- Modular / Frey method: not applicable, structural (Session 4).

**Honest assessment (unchanged, sharpened):** every currently known *effective* global tool
is quantitatively too weak for the Theorem-5 parameter range, and every *local/algebraic/
congruence* tool is defeated by the soft obstruction (the phantom $(10/3)^3$ is a global
rational cube whose factorization data $A=3$, $B=37/3$ reduce mod every prime $\ne3$). The
problem genuinely sits beyond present techniques for this range. The verification confirms
the conjecture empirically far below the Theorem-5 floor ($x,y\le2000$).

## Notes / still open (least-implausible remaining angles)

- The only place real solutions provably differ from the phantom is **3-adically**
  ($v_3(A)=0$ vs $1$). Any winning argument must exploit this *together with a global/size
  input* (since congruences mod $3^n$ alone are blocked). No mechanism is known, but this is
  the sharpest formulation of the wall.
- A genuinely new effective tool for "two comparable large $S$-units summing to a cube"
  (beyond Matveev / cubic irrationality measures) would be required; none is presently known.
  Worth watching the arithmetic-holonomy literature (arXiv:2510.04156 and successors) for a
  *simultaneous* two-variable refinement, though §2-§3 of `irrationality_measure_obstruction.md`
  suggest the $\kappa\approx0.62$ obstruction is structural.
- arXiv:2207.14492 (Thue-Mahler resolution) still un-executed for a concrete $k=1$ case;
  would only confirm per-case finiteness, not uniformity.
