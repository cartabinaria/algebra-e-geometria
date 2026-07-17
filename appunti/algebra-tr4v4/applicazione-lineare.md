---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 09-03-2024 11:26:02
links:
  - "[[lecture-07032024111604|Lecture 07032024111604]]"
  - "[[lecture-12032024091825|Lecture 12032024091825]]"
  - "[[lecture-14032024111404|Lecture 14032024111404]]"
  - "[[lecture-19032024091914|Lecture 19032024091914]]"
---
# Applicazione lineare
---
## Introduzione
Per comprendere la potenza delle applicazioni lineari, prendiamo in esempio il seguente caso. Fissiamo uno [[spazio-vettoriale|spazio vettoriale]] $V$ e $\beta = \{v_{1}, \cdots, v_{n}\}$ una sua [[base|base]] _ordinata_, quindi prendiamo un $v \in V$ t.c. le sue [[coordinate-rispetto-a-una-base|coordinate]] rispetto a $\beta$ sono
$$(v)_{\beta} = (\lambda_{1}, \cdots, \lambda_{n})$$
con $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$.

Ora consideriamo la [[funzione-matematica|funzione]] $f_{\beta}: V \to \mathbb{R}^{n}$ definita come $v \to (v)_{\beta}$, ovvero una funzione che preso un vettore ci associa le sue coordinate rispetto a una certa base, si dimostra che:
- $f_{\beta}$ è _[[funzione-iniettiva|iniettiva]]_
- $f_{\beta}$ è _[[funzione-suriettiva|suriettiva]]_
- $f_{\beta}$ _rispetta la somma e il prodotto per scalari_

o in poche parole che **$f_{\beta}$ è un [[isomorfismo|isomorfismo]] di spazi vettoriali**. Proprio per questo, date le proprietà degli isomorfismi, _possiamo lavorare in $V$ passando alle coordinate (quindi in $\mathbb{R}^{n}$) per poi tornare a $V$_.

## Definizione
> Dati $V, W$ spazi vettoriali, una funzione $f: V \to W$ si dice **applicazione lineare** (o **funzione lineare**, **mappa lineare**) se si ha:
> 1. $f(v + u) = f(v) + f(u) \ \ \ \forall u, v \in V$[^1]
> 2. $f(\lambda v) = \lambda f(v) \ \ \ \forall \lambda \in \mathbb{R}, \forall v \in V$
> 
> ovvero fondamentalmente se _$f$ rispetta la somma e il prodotto per scalare_.

### Esempi
#### $v \to (v)_{\beta}$
Si ha che la funzione $f: V \to \mathbb{R}^{n}$ definita come $v \to (v)_{\beta}$, ovvero la funzione che associa a un vettore le sue coordinate rispetto a una base dello spazio a cui appartiene, è un'applicazione lineare.

#### $f \to f'$
Dato $V = \{f: \mathbb{R} \to \mathbb{R}\}$ un insieme di [[funzioni-derivabili|funzioni derivabili]], $W = \{f: \mathbb{R} \to \mathbb{R}\}$, allora la funzione $d: V \to W$ definita come $f \to f'$ è lineare.

#### $\mathbb{R}^{n} \to \mathbb{R}^{m}$
Ovvero ogni [[applicazione-lineare-definita-da-una-matrice|applicazioni lineari definite da una matrice]].

### Forme
Abbiamo 3 modi per definire un'applicazione lineare:
1. assegnare $f(e_{1}), \cdots, f(e_{n})$ (che è la _formula chiave_)
2. dare la legge $f(x_{1}, \cdots, x_{n}) = (\cdots)$
3. dare la matrice $A$ dell'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]] $L_{A}$

E' facile passare da una all'altra:
- $1 \longrightarrow 3$ si fa per definizione di $A$, mettendo quindi i risultati $f(e_{1}), \cdots, f(e_{n})$ come colonne di $A$;
- $3 \longrightarrow 2$ si ottiene con la moltiplicazione $A \underline{x} = A \cdot \begin{pmatrix} x_{1} \\ \vdots \\ x_{n} \end{pmatrix}$
- $2 \longrightarrow 1$ si ottiene calcolando semplicemente i risultati di $f$ per ogni base canonica del dominio

<u>Nota bene</u>: _ci è comodo sempre ottenere la matrice $A$_.

## Proposizioni
### $f \text{ lineare} \implies f(0_{V}) = 0_{W}$
Vale che data una funzione $f: V \to W$ lineare, allora l'[[elemento-neutro|elemento neutro]] di $V$ ($0_{V}$) è mappato da $f$ nell'elemento neutro di $W$ ($0_{W}$). E' importante la contronominale $f(0_{V}) \neq 0_{W} \implies f \text{ non lineare}$ perché è un _criterio utile per controllare la linearità di un'applicazione_.

#### Dimostrazione
Si dimostra con la seguente catena di uguaglianze
$$f(0_{V}) = f(0 \cdot 0_{V}) \stackrel{\text{lin}}{=} 0 \cdot f(0_{V}) = 0_{W} \in W$$

### $f \text{ lineare} \implies \ker(f) \leq V$
Vale ovvero che data una funzione $f: V \to W$ lineare, allora il suo [[nucleo|kernel]] è [[sottospazio-vettoriale|sottospazio]] di $V$.

#### Dimostrazione
Per dimostrarlo applico la definizione di sottospazio. Devo avere:
1. $\underline{0} \in \ker(f)$
2. $v_{1} + v_{2} \in \ker(f) \ \ \ \forall v_{1}, v_{2} \in \ker(f)$
3. $\lambda v_{1} \in \ker(f) \ \ \ \forall v_{1} \in \ker(f), \forall \lambda \in \mathbb{R}$

Il vettore nullo è in $\ker(f)$ perché per la linearità di $f$ devo avere $f(0_{V}) = 0_{W}$, per cui $\underline{0} \in \ker(f)$.

Se so per ipotesi $v_{1}, v_{2} \in \ker(f)$, per la definizione di $\ker(f)$ ho che $f(v_{1}) = \underline{0}$ e $f(v_{2}) = \underline{0}$. Allora ottengo
$$f(v_{1} + v_{2}) \stackrel{\text{lin}}{=} f(v_{1}) + f(v_{2}) = \underline{0} + \underline{0} = \underline{0}$$

cioè ciò che volevo dimostrare.

Infine, avendo $v_{1} \in \ker(f)$ so che $f(v_{1}) = \underline{0}$, allora ottengo
$$f(\lambda v_{1}) \stackrel{\text{lin}}{=} \lambda f(v_{1}) = \lambda \underline{0} = \underline{0}$$

**Qed**.

### $f \text{ lineare} \implies \Im(f) \leq W$
In coppia con la proposizione precedente, data una funzione $f: V \to W$ lineare, ho che l'[[immagine-di-funzione|immagine]] di $f$ è sottospazio di $W$.

#### Dimostrazione
Anche in questo caso applico la definizione di sottospazio, per cui mi riduco a dimostrare:
- $\underline{0} \in \Im(f)$
- $w_{1} + w_{2} \in \Im(f) \ \ \ \forall w_{1}, w_{2} \in \Im(f)$
- $\lambda w_{1} \in \Im(f) \ \ \ \forall w_{1} \in \Im(f), \forall \lambda \in \mathbb{R}$

Il vettore nullo è nell'immagine di $f$ perché ho per forza $f(0_{V}) = 0_{W}$.

Fissati due vettori $w_{1}, w_{2} \in \Im(f)$, per definizione so che $\exists v_{1} | f(v_{1}) = w_{1}$ e $\exists v_{2} | f(v_{2}) = w_{2}$. Devo dimostrare $\exists v_{3} | f(v_{3}) = w_{1} + w_{2}$. Scelgo come $v_{3} = v_{1} + v_{2}$, in questo modo ottengo
$$f(v_{3}) = f(v_{1} + v_{2}) \stackrel{\text{lin}}{=} f(v_{1}) + f(v_{2}) = w_{1} + w_{2}$$
cioè ciò che volevo dimostrare.

Infine, avendo $w_{1} \in \Im(f)$ so che $\exists v_{1} | f(v_{1}) = w_{1}$. Devo dimostrare $\exists v_{2} | f(v_{2}) = \lambda w_{1}$. Scelgo $v_{2} = \lambda v_{1}$, per cui ottengo
$$f(v_{2}) = f(\lambda v_{1}) \stackrel{\text{lin}}{=} \lambda f(v_{1}) = \lambda w_{1}$$
proprio ciò che volevo dimostrare.

**Qed**.

### $f \text{ lineare} \implies f \text{ su} \iff \Im(f) = W$
Ovvero data una funzione $f: V \to W$ lineare, allora questa è [[funzione-suriettiva|suriettiva]] sse la sua immagine coincide con $W$.

E' vera per definizione di suriettività!

### $f \text{ lineare} \implies f \text{ 1-1} \iff \ker(f) = \{\underline{0}\}$[^2]
Fondamentalmente, questa importante proposizione ci sta dicendo che affinché un'applicazione lineare sia iniettiva basta che **l'unico elemento mappato nel vettore nullo del codominio sia il vettore nullo del dominio**: questo è il criterio sufficiente che ci basta per capire se tutta la funzione sarà iniettiva.

#### Dimostrazione
1° verso dell'implicazione: suppongo $f \text{ 1-1}$, per cui che $a \neq b \implies f(a) \neq f(b) \ \ \ \forall a, b$ e la contronominale $f(a) = f(b) \implies a = b \ \ \ \forall a, b$. Devo dimostrare $\ker(f) = \{\underline{0}\}$. Dalle ipotesi, scelgo $v \in \ker(f)$ t.c. $f(v) = \underline{0} = f(0_{V})$. Allora, essendo iniettiva per la contronominale, so che $v = 0_{V}$, e quindi $\ker(f) = \{0_{V}\} = \{\underline{0}\}$.

2° verso dell'implicazione: suppongo $\ker(f) = \{\underline{0}\}$. Devo dimostrare che $f \text{ 1-1}$, ovvero che $a \neq b \implies f(a) \neq f(b) \ \ \ \forall a, b$, o la contronominale $f(a) = f(b) \implies a = b \ \ \ \forall a, b$. Suppongo, per un qualche $a, b \in V$, $f(a) = f(b)$, che implica $f(a) - f(b) = \underline{0}$. Uso la _linearità_ di $f$ e ottengo $f(a-b) = \underline{0}$. Ho trovato allora un elemento del kernel $a-b \in \ker(f)$, e per ipotesi so che dev'essere $\underline{0}$. Allora $a-b = \underline{0} \implies a = b$.

**Qed**.

#### Osservazione
Questo è un _criterio che in [[analisi-i|analisi]]_, dove la linearità è solo uno spicchio dello spettro delle funzioni che si analizzano, _non vale sempre_. Di fatto presa anche solo la funzione $x \to x^{2}$, questa ha come kernel solo il vettore nullo, infatti solo $f(0) = 0$, _tuttavia sappiamo non essere assolutamente iniettiva_.

## Osservazioni
Come corollario della linearità di una funzione $f$ si ha che
$$f(\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}) = f(\lambda_{1}v_{1}) + \cdots + f(\lambda_{n}v_{n}) = \lambda_{1}f(v_{1}) + \cdots + \lambda_{n}f(v_{n})$$

## Teoremi
- [[teorema-di-esistenza-e-unicita-di-un-applicazione-lineare|Teorema di esistenza e unicità di un'applicazione lineare]]

## Referenze
[^1]: a tutti gli effetti un [[morfismo|morfismo]] di [[gruppo|gruppi]]
[^2]: nota il [[assioma-del-singoletto|singoletto]] del vettore nullo