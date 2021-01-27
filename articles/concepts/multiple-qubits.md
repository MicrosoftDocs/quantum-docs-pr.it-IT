---
title: più qubits Descrizione: informazioni su come eseguire operazioni su due o più qubits.
autore: bradben UID: Microsoft. Quantum. Concepts. multiple-qubits ms. Author: v-benbra ms. Date: 12/11/2017 ms. Topic: Conceptual no-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="multiple-qubits"></a>Più qubits

Sebbene le funzionalità di controllo single-qubit dispongano di alcune funzionalità intuitive, ad esempio la possibilità di trovarsi in più di uno stato in un determinato momento, se in un computer Quantum erano presenti solo qubit di controllo, sarebbe un dispositivo con potenza di calcolo che verrebbe sminuito anche da una calcolatrice lasciata da solo un supercomputer classico.
La vera potenza di quantum computing diventa evidente quando si aumenta il numero di qubits.
Questa potenza si pone, in parte, perché la dimensione dello spazio vettoriale dei vettori di stato quantum cresce in modo esponenziale con il numero di qubits.
Ciò significa che, mentre un singolo qubit può essere modellato in modo banale, la simulazione di un calcolo quantistico 50-qubit comporterebbe probabilmente il push dei limiti dei supercomputer esistenti.
L'aumento delle dimensioni del calcolo in base a un solo qubit aggiuntivo *raddoppia* la memoria necessaria per archiviare lo stato e *raddoppia* approssimativamente il tempo di calcolo.
Questo rapido raddoppio della potenza di calcolo è il motivo per cui un computer Quantum con un numero relativamente ridotto di qubits può superare i supercomputer più potenti di oggi, domani e oltre per alcune attività di calcolo.

Perché è presente una crescita esponenziale per i vettori di stato quantum?  L'obiettivo di questa sezione consiste nel rivedere le regole usate per creare gli Stati qubit da singoli Stati qubit, oltre a discutere le operazioni Gate che è necessario includere nel nostro set di controllo per formare un computer Quantum a molti qubit universale.
Questi strumenti sono assolutamente necessari per comprendere i set di controllo usati comunemente nel Q# codice e anche per ottenere informazioni sul motivo per cui gli effetti quantistici, ad esempio l'intrico o l'interferenza, rendono il calcolo quantistico più potente rispetto al computing classico.

## <a name="representing-two-qubits"></a>Rappresentazione di due qubits
La differenza principale tra gli Stati di uno e due qubit è che i due stati qubit sono quattro dimensionali anziché due dimensioni.
Questo è dovuto al fatto che la base computazionale per gli Stati qubit è costituita dai prodotti tensori di uno stato qubit.  Ad esempio, abbiamo \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} ,\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{bmatrix} , \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 0 \\\\ 0 \\\\ 1 \end{bmatrix} .
\end{align}

È facile vedere che, più in generale, lo stato del quantum di $ n $ qubits è rappresentato da un vettore di unità della dimensione $ 2 ^ n che $ Usa questa costruzione.  Vettore

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

rappresenta uno stato quantum su due qubits se $ | \alpha _{ 00 } | ^ 2 + | \alpha_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 + | \alpha_ { 11 } | ^ 2 = 1 $ . Proprio come per i singoli qubits, il vettore di stato quantum di più qubits include tutte le informazioni necessarie per descrivere il comportamento del sistema.

Se vengono forniti due qubits distinti, uno nello stato $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ e un secondo qubit nello stato $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ , lo stato di due qubit corrispondente è    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

dove l'operazione $ \otimes $ viene chiamata il prodotto tensore (o prodotto Kronecker) di vettori. Si noti che, sebbene sia sempre possibile prendere il prodotto tensore di due stati qubit per formare uno stato qubit, non tutti gli Stati del quantum a due qubit possono essere scritti come prodotti tensori di due stati qubit singoli.
Ad esempio, non ci sono stati e in questo $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ modo il prodotto tensore è lo stato     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} .$$ 

Uno stato simile a due qubit, che non può essere scritto come prodotto tensore di stati qubit singoli, viene definito stato "impigliato"; i due qubits sono detti " [*aggrovigliati*](https://en.wikipedia.org/wiki/Quantum_entanglement)".  Poiché lo stato del quantum non può essere considerato come un prodotto tensore di singoli Stati qubit, le informazioni contenute nello stato non sono confinate a uno dei qubits singolarmente.  Piuttosto, le informazioni vengono archiviate in modalità non locale nelle correlazioni tra i due Stati.  Questa non è la località delle informazioni rappresenta una delle principali funzionalità di distinzione del quantum computing rispetto al computing classico ed è essenziale per diversi protocolli Quantum, tra cui la [teleportazione quantistica](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) e la [correzione degli errori quantistici](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Misurazione degli Stati Two-Qubit ##
La misurazione di due stati qubit è molto simile alle misure a qubit singolo. Misurazione dello stato

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

restituisce $ 00 $ con probabilità $ | \alpha _{ 00 } | ^ 2 $ , $ 01 $ con probabilità $ | 01 \alpha_ { } | ^ 2 $ , $ 10 con probabilità $ $ | \alpha _{ 10 } | ^ 2 $ e $ 11 $ con $ probabilità | 11 \alpha_ { } | ^ 2 $ . Le variabili $ \alpha _{ 00 } , \alpha_ { 01 } , \alpha _{ 10 } $ e $ 11 \alpha_ { } $ sono state denominate intenzionalmente per rendere chiara questa connessione. Dopo la misurazione, se il risultato è $ 00, $ lo stato del quantum del sistema Two-qubit è compresso ed è ora

$$
    00 \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} .
$$

È anche possibile misurare un solo qubit di uno stato quantum a due qubit. Nei casi in cui si misura solo uno dei qubits, l'effetto della misurazione è leggermente diverso perché l'intero stato non è compresso a uno stato di base computazionale, ma viene compresso in un solo sottosistema.  In altre parole, in questi casi la misurazione di un solo qubit comprime solo uno dei sottosistemi ma non tutti.  

Per osservare questo problema, valutare la possibilità di misurare il primo qubit dello stato seguente, che è formato dall'applicazione della trasformazione Hadamard $ H $ in due qubits inizialmente impostati sullo stato "0": $$
H ^ { \otimes 2 } \left ( \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right ) 1 2 1 1 1 1 1 = \frac { } { } \begin{bmatrix} & & & \\\\ & -1 & 1 & -1 \\\\ 1 & 1 & -1 & -1 \\\\ 1 & -1 & -1 & 1 \end{bmatrix} \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \frac { 1 } { 2 } \begin{bmatrix} 1 \\\\ 1 1 1 \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { risultato } = 0 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { risultato } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1 \end{bmatrix} \\\\ \end{cases} .  
$$
Entrambi i risultati hanno una probabilità del 50% di verificarsi.  Il risultato è la probabilità del 50% per entrambi può essere intuito dal fatto che il vettore di stato quantum iniziale è invariante in uno scambio $ 0 $ con $ 1 $ sul primo qubit.

La regola matematica per la misurazione del primo o del secondo qubit è semplice.  Se si lascia $ e_k il $ vettore di base di $ calcolo k ^ { \rm e si } $ lascia $ $ che sia il set di tutti $ e_k $ in modo che qubit in questione accetti il valore $ 1 $ per il valore $ k $ .  Se, ad esempio, si è interessati alla misurazione del primo qubit, $ i sono $ costituiti da $ e_1 \equiv 10 $ e $ e_3 \equiv 11 $ .  Analogamente, se si è interessati alla seconda qubit $ S è $ costituito da $ e_2 \equiv 01 $ e $ e_3 \equiv 11 $ .  La probabilità di misurare il qubit scelto come $ 1 $ è per il vettore di stato $\psi$

$$
P ( \text { risultato } = 1) = \sum _ { e_k \text { nel set } S } \psi ^ \dagger e_k e_k ^ \dagger \psi .
$$

> [!NOTE]
> In questo documento viene usato il formato little endian per etichettare la base computazionale. Nel formato little endian, i bit meno significativi sono i primi. Il numero quattro nel formato little endian, ad esempio, è rappresentato dalla stringa di bit 001.

Poiché ogni misura qubit può restituire solo $ 0 $ o $ 1 $ , la probabilità di misurare $ 0 $ è semplicemente $ 1-P ( \text { risultato } = 1) $ .  Questo è il motivo per cui viene assegnata in modo esplicito una formula solo per la probabilità di misurare $ 1 $ .

L'azione che tale misura ha sullo stato può essere espressa matematicamente come

$$
\psi\mapsto \frac{\sum _ { e_k \text { nel set } S } e_k e_k ^ \dagger \psi } { \sqrt { P ( \text { risultato } = 1) } } .
$$

Il lettore cauto potrebbe preoccuparsi di ciò che accade quando la probabilità della misura è zero.  Sebbene lo stato risultante sia tecnicamente non definito in questo caso, non è mai necessario preoccuparsi di tali evenienze perché la probabilità è zero.


Se consideriamo $ \psi $ il vettore di stato uniforme indicato in precedenza e desideriamo misurare il primo qubit, 

$$
P ( \text { misurazione del primo qubit } = 1) = ( \psi ^ \dagger E_1) (E_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | E_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Si noti che questa è solo la somma delle due probabilità previste per misurare i risultati $ 10 $ e $ 11 $ tutti i qubits da misurare.
Per questo esempio, viene restituito

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & 0 \end{bmatrix} \begin{bmatrix} 1 \\\\ 1 1 1 \\\\ \\\\ \end{bmatrix} \right | ^ 2 + \frac { 1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 1 1 1 \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } .
$$

il che corrisponde perfettamente alle nostre intuizioni che indicano la probabilità.  Analogamente, lo stato può essere scritto come

$$
\frac{\frac{E_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

ancora una volta, in base alle nostre intuizioni.

## <a name="two-qubit-operations"></a>Operazioni di Two-Qubit
Come nel caso di un singolo qubit, qualsiasi trasformazione unitaria è un'operazione valida in qubits. In generale, una trasformazione unitaria in $ n $ qubits è una matrice $ U $ di dimensioni $ 2 ^ n \times 2 ^ n $ (in modo che agisca su vettori di dimensioni $ 2 ^ n $ ), in modo che $ u ^ { -1 } = u ^ \dagger $ .
Ad esempio, il Gate CNOT (controllato-non) è un controllo Two-qubit di uso comune ed è rappresentato dalla matrice unitaria seguente:

$$
\operatorname{CNOT 1 \ 0 \ 0 \ 0 } = \begin{bmatrix}  \\\\  0 \ 1 \ 0 \ 0 \ 0 \ 0 \ 0 \ 0 \ \\\\ \\\\  0 \ 1 \ 0 \end{bmatrix}
$$

È anche possibile creare le attività di controllo a due qubit applicando le attività di controllo single-qubit in entrambi qubits. Ad esempio, se si applicano le attività di controllo 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

e

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

alla prima e alla seconda qubits, rispettivamente, equivale a applicare l'unitario Two-qubit fornito dal rispettivo prodotto tensore: $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    AE-AF \ be \ BF \\\\
    AG \ Ah \ BG \ BH \\\\
    CE \ CF \ de \ DF \\\\
    CG \ ch \ DG \ DH \end{bmatrix} .$$
In questo modo, possiamo creare due qubit per le attività di controllo, prendendo il prodotto tensore di alcune attività note a singolo qubit. Di seguito sono riportati alcuni esempi di qubit, tra cui $ h \otimes h $ , $ x \otimes \boldone $ e $ x \otimes Z $ .

Si noti che, mentre le due attività di controllo single-qubit definiscono un controllo a due qubit prendendo il proprio prodotto tensore, il contrario non è vero. Non tutte le attività di controllo qubit possono essere scritte come il prodotto tensore dei controlli qubit singoli.  *Un controllo* di questo tipo è denominato controllo. Un esempio di controllo di CNOT è il Gate

Le informazioni sull'intuizione alla base di un controllo non controllato possono essere generalizzate a Gate arbitrarie.  Una barriera controllata in generale è un controllo che funge da identità (ovvero senza azione), a meno che un qubit specifico non sia $ 1 $ .  Si denota un Unity controllato, controllato in questo caso sulla qubit $ con etichetta x $ , con una $ \Lambda \_ x (U) $ .  Come esempio $ \Lambda _0 (u) e 1 \_ { } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ e $ \Lambda \_ 0 (u) e \_ { 0 e } \otimes { \psi } = \_ { 0 } \otimes { \psi } $ , dove $ e \_ 0 $ e $ e \_ 1 $ sono i vettori di base computazionali per un singolo qubit corrispondente ai valori $ 0 $ e $ 1 $ .  Si consideri, ad esempio, il seguente controllo Z controllato, $ $ che può essere espresso come $$
\Lambda\_0 (Z) = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { CNOT } ( \boldone \otimes h).
$$

La creazione di unitaries controllati in modo efficiente è una sfida importante.  Il modo più semplice per implementare questa operazione richiede la creazione di un database di versioni controllate dei controlli fondamentali e la sostituzione di ogni controllo fondamentale nell'operazione unitaria originale con la relativa controparte controllata.  Spesso si tratta di un'operazione piuttosto dispendiosa, che può essere usata per sostituire solo alcune attività di controllo con versioni controllate per ottenere lo stesso effetto.  Per questo motivo, nel nostro Framework viene offerta la possibilità di eseguire il metodo ingenuo di controllo o di consentire all'utente di definire una versione controllata dell'unità se è nota una versione ottimizzata ottimizzata per la mano.

Le attività di controllo possono anche essere controllate con le informazioni classiche.  Un non controllo classico, ad esempio, è solo un normale not-Gate, ma viene applicato solo se un bit classico è $ 1 $ anziché un bit del quantum.  In questo senso, un controllo classico può essere considerato come un'istruzione if nel codice Quantum in cui il Gate viene applicato solo in un ramo del codice.


Come nel caso di un singolo qubit, un set di controllo Two-qubit è universale se $ \times $ una matrice unitaria 4 4 può essere approssimata da un prodotto di controllo da questo set a una precisione arbitraria.
Un esempio di un set di controllo universale è Hadamard Gate, T Gate e CNOT Gate. Acquisendo i prodotti di questi controlli, possiamo approssimare qualsiasi matrice unitaria in due qubits.

## <a name="many-qubit-systems"></a>Sistemi di Many-Qubit
Si seguono esattamente gli stessi modelli esaminati nel caso di due qubit per creare stati Quantum qubit diversi dai sistemi più piccoli.  Tali Stati vengono compilati creando prodotti tensori di stati più piccoli.  Si consideri, ad esempio, la codifica della stringa $ di bit 1011001 $ in un computer Quantum.  È possibile codificare questo come

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} .
$$

I cancelli quantistici funzionano esattamente allo stesso modo.  Se ad esempio si vuole applicare il controllo $ X $ al primo qubit, quindi eseguire un CNOT tra il secondo e il terzo qubits è possibile esprimere questa trasformazione come

\begin{align}
&(X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001. \end{align}

In molti sistemi qubit è spesso necessario allocare e deallocare qubits che funge da memoria temporanea per il computer Quantum.  Un qubit di questo tipo è denominato ancilla.  Per impostazione predefinita, si presuppone che lo stato qubit venga inizializzato per $ E_0 al $ momento dell'allocazione.  Si presuppone inoltre che venga nuovamente restituito per $ E_0 $ prima della deallocazione.  Si tratta di un presupposto importante perché se un ancilla qubit diventa un altro registro qubit quando viene deallocato, il processo di deallocazione danneggia il ancilla.  Per questo motivo, si presuppone sempre che tali qubits vengano ripristinati allo stato iniziale prima di essere rilasciati.

Infine, sebbene sia necessario aggiungere nuove attività di controllo al nostro set di controllo per ottenere un calcolo quantistico universale per due computer Quantum qubit, non è necessario introdurre nuove attività di controllo nel caso di qubit.  I cancelli $ H $ , $ T $ e CNOT formano un controllo universale impostato su molti qubits perché qualsiasi trasformazione unitaria generale può essere suddivisa in una serie di due rotazioni qubit.  Possiamo quindi sfruttare la teoria sviluppata per il caso con due qubit e usarla di nuovo qui quando abbiamo molti qubits.

Sebbene la notazione algebrica lineare utilizzata finora possa essere utilizzata per descrivere gli Stati qubit, diventa sempre più complesso man mano che si aumentano le dimensioni degli Stati.  Il vettore di colonna risultante per una stringa di 7 bit di lunghezza, ad esempio, è $ 128 $ dimensionale, il che rende l'espressione utilizzando la notazione descritta in precedenza molto complessa.  Per questo motivo, si presenta una nota comune in quantum computing che consente di descrivere concisamente questi vettori ad alta dimensionalità.
