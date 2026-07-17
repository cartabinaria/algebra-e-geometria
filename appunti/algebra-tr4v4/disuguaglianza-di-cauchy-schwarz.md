---
tags:
  - category/note
  - status/finished
  - topic/analisi-I
  - topic/algebra-e-geometria
date: 18-03-2024 20:57:58
links:
  - "[[lecture-11032024131300|Lecture 11032024131300]]"
  - "[[lecture-24042024092014|Lecture 24042024092014]]"
---
# Disuguaglianza di Cauchy-Schwarz
---
## Introduzione
> La **disuguaglianza di [[cauchy|Cauchy]]-[[schwarz|Schwarz]]** è un risultato importante riguardante i concetti di [[norma-euclidea|norma]] e [[prodotto-scalare|prodotto scalare]], e si formulizza in
> $$|<x, y>| \leq ||x|| \cdot ||y|| \ \ \ \forall x, y \in \mathbb{R}^{n}$$
> Inoltre vale che $|<x, y>| = ||x|| \cdot ||y|| \iff$ $x$ e $y$ sono _collineari_ (puntano nella stessa direzione)[^1].

Si verifica mediante la rappresentazione dei vettori in [[coordinate-polari|coordinate polari]].

## Dimostrazione
Dimostriamo il teorema in $\mathbb{R}^{2}$, sfruttando la rappresentazione dei vettori $v_{1}, v_{2}$ in coordinate polari. Per cui ho $v_{1} = (x_{1}, y_{1})$ e $v_{2} = (x_{2}, y_{2})$.
La rappresentazione polare di $v_{1}, v_{2}$ è
$$v_{1} = (x_{1}, y_{1}) = r_{1} \cdot (\cos{\theta_{1}}, \sin{\theta_{1}})$$
$$v_{2} = (x_{2}, y_{2}) = r_{2} \cdot (\cos{\theta_{2}}, \sin{\theta_{2}})$$
dove $r_{1} = ||(x_{1}, y_{1})||$ e $r_{2} = ||(x_{2}, y_{2})||$.

Allora si ha
$$|<v_{1}, v_{2}>| = |r_{1}\cos{\theta_{1}} \cdot r_{2}\cos{\theta_{2}} + r_{1}\sin{\theta_{1}} \cdot r_{2}\sin{\theta_{2}}| = r_{1}r_{2} \cdot \cos{(\theta_{2} - \theta_{1})}$$

Per cui dobbiamo dimostrare
$$r_{1}r_{2} \cdot \cos{(\theta_{2} - \theta_{1})} \leq r_{1}r_{2}$$
Sapendo che $\cos{(\theta_{2}-\theta_{1})} \in [0, 1]$ automaticamente si dimostra la disuguaglianza.

**Qed**.

## Proprietà
### Angoli
Se $x \neq \underline{0} \neq y$ si ha che
$$0 \leq \frac{|<x, y>|}{||x|| \cdot ||y||} \leq 1$$
dove $\frac{|<x, y>|}{||x|| \cdot ||y||} = a$, e ogni $a \in [0, 1]$ non è che il risultato di $\cos{\theta}$, ovvero il coseno dell'angolo tra i [[vettore|vettori]] $x$ e $y$.

## Referenze
[^1]: per cui [[indipendenza-lineare|linearmente dipendenti]]