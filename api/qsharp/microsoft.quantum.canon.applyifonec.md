---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Operazione ApplyIfOneC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209418"
---
# <a name="applyifonec-operation"></a>Operazione ApplyIfOneC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione controllabile con un valore di risultato classico che è uno.

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` . Se `Zero` , non viene eseguita alcuna operazione in `target` .
Il suffisso `C` indica che l'operazione da applicare è controllabile.

## <a name="input"></a>Input

### <a name="result--__invalidresult__"></a>risultato: __non <Result> valido__

Risultato della misurazione che controlla se op viene applicato o meno.


### <a name="op--t--unit--is-ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Operazione da applicare in modo condizionale.


### <a name="target--t"></a>destinazione:' t

Input a cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Quantum. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. Quantum. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)