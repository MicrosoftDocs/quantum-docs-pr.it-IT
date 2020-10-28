---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718635"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto [](https://nuget.org/packages/)


Sposta la rappresentazione bit per bit di un numero a sinistra di un numero specificato di bit.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Input

### <a name="value--bigint"></a>valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numero la cui rappresentazione bit per bit deve essere spostata a sinistra (più significativa).


### <a name="amount--int"></a>importo: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit in base al quale deve `value` essere spostato verso sinistra.



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valore di `value` , spostato a sinistra di `amount` bit.

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```