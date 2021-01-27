---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operazione IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840292"
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



## <a name="example"></a>Esempio

Data un'operazione `op` , i due frammenti di codice seguenti sono equivalenti:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)