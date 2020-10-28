---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: IdxToUnitary (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: a142d8a5af56a43de6341e3c0bdc77f50030f06e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710601"
---
# <a name="idxtounitary-function"></a>IdxToUnitary (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Usato nell'implementazione di `PauliBlockEncoding`

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="genfun--int---generatorindex"></a>genFun: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="genidxtounitary--generatorindex---qubit--unit-adj--ctl"></a>genIdxToUnitary: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL





## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. PauliBlockEncoding](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)