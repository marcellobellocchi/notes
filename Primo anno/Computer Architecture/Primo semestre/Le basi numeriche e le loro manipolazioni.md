# Le basi numeriche

Sin dall'inizio, ci si è resi conto che l'utilizzo del sistema decimale in dispositivi elettronici era impraticabile: si è quindi reso necessario l'uso di un sistema alternativo. La scelta è quindi caduta sul sistema binario.

>[!tip] Il sistema binario
>Il sistema binario è una base che permette l'utilizzo di due valori: 0 e 1.
>Questi numeri rappresentano l'assenza (0) o la presenza (1) di voltaggio in un transistor, che viene aperto o chiuso in base a questi valori.
>

Nel tempo si sono provati anche altre basi alternative, con poco successo.
Il codice binario è posizionale: questo vuol dire che, come nel sistema decimale, la posizione di un numero nella sequenza determina il suo valore. Per ottenere l'equivalente di un numero binario in decimale, bisogna moltiplicare il numero per 2 alla potenza della posizione in cui si trova il numero, iniziando da 0.
$$
0111\quad\rightarrow\quad 0\times2^3 + 1\times2^2 + 1\times2^1 + 1\times2^0 = 7
$$
Per ottenere invece un numero binario da un numero decimale, si può invece usare questo metodo:
$$
\begin{array}{c|c|c}
\text{Divisione} & \text{Quoziente} & \text{Resto} \\ \hline
53 \div 2 & 26 & 1 \\
26 \div 2 & 13 & 0 \\
13 \div 2 & 6  & 1 \\
6 \div 2  & 3  & 0 \\
3 \div 2  & 1  & 1 \\
1 \div 2  & 0  & 1
\end{array}
$$
una volta ottenuti questi numeri, si posiziona il resto in modo che l'ultimo resto sia in prima posizione, quella più a sinistra ( denominata Most Significant Bit, MSB ), e il primo sia invece nella posizione più a destra ( Least Significant Bit, LSB )[^1]. Si ottiene dunque:
$$
53_{10}\quad\rightarrow\quad110101_{2}
$$
I numeri a pedice stanno a rappresentare la base usata.

Per rappresentare gruppi di 4 bit, viene anche usato il sistema esadecimale, o base 16. I numeri da 0 a 9 sono rappresentati dagli stessi numeri del sistema decimale, mentre assumono un ruolo anche le lettere, dove le lettere da A a F assumono valori da 10 a 15. Se prendiamo quindi un numero come $9AEF$, starà a rappresentare il numero $39663$. Per convertire da esadecimale a decimale si procede in modo analogo da binario a decimale, sostituendo la base della potenza che moltiplica con 16.
$$
9AEF\quad\rightarrow\quad9\times16^3 + 10\times16^2 + 14\times16^1 + 15\times16^0 = 39663
$$
Ogni numero in sistema esadecimale rappresenta 4 bit binari, occupandoli allo stesso modo in cui un numero decimale li occuperebbe.

[^1]:Il Least Significant bit determina se un numero è pari (se vale 0) o dispari, dato che vale $2^0$, ovvero 1.

# Rappresentazione di numeri negativi

I numeri con segno sono detti **signed**, mentre quelli senza segno, discussi fino ad ora, sono detti **unsigned**. Due strategie sono state create nel tempo per confrontare il problema della rappresentazione di numeri *signed*.

La prima strategia è detta *sign/magnitude*. è una strategia meno usata in quanto con questa rappresentazione non è possibile eseguire operazioni. In questa rappresentazione, l'MSB rappresenta il segno, con 0 di significato positivo e 1 negativo. La rappresentazione è denominata in questo modo perchè il primo bitt è detto sign bit, e il resto sono i magnitude bit. Il range di numeri rappresentabili in questa rappresentazione è $[-2^{n-1}+1, 2^{n-1}-1]$ , dove n rappresenta il numero di bit meno uno ( per la cronaca, i numeri signed hanno il range $[0, 2^{n-1}]$ ).

Il secondo metodo, utilizzato nella pratica, è denominato *complemento a due* ( o two's complement ). Anche in questa rappresentazione l'MSB rappresenta il segno, ma i restanti bit non sono semplicemente il numero positivo equivalente. per ottenere da un numero positivo l'equivalente negativo, e viceversa, bisogna usare il valore opposto per ogni bit e aggiungere uno
$$
0110\quad\rightarrow\quad1001 + 1 = 1010
$$
con questa rappresentazione, si possono eseguire le operazioni. Per questo motivo, è quella utilizzata nella pratica. Il range è $[-2^{n-1},2^{n-1}-1]$, ottenendo anche un numero extra rispetto a sign/magnitude, dato che non ci sono due valori per rappresentare lo stesso numero ( in sign/magnitude, 1000 e 0000 valgono entrambi 0 ). Esiste anche almeno un *weird number* in two's complement: in 4 bit, quel numero è -8. Essendoci sempre un numero negativo in più nel range che numeri positivi, scambiare il segno attraverso il metodo mostrato sopra non restituirà 8, ma sempre -8, dato che 8 non è compreso nel range.

Per ottenere il numero di bit necessari a rappresentare un numero, per i numeri unsigned si usa $\lfloor\log_2\left(A\right)\rfloor+1$, mentre per gli signed si usa $\lfloor\log_2\left(A\right)\rfloor+2$, dove A è il numero da rappresentare. 

Laddove non specificato, nel resto dei file, verrà usato il metodo complemento a due per i numeri signed.

# Rappresentazione di numeri frazionari

Ovviamente, per le applicazioni pratiche, serve anche una rappresentazione per i numeri frazionari. Esistono diverse rappresentazioni, ma appartengono tutte a due famiglie: **fixed point** e **floating point**.

>[!tip] Differenza
>I fixed point numer stabiliscono una posizione in cui mettere la virgola che separa i valori interi dai valori decimali. I floating point invece, cambiano questa posizione in base al valore del numero inserito, come vedremo.

Prendendo come esempio una serie signed di bit, con 4 bit che rappresentano la serie decimale e 4 la parte intera, dimostriamo un esempio su come convertire da bit a decimale in un numero fixed point ( In questo caso, si mette -2 invece che due perchè il numero è negativo ):
$$
\begin{array}{c c c c c c c c}
-2^3 & -2^2 & -2^1 & -2^0 & 2^{-1} & 2^{-2} & 2^{-3} & 2^{-4} \\
\downarrow & \downarrow & \downarrow & \downarrow &
\downarrow & \downarrow & \downarrow & \downarrow \\
1 & 1 & 0 & 0 & 1 & 1 & 0 & 0
\end{array}
$$
Per convertire da numero dopo la virgola a rappresentazione in bit, si prende il valore in base decimale e si moltiplica per due. Se il numero è maggiore a 1, il bit corrispondente sarà 1, altrimenti sarà uguale a 0. Poi, si sottrae 1 nel caso il numero fosse stato maggiore a 1, e si procede finchè si arriva a 0. Se non ci sono bit sufficienti alla rappresentazione del numero decimale, i numeri a seguire vengono scartati

Questa è una rappresentazione efficiente dal punto di vista di prestazioni, infatti viene usata nei livelli più bassi di hardware e circuiti, ma non è quella più usata in quanto non è il modo più efficiente di utilizzare i bit per la rappresentazione di numeri decimali.x
Per questo, nei dispositivi moderni, viene usata la rappresentazione floating point. In particolare, lo standard più utilizzato per questo tipo di rappresentazione è definito nell'IEEE 754.
Questo standard ( che d'ora in poi sarà quello a cui ci si riferisce automaticamente nel resto delle citazioni dei floating point ) è definito per dimensioni di 16, 32 e 64 bit. Cambiano soltanto i numeri di bit deicati ai rispettivi spazi, ma ci concentreremo sulla definizione per 32 bit.

I floating point sono separati in 3 sezioni. Il segno (1 bit), L'esponente (8 bit nella definizione da 32 bit) e la mantissa (23 bit nella definizione da 32 bit). La forma appare come $\pm M\times2^E$, dove M è la mantissa e E l'esponente.
Approfondiamo sui singoli gruppi di bit: Il bit del segno, intuitivamente, è uguale a 0 se il numero è positivo e 1 se negativo. L'esponente invece viene memorizzato aggiungendo al vero valore 127. 127, in questa rappresentazione, è detta bias, e l'esponente biase exponent. Questo perchè, in questo modo, non c'è bisogno di un bit dedicato al segno dell'esponente, e il bias è pari a 127 in quanto il massimo numero unsigned rappresentabile con 8 bit è 255.
Bisogna però prestare attenzione al fatto che i valori 00000000 e 11111111 dell'esponente sono riservati rispettivamente a zero/subnormal e infinito/NaN.
La mantissa invece va a rappresentare il numero vero e proprio da rappresentare. Nelle rappresentazioni floading point, la virgola si sposta a destra dell'uno con maggior valore, quindi si avrà $0111,1001\times2^0 \rightarrow 1,111001\times2^2$, oppure $0000,0101\times2^0\rightarrow1,01\times2^{-2}$. Dato che il primo bit sarà sempre uno, nelle rappresentazioni viene in realtà troncato. risulterà quindi un numero con forma simile a questa:
$$
-58.25_{10}
\rightarrow
1.1101001_2\times2^5
\rightarrow
\underbrace{1}_{\text{Segno}}\,
\underbrace{10000100}_{\text{Esponente}}\,
\underbrace{11010010000000000000000}_{\text{Mantissa}}
$$
i bit non usati dal numero rappresentato saranno semplicemente 0 messi a sinistra.
( Ricorda che, nella rappresentazione l'esponente non è uguale a 5 ma a 127 + 5 )
# Le operazioni

Per operare sistemi digitali, è necessario trovare sistemi per fare operazioni direttamente in codice binario. La somma e differenza in codice binario funzionano allo stesso modo che in base 10, sia per base binaria che base esadecimale. bisogna però essere attenti al rischio di overflow: se un numero di riporto eccede il numero massimo di bit disponibili, viene perso, causando l'operazione in questione a essere scorretta ( esempio con numero unsigned ):
$$
1011+0111=0010
$$
il problema è che un numero di riporto viene perso, sbagliando quindi l'operazione. Questo vale sia con somme che con differenze. Con i numeri signed con complemento a due, ci sono alcune particolarità. Due numeri di segno opposto non daranno mai overlflow, è finchè nelle somme o differenze di segno opposto il bit del segno non viene cambiato, non esiste overflow.

Esistono anche delle operazioni dette *bit shifts*, e ne esistono di due tipi: aritmetici e logici. A loro volta i bit shift si dividono verso destra e verso sinistra. I logici hanno tutti e due, gli aritmetici solo a destra. Molto semplicemente, spostano i bit o a destra o a sinistra e rimpiazzano i bit persi con uno specifico valore. I logici, marcati col segno >> ( A>>n e A<<n, dove A sono i bit che subiscono lo spostamento e n di quanto deve essere spostato ) rimpiazzano i bit persi con 0, mentre gli aritmetici ( A>>>n ) rimpiazzano i bit persi con il bit i segno.
$$
0110<<2\quad\rightarrow\quad1000\quad\quad|\quad\quad1000>>>2\quad\rightarrow\quad1110
$$
Il left shift vale come moltiplicazione, in quanto i numeri spostati aumentano di valore, essendo il codice binario un sistema che assegna valore in base alla posizione del numero. Il right shift **aritmetico** invece, vale come divisione, per un motivo analogo al precedente. Questo modo di eseguire divisioni è estremamente efficiente, in contrasto al normale algoritmo di divisione, ma funziona solo per divisioni con divisore pari. Una strategia in sistemi in cui l'efficienza è critica è di cercare di portare il divisore in numero pari proprio per questo motivo.
Ricorda che il left shift logico non ha questo stesso valore di divisione.
##### Estensioni
Laddove si dovesse rivelare necessario avere più bit per rappresentare numeri diversi, si possono estendere usando diverse strategie. Per i numeri unsigned è sufficiente aggiungere 0 a sinistra ( metodo chiamato zero extension ). Altrimenti, si deve aggiungere a sinistra il bit corrispondente al segno del numero:
$$
0110\quad\rightarrow\quad000110\quad\quad|\quad\quad
1011\quad\rightarrow\quad111011
$$
