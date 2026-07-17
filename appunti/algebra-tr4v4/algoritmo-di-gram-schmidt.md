---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 05-05-2024 21:44:50
links:
  - "[[lecture-30042024091716|Lecture 30042024091716]]"
---
# Algoritmo di Gram-Schmidt
---
## Introduzione
> Data una [[base|base]] di uno [[spazio-vettoriale|spazio vettoriale]] $W$, l'**algoritmo di Gram-Schmidt** serve _per trovare una [[base-ortogonale|base ortogonale]]_ (o [[base-ortonormale|ortonormale]]) _di $W$_, ossia una _base di vettori perpendicolari tra loro_ (e, se ortonormale, di [[norma-euclidea|norma]] 1).

## Algoritmo
L'algoritmo _si appoggia pesantamente sulle proprietà delle [[proiezione-ortogonale|proiezioni ortogonali]]_ per ottenere una base ortogonale di uno spazio a partire da un'altra.

Sia $\{w_{1}, \cdots, w_{k}\}$ una base di $W$, allora una base ortogonale $\{u_{1}, \cdots, u_{k}\}$ di $W$ si ottiene ponendo:
- $u_{1} = w_{1}$
- $u_{2} = w_{2} - proj_{u_{1}}(w_{2})$, in quanto $\bot u_{1}$
- $u_{3} = w_{3} - proj_{u_{2}}(w_{3}) - proj_{u_{1}}(w_{3})$, in quanto $\bot u_{1} \land \bot u_{2}$
- ...
- $u_{k} = w_{k} - proj_{u_{1}}(w_{k}) - \cdots - proj_{u_{k-1}}(w_{k})$, in quanto $\bot u_{1} \land \cdots \land \bot u_{k-1}$

Se venisse chiesta una base ortonormale, allora definita la base ortogonale $\{u_{1}, \cdots, u_{k}\}$, bisognerebbe semplicemente porre
$$f_{1} = \frac{u_{1}}{||u_{1}||}, \cdots, f_{k} = \frac{u_{k}}{||u_{k}||}$$
per ottenere quindi la base ortonormale $\{f_{1}, \cdots, f_{k}\}$.

<u>Nota bene</u>: _se vengono forniti 3 vettori, 2 dei quali sono già perpendicolari tra di loro, allora non conviene cambiarli tutti e 3, ma piuttosto adattare il primo ai due perpendicolari_! Si fa un solo calcolo invece che 2.

## Referenze