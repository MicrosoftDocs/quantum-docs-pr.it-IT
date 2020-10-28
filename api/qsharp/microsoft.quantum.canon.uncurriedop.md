---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715238"
---
# <a name="uncurriedop-function"></a>UncurriedOp (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Input

### <a name="curriedop--t---u--unit"></a>curriedOp: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit) 

Funzione che restituisce le operazioni.



## <a name="output--tu--unit"></a>Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit) 

Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo input di un'operazione sottoposta a currying.
### <a name="u"></a>' U

Tipo del secondo input di un'operazione sottoposta a currying.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)