---
tags:
  - category/note
  - status/finished
  - topic/analisi-I
  - topic/algebra-e-geometria
date: 24-09-2023 15:21:37
links:
  - "[[lecture-22092023133316|Lecture 22092023133316]]"
  - "[[lecture-09042024091802|Lecture 09042024091802]]"
---
# Funzione inversa
---
## Definizione
> Una [[funzione-matematica|funzione]] si dice **invertibile** se invertendo _legge di associazione_, _dominio_ e _codominio_ la funzione rimane valida. Quindi se
> $$\exists f^{-1}: C \to D | \forall d \in D: f^{-1}(f(d))=b \land \forall c \in C: f(f^{-1}(b))=a$$
> o in altri termini una funzione $f: A \to B$ è invertibile quando
> $$\exists g: B \to A \ \ \text{ t.c. } \ \ g \circ f = id_{A} \land f \circ g = id_{B}$$
> ovvero quando la composizione $g \circ f$ dà l'[[funzione-identita|identità]] del dominio $A$, e $f \circ g$ l'identità del codominio $B$.

<u>Osservazione</u>:
> $f$ è invertibile $\iff$ $f$ è [[funzione-biiettiva|biunivoca]] (per cui [[funzione-iniettiva|iniettiva]] e [[funzione-suriettiva|suriettiva]])

![[funzione-invertibile.png]]
## Referenze