---
uid: Microsoft.Quantum.Arrays.Mapped
title: Funzione mappata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719079"
---
# <a name="mapped-function"></a>Funzione mappata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice e una funzione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Input

### <a name="mapper--t---u"></a>Mapper:' t->' U

Funzione da `'T` a `'U` utilizzata per eseguire il mapping degli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--u"></a>Output:' U []

Matrice `'U[]` di elementi mappati dalla `mapper` funzione.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.
### <a name="u"></a>' U

Tipo di risultato della `mapper` funzione.

## <a name="remarks"></a>Commenti

La funzione viene definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `mapper: 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .