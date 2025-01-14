ELO-Ranking System
Expected Score Berechnung
Der Expected Score (EA) wird wie folgt berechnet:
$$EA = \frac{1}{1+10^{(R_B-R_A)/D}}$$
Dabei gilt:

$R_B$: ELO-Wert des Gegenspielers i-1
$R_A$: ELO-Wert des Spielers i
$D$: Parameter für die Bedeutung der ELO-Wert-Differenz

Kleinerer D-Wert: Punktedifferenzen haben größere Bedeutung
Größerer D-Wert: Punktedifferenzen werden inflationär



Actual Score
Der tatsächliche Score ($S_A$) in einem Heads-Up Match kann folgende Werte annehmen:

1: Spieler A gewinnt
0: Spieler A verliert
0.5: Unentschieden

ELO-Wert Anpassung
Die Anpassung des ELO-Werts erfolgt nach der Formel:
$$R'_A = R_A + K(S_A - E_A)$$

$K$: Veränderungsfaktor (empfohlener Bereich: 10-32)
Bei Überperformance ($S_A > E_A$): Rating steigt
Bei Unterperformance ($S_A < E_A$): Rating sinkt

Beispiel
Anatoly Karpov (2715) vs. Viktor Korchnoi (2645):

Mit $D = 400$: $E_A ≈ 0.6$
Bei Niederlage und $K = 32$:
$$R'_A = 2715 + 32(0-0.6) = 2695.8$$

Mehrwettbewerber-Umfeld
Unique Matchups
Anzahl einzigartiger Paarungen bei N Teilnehmern:
$$\frac{N(N-1)}{2}$$
Actual Relative Strength
Zwei Möglichkeiten zur Berechnung:

Linear:
$$S_A^{linear} = \frac{N-p_A}{\frac{N(N-1)}{2}}$$
Exponentiell:
$$S_A^{exp} = \frac{a^{N-p_A}-1}{\sum(a^{N-i}-1)}$$
wobei $a \in \mathbb{R}, a \neq 1$

Finale ELO-Anpassung
$$R'_A = R_A + K(N-1)(S_A-E_A)$$
Der Skalierungsfaktor $(N-1)$ berücksichtigt die Teilnehmeranzahl und ist optional bei konstanter oder ähnlicher Teilnehmerzahl.
