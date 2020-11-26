---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209860"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sposta la rappresentazione bit per bit di un numero a sinistra di un numero specificato di bit.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Input

### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Numero la cui rappresentazione bit per bit deve essere spostata a sinistra (più significativa).


### <a name="amount--int"></a>importo: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit in base al quale deve `value` essere spostato verso sinistra.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore di `value` , spostato a sinistra di `amount` bit.

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```