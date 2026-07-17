---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 01-03-2024 16:07:15
links:
  - "[[lecture-28022024091940|Lecture 28022024091940]]"
---
# Sottospazi vettoriali di R2
---
## Introduzione
I [[sottospazio-vettoriale|sottospazi]] dello [[spazio-vettoriale|spazio vettoriale]] $\mathbb{R}^{2}$ possono essere solo e unicamente 3. Prendiamo infatti $U \leq \mathbb{R}^{2}$, allora si può avere:
- $U = \{\underline{0}\} = \{(0, 0)\}$
- $U \neq \{\underline{0}\} : \exists! u \in U : u \neq \underline{0}$, ovvero che $U$ contiene un solo vettore "di partenza" $u$ e di conseguenza, per la chiusura del prodotto, tutti i prodotti di $u$ per uno scalare $\lambda \in \mathbb{R}$, perciò infiniti
- $U \neq \{\underline{0}\}: \exists u \in U : u \neq \underline{0}$, ovvero che $U$ contiene almeno due vettori "di partenza" $u$ e $v$, da cui però è possibile generare, per la chiusura della somma e del prodotto, una serie di infiniti altri vettori

L'idea allora è: non appena c'è un vettore, c'è una retta; e non appena ci sono due rette, c'è tutto il piano! Infatti, in definitiva si ha:
1. $U = \{\underline{0}\}$ --> il sottospazio banale
2. $U = \{(\lambda_{1}u, \lambda_{2}u, \lambda_{3}u, \cdots)\}$ --> una retta passante per l'origine
3. $U = \mathbb{R}^{2}$ --> l'intero piano

Per dimostrare quest'ultimo caso è sufficiente prendere un punto qualsiasi $p \in \mathbb{R}^{2}$, tracciare le parallele delle rette fissate da $u$ e $v$ (unici vettori di $U$) e passanti per $p$, e quindi ottenere che il punto $p$ è la somma di un certo $\lambda u$ e un certo $\mu v$.
![[Drawing 2024-03-02 15.36.35.excalidraw|750]]

### Corollario
> Preso lo spazio vettoriale $V = \mathbb{R}^{2} = \{(x, y) | x, y \in \mathbb{R}\}$ ne è sottospazio $S = \{(x, ax) | x \in \mathbb{R}\}$ (con $a$ fissato), ovvero **le rette passanti per le origini sono tutte sottospazi di $\mathbb{R}^{2}$**, mentre _le altre no_ (non verificano $(0, 0) \in S$).

<u>Nota bene</u>: quello che stiamo facendo è di _capire qual è il [[sottospazio-generato|sottospazio generato]] a partire da certi vettori di $\mathbb{R}^{2}$_!

## Esempio
Fissati $v_{1}, v_{2} \in \mathbb{R}^{2}$, il più piccolo sottospazio $z$ che li contiene è:
- $z = \{\underline{0}\} \iff v_{1} = v_{2} = \underline{0}$
- $z = r \iff v_{1}, v_{2}$ appartengono alla stessa retta $r$ (passante per l'origine)
- $z = \mathbb{R}^{2}$ altrimenti

## Referenze