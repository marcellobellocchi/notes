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

[^1]:Il Least Significant bit determina se un numero è pari (se vale 0) o dispari, dato che vale sempre 1 convertito in decimale.

# Le operazioni

Per operare sistemi digitali, è necessario trovare sistemi per fare operazioni direttamente in codice binario. Questo è molto semplice con numeri interi