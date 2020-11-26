---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operazione IterateThroughCartesianProduct
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206443"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operazione IterateThroughCartesianProduct

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione per ogni indice nel prodotto cartesiano di diversi intervalli.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descrizione

Applica in modo iterativo un'operazione per ogni elemento del prodotto cartesiano di `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Input

### <a name="bounds--int"></a>limiti: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice che specifica gli intervalli di cui eseguire l'iterazione, con ogni intervallo specificato come lunghezza intera.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da chiamare per ogni elemento del prodotto cartesiano specificato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)