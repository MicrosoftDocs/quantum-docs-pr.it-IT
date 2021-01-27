---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operazione GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853238"
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