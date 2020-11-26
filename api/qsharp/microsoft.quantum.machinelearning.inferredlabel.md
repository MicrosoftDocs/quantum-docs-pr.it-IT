---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211781"
---
# <a name="inferredlabel-function"></a>InferredLabel (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Data la probabilità di classificazione e la distorsione, restituisce l'etichetta dedotta da tale probabilità.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Input

### <a name="bias--double"></a>distorsione: [Double](xref:microsoft.quantum.lang-ref.double)

Distorsione tra due classi, in genere il risultato del training di un classificatore.


### <a name="probability--double"></a>probabilità: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilità di classificazione per un campione specifico, in genere risultanti dalla stima della relativa frequenza di classificazione.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Etichetta dedotta dalla probabilità di classificazione specificata.