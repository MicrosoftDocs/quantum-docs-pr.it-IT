---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operazione DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723989"
---
# <a name="drawrandomdouble-operation"></a>Operazione DrawRandomDouble

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)