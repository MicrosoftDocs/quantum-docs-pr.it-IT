---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operazione GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201462"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operazione GetQubitsAvailableToBorrow

Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce il numero di qubits attualmente disponibili per il prestito.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits che possono essere presi in prestito e che non verranno allocati come parte di un' `borrowing` istruzione.
Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)