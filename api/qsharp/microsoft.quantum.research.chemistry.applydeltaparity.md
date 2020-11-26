---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operazione ApplyDeltaParity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225755"
---
# <a name="applydeltaparity-operation"></a>Operazione ApplyDeltaParity

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Calcola la differenza di parità tra una PQRS precedente... termini e il PQRS successivo... termine. Questa differenza viene calcolata in un qubit ausiliario.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]

Elenco di indici per PQRS precedenti... termini.


### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]

Elenco di indici per PQRS successivi... termini.


### <a name="aux--qubit"></a>Aux: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ausiliari su cui vengono archiviati i risultati del calcolo della parità.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit agito da tutti PQRS... termini.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Si presuppone che gli indici di P < Q < R < S <... sia per prevPQ che per nextPQ.