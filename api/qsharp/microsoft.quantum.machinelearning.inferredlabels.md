---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196362"
---
# <a name="inferredlabels-function"></a>InferredLabels (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Data una matrice di probabilità di classificazione e una distorsione, restituisce l'etichetta dedotta da ogni probabilità.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Input

### <a name="bias--double"></a>distorsione: [Double](xref:microsoft.quantum.lang-ref.double)

Distorsione tra due classi, in genere il risultato del training di un classificatore.


### <a name="probabilities--double"></a>probabilità: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di probabilità di classificazione per un set di esempi, in genere risultante dalla stima delle frequenze di classificazione.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Etichetta dedotta da ogni probabilità di classificazione.