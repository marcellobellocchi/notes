>[!info] Problemi lineari
>Un problema lineare è un problema matematico in cui si studiano diversi elementi matematici, quali vettori, trasformazioni o sistemi di equazioni lineari cercando di trovare relazioni che soddisfano determinate condizioni. Tali relazioni sono le soluzioni di un problema lineare. In particolare, un problema è lineare quando le sue variabili sono alla prima potenza e non vengono moltiplicate fra loro.

Data questa definizione, sono diversi i metodi di risoluzione dei problemi lineari. Definiamo però prima le tipologie di problemi lineari.

## I sistemi lineari

Un sistema lineare ha la forma $a_1x_1 + a_2x_2 + a_3x_3 + \cdots + a_nx_n$ dove i numeri $a_1, \cdots, a_n \in \mathbb{R}$ sono detti i coefficienti della combinazione. Se in un equazione, il termine numerale ( a destra dell'uguale ) è detto costante. Una n-tupla $\left(s_1, s_2, \cdots, s_n\right) \in \mathbb{R}^n$ è una soluzione, o soddisfa, un equazione laddove la sostituzione degli elementi della tupla con la variabile restituisce una proposizione vera. Un sistema di equazioni lineari ha le soluzioni $\left(s_1,s_2,\cdots,s_n\right)$ se quella n-tupla è una soluzione per tutte le equazioni.

Per risolvere questo tipo di sistemi, si usa comunemente il metodo di gauss per la riduzione gaussiana. Esso procede con sostituzioni, eliminazioni e altri strumenti per arrivare al risultato finale. Tale risultato non deve però essere cambiato dai procedimenti svolti. Con questa limitazione, sono quindi consentite tre operazioni:
1. Un equazione è scambiata di posizione con un altra nel sistema
2. Un equazione ha tutti e due i lati moltiplicati per una costante diversa da 0
3. Un equazione è rimpiazzata con la somma di sé stesso e un multiplo di un altra equazione del sistema
Queste sono dette le operazioni Gaussiane, ma hanno diversi altri sinonimi

I sistemi possono avere infinite soluzioni reali. Generalmente, ne hanno infinite dove esistono più variabili che equazioni. In questo caso, una variabile deve essere scelta come parametro del risultato:
$$
x = 2 + 3t, \qquad t\in\mathbb{R}
$$
Allo stesso modo, i sistemi possono non avere soluzioni reali.

Per poter risolvere facilmente un sistema, si cerca di raggiungere la cosiddetta **forma a scala**
Questa è una forma in cui la prima variabile a sinistra, detta *leading* o variabile principale, diviene la variabile subito dopo la leading nell'equazione superiore nel sistema. Assumerà quindi una simile forma:
$$
\begin{cases}
x + 2y - z = 4 \\
\phantom{x +{}} y + 3z = 2 \\
\phantom{x + 2y -{}} z = 1
\end{cases}
$$
le variabili non-leading sono dette *free* o variabili libere.
In questa forma, è sufficiente sostituire la variabile nell'equazione risolta (in questo caso, $z=1$) per risolvere a catena le variabili superiori nel sistema

Un sistema può invece essere definito **omogeneo** quando le costanti (i numeri dopo l'uguale) sono uguali a zero.

## Matrici e vettori

>[!tip] Definizione
>Una matrice m * n è una tabella rettangolare di numeri con m righe e n colonne. Ogni numero nella matrice è denominato **elemento**

Una matrice appare con la seguente forma generica:
$$
A =
\begin{pmatrix}
a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m,1} & a_{m,2} & \cdots & a_{m,n}
\end{pmatrix}
$$
dole la riga e la colonna appaiono al pedice dell'elemento separati da una virgola.

Un vettore è semplicemente una matrice con una singola riga o una singola colonna. I suoi elementi sono denominati **componenti**. Un vettore i cui componenti sono tutti uguali a zero è denominato vettore zero. I vettori possono essere identificati con una freccia sopra la lettera che li rappresenta.

Le matrici possono essere sfruttate in diversi modi. uno fra questi è una rappresentazione più efficiente di sistemi lineari.

Esempio:
$$
\begin{cases}
2x + y - z = 3 \\
x - 2y + 3z = 1 \\
3x + y + 2z = 7
\end{cases}
\quad\Longrightarrow\quad
\left(
\begin{array}{ccc|c}
2 & 1 & -1 & 3 \\
1 & -2 & 3 & 1 \\
3 & 1 & 2 & 7
\end{array}
\right)
$$
in questo modo, anche i risultati del sistema possono essere rappresentati da una matrice.

Una matrice quadrata è definita regolare se è la matrice dei coefficienti di un sistema omogeneo con unica soluzione (come definito nel [[I lemmi e i teoremi#Corollario|corollario]] del primo teorema analizzato nel documento [[I lemmi e i teoremi]]). Contrariamente, è definito singolare se è la matrice dei coefficienti di un sistema con soluzioni infinite.