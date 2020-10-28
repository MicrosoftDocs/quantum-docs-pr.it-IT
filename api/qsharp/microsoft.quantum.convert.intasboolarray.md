---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713457"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


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