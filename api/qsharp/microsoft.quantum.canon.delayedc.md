---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716215"
---
# <a name="delayedc-function"></a>DelayedC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl"></a>op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare in seguito all'applicazione del valore restituito


### <a name="arg--t"></a>ARG:' t

Input a cui `op` viene applicata l'operazione.



## <a name="output--unit--unit-ctl"></a>Output: [Unit](xref:microsoft.quantum.lang-ref.unit) => [unità](xref:microsoft.quantum.lang-ref.unit) di unità CTL

Nuova operazione applicata con l' `op` input `arg`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Delayed](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)