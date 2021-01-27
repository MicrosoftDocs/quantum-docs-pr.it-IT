---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851981"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.
Il modificatore `C` indica che le operazioni sono controllabili.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Funzione che restituisce le operazioni.



## <a name="output--tu--unit--is-ctl"></a>Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo argomento di una funzione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo argomento di una funzione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)