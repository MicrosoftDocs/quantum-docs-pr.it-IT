---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718007"
---
# <a name="applyifzeroca-operation"></a>Operazione ApplyIfZeroCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione unitaria condizionata a un valore di risultato classico che è zero.

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` . Se `One` , non viene eseguita alcuna operazione in `target` .
Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).

## <a name="input"></a>Input

### <a name="result--__invalidresult__"></a>risultato: __non <Result> valido__

Risultato della misurazione che controlla se op viene applicato o meno.


### <a name="op--t--unit-adj--ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione da applicare in modo condizionale.


### <a name="target--t"></a>destinazione:' t

Input a cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. Quantum. Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. Quantum. Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)