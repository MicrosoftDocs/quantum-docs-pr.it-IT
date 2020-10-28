---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operazione GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712589"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operazione GetQubitsAvailableToBorrow

Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Pacchetto [](https://nuget.org/packages/)


Restituisce il numero di qubits attualmente disponibili per il prestito.
Sono inclusi i qubits inutilizzati; Ciò è incluso il qubits restituito da `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits che possono essere allocati in un' `borrowing` istruzione.
Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)