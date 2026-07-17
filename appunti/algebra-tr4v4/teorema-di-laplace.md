---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 07-04-2024 19:21:21
links:
  - "[[lecture-04042024112239|Lecture 04042024112239]]"
---
# Teorema di Laplace
---
## Introduzione
> Sia $A$ una [[matrice|matrice]] quadrata $\in M_{n} (\mathbb{R})$, allora
> 1. se $A$ ha ordine $n = 1$, cioè $A = (a_{11})$, si pone $$\det(A) = a_{11}$$
> 2. se $A$ ha ordine $n > 1$, supponiamo di saper calcolare il determinante delle matrici di ordine $n-1$, e definiamo $$\Gamma_{ij} = (-1)^{i+j} \det(A_{ij})$$ come un valore determinato dal determinante di $A_{ij}$, ovvero dalla [[matrice-minore|matrice minore]] $i, j$, allora si ha che $$\det(A) = a_{11}\Gamma_{11} + \cdots + a_{1n}\Gamma_{1n} = \sum\limits_{k=1}^{n}a_{1k}\Gamma_{1k}$$
> 
> <u>Nota bene</u>: _posso scegliere di lavorare con Laplace su qualunque riga o colonna, e funzionerà sempre_!
> <u>Nota bene</u>: si tratta di una definizione di [[determinante|determinante]] definita per [[ricorsione-strutturale|ricorsione strutturale]].

### $2 \times 2$
Verifichiamo lo sviluppo di Laplace sul caso di $A \in M_{2}(\mathbb{R})$, perciò
$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$
allora calcoliamo intanto $\Gamma_{11} = (-1)^{1+1}\det(d) = d$, e $\Gamma_{12} = (-1)^{1+2}\det(c) = -c$, e otteniamo che
$$\det(A) = a\Gamma_{11} + b\Gamma_{12} = ad - bc$$

## Referenze