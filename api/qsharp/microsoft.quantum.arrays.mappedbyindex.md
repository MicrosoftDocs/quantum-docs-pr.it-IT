---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845656"
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

## <a name="example"></a>Esempio

Le due righe seguenti sono equivalenti:

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

e

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. mapping](xref:Microsoft.Quantum.Arrays.Mapped)