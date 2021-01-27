---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operazione CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843279"
---
# <a name="compareusingripplecarry-operation"></a>Operazione CompareUsingRippleCarry

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Questa operazione verifica se un valore Integer rappresentato da un registro di qubits è maggiore di un altro numero intero, applicando un XOR del risultato in un qubit di output.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
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