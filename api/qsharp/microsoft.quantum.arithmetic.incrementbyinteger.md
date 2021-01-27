---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operazione IncrementByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843163"
---
# <a name="incrementbyinteger-operation"></a>Operazione IncrementByInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Si supponga che `target` codifica un Unsigned Integer $x $ in una codifica little-endian e che `increment` sia uguale a $a $.
Questa operazione implementa quindi l'unità $ \ket{x} \mapsto \ket{x + a} $, in cui viene eseguita l'aggiunta modulo $2 ^ n $, dove $n = \texttt{Length (target!)} $.

## <a name="input"></a>Input

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Integer in base al quale `target` viene incrementato.


### <a name="target--littleendian"></a>destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro Quantum che codifica un Unsigned Integer usando la codifica little-endian.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

