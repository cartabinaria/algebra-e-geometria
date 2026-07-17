---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 30-03-2024 12:43:49
links:
  - "[[lecture-26032024091342|Lecture 26032024091342]]"
---
# Composizione di applicazioni lineari
---
## Introduzione
> Una **composizione di [[applicazione-lineare|applicazioni lineari]]** $f, g$ t.c. $f: V \to W$ e $g: W \to Z$, è definita dalla [[funzione-composta|funzione composta]]
> $$g \circ f: V \to Z \ \ | \ \ (g \circ f)(v) = g(f(v))$$

## Proposizioni
### Linearità
> Siano $f, g$ applicazioni lineari t.c. $f: V \to W$ e $g: W \to Z$ e $g \circ f: V \to Z$ la loro composizione, allora _anch'essa è lineare_.

#### Dimostrazione
Per dimostrare che $g \circ f$ è lineare, usiamo la definizione di applicazione lineare, per cui deve valere:
1. $(g \circ f)(v + u) = (g \circ f)(v) + (g \circ f)(u) \ \ \ \forall v, u \in V$;
2. $(g \circ f)(\lambda v) = \lambda (g \circ f)(v) \ \ \ \forall v \in V, \forall \lambda \in \mathbb{R}$.

##### 1.
Ho che
$$(g \circ f)(v + u) = g(f(v+u)) \stackrel{\text{lin}}{=} g(f(v) + f(u)) \stackrel{\text{lin}}{=} g(f(v)) + g(f(u)) = (g \circ f)(v) + (g \circ f)(u)$$

**Qed**.

##### 2.
Ho che
$$(g \circ f)(\lambda v) = g(f(\lambda v)) \stackrel{\text{lin}}{=} g(\lambda f(v)) \stackrel{\text{lin}}{=} \lambda g(f(v)) = \lambda (g \circ f)(v)$$

**Qed**.

### Matrice associata
> Siano $f: \mathbb{R}^{n} \to \mathbb{R}^{s}$ e $g: \mathbb{R}^{s} \to \mathbb{R}^{m}$ lineari, e $A, B$ le [[applicazione-lineare-definita-da-una-matrice|matrici associate]] rispettivamente a $f, g$, ovvero $f = L_{A}$ e $g = L_{B}$, allora la matrice associata alla composizione $g \circ f$ è $BA$[^1], ovvero
> $$g \circ f = L_{BA}$$

<u>Nota bene</u>: si ha che $A \in M_{s \times n}$, $B \in M_{m \times s}$, per cui $BA \in M_{m \times n}$.

#### Dimostrazione
Se $f(\underline{x}) = A\underline{x}$ e $g(\underline{x}) = B\underline{x}$, allora
$$(g \circ f)(\underline{x}) = g(f(\underline{x})) = g(A\underline{x}) = B(A\underline{x}) = (BA)\underline{x}$$

**Qed**.

## Referenze
[^1]: [[matrice-prodotto|prodotto tra matrici]]