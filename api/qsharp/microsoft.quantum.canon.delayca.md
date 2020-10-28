---
uid: Microsoft.Quantum.Canon.DelayCA
title: Operazione DelayCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716271"
---
# <a name="delayca-operation"></a>Operazione DelayCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una determinata operazione con un ritardo.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Descrizione

Data un'operazione e un input per tale operazione, applica l'operazione dopo che è stato fornito un input aggiuntivo.
In particolare, l'espressione `Delay(op, arg, _)` è un'operazione che si applica `op` a `arg` quando viene chiamato.
Expression `Delay(op,arg,_)` consente di ritardare l'applicazione di `op` .

## <a name="input"></a>Input

### <a name="op--t--unit-ctl--adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Operazione da applicare.


### <a name="arg--t"></a>ARG:' t

Input a cui viene applicata l'operazione.


### <a name="aux--unit"></a>Aux: [unità](xref:microsoft.quantum.lang-ref.unit)

Argomento utilizzato per ritardare l'applicazione dell'operazione utilizzando l'applicazione parziale.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. Delayed](xref:Microsoft.Quantum.Canon.Delayed)