---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funzione sorted
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719103"
---
# <a name="issorted-function"></a>Funzione sorted

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice, restituisce un valore che indica se la matrice è ordinata in base a quanto definito da una funzione di confronto specificata.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Input

### <a name="comparison--tt---bool"></a>confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione che confronta due elementi, che `a` sono considerati minori o uguali a `b` se `comparison(a, b)` è `true` .


### <a name="array--t"></a>matrice:' t []

Matrice da verificare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se per ogni coppia di elementi `a` e `b` di `array` si verifica in questo ordine, `comparison(a, b)` è `true` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `array` .

## <a name="remarks"></a>Commenti

`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone. Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.