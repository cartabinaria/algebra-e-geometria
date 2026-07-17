---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 23-04-2024 00:51:37
links:
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
---
# Molteplicità algebrica
---
## Introduzione
> Sia $A \in M_{n}(\mathbb{R})$ e sia $\lambda \in \mathbb{R}$ un [[autovalore|autovalore]] dell'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare associata]], allora la **molteplicità algebrica** di $\lambda$, indicata con $m_{a}(\lambda)$ è la massima potenza di $(x - \lambda)$ che divide il [[polinomio-caratteristico|polinomio caratteristico]] $p_{A}(x)$.

Se per esempio supponiamo di aver trovato il seguente polinomio caratteristico $p_{A}(x) = (x-3)^{5}(x+2)^{3}(x-1)(x^{2}+7)$ di una matrice $A$ di grado 10, allora gli autovalori sono:
- $\lambda_{1} = 3$
- $\lambda_{2} = -2$
- $\lambda_{3} = 1$

Allora le rispettive molteplicità algebriche saranno:
- $\lambda_{1}$ --> $m_{a}(3) = 5$
- $\lambda_{2}$ --> $m_{a}(-2) = 3$
- $\lambda_{3}$ --> $m_{a}(1) = 1$

cioè il _grado dei rispettivi monomi_.

<u>Nota bene</u>: non ci sono autovalori per $(x^{2} + 7)$ perché _non ha soluzione reale_.

## Referenze