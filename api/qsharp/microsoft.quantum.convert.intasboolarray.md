---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224344"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Produce una rappresentazione binaria di un intero positivo, usando la rappresentazione little-endian per la matrice restituita.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Input

### <a name="number--int"></a>numero: [int](xref:microsoft.quantum.lang-ref.int)

Intero positivo da convertire in una matrice di valori booleani.


### <a name="bits--int"></a>bit: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit nella rappresentazione binaria di `number` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matrice di valori booleani che rappresentano `number` .

## <a name="remarks"></a>Commenti

L'input `bits` deve essere compreso tra 0 e 63.
L'input `number` deve essere compreso tra 0 e $2 ^ {\texttt{BITS}}-$1.