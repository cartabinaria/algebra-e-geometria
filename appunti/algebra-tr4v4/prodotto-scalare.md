---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
  - topic/analisi-I
date: 21-02-2024 09:05:50
links:
  - "[[lecture-20022024091619|Lecture 20022024091619]]"
  - "[[lecture-11032024131300|Lecture 11032024131300]]"
  - "[[lecture-24042024092014|Lecture 24042024092014]]"
---
# Prodotto scalare
---
## Introduzione
> Il **prodotto scalare** (o **dot-product**) ([[spazio-euclideo|euclideo]]) è una [[funzione-matematica|funzione]] $<,>: \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}$ tale che presi due [[vettore|vettori]] $v, w \in \mathbb{R}^{n}$, quindi del tipo $v = (v_{1}, \cdots, v_{n})$ e $w = (w_{1}, \cdots, w_{n})$, si ha che
> $$<v, w> = v_{1}w_{1} + \cdots + v_{n}w_{n}$$
> o, alternativamente
> $$<v, w> = \sum\limits_{k=1}^{n} v_{k}w_{k}$$
> <u>Attenzione</u>: _il risultato è un numero_!

### In $\mathbb{R}^{2}$
In $\mathbb{R}^{2}$ immaginiamo di prendere in considerazione due vettori $v = (x_{1}, y_{1})$ e $w = (x_{2}, y_{2})$. Sappiamo quindi che il loro prodotto scalare è
$$<v, w> = x_{1}x_{2} + y_{1}y_{2} \in \mathbb{R}$$

Un'interpretazione geometrica di questo valore può fornircela la seguente immagine:
![[Drawing 2024-05-05 17.08.05.excalidraw|750]]

Di fatto si dimostra che, considerato $\theta = \theta_{2}-\theta_{1}$ ovvero la differenza dei due angoli formati da $v$ e $w$, si ha la seguente uguaglianza
$$<v, w> = ||v|| \cdot ||w|| \cdot \cos{\theta}$$

<u>Nota bene</u>: ciò vale _solo in $\mathbb{R}^{2}$_.

#### Dimostrazione
Vogliamo dimostrare l'uguaglianza precedente, per cui partiamo da $<v, w>$:
$$<v, w> = x_{1}x_{2} + y_{1}y_{2}$$

Notiamo, dal disegno, che $x_{1} = ||v||\cos{\theta_{1}}$ mentre $y_{1} = ||v||\sin{\theta_{1}}$[^1]; similmente per $x_{2}, y_{2}$, perciò il prodotto scalare diventa:
$$<v, w> = ||v||\cos{\theta_{1}} \cdot ||w||\cos{\theta_{2}} + ||v||\sin{\theta_{1}} \cdot ||w||\sin{\theta_{2}}$$
quindi, raccogliamo le [[norma-euclidea|norme]] e otteniamo
$$<v, w> = ||v|| \cdot ||w|| \cdot (\cos{\theta_{1}}\cos{\theta_{2}} + \sin{\theta_{1}}\sin{\theta_{2}})$$

Ora, usando la [[trigonometria|trigonometria]], concludiamo che
$$<v, w> = ||v|| \cdot ||w|| \cdot \cos{(\theta_{2} - \theta_{1})} = ||v|| \cdot ||w|| \cdot \cos{\theta}$$

**Qed**.

## Proprietà
### Simmetria
$$<x, y> = <y, x> \ \ \ \forall x, y \in \mathbb{R}^{n}$$

### Bilinearità
$$<\lambda x, y> = \lambda <x, y>$$
$$<x+y, z> = <x, z> + <y, z>$$

### Positività
$$<x, x> \geq 0, \ \ <x, x> = 0 \iff x = \underline{0} \ \ \ \forall x \in \mathbb{R}^{n}$$

Questo è vero perché $<x, x> = \sum\limits_{k=1}^{n} x_{k}^{2} \geq 0$ perché somma di termini positivi.

## Referenze
[^1]: la rappresentazione in [[coordinate-polari|forma polare]] dei vettori