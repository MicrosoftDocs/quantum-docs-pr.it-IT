---
title: Misurazioni di Pauli | Microsoft Docs
description: Misurazioni di Pauli
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183710"
---
# <a name="pauli-measurements"></a>Misurazioni di Pauli

Nelle discussioni precedenti sono state illustrate le misure di base computazionali.  Sono infatti presenti altre misurazioni comuni che si verificano in quantum computing che, dal punto di vista della notazione, sono utili per esprimere in termini di misurazioni di base computazionale.  Il set più comune di queste misure sono le *misurazioni di Pauli*.  In questi casi, è comune discutere la misurazione di un operatore Pauli, in generale un operatore come $X, Y, Z $ o $Z \otimes Z, X\otimes X, X\otimes Y $ e così via.  La discussione sulla misurazione in termini di operatori Pauli è particolarmente comune nel sottocampo della correzione degli errori quantistici. In Q # si segue una convenzione simile; viene ora illustrata questa visualizzazione alternativa delle misurazioni.

Prima di approfondire i dettagli su come pensare a una misurazione di Pauli, è utile considerare la misurazione di un singolo qubit all'interno di un computer Quantum allo stato quantum.  Si supponga di avere un $n stato quantum $-qubit; quindi, la misurazione di un qubit immediatamente regola la metà delle possibilità di $2 ^ n $ che lo stato potrebbe essere in.  In altre parole, la misurazione proietta lo stato del quantum su uno dei due spazi.  Possiamo generalizzare il modo in cui pensiamo alla misurazione per riflettere questo aspetto.

Per identificare in modo conciso questi spazi, è necessario un linguaggio per descriverli.  Un modo per eseguire questa operazione consiste nel descrivere i due sottospazii specificando questi ultimi tramite una matrice che dispone solo di due autovalori univoci, presi per convenzione come $ \pm $1.  L'esempio più semplice è:

$ $ Z = \begin{Bmatrix} 1 & 0 \\\\ 0 &-1 \end{Bmatrix}.
$$

La matrice Pauli-$Z $ ha chiaramente due autovettori $ \ket{0}$ e $ \ket{1}$ con autovalori $ \pm $1.  Quindi, se misuriamo il valore di qubit e otteniamo $ \ket{0}$ we si trovano nel eigenspace $ + $1 (il set di tutti i vettori che sono formati di somme di autovettori con solo autovalori positivi o solo negativi) dell'operatore e se misuriamo $ \ket{1}$ we sono in $-$1 ei Genspace di $Z $.  Questo processo viene definito nel linguaggio delle misurazioni di Pauli come "misurazione di Pauli $Z $" ed è interamente equivalente all'esecuzione di una misurazione di base computazionale.

Naturalmente, la matrice di $2 \ Times $2 che è una trasformazione unitaria di $Z $ soddisfa anche questo criterio.  Ciò significa che è possibile prendere in considerazione anche Matrix $A = U ^ \dagger Z U $, per qualsiasi matrice unitaria $U $, per assegnare a una matrice che definisce i due risultati di una misurazione nel rispettivo $ \pm $1 autovettori.  La notazione delle misurazioni di Pauli fa riferimento a questo oggetto identificando $X, Y, Z $ misurations come misurazioni equivalenti che possono essere eseguite per ottenere informazioni da un qubit.  Queste misurazioni sono fornite di seguito per praticità.

$ $ \begin{array}{| c | c |} \text{Pauli Measurement} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{Array} $ $

In altre parole, l'uso di questo linguaggio "Measure $Y $" equivale all'applicazione di $HS ^ \dagger $, quindi alla misurazione della base computazionale, in cui $S $ è il cosiddetto punto di controllo della fase specificato da

$ $ \begin{Bmatrix}1 & 0\\\\ 0 & i\end {Bmatrix}.
$$

Equivale inoltre a applicare $HS ^ \dagger $ al vettore di stato quantum e quindi a misurare $Z $.  Lo stato corretto viene quindi trovato tramite la trasformazione di nuovo in base al calcolo, che equivale a applicare $SH $ al vettore di stato quantum.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Informazioni sui risultati classici Q # ottenuti dallo stato quantum
In Q # si direbbe il risultato, ovvero le informazioni classiche estratte dall'interazione con lo stato, è $j $ che si trova nel set $\{0, 1\}$ se il risultato è in $ (-1) ^ j $ eigenspace dell'operatore Pauli misurato.

Le misurazioni degli operatori qubit di Pauli sono definite in modo analogo, come illustrato di seguito:

$ $ Z\otimes Z = \begin{Bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {Bmatrix}.
$$

Di conseguenza, i prodotti tensore di due operatori Pauli-$Z $ formano una matrice costituita da due spazi costituiti dagli autovalori $ + $1 e $-$1.  Come nel caso di un singolo qubit, entrambe costituiscono un mezzo di spazio che significa che la metà dello spazio vettoriale accessibile appartiene al eigenspace $ + $1 e la metà rimanente al eigenspace $-$1.  In generale, è facile vedere dalla definizione del prodotto tensore che tutti i prodotti tensori di Pauli-$Z $ Operators e Identity obbediscono anche a questo.  Ad esempio,

$ $ Z\otimes\boldone = \begin{Bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ fine {Bmatrix}.
$$

Come prima, eventuali trasformazioni unitarie di tali matrici descrivono anche due spazi con etichetta di $ \pm $1 autovalori.  Ad esempio, $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ dall'identità che $Z = HXH $.  Analogamente al caso qubit, tutte le misurazioni di qubit Pauli possono essere scritte come $U ^ \dagger (Z\otimes \ID) U $ per $4 \ Times $4 matrici unitarie $U $.  Vengono enumerate le trasformazioni nella tabella seguente, in cui viene introdotta la convenienza dello scambio che scambia qubits $0 $ e $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{ CNOT}\_{01}$:

$ $ \begin{array}{| c | c |} \text{Pauli Measurement} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\ otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ operatorName {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \ operatorName {CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_@no__t _31_ (H\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{Array} $ $

Il Gate $ \operatorname{CNOT}\_{10}$ appare per il seguente motivo.  Ogni misura di Pauli che non include la matrice $ \boldone $ equivale a un elemento unitario a $Z \otimes Z $ in base ai motivi precedenti.  Gli autovalori di $Z \otimes Z $ dipendono solo dalla parità dei qubits che comprendono ogni vettore di base computazionale e le operazioni non controllate visualizzate in questo elenco servono a calcolare questa parità e archiviarle nel primo bit.  Quindi, una volta misurato il primo bit, è possibile recuperare l'identità dello spazio a metà risultante, equivalente alla misurazione dell'operatore Pauli.

Una nota aggiuntiva, sebbene possa essere tentata di presumere che la misurazione $Z \otimes Z $ corrisponda alla misurazione $Z \otimes \ID $ e quindi a $ \ID \otimes Z $, questo presupposto sarebbe falso.  Il motivo è che la misurazione $Z \otimes Z $ proietta lo stato del quantum nel autostato $ + $1 o $-$1 di questi operatori.  Misurando $Z \otimes \ID $, quindi $ \ID \otimes Z $ proietta prima il vettore di stato del quantum in una metà dello spazio $Z \otimes \ID $ e quindi su uno spazio metà di $ \ID \otimes Z $.  Poiché sono presenti quattro vettori di base di calcolo, l'esecuzione di entrambe le misurazioni riduce lo stato a un trimestre e quindi lo riduce a un singolo vettore di base computazionale.


## <a name="correlations-between-qubits"></a>Correlazioni tra qubits
Un altro modo per esaminare i prodotti tensori di Paulis, ad esempio $X \otimes X $ o $Z \otimes Z $, consiste nel fatto che queste misurazioni consentono di esaminare le informazioni archiviate nelle correlazioni tra i due qubits.  Misurazione $X \otimes \ID $ consente di esaminare le informazioni archiviate localmente nel primo qubit.  Sebbene entrambi i tipi di misurazioni siano ugualmente utili nell'elaborazione quantistica, il primo illumina la potenza del quantum computing. Si rivela che in quantum computing spesso le informazioni che si desidera apprendere non vengono archiviate in un singolo qubit, ma piuttosto archiviate in modo non locale in tutti i qubits in una sola volta e analizzate solo tramite una misurazione congiunta con $Z \otimes Z $, le informazioni diventano manifesto.

È possibile misurare anche operatori Pauli arbitrari, ad esempio $X \otimes Y \otimes Z \otimes \boldone $.  Tutti questi prodotti tensore di operatori Pauli hanno solo due autovalori $ \pm $1 e entrambi eigenspaces costituiscono metà spazi dell'intero spazio vettoriale.  Coincidono quindi con i requisiti indicati sopra.

In Q # tali misure restituiscono $j $ Se la misurazione restituisce un risultato nel eigenspace di segno $ (-1) ^ j $.  L'uso di questa funzionalità come funzionalità incorporata in Q # è utile perché la misurazione di tali operatori richiede lunghe catene di trasformazioni di base e non controllate, per descrivere diagonalizing $U $ Gate necessari per esprimere l'operazione come prodotto tensore di $Z $ e $ \ID $.  Grazie alla semplice possibilità di specificare che si desidera eseguire una di queste misurazioni predefinite, non è necessario preoccuparsi di come trasformare la base in modo che una misura di base computazionale fornisca le informazioni necessarie.  Q # gestisce automaticamente tutte le trasformazioni di base necessarie. Vedere le informazioni [di riferimento sulla libreria Q # per le misurazioni Pauli](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>Teorema di no-cloning
Le informazioni sul quantum sono potenti.  Ci permette di eseguire operazioni straordinarie, ad esempio numeri di fattore esponenzialmente più veloci rispetto agli algoritmi classici più noti, oppure simulare in modo efficiente i sistemi elettronici correlati che richiedono in genere un costo esponenziale per simulare in modo accurato.  Esistono tuttavia alcune limitazioni alla potenza del quantum computing.  Una limitazione di questo tipo viene fornita dal *teorema di no-cloning*.

Il teorema dell'assenza di clonazione è denominato.
Non consente la clonazione di stati Quantum generici da un computer Quantum.
La prova del teorema è molto semplice.
Anche se una prova completa del teorema di non clonazione è un po' troppo tecnica per la nostra discussione, la prova del teorema nel caso in cui il computer Quantum in questione non abbia qubits ancilla aggiuntivi è all'interno dell'ambito (ancilla qubits sono qubits utilizzati per zero spazio durante un calcolo e facilmente utilizzabile e gestito in Q #, vedere <xref:microsoft.quantum.techniques.qubits>).
Per tale computer quantistico, l'operazione di clonazione deve essere una matrice unitaria. Non è consentita la misurazione, perché danneggia lo stato del quantum che si sta tentando di clonare. La matrice unitaria desiderata deve avere la proprietà che $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ per qualsiasi stato $ \ket{\psi} $.
La proprietà Linearity della moltiplicazione di matrici implica quindi che per qualsiasi secondo stato del quantum $ \ket{\Phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\Phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Phi} \ KET{0}+ \frac{1}{\sqrt{2}} U\ket {\ psi} \ KET{0}@no__ t_9_ \\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\Phi}\ket{\Phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\Phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\Phi} + \ket{\psi} \right) \right).
\end{align}

Si tratta di un'intuizione fondamentale dietro il teorema di no-cloning: qualsiasi dispositivo che copia uno stato quantum sconosciuto deve causare errori in almeno alcuni degli stati copiati.  Sebbene il presupposto fondamentale che il Cloner agisca in modo lineare sullo stato di input possa essere violato tramite l'aggiunta di ancilla e la misurazione del qubits Ancilla, tali interazioni perdono anche le informazioni sul sistema tramite le statistiche di misurazione e impediscono clonazione esatta anche in questi casi.  Per una prova più completa del teorema di non clonazione, vedere [per altre informazioni](xref:microsoft.quantum.more-information).

Il teorema di no-cloning è importante per la comprensione qualitativa del quantum computing, perché se è possibile clonare gli Stati Quantum a costo elevato, è possibile ottenere una capacità quasi magica di apprendere dagli Stati Quantum.  In realtà, è possibile violare il principio di incertezza decantato di Heisenberg.  In alternativa, è possibile usare un Cloner ottimale per ottenere un singolo campione da una distribuzione quantistica complessa e apprendere tutti gli elementi che è possibile conoscere per la distribuzione da un solo esempio.  Si tratta di un'operazione analoga all'indicizzazione di una moneta e all'osservazione delle teste, quindi quando si comunica a un amico il risultato che li risponde "Ah la distribuzione di tale moneta deve essere di Bernoulli con $p = 0.512643 \ ldots $!".  Un'istruzione di questo tipo non è sensical, perché una certa quantità di informazioni (il risultato delle intestazioni) non è semplicemente in grado di fornire le informazioni necessarie per codificare la distribuzione senza sostanziali informazioni precedenti.  In modo analogo, senza informazioni precedenti, non è possibile clonare perfettamente uno stato quantico così come non è possibile preparare un insieme di tali monete senza conoscere $p $.

Le informazioni non sono gratuite in quantum computing.  Ogni qubit misurato fornisce un solo bit di informazioni e il teorema di no-cloning Mostra che non è presente alcuna backdoor che può essere sfruttata per aggirare il compromesso fondamentale tra le informazioni acquisite sul sistema e il disturbo richiamato al suo interno.

