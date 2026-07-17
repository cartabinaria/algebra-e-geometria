---
tags:
  - category/note
  - status/ongoing
  - topic/algebra-e-geometria
date: 07-03-2024 18:10:29
links:
  - "[[lecture-05032024091733|Lecture 05032024091733]]"
---
# Teorema del completamento
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]] [[sottospazio-generato-a64b18|fg]], e sia $\beta = \{v_{1}, \cdots, v_{n}\}$ [[base|base]] di $V$ e $w_{1}, \cdots, w_{m} \in V$ [[indipendenza-lineare|linearmente indipendenti]], allora:
> 1. $m \leq n$
> 2. possiamo aggiungere a $w_{1}, \cdots, w_{m}$ fino a $n-m$ vettori di $\beta$ in modo da ottenere una base

In poche parole ci dice fondamentalmente che _se abbiamo un po' di vettori linearmente indipendenti appartenenti a uno spazio $V$, allora possiamo aggiungerne un po' per ottenere una base_.

<u>Nota bene</u>: questo è una sorta di teorema simmetrico a quello dell'[[base-esistenza-della-base|esistenza della base]]. **Se con quel teorema si ha un algoritmo con il quale, cancellando vettori dipendenti, si ottiene una base**, in questo caso **ci viene dato un criterio per aggiungerne al fine di creare una base**.

## Dimostrazione
### $m \leq n$
Supponiamo [[regole-di-inferenza-del-raa|per assurdo]] che $m > n$, ed essendo $w_{1}, \cdots, w_{m} \in V$ mi definisco $W = \langle w_{1}, \cdots, w_{m} \rangle \leq V$. Per cui ho $\langle w_{1}, \cdots, w_{m} \rangle \leq \langle v_{1}, \cdots, v_{n} \rangle$. Di conseguenza posso dire $V = \langle w_{1}, \cdots, w_{m}, v_{1}, \cdots, v_{n} \rangle$, perché so che $w_{1}, \cdots, w_{m} \in V$. Per l'[[base-esistenza-della-base|esistenza della base]], sapendo che $w_{1}$ è combinazione lineare di $v_{1}, \cdots, v_{n}$, se elimino $v_{1}$ lo spazio generato non cambia; lo stesso vale per $w_{2}$, per cui elimino $v_{2}$; reiterando finisco, essendo $m > n$, per terminare i vettori $v$, per cui rimango con $V = \langle w_{1}, \cdots, w_{m} \rangle$, ed essendo per ipotesi $w_{1}, \cdots, w_{m}$ linearmente indipendenti allora sono anche base di $V$. Quindi mi ritrovo con
$$V = \langle v_{1}, \cdots, v_{n} \rangle = \langle w_{1}, \cdots, w_{m} \rangle$$
dove $m > n$, $v_{1}, \cdots, v_{n}$ e $w_{1}, \cdots, w_{m}$ linearmente indipendenti. Allora prendo $w_{1}$ e so che lo posso scrivere come combinazione lineare di $v_{1}, \cdots, v_{n}$ andandolo a sostituire a $v_{1}$, per cui ho $V = \langle w_{1}, v_{2}, \cdots, v_{n} \rangle$; la stessa cosa per $w_{2}$, per cui ho $V = \langle w_{1}, w_{2}, v_{3}, \cdots, v_{n} \rangle$. Reiterando l'algoritmo ottengo che $V = \langle w_{1}, \cdots, w_{n} \rangle = \langle w_{1}, \cdots, w_{m} \rangle$, che è un assurdo. Infatti preso $w_{n+1}$ da $w_{1}, \cdots, w_{m}$ (dato che $m > n$), questo è generato da $w_{1}, \cdots, w_{n}$, per cui è linearmente dipendente da $w_{1}, \cdots, w_{n}$, il che è in contraddizione con l'ipotesi di indipendenza lineare di $w_{1}, \cdots, w_{m}$[^1].

**Qed**.

## Conseguenze
Sappiamo che i [[sottospazi-vettoriali-di-r2|sottospazi di R2]] sono 3: sottospazio banale, una retta passante per l'origine, o tutto $\mathbb{R}^{2}$. Abbiamo dimostrato, in particolare, che sono sufficienti due vettori indipendenti per generare l'intero piano, ovvero proprio $\mathbb{R}^{2}$. Questo significa che già un terzo vettore sarebbe combinazione lineare dei due. Il teorema del completamento ci conferma questa tesi: sapendo che $\mathbb{R}^{2} = \langle v_{1}, v_{2} \rangle$ dove $v_{1}$ e $v_{2}$ sono due vettori linearmente indipendenti, allora $\beta = \{v_{1}, v_{2}\}$ è base di $\mathbb{R}^{2}$. Il _teorema ci dice che allora non possiamo prendere più di 2 vettori linearmente indipendenti in $\mathbb{R}^{2}$_.

Generalizzando si ottiene che:
> _In $\mathbb{R}^{n}$ ci sono al massimo $n$ vettori linearmente indipendenti_.

### Esempio
Se consideriamo per esempio un vettore $S = \{3, 1+x, x^{2}, 5x, 4x, -2x^{3}, x^{2}+10x-1\}$ tale che $\mathbb{R}_{3}[x] = \langle S \rangle$, sin da subito possiamo dire che sono linearmente dipendenti: essendo in $\mathbb{R}_{3}[x]$ avremmo un massimo di 4 vettori generatori che possono essere linearmente indipendenti, proprio per il teorema del completamento. Questo perché la base canonica è $\beta = \{x^{3}, x^{2}, x, 1\}$.

## Referenze
[^1]: questo si chiama [[teorema-della-dimensione-di-uno-spazio-vettoriale|teorema della dimensione di uno spazio vettoriale]]