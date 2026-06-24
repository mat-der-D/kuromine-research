# Research Hints

These are directions that may be worth exploring. They are not guaranteed to work.

## 1. $p$-adic Methods

The phantom solution lives in $\mathbb{Q}_3$ (the 3-adic numbers). The obstruction to the congruence method is precisely that the phantom solution is a 3-adic integer. Analyzing the 3-adic structure of the equation more carefully may reveal constraints that integer solutions must satisfy but the phantom solution does not (e.g., via 3-adic logarithms or Newton polygons).

## 2. Baker's Method (Linear Forms in Logarithms)

For Diophantine equations involving exponentials, Baker's theorem gives effective lower bounds on linear combinations of logarithms of algebraic numbers. Applied here, it could in principle bound $x$ and $y$ from above, reducing the problem to a finite (though possibly large) computation.

## 3. Connection to Pillai's Conjecture / Catalan's Theorem

The equation $2^x + 3^y = z^3 - 5$ is related to the general problem of representing integers as differences of perfect powers. Mihailescu's theorem (formerly Catalan's conjecture) resolves $a^p - b^q = 1$; techniques used there (cyclotomic fields, Galois theory of $p$-th power residues) may be adaptable.

## 4. Elliptic Curve / Algebraic Geometry Approach

Fixing one variable and viewing the equation as a curve may allow the use of Faltings' theorem (Mordell conjecture) or descent arguments. For example, fixing $x$ and studying $3^y + C = z^3$ as a family of curves.

## 5. Zsygmondy / Primitive Divisor Arguments

For large $x$ and $y$, Zsygmondy's theorem guarantees that $2^x - 1$ and $3^y - 1$ have primitive prime divisors. These primes impose constraints on $z^3 - 5$ that may be exploitable.

## 6. Numerical Search

Verify computationally that no solutions exist for $x \leq N$, $y \leq M$ for large bounds, using the congruence constraint from Theorem 5 to reduce the search space. This does not prove the conjecture but narrows it.
