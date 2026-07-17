---
tags:
  - category/note
  - status/finished
  - topic/algebra-e-geometria
date: 17-03-2024 13:34:17
links:
  - "[[lecture-14032024111404|Lecture 14032024111404]]"
---
# Teorema di esistenza e unicità di un'applicazione lineare
---
## Introduzione
> Il **teorema di esistenza e unicità di un'[[applicazione-lineare|applicazione lineare]]** afferma che dati $V, W$ [[spazio-vettoriale|spazi vettoriali]], $\beta = \{v_{1}, \cdots, v_{n}\}$ [[base|base]] di $V$ e $w_{1}, \cdots, w_{n} \in W$ vettori _non necessariamente distinti_[^1], allora si ha che _esiste un'unica applicazione lineare $f: V \to W$_ t.c.
> $$f(v_{1}) = w_{1}, \cdots, f(v_{n}) = w_{n}$$

## Dimostrazione
### Esistenza
Sappiamo che $V$ e $W$ sono due spazi vettoriali, che $\beta = \{v_{1}, \cdots, v_{n}\}$ è base di $V$ e che $w_{1}, \cdots, w_{n} \in W$. Dobbiamo dimostrare che $\exists f: V \to W | f(v_{1}) = w_{1}, \cdots, f(v_{n}) = w_{n}$.

Scelgo allora come _$f$ una funzione che proietta le [[coordinate-rispetto-a-una-base|coordinate rispetto alla base]] $\beta$ di $v \in V$ a un vettore $w \in W$_. Vale a dire che prendendo $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$, possibile perché $v_{1}, \cdots, v_{n}$ base, e quindi $(v)_{\beta} = (\lambda_{1}, \cdots, \lambda_{n})$, posso definire $f$ come
$$f(v) = \lambda_{1}w_{1} + \cdots + \lambda_{n}w_{n}$$

Dimostro allora che $f$ è lineare.

Per dimostrare che $f$ rispetta la somma prendo due vettori $v, u \in V$ t.c. $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$ e $u = \mu_{1}v_{1} + \cdots + \mu_{n}v_{n}$, e dimostro $f(v+u) = f(v)+f(u)$. Ho che
$$v+u = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n} + \mu_{1}v_{1} + \cdots + \mu_{n}v_{n} = (\lambda_{1} + \mu_{1})v_{1} + \cdots + (\lambda_{n} + \mu_{n})v_{n}$$
per cui $(v + u)_{\beta} = (\lambda_{1}+\mu_{1}, \cdots, \lambda_{n}+\mu_{n})$, e allora
$$f(v + u) = (\lambda_{1}+\mu_{1})w_{1} + \cdots + (\lambda_{n}+\mu_{n})w_{n} = \lambda_{1}w_{1} + \cdots + \lambda_{1}w_{n} + \mu_{1}w_{1} + \cdots + \mu_{n}w_{n} = f(v) + f(u)$$

Per dimostrare che $f$ rispetta il prodotto per scalare prendo un vettore $v \in V$ t.c. $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$ e uno scalare $\mu \in \mathbb{R}$ e dimostro $f(\mu v) = \mu f(v)$. Ho che
$$\mu v = \mu\lambda_{1}v_{1} + \cdots + \mu\lambda_{n}v_{n}$$
per cui $(\mu v)_{\beta} = (\mu\lambda_{1}, \cdots, \mu\lambda_{n})$, e allora
$$f(\mu v) = \mu\lambda_{1}w_{1} + \cdots + \mu\lambda_{n}w_{n} = \mu(\lambda_{1}w_{1} + \cdots + \lambda_{n}w_{n}) = \mu f(v)$$

### Unicità
Per dimostrare che questa $f$ è unica, suppongo di avere un'altra funzione lineare $g: V \to W | g(v_{1}) = w_{1}, \cdots, g(v_{n}) = w_{n}$, e dimostro $g = f$, e quindi $g-f = \underline{0}$.

Mi definisco allora una funzione $h: V \to W$ definita come $v \to g(v)-f(v)$, e dimostro $\ker(h) = V$. Allora fissato un $v \in V$ devo dimostrare che $v \in \ker(h)$, il che è sufficiente perché per definizione di kernel so $\ker(h) \subseteq V$. Definisco $v = \lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}$, e dimostro
$$h(\lambda_{1}v_{1} + \cdots + \lambda_{n}v_{n}) = \underline{0}$$
che, sapendo $h$ essere lineare in quanto composizione di due funzioni lineari $g, f$, diventa
$$h(\lambda_{1}v_{1}) + \cdots + h(\lambda_{n}v_{n}) = \underline{0}$$

Ora, so che $h(v) = g(v)-f(v)$, per cui dimostro
$$g(\lambda_{1}v_{1}) - f(\lambda_{1}v_{1}) + \cdots + g(\lambda_{n}v_{n}) - f(\lambda_{n}v_{n}) = \underline{0}$$

Uso la linearità di $g, f$ per ottenere
$$\lambda_{1}g(v_{1}) - \lambda_{1}f(v_{1}) + \cdots + \lambda_{n}g(v_{n}) - \lambda_{n}f(v_{n}) = \lambda_{1}(g(v_{1}) - f(v_{1})) + \cdots + \lambda_{n}(g(v_{n}) - f(v_{n})) = \underline{0}$$

Per definizione di $g$ e $f$ so che $g(v_{1}) = w_{1}, \cdots, g(v_{n}) = w_{n}$ e $f(v_{1}) = w_{1}, \cdots, f(v_{n}) = w_{n}$, e questo mi consente di concludere perché
$$\lambda_{1} (w_{1} - w_{1}) + \cdots + \lambda_{n} (w_{n} - w_{n}) = \lambda_{1}\underline{0} + \cdots + \lambda_{n}\underline{0} = \underline{0}$$

Ho ottenuto allora che $\ker(h) = V$, e perciò che $h(v) = g(v)-f(v) = \underline{0} \ \ \ \forall v \in V$, e quindi $g-f = \underline{0}$, da cui
$$g = f$$

**Qed**.

## Corollario
Il teorema è estremamente importante perché **mette in luce la "forza" della linearità**. Se di un'applicazione lineare $f: V \to W$ _conosco le [[immagine-di-funzione|immagini]] della base_, canonica o meno che sia, _conosco direttamente anche tutta $f$_!

In termini tecnici si riassume questa proprietà con la seguente proposizione:
> Siano $V, W$ due spazi vettoriali. Se due applicazioni lineari $T, S: V \to W$ _coincidono su di una base di $V$_, allora _coincidono su tutto $V$_.

In particolare questo si sposa bene con l'[[applicazione-lineare-definita-da-una-matrice|applicazione lineare definita da una matrice]]: $L_{A}$.

## Significato
Prendiamo lo spazio euclideo $\mathbb{R}^{2}$, il piano cartesiano. Preso un punto $(a, b) \in \mathbb{R}^{2}$ so che esiste ed è unica una retta passante per l'origine e per $(a, b)$: questa retta è l'applicazione lineare, e ciò è una conseguenza diretta del teorema, che sappiamo valere per spazi di dimensione anche superiore a $2$! Presi due punti di $\mathbb{R}^{3}$, per esempio, sappiamo che esiste ed è unico il piano passante per l'origine e quei due punti.

## Referenze
[^1]: questa condizione non necessaria permette ad $f$ di non essere per forza [[funzione-iniettiva|iniettiva]]