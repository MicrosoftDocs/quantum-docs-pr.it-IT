---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840776"
---
# <a name="curriedop-function"></a>CurriedOp (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una versione sottoposta a currying di un'operazione su due input.

In altre condizioni, data un'operazione con due input, questa funzione applica la $f isomorfismo (x, y) \equiv f (x) (y) di curry per restituire un'operazione di un input che restituisce un'operazione di un input.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Input

### <a name="op--tu--unit"></a>op: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit) 

Operazione il cui input è una coppia.



## <a name="output--t---u--unit"></a>Output: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit) 

Operazione che accetta il primo elemento di una coppia e restituisce un'operazione che accetta come input il secondo elemento dell'input dell'operazione originale.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo componente di una funzione definita per le coppie.
### <a name="u"></a>' U

Tipo del secondo componente di una funzione definita per le coppie.

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```