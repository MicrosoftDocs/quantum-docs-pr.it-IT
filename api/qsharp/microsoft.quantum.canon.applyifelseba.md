---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: Operazione ApplyIfElseBA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844990"
---
# <a name="applyifelseba-operation"></a>Operazione ApplyIfElseBA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica una delle due operazioni adjointable, a seconda del valore di un bit classico.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Descrizione

Dato un bit `bit` , applica l'operazione `trueOp` con `trueInput` come input quando `bit` è `true` e si applica `falseOp(falseInput)` quando `bit` è `false` .

## <a name="input"></a>Input

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Valore booleano utilizzato per determinare se `trueOp` `falseOp` viene applicato o.


### <a name="trueop--t--unit--is-adj"></a>trueOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione adjointable da applicare quando `bit` è `true` .


### <a name="trueinput--t"></a>trueInput: t

Input da fornire a `trueOp` quando `bit` è `true` .


### <a name="falseop--u--unit--is-adj"></a>falseOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione adjointable da applicare quando `bit` è `false` .


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