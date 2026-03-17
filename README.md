# Pi From a Sliding Ruler on a Parabola

**Author:** Sanjin Redzic  
**License:** MIT  
**Repository:** `ninjas1337/Pi-From-A-Sliding-Ruler-On-A-Parabola`

---

## Overview

This repository presents a geometric derivation of $\pi$ via the total angular sweep of the tangent line to the standard parabola $y = x^2$ as the point of tangency traverses the entire real line. The construction requires no trigonometric identities, no series expansions, and no appeal to the unit circle. It recovers $\pi$ as a consequence of a single, elementary observation about the asymptotic behaviour of the arctangent function — which is itself a statement about Euclidean flatness.

The result is classical in its ingredients but is presented here as a self-contained geometric argument with explicit connections to the deeper reason $\pi$ is what it is.

---

## The Construction

Let $f : \mathbb{R} \to \mathbb{R}$ be defined by $f(x) = x^2$. The tangent line to the parabola at the point $(x_0,\, x_0^2)$ has slope

$$m(x_0) = f'(x_0) = 2x_0,$$

and therefore makes an angle

$$\theta(x_0) = \arctan(2x_0)$$

with the positive $x$-axis.

As $x_0$ slides continuously from $-\infty$ to $+\infty$, the tangent line rotates. The **total angular sweep** of this rotation is

$$\Delta\theta = \lim_{x_0 \to +\infty} \arctan(2x_0) \;-\; \lim_{x_0 \to -\infty} \arctan(2x_0) = \frac{\pi}{2} - \left(-\frac{\pi}{2}\right) = \pi.$$

The sliding ruler sweeps exactly $\pi$ radians. No more, no less.

---

## Why This is a Statement About $\pi$, Not Just About Arctan

The derivation above is exact, but it invites a deeper question: *why does the full sweep of the tangent equal $\pi$ and not some other value?*

The answer is Euclidean. The function $\arctan : \mathbb{R} \to (-\pi/2,\, \pi/2)$ has the asymptotic behaviour

$$\lim_{t \to +\infty} \arctan(t) = \frac{\pi}{2}$$

because, in the Euclidean plane, the angle of a line with one component sent to infinity approaches — but never reaches — a right angle. The right angle *is* $\pi/2$ precisely because the interior angles of a Euclidean triangle sum to $\pi$. This is the angle-sum theorem of Euclidean geometry (Euclid, *Elements*, Book I, Proposition 32), which is equivalent to the parallel postulate and therefore a direct characterisation of flat space.

In formal terms, the asymptote $\pi/2$ is a consequence of the fact that in $\mathbb{R}^2$ equipped with the standard Euclidean metric, the full angular range of a directed line through the origin is exactly $\pi$ radians — the measure of a half-turn. The parabola construction is a mechanical device for *integrating* that angular range via a continuous sweep rather than a direct measurement.

The total tangent sweep can be written as the integral

$$\Delta\theta = \int_{-\infty}^{+\infty} \frac{d}{dx}\arctan(2x)\, dx = \int_{-\infty}^{+\infty} \frac{2}{1 + 4x^2}\, dx = \pi,$$

which is a special case of the standard Poisson-kernel integral

$$\int_{-\infty}^{+\infty} \frac{a}{a^2 + x^2}\, dx = \pi \qquad (a > 0).$$

This identity is itself a statement about the residue of a simple pole in the complex plane (see, e.g., Ahlfors, *Complex Analysis*, 3rd ed., §4.5), and the value $\pi$ emerges as the argument of the residue — again rooted in the topology of $\mathbb{R}^2$.

---

## Connection to the Fundamental Theorem of Calculus and Winding Numbers

The tangent sweep has a natural interpretation in terms of winding numbers. The map $x_0 \mapsto e^{2i\arctan(2x_0)}$ traces a semicircle in $\mathbb{C}$, and the total variation of the argument is $\pi$. This is the winding number of the real line, compactified to a circle via the one-point compactification, around the origin — a topological invariant that equals $\pi$ for any smooth curve whose tangent rotates monotonically through a half-turn.

More precisely, consider the Gauss map of the parabola:

$$\mathbf{n}(x_0) = \frac{(-2x_0,\, 1)}{\sqrt{1 + 4x_0^2}} \in S^1.$$

As $x_0$ traverses $\mathbb{R}$, $\mathbf{n}$ sweeps continuously from $(0, -1)$ to $(0, 1)$ along the left semicircle of $S^1$, tracing an arc of length $\pi$. The total curvature of the parabola (in the sense of Milnor, *On the total curvature of knots*, Ann. Math. 1950) is therefore

$$\int_{-\infty}^{+\infty} |\kappa(x)|\, ds = \pi,$$

where $\kappa(x) = 2/(1 + 4x^2)^{3/2}$ is the signed curvature and $ds = \sqrt{1+4x^2}\, dx$ is the arc length element. The factors combine to yield the Poisson kernel above.

---

## Non-Euclidean Remark

The value $\pi$ in this construction is not universal. On a surface of Gaussian curvature $K \neq 0$, the Gauss–Bonnet theorem (do Carmo, *Differential Geometry of Curves and Surfaces*, §4.5) gives

$$\int_C \kappa_g\, ds + \iint_D K\, dA = 2\pi \chi(D),$$

where $\kappa_g$ is the geodesic curvature. For a complete geodesic on a sphere (analogous to our parabola), the integrated geodesic curvature vanishes, and the enclosed area term shifts the effective "half-turn" away from $\pi$. The sliding-ruler construction would yield a different constant on any non-flat surface — demonstrating that $\pi$ is a *signature of Euclidean geometry*, not an abstract constant independent of the ambient space.

---

## Relation to Other $\pi$-Identities

The integral $\int_{-\infty}^{+\infty} \frac{2}{1+4x^2}\,dx = \pi$ is related to a family of classical results:

| Identity | Value | Reference |
|---|---|---|
| $\int_{-\infty}^{+\infty} \frac{1}{1+x^2}\,dx$ | $\pi$ | Cauchy, 1827 |
| $\int_{0}^{+\infty} \frac{\sin x}{x}\,dx$ | $\pi/2$ | Dirichlet, 1829 |
| $\sum_{n=0}^{\infty} \frac{(-1)^n}{2n+1}$ | $\pi/4$ | Leibniz, 1676 |
| $\prod_{n=1}^{\infty} \frac{4n^2}{4n^2-1}$ | $\pi/2$ | Wallis, 1655 |

All are manifestations of the same underlying fact: the residue of $1/(1+z^2)$ at $z = i$ is $1/(2i)$, and the contour integral over the upper half-plane closes with residue $\pi$. The sliding ruler is a geometric, pre-complex-analysis route to the same number.

---

## Files

| File | Description |
|---|---|
| `README.md` | This document |
| `LICENSE` | MIT License |

*Visualization and formal paper forthcoming.*

---

## Citation

If you use or build on this construction, please cite as:

```
Redzic, S. (2026). Pi From a Sliding Ruler on a Parabola.
GitHub repository: https://github.com/ninjas1337/Pi-From-A-Sliding-Ruler-On-A-Parabola
MIT License.
```

---

## References

- Euclid. *Elements*, Book I, Proposition 32. c. 300 BCE.
- Leibniz, G. W. Series for π/4, 1676. (Published in *Acta Eruditorum*, 1682.)
- Wallis, J. *Arithmetica Infinitorum*. Oxford, 1655.
- Cauchy, A.-L. *Résumé des leçons sur le calcul infinitésimal*. Paris, 1823.
- Dirichlet, P. G. L. Sur la convergence des séries trigonométriques. *J. reine angew. Math.*, 4:157–169, 1829.
- Milnor, J. On the total curvature of knots. *Ann. Math.*, 52(2):248–257, 1950.
- Ahlfors, L. V. *Complex Analysis*, 3rd ed. McGraw-Hill, 1979. §4.5.
- do Carmo, M. P. *Differential Geometry of Curves and Surfaces*. Prentice-Hall, 1976. §4.5.
