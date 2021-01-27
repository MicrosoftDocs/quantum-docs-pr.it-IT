---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operazione ApplyDeltaParity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851103"
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