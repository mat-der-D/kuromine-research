# Current Focus

**Session:** 2026-06-25 (first research session)

**Current direction:** Two-place (archimedean × 3-adic) linear-forms-in-logarithms
(Baker's method), reframed from the HIGH-priority p-adic direction.

**Why this direction:** The HIGH-priority "p-adic analysis of the phantom" direction was
explored and produced a decisive clarification: the phantom $(5,-3,10/3)$ is *exactly* the
fibre $z^3-2^x-5=3^y$ at $x=5,\,y=-3$ (since $(10/3)^3-32-5=1/27=3^{-3}$). This shows a
**purely** 3-adic argument cannot work — the phantom is a genuine $\mathbb{Q}_3$-point and the
real branch $y\ge 2$ only separates from it at the **archimedean** place. The right tool is
therefore Baker's method combining the real and 3-adic places.

**What has been done in this direction:**
- Verified known solutions, phantom identity, and Theorem-4 mod-9 constraint (only
  $x\equiv 5\pmod 6$ survives for $y\ge 2$). [Wolfram]
- Computed 3-adic admissible-$x$ density: stabilises at ~0.18, does NOT decay → sharp
  confirmation of the congruence "hard wall". Recorded in
  `knowledge/references/three_adic_density.md`. [Wolfram]
- Reduced the three-term equation to two-term archimedean linear forms $\Lambda_1=3\ln z-x\ln2$
  (Regime A) and the symmetric Regime B; derived inequality (A). Recorded in
  `knowledge/references/baker_method.md`.
- Identified the **closing mechanism**: archimedean form bounds only $x\ln2-y\ln3$; a 3-adic
  (Yu) form bounding $y=v_3(z^3-2^x-5)$ is needed to bound $x,y$ individually.
- Extended exact numerical search (integer Newton cube root, verified correct): no new
  solutions for $x\equiv5\pmod6,\ x\le600,\ y\le300$. Only $(5,3,4)$. [Wolfram]
- Rough Matveev estimate: raw bound likely $x\lesssim 10^{14}$–$10^{16}$, reducible.

**Blockers:**
- Need explicit Matveev constants (archimedean) and Yu constants (3-adic) worked out for the
  specific heights here to get a concrete, citable bound.
- The two inequalities must be combined carefully; the constant term $+5$ and the $O(3^{-y})$
  error need rigorous handling.

**Notes:** This session connected the two top directions (p-adic ↔ Baker). They are not
independent: the correct proof is a *two-place* linear-forms argument. Next session should
make the archimedean Matveev bound explicit.
