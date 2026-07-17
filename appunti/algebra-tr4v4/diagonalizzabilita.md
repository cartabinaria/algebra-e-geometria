---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-04-2024 22:30:14
links:
  - "[[lecture-16042024091615|Lecture 16042024091615]]"
  - "[[lecture-18042024111552|Lecture 18042024111552]]"
  - "[[lecture-23042024092139|Lecture 23042024092139]]"
---
# Diagonalizzabilità
---
## Introduzione
> Un'[[applicazione-lineare|applicazione lineare]] $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ [[applicazione-lineare-definita-da-una-matrice|definita da una matrice]] $M$ si dice **diagonalizzabile** se esiste una [[base|base]] $\beta$ di $\mathbb{R}^{n}$ tale che $M_{\beta}^{\beta} (f)$ sia [[matrice-diagonale|diagonale]].

## Proposizioni
### Legame con autovettori
Prendiamo per esempio $f: \mathbb{R}^{2} \to \mathbb{R}^{2}$ tale che $f(e_{1}) = e_{2}, f(e_{2}) = e_{1}$, ovvero un'applicazione lineare che _flippa_ lo spazio $\mathbb{R}^{2}$, creando una simmetria rispetto alla retta $y = x$. Di fatto si ha che $(x_{1}, x_{2}) \to (x_{2}, x_{1})$. Ci sono quindi dei vettori, come $(2, 1) \to (1, 2)$, che invertono simmetricamente a $y=x$ la loro direzione, e altri che invece la mantengono: proprio gli [[autovettore|autovettori]]. In particolare, _tutti i vettori sulla retta $y=x$ e $y=-x$ sono autovettori_.
Si pensi a
- $v_{1} = (1, 1) \to (1, 1)$, con [[autovalore|autovalore]] $1$;
- $v_{2} = (1, -1) \to (-1, 1) = -(1, -1)$, con autovalore $-1$;

Osserviamo ora che $\beta = \{v_{1}, v_{2}\}$ è base di $\mathbb{R}^{2}$ (dal [[teorema-gel|teorema GEL]]). Allora troviamo $A_{\beta\beta}$:
$$A_{\beta\beta} = ((f(v_{1}))_{\beta}, (f(v_{2}))_{\beta})) = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$
et-voilà! La matrice è diagonale.

L'idea è che **se prendo una base di autovettori la matrice viene _sempre_ diagonale**.

> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ lineare, allora si ha che
> $$f \text{ diagonalizzabile} \iff \exists \beta \subseteq \mathbb{R}^{n} \text{ di autovettori di } f$$
> ovvero $f$ è diagonalizzabile sse esiste una base di $\mathbb{R}^{n}$ costituita da autovettori di $f$.

<u>Nota bene</u>: gli elementi sulla diagonale principale di una matrice diagonale associata a una $f$ sono proprio gli autovalori.

#### Dimostrazione
$\impliedby$: supponiamo che esista una base $\beta = \{v_{1}, \cdots, v_{n}\}$ di autovettori di $f$. Perciò $f(v_{1}) = \lambda_{1}v_{1}, \cdots, f(v_{n}) = \lambda_{n}v_{n}$. Costruisco $A_{\beta\beta} = ((f(v_{1}))_{\beta}, \cdots, (f(v_{n}))_{\beta}) = ((\lambda_{1}v_{1})_{\beta}, \cdots, (\lambda_{n}v_{n})_{\beta})$. Le coordinate di $\lambda_{i}v_{i}$ rispetto alla base $\beta$ sono $(0, \cdots, \lambda_{i}, \cdots, 0)$, per cui si ottiene
$$A_{\beta\beta} = \begin{pmatrix} \lambda_{1} & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & \lambda_{n} \end{pmatrix}$$
ovvero $A_{\beta\beta}$ diagonale, per cui $f$ diagonalizzabile.

$\implies$: supponiamo ora che $f$ sia diagonalizzabile, ovvero che esista una base $\beta = \{v_{1}, \cdots, v_{n}\}$ tale che $A_{\beta\beta}$ sia diagonale, ovvero
$$A_{\beta\beta} = \begin{pmatrix} \lambda_{1} & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & \lambda_{n} \end{pmatrix}$$
Sapendo che $A_{\beta\beta} = ((f(v_{1}))_{\beta}, \cdots, (f(v_{n}))_{\beta})$, ottengo che $f(v_{1})_{\beta} = (\lambda_{1}, \cdots, 0), \cdots, f(v_{n})_{\beta} = (0, \cdots, \lambda_{n})$, per cui $f(v_{1}) = \lambda_{1}v_{1}, \cdots, f(v_{n}) = \lambda_{n}v_{n}$, ovvero che $v_{1}, \cdots, v_{n}$ sono autovettori. Perciò $\beta$ è una base di autovettori.

**Qed**.

### Legame con matrici diagonalizzabili
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ lineare e sia $A = M_{c}^{c}(\mathbb{R})$ la matrice associata a $f$ ($f = L_{A}$), allora si ha che
> $$f \text{ diagonalizzabile} \iff A \text{ diagonalizzabile}$$

Quello che stiamo cercando di dire è che _se ad una $f$ è associata, per una certa base $\beta$, una matrice $A_{\beta\beta}$ diagonale, per cui $f$ diagonalizzabile, allora $A_{cc}$ è diagonalizzabile, ovvero simile a una matrice diagonale_: _proprio $A_{\beta\beta}$_! E viceversa.

#### Dimostrazione
$\implies$: supponiamo $f$ diagonalizzabile, ovvero che esiste una base $\beta = \{v_{1}, \cdots, v_{n}\}$ tale che $A_{\beta\beta}$ è diagonale. Allora per $A_{cc}$ è diagonalizzabile perché per la [[cambio-di-base-formula-per-il-cambio-di-base|formula del cambio base]] ho
$$A_{\beta\beta} = I_{c \beta} \cdot A_{cc} \cdot I_{\beta c} = I_{\beta c}^{-1} \cdot A_{cc} \cdot I_{\beta c}$$
per cui $A_{\beta\beta}$ è [[matrice-simile|simile]] a $A_{cc}$, e per la [[riflessivita-di-una-relazione|riflessività]] della [[relazione|relazione]] "essere simili", anche $A_{cc}$ è simile ad $A_{\beta\beta}$, che _essendo diagonale rende $A_{cc}$ diagonalizzabile_.

$\impliedby$: supponiamo $A$ diagonalizzabile. Allora significa che $D = P^{-1} \cdot A \cdot P$ dove $P$ è una [[matrice-invertibile|matrice invertibile]] e $D$ una matrice diagonale. Devo dimostrare $f$ diagonalizzabile, ovvero che esiste una base $\beta = \{v_{1}, \cdots, v_{n}\}$ tale che $A_{\beta\beta}$ è diagonale. Scelgo come vettori della base le ipotetiche colonne di $P$, ovvero $\beta = \{c_{1}, \cdots, c_{n}\}$, ed essendo $P$ invertibile dal [[determinante-teoremone|teoremone]] so che sono linearmente indipendenti e da [[teorema-gel|GEL]] che generano $\mathbb{R}^{n}$, per cui base di $\mathbb{R}^{n}$. Ora, dalla formula del cambio di base so che
$$A_{\beta\beta} = I_{\beta c}^{-1} \cdot A_{cc} \cdot I_{\beta c}$$
Calcolo quindi $I_{\beta c}$, ovvero $I_{\beta c} = (id(c_{1})_{c}, \cdots, id(c_{n})_{c}) = (c_{1}, \cdots, c_{n})$, ovvero $I_{\beta c} = P$. Per cui
$$A_{\beta\beta} = P^{-1} \cdot A \cdot P = D$$
e quindi $A_{\beta\beta}$ è diagonale.

**Qed**.

### Lineare indipendenza
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ un'applicazione lineare e $v_{1}, \cdots, v_{k}$ autovettori di $f$ con autovalori distinti $\lambda_{1}, \cdots, \lambda_{k}$, allora $v_{1}, \cdots, v_{k}$ sono [[indipendenza-lineare|linearmente indipendenti]].

### Legame con autovalori
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ un'applicazione lineare con $n$ autovalori distinti, allora $f$ è diagonalizzabile.

Per cui se ci viene chiesto _solo_ se una certa $f$ è diagonalizzabile ci basta trovare $n$ autovalori, senza la base di $n$ autovettori.

#### Dimostrazione
Se $f$ ha $n$ autovalori distinti allora significa che si hanno $\lambda_{1}, \cdots, \lambda_{n} \in \mathbb{R}$ e $v_{1}, \cdots, v_{n}$ dei rispettivi autovettori. Dalla proposizione precedente abbiamo che _$v_{1}, \cdots, v_{n}$ sono linearmente indipendenti, perciò per [[teorema-gel|GEL]] che costituiscono una base di $\mathbb{R}^{n}$_: abbiamo trovato una base di autovettori, per cui per la prima proposizione $f$ è diagonalizzabile.

### Legame con molteplicità
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ con autovalori $\lambda_{1}, \cdots, \lambda_{k}$ allora sapendo che
> $$m_{a}(\lambda_{1}) + \cdots + m_{a}(\lambda_{k}) \leq n$$
> e che, per il [[autovalore-legame-con-molteplicita|legame tra molteplicità e autovalori]],
> $$1 \leq m_{g}(\lambda_{i}) \leq m_{a}(\lambda_{i}) \ \ \ \forall i = \{1, \cdots, k\}$$
> allora
> $$\begin{align} & f \text{ diagonalizzabile} \\ & \iff \dim(V_{\lambda_{1}}) + \cdots + \dim(V_{\lambda_{k}}) = n \\ & \iff \dim(V_{\lambda_{i}}) = m_{a}(\lambda_{i}) \ \ \forall i = \{1, \cdots, k\} \\ & \iff m_{g}(\lambda_{i}) = m_{a}(\lambda_{i}) \ \ \forall i = \{1, \cdots, k\} \end{align}$$
> o alternativamente
> $$f \text{ diagonalizzabile} \iff m_{a}(\lambda_{1}) + \cdots + m_{a}(\lambda_{k}) = n \ \ \land \ \ m_{g}(\lambda_{i}) = m_{a}(\lambda_{i}) \ \ \forall i \in \{1, \cdots, k\}$$

L'idea di fondo è questa: affinché $f$ sia diagonalizzabile dobbiamo trovare una base di autovettori, per cui $n$ autovettori linearmente indipendenti. Con il polinomio caratteristico riusciamo a trovare $k$ autovalori, per cui si ha che:
- $k = n \implies$ per le proposizioni precedenti abbiamo anche $n$ autovettori indipendenti;
- $k < n \implies$ dobbiamo analizzare gli autospazi associati a tali autovalori.

In particolare il polinomio caratteristico può essere composto da monomi di grado superiore a 1, come nel seguente caso $p_{A}(x) = (x-3)^{4}(x-5)(x-4)^{2}(x+2)$. In altre parole si troveranno autovalori con [[molteplicita-algebrica|molteplicità algebriche]] anche superiori a 1.

Allora per gli autovalori con molteplicità algebrica uguale a 1 sappiamo, per la proposizione sul legame degli autovalori con le molteplicità, che la dimensione dell'autospazio per quell'autovalore, ovvero la sua [[molteplicita-geometrica|molteplicità geometrica]], sarà esattamente 1. Vale a dire che riusciremo ad estrarre 1 autovettore linearmente indipendente da quell'autospazio.

Per gli autovalori con molteplicità algebrica maggiore di 1 dovremmo andare ad analizzare la dimensione dell'autospazio! Tale dimensione indica di fatto quanti autovettori linearmente indipendenti possiamo estrapolare per quell'autovalore: se $m_{a}(\lambda) = 3$ potrebbe capitare che $m_{g}(\lambda) = 1$. Se dobbiamo trovare $n$ autovettori linearmente indipendenti (per formare una base) allora la somma delle dimensioni degli autospazi dev'essere esattamente $n$; e se sappiamo che la somma delle molteplicità algebriche deve a sua volta essere $n$ (altrimenti non c'è speranza che $f$ sia diagonalizzabile), allora per forza $m_{a}(\lambda_{i}) = m_{g}(\lambda_{i}) \ \ \forall i \in \{1, \cdots, k\}$.

Fondamentalmente **se anche per un solo autovalore la molteplicità geometrica non coincide con quella algebrica significa che non riusciremo mai a ottenere abbastanza autovettori linearmente indipendenti per formare una base di $f$**.

## Esercizi
### Completezza
Sia $f: \mathbb{R}^{2} \to \mathbb{R}^{2}$ tale che $f(x_{1}, x_{2}) = (-7x_{1}-3x_{2}, 9x_{1}+5x_{2})$ e sia $A = A_{cc}$.
Viene richiesto di:
1. trovare $A$ (semplice)
2. stabilire se $f$ è diagonalizzabile, e se sì punto 3
3. trovare $D$ diagonale simile ad $A$
4. trovare $P$ t.c. $P^{-1} \cdot A \cdot P = D$
5. trovare tutte le matrici $D$ diagonali simili ad $A$ (bonus)
6. trovare se possibile $P_{1}, P_{2}$ distinte t.c. $P_{1}^{-1} \cdot A \cdot P_{1} = P_{2}^{-1} \cdot A \cdot P_{2} = D$ (bonus)

#### 1.
Semplice, perché abbiamo $A = A_{cc}$, quindi ci basta proiettare sulle basi canoniche, e ci viene
$$A = \begin{pmatrix} -7 & -3 \\ 9 & 5 \end{pmatrix}$$

#### 2.
Per stabilire o meno se $f$ è diagonalizzabile dobbiamo trovare una base di autovettori, per cui partiamo con l'unico strumento a nostra disposizione per cercare innanzitutto gli autovalori: il [[polinomio-caratteristico|polinomio caratteristico]]. _Se non ci sono autovalori, non ci saranno neanche autovettori_, e vale il contrario.

Quindi 
$$p_{A}(x) = \det\begin{pmatrix} -7-x & -3 \\ 9 & 5-x \end{pmatrix} = (-7-x)(5-x)-(-27) = x^{2}+2x-35+27 = x^{2}+2x-8$$

Fattorizziamo $p_{A}(x)$ e otteniamo
$$p_{A}(x) = (x+4)(x-2)$$
per cui gli autovalori esistono e sono:
- $\lambda_{1} = -4$
- $\lambda_{2} = 2$

<u>Nota bene</u>: il polinomio caratteristico ha grado 2, per cui è una parabola. _Potrebbero anche non esserci soluzioni, e in tal caso non ci sarebbero autovalori, quindi nemmeno autovettori e di conseguenza $f$ non sarebbe diagonalizzabile_.

Trovati gli autovalori bisogna determinare gli autovettori: usiamo gli [[autospazio|autospazi]]. Partendo da $\lambda_{1}$ si ha che
$$V_{\lambda_{1}} = V_{-4} = \ker(A - (-4)I) = \ker(A + 4I) = \ker\begin{pmatrix} -7+4 & -3 \\ 9 & 5+4 \end{pmatrix} = \ker\begin{pmatrix} -3 & -3 \\ 9 & 9 \end{pmatrix}$$

Ovviamente della matrice risultante possiamo notare che il determinante è 0: **lo abbiamo costruito apposta per la definizione di polinomio caratteristico**! Quindi è giusto che sia 0 e dovremmo preoccuparci se così non fosse.

In ogni caso troviamo il sottospazio di $\ker$, risolvendo il sistema lineare associato
$$\begin{pmatrix} -3 & -3 & 0 \\ 9 & 9 & 0 \end{pmatrix}$$

e l'equazione cartesiana associata viene $x_{1} = -x_{2}$, per cui concludiamo scrivendo
$$V_{-4} = \langle (-1, 1) \rangle$$

Rifacendo lo stesso ragionamento per $V_{\lambda_{2}} = 2$ ci viene
$$V_{2} = \langle (1, -3) \rangle$$

Ecco che _allora riesco a trovare una base di autovettori per $f$_: $\beta = \{(-1, 1), (1, -3)\}$ lo è!

#### 3.
La matrice diagonale associata a tale base, ovvero $A_{\beta\beta}$, la sappiamo già senza bisogno di fare alcun calcolo: **basta mettere gli autovalori sulla diagonale**, ovvero
$$A_{\beta\beta} = \begin{pmatrix} -4 & 0 \\ 0 & 2 \end{pmatrix}$$

Per la proposizione sopra riportata sappiamo che $A$ ($A_{cc}$) è quindi diagonalizzabile, ovvero simile a questa $A_{\beta\beta}$. Per cui è $A_{\beta\beta}$ la matrice diagonale richiesta nel punto 3.

#### 4.
Per la proposizione sopra riportata sappiamo che è facile identificare $P$ tale che $P^{-1} \cdot A_{cc} \cdot P = D = A_{\beta\beta}$. Questa $P$ sarà per forza $I_{\beta c}$, ovvero
$$I_{\beta c} = \begin{pmatrix}
-1 & 1 \\ 1 & -3
\end{pmatrix}$$

#### 5.
Sappiamo che $D$ ($A_{\beta\beta}$) per essere diagonale deve avere sulla diagonale gli autovalori, per cui avendo in questo caso solo 2 autovalori posso scambiarli e ottenere
$$D_{2} = \begin{pmatrix} 2 & 0 \\ 0 & -4 \end{pmatrix}$$
Questo posso farlo perché siamo sotto l'assunzione che $\beta$ sia una base _ordinata_, per cui _se scambio i due autovettori $(-1, 1), (1, -3)$ ottengo una base $\beta'$ diversa da $\beta$_.

Quindi $D$ non è unica, ma c'è un numero finito di scelte di $D$, ed è precisamente **$n!$ matrici**.

#### 6.
Sapendo che $P = I_{\beta c}$ allora posso prendere $\beta_{2} = \{(1, -1), (7, -21)\}$ perché $(1, -1) \in V_{-4}$ e $(7, -21) \in V_{2}$, e ottengo un nuovo $P_{2}$, precisamente
$$P_{2} = \begin{pmatrix} 1 & 7 \\ -1 & -21 \end{pmatrix}$$

Fondamentalmente ci sono **infinite $P$** che posso prendere, perché ci sono infinite [[combinazione-lineare|combinazioni lineari]] che posso comporre per ottenere una nuova base $\beta_{i}$.

### Molteplicità
Ora analizziamo invece un esercizio che mette in luce la relazione che sussiste tra molteplicità algebra, molteplicità geometrica e diagonalizzabilità di un'applicazione lineare.

Consideriamo la seguente matrice $A$ (associata a un'applicazione lineare $f$):
$$A = \begin{pmatrix} 8 & -18 & 9 \\ 3 & -7 & 3 \\ 0 & 0 & -1 \end{pmatrix}$$
Dobbiamo capire se è diagonalizzabile o meno.

Sappiamo che è diagonalizzabile $\iff$ riusciamo a trovare una base di autovettori. Allora cerchiamo gli autovalori attraverso il polinomio caratteristico, per cui
$$p_{A}(x) = \det(A - xI) = -(x+1)[(8-x)(-7-x)-3(-18)] = -(x+1)[x^{2}-x-56+54] = -(x+1)(x-2)(x+1)$$

cioè in definitiva
$$p_{A}(x) = -(x+1)^{2}(x-2)$$

Gli autovalori e le rispettive molteplicità algebriche sono allora
- $\lambda_{1} = -1$ --> $m_{a}(-1) = 2$;
- $\lambda_{2} = 2$ --> $m_{a}(2) = 1$.

Di conseguenza la dimensione dell'autospazio $V_{2}$ è per forza 1, infatti $1 \leq m_{g}(2) \leq 1$, per cui potremmo estrarre solo 1 autovettore da esso.

La dimensione dell'autospazio $V_{-1}$ invece non sappiamo se è 1 o se è 2, infatti $1 \leq m_{g}(-1) \leq 2$, per cui dobbiamo analizzarlo meglio:
$$V_{-1} = \ker(A - (-1)I) = \ker(A + I)$$
da cui, risolvendo il [[sistema-lineare-omogeneo|sistema lineare omogeneo]] viene che $\dim(V_{-1}) = 3-1 = 2$.

Per cui riesco ad estrarre fino a 2 autovettori linearmente indipendenti da $V_{-1}$, _per un totale, insieme all'autovettore estratto da $V_{2}$, di 3 autovettori linearmente indipendenti_: **riusciamo a costruire una base di autovettori, per cui $A$ è diagonalizzabile**.

E non solo: possiamo anche facilmente individuare la matrice diagonale simile ad $A$. Se consideriamo la base $\beta$ di autovettori di $A$, allora possiamo costruire la matrice $D = A_{\beta\beta}$ come $D = ((f(v_{1}))_{\beta}, \cdots, (f(v_{n}))_{\beta}) = ((\lambda_{1}v_{1})_{\beta}, \cdots, (\lambda_{n}v_{n})_{\beta})$ ed essendo $(\lambda_{i}v_{i})_{\beta} = (0, \cdots, \lambda_{i}, \cdots, 0) \ \ \forall i \in \{1, \cdots, n\}$, si ha proprio che $D$ è diagonale, e per la formula del cambio di base che $A_{cc}$ è simile ad $A_{\beta\beta} = D$.

In poche parole costruiamo la matrice $D$ mettendo gli autovalori trovato nella diagonale:
$$D = \begin{pmatrix} -1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 2 \end{pmatrix}$$

## Referenze
- una spiegazione e dimostrazione del teorema di diagonalizzabilità (ultima proposizione) è data [qui](https://pagine.dm.unipi.it/~algebralineare/ing1718/AppuntiSecondoSemestre/Alg%20Lin.pdf)

[^1]: questo è possibile grazie alla [[riflessivita-di-una-relazione|riflessività]] della [[relazione|relazione]] "essere simili" ($A = P^{-1} \cdot A \cdot P$)