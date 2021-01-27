---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funzione ordinata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845437"
---
# <a name="sorted-function"></a>Funzione ordinata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Esempio

Il frammento di codice seguente ordina una matrice di numeri interi che si verificano in ordine crescente:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Commenti

`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone. Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.

Poiché si tratta di una funzione, i risultati sono completamente determinstic, anche quando due elementi sono considerati uguali in, `comparison` ovvero quando `comparison(a, b)` e `comparison(b, a)` sono entrambi `true` .
In particolare, l'ordinamento eseguito da questa funzione è sicuramente stabile, in modo che se due elementi `a` e `b` si verificano in tale ordine all'interno di `array` e sono considerati uguali in `comparison` , viene `a` visualizzato anche prima `b` nell'output.

Ad esempio:

```qsharp
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