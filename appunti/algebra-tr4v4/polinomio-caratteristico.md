---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 18-04-2024 00:31:30
links:
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
---
# Polinomio caratteristico
---
## Introduzione
> Sia $A \in M_{n} (\mathbb{R})$ una [[matrice|matrice]] _quadrata_, allora il suo **polinomio caratteristico** è
> $$p_{A}(x) = \det(A - xI)$$
> ovvero il [[determinante|determinante]] della matrice ottenuta sottraendo da $A$ l'[[matrice-identita|identità]] moltiplicata per $x$.

## Importanza
Il polinomio caratteristico è uno **strumento fondamentale per la ricerca di [[autovalore|autovalori]] e [[autovettore|autovettori]] di un'[[applicazione-lineare|applicazione lineare]]**.

## Proposizioni
### Autovalori
> Sia $A \in M_{n}(\mathbb{R})$ una matrice quadrata, allora $\lambda \in \mathbb{R}$ è un autovalore di $A$ $\iff$ $\lambda$ è uno zero del polinomio caratteristico, ovvero
> $$\det(A - \lambda I) = 0$$

#### Dimostrazione
$\implies$: supponiamo che $\lambda$ sia autovalore di $A$, allora $A x = \lambda x$ per un qualche $x \in \mathbb{R}^{n}$ e $x \neq \underline{0}$, ovvero $A x - \lambda x = \underline{0}$, quindi $(A - \lambda I)x = \underline{0}$. Allora si ha $x \in \ker(A - \lambda I)$, ed essendo $x \neq \underline{0}$ significa che $\dim(\ker(A - \lambda I)) > 0$, perciò non è iniettiva, e quindi $\det(A - \lambda I) = 0$.

$\impliedby$: supponiamo $\det(A - \lambda I) = 0$, allora significa che $A - \lambda I$ non è iniettiva, per cui esiste un $x \in \ker(A - \lambda I)$ tale che $x \neq 0$. Quindi vale $(A - \lambda I)x = \underline{0}$, ovvero $Ax - \lambda x = \underline{0}$, cioè $Ax = \lambda x$: la definizione di autovalore per $\lambda$.

**Qed**.

## Referenze