# Current Focus

**Session:** 2026-06-24 (20260624_181415)

**Current direction:** Factorization of the open-region equation + divisor sieve, with a
clarified understanding of why $p$-adic and Baker methods stall.

**Why this direction:** Started from the [HIGH] $p$-adic direction. Found that the
phantom obstruction is **two-sided** (both 2-adic and 3-adic local conditions are
automatically satisfiable), which definitively closes pure local methods. This pushed the
work toward a global/multiplicative handle: the factorization $z^3-v^3=2^x+5$ with
$v=3^{y/3}$ (valid because $y\equiv0\pmod3$ in the open region).

**What has been established this session:**
1. The two-sided phantom (see `knowledge/references/factorization_and_divisor_sieve.md`
   Â§3). Congruence/local methods exhausted from both 2- and 3-adic sides.
2. Naive Baker via the cube root is **ineffective** because $h(z)\sim x$ (variable cube
   base is the core obstruction). Baker would only help in the balanced regime, which the
   cube condition does not force.
3. **Coprime factorization** $(z-v)(z^2+zv+v^2)=2^x+5$ with $\gcd=1$. Subcase $A=z-v=1$
   eliminated (mod 27 forces $x\equiv11\pmod{18}$, contradicting open $x\equiv5\pmod{18}$).
4. **Divisor sieve:** in the open region $2^x+5$ can only have prime factors from a
   density-$\sim1/8$ "allowed" set; almost all small primes are forbidden. NOT blocked by
   the phantom.

**Blockers:**
- High powers of 3 give nothing new (phantom). The factorization's leverage must come from
  2-power moduli, other primes, and the multiplicative structure of $A,B$.
- $A$ ranges over (small) divisors of $2^x+5$; eliminating ALL of them uniformly is the
  open challenge.

**Notes:** Full details and next steps in
`knowledge/references/factorization_and_divisor_sieve.md`.
