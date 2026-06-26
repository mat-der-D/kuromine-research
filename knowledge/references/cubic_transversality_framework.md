# Cubic-Transversality / Dial–Lattice Framework (Session, 2026-06-27 build)

**Status:** New theory-building framework (SPECIAL DIRECTIVE). Built because the arXiv
watch is again negative and the two prior theory-building frameworks (Coupling-Height S20,
Differential-Progression S24) were retired for being **3-adic-only**. This framework is
deliberately **archimedean-first** and is logically distinct from all retired frameworks.
It is a **blueprint with one verified structural backbone and two unproven crux lemmas**, not
a proof. All numerical anchors below are Wolfram-verified.

---

## 0. Why a new archimedean handle is required (recap of the wall)

Every retired framework worked **one place at a time**, and the phantom
$2^5 + 3^{-3} + 5 = (10/3)^3$ is invisible to each place separately:
- 3-adic-only data reduces to Theorem-J (Coupling-Height, Differential-Progression both
  retired; four independent confirmations).
- Baker is inapplicable: $v_p(\Lambda_p) = 0$ (the two-comparable-S-units regime).
- Irrationality measures act only on *good* approximations ($\mu \ge 2$); the realized
  exponent of the gap is sub-Dirichlet ($E \to 2/3$, Wolfram), so measures have nothing to
  act on.

**The corrected open target (Session 26, re-verified this session):** for any surviving
Theorem-5 pair, the realized gap exponent
$$E(k_x,k_y) = \frac{\log(2^x+5)}{\log(z^3)} \in \left(\tfrac23, 1\right),$$
and at the near-boundary surviving pair $(k_x,k_y)=(84180,\,\lfloor\cdots\rfloor)$ with
$D=0.53667$, Wolfram gives $E = 0.6666666667\ldots \to 2/3^+$. An effective gap bound with
any fixed $\kappa>1$ resolves the family; no such bound exists.

**The new handle this framework introduces.** The genuine-vs-phantom distinction has a purely
**archimedean / rational** face that no previous session exploited:

> A genuine solution is an **integer** cube root ($z \in \mathbb Z$, denominator 1).
> The phantom is a **denominator-exactly-3 rational** cube root ($z = 10/3$).
> Equivalently, with $W := 3z$, a genuine solution has $W \in 3\mathbb Z$, while the phantom
> has $W = 10 \notin 3\mathbb Z$.

This is a statement about the **real number** $z$ and its rational denominator, NOT about any
$p$-adic valuation. It is therefore outside the scope of every retired (place-by-place)
framework.

---

## 1. The cubic-dial reformulation (verified backbone)

**Definition 1.1 (the dial form).** Set $W := 3z$. Multiplying the Kuromine equation by 27,
$$\boxed{\,W^3 \;=\; 27\cdot 2^x \;+\; 3^{\,y+3} \;+\; 135\,}\qquad(\star)$$
(Wolfram-verified: $135 = 5\cdot27$ and $27\cdot 3^y = 3^{y+3}$.)

- **Genuine solutions** ($y\ge0$, $z\in\mathbb Z$): the RHS of $(\star)$ is divisible by 27
  (each summand is), so $27\mid W^3 \Rightarrow 3\mid W$, consistent with $W=3z$.
  Verified: $(x,y)=(1,0)\Rightarrow W^3=216=6^3$; $(5,3)\Rightarrow W^3=1728=12^3$.
- **Phantom** ($y=-3$): $3^{y+3}=3^0=1$, so $W^3 = 27\cdot2^5 + 1 + 135 = 1000 = 10^3$, and
  $W=10\notin 3\mathbb Z$. The phantom **escapes** the $27\mid\text{RHS}$ structure precisely
  because $y<0$.

So $(\star)$ already encodes the genuine-vs-phantom split as the *real, integer* condition
"$W$ is a multiple of 3," available only for $y\ge0$. This is the verified backbone.

**Definition 1.2 (the dial and the cube lattice).** Regard $x$ as a continuous real "dial"
$t$ and fix $y$. Define
$$M_y(t) := 27\cdot 2^{t} + 3^{y+3} + 135, \qquad R_y(t) := M_y(t)^{1/3}.$$
A genuine solution is a point where the dial places $R_y(t)$ **exactly on the lattice**
$3\mathbb Z$ of multiples of 3, at an integer $t=x$.

**Definition 1.3 (cubic defect / cubic theta).** The **cubic defect** of the dial at $(x,y)$
(genuine target) is
$$\Theta(x,y) := \operatorname{dist}\!\big(R_y(x),\, 3\mathbb Z\big)
= \min_{n\in\mathbb Z}\big|\,(27\cdot2^x+3^{y+3}+135)^{1/3} - 3n\,\big|.$$
A genuine solution $\iff \Theta(x,y)=0$. The phantom is at $\Theta=\tfrac13$ from $3\mathbb Z$
(its $R=10$, nearest multiples of 3 are 9 and 12, distance 1; but the phantom is not on the
$y\ge0$ sheet, so it is formally outside $\Theta$'s domain — exactly the separation).

---

## 2. The transversality picture (verified sensitivity law)

**Sensitivity law (Wolfram-verified).** Differentiating $(\star)$ along the dial,
$$\frac{dR_y}{dt} = \frac{27\log2\cdot 2^t}{3\,R_y^2} = \frac{9\log2\cdot 2^t}{R_y^2}.$$
At the boundary $2^x$ dominant ($R^3\approx 27\cdot2^x$, so $R^2\approx (27\cdot2^x)^{2/3}$),
$$\frac{dR_y}{dt} \;\asymp\; \log2\cdot 3^{?}\cdot 2^{x/3} \;\sim\; c\cdot 2^{x/3},
\qquad c = 3\log2\cdot 3^{2/3}/3 = \log2\cdot 3^{2/3}\approx 1.4418.$$
Verified: sensitivity $=2.20$ at $x=5$, $6.99$ at $x=10$, $7.50\times10^9$ at $x=100$ —
growing like $2^{x/3}$.

**Interpretation (the new geometric content).** As the integer dial $x$ increments by 1,
$R_y$ sweeps through $\sim 2^{x/3}$ consecutive integers, i.e. $\sim 2^{x/3}/3$ consecutive
multiples of 3. The Kuromine question becomes:

> **Does the exponential dial $\{R_y(x)\}_{x\in\mathbb Z}$ ever land exactly on the cubic
> lattice $3\mathbb Z$, in the survival wedge $k_y/k_x < 3\log_3 2-1 = 0.89279$?**

This is a **resonance / transversality** problem between an exponential orbit and a fixed
arithmetic lattice — a category of problem with its own (archimedean) machinery
(equidistribution, discrepancy, transcendence of the orbit), entirely distinct from
$p$-adic valuation analysis and from irrationality measures of $2^{1/3}$.

---

## 3. Axiomatic definition of the framework

All objects live on the Theorem-5 lattice
$\mathcal L = \{x=5+332640k_x,\ y=166317+166320k_y,\ k_x\ge1,\ k_y\ge0\}$, $j=y/3$.

**Def 3.1 (dial orbit).** $\mathcal O := \{R_y(x) : (x,y)\in\mathcal L\}\subset\mathbb R_{>0}$,
$R_y(x)=(27\cdot2^x+3^{y+3}+135)^{1/3}$.

**Def 3.2 (cubic theta / defect).** $\Theta(x,y)=\operatorname{dist}(R_y(x),3\mathbb Z)$ as
in Def 1.3. The **genuine locus** is $\{\Theta=0\}$.

**Def 3.3 (defect velocity).** $\theta'(x,y) := dR_y/dt|_{t=x} = 9\log2\cdot2^x/R_y^2$ — the
rate (per unit dial) at which $R_y$ crosses multiples of 3; $\theta'\asymp 2^{x/3}$.

**Def 3.4 (transversality functional).** The genuine-vs-phantom **transversality**
$$\mathcal T(x,y) := \frac{\Theta(x,y)}{\,1/\theta'(x,y)\,} = \Theta(x,y)\cdot\theta'(x,y),$$
the defect measured in units of one dial-step's sweep. $\mathcal T$ is the archimedean
analogue of "how many lattice cells the dial misses the target by."

**Def 3.5 (the phantom's archimedean signature).** The phantom has $W=10$, $z=10/3$, so its
"reduced denominator" is exactly 3. Define the **denominator obstruction**
$\operatorname{den}(z)$ = denominator of $z$ in lowest terms; genuine $\Rightarrow
\operatorname{den}=1$, phantom $\Rightarrow \operatorname{den}=3$. This is an archimedean
invariant of the *real* solution, not a $p$-adic one.

---

## 4. Problem translation and the two crux lemmas

A Theorem-5 integer solution is, in this language, **a point of $\mathcal L$ at which the dial
orbit $\mathcal O$ hits the lattice $3\mathbb Z$ exactly** ($\Theta=0$, equivalently
$\operatorname{den}(z)=1$). The conjecture becomes:

> **Cubic-Transversality Conjecture.** For all $(x,y)\in\mathcal L$ with $k_x\ge1$,
> $\Theta(x,y)>0$; equivalently the exponential dial orbit $\mathcal O$ is **transversal** to
> $3\mathbb Z$ on the whole survival wedge.

Two lemmas would force this. **Both are unproven; honest status given.**

---

### Lemma C (Defect Quantization — the archimedean crux).

*There is an effective $c>0$ such that for every $(x,y)\in\mathcal L$ with $k_x\ge1$,*
$$\Theta(x,y) \;\ge\; c\cdot 2^{-2x/3}\cdot 3^{\,?}, \qquad\text{more precisely}\qquad
|M_y(x) - W^3| \ge c'\quad\text{for the nearest } W\in 3\mathbb Z,\ W^3\ne M_y(x).$$
*In words: the dial value $M_y(x)$ is never closer than an effective constant to a cube of a
multiple of 3 (other than an exact hit), and exact hits are excluded by the gate below.*

**Why it would resolve the problem.** $\Theta=0$ requires $M_y(x)$ to be *exactly* a cube
$W^3$ with $3\mid W$. Lemma C says $M_y(x)$ is bounded away from such cubes by $c'>0$; since
$M_y(x)\in\mathbb Z$, "bounded away from an integer cube by a positive constant" combined with
the **integrality** of $M_y(x)$ forces $M_y(x)$ to *not* be such a cube — i.e. no solution.
The content is to convert the real defect $\Theta$ into a positive integer gap
$|M_y(x)-W^3|$.

**Honest status.** This is the archimedean reformulation of the open target — and it is
**exactly as hard**, because $|M_y(x)-W^3| = 27\,|2^x+3^y+5 - z^3|$ which is $0$ at a solution
and otherwise $\ge1$ trivially (integrality), so the *trivial* gap is already $\ge27$. The
non-trivial content Lemma C must supply is **not** "$|M_y(x)-W^3|\ge c'$" (trivially true) but
the *contrapositive separation*: that $M_y(x)$ cannot be a cube **at all** on $\mathcal L$,
$k_x\ge1$. So Lemma C as a mere gap bound is vacuous (the gap is the original quantity); its
real job is to be proved via the **transversality velocity** (Def 3.3): because the dial
velocity $\theta'\asymp2^{x/3}$ is *transcendental-orbit-fast* and the lattice $3\mathbb Z$ is
fixed, an **equidistribution/discrepancy** argument might show the orbit cannot resonate.
**This is unproven and is the crux.** It is genuinely different from the retired frameworks
(no $p$-adic depth; no irrationality measure), but whether the equidistribution of an
exponential orbit can be made *effective enough to exclude a single exact hit* is open and, by
the same metric obstruction (two comparable S-units), likely faces an analogous barrier in a
new disguise. **Diagnostic value:** Lemma C names the archimedean form of the resonance
precisely; its difficulty isolates whether the barrier is intrinsically place-bound.

---

### Lemma D (Denominator Rigidity — the gate, partially structural).

*For every $(x,y)\in\mathcal L$ with $y\ge0$, if $M_y(x)=27(2^x+3^y+5)$ is a perfect cube
$W^3$, then $3\mid W$ (so $z=W/3\in\mathbb Z$).*

**Status: PROVED (trivial, but it is the structural gate).** If $W^3 = 27(2^x+3^y+5)$ with
$y\ge0$, then $27\mid W^3$, hence $3\mid W$ (cube). Verified in §1. This rules out a
**denominator-3 phantom on the $y\ge0$ sheet**: any cube hit on $\mathcal L$ is automatically a
*genuine integer* solution. So the phantom's denominator-3 escape is **structurally confined to
$y<0$**, off $\mathcal L$.

**Consequence (the framework's one clean output).** On the survival wedge $\mathcal L$
($y\ge0$), there is **no rational-non-integer obstruction**: every cube hit is a genuine
integer solution. Therefore the conjecture on $\mathcal L$ is *equivalent* to the pure
transversality statement (Lemma C) with **no phantom to dodge** — the phantom has been
"quotiented out" by the dial reformulation. This is a genuine simplification: it shows the
phantom obstruction, which blocked all *local* methods, **does not block the archimedean
transversality formulation**, because the phantom lives on the $y<0$ sheet that the dial form
$(\star)$ separates cleanly.

---

## 5. What the framework buys, honestly

**Genuine gains (verified):**
1. The dial reformulation $(\star)$ $W^3=27\cdot2^x+3^{y+3}+135$ is a clean, verified new
   encoding in which the phantom's denominator-3 escape is **structurally confined to $y<0$**
   (Lemma D, proved). On the survival sheet $y\ge0$ there is **no rational phantom** — every
   cube hit is genuine. This is the first formulation in which the phantom is provably *absent*
   from the relevant sheet, rather than merely "soft-obstructing" every test.
2. The problem is recast as a **transversality/resonance** of an exponential dial orbit against
   the fixed lattice $3\mathbb Z$, with explicit, Wolfram-verified velocity $\theta'\asymp
   2^{x/3}$ — an archimedean object that is NOT an irrationality measure of $2^{1/3}$ and NOT a
   $p$-adic valuation. It is therefore logically distinct from every retired framework.

**Honest limitation (the crux is unproven and likely barrier-bound):**
3. Lemma C (the archimedean crux) is the resonance-exclusion statement; as a naive gap bound it
   is vacuous (it equals the original quantity $27|2^x+3^y+5-z^3|$). Its only non-trivial route
   is an **effective equidistribution/discrepancy bound for the exponential dial orbit** strong
   enough to exclude a single exact lattice hit — and this is precisely where the
   two-comparable-S-units degeneracy is expected to re-surface (the orbit's effective
   equidistribution rate is governed by the same Diophantine quantities that make Baker
   give $v_p=0$). The framework **relocates** the wall to an archimedean equidistribution
   question; it does not yet breach it.

**Verdict.** A genuinely new *archimedean* reformulation (distinct from all four retired
frameworks), with one proved structural gate (Lemma D: phantom confined to $y<0$) and one
unproven crux (Lemma C: effective resonance exclusion). The proved part is a real
clarification — the phantom does **not** obstruct the survival sheet in this formulation. The
unproven part is the honest open frontier. **No false claim of resolution.**

---

## 6. Wolfram-verified anchors (this session)

- Known solutions $(1,0,2),(5,3,4)$; phantom $(10/3)^3=1000/27$. ✓
- Dial form $(\star)$: $W^3=27\cdot2^x+3^{y+3}+135$; genuine $W=6,12$; phantom $W=10$. ✓
- $\Theta$/defect velocity $\theta'=9\log2\cdot2^x/R^2\asymp 2^{x/3}$ (values $2.20, 6.99,
  7.50\times10^9$ at $x=5,10,100$). ✓
- Boundary gap exponent at $(k_x,k_y)=(84180,\ldots)$, $D=0.53667$:
  $E=\log(2^x+5)/\log z^3 = 0.6666666667\to 2/3^+$. ✓
- Threshold $3-3\log_3 2 = 1.10721$; wedge slope $3\log_3 2-1=0.89279$. ✓
- Only cube hits for $x\le60,y\le40$: $(1,0)$ and $(5,3)$. ✓

---

## 7. Session 28 resolution — Lemma C REFUTED (framework retired; Lemma D kept)

**Verdict: Lemma C is refuted as a route. The framework is RETIRED. Lemma D is kept as a correct
structural clarification.** All claims below are Wolfram-verified (Session 28).

**7.1 The decisive exact identity.** Wolfram `Simplify` gives, for all $x,y\ge0$,
$$\big(27\cdot 2^x + 3^{y+3} + 135\big)^{1/3} \;=\; 3\,\big(2^x + 3^y + 5\big)^{1/3}\quad
\Longrightarrow\quad
\boxed{\ \Theta(x,y)=\operatorname{dist}\big(R_y(x),3\mathbb Z\big)=3\cdot
\operatorname{dist}\big((2^x+3^y+5)^{1/3},\mathbb Z\big).\ }$$
The dial-orbit discrepancy from $3\mathbb Z$ is **exactly 3 times the original cube-root
distance** of $z=(2^x+3^y+5)^{1/3}$ from $\mathbb Z$. The $\times27$ / $W=3z$ rescaling that
*defined* the dial form is undone by the cube root: $R_y=3z$, so $\operatorname{dist}(R_y,
3\mathbb Z)=3\operatorname{dist}(z,\mathbb Z)$. **The "new archimedean object" is the original
cube-distance.** This is the single decisive finding: the dial reformulation does not produce a
genuinely new analytic quantity.

**7.2 Reduction to the Session-3 $2^{2/3}$ quantity.** On the Theorem-5 lattice
$x=5+332640\,k_x$, $x\equiv2\pmod3$ universally (Wolfram: $5\equiv2$, $332640\equiv0\bmod3$), so
$2^x=4M^3$ with $M=2^{(x-2)/3}\in\mathbb Z$. In the $2^x$-dominant survival wedge,
$N=2^x+3^y+5=4M^3+(3^y+5)$, and for the nearest integer $m\approx 2^{2/3}M$,
$$\operatorname{dist}(z,\mathbb Z)\approx\frac{|N-m^3|}{3N^{2/3}}
=\frac{|m^3-4M^3-(3^y+5)|}{3N^{2/3}},$$
whose minimal numerator is governed by $|m^3-4M^3|$ — the rational approximation of
$2^{2/3}=4^{1/3}$ by $m/M$ ($M$ a power of two). **This is exactly the Session-3 auxiliary
$2^{2/3}$-Thue casting** ($z^3-4W^3$, $W=2^a$).

**7.3 No positive constant lower bound (Wolfram).** Sweeping $m=\operatorname{round}(2^{2/3}\,
2^a)$: at deep convergents of $2^{2/3}$ the gap $|m^3-2^{3a+2}|$ is anomalously small (e.g.
$a=11$, $x=35$: $m=3251$, gap $=83883$, $\log_M(\text{gap})=1.487$, $\operatorname{dist}\approx
0.00265$; smaller along deeper convergents). The discrepancy demonstrably descends toward 0 — it
is **not** bounded below by any positive constant. For $x\equiv0\bmod3$ (NOT the family residue)
$2^x$ is itself a cube and the distance plunges to $\sim10^{-7}$, an extreme illustration.

**7.4 Sub-Dirichlet exponent (Wolfram).** The realized approximation exponent of $m/M\to2^{2/3}$
along the family is $\kappa\le1.21$ and negative for most pairs ($-0.377,+0.811,+1.208,+0.415,
\ldots$), strictly below the Dirichlet floor 2 — reproducing the Session-3/11 record. So no
irrationality measure can act (measures only bound *good* approximations, exponent $\ge2$), and
no effective lower bound $\operatorname{dist}\gg N^{-c}$ ($c<2/3$) is available.

**7.5 Conclusion.** Lemma C's only non-trivial route — an effective equidistribution/discrepancy
bound excluding a single exact lattice hit — IS, by §7.1–7.4, the Session-3 sub-Dirichlet
$2^{2/3}$-approximation obstruction in archimedean clothing (the same Diophantine quantity that
makes Baker give $v_p=0$). The framework **relocated** the wall and, on inspection, the new
location is the same wall. **Sixth independent confirmation that the barrier is
place-independent.** Lemma D (§4, phantom confined to $y<0$, survival sheet phantom-free) remains
a correct clarification and is kept; it is not a step toward a proof. Framework retired; see
`knowledge/dead_ends.md` and `log/20260628_000000.md`.
