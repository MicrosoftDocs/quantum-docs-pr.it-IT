---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fa204433dc8195dd27fa40980fb2262f8a3848bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204845"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="fn--u---t"></a>FN:' U->' t

Funzione che trasforma l'input specificato in un form previsto dall'operazione.


### <a name="op--t--unit--is-adj--ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da trasformare.



## <a name="output--u--unit--is-adj--ctl"></a>Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. compose](xref:Microsoft.Quantum.Canon.Composed)