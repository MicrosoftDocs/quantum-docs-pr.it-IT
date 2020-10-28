---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722480"
---
# <a name="inferredlabels-function"></a>InferredLabels (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


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