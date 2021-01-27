---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funzione subarray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845427"
---
# <a name="subarray-function"></a>Funzione subarray

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Accetta una matrice e un elenco di percorsi e produce una nuova matrice formata dagli elementi della matrice originale che corrispondono alle posizioni specificate.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="indices--int"></a>indici: [int](xref:microsoft.quantum.lang-ref.int)[]

Elenco di numeri interi utilizzati per definire la sottomatrice.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--t"></a>Output:' t []

Matrice `out` di elementi i cui indici corrispondono alla sottomatrice, in modo tale che `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="remarks"></a>Commenti

La funzione viene definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un elenco di percorsi che `Int[]` definiscono la sottomatrice.
La costruzione della sottomatrice è basata sulla generazione di una nuova copia completa della matrice specificata anziché sulla gestione dei riferimenti.

Se `Length(indices) < Length(array)` , questa funzione restituirà un subset di `array` . D'altra parte, se `indices` contiene elementi ripetuti, verranno ripetuti anche gli elementi corrispondenti di `array` .
Se `indices` e `array` sono della stessa lunghezza, questa funzione fornisce permutazioni di `array` .