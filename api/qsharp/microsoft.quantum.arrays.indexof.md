---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funzione IndexOf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848515"
---
# <a name="indexof-function"></a>Funzione IndexOf

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce il primo indice del primo elemento di una matrice che soddisfa un predicato specificato. Se tale elemento non esiste, restituisce-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione di predicato che agisce sugli elementi della matrice.


### <a name="arr--t"></a>arr:' t []

Matrice da cercare utilizzando il predicato specificato.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Indice più piccolo in `idx` modo che `predicate(arr[idx])` sia true oppure-1 se tale elemento non esiste.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="example"></a>Esempio

Si supponga che `IsEven : Int -> Bool` sia una funzione che restituisce `true` se e solo se l'input è pari. Quindi, può essere usato con `IndexOf` per trovare il primo elemento even in una matrice:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```