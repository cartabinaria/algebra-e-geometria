---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 28-02-2024 21:28:10
links:
  - "[[lecture-27022024091857|Lecture 27022024091857]]"
---
# Spazio vettoriale
---
## Introduzione
> Uno **spazio vettoriale** è una [[strutture-algebriche|struttura algebrica]] composta da un [[insieme|insieme]] $V$ di vettori, due operazioni, la _somma_ tra due vettori e il _prodotto per uno scalare_ tra un reale e un vettore, e una serie di proprietà.
> Gli elementi di uno spazio vettoriale si dicono _[[vettore|vettori]]_, mentre i numeri reali _[[scalare|scalari]]_.

## Operazioni
### Somma
Presi due vettori $u = (u_{1}, \cdots, u_{n})$ e $v = (v_{1}, \cdots, v_{n})$ appartenenti a uno spazio vettoriale $V$, la loro somma $u+v$ è definita come
$$u + v = (u_{1}+v_{1}, \cdots, u_{n}+v_{n})$$

### Prodotto per scalare
Preso un vettore $u = (u_{1}, \cdots, u_{n})$ appartenente a uno spazio vettoriale $V$ e uno scalare $\lambda$ appartenente a $\mathbb{R}$, il prodotto $\lambda u$ è definito come
$$\lambda u = (\lambda u_{1}, \cdots, \lambda u_{n})$$

## Proprietà
Le proprietà degli spazi vettoriali si dividono nelle due operazioni: somma e prodotto per uno scalare.

### Somma
Per l'operazione di somma $+$ valgono le seguenti proprietà:
- _commutativa_ $\implies u + v = v + u$
- _associativa_ $\implies (u + v) + \omega = u + (v + \omega)$
- _[[elemento-neutro|elemento neutro]]_ ($\underline{0}$ o $0_{V}$, ovvero il _vettore nullo_) $\implies \underline{0} + u = u$
- _[[elemento-opposto|elemento opposto]]_ $\implies u + (-u) = 0$

<u>Nota bene</u>: si ha che _lo spazio vettoriale è un [[gruppo|gruppo]] [[abelianita|abeliano]] rispetto alla somma_.

### Prodotto per scalare
Per l'operazione di prodotto per uno scalare $\cdot$ valgono le seguenti proprietà:
- _elemento neutro_ $\implies 1u = u$
- _associativa_ $\implies (\lambda \mu)u = \lambda (\mu u) \ \ \ \forall \lambda, \mu \in \mathbb{R}$
- _distributiva per scalare_ $\implies \lambda (u + v) = \lambda u + \lambda v \ \ \ \forall \lambda \in \mathbb{R}$
- _distributiva per vettori_ $\implies (\lambda + \mu)u = \lambda u + \mu u \ \ \ \forall \lambda, \mu \in \mathbb{R}$

### Conseguenze
Ci sono altre proprietà che seguono da quelle base:
- il _vettore nullo è unico_ e si indica con $0_{V}$ (o $\underline{0}$)
- se $u$ è un vettore di $V$ il suo opposto è unico e si indica con $-u$
- $\lambda \underline{0} = \underline{0} \ \ \ \forall \lambda \in \mathbb{R}$
- $0u = \underline{0} \ \ \ \forall u \in V$
- $\lambda u = \underline{0} \implies \lambda = 0 \lor u = \underline{0}$
- $(-\lambda)u = \lambda(-u) = -\lambda u$

## Applicazioni
Gli _spazi vettoriali sono tra le strutture algebriche più vaste_. Lo sono infatti:
- [[vettore|vettori]] applicati in un punto
- [[matrice|matrici]], perché posso sommare due matrici e moltiplicare una matrice per uno scalare
- [[polinomio|polinomi]], per lo stesso motivo delle matrici
- [[funzione-matematica|funzioni]], per lo stesso motivo dei polinomi
- $\mathbb{R}^{n} = \{(a_{1}, \cdots, a_{n}) | a_{i} \in \mathbb{R}\}$

## Referenze
- [[sottospazio-vettoriale|Sottospazio vettoriale]]