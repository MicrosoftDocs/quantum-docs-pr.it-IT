---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operazione DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847616"
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

## <a name="example"></a>Esempio

Il seguente frammento Q # disegna in modo casuale un angolo compreso tra $0 $ e $2 \Pi $:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Commenti

Ha esito negativo se `max <= min` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)