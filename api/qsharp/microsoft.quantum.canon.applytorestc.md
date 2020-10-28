---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operazione ApplyToRestC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717097"
---
# <a name="applytorestc-operation"></a>Operazione ApplyToRestC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .

## <a name="input"></a>Input

### <a name="op--t--unit-ctl"></a>op:' t [] => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare.


### <a name="targets--t"></a>destinazioni:' t []

Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToRest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. Quantum. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. Quantum. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)