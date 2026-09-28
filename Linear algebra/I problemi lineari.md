>[!info] Problemi lineari
>Un problema lineare è un problema matematico in cui si studiano diversi elementi matematici, quali vettori, trasformazioni o sistemi di equazioni lineari cercando di trovare relazioni che soddisfano determinate condizioni. Tali relazioni sono le soluzioni di un problema lineare. In particolare, un problema è lineare quando le sue variabili sono alla prima potenza e non vengono moltiplicate fra loro.

Data questa definizione, sono diversi i metodi di risoluzione dei problemi lineari. Definiamo però prima le tipologie di problemi lineari.

#### I sistemi lineari

Un sistema lineare ha la forma $a_1x_1 + a_2x_2 + a_3x_3 + \cdots + a_nx_n$ dove i numeri $a_1, \cdots, a_n \in \mathbb{R}$ sono detti i coefficienti della combinazione. Se in un equazione, il termine numerale è detto costante. Una n-tupla $\left(s_1, s_2, \cdots, s_n\right) \in \mathbb{R}^n$ è una soluzione, o soddisfa, un equazione laddove la sostituzione degli elementi della tupla con la variabile restituisce una proposizione vera. Un sistema di equazioni lineari ha le soluzioni $\left(s_1,s_2,\cdots,s_n\right)$ se quella n-tupla è una soluzione per tutte le equazioni.

Per risolvere questo tipo di sistemi, si usa comunemente il metodo di gauss. Esso procede con sostituzioni, eliminazioni e altri strumenti per arrivare al risultato finale. Tale risultato non deve però essere cambiato dai procedimenti svolti. Con questa limitazione, sono quindi consentite tre operazioni:
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