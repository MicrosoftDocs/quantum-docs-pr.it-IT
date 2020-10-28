---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operazione IncrementPhaseByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721074"
---
# <a name="incrementphasebyinteger-operation"></a>Operazione IncrementPhaseByInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Si supponga che `target` codifica un Unsigned Integer $x $ in una codifica little-endian e che `increment` sia uguale a $a $.
Questa operazione implementa quindi l'unità $ \ket{x} \mapsto \ket{x + a} $, in cui viene eseguita l'aggiunta modulo $2 ^ n $, dove $n = \texttt{Length (target!)} $.

## <a name="input"></a>Input

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Integer in base al quale `target` viene incrementato.


### <a name="target--phaselittleendian"></a>destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Un registro Quantum codifica un Unsigned Integer usando la codifica little-endian nella doppia (QFT).



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Si noti che il circuito è stato semplificato perché l'incremento è una costante classica, non un registro quantico.

Vedere la figura della [ pagina 6 di arXiv: quanti-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) per la spiegazione e il diagramma del circuito.

## <a name="references"></a>Riferimenti

- [*Thomas G. Draper* , arXiv: quanti-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)