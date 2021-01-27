---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: operazione _iterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853571"
---
# <a name="_iteratethroughcartesianpower-operation"></a>operazione _iterateThroughCartesianPower

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Scorre una variabile tramite un prodotto cartesiano [0, Bounds [0]-1] × [0, Bounds [1]-1] × [0, Bounds [length (Bounds)-1]-1] e chiama op (arr) per ogni elemento del prodotto cartesiano

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Input

### <a name="length--int"></a>Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

