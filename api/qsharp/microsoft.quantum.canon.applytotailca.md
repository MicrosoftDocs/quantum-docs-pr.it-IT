---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operazione ApplyToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841191"
---
# <a name="applytotailca-operation"></a>Operazione ApplyToTailCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione all'ultimo elemento di una matrice.

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .

## <a name="input"></a>Input

### <a name="op--t--unit--is-adj--ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da applicare.


### <a name="targets--t"></a>destinazioni:' t []

Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. Quantum. Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. Quantum. Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)