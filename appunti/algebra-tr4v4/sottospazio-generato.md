---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 02-03-2024 16:17:19
links:
  - "[[lecture-28022024091940|Lecture 28022024091940]]"
  - "[[lecture-29022024111734|Lecture 29022024111734]]"
  - "[[lecture-05032024091733|Lecture 05032024091733]]"
  - "[[lecture-26032024091342|Lecture 26032024091342]]"
  - "[[lecture-27032024091734|Lecture 27032024091734]]"
---
# Sottospazio generato
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]] t.c. $v_{1}, \cdots, v_{n} \in V$, allora si dice che il **sottospazio generato** da $v_{1}, \cdots, v_{n}$ è l'insieme di tutte le sue [[combinazione-lineare|combinazioni lineari]], e si indica con
> $$\langle v_{1}, \cdots, v_{n} \rangle = \{\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} | \lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}\}$$

Se si hanno i vettori $v_{1}, \cdots, v_{n} \in V$ dove $V$ è un qualunque spazio vettoriale (anche un sottospazio), **il più piccolo sottospazio che li contiene è proprio il sottospazio generato da $v_{1}, \cdots, v_{n}$, ovvero $\langle v_{1}, \cdots, v_{n} \rangle$**.

### Definizioni
> Sia $V$ uno spazio vettoriale t.c. $v_{1}, \cdots, v_{n} \in V$, allora si dice che $\{v_{1}, \cdots, v_{n}\}$ genera $V$ (o $v_{1}, \cdots, v_{n}$ generano $V$) $\iff$ $V = \langle v_{1}, \cdots, v_{n} \rangle$.

> Uno spazio vettoriale $V$ si dice _finitamente generato_ (_fg_) se ha un insieme finito di generatori, ovvero se $\exists v_{1}, \cdots, v_{n} \in V : V = \langle v_{1}, \cdots, v_{n} \rangle$.

^a64b18

Per esempio $\mathbb{R}^{2}$ è finitamente generato; mentre $\mathbb{R}[x]$ ([[sottospazi-vettoriali-dei-polinomi|sottospazio vettoriale dei polinomi]]) non è fg perché per rappresentare ogni polinomio mi servirebbero infiniti elementi nel generatore, difatti $\mathbb{R}[x] = \langle 1, x, x^{2}, x^{3}, \cdots, x^{n}, x^{n+1}, \cdots \rangle$.

### Osservazioni
Se $V$ è un sottospazio t.c. $v \in V$, allora $\langle v \rangle = \{\lambda v : \lambda \in \mathbb{R}\}$, ovvero _il sottospazio generato da $v$ è l'insieme dei suoi multipli_[^1].

Di conseguenza, _il sottospazio generato dal vettore nullo è il sottospazio banale_, ovvero $\langle \underline{0} \rangle = \{\underline{0}\}$.

<u>Nota bene</u>: $v_{1} \in \langle v_{1}, \cdots, v_{n} \rangle$, perché la combinazione lineare $1v_{1} + 0v_{2} + \cdots + 0v_{n} = v_{1}$. Lo stesso vale $\forall v \in \{v_{1}, \cdots, v_{n}\}$.

## Proposizioni
Preso $V$ come spazio vettoriale t.c. $v_{1}, \cdots, v_{n} \in V$, allora
1. $\langle v_{1}, \cdots, v_{n} \rangle \leq V$
2. $Z \leq V : v_{1}, \cdots, v_{n} \in Z \implies \langle v_{1}, \cdots, v_{n} \rangle \subseteq Z$, ovvero **$\langle v_{1}, \cdots, v_{n} \rangle$ è il più piccolo sottospazio di $V$ che contiene $v_{1}, \cdots, v_{n}$**
3. $w \in \langle v_{1}, \cdots, v_{n} \rangle \iff \langle v_{1}, \cdots, v_{n} \rangle = \langle v_{1}, \cdots, v_{n}, w \rangle$

### $\langle v_{1}, \cdots, v_{n} \rangle \leq V$
Dobbiamo dimostrare che $\langle v_{1}, \cdots, v_{n} \rangle$ è un sottospazio di un generico spazio vettoriale $V$.

Per la definizione di sottospazio bisogna avere $(0, \cdots, 0) \in \langle v_{1}, \cdots, v_{n} \rangle$, vero perché presa la combinazione lineare $\lambda_{1}v_{1}, \cdots, \lambda_{n}v_{n}$ con $\lambda_{1}, \cdots, \lambda_{n} = 0$ si ottiene proprio $(0, \cdots, 0)$.

Quindi $\langle v_{1}, \cdots, v_{n} \rangle$ dev'essere chiuso rispetto alla somma, ovvero presi $u, v \in \langle v_{1}, \cdots, v_{n} \rangle$, anche $u + v \in \langle v_{1}, \cdots, v_{n} \rangle$. Per la definizione di sottospazio generato, $u$ e $v$ sono entrambe combinazioni lineari di $\{v_{1}, \cdots, v_{n}\}$, e quindi del tipo $u = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$ e $v = \beta_{1}v_{1} + \cdots + \beta_{n}v_{n}$. La loro somma allora sarebbe $u + v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} + \beta_{1}v_{1} + \cdots + \beta_{n}v_{n} = (\lambda_{1} + \beta_{1})v_{1} + \cdots + (\lambda_{n} + \beta_{n})v_{n} \in \langle v_{1}, \cdots, v_{n} \rangle$ per la definizione di sottospazio generato.

Ci manca la chiusura rispetto al prodotto, per cui preso $u \in \langle v_{1}, \cdots, v_{n} \rangle$ e $\beta \in \mathbb{R}$, devo mostrare $\beta u \in \langle v_{1}, \cdots, v_{n} \rangle$. Per la definizione di sottospazio generato, $u$ è una combinazione lineare di $\{v_{1}, \cdots, v_{n}\}$, quindi del tipo $u = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$. Allora il prodotto per scalare $\beta u = \beta\lambda_{1}v_{1} + \cdots + \beta\lambda_{n}v_{n} \in \langle v_{1}, \cdots, v_{n} \rangle$ per definizione di sottospazio generato.

**Qed**.

### $Z \leq V : v_{1}, \cdots, v_{n} \in Z \implies \langle v_{1}, \cdots, v_{n} \rangle \subseteq Z$
Prima di dimostrarlo mostriamo il significato di questa proposizione attraverso un diagramma a insiemi (anche se impreciso):
![[Drawing 2024-03-02 17.45.06.excalidraw|750]]

Ovvero, preso un sottospazio vettoriale $Z$ di $V$ composto da $v_{1}, \cdots, v_{n}$ vettori, si ha che il sottospazio generato $\langle v_{1}, \cdots, v_{n} \rangle$ è [[sottoinsieme-chiuso|sottoinsieme]] di $Z$, e quindi _non sfora in $V$_. Per questo motivo si dice che $\langle v_{1}, \cdots, v_{n} \rangle$ è il più piccolo sottospazio generato dall'insieme di vettori $\{v_{1}, \cdots, v_{n}\}$.

Per dimostrarlo ci basta _prendere l'[[combinazione-lineare-osservazione|osservazione sulle combinazioni lineari]]_, che ci dice che se $U \leq V$ t.c. $u_{1}, \cdots, u_{n} \in U$ e $\lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}$, allora $\lambda_{1}u_{1} + \cdots + \lambda_{n}u_{n} \in U$, e _considerarla valida per ogni combinazione lineare del sottospazio generato $\langle u_{1}, \cdots, u_{n} \rangle$_.

Formalmente, se vogliamo dimostrare $\langle v_{1}, \cdots, v_{n} \rangle \subseteq Z$, per la [[definizione-di-essere-sottoinsieme|definizione di essere sottoinsieme]], ci basta sapere che ogni elemento in $\langle v_{1}, \cdots, v_{n} \rangle$ è presente anche in $Z$. Quindi, fissato un elemento $u \in \langle v_{1}, \cdots, v_{n} \rangle$, ovvero esprimibile come $u = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$, ed essendo $v_{1}, \cdots, v_{n} \in Z$ per ipotesi, allora anche la suddetta combinazione lineare $u$ apparterrà a $Z$, per le proprietà stesse delle combinazioni lineari.

**Qed**.

### $w \in \langle v_{1}, \cdots, v_{n} \rangle \iff \langle v_{1}, \cdots, v_{n} \rangle = \langle v_{1}, \cdots, v_{n}, w \rangle$
Partiamo con il primo verso dell'implicazione. Dalle ipotesi sappiamo che $w \in \langle v_{1}, \cdots, v_{n} \rangle$, per cui per dimostrare $\langle v_{1}, \cdots, v_{n} \rangle = \langle v_{1}, \cdots, v_{n}, w \rangle$ ci basta verificare che $w \in \langle v_{1}, \cdots, v_{n}, w \rangle$, ovvio.

Con il secondo verso dell'implicazione, per ipotesi sappiamo che $\langle v_{1}, \cdots, v_{n} \rangle = \langle v_{1}, \cdots, v_{n}, w \rangle$, per cui per dimostrare $w \in \langle v_{1}, \cdots, v_{n} \rangle$ possiamo sfruttare l'uguaglianza e passare a dimostrare $w \in \langle v_{1}, \cdots, v_{n}, w \rangle$, ovvio.

**Qed**.

#### Osservazioni
Questo significa che, verificato che $\{(1, 0), (0, 1), (1, 2)\}$ generano $\mathbb{R}^{2}$, se so che $(1, 2)$ è una combinazione lineare di $\{(1, 0), (0, 1)\}$, allora posso cancellare $(1, 2)$ dallo spazio che genera $\mathbb{R}^{2}$, ottenendo una forma più compatta di sottospazio generato: $\mathbb{R}^{2} = \langle (1, 0), (0, 1) \rangle$.
Fondamentalmente _per trovare l'insieme di vettori generatori più piccolo possibile per un determinato sottospazio è necessario ricorrere al concetto di [[indipendenza-lineare|indipendenza lineare]]_.

Di fatto **un insieme generatore linearmente indipendente è il modo più efficiente di descrivere tale sottospazio**, ovvero è _formato dal numero minimo di vettori necessario per caratterizzare il sottospazio_.

## Esempi
### $\mathbb{R}^{3} = \langle (1, 0, 0), (0, 1, 0), (0, 0, 1) \rangle$?
Per dimostrare ciò espandiamo il sottospazio generato con la sua definizione:
$$\langle (1, 0, 0), (0, 1, 0), (0, 0, 1) \rangle = \{\lambda_{1}(1, 0, 0) + \lambda_{2}(0, 1, 0) + \lambda_{3}(0, 0, 1) | \lambda_{1}, \lambda_{2}, \lambda_{3} \in \mathbb{R}\}$$

Ora, per dimostrare che $\mathbb{R}^{3}$ è uguale a ciò, fissiamo un vettore qualsiasi $(a, b, c) \in \mathbb{R}^{3}$ e dimostriamo che esso è una combinazione lineare appartenente a $\langle (1, 0, 0), (0, 1, 0), (0, 0, 1) \rangle$. Quindi:
$$(a, b, c) = \lambda_{1}(1, 0, 0) + \lambda_{2}(0, 1, 0) + \lambda_{3}(0, 0, 1)$$
ovvero
$$(a, b, c) = (\lambda_{1}, \lambda_{2}, \lambda_{3})$$

La domanda da porsi è: _possiamo trovare $\lambda_{1}, \lambda_{2}, \lambda_{3}$ t.c. si eguagli l'espressione_? La risposta è sì, infatti per $\lambda_{1} = a, \lambda_{2} = b, \lambda_{3} = c$ ho
$$(a, b, c) = (a, b, c)$$

### $\mathbb{R}^{2} = \langle (2, 1), (-1, -1) \rangle$?
Anche in questo caso espandiamo il sottospazio generato:
$$\langle (2, 1), (-1, -1) \rangle = \{\lambda_{1}(2, 1) + \lambda_{2}(-1, -1) | \lambda_{1}, \lambda_{2} \in \mathbb{R}\}$$

Procedo fissando allora un vettore qualsiasi $(a, b) \in \mathbb{R}^{2}$, e dimostro che è una combinazione lineare di $\langle (2, 1), (-1, -1) \rangle$. Quindi:
$$(a, b) = \lambda_{1}(2, 1) + \lambda_{2}(-1, -1)$$
ovvero
$$(a, b) = (2\lambda_{1} - \lambda_{2}, \lambda_{1} - \lambda_{2})$$

In questo caso ci è più difficile trovare valori di $\lambda_{1}, \lambda_{2}$ in funzione di $a, b$ t.c. l'espressione si eguagli. Ma ci vengono in aiuto i [[sistema-lineare|sistemi lineari]]! Di fatto, quello che stiamo cercando di risolvere è un sistema della forma:
$$\begin{cases} 2\lambda_{1} - \lambda_{2} = a \\ \lambda_{1} - \lambda_{2} = b \end{cases}$$

Di questo sistema non sarà possibile trovare un valore preciso di $\lambda_{1}$ e $\lambda_{2}$, perché _i termini noti sono generici_: ma a noi non importa. Quello che ci interessa è di capire se il sistema ha soluzione, ovvero se è esiste almeno una coppia $\lambda_{1}, \lambda_{2}$ che soddisfi le equazioni. Quindi, come sempre, scriviamo la _[[matrice|matrice]] associata al sistema_
$$\begin{pmatrix} 2 & -1 & a \\ 1 & -1 & b \end{pmatrix}$$
e attraverso l'[[algoritmo-di-gauss|algoritmo di Gauss]] la riduciamo [[matrice-a-scala|a scala]]:
$$\begin{pmatrix} 1 & -1 & b \\ 0 & 1 & a-2b \end{pmatrix}$$

A prescindere dai valori di $a$ e $b$ (che sono appunto generici), il [[rango-righe|rango righe]] di della matrice incompleta è uguale al rango righe della matrice completa, ovvero
$$rr(A) = 2 = rr(A|\underline{b})$$
per cui _il sistema ha soluzione_. Il numero di incognite, per altro, è sempre 2 ($\lambda_{1}, \lambda_{2}$), perciò _il sistema ha una sola soluzione_, ma a noi questo non importa: **ciò che conta è di aver trovato che il sistema ha soluzione**.

Arrivati a questo punto siamo in grado di dire che un qualunque $(a, b) \in \mathbb{R}^{2}$ può essere generato a partire dai vettori $(2, 1)$ e $(-1, -1)$, ovvero $(a, b) \in \langle (2, 1), (-1, -1) \rangle \ \ \forall (a, b)$, e che quindi
$$\mathbb{R}^{2} = \langle (2, 1), (-1, -1) \rangle$$

### $U = \langle (1, 1), (2, k) \rangle$
Dobbiamo determinare qual è il sottospazio generato da $U = \langle (1, 1), (2, k) \rangle$ al variare di $k \in \mathbb{R}$. Lo spazio vettoriale di riferimento sarà allora $\mathbb{R}^{2}$ (per vettori come coppie di numeri). Allora faccio un'assunzione, ovvero, affinché una qualsiasi coppia $(a, b)$ di $\mathbb{R}^{2}$ appartenga a $U$, devo avere una combinazione lineare di $U$ t.c. possa ottenere $(a, b)$, o in formule:
$$(a, b) \in U \iff \exists \lambda_{1}, \lambda_{2} \in \mathbb{R} : (a, b) = \lambda_{1}(1, 1) + \lambda_{2}(2, k) = (\lambda_{1} + 2\lambda_{2}, \lambda_{1} + k\lambda_{2})$$

Di nuovo ci troviamo a dover risolvere un _sistema_, ma questa volta _parametrico_, del tipo
$$\begin{cases} \lambda_{1} + 2\lambda_{2} = a \\ \lambda_{1} + k\lambda_{2} = b \end{cases}$$
per cui riducendo a scala la matrice associata ottengo
$$\begin{pmatrix} 1 & 2 & a \\ 0 & k-2 & b-a \end{pmatrix}$$

Qui non ci rimane che distinguere per casi:
- $k \neq 2 \implies rr(A) = 2 = rr(A|\underline{b}) (= \text{n° incognite}) \implies$ _il sistema ha (1) soluzione_; si ha $(a, b) \in U \ \ \forall (a, b) \implies U = \mathbb{R}^{2}$
- $k = 2$
	- $b-a \neq 0 \implies rr(A) = 1 \neq 2 = rr(A|\underline{b}) \implies$ _il sistema non ha soluzione_;
	- $b - a = 0 \implies rr(A) = 1 = rr(A|\underline{b}) (< \text{n° incognite}) \implies$ _il sistema ha infinite soluzioni dipendenti da 1 variabile libera_; si ha infatti $U = \{(a, a) | a \in \mathbb{R}\}$

Graficamente parlando, preso il sottospazio generato da $U$ ci accorgiamo che _se $k$ è diverso da 2 abbiamo due vettori su due rette diverse_, che quindi [[sottospazi-vettoriali-di-r2|come già dimostrato]] portano $U = \mathbb{R}^{2}$; _se invece $k$ è uguale a 2, avremo lo spazio generato da $\langle (1, 1), (2, 2) \rangle$_, ovvero tutte le coppie sulla retta $y=x$, ed è per questo che distinguiamo per le _coppie in cui $b \neq a$, che non stanno nella retta_, da quelle in cui _$b = a$, che invece appartengono a tale retta_.

## Referenze
- [[forme-dei-sottospazi|Forme dei sottospazi]]

[^1]: esattamente quello che avevamo visto per il secondo caso dei [[sottospazi-vettoriali-di-r2|sottospazi di R2]] (_la retta_)
[^2]: che sappiamo essere sottospazio di $V$ perché $\ker(f) \leq V$;