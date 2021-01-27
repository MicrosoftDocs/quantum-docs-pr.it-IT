---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Operazione ApplyIfElseBC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841829"
---
# <a name="applyifelsebc-operation"></a>Operazione ApplyIfElseBC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica una delle due operazioni controllabili, a seconda del valore di un bit classico.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Descrizione

Dato un bit `bit` , applica l'operazione `trueOp` con `trueInput` come input quando `bit` è `true` e si applica `falseOp(falseInput)` quando `bit` è `false` .

## <a name="input"></a>Input

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Valore booleano utilizzato per determinare se `trueOp` `falseOp` viene applicato o.


### <a name="trueop--t--unit--is-ctl"></a>trueOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Operazione controllabile da applicare quando `bit` è `true` .


### <a name="trueinput--t"></a>trueInput: t

Input da fornire a `trueOp` quando `bit` è `true` .


### <a name="falseop--u--unit--is-ctl"></a>falseOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Operazione controllabile da applicare quando `bit` è `false` .


### <a name="falseinput--u"></a>falseInput:' U

Input da fornire a `falseOp` quando `bit` è `false` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione `trueOp` da applicare in modo condizionale.
### <a name="u"></a>' U

Tipo di input dell'operazione `falseOp` da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)