# ELO-Ranking System

## Expected Score Berechnung

Der Expected Score ($E_A$) wird wie folgt berechnet:

$$
E_A = \frac{1}{1 + 10^{(R_B - R_A) / D}}
$$

### Variablen
- $R_B$: ELO-Wert des Gegenspielers (i-1)
- $R_A$: ELO-Wert des Spielers (i)
- $D$: Parameter für die Bedeutung der ELO-Wert-Differenz

#### Auswirkungen des Parameters $D$
- **Kleinerer D-Wert**: Punktedifferenzen haben größere Bedeutung.
- **Größerer D-Wert**: Punktedifferenzen werden inflationär behandelt.

---

## Actual Score

Der tatsächliche Score ($S_A$) in einem Heads-Up Match kann folgende Werte annehmen:
- **1**: Spieler A gewinnt
- **0**: Spieler A verliert
- **0.5**: Unentschieden

---

## ELO-Wert Anpassung

Die Anpassung des ELO-Werts erfolgt nach der Formel:

$$
R'_A = R_A + K(S_A - E_A)
$$

### Variablen
- $K$: Veränderungsfaktor (empfohlener Bereich: 10–32)

### Auswirkungen
- **Überperformance** ($S_A > E_A$): Der Rating-Wert steigt.
- **Unterperformance** ($S_A < E_A$): Der Rating-Wert sinkt.

---

## Beispiel

Anatoly Karpov ($R_A = 2715$) vs. Viktor Korchnoi ($R_B = 2645$):

### Gegeben:
- $D = 400$
- $E_A ≈ 0.6$
- $K = 32$

Bei einer Niederlage von Karpov:

$$
R'_A = 2715 + 32(0 - 0.6) = 2695.8
$$

---

## Mehrwettbewerber-Umfeld

### Unique Matchups

Die Anzahl einzigartiger Paarungen bei $N$ Teilnehmern:

$$
\text{Unique Matchups} = \frac{N(N-1)}{2}
$$

---

### Actual Relative Strength

Es gibt zwei Möglichkeiten zur Berechnung:

#### Linear
$$
S_A^{linear} = \frac{N - p_A}{\frac{N(N-1)}{2}}
$$

#### Exponentiell
$$
S_A^{exp} = \frac{a^{N-p_A} - 1}{\sum(a^{N-i} - 1)}
$$

**Hinweis:** $a \in \mathbb{R}, a \neq 1$

---

## Finale ELO-Anpassung

Die finale Anpassung des ELO-Werts erfolgt wie folgt:

$$
R'_A = R_A + K(N-1)(S_A - E_A)
$$

### Skalierungsfaktor $(N-1)$
Der Faktor $(N-1)$ berücksichtigt die Teilnehmeranzahl und ist optional bei konstanter oder ähnlicher Teilnehmerzahl.

