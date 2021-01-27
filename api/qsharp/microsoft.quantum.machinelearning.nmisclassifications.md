---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853907"
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

## <a name="example"></a>Esempio

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```