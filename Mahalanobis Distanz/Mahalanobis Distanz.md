Kovarianzmatrix

Die Kovarianzmatrix wird berechnet als:

\[
\Sigma = \frac{1}{N} X^T X
\]

---

# Kovarianz Singular Value Decomposition (SVD)

Die Kovarianzmatrix kann als:

\[
\Sigma = U \Lambda U^T
\]

zerlegt werden, wobei:
- \( U \) die Matrix der Eigenvektoren ist
- \( \Lambda \) die Diagonalmatrix der Eigenwerte ist

---

# ZCA Whitening Transformation

ZCA Whitening ist die Inverse der Quadratwurzel der Kovarianzmatrix:

\[
\mathbf{z}_{\text{zca}} = \Sigma^{-\frac{1}{2}}
\]

Die Whitening-Matrix ist:

\[
W_{\text{zca}} = U \Lambda^{\frac{1}{2}} U^T
\]

Alternativ kann es auch als:

\[
W_{\text{zca}} = \Sigma^{-\frac{1}{2}}
\]

ausgedrückt werden.

---

# Mahalanobis-Distanz

Die Mahalanobis-Distanz zwischen einem Vektor \( x \) und dem Mittelwert \( \mu \) ist:

\[
D_m(x, \mu) = \sqrt{(x - \mu)^T \Sigma^{-1} (x - \mu)}
\]

---

# Euklidische Distanz

Die euklidische Distanz zwischen \( x \) und \( \mu \) ist:

\[
D_e(x, \mu) = \sqrt{(x - \mu)^T (x - \mu)}
\]

Die euklidische Distanz zwischen \( x_{\text{zca}} \) und \( y_{\text{zca}} \), unter Verwendung von ZCA Whitening, ist:

\[
D_e(x_{\text{zca}}, y_{\text{zca}}) = \sqrt{\left( \Sigma^{-\frac{1}{2}} x - \Sigma^{-\frac{1}{2}} \mu \right)^T \left( \Sigma^{-\frac{1}{2}} x - \Sigma^{-\frac{1}{2}} \mu \right)}
\]

Dies vereinfacht sich zu:

\[
D_e(x_{\text{zca}}, y_{\text{zca}}) = \sqrt{\left( \Sigma^{-\frac{1}{2}} (x - \mu) \right)^T \left( \Sigma^{-\frac{1}{2}} (x - \mu) \right)}
\]

Und schließlich:

\[
D_e(x, \mu) = \sqrt{(x - \mu)^T \Sigma^{-1} (x - \mu)}
