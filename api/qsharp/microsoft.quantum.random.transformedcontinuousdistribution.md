---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226265"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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