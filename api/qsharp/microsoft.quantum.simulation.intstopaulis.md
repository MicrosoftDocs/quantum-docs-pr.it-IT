---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709453"
---
# <a name="intstopaulis-function"></a>IntsToPaulis (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Converte una matrice di numeri interi in una matrice di operatori Pauli a qubit singola.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Input

### <a name="ints--int"></a>int: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di numeri interi nell'intervallo `0..3`  da convertire in operatori Pauli.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice `paulis` di operatori Pauli `Pauli[]` la cui lunghezza `ints` `paulis[idxPauli]` è uguale all'elemento di `[PauliI, PauliX, PauliY, PauliZ]` specificato da `ints[idxPauli]` .