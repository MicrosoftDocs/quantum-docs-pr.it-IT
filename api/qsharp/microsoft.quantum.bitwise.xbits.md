---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718563"
---
# <a name="xbits-function"></a>XBits (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto [](https://nuget.org/packages/)


Restituisce un Integer che rappresenta i bit X di una matrice di operatori Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di operatori Pauli da rappresentare come Integer.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Integer $x $ con rappresentazione binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, dove $p _i = $0 se `paulis[i]` è `PauliI` o `PauliZ` e dove $p _i = $1 se `paulis[i]` è `PauliX` o `PauliY` .

## <a name="remarks"></a>Commenti

La funzione genererà un'eccezione se la lunghezza della `paulis` matrice è maggiore di 63.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. bit per bit. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)