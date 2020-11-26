---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229206"
---
# <a name="inttopauli-function"></a>IntToPauli (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte un Integer in un operatore Pauli a qubit singola.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Input

### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Integer nell'intervallo `0..3` da convertire in operatori Pauli.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Operatore fornito da `[PauliI, PauliX, PauliY, PauliZ][idx]` .