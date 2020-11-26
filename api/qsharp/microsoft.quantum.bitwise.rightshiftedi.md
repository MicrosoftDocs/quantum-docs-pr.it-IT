---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209775"
---
# <a name="rightshiftedi-function"></a>RightShiftedI (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Input

### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).


### <a name="amount--int"></a>importo: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit in base al quale deve `value` essere spostato a destra.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore di `value` , spostato a destra di `amount` bit.

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```