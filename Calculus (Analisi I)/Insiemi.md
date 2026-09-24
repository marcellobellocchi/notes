## Gli insiemi e gli insiemi numerici

>[!info] Definizione
>Un insieme in matematica è un raggruppamento di elementi di qualsiasi tipo che soddisfa due caratteristiche:
>1.  è possibile stabilire con assoluta certezza se un elemento appartiene all'insieme
>2.  gli elementi dell'insieme sono tutti diversi fra loro

Diversi rami della matematica fanno uso degli insiemi, e fra le altre cose, vengono usati per categorizzare i numeri. Gli insiemi principalmente utilizzati a questo scopo sono l'insieme dei numeri **naturali**, dei numeri **interi**, dei numeri **razionali** e dei numeri **reali**. Esistono altri insiemi, ma per adesso esploriamo questi.

I numeri naturali sono quelli che si usano per contare:
$$
\mathbb{N} = \{1,2,3,4,5,\dots\}
$$

I numeri interi sono i numeri naturali, più zero e i loro opposti negativi:
$$
\mathbb{Z} = \{0, \pm1, \pm2, \pm3, \ldots\}
$$

I numeri razionali sono tutti i numeri che possono essere espressi come frazioni di due numeri interi, con denominatore diverso da 0
$$
\mathbb{Q} = \left\{ \frac{a}{b} \;\middle|\; a,b \in \mathbb{Z},\ b \neq 0 \right\}
$$
esempi:
$$
\frac{1}{2}​, −\frac{3}{4}, 5, 0, 1,333…
$$

I numeri reali sono tutti i numeri che possono essere rappresentati sulla retta numerica, e comprenono numeri irrazioniali come $\pi$ e $\sqrt{2}$:
$$
\mathbb{R} = \{\,\ldots,-2,-1,0,1,\sqrt{2},2,\pi,4,\ldots\,\}
$$

>[!tip] I numeri reali
>L'insieme dei numeri reali è particolarmente rilevante anche per le sue proprietà:
>*  Ad ogni numero reale corrisponde uno e un solo punto sulla retta numerica
>*  Per ogni coppia di numeri reali, è sempre possibile confrontarli per vedere se uno è maggiore, minore o uguale rispetto all'altro.
>* Tra due numeri reali ce ne sono infiniti altri. questa proprietà viene definita densità dei numeri reali, e caratterizza anche l'insieme dei numeri razionali e irrazionali
>*  $\mathbb{R}$ rispetta l'assioma della [[#Assioma della completezza|completezza]]: su questo espanderemo a seguito della definizione di estremi

rivisiteremo la definizione di completezza dei numeri reali più tardi, dopo la definizione degli estremi di un insieme.

Non tutti gli insiemi consentono tutte le operazioni: l'insieme dei numeri naturali consente solo somma e moltiplicazione, gli interi aggiungono a queste le sottrazioni, e gli altri due consentono tutte e 4 le operazioni basiche:
$$
\begin{array}{c|cccc}
 & + & - & \times & \div \\ \hline
\mathbb{N} & \checkmark & \times & \checkmark & \times \\
\mathbb{Z} & \checkmark & \checkmark & \checkmark & \times \\
\mathbb{Q} & \checkmark & \checkmark & \checkmark & \checkmark^1 \\
\mathbb{R} & \checkmark & \checkmark & \checkmark & \checkmark^1
\end{array}
$$
1. *ammesso che nella divisione il divisore sia diverso da 0*

Esistono anche le operazioni fra gli insiemi, che sono evidenziate nella [[Legenda simboli]].

Con questa notazione, è evidente notare come ogni insieme dei numeri contiene il suo precedente, secondo questo ordine:
$$
\mathbb{N} \subset \mathbb{Z} \subset \mathbb{Q} \subset \mathbb{R}
$$
## Estremi di un insieme

Per definire gli insiemi, definiamo prima il concetto di numero maggiorante e minorante.
Un numero si dice maggiorante se $\forall x\in A, x\leq M$, e minorante se $\forall x\in A,m\leq x$.
Molti numeri possono essere minoranti e maggioranti, e per questo sono contenuti in un insieme, l'insieme dei numeri maggioranti e minoranti. L'estremo superiore (o supremo) è definito come il minimo dell'insieme dei numeri maggioranti

$$
s=\sup A
\iff
\begin{cases}
x\leq s & \forall x\in A\\
\forall\varepsilon>0,\ \exists x\in A:\ x>s-\varepsilon
\end{cases}
$$

Allo stesso modo, l'estremo inferiore (o infimo) è definito come il massimo dell'insieme dei numeri minoranti
$$
i=\inf A
\iff
\begin{cases}
i\leq x & \forall x\in A\\
\forall\varepsilon>0,\ \exists x\in A:\ x<i+\varepsilon
\end{cases}
$$
è sufficiente un valore x che non rispetta questa condizione perchè il valore non corrisponda all'estremo.

Laddove l'estremo inferiore o superiore sono inclusi nell'insieme, efiniscono anche i massimi o i minimi dell'insieme. Questi ultimi non esistono invece se quei valori non sono inclusi nell'insieme.

## Assiomi e teoremi degli insiemi dei numeri

##### Assioma della completezza
Una particolarità dell'insieme $\mathbb{R}$ è, come anticipato, il suo assioma della completezza, che enuncia che tutti i suoi sottoinsiemi limitati superiormente o inferiormente hanno, rispettivamente, un estremo superiore o inferiore in $\mathbb{R}$.
Essendo un assioma, non ha una dimostrazione. Essenzialmente, questa proprietà conferma che la linea dei numeri che rappresenta $\mathbb{R}$ non ha intervalli senza valori, o più colloquialmente, "buchi".

##### Densità
Gli insiemi $\mathbb{Q}$ e $\mathbb{R}$ sono detti densi, perchè fra due numeri razionali o reali (anche fra numeri irrazionali) esiste un numero infinito di valori che li separa.

>[!info] Definizione di densità
>Per ogni valore a e b appartenente nell'insieme A, se a è minore di b, allora esiste un elemento c appartenente ad A tale che c sia maggiore di a e minore di b
>
>$$
>\boxed{
>\forall a,b\in A,\quad
>a<b\Rightarrow\exists c\in A:\ a<c<b
>}
>$$

Questo viene dimostrando selezionando c tale che esso sia uguale alla semisomma di a e b. in $\mathbb{R}$ e in $\mathbb{Q}$ questo valore esisterà sempre, mentre non sarà cosi in $\mathbb{N}$ o in $\mathbb{Z}$