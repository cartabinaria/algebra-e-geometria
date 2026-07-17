---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-04-2024 22:16:38
links:
  - "[[lecture-16042024091615|Lecture 16042024091615]]"
---
# Autovettore
---
## Introduzione
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ un'[[applicazione-lineare|applicazione lineare]], allora un [[vettore|vettore]] $v \in \mathbb{R}^{n}$ si dice **autovettore** di [[autovalore|autovalore]] $\lambda \in \mathbb{R}$ se per $v \neq \underline{0}$ si ha:
> $$f(v) = \lambda v$$

Un'applicazione lineare deforma lo spazio dei vettori su cui viene applicata. Alcuni di questi **vettori rimangono nello stesso [[sottospazio-generato|spazio generato]]** ($Span$) **mantenendo quindi la loro direzione**: vengono **mappati in un multiplo di loro stessi**.

## Importanza
Di una [[matrice|matrice]] che [[applicazione-lineare-definita-da-una-matrice|identifica un'applicazione lineare]] vogliamo fare il [[cambio-di-base|cambio di base]] in modo che tale matrice sia [[matrice-diagonale|diagonale]], _per questioni di comodità_. Ebbene questa base, affinché la matrice associata sia diagonale, dovrà essere composta da autovettori in colonna.

Per cui se esiste una base di questo tipo, l'applicazione lineare definita da questa matrice si dice [[diagonalizzabilita|diagonalizzabile]].

## Referenze