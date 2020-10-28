---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operazione IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721110"
---
# <a name="incrementbyinteger-operation"></a>Operazione IncrementByInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

