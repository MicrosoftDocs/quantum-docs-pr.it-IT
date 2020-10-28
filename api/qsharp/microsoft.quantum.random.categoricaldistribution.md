---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722816"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


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