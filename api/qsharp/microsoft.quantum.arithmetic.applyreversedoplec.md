---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Operazione ApplyReversedOpLEC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721446"
---
# <a name="applyreversedoplec-operation"></a>Operazione ApplyReversedOpLEC

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione che accetta input little-endian a un registro che codifica un Unsigned Integer usando il formato big-endian.

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Input

### <a name="op--littleendian--unit-ctl"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL

Operazione che agisce su un registro little-endian.


### <a name="register--bigendian"></a>registra: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registro Big-Endian da trasformare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. ApplyReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [Microsoft. Quantum. aritmetic. ApplyReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [Microsoft. Quantum. aritmetic. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)