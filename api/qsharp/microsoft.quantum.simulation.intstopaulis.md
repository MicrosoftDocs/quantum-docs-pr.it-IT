---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842233"
---
# <a name="intstopaulis-function"></a>IntsToPaulis (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte una matrice di numeri interi in una matrice di operatori Pauli a qubit singola.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Input

### <a name="ints--int"></a>int: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di numeri interi nell'intervallo `0..3`  da convertire in operatori Pauli.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice `paulis` di operatori Pauli `Pauli[]` la cui lunghezza `ints` `paulis[idxPauli]` è uguale all'elemento di `[PauliI, PauliX, PauliY, PauliZ]` specificato da `ints[idxPauli]` .