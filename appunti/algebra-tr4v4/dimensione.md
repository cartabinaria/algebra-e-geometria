---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 07-03-2024 19:11:40
links:
  - "[[lecture-06032024091542|Lecture 06032024091542]]"
  - "[[lecture-21032024111439|Lecture 21032024111439]]"
---
# Dimensione
---
## Introduzione
> La **dimensione** di uno [[spazio-vettoriale|spazio vettoriale]] $V$ è il _numero di elementi delle [[base|basi]]_ di $V$, e si indica con
> $$\dim(V)$$
> Quando $V$ è [[sottospazio-generato-a64b18|finitamente generato]] allora si dice di _dimensione finita_.

### Grandi classici
- $\dim(\mathbb{R}^{n}) = n$
- $\dim(\mathbb{R}_{n}[x]) = n+1$
- $\dim(M_{m \times n}(\mathbb{R})) = m \cdot n$

### Esempio
Si prenda $W = \langle (1, 3, 4, 0), (2, 1, -5, 7) \rangle \leq \mathbb{R}^{4}$, ovvero un sottospazio di $\mathbb{R}^{4}$ generato da quei due vettori. Questi sono linearmente indipendenti (uno non è multiplo dell'altro), per cui sono base di $W$. Allora _$W$ avrà dimensione 2_.

<u>Attenzione</u>: $W$ è sottoinsieme di $\mathbb{R}^{4}$, non è $\mathbb{R}^{4}$.

## Proprietà
> Sia $V$ spazio vettoriale e $W \leq V$ ([[sottospazio-vettoriale|sottospazio]]), allora
> 1. $\dim(W) \leq \dim(V)$
> 2. $\dim(W) = \dim(V) \iff W = V$

### Dimostrazione
#### $\dim(W) \leq \dim(V)$
Sia $\beta_{w} = \{w_{1}, \cdots, w_{n}\}$ base di $W$, sapendo $W \leq V$ sappiamo per definizione di sottospazio che $w_{1}, \cdots, w_{n} \in V$ e sono linearmente indipendenti. Presa $\beta_{v} = \{v_{1}, \cdots, v_{r}\}$ base di $V$, per il [[teorema-del-completamento|teorema del completamento]] ho che $n \leq r$, ovvero $\dim(W) \leq \dim(V)$.

**Qed**.

#### $\dim(W) = \dim(V) \iff W = V$
Primo verso dell'implicazione: per ipotesi abbiamo, prese le basi $\beta_{w} = \{w_{1}, \cdots, w_{n}\}$ di $W$ e $\beta_{v} = \{v_{1}, \cdots, v_{r}\}$ di $V$, che $n = r$. Per cui sempre per il teorema del completamento possiamo aggiungere a $\{w_{1}, \cdots, w_{n}\}$ $r-n = 0$ vettori per ottenere una base di $V$, perciò anche $V = \langle \beta_{w} \rangle$. Si ottiene allora
$$W = \langle \beta_{w} \rangle = V$$

Secondo verso dell'implicazione: per ipotesi sappiamo $W = V$, per cui per il [[base-elementi-delle-basi|teorema degli elementi di una base]] abbiamo che due basi $\beta_{W}$ e $\beta_{V}$ hanno lo stesso numero di elementi, e perciò
$$\dim(W) = \dim(V)$$

**Qed**.

## Referenze