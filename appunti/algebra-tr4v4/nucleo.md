---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 16-03-2024 20:17:39
links:
  - "[[lecture-14032024111404|Lecture 14032024111404]]"
  - "[[lecture-19032024091914|Lecture 19032024091914]]"
---
# Nucleo
---
## Introduzione
> Il **nucleo**, meglio conosciuto sotto il nome di **kernel**, di un'[[applicazione-lineare|applicazione lineare]] $f: V \to W$, è definito come
> $$\ker(f) = \{v \in V | f(v) = \underline{0}\}$$
> ovvero l'_[[insieme|insieme]] di tutti i [[vettore|vettori]] di $V$ cui [[immagine-di-funzione|immagine]] di $f$ è il vettore nullo in $W$_.

![[Drawing 2024-03-17 15.48.45.excalidraw|800]]

## Calcolo
### Esempio
Data una funzione $f: \mathbb{R}^{3} \to \mathbb{R}^{2}$ definita come $(x_{1}, x_{2}, x_{3}) \to (x_{1}+x_{2}, x_{1}-x_{3})$ _lineare_, devo trovare $\ker(f)$. Applico la definizione di kernel su $f$, per cui
$$\ker(f) = \{(x_{1}, x_{2}, x_{3}) | f(x_{1}, x_{2}, x_{3}) = \underline{0}\} = \{(x_{1}, x_{2}, x_{3}) | (x_{1}+x_{2}, x_{1}-x_{3}) = (0, 0)\}$$

Il nucleo, allora, sarà formato da tutte quelle coppie di valori $(x_{1}+x_{2}, x_{1}-x_{3})$ per cui vale $x_{1}+x_{2} = 0$ e $x_{1}-x_{3} = 0$, ovvero a [[sistema-lineare|sistema]]
$$\begin{cases} x_{1}+x_{2} = 0 \\ x_{1}-x_{3} = 0 \end{cases}$$

<u>Nota bene</u>: si tratta di un [[sistema-lineare-omogeneo|sistema lineare omogeneo]], per cui _sicuramente sappiamo che $\ker(f) \neq \varnothing$_, ma questo è triviale per la [[Applicazione lineare#$f text{ lineare} implies f(0_{V}) = 0_{W}$|proposizione]] che per ogni funzione lineare $f$ si deve avere $f(\underline{0}) = \underline{0}$.

Ad ogni modo, risolvendo il sistema ci accorgiamo che i valori dipendono da 1 variabile libera: anche se in questo caso è molto semplice, risolvendo con [[algoritmo-di-gauss|Gauss]] ci verrebbe $rr(A) = 2 = rr(A|\underline{b}) < 3 = \text{ n° incognite}$. Infatti possiamo scrivere le soluzioni come dipendenti da $x_{1}$:
$$\begin{cases} x_{2} = -x_{1} \\ x_{3} = x_{1} \end{cases}$$

da cui otteniamo che
$$\ker(f) = \{(x_{1}, -x_{1}, x_{1}) | x_{1} \in \mathbb{R}\}$$

che fattorizzando per $x_{1}$ ci viene
$$\ker(f) = \{x_{1}(1, -1, 1) | x_{1} \in \mathbb{R}\} = \langle (1, -1, 1) \rangle$$

ovvero il [[sottospazio-generato|sottospazio generato]] dal vettore $(1, -1, 1)$.

<u>Nota bene</u>: _se ci venisse chiesto se $f$ è [[funzione-iniettiva|iniettiva]] risponderemmo di no_, perché $\ker(f) \neq \{\underline{0}\}$.

### Esempio
Mettiamo caso ora di avere un'applicazione lineare $f$ [[applicazione-lineare-definita-da-una-matrice|definita mediante matrice]] $A$:
$$A = \begin{pmatrix} 1 & 3 & 2 & 1 & 1 \\ 2 & 6 & 5 & 3 & 1 \\ 0 & 0 & 4 & 4 & -4\end{pmatrix}$$
Per cui, per il [[teorema-di-esistenza-e-unicita-di-un-applicazione-lineare|teorema di esistenza e unicità di un'applicazione lineare]] si avrà $f = L_{A}$. Il kernel di questa funzione equivale allora a
$$\ker(f) = \{\underline{x} \in \mathbb{R}^{5} | f(\underline{x}) = \underline{0}\} = \{\underline{x} \in \mathbb{R}^{5} | A\underline{x} = \underline{0}\}$$

Allora il nucleo è l'insieme delle soluzioni del sistema lineare omogeneo associato ad $A$ del tipo
$$A \underline{x} = 0$$
In breve il sistema ci porta alla formulazione della seguente matrice:
$$\begin{pmatrix} 1 & 3 & 2 & 1 & 1 & 0 \\ 2 & 6 & 5 & 3 & 1 & 0 \\ 0 & 0 & 4 & 4 &-4 & 0 \end{pmatrix}$$
da cui con [[algoritmo-di-gauss|Gauss]] ricaviamo
$$\begin{pmatrix} 1 & 3 & 2 & 1 & 1 & 0 \\ 0 & 0 & 1 & 1 & -1 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 \end{pmatrix}$$
per cui capiamo che ci sono infinite soluzioni che dipendono da 3 parametri, perché il numero di incognite è 5, il numero di righe non nulle è 2 $\implies 5-2 = 3$. Ricaviamo allora tali soluzioni in funzione dei pivot $x_{1}, x_{3}$, ottenendo
$$\begin{cases} x_{1}+3x_{2}+2x_{3}+x_{4}+x_{5} = 0 \\ x_{3}+x_{4}-x_{5} = 0 \end{cases} \implies S = \{(-3x_{2}+x_{4}-3x_{5}, x_{2}, -x_{4}+x_{5}, x_{4}, x_{5}) | x_{2}, x_{4}, x_{5} \in \mathbb{R}\}$$

Ora, per calcolare $\ker$ raccogliamo le variabili $x_{2}, x_{4}, x_{5}$ e otteniamo un sottospazio generato di $\mathbb{R}^{5}$, del tipo
$$\ker(f) = \{x_{2}(-3, 1, 0, 0, 0) + x_{4}(1, 0, -1, 1, 0) + x_{5}(-3, 0, 1, 0, 1) | x_{2}, x_{4}, x_{5} \in \mathbb{R}\}$$

Questa è la definizione di sottospazio generato, per cui
$$\ker(f) = \langle (-3, 1, 0, 0, 0), (1, 0, -1, 1, 0), (-3, 0, 1, 0, 1) \rangle = \langle v_{1}, v_{2}, v_{3} \rangle$$

che ci portano a concludere che
$$\dim(\ker(f)) = 3$$

<u>Nota bene</u>: **diciamo che le soluzioni di $A \underline{x} = 0$ dipendono da $k = n-r$ parametri, e che il kernel ha proprio dimensione $k$**, e una base $v_{1}, \cdots, v_{k}$ di $\ker$ si ottiene creando ogni vettore $v_{i}$ della base come l'$i$-esimo parametro $= 1$ e gli altri $= 0$. In questo caso, per esempio, potevamo prendere $S = \{(-3x_{2}+x_{4}-3x_{5}, x_{2}, -x_{4}+x_{5}, x_{4}, x_{5}) | x_{2}, x_{4}, x_{5} \in \mathbb{R}\}$ e trovare il risultato per $x_{2} = 1, x_{4} = 0, x_{5} = 0$, che infatti ci veniva $(-3, 1, 0, 0, 0)$; quindi per $x_{2} = 0, x_{4} = 1, x_{5} = 0$, che dà $(1, 0, -1, 1, 0)$; e infine $x_{2} = 0, x_{4} = 0, x_{5} = 1$, che risulta dare $(-3, 0, 1, 0, 1)$.

## Referenze