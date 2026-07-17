---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 30-03-2024 13:01:38
links:
  - "[[lecture-26032024091342|Lecture 26032024091342]]"
  - "[[lecture-27032024091734|Lecture 27032024091734]]"
---
# Controimmagine
---
## Introduzione
> Sia $f: A \to B$ una [[funzione-matematica|funzione]], e sia $b \in B$, allora la **controimmagine** (o **preimmagine**, **antimmagine**) di $b$ tramite $f$ è
> $$f^{-1}(b) = \{a \in A | f(a) = b\}$$
> <u>Attenzione</u>: non è l'[[funzione-inversa|inversa]] di $f$.

### Conseguenze
Si ha allora che la controimmagine di un certo $b$ tramite $f$ è l'[[definizione-di-insieme-vuoto|insieme vuoto]] sse quel $b$ non appartiene all'[[immagine-di-funzione|immagine]] di $f$, ovvero
$$f^{-1}(b) = \varnothing \iff b \notin \Im(f)$$

## Algebra lineare
In [[algebra-lineare|algebra lineare]] si analizza la controimmagine di un'[[applicazione-lineare|applicazione lineare]] $f: V \to W$ dove $V, W$ sono [[spazio-vettoriale|spazi vettoriali]].

### Casistiche
Si ha che per questa $f: V \to W$ lineare, preso un $w \in W$ si distinguono due casi:
- $w \neq \underline{0} \implies f^{-1}(w) \nleq V$, questo perché $0_{V} \notin f^{-1}(w)$[^1], infatti $f(0_{V})=0_{W} \neq w$;
- $w = \underline{0} \implies f^{-1}(w) \leq V$, questo perché $f^{-1}(w) = \ker(f) \leq V$[^2];

### Esercizi
#### 1.
Sia $f: \mathbb{R}^{3} \to \mathbb{R}^{2}$ un'applicazione lineare definita nel seguente modo
$$f(x_{1}, x_{2}, x_{3}) = (x_{1}-x_{2}, x_{1}+2x_{3})$$

Viene chiesto di trovare
$$f^{-1}(2, -3)$$
ovvero la controimmagine di $w = (2, -3)$.

Scriviamo intanto la matrice $A$ associata a $f$
$$A = \begin{pmatrix} 1 & -1 & 0 \\ 1 & 0 & 2 \end{pmatrix}$$
quindi applichiamo la definizione di controimmagine
$$f^{-1}(2, -3) = \{\underline{x} \in \mathbb{R}^{3} | f(\underline{x}) = (2, -3)\} = \{\underline{x} \in \mathbb{R}^{3} | A\underline{x} = (2, -3)\}$$

Allora la controimmagine sarà l'_insieme delle soluzioni del sistema lineare $A\underline{x} = (2, -3)$_, cui matrice è
$$(A|\underline{b}) = \begin{pmatrix} 1 & -1 & 0 & 2 \\ 1 & 0 & 2 & -3 \end{pmatrix}$$

Applicando [[algoritmo-di-gauss|Gauss]] si ottiene che
$$rr(A) = 2 = rr(A|\underline{b}) < 3 = \text{ n° incognite}$$
per cui il sistema ha infinite soluzioni dipendenti da $3-2=1$ parametro, e si scrive
$$f^{-1}(2, -3) = \{(-2x_{3}-3, -2x_{3}-5, x_{3}) | x_{3} \in \mathbb{R}\} = \{(-3, -5, 0) + (-2, -2, 1)x_{3} | x_{3} \in \mathbb{R}\}$$

#### 2.
In questo altro esercizio, data un'applicazione $f_{a}: \mathbb{R}^{3} \to \mathbb{R}^{4}$ definita da
- $f_{a}(e_{1}) = e_{1}+ae_{2}+6e_{3}+4e_{4}$
- $f_{a}(e_{2}) = ae_{2}+e_{3}+e_{4}$
- $f_{a}(e_{3}) = e_{1}+14e_{2}+ae_{3}+(a-2)e_{4}$

si chiede:
1. di stabilire per quali valori di $a$ si ha che $w = 2e_{1}+14e_{2}+12e_{3}+8e_{4} \in \Im(f_{a})$
2. di, scelto tale valore $a$, determinare $f_{a}^{-1}(w)$

Allora le vie per risolvere tale esercizio sono 2, ma prima di tutto ci determiniamo la matrice $A$ associata a $f_{a}$:
$$A = \begin{pmatrix} 1 & 0 & 1 \\ a & a & 14 \\ 6 & 1 & a \\ 4 & 1 & a-2 \end{pmatrix}$$

##### 1° modo
Se ci viene chiesto di scoprire per quale valore di $a$ il vettore $w$ appartiene a $\Im(f_{a})$, sfruttiamo la [[immagine-di-funzione-spazio-generato-dell-immagine|proposizione]]
$$\Im(f_{a}) = \langle f_{a}(e_{1}), \cdots, f_{a}(e_{3}) \rangle$$

Per cui troviamo una base di $\Im(f_{a})$ riducendo a scala $A^{T}$[^3], quindi a seconda dei casi di $a$ aggiungiamo il vettore $w$ per vedere se lo spazio generato cambia o meno, e quindi se la [[dimensione|dimensione]] di $\Im(f_{a})$ aumenta o rimane uguale. Infatti, se questa aumenta allora $w \notin \Im(f_{a})$; se questa rimane uguale invece $w \in \Im(f_{a})$.

<u>Nota bene</u>: nell'ultimo passaggio stiamo unendo [[Sottospazio generato#$w in langle v_{1}, cdots, v_{n} rangle iff langle v_{1}, cdots, v_{n} rangle = langle v_{1}, cdots, v_{n}, w rangle$|questa]] proposizione con [[Dimensione#$ dim(W) = dim(V) iff W = V$|quest'altra]].

Il problema di questo approccio risolutivo è che ci consente di rispondere solo alla prima domanda: _per rispondere alla seconda dobbiamo considerare invece la controimmagine $f_{a}^{-1}(w)$, su cui non abbiamo alcuna informazione_!

##### 2° modo
Con questo secondo approccio, infatti, riusciamo a rispondere alla seconda domanda in modo quasi immediato direttamente dai risultati ottenuti dalla prima risposta.

L'idea è di rigirare la domanda: ci viene chiesto di capire per quali valori di $a$ si ha $w \in \Im(f_{a})$? Bene, ma noi sappiamo che
$$w \in \Im(f_{a}) \iff \exists v \in \mathbb{R}^{3} | f_{a}(v) = w \iff f_{a}^{-1}(w) \neq \varnothing$$

Per cui, per sapere per quale $a$ si ha $w \in \Im(f_{a})$, ci basta conoscere per quale $a$ la controimmagine $f_{a}^{-1}(w) \neq \varnothing$.

Dobbiamo pensare a questa transizione un po' come se si trattasse di un [[isomorfismo|isomorfismo]]: **chiedersi se un vettore appartiene all'immagine è equivalente a chiedersi se la controimmagine per quel vettore è diversa dal vuoto**.

Allora analizziamo la controimmagine
$$f_{a}^{-1}(w) = \{v \in \mathbb{R}^{3} | f(v) = w\} = \{v \in \mathbb{R}^{3} | Av = w\}$$

che è appunto l'insieme delle soluzioni del sistema lineare $Av = w$. Risolto il sistema lineare associato otteniamo che
$$w \in \Im(f_{a}) \iff a \neq -2$$

Il primo punto è fatto. Per il secondo non rimane che scegliere un valore di $a$ per cui $w \in \Im(f_{a})$, e sostituire tale valore nella matrice che identifica $f_{a}^{-1}(w)$ e scrivere tale controimmagine come insieme di soluzioni (come fatto già nell'esercizio 1).

La morale è che _al posto di concentrarsi sull'immagine e quindi sulle colonne di $A$, in questo esercizio conviene rimanere sulla controimmagine e quindi sulle righe_.

### Proposizione
#### Soluzione di un sistema lineare
> La controimmagine di un'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]] $A$ può essere definita come l'**insieme delle soluzioni di un sistema lineare**.

Se per esempio si ha $f = L_{A}$, allora possiamo scrivere la controimmagine di $f$ per un certo $w \in W$ come
$$f^{-1}(w) = \{v \in V | A v = w\}$$
che non è altro che l'insieme delle soluzioni di un sistema lineare definito dalla matrice
$$(A|w)$$

#### Traslazione
> Sia $f: V \to W$ lineare e $w \in W$, se $f^{-1}(w) \neq \varnothing$, allora fissato un $v \in f^{-1}(w)$ t.c. $f(v) = w$, la controimmagine di $f$ può essere descritta come
> $$f^{-1}(w) = \{v+z | z \in \ker(f)\}$$

Ma cosa significa ciò? Vuol dire che la **controimmagine di un'applicazione lineare da $V$ a $W$ spazi vettoriali non è altro che il kernel traslato di $v \in f^{-1}(w)$**. Si osservi il seguente disegno:
![[Drawing 2024-03-31 12.19.58.excalidraw|750]]

<u>Nota bene</u>: _questo vale solo e unicamente nel mondo lineare_!

La proposizione sorella di questa si chiama [[teorema-di-struttura-per-sistemi-lineari|teorema di struttura per sistemi lineari]], e _unisce semplicemente i risultati della proposizione precedente ($f^{-1}$ come soluzioni di un sistema lineare) con questa_.

##### Dimostrazione
Dalle ipotesi, sapendo che $f^{-1}(w) \neq \varnothing$ per forza so che esiste appunto un $v \in f^{-1}(w)$, per cui $f(v) = w$. Allora posso scrivere $f^{-1}(w)$ come
$$f^{-1}(w) = f^{-1}(f(v))$$

Scrivo adesso che cos'è $f^{-1}(f(v))$, usando la definizione di controimmagine:
$$f^{-1}(f(v)) = \{v' \in V | f(v') = f(v)\} = \{v' \in V | f(v')-f(v) = 0\} \stackrel{\text{lin}}{=} \{v' \in V | f(v'-v) = \underline{0}\}$$

Ma allora l'insieme $\{v' \in V | f(v'-v) = \underline{0}\}$ non è altro che $\{v' \in V | (v'-v) \in \ker(f)\}$. Per cui abbiamo scoperto fondamentalmente che
$$f^{-1}(w) = \{v' \in V | (v'-v) \in \ker(f)\}$$
Ora, fissato $z = v'-v \in \ker(f)$, si ha $v' = v+z \in V$ e allora possiamo scrivere la controimmagine come
$$f^{-1}(w) = \{v+z \in V | z \in \ker(f)\}$$

o meglio, sapendo che $v+z = v+v'-v = v'$ appartiene a $V$ per ipotesi, si giunge a
$$f^{-1}(w) = \{v + z | z \in \ker(f)\}$$

**Qed**.

## Referenze
[^1]: primo criterio degli spazi vettoriali
[^2]: dimostrato [[Applicazione lineare#$f text{ lineare} implies ker(f) leq V$|qui]]
[^3]: ovvero la [[matrice-trasposizione|trasposta]] di $A$