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


