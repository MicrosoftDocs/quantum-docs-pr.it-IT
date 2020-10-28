---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709428"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Input

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale più piccolo da disegnare.


### <a name="max--double"></a>numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale più grande da disegnare.



## <a name="output--continuousdistribution"></a>Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Una distribuzione le cui variabili casuali sono numeri reali nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)