---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Operazione ApplyReversedOpBECA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721470"
---
# <a name="applyreversedopbeca-operation"></a>Operazione ApplyReversedOpBECA

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="op--bigendian--unit-ctl--adj"></a>op: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Operazione che agisce su un registro big-endian.


### <a name="register--littleendian"></a>registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro Little-Endian da trasformare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. Quantum. aritmetic. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. aritmetic. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)