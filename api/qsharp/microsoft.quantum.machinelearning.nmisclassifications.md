---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196311"
---
# <a name="nmisclassifications-function"></a>NMisclassifications (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dato un set di etichette derivate e un set di etichette corrette, restituisce il numero di indici in cui ogni set di etichette è diverso.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Input

### <a name="proposed--int"></a>proposta: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>effettivo: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di indici di questo `idx` tipo `inferredLabels[idx] != actualLabels[idx]` .