---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operazione DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851130"
---
# <a name="drawrandomint-operation"></a>Operazione DrawRandomInt

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Esempio

Il seguente frammento Q # esegue in modo casuale un dado a sei lati:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)