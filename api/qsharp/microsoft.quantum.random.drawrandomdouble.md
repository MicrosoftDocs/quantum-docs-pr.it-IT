---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operazione DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192945"
---
# <a name="drawrandomdouble-operation"></a>Operazione DrawRandomDouble

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Disegna un numero reale casuale in un intervallo inclusivo specificato.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Input

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale più piccolo da disegnare.


### <a name="max--double"></a>numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale più grande da disegnare.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale casuale nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.

## <a name="remarks"></a>Osservazioni

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)