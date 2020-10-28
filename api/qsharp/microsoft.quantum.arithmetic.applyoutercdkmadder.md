---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operazione ApplyOuterCDKMAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721566"
---
# <a name="applyoutercdkmadder-operation"></a>Operazione ApplyOuterCDKMAdder

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Operazione di ripple sul posto reversibile utilizzata nell'operazione di addizione Integer RippleCarryAdderCDKM di seguito.
Dato due registri qubit `xs` e `ys` della stessa lunghezza, l'operazione applica una sequenza di trascinamento delle Ripple di CNOT e CCNOT Gates con qubits in `xs` e `ys` come controlli e qubits in `xs` come destinazioni.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primo registro qubit, che contiene i controlli e le destinazioni.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Secondo registro qubit, che contribuisce ai controlli.


### <a name="ancilla--qubit"></a>Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1