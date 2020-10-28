---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funzione ordinata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718887"
---
# <a name="sorted-function"></a>Funzione ordinata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice, restituisce gli elementi di tale matrice ordinati in base a una funzione di confronto specificata.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="comparison--tt---bool"></a>confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione che confronta due elementi, che `a` sono considerati minori o uguali a `b` se `comparison(a, b)` è `true` .


### <a name="array--t"></a>matrice:' t []

Matrice da ordinare.



## <a name="output--t"></a>Output:' t []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `array` .

## <a name="remarks"></a>Commenti

`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone. Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.

Poiché si tratta di una funzione, i risultati sono completamente determinstic, anche quando due elementi sono considerati uguali in, `comparison` ovvero quando `comparison(a, b)` e `comparison(b, a)` sono entrambi `true` .
In particolare, l'ordinamento eseguito da questa funzione è sicuramente stabile, in modo che se due elementi `a` e `b` si verificano in tale ordine all'interno di `array` e sono considerati uguali in `comparison` , viene `a` visualizzato anche prima `b` nell'output.

Ad esempio:

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```