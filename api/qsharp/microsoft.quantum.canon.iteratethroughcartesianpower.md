---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operazione IterateThroughCartesianPower
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206477"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operazione IterateThroughCartesianPower

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione per ogni indice nella potenza cartesiana di un intervallo di numeri interi.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descrizione

Applica in modo iterativo un'operazione per ogni elemento di una potenza cartesiana dell'intervallo `0..(bound - 1)` .

## <a name="input"></a>Input

### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Potenza cartesiana a cui `0..(bound - 1)` deve essere generato l'intervallo.


### <a name="bound--int"></a>associato: [int](xref:microsoft.quantum.lang-ref.int)

Specifica dell'intervallo su cui eseguire l'iterazione, dato come lunghezza dell'intervallo.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da chiamare per ogni elemento della potenza cartesiana specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)