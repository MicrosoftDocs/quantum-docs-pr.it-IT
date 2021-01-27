---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845237"
---
# <a name="xbits-function"></a>XBits (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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