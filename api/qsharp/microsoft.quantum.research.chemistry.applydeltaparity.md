---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operazione ApplyDeltaParity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723978"
---
# <a name="applydeltaparity-operation"></a>Operazione ApplyDeltaParity

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto [](https://nuget.org/packages/)


Calcola la differenza di parità tra una PQRS precedente... termini e il PQRS successivo... termine. Questa differenza viene calcolata in un qubit ausiliario.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
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