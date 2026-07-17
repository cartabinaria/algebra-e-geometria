---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 13-04-2024 13:32:05
links:
  - "[[lecture-09042024091802|Lecture 09042024091802]]"
---
# Matrice invertibile
---
## Introduzione
> Una [[matrice|matrice]] $A \in M_{n}(\mathbb{R})$ (quadrata) si dice **invertibile** $\iff$
> $$\exists B \in M_{n}(\mathbb{R}) : AB = BA = I_{n}$$
> ovvero se esiste una matrice $B$ dello stesso ordine di $A$ tale che il [[matrice-prodotto|prodotto]] $AB$ e $BA$ dia sempre la [[matrice-identita|matrice identità]]. In tal caso, $B$ si dice l'_inversa_ di $A$[^1] e si indica con
> $$A^{-1}$$
> <u>Nota bene</u>: _di solito il prodotto non è commutativo, ma in questo caso lo dev'essere_.

## Calcolo
Un metodo standard per calcolare l'inversa di una matrice quadrata $A$ invertibile, ovvero per cui vale $\det(A) \neq 0$ per [[determinante-invertibilita|questa proposizione]], è di usare la [[algoritmo-di-gauss|riduzione di Gauss]] su
$$A|I$$
dove $I$ è la matrice identità dello stesso ordine di $A$. Con Gauss infatti è _sempre_ possibile arrivare alla forma
$$I|B$$
e si ottiene che
$$B = A^{-1}$$

## Referenze
[^1]: letteralmente l'[[elemento-opposto|elemento opposto]] rispetto al prodotto per $A$