---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715210"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.
Il modificatore `C` indica che le operazioni sono controllabili.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: t->' U => [unità](xref:microsoft.quantum.lang-ref.unit) CTL

Funzione che restituisce le operazioni.



## <a name="output--tu--unit-ctl"></a>Output: (t,' U) => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo argomento di una funzione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo argomento di una funzione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)