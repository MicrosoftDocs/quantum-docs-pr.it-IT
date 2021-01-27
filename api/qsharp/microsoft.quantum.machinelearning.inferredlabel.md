---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848411"
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