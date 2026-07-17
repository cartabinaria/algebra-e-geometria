---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 04-03-2024 17:41:54
links:
  - "[[lecture-29022024111734|Lecture 29022024111734]]"
---
# Indipendenza lineare
---
## Introduzione
> Sia $V$ uno [[spazio-vettoriale|spazio vettoriale]]. I [[vettore|vettori]] $v_{1}, \cdots, v_{n} \in V$ si dicono **linearmente indipendenti** se per ogni [[combinazione-lineare|combinazione lineare]]
> $$\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} = \underline{0}$$
> si ha $\lambda_{1} = \cdots = \lambda_{n} = 0$.
> In altro parole tali vettori si dicono linearmente indipendenti se _l'unica combinazione lineare che dà come risultato il vettore nullo ($\underline{0}$) è quella con [[scalare|scalari]] tutti nulli_. In tal caso, l'insieme dei vettori $\{v_{1}, \cdots, v_{n}\}$ si dice linearmente indipendente.

<u>Nota bene</u>: i vettori $v_{1}, \cdots, v_{n}$ si dicono **linearmente dipendenti** se _non sono linearmente indipendenti_[^1].

### Esempio
Preso l'insieme di vettori $\{(1, 1), (1, 3)\}$, questo è linearmente indipendente perché
$$\lambda_{1}(1, 1) + \lambda_{2}(1, 3) = (0, 0) \ \ \ \ \iff \ \ \ \ \lambda_{1} = \lambda_{2} = 0$$

Per verificarlo mettiamo sviluppiamo il prodotto per scalare
$$(\lambda_{1} + \lambda_{2}, \lambda_{1} + 3\lambda_{2}) = (0, 0)$$
e scriviamo il [[sistema-lineare|sistema lineare]] associato
$$\begin{cases} \lambda_{1} + \lambda_{2} = 0 \\ \lambda_{1} + 3\lambda_{2} = 0 \end{cases}$$

<u>Nota bene</u>: si tratta di un [[sistema-lineare-omogeneo|sistema omogeneo]]! Quindi almeno la soluzione nulla è presente, _ci basta verificare se è unica o se sono infinite_. Nel primo caso i vettori sono indipendenti, nel secondo no!

Applicando l'[[algoritmo-di-gauss|algoritmo di Gauss]] otteniamo la seguente [[matrice-a-scala|matrice a scala]] associata al sistema
$$\begin{pmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \end{pmatrix}$$

per cui $rr(A) = 2 = rr(A|\underline{b}) = \text{n° incognite}$ per cui _c'è una sola soluzione, ovvero quella nulla_: **i vettori sono indipendenti**.

## Proposizioni
Si ha che l'insieme
$$\{\underline{0}, v_{1}, \cdots, v_{n}\}$$ è **sempre dipendente**, poiché $\lambda_{0}$ (quello che moltiplica il vettore nullo $\underline{0}$) _può essere qualunque cosa in $\mathbb{R}$_ e tutti gli altri $\lambda_{1, \cdots, n} = 0$: il risultato è il vettore nullo ma non tutti i $\lambda$ sono per forza a 0.

Inoltre si ha:
- $\varnothing$ (l'[[definizione-di-insieme-vuoto|insieme vuoto]]) è linearmente _indipendente_ per convenzione;
- $\{\underline{0}\}$ (il [[assioma-del-singoletto|singoletto]] del vettore nullo) è linearmente _dipendente_;

Si ha anche che:
> Se $S$ è un insieme di vettori linearmente indipendenti, _ogni suo sottoinsieme è ancora linearmente indipendente_.

### Multiplicità
> Sia $V$ uno spazio vettoriale. Si ha che $v_{1}, \cdots, v_{n} \in V$ sono _dipendenti_ $\iff$ _uno di essi è combinazione lineare degli altri_.

#### Dimostrazione
Dimostriamo il primo verso dell'implicazione. Ho che $v_{1}, \cdots, v_{n} \in V$ sono dipendenti, ovvero che non sono indipendenti. Perciò $\exists \lambda_{1}, \cdots, \lambda_{n} : \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} = \underline{0} \land \lambda_{k} \neq 0$, ovvero esiste una sequenza di scalari che come risultato dà il vettore nullo con un qualche $\lambda_{k}$ che nullo non è. Per dimostrare allora che uno tra $v_{1}, \cdots, v_{n}$ vettori è combinazione lineare degli altri, prendo proprio il $v_{k}$ associato al $\lambda_{k}$ non nullo e lo isolo: $\lambda_{1}v_{1} + \cdots + \lambda_{k}v_{k} + \lambda_{n}v_{n} = \underline{0}$, da cui $-\lambda_{k}v_{k} = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$. Ora, dato che $\lambda_{k} \neq 0$ per le ipotesi, posso dividere ambo i membri per $-\lambda_{k}$, e ottenere
$$v_{k} = - \frac{\lambda_{1}}{\lambda_{k}}v_{1} - \cdots - \frac{\lambda_{n}}{\lambda_{k}}v_{n}$$
che dimostra che posso ottenere un vettore dalla combinazione lineare degli altri.

Dimostro il secondo verso dell'implicazione. Ho che almeno uno tra i vettori $v_{1}, \cdots, v_{n}$ è combinazione lineare degli altri, ovvero $\exists v_{k} \in \{v_{1}, \cdots, v_{n}\} : v_{k} = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$. Devo dimostrare che $v_{1}, \cdots, v_{n}$ sono dipendenti, o che non sono indipendenti, cioè che $\exists \lambda_{1}, \cdots, \lambda_{n} : \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} = \underline{0} \land \lambda_{k} \neq 0$. Devo fondamentalmente trovare questo $\lambda_{k}$ non nullo che renda dipendente l'insieme di vettori. Dall'ipotesi, allora, porto $v_{k}$ a destra dell'uguale e ottengo il $\lambda_{k}$ che cercavo, ovvero -1. Infatti ottengo
$$\lambda_{1}v_{1} + \cdots + (-1)v_{k} + \lambda_{n}v_{n} = \underline{0}$$
con cui dimostro che i vettori sono dipendenti.

#### Esempio
Preso l'insieme di vettori $\{(1, 0), (0, 1), (1, 2)\}$ è facile notare come $(1, 2) = 1(1, 0) + 2(0, 1)$.

#### Corollario
E' proprio da questa proposizione che si arriva a capire che
> Due vettori sono linearmente indipendenti $\iff$ _non sono uno multiplo dell'altro_.

Ciò era scontato, ma non ovvio.

<u>Attenzione</u>: non vale il contrario! _Un insieme di vettori linearmente dipendenti non sono per forza uno multiplo dell'altro_.

### Sottoinsiemi
> Un [[definizione-di-essere-sottoinsieme|sottoinsieme]] non vuoto di un _insieme di vettori linearmente indipendenti_ è formato da vettori che _sono ancora linearmente indipendenti_.

## Referenze
[^1]: un po' come la definizione di [[insieme-finito|insieme finito]]