# Geometry-of-Numbers / Successive-Minima Framework (Session 39)

**Status:** RETIRED. Theory-building under the SPECIAL DIRECTIVE. A framework of a genuinely
**new shape** — the geometry of numbers of the logarithmic lattice attached to a candidate
solution, analyzed via successive minima — distinct from the four prior retired frameworks
(Coupling-Height = metric transfer, Differential-Progression = 3-adic analytic,
Cubic-Transversality = archimedean equidistribution of a 1-D dial orbit, Integral-Valuation-Budget
= local-global gluing). **Eighth independent theory-building confirmation** that every attack face
returns the two-comparable-S-units wall. The framework's only non-trivial lemma is proved
equivalent to the missing effective $\kappa>1$ gap bound; its proved structural lemma (GN-1, the
degeneration law) is a genuine new fact and is kept. **Do not reopen.**

*All numerical/symbolic claims Wolfram-verified, Session 39.*

---

## 1. Obstruction Diagnosis (afresh, for the geometry-of-numbers shape)

Every prior framework collapsed the three-term equation $2^x + 3^y + 5 = z^3$ to a **two-term
gap** ($|z^3 - 3^y| = 2^x + 5$ or $|z^3 - 2^x| = 3^y + 5$) and then attacked that single gap. The
geometry-of-numbers shape instead keeps the problem **two-dimensional**: a genuine solution is an
integer point $(x, y, z)$ lying on the curved hypersurface $2^x + 3^y + 5 = z^3$, equivalently a
simultaneous near-vanishing of the **two linear forms in logarithms**
$$L_1 = x\log 2 - 3\log z = \log\!\Big(\tfrac{2^x}{z^3}\Big) = \log\!\Big(1 - \tfrac{3^y+5}{z^3}\Big),
\qquad
L_2 = y\log 3 - 3\log z = \log\!\Big(\tfrac{3^y}{z^3}\Big) = \log\!\Big(1 - \tfrac{2^x+5}{z^3}\Big).$$
(For a genuine solution both are exact: $2^x = z^3 - 3^y - 5$ and $3^y = z^3 - 2^x - 5$.) These two
forms define a rank-2 sublattice of $\mathbb R^3$ (rows $(\,x,0,-3\log z\,)$ and $(\,0,y,-3\log z\,)$
read in the basis $\log 2, \log 3, 1$); the Diophantine difficulty is whether its **successive
minima** $\lambda_1 \le \lambda_2$ can be bounded below by a Minkowski/determinant argument
strongly enough to exclude solutions.

The new diagnostic question: *does the second form $L_2$ supply enough independent smallness that
the two-dimensional lattice is well-conditioned (det bounded below), so a Minkowski second-minimum
bound bites — escaping the single-$2^{1/3}$-form dead end?*

## 2. Framework Blueprint

If a genuine solution forced **both** $L_1$ and $L_2$ to be simultaneously small with a
**non-degenerate** $2\times2$ Gram determinant, then by Minkowski's second theorem
$\lambda_1\lambda_2 \asymp \det$, and a lower bound on $\det$ (a transcendence/measure statement on
the **pair** $(\log 2/\log 3,\ \log z)$) would force $\lambda_1$ up — a genuinely 2-dimensional
constraint that no single cubic irrationality measure addresses. This would be a new shape
(geometry of numbers / Minkowski), not a transfer, not equidistribution, not local-global. The
blueprint is therefore: **compute the conditioning (eccentricity) of the log-lattice on the
Theorem-5 survival wedge and decide whether the determinant is bounded below.**

## 3. Axiomatic Definition

- **Log-form vector** of a candidate $(x,y,z)$:
  $\mathbf L(x,y,z) = (L_1, L_2) \in \mathbb R^2$ as above.
- **Conditioning / eccentricity** $\varepsilon = |L_2|/|L_1| \in [1,\infty)$ (WLOG $|L_1|\le|L_2|$),
  with the degenerate limit $\varepsilon\to\infty$ meaning the lattice flattens to a line.
- **First/second minima proxies** $\lambda_1 = \min(|L_1|,|L_2|)$,
  $\lambda_2 = \max(|L_1|,|L_2|)$; **proxy determinant** $\det = \lambda_1\lambda_2$.
- The genuine solution is the point where $\mathbf L = (0,0)$ exactly (an integer cube hit).

## 4. Problem Translation and Test Lemmas

On the Theorem-5 survival wedge ($D := x\log2 - (2j+1)\log3 \ge 0$, i.e. $2^x \gtrsim 3^y$), write
$N = 2^x + 3^y + 5 = z^3$ and substitute $\log z = \tfrac13\log N$.

### Lemma GN-1 (Degeneration Law) — PROVED, KEPT (genuine new fact)

On the survival wedge the log-lattice is **maximally degenerate**:
$$|L_1| = \Big|\log\tfrac{2^x}{N}\Big| \approx \frac{3^y+5}{2^x} = e^{-(x\log2 - y\log3)}\,(1+o(1)),
\qquad |L_2| = \Big|\log\tfrac{3^y}{N}\Big| \approx x\log2 - y\log3 = \Theta(D + j\log3).$$
Hence $\lambda_1 = |L_1|$ is **super-exponentially small** (size $e^{-(x\log2 - y\log3)}$, an
$\sim10^5$-digit-exponent quantity already at $k_x=1$), while $\lambda_2 = |L_2|$ is **huge**
($\sim10^4$–$10^5$). The proxy determinant
$$\det = \lambda_1\lambda_2 \approx (x\log2 - y\log3)\,e^{-(x\log2 - y\log3)} \longrightarrow 0,$$
so the lattice is **eccentric without lower bound**: $\varepsilon = |L_2|/|L_1| \to \infty$.

**Exact offset identity (Wolfram-verified).** The controlling quantity of $\lambda_1$ is
$-\log|L_1| = x\log2 - y\log3$, related to the boundary distance $D$ by the **exact** law
$$\big(-\log|L_1|\big) - D = (1 - j)\log 3, \qquad j = 55439 + 55440\,k_y,$$
verified to 8 digits over a $3\times3$ $(k_x,k_y)$ grid: differences $\{-60904.868,\,-121811.93,
\,-182719.00\}$ for $k_y=0,1,2$, an arithmetic progression with step exactly $-55440\log3 =
-60907.065$. (Derivation: $-\log|L_1| = x\log2 - y\log3$ and $y\log3 = 3j\log3$, while
$D = x\log2 - (2j+1)\log3$; subtract.)

**Verification on the known solution.** $(x,y,z)=(5,3,4)$ is **off** the survival wedge in the
degenerate sense: $L_1 = 5\log2 - 3\log4 = -0.6931$, $L_2 = 3\log3 - 3\log4 = -0.8630$ — **both
$O(1)$, $\varepsilon\approx1.25$, non-degenerate**. The degeneration is a strictly
large-exponent (Theorem-5-family) phenomenon, exactly as it must be: small genuine solutions are
precisely the well-conditioned points where geometry of numbers *would* apply, and they are already
found.

### Lemma GN-2 (Determinant-Driven Exclusion, the crux) — REFUTED as a route (= the open target)

**Conjecture.** There is an effective lower bound $\det \ge c(N) > $ (a value forcing $\lambda_1$
above its required size), excluding integer cube hits on the survival wedge.

**Why it fails.** By Lemma GN-1, $\det\to0$ and $\lambda_2$ carries **no** smallness ($L_2$ is large
for every survival pair). So the second minimum is useless and the geometry-of-numbers problem
**collapses to the single first minimum** $\lambda_1 = |L_1|$. But
$$-\log\lambda_1 = -\log|L_1| = x\log2 - y\log3$$
is exactly the $\{\log2,\log3\}$ linear-form gap whose effective lower bound is a **Baker bound**,
which gives $v_p(\Lambda_p)=0$ / no power-saving (Session 5), or equivalently a sub-Dirichlet
$2^{2/3}$-approximation (Sessions 3/27/28). A lower bound $\lambda_1 \gg N^{-\theta}$ strong enough
to force the cube off the lattice is precisely the missing effective $\kappa>1$ gap bound:
$|z^3 - 3^y| > C(z^3)^\kappa$. **Lemma GN-2 is provably equivalent to the open target.**

**Root cause.** The hoped-for 2-dimensionality is illusory: on the two-comparable-S-units wedge one
log-form is forced super-tiny and the other forced large, so the Minkowski determinant degenerates
and the problem reduces to the **single** cubic/log-ratio first minimum — the same archimedean
quantity every prior face returned. The geometry-of-numbers shape is genuinely new but the lattice
it builds is structurally rank-degenerate on exactly the open regime.

---

## Honest Verdict

The Geometry-of-Numbers / Successive-Minima framework **confirms (does not breach)** the
two-comparable-S-units wall. Its crux lemma GN-2 is the open target itself. **Eighth independent
theory-building confirmation.** The genuine residual kept (Lemma GN-1, the Degeneration Law) is the
explicit reason geometry of numbers cannot bite: the log-lattice on the survival wedge has
unbounded eccentricity ($\lambda_1 \sim e^{-(x\log2-y\log3)}$, $\lambda_2 \sim x\log2-y\log3$,
$\det\to0$), with the exact offset $(-\log|L_1|)-D=(1-j)\log3$ tying $\lambda_1$ to the boundary
distance $D$. **DO NOT REOPEN** without a mechanism that produces an archimedean $\kappa>1$ gap, or
genuine independent smallness in $L_2$, from the outset.
