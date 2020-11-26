---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204692"
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