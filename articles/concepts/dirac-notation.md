---
title: Notazione di Dirac
description: Informazioni sull'uso della notazione Dirac per rappresentare gli Stati Quantum e per simulare le operazioni Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 958910452109fc722999acddd70894c458e38357
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630392"
---
# <a name="dirac-notation"></a>Notazione Dirac

Sebbene la notazione del vettore di colonna sia onnipresente nell'algebra lineare, è spesso complessa nell'elaborazione quantistica, soprattutto quando si gestiscono più qubits.  Ad esempio, quando si definisce $ \psi come $ vettore, non è evidente se $ \psi $ è una riga o un vettore di colonna.  Di conseguenza, se $ \Phi $ e $ \psi $ sono vettori, non è chiaro se $ \Phi \psi $ è anche definito perché le forme di $ \Phi $ e $ \psi $ potrebbero non essere chiare nel contesto.  Oltre l'ambiguità sulle forme dei vettori, esprimere anche vettori semplici con la notazione algebrica lineare introdotta in precedenza può essere molto complessa. Se, ad esempio, si vuole descrivere uno $ stato $n-qubit in cui ogni qubit accetta il valore $0 $ , viene formalmente espresso lo stato come 

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } . $$  

Ovviamente la valutazione di questo prodotto tensore è poco pratica perché il vettore si trova in uno spazio esponenzialmente grande e pertanto questa notazione è in realtà la migliore descrizione dello stato che è possibile assegnare utilizzando la notazione precedente.  

La [*notazione Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) risolve questi problemi presentando un nuovo linguaggio per soddisfare le esigenze specifiche dei meccanismi quantistici.  Per questo motivo, è consigliabile che il lettore non possa visualizzare gli esempi in questa sezione come una ricetta rigida su come descrivere gli Stati dei quantum, ma incoraggiare il lettore a visualizzarli come suggerimenti che possono essere usati per esprimere concisamente le idee di Quantum.

Sono disponibili due tipi di vettori nella notazione Dirac: il vettore *Bra* e il vettore *KET* , denominati perché, quando assemblati, formano un *freno* o un prodotto interno.  Se $ \psi $ è un vettore di colonna, è possibile scriverlo nella notazione Dirac come $ \ket { \psi } $, dove $ \ket { \cdot } $ indica che si tratta di un vettore di colonna di unità, ovvero un vettore *KET* .  Analogamente, la riga Vector $ \psi ^ \dagger $ è espressa come $ \bra { \psi } $. In altre parole, $ \psi ^ \dagger $ viene ottenuto applicando una coniugazione complessa a livello di voce agli elementi della Trasponi di $ \psi $ . La notazione bra-ket implica direttamente che $ \braket { \psi | \psi } $ sia il prodotto interno di Vector $ \psi $ con se stesso, che è la definizione $1 $ .  

Più in generale, se $ \psi $ e $ \Phi $ sono vettori di stato quantum il prodotto interno è $ \braket { \Phi | \psi } $, che implica che la probabilità di misurare lo stato $ \ket { \psi $ sia } $ \ket { \Phi } $ is $ | \braket \Phi \psi { | } | ^ 2 $ .  

La convenzione seguente viene usata per descrivere gli Stati del quantum che codificano i valori di zero e uno (gli Stati di base di calcolo a qubit singolo):

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Esempio: rappresentazione dell'operazione Hadamard con la notazione Dirac

La notazione seguente viene spesso usata per descrivere gli Stati che risultano dall'applicazione di Hadamard Gate a $ \ket{0 } $ e $ \ket{1 } $ (che corrispondono ai vettori di unità nelle direzioni $ + x $ e $-x $ sulla sfera Bloch):

$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = h \ket {1 } = \ket { -}.
$$

Questi Stati possono anche essere espansi usando la notazione Dirac come somme di $ \ket{0 } $ e $ \ket{1 } $:

$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).
$$

### <a name="computational-basis-vectors"></a>Vettori di base di calcolo
In questo modo viene illustrato il motivo per cui questi Stati sono spesso denominati *base computazionale*: ogni stato quantico può sempre essere espresso come somma di vettori di base computazionale e tali somme sono facilmente espresse utilizzando la notazione Dirac.  Il contrario è vero anche nel caso in cui gli Stati $ \ket { +} $ e $ \ket { -} $ formino anche una base per gli Stati Quantum.  È possibile osservare questo aspetto dal fatto che

$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).
$$

Come esempio di notazione Dirac, prendere in considerazione il freno $ \braket{0 | 1 } $, ovvero il prodotto interno compreso tra $0 $ e $1 $ .  Può essere scritto come 

$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end { bmatrix } = 0. $ $

Ciò indica che $ \ket{0 } $ e $ \ket{1 } $ sono vettori ortogonali, vale a dire che $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .  Anche per definizione $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , il che significa che i due vettori di base di calcolo possono anche essere chiamati *ortonormale*.
Queste proprietà di ortonormale saranno utili nell'esempio seguente. Se è presente uno stato $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ then perché $ \braket{1 | 0 } = 0 $ la probabilità di misurazione di $1 $ è  

$ $ \Big | \braket{1 | \psi } \Big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>Notazione del prodotto tensore
La notazione Dirac include anche una struttura di prodotto tensore implicita al suo interno.  Questo è importante perché in quantum computing, il vettore di stato descritto da due registri quantum non correlati è il tensore di prodotti dei due vettori di stato.  La descrizione concisa della struttura del prodotto tensore o della loro mancanza è fondamentale se si vuole spiegare un calcolo quantistico.  La struttura del prodotto tensore implica che è possibile scrivere $ \psi \otimes \Phi $ per i due vettori di stato quantum $ \Phi $ e $ \psi $ come $ \ket \psi \ket \Phi { } { } $, a volte scritta in modo esplicito come $ \ket \psi \otimes \ket \Phi { } { } $, tuttavia, per convenzione, la scrittura di $ \otimes $ tra i vettori non è necessaria.  Ad esempio, lo stato con due qubits inizializzato sullo stato zero viene fornito da

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 \otimes } \ket{0 } = } } \ket{0 \ket{0.
$$

Allo stesso modo, lo stato $ \ket{p } $ per integer $p $ rappresenta uno stato quantum che codifica nella rappresentazione binaria dell'intero $p $ .  Se, ad esempio, si vuole esprimere il numero $5 $ usando una codifica binaria senza segno, è possibile esprimere lo stesso nome

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

In questa notazione $ \ket{0 } $ non deve fare riferimento a uno stato qubit singolo, ma piuttosto a un *Registro qubit* che archivia una codifica binaria $0 $ .  Le differenze tra queste due notazioni sono in genere chiare dal contesto.  Questa convenzione è utile per semplificare il primo esempio che può essere scritto in uno dei modi seguenti:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{= \ket{0 \otimes \cdots \otimes \ket{0 bmatrix } } } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Esempio: Descrizione della superposizione con la notazione Dirac
Come altro esempio di come è possibile usare la notazione Dirac per descrivere uno stato quantico, prendere in considerazione le modalità equivalenti seguenti per la scrittura di uno stato quantum che rappresenta una superposizione uguale su ogni stringa di bit di lunghezza $n$

$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ Sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .
$$

Qui è possibile chiedersi perché la somma va da $0 $ a $2 ^ {n } -1 $ per $n $ bit.  Si noti innanzitutto che sono disponibili $2 ^ {n } $ configurazioni diverse che $n $ bit possono richiedere.  È possibile notare che un bit può assumere $2 $ valori, ma due bit possono richiedere $4 $ valori e così via. In generale, ciò significa che sono disponibili $2 ^ n $ diverse stringhe di bit, ma il valore più grande codificato in uno di essi $1 \cdots 1 = 2 ^ n-1 $ e quindi è il limite massimo per la somma.
Come si può notare, in questo esempio non è stato usato $ \ket { +} ^ {\otimes n } = \ket { +} $ in Analogy a $ \ket{0 } ^ {\otimes n } = \ket{0 } $ perché questa convenzione di notazione è generalmente riservata allo stato di base computazionale con ogni qubit inizializzato su zero.  Sebbene tale convenzione sarebbe sensata in questo caso, non viene utilizzata nella letteratura per il calcolo del quantum.

### <a name="expressing-linearity-with-dirac-notation"></a>Espressione della linearità con la notazione Dirac
Un'altra interessante funzionalità della notazione Dirac è il fatto che è lineare.  Se si vuole scrivere per quattro vettori di stato quantistici, 

$ $ (\Alpha \ket { \psi } + \beta \ket { \Phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \Alpha \ket \psi \ket \chi \gamma { } { } + \Alpha \delta \ket { \psi \ket \omega } { } + \beta \gamma \ket { \Phi } \ket { \chi } + \beta \delta \ket { \Phi } \ket { \omega } . $ $

Ciò significa che è possibile distribuire la notazione del prodotto tensore nella notazione Dirac, in modo che l'acquisizione di un tensore di prodotti tra vettori di stato termini come una moltiplicazione ordinata.

I vettori Bra seguono una convenzione simile a vettori ket.  Ad esempio, Vector $ \bra { \psi } \bra { \Phi } $ equivale al vettore di stato $ \psi ^ \dagger \otimes \Phi ^ \dagger = (\psi \otimes \Phi) ^ \dagger $ . Se il vettore ket $ \ket { \psi } $ è $ \Alpha \ket{0 } + \beta \ket{1 } $, la versione del vettore Bra del vettore è $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra{0 } \Alpha ^ * + \bra{1 } \beta ^ *) $.

Si supponga, ad esempio, di voler calcolare la probabilità di misurare lo stato $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ usando un programma Quantum per misurare gli stati in modo che sia $ \ket { +} $ o $ \ket { -} $. Quindi, la probabilità che il dispositivo restituisca che lo stato sia $ \ket { -} $ è 

$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $

Il fatto che il segno negativo venga visualizzato nel calcolo della probabilità è una manifestazione di interferenza quantistica, che è uno dei meccanismi con cui quantum computing ottiene vantaggi rispetto al calcolo classico.

## <a name="ketbra-or-outer-product"></a>ketbra o prodotto esterno
L'elemento finale che vale la pena discutere nella notazione Dirac è il prodotto *ketbra* o esterno.  Il prodotto esterno è rappresentato nelle notazioni di Dirac come $ \ket { \psi } \bra { \Phi } $ e talvolta denominato ketbras perché i Bras e KET si verificano nell'ordine opposto come i freni.  Il prodotto esterno viene definito tramite la moltiplicazione di matrici come $ \ket { \psi } \bra { \Phi } = \psi \Phi ^ \dagger $ per i vettori di stato quantum $ \psi $ e $ \Phi $ .  L'esempio più semplice e probabilmente più comune di questa notazione è

$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end { bmatrix } \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end { bmatrix } .
$$

Ketbras vengono spesso denominati proiettori perché proiettano uno stato quantico su un valore fisso.  Poiché queste operazioni non sono unite (e non mantengono neanche la norma di un vettore), non dovrebbe essere sorprendente che un computer quantum non possa applicare in modo deterministico un proiettore.  Tuttavia, i proiettori eseguono un bel lavoro per descrivere l'azione che la misura ha su uno stato quantico.  Ad esempio, se si misura uno stato $ \ket { \psi } $ come $0, $ la trasformazione risultante che lo stato subisce come risultato della misurazione è

  $ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $

come previsto, se si dovesse misurare lo stato e trovarlo come $ \ket{0 } $.  Per eseguire nuovamente l'iterazione, non è possibile applicare tali proiettori a uno stato in un computer Quantum in modo deterministico.  Al contrario, possono essere applicati in modo casuale con i risultati $ \ket{0 } $ visualizzati con una probabilità fissa.  La probabilità di una misurazione di questo tipo può essere scritta come valore previsto del proiettore Quantum nello stato

$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $

viene illustrato che i proiettori forniscono semplicemente un nuovo modo per esprimere il processo di misurazione.

Se invece si considera la misurazione del primo qubit di uno stato qubit a $1 $ , è anche possibile descrivere questo processo in modo appropriato usando i proiettori e la notazione Dirac:

$ $ P (\Text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .
$$

Qui la matrice di identità può essere facilmente scritta nella notazione Dirac come

$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .
$$

Nel caso in cui ci siano due qubits, il proiettore può essere espanso come 

$ $ \ket{1 } \bra{1 } \otimes \ID = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .
$$

È quindi possibile osservare che questo è coerente con la discussione sulle probabilità di misurazione per gli Stati multiqubit usando la notazione a vettori di colonna:

$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $

che corrisponde alla discussione sulla misurazione multiqubit.  La generalizzazione di questo risultato nel caso di qubit, tuttavia, è leggermente più semplice da esprimere usando la notazione Dirac rispetto alla notazione a vettori di colonna ed è completamente equivalente al trattamento precedente.

## <a name="density-operators"></a>Operatori di densità

Un altro operatore utile per esprimere l'uso della notazione Dirac è un *operatore di densità*, talvolta noto anche come *operatore di stato*.
Un operatore di densità per un vettore di stato quantum assume il formato $ \rho = \ket { \psi } \bra { \psi } $.
Questo concetto di rappresentazione dello stato sotto forma di matrice, anziché di un vettore, è spesso utile perché fornisce un modo pratico per rappresentare i calcoli di probabilità e consente anche di descrivere sia l'incertezza statistica che l'incertezza quantistica nello stesso formalismo.
Gli operatori di stato quantum generale, anziché i vettori, sono onnipresenti in alcune aree del calcolo quantistico, ma non sono necessari per comprendere le nozioni di base del campo.
Per il lettore interessato, è consigliabile leggere uno dei libri di riferimento disponibili in [per ulteriori informazioni](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Sequenze d # Gate equivalenti agli Stati Quantum
Un punto finale da considerare per la notazione quantistica e il linguaggio di programmazione Q #: all'inizio di questo documento è stato ricordato che lo stato del quantum è l'oggetto fondamentale delle informazioni in quantum computing.  Questo potrebbe sorprendere che in Q # non esiste alcuna nozione di stato quantico.  Al contrario, tutti gli Stati vengono descritti solo dalle operazioni utilizzate per prepararli.  L'esempio precedente è un'illustrazione eccellente di questo.  Anziché esprimere una superposizione uniforme su ogni stringa di bit Quantum in un registro, è possibile rappresentare il risultato come $H ^ {\otimes n } \ket{0 } $.  Questa descrizione esponenzialmente più breve dello stato non solo ha il vantaggio di poterla ragionare in modo classico, ma anche di definire in modo conciso le operazioni necessarie per la propagazione tramite lo stack software per implementare l'algoritmo.  Per questo motivo, Q # è progettato per emettere sequenze di controllo anziché gli Stati Quantum; Tuttavia, a un livello teorico le due prospettive sono equivalenti.
