---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719055"
---
# <a name="mappedbyindex-function"></a>MappedByIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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