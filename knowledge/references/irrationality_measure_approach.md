# Effective Irrationality Measure Approach (cube root of 4 / 2^(2/3))

Session 3 (2026-06-25). All numerics by Wolfram MCP.

## Goal

Test the [HIGH] "effective Diophantine approximation to 2^(1/3)" direction concretely:
translate the reframed equation `z^3 - 2^x = 3^y + 5` into a rational approximation of a
fixed cube root, plug in the best known effective irrationality measure, and determine
whether it forces a contradiction.

## Exact setup

For a Theorem-5 solution, `x = 5 + 332640 k` (k >= 1) and `y = 166317 + 166320 m` (m >= 0).
Note `x ≡ 2 (mod 3)` always (since `5 ≡ 2` and `332640 ≡ 0 (mod 3)`), so write

    x = 3a + 2,   a = (x - 2)/3 = 1 + 110880 k.

Then `2^x = 4 · 8^a = 4 · (2^a)^3`. Set `q = 2^a` and `α = 4^(1/3) = 2^(2/3)` (so `α^3 = 4`).
With `D = 3^y + 5`, the equation `z^3 - 2^x = D` becomes `z^3 - α^3 q^3 = D`, and the
**exact identity** (verified symbolically in Wolfram) holds:

    z/q - α  =  (z^3 - α^3 q^3) / ( q^3 · ((z/q)^2 + (z/q)α + α^2) )
             =  D / ( q^3 · ((z/q)^2 + (z/q)α + α^2) ).

Since `z/q → α`, the denominator `→ 3α^2 = 3·4^(2/3) ≈ 7.5595`. Hence

    |z/q - α| = D / (q^3 · 3α^2)  · (1 + o(1)),   q = 2^a.

So `p/q = z/2^a` is a rational approximation to the fixed algebraic irrational `α = 2^(2/3)`
of quality

    |α - p/q| ≈ c' · q^(-κ_actual),     κ_actual = 3 - logD/logq,
    logD = y log 3,   logq = a log 2 = (x-2)/3 · log 2.

## Best known effective irrationality measure

Bennett-type effective measures give, for cube roots of small-height rationals,

    |2^(1/3) - p/q| > 0.25 · q^(-2.4325)   (best known; ~2.43–2.45 class).

Bennett's method covers `(b/a)^(1/n)`, so `4^(1/3) = (4/1)^(1/3)` is in scope; the precise
published constant/exponent for `4^(1/3)` was not located, but the exponent is in the same
~2.43 class and **the exponent value, not the constant, drives the conclusion**.

Write the theorem as `|α - p/q| > c · q^(-κ_thm)`, `κ_thm ≈ 2.4325`.

## When does this force a contradiction?

A solution would make `p/q = z/2^a` approximate α *better* than the theorem allows iff

    κ_actual > κ_thm,   i.e.   3 - logD/logq > κ_thm,

equivalently (dropping the negligible additive constant `log(0.25·3α^2)/log3 ≈ 0.58`):

    **y < ((3 - κ_thm)/3) · (log2/log3) · (x - 2)**,
    i.e. with κ_thm = 2.4325:   y < 0.119351 (x - 2),   equivalently   x > 8.3787 y.

In that region the forced gap is smaller than Bennett's lower bound — impossible. **So:**

> **Result (Session 3).** No Theorem-5 solution exists with `x > 8.3787 y`
> (the 2^x-dominant tail). Rigorous, via the exact identity above + Bennett's measure.

## What it CANNOT do (sharp negative bound)

The coefficient is `(3-κ)/3 · log2/log3`. Since every irrational has irrationality
exponent ≥ 2 (Dirichlet), no effective measure can use `κ < 2`. The **best-possible**
threshold (`κ → 2+`) is

    y < 0.21031 (x - 2)   ⇔   x > 4.7549 y.

The "balanced" line `2^x = 3^y` is `x = 1.585 y`. Therefore the entire region

    **x ≤ 4.7549 y   (which contains the whole balanced & 3^y-dominant regime)**

is provably **out of reach of this single-cube-root method, even with an optimal measure**.

Reason it is structurally one-sided: on the 3-side, `y = 3j` (Session 1) makes `3^y = (3^j)^3`
an *exact cube*, so the analogous ratio `z/3^j → 1` is rational — there is **no fixed
algebraic irrational** to approximate. The cube-root-approximation method only bites when the
dominant term's non-cube residue is a fixed constant (here `2^x = 4·(2^a)^3`, residue `4`).

## Effect on the Theorem-5 family

Eliminated region `x > 8.3787 y` removes, for each fixed `m` (i.e. fixed `y`), all
sufficiently large `k`. Smallest surviving cases (regime B, `x ≤ 8.3787 y`):

| m | y          | k eliminated | k surviving |
|---|------------|--------------|-------------|
| 0 | 166317     | k ≥ 5        | k = 1..4    |
| 1 | 332637     | k ≥ 9        | k = 1..8    |
| 2 | 498957     | k ≥ 13       | k = 1..12   |
| 3 | 665277     | k ≥ 17       | k = 1..16   |

So Bennett removes an infinite, cofinite-in-`k` slice for every `y`, but leaves finitely
many small-`k` cases per `y` and infinitely many `y` — it does **not** finish the problem.

## Take-away for the research program

- The [HIGH] irrationality-measure direction is **partially successful and now precisely
  quantified**: it is a real reduction (kills `x > 8.379 y`), not a dead end, but it is
  provably incapable of closing the problem alone. Downgrade its expectations accordingly.
- The **hard core** is `x ≲ 4.75 y` (in particular the balanced/`3^y`-heavy regime), where
  both `2^x` and `3^y` are "active". That region is the natural home of a two-term linear
  form `Λ = 3 log z - x log 2 - …` (Baker) or a Thue-Mahler treatment of `z^3 - w^3 = 2^x+5`
  — not single rational approximation.
- Combining: a future proof likely needs (i) Bennett's measure for the `2^x`-heavy tail
  `x > 8.379 y`, plus (ii) a Baker/Thue-Mahler argument for `x ≤ 8.379 y`. The reduction in
  (i) caps the relevant `log z` in (ii) by `log z ≲ (x)/3 · log2 ≲ (8.379/3) y log2`, i.e.
  ties the height of `z` to `y`. This is the most concrete handle produced so far.
