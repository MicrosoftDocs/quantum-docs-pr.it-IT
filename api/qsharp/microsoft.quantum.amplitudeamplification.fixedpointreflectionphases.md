---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845849"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases (funzione)

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola le fasi di Reflection parziali per l'amplificazione dell'ampiezza a virgola fissa.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Input

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Numero di query per la preparazione dello stato Oracle. Deve essere un intero dispari.


### <a name="successmin--double"></a>successMin: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilità di riuscita minima di destinazione.



## <a name="output--reflectionphases"></a>Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Matrice di fasi che è possibile usare nell'implementazione dell'algoritmo Quantum a virgola fissa.

## <a name="references"></a>Riferimenti

Si usano le fasi nell'"amplificazione dell'ampiezza a virgola fissa con un numero ottimale di query"

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Vedere anche "metodologia di controlli Quantum compositi"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) per le fasi nel `RotationPhases` formato.