---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 05-05-2024 19:06:38
links:
  - "[[lecture-24042024092014|Lecture 24042024092014]]"
  - "[[lecture-30042024091716|Lecture 30042024091716]]"
---
# Sottospazio ortogonale
---
## Introduzione
> Sia $W \leq \mathbb{R}^{n}$, quindi [[sottospazio-vettoriale|sottospazio]] dello [[spazio-vettoriale|spazio vettoriale]] $\mathbb{R}^{n}$, allora si ha che
> $$W^{\bot} = \{v \in \mathbb{R}^{n} | <v, w> = 0 \ \ \forall w \in W\}$$
> è un sottospazio di $\mathbb{R}^{n}$ e si dice **sottospazio ortogonale** a $W$.
> Si tratta dell'insieme di _tutti i vettori di $\mathbb{R}^{n}$ che sono [[ortogonalita|ortogonali]] a ogni vettore di $W$_.
> Si ha, ovviamente, che $W$ è ortogonale a $W^{\bot}$, perché vale
> $$<v, w> = 0 \ \ \forall v \in W, \ \forall w \in W^{\bot}$$
> e si indica con
> $$W^{\bot} \bot W$$

### Dimostrazione sottospazio
Dimostriamo che $W^{\bot} \leq \mathbb{R}^{n}$. Per definizione deve avvenire che:
- $\underline{0} \in W^{\bot}$
- $u + v \in W^{\bot} \ \ \forall u, v \in W^{\bot}$
- $\lambda u \in W^{\bot} \ \ \forall u \in W^{\bot}, \ \forall \lambda \in \mathbb{R}$

#### $\underline{0} \in W^{\bot}$
Vero perché _il vettore nullo è ortogonale a qualunque altro vettore_, per cui sicuramente fa parte di $W^{\bot}$.

#### $u + v \in W^{\bot} \ \ \forall u, v \in W^{\bot}$
Fisso due vettori $u, v \in W^{\bot}$, ovvero tali che $<u, w> = 0 \ \ \forall w \in W$ e $<v, w> = 0 \ \ \forall w \in W$. Devo dimostrare che $u + v \in W^{\bot}$, ovvero che
$$<u + v, w> = 0 \ \ \forall w \in W$$
Allora uso le proprietà del prodotto scalare e ottengo
$$<u, w> + <v, w> = 0 \ \ \forall w \in W$$
il che è vero per le assunzioni iniziali.

#### $\lambda u \in W^{\bot} \ \ \forall u \in W^{\bot}, \ \forall \lambda \in \mathbb{R}$
Fisso $u \in W^{\bot}$ tale che $<u, w> = 0 \ \ \forall w \in W$, e fisso $\lambda \in \mathbb{R}$. Devo dimostrare $\lambda u \in W^{\bot}$, ovvero che
$$<\lambda u, w> = 0 \ \ \forall w \in W$$
Allora uso le proprietà del prodotto scalare e ottengo
$$\lambda <u, w> = 0 \ \ \forall w \in W$$
il che è vero per le assunzioni iniziali.

**Qed**.

## Proposizioni
### Verifica con base
> Sia $W = \langle w_{1}, \cdots, w_{k} \rangle$, allora il sottospazio ortogonale è dato da
> $$W^{\bot} = \{v \in \mathbb{R}^{n} | <v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k\}$$

Ovvero fondamentalmente **per controllare se un vettore $v \in W^{\bot}$ basta verificare la perpendicolarità tra $v$ e $w_{i}$ per ogni $w_{i}$ che genera $W$**.
E' semplicemente un criterio per verificare in tempo limitato e non infinito l'appartenenza di un vettore a un sottospazio ortogonale! _Se ciò non valesse, infatti, dovremmo verificare l'ortogonalità tra $v$ e tutti gli infiniti vettori $w$ di $W$_.

#### Dimostrazione
Dobbiamo fondamentalmente dimostrare l'uguaglianza tra due insiemi, e in particolare che se un vettore $v$ appartiene a $\{v \in \mathbb{R}^{n} | <v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k\}$ allora automaticamente appartiene anche a $\{v \in \mathbb{R}^{n} | <v, w> = 0 \ \ \forall w \in W\}$.

Assumiamo allora che $v \in \{v \in \mathbb{R}^{n} | <v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k\}$, ossia che
$$<v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k$$

Devo dimostrare che $v \in \{v \in \mathbb{R}^{n} | <v, w> = 0 \ \ \forall w \in W\}$, ovvero che
$$<v, w> = 0 \ \ \forall w \in W$$

Fisso $w \in W$, e so quindi che $w = \lambda_{1}w_{1} + \cdots + \lambda_{k}w_{k}$, per cui sostituisco nel prodotto scalare e ottengo
$$<v, \lambda_{1}w_{1} + \cdots + \lambda_{k}w_{k}> = 0$$

Uso la bilinearità e mi riduco a dimostrare
$$\lambda_{1}<v, w_{1}> + \cdots + \lambda_{k}<v, w_{k}> = 0$$

che è ovvio per l'ipotesi $<v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k$.

**Qed**.


<u>Nota bene</u>: _non c'è bisogno di dimostrare l'altro senso di appartenenza perché è banale_. Infatti se un vettore sta in $\{v \in \mathbb{R}^{n} | <v, w> = 0 \ \ \forall w \in W\}$ automaticamente è presente anche in $\{v \in \mathbb{R}^{n} | <v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k\}$.

#### Esercizio
Per capire l'importanza di questa proposizione si svolge il seguente esercizio: fissato $W = \langle (1, 0, 0, 1, 1), (1, 1, 0, 1, 1), (0, 0, 1, 0, -1), (2, 1, 1, 2, 1) \rangle = \langle w_{1}, w_{2}, w_{3}, w_{4} \rangle$ si deve trovare una base di $W^{\bot}$.

Per trovare una base di $W^{\bot}$ usiamo le _equazioni cartesiane_[^1], ovvero risolviamo il sistema associato a
$$x = (x_{1}, x_{2}, x_{3}, x_{4}, x_{5}) \in W^{\bot}$$

Questo avviene, per la proposizione in analisi, $\iff$
$$<x, w_{i}> = 0 \ \ \forall i = 1, \cdots, 4$$

Per cui riassumiamo in un [[sistema-lineare|sistema lineare]] le condizioni affinché $x \in W^{\bot}$:
$$x \in W^{\bot} \iff \begin{cases}1x_{1} + 0x_{2} + 0x_{3} + 1x_{4} + 1x_{5} = 0 \\ 1x_{1} + 1x_{2} + 0x_{3} + 1x_{4} + 1x_{5} = 0 \\ 0x_{1} + 0x_{2} + 1x_{3} + 0x_{4} - 1x_{5} = 0 \\ 2x_{1} + 1x_{2} + 1x_{3} + 2x_{4} + x_{5} = 0\end{cases}$$

Notiamo che è [[sistema-lineare-omogeneo|omogeneo]]: questo è ovvio, infatti _la soluzione nulla $x = \underline{0}$ è ortogonale a qualunque vettore ed è sempre presente in $W^{\bot}$_ (motivo per cui è un sottospazio).

Ad ogni modo, risolvendo con [[algoritmo-di-gauss|Gauss]], si ottiene che le soluzioni dipendono da $5-3 = 2$ parametri, per cui
$$\dim(W^{\bot}) = 5 - 3 = 2$$
In particolare, trasformando le equazioni cartesiane risultanti in [[sottospazio-generato|sottospazio generato]], si ottiene la base di $W^{\bot}$:
$$W^{\bot} = \langle (-1, 0, 0, 1, 0), (-1, 0, 1, 0, 1) \rangle$$


### Dimensione
> Sia $W \leq \mathbb{R}^{n}$, allora si ha che
> $$\dim(W^{\bot}) = n - \dim(W)$$

Una sorta di [[teorema-della-dimensione|teorema della dimensione]] ma per spazi ortogonali.

#### Dimostrazione
Suppongo che $W$ abbia dimensione $k \leq n$, ovvero
$$\dim(W) = k \leq n$$
per cui definiamo una base $\beta = \{w_{1}, \cdots, w_{k}\}$ di $W$, tale che $W = \langle w_{1}, \cdots, w_{k} \rangle$.

Allora $W^{\bot} = \{v \in \mathbb{R}^{n} | <v, w_{i}> = 0 \ \ \forall i = 1, \cdots, k\}$, ossia affinché un vettore di $\mathbb{R}^{n}$ $v$ appartenga a $W^{\bot}$ deve soddisfare $k$ condizioni su vettori di ordine $n$, ossia
$$v \in W^{\bot} \iff \begin{cases} v_{1}w_{11} + \cdots + v_{n}w_{1n} = 0 \\ \vdots & (k) \\ v_{1}w_{k1} + \cdots + v_{n}w_{kn} = 0 \end{cases}$$

Il sistema è associato a una matrice $A$ che ha per righe $w_{1}, \cdots, w_{k}$, per cui si ottiene che
$$W^{\bot} = \{v \in \mathbb{R}^{n} | Av = \underline{0}\}$$
ovvero un vero e proprio [[nucleo|kernel]].

Sappiamo che almeno una soluzione esiste: quella nulla (perché si tratta di un sistema lineare omogeneo). Perciò per il [[teorema-di-rouche-capelli|teorema di Rouché-Capelli]], fissato $n$ come il numero di colonne e $k$ come il rango della matrice associata (perché $w_{1}, \cdots, w_{k}$ sono linearmente indipendenti), la soluzione del sistema dipenderà da $n - k$ parametri, per cui la dimensione di $W^{\bot}$ sarà proprio $n - k$:
$$\dim(W^{\bot}) = n - k = n - \dim(W)$$

**Qed**.

### Intersezione
> Sia $W \leq \mathbb{R}^{n}$, allora si ha che
> $$W \cap W^{\bot} = \{\underline{0}\}$$

#### Dimostrazione
Per dimostrare che l'intersezione tra $W$ e $W^{\bot}$ fornisce il [[assioma-del-singoletto|singoletto]] del vettore nullo $\underline{0}$, fissiamo un $v \in W \cap W^{\bot}$ e dimostriamo che $v = \underline{0}$.

Sia $v \in W$, e sia sempre $v \in W^{\bot}$, tale che
$$<v, w> = 0 \ \ \forall w \in W$$
Allora si ha anche
$$<v, v> = 0 \implies v = \underline{0}$$

**Qed**.

## Referenze
[^1]: fare riferimento alle [[forme-dei-sottospazi|forme dei sottospazi]]