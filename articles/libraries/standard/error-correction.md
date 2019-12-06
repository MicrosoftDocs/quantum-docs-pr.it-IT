---
title: 'Q # librerie standard-correzione errori | Microsoft Docs'
description: 'Librerie standard Q #-correzione errori'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e1b78cf94ae0a043ad275d4cb06b230eafd7fc85
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863198"
---
# <a name="error-correction"></a>Correzione errori #

## <a name="introduction"></a>Introduzione ##

Nell'elaborazione classica, se si vuole proteggere un bit da errori, spesso è sufficiente rappresentare tale bit per un *bit logico* ripetendo il bit di dati.
Ad esempio, Let $ \overline{0} = $0 è la codifica del bit di dati 0, in cui si usa la riga a sopra l'etichetta 0 per indicare che si tratta di una codifica di un bit nello stato 0.
Se si lascia in modo analogo $ \overline{1} = $111, è disponibile un semplice codice di ripetizione che protegge da qualsiasi errore di capovolgimento di un bit.
Ovvero, se uno dei tre bit viene capovolto, è possibile recuperare lo stato del bit logico prendendo un voto di maggioranza.
Sebbene la correzione degli errori classica sia un argomento molto più completo che questo particolare esempio (si consiglia di [introdurre la teoria di codifica](https://www.springer.com/us/book/9783540641339)), il codice di ripetizione precedente punta già a un possibile problema nella protezione delle informazioni sui quantum.
In particolare, il [teorema di no-cloning](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implica che se misuriamo ogni singolo qubit e scegliamo una maggioranza di voti per analogia con il codice classico precedente, abbiamo perso le informazioni precise che stiamo tentando di proteggere.

Nell'impostazione Quantum si noterà che la misurazione è problematica. È comunque possibile implementare la codifica precedente.
È utile eseguire questa operazione per vedere come è possibile generalizzare la correzione degli errori nel caso del quantum.
Quindi, Let $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$ e Let $ \ket{\overline{1}} = \ket{111}$.
Quindi, per linearità, abbiamo definito il nostro codice di ripetizione per tutti gli input; ad esempio, $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.
In particolare, con un errore di Flip bit $X _1 $ Act sulla qubit centrale, si noterà che la correzione necessaria in entrambi i rami è precisa $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).
\end{align} $ $

Per capire in che modo è possibile identificare questo problema senza misurare lo stato che si sta tentando di proteggere, è utile prendere nota della situazione di ogni singolo errore di Flip bit per gli stati logici:

| Errore $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X_0$ | $ \ket{100}$ | $ \ket{011}$ |
| $X_1$ | $ \ket{010}$ | $ \ket{101}$ |
| $X_2$ | $ \ket{001}$ | $ \ket{110}$ |

Per proteggere lo stato che si sta codificando, è necessario essere in grado di distinguere i tre errori l'uno dall'altro e dall'identità $ \boldone $ senza distinguere tra $ \ket{\overline{0}} $ e $ \ket{\overline{1}} $.
Se, ad esempio, si misura $Z _0 $, si ottiene un risultato diverso per $ \ket{\overline{0}} $ e $ \ket{\overline{1}} $ nel caso no-error, in modo da comprimere lo stato codificato.
D'altra parte, prendere in considerazione la misurazione $Z _0 Z_1 $, la parità dei primi due bit in ogni stato di base di calcolo.
Tenere presente che ogni misura di un operatore di Pauli controlla quale autovalore lo stato misurato corrisponde a, quindi, per ogni stato $ \ket{\psi} $ nella tabella precedente, è possibile calcolare $Z _0 Z_1 \ket{\psi} $ per verificare se si ottiene $ \pm\ket{\psi} $.
Si noti che $Z _0 Z_1 \ket{000} = \ket{000}$ e che $Z _0 Z_1 \ket{111} = \ket{111}$, in modo che si concluda che questa misurazione esegue la stessa operazione in entrambi gli stati codificati.
D'altra parte, $Z _0 Z_1 \ket{100} =-\ket{100}$ e $Z _0 Z_1 \ket{011} =-\ket{011}$, quindi il risultato della misurazione $Z _0 Z_1 $ rivela informazioni utili sull'errore che si è verificato.

Per evidenziare questo problema, si ripete la tabella precedente, ma si aggiungono i risultati della misurazione $Z _0 Z_1 $ e $Z _1 Z_2 $ a ogni riga.
I risultati di ogni misura vengono identificati in base al segno di autovalore osservato, ovvero $ + $ o $-$, corrispondenti ai valori di Q # `Result` rispettivamente di `Zero` e `One`.

| Errore $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | Risultato della $Z _0 Z_1 $ | Risultato della $Z _1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X_0$ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X_1$ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X_2$ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

In questo modo, i risultati delle due misure determinano in modo univoco quale errore di Flip bit si è verificato, ma senza rivelare informazioni sullo stato codificato.
Questi risultati vengono chiamati una *sindrome*e si fa riferimento al processo di mapping di una sindrome all'errore che lo ha causato come *ripristino*.
In particolare, viene evidenziato che il ripristino è una procedura di inferenza *classica* che accetta come input la sindrome che si è verificata e restituisce una prescrizione per la risoluzione degli errori che potrebbero essersi verificati.

> [!NOTE]
> Il codice di capovolgimento dei bit precedente può essere corretto solo in caso di errori di singolo capovolgimento. ovvero un'operazione `X` che agisce su un singolo qubit.
> L'applicazione di `X` a più di un qubit eseguirà il mapping di $ \ket{\overline{0}} $ a $ \ket{\overline{1}} $ dopo il ripristino.
> Analogamente, l'applicazione di un'operazione di capovolgimento della fase `Z` eseguirà il mapping di $ \ket{\overline{1}} $ a $-\ket{\overline{1}} $, quindi eseguirà il mapping di $ \ket{\overline{+}} $ a $ \ket{\overline{-}} $.
> Più in generale, è possibile creare codici per gestire un numero maggiore di errori e gestire $Z $ Errors, nonché $X $ Errors.

Il modo in cui è possibile descrivere le misurazioni nella correzione degli errori quantistici che operano allo stesso modo su tutti gli Stati del codice è l'essenza del *formalismo di stabilizzazione*.
Il Canon Q # fornisce un Framework per descrivere la codifica e la decodifica da codici di stabilizzatori e per descrivere la modalità di ripristino da errori.
In questa sezione viene descritto questo Framework e la relativa applicazione per alcuni semplici codici di correzione degli errori quantistici.

> [!TIP]
> Un'introduzione completa al formalismo di stabilizzatore esula dall'ambito di questa sezione.
> Ci riferiamo ai lettori interessati a saperne di più su [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-q"></a>Rappresentazione di codici di correzione degli errori in Q # ##

Per specificare i codici di correzione degli errori, il Canon Q # offre diversi tipi distinti definiti dall'utente:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: indica che un registro di qubits deve essere interpretato come il blocco di codice di un codice di correzione degli errori.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: indica che una matrice di risultati di misurazione deve essere interpretata come la sindrome misurata in un blocco di codice.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: indica che è necessario usare una funzione *classica* per interpretare una sindrome e restituire una correzione da applicare.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: indica che un'operazione accetta qubits che rappresentano i dati insieme a qubits ancilla aggiornati per produrre un blocco di codice di un codice di correzione degli errori.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: indica che un'operazione scompone un blocco di codice di un errore durante la correzione del codice nei dati qubits e Ancilla qubits utilizzati per rappresentare le informazioni sulla sindrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: indica un'operazione da usare per estrarre le informazioni sulla sindrome da un blocco di codice, senza compromettere lo stato protetto dal codice.

Infine, la canonica fornisce il tipo <xref:microsoft.quantum.errorcorrection.qecc> per raccogliere gli altri tipi necessari per definire un codice di correzione degli errori Quantum. Associato a ogni codice Quantum di stabilizzatore è la lunghezza del codice $n $, il numero $k $ dei qubits logici e la distanza minima $d $, spesso raggruppati insieme nella notazione ⟦ $n $, $k $, $d $ ⟧. Ad esempio, la funzione <xref:microsoft.quantum.errorcorrection.bitflipcode> definisce il codice ⟦ 3, 1, 1 ⟧ bit flip:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Si noti che il tipo di `QECC` *non include una* funzione di ripristino.
Questo consente di modificare la funzione di ripristino usata per correggere gli errori senza modificare la definizione del codice stesso. Questa possibilità è particolarmente utile quando si incorporano commenti e suggerimenti dalle misurazioni di caratterizzazione nel modello presupposto dal ripristino.

Una volta definito un codice in questo modo, è possibile usare l'operazione <xref:microsoft.quantum.errorcorrection.recover> per correggere gli errori:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Questo aspetto viene esaminato più dettagliatamente nell' [esempio di codice di Flip bit](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).

Oltre al codice di Flip bit, il canone Q # viene fornito con le implementazioni del [codice perfetto qubit](https://arxiv.org/abs/quant-ph/9602019)e il [codice qubit](https://arxiv.org/abs/quant-ph/9705052), che possono correggere un errore arbitrario qubit singolo.
