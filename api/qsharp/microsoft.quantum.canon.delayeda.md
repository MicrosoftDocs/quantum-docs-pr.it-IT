---
uid: Microsoft.Quantum.Canon.DelayedA
title: Funzione delaya
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716246"
---
# <a name="delayeda-function"></a>Funzione delaya

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit-adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione da applicare in seguito all'applicazione del valore restituito


### <a name="arg--t"></a>ARG:' t

Input a cui `op` viene applicata l'operazione.



## <a name="output--unit--unit-adj"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ unità

Nuova operazione applicata con l' `op` input `arg`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Delayed](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)