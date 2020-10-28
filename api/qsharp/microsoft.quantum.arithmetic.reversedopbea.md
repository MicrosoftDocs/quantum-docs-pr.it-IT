---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719694"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA (funzione)

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="op--bigendian--unit-adj"></a>op: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione il cui input deve essere annullato.



## <a name="output--littleendian--unit-adj"></a>Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ADJ [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian

Nuova operazione che accetta l'input come registro little-endian.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. aritmetic. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. aritmetic. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. aritmetic. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)