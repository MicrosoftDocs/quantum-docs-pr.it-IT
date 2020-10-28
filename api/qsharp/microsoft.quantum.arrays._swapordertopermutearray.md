---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funzione _SwapOrderToPermuteArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719490"
---
# <a name="_swapordertopermutearray-function"></a>Funzione _SwapOrderToPermuteArray

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

## <a name="psuedocode"></a>Psuedocode

per (index in 0.. length (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}