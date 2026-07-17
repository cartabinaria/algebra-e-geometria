---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 20-02-2024 19:34:43
links:
  - "[[lecture-20022024091619|Lecture 20022024091619]]"
  - "[[lecture-21022024091849|Lecture 21022024091849]]"
  - "[[lecture-27022024091857|Lecture 27022024091857]]"
---
# Sistema lineare
---
## Introduzione
> Un **sistema lineare** di $n$ [[equazione-lineare|equazioni lineari]] in $n$ incognite è un _[[insieme|insieme]] di equazioni che devono essere tutte verificate contemporaneamente_. Come per le equazioni lineari, la soluzione di un sistema lineare è una $n$-upla ordinata $(c_{1}, c_{2}, ..., c_{n})$ di numeri reali che sostituiti alle incognite rendono vere l'equazioni.

### Esempio
Un esempio di sistema lineare può essere
$$\begin{cases} 3x_{1} - 2x_{2} = 1 \\ x_{1} + x_{2} = 7 \end{cases}$$
per il quale una soluzione possibile è $(3, 4)$.

## Rapporto con [[matrice|matrici]]
Un qualunque sistema lineare può essere rappresentato attraverso una matrice, nel seguente modo. Supponendo di avere un sistema del tipo
$$\begin{cases} a_{11}x_{1} + a_{12}x_{2} + a_{13}x_{3} = b_{1} \\ a_{21}x_{1} + a_{22}x_{2} + a_{23}x_{3} = b_{2} \\ a_{31}x_{1} + a_{32}x_{2} + a_{33}x_{3} = b_{3} \end{cases}$$
possiamo scrivere la parte a sinistra e a destra dell'uguale come due [[vettore|vettori]], nel seguente modo
$$\begin{pmatrix} a_{11}x_{1} + a_{12}x_{2} + a_{13}x_{3} \\ a_{21}x_{1} + a_{22}x_{2} + a_{23}x_{3} \\ a_{31}x_{1} + a_{32}x_{2} + a_{33}x_{3} \end{pmatrix} = \begin{pmatrix} b_{1} \\ b_{2} \\ b_{3} \end{pmatrix}$$

A sua volta, il vettore di sinistra, può essere visto come il risultato di un [[matrice-prodotto|prodotto matriciale]] del tipo
$$\begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix} \cdot \begin{pmatrix} x_{1} \\ x_{2} \\ x_{3} \end{pmatrix} = \begin{pmatrix} b_{1} \\ b_{2} \\ b_{3} \end{pmatrix}$$
condensato nella formula:
$$A\underline{x} = \underline{b}$$
dove:
- $A$ è la _matrice dei coefficienti_, anche detta "_incompleta_"
- $\underline{x}$ è il _vettore delle incognite_
- $\underline{b}$ è il _vettore_ (o la colonna) _dei termini noti_

Da questa possiamo ricavare la **matrice completa**, ovvero la matrice dei coefficienti a cui è stata aggiunta la colonna dei termini noti, della forma
$$(A|\underline{b}) = \left( \begin{matrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{matrix} \left| \begin{matrix} b_{1} \\ b_{2} \\ b_{3} \end{matrix} \right. \right)$$

Il motivo per cui ci è utile trascrivere un sistema lineare nella sua matrice completa associata è perché, attraverso opportune analisi, si è in grado di risolvere con facilità il sistema.

### Risoluzione
> Un sistema lineare associato a una matrice completa **[[matrice-a-scala|a scala]]** è facilmente risolvibile attraverso _sostituzioni successive partendo dal basso_.

In particolare si distinguono 3 casistiche che consentono di _classificare le soluzioni di un sistema lineare a partire dalla matrice completa associata a scala_.

> Fissato un sistema lineare $A\underline{x} = \underline{b}$ a scala di $n$ incognite, allora
> - $rr(A) \neq rr(A|\underline{b}) \implies \text{sistema impossibile}$;
> - $rr(A) = rr(A|\underline{b}) = n \implies \text{sistema ha 1 sola soluzione}$;
> - $rr(A) = rr(A|\underline{b}) = k < n \implies \text{sistema ha infinite soluzioni dipendenti da } n-k \text{ variabili libere}$;
> 
> dove $rr()$ è il [[rango-righe|rango righe]].

Nel primo caso, infatti, confrontando la matrice incompleta con quella completa, se il numero di righe non nulle delle due non coincide, significa che _tra le ultime righe si ha un'equazione lineare falsa_ (del tipo $0=4$);

Nel secondo caso, invece, se il rango righe delle due matrici coincide ed è anche uguale al numero delle incognite allora significa che _esiste una e una sola $n$-upla soluzione_;

Nel terzo caso, infine, si ha che i ranghi righe coincidono ma sono meno delle incognite, e ciò significa che il _sistema ha infinite soluzioni che dipendono da $n-k$ parametri_. In quest'ultimo caso il consiglio è quello di _ricavare le $k$ incognite corrispondenti ai pivot, e di lasciare arbitrarie le restanti $n-k$ incognite_.

### Strategia
Non tutti i sistemi lineari sono a scala (hanno matrice completa associata in forma a scala), ma ogni matrice, attraverso opportune sequenze di operazioni elementari, può essere trasformata a scala. _La serie di passi di [[operazioni-elementari|operazioni elementari]] che porta a trasformare un sistema lineare in uno [[sistemi-equivalenti|equivalente]] a scala prende il nome di [[algoritmo-di-gauss|algoritmo di Gauss]]_.

## Tipologie
- [[sistema-lineare-omogeneo|Sistema lineare omogeneo]]

## Referenze