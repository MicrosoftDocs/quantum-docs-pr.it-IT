---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funzione filtrata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847153"
---
# <a name="filtered-function"></a>Funzione filtrata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice e un predicato definito per gli elementi della matrice, restituisce una matrice costituita dagli elementi che soddisfano il predicato.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione da `'T` a booleana utilizzata per filtrare gli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--t"></a>Output:' t []

Matrice `'T[]` di elementi che soddisfano il predicato.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

Nel codice seguente viene illustrata la funzione "filtrata".
Un predicato viene definito utilizzando la @"microsoft.quantum.logical.greaterthani" funzione:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

Il risultato previsto da questo esempio sarà una matrice di numeri maggiori di 5.

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.