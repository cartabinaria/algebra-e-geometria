---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-04-2024 23:02:32
links:
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
  - "[[lecture-23042024092139|Lecture 23042024092139]]"
---
# Matrice simile
---
## Introduzione
> Una [[matrice|matrice]] _quadrata_ $B$ si dice **simile** a una matrice quadrata $A$ se esiste una matrice $P \in M_{n}(\mathbb{R})$ [[matrice-invertibile|invertibile]] tale che
> $$A = P^{-1} \cdot B \cdot P$$
[^1]

## Proposizioni
### Polinomio caratteristico
> Due matrici simili $A, B$ hanno lo stesso [[polinomio-caratteristico|polinomio caratteristico]], ovvero
> $$p_{A}(x) = p_{B}(x)$$

In altri termini possiamo dire che il [[cambio-di-base|cambio base]] non influenza in alcun modo il polinomio caratteristico delle matrici, o meglio _il polinomio caratteristico non dipende dalla base purché sia la stessa per dominio e codominio_.

Se per intenderci ci viene data una matrice $A_{\beta\beta}$ dove $\beta$ è una base non-canonica, _per calcolare il polinomio caratteristico non c'è bisogno di applicare la [[cambio-di-base-formula-per-il-cambio-di-base|formula del cambio di base]] per passare ad $A_{cc}$_.

<u>Nota bene</u>: l'implicazione ha un verso solo! Non è quindi detto che se $p_{A}(x) = p_{B}(x)$ allora $A$ è simile a $B$.

Se per esempio considero $A = \begin{pmatrix} -4 & 0 \\ 0 & -4 \end{pmatrix}$ e $B = \begin{pmatrix} -4 & 1 \\ 0 & -4 \end{pmatrix}$, si ha $p_{A}(x) = (x+4)^{2}, p_{B}(x) = (x+4)^{2}$. Ciononostante $A$ è diagonalizzabile, perché diagonale, mentre per $B$ dobbiamo fare i conti. Viene $V_{-4} = \ker(B + 4I) = \ker\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$. Risolvendo si ha che $\dim(V_{-4}) = 2-1 = 1 \neq m_{a}(-4)$, per cui $B$ non è diagonalizzabile, per cui essendo "essere simili" una relazione di equivalenza $B$ non è simile ad $A$.

## Referenze
[^1]: "essere simili" è una [[relazione-di-equivalenza|relazione di equivalenza]]