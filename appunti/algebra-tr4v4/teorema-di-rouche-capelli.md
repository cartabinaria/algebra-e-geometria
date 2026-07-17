---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 31-03-2024 13:05:42
links:
  - "[[lecture-27032024091734|Lecture 27032024091734]]"
---
# Teorema di Rouché-Capelli
---
## Introduzione
> Il **teorema di Rouché-Capelli** è il risultato più importante nella teoria dei [[sistema-lineare|sistemi lineari]], perché mette in luce il legame tra questi e le [[applicazione-lineare|applicazioni lineari]], e dice che un sistema lineare $A\underline{x} = \underline{b}$ dove $A \in M_{m \times n} (\mathbb{R})$ ha soluzione $\iff$ $rk(A) = rk(A|\underline{b})$[^1]. Se il sistema ha soluzione allora per $rk(A) = rk(A|\underline{b}) = r$ e per $n$ come numero di colonne e quindi di incognite si ha:
> - $r = n \implies$ il sistema ha 1 soluzione;
> - $r < n \implies$ il sistema ha infinite soluzioni che dipendono da $n-r$ parametri.

<u>Nota bene</u>: si tratta di _risultati che avevamo dato per scontato nella risoluzione di sistemi lineari_, e in particolare adottati su una matrice $A$ ridotta a scala con [[algoritmo-di-gauss|Gauss]]. Questo teorema dimostra questa intuizione usando gli strumenti dell'[[algebra-lineare|algebra lineare]] finora studiati.

## Dimostrazione
### 1° parte
Dimostriamo intanto che $A\underline{x} = \underline{b}$ ha soluzione $\iff rk(A) = rk(A|\underline{b})$. Definita $L_{A}: \mathbb{R}^{n} \to \mathbb{R}^{m}$ come l'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita dalla matrice]] $A$, si ha che $L_A(\underline{x}) = A\underline{x}$, e che perciò che la [[controimmagine|controimmagine]] $L^{-1}_{A}(b)$ è esattamente
$$L^{-1}_{A}(b) = \{\underline{x} \in \mathbb{R}^{n} | A\underline{x} = \underline{b}\}$$
ovvero l'insieme delle soluzioni del sistema $A\underline{x} = \underline{b}$. Di fatto si sa da [[controimmagine-soluzione-di-un-sistema-lineare|questa proposizione]] che ogni controimmagine può essere vista come l'insieme delle soluzioni di un sistema lineare.

Otteniamo allora la seguente catena di equivalenze
$$A\underline{x} = \underline{b} \text{ ha soluzione} \iff L_{A}^{-1}(b) \neq \varnothing$$
e
$$L^{-1}_{A}(b) \neq \varnothing \iff b \in \Im(L_{A})$$
che per [[immagine-di-funzione-spazio-generato-dell-immagine|questa proposizione]] per $\Im(L_{A})$ si ha che
$$b \in \Im(L_{A}) \iff b \in \langle c_{1}, \cdots, c_{n} \rangle$$
dove $c_{1}, \cdots, c_{n}$ sono le colonne di $A$ (ovvero $L_{A}(e_{1}), \cdots, L_{A}(e_{n})$). Allora per [[Sottospazio generato#$w in langle v_{1}, cdots, v_{n} rangle iff langle v_{1}, cdots, v_{n} rangle = langle v_{1}, cdots, v_{n}, w rangle$|quest'altra proposizione]] si ha che
$$b \in \langle c_{1}, \cdots, c_{n} \rangle \iff \langle c_{1}, \cdots, c_{n} \rangle = \langle c_{1}, \cdots, c_{n}, b \rangle$$
e avendo che $\langle c_{1}, \cdots, c_{n} \rangle \leq \langle c_{1}, \cdots, c_{n}, b \rangle$ per [[Dimensione#$ dim(W) = dim(V) iff W = V$|quest'altra proposizione ancora]] posso dire che
$$\langle c_{1}, \cdots, c_{n} \rangle = \langle c_{1}, \cdots, c_{n}, b \rangle \iff \dim(\langle c_{1}, \cdots, c_{n} \rangle) = \dim(\langle c_{1}, \cdots, c_{n}, b \rangle)$$

dove sappiamo per costruzione della matrice $A$ che $\dim(\langle c_{1}, \cdots, c_{n} \rangle) = rc(A)$ mentre $\dim(\langle c_{1}, \cdots, c_{n}, b \rangle) = rc(A|\underline{b})$. Per cui si deve avere
$$rc(A) = rc(A|\underline{b})$$
ovvero, per il [[teorema-della-dimensione-righe-e-colonne-di-una-matrice|corollario del teorema della dimensione]] che
$$rk(A) = rk(A|\underline{b})$$

**Qed**.

### 2° parte
Supponendo che il sistema $A\underline{x} = \underline{b}$ abbia soluzione, per cui che $rk(A) = rk(A|\underline{b})$, devo dimostrare che:
- $rk(A) = n \implies$ 1 soluzione;
- $rk(A) < n \implies$ infinite soluzioni dipendenti da $n-rk(A)$ parametri;

#### $rk(A) = n$
Se so che $rk(A) = rc(A) = n$ e che $\Im(L_{A}) = \langle c_{1}, \cdots, c_{n} \rangle$, allora $c_{1}, \cdots, c_{n}$ sono linearmente indipendenti e generano $\Im(L_{A})$: sono base dell'immagine. Allora
$$\dim(\Im(L_{A})) = n$$
Ora, per il [[teorema-della-dimensione|teorema della dimensione]] devo avere
$$\dim(\mathbb{R}^{n}) = \dim(\ker(L_{A})) + \dim(\Im(L_{A})) \iff n = \dim(\ker(L_{A})) + n \iff \dim(\ker(L_{A})) = 0$$

Per cui ho dimostrato che $L_{A}$ è [[funzione-iniettiva|iniettiva]] e [[funzione-suriettiva|suriettiva]], e in particolare che $\dim(\ker(L_{A})) = 0$, ovvero $\ker(L_{A}) = \{(0, \cdots, 0)\}$.

Ora, posso scrivere per il [[teorema-di-struttura-per-sistemi-lineari|teorema di struttura per sistemi lineari]] la soluzione di $A\underline{x} = \underline{b}$ come
$$S = \{v + z | z \in \ker(L_{A})\}$$
dove $v \in L^{-1}_{A}(b)$, e sapendo che $\ker(L_{A}) = \{(0, \cdots, 0)\}$ mi rimane che
$$S = \{v\}$$
per cui ho 1 soluzione.

**Qed**.

#### $rk(A) < n$
Se $rk(A) = rc(A) < n$ e $\Im(L_{A}) = \langle c_{1}, \cdots, c_{n} \rangle$, allora significa $c_{1}, \cdots, c_{n}$ sono linearmente dipendenti e che perciò
$$\dim(\Im(L_{A})) = rc(A) < n$$

Ora, sempre per il teorema della dimensione devo avere
$$\dim(\mathbb{R}^{n}) = \dim(\ker(L_{A})) + \dim(\Im(L_{A})) \iff n = \dim(\ker(L_{A})) + rk(A)$$
e ciò avviene allora $\iff$
$$\dim(\ker(L_{A})) = n - rk(A) > 0$$

Posso allora sempre scrivere per il teorema di struttura per sistemi lineari la soluzione di $A\underline{x} = \underline{b}$ come
$$S = \{v + z | z \in \ker(L_{A})\}$$
dove $v \in L^{-1}_{A}(b)$, e sapendo che $\dim(\ker(L_{A})) = n - rk(A)$, ho infiniti vettori di $S$ che dipendono proprio da $n - rk(A)$ parametri. Infatti fissato $t = n-rk(A)$, allora $\ker(L_{A}) = \langle v_{1}, \cdots, v_{t} \rangle$. Quindi se $z \in \ker(L_{A})$ significa che $\exists \lambda_{1}, \cdots, \lambda_{t} | z = \lambda_{1}v_{1} + \cdots + \lambda_{t}v_{t}$. Allora se questo vale per ogni $z \in \ker(L_{A})$ e $S = \{v+z\}$, si ha che le soluzioni dipendono da $\lambda_{1}, \cdots, \lambda_{t}$, ovvero da $t = n-rk(A)$ parametri.

**Qed**.

## Referenze
[^1]: ovvero se hanno lo stesso [[rango-righe|rango]]