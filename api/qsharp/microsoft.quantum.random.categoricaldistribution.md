---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842356"
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

## <a name="example"></a>Esempio

Il codice Q # seguente visualizzerà 0 con probabilità 30% e 1 con probabilità 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```