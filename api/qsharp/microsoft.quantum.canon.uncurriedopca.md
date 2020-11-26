---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216388"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.
Il modificatore `CA` indica che le operazioni sono controllabili e adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Funzione che restituisce le operazioni.



## <a name="output--tu--unit--is-adj--ctl"></a>Output: (' t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo argomento di una funzione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo argomento di una funzione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)