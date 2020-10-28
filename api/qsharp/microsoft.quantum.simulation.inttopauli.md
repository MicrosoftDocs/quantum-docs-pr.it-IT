---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724846"
---
# <a name="inttopauli-function"></a>IntToPauli (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Converte un Integer in un operatore Pauli a qubit singola.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Input

### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Integer nell'intervallo `0..3` da convertire in operatori Pauli.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Operatore fornito da `[PauliI, PauliX, PauliY, PauliZ][idx]` .