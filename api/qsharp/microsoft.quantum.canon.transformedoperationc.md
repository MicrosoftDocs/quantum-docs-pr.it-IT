---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715322"
---
# <a name="transformedoperationc-function"></a>TransformedOperationC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="fn--u---t"></a>FN:' U->' t

Funzione che trasforma l'input specificato in un form previsto dall'operazione.


### <a name="op--t--unit-ctl"></a>op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da trasformare.



## <a name="output--u--unit-ctl"></a>Output:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

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