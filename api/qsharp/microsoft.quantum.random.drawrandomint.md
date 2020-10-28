---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operazione DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724661"
---
# <a name="drawrandomint-operation"></a>Operazione DrawRandomInt

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Disegna un intero casuale in un intervallo inclusivo specificato.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Input

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Integer più piccolo da disegnare.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Integer più grande da disegnare.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Intero nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)