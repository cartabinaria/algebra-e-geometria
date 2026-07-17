---
tags:
  - category/note
  - status/finished
  - topic/analisi-I
  - topic/algebra-e-geometria
date: 17-03-2024 22:16:58
links:
  - "[[lecture-11032024131300|Lecture 11032024131300]]"
  - "[[lecture-24042024092014|Lecture 24042024092014]]"
---
# Norma euclidea
---
## Introduzione
> Preso un [[vettore|vettore]] $x$ appartenente allo [[spazio-euclideo|spazio euclideo]] $\mathbb{R}^{n}$ si definisce la sua **norma**, anche detta **modulo** o **lunghezza**, come
> $$||x|| = \sqrt{<x, x>}$$
> ovvero come la _radice quadrata del [[prodotto-scalare|prodotto scalare]] di $x$ con se stesso_.
> La _norma esiste sempre_ e si ha
> $$||x|| \geq 0 \ \ \ \forall x \in \mathbb{R}^{n}$$

### Esempi
Si ha che
- $n = 1 \implies ||x|| = \sqrt{x \cdot x} = \sqrt{x^{2}} = |x|$, ovvero che nello spazio $\mathbb{R}$ (degli [[scalare|scalari]]) la norma equivale al [[valore-assoluto|valore assoluto]];
- $n = 2 \implies ||x|| = \sqrt{x \cdot x} = \sqrt{x_{1}^{2} + x_{2}^{2}}$, che equivale alla distanza tra l'origine $(0, 0)$ e $x = (a, b)$, di fatto la formula del [[teorema-di-pitagora|teorema di Pitagora]];

<u>Nota bene</u>: i vettori [[coordinate-rispetto-a-una-base|coordinati]] (le [[base|basi]] canoniche) sono vettori di _norma unitaria_, infatti $||e_{j}|| = ||(0, \cdots, 0, 1, 0, \cdots, 0)|| = 1 \ \ \ \forall j \in \{1, \cdots, n\}$.

## Proprietà
### Linearità
$$||\lambda x|| = |\lambda| \cdot ||x|| \ \ \ \forall x \in \mathbb{R}^{n}, \ \forall \lambda \in \mathbb{R}$$

### Positività
$$||x|| \geq 0, \ ||x|| = 0 \iff x = \underline{0} \ \ \ \forall x \in \mathbb{R}^{n}$$[^1]

## Referenze
- [[disuguaglianza-triangolare|Disuguaglianza triangolare]]
- [[quadrato-di-un-binomio|Quadrato di un binomio]]

[^1]: di fatto la [[prodotto-scalare-positivita|stessa del prodotto scalare]]