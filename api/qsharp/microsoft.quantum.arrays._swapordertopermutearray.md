---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funzione _SwapOrderToPermuteArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846300"
---
# <a name="_swapordertopermutearray-function"></a>Funzione _SwapOrderToPermuteArray

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce gli elementi Order in una matrice devono essere scambiati per produrre una matrice ordinata.
Presuppone che si verifichino scambi sul posto.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Input

### <a name="neworder--int"></a>newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice con la permutazione degli indici della nuova matrice. Deve essere presente $n $ Elements, ognuno dei quali è un intero univoco compreso tra $0 $ e $n-$1.



## <a name="output--intint"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

La tupla rappresenta i due indici da scambiare. Gli scambi iniziano in corrispondenza dell'indice più basso.

## <a name="example"></a>Esempio

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Commenti

## <a name="psuedocode"></a>Psuedocode

per (index in 0.. length (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}