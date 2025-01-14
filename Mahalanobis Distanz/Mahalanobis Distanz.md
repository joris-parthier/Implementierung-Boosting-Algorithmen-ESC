# Mahalanobis Distanz

Die Mahalanobis-Distanz (MD) ist ein Distanzmaß im multivariaten Raum, das im Gegensatz zur euklidischen Distanz sowohl die Korrelation zwischen den Variablen als auch die Streuung der Daten berücksichtigt. Sie dient der Messung der Ähnlichkeit zweier Punkte unter Berücksichtigung der statistischen Eigenschaften der Verteilung.

## Mathematische Definition

Die Mahalanobis-Distanz wird durch folgende Formel definiert:

$$
D_M(x) = \sqrt{(x-\mu)^T S^{-1} (x-\mu)}
$$

wobei:
- $x$ = Der Datenpunkt (Vektor), dessen Abstand gemessen wird
- $\mu$ = Der Mittelwertvektor der Verteilung
- $S^{-1}$ = Die Inverse der Kovarianzmatrix der Verteilung
- $T$ = Transposition

## Intuitive Herleitung

Die Mahalanobis-Distanz lässt sich intuitiver verstehen, wenn man sie als zweistufigen Prozess betrachtet:

1. Whitening Space Transformation der Originaldaten
2. Berechnung der euklidischen Distanz im transformierten Raum

### Whitening Space Transformation

Die Whitening Space Transformation (auch Statistical Whitening genannt) ist eine Datentransformation, die drei wesentliche Eigenschaften erfüllt:

1. **Zentrierung der Daten**
   $$\mathbb{E}[X] = 0$$
   Jede Dimension wird so verschoben, dass ihr Mittelwert 0 ist.

2. **Einheitsvarianz**
   $$\text{Var}(X_i) = 1$$
   Jede Dimension wird so skaliert, dass ihre Varianz 1 beträgt.

3. **Dekorrelation**
   $$\text{Cov}(X) = I$$
   Die Kovarianzmatrix der transformierten Daten entspricht der Einheitsmatrix.

Ein spezifisches Beispiel für eine solche Transformation ist die Zero-phase Component Analysis (ZCA) Whitening.

## Berechnung in n Dimensionen

In einem n-dimensionalen Raum lässt sich die Mahalanobis-Distanz als Verkettung folgender Schritte verstehen:

1. Transformation der Daten in den Whitening Space
2. Berechnung der euklidischen Distanz zwischen dem transformierten Datenpunkt und dem (transformierten) Mittelwertvektor

Dies kann mathematisch ausgedrückt werden als:

$$
D_M(x) = \|W(x-\mu)\|_2
$$

wobei $W$ die Whitening-Transformationsmatrix ist, die sich aus der Kovarianzmatrix ableitet:

$$
W = S^{-1/2}
$$
