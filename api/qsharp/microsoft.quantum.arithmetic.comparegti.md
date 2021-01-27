---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Operazione CompareGTI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843307"
---
# <a name="comparegti-operation"></a>Operazione CompareGTI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Wrapper per il confronto di valori integer: `result = x > y` .

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primo $n numero di $ bit


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Secondo numero $n $ bit


### <a name="result--qubit"></a>risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Verrà capovolto se $x > y $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

