---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814175"
---
# <a name="normaldistribution-function"></a>NormalDistribution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce una distribuzione normale con una media e una varianza specificate.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Input

### <a name="mean--double"></a>media: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>varianza: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Esempio

Il codice seguente disegna 10 campioni dalla distribuzione normale con media 2 e deviazione standard 0,1:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Random. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)