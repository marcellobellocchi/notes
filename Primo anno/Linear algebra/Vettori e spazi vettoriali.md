# Vettori

Come abbiamo visto, i vettori non sono altro che matrici composte da una colonna o una riga. I vettori però, come sappiamo dalla fisica, hanno anche una rappresentazione geometrica e spaziale.

>[!tip]+ I vettori in geometria
>In geometria, i vettori possono essere definiti come rappresentazioni di spostamenti, quindi i punti in cui iniziano e finiscono non sono considerati nel confronto fra di loro.
>I componenti di un vettore sono quindi **magnitudine** e **direzione**

La magnitudine è il valore effettivo del vettore, o geometricamente la sua lunghezza.

Un vettore che si estende da ($a_1, a_2$) a ($b_1, b_2$) viene quindi descritto come:
$$
\begin{pmatrix}
b_1 - a_1 \\
b_2 - a_2
\end{pmatrix}
$$
L'angolo fra due vettori è invece pari a:
$$
arccos\left(\frac{\vec{u}\cdot\vec{v}}{\rvert\vec{u}\lvert\rvert\vec{v}\lvert}\right)
$$
Due vettori sono perpendicolari fra di loro se la loro moltiplicazione scalare è pari a 0; sono invece paralleli se la loro moltiplicazione scalare è pari alla moltiplicazione delle loro magnitudini
# Spazi vettoriali

>[!tip]+ Definizione
>Uno spazio vettoriale (su $\mathbb{R}$) è un insieme di vettori che possono essere sommati fra loro e moltiplicati per scalari, rispettando queste condizioni:
>1. La somma di due vettori appartenenti allo spazio vettoriale appartiene ancora allo stesso spazio vettoriale
>2. Cambiando l'ordine della somma di vettori, il risultato non cambia
>3. Quando si sommano più vettori, il moo in cui essi vengono sommati non cambia il risultato
>4. Esiste un vettore $\vec{0}$ che, se sommato a qualsiasi vettore, lo lascia invariato
>5. Ogni vettore ha il suo opposto, e se esso viene sommato al vettore iniziale, restituisce il vettore nullo
>6. Moltiplicando un vettore per uno scalare, si ottiene comunque un vettore appartenente allo spazio vettoriale
>7. Moltiplicare un vettore per la somma di due scalari equivale a moltiplicarlo separatamente per ciascuno scalare per poi sommare i risultati
>8. Moltiplicare per uno scalare la somma di due vettori equivale a moltiplicare ciascun vettore per quello scalare per poi sommarli
>9. Moltiplicare uno scalare per il risultato della moltiplicazione di un altro scalare per un vettore equivale a moltiplicare i due scalari fra loro per poi moltiplicarli al vettore
>10. Moltiplicare un vettore per lo scalare 1 lo lascia invariato

Tutte queste condizioni, analizzandole sotto la superficie, sono in realtà abbastanza elementari, e già riscontrate per le normali operazioni in $\mathbb{R}$. 
Uno spazio vettoriale da un elemento è denominato *trivial space*, o banale in italiano, ma non esiste spazio vettoriale senza elementi, in quanto non rispetta alcune delle condizioni (nello specifico, la condizione per cui lo spazio vettoriale deve sempre contenere $\vec{0}$, condizione 4. Da questo segue che lo spazio vettoriale trivial contiene solo $\vec{0}$).

Di uno spazio vettoriale possono esistere anche i sottospazi, che sono sottoinsiemi di altri spazi vettoriali, di cui ereditano le operazioni. Molti spazi vettoriali sono infatti sottospazi di $\mathbb{R}^n$, e ne ereditano le sue operazioni di moltiplicazione e somma. Tutti gli spazi vettoriali hanno il loro sottospazio trivial che contiene solo $\vec{0}$. Un sottospazio che non contiene tutti gli elementi del suo spazio vettoriale maggiore è detto sottospazio proprio, mentre in caso contrario sono definiti impropri.

Uno spazio generato (o *span*) è l'insieme di tutte le possibili combinazioni lineari dei vettori in uno spazio vettoriale. Dati i vettori $v_1, v_2, \cdots, v_n$, il loro span si definisce come:
$$
\operatorname{span}(v_1,\ldots,v_n)
=
\left\{
\sum_{i=1}^n\lambda_i v_i
\;\middle|\;
\lambda_i\in\mathbb{R}
\right\}
$$
dove $\lambda_1,\cdots,\lambda_n$ sono scalari reali. In altre parole, moltiplichiamo ciascun vettore per uno scalare e sommiamo i risultati.
Se si calcola lo span di un qualsiasi sottoinsieme si uno spazio vettoriale, esso è un sottospazio dell'originale spazio vettoriale. Questo perchè calcolando soltanto le possibili combinazioni vettoriali si eliminano i componenti che violano le regole che non consentono al sottoinsieme di essere un sottospazio.
### Indipendenza lineare

>[!tip]+ Definizione
>In uno spazio vettoriale, un insieme di vettori è linearmente indipendente se nessuno dei suoi elementi è una combinazione lineare degli altri nell'insieme, altrimenti è linearmente dipendente. 

Due (o più) vettori possono essere in una relazione lineare nel caso siano una combinazione lineare dell'altro.
Un sottoinsieme di uno spazio vettoriale è linearmente indipendente se e solo se l'unica relazione lineare con il vettore $\vec{0}$ sia quella in cui i coefficienti sono 0. Nel caso in cui questo non fosse vero infatti, ci sarebbero due vettori dal coefficiente opposto che sarebbero in relazione lineare con il vettore $\vec{0}$. È sufficiente verificare questa condizione per il vettore nullo, perchè esso ci permette di verificare se uno dei vettori può essere ricavato da altri attraverso una combinazione lineare. 
Nelle matrici in forma a scala, sono linearmente indipendenti le righe diverse da 0. In uno spazio vettoriale composto da 3 vettori, un modo semplice per vedere se lo spazio è linearmente indipendente è se il terzo vettore è due volte il primo più il secondo.

# Teoremi sullo spazio generato

>[!info]+ Definizione
>Dove V è uno spazio vettoriale, S è un sottoinsieme dello spazio, e $\vec{v}$ è un elemento dello spazio, $[S \cup \{\vec{v}\}] = [S] \iff \vec{v} \in [S]$

Quindi, aggiungere un vettore a un insieme non cambia lo spazio generato se e solo se quel vettore appartiene già allo spazio generato dall'insieme.
In un insieme linearmente indipendente, la sola aggiunta di un vettore non lo rende linearmente dipendente: ciò invece dipende dal contenuto del vettore, e se altera le condizioni nella proprietà fondamentale dell'indipendenza lineare.
A causa di questo teorema, segue che l'eliminazione di un vettore $\vec{v}$ a uno span S non riduce S se e solo se $\vec{v}$ è in relazione lineare con altri vettori in S. Pertanto, S è linearmente indipendente se la rimozione di qualsiasi suo vettore riduce S.
In uno spazio vettoriale, ogni insieme finito di vettori contiene quindi un sottoinsieme linearmente indipendente che genera la stessa span. Questo succede perché la span descrive le combinazioni lineari possibili in un insieme, e quindi è sufficiente selezionare quei vettori che possono generare le combinazioni lineari possibili.
Un sottoinsieme di un insieme linearmente indipendente è linearmente indipendente, mentre un superinsieme di un insieme linearmente dipendente è anche esso linearmente dipendente.


>[!info]+ Definizione
>Un insieme $S=\{\vec{s}_1,\cdots,\vec{s}_n\}$ è linearmente dipendente se e solo se almeno un vettore $\vec{s}_i$ è una combinazione lineare dei vettori che lo precedono, ovvero $\vec{s}_1,\cdots,\vec{s}_{i-1}$

Prendiamo come esempio $\vec{a}=\begin{pmatrix}1 \\ 0 \end{pmatrix}, \vec{b}=\begin{pmatrix}0 \\ 1 \end{pmatrix}, \vec{c}=\begin{pmatrix}1 \\ 1 \end{pmatrix}$. Vediamo chiaramente come c sia uguale ad a + b, ma se posizioniamo in un insieme $S=\{\vec{a}, \vec{b}, \vec{c}\}$ allora $\vec{c}=\vec{a}+\vec{b}$, mentre se nell'insieme invertiamo le posizioni di c e b, allora $\vec{b}=\vec{c}-\vec{a}$, ma queste relazioni valgono solo per un sistema in base all'ordine degli elementi.
