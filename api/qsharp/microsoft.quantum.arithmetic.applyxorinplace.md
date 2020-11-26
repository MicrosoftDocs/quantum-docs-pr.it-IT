---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operazione ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210114"
---
# <a name="applyxorinplace-operation"></a>Operazione ApplyXorInPlace

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione XOR bit per bit tra un intero classico e un Integer rappresentato da un registro di qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Applica `X` le operazioni a qubits in un registro Little-Endian basato su 1 bit in un intero.

È possibile denotare `value` un oggetto e lasciare che y sia un Unsigned Integer codificato in `target` , quindi `InPlaceXorLE` esegue un'operazione fornita dalla mappa seguente: $ \ket{y}\rightarrow \ket{y\oplus a} $, dove $ \oplus $ è l'operatore OR esclusivo bit per bit.

## <a name="input"></a>Input

### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Integer considerato non negativo.


### <a name="target--littleendian"></a>destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum usato per archiviare la `value` codifica little-endian.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

