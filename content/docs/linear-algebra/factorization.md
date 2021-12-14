---
title: "Factorization"
weight: 2
katex: true
---

## What is the _spectrum_?

## Eigendecomposition
**Eigendecomposition** is the diagonalization of the

You can view it as change of basis to the vector space whose basis is formed by the **eigenvectors**.

{{<katex display>}}
A = U \Lambda U^\dagger
{{</katex>}}

where {{<katex>}}U{{</katex>}} is ... and {{<katex>}}\Lambda{{</katex>}} is a diagonal matrix filled with the eigenvalues.

<!-- Transformation/Mapping from/to the **same** vector space -->

{{<katex display>}}
A v = \lambda v
{{</katex>}}

{{<katex display>}}
(A - \lambda I) v = 0
{{</katex>}}
<!-- View with finding λ such that A in upper triangular form (Gauss method) has at least one of the values at the diagonal turned to 0? Diagonal values are not eigenvalues but there is a certain relationship. -->


### Relationship with the determinant

The determinant is 0 if and only at least one of the eigenvalues λ is 0.

{{<hint warning>}}
What is the volume of a circle? And of a square? And of a plane?

It is clearly **0**. They lack the _depth_ dimension!
{{</hint>}}

{{<katex display>}}
\det(A) = \det(\Lambda)
{{</katex>}}

## Singular Value Decomposition (SVD)
<!-- Transformation/Mapping from/to **different** vector space -->

{{<katex display>}}
A = U S V^\dagger
{{</katex>}}
where {{<katex>}}S{{</katex>}} is diagonal matrix
