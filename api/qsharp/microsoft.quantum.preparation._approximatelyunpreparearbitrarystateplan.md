---
uid: Microsoft.Quantum.Preparation._ApproximatelyUnprepareArbitraryStatePlan
title: Funzione _ApproximatelyUnprepareArbitraryStatePlan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 4050a65b0830da4c3d73e84942780aa7c2643c76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724202"
---
# <a name="_approximatelyunpreparearbitrarystateplan-function"></a>Funzione _ApproximatelyUnprepareArbitraryStatePlan

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Passaggio di implementazione della procedura di preparazione dello stato arbitrario.

```qsharp
function _ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>coefficienti: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl: [intervallo](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PrepareArbitraryState](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft. Quantum. Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)