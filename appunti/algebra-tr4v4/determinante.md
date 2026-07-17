---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 07-04-2024 17:27:01
links:
  - "[[lecture-04042024112239|Lecture 04042024112239]]"
  - "[[lecture-09042024091802|Lecture 09042024091802]]"
---
# Determinante
---
## Introduzione
> Il **determinante** di una [[matrice|matrice]] quadrata $A \in M_{n} (\mathbb{R})$ è una [[funzione-matematica|funzione]] $\det: M_{n} (\mathbb{R}) \to \mathbb{R}$ definita come $A \to \det(A)$ tale che:
> 1. _presa una riga $j$ di $A$ e scomposto tale [[vettore|vettore]] come somma di altri due vettori $u, v$, allora $\det(A)$ è la somma dei determinanti delle due matrici ottenute sostituendo alla riga $j$ rispettivamente $u$ e $v$_;
> 2. _presa una riga $j$ di $A$ e scomposto tale vettore come il prodotto $\lambda u$, allora $\det(A)$ è il prodotto tra $\lambda$ e il determinante della matrice ottenuta sostituendo alla riga $j$ il vettore $u$_;
> 3. _se due righe di $A$ sono uguali allora $\det(A) = 0$_;
> 4. _$\det(I) = 1$ dove $I$ è la [[matrice-identita|matrice identità]]_.
> 
> <u>Nota bene</u>: non viene definita una formula, ma solo dei criteri che la funzione $\det$ deve rispettare!

E' importante tenere in considerazione che si dimostra come **una funzione che soddisfi queste 4 proprietà esiste ed è unica**, per cui è possibile studiarla.

### Importanza
Determinare il determinante di una matrice quadrata è utile a studiarne l'[[matrice-invertibile|invertibilità]] e il comportamento dell'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare associata]] $L_{A}$.

Di fatto si ha che
$$A \text{ invertibile} \iff \det(A) \neq 0$$
e che $\det(A)$ dove $A$ è la matrice associata $\in M_{n}(\mathbb{R})$ a $L_{A}: \mathbb{R}^{n} \to \mathbb{R}^{n}$ ci dice come cambiano le aree ($\mathbb{R}^{2}$), i volumi ($\mathbb{R}^{3}$) o gli iper-spazi ($\mathbb{R}^{n>3}$) quando si applica $L_{A}$: funge un po' da [[derivata|derivata]] di $L_{A}$.

## Corollario
Inchiodata una funzione che soddisfi il [[prototipo-vs-implementazione|prototipo]] di determinante, si derivano le seguenti conseguenze:
1. _se $B$ si ottiene da $A$ scambiando due righe allora $$\det(A) = -\det(B)$$_;
2. _se $B$ si ottiene da $A$ sommando a una riga di $A$ una qualunque combinazione lineare delle altre righe allora $$\det(A) = \det(B)$$_;
3. _se $A$ è una [[matrice-triangolare|matrice triangolare]] superiore (o inferiore) allora $\det(A)$ è il prodotto degli elementi che si trovano sulla sua diagonale principale_;

Con queste 3 nuove regole, e con la 2° legge del determinante, **riusciamo a determinare il determinante di qualunque matrice usando semplicemente l'[[algoritmo-di-gauss|algoritmo di Gauss]]**! Infatti le operazioni di _scambio di righe_, _moltiplicazione per scalare_ e _somma di combinazione lineare_ non sono altro che le [[operazioni-elementari|operazioni elementari]]. Per cui fondamentalmente riducendo [[matrice-a-scala|a scala]] una qualunque matrice, e seguendo i passi del valore del determinante associato a tale matrice, possiamo sempre ricavare il suo determinante, **senza usare alcuna formula**.

## Calcolo
Proprio da quest'ultima osservazione si ottiene un _calcolo metodico del determinante di una matrice basato sull'algoritmo di Gauss_.

### $2 \times 2$
Presa infatti una generica matrice $A \in M_{2}(\mathbb{R})$ definita come
$$A = \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}$$
la vogliamo ridurre a scala. Perciò ci basta avere $0$ al posto di $a_{21}$. Applichiamo Gauss e otteniamo
$$A = \begin{pmatrix} a_{11} & a_{12} \\ 0 & a_{22} - \frac{a_{21}}{a_{11}}a_{12} \end{pmatrix}$$
Ora sappiamo che è a scala, perciò è triangolare superiore: per la 3° conseguenza delle proprietà del determinante sappiamo che $\det(A)$ non è altro che il prodotto degli elementi che si trovano sulla diagonale principale, ovvero
$$\det(A) = a_{11} \cdot \left(a_{22} - \frac{a_{21}}{a_{11}}a_{12}\right) = a_{11}a_{22} - a_{12}a_{21}$$
il che ci porta a concludere che il determinante di una qualunque matrice $2 \times 2$ è
$$\det(A) = a_{11}a_{22} - a_{12}a_{21}$$

### $3 \times 3$
Usando lo stesso ragionamento del caso $2 \times 2$ si ottiene che il determinante di una qualunque matrice $3 \times 3$ è
$$\det(A) = a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31} - a_{12}a_{21}a_{33} - a_{11}a_{23}a_{32}$$

che si può ricordare facilmente usando la [[regola-di-sarrus|regola di Sarrus]].

### Formule
Nonostante il metodo con Gauss funzioni sempre, per matrici di ordine superiore al 3 viene preferita la formula derivante dal [[teorema-di-laplace|teorema di Laplace]].

## Teoremi
- [[teorema-di-binet|Teorema di Binet]]

## Proposizioni
### Trasposta
Le proprietà del determinante sulle righe valgono anche per le colonne[^1], per cui vale che
$$\det(A) = \det(A^{T})$$
ovvero che $A$ e la sua [[matrice-trasposizione|trasposta]] hanno lo stesso determinante.

### Invertibilità di una matrice
> Sia $A \in M_{n}(\mathbb{R})$, allora si ha che
> $$A \text{ invertibile} \iff \det(A) \neq 0$$

#### Dimostrazione
Primo verso dell'[[implicazione|implicazione]]: supponiamo che $A$ sia invertibile, allora per ipotesi si ha che
$$\exists B \in M_{n}(\mathbb{R}): AB = BA = I_{n}$$

Per il teorema di Binet sappiamo che
$$\det(AB) = \det(A)\det(B)$$
ma essendo $AB = I$, allora $\det(AB) = \det(I) = 1$, per cui
$$1 = \det(A)\det(B)$$
il che ci porta a concludere che per forza
$$\det(A) \neq 0$$

Secondo verso dell'implicazione: supponiamo $\det(A) \neq 0$, allora per un teorema che non dimostriamo possiamo scrivere l'inversa di $A = A^{-1} = B = (b_{ij})$ come
$$b_{ij} = \frac{1}{\det(A)}\Gamma_{ji} = \frac{1}{\det(A)} (-1)^{i+j} \det(A_{ji})$$

ed essendo $\det(A) \neq 0$ questa inversa esiste.

**Qed**.

### Invertibilità di una funzione
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ un'[[applicazione-lineare|applicazione lineare]], e sia $A$ la matrice associata a $f$ rispetto alla [[base-canonica|base canonica]] di $\mathbb{R}^{n}$ ($f = L_{A}$), allora si ha che
> $$f \text{ invertibile} \iff \det(A) \neq 0$$
> e che _l'[[funzione-inversa|inversa]] di $f$ ($f^{-1}$) è l'applicazione lineare associata ad $A^{-1}$_.

#### Dimostrazione
##### $\implies$
Sia $f$ invertibile e quindi $g$ la sua inversa. Sia $B$ la matrice associata a $g$ ($g = L_{B}$), allora non ci resta che mostrare che $B = A^{-1}$, perché questo implica $\det(A) \neq 0$ per la proposizione precedente.

Sappiamo che
$$g \circ f = id$$
che per la [[composizione-di-applicazioni-lineari|composizione di applicazioni lineari]] equivale a dire
$$g(f(\underline{x})) = (BA)\underline{x} = \underline{x}$$
il che implica che
$$BA = I$$

Ma sappiamo per ipotesi che anche
$$f \circ g = id$$
il che per lo stesso ragionamento di prima implica
$$AB = I$$

<u>Nota bene</u>: i due $id$ sono uguali perché $f$ va da $\mathbb{R}^{n}$ a $\mathbb{R}^{n}$.

Avendo
$$AB = BA = I$$
concludiamo per la definizione di matrice inversa che
$$B = A^{-1}$$
il che a sua volta implica
$$\det(A) \neq 0$$

<u>Osservazione</u>: per dimostrare che $B = A^{-1}$ si potrebbe semplicemente dimostrare $AB = I$, senza verificare anche $BA = I$. Per Binet, infatti se per ipotesi vale $AB = I$, allora $1 = \det(I) = \det(AB) = \det(A)\det(B)$, il che implica $\det(A) \neq 0$, perciò $A$ è invertibile; allora fissata $A^{-1}$ come l'inversa di $A$, abbiamo la seguente equivalenza:
$$AB = I \implies A^{-1}AB = A^{-1}I \implies IB = A^{-1} \implies B = A^{-1} \implies AB = BA = I$$

##### $\impliedby$
Assumiamo $\det(A) \neq 0$, perciò $\exists B = A^{-1}$. Ora sia $g = L_{B}$, ovvero l'applicazione lineare definita da questa $B$. Dobbiamo mostrare che $g \circ f = f \circ g = id$.
Sappiamo che la matrice associata a $g \circ f$ è
$$BA = A^{-1}A = I$$
il che implica che
$$g \circ f = id$$
Sappiamo anche, analogamente, che la matrice associata a $f \circ g$ è
$$AB = AA^{-1} = I$$
per cui
$$f \circ g = id$$
e allora
$$g \circ f = f \circ g = id$$

**Qed**.

### Teoremone
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{n}$ e sia $A$ la matrice associata ad $f$, allora le seguenti proposizioni sono equivalenti:
> 1. $f$ è invertibile
> 2. $f$ è iniettiva
> 3. $f$ è suriettiva
> 4. $\dim(\Im(f)) = n$
> 5. $rk(A) = n$
> 6. le colonne di $A$ sono linearmente indipendenti
> 7. le righe di $A$ sono linearmente indipendenti
> 8. il sistema $A\underline{x} = \underline{0}$ ha un'unica soluzione
> 9. il sistema $A\underline{x} = b$ ha una sola soluzione $\forall b \in \mathbb{R}^{n}$ (dalla definizione di controimmagine)
> 10. $A$ è invertibile
> 11. $\det(A) \neq 0$

Questo ci è utilissimo: _se ci viene chiesto per esempio se una $f$ è iniettiva possiamo semplicemente calcolare il determinante della matrice associata e vedere se è diverso da 0_.

## Referenze
[^1]: proprietà che si ripercuote proprio sul [[teorema-di-laplace|teorema di Laplace]]