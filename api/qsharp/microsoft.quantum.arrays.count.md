---
uid: Microsoft.Quantum.Arrays.Count
title: Count - funzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842843"
---
# <a name="count-function"></a>Count - funzione

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice e un predicato definito per gli elementi della matrice, restituisce il numero di elementi una matrice costituita dagli elementi che soddisfano il predicato.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione da `'T` a booleana utilizzata per filtrare gli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero di elementi in `array` che soddisfano il predicato.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

Nel codice seguente viene illustrata la funzione "count".
Un predicato viene definito utilizzando la @"microsoft.quantum.logical.greaterthani" funzione:

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.