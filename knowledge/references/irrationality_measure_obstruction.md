# Why effective irrationality measures for 2^(1/3) do NOT solve the Kuromine Problem

Session 3 (2026-06-25). All computations with Wolfram MCP.

This file records a **decisive negative result** for the direction
"Effective Diophantine approximation to 2^(1/3)" that was marked [HIGH] after
Session 2. The direction does not work, and the reason is structural (not a
matter of improving constants).

## The reframing tested

For a Theorem-5 solution, x = 5 + 332640k, so x ≡ 2 (mod 3); write x = 3a + 2.
Then 2^x = 4·8^a = 4·W^3 with W = 2^a. The equation z^3 = 2^x + 3^y + 5 becomes

    z^3 - 4 W^3 = 3^y + 5 =: h .

This is a cubic **Thue form** F(z, W) = z^3 - 4W^3 taking the value h. Equivalently,
dividing by W^3 and setting α = 4^(1/3) = 2^(2/3),

    (z/W)^3 - α^3 = h / W^3 ,   so   |α - z/W| ≈ h / (3 α^2 W^3).

So z/W is a rational approximation to the cubic irrational α = 2^(2/3), and the
quality of that approximation is governed entirely by h = 3^y + 5.

## The two ways to use an irrationality measure — both fail

Let μ be any **effective** irrationality measure for α: |α - p/q| > c(μ)/q^μ for all
p/q. Best known effective values: Baker μ ≈ 2.955; Chudnovsky ≈ 2.43; Bennett/Voutier
≈ 2.45; the 2025 holonomy bounds (arXiv:2510.04156) sharpen these but remain > 2.
(The Liouville/degree bound is μ = 3.)

### (1) As an approximation-quality test — FAILS
The approximation z/W actually realizes exponent

    κ_real = −log|α − z/W| / log W .

Wolfram (min case x = 332645, y = 166317, a = 110881):
- log W = a·log2 ≈ 76856.9
- log h ≈ y·log3 ≈ 182718
- log|α − z/W| ≈ log h − log(3α^2) − 3 log W ≈ −47854.7
- **κ_real ≈ 0.6226.**

Since κ_real ≈ 0.62 is far **below** any μ ≥ 2, z/W is a *bad* approximation to α.
An irrationality measure is a *lower* bound on |α − p/q|; it only constrains *good*
approximations (κ ≥ μ). A bad approximation is never contradicted. **No information.**

### (2) As a Thue lower bound on the form value — FAILS
Effective irrationality measure ⟹ |z^3 − 4W^3| ≥ c · max(z, W)^(3 − μ).
A contradiction would require h < c · max(z, W)^(3 − μ), i.e.

    log h  <  (3 − μ) · log max(z, W).

Wolfram (μ = 2.43, generous):
- log max(z, W) ≈ 76857.3  (log z ≈ (x/3)log2 ≈ log W)
- RHS = (3 − 2.43)·76857.3 ≈ 43808.7
- LHS = log h ≈ 182718.
- **LHS − RHS ≈ +138909 > 0** ⟹ no contradiction. h is far too large.

## Root cause: 3^y is not a small perturbation

The hypergeometric / holonomy / Thue–Siegel–Baker irrationality machinery proves a
contradiction only when the form value h is **small** relative to the variables —
roughly h ≪ max(z, W)^(3 − μ), i.e. h smaller than about W^(0.57). Here instead

    log h / log W ≈ 182718 / 76857 ≈ 2.378,

so h ≈ W^2.378, i.e. h is comparable to W^2 ≈ z^2 — it is a *large* value of the form,
not a small one. Equivalently, although the *logarithmic* gap
log|3 log z − x log 2| ≈ −47854 looks small, the *value* 3^y + 5 that must be absorbed
is genuinely huge (log 3^y ≈ 0.79·log 2^x; ratio of the two dominant logs
log2^x / log3^y ≈ 1.26). This is the regime of **two comparable dominant S-units**,
which a single cubic irrationality measure cannot resolve.

## What this leaves

- Single 2-term linear forms / irrationality measures: provably insufficient (this file).
- Full 3-log Baker (Matveev): too weak by ~10^10 (constant cc ≈ 4.1×10^13 ⟹ bound
  ≈ −5.6×10^14 vs actual −47854). See `baker_method.md`.
- Local methods: provably insufficient (phantom is a global cube). See `two_adic_structure.md`.

The honest situation: every *currently known effective* global tool (irrationality
measures, 2-term and 3-term linear forms in logarithms) is quantitatively too weak for
the Theorem-5 parameter range. The problem sits in the "two large exponential terms of
comparable size" regime where no effective method is presently strong enough.

## Consequence for strategy

Stop treating "effective approximation to 2^(1/3)" as a near-term [HIGH] lead — it is
quantitatively dead for the same reason Baker is. The remaining non-quantitative hope is
the **algebraic** factorization route (Eisenstein norm form z^2+zw+w^2 with all prime
factors ≡ 1 mod 3, w = 3^j, all powers of 2 and 5 forced into z − w), which does not
rely on size and might yield a contradiction modulo a cleverly chosen prime ≡ 1 mod 3
keyed to k — though this too must respect the soft-obstruction principle (any such
argument must be one the phantom violates, i.e. must use that w = 3^j is an *integer*
power, not just w ∈ Q_p).
