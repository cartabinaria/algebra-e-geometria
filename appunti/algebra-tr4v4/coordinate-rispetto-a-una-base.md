---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 08-03-2024 17:05:13
links:
  - "[[lecture-06032024091542|Lecture 06032024091542]]"
---
# Coordinate rispetto a una base
---
## Introduzione
> Sia $\beta = \{v_{1}, \cdots, v_{n}\}$ [[base|base]] _ordinata_ di $V$ [[spazio-vettoriale|spazio vettoriale]], e sia $v \in V$, allora esistono unici $\lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}$ tali che
> $$v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$$
> Questi scalari si dicono **coordinate** (o **componenti**) di $v$ rispetto alla base $\beta$, e si indicano così:
> $$(v)_{\beta} = (\lambda_{1}, \cdots, \lambda_{n})$$

<u>Nota bene</u>: il teorema _ci assicura che presa una base ordinata esistono sempre coordinate di un vettore appartenente allo spazio vettoriale_. Per cui se la soluzione di un sistema per trovare i valori di $\lambda$ che determinino la combinazione lineare di un certo vettore ci viene impossibile o con infinite soluzioni, siamo sicuri di star sbagliando!

### Esempio
Presa la base canonica $e = \{(1, 0), (0, 1)\}$ di $\mathbb{R}^{2}$ e un vettore $v = (3, 5) \in \mathbb{R}^{2}$, si ha che $(3, 5) = 3(1, 0) + 5(0, 1)$, per cui $(v)_{\beta} = (3, 5)$.

## Dimostrazione
Sapendo che $v_{1}, \cdots, v_{n}$ è base di $V$, preso un generico $v \in V$, per la definizione di base, si ha che $\exists \lambda_{1}, \cdots, \lambda_{n} : v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$. Per dimostrare l'unicità supponiamo allora che $v = \beta_{1}v_{1} + \cdots + \beta_{n}v_{n}$, da cui $v-v = \underline{0}$ e quindi $\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} - (\beta_{1}v_{1} + \cdots + \beta_{n}v_{n}) = (\lambda_{1} - \beta_{1})v_{1} + \cdots + (\lambda_{n} - \beta_{n})v_{n} = \underline{0}$. Avendo $v_{1}, \cdots, v_{n}$ linearmente indipendenti è necessario che $\lambda_{1} - \beta_{1} = 0, \cdots, \lambda_{n} - \beta_{n} = 0$, da cui consegue l'unicità degli scalari.

**Qed**.

## Referenze