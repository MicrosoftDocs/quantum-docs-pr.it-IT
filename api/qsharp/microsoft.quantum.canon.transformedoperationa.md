---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840134"
---
# <a name="transformedoperationa-function"></a>TransformedOperationA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="fn--u---t"></a>FN:' U->' t

Funzione che trasforma l'input specificato in un form previsto dall'operazione.


### <a name="op--t--unit--is-adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione da trasformare.



## <a name="output--u--unit--is-adj"></a>Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U



## <a name="example"></a>Esempio

La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per trasformare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input in un'operazione che accetta input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. compose](xref:Microsoft.Quantum.Canon.Composed)