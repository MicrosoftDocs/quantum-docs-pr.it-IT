---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719043"
---
# <a name="mappedoverrange-function"></a>MappedOverRange (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Dato un intervallo e una funzione che accetta un Integer come input, restituisce una nuova matrice costituita dalle immagini dei valori di intervallo nella funzione.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Input

### <a name="mapper--int---t"></a>Mapper: [int](xref:microsoft.quantum.lang-ref.int) ->' t

Funzione da `Int` a `'T` utilizzata per eseguire il mapping dei valori di intervallo.


### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)

Un intervallo di numeri interi.



## <a name="output--t"></a>Output:' t []

Matrice `'T[]` di elementi mappati dalla `mapper` funzione.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di risultato della `mapper` funzione.

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio ogni volta che è presente una funzione, è `mapper: Int -> 'T` possibile eseguire il mapping dei valori dell'intervallo e produrre una matrice di tipo `'T[]` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. mapping](xref:Microsoft.Quantum.Arrays.Mapped)