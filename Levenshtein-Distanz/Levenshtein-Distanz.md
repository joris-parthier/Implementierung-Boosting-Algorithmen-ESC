# Normalisierte Levenshtein-Distanz zur Messung sprachlicher Nähe

Um einen Proxy für sprachliche Nähe zu finden, programmierten wir basierend auf der **Levenshtein-Distanz**. Diese Distanz misst die minimale Anzahl von Operationen (Einfügen, Löschen, Ersetzen), die notwendig sind, um ein Wort in einer Sprache in ein Wort einer anderen Sprache zu transformieren. Mithilfe der phonetischen Sprachwörterlisten von **ASJP** (Automated Similarity Judgement Program) berechneten wir die normalisierte Levenshtein-Distanz.

## Definition der normalisierten Levenshtein-Distanz

Die normalisierte Levenshtein-Distanz lässt sich wie folgt schreiben:

$$
d_{\text{norm}}(s_1, s_2) = \frac{D(s_1, s_2)}{\max(\text{len}(s_1), \text{len}(s_2))}
$$

### Bestandteile der Formel:

- $$D(s_1, s_2)$$: Die Levenshtein-Distanz zwischen den Strings $$s_1$$ und $$s_2$$.
- $$\max(\text{len}(s_1), \text{len}(s_2))$$: Die maximale mögliche Länge der beiden Wörter.

Diese Normalisierung ermöglicht es, die Distanz unabhängig von der Wortlänge zu interpretieren.

## Anwendung auf Sprachlisten

Stellvertretend für die Sprachen eines jeden Landes berechneten wir diese Distanz für jedes Wort aus den **ASJP-Wörterlisten** der zu vergleichenden Sprachen. Die ASJP-Wörterlisten basieren auf der Idee der **Swadesh-Liste** und versuchen, eine Sammlung universaler Begriffe und deren phonetischen Repräsentationen bereitzustellen. Dies ermöglicht den Vergleich von Sprachen mit verschiedenen Schriftarten und Lautsystemen.

| ~   | DE     | FR     | IT     | ES     | PL     | NL     | BE     | SE     | GR     | AT     |
|------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
| DE   | 0.0    | 0.8722 | 0.8155 | 0.8591 | 0.9018 | 0.4506 | 0.6131 | 0.624  | 0.9035 | 0.4776 |
| FR   | 0.8722 | 0.0    | 0.6714 | 0.7416 | 0.878  | 0.8539 | 0.5159 | 0.8791 | 0.8665 | 0.8589 |
| IT   | 0.8155 | 0.6714 | 0.0    | 0.4815 | 0.8515 | 0.8011 | 0.7499 | 0.8533 | 0.8199 | 0.7891 |
| ES   | 0.8591 | 0.7416 | 0.4815 | 0.0    | 0.8701 | 0.8357 | 0.7987 | 0.8733 | 0.8472 | 0.8308 |
| PL   | 0.9018 | 0.878  | 0.8515 | 0.8701 | 0.0    | 0.8635 | 0.8696 | 0.894  | 0.8828 | 0.8506 |
| NL   | 0.4506 | 0.8539 | 0.8011 | 0.8357 | 0.8635 | 0.0    | 0.3426 | 0.5996 | 0.8913 | 0.6455 |
| BE   | 0.6131 | 0.5159 | 0.7499 | 0.7987 | 0.8696 | 0.3426 | 0.0    | 0.7105 | 0.8816 | 0.7283 |
| SE   | 0.624  | 0.8791 | 0.8533 | 0.8733 | 0.894  | 0.5996 | 0.7105 | 0.0    | 0.9032 | 0.7101 |
| GR   | 0.9035 | 0.8665 | 0.8199 | 0.8472 | 0.8828 | 0.8913 | 0.8816 | 0.9032 | 0.0    | 0.9028 |
| AT   | 0.4776 | 0.8589 | 0.7891 | 0.8308 | 0.8506 | 0.6455 | 0.7283 | 0.7101 | 0.9028 | 0.0    |

**Tabelle 1:** Eine Similaritätsmatrix basierend auf selbst berechneten Levenshtein-Distanzen für 10 beliebig ausgewählte europäische Länder

Weitere Berechnungen sehen sie hier: https://github.com/joris-parthier/Implementierung-Boosting-Algorithmen-ESC/blob/main/Levenshtein-Distanz/LDN.csv

