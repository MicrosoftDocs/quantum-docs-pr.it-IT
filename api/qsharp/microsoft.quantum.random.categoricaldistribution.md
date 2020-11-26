---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210251"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce una distribuzione categorica discreta, in cui viene specificata in modo esplicito la probabilità per ogni elenco finito di risultati specificati.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Input

### <a name="probs--double"></a>Probe: [Double](xref:microsoft.quantum.lang-ref.double)[]

Probabilità per ogni risultato della distribuzione categorica.
Queste probabilità potrebbero non essere normalizzate, ma devono essere tutte non negative.



## <a name="output--discretedistribution"></a>Output: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Indice `i` con probabilità `probs[i] / sum` , dove `sum` è la somma di `probs` specificata da `Fold(PlusD, 0.0, probs)` .