---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 08-03-2024 16:41:46
links:
  - "[[lecture-06032024091542|Lecture 06032024091542]]"
---
# Teorema GEL
---
## Introduzione
> Il **teorema GEL** (= _Generare Equivale Lineare Indipendenza_) ci dice che se $V$ è uno [[spazio-vettoriale|spazio vettoriale]] di [[dimensione|dimensione]] $n$ ($\dim(n)$), allora sono equivalenti
> 1. $\{v_{1}, \cdots, v_{n}\}$ è [[base|base]] di $V$
> 2. $\{v_{1}, \cdots, v_{n}\}$ sono [[indipendenza-lineare|linearmente indipendenti]]
> 3. $\{v_{1}, \cdots, v_{n}\}$ [[sottospazio-generato|generano]] $V$

Questa _relazione tra dimensione, base, indipendenza lineare e generazione_ è _frutto del [[teorema-del-completamento|teorema del completamento]]_.

## Dimostrazione
Sappiamo già, per definizione di base, che $1 \implies 2$ e che $1 \implies 3$. Allora verifichiamo gli altri casi.

### $2 \implies 1$
Ho $\{v_{1}, \cdots, v_{n}\}$ vettori linearmente indipendenti di $V$ e so che la dimensione di $V$ è $n$, allora per il teorema del completamento posso aggiungere $\dim(V) - n = 0$ vettori a $\{v_{1}, \cdots, v_{n}\}$ per completarlo a base di $V$.

**Qed**.

### $3 \implies 1$
Ho $\{v_{1}, \cdots, v_{n}\}$ vettori che generano $V$ e so che la dimensione di $V$ è $n$, per cui per l'[[base-esistenza-della-base|esistenza della base]] posso cancellare vettori dipendenti di $\{v_{1}, \cdots, v_{n}\}$ per ottenere una base grande $n$, perciò non devo cancellare nulla.

**Qed**.

## Utilità
Il teorema ci assicura che se di uno spazio vettoriale conosciamo la sua dimensione $n$, automaticamente so che:
- se un insieme di vettori $\{v_{1}, \cdots, v_{n}\}$ è linearmente indipendente allora è anche base e quindi genera;
- se un insieme di vettori $\{v_{1}, \cdots, v_{n}\}$ genera allora è anche base e quindi linearmente indipendente;
- se un insieme di vettori $\{v_{1}, \cdots, v_{n}\}$ è base allora (ma qui per definizione) è anche linearmente indipendente e genera;

Per cui se ci viene dato un insieme $\{2x, 5, x^{2}\}$ di vettori di $\mathbb{R}_{2}[x]$ (cui dimensione è 3), per controllare se sono base ci basta verificare o che generino $\mathbb{R}_{2}[x]$ (lungo) o che siano linearmente indipendenti (più corto).

### Esempio
Se dobbiamo stabilire se $\{(1, 3, 4), (2, 7, 9), (0, 1, -5), (4, 3, 2)\}$ sono linearmente indipendenti, possiamo usare il [[indipendenza-lineare-esempio|metodo standard]], o semplicemente osservare che trattandosi di vettori di $\mathbb{R}^{3}$ che ha dimensione 3, è possibile selezionare al massimo 3 vettori linearmente indipendenti, per cui no: sono dipendenti.

## Referenze