---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715221"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.
Il modificatore `A` indica che le operazioni sono adjointable.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit-adj"></a>curriedOp:' t->' U => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

Funzione che restituisce le operazioni.



## <a name="output--tu--unit-adj"></a>Output: (t,' U) => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo argomento di una funzione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo argomento di una funzione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)