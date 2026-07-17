---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 05-05-2024 18:12:58
links:
  - "[[lecture-24042024092014|Lecture 24042024092014]]"
---
# Base ortonormale
---
## Introduzione
> Si definisce **base ortonormale** di uno [[spazio-vettoriale|spazio vettoriale]] $\mathbb{R}^{n}$ una [[base|base]] costituita da $n$ _[[vettore|vettori]] ortonormali_, ovvero tali per cui per $v_{1}, \cdots, v_{n}$ vale che
> $$<v_{i}, v_{j}> = \delta_{ij} = \begin{cases}1 & i = j \\ 0 & i \neq j\end{cases} \ \ \ \forall i, j \in \{1, \cdots, n\}$$
> ovvero che il [[prodotto-scalare|prodotto scalare]] a due a due di ogni vettore della base sia uguale al _[[delta-di-kronecker|delta di Kronecker]]_, ossia a 1 $\iff$ $v_{i} = v_{j} \iff i = j$; e a 0 se invece $v_{i} \neq v_{j} \iff i \neq j$.
> Nota la differenza con la [[base-ortogonale|base ortogonale]], per cui non è richiesto che $||v_{i}|| = 1$ perché i vettori della base non devono essere [[normalizzazione|normalizzati]].

### Esempi
Si prendano $e_{1}, e_{2} \in \mathbb{R}^{2}$: questi formano una base ortonormale, non per niente quella [[base-canonica|canonica]]. Così come $e_{1}, e_{2}, e_{3} \in \mathbb{R}^{3}$.
In generale diremo che _$\{e_{1}, \cdots, e_{n}\}$ è una base ortonormale di $\mathbb{R}^{n}$_.

## Proposizioni
### Coordinate rispetto a una base
> Sia $\beta = \{v_{1}, \cdots, v_{n}\}$ una base ortonormale di $\mathbb{R}^{n}$, allora preso un vettore $v \in \mathbb{R}^{n}$ si ha che
> $$(v)_{\beta} = (<v, v_{1}>, \cdots, <v, v_{n}>)$$
> ovvero che le sue [[coordinate-rispetto-a-una-base|coordinate rispetto alla base]] $\beta$ sono il prodotto scalare tra $v$ e ogni vettore della base.

#### Dimostrazione
Sappiamo che $v$ è [[combinazione-lineare|combinazione lineare]] di $v_{1}, \cdots, v_{n}$, ovvero
$$v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$$

Per cui, per la definizione di coordinate, dobbiamo solo dimostrare che $\lambda_{1} = <v, v_{1}>, \cdots, \lambda_{n} = <v, v_{n}>$.

Preso allora un generico $v_{i}$ dimostro $<v, v_{i}> = \lambda_{i}$:
$$<v, v_{i}> = <\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}, v_{i}>$$
che per la bilinearità del prodotto scalare si traduce in
$$<v, v_{i}> = \lambda_{1}<v_{1}, v_{i}> + \cdots + \lambda_{i}<v_{i}, v_{i}> + \cdots + \lambda_{n}<v_{n}, v_{i}>$$

Quindi, essendo $v_{1}, \cdots, v_{n}$ ortonormali tra loro, "sopravviverà" soltanto $<v_{i}, v_{i}> = 1$, da cui
$$<v, v_{i}> = \lambda_{i}$$

**Qed**.

## Referenze