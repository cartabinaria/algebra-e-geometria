---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 05-05-2024 21:05:51
links:
  - "[[lecture-30042024091716|Lecture 30042024091716]]"
---
# Proiezione ortogonale
---
## Introduzione
> Siano $u, v \in \mathbb{R}^{n}$, allora la **proiezione ortogonale** _di $v$ su $u$_ è data da
> $$proj_{u}(v) = \frac{<v, u>}{<u, u>}u = <v, u> \frac{u}{{||u||^{2}}}$$
> ovvero si definisce come il [[prodotto-scalare|prodotto scalare]] tra $v$ e $u$ diviso la [[norma-euclidea|norma]] al quadrato di $u$, il tutto per $u$.

### Interpretazione
Geometricamente parlando la proiezione ortogonale è relativamente semplice da capire. Consideriamo due vettori $u, v \in \mathbb{R}^{2}$; definiamo la **proiezione ortogonale di $v$ su $u$ quel vettore che punta verso $u$ e che ha magnitudo $v$**.
![[Drawing 2024-05-05 21.13.41.excalidraw|750]]

Si chiarisce tutto usando le [[coordinate-polari|coordinate polari]] dei vettori, sfruttando il fatto che siamo in $\mathbb{R}^{2}$. Infatti se rappresentiamo $<v, u>$ come $||v|| \cdot ||u|| \cdot \cos{\theta}$ e $<u, u>$ come $||u||^{2}$, si ottiene
$$proj_{u}(v) = ||v|| \cdot ||u|| \cdot \cos{\theta} \cdot \frac{u}{||u||^{2}} = ||v|| \cos{\theta} \cdot \frac{u}{||u||}$$

ovvero esattamente il **vettore in direzione $u$** (la direzione è data da $\frac{u}{||u||}$), e **di magnitudo $||v|| \cos{\theta}$, ossia la lunghezza di $v$ per la sua inclinazione rispetto a $u$**.

Ciò che è più importante, però, non è tanto questo nuovo vettore $proj_{u}(v)$, ma bensì $v - proj_{u}(v)$:
![[Drawing 2024-05-05 21.33.46.excalidraw|750]]

Questo vettore, di fatto, è **[[ortogonalita|ortogonale]] a $u$ e misura la distanza dalla punta di $v$**. E cosa più importante: è una [[combinazione-lineare|combinazione lineare]] di $u$ e $v$. Questo è fondamentale per l'applicazione dell'[[algoritmo-di-gram-schmidt|algoritmo di Gram-Schmidt]].

#### Dimostrazione di ortogonalità
Dimostriamo che vale in generale che $v - proj_{u}(v) \bot u$, ovvero che
$$<v - proj_{u}(v), u> = 0 \ \ \forall u, v \in \mathbb{R}^{n}$$

Sviluppo $v - proj_{u}(v)$, ottenendo
$$v - proj_{u}(v) = v - \frac{<v, u>}{<u, u>}u$$

ora reinserisco all'interno del prodotto scalare
$$<v - \frac{<v, u>}{<u, u>}u, u> = 0$$
che per le proprietà dello stesso si traduce in
$$<v, u> - <\frac{<v, u>}{<u, u>}u, u> = 0$$
e quindi ancora in
$$<v, u> - \frac{<v, u>}{<u, u>} <u, u> = 0$$

Quindi
$$<v, u> - <v, u> = 0$$

**Qed**.

## Referenze