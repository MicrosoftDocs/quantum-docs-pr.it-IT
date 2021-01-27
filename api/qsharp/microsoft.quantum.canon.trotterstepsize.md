---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840081"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola le dimensioni del passaggio Trotter nell'implementazione ricorsiva dell'algoritmo di simulazione Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Input

### <a name="order--int"></a>ordine: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Questa operazione usa una convenzione di indicizzazione diversa da [quanti-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). In particolare, `DecomposedIntoTimeStepsCA(_, 4)` corrisponde al valore scalare $p _2 (\lambda) $ in quanti-pH/0508139.