---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716218"
---
# <a name="delayedca-function"></a>DelayedCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl--adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Operazione da applicare in seguito all'applicazione del valore restituito


### <a name="arg--t"></a>ARG:' t

Input a cui `op` viene applicata l'operazione.



## <a name="output--unit--unit-ctl--adj"></a>Output: [Unit](xref:microsoft.quantum.lang-ref.unit) => [unità](xref:microsoft.quantum.lang-ref.unit) di unità CTL + ADJ

Nuova operazione applicata con l' `op` input `arg`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Delayed](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)