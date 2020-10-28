---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funzione subarray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718842"
---
# <a name="subarray-function"></a>Funzione subarray

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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