---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operazione ApplyToMostA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717209"
---
# <a name="applytomosta-operation"></a>Operazione ApplyToMostA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .

## <a name="input"></a>Input

### <a name="op--t--unit-adj"></a>op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione da applicare.


### <a name="targets--t"></a>destinazioni:' t []

Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. Quantum. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. Quantum. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)