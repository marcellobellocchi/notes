# Basi

>[!info]+ Definizione
> Una base di uno spazio vettoriale è una sequenza di vettori che è linearmente indipendente e che genera lo spazio.

Quindi, lo spazio generato (span) di B è il suo spazio vettoriale annesso. Per denotare una base, si usano le parentesi con angolo, perché l'ordine degli elementi della base denota basi diverse dato che le basi sono sequenze:
$$
\mathbb{R}^n = \langle e_1, \dots, e_n \rangle, \qquad\qquad \mathbb{R}_n[x] = \langle 1, x, \dots, x^n \rangle
$$
La base naturale di qualsiasi $\mathbb{R}^n$ è:
$$
\mathcal{E}_n = \langle\begin{pmatrix} 1 \\ 0 \\ \vdots \\ 0 \end{pmatrix}, \
\begin{pmatrix} 0 \\ 1 \\ \vdots \\ 0 \end{pmatrix}, \cdots, \
\begin{pmatrix} 0 \\ 0 \\ \vdots \\ 1 \end{pmatrix}\rangle
$$
I vettori compresi in $\mathcal{E}_n$ sono denotati come $\vec{e}_1, \cdots, \vec{e}_n$.
Una condizione delle basi è questa:

>[!tip]+ Teorema
>In qualsiasi spazio vettoriale, un sottoinsieme è una base se e solo se ogni vettore dello spazio si può esprimere come combinazione lineare di elementi del sottoinsieme in uno e un solo modo.

In uno spazio vettoriale di base B, la rappresentazione di $\vec{v}$ rispetto a B è la colonna dei coefficienti usati per esprimere $\vec{v}$ come combinazione lineare dei vettori della base.
$$
Rep_B(\vec{v}) = \begin{pmatrix}c_1 \\ c_2 \\ \vdots \\ c_n \end{pmatrix}_B
$$
Dove $B = \langle\vec{\beta}_1,\cdots,\vec{\beta}_n\rangle$ e $\vec{v} = c_1\vec{\beta}_1+c_2\vec{\beta}_2+\cdots+c_n\vec{\beta}_n$. Le c sono le coordinate di $\vec{v}$ rispetto a B.

# Dimensioni

>[!info] Definizione
>Uno spazio vettoriale è di dimensione finita se ha una base con un numero finito di vettori, altrimenti è detto di dimensione infinita. La dimensione di uno spazio vettoriale è data dal numero di vettori in qualsiasi delle sue basi, e tutte le sue basi hanno sempre lo stesso numero di dimensioni.

D'ora in poi, laddove non specificato, uno spazio vettoriale avrà sempre dimensione finita.
Nessun insieme linearmente indipendente può avere una dimensione più grande della dimensione dello spazio vettoriale che lo contiene, ma tutti gli insiemi linearmente indipendenti possono essere espansi per produrre una base