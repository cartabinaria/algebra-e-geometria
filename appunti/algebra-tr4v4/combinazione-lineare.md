---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 02-03-2024 16:03:41
links:
  - "[[lecture-28022024091940|Lecture 28022024091940]]"
---
# Combinazione lineare
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]] t.c. $v_{1}, \cdots, v_{n} \in V$, una **combinazione lineare** di $V$ è un vettore $v \in V$ del tipo
> $$v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$$
> con $\lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}$.
> Il motivo per cui $v \in V$ è la diretta conseguenza delle [[spazio-vettoriale-proprieta|proprietà degli spazi vettoriali]].

### Osservazione
Per lo stesso motivo, si ha che se $U \leq V$ ([[sottospazio-vettoriale|sottospazio vettoriale]]) t.c. $u_{1}, \cdots, u_{n} \in U$ e $\lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}$, allora $\lambda_{1}u_{1} + \cdots + \lambda_{n}u_{n} \in U$.
Si dimostra usando le proprietà dei sottospazi: se $u_{1}, \cdots, u_{n} \in U$, allora per la _chiusura del prodotto_ anche $\lambda_{1}u_{1}, \cdots, \lambda_{n}u_{n} \in U$. Per la _chiusura della somma_, quindi, si ha che $\lambda_{1}u_{1} + \lambda_{2}u_{2} \in U$, e perciò anche $(\lambda_{1}u_{1} + \lambda_{2}u_{2}) + \lambda_{3}u_{3} + \cdots + \lambda_{n}u_{n} \in U$. Per l'_associatività della somma_ ho proprio $\lambda_{1}u_{1} + \cdots \lambda_{n}u_{n} \in U$.

## Referenze