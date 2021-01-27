---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842242"
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