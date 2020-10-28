---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funzione filtrata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719271"
---
# <a name="filtered-function"></a>Funzione filtrata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.