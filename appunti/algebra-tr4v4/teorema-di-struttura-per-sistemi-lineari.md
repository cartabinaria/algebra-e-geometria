---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 31-03-2024 12:34:46
links:
  - "[[lecture-27032024091734|Lecture 27032024091734]]"
---
# Teorema di struttura per sistemi lineari
---
## Introduzione
> Il **teorema di struttura per sistemi lineari** ci dice che considerato $Ax = b$ un [[sistema-lineare|sistema lineare]] di $m$ equazioni in $n$ incognite ove $A \in M_{m \times n}$ che ammette almeno una soluzione[^1], allora l'insieme delle soluzioni del sistema può essere scritto come
> $$S = \{v + z | Az = \underline{0}\} = \{v + z | z \in \ker(L_{A})\}$$
> ovvero come le soluzioni del [[nucleo|nucleo]] dell'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]] $L_{A}$ traslate di $v$, ove $v$ è una soluzione particolare del sistema.

## Dimostrazione
La dimostrazione richiede, in realtà, di unire alcune proprietà della [[controimmagine|controimmagine]] di un'applicazione $f$. In particolare sappiamo dalla [[controimmagine-soluzione-di-un-sistema-lineare|1° proposizione]] che la controimmagine può essere scritta come
$$f^{-1}(w) = \{v \in V | Av = w\} = L_{A}^{-1}(w)$$
ovvero come l'insieme di soluzioni di un sistema lineare $Av = w$.

E dalla [[controimmagine-traslazione|2° proposizione]] si ha che la controimmagine può essere scritta nella seguente forma:
$$f^{-1}(w) = \{v + z | z \in \ker(f)\}$$

Per cui unendo le due proposizioni si ottiene che le soluzioni di un sistema lineare del tipo $Av = w$ si possono scrivere come
$$S = f^{-1}(w) = L^{-1}_{A}(w) = \{v + z | z \in \ker(L_{A})\}$$
dove $v$ è una soluzione del sistema perché infatti $v \in f^{-1}(w)$ (in quanto $f(v) = w$).

**Qed**.

## Conseguenze
Sulla falsa riga della [[controimmagine-soluzione-di-un-sistema-lineare|proposizione sorella]] (sempre la 1° sulla controimmagine), questo teorema ci dice che **le soluzioni di un sistema lineare $Ax = b$ non sono altro che la soluzione del sistema lineare omogeneo $Ax = \underline{0}$ (il nucleo di $L_{A}$) traslate di una soluzione $v$**!

## Referenze
[^1]: $rr(A) = rr(A|b)$