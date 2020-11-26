---
Titolo: Pauli Measurements Description: informazioni su come usare le operazioni di misurazione di Pauli a qubit singolo e a più livelli.
autore: bradben UID: Microsoft. Quantum. Concepts. Pauli ms. Author: v-benbra ms. Date: 12/11/2017 ms. Topic: article no-loc:
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

# <a name="pauli-measurements"></a>Misurazioni di Pauli

Nelle discussioni precedenti sono state illustrate le misure di base computazionali.
In realtà, esistono altre misure comuni che si verificano in quantum computing che, dal punto di vista della notazione, sono utili per esprimere in termini di misurazioni di base computazionale.
Quando si lavora con Q# , il tipo di misurazioni più comune che verrà eseguito sarà probabilmente costituito dalle *misurazioni di Pauli*, che generalizzano le misurazioni di base computazionali per includere le misurazioni in altre basi e la parità tra qubits diversi.
In questi casi, è comune discutere la misurazione di un operatore Pauli, in generale un operatore come $ x, Y, z $ o $ z \otimes z, x \otimes x, x \otimes Y $ e così via. 

> [!TIP]
> In Q# gli operatori Pauli multiqubit sono in genere rappresentati da matrici di tipo `Pauli[]` .
> Ad esempio, per rappresentare $ X \otimes Z \otimes Y $ , è possibile usare la matrice `[PauliX, PauliZ, PauliY]` .

La discussione sulla misurazione in termini di operatori Pauli è particolarmente comune nel sottocampo della correzione degli errori quantistici.
In Q# si segue una convenzione simile, che ora spiega questa visualizzazione alternativa delle misurazioni.

Prima di approfondire i dettagli su come pensare a una misurazione di Pauli, è utile considerare la misurazione di un singolo qubit all'interno di un computer Quantum allo stato quantum.
Si supponga di avere uno $ $ stato quantum n-qubit, quindi la misurazione di un qubit immediatamente regola la metà delle $ 2 ^ n $ possibilità che lo stato potrebbe essere.
In altre parole, la misurazione proietta lo stato del quantum su uno dei due spazi.
Possiamo generalizzare il modo in cui pensiamo alla misurazione per riflettere questa intuizione.

Per identificare in modo conciso questi spazi, è necessario un linguaggio per descriverli.
Per descrivere i due sottospazi, è possibile specificarli tramite una matrice in cui sono presenti solo due autovalori univoci, presi dalla Convenzione come $ \pm 1 $ .
Per un semplice esempio di descrizione di sottospazi in questo modo, prendere in considerazione $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .
\end{align}
$$

Leggendo gli elementi diagonali della matrice Pauli- $ Z $ , è possibile osservare che la $ Z $ ha due autovettori, $ \ket { 0 } $ e $ \ket { 1 } $ , con gli autovalori corrispondenti $ \pm 1 $ .
Quindi, se misuriamo il qubit e otteniamo `Zero` (corrispondente allo stato $ \ket { 0 } $ ), sappiamo che lo stato del qubit è a $ + 1 $ autostato dell' $ $ operatore Z.
Analogamente, se si ottiene `One` , sappiamo che lo stato del qubit è $ -1 $ autostato $ Z $ . Questo processo viene definito nel linguaggio delle misurazioni di Pauli come "misurazione di Pauli $ Z $ " ed è completamente equivalente all'esecuzione di una misurazione di base computazionale.

Qualsiasi $ \times matrice 2 2 $ che rappresenta una trasformazione unitaria di $ Z $ soddisfa anche questo criterio.
È anche possibile usare una matrice $ a = u ^ \dagger Z u $ , dove $ u $ è qualsiasi altra matrice unitaria, per assegnare a una matrice la definizione dei due risultati di una misura nel $ \pm 1 $ autovettori.
La notazione delle misurazioni di Pauli fa riferimento a questa equivalenza unitaria identificando le $ misurazioni X, Y, Z $ come misurazioni equivalenti che possono essere eseguite per ottenere informazioni da un qubit.
Queste misurazioni sono fornite di seguito per praticità.


|Trasformazione unità di misura Pauli ||
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $HS ^               {\dagger}$         |

Ovvero, usando questo linguaggio, "Measure $ Y $ " equivale a applicare $ HS ^ \dagger $ e quindi a misurare la base di calcolo, dove [`S`](xref:Microsoft.Quantum.Intrinsic.S) è un'operazione Quantum intrinseca talvolta denominata "Phase Gate" e può essere simulata dalla matrice unitaria.

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

Equivale anche all'applicazione di $ HS ^ \dagger $ al vettore di stato quantum e alla misurazione $ della Z $ , in modo che l'operazione seguente sia equivalente a `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Lo stato corretto viene quindi trovato trasformando di nuovo in base al calcolo, che equivale a applicare $ sh $ al vettore di stato quantum. nel frammento di codice precedente, la trasformazione alla base computazionale viene gestita automaticamente dall'utilizzo del `within … apply` blocco.

In Q# si dice il risultato---ovvero le informazioni classiche estratte dall'interazione con lo stato---sono fornite da un `Result` valore $ j \in \\ { \texttt { zero } , uno che \texttt { } \\ } $ indica se il risultato è in $ (-1) ^ j $ eigenspace dell'operatore Pauli misurato.


## <a name="multiple-qubit-measurements"></a>Misurazioni a più qubit

Le misurazioni degli operatori qubit di Pauli sono definite in modo analogo, come illustrato di seguito:

$$
Z \otimes z = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\  0 & -1 & 0 & 0 \\\\ 0 & 0 & -1 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix} .
$$

Di conseguenza, i prodotti tensore di due operatori Pauli- $ Z $ formano una matrice costituita da due spazi costituiti da $ + 1 $ e $ -1 $ autovalori.
Come nel caso di un singolo qubit, entrambe costituiscono un mezzo di spazio che significa che la metà dello spazio vettoriale accessibile appartiene a $ + 1 $ eigenspace e la metà rimanente a $ -1 $ eigenspace.
In generale, è facile vedere dalla definizione del prodotto tensore che tutti i prodotti tensori degli operatori Pauli- $ Z $ e l'identità rispettano questo problema.
Ad esempio,

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 &  0 &  0 &  0 \\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 &  0 & -1 \end{bmatrix} .
\end{align}
$$

Come prima, eventuali trasformazioni unitarie di tali matrici descrivono anche due spazi con etichetta $ \pm 1 $ .
Ad esempio, $ x \otimes x = h h \otimes (z \otimes z) h \otimes h $  dall'identità $ = HxH z $ .
Analogamente al caso qubit, tutte le qubit di tipo Pauli possono essere scritte come $ u ^ \dagger (Z \otimes \id ) u $ per $ 4 \times $ matrici unitarie $ u $ . Le trasformazioni vengono enumerate nella tabella seguente.

> [!NOTE]
>Nella tabella seguente si usa $ \operatorname { swap } $ per indicare la matrice >$$
> \begin{align}
>     \operatorname{Scambia } &=
>     \left( \begin { matrice}
>         1 & 0 & 0 & 0 \\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { matrice } \right ) >     \end{align}
> $$
> utilizzato per simulare l'operazione intrinseca [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .

|Trasformazione unità di misura Pauli ||
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes $ | $ \operatorname { swap } Z $|
|$\boldone \otimes $ | $ \otimes \boldone \operatorname { swap } X (H $ )|
|$\boldone \otimes $ | $ \dagger \otimes \boldone \operatorname { scambio } Y $ (HS ^)|
|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

In questo caso, l' [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operazione viene visualizzata per il motivo seguente.
Ogni misura di Pauli che non include la $ \boldone $ matrice è equivalente al valore di un elemento unitario alla $ z \otimes z $ con la motivazione precedente.
Gli autovalori della $ z \otimes z $ dipendono solo dalla parità dei qubits che comprendono ogni vettore di base computazionale e le operazioni controllate-not servono per calcolare questa parità e archiviarla nel primo bit.
Quindi, una volta misurato il primo bit, è possibile recuperare l'identità dello spazio a metà risultante, equivalente alla misurazione dell'operatore Pauli.

Una nota aggiuntiva: Sebbene sia possibile tentare di presumere che la misura $ z \otimes z $ sia uguale alla misurazione sequenziale di $ z \otimes \mathbb { 1 } $ e quindi di $ \mathbb { 1 } \otimes Z $ , questo presupposto è false.
Il motivo è che la misurazione della $ z \otimes z $ proietta lo stato del quantum in una $ autostato + 1 $ o $ -1 $ di questi operatori.
Se si misura $ z \otimes \mathbb { 1 } $ e poi $ \mathbb { 1 } \otimes z, $ il vettore di stato quantum viene proiettato per primo in una metà dello spazio $ z \otimes \mathbb { 1 } $ e quindi in una metà dello spazio $ \mathbb { 1 } \otimes z $ . Poiché sono presenti quattro vettori di base di calcolo, l'esecuzione di entrambe le misurazioni riduce lo stato a un trimestre e quindi lo riduce a un singolo vettore di base computazionale.

## <a name="correlations-between-qubits"></a>Correlazioni tra qubit
Un altro modo per esaminare i prodotti tensori di matrici di Pauli come $ x \otimes x $ o $ z \otimes z $ è che queste misurazioni consentono di esaminare le informazioni archiviate nelle correlazioni tra le due qubits.
La misurazione di $ X \otimes \id $ consente di esaminare le informazioni archiviate localmente nel primo qubit.
Sebbene entrambi i tipi di misurazioni siano ugualmente utili nell'elaborazione quantistica, il primo illumina la potenza del quantum computing.
Si rivela che in quantum computing, spesso le informazioni che si desidera apprendere non vengono archiviate in un singolo qubit ma piuttosto archiviate in modo non locale in tutti i qubits in una sola volta e, pertanto, solo esaminando la misura tramite una misurazione congiunta (ad esempio, $ z \otimes z $ ) queste informazioni diventano manifeste.

Nella correzione degli errori, ad esempio, si desidera spesso conoscere l'errore che si è verificato durante l'apprendimento di nulla sullo stato che si sta tentando di proteggere.
Nell' [esempio di codice a scorrimento bit](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) viene illustrato un esempio di come è possibile utilizzare misure come $ z \otimes z \otimes \id $ e $ \id \otimes z \otimes z $ . < --TODO: modificare questo valore in un collegamento al browser degli esempi non appena viene caricato l'esempio di codice di Flip bit. -->

$ \otimes \otimes \otimes \boldone $ È possibile misurare anche operatori Pauli arbitrari, ad esempio X Y Z.
Tutti questi prodotti tensore di operatori Pauli hanno solo due autovalori $ \pm 1 $ e entrambi eigenspaces costituiscono metà spazi dell'intero spazio vettoriale.
Coincidono quindi con i requisiti indicati sopra.

In Q# , tali misure restituiscono $ j $ se la misurazione restituisce un risultato nel eigenspace di segno $ (-1) ^ j $ .
Il fatto che le misurazioni di Pauli come funzionalità integrate in Q# risulti utile perché la misurazione di tali operatori richiede lunghe catene di controlli e non trasformazioni di base per descrivere il diagonalizing $ U $ Gate necessario per esprimere l'operazione come prodotto tensore $ Z $ e $ \id $ .
Con la possibilità di specificare che si desidera eseguire una di queste misurazioni predefinite, non è necessario preoccuparsi di come trasformare la base in modo che una misura di base computazionale fornisca le informazioni necessarie.
Q# gestisce automaticamente tutte le trasformazioni di base necessarie.
Per ulteriori informazioni, vedere le [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operazioni e.

## <a name="the-no-cloning-theorem"></a>Teorema del No-Cloning

Le informazioni sul quantum sono potenti.
Ci permette di eseguire operazioni straordinarie, ad esempio numeri di fattore esponenzialmente più veloci rispetto agli algoritmi classici più noti, oppure simulare in modo efficiente i sistemi elettronici correlati che richiedono in genere un costo esponenziale per simulare in modo accurato.
Esistono tuttavia alcune limitazioni alla potenza del quantum computing.
Una limitazione di questo tipo viene fornita dal *teorema di no-cloning*.

Il nome del teorema No-Cloning è appropriato.
Non consente la clonazione di stati Quantum generici da un computer Quantum.
La prova del teorema è molto semplice.
Anche se una prova completa del teorema di non clonazione è un po' troppo tecnica per la nostra discussione, la prova, nel caso di nessun qubits ausiliario aggiuntivo, rientra nell'ambito.

Per tale computer quantistico, l'operazione di clonazione deve essere descritta da una matrice unitaria.
Non è consentita la misurazione, perché danneggia lo stato del quantum che si sta tentando di clonare.
Per simulare l'operazione di clonazione, è necessario che la matrice unitaria venga utilizzata per la proprietà $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
per qualsiasi stato $ \ket { \psi } $ .
La proprietà Linearity della moltiplicazione di matrici implica quindi che per qualsiasi secondo stato quantum $ \ket { \phi } $ ,

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Questo fornisce l'intuizione fondamentale dietro il teorema del No-Cloning: qualsiasi dispositivo che copia uno stato quantum sconosciuto deve causare errori in almeno alcuni degli stati copiati.
Sebbene il presupposto fondamentale che il Cloner agisca in modo lineare sullo stato di input possa essere violato tramite l'aggiunta e la misurazione di qubits ausiliari, tali interazioni perdono anche le informazioni sul sistema attraverso le statistiche di misurazione e impediscono la clonazione esatta in tali casi.
Per una prova più completa del teorema di No-Cloning, vedere [per altre informazioni](xref:microsoft.quantum.more-information).

Il teorema No-Cloning è importante per la comprensione qualitativa del quantum computing, perché se è possibile clonare gli Stati del quantum a costo elevato, è possibile ottenere una capacità quasi magica di apprendere dagli Stati Quantum.
In realtà, è possibile violare il principio di incertezza decantato di Heisenberg.
In alternativa, è possibile usare un Cloner ottimale per ottenere un singolo campione da una distribuzione quantistica complessa e apprendere tutti gli elementi che è possibile conoscere per la distribuzione da un solo esempio.
Si tratta di un'operazione analoga a quella di una moneta e all'osservazione delle teste, quindi quando si comunica a un amico il risultato che li risponde "Ah la distribuzione di tale moneta deve essere Bernoulli con $ p = 0.512643 \ ldots $ !".  Un'istruzione di questo tipo non è sensical, perché una certa quantità di informazioni (il risultato delle intestazioni) non è semplicemente in grado di fornire le informazioni necessarie per codificare la distribuzione senza sostanziali informazioni precedenti.
In modo analogo, senza informazioni precedenti, non è possibile clonare perfettamente uno stato quantico proprio come non è possibile preparare un insieme di tali monete senza conoscere $ p $ .

Le informazioni non sono gratuite in quantum computing.
Ogni qubit misurato fornisce un solo bit di informazioni e il teorema No-Cloning Mostra che non è presente alcuna backdoor che può essere sfruttata per aggirare il compromesso fondamentale tra le informazioni acquisite sul sistema e il disturbo richiamato su di esso.
