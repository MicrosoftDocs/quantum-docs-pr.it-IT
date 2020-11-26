---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229988"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce il numero totale di qubits che devono essere allocati per applicare l'operazione restituita da @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Input

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Errore di destinazione $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di coefficienti da specificare durante la preparazione di uno stato misto.



## <a name="output--mixedstatepreparationrequirements"></a>Output: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Descrizione del numero di qubits necessari in totale e per ciascuno degli indici e dei registri di Garbage Collection utilizzati dalla @"microsoft.quantum.preparation.purifiedmixedstate" funzione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)