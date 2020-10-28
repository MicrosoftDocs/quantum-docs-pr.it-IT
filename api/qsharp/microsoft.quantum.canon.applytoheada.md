---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operazione ApplyToHeadA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717254"
---
# <a name="applytoheada-operation"></a>Operazione ApplyToHeadA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione al primo elemento di una matrice.

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .

## <a name="input"></a>Input

### <a name="op--t--unit-adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione da applicare.


### <a name="targets--t"></a>destinazioni:' t []

Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Quantum. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)