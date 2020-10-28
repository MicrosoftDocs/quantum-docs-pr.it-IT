---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operazione CompareUsingRippleCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721275"
---
# <a name="compareusingripplecarry-operation"></a>Operazione CompareUsingRippleCarry

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Questa operazione verifica se un valore Integer rappresentato da un registro di qubits è maggiore di un altro numero intero, applicando un XOR del risultato in un qubit di output.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Dato due integer `x` e `y` archiviati in registri di qubit di dimensioni uguali, questa operazione Controlla se soddisfano `x > y` . Se true, 1 è XORed in un qubit di output. In caso contrario, 0 è XORed in un qubit di output.
In altre parole, questa operazione può essere rappresentata dall'unità $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Input

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Secondo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.


### <a name="output--qubit"></a>output: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit che archivia il risultato del confronto $x>y $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Una nuova Ripple quantistica, il circuito di addizione Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184