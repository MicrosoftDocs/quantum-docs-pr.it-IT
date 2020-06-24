---
title: Qubit in quantum computing
description: Scopri di più su qubits, l'unità di base di informazioni in quantum computing.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 0b768190137aa4effe0fbac9c764dff60ec00e16
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269576"
---
# <a name="the-qubit"></a>Qubit

Proprio come bits sono l'oggetto fondamentale delle informazioni nell'elaborazione classica, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum BITS) sono l'oggetto fondamentale delle informazioni in quantum computing.  Per comprendere questa corrispondenza, esaminiamo l'esempio più semplice: un singolo qubit.

## <a name="representing-a-qubit"></a>Rappresentazione di un qubit

Mentre un bit, o una cifra binaria, può avere valore $0 $ o $1 $ , un qubit può avere un valore che corrisponde a uno di questi o a una superposizione quantistica di $0 $ e $1 $ .

Lo stato di un singolo qubit può essere descritto da un vettore di colonna bidimensionale di unità Norm, ovvero la grandezza quadrata delle relative voci deve essere sommata a $1 $ . Questo vettore, denominato quantum state Vector, include tutte le informazioni necessarie per descrivere il sistema Quantum One-qubit, proprio come un singolo bit, che include tutte le informazioni necessarie per descrivere lo stato di una variabile binaria.

Qualsiasi vettore di colonna bidimensionale di numeri reali o complessi con norma $1 $ rappresenta un possibile stato quantum utilizzato da un qubit. Quindi $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $ rappresenta uno stato di qubit se $ \Alpha $ e $ \beta $ sono numeri complessi che soddisfano $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ . Alcuni esempi di vettori di stato quantum validi che rappresentano qubits includono

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } , \Text { e} \begin{ bmatrix } \frac{1 } {\sqrt{2} \frac{i {\sqrt{2} \end{ } \\ \\ } } bmatrix } . $ $

I vettori di stato quantum $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ e $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ accettano un ruolo speciale. Questi due vettori formano una base per lo spazio vettoriale che descrive lo stato di qubit. Ciò significa che qualsiasi vettore di stato quantum può essere scritto come una somma di questi vettori di base. In particolare, Vector $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ può essere scritto come $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Sebbene la rotazione di questi vettori possa essere usata come base perfettamente valida per qubit, si sceglie di privilegiare questo valore, chiamandolo come *base computazionale*.

Questi due stati Quantum corrispondono ai due stati di un bit classico, ovvero $0 $ e $1 $ . La convenzione standard consiste nel scegliere

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , $ $

Sebbene la scelta opposta possa essere eseguita ugualmente correttamente. Pertanto, dal numero infinito di possibili vettori di stato quantum a singolo qubit, solo due corrispondono agli Stati dei bit classici; tutti gli altri Stati quantum non lo sono.

## <a name="measuring-a-qubit"></a>Misurazione di un qubit

Ora che si è appreso come rappresentare una qubit, è possibile ottenere alcune informazioni sull'aspetto di questi stati esaminando il concetto di [*misurazione*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Una misura corrisponde all'idea informale di "ricerca" in un qubit, che comprime immediatamente lo stato del quantum in uno dei due stati classici $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ o $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Quando si misura un qubit fornito da quantum state Vector $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $, viene ottenuto il risultato $0 $ con la probabilità $ | \Alpha | ^ 2 $ e il risultato $1 $ con la probabilità $ | \beta | ^ 2 $ . Nel risultato $0 $ , il nuovo stato di qubit è $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; nel risultato $1 $ il suo stato è $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Si noti che queste probabilità riassumono fino a $1 a $ causa della condizione di normalizzazione $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Le proprietà di misurazione indicano anche che il segno generale del vettore di stato quantum è irrilevante. La negazione di un vettore equivale a $ \Alpha \rightarrow-\Alpha $ e $ \beta \rightarrow-\beta $ . Poiché la probabilità di misurare $0 $ e $1 $ dipende dalla grandezza quadrata dei termini, l'inserimento di tali segni non comporta alcuna modifica delle probabilità. Tali fasi sono comunemente chiamate [ `` *fasi globali*''](https://en.wikipedia.org/wiki/Phase_factor) e più in generale possono essere nel formato $e ^ {i \Phi } $ anziché solo $ \pm 1 $ .

Una delle principali proprietà importanti della misurazione è che non danneggia necessariamente tutti i vettori di stato quantistici. Se si inizia con un qubit nello stato $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $, che corrisponde allo stato classico $0, la $ misurazione di questo stato produrrà sempre il risultato $0 $ e rimarrà invariato lo stato del quantum. In questo senso, se sono presenti solo bit classici (ad esempio, qubits $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ o $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $), la misurazione non danneggia il sistema. Ciò significa che è possibile replicare i dati classici e manipolarli in un computer Quantum come un computer classico. La possibilità, tuttavia, di archiviare le informazioni in entrambi gli stati in una sola volta è quello che eleva il calcolo quantistico oltre quello che è possibile in modo classico e deruba ulteriormente i computer Quantum della possibilità di copiare i dati Quantum in modo indiscriminato, vedere anche [il teorema di no-cloning](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualizzazione di qubits e trasformazioni con la sfera Bloch

Qubits può anche essere illustrato in $3 $ D usando la rappresentazione della [*sfera Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  La sfera Bloch fornisce un modo per descrivere uno stato del quantum a qubit singolo (ovvero un vettore complesso bidimensionale) come vettore con valori reali tridimensionali.  Questo è importante perché consente di visualizzare gli Stati qubit singoli e di sviluppare ragionamenti che possono risultare utili per comprendere gli Stati qubit, dove Sfortunatamente la rappresentazione della sfera Bloch si interrompe.  La sfera Bloch può essere visualizzata come segue:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Sfera Bloch](~/media/concepts_bloch.png)

Le frecce in questo diagramma mostrano la direzione in cui il vettore di stato quantum sta puntando e ogni trasformazione della freccia può essere considerata come una rotazione di uno degli assi cardinali.
Quando si pensa a un calcolo quantistico come una sequenza di rotazioni è un'intuizione avanzata, è difficile usare questa intuizione per la progettazione e la descrizione degli algoritmi. Q # attenua questo problema fornendo un linguaggio per la descrizione di tali rotazioni.

## <a name="single-qubit-operations"></a>Operazioni Single-qubit

I computer Quantum elaborano i dati applicando un set universale di controlli Quantum che possono emulare qualsiasi rotazione del vettore di stato quantum.
Questa nozione di universalità è simile alla nozione di universalità per il calcolo tradizionale (ovvero classica) in cui un set di controllo è considerato universale se ogni trasformazione dei bit di input può essere eseguita usando un circuito di lunghezza finita.
In quantum computing, le trasformazioni valide che è possibile eseguire su un qubit sono le trasformazioni e la misurazione unitarie.
L' *operazione contigua* o la trasposta del coniugato complesso è di importanza fondamentale per l'elaborazione quantistica perché è necessaria per invertire le trasformazioni Quantum.
Q # riflette questo aspetto fornendo metodi per compilare automaticamente le sequenze di controllo nel rispettivo contiguo, che consente di evitare che il programmatore debba consegnare i contigui al codice in molti casi. Un esempio è illustrato di seguito:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Sebbene si tratta di un esempio banale (poiché l' <xref:microsoft.quantum.intrinsic.h> operazione è autocontigua), è possibile vedere come questa operazione diventa inestimabile per operazioni qubit più complesse.
Per ulteriori informazioni, vedere [operazioni e funzioni](xref:microsoft.quantum.guide.operationsfunctions).

Sono disponibili solo quattro funzioni che eseguono il mapping di un bit a un bit in un computer classico. Al contrario, è presente un numero infinito di trasformazioni unitarie in un singolo qubit in un computer Quantum. Pertanto, nessun set limitato di operazioni Quantum primitive, denominate [*Gates*](https://en.wikipedia.org/wiki/Quantum_logic_gate), può replicare esattamente il set infinito di trasformazioni unitarie consentite in quantum computing. Ciò significa che, a differenza dell'elaborazione classica, è impossibile per un computer Quantum implementare ogni possibile programma Quantum usando esattamente un numero finito di attività di controllo. Di conseguenza, i computer quantum non possono essere universali nello stesso senso dei computer classici. Di conseguenza, quando si afferma che un set di controlli è *universale* per quantum computing, significa che si tratta di un elemento leggermente più debole rispetto al calcolo classico.
Per quanto riguarda l'universalità, è necessario che un computer Quantum *approssimi* solo ogni matrice unitaria all'interno di un errore finito usando una sequenza di Gate di lunghezza finita.
In altre parole, un set di controlli è un set di porte universali se una qualsiasi trasformazione unitaria può essere scritta approssimativamente come un prodotto di controllo da questo set. È necessario che per ogni errore previsto associato esistano delle attività di controllo $G _ {1 } , G_ {2 } , \ldots G_N $ dal set di controllo in modo che

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

Si noti che poiché la convenzione per la moltiplicazione di matrici consiste nel moltiplicare da destra a sinistra la prima operazione di controllo in questa sequenza, $G _N $ , è effettivamente l'ultima applicata al vettore di stato quantum. Più formalmente, si afferma che tale set di controlli è universale se per ogni tolleranza di errore $ \epsilon>0 esiste $ $G _1, \ldots G_N $ in modo che la distanza tra $G _N \ldots G_1 $ e $U $ sia al massimo $ \epsilon $ . Idealmente, il valore di $N $ necessario per raggiungere questa distanza di $ \epsilon $ dovrebbe ridimensionare Poly-logaritmicamente con $1/\ Epsilon $ .

Che cos'è un set di controllo universale in pratica?  Il set di controllo universale più semplice per le attività di controllo single-qubit è costituito solo da due controlli: il Gate Hadamard $H $ e il cosiddetto $T $ -Gate (noto anche come il Gate $ \ PI/8 $ ):

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ PI/4 } \end{ bmatrix } .
$$

Tuttavia, per motivi pratici relativi alla correzione degli errori quantistici, può essere più pratico considerare un set di controllo più ampio, ovvero uno che può essere generato usando $H $ e $T $ .
È possibile classificare i controlli Quantum in due categorie: Clifford Gates e il $T $ -Gate.
Questa suddivisione è utile perché in molti schemi di correzione degli errori quantistici i cosiddetti Clifford Gates sono facili da implementare, ovvero richiedono pochissime risorse in termini di operazioni e qubits per implementare la tolleranza di errore, mentre i cancelli non Clifford sono piuttosto costosi quando richiedono la tolleranza di errore. Il set standard di single-qubit Clifford Gates, [incluso per impostazione predefinita in Q #](xref:microsoft.quantum.libraries.standard.prelude), include

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2, \qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4h, $ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \END{ bmatrix } = t ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4.
$$

Qui le operazioni $X $ , $Y $ e $Z $ vengono usate con particolare frequenza e sono denominate [*operatori Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) dopo il creatore Wolfgang Pauli.
Insieme al Gate non-Clifford (il $T $ -Gate), queste operazioni possono essere composte per approssimare qualsiasi trasformazione unitaria in un singolo qubit.

Per altre informazioni su queste operazioni, le rappresentazioni della sfera Bloch e le implementazioni di Q #, vedere [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Come esempio del modo in cui è possibile compilare le trasformazioni unitarie da queste primitive, le tre trasformazioni illustrate nelle sfere Bloch precedenti corrispondono alla sequenza di controllo $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $.

Sebbene i precedenti costituiscano i controlli primitivi più diffusi per la descrizione delle operazioni sul livello logico dello stack (si pensi al livello logico come livello dell'algoritmo Quantum), è spesso utile considerare meno operazioni di base a livello algoritmico, ad esempio operazioni più vicine a un livello di descrizione della funzione. Fortunatamente, Q # dispone anche di metodi per l'implementazione di unitaries di livello superiore, che a loro volta consentono di implementare algoritmi di alto livello senza scomporre in modo esplicito tutti gli elementi fino a Clifford e $T $ -Gates.

La primitiva più semplice è il singolo qubit-Rotation. Vengono in genere considerate tre rotazioni a qubit singolo: $R _x $ , $R _y $ e $R _z $ . Per visualizzare l'azione della rotazione $R _x (\theta) $, ad esempio, si supponga di puntare il pollice destro lungo la direzione dell'asse $x $ della sfera Bloch e ruotare il vettore con la mano in un angolo di $ \ Theta/2 $ radianti. Questo fattore di confusione di $2 $ deriva dal fatto che i vettori ortogonali sono $180 ^ \circ $ a parte se tracciati nella sfera Bloch, ma sono in realtà $90 ^ \circ $ Degrees, a parte geometrica. Le matrici unitarie corrispondenti sono:

\begin{align *} &R_z (\theta) = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ Theta/2 } & 0 \\\\ 0 & e ^ {i \ Theta/2 } \end{ bmatrix } , \\ \\ &R_x (\theta) = e ^ {-i\theta x/2 } = HR_z (\theta) H = \begin{ bmatrix } \cos (\ Theta/2) &-i\sin (\ Theta/2) \\ \\ -i\sin (\ Theta/2) & \cos (\ Theta/2) \end{ bmatrix } , \\ \\ &R_y (\theta) = e ^ {-i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{ bmatrix } \cos (\ Theta/2) &-\sin (\ Theta/2) \\ \\ \sin (\ Theta/2) & \cos (\ Theta/2) \end{ bmatrix } . \end{align*}

Così come tutte e tre le rotazioni possono essere combinate insieme per eseguire una rotazione arbitraria in tre dimensioni, è possibile osservare dalla rappresentazione della sfera Bloch che qualsiasi matrice unitaria può essere scritta come una sequenza di tre rotazioni. In particolare, per ogni matrice unitaria $U esiste $ $ \Alpha, \beta, \gamma, \delta in $ modo che $U = e ^ {i \alpha } R_x (\beta) R_z (\gamma) R_x (\delta) $. Pertanto $R _z (\theta) $ e $H $ anche un set di controllo universale, sebbene non sia un set discreto perché $ \theta $ può assumere qualsiasi valore. Per questo motivo, e a causa delle applicazioni nella simulazione quantistica, le attività di controllo continuo sono cruciali per il calcolo quantistico, soprattutto a livello di progettazione dell'algoritmo Quantum. Per ottenere un'implementazione hardware a tolleranza di errore, questi ultimi verranno compilati in sequenze di controllo discrete che si avvicinano strettamente a queste rotazioni.
