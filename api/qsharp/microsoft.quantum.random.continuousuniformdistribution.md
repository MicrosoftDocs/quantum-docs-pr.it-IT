---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842323"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Esempio

Il seguente frammento Q # disegna in modo casuale un angolo compreso tra $0 $ e $2 \Pi $:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)