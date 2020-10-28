---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operazione ApplyToElementC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717450"
---
# <a name="applytoelementc-operation"></a>Operazione ApplyToElementC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione a un determinato elemento di una matrice.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Descrizione

`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .

## <a name="input"></a>Input

### <a name="op--t--unit-ctl"></a>op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare.


### <a name="index--int"></a>Indice: [int](xref:microsoft.quantum.lang-ref.int)

Indice nella matrice di destinazioni.


### <a name="targets--t"></a>destinazioni:' t []

Matrice di destinazioni possibili per `op` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)