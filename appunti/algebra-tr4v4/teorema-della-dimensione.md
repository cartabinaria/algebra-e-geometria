---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 23-03-2024 12:14:07
links:
  - "[[lecture-20032024091443|Lecture 20032024091443]]"
---
# Teorema della dimensione
---
## Introduzione
> Sia $f: V \to W$ un'[[applicazione-lineare|applicazione lineare]], allora si ha che
> $$\dim(V) = \dim(\ker(f)) + \dim(\Im(f))$$
> ovvero che la [[dimensione|dimensione]] del dominio $V$ è uguale alla somma della dimensione del [[nucleo|kernel]] di $f$ con la dimensione dell'[[immagine-di-funzione|immagine]] di $f$.

## Dimostrazione
Per semplicità, usiamo le proprietà algebriche delle equazioni e ci riduciamo a dimostrare
$$\dim(V) - \dim(\ker(f)) = \dim(\Im(f))$$

Supponiamo di avere una base di $V$ t.c. $\dim(V) = n$. La dimensione del kernel di $f$, supponendo di aver risolto il [[sistema-lineare-omogeneo|sistema lineare omogeneo]] associato alla [[matrice|matrice]] $A$ che definisce l'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare]] $L_{A} = f$, sarà $r \leq n$, dove $r$ è il numero di righe non nulle (_pivot_) di $A$ ridotta a scala. Vale a dire che una base di $\ker(f)$ sarebbe del tipo $\{v_{1}, \cdots, v_{r}\}$ t.c. $f(v_{1}) = \cdots = f(v_{r}) = \underline{0}$. Sostituendo tali valori nell'equazione otteniamo che dobbiamo dimostrare
$$\dim(\Im(f)) = n - r$$

Ora per il [[teorema-del-completamento|teorema del completamento]] possiamo completare la base di $\ker(f)$ a una base di $V$, ottenendo
$$\beta = \{v_{1}, \cdots, v_{r}, v_{r+1}, \cdots, v_{n}\}$$

Ora calcoliamo una base di $\Im(f)$, sapendo che vale la seguente [[immagine-di-funzione-proposizioni|proposizione]]
$$\Im(f) = \langle f(v_{1}), \cdots, f(v_{n}) \rangle$$

per cui dimostriamo che una base di $\Im(f)$ è
$$\{f(v_{r+1}), \cdots, f(v_{n})\}$$
composta infatti da $n-r$ vettori.

Sappiamo, per ipotesi, che
$$f(v_{1}) = \cdots = f(v_{r}) = \underline{0}$$
perché $v_{1}, \cdots, v_{r} \in \ker(f)$. Usando la proposizione sul sottospazio generato di $\Im(f)$, abbiamo
$$\Im(f) = \langle \underline{0}, \cdots, \underline{0}, f(v_{r+1}), \cdots, f(v_{n}) \rangle$$
per cui possiamo eliminare tutti i vettori nulli (perché linearmente dipendenti da qualunque vettore[^1]), e ci rimane
$$\Im(f) = \langle f(v_{r+1}), \cdots, f(v_{n}) \rangle$$
per cui dobbiamo mostrare che $f(v_{r+1}), \cdots, f(v_{n})$ sono [[indipendenza-lineare|linearmente indipendenti]]. Usiamo la definizione:
$$\lambda_{r+1}f(v_{r+1}) + \cdots + \lambda_{n}f(v_{n}) = \underline{0} \iff \lambda_{r+1} = \cdots = \lambda_{n} = 0$$
Sfrutto allora la linearità di $f$, e ottengo
$$f(\lambda_{r+1}v_{r+1} + \cdots + \lambda_{n}v_{n}) = \underline{0} \iff \lambda_{r+1} = \cdots = \lambda_{n} = 0$$

e perciò che
$$v = \lambda_{r+1}v_{r+1} + \cdots + \lambda_{n}v_{n} \in \ker(f)$$

Riscrivo allora questo vettore come combinazione lineare della base di $\ker(f)$ $\{v_{1}, \cdots, v_{r}\}$:
$$v = \mu_{1}v_{1} + \cdots + \mu_{r}v_{r}$$

Ottengo la seguente uguaglianza
$$\lambda_{r+1}v_{r+1} + \cdots + \lambda_{n}v_{n} = \mu_{1}v_{1} + \cdots + \mu_{r}v_{r}$$
per cui
$$\lambda_{r+1}v_{r+1} + \cdots + \lambda_{n}v_{n} - \mu_{1}v_{1} - \cdots - \mu_{r}v_{r} = \underline{0}$$

il che è ovvio perché $v_{1}, \cdots v_{r}, v_{r+1}, \cdots, v_{n}$ è base di $V$, per cui sono linearmente indipendenti, e allora l'unica maniera affinché tale combinazione lineare sia uguale a $\underline{0}$ è quando
$$\lambda_{r+1} = \cdots = \lambda_{n} = \mu_{1} = \cdots = \mu_{r} = 0$$
e in particolare
$$\lambda_{r+1} = \cdots = \lambda_{n} = 0$$

Ricapitolando abbiamo ottenuto che
$$\{f(v_{r+1}), \cdots, f(v_{n})\}$$
genera $\Im(f)$ ed è linearmente indipendente, per cui è base di $\Im(f)$:
$$\dim(\Im(f)) = n - r$$

**Qed**.

## Utilità
Questo teorema risulta fondamentale nello svolgimento di esercizi in cui magari _non viene richiesto di conoscere il sottospazio generato dal nucleo né il sottospazio generato dall'immagine, ma magari solo la loro dimensione_: **calcolando anche solo una delle due dimensioni, per questo teorema ricaviamo immediatamente quella dell'altro**.

Per esempio
- per sapere se una certa $f: V \to W$ è [[funzione-suriettiva|suriettiva]] ci basta avere che $\dim(\Im(f)) = \dim(W)$;
- per sapere se una certa $f: V \to W$ è [[funzione-iniettiva|iniettiva]] ci basta avere che $\dim(\ker(f)) = 0$;

### Esempi
#### $\nexists f: \mathbb{R}^{5} \to \mathbb{R}^{3} | f \text{ 1-1}$
Procediamo [[regole-di-inferenza-del-raa|per assurdo]], per cui supponiamo che tale funzione $f$ esista e sia iniettiva. Per questo vorrebbe dire che $\dim(\ker(f)) = 0$. Il teorema della dimensione, allora, ci dice che deve valere
$$\dim(\mathbb{R}^{5}) = \dim(\ker(f)) + \dim(\Im(f))$$
ovvero
$$5 = 0 + \dim(\Im(f))$$

Ma noi sappiamo che $\Im(f)$ vive (è sottospazio) in $\mathbb{R}^{3}$, per cui la dimensione massima di $\Im(f)$ è proprio 3; allora dovrebbe valere
$$5 = 3$$
che è un assurdo.

#### $\nexists f: \mathbb{R}^{4} \to \mathbb{R}^{7} | f \text{ su}$
Procediamo sempre per assurdo, supponendo che tale funzione $f$ esista e sia suriettiva. Per questo vuol dire che abbiamo $\dim(\Im(f)) = \dim(\mathbb{R}^{7})$, per cui per il teorema della dimensione vale
$$\dim(\mathbb{R}^{4}) = \dim(\ker(f)) + \dim(\mathbb{R}^{7})$$
ovvero
$$4 = \dim(\ker(f)) + 7$$

il che è impossibile, perché vorrebbe dire
$$\dim(\ker(f)) = -3$$
e la dimensione non può mai essere negativa, per cui assurdo.

## Corollario
### Limite all'iniettività
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{m}$ t.c. $n > m$, allora $f$ _non è iniettiva_.

### Limite alla suriettività
> Sia $f: \mathbb{R}^{n} \to \mathbb{R}^{m}$ t.c. $n < m$, allora $f$ _non è suriettiva_.

### Iniettività $\iff$ suriettività
> Siano $V, W$ spazi vettoriali tali che $\dim(V) = \dim(W)$ e sia $f: V \to W$ lineare, allora
> $$f \text{ 1-1} \iff f \text{ su}$$

#### Dimostrazione
E' una conseguenza diretta del teorema del completamento, infatti si ha che se $\dim(V) = \dim(W)$, allora
$$\dim(V) = \dim(\ker(f)) + \dim(\Im(f)) = \dim(W)$$
e allora:
- $f$ è iniettiva $\implies \dim(\ker(f)) = 0 \implies \dim(V) = \dim(\Im(f)) = \dim(W) \implies$ f è suriettiva;
- $f$ è suriettiva $\implies \dim(\Im(f)) = \dim(W) \implies \dim(V) = \dim(\ker(f)) + \dim(W) = \dim(W) \implies \dim(\ker(f)) = 0 \implies$ f è iniettiva.

### Righe e colonne di una matrice
> Sia $A \in M_{m \times n} (\mathbb{R})$ t.c. $r_{1}, \cdots, r_{m}$ sono le righe di $A$ e $c_{1}, \cdots, c_{n}$ le colonne di $A$, allora
> $$\dim(\langle r_{1}, \cdots, r_{m} \rangle) = \dim(\langle c_{1}, \cdots, c_{n} \rangle)$$
> ovvero la dimensione del sottospazio generato dalle righe è la stessa di quello generato dalle colonne.

Tra le conseguenze questa è sicuramente tra quelle più significative, perché lega concetti apparentemente sconnessi. Sappiamo infatti che le _righe e le colonne di una matrice vivono su spazi vettoriali di dimensione e fattezze diversi_, _eppure la dimensione del sottospazio generato da righe e da colonne sarà sempre lo stesso_.

#### Dimostrazione
Consideriamo un'applicazione lineare $L_{A}: \mathbb{R}^{n} \to \mathbb{R}^{m}$ definita da una matrice $A \in M_{m \times n} (\mathbb{R})$.  Abbiamo che $\ker(L_{A})$ è definito come l'insieme delle soluzioni del sistema lineare omogeneo $A\underline{x} = \underline{0}$. Riducendo $A$ a scala con Gauss, otteniamo che il $\ker(f)$ è l'insieme delle soluzioni dipendenti da $n-rr(A)$[^2] variabili libere, ovvero che
$$\dim(\ker(L_{A})) = n - rr(A)$$

Ora, considerando l'immagine $\Im(L_{A})$ sappiamo che si ricava da $A^{T}$[^3] riducendo tale matrice sempre a scala. Otteniamo un certo valore $rr(A^{T}) = rc(A)$, che corrisponde alla dimensione dell'immagine di $L_{A}$, per cui
$$\dim(\Im(L_{A})) = rc(A)$$

Ora applichiamo il teorema della dimensione, che ci dice
$$\dim(\mathbb{R}^{n}) = \dim(\ker(L_{A})) + \dim(\Im(L_{A}))$$
allora, per i risultati precedenti, otteniamo
$$n = n-rr(A)+rc(A)$$
e quindi che
$$rr(A) = rc(A)$$

il che significa che
$$\dim(\langle r_{1}, \cdots, r_{m} \rangle) = \dim(\langle c_{1}, \cdots, c_{n} \rangle)$$

**Qed**.

## Referenze
[^1]: basta moltiplicare un qualsiasi vettore per lo [[scalare|scalare]] $0$
[^2]: [[rango-righe|rango righe]]
[^3]: [[matrice-trasposizione|trasposta]]