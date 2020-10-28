---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715207"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.
Il modificatore `CA` indica che le operazioni sono controllabili e adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp: t->' U => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Funzione che restituisce le operazioni.



## <a name="output--tu--unit-ctl--adj"></a>Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo argomento di una funzione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo argomento di una funzione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)