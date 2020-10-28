---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Operazione ApplyToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717447"
---
# <a name="applytoelementca-operation"></a>Operazione ApplyToElementCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione a un determinato elemento di una matrice.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Descrizione

`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .

## <a name="input"></a>Input

### <a name="op--t--unit-adj--ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

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
- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)