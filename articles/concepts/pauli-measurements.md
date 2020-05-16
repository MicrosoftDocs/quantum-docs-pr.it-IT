---
title: Misurazioni di Pauli
description: Informazioni su come usare le operazioni di misurazione di Pauli a qubit singola e a più livelli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3ce9c0ea13d62bd662f3ccc450c385799ddb264b
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426560"
---
# <a name="pauli-measurements"></a>Misurazioni di Pauli

Nelle discussioni precedenti sono state illustrate le misure di base computazionali.
In realtà, esistono altre misure comuni che si verificano in quantum computing che, dal punto di vista della notazione, sono utili per esprimere in termini di misurazioni di base computazionale.
Quando si lavora con Q #, il tipo più comune di misurazioni che verrà eseguito sarà probabilmente *misurazioni di Pauli*, che generalizzano le misurazioni di base computazionali per includere le misurazioni in altre basi e la parità tra qubits diversi.
In questi casi, è comune discutere la misurazione di un operatore Pauli, in generale un operatore come $X, Y, Z $ o $Z \otimes Z, X\otimes X, X\otimes Y $ e così via.

> [!TIP]
> In Q #, gli operatori di qubit Pauli sono in genere rappresentati da matrici di tipo `Pauli[]` .
> Ad esempio, per rappresentare $X \otimes Z \otimes Y $, è possibile usare la matrice `[PauliX, PauliZ, PauliY]` .

La discussione sulla misurazione in termini di operatori Pauli è particolarmente comune nel sottocampo della correzione degli errori quantistici.
In Q # si segue una convenzione simile. viene ora illustrata questa visualizzazione alternativa delle misurazioni.

Prima di approfondire i dettagli su come pensare a una misurazione di Pauli, è utile considerare la misurazione di un singolo qubit all'interno di un computer Quantum allo stato quantum.
Si supponga di avere un $n stato quantum $-qubit; quindi, la misurazione di un qubit immediatamente regola la metà delle possibilità di $2 ^ n $ che lo stato potrebbe essere in.
In altre parole, la misurazione proietta lo stato del quantum su uno dei due spazi.
Possiamo generalizzare il modo in cui pensiamo alla misurazione per riflettere questa intuizione.

Per identificare in modo conciso questi spazi, è necessario un linguaggio per descriverli.
Per descrivere i due sottospazi, è possibile specificarli tramite una matrice in cui sono presenti solo due autovalori univoci, presi dalla Convenzione come $ \pm $1.
Per un semplice esempio di descrizione di sottospazi in questo modo, prendere in considerazione $Z $:

$ $ \begin{align} Z & = \begin{Bmatrix} 1 & 0 \\ \\ 0 &-1 \end{Bmatrix}.
\end{align} $ $

Leggendo gli elementi diagonali di Pauli-$Z $ Matrix, è possibile osservare che $Z $ ha due autovettori, $ \ket {0} $ e $ \ket {1} $, con gli autovalori corrispondenti $ \pm $1.
Quindi, se misuriamo il qubit e otteniamo `Zero` (corrispondente allo stato $ \ket {0} $), sappiamo che lo stato del qubit è un autostato $ + $1 dell'operatore $Z $.
Analogamente, se si ottiene `One` , sappiamo che lo stato di qubit è un autostato $-$1 di $Z $.
Questo processo è indicato nel linguaggio delle misurazioni di Pauli come "misurazione di Pauli $Z $" ed è completamente equivalente all'esecuzione di una misurazione di base computazionale.

Qualsiasi matrice $2 \ Times $2 che rappresenta una trasformazione unitaria di $Z $ soddisfa anche questo criterio.
È anche possibile usare una matrice $A = U ^ \dagger Z U $, in cui $U $ è qualsiasi altra matrice unitaria, per fornire una matrice che definisce i due risultati di una misurazione nel relativo $ \pm $1 autovettori.
La notazione delle misurazioni di Pauli fa riferimento a questa equivalenza unitaria identificando $X, Y, Z $ misurations come misurazioni equivalenti per ottenere informazioni da un qubit.
Queste misurazioni sono fornite di seguito per praticità.


|Misurazione di Pauli  |Trasformazione unitaria  |
|-------------------|------------------------|
| $Z $               | $ \boldone $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\dagger} $         |

In altre parole, l'uso di questo linguaggio "Measure $Y $" equivale all'applicazione $HS ^ \dagger $, quindi alla misurazione della base di calcolo, in cui [`S`](xref:microsoft.quantum.intrinsic.s) è un'operazione Quantum intrinseca talvolta denominata "Phase Gate" e può essere simulata dalla matrice unitaria.

$ $ \begin{align} S = \begin{Bmatrix} 1 & 0 \\ \\ 0 & i \end{Bmatrix}.
\end{align} $ $

Equivale inoltre a applicare $HS ^ \dagger $ al vettore di stato quantum e quindi a misurare $Z $, in modo che l'operazione seguente sia equivalente a `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Lo stato corretto viene quindi trovato trasformando di nuovo in base al calcolo, che equivale a applicare $SH $ al vettore di stato quantum; nel frammento di codice precedente, la trasformazione di nuovo in base al calcolo viene gestita automaticamente dall'utilizzo del `within … apply` blocco.

In Q #, diciamo il risultato---ovvero, le informazioni classiche estratte dall'interazione con lo stato---sono fornite da un `Result` valore $j \In \\ {\Texttt{zero}, \texttt{One} \\ } $ che indica se il risultato è in $ (-1) ^ j $ eigenspace dell'operatore Pauli misurato.


## <a name="multiple-qubit-measurements"></a>Misurazioni a più qubit

Le misurazioni degli operatori qubit di Pauli sono definite in modo analogo, come illustrato di seguito:

$ $ Z\otimes Z = \begin{Bmatrix}1 &0 &0&0 \\ \\ 0&-1&0&0 \\ \\ 0&0&-1&0 \\ \\ 0&0&0&1 \ end {Bmatrix}.
$$

Di conseguenza, i prodotti tensore di due operatori Pauli-$Z $ formano una matrice costituita da due spazi costituiti dagli autovalori $ + $1 e $-$1.
Come nel caso di un singolo qubit, entrambe costituiscono un mezzo di spazio che significa che la metà dello spazio vettoriale accessibile appartiene al eigenspace $ + $1 e la metà rimanente al eigenspace $-$1.
In generale, è facile vedere dalla definizione del prodotto tensore che tutti i prodotti tensori di Pauli-$Z $ Operators e Identity obbediscono anche a questo.
Ad esempio,

$ $ \begin{align} Z \otimes \boldone = \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{Bmatrix}.
\end{align} $ $

Come prima, eventuali trasformazioni unitarie di tali matrici descrivono anche due spazi con etichetta di $ \pm $1 autovalori.
Ad esempio, $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ dall'identità che $Z = HXH $.
Analogamente al caso qubit, tutte le misurazioni di qubit Pauli possono essere scritte come $U ^ \dagger (Z\otimes \ID) U $ per $4 \ Times $4 matrici unitarie $U $. Le trasformazioni vengono enumerate nella tabella seguente.

> [!NOTE]
> Nella tabella seguente viene usato $ \operatorname{SWAP} $ per indicare la matrice $ $ \begin{align} \operatorname{SWAP} & = \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix}\right) \end{align} $ $ usato per simulare l'operazione intrinseca [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Misurazione di Pauli     |Trasformazione unitaria  |
|----------------------|------------------------|
| $Z \otimes \boldone $ | $ \boldone \otimes \boldone $ |
| $Z \otimes \boldone $ | $ \boldone\otimes \boldone $ |
| $X \otimes \boldone $ | $H \otimes \boldone $ |
| $Y \otimes \boldone $ | $HS ^ \dagger\otimes \boldone $ |
| $ \boldone \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \boldone \otimes X $ | $ (H\otimes \boldone) \operatorname{SWAP} $ |
| $ \boldone \otimes Y $ | $ (HS ^ \dagger\otimes \boldone) \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT} \_ {10} $ |
| $X \otimes Z $ | $ \operatorname{CNOT} \_ {10} (H\otimes \boldone) $ |
| $Y \otimes Z $ | $ \operatorname{CNOT} \_ {10} (HS ^ \dagger\otimes \boldone) $ |
| $Z \otimes X $ | $ \operatorname{CNOT} \_ {10} (\boldone\otimes H) $ |
| $X \otimes X $ | $ \operatorname{CNOT} \_ {10} (H\otimes H) $ |
| $Y \otimes X $ | $ \operatorname{CNOT} \_ {10} (HS ^ \dagger\otimes H) $ |
| $Z \otimes Y $ | $ \operatorname{CNOT} \_ {10} (\BOLDONE \otimes HS ^ \dagger) $ |
| $X \otimes Y $ | $ \operatorname{CNOT} \_ {10} (H\otimes HS ^ \dagger) $ |
| $Y \otimes Y $ | $ \operatorname{CNOT} \_ {10} (HS ^ \dagger\otimes HS ^ \dagger) $ |

In questo caso, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operazione viene visualizzata per il motivo seguente.
Ogni misura di Pauli che non include la matrice $ \boldone $ equivale a un elemento unitario a $Z \otimes Z $ in base ai motivi precedenti.
Gli autovalori di $Z \otimes Z $ dipendono solo dalla parità dei qubits che comprendono ogni vettore di base computazionale e le operazioni non controllate servono per calcolare questa parità e archiviarla nel primo bit.
Quindi, una volta misurato il primo bit, è possibile recuperare l'identità dello spazio a metà risultante, equivalente alla misurazione dell'operatore Pauli.

Una nota aggiuntiva: Sebbene sia possibile tentare di presupporre che la misurazione $Z \otimes Z $ corrisponda alla misurazione sequenziale $Z \otimes \mathbb {1} $ e quindi a $ \mathbb {1} \otimes Z $, questo presupposto sarà false.
Il motivo è che la misurazione $Z \otimes Z $ proietta lo stato del quantum nel autostato $ + $1 o $-$1 di questi operatori.
Misurando $Z \otimes \mathbb {1} $, quindi $ \mathbb {1} \otimes Z $ proietta prima il vettore di stato del quantum in una metà dello spazio $Z \otimes \mathbb {1} $ e quindi su uno spazio metà di $ \mathbb {1} \otimes Z $.
Poiché sono presenti quattro vettori di base di calcolo, l'esecuzione di entrambe le misurazioni riduce lo stato a un trimestre e quindi lo riduce a un singolo vettore di base computazionale.

## <a name="correlations-between-qubits"></a>Correlazioni tra qubits
Un altro modo per esaminare i prodotti tensori di matrici di Pauli come $X \otimes X $ o $Z \otimes Z $ consiste nel fatto che queste misurazioni consentono di esaminare le informazioni archiviate nelle correlazioni tra i due qubits.
Misurazione $X \otimes \ID $ consente di esaminare le informazioni archiviate localmente nel primo qubit.
Sebbene entrambi i tipi di misurazioni siano ugualmente utili nell'elaborazione quantistica, il primo illumina la potenza del quantum computing.
Si rivela che in quantum computing, spesso le informazioni che si desidera apprendere non vengono archiviate in un singolo qubit, ma piuttosto archiviate in modo non locale in tutti i qubits in una sola volta e quindi esaminate solo tramite una misurazione congiunta, ad esempio $Z \otimes Z $, le informazioni diventano manifeste.

Nella correzione degli errori, ad esempio, si desidera spesso conoscere l'errore che si è verificato durante l'apprendimento di nulla sullo stato che si sta tentando di proteggere.
Nell' [esempio di codice di tipo bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) viene illustrato un esempio di come è possibile utilizzare misurazioni come $Z \otimes Z \otimes \ID $ e $ \Id \otimes Z \otimes z $.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

È possibile misurare anche operatori Pauli arbitrari, ad esempio $X \otimes Y \otimes Z \otimes \boldone $.
Tutti questi prodotti tensore di operatori Pauli hanno solo due autovalori $ \pm $1 e entrambi eigenspaces costituiscono metà spazi dell'intero spazio vettoriale.
Coincidono quindi con i requisiti indicati sopra.

In Q # tali misure restituiscono $j $ Se la misurazione restituisce un risultato nel eigenspace di segno $ (-1) ^ j $.
La presenza di misurazioni di Pauli come funzionalità incorporata in Q # è utile perché la misurazione di tali operatori richiede lunghe catene di trasformazioni di base e non controllate per descrivere diagonalizing $U $ Gate necessari per esprimere l'operazione come prodotto tensore di $Z $ e $ \ID $.
Con la possibilità di specificare che si desidera eseguire una di queste misurazioni predefinite, non è necessario preoccuparsi di come trasformare la base in modo che una misura di base computazionale fornisca le informazioni necessarie.
Q # gestisce automaticamente tutte le trasformazioni di base necessarie.
Per ulteriori informazioni, vedere le [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operazioni e.

## <a name="the-no-cloning-theorem"></a>Teorema di no-cloning

Le informazioni sul quantum sono potenti.
Ci permette di eseguire operazioni straordinarie, ad esempio numeri di fattore esponenzialmente più veloci rispetto agli algoritmi classici più noti, oppure simulare in modo efficiente i sistemi elettronici correlati che richiedono in genere un costo esponenziale per simulare in modo accurato.
Esistono tuttavia alcune limitazioni alla potenza del quantum computing.
Una limitazione di questo tipo viene fornita dal *teorema di no-cloning*.

Il teorema dell'assenza di clonazione è denominato.
Non consente la clonazione di stati Quantum generici da un computer Quantum.
La prova del teorema è molto semplice.
Anche se una prova completa del teorema di non clonazione è un po' troppo tecnica per la nostra discussione, la prova, nel caso di nessun qubits ausiliario aggiuntivo, è all'interno dell'ambito (qubits ausiliari sono qubits usati per lo spazio scratch durante un calcolo e sono facilmente utilizzabili e gestiti in Q #, vedere la pagina relativa a [qubits in prestito](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

Per tale computer quantistico, l'operazione di clonazione deve essere descritta da una matrice unitaria.
Non è consentita la misurazione, perché danneggia lo stato del quantum che si sta tentando di clonare.
Per simulare l'operazione di clonazione, è necessario che la matrice unitaria venga utilizzata per la proprietà che $ $ U \ket{\psi} \ket {0} = \ket{\psi} \ket{\psi} $ $ per qualsiasi stato $ \ket{\psi} $.
La proprietà Linearity della moltiplicazione di matrici implica quindi che per qualsiasi secondo stato del quantum $ \ket{\Phi} $,

$ $ \begin{align} U \left [\frac {1} {\sqrt {2} } \left (\ket{\Phi} + \ket{\psi} \right) \right] \ket {0} & = \frac {1} {\sqrt {2} } U\ket {\ Phi} \ KET {0} + \frac {1} {\sqrt {2} } U\ket {\ psi} \ KET {0} \\ \\ & = \frac {1} {\sqrt {2} } \left (\ket{\Phi} \ket{\Phi} + \ket{\psi} \ket{\psi} \right) \\ \\ & \ne \left (\frac {1} {\sqrt {2} } \left (\ket{\Phi} + \ket{\psi} \right) \right) \otimes \left (\frac {1} {\sqrt {2} } \left (\ket{\Phi} + \ket{\psi} \right) \right).
\end{align} $ $

Si tratta di un'intuizione fondamentale dietro il teorema di no-cloning: qualsiasi dispositivo che copia uno stato quantum sconosciuto deve causare errori in almeno alcuni degli stati copiati.
Sebbene il presupposto fondamentale che il Cloner agisca in modo lineare sullo stato di input possa essere violato tramite l'aggiunta e la misurazione di qubits ausiliari, tali interazioni perdono anche le informazioni sul sistema attraverso le statistiche di misurazione e impediscono la clonazione esatta in tali casi.
Per una prova più completa del teorema di non clonazione, vedere [per altre informazioni](xref:microsoft.quantum.more-information).

Il teorema di no-cloning è importante per la comprensione qualitativa del quantum computing, perché se è possibile clonare gli Stati Quantum a costo elevato, è possibile ottenere una capacità quasi magica di apprendere dagli Stati Quantum.
In realtà, è possibile violare il principio di incertezza decantato di Heisenberg.
In alternativa, è possibile usare un Cloner ottimale per ottenere un singolo campione da una distribuzione quantistica complessa e apprendere tutti gli elementi che è possibile conoscere per la distribuzione da un solo esempio.
Si tratta di un'operazione analoga all'indicizzazione di una moneta e all'osservazione delle teste, quindi quando si comunica a un amico il risultato che li risponde "Ah la distribuzione di tale moneta deve essere di Bernoulli con $p = 0.512643 \ ldots $!".  Un'istruzione di questo tipo non è sensical, perché una certa quantità di informazioni (il risultato delle intestazioni) non è semplicemente in grado di fornire le informazioni necessarie per codificare la distribuzione senza sostanziali informazioni precedenti.
In modo analogo, senza informazioni precedenti, non è possibile clonare perfettamente uno stato quantico così come non è possibile preparare un insieme di tali monete senza conoscere $p $.

Le informazioni non sono gratuite in quantum computing.
Ogni qubit misurato fornisce un solo bit di informazioni e il teorema di no-cloning Mostra che non è presente alcuna backdoor che può essere sfruttata per aggirare il compromesso fondamentale tra le informazioni acquisite sul sistema e il disturbo richiamato al suo interno.
