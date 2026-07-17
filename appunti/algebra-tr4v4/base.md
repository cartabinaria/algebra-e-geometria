---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 07-03-2024 17:32:55
links:
  - "[[lecture-05032024091733|Lecture 05032024091733]]"
  - "[[lecture-06032024091542|Lecture 06032024091542]]"
---
# Base
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]], allora un insieme $\{v_{1}, \cdots, v_{n}\}$ si dice **base** di $V$ se
> 1. $v_{1}, \cdots, v_{n}$ [[sottospazio-generato|generano]] $V$, ovvero $V = \langle v_{1}, \cdots, v_{n} \rangle$
> 2. $v_{1}, \cdots, v_{n}$ sono [[indipendenza-lineare|linearmente indipendenti]]
> 
> e lo si indica con
> $$\beta = \{v_{1}, \cdots, v_{n}\}$$

### Esempi
- $\{(1, 0), (0, 1)\}$ è base di $\mathbb{R}^{2}$ (generano e sono indipendenti)
- $\{(1, 0), (0, 1), (1, 2)\}$ non è base di $\mathbb{R}^{2}$ (generano ma sono dipendenti)
- $\{(1, 2, 0), (0, 5, 0)\}$ non è base di $\mathbb{R}^{3}$ (sono indipendenti, ma non generano)

## Proposizioni
### Esistenza della base
> Sia $V$ uno spazio vettoriale [[sottospazio-generato-a64b18|fg]], allora $V$ ha una base.

#### Dimostrazione
Per dimostrare tale proposizione analizziamo i casi di $V$: $V = \{\underline{0}\}$ e $V = \langle v_{1}, \cdots, v_{n} \rangle$.

##### $V = \{\underline{0}\}$
In tal caso, per convenzione, _$\varnothing$ è una base di $V$_[^1].

##### $V = \langle v_{1}, \cdots, v_{n} \rangle$
In questo caso, invece, _se $v_{1}, \cdots, v_{n}$ sono indipendenti sono anche una base_; altrimenti se sono dipendenti vuol dire che uno di essi, che indichiamo con $v_{i}$, può essere espresso come combinazione lineare degli altri, per cui:
1. cancello $v_{i}$ dall'insieme dei generatori;
2. controllo se sono ancora dipendenti, se sì identifico la combinazione lineare che esprime $v_{i}$ e ricomincio dal punto 1; altrimenti ho una base

_Reiterando quest'algoritmo prima o poi si raggiunge una base_.

<u>Nota bene</u>: questa _dimostrazione ci dice qualcosa di più della proposizione_. Ci sta suggerendo un metodo per ottenere una base a partire da un insieme generatore, ovvero _cancellando i generatori superflui_!

###### Esempio
Dato l'insieme di vettori $S = \{3, 1+x, x^{2}, 5x, 4x, -2x^{3}, x^{2}+10x-1\}$, sapendo che $\mathbb{R}_{3}[x] = \langle S \rangle$, ci viene chiesto di trovare un sottoinsieme di $S$ che è una base di $\mathbb{R}_{3}[x]$.

Dobbiamo cancellare da $S$ i vettori dipendenti, fino ad arrivare ad avere un insieme linearmente indipendente. Iterando l'algoritmo di cancellazione si arriva a ottenere per esempio l'insieme $\{3, x^{2}, 5x, -2x^{3}\}$. Per essere sicuri che non siano uno multiplo dell'altro, applico la definizione di indipendenza lineare e risolvo la seguente equazione
$$\lambda_{1}(3) + \lambda_{2}(x^{2}) + \lambda_{3}(5x) + \lambda_{4}(-2x^{3}) = \underline{0} \iff \lambda_{1} = \lambda_{2} = \lambda_{3} = \lambda_{4} = 0$$
Il sistema associato viene
$$\begin{cases} -2\lambda_{4} = 0 \\ \lambda_{2} = 0 \\ 5\lambda_{3} = 0 \\ 3\lambda_{1} = 0 \end{cases}$$
che come unica soluzione ha ovviamente $\lambda_{1} = \lambda_{2} = \lambda_{3} = \lambda_{4} = 0$. Per cui sì, sono linearmente indipendenti, e perciò generando anche $\mathbb{R}_{3}[x]$ sono una sua base.

### $S = \{v_{1}, \cdots, v_{n}\}, V = \langle S \rangle \implies \exists \beta \text{ base di } V : \beta \subseteq S$
Questo è una conseguenza diretta della proposizione precedente.

#### Osservazione
Questa proposizione assume, tra le ipotesi, che $V$ sia generato da $S$. Ma anche se $S$ generasse solo un sottospazio di $V$, esisterebbe sempre una base di tale sottospazio di $V$ che è sottoinsieme di $S$.

### $S = \{v_{1}, \cdots, v_{m}\} \text{ lin. indip.} \implies \exists \beta \text{ base di } V : S \subseteq \beta$
Speculare alla precedente, è una conseguenza del [[teorema-del-completamento|teorema del completamento]] che ci dice che _se si selezionano $m$ vettori indipendenti $\in V$, questi sono sicuramente un sottoinsieme di una base di $V$_. Nota: sottoinsieme non proprio, infatti può essere $S = \beta$.

E' importantissimo notare che _non è necessario imporre la condizione $m \leq n$_, dove $n$ è la [[dimensione|dimensione]] di $V$ (il numero di elementi di una sua base), perché _questo è già implicito all'ipotesi che i vettori di $S$ sono linearmente indipendenti_. Questa infatti attiva il teorema del completamento che impone $m \leq n$.

### Elementi delle basi
Come corollario del teorema del completamento e delle proposizioni di sopra si ha che
> Se $V$ è uno spazio vettoriale fg, allora _due basi di $V$ hanno lo stesso numeri di elementi_.

Di conseguenza **tutte le basi di uno spazio $V$ hanno stessa dimensione**.

#### Dimostrazione
Supponiamo di avere due basi $\beta_{1} = \{v_{1}, \cdots, v_{r}\}$ e $\beta_{2} = \{v_{1}, \cdots, v_{k}\}$ di uno spazio vettoriale $V$. Per ipotesi si ha che $v_{1}, \cdots, v_{r} \in V$ sono linearmente indipendenti, perciò prendendo come base di riferimento $\beta_{2}$ per il teorema del completamento ho
$$r \leq k$$
Sempre per ipotesi si ha $v_{1}, \cdots, v_{k} \in V$ linearmente indipendenti, quindi prendendo come base questa volta $\beta_{1}$ per il teorema del completamento si ottiene
$$k \leq r$$
Unendo i due risultati si ha per forza
$$k = r$$

**Qed**.

### Massimale e minimale
> Siano $v_{1}, \cdots, v_{n} \in V$ spazio vettoriale, allora
> 1. $\{v_{1}, \cdots, v_{n}\}$ è una base di $V \iff$ è un [[insieme-minimale|insieme minimale]] di generatori;
> 2. $\{v_{1}, \cdots, v_{n}\}$ è una base di $V \iff$ è un [[insieme-massimale|insieme massimale]] di vettori linearmente indipendenti;

<u>Nota bene</u>: entrambe sono _proprietà equivalenti al concetto di base_, non una definizione.

## Referenze
- [[base-canonica|Base canonica]]
- [[coordinate-rispetto-a-una-base|Coordinate rispetto a una base]]

[^1]: per questo motivo si dice che $\varnothing$ è linearmente indipendente tra le [[indipendenza-lineare-proposizioni|proposizioni]]