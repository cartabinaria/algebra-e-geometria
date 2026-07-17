---
tags:
  - category/note
  - status/finished
  - topic/analisi-I
  - topic/algebra-e-geometria
date: 17-03-2024 22:12:39
links:
  - "[[lecture-11032024131300|Lecture 11032024131300]]"
  - "[[lecture-14032024140617|Lecture 14032024140617]]"
---
# Ortogonalità
---
## Introduzione
> Due [[vettore|vettori]] $x, y \in \mathbb{R}^{n}$ si dicono **ortogonali** (o **perpendicolari**) sse
> $$<x, y> = 0$$
> ovvero se il loro [[prodotto-scalare|prodotto scalare]] fa 0, e in tal caso si scrive
> $$x \bot y$$

Per esempio si ha che:
- $\underline{0}$ è ortogonale a ogni vettore;
- se $x = (a, b)$ e $y = (-b, a)$ entrambi in $\mathbb{R}^{2}$ si ha $x \cdot y = a(-b) + ba = 0$
- se $x \in \mathbb{R}^{n}$ e $y = \left(\frac{1}{n}, \cdots, \frac{1}{n}\right) \in \mathbb{R}^{n}$ allora $x \cdot y$ è la media di $x$
- i vettori [[coordinate-rispetto-a-una-base|coordinati]] (le [[base|basi]] canoniche) $e_{1}, \cdots, e_{n}$ sono ortogonali a coppie, infatti $j \neq k \implies e_{j} \cdot e_{k} = 0$ è una famiglia ortogonale

## Proprietà
### Punto di minima distanza
Si ha che dati $v \neq \underline{0}$ e $x \in \mathbb{R}^{n}$, il [[distanza-tra-punti-punto-di-minima-distanza-da-una-retta|punto di minima distanza]] $\frac{xv}{|v|^{2}}v$ soddisfa
$$\left(x - \frac{xv}{|v|^{2}}v\right)v = xv - \frac{xv}{|v|^{2}}v \cdot v = xv - xv = 0$$

per cui è ortogonale a $x$.

### Vettore nullo
> L'unico vettore di $\mathbb{R}^{n}$ perpendicolare a tutti gli altri è il vettore nullo $\underline{0}$, ovvero
> $$<v, w> = 0 \ \ \forall w \in \mathbb{R}^{n} \iff v = \underline{0}$$

### Lineare indipendenza
> Siano $v_{1}, \cdots, v_{k} \in \mathbb{R}^{n}$ vettori non nulli e a due a due ortogonali, allora $v_{1}, \cdots, v_{k}$ sono [[indipendenza-lineare|linearmente indipendenti]].

Come importante corollario della proposizione si ha che, per il [[teorema-del-completamento|teorema del completamento]], **il numero massimo di vettori non nulli di $\mathbb{R}^{n}$ ortogonali tra loro è $n$**.

#### Dimostrazione
Devo dimostrare l'indipendenza lineare di $v_{1}, \cdots, v_{k}$, allora uso la definizione e dimostro
$$\lambda_{1}v_{1} + \cdots + \lambda_{k}v_{k} = \underline{0} \iff \lambda_{1} = \cdots = \lambda_{k} = 0$$

Prendiamo in considerazione solo il seguente caso
$$<\underline{0}, v_{1}> = 0$$
Allora sostituisco il vettore nullo con $\lambda_{1}v_{1} + \cdots + \lambda_{k}v_{k}$ e dimostro
$$<\lambda_{1}v_{1} + \cdots + \lambda_{k}v_{k}, v_{1}> = 0 \iff \lambda_{1} = \cdots = \lambda_{k} = 0$$

Quindi, per la bilinearità del prodotto scalare posso scrivere
$$\lambda_{1}<v_{1}, v_{1}> + \cdots + \lambda_{k}<v_{k}, v_{1}> = 0$$
ed essendo i vettori ortogonali a due a due ho $<v_{i}, v_{1}> = 0 \ \ \forall i \neq 1$, perciò non rimane che
$$\lambda_{1} <v_{1}, v_{1}> = 0$$
ed essendo $v_{1}$ non nullo per ipotesi allora il risultato viene $\iff$
$$\lambda_{1} = 0$$

Ripetendo questo procedimento per i $k$ vettori si ottiene che ogni scalare $\lambda$ dev'essere uguale a 0, confermando la tesi.

**Qed**.

## Referenze