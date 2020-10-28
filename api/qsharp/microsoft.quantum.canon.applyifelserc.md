---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718119"
---
# <a name="applyifelserc-operation"></a>Operazione ApplyIfElseRC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una delle due operazioni controllabili, a seconda del valore di un risultato classico.

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a>Descrizione

Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .

## <a name="input"></a>Input

### <a name="result--__invalidresult__"></a>risultato: __non <Result> valido__

Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.


### <a name="zeroop--t--unit-ctl"></a>zeroOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione controllabile da applicare quando `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: t

Input da fornire a `zeroOp` quando `result == Zero` .


### <a name="oneop--u--unit-ctl"></a>oneOp:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione controllabile da applicare quando `result == One` .


### <a name="oneinput--u"></a>oneInput:' U

Input da fornire a `oneOp` quando `result == One` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.
### <a name="u"></a>' U

Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)