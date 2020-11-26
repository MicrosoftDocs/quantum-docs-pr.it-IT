---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operazione GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201411"
---
# <a name="getqubitsavailabletouse-operation"></a>Operazione GetQubitsAvailableToUse

Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce il numero di qubits attualmente disponibili per l'utilizzo.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits che possono essere allocati in un' `using` istruzione.
Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)