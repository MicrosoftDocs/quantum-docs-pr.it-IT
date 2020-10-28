---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Operazione ApplyInnerTTKAdderWithoutCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721647"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>Operazione ApplyInnerTTKAdderWithoutCarry

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Implementa la funzione di addizione interna per l'operazione RippleCarryAdderNoCarryTTK. Si tratta dell'operazione interna che viene coniugata con l'operazione esterna per costruire il Adder completo.

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderNoCarryTTK.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderNoCarryTTK.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

L'operazione controllata specificata si avvale della simmetria e dell'annullamento reciproco delle operazioni per migliorare l'implementazione predefinita che aggiunge un controllo a ogni operazione.

## <a name="references"></a>Riferimenti

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530