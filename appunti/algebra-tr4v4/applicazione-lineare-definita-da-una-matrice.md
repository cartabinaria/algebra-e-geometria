---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-03-2024 16:50:54
links:
  - "[[lecture-12032024091825|Lecture 12032024091825]]"
  - "[[lecture-14032024111404|Lecture 14032024111404]]"
---
# Applicazione lineare definita da una matrice
---
## Introduzione
> Data una [[matrice|matrice]] $A \in M_{m \times n} (\mathbb{R})$ si ha che la funzione $L_{A}: \mathbb{R}^{n} \to \mathbb{R}^{m}$ definita come
> $$(x_{1}, \cdots, x_{n}) \to A \cdot \begin{pmatrix} x_{1} \\ \vdots \\ x_{n} \end{pmatrix}$$
> che _mappa un vettore di $n$ elementi con il vettore di $m$ elementi come risultato del prodotto riga $\times$ colonna_ (tutti i [[prodotto-scalare|prodotti scalari]]) _tra il vettore in input e la matrice $A$_, è un'[[applicazione-lineare|applicazione lineare]].

L'applicazione $L_{A}$ è fondamentale per il teorema sottostante.

## Teorema
> E' possibile rappresentare qualunque altra funzione lineare $\mathbb{R}^{n} \to \mathbb{R}^{m}$ come $L_{A}$. Pertanto, per il [[teorema-di-esistenza-e-unicita-di-un-applicazione-lineare|teorema dell'esistenza e unicità di un'applicazione lineare]], abbiamo che _tutte le funzioni lineari sono del tipo $L_{A}$ per una certa matrice $A$_:
> $$f: \mathbb{R}^{n} \to \mathbb{R}^{m} \text{ lineare} \implies f = L_{A}$$

Questo è possibile attraverso una **serie di passaggi che da $f$, fissate le basi canoniche di $\mathbb{R}^{n}$ e $\mathbb{R}^{m}$, ci portano per la sua linearità alla forma di una matrice moltiplicata per un vettore, ovvero proprio $L_{A}$**. La dimostrazione è lunga e si tratta solo di raccoglimenti e sostituzioni, l'importante è capire che ogni funzione $\mathbb{R}^{n} \to \mathbb{R}^{m}$ è riconducibile a $L_{A}$.

### Esempio
Prendiamo in esame $f: \mathbb{R}^{3} \to \mathbb{R}^{2}$ definita come $(x_{1}, x_{2}, x_{3}) \to (x_{1}+x_{2}, x_{1}-x_{3})$. Proietto allora una base di $\mathbb{R}^{3}$, per comodità quella canonica $e_{1} = (1, 0, 0)$, $e_{2} = (0, 1, 0)$ ed $e_{3} = (0, 0, 1)$, su $f$, ottenendo:
- $f(e_{1}) = (1, 1)$
- $f(e_{2}) = (1, 0)$
- $f(e_{3}) = (0, -1)$

Mi creo allora la matrice $A \in M_{2 \times 3} (\mathbb{R})$ cui colonne sono le immagini della base canonica di $\mathbb{R}^{3}$, ovvero
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 1 & 0 & -1 \end{pmatrix}$$
A questo punto mi definisco $L_{A}: \mathbb{R}^{3} \to \mathbb{R}^{2}$ definita proprio come $(x_{1}, x_{2}, x_{3}) \to A \cdot \begin{pmatrix} x_{1} \\ x_{2} \\ x_{3} \end{pmatrix}$. Visto che $L_{A}(e_{1}) = f(e_{1})$, $L_{A}(e_{2}) = f(e_{2})$ e $L_{A}(e_{3}) = f(e_{3})$, per l'unicità dell'applicazione lineare $f$ devo avere
$$f = L_{A}$$

<u>Nota bene</u>: è normale che $L_{A}(e_{i}) = f(e_{i})$, perché abbiamo definito $A$ come matrice di colonne di $f(e_{i})$. Notiamo quindi come $L_{A}$, per le basi canoniche di $\mathbb{R}^{3}$, restituisca le colonne di $A$, per cui la colonna $1$ è immagine di $e_{1}$; la colonna $2$ è immagine di $e_{2}$; ecc...

Come prova del 9, se non ci si fida, si può notare come preso un generico vettore $(x_{1}, x_{2}, x_{3})$ si ha che
$$L_{A} = \begin{pmatrix} 1 & 1 & 0 \\ 1 & 0 & -1 \end{pmatrix} \cdot \begin{pmatrix} x_{1} \\ x_{2} \\ x_{3} \end{pmatrix} = \begin{pmatrix} x_{1}+x_{2} \\ x_{1}-x_{3} \end{pmatrix}$$
ovvero proprio $f(x_{1}, x_{2}, x_{3})$!

Ora che sappiamo $f = L_{A}$, abbiamo trovato un modo per ottenere l'immagine di $f$ con semplicità. Chiedersi quanto vale $f(3, 6, -2)$ equivale a chiedere quanto è $L_{A}(3, 6, -2)$. Infatti:
$$f(3, 6, -2) = (3 + 6, 3 - (-2)) = (9, 5)$$
$$L_{A}(3, 6, -2) = (1 \cdot 3 + 1 \cdot 6 + 0 \cdot -2, 1 \cdot 3 + 0 \cdot 6 + (-1) \cdot (-2)) = (9, 5)$$

In questo caso risulta poco utile usare $L_{A}$, perché conosciamo già tutta $f$. Ma _se conoscessimo il comportamento di $f$ solo per le basi canoniche $e_{1}, e_{2}, e_{3}$, l'unico modo certo per conoscere tutta $f$ sarebbe attraverso $L_{A}$_, sempre per il teorema dell'esistenza e unicità di un'applicazione lineare.

## Referenze