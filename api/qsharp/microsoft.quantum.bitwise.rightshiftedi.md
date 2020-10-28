---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718578"
---
# <a name="rightshiftedi-function"></a>RightShiftedI (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto [](https://nuget.org/packages/)


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