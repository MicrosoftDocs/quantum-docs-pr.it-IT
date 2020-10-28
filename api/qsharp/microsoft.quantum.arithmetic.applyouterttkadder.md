---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operazione ApplyOuterTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721563"
---
# <a name="applyouterttkadder-operation"></a>Operazione ApplyOuterTTKAdder

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Implementa l'operazione esterna per RippleCarryAdderTTK per coniugare l'operazione interna per costruire la vipera completa.

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderTTK.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530