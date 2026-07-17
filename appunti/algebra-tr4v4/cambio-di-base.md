---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 15-04-2024 17:24:10
links:
  - "[[lecture-10042024092444|Lecture 10042024092444]]"
  - "[[lecture-15042024131541|Lecture 15042024131541]]"
  - "[[lecture-16042024091615|Lecture 16042024091615]]"
---
# Cambio di base
---
## Introduzione
> Il **cambio di base** è un processo che consiste nel _modificare_, attraverso opportune formule, _le [[base|basi]] di riferimento di [[applicazione-lineare-definita-da-una-matrice|applicazioni lineari definite da matrici]] del dominio e codominio_.

Infatti un'applicazione lineare $f: \mathbb{R}^{n} \to \mathbb{R}^{m}$ identificata da una matrice $A$, può essere rappresentata da infinite basi diverse del dominio e del codominio: non per forza quelle canoniche. Allora, _modificando le basi, cambiano di conseguenza le [[coordinate-rispetto-a-una-base|coordinate]] rispetto a tali basi, e quindi anche le matrici_.

### Generalizzazione di un'applicazione lineare definita da matrice
Per poter procedere ci è necessario generalizzare il concetto di applicazione lineare definita da una matrice. In particolare sapevamo che fissata la base canonica $\beta = \{v_{1}, \cdots, v_{n}\}$ del dominio, potevamo definire $f$ come
$$f(v) = A \cdot v$$
dove $A$ è una matrice che ha per colonna le coordinate delle immagini $f(v_{1}), \cdots, f(v_{n})$ rispetto alla base canonica del codominio.

Da notare quindi come sia dominio che codominio lavorassero sulle loro rispettive basi canoniche. Non era necessario specificarlo perché davamo per scontato che trattassimo le $L_{A}$ su basi canoniche.

Se invece volessimo dare una definizione generale, dovremmo scrivere:
> Sia $f: V \to W$ un'applicazione lineare, $\beta = \{v_{1}, \cdots, v_{n}\}$ una base _ordinata_ di $V$ e $\beta' = \{w_{1}, \cdots, w_{m}\}$ base _ordinata_ di $W$, allora esiste una matrice
> $$A_{\beta\beta'} = M_{\beta}^{\beta'} (f) \in M_{m \times n} (\mathbb{R})$$
> tale che
> $$(f(v))_{\beta'} = A_{\beta\beta'} \cdot (v)_{\beta}$$
> dove
> $$A_{\beta\beta'} = \begin{pmatrix} (f(v_{1}))_{\beta'} & \cdots & (f(v_{n}))_{\beta'} \end{pmatrix}$$

<u>Nota bene</u>: la versione non generale, quindi, si scriverebbe come $$(f(v))_{c'} = A \cdot (v)_{c}$$, dove $c$ è la base canonica di $V$ e $c'$ quella di $W$.

#### Dimostrazione
Dobbiamo dimostrare che è sempre possibile creare una matrice $A$ in tale modo. Ci concentriamo sul caso $n = 2$ e $m = 3$ e ci fidiamo del fatto che il ragionamento si può estendere al caso generale.

Per cui fissiamo $\beta = \{v_{1}, v_{2}\}$ base ordinata di $V$, e $\beta' = \{w_{1}, w_{2}, w_{3}\}$ e prendiamo un $v \in V$ per cui $v = \lambda_{1}v_{1} + \lambda_{2}v_{2}$ ([[combinazione-lineare|combinazione lineare]] di $\beta$) e $(v)_{\beta} = (\lambda_{1}, \lambda_{2})$.
L'idea è ora di definire $A_{\beta\beta'}$, per cui scriviamo le immagini della base $\beta$, e poi le loro coordinate rispetto a $\beta'$. Abbiamo $f(v_{1}) = \mu_{1}w_{1} + \mu_{2}w_{2} + \mu_{3}w_{3}$ e $f(v_{2}) = \mu_{4}w_{1} + \mu_{5}w_{2} + \mu_{6}w_{3}$, per cui $(f(v_{1}))_{\beta'} = (\mu_{1}, \mu_{2}, \mu_{3})$ e $(f(v_{2}))_{\beta'} = (\mu_{4}, \mu_{5}, \mu_{6})$.
Non ci resta che calcolare $f(v)$ per arrivare a definire la matrice, per cui
$$f(v) = \lambda_{1}f(v_{1}) + \lambda_{2}f(v_{2}) = \lambda_{1}\mu_{1}w_{1} + \lambda_{1}\mu_{2}w_{2} + \lambda_{1}\mu_{3}w_{3} + \lambda_{2}\mu_{4}w_{1} + \lambda_{2}\mu_{5}w_{2} + \lambda_{2}\mu_{6}w_{3}$$
e, raccogliendo $w_{1}, w_{2}, w_{3}$ otteniamo
$$f(v) = (\lambda_{1}\mu_{1} + \lambda_{2}\mu_{4})w_{1} + (\lambda_{1}\mu_{2} + \lambda_{2}\mu_{5})w_{2} + (\lambda_{1}\mu_{3} + \lambda_{2}\mu_{6})w_{3}$$

Ora, le coordinate di $f(v)$ rispetto a $\beta'$ saranno
$$(f(v))_{\beta'} = ((\lambda_{1}\mu_{1} + \lambda_{2}\mu_{4}), (\lambda_{1}\mu_{2} + \lambda_{2}\mu_{5}), (\lambda_{1}\mu_{3} + \lambda_{2}\mu_{6}))$$
Se noi raccogliamo le coordinate di $v$ rispetto a $\beta$, ovvero $\lambda_{1}, \lambda_{2}$, possiamo riscrivere queste coordinate come
$$(f(v))_{\beta'} = \begin{pmatrix} \mu_{1} & \mu_{4} \\ \mu_{2} & \mu_{5} \\ \mu_{3} & \mu_{6} \end{pmatrix} \cdot \begin{pmatrix} \lambda_{1} \\ \lambda_{2} \end{pmatrix} = A_{\beta\beta'} \cdot (v)_{\beta}$$
e infatti $A_{\beta\beta'}$ si può definire come
$$A_{\beta\beta'} = ((f(v_{1}))_{\beta'}, (f(v_{2}))_{\beta'})$$
Allora questa matrice esiste.

**Qed**.

## Proposizioni
### Composizione di applicazioni lineari
> Siano $f: V \to W$ e $g: W \to Z$ applicazioni lineari, e $\beta, \beta', \mu$ basi ordinate di $V, W, Z$ tali che possiamo definire le seguenti matrici associate a $f$ e a $g$ come
> - $A_{\beta\beta'} = M_{\beta}^{\beta'} (f)$
> - $B_{\beta'\mu} = M_{\beta'}^{\mu} (g)$
> 
> allora si può definire la matrice associata a $g \circ f$ come
>$$C_{\beta\mu} = M_{\beta}^{\mu} (g \circ f)$$
>per cui $C_{\beta\mu} = B_{\beta'\mu} \cdot A_{\beta\beta'}$.

<u>Nota bene</u>: questo non è altro che il risultato generalizzato di [[composizione-di-applicazioni-lineari-matrice-associata|questa proposizione]] per basi non per forza canoniche.

### Inversa di un'identità
> Fissata una base $\beta$ di $V$ e $c$ base canonica di $V$ si ha che
> $$I_{c \beta} = I_{\beta c}^{-1}$$

### Calcolo delle coordinate alternativo
> Preso un vettore $v \in V$ e una base ordinata $\beta$ di $V$, si ha che
> $$(v)_{\beta} = I_{\beta c}^{-1} \cdot (v)_{c}$$
> dove $I_{\beta c}^{-1}$ è la matrice identità da $\beta$ a $c$ (base canonica) inversa e $(v)_{c}$ sono le coordinate di $v$ rispetto alla base canonica $c$. Questo segue dal fatto che $(id(v))_{\beta} = M_{c}^{\beta}(id) \cdot (v)_{c}$ e $M_{c}^{\beta}(id) = I_{\beta c}^{-1}$.

<u>Nota bene</u>: noi sappiamo come calcolare le coordinate di un vettore rispetto a una base, ovvero risolvendo il sistema lineare associato. Ma la fatica è la stessa di calcolare l'inversa, e _questo metodo è utile nel momento in cui si devono calcolare tanti vettori rispetto a una base_, infatti in quel caso non ha senso fare tanti sistemi lineari, conviene calcolarsi una volta l'inversa e fare tot. prodotti righe per colonna.

## Formula per il cambio di base
### Esempio introduttivo
Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ un'applicazione lineare definita come $f = id_{\mathbb{R}^{n}}$, ovvero l'identità, allora sappiamo che la matrice associata ad $f$ rispetto a $c$ base canonica di $\mathbb{R}^{n}$ è
$$A_{cc} = \begin{pmatrix} 1 & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & 1 \end{pmatrix}$$
ovvero proprio la [[matrice-identita|matrice identità]].

Fissiamo ora una base ordinata $\beta = \{v_{1}, \cdots, v_{n}\}$ di $\mathbb{R}^{n}$, e vogliamo ottenere:
- $A_{\beta c}$
- $A_{\beta\beta}$
- $A_{c \beta}$

In particolare prendiamo l'esempio per $n = 2$ e $\beta = \{e_{1}-e_{2}, 2e_{1}+3e_{2}\}$.

#### $A_{\beta c}$
Questa matrice è facile da ottenere. Infatti se sappiamo che $A$ è della forma
$$A = ((f(v_{1}))_{c}, \cdots, (f(v_{n}))_{c})$$
allora essendo le coordinate di un qualunque vettore rispetto alla base canonica esattamente quel vettore, otteniamo che
$$A_{\beta c} = (f(v_{1}), f(v_2))$$
ed essendo $f = id$ si ha
$$A_{\beta c} = (v_{1}, v_{2})$$
per cui
$$A_{\beta c} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}$$

#### $A_{\beta\beta}$
In quest'altro caso, invece, dobbiamo scrivere le coordinate di $f(v_{1}), f(v_{2})$ rispetto a $\beta$, ovvero proprio a $\{v_{1}, v_{2}\}$! Infatti il risultato è
$$A_{\beta\beta} = ((f(v_{1}))_{\beta}, (f(v_{2}))_{\beta})$$
ovvero
$$A_{\beta\beta} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$
<u>Nota bene</u>: è l'identità, di fatto _se la base è la stessa nel dominio e nel codominio viene sempre la matrice identica_ (non solo quando si ha la base canonica).

#### $A_{c \beta}$
Questo è invece il caso più "difficile"... Ci viene infatti richiesto
$$A_{c \beta} = ((f(e_{1}))_{\beta}, (f(e_{2}))_{\beta})$$
e di trovare quindi le coordinate di $f(e_{1}), f(e_{2})$ rispetto alla base $\beta$. Questo richiede di risolvere 2 sistemi lineari, o per un caso di spazio di ordine $n$, $n$ sistemi.

Per fare prima usiamo un trucco: le _composizioni_. Guardiamo il seguente schema
![[Drawing 2024-04-15 19.55.35.excalidraw|750]]
Si tratta di una relazione di composizioni che si può riassumere nella seguente formula
$$A_{\beta\beta} = A_{c \beta} \cdot A_{\beta c}$$
Se ci pensiamo, infatti, queste matrici $A$ sono associate a delle applicazioni lineari da $\mathbb{R}^{n}$ a $\mathbb{R}^{n}$, e sappiamo dalla teoria che la composizione tra due funzioni $g \circ f$ per cui $f = L_{A}$ e $g = L_{B}$ si può scrivere come $g \circ f = L_{BA}$.

Ora che abbiamo questa relazione, sapendo che $A_{\beta\beta} = I$ dove $I$ è la matrice identità, immediatamente ricaviamo che $A_{c \beta}$ non è che l'[[matrice-invertibile|inversa]] di $A_{\beta c}$.

Ci calcoliamo l'inversa di $A_{\beta c}$ usando allora il metodo standard che usa l'[[algoritmo-di-gauss|algoritmo di Gauss]] e otteniamo proprio $A_{c \beta}$.

### Formula
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{m}$ lineare, e $A_{cc'} = M_{c}^{c'}(f)$ la matrice associata ad $f$ sulle basi canoniche di dominio e codominio. Fissiamo $\beta$ base ordinata di $\mathbb{R}^{n}$ e $\beta'$ base ordinata di $\mathbb{R}^{m}$, allora si ha che
> $$A_{\beta\beta'} = I_{c'\beta'} \cdot A_{cc'} \cdot I_{\beta c} = I_{\beta'c'}^{-1} \cdot A_{cc'} \cdot I_{\beta c}$$

Si guardi infatti il seguente schema
![[Drawing 2024-04-15 20.17.55.excalidraw|750]]
Fondamentalmente se noi a $A_{cc'}$ ci aggiungiamo due funzioni identità tra le due basi $\beta$ e $\beta'$ in modo da ottenere una $I_{\beta c}$ e una $I_{c'\beta'}$, possiamo scrivere $L_{A_{\beta\beta'}}$ come la composizione di 3 funzioni, e quindi $A_{\beta\beta'}$ come la moltiplicazione di 3 matrici[^1].

### Esercizio
Determinare se possibile un'applicazione lineare $f: \mathbb{R}^{3} \to \mathbb{R}^{3}$ tale che:
- $\ker(f) = \langle e_{1}+e_{2}+2e_{3} \rangle = \langle (1, 1, 2) \rangle$
- $\Im(f) = \langle e_{1}-e_{2}, e_{2}+7e_{3} \rangle = \langle (1, -1, 0), (0, 1, 7) \rangle$

quindi scrivere la matrice associata ad $f$ _rispetto alla base canonica_.

Per prima cosa controlliamo la compatibilità con il [[teorema-della-dimensione|teorema della dimensione]]:
$$3 = \dim(\ker(f)) + \dim(\Im(f)) = 1 + 2$$

Ora per costruire $f$ sfruttiamo i vincoli imposti su $\ker$ e $\Im$. Sappiamo infatti che $f(1, 1, 2) = \underline{0}$, allora ci creiamo una base di $\mathbb{R}^{3}$ che contenga proprio $(1, 1, 2)$, perché _sappiamo dove è mappato_. Per esempio prendiamo come base
$$\beta = \{(1, 1, 2), (0, 1, 0), (0, 0, 1)\} = \{v_{1}, v_{2}, v_{3}\}$$

, che sappiamo essere base dal [[teorema-gel|teorema GEL]] e Gauss. Quindi imponiamo le immagini dei vettori della base in modo da far coincidere gli altri due vettori $(0, 1, 0), (0, 0, 1)$ con i vettori che generano l'immagine (da vincolo), ovvero
- $f(1, 1, 2) = (0, 0, 0)$ --> così rispetta il $\ker$
- $f(0, 1, 0) = (1, -1, 0)$ --> così rispetta l'$\Im$
- $f(0, 0, 1) = (0, 1, 7)$ --> così rispetta l'$\Im$

Ora, dal [[teorema-di-esistenza-e-unicita-di-un-applicazione-lineare|teorema di esistenza e unicità di un'applicazione lineare]] sappiamo che questa _$f$ esiste ed è unica_.

<u>Osservazione</u>: sappiamo che $\langle (1, 1, 2) \rangle \leq \ker(f)$, e questo non ci dice che il nucleo è proprio uguale. Tuttavia, per il teorema della dimensione si ha che $\dim(\ker(f)) = 1$ perciò per forza si avrà $\langle (1, 1, 2) \rangle = \ker(f)$, rispettando così il vincolo imposto.

Per scrivere la matrice associata a $f$ rispetto alla base canonica, partiamo con la scrittura rispetto alla base $\beta$ nel dominio, e $c$ (canonica) nel codominio, ovvero
$$A_{\beta c} = ((f(v_{1}))_{c}, (f(v_{2}))_{c}, (f(v_{3}))_{c}) = \begin{pmatrix} 0 & 1 & 0 \\ 0 & -1 & 1 \\ 0 & 0 & 7 \end{pmatrix}$$

Noi vogliamo $A_{cc}$. Quindi, dal seguente schema
![[Drawing 2024-04-17 22.05.53.excalidraw|750]]
ricaviamo che
$$A_{cc} = A_{\beta c} \cdot I_{c \beta} = A_{\beta c} \cdot I_{\beta c}^{-1}$$

Quindi per calcolare $A_{cc}$ non ci resta che trovare $I_{\beta c}^{-1}$. Intanto calcoliamo $I_{\beta c}$, mettendo semplicemente per colonna i vettori della base $\beta$, per cui
$$I_{\beta c} = \begin{pmatrix} 1 & 0 & 0 \\ 1 & 1 & 0 \\ 2 & 0 & 1 \end{pmatrix}$$

Ci calcoliamo l'inversa tramite Gauss e otteniamo
$$I_{\beta c}^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ -1 & 1 & 0 \\ -2 & 0 & 1 \end{pmatrix}$$

Ora, con il prodotto righe $\times$ colonne $A_{\beta c} \cdot I_{\beta c}^{-1}$, otteniamo $A_{cc}$.

#### Metodo alternativo
Un metodo più veloce per trovare $f$ consiste nel sfruttare la sua linearità. Se infatti sappiamo che $f(1, 1, 2) = f(e_{1} + e_{2} + 2e_{3}) = f(e_{1}) + f(e_{2}) + 2f(e_{3}) = \underline{0}$, allora possiamo scrivere $f(e_{1})$ in funzione di $f(e_{2})$ e $f(e_{3})$, nel seguente modo:
$$f(e_{1}) = -f(e_{2}) - 2f(e_{3})$$

Per cui "mandiamo" $f(e_{2})$ e $f(e_{3})$ rispettivamente in $(1, -1, 0), (0, 1, 7)$, così da rispettare il vincolo dell'immagine, e poi calcoliamo di conseguenza $f(e_{1})$ sfruttando la relazione sopra riportata.

## Referenze
[^1]: sempre ricordando l'ordine di composizione, da destra a sinistra