---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 30-03-2024 19:23:56
links:
  - "[[lecture-27032024091734|Lecture 27032024091734]]"
---
# Forme dei sottospazi
---
## Introduzione
Uno spazio generato di $\mathbb{R}^{n}$ si può assegnare nei 2 seguenti modi:
1. $V = \langle v_{1}, \cdots, v_{k} \rangle$, ovvero fornendo un insieme di generatori;
2. $V = \{\underline{x} \in \mathbb{R}^{n} | A \underline{x} = \underline{0}\}$, ovvero come insieme delle soluzioni di un [[sistema-lineare-omogeneo|sistema omogeneo]] che identifica il [[nucleo|nucleo]], quindi fornendo delle equazioni che "producono" queste soluzioni[^2];

## Passaggi
### $2 \longrightarrow 1$
Passare dall'insieme delle soluzioni di tale sistema omogeneo all'insieme di generatori è facile:
1. date le equazioni costruiamo la [[applicazione-lineare-definita-da-una-matrice|matrice associata]] $A$ attraverso le [[immagine-di-funzione|immagini]] della [[base-canonica|base canonica]] di $\mathbb{R}^{n}$;
2. scriviamo la matrice del sistema $A\underline{x} = \underline{0}$ associata e riduciamo a scala con Gauss;
3. raccogliamo i parametri o semplicemente poniamo quelli di riferimento a 1 e tutti gli altri a 0, ottenendo l'**insieme generatore delle soluzioni del sistema**.

### $1 \longrightarrow 2$
Per passare invece da un insieme generatore alle equazioni che identificano lo spazio generato, bisogna procedere nel seguente modo:
1. consideriamo il sistema lineare associato alla matrice che ha per colonne i vettori generatori $v_{1}, \cdots, v_{k}$, e come colonna dei termini noti $x_{1}, \cdots, x_{n}$;
2. riduciamo a scala con Gauss e imponiamo $r(A) = r(A|\underline{b})$;
3. ciò che ne risulta sono le **equazioni cartesiane**.

<u>Nota bene</u>: se lo _spazio $V$ è uguale a uno spazio euclideo $\mathbb{R}^{n}$_ (es. $\mathbb{R}^{4}$), allora l'_insieme delle equazioni cartesiane è l'[[definizione-di-insieme-vuoto|insieme vuoto]]_, perché affinché un vettore $\underline{x} = (x_{1}, \cdots, x_{n})$ appartenga a $V = \mathbb{R}^{n}$ non c'è alcuna condizione da imporre su $x_{1}, \cdots, x_{n}$.

<u>Nota bene</u>: **ogni equazione cartesiana abbassa di 1 la dimensione di $V$ rispetto allo spazio euclideo di riferimento**.

#### Esempio
Prendiamo lo spazio $V = \langle (1, 1, 0, 3), (2, 2, 1, 3) \rangle = \langle v_{1}, v_{2} \rangle$ (non devono per forza essere base di $V$). Ci chiediamo quando un vettore $\underline{x} = (x_{1}, x_{2}, x_{3}, x_{4})$ appartiene a $V$. Per la definizione di sottospazio generato abbiamo che
$$\underline{x} \in V \iff \exists \lambda_{1}, \lambda_{2} \in \mathbb{R} | \underline{x} = \lambda_{1}v_{1} + \lambda_{2}v_{2}$$
ovvero se $\exists \lambda_{1}, \lambda_{2} : (x_{1}, x_{2}, x_{3}, x_{4}) = \lambda_{1}(1, 1, 0, 3) + \lambda_{2}(2, 2, 1, 3)$.

Scriviamo il sistema associato:
$$\begin{cases} x_{1} = \lambda_{1}+2\lambda_{2} \\ x_{2} = \lambda_{1}+2\lambda_{2} \\ x_{3} = \lambda_{2} \\ x_{4} = 3\lambda_{1}+3\lambda_{2} \end{cases}$$

Queste si dicono **equazioni parametriche** di $V$, perché al variare di $\lambda_{1}, \lambda_{2} \in \mathbb{R}$ si ottengono tutti i vettori di $V$. Ma noi non vogliamo sapere per quali di questi $\lambda_{1}, \lambda_{2}$ tali equazioni sono verificate, bensì **quali condizioni su $x_{1}, x_{2}, x_{3}, x_{4}$ devono essere applicate per consentire a una eventuale combinazione di $\lambda_{1}, \lambda_{2}$ (una o infinite che siano) di far appartenere $\underline{x}$ a $V$**. L'obiettivo è allora di passare da queste equazioni parametriche alle cosiddette equazioni cartesiane.

Scriviamo quindi la matrice associata a tale sistema nelle incognite $\lambda_{1}, \lambda_{2}$:
$$\begin{pmatrix} 1 & 2 & x_{1} \\ 1 & 2 & x_{2} \\ 0 & 1 & x_{3} \\ 3 & 3 & x_{4} \end{pmatrix}$$
Questa, ridotta a scala, diventa
$$\begin{pmatrix} 1 & 2 & x_{2} \\ 0 & 1 & x_{3} \\ 0 & 0 & x_{2}-x_{1} \\ 0 & 0 & x_{4}-3x_{1}+3x_{3} \end{pmatrix}$$

Perciò, affinché il sistema abbia soluzione dobbiamo avere $rr(A) = rr(A|\underline{b})$, e questo avviene $\iff$
$$x_{2}-x_{1} = 0 \land x_{4}-3x_{1}+3x_{3} = 0$$
o, scritto meglio a sistema,
$$\begin{cases} x_{2}-x_{1} = 0 \\ x_{4}-3x_{1}+3x_{3} = 0 \end{cases}$$

Ecco che queste sono le equazioni cartesiane di $V$, perché identificano i criteri affinché un vettore $\underline{x} = (x_{1}, x_{2}, x_{3}, x_{4})$ appartenga a $V$.

Di solito si scrive allora che
$$V = \{(x_{1}, x_{2}, x_{3}, x_{4}) \in \mathbb{R}^{4} | x_{2}-x_{1}=0, x_{4}-3x_{1}+3x_{3}=0\}$$

<u>Nota bene</u>: si riconferma l'osservazione sulla dimensione di $V$. Infatti $V \leq \mathbb{R}^{4}$, e il numero di equazioni cartesiane è $2$. Infatti $\dim(V) = \dim(\mathbb{R}^{4})-2 = 2$.

## Referenze