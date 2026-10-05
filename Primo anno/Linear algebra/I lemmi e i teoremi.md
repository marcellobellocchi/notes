Nell'algebra lineare sono usati diversi teoremi e lemmi (che equivalgono a parti minori di teoremi, o loro componenti) per descrivere il comportamento e definire strumenti per affrontare problemi lineari. Esploriamone alcuni.

## Teorema della struttura dell'insieme delle soluzioni di un sistema lineare

>[!info] Enunciato
>Ogni sistema lineare ha la forma
>$$
>\left\{\vec{p} + c_1\vec{b}_1 + \cdots + c_k\vec{b}_k \mid c_1,\ldots,c_k \in
>\mathbb{R}\right\}
>$$
>dove $\vec{p}$ è una qualsiali soluzione particolare e dove il numero di vettori $\vec{b}_1,\cdots,\vec{b}_k$ è uguale al numero di variabili libere che il sistema ha dopo una riduzione gaussiana

Ricordiamo che le variabili libere sono quelle variabili che, dopo una riduzione gaussiana, non hanno una propria colonna nel sistema. Un esempio  di soluzioni di sistemi, e il significato del teorema:
$$
\begin{cases}
x+y+z=3
\end{cases}
\qquad\Longrightarrow\qquad
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}
=
\underbrace{
\begin{pmatrix}
3\\
0\\
0
\end{pmatrix}
}_{\vec p}
+
\underbrace{s}_{c_1}
\underbrace{
\begin{pmatrix}
-1\\
1\\
0
\end{pmatrix}
}_{\vec b_1}
+
\underbrace{t}_{c_2}
\underbrace{
\begin{pmatrix}
-1\\
0\\
1
\end{pmatrix}
}_{\vec b_2},
\qquad s,t\in\mathbb{R}
$$

Questo teorema è dimostrato da due lemmi.

##### Lemma 1

Per qualsiasi sistema lineare omogeneo esistono vettori $\vec{b}_1,\cdots,\vec{b}_k$ tali che l'insieme delle soluzioni del sistema è 
$$
\left\{c_1\vec{b}_1 + \cdots + c_k\vec{b}_k \mid c_1,\ldots,c_k \in
\mathbb{R}\right\}
$$
dove k è il numero di variabili libere nella forma a scala del sistema.

Non appunterò qui la dimostrazione, perchè non è necessaria per l'esame. Se ho tempo, lo farò. La dimostrazione è molto prolissa.

##### Lemma 2

Per qualsiasi sistema lineare e per le sue soluzioni $\vec{p}$ associate, l'insieme delle soluzioni equivale a { $\vec{p} + \vec{h}$ }, dove $\vec{h}$ è la soluzione del sistema omogeneo associato.

In parole povere:
$$
\boxed{
\begin{aligned}
&\text{Sistema originale:}
&&x+y=3
\\[6pt]
&\text{Soluzione particolare:}
&&\vec p=
\begin{pmatrix}
3\\
0
\end{pmatrix}
\\[6pt]
&\text{Sistema omogeneo:}
&&x+y=0
\\[6pt]
&\text{Soluzioni dell'omogeneo:}
&&\vec h=
t
\begin{pmatrix}
-1\\
1
\end{pmatrix},
\qquad t\in\mathbb R
\\[8pt]
&\text{Teorema:}
&&\vec x=\vec p+\vec h
\\[6pt]
&\text{Soluzione generale:}
&&\boxed{
\vec x=
\begin{pmatrix}
3\\
0
\end{pmatrix}
+
t
\begin{pmatrix}
-1\\
1
\end{pmatrix}
=
\begin{pmatrix}
3-t\\
t
\end{pmatrix}
}
\end{aligned}
}
$$

Infatti, se nella soluzione generale si sostituisce t con qualsiasi numero $t\in\mathbb{R}$, si ottengono tutte le soluzioni possibili con x diverse.

Per la dimostrazione, supponiamo l'equazione $A\vec{x} = \vec{b}$ e che $\vec{p}$ sia una soluzione particolare, quindi $A\vec{p} = \vec{b}$. Il sistema omogeneo associato sarà invece $A\vec{h} = \vec{0}$.

Partiamo quindi dalla soluzione del sistema omogeneo associato.
Sommiamo quindi h alla soluzione particolare p:
$$
\vec{x} = \vec{p} + \vec{h}
$$
vediamo se $\vec{x}$ è una soluzione del sistema originale:
$$
A\vec{x} = A\left(\vec{p}+\vec{h}\right) = A\vec{p}+A\vec{h} = \vec{b} + \vec{0} = \vec{b}
$$
quindi $\vec{p} + \vec{h}$ è una soluzione del sistema omogeneo associato.

Procediamo con la soluzione del sistema originale.
Se sottraiamo le equazioni $A\vec{x} = \vec{b}$ e $A\vec{p} = A\vec{b}$ , otteniamo
$$
A\vec{x} - A\vec{p} = \vec{b} - \vec{b}
$$
quindi $A\left(\vec{x} - \vec{p}\right) = \vec{0}$ . Definiamo quindi $\vec{h} = \vec{x} - \vec{p}$ .  Quindi $A\vec{h} = A\left(\vec{x} - \vec{p}\right)$.  Dalla definizione iniziale di Ax e Ap, deriviamo quini che $A\vec{h} = \vec{b} - \vec{b} = \vec{0}$. Questa è proprio una soluzione del sistema omogeneo associato, e abbiamo anche $\vec{x} = \vec{p} + \vec{h}$. CVD.

##### Corollario

Gli insiemi delle soluzioni di un sistema sono vuoti, hanno un elemento o ne hanno infiniti.

Per dimostrare, sappiamo intanto che le tre possibilità enunciate dal corollario esistono. Dobbiamo quindi dimostrare che sono le uniche.

Prima osserviamo come un sistema omogeneo con almeno una soluzione $\vec{v}$ diversa da $\vec{0}$ ha infinite soluzioni, perchè tutti i multipli scalari di $\vec{v}$ risolvono anche i sistemi omogenei, e ci sono infiniti multipli scalari di $\vec{v}$.

Applichiamo quindi il secondo lemma per concludere che l'insieme di soluzione è vuoto ( se non ci sono soluzioni particolari $\vec{p}$ ), ha un elemento ( se esiste un $\vec{p}$ e il sistema omogeneo ha unica soluzione $\vec{0}$ ), o è infinito sotto le condizioni evidenziate sopra.


# Disuguaglianza triangolare e derivati

>[!info] Enunciato
>per ogni $\vec{u}, \vec{v} \in \mathbb{R}^n$ ,
>$$
>\lvert \vec{u} + \vec{v} \rvert \leq \lvert\vec{u}\rvert + \lvert\vec{v}\rvert
>$$
>dove i valori sono uguali soltanto se uno dei vettori è un multiplo positivo scalare dell'altro

Dimostriamo sapendo che essendo tutti i numeri positivi, la diseguaglianza è vera solo se anche il suo quadrato è vero: $$
\lvert\vec{u}+\vec{v}\rvert^2 \leq \left(\lvert\vec{u}+\vec{v}\right)^2
\rightarrow\vec{u}^2+2\vec{uv}+\vec{v}^2\leq\vec{u}^2+2\lvert\vec{u}\rvert\lvert\vec{v}\rvert+\vec{v}^2\newline\rightarrow2\vec{uv} \leq 2\lvert\vec{u}\rvert\lvert\vec{v}\rvert
$$


