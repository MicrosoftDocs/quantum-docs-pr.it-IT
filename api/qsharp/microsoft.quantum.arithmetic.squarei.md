---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operazione squarei
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846305"
---
# <a name="squarei-operation"></a>Operazione squarei

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Calcola il quadrato del valore integer `xs` in `result` , che deve essere inizialmente zero.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n il numero di $ bit al quadrato (LittleEndian)


### <a name="result--littleendian"></a>risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

il risultato $2n $-bit (LittleEndian) deve essere in stato inizialmente $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Usa un approccio standard di spostamento e aggiunta per calcolare il quadrato. Salva $n-$1 qubits rispetto alla soluzione diretta che copia prima di tutto XS prima di applicare un moltiplicatore regolare e quindi di eseguire l'operazione di copia.