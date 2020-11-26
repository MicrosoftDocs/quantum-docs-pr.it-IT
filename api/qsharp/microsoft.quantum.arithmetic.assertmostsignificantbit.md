---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operazione AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223783"
---
# <a name="assertmostsignificantbit-operation"></a>Operazione AssertMostSignificantBit

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Asserisce che il qubit più significativo di un registro qubit che rappresenta un Unsigned Integer si trova in un determinato stato.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="value--__invalidresult__"></a>valore: __non <Result> valido__

Valore del bit più alto da dichiarare.


### <a name="number--littleendian"></a>numero: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Intero senza segno di cui viene verificato il bit più alto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

La versione controllata di questa operazione ignora i controlli.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Intrinsic. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)