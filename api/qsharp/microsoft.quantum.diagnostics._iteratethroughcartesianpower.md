---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: operazione _iterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713138"
---
# <a name="_iteratethroughcartesianpower-operation"></a>operazione _iterateThroughCartesianPower

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Scorre una variabile tramite un prodotto cartesiano [0, Bounds [0]-1] × [0, Bounds [1]-1] × [0, Bounds [length (Bounds)-1]-1] e chiama op (arr) per ogni elemento del prodotto cartesiano

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Input

### <a name="length--int"></a>Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

