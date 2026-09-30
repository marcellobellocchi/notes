>[!info] Definizione
>Una funzione matematica è una relazione che associa a ogni elemento di un insieme di partenza uno e un solo elemento di un insieme di arrivo.

Si scrive, ad esempio
$$
f: A \rightarrow B
$$
dove **A** è il dominio ( il nome dell'insieme di partenza ) e **B** è il codominio ( o il nome dell'insieme di arrivo ). $f\left(x\right)$ è il valore che la funzione associa a x. A ogni numero x corrisponde uno e un solo risultato, ad esempio $f\left(3\right) = 7$. Esistono funzioni che violano quest'ultima proprietà, denominate multivoche, che però non sono discusse in questo corso.

Essendo una relazione fra insiemi, il dominio e il codominio presentano estremi. Questi dipendono dalle caratteristiche della funzione e dai valori che la funzione può assumere. L'immagine di una funzione sono invece i valori che la funzione raggiunge effettivamente nel codominio. Alcuni esempi di funzioni e i loro insiemi.
$$
\begin{array}{|c|c|c|c|c|}
\hline
\textbf{Tipo di funzione}
& \textbf{Condizioni di esistenza}
& \textbf{Dominio}
& \textbf{Codominio}
& \textbf{Immagine}
\\
\hline

\text{Costante } f(x)=c
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& \{c\}
\\
\hline

\text{Identità } f(x)=x
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& \mathbb{R}
\\
\hline

\text{Polinomiale } f(x)=a_nx^n+\cdots+a_0
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& \operatorname{Im}(f)
\\
\hline

\text{Razionale intera } f(x)=ax+b
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& \mathbb{R}\quad(a\neq0)
\\
\hline

\text{Frazionaria } f(x)=\frac{P(x)}{Q(x)}
& Q(x)\neq0
& \{x\in\mathbb{R}:Q(x)\neq0\}
& \mathbb{R}
& \operatorname{Im}(f)
\\
\hline

\text{Radicale pari } f(x)=\sqrt[2n]{g(x)}
& g(x)\geq0
& \{x\in\mathbb{R}:g(x)\geq0\}
& \mathbb{R}
& [0,+\infty)
\\
\hline

\text{Radicale dispari } f(x)=\sqrt[2n+1]{g(x)}
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& \operatorname{Im}(f)
\\
\hline

\text{Potenza } f(x)=x^\alpha
& \text{dipende da }\alpha
& \operatorname{Dom}(f)
& \mathbb{R}
& \operatorname{Im}(f)
\\
\hline

\text{Esponenziale } f(x)=a^x
& a>0,\ a\neq1
& \mathbb{R}
& \mathbb{R}
& (0,+\infty)
\\
\hline

\text{Logaritmica } f(x)=\log_a x
& a>0,\ a\neq1,\ x>0
& (0,+\infty)
& \mathbb{R}
& \mathbb{R}
\\
\hline

\text{Valore assoluto } f(x)=|x|
& \text{nessuna}
& \mathbb{R}
& \mathbb{R}
& [0,+\infty)
\\
\hline
\end{array}
$$

Le funzioni possono essere rappresentate in grafici, e ognuna di queste funzioni elencate sopra ha caratteristiche particolari sui grafici. 
Una funzione può essere descritta con diverse caratteristiche e valori particolari:
1. **Zeri**: gli zeri di una funzione è dove la funzione è $f\left(x\right) = 0$
2. **Segno**: la funzione è positiva se $f\left(x\right) \geq 0$, altrimenti è negativa.
3. **Monotonia**: la funzione è crescente se $x_1<x_2\rightarrow f\left(x_1\right)\leq f\left(x_2\right)$, sarà decrescente se $x_1>x_2\rightarrow f\left(x_1\right)\geq f\left(x_2\right)$
4. **Simmetria**: una funzione può essere pari se $f\left(-x\right) = f\left(x\right)$, dispari se $f\left(-x\right) = -f\left(x\right)$, ma può anche non essere nessuna delle due. Una funzione pari sarà simmetrics rispetto all'asse y, mentre una dispari è simmetrica rispetto all'origine. Il loro dominio rispecchia questa simmetria.

Le funzioni possono anche essere traslate: una funzione $f\left(x-h\right) + k$, dove $h,k\in\mathbb{R}$, sarà spostata a destra di $h$ e in alto di $k$

##### Funzioni inverse 

Prima di definire le funzioni inverse, dobbiamo conoscere i concetti di iniettività e suriettività. Una funzione si dice **iniettiva** laddove tutti i valori di $x$ danno valori di $y$ diversi; non potrà quindi esistere in una funzione iniettiva due valori come $f\left(3\right) = 7$ e $f\left(5\right) = 7$. Una funzione **suriettiva** è invece una funzione la cui immagine  assume tutti i valori del codominio. Una funzione è **biiettiva** quando rispetta sia la suriettività che la iniettività. Si possono anche selezionare intervalli in cui una funzione è suriettiva, iniettiva o biiettiva.

Le funzioni possono essere invertite solo se esse sono iniettive. Questo per la stessa definizione di una funzione: quello che in una funzione normale è $y$, in una funzione inversa è $x$, questo comporterebbe più $x$ che restituiscono un valore $y$, violando questa regola.

Una funzione inversa restituisce x se l'argomento è la funzione di origine:
$$
f^{-1} \left(f\left(x\right)\right) = x
$$
questa è chiamata **identità** della funzione.

##### Sequenze numeriche

Mentre le funzioni sono un sottoinsieme di $\mathbb{R}$, le sequenze numeriche invece si estendono solo in $\mathbb{N}$. Questo risulta in un grafico a "punti", invece che la linea continua che le funzioni restituiscono
