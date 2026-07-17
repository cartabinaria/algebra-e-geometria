---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-04-2024 22:21:27
links:
  - "[[lecture-16042024091615|Lecture 16042024091615]]"
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
  - "[[lecture-23042024092139|Lecture 23042024092139]]"
---
# Autovalore
---
## Introduzione
> Un **autovalore** è uno [[scalare|scalare]] $\lambda$ associato a un [[autovettore|autovettore]], ovvero tale che per un'[[applicazione-lineare|applicazione lineare]] $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ e un [[vettore|vettore]] $v \in \mathbb{R}^{n}$ con $v \neq \underline{0}$, avviene che $f(v) = \lambda v$.

## Proposizioni
### Legame con molteplicità
Un'importantissima proposizione sugli autovalori riguarda il suo legame con la [[molteplicita-algebrica|molteplicità algebrica]] e la [[molteplicita-geometrica|molteplicità geometrica]], ed è un criterio fondamentale per analizzare la [[diagonalizzabilita|diagonalizzabilità]] di una matrice $A$.

> Se $\lambda$ è autovalore di $A$, allora
> $$1 \leq m_{g}(\lambda) \leq m_{a}(\lambda)$$
> ovvero la molteplicità geometrica di $\lambda$ è compresa tra 1 e la molteplicità algebrica di $\lambda$.

<u>Nota bene</u>: la molteplicità geometrica di un qualunque $\lambda$ non può essere inferiore a 1, perché vorrebbe dire che $\dim(V_{\lambda}) = 0$, il che _è impossibile dato che avendo trovato un autovalore $\lambda$ almeno un autovettore dev'essere presente_.

### Autovalore $0$
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ con autovalore $\lambda = 0$, allora per definizione si ha che $\exists v \in \mathbb{R}^{n}$ t.c. $v \neq \underline{0}$ e
> $$f(v) = 0v = \underline{0}$$
> Allora ho che $v \in \ker(f)$, ed essendo $v \neq \underline{0}$ devo per forza avere $\dim(\ker(f)) > 0$, da cui ho che $f$ non è iniettiva. Per il [[determinante-teoremone|teoremone]] scopro allora che $f$ non è neanche invertibile.

<u>Nota bene</u>: questo non significa che c'è una relazione di implicazione tra diagonalizzabilità e invertibilità, e anzi si ha che $\text{diagonalizzabile} \not \implies \text{invertibile}$ e che $\text{invertibile} \not \implies \text{diagonalizzabile}$.

## Referenze