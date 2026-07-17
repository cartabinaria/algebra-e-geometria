---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 18-04-2024 00:50:17
links:
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
---
# Autospazio
---
## Introduzione
> Sia $\lambda \in \mathbb{R}$ un [[autovalore|autovalore]] di $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ [[applicazione-lineare|applicazione lineare]], allora
> $$V_{\lambda} = \{v \in \mathbb{R}^{n} | f(v) = \lambda v\}$$
> si dice **autospazio** relativo all'autovalore $\lambda$.
> Fondamentalmente non è altro che _l'insieme degli [[autovettore|autovettori]] che condividono lo stesso autovalore_.

## Proposizioni
### $V_{\lambda} \leq \mathbb{R}^{n}$
Si ha che $V_{\lambda}$ è [[sottospazio-vettoriale|sottospazio]] di $\mathbb{R}^{n}$ perché è un [[nucleo|nucleo]]! Infatti
$$\begin{align} V_{\lambda} =& \{v \in \mathbb{R}^{n} | f(v) = \lambda v\} \\ =& \{v \in \mathbb{R}^{n} | Av - \lambda v = \underline{0}\} \\ =& \{v \in \mathbb{R}^{n} | (A - \lambda I)v = \underline{0}\} \\ =& \{v \in \mathbb{R}^{n} | v \in \ker(A - \lambda I)\} \\ =& \ker(A - \lambda I) \end{align}$$

## Referenze