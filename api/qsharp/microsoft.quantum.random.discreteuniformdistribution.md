---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720294"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)