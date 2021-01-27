---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833313"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Produce una rappresentazione binaria di un numero intero non negativo, usando la rappresentazione little-endian per la matrice restituita.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Input

### <a name="number--int"></a>numero: [int](xref:microsoft.quantum.lang-ref.int)

Intero non negativo da convertire in una matrice di valori booleani.


### <a name="bits--int"></a>bit: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit nella rappresentazione binaria di `number` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matrice di valori booleani che rappresentano `number` .

## <a name="remarks"></a>Commenti

L'input `bits` deve essere compreso tra 0 e 63.
L'input `number` deve essere compreso tra 0 e $2 ^ {\texttt{BITS}}-$1.