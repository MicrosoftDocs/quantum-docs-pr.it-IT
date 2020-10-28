---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operazione GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712578"
---
# <a name="getqubitsavailabletouse-operation"></a>Operazione GetQubitsAvailableToUse

Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Pacchetto [](https://nuget.org/packages/)


Restituisce il numero di qubits attualmente disponibili per l'utilizzo.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits che possono essere allocati in un' `using` istruzione.
Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)