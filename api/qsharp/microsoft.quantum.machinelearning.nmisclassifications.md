---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709736"
---
# <a name="nmisclassifications-function"></a>NMisclassifications (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Dato un set di etichette derivate e un set di etichette corrette, restituisce il numero di indici in cui ogni set di etichette è diverso.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Input

### <a name="proposed--int"></a>proposta: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>effettivo: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di indici di questo `idx` tipo `inferredLabels[idx] != actualLabels[idx]` .