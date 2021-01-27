---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842103"
---
# <a name="rightshiftedl-function"></a>RightShiftedL (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Input

### <a name="value--bigint"></a>valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).


### <a name="amount--int"></a>importo: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit in base al quale deve `value` essere spostato a destra.



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valore di `value` , spostato a destra di `amount` bit.

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```