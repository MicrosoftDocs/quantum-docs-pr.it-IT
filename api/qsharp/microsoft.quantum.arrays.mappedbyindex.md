---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209928"
---
# <a name="mappedbyindex-function"></a>MappedByIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice e una funzione definita per gli elementi indicizzati della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Input

### <a name="mapper--intt---u"></a>Mapper: ([int](xref:microsoft.quantum.lang-ref.int),' t)->' U

Funzione da `(Int, 'T)` a `'U` utilizzata per eseguire il mapping degli elementi e dei relativi indici.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--u"></a>Output:' U []

Matrice `'U[]` di elementi mappati dalla `mapper` funzione.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.
### <a name="u"></a>' U

Tipo di risultato della `mapper` funzione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. mapping](xref:Microsoft.Quantum.Arrays.Mapped)