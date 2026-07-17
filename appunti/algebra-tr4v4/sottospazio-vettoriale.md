---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 28-02-2024 21:50:39
links:
  - "[[lecture-27022024091857|Lecture 27022024091857]]"
  - "[[lecture-28022024091940|Lecture 28022024091940]]"
---
# Sottospazio vettoriale
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]], un [[definizione-di-essere-sottoinsieme|sottoinsieme]] $S \subseteq V$ si dice **sottospazio vettoriale** di $V$ se a sua volta è uno spazio vettoriale. In particolare deve verificare le 3 condizioni di seguito:
> 1. $S \neq \varnothing$, _non dev'essere l'[[definizione-di-insieme-vuoto|insieme vuoto]]_;
> 2. $\forall u, v \in S \ \ \ u + v \in S$, ovvero dev'essere _chiuso rispetto alla somma_;
> 3. $\forall u \in S, \forall \lambda \in \mathbb{R} \ \ \ \lambda u \in S$, ovvero dev'essere _chiuso rispetto al prodotto per scalari_;
> 
> In tal caso, $S$ è sottospazio di $V$, e si indica con
> $$S \leq V$$

<u>Nota bene</u>: _per verificare la prima condizione è sufficiente dimostrare che $\underline{0} \in S$_. Infatti se $S \neq \varnothing$ allora $\exists u \in S$, che posso moltiplicare per lo scalare $0$ e ottenere $\underline{0}$, che quindi sarà in $S$ per la chiusura rispetto al prodotto.

## Leggi generali
$$\forall u, v \in V, \ \forall \lambda, \mu \in \mathbb{R} \ \ \ \lambda u + \mu v \in V$$
per unione della 2° condizione con la 3°.

$$\forall u \in V: u \neq 0, \forall \lambda, \mu \in \mathbb{R} \ \ \ \lambda \neq \mu \implies \lambda u \neq \mu u$$
con dimostrazione per [[implicazione|contronominale]].

$$\{\underline{0}\} \leq V \ \land \ V \leq V \ \ \ \ \forall V$$
ovvero che fissato uno spazio vettoriale $V$, si ha che _il sottospazio banale e $V$ stesso sono sempre sottospazi di $V$_.

## Casistiche
Preso un $U \leq V$, sono due le casistiche possibili:
1. $U = \{\underline{0}\}$[^1], in tal caso si dice che $U$ è un **sottospazio nullo** (o **banale**);
2. $U \neq \{\underline{0}\} \implies \exists u \in U : u \neq \underline{0}$, in questo caso $U$ contiene tutti i vettori del tipo $\lambda u$ al variare di $\lambda \in \mathbb{R}$ (che sono tutti diversi, come dimostrato in precedenza); allora $U$ **contiene infiniti vettori**;

Quindi _in un sottospazio o c'è un solo vettore (nullo), o ci sono infiniti vettori_[^2].

## Casi significativi
- [[sottospazi-vettoriali-di-r2|Sottospazi vettoriali di R2]]
- [[sottospazi-vettoriali-di-r3|Sottospazi vettoriali di R3]]
- [[sottospazi-vettoriali-dei-polinomi|Sottospazi vettoriali dei polinomi]]

### Esempio
Verifichiamo per esempio che $S = \{(x, 3x) | x \in \mathbb{R}\}$ è sottospazio di $V$ ($\mathbb{R}^{2}$). Quindi:
1. $S \neq \varnothing$, sì perché $(0, 3 \cdot 0) = (0, 0) \in S$
2. $S$ è chiuso rispetto alla somma perché preso $u_{1} = (x_{1}, 3x_{1})$ e $u_{2} = (x_{2}, 3x_{2})$ appartenenti a $S$, la loro somma $u_{1} + u_{2} = (x_{1} + x_{2}, 3x_{1} + 3x_{2}) = (x_{1} + x_{2}, 3 \cdot (x_{1} + x_{2})) \in S$ per definizione
3. $S$ è chiuso rispetto al prodotto perché preso $u_{1} = (x_{1}, 3x_{1})$ e $\lambda \in \mathbb{R}$, il prodotto $\lambda u_{1} = (\lambda x_{1}, \lambda 3 x_{1}) = (\lambda x_{1}, 3(\lambda x_{1})) \in S$ per definizione

Quindi $S$ è un sottospazio di $V$.
<u>Nota bene</u>: essendo $\mathbb{R}^{2}$ in [[funzione-biiettiva|corrispondenza biunivoca]] con il piano cartesiano, il sottospazio $S$ corrisponde alla retta $y = 3x$.

Verifichiamo ora se $S = \{(x_{1}, x_{2}, x_{3}) | x_{1} + 2x_{2} - x_{3} \geq 0\}$ è sottospazio di $V = \mathbb{R}^{3}$. Quindi:
1. $S \neq \varnothing$, sì perché $(0, 0, 0) \in S$
2. $S$ è chiuso rispetto alla somma perché preso $u_{1} = (x_{1}, x_{2}, x_{3})$ e $u_{2} = (y_{1}, y_{2}, y_{3}) \in S$, la somma $u_{1} + u_{2} = (x_{1} + y_{1}, x_{2} + y_{2}, x_{3} + y_{3})$ per essere in $S$ dovrebbe valere che $(x_{1} + y_{1}) + 2(x_{2} + y_{2}) - (x_{3} + y_{3}) = x_{1} + y_{1} + 2x_{2} + 2y_{2} - x_{3} - y_{3} = x_{1} + 2x_{2} - x_{3} + y_{1} + 2y_{2} - y_{3} \geq 0$, vero perché somma di due positivi per le ipotesi
3. $S$ però non è chiuso rispetto al prodotto, infatti preso $u_{1} = (x_{1}, x_{2}, x_{3})$ e $\lambda \in \mathbb{R}$, si ha che $\lambda u_{1} = (\lambda x_{1}, \lambda x_{2}, \lambda x_{3})$, che per stare in $S$ deve accadere che $\lambda x_{1} + 2\lambda x_{2} - \lambda x_{3} = \lambda (x_{1} + 2x_{2} - x_{3}) \geq 0$, che non è vero $\forall \lambda \in \mathbb{R}$ (si pensi a $\lambda$ negativi)

Quindi $S$ non è un sottospazio di $V$.

## Referenze
[^1]: $U$ contiene il [[assioma-del-singoletto|singoletto]] del _vettore nullo_
[^2]: la somiglianza con il numero di soluzioni possibili di un [[sistema-lineare|sistema lineare]] non è un caso