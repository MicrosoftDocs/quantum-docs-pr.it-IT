---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funzione di classificazione errata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853921"
---
# <a name="misclassifications-function"></a>Funzione di classificazione errata

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dato un set di etichette derivate e un set di etichette corrette, restituisce gli indici per i casi in cui ogni set di etichette è diverso.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Input

### <a name="inferredlabels--int"></a>inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Etichette dedotte per un determinato training o set di convalida.


### <a name="actuallabels--int"></a>actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Etichette vere per un determinato training o set di convalida.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di indici di questo `idx` tipo `inferredLabels[idx] != actualLabels[idx]` .

## <a name="example"></a>Esempio

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```