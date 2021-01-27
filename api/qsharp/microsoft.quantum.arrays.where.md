---
uid: Microsoft.Quantum.Arrays.Where
title: Funzione Where
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842211"
---
# <a name="where-function"></a>Funzione Where

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dato un predicato e una matrice, restituisce gli indici della matrice in cui il predicato è true.

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione da `'T` a booleana utilizzata per filtrare gli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di indici in cui `predicate` è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.