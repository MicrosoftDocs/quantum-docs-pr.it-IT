---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845643"
---
# <a name="mappedoverrange-function"></a>MappedOverRange (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Esempio

Questo esempio aggiunge 1 a un intervallo di numeri pari:

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio ogni volta che è presente una funzione, è `mapper: Int -> 'T` possibile eseguire il mapping dei valori dell'intervallo e produrre una matrice di tipo `'T[]` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. mapping](xref:Microsoft.Quantum.Arrays.Mapped)