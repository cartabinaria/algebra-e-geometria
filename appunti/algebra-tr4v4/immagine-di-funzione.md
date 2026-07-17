---
tags:
  - category/note
  - status/finished
  - topic/analisi-I
  - topic/logica-per-informatica
  - topic/algebra-e-geometria
date: 29-12-2023 17:35:46
links:
  - "[[lecture-13122023131453|Lecture 13122023131453]]"
  - "[[lecture-14032024111404|Lecture 14032024111404]]"
  - "[[lecture-19032024091914|Lecture 19032024091914]]"
---
# Immagine di funzione
---
## Introduzione
> Si definisce **immagine** di una [[funzione-matematica|funzione]] $f$ il [[definizione-di-essere-sottoinsieme|sottoinsieme]] degli elementi del codominio $C$ per cui esiste un elemento del dominio $D$ mappato su ognuno di essi, o formalmente
> $$\Im(f) := \{c \in C | \exists d \in D. f(d) = c\} \subseteq C$$
> o alternativamente
> $$\Im(f) = \{f(d) | d \in D\}$$

![[Drawing 2024-03-17 15.54.19.excalidraw|800]]

## Restrizione di una funzione alla sua immagine
Restringendo il codominio di una funzione alla sua immagine, la si rende [[funzione-suriettiva|suriettiva]][^1], o meglio:
> Per ogni $f: \mathbb{A} \to \mathbb{B}$ si ha che $f$, vista come funzione di tipo $\mathbb{A} \to \Im(f)$, è suriettiva.

## Proposizioni
### Spazio generato dell'immagine
> Sia $f: V \to W$ un'[[applicazione-lineare|applicazione lineare]] e $\beta = \{v_{1}, \cdots, v_{n}\}$ [[base|base]] di $V$, allora
> $$\Im(f) = \langle f(v_{1}), \cdots, f(v_{n}) \rangle$$
> ovvero l'immagine è generata dal [[sottospazio-generato|sottospazio]] delle immagini della base $\beta$.

#### Dimostrazione
Per dimostrare l'uguaglianza tra i due [[insieme|insiemi]] utilizzo la doppia [[definizione-di-essere-sottoinsieme|inclusione]]: dimostro quindi che $\Im(f) \subseteq \langle f(v_{1}), \cdots, f(v_{n}) \rangle$ e $\langle f(v_{1}), \cdots, f(v_{n}) \rangle \subseteq \Im(f)$. Fisso intanto una funzione $f: V \to W$ lineare.

##### $\Im(f) \subseteq \langle f(v_{1}), \cdots, f(v_{n}) \rangle$
Usando la definizione di essere sottoinsieme mi riduco a dimostrare che fissato un elemento $w \in \Im(f)$ devo avere che $w \in \langle f(v_{1}), \cdots, f(v_{n}) \rangle$. Se $w \in \Im(f)$ significa $\exists v \in V : f(v) = w$. Sapendo che $v \in V$ e che $v_{1}, \cdots, v_{n}$ è base di $V$, posso dire $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$. Avendo $f(v) = w$ ho anche quindi che
$$f(\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}) = w$$

Uso quindi la linearità di $f$ e ottengo
$$\lambda_{1}f(v_{1}) + \cdots + \lambda_{n}f(v_{n}) = w$$

Ma questo significa che $w$ è generato da una combinazione lineare di $f(v_{1}), \cdots, f(v_{n})$. Per cui ho proprio
$$w \in \langle f(v_{1}), \cdots, f(v_{n}) \rangle$$

##### $\langle f(v_{1}), \cdots, f(v_{n}) \rangle \subseteq \Im(f)$
Usando sempre la definizione di essere sottoinsieme, dimostro che un elemento fissato $w \in \langle f(v_{1}), \cdots, f(v_{n}) \rangle$ ho che $w \in \Im(f)$. Procedo con lo stesso ragionamento di prima ma partendo dalla fine! Dimostro quindi che
$$w \in \Im(f)$$

<u>Nota bene</u>: _per dimostrare ciò si poteva usare [[Sottospazio generato#$Z leq V v_{1}, cdots, v_{n} in Z implies langle v_{1}, cdots, v_{n} rangle subseteq Z$|questa proposizione]]_, che ci dice che se $f(v_{1}), \cdots, f(v_{n}) \in \Im(f)$, e $\Im(f) \leq W$ allora ho $\langle f(v_{1}), \cdots, f(v_{n}) \rangle \subseteq \Im(f)$.

**Qed**.

## Calcolo
### Esempio
Supponendo di avere un'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]] $A = \begin{pmatrix} 1 & 3 & 2 & 1 & 1 \\ 2 & 6 & 5 & 3 & 1 \\ 0 & 0 & 4 & 4 & -4 \end{pmatrix}$ con $L_{A}: \mathbb{R}^{5} \to \mathbb{R}^{3}$. Se ci viene chiesto di calcolare una base di $\Im(L_{A})$, sfruttiamo la proposizione precedente. Per cui prendiamo la base canonica $\beta = \{e_{1}, \cdots, e_{5}\}$ di $\mathbb{R}^{5}$, e calcoliamo $f(e_{1}), \cdots, f(e_{5})$, ottenendo che
$$\Im(L_{A}) = \langle L_{A}(e_{1}), \cdots, L_{A}(e_{5}) \rangle = \langle (1, 2, 0), (3, 6, 0), (2, 5, 4), (1, 3, 4), (1, 1, -4) \rangle$$

<u>Nota bene</u>: tale sottospazio non è altro che $A^{T}$, ovvero $A$ [[matrice-trasposizione|trasposta]]!

Ora, per il [[teorema-del-completamento-conseguenze|corollario del teorema del completamento]], sappiamo che questa non può essere una base di $\Im(L_{A})$, perché questa vive nel codominio $\mathbb{R}^{3}$, e i vettori in questione sono 5. Allora usiamo [[algoritmo-di-gauss-utilizzo-diretto|Gauss in modo diretto]] e troviamo una base del sottospazio generato
$$\{(1, 2, 0), (0, 1, 4)\}$$
da cui ricaviamo che
$$\dim(\Im(L_{A})) = 2$$

## Referenze
[^1]: è la tecnica con cui sono definite le [[funzioni-trigonometriche-inverse|funzioni trigonometriche inverse]]