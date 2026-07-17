---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 01-03-2024 15:09:26
links:
  - "[[lecture-27022024091857|Lecture 27022024091857]]"
  - "[[lecture-19032024091914|Lecture 19032024091914]]"
---
# Sistema lineare omogeneo
---
## Introduzione
> Un [[sistema-lineare|sistema lineare]] si dice **omogeneo** se _la colonna dei termini noti $\underline{b} = 0$_. _Tutti i sistemi omogenei hanno almeno la soluzione nulla $\underline{x} = (0, \cdots, 0)$_: se viene chiesto di discuterne uno è quindi necessario capire se la soluzione è solo una (quella nulla) o se sono infinite.

## Osservazioni
Dalle proprietà del [[nucleo|kernel]] che ci dicono che $\ker(f) \leq V$ per un'[[applicazione-lineare|applicazione lineare]] $f: V \to W$, sapendo che per definizione corrisponde all'insieme delle soluzioni di un sistema lineare omogeneo, e riscrivendo $f$ come definita da una matrice $A$ t.c. $L_{A} = f$ ([[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]]), concludiamo che tale insieme di soluzioni è sempre un sottospazio di $\mathbb{R}^{n}$, perché $\ker(L_{A}) \leq V$.

## Referenze