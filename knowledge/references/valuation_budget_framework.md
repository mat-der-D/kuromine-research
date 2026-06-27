# The Integral Valuation-Budget Framework (Session 38, theory-building under SPECIAL DIRECTIVE)

**Status:** NEW framework built under the THEORY-BUILDING PROTOCOL. Honest verdict up front:
like the three prior frameworks (Coupling-Height S20, Differential-Progression S24,
Cubic-Transversality S27), this one **confirms, does not breach**, the two-comparable-S-units
wall. Its load-bearing lemma (Lemma VB-2) is proved to be **equivalent to the missing effective
$\kappa>1$ gap bound**. It is recorded because (i) the SPECIAL DIRECTIVE mandates the
construction, (ii) it produces the cleanest *positive* statement to date of why the phantom is
inescapable place-by-place, and (iii) the Session-38 multi-prime computation behind it is a
genuine, previously-unrecorded confirmation.

This file is the full statement; the session narrative is in `log/20260704_000000.md`.

---

## 1. Obstruction Diagnosis (sub-step 1)

We diagnose the **exact mathematical nature of the wall** afresh, from the factorization
$2^x+5 = A\cdot B$ with $A=z-3^j$, $B=z^2+z3^j+3^{2j}$, $\gcd(A,B)=1$.

**(D1) The phantom is a global rational cube root and sits on the family's cube-root branch at
every prime.** Session 38 (Wolfram) computed, for the first nominal family member
$(k_x,k_y)=(1,1)$, the three cube roots $z$ of $N=2^x+3^y+5 \bmod p$ and the corresponding
$B=z^2+zw+w^2 \bmod p$ for $p\in\{7,13,19,31,37,43,61,67,73,97,109,127\}$, and verified that the
phantom $z_{\text{ph}}\equiv 10\cdot 3^{-1}$ is **always one of the three family roots** and
$B_{\text{ph}}\equiv 37\cdot 3^{-1}$ is **always among the family $B$-values**. (At $p=37$:
roots $\{21,25,28\}$, $B\equiv\{0,25,0\}$, so $37\mid B$ on $z\in\{21,28\}$, phantom on
$z\equiv28$ — confirming $37\Vert B$, S18.) **Conclusion:** no single-prime congruence on $z$, on
$A$, or on $B$ separates a genuine integer solution from the phantom. This is the soft obstruction,
now verified jointly across 12 primes.

**(D2) The valuation budget is conserved and the phantom escapes only by a fractional split.**
$v_p(A)+v_p(B)=v_p(AB)=v_p(2^x+5)$. At $p=3$: $2^x+5\equiv 1\pmod 3$ universally on the family
($x$ odd $\Rightarrow 2^x\equiv 2$, $2+5\equiv 1$), so $v_3(2^x+5)=0$ (Wolfram, $k_x=0..5$:
$v_3=0$). Therefore
$$v_3(A)+v_3(B)=0 \qquad\text{(universal product-formula constraint at 3).}$$
The **genuine** solution realizes this as $(v_3(A),v_3(B))=(0,0)$ (both 3-adic units — Theorems
I, L). The **phantom** realizes the *same* sum as $(v_3(A),v_3(B))=(1,-1)$:
$A_{\text{ph}}=3$ ($v_3=1$), $B_{\text{ph}}=37/3$ ($v_3=-1$). The phantom has *moved one unit of
3-adic valuation from $B$ into $A$*, keeping the product $2^x+5$ a fixed 3-adic unit. **This is the
precise mechanism of the wall**: the conserved budget makes $v_3$ alone blind to the
genuine/phantom distinction, and the only thing forbidding the phantom's split — that $B=37/3$ is
not an integer ($v_3(B)=-1<0$) — is *automatically* satisfied by any integer solution and so adds
no constraint (this is exactly Lemma D of the Cubic-Transversality framework, $y\ge0$).

**(D3) Why every standard tool fails, restated through (D1)–(D2).** Baker/$p$-adic-Baker
(S5): $v_p(\Lambda_p)=0$ because $2^x+5$ is a $p$-adic unit at $p\in\{2,3\}$ — the budget at those
primes is zero, so no linear form is forced small. Congruence/Skolem (S5): the equation is locally
solvable everywhere by (D1). Thue-Mahler (S18): the additive $5$ prevents a single-S-unit RHS.
Chabauty-Kim (S13): categorical. Irrationality measures (S3): the realized $2^{2/3}$ approximation
is sub-Dirichlet. Decidability (S22): free degree-3 cube. **All trace to the same fact:** the
$p$-adic budget is conserved and the genuine/phantom distinction lives only in the *integrality*
of the split, which is archimedean-archimedean (size) once the place valuations are pinned. The
"missing tool" is a power-saving lower bound $|z^3-3^y|>C(z^3)^\kappa$, $\kappa>1$.

---

## 2. Framework Blueprint (sub-step 2)

**What kind of machinery could bypass (D1)–(D3)?** The three retired frameworks all tried to
*transfer* the one non-degenerate handle (the 3-adic depth $v_3(2^x+5-A^3)=j+1\to\infty$) into an
archimedean size constraint, and each collapsed onto the $2^{2/3}$ approximation. So a transfer
operator is the wrong shape.

The diagnosis (D2) suggests a different shape. The genuine/phantom distinction is the
*integrality of the valuation-split vector* $\mathbf v(A,B)=(v_p(A))_p$ vs $(v_p(B))_p$, subject
to the conserved budget $\mathbf v(A)+\mathbf v(B)=\mathbf v(2^x+5)$. This is not a metric question
and not a transfer; it is a **gluing / cohomological** question: can a locally-consistent
assignment of valuation data (one that is consistent at every place, as (D1) shows the phantom's
is) fail to glue to a *global integer point*? That is precisely the language of a **local-global
obstruction class** — a torsor / Brauer–Manin-type defect — except adapted to the
*exponential* (non-algebraic) setting where the points are $(2^x,3^y)$ on a product of
multiplicative groups, not on a variety.

**Reasoning for this choice.** The wall is a *local-global* failure: locally solvable everywhere
(D1), no global integer solution conjectured. The natural machinery for local-global gaps is a
**cohomological obstruction over the adèles**, but the standard Brauer–Manin obstruction is
*empty* here because the underlying object (a torus $\mathbb G_m\times\mathbb G_m$ cut by an
exponential cube condition) has no Brauer classes that see the additive constant $5$. So we need a
**bespoke obstruction functor** that (a) records the valuation-budget vector at every place, (b)
records the archimedean size as a real-valued "place at infinity" of the *same* object, and (c)
measures the failure of the local data to come from a global *integer* (not merely rational)
point. This is a new structure: an **Integral Valuation-Budget sheaf** on the parameter torus,
with a distinguished "phantom section" that is locally everywhere defined but not integral.

---

## 3. Axiomatic Definition (sub-step 3)

Fix the Theorem-5 family parameters $x=5+332640\,k_x$, $j=55439+55440\,k_y$, $w=3^j$,
$N=2^x+w^3+5$. Let $\mathcal P=\{2,3,5\}\cup\{p:p\equiv1\ (3)\}\cup\{\infty\}$ (all places).

**Definition 1 (Budget space).** Let
$$\mathcal B = \big\{\,\mathbf b=(b_p)_{p\in\mathcal P}\ :\ b_p\in\mathbb Z\ (p<\infty),\
b_\infty\in\mathbb R_{\ge0},\ \textstyle\sum_{p<\infty} b_p\log p \le b_\infty\,\big\}.$$
The inequality is the archimedean dominance constraint (a finite integer's log-size is at least
the log of its $\mathcal P$-part).

**Definition 2 (Split section).** For a candidate cube-root $z$ (rational, denominator a power of
3, encoding both genuine $z\in\mathbb Z$ and the phantom $z=10/3$) define the **split section**
$$\Sigma(z) = \big(\mathbf v(A),\ \mathbf v(B),\ \log^+|A|_\infty\big),\qquad A=z-w,\ B=N/A\ \text{(or }(2^x+5)/A\text{)}.$$
$\Sigma(z)$ assigns to each place the pair of valuations of the two factors plus the archimedean
size of $A$.

**Definition 3 (Integrality functor / obstruction class).** Let
$$\mathrm{ob}(\Sigma) \;=\; \big[\,\min_p\big(\min(v_p(A),v_p(B))\big)\,\big]\ \in\ \mathbb Z_{\le0},$$
the most negative valuation appearing in the split. Define $\Sigma$ to be **integral** iff
$\mathrm{ob}(\Sigma)=0$ (equivalently $A,B\in\mathbb Z$). The **phantom defect** of $\Sigma$ is
$\partial(\Sigma)=-\mathrm{ob}(\Sigma)\ge0$; $\partial=0$ iff integral, $\partial\ge1$ for the
phantom (which has $v_3(B)=-1$, so $\partial=1$).

**Definition 4 (Budget torus and the genuine locus).** The parameter torus is
$\mathbb T=(\mathbb Z_2\times\mathbb Z_3)/{\sim}$ carrying the two free bijective coordinates
$k_y$ (controls $\mathbf v$ at $2$, Theorem P) and $k_x$ (controls $\mathbf v$ at $3$, Theorem J),
per Observation Q. The **archimedean height** on $\mathbb T$ is the affine function
$$h(k_x,k_y)=D=x\log2-(2j+1)\log3=c_0+k_xP_c-k_yQ_c,$$
$P_c=332640\log2$, $Q_c=110880\log3$, $\rho=P_c/Q_c=3\log2/\log3$. The **genuine locus**
$\mathcal G\subset\mathbb T$ is the set of $(k_x,k_y)$ for which the unique integer $A$ in the band
$[e^{D}/3,\,3e^{D}]$ satisfies $v_3(2^x+5-A^3)=j+1$ (Theorem N) **and** $A$ is the genuine integer
cube-root distance.

These are the formal objects. The framework's content is the relation between $\partial$, the
height $h$, and membership in $\mathcal G$.

---

## 4. Problem Translation and Test Lemmas (sub-step 4)

**Translation.** A Kuromine solution with $x\ge6,y\ge2$ is exactly an integral split section
$\Sigma(z)$ ($\partial(\Sigma)=0$) whose parameters $(k_x,k_y)\in\mathbb T$ lie on the genuine
locus $\mathcal G$ with $z\in\mathbb Z$. The phantom is the section $\Sigma(10/3)$ with
$\partial=1$, parameters $(k_x,k_y)=(0,-1)$ (off the survival sheet $k_y\ge0$, Lemma D).

**Lemma VB-1 (Budget rigidity — PROVED, Session 38).** On the survival sheet $k_y\ge0$ (equivalently
$j\ge1$, $y\ge0$), every integral split section has $\mathbf v_3(A)=\mathbf v_3(B)=0$ and the
phantom defect $\partial$ is structurally $0$. Equivalently, the phantom's $(v_3(A),v_3(B))=(1,-1)$
split is confined to $k_y<0$.
*Proof.* $v_3(A)+v_3(B)=v_3(2^x+5)=0$ universally (Wolfram). $B$ integer $\Rightarrow v_3(B)\ge0$;
$A$ integer $\Rightarrow v_3(A)\ge0$; the sum being $0$ forces both $=0$. The phantom's $v_3(B)=-1$
requires $w=3^j$ with $j<0$, i.e. $y<0$. $\square$
**This is exactly Cubic-Transversality Lemma D, re-derived through the budget.** It is correct and
kept, but, as before, gives **no constraint on genuine solutions** (their $\partial=0$ is
automatic).

**Lemma VB-2 (Height–Integrality Incompatibility — the crux, UNPROVEN).** *Conjecture:* for all
$(k_x,k_y)\in\mathbb T$ with $k_x\ge1$, $k_y\ge0$, $D\ge0$, the unique integer $A$ in the band
$[e^D/3,3e^D]$ does **not** satisfy $v_3(2^x+5-A^3)=j+1$. (I.e. $\mathcal G\cap\{k_x\ge1\}=\varnothing$.)

**Status of Lemma VB-2: equivalent to the missing $\kappa>1$ tool (Session 38 analysis).** The
band has width $\sim e^D$; for $A$ to hit depth $j+1$ it must equal the genuine 3-adic cube-root
truncation to depth $j+1$, an integer of size $\sim 2^{x/3}$. Whether the band of size $e^D$
contains that specific deep integer is exactly the question "is $|z^3-3^y|=2^x+5$ small relative to
$(z^3)^\kappa$" — the realized-gap-exponent question (S26/S31, $E\in(2/3,1)$). The Session-34
Convergent–Depth Trade-off (Theorem S) shows small $D$ (small band) forces huge $k_x$ (huge depth
$j+1$), with the Theorem-N corollary excluding each *concrete* near-boundary witness (S34:
$k_x=16836$, $A\in[43,129]$; S37: $k_x=84180$, $A\in\{1..5\}$, killed by Theorem P alone). But
**proving** $\mathcal G\cap\{k_x\ge1\}=\varnothing$ for *all* $k_x$ requires bounding the gap
$2^x+5$ below by $C(z^3)^\kappa$, $\kappa>1$ — which Baker gives only with $v_p(\Lambda)=0$
(useless, S5) and which no effective measure supplies (sub-Dirichlet, S25). **Lemma VB-2 is
therefore provably equivalent to the open target, not a way around it.**

---

## 5. Verdict

The Integral Valuation-Budget framework reorganizes the obstruction into its cleanest form to date —
a conserved place-by-place valuation budget whose genuine realization $(0,0)$ and phantom
realization $(1,-1)$ differ only by an integrality (archimedean) condition — and re-derives
Cubic-Transversality Lemma D as Lemma VB-1. Its only non-trivial lemma (VB-2) is **equivalent to
the missing effective $\kappa>1$ gap bound**. It is the **seventh independent confirmation** that
every attack face returns the two-comparable-S-units wall, now from the local-global /
valuation-budget side. **DO NOT REOPEN** without a tool that bounds $|z^3-3^y|$ below by a power
$\kappa>1$ of $z^3$ (equivalently, beats the Dirichlet floor on the $2^{2/3}$ approximation).

**Genuine residual facts produced (kept):**
- The multi-prime joint portrait (Session 38, Wolfram): the phantom cube-root branch
  $z_{\text{ph}}\equiv10\cdot3^{-1}$ and $B_{\text{ph}}\equiv37\cdot3^{-1}$ lie on the family's
  cube-root/$B$ branch at every prime $p\in\{7,\ldots,127\}$ — the sharpest single demonstration of
  the soft obstruction across many primes simultaneously.
- The budget-cancellation identity $v_3(A)+v_3(B)=v_3(2^x+5)=0$ universal, with genuine $(0,0)$ vs
  phantom $(1,-1)$ — the precise reason 3-adic valuation alone is blind to the distinction.
