---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operazione ApplyIfCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209622"
---
# <a name="applyifca-operation"></a>Operazione ApplyIfCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione unitaria condizionata su un bit classico.

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` . Se `false` , non viene eseguita alcuna operazione in `target` .
Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).

## <a name="input"></a>Input

### <a name="op--t--unit--is-adj--ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da applicare in modo condizionale.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

valore booleano che controlla se op viene applicato o meno.


### <a name="target--t"></a>destinazione:' t

Input a cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)