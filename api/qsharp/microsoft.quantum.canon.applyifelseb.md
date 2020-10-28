---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Operazione ApplyIfElseB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718218"
---
# <a name="applyifelseb-operation"></a>Operazione ApplyIfElseB

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una delle due operazioni, a seconda del valore di un bit classico.

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a>Descrizione

Dato un bit `bit` , applica l'operazione `trueOp` con `trueInput` come input quando `bit` è `true` e si applica `falseOp(falseInput)` quando `bit` è `false` .

## <a name="input"></a>Input

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Valore booleano utilizzato per determinare se `trueOp` `falseOp` viene applicato o.


### <a name="trueop--t--unit"></a>trueOp:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da applicare quando `bit` è `true` .


### <a name="trueinput--t"></a>trueInput: t

Input da fornire a `trueOp` quando `bit` è `true` .


### <a name="falseop--u--unit"></a>falseOp:' U = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da applicare quando `bit` è `false` .


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