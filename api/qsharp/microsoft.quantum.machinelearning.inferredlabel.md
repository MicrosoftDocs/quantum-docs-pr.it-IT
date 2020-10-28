---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722519"
---
# <a name="inferredlabel-function"></a>InferredLabel (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


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