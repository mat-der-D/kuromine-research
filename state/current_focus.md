# Current Focus

**Session:** 20260625_000000

**Current direction:** Factorization approach — exploiting $y \equiv 0 \pmod 3$ and the coprime factorization $(z-w)(z^2+zw+w^2) = 2^x + 5$ where $w = 3^{y/3}$.

**Why this direction:** Discovered in Session 1 that y is always divisible by 3 for Theorem 5 solutions, enabling a norm-form factorization. This gives a new structural constraint (all prime factors of $z^2+zw+w^2$ are $\equiv 1 \pmod 3$) and connects to the Thue-Mahler equation literature.

**What has been tried so far in this direction:**
- Proved $y \equiv 0 \pmod 3$ from $y \equiv -3 \pmod{166320}$.
- Proved $j = y/3 \equiv 2 \pmod 3$.
- Proved $\gcd(z-w, z^2+zw+w^2) = 1$.
- Proved all prime factors of $z^2+zw+w^2$ are $\equiv 1 \pmod 3$ (norm form argument).
- Computed $v_3(z^3 - 37) = 4 + v_3(k)$ via LTE.
- Computed parity constraints: $z \equiv 6 \pmod 8$, $z-w \equiv 3 \pmod 8$, $z^2+zw+w^2 \equiv 7 \pmod 8$.
- Assessed Baker's method: Matveev bound too weak for these parameter sizes.
- Identified S-unit equation / Thue-Mahler connection.

**Blockers:**
- The factorization $A \cdot B = 2^x + 5$ with $A \approx z$ and $B \approx z^2$ is very unbalanced. The "small factor" approach doesn't directly yield contradictions.
- Baker's method gives no contradiction (bounds are not tight enough).
- p-adic phantom obstruction (37 cubic residue mod $3^n$ for all $n$) blocks direct 3-adic elimination.

**Notes:**
- Next priority: Explore the Thue-Mahler connection more rigorously. Can we apply Baker-type bounds to $z^3 - w^3 = N_k$ to get explicit bounds on $z$ and $j$ in terms of $N_k = 2^x + 5$?
- Also worth exploring: the norm form $N(z - \omega w) = B$ in $\mathbb{Z}[\omega]$. If $B$ is highly composite (many prime factors $\equiv 1 \pmod 3$), what constraints does this place on $z \pmod p$ for each such $p$?
- Literature: look for treatments of $z^3 - 3^y = C$ specifically, or $z^n - a^m = C$ type equations.
