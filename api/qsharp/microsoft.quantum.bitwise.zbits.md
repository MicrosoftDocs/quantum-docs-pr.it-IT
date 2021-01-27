---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842070"
---
# <a name="zbits-function"></a>ZBits (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce un Integer che rappresenta i bit Z di una matrice di operatori Pauli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di operatori Pauli da rappresentare come Integer.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Integer $x $ con rappresentazione binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, dove $p _i = $0 se `paulis[i]` è `PauliI` o `PauliX` e dove $p _i = $1 se `paulis[i]` è `PauliY` o `PauliZ` .

## <a name="remarks"></a>Commenti

La funzione genererà un'eccezione se la lunghezza della `paulis` matrice è maggiore di 63.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. bit per bit. XBits](xref:Microsoft.Quantum.Bitwise.XBits)