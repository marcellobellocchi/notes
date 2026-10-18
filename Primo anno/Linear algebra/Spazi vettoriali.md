>[!info]+ Definizione
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

Di uno spazio vettorilale possono esistere anche i sottospazi, che sono sottoinsiemi di altri spazi vettoriali, di cui ereditano le operazioni. Molti spazi vettoriali sono infatti sottospazi di $\mathbb{R}^n$, e ne ereditano le sue operazioni di moltiplicazione e somma. Tutti gli spazi vettoriali hanno il loro sottospazio trivial che contiene solo $\vec{0}$. Un sottospazio che non contiene tutti gli elementi del suo spazio vettoriale maggiore è detto sottospazio proprio, mentre in caso contrario sono definiti impropri.

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
Se si calcola lo span di un qualsiasi sottoinsieme si uno spazio vettoriale, esso è un sottospazio dell'originale spazio vettoriale. Questo perchè calcolando soltanto le possibili combinazioni vettoriali si eliminano i componenti che violano le regole che non consentono al sottoinsieme di essere un sotospazio 