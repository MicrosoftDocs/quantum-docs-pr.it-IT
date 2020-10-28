---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710940"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Data una distribuzione continua, restituisce una nuova distribuzione che trasforma l'originale in base a una determinata funzione.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Input

### <a name="transform--double---double"></a>trasformazione: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)

Funzione che trasforma le variabili della distribuzione originale nella distribuzione trasformata.


### <a name="distribution--continuousdistribution"></a>distribuzione: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Distribuzione originale da trasformare.



## <a name="output--continuousdistribution"></a>Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Nuova distribuzione correlata a `distribution` dalla trasformazione fornita da `transform` .