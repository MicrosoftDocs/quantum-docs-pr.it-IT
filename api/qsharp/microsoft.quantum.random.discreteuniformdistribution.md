---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853728"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Input

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Integer più piccolo da disegnare.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Integer più grande da disegnare.



## <a name="output--discretedistribution"></a>Output: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Una distribuzione le cui variabili casuali sono numeri interi nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.

## <a name="example"></a>Esempio

Il seguente frammento Q # esegue in modo casuale un dado a sei lati:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)