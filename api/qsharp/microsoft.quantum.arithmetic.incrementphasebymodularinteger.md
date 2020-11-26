---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operazione IncrementPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222882"
---
# <a name="incrementphasebymodularinteger-operation"></a>Operazione IncrementPhaseByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue un incremento modulare di un registro qubit da una costante Integer.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.
L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} i numeri interi sono codificati in formato little-endian in base a QFT.

## <a name="input"></a>Input

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Incremento Integer $a $ da aggiungere a $y $.


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ che mods $y + a $.


### <a name="target--phaselittleendian"></a>destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Integer $y $ in formato little-endian con codifica fase `increment` a cui viene aggiunto $a $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Presuppone che `target` il bit più alto sia impostato su 0.
Presuppone inoltre che il valore di target sia minore di $N $.

Per il diagramma di circuito e la spiegazione, vedere la figura 5 [della pagina 5 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. IncrementByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)