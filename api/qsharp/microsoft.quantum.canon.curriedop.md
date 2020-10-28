---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716369"
---
# <a name="curriedop-function"></a>CurriedOp (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


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